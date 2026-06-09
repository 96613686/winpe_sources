# Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1::EncodeFileNameForMimeHeader

- ea: `0xc9b0`
- end: `0xca9c`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1::EncodeFileNameForMimeHeader`
- size: `236`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xc9b0`

## pseudocode

```c

```

## disassembly

```asm
0xc9b0  ldarg.1
0xc9b1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc9b6  brfalse.s loc_C9BA
0xc9b8  ldarg.1
0xc9b9  ret
0xc9ba  ldarg.1
0xc9bb  callvirt instance int32 [mscorlib]System.String::get_Length()
0xc9c0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0xc9c5  stloc.0
0xc9c6  ldarg.1
0xc9c7  callvirt instance char[] [mscorlib]System.String::ToCharArray()
0xc9cc  stloc.1
0xc9cd  ldc.i4.0
0xc9ce  stloc.2
0xc9cf  br       loc_CA89
0xc9d4  ldloc.1
0xc9d5  ldloc.2
0xc9d6  ldelem.u2
0xc9d7  call     int32 [mscorlib]System.Convert::ToInt32(char)
0xc9dc  stloc.3
0xc9dd  ldloc.3
0xc9de  ldc.i4.s 0x41
0xc9e0  blt.s    loc_C9E7
0xc9e2  ldloc.3
0xc9e3  ldc.i4.s 0x5A
0xc9e5  ble.s    loc_CA05
0xc9e7  ldloc.3
0xc9e8  ldc.i4.s 0x61
0xc9ea  blt.s    loc_C9F1
0xc9ec  ldloc.3
0xc9ed  ldc.i4.s 0x7A
0xc9ef  ble.s    loc_CA05
0xc9f1  ldloc.3
0xc9f2  ldc.i4.s 0x30
0xc9f4  blt.s    loc_C9FB
0xc9f6  ldloc.3
0xc9f7  ldc.i4.s 0x39
0xc9f9  ble.s    loc_CA05
0xc9fb  ldloc.3
0xc9fc  ldc.i4.s 0x20
0xc9fe  beq.s    loc_CA05
0xca00  ldloc.3
0xca01  ldc.i4.s 0x2E
0xca03  bne.un.s loc_CA11
0xca05  ldloc.0
0xca06  ldloc.1
0xca07  ldloc.2
0xca08  ldelem.u2
0xca09  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0xca0e  pop
0xca0f  br.s     loc_CA85
0xca11  ldloc.3
0xca12  ldc.i4   0xD800
0xca17  blt.s    loc_CA26
0xca19  ldloc.3
0xca1a  ldc.i4   0xDFFF
0xca1f  cgt
0xca21  ldc.i4.0
0xca22  ceq
0xca24  br.s     loc_CA27
0xca26  ldc.i4.0
0xca27  stloc.s  4
0xca29  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0xca2e  ldloc.1
0xca2f  ldloc.2
0xca30  ldloc.s  4
0xca32  brtrue.s loc_CA37
0xca34  ldc.i4.1
0xca35  br.s     loc_CA38
0xca37  ldc.i4.2
0xca38  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(char[], int32, int32)
0xca3d  stloc.s  5
0xca3f  ldc.i4.0
0xca40  stloc.s  6
0xca42  br.s     loc_CA75
0xca44  ldloc.s  5
0xca46  ldloc.s  6
0xca48  ldelem.u1
0xca49  stloc.s  7
0xca4b  ldloc.0
0xca4c  ldstr    asc_1327C// "%"
0xca51  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xca56  pop
0xca57  ldloc.0
0xca58  ldloca.s 7
0xca5a  ldstr    aX_0// "X"
0xca5f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xca64  call     instance string [mscorlib]System.Byte::ToString(string, class [mscorlib]System.IFormatProvider)
0xca69  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xca6e  pop
0xca6f  ldloc.s  6
0xca71  ldc.i4.1
0xca72  add
0xca73  stloc.s  6
0xca75  ldloc.s  6
0xca77  ldloc.s  5
0xca79  ldlen
0xca7a  conv.i4
0xca7b  blt.s    loc_CA44
0xca7d  ldloc.s  4
0xca7f  brfalse.s loc_CA85
0xca81  ldloc.2
0xca82  ldc.i4.1
0xca83  add
0xca84  stloc.2
0xca85  ldloc.2
0xca86  ldc.i4.1
0xca87  add
0xca88  stloc.2
0xca89  ldloc.2
0xca8a  ldarg.1
0xca8b  callvirt instance int32 [mscorlib]System.String::get_Length()
0xca90  blt      loc_C9D4
0xca95  ldloc.0
0xca96  callvirt instance string [mscorlib]System.Object::ToString()
0xca9b  ret
```
