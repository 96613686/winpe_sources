# Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::GetAutoIncFileName

- ea: `0x6a0`
- end: `0x742`
- name: `Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::GetAutoIncFileName`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1270`

## callees

- `0x6a0`

## pseudocode

```c

```

## disassembly

```asm
0x6a0  ldstr    asc_5244// "_"
0x6a5  stloc.0
0x6a6  ldstr    asc_5248// ""
0x6ab  stloc.1
0x6ac  ldarg.1
0x6ad  ldstr    asc_524A// "."
0x6b2  ldc.i4.4
0x6b3  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x6b8  stloc.2
0x6b9  ldloc.2
0x6ba  ldc.i4.m1
0x6bb  beq.s    loc_6CF
0x6bd  ldarg.1
0x6be  ldloc.2
0x6bf  callvirt instance string [mscorlib]System.String::Substring(int32)
0x6c4  stloc.1
0x6c5  ldarg.1
0x6c6  ldc.i4.0
0x6c7  ldloc.2
0x6c8  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x6cd  starg.s  1
0x6cf  ldarg.1
0x6d0  ldloc.0
0x6d1  ldc.i4.4
0x6d2  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x6d7  stloc.3
0x6d8  ldloc.3
0x6d9  ldc.i4.m1
0x6da  beq.s    loc_731
0x6dc  ldarg.1
0x6dd  ldloc.3
0x6de  ldc.i4.1
0x6df  add
0x6e0  callvirt instance string [mscorlib]System.String::Substring(int32)
0x6e5  stloc.s  4
0x6e7  ldc.i4.4
0x6e8  newarr   [mscorlib]System.Object
0x6ed  dup
0x6ee  ldc.i4.0
0x6ef  ldarg.1
0x6f0  ldc.i4.0
0x6f1  ldloc.3
0x6f2  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x6f7  stelem.ref
0x6f8  dup
0x6f9  ldc.i4.1
0x6fa  ldloc.0
0x6fb  stelem.ref
0x6fc  dup
0x6fd  ldc.i4.2
0x6fe  ldloc.s  4
0x700  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x705  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x70a  ldc.i4.1
0x70b  add
0x70c  box      [mscorlib]System.Int32
0x711  stelem.ref
0x712  dup
0x713  ldc.i4.3
0x714  ldloc.1
0x715  stelem.ref
0x716  call     string [mscorlib]System.String::Concat(object[])
0x71b  starg.s  1
0x71d  leave.s  loc_740
0x71f  pop
0x720  ldarg.1
0x721  ldloc.0
0x722  ldstr    a1// "1"
0x727  ldloc.1
0x728  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x72d  starg.s  1
0x72f  leave.s  loc_740
0x731  ldarg.1
0x732  ldloc.0
0x733  ldstr    a1// "1"
0x738  ldloc.1
0x739  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x73e  starg.s  1
0x740  ldarg.1
0x741  ret
```
