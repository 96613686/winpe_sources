# System.ComponentModel.Design.Serialization.CodeDomDesignerLoader::ThrowMissingService

- ea: `0x6ee60`
- end: `0x6ee8c`
- name: `System.ComponentModel.Design.Serialization.CodeDomDesignerLoader::ThrowMissingService`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6ef70`
- `0x6efe0`

## callees

- `0x8eec0`

## string_xrefs

- `0x6ee60`: `BasicDesignerLoaderMissingService`
- `0x6ee80`: `BasicDesignerLoaderMissingService`

## pseudocode

```c

```

## disassembly

```asm
0x6ee60  ldstr    aBasicdesignerl_2// "BasicDesignerLoaderMissingService"
0x6ee65  ldc.i4.1
0x6ee66  newarr   [mscorlib]System.Object
0x6ee6b  dup
0x6ee6c  ldc.i4.0
0x6ee6d  ldarg.1
0x6ee6e  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x6ee73  stelem.ref
0x6ee74  call     string System.Design.SR::GetString(string name, object[] args)
0x6ee79  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6ee7e  stloc.0
0x6ee7f  ldloc.0
0x6ee80  ldstr    aBasicdesignerl_2// "BasicDesignerLoaderMissingService"
0x6ee85  callvirt instance void [mscorlib]System.Exception::set_HelpLink(string)
0x6ee8a  ldloc.0
0x6ee8b  throw
```
