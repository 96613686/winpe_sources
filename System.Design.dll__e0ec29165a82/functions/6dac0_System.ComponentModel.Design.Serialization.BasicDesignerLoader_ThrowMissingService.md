# System.ComponentModel.Design.Serialization.BasicDesignerLoader::ThrowMissingService

- ea: `0x6dac0`
- end: `0x6daec`
- name: `System.ComponentModel.Design.Serialization.BasicDesignerLoader::ThrowMissingService`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6cf10`

## callees

- `0x8eec0`

## string_xrefs

- `0x6dac0`: `BasicDesignerLoaderMissingService`
- `0x6dae0`: `BasicDesignerLoaderMissingService`

## pseudocode

```c

```

## disassembly

```asm
0x6dac0  ldstr    aBasicdesignerl_2// "BasicDesignerLoaderMissingService"
0x6dac5  ldc.i4.1
0x6dac6  newarr   [mscorlib]System.Object
0x6dacb  dup
0x6dacc  ldc.i4.0
0x6dacd  ldarg.1
0x6dace  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x6dad3  stelem.ref
0x6dad4  call     string System.Design.SR::GetString(string name, object[] args)
0x6dad9  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6dade  stloc.0
0x6dadf  ldloc.0
0x6dae0  ldstr    aBasicdesignerl_2// "BasicDesignerLoaderMissingService"
0x6dae5  callvirt instance void [mscorlib]System.Exception::set_HelpLink(string)
0x6daea  ldloc.0
0x6daeb  throw
```
