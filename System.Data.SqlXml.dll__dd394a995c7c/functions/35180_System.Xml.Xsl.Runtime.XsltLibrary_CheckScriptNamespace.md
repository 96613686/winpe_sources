# System.Xml.Xsl.Runtime.XsltLibrary::CheckScriptNamespace

- ea: `0x35180`
- end: `0x351aa`
- name: `System.Xml.Xsl.Runtime.XsltLibrary::CheckScriptNamespace`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x3780`
- `0x2f330`
- `0x30b70`
- `0x35180`

## string_xrefs

- `0x35193`: `Xslt_ScriptAndExtensionClash`

## pseudocode

```c

```

## disassembly

```asm
0x35180  ldarg.0
0x35181  ldfld    class System.Xml.Xsl.Runtime.XmlQueryRuntime System.Xml.Xsl.Runtime.XsltLibrary::runtime
0x35186  callvirt instance class System.Xml.Xsl.Runtime.XmlQueryContext System.Xml.Xsl.Runtime.XmlQueryRuntime::get_ExternalContext()
0x3518b  ldarg.1
0x3518c  callvirt instance object System.Xml.Xsl.Runtime.XmlQueryContext::GetLateBoundObject(string namespaceUri)
0x35191  brfalse.s loc_351A8
0x35193  ldstr    aXsltScriptande// "Xslt_ScriptAndExtensionClash"
0x35198  ldc.i4.1
0x35199  newarr   [mscorlib]System.String
0x3519e  dup
0x3519f  ldc.i4.0
0x351a0  ldarg.1
0x351a1  stelem.ref
0x351a2  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x351a7  throw
0x351a8  ldc.i4.0
0x351a9  ret
```
