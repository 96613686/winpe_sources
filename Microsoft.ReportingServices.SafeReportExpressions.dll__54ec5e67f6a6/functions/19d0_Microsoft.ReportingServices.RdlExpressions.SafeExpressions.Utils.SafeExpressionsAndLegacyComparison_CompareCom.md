# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareComplexObjects

- ea: `0x19d0`
- end: `0x1aba`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareComplexObjects`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x2e80`

## callees

- `0x1710`
- `0x19d0`
- `0x1de0`
- `0x1e00`

## pseudocode

```c

```

## disassembly

```asm
0x19d0  ldc.i4.0
0x19d1  stloc.0
0x19d2  ldarg.1
0x19d3  ldarg.2
0x19d4  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x19d9  brfalse.s loc_19DD
0x19db  ldc.i4.1
0x19dc  ret
0x19dd  ldarg.1
0x19de  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x19e3  callvirt instance class [mscorlib]System.Reflection.PropertyInfo[] [mscorlib]System.Type::GetProperties()
0x19e8  stloc.1
0x19e9  ldarg.2
0x19ea  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x19ef  callvirt instance class [mscorlib]System.Reflection.PropertyInfo[] [mscorlib]System.Type::GetProperties()
0x19f4  stloc.2
0x19f5  ldloc.1
0x19f6  brtrue.s loc_1A04
0x19f8  ldloca.s 5
0x19fa  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1a00  ldloc.s  5
0x1a02  br.s     loc_1A0C
0x1a04  ldloc.1
0x1a05  ldlen
0x1a06  conv.i4
0x1a07  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1a0c  stloc.3
0x1a0d  ldloc.2
0x1a0e  brtrue.s loc_1A1C
0x1a10  ldloca.s 5
0x1a12  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1a18  ldloc.s  5
0x1a1a  br.s     loc_1A24
0x1a1c  ldloc.2
0x1a1d  ldlen
0x1a1e  conv.i4
0x1a1f  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1a24  stloc.s  4
0x1a26  ldloca.s 3
0x1a28  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x1a2d  ldloca.s 4
0x1a2f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x1a34  ceq
0x1a36  ldloca.s 3
0x1a38  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x1a3d  ldloca.s 4
0x1a3f  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x1a44  ceq
0x1a46  and
0x1a47  brtrue.s loc_1A4B
0x1a49  ldc.i4.0
0x1a4a  ret
0x1a4b  ldloc.1
0x1a4c  stloc.s  6
0x1a4e  ldc.i4.0
0x1a4f  stloc.s  7
0x1a51  br.s     loc_1AB0
0x1a53  ldloc.s  6
0x1a55  ldloc.s  7
0x1a57  ldelem.ref
0x1a58  stloc.s  8
0x1a5a  ldarg.2
0x1a5b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1a60  ldloc.s  8
0x1a62  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1a67  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string)
0x1a6c  ldloc.s  8
0x1a6e  ldarg.1
0x1a6f  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object)
0x1a74  stloc.s  9
0x1a76  ldarg.2
0x1a77  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object)
0x1a7c  stloc.s  0xA
0x1a7e  ldarg.0
0x1a7f  ldloc.s  9
0x1a81  ldloc.s  0xA
0x1a83  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::NeitherIsNull(object objA, object objB)
0x1a88  brfalse.s loc_1A9A
0x1a8a  ldarg.0
0x1a8b  ldloc.s  9
0x1a8d  ldloc.s  0xA
0x1a8f  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareObjects(object legacyExprResult, object safeExprResult)
0x1a94  brtrue.s loc_1AAA
0x1a96  ldc.i4.0
0x1a97  stloc.0
0x1a98  br.s     loc_1AB8
0x1a9a  ldarg.0
0x1a9b  ldloc.s  9
0x1a9d  ldloc.s  0xA
0x1a9f  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::OneIsNull(object objA, object objB)
0x1aa4  brfalse.s loc_1AAA
0x1aa6  ldc.i4.0
0x1aa7  stloc.0
0x1aa8  br.s     loc_1AB8
0x1aaa  ldloc.s  7
0x1aac  ldc.i4.1
0x1aad  add
0x1aae  stloc.s  7
0x1ab0  ldloc.s  7
0x1ab2  ldloc.s  6
0x1ab4  ldlen
0x1ab5  conv.i4
0x1ab6  blt.s    loc_1A53
0x1ab8  ldloc.0
0x1ab9  ret
```
