# Microsoft.SharePoint.SPScaleOutDatabase::HandleScaleOutOperationError_0

- ea: `0x8e88d0`
- end: `0x8e8c7a`
- name: `Microsoft.SharePoint.SPScaleOutDatabase::HandleScaleOutOperationError_0`
- size: `938`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x8e84a0`
- `0x8e85e0`

## callees

- `0x1b7de0`
- `0x577070`
- `0x8e88d0`
- `0x93dab0`
- `0x9573f0`

## string_xrefs

- `0x8e892e`: `An attempt has been made to create a data range to the databasewith id {0}. But this range already exists in this database's range mappings.`
- `0x8e8953`: `ScaleOutDatabaseDataRangeAlreadyExists`
- `0x8e897a`: `An attempt has been made to mark a sub-range in database with id {0}, but the specified sub-range point is not in existing range boundaries ofthe database.`
- `0x8e8a12`: `An attempt has been made to convert a deleted sub-range into a different sub-range mode in database with id {0}.`
- `0x8e8a3a`: `ScaleOutDatabaseCannotModifyDeletedSubRange`
- `0x8e8a61`: `An attempt has been made to extend the range in database {0}. But the specified range point is actually inside the existing range.`
- `0x8e8a89`: `ScaleOutDatabaseRangeExtensionInvalid`
- `0x8e8ab0`: `An attempt has been made to extend the range in database {0}. But there is a sub-range on the extended side of the range which is not valid for extension.`
- `0x8e8ad8`: `ScaleOutDatabaseSubRangeInvalidForRangeExtension`
- `0x8e8aff`: `An attempt has been mode to shrink a sub-range in database with id {0}.`
- `0x8e8b4e`: `An attempt has been made to convert a read-only sub-range into a changing sub-range mode in database with id {0}.`
- `0x8e8b76`: `ScaleOutDatabaseCannotChangeReadOnlySubRangeToChanging`
- `0x8e8b9d`: `An attempt has been made to convert a changing sub-range into a read-write sub-range mode in database with id {0}.`
- `0x8e8bc5`: `ScaleOutDatabaseCannotChangeChangingSubRangeToReadWrite`
- `0x8e8bec`: `An attempt has been made to create a new sub-range which is intersecting with an existing sub-range at the opposite half of the range in database with id {0}.`
- `0x8e8c3b`: `An attempt has been made to clear the scale out log in database with id {0} but there are recent log entries in the log.`

## pseudocode

```c

```

## disassembly

