# Microsoft.SharePoint.Administration.AppDeployment.Scaffolding.AzureAccount::CreateSecureStoreProvider

- ea: `0x3c6340`
- end: `0x3c68ae`
- name: `Microsoft.SharePoint.Administration.AppDeployment.Scaffolding.AzureAccount::CreateSecureStoreProvider`
- size: `1390`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x3c6080`
- `0x3c6910`
- `0x3c6b00`
- `0x3c6d00`

## callees

- `0x3c0050`
- `0x3c0060`
- `0x3c6340`
- `0x93dab0`
- `0x957770`

## string_xrefs

- `0x3c654c`: `Unable to create an instance of ISecureStoreProvider. Type Name = {0}. {1}`
- `0x3c65ae`: `Unable to create an instance of ISecureStoreProvider. Type Name = {0}. {1}`
- `0x3c6610`: `Unable to create an instance of ISecureStoreProvider. Type Name = {0}. {1}`
- `0x3c6672`: `Unable to create an instance of ISecureStoreProvider. Type Name = {0}. {1}`
- `0x3c66d4`: `Unable to create an instance of ISecureStoreProvider. Type Name = {0}. {1}`
- `0x3c6736`: `Unable to create an instance of ISecureStoreProvider. Type Name = {0}. {1}`
- `0x3c6798`: `Unable to create an instance of ISecureStoreProvider. Type Name = {0}. {1}`
- `0x3c67fa`: `Unable to create an instance of ISecureStoreProvider. Type Name = {0}. {1}`
- `0x3c685c`: `Unable to create an instance of ISecureStoreProvider. Type Name = {0}. {1}`
- `0x3c657a`: `Unable to create an instance of ISecureStoreProvider. Type Name = {0}.`
- `0x3c65dc`: `Unable to create an instance of ISecureStoreProvider. Type Name = {0}.`
- `0x3c663e`: `Unable to create an instance of ISecureStoreProvider. Type Name = {0}.`
- `0x3c66a0`: `Unable to create an instance of ISecureStoreProvider. Type Name = {0}.`
- `0x3c6702`: `Unable to create an instance of ISecureStoreProvider. Type Name = {0}.`
- `0x3c6764`: `Unable to create an instance of ISecureStoreProvider. Type Name = {0}.`
- `0x3c67c6`: `Unable to create an instance of ISecureStoreProvider. Type Name = {0}.`
- `0x3c6828`: `Unable to create an instance of ISecureStoreProvider. Type Name = {0}.`
- `0x3c688a`: `Unable to create an instance of ISecureStoreProvider. Type Name = {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x3c6340  ldnull
0x3c6341  stloc.0
0x3c6342  ldarg.0
0x3c6343  ldc.i4.1
0x3c6344  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string, bool)
0x3c6349  stloc.0
0x3c634a  leave    loc_3C646C
0x3c634f  stloc.1
0x3c6350  ldc.i4   0x6D636937
0x3c6355  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppDeployment()
0x3c635a  ldc.i4.s 0x14
0x3c635c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3c6361  ldstr    aUnableToLoadTh_0// "Unable to load the type. Type Name = {0"...
0x3c6366  ldc.i4.2
0x3c6367  newarr   [mscorlib]System.Object
0x3c636c  stloc.s  0x10
0x3c636e  ldloc.s  0x10
0x3c6370  ldc.i4.0
0x3c6371  ldarg.0
0x3c6372  stelem.ref
0x3c6373  ldloc.s  0x10
0x3c6375  ldc.i4.1
0x3c6376  ldloc.1
0x3c6377  callvirt instance string [mscorlib]System.Object::ToString()
0x3c637c  stelem.ref
0x3c637d  ldloc.s  0x10
0x3c637f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3c6384  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x3c6389  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x3c638e  ldstr    aUnableToLoadTh_1// "Unable to load the type. Type Name = {0"...
0x3c6393  ldc.i4.1
0x3c6394  newarr   [mscorlib]System.Object
0x3c6399  stloc.s  0x11
0x3c639b  ldloc.s  0x11
0x3c639d  ldc.i4.0
0x3c639e  ldarg.0
0x3c639f  stelem.ref
0x3c63a0  ldloc.s  0x11
0x3c63a2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3c63a7  ldloc.1
0x3c63a8  newobj   instance void Microsoft.SharePoint.Administration.AppDeployment.AppDeploymentException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x3c63ad  throw
0x3c63ae  stloc.2
0x3c63af  ldc.i4   0x6D636938
0x3c63b4  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppDeployment()
0x3c63b9  ldc.i4.s 0x14
0x3c63bb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3c63c0  ldstr    aUnableToLoadTh_0// "Unable to load the type. Type Name = {0"...
0x3c63c5  ldc.i4.2
0x3c63c6  newarr   [mscorlib]System.Object
0x3c63cb  stloc.s  0x12
0x3c63cd  ldloc.s  0x12
0x3c63cf  ldc.i4.0
0x3c63d0  ldarg.0
0x3c63d1  stelem.ref
0x3c63d2  ldloc.s  0x12
0x3c63d4  ldc.i4.1
0x3c63d5  ldloc.2
0x3c63d6  callvirt instance string [mscorlib]System.Object::ToString()
0x3c63db  stelem.ref
0x3c63dc  ldloc.s  0x12
0x3c63de  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3c63e3  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x3c63e8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x3c63ed  ldstr    aUnableToLoadTh_1// "Unable to load the type. Type Name = {0"...
0x3c63f2  ldc.i4.1
0x3c63f3  newarr   [mscorlib]System.Object
0x3c63f8  stloc.s  0x13
0x3c63fa  ldloc.s  0x13
0x3c63fc  ldc.i4.0
0x3c63fd  ldarg.0
0x3c63fe  stelem.ref
0x3c63ff  ldloc.s  0x13
0x3c6401  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3c6406  ldloc.2
0x3c6407  newobj   instance void Microsoft.SharePoint.Administration.AppDeployment.AppDeploymentException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x3c640c  throw
0x3c640d  stloc.3
0x3c640e  ldc.i4   0x6D636939
0x3c6413  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppDeployment()
0x3c6418  ldc.i4.s 0x14
0x3c641a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3c641f  ldstr    aUnableToLoadTh_0// "Unable to load the type. Type Name = {0"...
0x3c6424  ldc.i4.2
0x3c6425  newarr   [mscorlib]System.Object
0x3c642a  stloc.s  0x14
0x3c642c  ldloc.s  0x14
0x3c642e  ldc.i4.0
0x3c642f  ldarg.0
0x3c6430  stelem.ref
0x3c6431  ldloc.s  0x14
0x3c6433  ldc.i4.1
0x3c6434  ldloc.3
0x3c6435  callvirt instance string [mscorlib]System.Object::ToString()
0x3c643a  stelem.ref
0x3c643b  ldloc.s  0x14
0x3c643d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3c6442  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x3c6447  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x3c644c  ldstr    aUnableToLoadTh_1// "Unable to load the type. Type Name = {0"...
0x3c6451  ldc.i4.1
0x3c6452  newarr   [mscorlib]System.Object
0x3c6457  stloc.s  0x15
0x3c6459  ldloc.s  0x15
0x3c645b  ldc.i4.0
0x3c645c  ldarg.0
0x3c645d  stelem.ref
0x3c645e  ldloc.s  0x15
0x3c6460  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3c6465  ldloc.3
0x3c6466  newobj   instance void Microsoft.SharePoint.Administration.AppDeployment.AppDeploymentException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x3c646b  throw
0x3c646c  ldloc.0
0x3c646d  ldnull
0x3c646e  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3c6473  brfalse.s loc_3C64C8
0x3c6475  ldc.i4   0x6D636A30
0x3c647a  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppDeployment()
0x3c647f  ldc.i4.s 0x14
0x3c6481  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3c6486  ldstr    aUnableToLoadTh_2// "Unable to load the type. Type Name = {0"...
0x3c648b  ldc.i4.1
0x3c648c  newarr   [mscorlib]System.Object
0x3c6491  stloc.s  0x16
0x3c6493  ldloc.s  0x16
0x3c6495  ldc.i4.0
0x3c6496  ldarg.0
0x3c6497  stelem.ref
0x3c6498  ldloc.s  0x16
0x3c649a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3c649f  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x3c64a4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x3c64a9  ldstr    aUnableToLoadTh_2// "Unable to load the type. Type Name = {0"...
0x3c64ae  ldc.i4.1
0x3c64af  newarr   [mscorlib]System.Object
0x3c64b4  stloc.s  0x17
0x3c64b6  ldloc.s  0x17
0x3c64b8  ldc.i4.0
0x3c64b9  ldarg.0
0x3c64ba  stelem.ref
0x3c64bb  ldloc.s  0x17
0x3c64bd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3c64c2  newobj   instance void Microsoft.SharePoint.Administration.AppDeployment.AppDeploymentException::.ctor(string message)
0x3c64c7  throw
0x3c64c8  ldloc.0
0x3c64c9  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x3c64ce  stloc.s  4
0x3c64d0  ldloc.s  4
0x3c64d2  isinst   [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.SecureStore.ISecureStoreProvider
0x3c64d7  stloc.s  5
0x3c64d9  ldloc.s  5
0x3c64db  brtrue.s loc_3C6530
0x3c64dd  ldc.i4   0x6D636A31
0x3c64e2  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppDeployment()
0x3c64e7  ldc.i4.s 0x14
0x3c64e9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3c64ee  ldstr    aUnableToLoadTh_3// "Unable to load the ISecureStoreProvider"...
0x3c64f3  ldc.i4.1
0x3c64f4  newarr   [mscorlib]System.Object
0x3c64f9  stloc.s  0x18
0x3c64fb  ldloc.s  0x18
0x3c64fd  ldc.i4.0
0x3c64fe  ldarg.0
0x3c64ff  stelem.ref
0x3c6500  ldloc.s  0x18
0x3c6502  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3c6507  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x3c650c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x3c6511  ldstr    aUnableToLoadTh_3// "Unable to load the ISecureStoreProvider"...
0x3c6516  ldc.i4.1
0x3c6517  newarr   [mscorlib]System.Object
0x3c651c  stloc.s  0x19
0x3c651e  ldloc.s  0x19
0x3c6520  ldc.i4.0
0x3c6521  ldarg.0
0x3c6522  stelem.ref
0x3c6523  ldloc.s  0x19
0x3c6525  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3c652a  newobj   instance void Microsoft.SharePoint.Administration.AppDeployment.AppDeploymentException::.ctor(string message)
0x3c652f  throw
0x3c6530  ldloc.s  5
0x3c6532  stloc.s  0xF
0x3c6534  leave    loc_3C68AB
0x3c6539  stloc.s  6
0x3c653b  ldc.i4   0x6D636A32
0x3c6540  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppDeployment()
0x3c6545  ldc.i4.s 0x14
0x3c6547  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3c654c  ldstr    aUnableToCreate_1// "Unable to create an instance of ISecure"...
0x3c6551  ldc.i4.2
0x3c6552  newarr   [mscorlib]System.Object
0x3c6557  stloc.s  0x1A
0x3c6559  ldloc.s  0x1A
0x3c655b  ldc.i4.0
0x3c655c  ldarg.0
0x3c655d  stelem.ref
0x3c655e  ldloc.s  0x1A
0x3c6560  ldc.i4.1
0x3c6561  ldloc.s  6
0x3c6563  callvirt instance string [mscorlib]System.Object::ToString()
0x3c6568  stelem.ref
0x3c6569  ldloc.s  0x1A
0x3c656b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3c6570  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x3c6575  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x3c657a  ldstr    aUnableToCreate_2// "Unable to create an instance of ISecure"...
0x3c657f  ldc.i4.1
0x3c6580  newarr   [mscorlib]System.Object
0x3c6585  stloc.s  0x1B
0x3c6587  ldloc.s  0x1B
0x3c6589  ldc.i4.0
0x3c658a  ldarg.0
0x3c658b  stelem.ref
0x3c658c  ldloc.s  0x1B
0x3c658e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3c6593  ldloc.s  6
0x3c6595  newobj   instance void Microsoft.SharePoint.Administration.AppDeployment.AppDeploymentException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x3c659a  throw
0x3c659b  stloc.s  7
0x3c659d  ldc.i4   0x6D636A33
0x3c65a2  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppDeployment()
0x3c65a7  ldc.i4.s 0x14
0x3c65a9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3c65ae  ldstr    aUnableToCreate_1// "Unable to create an instance of ISecure"...
0x3c65b3  ldc.i4.2
0x3c65b4  newarr   [mscorlib]System.Object
0x3c65b9  stloc.s  0x1C
0x3c65bb  ldloc.s  0x1C
0x3c65bd  ldc.i4.0
0x3c65be  ldarg.0
0x3c65bf  stelem.ref
0x3c65c0  ldloc.s  0x1C
0x3c65c2  ldc.i4.1
0x3c65c3  ldloc.s  7
0x3c65c5  callvirt instance string [mscorlib]System.Object::ToString()
0x3c65ca  stelem.ref
0x3c65cb  ldloc.s  0x1C
0x3c65cd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3c65d2  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x3c65d7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x3c65dc  ldstr    aUnableToCreate_2// "Unable to create an instance of ISecure"...
0x3c65e1  ldc.i4.1
0x3c65e2  newarr   [mscorlib]System.Object
0x3c65e7  stloc.s  0x1D
0x3c65e9  ldloc.s  0x1D
0x3c65eb  ldc.i4.0
0x3c65ec  ldarg.0
0x3c65ed  stelem.ref
0x3c65ee  ldloc.s  0x1D
0x3c65f0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3c65f5  ldloc.s  7
0x3c65f7  newobj   instance void Microsoft.SharePoint.Administration.AppDeployment.AppDeploymentException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x3c65fc  throw
0x3c65fd  stloc.s  8
0x3c65ff  ldc.i4   0x6D636A34
0x3c6604  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppDeployment()
0x3c6609  ldc.i4.s 0x14
0x3c660b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3c6610  ldstr    aUnableToCreate_1// "Unable to create an instance of ISecure"...
0x3c6615  ldc.i4.2
0x3c6616  newarr   [mscorlib]System.Object
0x3c661b  stloc.s  0x1E
0x3c661d  ldloc.s  0x1E
0x3c661f  ldc.i4.0
0x3c6620  ldarg.0
0x3c6621  stelem.ref
0x3c6622  ldloc.s  0x1E
0x3c6624  ldc.i4.1
0x3c6625  ldloc.s  8
0x3c6627  callvirt instance string [mscorlib]System.Object::ToString()
0x3c662c  stelem.ref
0x3c662d  ldloc.s  0x1E
0x3c662f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3c6634  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x3c6639  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x3c663e  ldstr    aUnableToCreate_2// "Unable to create an instance of ISecure"...
0x3c6643  ldc.i4.1
0x3c6644  newarr   [mscorlib]System.Object
0x3c6649  stloc.s  0x1F
0x3c664b  ldloc.s  0x1F
0x3c664d  ldc.i4.0
0x3c664e  ldarg.0
0x3c664f  stelem.ref
0x3c6650  ldloc.s  0x1F
0x3c6652  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3c6657  ldloc.s  8
0x3c6659  newobj   instance void Microsoft.SharePoint.Administration.AppDeployment.AppDeploymentException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x3c665e  throw
0x3c665f  stloc.s  9
0x3c6661  ldc.i4   0x6D636A35
0x3c6666  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppDeployment()
0x3c666b  ldc.i4.s 0x14
0x3c666d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3c6672  ldstr    aUnableToCreate_1// "Unable to create an instance of ISecure"...
0x3c6677  ldc.i4.2
0x3c6678  newarr   [mscorlib]System.Object
0x3c667d  stloc.s  0x20
0x3c667f  ldloc.s  0x20
0x3c6681  ldc.i4.0
0x3c6682  ldarg.0
  ... truncated ...
```
