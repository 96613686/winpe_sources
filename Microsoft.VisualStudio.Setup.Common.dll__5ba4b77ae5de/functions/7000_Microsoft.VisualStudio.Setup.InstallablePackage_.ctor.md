# Microsoft.VisualStudio.Setup.InstallablePackage::.ctor

- ea: `0x7000`
- end: `0x7012`
- name: `Microsoft.VisualStudio.Setup.InstallablePackage::.ctor`
- size: `18`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x46f0`
- `0x4d80`
- `0x6970`
- `0x8fb0`

## callees

- `0x70d0`
- `0x99f0`

## pseudocode

```c

```

## disassembly

```asm
0x7000  ldarg.0
0x7001  call     instance void Microsoft.VisualStudio.Setup.Package::.ctor()
0x7006  ldarg.0
0x7007  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Payload>::.ctor()
0x700c  call     instance void Microsoft.VisualStudio.Setup.InstallablePackage::set_Payloads(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.Payload> value)
0x7011  ret
```
