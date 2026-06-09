# Microsoft.VisualStudio.Setup.Security.InvalidSignatureException::TryCreate

- ea: `0x10ac0`
- end: `0x10aeb`
- name: `Microsoft.VisualStudio.Setup.Security.InvalidSignatureException::TryCreate`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x10ac0`
- `0x10af0`
- `0x110c0`
- `0x11120`
- `0x11140`
- `0x11180`
- `0x111d0`

## pseudocode

```c

```

## disassembly

```asm
0x10ac0  ldarg.0
0x10ac1  brfalse.s loc_10AE9
0x10ac3  ldarg.0
0x10ac4  callvirt instance bool Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_HasResources()
0x10ac9  brfalse.s loc_10AE9
0x10acb  ldarg.0
0x10acc  callvirt instance valuetype Microsoft.VisualStudio.Setup.Security.VerificationResult Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_Result()
0x10ad1  ldarg.0
0x10ad2  callvirt instance class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_ResourceManager()
0x10ad7  ldarg.0
0x10ad8  callvirt instance string Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_ResourceId()
0x10add  ldarg.0
0x10ade  callvirt instance object[] Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_TelemetryResourceArgs()
0x10ae3  newobj   instance void Microsoft.VisualStudio.Setup.Security.InvalidSignatureException::.ctor(valuetype Microsoft.VisualStudio.Setup.Security.VerificationResult result, class [mscorlib]System.Resources.ResourceManager resourceManager, string resourceId, object[] args)
0x10ae8  ret
0x10ae9  ldnull
0x10aea  ret
```
