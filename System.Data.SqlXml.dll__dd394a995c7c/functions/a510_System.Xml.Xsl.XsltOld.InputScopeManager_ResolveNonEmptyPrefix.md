# System.Xml.Xsl.XsltOld.InputScopeManager::ResolveNonEmptyPrefix

- ea: `0xa510`
- end: `0xa56b`
- name: `System.Xml.Xsl.XsltOld.InputScopeManager::ResolveNonEmptyPrefix`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0xa570`
- `0xa590`

## callees

- `0x9110`
- `0xa1f0`
- `0xa510`

## string_xrefs

- `0xa524`: `xmlns`
- `0xa530`: `http://www.w3.org/2000/xmlns/`
- `0xa51d`: `http://www.w3.org/XML/1998/namespace`

## pseudocode

```c

```

## disassembly

```asm
0xa510  ldarg.1
0xa511  ldstr    aXml// "xml"
0xa516  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa51b  brfalse.s loc_A523
0xa51d  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0xa522  ret
0xa523  ldarg.1
0xa524  ldstr    aXmlns// "xmlns"
0xa529  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa52e  brfalse.s loc_A536
0xa530  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2000/xmlns/"
0xa535  ret
0xa536  ldarg.0
0xa537  ldfld    class System.Xml.Xsl.XsltOld.InputScope System.Xml.Xsl.XsltOld.InputScopeManager::scopeStack
0xa53c  stloc.0
0xa53d  br.s     loc_A553
0xa53f  ldloc.0
0xa540  ldarg.1
0xa541  callvirt instance string System.Xml.Xsl.XsltOld.DocumentScope::ResolveNonAtom(string prefix)
0xa546  stloc.1
0xa547  ldloc.1
0xa548  brfalse.s loc_A54C
0xa54a  ldloc.1
0xa54b  ret
0xa54c  ldloc.0
0xa54d  callvirt instance class System.Xml.Xsl.XsltOld.InputScope System.Xml.Xsl.XsltOld.InputScope::get_Parent()
0xa552  stloc.0
0xa553  ldloc.0
0xa554  brtrue.s loc_A53F
0xa556  ldstr    aXsltInvalidpre// "Xslt_InvalidPrefix"
0xa55b  ldc.i4.1
0xa55c  newarr   [mscorlib]System.String
0xa561  dup
0xa562  ldc.i4.0
0xa563  ldarg.1
0xa564  stelem.ref
0xa565  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0xa56a  throw
```
