# Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTable::GetPage

- ea: `0x205900`
- end: `0x205a20`
- name: `Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTable::GetPage`
- size: `288`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x2058a0`
- `0x2058c0`

## callees

- `0x205900`
- `0x205a90`
- `0x205aa0`
- `0x205af0`
- `0x205b30`
- `0x205b90`
- `0x205bc0`
- `0x205c20`
- `0x20ffb0`

## string_xrefs

- `0x205980`: `Must be able to Seek, Read, and Write stream`

## pseudocode

```c

```

## disassembly

```asm
0x205900  ldarg.0
0x205901  ldarg.1
0x205902  call     instance int32 Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTable::CalcPageNum(int64 id)
0x205907  stloc.0
0x205908  ldnull
0x205909  stloc.1
0x20590a  ldarg.0
0x20590b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTablePage> Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTable::m_pageCache
0x205910  ldloc.0
0x205911  ldloca.s 1
0x205913  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTablePage>::TryGetValue(var<u1>, !!T0)
0x205918  brtrue   loc_205A1E
0x20591d  ldarg.0
0x20591e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTablePage> Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTable::m_pageCache
0x205923  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTablePage>::get_Count()
0x205928  ldarg.0
0x205929  ldfld    int32 Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTable::m_cacheSize
0x20592e  bne.un   loc_2059F7
0x205933  ldarg.0
0x205934  ldfld    class [mscorlib]System.IO.Stream Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTable::m_stream
0x205939  brtrue.s loc_20598A
0x20593b  ldarg.0
0x20593c  ldarg.0
0x20593d  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IStreamHandler Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTable::m_streamCreator
0x205942  callvirt instance class [mscorlib]System.IO.Stream Microsoft.ReportingServices.OnDemandProcessing.Scalability.IStreamHandler::OpenStream()
0x205947  stfld    class [mscorlib]System.IO.Stream Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTable::m_stream
0x20594c  ldarg.0
0x20594d  ldnull
0x20594e  stfld    class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IStreamHandler Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTable::m_streamCreator
0x205953  ldarg.0
0x205954  ldfld    class [mscorlib]System.IO.Stream Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTable::m_stream
0x205959  callvirt instance bool [mscorlib]System.IO.Stream::get_CanSeek()
0x20595e  brfalse.s loc_20597A
0x205960  ldarg.0
0x205961  ldfld    class [mscorlib]System.IO.Stream Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTable::m_stream
0x205966  callvirt instance bool [mscorlib]System.IO.Stream::get_CanRead()
0x20596b  brfalse.s loc_20597A
0x20596d  ldarg.0
0x20596e  ldfld    class [mscorlib]System.IO.Stream Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTable::m_stream
0x205973  callvirt instance bool [mscorlib]System.IO.Stream::get_CanWrite()
0x205978  brtrue.s loc_20598A
0x20597a  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20597f  ldc.i4.0
0x205980  ldstr    aMustBeAbleToSe// "Must be able to Seek, Read, and Write s"...
0x205985  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x20598a  ldarg.0
0x20598b  call     instance class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTablePage Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTable::QueueExtractFirst()
0x205990  stloc.1
0x205991  ldloc.1
0x205992  ldfld    int32 Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTablePage::PageNumber
0x205997  stloc.2
0x205998  ldarg.0
0x205999  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTablePage> Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTable::m_pageCache
0x20599e  ldloc.2
0x20599f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTablePage>::Remove(var<u1>)
0x2059a4  pop
0x2059a5  ldloc.1
0x2059a6  ldfld    bool Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTablePage::Dirty
0x2059ab  brfalse.s loc_2059D2
0x2059ad  ldarg.0
0x2059ae  ldloc.2
0x2059af  conv.i8
0x2059b0  call     instance int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTable::CalcPageOffset(int64 pageNum)
0x2059b5  stloc.s  4
0x2059b7  ldarg.0
0x2059b8  ldfld    class [mscorlib]System.IO.Stream Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTable::m_stream
0x2059bd  ldloc.s  4
0x2059bf  ldc.i4.0
0x2059c0  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x2059c5  pop
0x2059c6  ldloc.1
0x2059c7  ldarg.0
0x2059c8  ldfld    class [mscorlib]System.IO.Stream Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTable::m_stream
0x2059cd  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTablePage::Write(class [mscorlib]System.IO.Stream stream)
0x2059d2  ldarg.0
0x2059d3  ldloc.0
0x2059d4  conv.i8
0x2059d5  call     instance int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTable::CalcPageOffset(int64 pageNum)
0x2059da  stloc.3
0x2059db  ldarg.0
0x2059dc  ldfld    class [mscorlib]System.IO.Stream Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTable::m_stream
0x2059e1  ldloc.3
0x2059e2  ldc.i4.0
0x2059e3  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x2059e8  pop
0x2059e9  ldloc.1
0x2059ea  ldarg.0
0x2059eb  ldfld    class [mscorlib]System.IO.Stream Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTable::m_stream
0x2059f0  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTablePage::Read(class [mscorlib]System.IO.Stream stream)
0x2059f5  br.s     loc_205A03
0x2059f7  ldarg.0
0x2059f8  ldfld    int32 Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTable::m_pageSize
0x2059fd  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTablePage::.ctor(int32 size)
0x205a02  stloc.1
0x205a03  ldloc.1
0x205a04  ldloc.0
0x205a05  stfld    int32 Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTablePage::PageNumber
0x205a0a  ldarg.0
0x205a0b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTablePage> Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTable::m_pageCache
0x205a10  ldloc.0
0x205a11  ldloc.1
0x205a12  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTablePage>::set_Item(var<u1>, !!T0)
0x205a17  ldarg.0
0x205a18  ldloc.1
0x205a19  call     instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTable::QueueAppendPage(class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IndexTablePage page)
0x205a1e  ldloc.1
0x205a1f  ret
```
