# System.Windows.Threading.Dispatcher::OnRequestProcessingFailure

- ea: `0x3c810`
- end: `0x3c8d6`
- name: `System.Windows.Threading.Dispatcher::OnRequestProcessingFailure`
- size: `198`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x3c730`
- `0x3c7b0`

## callees

- `0x2c100`
- `0x2f960`
- `0x3c810`

## string_xrefs

- `0x3c89b`: `... entries removed to conserve memory ...`

## pseudocode

```c

```

## disassembly

```asm
0x3c810  ldarg.0
0x3c811  ldfld    bool System.Windows.Threading.Dispatcher::_hasRequestProcessingFailed
0x3c816  brtrue.s loc_3C835
0x3c818  ldarg.0
0x3c819  ldarg.0
0x3c81a  ldfld    object System.Windows.Threading.Dispatcher::_reservedPtsCache
0x3c81f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x3c824  newobj   instance void class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>::.ctor(var<u1>, !!T0)
0x3c829  stfld    object System.Windows.Threading.Dispatcher::_reservedPtsCache
0x3c82e  ldarg.0
0x3c82f  ldc.i4.1
0x3c830  stfld    bool System.Windows.Threading.Dispatcher::_hasRequestProcessingFailed
0x3c835  ldarg.0
0x3c836  ldfld    object System.Windows.Threading.Dispatcher::_reservedPtsCache
0x3c83b  isinst   class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>
0x3c840  stloc.0
0x3c841  ldloc.0
0x3c842  brfalse.s loc_3C8A5
0x3c844  ldloc.0
0x3c845  callvirt instance var<u1> class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>::get_Item2()
0x3c84a  stloc.1
0x3c84b  ldloc.1
0x3c84c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3c851  ldstr    a0O1Failed// "{0:O} {1} failed"
0x3c856  ldc.i4.2
0x3c857  newarr   [mscorlib]System.Object
0x3c85c  dup
0x3c85d  ldc.i4.0
0x3c85e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x3c863  box      [mscorlib]System.DateTime
0x3c868  stelem.ref
0x3c869  dup
0x3c86a  ldc.i4.1
0x3c86b  ldarg.1
0x3c86c  stelem.ref
0x3c86d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3c872  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3c877  ldloc.1
0x3c878  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x3c87d  ldc.i4   0x3E8
0x3c882  ble.s    loc_3C8A5
0x3c884  ldloc.1
0x3c885  ldc.i4.s 0x64
0x3c887  ldloc.1
0x3c888  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x3c88d  ldc.i4   0xC8
0x3c892  sub
0x3c893  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::RemoveRange(int32, int32)
0x3c898  ldloc.1
0x3c899  ldc.i4.s 0x64
0x3c89b  ldstr    aEntriesRemoved// "... entries removed to conserve memory "...
0x3c8a0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Insert(int32, var<u1>)
0x3c8a5  call     valuetype HandleDispatcherRequestProcessingFailureOptions System.Windows.BaseCompatibilityPreferences::get_HandleDispatcherRequestProcessingFailure()
0x3c8aa  stloc.2
0x3c8ab  ldloc.2
0x3c8ac  switch   loc_3C8D5, loc_3C8BE, loc_3C8CE
0x3c8bd  ret
0x3c8be  ldstr    aDispatcherrequ// "DispatcherRequestProcessingFailed"
0x3c8c3  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x3c8c8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3c8cd  throw
0x3c8ce  ldarg.0
0x3c8cf  ldc.i4.0
0x3c8d0  stfld    int32 System.Windows.Threading.Dispatcher::_postedProcessingType
0x3c8d5  ret
```
