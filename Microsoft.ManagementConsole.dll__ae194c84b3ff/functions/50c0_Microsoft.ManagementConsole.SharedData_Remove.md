# Microsoft.ManagementConsole.SharedData::Remove

- ea: `0x50c0`
- end: `0x5121`
- name: `Microsoft.ManagementConsole.SharedData::Remove`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x4e80`
- `0x50c0`
- `0x5130`
- `0x53b0`
- `0x53e0`
- `0x8370`

## pseudocode

```c

```

## disassembly

```asm
0x50c0  ldarg.1
0x50c1  ldstr    aClipboardforma// "clipboardFormatId"
0x50c6  ldc.i4.1
0x50c7  call     bool Microsoft.ManagementConsole.Internal.Utility::CheckStringNullOrEmpty(string stringToCheck, string name, bool throwException)
0x50cc  pop
0x50cd  ldarg.1
0x50ce  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x50d3  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x50d8  stloc.0
0x50d9  ldarg.0
0x50da  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ManagementConsole.SharedDataItem> Microsoft.ManagementConsole.SharedData::_dataItems
0x50df  ldloc.0
0x50e0  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ManagementConsole.SharedDataItem>::ContainsKey(var<u1>)
0x50e5  brfalse.s loc_5120
0x50e7  ldarg.0
0x50e8  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ManagementConsole.SharedDataItem> Microsoft.ManagementConsole.SharedData::_dataItems
0x50ed  ldloc.0
0x50ee  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ManagementConsole.SharedDataItem>::get_Item(void)
0x50f3  stloc.1
0x50f4  ldarg.0
0x50f5  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ManagementConsole.SharedDataItem> Microsoft.ManagementConsole.SharedData::_dataItems
0x50fa  ldloc.0
0x50fb  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ManagementConsole.SharedDataItem>::Remove(var<u1>)
0x5100  pop
0x5101  ldloc.1
0x5102  ldarg.0
0x5103  ldftn    instance void Microsoft.ManagementConsole.SharedData::OnSharedDataChanged(object sender, class Microsoft.ManagementConsole.SharedDataChangedEventArgs e)
0x5109  newobj   instance void SharedDataChangedEventHandler::.ctor(object object, native int method)
0x510e  callvirt instance void Microsoft.ManagementConsole.SharedDataItem::remove_Changed(class SharedDataChangedEventHandler value)
0x5113  ldarg.0
0x5114  ldc.i4.1
0x5115  ldloc.1
0x5116  newobj   instance void Microsoft.ManagementConsole.SharedDataChangedEventArgs::.ctor(valuetype Microsoft.ManagementConsole.SharedDataChangeType changeType, class Microsoft.ManagementConsole.SharedDataItem publishedDataItem)
0x511b  call     instance void Microsoft.ManagementConsole.SharedData::NotifyChanged(class Microsoft.ManagementConsole.SharedDataChangedEventArgs args)
0x5120  ret
```
