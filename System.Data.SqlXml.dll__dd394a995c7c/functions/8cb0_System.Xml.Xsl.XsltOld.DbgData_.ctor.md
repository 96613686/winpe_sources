# System.Xml.Xsl.XsltOld.DbgData::.ctor

- ea: `0x8cb0`
- end: `0x8cf1`
- name: `System.Xml.Xsl.XsltOld.DbgData::.ctor`
- size: `65`
- prototype: ``
- caller_count: `25`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x543f0`
- `0x54460`
- `0x544d0`
- `0x54540`
- `0x545b0`
- `0x54620`
- `0x54690`
- `0x54700`
- `0x54770`
- `0x547e0`
- `0x54870`
- `0x548d0`
- `0x54940`
- `0x549b0`
- `0x54a20`
- `0x54a90`
- `0x54b70`
- `0x54be0`
- `0x54c60`
- `0x54cd0`
- `0x54d40`
- `0x54dc0`
- `0x54e20`
- `0x54e90`
- `0x54ee0`

## callees

- `0x5af0`
- `0x5b80`
- `0x8c90`
- `0x8dd0`
- `0xa8b0`
- `0x135e0`

## pseudocode

```c

```

## disassembly

```asm
0x8cb0  ldarg.0
0x8cb1  call     instance void [mscorlib]System.Object::.ctor()
0x8cb6  ldarg.1
0x8cb7  castclass System.Xml.Xsl.XsltOld.DbgCompiler
0x8cbc  stloc.0
0x8cbd  ldarg.0
0x8cbe  ldloc.0
0x8cbf  callvirt instance class System.Xml.Xsl.XsltOld.NavigatorInput System.Xml.Xsl.XsltOld.Compiler::get_Input()
0x8cc4  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator System.Xml.Xsl.XsltOld.NavigatorInput::get_Navigator()
0x8cc9  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNavigator::Clone()
0x8cce  stfld    class [System.Xml]System.Xml.XPath.XPathNavigator System.Xml.Xsl.XsltOld.DbgData::styleSheet
0x8cd3  ldarg.0
0x8cd4  ldloc.0
0x8cd5  callvirt instance class System.Xml.Xsl.XsltOld.VariableAction[] System.Xml.Xsl.XsltOld.DbgCompiler::get_LocalVariables()
0x8cda  stfld    class System.Xml.Xsl.XsltOld.VariableAction[] System.Xml.Xsl.XsltOld.DbgData::variables
0x8cdf  ldloc.0
0x8ce0  callvirt instance class System.Xml.Xsl.XsltOld.Debugger.IXsltDebugger System.Xml.Xsl.XsltOld.Compiler::get_Debugger()
0x8ce5  ldarg.0
0x8ce6  call     instance class [System.Xml]System.Xml.XPath.XPathNavigator System.Xml.Xsl.XsltOld.DbgData::get_StyleSheet()
0x8ceb  callvirt instance void System.Xml.Xsl.XsltOld.Debugger.IXsltDebugger::OnInstructionCompile(class [System.Xml]System.Xml.XPath.XPathNavigator styleSheetNavigator)
0x8cf0  ret
```
