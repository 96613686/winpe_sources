# <>c__DisplayClass70_0::<CreateFileListener>b__0

- ea: `0x18280`
- end: `0x1845a`
- name: `<>c__DisplayClass70_0::<CreateFileListener>b__0`
- size: `474`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x117c0`
- `0x16850`
- `0x170f0`
- `0x18280`

## pseudocode

```c

```

## disassembly

```asm
0x18280  ldarg.0
0x18281  ldfld    class RSWPTraceInternal <>c__DisplayClass70_0::<>4__this
0x18286  ldfld    string RSWPTraceInternal::m_traceFileName
0x1828b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x18290  brtrue.s loc_182A8
0x18292  ldarg.0
0x18293  ldfld    class RSWPTraceInternal <>c__DisplayClass70_0::<>4__this
0x18298  ldarg.0
0x18299  ldfld    class RSWPTraceInternal <>c__DisplayClass70_0::<>4__this
0x1829e  ldfld    string RSWPTraceInternal::m_CachedProcessName
0x182a3  stfld    string RSWPTraceInternal::m_traceFileName
0x182a8  ldarg.0
0x182a9  ldfld    class RSWPTraceInternal <>c__DisplayClass70_0::<>4__this
0x182ae  ldfld    valuetype TraceFileMode RSWPTraceInternal::m_TraceFileMode
0x182b3  brtrue   loc_1836C
0x182b8  ldarg.0
0x182b9  ldfld    class RSWPTraceInternal <>c__DisplayClass70_0::<>4__this
0x182be  ldarg.0
0x182bf  ldfld    class RSWPTraceInternal <>c__DisplayClass70_0::<>4__this
0x182c4  ldfld    int32 RSWPTraceInternal::m_keepFileForDays
0x182c9  call     instance void RSWPTraceInternal::CleanOldFiles(int32 daysToKeep)
0x182ce  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x182d3  stloc.2
0x182d4  ldarg.0
0x182d5  ldfld    class RSWPTraceInternal <>c__DisplayClass70_0::<>4__this
0x182da  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x182df  ldstr    a01230040050060// "{0}\\{1}_{2}_{3:00}_{4:00}_{5:00}_{6:00"...
0x182e4  ldc.i4.8
0x182e5  newarr   [mscorlib]System.Object
0x182ea  dup
0x182eb  ldc.i4.0
0x182ec  ldarg.0
0x182ed  ldfld    class RSWPTraceInternal <>c__DisplayClass70_0::<>4__this
0x182f2  callvirt instance string Microsoft.ReportingServices.Diagnostics.Utilities.RSTraceInternal::get_TraceDirectory()
0x182f7  stelem.ref
0x182f8  dup
0x182f9  ldc.i4.1
0x182fa  ldarg.0
0x182fb  ldfld    class RSWPTraceInternal <>c__DisplayClass70_0::<>4__this
0x18300  ldfld    string RSWPTraceInternal::m_traceFileName
0x18305  stelem.ref
0x18306  dup
0x18307  ldc.i4.2
0x18308  ldloca.s 2
0x1830a  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x1830f  box      [mscorlib]System.Int32
0x18314  stelem.ref
0x18315  dup
0x18316  ldc.i4.3
0x18317  ldloca.s 2
0x18319  call     instance int32 [mscorlib]System.DateTime::get_Month()
0x1831e  box      [mscorlib]System.Int32
0x18323  stelem.ref
0x18324  dup
0x18325  ldc.i4.4
0x18326  ldloca.s 2
0x18328  call     instance int32 [mscorlib]System.DateTime::get_Day()
0x1832d  box      [mscorlib]System.Int32
0x18332  stelem.ref
0x18333  dup
0x18334  ldc.i4.5
0x18335  ldloca.s 2
0x18337  call     instance int32 [mscorlib]System.DateTime::get_Hour()
0x1833c  box      [mscorlib]System.Int32
0x18341  stelem.ref
0x18342  dup
0x18343  ldc.i4.6
0x18344  ldloca.s 2
0x18346  call     instance int32 [mscorlib]System.DateTime::get_Minute()
0x1834b  box      [mscorlib]System.Int32
0x18350  stelem.ref
0x18351  dup
0x18352  ldc.i4.7
0x18353  ldloca.s 2
0x18355  call     instance int32 [mscorlib]System.DateTime::get_Second()
0x1835a  box      [mscorlib]System.Int32
0x1835f  stelem.ref
0x18360  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x18365  stfld    string RSWPTraceInternal::m_TraceFilePath
0x1836a  br.s     loc_1839C
0x1836c  ldarg.0
0x1836d  ldfld    class RSWPTraceInternal <>c__DisplayClass70_0::<>4__this
0x18372  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18377  ldstr    a01Log// "{0}\\{1}.log"
0x1837c  ldarg.0
0x1837d  ldfld    class RSWPTraceInternal <>c__DisplayClass70_0::<>4__this
0x18382  callvirt instance string Microsoft.ReportingServices.Diagnostics.Utilities.RSTraceInternal::get_TraceDirectory()
0x18387  ldarg.0
0x18388  ldfld    class RSWPTraceInternal <>c__DisplayClass70_0::<>4__this
0x1838d  ldfld    string RSWPTraceInternal::m_traceFileName
0x18392  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x18397  stfld    string RSWPTraceInternal::m_TraceFilePath
0x1839c  ldc.i4.2
0x1839d  stloc.0
0x1839e  ldnull
0x1839f  stloc.1
0x183a0  ldarg.0
0x183a1  ldfld    class RSWPTraceInternal <>c__DisplayClass70_0::<>4__this
0x183a6  ldfld    valuetype TraceFileMode RSWPTraceInternal::m_TraceFileMode
0x183ab  ldc.i4.2
0x183ac  bne.un.s loc_183B0
0x183ae  ldc.i4.6
0x183af  stloc.0
0x183b0  nop
0x183b1  ldarg.0
0x183b2  ldfld    class RSWPTraceInternal <>c__DisplayClass70_0::<>4__this
0x183b7  ldfld    string RSWPTraceInternal::m_TraceFilePath
0x183bc  ldloc.0
0x183bd  ldc.i4.2
0x183be  ldc.i4.3
0x183bf  call     class [mscorlib]System.IO.FileStream [mscorlib]System.IO.File::Open(string, valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess, valuetype [mscorlib]System.IO.FileShare)
0x183c4  stloc.1
0x183c5  leave.s  loc_183F1
0x183c7  pop
0x183c8  ldarg.0
0x183c9  ldfld    class RSWPTraceInternal <>c__DisplayClass70_0::<>4__this
0x183ce  ldfld    valuetype TraceFileMode RSWPTraceInternal::m_TraceFileMode
0x183d3  ldc.i4.1
0x183d4  bne.un.s loc_183EA
0x183d6  ldarg.0
0x183d7  ldfld    class RSWPTraceInternal <>c__DisplayClass70_0::<>4__this
0x183dc  ldfld    string RSWPTraceInternal::m_TraceFilePath
0x183e1  ldc.i4.6
0x183e2  ldc.i4.2
0x183e3  ldc.i4.3
0x183e4  call     class [mscorlib]System.IO.FileStream [mscorlib]System.IO.File::Open(string, valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess, valuetype [mscorlib]System.IO.FileShare)
0x183e9  stloc.1
0x183ea  leave.s  loc_183EF
0x183ec  pop
0x183ed  leave.s  loc_183EF
0x183ef  leave.s  loc_183F1
0x183f1  ldarg.0
0x183f2  ldfld    class RSWPTraceInternal <>c__DisplayClass70_0::<>4__this
0x183f7  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Today()
0x183fc  stfld    valuetype [mscorlib]System.DateTime RSWPTraceInternal::m_startDate
0x18401  ldloc.1
0x18402  brfalse.s loc_1844D
0x18404  ldloc.1
0x18405  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Unicode()
0x1840a  newobj   instance void [mscorlib]System.IO.StreamWriter::.ctor(class [mscorlib]System.IO.Stream, class [mscorlib]System.Text.Encoding)
0x1840f  dup
0x18410  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.IO.StreamWriter::get_BaseStream()
0x18415  ldc.i4.0
0x18416  conv.i8
0x18417  ldc.i4.2
0x18418  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x1841d  pop
0x1841e  call     class [mscorlib]System.IO.TextWriter [mscorlib]System.IO.TextWriter::Synchronized(class [mscorlib]System.IO.TextWriter)
0x18423  dup
0x18424  ldarg.0
0x18425  ldfld    class RSWPTraceInternal <>c__DisplayClass70_0::<>4__this
0x1842a  ldarg.0
0x1842b  ldfld    class RSWPTraceInternal <>c__DisplayClass70_0::<>4__this
0x18430  ldfld    string RSWPTraceInternal::m_TraceFilePath
0x18435  call     instance string RSWPTraceInternal::GetTraceHeader(string fileName)
0x1843a  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x1843f  newobj   instance void [System]System.Diagnostics.TextWriterTraceListener::.ctor(class [mscorlib]System.IO.TextWriter)
0x18444  stloc.3
0x18445  ldarg.0
0x18446  ldloc.3
0x18447  stfld    class [System]System.Diagnostics.TextWriterTraceListener <>c__DisplayClass70_0::listener
0x1844c  ret
0x1844d  ldarg.0
0x1844e  ldfld    class RSWPTraceInternal <>c__DisplayClass70_0::<>4__this
0x18453  ldc.i4.0
0x18454  stfld    bool RSWPTraceInternal::m_createdFileTraceCorrectly
0x18459  ret
```
