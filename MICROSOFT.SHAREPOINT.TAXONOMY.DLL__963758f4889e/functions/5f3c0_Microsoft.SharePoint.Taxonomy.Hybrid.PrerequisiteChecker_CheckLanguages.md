# Microsoft.SharePoint.Taxonomy.Hybrid.PrerequisiteChecker::CheckLanguages

- ea: `0x5f3c0`
- end: `0x5f56c`
- name: `Microsoft.SharePoint.Taxonomy.Hybrid.PrerequisiteChecker::CheckLanguages`
- size: `428`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5f3a0`
- `0x5f3b0`

## callees

- `0x2ad40`
- `0x582f0`
- `0x5a320`
- `0x5f3c0`

## string_xrefs

- `0x5f41d`: `This language : {0} is not installed in local termstore.`
- `0x5f4db`: `This language : {0} is not installed in remote termstore`

## pseudocode

```c

```

## disassembly

```asm
0x5f3c0  ldc.i4   0x120E442
0x5f3c5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5f3ca  ldc.i4.s 0x32
0x5f3cc  ldstr    aStartingToChec// "Starting to check languages between rem"...
0x5f3d1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x5f3d6  ldarg.1
0x5f3d7  brfalse  loc_5F49A
0x5f3dc  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x5f3e1  stloc.0
0x5f3e2  ldarg.0
0x5f3e3  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService Microsoft.SharePoint.Taxonomy.Hybrid.PrerequisiteChecker::remoteService
0x5f3e8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<int32> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::get_Languages()
0x5f3ed  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<int32>::GetEnumerator()
0x5f3f2  stloc.s  4
0x5f3f4  br.s     loc_5F44D
0x5f3f6  ldloc.s  4
0x5f3f8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<int32>::get_Current()
0x5f3fd  stloc.1
0x5f3fe  ldarg.0
0x5f3ff  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.LocalService Microsoft.SharePoint.Taxonomy.Hybrid.PrerequisiteChecker::localService
0x5f404  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<int32> Microsoft.SharePoint.Taxonomy.Hybrid.LocalService::get_Languages()
0x5f409  ldloc.1
0x5f40a  call     T0x2B00008C
0x5f40f  brtrue.s loc_5F44D
0x5f411  ldc.i4   0x120E443
0x5f416  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5f41b  ldc.i4.s 0xA
0x5f41d  ldstr    aThisLanguage0I// "This language : {0} is not installed in"...
0x5f422  ldc.i4.1
0x5f423  newarr   [mscorlib]System.Object
0x5f428  stloc.s  5
0x5f42a  ldloc.s  5
0x5f42c  ldc.i4.0
0x5f42d  ldloc.1
0x5f42e  box      [mscorlib]System.Int32
0x5f433  stelem.ref
0x5f434  ldloc.s  5
0x5f436  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x5f43b  ldloc.0
0x5f43c  ldloca.s 1
0x5f43e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5f443  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x5f448  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5f44d  ldloc.s  4
0x5f44f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5f454  brtrue.s loc_5F3F6
0x5f456  leave.s  loc_5F464
0x5f458  ldloc.s  4
0x5f45a  brfalse.s loc_5F463
0x5f45c  ldloc.s  4
0x5f45e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5f463  endfinally
0x5f464  ldloc.0
0x5f465  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x5f46a  brfalse  loc_5F555
0x5f46f  ldstr    aReplicationdif// "ReplicationDifferentLanguageError"
0x5f474  ldc.i4.1
0x5f475  newarr   [mscorlib]System.Object
0x5f47a  stloc.s  6
0x5f47c  ldloc.s  6
0x5f47e  ldc.i4.0
0x5f47f  ldstr    asc_7D394// " "
0x5f484  ldloc.0
0x5f485  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x5f48a  stelem.ref
0x5f48b  ldloc.s  6
0x5f48d  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x5f492  ldc.i4.s 0xF9
0x5f494  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPException::.ctor(string, int32)
0x5f499  throw
0x5f49a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x5f49f  stloc.2
0x5f4a0  ldarg.0
0x5f4a1  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.LocalService Microsoft.SharePoint.Taxonomy.Hybrid.PrerequisiteChecker::localService
0x5f4a6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<int32> Microsoft.SharePoint.Taxonomy.Hybrid.LocalService::get_Languages()
0x5f4ab  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<int32>::GetEnumerator()
0x5f4b0  stloc.s  7
0x5f4b2  br.s     loc_5F50B
0x5f4b4  ldloc.s  7
0x5f4b6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<int32>::get_Current()
0x5f4bb  stloc.3
0x5f4bc  ldarg.0
0x5f4bd  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService Microsoft.SharePoint.Taxonomy.Hybrid.PrerequisiteChecker::remoteService
0x5f4c2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<int32> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::get_Languages()
0x5f4c7  ldloc.3
0x5f4c8  call     T0x2B00008C
0x5f4cd  brtrue.s loc_5F50B
0x5f4cf  ldc.i4   0x120E444
0x5f4d4  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5f4d9  ldc.i4.s 0xA
0x5f4db  ldstr    aThisLanguage0I_0// "This language : {0} is not installed in"...
0x5f4e0  ldc.i4.1
0x5f4e1  newarr   [mscorlib]System.Object
0x5f4e6  stloc.s  8
0x5f4e8  ldloc.s  8
0x5f4ea  ldc.i4.0
0x5f4eb  ldloc.3
0x5f4ec  box      [mscorlib]System.Int32
0x5f4f1  stelem.ref
0x5f4f2  ldloc.s  8
0x5f4f4  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x5f4f9  ldloc.2
0x5f4fa  ldloca.s 3
0x5f4fc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5f501  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x5f506  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5f50b  ldloc.s  7
0x5f50d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5f512  brtrue.s loc_5F4B4
0x5f514  leave.s  loc_5F522
0x5f516  ldloc.s  7
0x5f518  brfalse.s loc_5F521
0x5f51a  ldloc.s  7
0x5f51c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5f521  endfinally
0x5f522  ldloc.2
0x5f523  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x5f528  brfalse.s loc_5F555
0x5f52a  ldstr    aMigrationdiffe// "MigrationDifferentLanguageError"
0x5f52f  ldc.i4.1
0x5f530  newarr   [mscorlib]System.Object
0x5f535  stloc.s  9
0x5f537  ldloc.s  9
0x5f539  ldc.i4.0
0x5f53a  ldstr    asc_7D394// " "
0x5f53f  ldloc.2
0x5f540  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x5f545  stelem.ref
0x5f546  ldloc.s  9
0x5f548  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x5f54d  ldc.i4.s 0xFA
0x5f54f  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPException::.ctor(string, int32)
0x5f554  throw
0x5f555  ldc.i4   0x120E445
0x5f55a  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5f55f  ldc.i4.s 0x32
0x5f561  ldstr    aFinishedChecki// "Finished checking languages between rem"...
0x5f566  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x5f56b  ret
```
