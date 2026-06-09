# System.IO.Packaging.StorageInfo::CreateStream

- ea: `0x46770`
- end: `0x468d8`
- name: `System.IO.Packaging.StorageInfo::CreateStream`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x468e0`

## callees

- `0x28410`
- `0x28500`
- `0x2c100`
- `0x2c130`
- `0x452d0`
- `0x45370`
- `0x45540`
- `0x45680`
- `0x46770`
- `0x46ae0`
- `0x47290`
- `0x477c0`
- `0x47920`
- `0x47c80`
- `0x47cc0`
- `0x48090`
- `0x48790`
- `0x487a0`
- `0x487b0`

## string_xrefs

- `0x467c2`: `StreamAlreadyExist`

## pseudocode

```c

```

## disassembly

```asm
0x46770  ldarg.0
0x46771  call     instance void System.IO.Packaging.StorageInfo::CheckDisposedStatus()
0x46776  ldarg.1
0x46777  brtrue.s loc_46784
0x46779  ldstr    aName_0// "name"
0x4677e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x46783  throw
0x46784  call     class MS.Internal.IO.Packaging.CaseInsensitiveOrdinalStringComparer MS.Internal.IO.Packaging.CompoundFile.ContainerUtilities::get_StringCaseInsensitiveComparer()
0x46789  ldarg.1
0x4678a  call     string System.IO.Packaging.EncryptedPackageEnvelope::get_PackageStreamName()
0x4678f  callvirt instance bool [mscorlib]System.Collections.IEqualityComparer::Equals(object, object)
0x46794  brfalse.s loc_467B0
0x46796  ldstr    aStreamnamenotv// "StreamNameNotValid"
0x4679b  ldc.i4.1
0x4679c  newarr   [mscorlib]System.Object
0x467a1  dup
0x467a2  ldc.i4.0
0x467a3  ldarg.1
0x467a4  stelem.ref
0x467a5  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x467aa  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x467af  throw
0x467b0  ldarg.0
0x467b1  ldarg.1
0x467b2  ldarg.2
0x467b3  ldarg.3
0x467b4  newobj   instance void System.IO.Packaging.StreamInfo::.ctor(class System.IO.Packaging.StorageInfo parent, string streamName, valuetype System.IO.Packaging.CompressionOption compressionOption, valuetype System.IO.Packaging.EncryptionOption encryptionOption)
0x467b9  stloc.0
0x467ba  ldloc.0
0x467bb  callvirt instance bool System.IO.Packaging.StreamInfo::InternalExists()
0x467c0  brfalse.s loc_467D2
0x467c2  ldstr    aStreamalreadye// "StreamAlreadyExist"
0x467c7  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x467cc  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0x467d1  throw
0x467d2  ldarg.0
0x467d3  call     instance class System.IO.Packaging.StorageRoot System.IO.Packaging.StorageInfo::get_Root()
0x467d8  callvirt instance class System.IO.Packaging.DataSpaceManager System.IO.Packaging.StorageRoot::GetDataSpaceManager()
0x467dd  stloc.1
0x467de  ldnull
0x467df  stloc.2
0x467e0  ldloc.1
0x467e1  brfalse  loc_468C2
0x467e6  ldarg.2
0x467e7  ldc.i4.m1
0x467e8  beq.s    loc_46807
0x467ea  ldloc.1
0x467eb  ldsfld   string System.IO.Packaging.StorageInfo::sc_compressionTransformName
0x467f0  callvirt instance bool System.IO.Packaging.DataSpaceManager::TransformLabelIsDefined(string transformLabel)
0x467f5  brtrue.s loc_46807
0x467f7  ldloc.1
0x467f8  call     string MS.Internal.IO.Packaging.CompoundFile.CompressionTransform::get_ClassTransformIdentifier()
0x467fd  ldsfld   string System.IO.Packaging.StorageInfo::sc_compressionTransformName
0x46802  callvirt instance void System.IO.Packaging.DataSpaceManager::DefineTransform(string transformClassName, string newTransformLabel)
0x46807  ldarg.3
0x46808  ldc.i4.1
0x46809  bne.un.s loc_46828
0x4680b  ldloc.1
0x4680c  call     string System.IO.Packaging.EncryptedPackageEnvelope::get_EncryptionTransformName()
0x46811  callvirt instance bool System.IO.Packaging.DataSpaceManager::TransformLabelIsDefined(string transformLabel)
0x46816  brtrue.s loc_46828
0x46818  ldstr    aRightsmanageme// "RightsManagementEncryptionTransformNotF"...
0x4681d  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x46822  newobj   instance void [mscorlib]System.SystemException::.ctor(string)
0x46827  throw
0x46828  ldarg.2
0x46829  ldc.i4.m1
0x4682a  beq.s    loc_46863
0x4682c  ldarg.3
0x4682d  ldc.i4.1
0x4682e  bne.un.s loc_46863
0x46830  ldsfld   string System.IO.Packaging.StorageInfo::sc_dataspaceLabelRMEncryptionNormalCompression
0x46835  stloc.2
0x46836  ldloc.1
0x46837  ldloc.2
0x46838  callvirt instance bool System.IO.Packaging.DataSpaceManager::DataSpaceIsDefined(string dataSpaceLabel)
0x4683d  brtrue   loc_468C2
0x46842  ldc.i4.2
0x46843  newarr   [mscorlib]System.String
0x46848  stloc.3
0x46849  ldloc.3
0x4684a  ldc.i4.0
0x4684b  call     string System.IO.Packaging.EncryptedPackageEnvelope::get_EncryptionTransformName()
0x46850  stelem.ref
0x46851  ldloc.3
0x46852  ldc.i4.1
0x46853  ldsfld   string System.IO.Packaging.StorageInfo::sc_compressionTransformName
0x46858  stelem.ref
0x46859  ldloc.1
0x4685a  ldloc.3
0x4685b  ldloc.2
0x4685c  callvirt instance void System.IO.Packaging.DataSpaceManager::DefineDataSpace(string[] transformStack, string newDataSpaceLabel)
0x46861  br.s     loc_468C2
0x46863  ldarg.2
0x46864  ldc.i4.m1
0x46865  beq.s    loc_46895
0x46867  ldarg.3
0x46868  brtrue.s loc_46895
0x4686a  ldsfld   string System.IO.Packaging.StorageInfo::sc_dataspaceLabelNoEncryptionNormalCompression
0x4686f  stloc.2
0x46870  ldloc.1
0x46871  ldloc.2
0x46872  callvirt instance bool System.IO.Packaging.DataSpaceManager::DataSpaceIsDefined(string dataSpaceLabel)
0x46877  brtrue.s loc_468C2
0x46879  ldc.i4.1
0x4687a  newarr   [mscorlib]System.String
0x4687f  stloc.s  4
0x46881  ldloc.s  4
0x46883  ldc.i4.0
0x46884  ldsfld   string System.IO.Packaging.StorageInfo::sc_compressionTransformName
0x46889  stelem.ref
0x4688a  ldloc.1
0x4688b  ldloc.s  4
0x4688d  ldloc.2
0x4688e  callvirt instance void System.IO.Packaging.DataSpaceManager::DefineDataSpace(string[] transformStack, string newDataSpaceLabel)
0x46893  br.s     loc_468C2
0x46895  ldarg.3
0x46896  ldc.i4.1
0x46897  bne.un.s loc_468C2
0x46899  call     string System.IO.Packaging.EncryptedPackageEnvelope::get_DataspaceLabelRMEncryptionNoCompression()
0x4689e  stloc.2
0x4689f  ldloc.1
0x468a0  ldloc.2
0x468a1  callvirt instance bool System.IO.Packaging.DataSpaceManager::DataSpaceIsDefined(string dataSpaceLabel)
0x468a6  brtrue.s loc_468C2
0x468a8  ldc.i4.1
0x468a9  newarr   [mscorlib]System.String
0x468ae  stloc.s  5
0x468b0  ldloc.s  5
0x468b2  ldc.i4.0
0x468b3  call     string System.IO.Packaging.EncryptedPackageEnvelope::get_EncryptionTransformName()
0x468b8  stelem.ref
0x468b9  ldloc.1
0x468ba  ldloc.s  5
0x468bc  ldloc.2
0x468bd  callvirt instance void System.IO.Packaging.DataSpaceManager::DefineDataSpace(string[] transformStack, string newDataSpaceLabel)
0x468c2  ldloc.2
0x468c3  brtrue.s loc_468CE
0x468c5  ldloc.0
0x468c6  callvirt instance class [mscorlib]System.IO.Stream System.IO.Packaging.StreamInfo::Create()
0x468cb  pop
0x468cc  br.s     loc_468D6
0x468ce  ldloc.0
0x468cf  ldloc.2
0x468d0  callvirt instance class [mscorlib]System.IO.Stream System.IO.Packaging.StreamInfo::Create(string dataSpaceLabel)
0x468d5  pop
0x468d6  ldloc.0
0x468d7  ret
```
