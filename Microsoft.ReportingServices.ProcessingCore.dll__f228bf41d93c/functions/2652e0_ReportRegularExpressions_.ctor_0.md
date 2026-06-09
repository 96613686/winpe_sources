# ReportRegularExpressions::.ctor_0

- ea: `0x2652e0`
- end: `0x2659e0`
- name: `ReportRegularExpressions::.ctor_0`
- size: `1792`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2659e0`

## callees

- `0x2652e0`

## string_xrefs

- `0x2659bc`: `)|(?<comma>`
- `0x265881`: `RewrittenCommandText\s*$`
- `0x2659a2`: `("(("")|[^"])*")|(?<openParen>`

## pseudocode

```c

```

## disassembly

```asm
0x2652e0  ldarg.0
0x2652e1  call     instance void [mscorlib]System.Object::.ctor()
0x2652e6  ldc.i4.s 0x1D
0x2652e8  stloc.0
0x2652e9  ldarg.0
0x2652ea  ldstr    aS_0// "^\\s*="
0x2652ef  ldloc.0
0x2652f0  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x2652f5  stfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::NonConstant
0x2652fa  ldstr    asc_2A78FE// "-+()#,:&*/\\^<=>"
0x2652ff  call     string [System]System.Text.RegularExpressions.Regex::Escape(string)
0x265304  stloc.1
0x265305  ldstr    asc_2A791E// "!"
0x26530a  call     string [System]System.Text.RegularExpressions.Regex::Escape(string)
0x26530f  stloc.2
0x265310  ldstr    asc_27F114// "."
0x265315  call     string [System]System.Text.RegularExpressions.Regex::Escape(string)
0x26531a  stloc.3
0x26531b  ldstr    asc_298FB4// "["
0x265320  ldloc.2
0x265321  ldloc.3
0x265322  ldstr    asc_28C3A6// "]"
0x265327  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x26532c  stloc.s  4
0x26532e  ldstr    asc_2A9CA0// "(^|["
0x265333  ldloc.1
0x265334  ldstr    aS_2// "\\s])"
0x265339  call     string [mscorlib]System.String::Concat(string, string, string)
0x26533e  stloc.s  5
0x265340  ldc.i4.5
0x265341  newarr   [mscorlib]System.String
0x265346  dup
0x265347  ldc.i4.0
0x265348  ldstr    asc_2A7932// "($|["
0x26534d  stelem.ref
0x26534e  dup
0x26534f  ldc.i4.1
0x265350  ldloc.1
0x265351  stelem.ref
0x265352  dup
0x265353  ldc.i4.2
0x265354  ldloc.2
0x265355  stelem.ref
0x265356  dup
0x265357  ldc.i4.3
0x265358  ldloc.3
0x265359  stelem.ref
0x26535a  dup
0x26535b  ldc.i4.4
0x26535c  ldstr    aS_2// "\\s])"
0x265361  stelem.ref
0x265362  call     string [mscorlib]System.String::Concat(string[])
0x265367  stloc.s  6
0x265369  ldarg.0
0x26536a  ldstr    asc_2A9CAA// "(\"((\"\")|[^\"])*\")|"
0x26536f  ldloc.s  5
0x265371  ldstr    aDetectedFields// "(?<detected>Fields)"
0x265376  ldloc.s  6
0x265378  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x26537d  ldloc.0
0x26537e  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x265383  stfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::FieldDetection
0x265388  ldarg.0
0x265389  ldstr    asc_2A9CAA// "(\"((\"\")|[^\"])*\")|"
0x26538e  ldloc.s  5
0x265390  ldstr    aDetectedReport// "(?<detected>ReportItems)"
0x265395  ldloc.s  6
0x265397  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x26539c  ldloc.0
0x26539d  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x2653a2  stfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::ReportItemsDetection
0x2653a7  ldarg.0
0x2653a8  ldstr    asc_2A9CAA// "(\"((\"\")|[^\"])*\")|"
0x2653ad  ldloc.s  5
0x2653af  ldstr    aDetectedParame// "(?<detected>Parameters)"
0x2653b4  ldloc.s  6
0x2653b6  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x2653bb  ldloc.0
0x2653bc  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x2653c1  stfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::ParametersDetection
0x2653c6  ldarg.0
0x2653c7  ldc.i4.8
0x2653c8  newarr   [mscorlib]System.String
0x2653cd  dup
0x2653ce  ldc.i4.0
0x2653cf  ldstr    asc_2A9CAA// "(\"((\"\")|[^\"])*\")|"
0x2653d4  stelem.ref
0x2653d5  dup
0x2653d6  ldc.i4.1
0x2653d7  ldloc.s  5
0x2653d9  stelem.ref
0x2653da  dup
0x2653db  ldc.i4.2
0x2653dc  ldstr    aDetectedGlobal// "(?<detected>(Globals"
0x2653e1  stelem.ref
0x2653e2  dup
0x2653e3  ldc.i4.3
0x2653e4  ldloc.s  4
0x2653e6  stelem.ref
0x2653e7  dup
0x2653e8  ldc.i4.4
0x2653e9  ldstr    aPagenumberGlob// "PageNumber)|(Globals"
0x2653ee  stelem.ref
0x2653ef  dup
0x2653f0  ldc.i4.5
0x2653f1  ldloc.s  4
0x2653f3  stelem.ref
0x2653f4  dup
0x2653f5  ldc.i4.6
0x2653f6  ldstr    aTotalpages_0// "TotalPages))"
0x2653fb  stelem.ref
0x2653fc  dup
0x2653fd  ldc.i4.7
0x2653fe  ldloc.s  6
0x265400  stelem.ref
0x265401  call     string [mscorlib]System.String::Concat(string[])
0x265406  ldloc.0
0x265407  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x26540c  stfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::PageGlobalsDetection
0x265411  ldarg.0
0x265412  ldstr    asc_2A9CAA// "(\"((\"\")|[^\"])*\")|"
0x265417  ldloc.s  5
0x265419  ldstr    aDetectedAggreg// "(?<detected>Aggregates)"
0x26541e  ldloc.s  6
0x265420  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x265425  ldloc.0
0x265426  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x26542b  stfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::AggregatesDetection
0x265430  ldarg.0
0x265431  ldstr    asc_2A9CAA// "(\"((\"\")|[^\"])*\")|"
0x265436  ldloc.s  5
0x265438  ldstr    aDetectedUser// "(?<detected>User)"
0x26543d  ldloc.s  6
0x26543f  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x265444  ldloc.0
0x265445  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x26544a  stfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::UserDetection
0x26544f  ldarg.0
0x265450  ldstr    asc_2A9CAA// "(\"((\"\")|[^\"])*\")|"
0x265455  ldloc.s  5
0x265457  ldstr    aDetectedDatase// "(?<detected>DataSets)"
0x26545c  ldloc.s  6
0x26545e  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x265463  ldloc.0
0x265464  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x265469  stfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::DataSetsDetection
0x26546e  ldarg.0
0x26546f  ldstr    asc_2A9CAA// "(\"((\"\")|[^\"])*\")|"
0x265474  ldloc.s  5
0x265476  ldstr    aDetectedDataso// "(?<detected>DataSources)"
0x26547b  ldloc.s  6
0x26547d  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x265482  ldloc.0
0x265483  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x265488  stfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::DataSourcesDetection
0x26548d  ldarg.0
0x26548e  ldstr    asc_2A9CAA// "(\"((\"\")|[^\"])*\")|"
0x265493  ldloc.s  5
0x265495  ldstr    aDetectedMeValu// "(?<detected>(?:Me.)?Value)"
0x26549a  ldloc.s  6
0x26549c  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x2654a1  ldloc.0
0x2654a2  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x2654a7  stfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::MeDotValueDetection
0x2654ac  ldstr    asc_27AEB8// ":"
0x2654b1  call     string [System]System.Text.RegularExpressions.Regex::Escape(string)
0x2654b6  stloc.s  7
0x2654b8  ldstr    asc_27F1F4// "#"
0x2654bd  call     string [System]System.Text.RegularExpressions.Regex::Escape(string)
0x2654c2  stloc.s  8
0x2654c4  ldc.i4.7
0x2654c5  newarr   [mscorlib]System.String
0x2654ca  dup
0x2654cb  ldc.i4.0
0x2654cc  ldstr    asc_289678// "("
0x2654d1  stelem.ref
0x2654d2  dup
0x2654d3  ldc.i4.1
0x2654d4  ldloc.s  8
0x2654d6  stelem.ref
0x2654d7  dup
0x2654d8  ldc.i4.2
0x2654d9  ldstr    asc_2A7A02// "[^"
0x2654de  stelem.ref
0x2654df  dup
0x2654e0  ldc.i4.3
0x2654e1  ldloc.s  8
0x2654e3  stelem.ref
0x2654e4  dup
0x2654e5  ldc.i4.4
0x2654e6  ldstr    asc_2A7A08// "]*"
0x2654eb  stelem.ref
0x2654ec  dup
0x2654ed  ldc.i4.5
0x2654ee  ldloc.s  8
0x2654f0  stelem.ref
0x2654f1  dup
0x2654f2  ldc.i4.6
0x2654f3  ldstr    asc_28967C// ")"
0x2654f8  stelem.ref
0x2654f9  call     string [mscorlib]System.String::Concat(string[])
0x2654fe  stloc.s  9
0x265500  ldstr    asc_2A7A0E// ":="
0x265505  call     string [System]System.Text.RegularExpressions.Regex::Escape(string)
0x26550a  stloc.s  0xA
0x26550c  ldarg.0
0x26550d  ldstr    aDetectedU000dU// "(?<detected>(\\u000D\\u000A)|([\\u000D"...
0x265512  ldloc.0
0x265513  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x265518  stfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::LineTerminatorDetection
0x26551d  ldarg.0
0x26551e  ldc.i4.7
0x26551f  newarr   [mscorlib]System.String
0x265524  dup
0x265525  ldc.i4.0
0x265526  ldstr    asc_2A9CAA// "(\"((\"\")|[^\"])*\")|"
0x26552b  stelem.ref
0x26552c  dup
0x26552d  ldc.i4.1
0x26552e  ldloc.s  9
0x265530  stelem.ref
0x265531  dup
0x265532  ldc.i4.2
0x265533  ldstr    asc_2A7A86// "|"
0x265538  stelem.ref
0x265539  dup
0x26553a  ldc.i4.3
0x26553b  ldloc.s  0xA
0x26553d  stelem.ref
0x26553e  dup
0x26553f  ldc.i4.4
0x265540  ldstr    aDetected_2// "|(?<detected>"
0x265545  stelem.ref
0x265546  dup
0x265547  ldc.i4.5
0x265548  ldloc.s  7
0x26554a  stelem.ref
0x26554b  dup
0x26554c  ldc.i4.6
0x26554d  ldstr    asc_28967C// ")"
0x265552  stelem.ref
0x265553  call     string [mscorlib]System.String::Concat(string[])
0x265558  ldloc.0
0x265559  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x26555e  stfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::IllegalCharacterDetection
0x265563  ldstr    aPLuPLlPLtPLmPL_1// "[\\p{Lu}\\p{Ll}\\p{Lt}\\p{Lm}\\p{Lo}\\p"...
0x265568  stloc.s  0xB
0x26556a  ldc.i4.5
0x26556b  newarr   [mscorlib]System.String
0x265570  dup
0x265571  ldc.i4.0
0x265572  ldstr    aReportitems// "ReportItems"
0x265577  stelem.ref
0x265578  dup
0x265579  ldc.i4.1
0x26557a  ldloc.2
0x26557b  stelem.ref
0x26557c  dup
0x26557d  ldc.i4.2
0x26557e  ldstr    aReportitemname_1// "(?<reportitemname>"
0x265583  stelem.ref
0x265584  dup
0x265585  ldc.i4.3
0x265586  ldloc.s  0xB
0x265588  stelem.ref
0x265589  dup
0x26558a  ldc.i4.4
0x26558b  ldstr    asc_28967C// ")"
0x265590  stelem.ref
0x265591  call     string [mscorlib]System.String::Concat(string[])
0x265596  stloc.s  0xC
0x265598  ldc.i4.5
0x265599  newarr   [mscorlib]System.String
0x26559e  dup
0x26559f  ldc.i4.0
0x2655a0  ldstr    aFields_0// "Fields"
0x2655a5  stelem.ref
0x2655a6  dup
0x2655a7  ldc.i4.1
0x2655a8  ldloc.2
0x2655a9  stelem.ref
0x2655aa  dup
0x2655ab  ldc.i4.2
0x2655ac  ldstr    aFieldname_2// "(?<fieldname>"
0x2655b1  stelem.ref
0x2655b2  dup
0x2655b3  ldc.i4.3
0x2655b4  ldloc.s  0xB
0x2655b6  stelem.ref
0x2655b7  dup
0x2655b8  ldc.i4.4
0x2655b9  ldstr    asc_28967C// ")"
0x2655be  stelem.ref
0x2655bf  call     string [mscorlib]System.String::Concat(string[])
0x2655c4  stloc.s  0xD
0x2655c6  ldc.i4.5
0x2655c7  newarr   [mscorlib]System.String
0x2655cc  dup
0x2655cd  ldc.i4.0
0x2655ce  ldstr    aParameters// "Parameters"
  ... truncated ...
```
