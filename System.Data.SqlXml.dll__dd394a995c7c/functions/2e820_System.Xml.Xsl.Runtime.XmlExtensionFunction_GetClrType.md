# System.Xml.Xsl.Runtime.XmlExtensionFunction::GetClrType

- ea: `0x2e820`
- end: `0x2e85c`
- name: `System.Xml.Xsl.Runtime.XmlExtensionFunction::GetClrType`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x2e620`

## callees

- `0x3780`
- `0x2e820`

## string_xrefs

- `0x2e837`: `XmlIl_ByRefType`

## pseudocode

```c

```

## disassembly

```asm
0x2e820  ldarg.1
0x2e821  callvirt instance bool [mscorlib]System.Type::get_IsEnum()
0x2e826  brfalse.s loc_2E82F
0x2e828  ldarg.1
0x2e829  call     class [mscorlib]System.Type [mscorlib]System.Enum::GetUnderlyingType(class [mscorlib]System.Type)
0x2e82e  ret
0x2e82f  ldarg.1
0x2e830  callvirt instance bool [mscorlib]System.Type::get_IsByRef()
0x2e835  brfalse.s loc_2E85A
0x2e837  ldstr    aXmlilByreftype// "XmlIl_ByRefType"
0x2e83c  ldc.i4.2
0x2e83d  newarr   [mscorlib]System.String
0x2e842  dup
0x2e843  ldc.i4.0
0x2e844  ldarg.0
0x2e845  ldfld    string System.Xml.Xsl.Runtime.XmlExtensionFunction::namespaceUri
0x2e84a  stelem.ref
0x2e84b  dup
0x2e84c  ldc.i4.1
0x2e84d  ldarg.0
0x2e84e  ldfld    string System.Xml.Xsl.Runtime.XmlExtensionFunction::name
0x2e853  stelem.ref
0x2e854  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x2e859  throw
0x2e85a  ldarg.1
0x2e85b  ret
```
