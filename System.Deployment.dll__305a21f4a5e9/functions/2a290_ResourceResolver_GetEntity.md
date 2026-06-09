# ResourceResolver::GetEntity

- ea: `0x2a290`
- end: `0x2a345`
- name: `ResourceResolver::GetEntity`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x23020`
- `0x2a290`

## string_xrefs

- `0x2a2d7`: `df://resources/-//W3C//DTD XMLSCHEMA 200102//EN`
- `0x2a2e9`: `XMLSchema.dtd`

## pseudocode

```c

```

## disassembly

```asm
0x2a290  ldarg.1
0x2a291  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x2a296  ldstr    aDfResources// "df://resources/"
0x2a29b  ldc.i4.4
0x2a29c  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x2a2a1  brfalse  loc_2A33B
0x2a2a6  ldarg.3
0x2a2a7  ldnull
0x2a2a8  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2a2ad  brfalse.s loc_2A2D1
0x2a2af  ldarg.3
0x2a2b0  ldtoken  [mscorlib]System.IO.Stream
0x2a2b5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a2ba  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2a2bf  brfalse.s loc_2A2D1
0x2a2c1  ldstr    aExOnlystreamty// "Ex_OnlyStreamTypeSupported"
0x2a2c6  call     string System.Deployment.Application.Resources::GetString(string s)
0x2a2cb  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string)
0x2a2d0  throw
0x2a2d1  ldarg.1
0x2a2d2  callvirt instance string [mscorlib]System.Object::ToString()
0x2a2d7  ldstr    aDfResourcesW3c// "df://resources/-//W3C//DTD XMLSCHEMA 20"...
0x2a2dc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2a2e1  brfalse.s loc_2A2F4
0x2a2e3  ldarg.0
0x2a2e4  ldfld    class [mscorlib]System.Reflection.Assembly ResourceResolver::_assembly
0x2a2e9  ldstr    aXmlschemaDtd// "XMLSchema.dtd"
0x2a2ee  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.Reflection.Assembly::GetManifestResourceStream(string)
0x2a2f3  ret
0x2a2f4  ldarg.1
0x2a2f5  callvirt instance string [mscorlib]System.Object::ToString()
0x2a2fa  ldstr    aDfResourcesXsD// "df://resources/xs-datatypes"
0x2a2ff  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2a304  brfalse.s loc_2A317
0x2a306  ldarg.0
0x2a307  ldfld    class [mscorlib]System.Reflection.Assembly ResourceResolver::_assembly
0x2a30c  ldstr    aDatatypesDtd// "datatypes.dtd"
0x2a311  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.Reflection.Assembly::GetManifestResourceStream(string)
0x2a316  ret
0x2a317  ldarg.1
0x2a318  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x2a31d  ldc.i4.0
0x2a31e  ldstr    aDfResources// "df://resources/"
0x2a323  call     instance int32 [mscorlib]System.String::get_Length()
0x2a328  callvirt instance string [mscorlib]System.String::Remove(int32, int32)
0x2a32d  stloc.0
0x2a32e  ldarg.0
0x2a32f  ldfld    class [mscorlib]System.Reflection.Assembly ResourceResolver::_assembly
0x2a334  ldloc.0
0x2a335  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.Reflection.Assembly::GetManifestResourceStream(string)
0x2a33a  ret
0x2a33b  ldarg.0
0x2a33c  ldarg.1
0x2a33d  ldarg.2
0x2a33e  ldarg.3
0x2a33f  call     instance object [System.Xml]System.Xml.XmlUrlResolver::GetEntity(class [System]System.Uri, string, class [mscorlib]System.Type)
0x2a344  ret
```
