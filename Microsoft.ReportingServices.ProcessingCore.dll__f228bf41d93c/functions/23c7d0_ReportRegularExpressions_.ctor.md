# ReportRegularExpressions::.ctor

- ea: `0x23c7d0`
- end: `0x23da76`
- name: `ReportRegularExpressions::.ctor`
- size: `4774`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x23dae0`

## callees

- `0x23da80`

## string_xrefs

- `0x23d643`: `CreateDrillthroughContext`
- `0x23cfe9`: `(?<scopename>`
- `0x23d3a6`: `(?<scopename>`
- `0x23d524`: `RewrittenCommandText`
- `0x23d9e7`: `("(("")|[^"])*")|('.*)|(?<openParen>`
- `0x23da01`: `)|(?<openCurly>`
- `0x23da1b`: `)|(?<comma>`

## pseudocode

```c

```

## disassembly

```asm
0x23c7d0  ldarg.0
0x23c7d1  call     instance void [mscorlib]System.Object::.ctor()
0x23c7d6  ldc.i4.s 0x1C
0x23c7d8  stloc.0
0x23c7d9  ldarg.0
0x23c7da  ldstr    aS_0// "^\\s*="
0x23c7df  ldloc.0
0x23c7e0  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x23c7e5  stfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::NonConstant
0x23c7ea  ldstr    asc_2A78FE// "-+()#,:&*/\\^<=>"
0x23c7ef  call     string [System]System.Text.RegularExpressions.Regex::Escape(string)
0x23c7f4  stloc.1
0x23c7f5  ldstr    asc_2A791E// "!"
0x23c7fa  call     string [System]System.Text.RegularExpressions.Regex::Escape(string)
0x23c7ff  stloc.2
0x23c800  ldstr    asc_27F114// "."
0x23c805  call     string [System]System.Text.RegularExpressions.Regex::Escape(string)
0x23c80a  stloc.3
0x23c80b  ldstr    asc_298FB4// "["
0x23c810  ldloc.2
0x23c811  ldloc.3
0x23c812  ldstr    asc_28C3A6// "]"
0x23c817  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x23c81c  stloc.s  4
0x23c81e  ldstr    asc_298FB4// "["
0x23c823  ldloc.1
0x23c824  ldstr    aS_1// "\\s]"
0x23c829  call     string [mscorlib]System.String::Concat(string, string, string)
0x23c82e  stloc.s  5
0x23c830  ldstr    asc_2A792A// "(^|"
0x23c835  ldloc.s  5
0x23c837  ldstr    asc_28967C// ")"
0x23c83c  call     string [mscorlib]System.String::Concat(string, string, string)
0x23c841  stloc.s  6
0x23c843  ldc.i4.5
0x23c844  newarr   [mscorlib]System.String
0x23c849  dup
0x23c84a  ldc.i4.0
0x23c84b  ldstr    asc_2A7932// "($|["
0x23c850  stelem.ref
0x23c851  dup
0x23c852  ldc.i4.1
0x23c853  ldloc.1
0x23c854  stelem.ref
0x23c855  dup
0x23c856  ldc.i4.2
0x23c857  ldloc.2
0x23c858  stelem.ref
0x23c859  dup
0x23c85a  ldc.i4.3
0x23c85b  ldloc.3
0x23c85c  stelem.ref
0x23c85d  dup
0x23c85e  ldc.i4.4
0x23c85f  ldstr    aS_2// "\\s])"
0x23c864  stelem.ref
0x23c865  call     string [mscorlib]System.String::Concat(string[])
0x23c86a  stloc.s  7
0x23c86c  ldstr    asc_2A7932// "($|["
0x23c871  ldloc.1
0x23c872  ldloc.3
0x23c873  ldstr    aS_2// "\\s])"
0x23c878  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x23c87d  stloc.s  8
0x23c87f  ldstr    aFields_0// "Fields"
0x23c884  call     string ReportRegularExpressions::CaseInsensitive(string input)
0x23c889  stloc.s  9
0x23c88b  ldstr    aValue// "Value"
0x23c890  call     string ReportRegularExpressions::CaseInsensitive(string input)
0x23c895  stloc.s  0xA
0x23c897  ldstr    aScopes// "Scopes"
0x23c89c  call     string ReportRegularExpressions::CaseInsensitive(string input)
0x23c8a1  stloc.s  0xB
0x23c8a3  ldstr    aReportitems// "ReportItems"
0x23c8a8  call     string ReportRegularExpressions::CaseInsensitive(string input)
0x23c8ad  stloc.s  0xC
0x23c8af  ldstr    aParameters// "Parameters"
0x23c8b4  call     string ReportRegularExpressions::CaseInsensitive(string input)
0x23c8b9  stloc.s  0xD
0x23c8bb  ldstr    aGlobals// "Globals"
0x23c8c0  call     string ReportRegularExpressions::CaseInsensitive(string input)
0x23c8c5  stloc.s  0xE
0x23c8c7  ldstr    aRenderformat// "RenderFormat"
0x23c8cc  call     string ReportRegularExpressions::CaseInsensitive(string input)
0x23c8d1  stloc.s  0xF
0x23c8d3  ldstr    aOveralltotalpa// "OverallTotalPages"
0x23c8d8  call     string ReportRegularExpressions::CaseInsensitive(string input)
0x23c8dd  stloc.s  0x10
0x23c8df  ldstr    aTotalpages// "TotalPages"
0x23c8e4  call     string ReportRegularExpressions::CaseInsensitive(string input)
0x23c8e9  stloc.s  0x11
0x23c8eb  ldstr    aDatasets// "DataSets"
0x23c8f0  call     string ReportRegularExpressions::CaseInsensitive(string input)
0x23c8f5  stloc.s  0x12
0x23c8f7  ldstr    aDatasources// "DataSources"
0x23c8fc  call     string ReportRegularExpressions::CaseInsensitive(string input)
0x23c901  stloc.s  0x13
0x23c903  ldstr    aVariables// "Variables"
0x23c908  call     string ReportRegularExpressions::CaseInsensitive(string input)
0x23c90d  stloc.s  0x14
0x23c90f  ldstr    aMe// "Me"
0x23c914  call     string ReportRegularExpressions::CaseInsensitive(string input)
0x23c919  stloc.s  0x15
0x23c91b  ldstr    aItem// "Item"
0x23c920  call     string ReportRegularExpressions::CaseInsensitive(string input)
0x23c925  stloc.s  0x16
0x23c927  ldstr    aInscope// "InScope"
0x23c92c  call     string ReportRegularExpressions::CaseInsensitive(string input)
0x23c931  stloc.s  0x17
0x23c933  ldstr    aLevel// "Level"
0x23c938  call     string ReportRegularExpressions::CaseInsensitive(string input)
0x23c93d  stloc.s  0x18
0x23c93f  ldarg.0
0x23c940  ldc.i4.6
0x23c941  newarr   [mscorlib]System.String
0x23c946  dup
0x23c947  ldc.i4.0
0x23c948  ldstr    asc_2A794C// "(\"((\"\")|[^\"])*\")|('.*)|"
0x23c94d  stelem.ref
0x23c94e  dup
0x23c94f  ldc.i4.1
0x23c950  ldloc.s  6
0x23c952  stelem.ref
0x23c953  dup
0x23c954  ldc.i4.2
0x23c955  ldstr    aDetected_0// "(?<detected>"
0x23c95a  stelem.ref
0x23c95b  dup
0x23c95c  ldc.i4.3
0x23c95d  ldloc.s  9
0x23c95f  stelem.ref
0x23c960  dup
0x23c961  ldc.i4.4
0x23c962  ldstr    asc_28967C// ")"
0x23c967  stelem.ref
0x23c968  dup
0x23c969  ldc.i4.5
0x23c96a  ldloc.s  7
0x23c96c  stelem.ref
0x23c96d  call     string [mscorlib]System.String::Concat(string[])
0x23c972  ldloc.0
0x23c973  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x23c978  stfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::FieldDetection
0x23c97d  ldarg.0
0x23c97e  ldc.i4.6
0x23c97f  newarr   [mscorlib]System.String
0x23c984  dup
0x23c985  ldc.i4.0
0x23c986  ldstr    asc_2A794C// "(\"((\"\")|[^\"])*\")|('.*)|"
0x23c98b  stelem.ref
0x23c98c  dup
0x23c98d  ldc.i4.1
0x23c98e  ldloc.s  6
0x23c990  stelem.ref
0x23c991  dup
0x23c992  ldc.i4.2
0x23c993  ldstr    aDetected_0// "(?<detected>"
0x23c998  stelem.ref
0x23c999  dup
0x23c99a  ldc.i4.3
0x23c99b  ldloc.s  0xB
0x23c99d  stelem.ref
0x23c99e  dup
0x23c99f  ldc.i4.4
0x23c9a0  ldstr    asc_28967C// ")"
0x23c9a5  stelem.ref
0x23c9a6  dup
0x23c9a7  ldc.i4.5
0x23c9a8  ldloc.s  7
0x23c9aa  stelem.ref
0x23c9ab  call     string [mscorlib]System.String::Concat(string[])
0x23c9b0  ldloc.0
0x23c9b1  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x23c9b6  stfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::ScopesDetection
0x23c9bb  ldarg.0
0x23c9bc  ldc.i4.6
0x23c9bd  newarr   [mscorlib]System.String
0x23c9c2  dup
0x23c9c3  ldc.i4.0
0x23c9c4  ldstr    asc_2A794C// "(\"((\"\")|[^\"])*\")|('.*)|"
0x23c9c9  stelem.ref
0x23c9ca  dup
0x23c9cb  ldc.i4.1
0x23c9cc  ldloc.s  6
0x23c9ce  stelem.ref
0x23c9cf  dup
0x23c9d0  ldc.i4.2
0x23c9d1  ldstr    aDetected_0// "(?<detected>"
0x23c9d6  stelem.ref
0x23c9d7  dup
0x23c9d8  ldc.i4.3
0x23c9d9  ldloc.s  0xC
0x23c9db  stelem.ref
0x23c9dc  dup
0x23c9dd  ldc.i4.4
0x23c9de  ldstr    asc_28967C// ")"
0x23c9e3  stelem.ref
0x23c9e4  dup
0x23c9e5  ldc.i4.5
0x23c9e6  ldloc.s  7
0x23c9e8  stelem.ref
0x23c9e9  call     string [mscorlib]System.String::Concat(string[])
0x23c9ee  ldloc.0
0x23c9ef  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x23c9f4  stfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::ReportItemsDetection
0x23c9f9  ldarg.0
0x23c9fa  ldc.i4.6
0x23c9fb  newarr   [mscorlib]System.String
0x23ca00  dup
0x23ca01  ldc.i4.0
0x23ca02  ldstr    asc_2A794C// "(\"((\"\")|[^\"])*\")|('.*)|"
0x23ca07  stelem.ref
0x23ca08  dup
0x23ca09  ldc.i4.1
0x23ca0a  ldloc.s  6
0x23ca0c  stelem.ref
0x23ca0d  dup
0x23ca0e  ldc.i4.2
0x23ca0f  ldstr    aDetected_0// "(?<detected>"
0x23ca14  stelem.ref
0x23ca15  dup
0x23ca16  ldc.i4.3
0x23ca17  ldloc.s  0xD
0x23ca19  stelem.ref
0x23ca1a  dup
0x23ca1b  ldc.i4.4
0x23ca1c  ldstr    asc_28967C// ")"
0x23ca21  stelem.ref
0x23ca22  dup
0x23ca23  ldc.i4.5
0x23ca24  ldloc.s  7
0x23ca26  stelem.ref
0x23ca27  call     string [mscorlib]System.String::Concat(string[])
0x23ca2c  ldloc.0
0x23ca2d  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x23ca32  stfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::ParametersDetection
0x23ca37  ldarg.0
0x23ca38  ldc.i4.8
0x23ca39  newarr   [mscorlib]System.String
0x23ca3e  dup
0x23ca3f  ldc.i4.0
0x23ca40  ldstr    asc_2A794C// "(\"((\"\")|[^\"])*\")|('.*)|"
0x23ca45  stelem.ref
0x23ca46  dup
0x23ca47  ldc.i4.1
0x23ca48  ldloc.s  6
0x23ca4a  stelem.ref
0x23ca4b  dup
0x23ca4c  ldc.i4.2
0x23ca4d  ldstr    aDetected_1// "(?<detected>("
0x23ca52  stelem.ref
0x23ca53  dup
0x23ca54  ldc.i4.3
0x23ca55  ldloc.s  0xE
0x23ca57  stelem.ref
0x23ca58  dup
0x23ca59  ldc.i4.4
0x23ca5a  ldloc.s  4
0x23ca5c  stelem.ref
0x23ca5d  dup
0x23ca5e  ldc.i4.5
0x23ca5f  ldloc.s  0xF
0x23ca61  stelem.ref
0x23ca62  dup
0x23ca63  ldc.i4.6
0x23ca64  ldloc.s  7
0x23ca66  stelem.ref
0x23ca67  dup
0x23ca68  ldc.i4.7
0x23ca69  ldstr    asc_2A79B2// "))"
0x23ca6e  stelem.ref
0x23ca6f  call     string [mscorlib]System.String::Concat(string[])
0x23ca74  ldloc.0
0x23ca75  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x23ca7a  stfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::RenderFormatAnyDetection
0x23ca7f  ldarg.0
0x23ca80  ldc.i4.s 0xC
0x23ca82  newarr   [mscorlib]System.String
0x23ca87  dup
0x23ca88  ldc.i4.0
0x23ca89  ldstr    asc_2A794C// "(\"((\"\")|[^\"])*\")|('.*)|"
0x23ca8e  stelem.ref
0x23ca8f  dup
0x23ca90  ldc.i4.1
0x23ca91  ldloc.s  6
0x23ca93  stelem.ref
0x23ca94  dup
0x23ca95  ldc.i4.2
0x23ca96  ldstr    aDetected_1// "(?<detected>("
0x23ca9b  stelem.ref
0x23ca9c  dup
0x23ca9d  ldc.i4.3
0x23ca9e  ldloc.s  0xE
0x23caa0  stelem.ref
0x23caa1  dup
0x23caa2  ldc.i4.4
0x23caa3  ldloc.s  4
0x23caa5  stelem.ref
0x23caa6  dup
0x23caa7  ldc.i4.5
  ... truncated ...
```
