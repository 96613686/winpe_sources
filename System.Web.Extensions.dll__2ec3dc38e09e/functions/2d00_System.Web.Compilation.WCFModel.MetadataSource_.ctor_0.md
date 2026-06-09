# System.Web.Compilation.WCFModel.MetadataSource::.ctor_0

- ea: `0x2d00`
- end: `0x2d68`
- name: `System.Web.Compilation.WCFModel.MetadataSource::.ctor_0`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x2d00`
- `0x2b990`
- `0x2b9b0`
- `0x2ba70`

## string_xrefs

- `0x2d09`: `protocol`

## pseudocode

```c

```

## disassembly

```asm
0x2d00  ldarg.0
0x2d01  call     instance void [mscorlib]System.Object::.ctor()
0x2d06  ldarg.1
0x2d07  brtrue.s loc_2D14
0x2d09  ldstr    aProtocol// "protocol"
0x2d0e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2d13  throw
0x2d14  ldarg.2
0x2d15  brtrue.s loc_2D22
0x2d17  ldstr    aAddress// "address"
0x2d1c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2d21  throw
0x2d22  ldarg.1
0x2d23  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2d28  brtrue.s loc_2D35
0x2d2a  call     string System.Web.Resources.WCFModelStrings::get_ReferenceGroup_EmptyProtocol()
0x2d2f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2d34  throw
0x2d35  ldarg.2
0x2d36  brtrue.s loc_2D43
0x2d38  call     string System.Web.Resources.WCFModelStrings::get_ReferenceGroup_EmptyAddress()
0x2d3d  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2d42  throw
0x2d43  ldarg.0
0x2d44  ldarg.1
0x2d45  stfld    string System.Web.Compilation.WCFModel.MetadataSource::m_Protocol
0x2d4a  ldarg.0
0x2d4b  ldarg.2
0x2d4c  stfld    string System.Web.Compilation.WCFModel.MetadataSource::m_Address
0x2d51  ldarg.3
0x2d52  ldc.i4.0
0x2d53  bge.s    loc_2D60
0x2d55  call     string System.Web.Resources.WCFModelStrings::get_ReferenceGroup_InvalidSourceId()
0x2d5a  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2d5f  throw
0x2d60  ldarg.0
0x2d61  ldarg.3
0x2d62  stfld    int32 System.Web.Compilation.WCFModel.MetadataSource::m_SourceId
0x2d67  ret
```
