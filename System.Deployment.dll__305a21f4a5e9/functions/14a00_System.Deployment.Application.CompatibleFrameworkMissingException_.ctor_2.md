# System.Deployment.Application.CompatibleFrameworkMissingException::.ctor_2

- ea: `0x14a00`
- end: `0x14a29`
- name: `System.Deployment.Application.CompatibleFrameworkMissingException::.ctor_2`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14920`

## string_xrefs

- `0x14a0a`: `_compatibleFrameworks`

## pseudocode

```c

```

## disassembly

```asm
0x14a00  ldarg.0
0x14a01  ldarg.1
0x14a02  ldarg.2
0x14a03  call     instance void System.Deployment.Application.DependentPlatformMissingException::.ctor(class [mscorlib]System.Runtime.Serialization.SerializationInfo serializationInfo, valuetype [mscorlib]System.Runtime.Serialization.StreamingContext streamingContext)
0x14a08  ldarg.0
0x14a09  ldarg.1
0x14a0a  ldstr    aCompatiblefram// "_compatibleFrameworks"
0x14a0f  ldtoken  System.Deployment.Application.CompatibleFrameworks
0x14a14  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14a19  callvirt instance object [mscorlib]System.Runtime.Serialization.SerializationInfo::GetValue(string, class [mscorlib]System.Type)
0x14a1e  castclass System.Deployment.Application.CompatibleFrameworks
0x14a23  stfld    class System.Deployment.Application.CompatibleFrameworks System.Deployment.Application.CompatibleFrameworkMissingException::_compatibleFrameworks
0x14a28  ret
```
