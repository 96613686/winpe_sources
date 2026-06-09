# System.Deployment.Application.CompatibleFrameworkMissingException::GetObjectData

- ea: `0x14a50`
- end: `0x14a6a`
- name: `System.Deployment.Application.CompatibleFrameworkMissingException::GetObjectData`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14980`

## string_xrefs

- `0x14a59`: `_compatibleFrameworks`

## pseudocode

```c

```

## disassembly

```asm
0x14a50  ldarg.0
0x14a51  ldarg.1
0x14a52  ldarg.2
0x14a53  call     instance void System.Deployment.Application.DependentPlatformMissingException::GetObjectData(class [mscorlib]System.Runtime.Serialization.SerializationInfo info, valuetype [mscorlib]System.Runtime.Serialization.StreamingContext context)
0x14a58  ldarg.1
0x14a59  ldstr    aCompatiblefram// "_compatibleFrameworks"
0x14a5e  ldarg.0
0x14a5f  ldfld    class System.Deployment.Application.CompatibleFrameworks System.Deployment.Application.CompatibleFrameworkMissingException::_compatibleFrameworks
0x14a64  callvirt instance void [mscorlib]System.Runtime.Serialization.SerializationInfo::AddValue(string, object)
0x14a69  ret
```
