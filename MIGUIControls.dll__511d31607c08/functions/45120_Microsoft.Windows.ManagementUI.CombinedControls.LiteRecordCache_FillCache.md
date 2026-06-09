# Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::FillCache

- ea: `0x45120`
- end: `0x452be`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::FillCache`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x45030`

## callees

- `0x1cd50`
- `0x1ce20`
- `0x42e00`
- `0x45120`
- `0x452c0`

## string_xrefs

- `0x4512e`: `FillCacheGettingHandles(`
- `0x451e1`: `FillCacheGettingHandles1(`

## pseudocode

```c

```

## disassembly

```asm
0x45120  ldc.i4.0
0x45121  stloc.0
0x45122  ldarg.2
0x45123  stloc.1
0x45124  ldarg.1
0x45125  stloc.2
0x45126  ldc.i4.7
0x45127  newarr   [mscorlib]System.String
0x4512c  dup
0x4512d  ldc.i4.0
0x4512e  ldstr    aFillcachegetti// "FillCacheGettingHandles("
0x45133  stelem.ref
0x45134  dup
0x45135  ldc.i4.1
0x45136  ldarga.s 1
0x45138  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4513d  ldtoken  [mscorlib]System.Int64
0x45142  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x45147  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x4514c  castclass [mscorlib]System.IFormatProvider
0x45151  call     instance string [mscorlib]System.UInt64::ToString(class [mscorlib]System.IFormatProvider)
0x45156  stelem.ref
0x45157  dup
0x45158  ldc.i4.2
0x45159  ldstr    asc_AC604// ","
0x4515e  stelem.ref
0x4515f  dup
0x45160  ldc.i4.3
0x45161  ldarga.s 2
0x45163  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x45168  ldtoken  [mscorlib]System.Int64
0x4516d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x45172  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x45177  castclass [mscorlib]System.IFormatProvider
0x4517c  call     instance string [mscorlib]System.UInt64::ToString(class [mscorlib]System.IFormatProvider)
0x45181  stelem.ref
0x45182  dup
0x45183  ldc.i4.4
0x45184  ldstr    asc_AC604// ","
0x45189  stelem.ref
0x4518a  dup
0x4518b  ldc.i4.5
0x4518c  ldarga.s 3
0x4518e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x45193  ldtoken  [mscorlib]System.Int32
0x45198  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4519d  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x451a2  castclass [mscorlib]System.IFormatProvider
0x451a7  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x451ac  stelem.ref
0x451ad  dup
0x451ae  ldc.i4.6
0x451af  ldstr    asc_AD8F6// ")"
0x451b4  stelem.ref
0x451b5  call     string [mscorlib]System.String::Concat(string[])
0x451ba  stloc.3
0x451bb  ldarg.0
0x451bc  ldloc.3
0x451bd  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::StartMethod(object thisObject, string methodName)
0x451c2  ldarg.0
0x451c3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::_resultSet
0x451c8  ldarg.2
0x451c9  ldarga.s 3
0x451cb  callvirt instance native int[] Microsoft.Windows.ManagementUI.CombinedControls.EventsResultSet::GetEventHandlesAt(unsigned int64 index, int32& numberOfHandlesReturned)
0x451d0  stloc.s  4
0x451d2  ldarg.0
0x451d3  ldloc.3
0x451d4  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::EndMethod(object thisObject, string methodName)
0x451d9  ldc.i4.7
0x451da  newarr   [mscorlib]System.String
0x451df  dup
0x451e0  ldc.i4.0
0x451e1  ldstr    aFillcachegetti_0// "FillCacheGettingHandles1("
0x451e6  stelem.ref
0x451e7  dup
0x451e8  ldc.i4.1
0x451e9  ldarga.s 1
0x451eb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x451f0  ldtoken  [mscorlib]System.Int64
0x451f5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x451fa  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x451ff  castclass [mscorlib]System.IFormatProvider
0x45204  call     instance string [mscorlib]System.UInt64::ToString(class [mscorlib]System.IFormatProvider)
0x45209  stelem.ref
0x4520a  dup
0x4520b  ldc.i4.2
0x4520c  ldstr    asc_AC604// ","
0x45211  stelem.ref
0x45212  dup
0x45213  ldc.i4.3
0x45214  ldarga.s 2
0x45216  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4521b  ldtoken  [mscorlib]System.Int64
0x45220  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x45225  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x4522a  castclass [mscorlib]System.IFormatProvider
0x4522f  call     instance string [mscorlib]System.UInt64::ToString(class [mscorlib]System.IFormatProvider)
0x45234  stelem.ref
0x45235  dup
0x45236  ldc.i4.4
0x45237  ldstr    asc_AC604// ","
0x4523c  stelem.ref
0x4523d  dup
0x4523e  ldc.i4.5
0x4523f  ldarga.s 3
0x45241  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x45246  ldtoken  [mscorlib]System.Int32
0x4524b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x45250  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x45255  castclass [mscorlib]System.IFormatProvider
0x4525a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x4525f  stelem.ref
0x45260  dup
0x45261  ldc.i4.6
0x45262  ldstr    asc_AD8F6// ")"
0x45267  stelem.ref
0x45268  call     string [mscorlib]System.String::Concat(string[])
0x4526d  stloc.3
0x4526e  ldc.i4.0
0x4526f  stloc.s  5
0x45271  br.s     loc_452A0
0x45273  ldarg.0
0x45274  ldloc.1
0x45275  ldloc.2
0x45276  conv.i4
0x45277  ldloc.s  4
0x45279  ldloc.s  5
0x4527b  ldelem.i
0x4527c  call     instance int32 Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::SetLiteRecord(unsigned int64 bookmark, int32 index, native int hEvent)
0x45281  stloc.0
0x45282  ldloc.0
0x45283  brtrue.s loc_452A5
0x45285  ldloc.2
0x45286  ldc.i4.1
0x45287  conv.i8
0x45288  add
0x45289  stloc.2
0x4528a  ldloc.1
0x4528b  ldc.i4.1
0x4528c  conv.i8
0x4528d  add
0x4528e  stloc.1
0x4528f  ldloc.2
0x45290  ldsfld   unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::LITE_CACHE_SIZE
0x45295  blt.un.s loc_4529A
0x45297  ldc.i4.0
0x45298  conv.i8
0x45299  stloc.2
0x4529a  ldloc.s  5
0x4529c  ldc.i4.1
0x4529d  add
0x4529e  stloc.s  5
0x452a0  ldloc.s  5
0x452a2  ldarg.3
0x452a3  blt.s    loc_45273
0x452a5  ldarg.0
0x452a6  ldfld    unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::firstEventInCache
0x452ab  ldarg.2
0x452ac  ble.un.s loc_452BC
0x452ae  ldarg.0
0x452af  ldarg.1
0x452b0  stfld    unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::firstItemIndexInLiteCache
0x452b5  ldarg.0
0x452b6  ldarg.2
0x452b7  stfld    unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::firstEventInCache
0x452bc  ldloc.0
0x452bd  ret
```
