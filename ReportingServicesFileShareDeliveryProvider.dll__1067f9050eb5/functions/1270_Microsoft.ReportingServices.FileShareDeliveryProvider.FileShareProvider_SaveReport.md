# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::SaveReport

- ea: `0x1270`
- end: `0x18dd`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::SaveReport`
- size: `1645`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x6a0`
- `0x850`
- `0x860`
- `0x870`
- `0x890`
- `0x8b0`
- `0x1270`
- `0x1b70`
- `0x1c70`
- `0x1c80`
- `0x1c90`
- `0x1ca0`
- `0x1cb0`
- `0x3740`
- `0x3d00`
- `0x3d60`
- `0x3da0`
- `0x3dd0`
- `0x3de0`
- `0x3df0`
- `0x3e00`

## string_xrefs

- `0x1596`: `Overwrite`

## pseudocode

```c

```

## disassembly

```asm
0x1270  ldarg.2
0x1271  isinst   Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData
0x1276  stloc.0
0x1277  ldstr    aDeviceinfoUsef// "<DeviceInfo>\r\n                       "...
0x127c  stloc.1
0x127d  ldnull
0x127e  stloc.2
0x127f  ldnull
0x1280  stloc.3
0x1281  ldnull
0x1282  stloc.s  4
0x1284  ldc.i4.2
0x1285  stloc.s  5
0x1287  ldarg.1
0x1288  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Report [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::get_Report()
0x128d  ldloc.0
0x128e  callvirt instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_RenderFormat()
0x1293  ldloc.1
0x1294  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.RenderedOutputFile[] [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Report::Render(string, string)
0x1299  stloc.s  6
0x129b  ldc.i4.2
0x129c  stloc.s  7
0x129e  ldstr    asc_5248// ""
0x12a3  stloc.s  8
0x12a5  ldstr    asc_5248// ""
0x12aa  stloc.s  9
0x12ac  ldstr    asc_5248// ""
0x12b1  stloc.s  0xA
0x12b3  ldstr    asc_5248// ""
0x12b8  stloc.s  0xB
0x12ba  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x12bf  stloc.s  0xC
0x12c1  call     native int Microsoft.ReportingServices.FileShareDeliveryProvider.SecuUtil32::GetCurrentThread()
0x12c6  stloc.s  0xD
0x12c8  ldnull
0x12c9  stloc.s  0xE
0x12cb  ldc.i4.0
0x12cc  stloc.s  0xF
0x12ce  ldc.i4.0
0x12cf  stloc.s  0x10
0x12d1  ldloc.s  6
0x12d3  brfalse.s loc_12DA
0x12d5  ldloc.s  6
0x12d7  ldlen
0x12d8  brtrue.s loc_1310
0x12da  ldarg.1
0x12db  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_NoReportData()
0x12e0  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::set_Status(string)
0x12e5  ldarg.1
0x12e6  ldc.i4.0
0x12e7  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::set_Retry(bool)
0x12ec  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_tracer
0x12f1  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x12f6  brfalse  loc_18D7
0x12fb  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_tracer
0x1300  ldc.i4.1
0x1301  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_NoReportData()
0x1306  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x130b  br       loc_18D7
0x1310  ldloc.s  6
0x1312  ldc.i4.0
0x1313  ldelem.ref
0x1314  stloc.s  0x11
0x1316  ldloc.s  0x11
0x1318  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.RenderedOutputFile::get_Data()
0x131d  ldc.i4.0
0x131e  conv.i8
0x131f  ldc.i4.0
0x1320  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x1325  pop
0x1326  ldloc.s  0x11
0x1328  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.RenderedOutputFile::get_Extension()
0x132d  callvirt instance string [mscorlib]System.String::Trim()
0x1332  stloc.s  8
0x1334  ldloc.0
0x1335  callvirt instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_FileName()
0x133a  callvirt instance string [mscorlib]System.String::Trim()
0x133f  stloc.s  0xB
0x1341  ldloc.0
0x1342  callvirt instance bool Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::get_FileExtn()
0x1347  brfalse.s loc_135B
0x1349  ldloc.s  0xB
0x134b  ldstr    asc_524A// "."
0x1350  ldloc.s  8
0x1352  call     string [mscorlib]System.String::Concat(string, string, string)
0x1357  stloc.s  9
0x1359  br.s     loc_135F
0x135b  ldloc.s  0xB
0x135d  stloc.s  9
0x135f  ldstr    aTimestamp// "\\@TimeStamp"
0x1364  ldc.i4.1
0x1365  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x136a  ldloc.s  9
0x136c  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x1371  stloc.s  0x12
0x1373  ldloca.s 0x12
0x1375  ldstr    aYyyyMmDdHhmmss// "yyyy_MM_dd_HHmmss"
0x137a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x137f  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x1384  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1389  callvirt instance string [mscorlib]System.String::ToString(class [mscorlib]System.IFormatProvider)
0x138e  callvirt instance string [System]System.Text.RegularExpressions.Regex::Replace(string, string)
0x1393  stloc.s  9
0x1395  ldloc.0
0x1396  callvirt instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_Path()
0x139b  ldsfld   char [mscorlib]System.IO.Path::DirectorySeparatorChar
0x13a0  stloc.s  0x13
0x13a2  ldloca.s 0x13
0x13a4  call     instance string [mscorlib]System.Char::ToString()
0x13a9  ldloc.s  9
0x13ab  call     string [mscorlib]System.String::Concat(string, string, string)
0x13b0  stloc.s  0xA
0x13b2  ldloc.0
0x13b3  ldloc.s  9
0x13b5  callvirt instance void Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::set_FileName(string value)
0x13ba  call     native int Microsoft.ReportingServices.FileShareDeliveryProvider.SecuUtil32::GetCurrentThread()
0x13bf  ldc.i4.4
0x13c0  ldc.i4.1
0x13c1  ldloca.s 0xC
0x13c3  call     bool Microsoft.ReportingServices.FileShareDeliveryProvider.SecuUtil32::OpenThreadToken([in] native int threadHandle, [in] unsigned int32 DesiredAccess, [in] bool OpenAsSelf, [out] native int& TokenHandle)
0x13c8  brtrue.s loc_13F7
0x13ca  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x13cf  ldc.i4   0x3F0
0x13d4  beq.s    loc_13F7
0x13d6  ldarg.1
0x13d7  ldloc.0
0x13d8  callvirt instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_Path()
0x13dd  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::NetworkError(string path)
0x13e2  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::set_Status(string)
0x13e7  ldarg.1
0x13e8  ldc.i4.1
0x13e9  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::set_Retry(bool)
0x13ee  ldloc.s  0x10
0x13f0  stloc.s  0x15
0x13f2  leave    loc_18DA
0x13f7  ldloc.s  0xC
0x13f9  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x13fe  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x1403  brfalse.s loc_1430
0x1405  call     bool Microsoft.ReportingServices.FileShareDeliveryProvider.SecuUtil32::RevertToSelf()
0x140a  brtrue.s loc_142D
0x140c  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x1411  pop
0x1412  ldarg.1
0x1413  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_ErrorThreadToken()
0x1418  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::set_Status(string)
0x141d  ldarg.1
0x141e  ldc.i4.1
0x141f  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::set_Retry(bool)
0x1424  ldloc.s  0x10
0x1426  stloc.s  0x15
0x1428  leave    loc_18DA
0x142d  ldc.i4.1
0x142e  stloc.s  0xF
0x1430  ldloc.0
0x1431  ldloca.s 0xE
0x1433  call     native int Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::GetTokenHandle(class Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData data, [out] class [ReportingServicesNativeClient]Util.SafeToken& domainImpToken)
0x1438  stloc.s  0x14
0x143a  ldloca.s 0xD
0x143c  ldloc.s  0x14
0x143e  call     bool Microsoft.ReportingServices.FileShareDeliveryProvider.SecuUtil32::SetThreadToken([in] native int& threadHandle, [in] native int TokenHandle)
0x1443  ldc.i4.1
0x1444  stloc.s  0xF
0x1446  brtrue.s loc_146E
0x1448  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x144d  pop
0x144e  ldarg.1
0x144f  ldloc.0
0x1450  callvirt instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_Path()
0x1455  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::NetworkError(string path)
0x145a  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::set_Status(string)
0x145f  ldarg.1
0x1460  ldc.i4.1
0x1461  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::set_Retry(bool)
0x1466  ldc.i4.0
0x1467  stloc.s  0x10
0x1469  br       loc_169C
0x146e  ldloc.s  0xA
0x1470  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x1475  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x147a  brfalse  loc_15B7
0x147f  ldloc.0
0x1480  callvirt instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_WriteMode()
0x1485  brfalse.s loc_149F
0x1487  ldloc.0
0x1488  callvirt instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_WriteMode()
0x148d  callvirt instance string [mscorlib]System.String::Trim()
0x1492  ldstr    aNone// "None"
0x1497  ldc.i4.5
0x1498  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x149d  brfalse.s loc_14BC
0x149f  ldarg.1
0x14a0  ldloc.s  9
0x14a2  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::FileAlreadyExists(string filename)
0x14a7  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::set_Status(string)
0x14ac  ldarg.1
0x14ad  ldc.i4.0
0x14ae  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::set_Retry(bool)
0x14b3  ldloc.s  0x10
0x14b5  stloc.s  0x15
0x14b7  leave    loc_18DA
0x14bc  ldloc.0
0x14bd  callvirt instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_WriteMode()
0x14c2  callvirt instance string [mscorlib]System.String::Trim()
0x14c7  ldstr    aAutoincrement// "AutoIncrement"
0x14cc  ldc.i4.4
0x14cd  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x14d2  brtrue   loc_158B
0x14d7  ldc.i4.1
0x14d8  stloc.s  0x16
0x14da  ldc.i4.1
0x14db  stloc.s  7
0x14dd  br.s     loc_1556
0x14df  ldarg.0
0x14e0  ldloc.s  9
0x14e2  call     instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::GetAutoIncFileName(string filename)
0x14e7  stloc.s  9
0x14e9  ldloc.0
0x14ea  callvirt instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_Path()
0x14ef  ldsfld   char [mscorlib]System.IO.Path::DirectorySeparatorChar
0x14f4  stloc.s  0x13
0x14f6  ldloca.s 0x13
0x14f8  call     instance string [mscorlib]System.Char::ToString()
0x14fd  ldloc.s  9
0x14ff  call     string [mscorlib]System.String::Concat(string, string, string)
0x1504  stloc.s  0xA
0x1506  ldloc.s  0xA
0x1508  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x150d  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x1512  stloc.s  0x16
0x1514  ldloc.s  0x16
0x1516  brtrue.s loc_1556
0x1518  ldloc.s  0xA
0x151a  ldloc.s  7
0x151c  ldloc.s  5
0x151e  newobj   instance void [mscorlib]System.IO.FileStream::.ctor(string, valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess)
0x1523  stloc.s  4
0x1525  leave.s  loc_1556
0x1527  stloc.s  0x17
0x1529  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_tracer
0x152e  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x1533  brfalse.s loc_1551
0x1535  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_tracer
0x153a  ldc.i4.4
0x153b  ldstr    aIoexceptionInA// "IOException in auto increment filename "...
0x1540  ldloc.s  0x17
0x1542  callvirt instance string [mscorlib]System.Object::ToString()
0x1547  call     string [mscorlib]System.String::Concat(string, string)
0x154c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x1551  ldc.i4.1
0x1552  stloc.s  0x16
0x1554  leave.s  loc_1556
0x1556  ldloc.s  0x16
0x1558  brtrue.s loc_14DF
0x155a  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_tracer
0x155f  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x1564  brfalse.s loc_1581
0x1566  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_tracer
0x156b  ldc.i4.3
0x156c  ldstr    aAutoIncrementF// "Auto increment filename = {0}"
0x1571  ldc.i4.1
0x1572  newarr   [mscorlib]System.Object
0x1577  dup
0x1578  ldc.i4.0
0x1579  ldloc.s  9
0x157b  stelem.ref
0x157c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1581  ldloc.0
0x1582  ldloc.s  9
0x1584  callvirt instance void Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::set_FileName(string value)
0x1589  br.s     loc_15B7
0x158b  ldloc.0
0x158c  callvirt instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_WriteMode()
0x1591  callvirt instance string [mscorlib]System.String::Trim()
0x1596  ldstr    aOverwrite_0// "Overwrite"
0x159b  ldc.i4.4
0x159c  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x15a1  brtrue.s loc_15B7
0x15a3  ldc.i4.5
0x15a4  stloc.s  7
0x15a6  ldloc.s  0xA
0x15a8  ldc.i4   0x80
0x15ad  call     void [mscorlib]System.IO.File::SetAttributes(string, valuetype [mscorlib]System.IO.FileAttributes)
0x15b2  leave.s  loc_15B7
0x15b4  pop
0x15b5  leave.s  loc_15B7
0x15b7  ldloc.s  4
0x15b9  brtrue.s loc_15C8
0x15bb  ldloc.s  0xA
0x15bd  ldloc.s  7
0x15bf  ldloc.s  5
0x15c1  newobj   instance void [mscorlib]System.IO.FileStream::.ctor(string, valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess)
0x15c6  stloc.s  4
0x15c8  ldloc.s  0x11
0x15ca  callvirt instance class [mscorlib]System.Text.Encoding [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.RenderedOutputFile::get_Encoding()
0x15cf  brtrue.s loc_160E
0x15d1  ldc.i4   0x10000
0x15d6  newarr   [mscorlib]System.Byte
0x15db  stloc.s  0x19
0x15dd  br.s     loc_15EB
  ... truncated ...
```
