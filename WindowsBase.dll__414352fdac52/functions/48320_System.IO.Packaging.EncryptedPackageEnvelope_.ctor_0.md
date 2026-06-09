# System.IO.Packaging.EncryptedPackageEnvelope::.ctor_0

- ea: `0x48320`
- end: `0x48377`
- name: `System.IO.Packaging.EncryptedPackageEnvelope::.ctor_0`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x484b0`

## callees

- `0x2c100`
- `0x47440`
- `0x47490`
- `0x48320`
- `0x487c0`
- `0x48a20`
- `0x48ab0`

## string_xrefs

- `0x48357`: `StreamNeedsReadWriteAccess`

## pseudocode

```c

```

## disassembly

```asm
0x48320  ldarg.0
0x48321  call     instance void [mscorlib]System.Object::.ctor()
0x48326  ldarg.1
0x48327  brtrue.s loc_48334
0x48329  ldstr    aEnvelopestream// "envelopeStream"
0x4832e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x48333  throw
0x48334  ldarg.0
0x48335  ldarg.2
0x48336  ldarg.3
0x48337  call     instance void System.IO.Packaging.EncryptedPackageEnvelope::ThrowIfRMEncryptionInfoInvalid(class System.Security.RightsManagement.PublishLicense publishLicense, class System.Security.RightsManagement.CryptoProvider cryptoProvider)
0x4833c  ldarg.0
0x4833d  ldarg.1
0x4833e  ldc.i4.2
0x4833f  call     class System.IO.Packaging.StorageRoot System.IO.Packaging.StorageRoot::CreateOnStream(class [mscorlib]System.IO.Stream baseStream, valuetype [mscorlib]System.IO.FileMode mode)
0x48344  stfld    class System.IO.Packaging.StorageRoot System.IO.Packaging.EncryptedPackageEnvelope::_root
0x48349  ldarg.0
0x4834a  ldfld    class System.IO.Packaging.StorageRoot System.IO.Packaging.EncryptedPackageEnvelope::_root
0x4834f  callvirt instance valuetype [mscorlib]System.IO.FileAccess System.IO.Packaging.StorageRoot::get_OpenAccess()
0x48354  ldc.i4.3
0x48355  beq.s    loc_48367
0x48357  ldstr    aStreamneedsrea// "StreamNeedsReadWriteAccess"
0x4835c  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x48361  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x48366  throw
0x48367  ldarg.0
0x48368  ldarg.2
0x48369  ldarg.3
0x4836a  call     instance void System.IO.Packaging.EncryptedPackageEnvelope::InitializeRMForCreate(class System.Security.RightsManagement.PublishLicense publishLicense, class System.Security.RightsManagement.CryptoProvider cryptoProvider)
0x4836f  ldarg.0
0x48370  ldnull
0x48371  call     instance void System.IO.Packaging.EncryptedPackageEnvelope::EmbedPackage(class [mscorlib]System.IO.Stream packageStream)
0x48376  ret
```