```asm
0x8e88d0  ldarg.0
0x8e88d1  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x8e88d6  brfalse  loc_8E8C79
0x8e88db  ldarg.0
0x8e88dc  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x8e88e1  unbox.any [mscorlib]System.Int32
0x8e88e6  stloc.0
0x8e88e7  ldloc.0
0x8e88e8  ldc.i4.s 0xF5
0x8e88ea  sub
0x8e88eb  switch   loc_8E8C2A, loc_8E8BDB, loc_8E8B8C, loc_8E8B3D, loc_8E8AEE, loc_8E8A9F, loc_8E8A50, loc_8E8A01, loc_8E89B5, loc_8E8969, loc_8E891D
0x8e891c  ret
0x8e891d  ldc.i4   0xE3289
0x8e8922  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Database()
0x8e8927  ldc.i4.s 0x14
0x8e8929  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8e892e  ldstr    aAnAttemptHasBe// "An attempt has been made to create a da"...
0x8e8933  ldc.i4.1
0x8e8934  newarr   [mscorlib]System.Object
0x8e8939  stloc.1
0x8e893a  ldloc.1
0x8e893b  ldc.i4.0
0x8e893c  ldarg.1
0x8e893d  box      [mscorlib]System.Guid
0x8e8942  stelem.ref
0x8e8943  ldloc.1
0x8e8944  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8e8949  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x8e894e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x8e8953  ldstr    aScaleoutdataba_2// "ScaleOutDatabaseDataRangeAlreadyExists"
0x8e8958  ldc.i4.0
0x8e8959  newarr   [mscorlib]System.Object
0x8e895e  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x8e8963  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x8e8968  throw
0x8e8969  ldc.i4   0xE328A
0x8e896e  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Database()
0x8e8973  ldc.i4.s 0x14
0x8e8975  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8e897a  ldstr    aAnAttemptHasBe_0// "An attempt has been made to mark a sub-"...
0x8e897f  ldc.i4.1
0x8e8980  newarr   [mscorlib]System.Object
0x8e8985  stloc.2
0x8e8986  ldloc.2
0x8e8987  ldc.i4.0
0x8e8988  ldarg.1
0x8e8989  box      [mscorlib]System.Guid
0x8e898e  stelem.ref
0x8e898f  ldloc.2
0x8e8990  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8e8995  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x8e899a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x8e899f  ldstr    aScaleoutdataba_3// "ScaleOutDatabaseSubRangeViolatesRange"
0x8e89a4  ldc.i4.0
0x8e89a5  newarr   [mscorlib]System.Object
0x8e89aa  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x8e89af  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x8e89b4  throw
0x8e89b5  ldc.i4   0xE328B
0x8e89ba  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Database()
0x8e89bf  ldc.i4.s 0x14
0x8e89c1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8e89c6  ldstr    aAScaleOutOpera// "A scale-out operation has been submitte"...
0x8e89cb  ldc.i4.1
0x8e89cc  newarr   [mscorlib]System.Object
0x8e89d1  stloc.3
0x8e89d2  ldloc.3
0x8e89d3  ldc.i4.0
0x8e89d4  ldarg.1
0x8e89d5  box      [mscorlib]System.Guid
0x8e89da  stelem.ref
0x8e89db  ldloc.3
0x8e89dc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8e89e1  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x8e89e6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x8e89eb  ldstr    aScaleoutdataba_4// "ScaleOutDatabaseExpectedValuesMismatch"
0x8e89f0  ldc.i4.0
0x8e89f1  newarr   [mscorlib]System.Object
0x8e89f6  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x8e89fb  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x8e8a00  throw
0x8e8a01  ldc.i4   0xE328C
0x8e8a06  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Database()
0x8e8a0b  ldc.i4.s 0x14
0x8e8a0d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8e8a12  ldstr    aAnAttemptHasBe_1// "An attempt has been made to convert a d"...
0x8e8a17  ldc.i4.1
0x8e8a18  newarr   [mscorlib]System.Object
0x8e8a1d  stloc.s  4
0x8e8a1f  ldloc.s  4
0x8e8a21  ldc.i4.0
0x8e8a22  ldarg.1
0x8e8a23  box      [mscorlib]System.Guid
0x8e8a28  stelem.ref
0x8e8a29  ldloc.s  4
0x8e8a2b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8e8a30  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x8e8a35  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x8e8a3a  ldstr    aScaleoutdataba_5// "ScaleOutDatabaseCannotModifyDeletedSubR"...
0x8e8a3f  ldc.i4.0
0x8e8a40  newarr   [mscorlib]System.Object
0x8e8a45  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x8e8a4a  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x8e8a4f  throw
0x8e8a50  ldc.i4   0xE328D
0x8e8a55  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Database()
0x8e8a5a  ldc.i4.s 0x14
0x8e8a5c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8e8a61  ldstr    aAnAttemptHasBe_2// "An attempt has been made to extend the "...
0x8e8a66  ldc.i4.1
0x8e8a67  newarr   [mscorlib]System.Object
0x8e8a6c  stloc.s  5
0x8e8a6e  ldloc.s  5
0x8e8a70  ldc.i4.0
0x8e8a71  ldarg.1
0x8e8a72  box      [mscorlib]System.Guid
0x8e8a77  stelem.ref
0x8e8a78  ldloc.s  5
0x8e8a7a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8e8a7f  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x8e8a84  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x8e8a89  ldstr    aScaleoutdataba_6// "ScaleOutDatabaseRangeExtensionInvalid"
0x8e8a8e  ldc.i4.0
0x8e8a8f  newarr   [mscorlib]System.Object
0x8e8a94  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x8e8a99  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x8e8a9e  throw
0x8e8a9f  ldc.i4   0xE328E
0x8e8aa4  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Database()
0x8e8aa9  ldc.i4.s 0x14
0x8e8aab  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8e8ab0  ldstr    aAnAttemptHasBe_3// "An attempt has been made to extend the "...
0x8e8ab5  ldc.i4.1
0x8e8ab6  newarr   [mscorlib]System.Object
0x8e8abb  stloc.s  6
0x8e8abd  ldloc.s  6
0x8e8abf  ldc.i4.0
0x8e8ac0  ldarg.1
0x8e8ac1  box      [mscorlib]System.Guid
0x8e8ac6  stelem.ref
0x8e8ac7  ldloc.s  6
0x8e8ac9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8e8ace  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x8e8ad3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x8e8ad8  ldstr    aScaleoutdataba_7// "ScaleOutDatabaseSubRangeInvalidForRange"...
0x8e8add  ldc.i4.0
0x8e8ade  newarr   [mscorlib]System.Object
0x8e8ae3  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x8e8ae8  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x8e8aed  throw
0x8e8aee  ldc.i4   0xE328F
0x8e8af3  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Database()
0x8e8af8  ldc.i4.s 0x14
0x8e8afa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8e8aff  ldstr    aAnAttemptHasBe_4// "An attempt has been mode to shrink a su"...
0x8e8b04  ldc.i4.1
0x8e8b05  newarr   [mscorlib]System.Object
0x8e8b0a  stloc.s  7
0x8e8b0c  ldloc.s  7
0x8e8b0e  ldc.i4.0
0x8e8b0f  ldarg.1
0x8e8b10  box      [mscorlib]System.Guid
0x8e8b15  stelem.ref
0x8e8b16  ldloc.s  7
0x8e8b18  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8e8b1d  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x8e8b22  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x8e8b27  ldstr    aScaleoutdataba_8// "ScaleOutDatabaseNewSubRangeNotSpansExis"...
0x8e8b2c  ldc.i4.0
0x8e8b2d  newarr   [mscorlib]System.Object
0x8e8b32  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x8e8b37  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x8e8b3c  throw
0x8e8b3d  ldc.i4   0xE3290
0x8e8b42  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Database()
0x8e8b47  ldc.i4.s 0x14
0x8e8b49  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8e8b4e  ldstr    aAnAttemptHasBe_5// "An attempt has been made to convert a r"...
0x8e8b53  ldc.i4.1
0x8e8b54  newarr   [mscorlib]System.Object
0x8e8b59  stloc.s  8
0x8e8b5b  ldloc.s  8
0x8e8b5d  ldc.i4.0
0x8e8b5e  ldarg.1
0x8e8b5f  box      [mscorlib]System.Guid
0x8e8b64  stelem.ref
0x8e8b65  ldloc.s  8
0x8e8b67  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8e8b6c  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x8e8b71  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x8e8b76  ldstr    aScaleoutdataba_9// "ScaleOutDatabaseCannotChangeReadOnlySub"...
0x8e8b7b  ldc.i4.0
0x8e8b7c  newarr   [mscorlib]System.Object
0x8e8b81  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x8e8b86  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x8e8b8b  throw
0x8e8b8c  ldc.i4   0xE3291
0x8e8b91  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Database()
0x8e8b96  ldc.i4.s 0x14
0x8e8b98  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8e8b9d  ldstr    aAnAttemptHasBe_6// "An attempt has been made to convert a c"...
0x8e8ba2  ldc.i4.1
0x8e8ba3  newarr   [mscorlib]System.Object
0x8e8ba8  stloc.s  9
0x8e8baa  ldloc.s  9
0x8e8bac  ldc.i4.0
0x8e8bad  ldarg.1
0x8e8bae  box      [mscorlib]System.Guid
0x8e8bb3  stelem.ref
0x8e8bb4  ldloc.s  9
0x8e8bb6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8e8bbb  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x8e8bc0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x8e8bc5  ldstr    aScaleoutdataba_10// "ScaleOutDatabaseCannotChangeChangingSub"...
0x8e8bca  ldc.i4.0
0x8e8bcb  newarr   [mscorlib]System.Object
0x8e8bd0  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x8e8bd5  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x8e8bda  throw
0x8e8bdb  ldc.i4   0xE3292
0x8e8be0  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Database()
0x8e8be5  ldc.i4.s 0x14
0x8e8be7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8e8bec  ldstr    aAnAttemptHasBe_7// "An attempt has been made to create a ne"...
0x8e8bf1  ldc.i4.1
0x8e8bf2  newarr   [mscorlib]System.Object
0x8e8bf7  stloc.s  0xA
0x8e8bf9  ldloc.s  0xA
0x8e8bfb  ldc.i4.0
0x8e8bfc  ldarg.1
0x8e8bfd  box      [mscorlib]System.Guid
0x8e8c02  stelem.ref
0x8e8c03  ldloc.s  0xA
0x8e8c05  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8e8c0a  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x8e8c0f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x8e8c14  ldstr    aScaleoutdataba_11// "ScaleOutDatabaseNewSubRangeIntersectsEx"...
0x8e8c19  ldc.i4.0
0x8e8c1a  newarr   [mscorlib]System.Object
0x8e8c1f  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x8e8c24  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x8e8c29  throw
0x8e8c2a  ldc.i4   0xE3293
0x8e8c2f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Database()
0x8e8c34  ldc.i4.s 0x14
0x8e8c36  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8e8c3b  ldstr    aAnAttemptHasBe_8// "An attempt has been made to clear the s"...
0x8e8c40  ldc.i4.1
0x8e8c41  newarr   [mscorlib]System.Object
0x8e8c46  stloc.s  0xB
0x8e8c48  ldloc.s  0xB
0x8e8c4a  ldc.i4.0
0x8e8c4b  ldarg.1
0x8e8c4c  box      [mscorlib]System.Guid
0x8e8c51  stelem.ref
0x8e8c52  ldloc.s  0xB
0x8e8c54  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8e8c59  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x8e8c5e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x8e8c63  ldstr    aScaleoutdataba_12// "ScaleOutDatabaseLogCannotBeClearedRecen"...
0x8e8c68  ldc.i4.0
0x8e8c69  newarr   [mscorlib]System.Object
0x8e8c6e  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x8e8c73  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x8e8c78  throw
0x8e8c79  ret
```
