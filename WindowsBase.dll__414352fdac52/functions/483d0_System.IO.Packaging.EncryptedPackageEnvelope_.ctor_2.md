# System.IO.Packaging.EncryptedPackageEnvelope::.ctor_2

- ea: `0x483d0`
- end: `0x48437`
- name: `System.IO.Packaging.EncryptedPackageEnvelope::.ctor_2`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x484d0`

## callees

- `0x2c100`
- `0x47440`
- `0x47490`
- `0x483d0`
- `0x487c0`
- `0x48a20`
- `0x48ab0`

## string_xrefs

- `0x48416`: `StreamNeedsReadWriteAccess`

## pseudocode

```c

```

## disassembly

```asm
0x483d0  ldarg.0
0x483d1  call     instance void [mscorlib]System.Object::.ctor()
0x483d6  ldarg.1
0x483d7  brtrue.s loc_483E4
0x483d9  ldstr    aEnvelopestream// "envelopeStream"
0x483de  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x483e3  throw
0x483e4  ldarg.2
0x483e5  brtrue.s loc_483F2
0x483e7  ldstr    aPackagestream// "packageStream"
0x483ec  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x483f1  throw
0x483f2  ldarg.0
0x483f3  ldarg.3
0x483f4  ldarg.s  4
0x483f6  call     instance void System.IO.Packaging.EncryptedPackageEnvelope::ThrowIfRMEncryptionInfoInvalid(class System.Security.RightsManagement.PublishLicense publishLicense, class System.Security.RightsManagement.CryptoProvider cryptoProvider)
0x483fb  ldarg.0
0x483fc  ldarg.1
0x483fd  ldc.i4.2
0x483fe  call     class System.IO.Packaging.StorageRoot System.IO.Packaging.StorageRoot::CreateOnStream(class [mscorlib]System.IO.Stream baseStream, valuetype [mscorlib]System.IO.FileMode mode)
0x48403  stfld    class System.IO.Packaging.StorageRoot System.IO.Packaging.EncryptedPackageEnvelope::_root
0x48408  ldarg.0
0x48409  ldfld    class System.IO.Packaging.StorageRoot System.IO.Packaging.EncryptedPackageEnvelope::_root
0x4840e  callvirt instance valuetype [mscorlib]System.IO.FileAccess System.IO.Packaging.StorageRoot::get_OpenAccess()
0x48413  ldc.i4.3
0x48414  beq.s    loc_48426
0x48416  ldstr    aStreamneedsrea// "StreamNeedsReadWriteAccess"
0x4841b  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x48420  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x48425  throw
0x48426  ldarg.0
0x48427  ldarg.3
0x48428  ldarg.s  4
0x4842a  call     instance void System.IO.Packaging.EncryptedPackageEnvelope::InitializeRMForCreate(class System.Security.RightsManagement.PublishLicense publishLicense, class System.Security.RightsManagement.CryptoProvider cryptoProvider)
0x4842f  ldarg.0
0x48430  ldarg.2
0x48431  call     instance void System.IO.Packaging.EncryptedPackageEnvelope::EmbedPackage(class [mscorlib]System.IO.Stream packageStream)
0x48436  ret
```
