# Microsoft.ManagementConsole.WritableSharedData::Remove

- ea: `0x5660`
- end: `0x56e1`
- name: `Microsoft.ManagementConsole.WritableSharedData::Remove`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x5460`
- `0x5660`
- `0x5850`
- `0x5890`
- `0x58c0`
- `0x58d0`
- `0x5910`
- `0x8370`

## pseudocode

```c

```

## disassembly

```asm
0x5660  ldarg.1
0x5661  ldstr    aClipboardforma// "clipboardFormatId"
0x5666  ldc.i4.1
0x5667  call     bool Microsoft.ManagementConsole.Internal.Utility::CheckStringNullOrEmpty(string stringToCheck, string name, bool throwException)
0x566c  pop
0x566d  ldarg.1
0x566e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5673  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x5678  stloc.0
0x5679  ldarg.0
0x567a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ManagementConsole.WritableSharedDataItem> Microsoft.ManagementConsole.WritableSharedData::_dataItems
0x567f  ldloc.0
0x5680  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ManagementConsole.WritableSharedDataItem>::ContainsKey(var<u1>)
0x5685  brfalse.s loc_56E0
0x5687  ldarg.0
0x5688  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ManagementConsole.WritableSharedDataItem> Microsoft.ManagementConsole.WritableSharedData::_dataItems
0x568d  ldloc.0
0x568e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ManagementConsole.WritableSharedDataItem>::get_Item(void)
0x5693  stloc.1
0x5694  ldarg.0
0x5695  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ManagementConsole.WritableSharedDataItem> Microsoft.ManagementConsole.WritableSharedData::_dataItems
0x569a  ldloc.0
0x569b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ManagementConsole.WritableSharedDataItem>::Remove(var<u1>)
0x56a0  pop
0x56a1  ldloc.1
0x56a2  ldarg.0
0x56a3  ldftn    instance void Microsoft.ManagementConsole.WritableSharedData::OnSharedDataChanged(object sender, class Microsoft.ManagementConsole.WritableSharedDataChangedEventArgs e)
0x56a9  newobj   instance void SharedDataChangedEventHandler::.ctor(object object, native int method)
0x56ae  callvirt instance void Microsoft.ManagementConsole.WritableSharedDataItem::remove_Changed(class SharedDataChangedEventHandler value)
0x56b3  ldloc.1
0x56b4  ldarg.0
0x56b5  ldftn    instance void Microsoft.ManagementConsole.WritableSharedData::OnPropertyChangeRequested(object sender, class Microsoft.ManagementConsole.WritableSharedDataChangeRequestEventArgs e)
0x56bb  newobj   instance void SharedDataChangeRequestEventHandler::.ctor(object object, native int method)
0x56c0  callvirt instance void Microsoft.ManagementConsole.WritableSharedDataItem::remove_PropertyChangeRequested(class SharedDataChangeRequestEventHandler value)
0x56c5  ldarg.0
0x56c6  ldfld    class SharedDataChangedEventHandler Microsoft.ManagementConsole.WritableSharedData::Changed
0x56cb  brfalse.s loc_56E0
0x56cd  ldarg.0
0x56ce  ldfld    class SharedDataChangedEventHandler Microsoft.ManagementConsole.WritableSharedData::Changed
0x56d3  ldarg.0
0x56d4  ldc.i4.1
0x56d5  ldloc.1
0x56d6  newobj   instance void Microsoft.ManagementConsole.WritableSharedDataChangedEventArgs::.ctor(valuetype Microsoft.ManagementConsole.WritableSharedDataChangeType changeType, class Microsoft.ManagementConsole.WritableSharedDataItem publishedDataItem)
0x56db  callvirt instance void SharedDataChangedEventHandler::Invoke(object sender, class Microsoft.ManagementConsole.WritableSharedDataChangedEventArgs e)
0x56e0  ret
```
