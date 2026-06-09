# Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::RunCsomQueryWithRetries

- ea: `0x25480`
- end: `0x2550d`
- name: `Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::RunCsomQueryWithRetries`
- size: `141`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xc6c0`
- `0xd6e0`
- `0x3a180`
- `0x3a660`
- `0x5a4a0`

## callees

- `0x25480`

## string_xrefs

- `0x25484`: `maxAttempts`
- `0x254a8`: `Exception occurred when run the csom query. Attempt times: {0}, exception: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x25480  ldarg.1
0x25481  ldc.i4.1
0x25482  bge.s    loc_2548F
0x25484  ldstr    aMaxattempts// "maxAttempts"
0x25489  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x2548e  throw
0x2548f  ldc.i4.1
0x25490  stloc.0
0x25491  br.s     loc_25508
0x25493  ldarg.0
0x25494  callvirt instance void [mscorlib]System.Action::Invoke()
0x25499  leave.s  loc_2550C
0x2549b  stloc.1
0x2549c  ldc.i4   0x1597554
0x254a1  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x254a6  ldc.i4.s 0xA
0x254a8  ldstr    aExceptionOccur// "Exception occurred when run the csom qu"...
0x254ad  ldc.i4.2
0x254ae  newarr   [mscorlib]System.Object
0x254b3  stloc.2
0x254b4  ldloc.2
0x254b5  ldc.i4.0
0x254b6  ldloc.0
0x254b7  box      [mscorlib]System.Int32
0x254bc  stelem.ref
0x254bd  ldloc.2
0x254be  ldc.i4.1
0x254bf  ldloc.1
0x254c0  callvirt instance string [mscorlib]System.Object::ToString()
0x254c5  stelem.ref
0x254c6  ldloc.2
0x254c7  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x254cc  ldloc.1
0x254cd  isinst   [System]System.Net.WebException
0x254d2  brtrue.s loc_254DC
0x254d4  ldloc.1
0x254d5  isinst   [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException
0x254da  brfalse.s loc_25506
0x254dc  ldloc.0
0x254dd  dup
0x254de  ldc.i4.1
0x254df  add.ovf
0x254e0  stloc.0
0x254e1  ldarg.1
0x254e2  bge.s    loc_25506
0x254e4  ldc.i4   0x1597555
0x254e9  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x254ee  ldc.i4.s 0xF
0x254f0  ldstr    aGetWebexceptio// "Get WebException or ServerException. Wi"...
0x254f5  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x254fa  ldc.i4   0x1388
0x254ff  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x25504  leave.s  loc_25508
0x25506  rethrow
0x25508  ldloc.0
0x25509  ldarg.1
0x2550a  ble.s    loc_25493
0x2550c  ret
```
