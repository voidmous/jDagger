

# Info

* [Grand – ggTools: Grand](https://ant-grand.github.io/Grand/grand.html "")
* [Ant-Grand/Grand: Graphical Representation of ANt Dependencies](https://github.com/Ant-Grand/Grand "")

# Intro

To visualize `build.xml`, create Ant file `grand-visual.xml`:

```xml
<?xml version="1.0"?>
<project name="Grand" basedir="." default="grand">

	<typedef resource="net/ggtools/grand/antlib.xml" classpath="grand-1.9.5.jar" />

	<target name="grand">
		<grand output="build.dot" buildfile="build.xml" />
		<exec executable="dot">
		  <arg line="-Tpdf -Gsize=11.69,8.27 -Grotate=90 -o build.pdf build.dot" />
		</exec>
	</target>

</project>
```

Run `ant -file grand-visual.xml grand` to generate `.dot` and `.pdf` file.



# Reference

* [Ant Task Dependency Graphs](https://javaranch.com/journal/200711/ant_dependency_graph.html "")

