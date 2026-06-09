# Microsoft.BIServer.HostingEnvironment.Logger::DeleteExpiredFilesInternal

- ea: `0x16d0`
- end: `0x1764`
- name: `Microsoft.BIServer.HostingEnvironment.Logger::DeleteExpiredFilesInternal`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x16a0`

## callees

- `0x1550`
- `0x15b0`
- `0x1680`
- `0x16d0`
- `0x1cd0`
- `0x1cf0`

## pseudocode

```c

```

## disassembly

```asm
0x16d0  ldarg.1
0x16d1  ldsfld   class [mscorlib]System.Func`2<class [mscorlib]System.IO.FileInfo, class Microsoft.BIServer.HostingEnvironment.LogFileInfo> <>c::<>9__74_0
0x16d6  dup
0x16d7  brtrue.s loc_16F0
0x16d9  pop
0x16da  ldsfld   class <>c <>c::<>9
0x16df  ldftn    instance class Microsoft.BIServer.HostingEnvironment.LogFileInfo <>c::<DeleteExpiredFilesInternal>b__74_0(class [mscorlib]System.IO.FileInfo fileInfo)
0x16e5  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.IO.FileInfo, class Microsoft.BIServer.HostingEnvironment.LogFileInfo>::.ctor(object, native int)
0x16ea  dup
0x16eb  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.IO.FileInfo, class Microsoft.BIServer.HostingEnvironment.LogFileInfo> <>c::<>9__74_0
0x16f0  call     T0x2B00000F
0x16f5  ldarg.0
0x16f6  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.HostingEnvironment.LogFileInfo> Microsoft.BIServer.HostingEnvironment.Logger::GetExpiredLogFiles(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.HostingEnvironment.LogFileInfo> logFiles, int32 keepUntilDays)
0x16fb  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.HostingEnvironment.LogFileInfo>::GetEnumerator()
0x1700  stloc.0
0x1701  br.s     loc_174F
0x1703  ldloc.0
0x1704  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.BIServer.HostingEnvironment.LogFileInfo>::get_Current()
0x1709  stloc.1
0x170a  ldstr    aDeletingExpire// "Deleting expired log file: {0} Last wri"...
0x170f  ldc.i4.2
0x1710  newarr   [mscorlib]System.Object
0x1715  dup
0x1716  ldc.i4.0
0x1717  ldloc.1
0x1718  callvirt instance string Microsoft.BIServer.HostingEnvironment.LogFileInfo::get_FullName()
0x171d  stelem.ref
0x171e  dup
0x171f  ldc.i4.1
0x1720  ldloc.1
0x1721  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.BIServer.HostingEnvironment.LogFileInfo::get_LastWriteTime()
0x1726  box      [mscorlib]System.DateTime
0x172b  stelem.ref
0x172c  call     void Microsoft.BIServer.HostingEnvironment.Logger::Info(string formatString, object[] formatParams)
0x1731  ldloc.1
0x1732  callvirt instance string Microsoft.BIServer.HostingEnvironment.LogFileInfo::get_FullName()
0x1737  call     void [mscorlib]System.IO.File::Delete(string)
0x173c  leave.s  loc_174F
0x173e  ldstr    aExceptionDelet// "Exception deleting expired log file"
0x1743  call     T0x2B00000A
0x1748  call     void Microsoft.BIServer.HostingEnvironment.Logger::Warning(class [mscorlib]System.Exception ex, string formatString, object[] formatParams)
0x174d  leave.s  loc_174F
0x174f  ldloc.0
0x1750  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1755  brtrue.s loc_1703
0x1757  leave.s  loc_1763
0x1759  ldloc.0
0x175a  brfalse.s loc_1762
0x175c  ldloc.0
0x175d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1762  endfinally
0x1763  ret
```
