# Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::ProcessTaskSchedulerEvent

- ea: `0x7e140`
- end: `0x7e7d5`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::ProcessTaskSchedulerEvent`
- size: `1685`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x7ddf0`

## callees

- `0x12ed0`
- `0x12f50`
- `0x33e70`
- `0x35250`
- `0x4d1c0`
- `0x67bb0`
- `0x7cd60`
- `0x7e140`
- `0x7e7e0`
- `0x7e880`
- `0xa2740`
- `0xa27e0`
- `0xa2810`
- `0xa2920`
- `0xa2940`
- `0xa29a0`
- `0xa2a50`
- `0xa2aa0`
- `0xa2b30`

## string_xrefs

- `0x7e1ce`: `Event/System/TimeCreated/@SystemTime`
- `0x7e1e7`: `Event/System/TimeCreated/@SystemTime`
- `0x7e200`: `Event/System/TimeCreated/@SystemTime`
- `0x7e221`: `Event/System/TimeCreated/@SystemTime`
- `0x7e1c6`: `Event/EventData/Data[@Name='TaskName']`
- `0x7e23b`: `UnexpectedTaskEventID`

## pseudocode

```c

```

## disassembly

```asm
0x7e140  ldarg.1
0x7e141  ldc.i4.s 0x64
0x7e143  sub
0x7e144  switch   loc_7E1B6, loc_7E23B, loc_7E1D7, loc_7E1F0, loc_7E23B, loc_7E23B, loc_7E23B, loc_7E22A, loc_7E22A, loc_7E22A, loc_7E23B, loc_7E211, loc_7E23B, loc_7E23B, loc_7E23B, loc_7E23B, loc_7E23B, loc_7E22A, loc_7E22A, loc_7E22A, loc_7E22A, loc_7E22A, loc_7E22A, loc_7E22A, loc_7E22A, loc_7E22A
0x7e1b1  br       loc_7E23B
0x7e1b6  ldc.i4.3
0x7e1b7  newarr   [mscorlib]System.String
0x7e1bc  dup
0x7e1bd  ldc.i4.0
0x7e1be  ldstr    aEventEventdata// "Event/EventData/Data[@Name='InstanceId'"...
0x7e1c3  stelem.ref
0x7e1c4  dup
0x7e1c5  ldc.i4.1
0x7e1c6  ldstr    aEventEventdata_0// "Event/EventData/Data[@Name='TaskName']"
0x7e1cb  stelem.ref
0x7e1cc  dup
0x7e1cd  ldc.i4.2
0x7e1ce  ldstr    aEventSystemTim// "Event/System/TimeCreated/@SystemTime"
0x7e1d3  stelem.ref
0x7e1d4  stloc.0
0x7e1d5  br.s     loc_7E24B
0x7e1d7  ldc.i4.2
0x7e1d8  newarr   [mscorlib]System.String
0x7e1dd  dup
0x7e1de  ldc.i4.0
0x7e1df  ldstr    aEventEventdata// "Event/EventData/Data[@Name='InstanceId'"...
0x7e1e4  stelem.ref
0x7e1e5  dup
0x7e1e6  ldc.i4.1
0x7e1e7  ldstr    aEventSystemTim// "Event/System/TimeCreated/@SystemTime"
0x7e1ec  stelem.ref
0x7e1ed  stloc.0
0x7e1ee  br.s     loc_7E24B
0x7e1f0  ldc.i4.3
0x7e1f1  newarr   [mscorlib]System.String
0x7e1f6  dup
0x7e1f7  ldc.i4.0
0x7e1f8  ldstr    aEventEventdata// "Event/EventData/Data[@Name='InstanceId'"...
0x7e1fd  stelem.ref
0x7e1fe  dup
0x7e1ff  ldc.i4.1
0x7e200  ldstr    aEventSystemTim// "Event/System/TimeCreated/@SystemTime"
0x7e205  stelem.ref
0x7e206  dup
0x7e207  ldc.i4.2
0x7e208  ldstr    aEventEventdata_1// "Event/EventData/Data[@Name='ResultCode'"...
0x7e20d  stelem.ref
0x7e20e  stloc.0
0x7e20f  br.s     loc_7E24B
0x7e211  ldc.i4.2
0x7e212  newarr   [mscorlib]System.String
0x7e217  dup
0x7e218  ldc.i4.0
0x7e219  ldstr    aEventEventdata// "Event/EventData/Data[@Name='InstanceId'"...
0x7e21e  stelem.ref
0x7e21f  dup
0x7e220  ldc.i4.1
0x7e221  ldstr    aEventSystemTim// "Event/System/TimeCreated/@SystemTime"
0x7e226  stelem.ref
0x7e227  stloc.0
0x7e228  br.s     loc_7E24B
0x7e22a  ldc.i4.1
0x7e22b  newarr   [mscorlib]System.String
0x7e230  dup
0x7e231  ldc.i4.0
0x7e232  ldstr    aEventEventdata// "Event/EventData/Data[@Name='InstanceId'"...
0x7e237  stelem.ref
0x7e238  stloc.0
0x7e239  br.s     loc_7E24B
0x7e23b  ldstr    aUnexpectedtask// "UnexpectedTaskEventID"
0x7e240  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7e245  newobj   instance void ReadingDataFailedException::.ctor(string errorMsg)
0x7e24a  throw
0x7e24b  ldloc.0
0x7e24c  ldlen
0x7e24d  conv.i4
0x7e24e  ldloc.0
0x7e24f  ldc.i4.0
0x7e250  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::CreateRenderContext(int32 countOfValues, string[] valuePaths, int32 flags)
0x7e255  stloc.1
0x7e256  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x7e25b  stloc.2
0x7e25c  ldloc.1
0x7e25d  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x7e262  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x7e267  brfalse.s loc_7E2A8
0x7e269  ldnull
0x7e26a  ldstr    aCrimsonexcepti// "CrimsonException"
0x7e26f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7e274  ldc.i4.1
0x7e275  newarr   [mscorlib]System.Object
0x7e27a  dup
0x7e27b  ldc.i4.0
0x7e27c  ldloca.s 2
0x7e27e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7e283  ldtoken  [mscorlib]System.Int32
0x7e288  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7e28d  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x7e292  castclass [mscorlib]System.IFormatProvider
0x7e297  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x7e29c  stelem.ref
0x7e29d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7e2a2  newobj   instance void ReadingDataFailedException::.ctor(string errorMsg)
0x7e2a7  throw
0x7e2a8  ldc.i4   0x400
0x7e2ad  stloc.3
0x7e2ae  ldloc.3
0x7e2af  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x7e2b4  stloc.s  4
0x7e2b6  ldarg.0
0x7e2b7  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl::get_DataModel()
0x7e2bc  castclass Microsoft.Windows.ManagementUI.CombinedControls.UITaskService
0x7e2c1  ldarg.0
0x7e2c2  ldarg.2
0x7e2c3  ldloc.1
0x7e2c4  ldloca.s 4
0x7e2c6  ldloca.s 3
0x7e2c8  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::RenderCrimsonEvent(native int hEvent, native int evtRenderContext, native int& buffer, int32& bufferSize)
0x7e2cd  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_ComputerName()
0x7e2d2  call     bool Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::CurrentUserIsAdmin(string computerName)
0x7e2d7  stloc.s  5
0x7e2d9  ldarg.1
0x7e2da  ldc.i4.s 0x64
0x7e2dc  sub
0x7e2dd  switch   loc_7E34F, loc_7E7CA, loc_7E478, loc_7E54D, loc_7E7CA, loc_7E7CA, loc_7E7CA, loc_7E74C, loc_7E74C, loc_7E74C, loc_7E7CA, loc_7E67A, loc_7E7CA, loc_7E7CA, loc_7E7CA, loc_7E7CA, loc_7E7CA, loc_7E74C, loc_7E74C, loc_7E74C, loc_7E74C, loc_7E74C, loc_7E74C, loc_7E74C, loc_7E74C, loc_7E74C
0x7e34a  br       loc_7E7CA
0x7e34f  ldloc.s  4
0x7e351  stloc.s  6
0x7e353  ldloc.s  6
0x7e355  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x7e35a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7e35f  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x7e364  unbox.any Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x7e369  stloc.s  7
0x7e36b  ldloc.s  7
0x7e36d  call     object Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::VariantToObject(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant var)
0x7e372  callvirt instance string [mscorlib]System.Object::ToString()
0x7e377  stloc.s  8
0x7e379  ldloc.s  6
0x7e37b  ldloc.s  7
0x7e37d  box      Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x7e382  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(object)
0x7e387  call     native int Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::AddOffset(native int ptr, int32 offset)
0x7e38c  stloc.s  6
0x7e38e  ldloc.s  6
0x7e390  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x7e395  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7e39a  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x7e39f  unbox.any Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x7e3a4  stloc.s  7
0x7e3a6  ldloc.s  7
0x7e3a8  call     object Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::VariantToObject(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant var)
0x7e3ad  castclass [mscorlib]System.String
0x7e3b2  stloc.s  9
0x7e3b4  ldloc.s  6
0x7e3b6  ldloc.s  7
0x7e3b8  box      Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x7e3bd  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(object)
0x7e3c2  call     native int Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::AddOffset(native int ptr, int32 offset)
0x7e3c7  stloc.s  6
0x7e3c9  ldarg.0
0x7e3ca  ldloc.s  5
0x7e3cc  ldloc.s  9
0x7e3ce  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::ShouldShowTask(bool isAdmin, string taskPath)
0x7e3d3  brfalse  loc_7E7CA
0x7e3d8  ldloc.s  6
0x7e3da  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x7e3df  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7e3e4  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x7e3e9  unbox.any Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x7e3ee  stloc.s  7
0x7e3f0  ldloc.s  7
0x7e3f2  call     object Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::VariantToObject(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant var)
0x7e3f7  unbox.any [mscorlib]System.DateTime
0x7e3fc  stloc.s  0xA
0x7e3fe  ldarg.0
0x7e3ff  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityData> Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTaskActivityDictionary
0x7e404  ldloc.s  8
0x7e406  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityData>::ContainsKey(var<u1>)
0x7e40b  brfalse.s loc_7E43A
0x7e40d  ldarg.0
0x7e40e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityData> Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTaskActivityDictionary
0x7e413  ldloc.s  8
0x7e415  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityData>::get_Item(void)
0x7e41a  ldloc.s  9
0x7e41c  callvirt instance void PastTaskActivityData::set_TaskPath(string value)
0x7e421  ldarg.0
0x7e422  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityData> Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTaskActivityDictionary
0x7e427  ldloc.s  8
0x7e429  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityData>::get_Item(void)
0x7e42e  ldloc.s  0xA
0x7e430  callvirt instance void PastTaskActivityData::set_StartTime(valuetype [mscorlib]System.DateTime value)
0x7e435  leave    loc_7E7D4
0x7e43a  newobj   instance void PastTaskActivityData::.ctor()
0x7e43f  stloc.s  0xC
0x7e441  ldloc.s  0xC
0x7e443  ldloc.s  8
0x7e445  callvirt instance void PastTaskActivityData::set_TaskInstanceGuid(string value)
0x7e44a  ldloc.s  0xC
0x7e44c  ldloc.s  9
0x7e44e  callvirt instance void PastTaskActivityData::set_TaskPath(string value)
0x7e453  ldloc.s  0xC
0x7e455  ldloc.s  0xA
0x7e457  callvirt instance void PastTaskActivityData::set_StartTime(valuetype [mscorlib]System.DateTime value)
0x7e45c  ldloc.s  0xC
0x7e45e  ldc.i4.4
0x7e45f  callvirt instance void PastTaskActivityData::set_TaskStatus(valuetype TaskStatusEnum value)
0x7e464  ldarg.0
0x7e465  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityData> Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTaskActivityDictionary
0x7e46a  ldloc.s  8
0x7e46c  ldloc.s  0xC
0x7e46e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityData>::Add(var<u1>, !!T0)
0x7e473  br       loc_7E7CA
0x7e478  ldloc.s  4
0x7e47a  stloc.s  6
0x7e47c  ldloc.s  6
0x7e47e  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x7e483  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7e488  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x7e48d  unbox.any Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x7e492  stloc.s  7
0x7e494  ldloc.s  7
0x7e496  call     object Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::VariantToObject(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant var)
0x7e49b  callvirt instance string [mscorlib]System.Object::ToString()
0x7e4a0  stloc.s  8
0x7e4a2  ldloc.s  6
0x7e4a4  ldloc.s  7
0x7e4a6  box      Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x7e4ab  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(object)
0x7e4b0  call     native int Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::AddOffset(native int ptr, int32 offset)
0x7e4b5  stloc.s  6
0x7e4b7  ldloc.s  6
0x7e4b9  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x7e4be  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7e4c3  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x7e4c8  unbox.any Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x7e4cd  stloc.s  7
0x7e4cf  ldloc.s  7
0x7e4d1  call     object Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::VariantToObject(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant var)
0x7e4d6  unbox.any [mscorlib]System.DateTime
0x7e4db  stloc.s  0xA
0x7e4dd  ldarg.0
0x7e4de  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityData> Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTaskActivityDictionary
0x7e4e3  ldloc.s  8
0x7e4e5  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityData>::ContainsKey(var<u1>)
0x7e4ea  brfalse.s loc_7E518
0x7e4ec  ldarg.0
0x7e4ed  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityData> Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTaskActivityDictionary
0x7e4f2  ldloc.s  8
0x7e4f4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityData>::get_Item(void)
0x7e4f9  ldloc.s  0xA
0x7e4fb  callvirt instance void PastTaskActivityData::set_EndTime(valuetype [mscorlib]System.DateTime value)
0x7e500  ldarg.0
0x7e501  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityData> Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTaskActivityDictionary
0x7e506  ldloc.s  8
0x7e508  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityData>::get_Item(void)
0x7e50d  ldc.i4.1
0x7e50e  callvirt instance void PastTaskActivityData::set_TaskStatus(valuetype TaskStatusEnum value)
0x7e513  leave    loc_7E7D4
0x7e518  newobj   instance void PastTaskActivityData::.ctor()
0x7e51d  stloc.s  0xD
0x7e51f  ldloc.s  0xD
0x7e521  ldloc.s  8
0x7e523  callvirt instance void PastTaskActivityData::set_TaskInstanceGuid(string value)
0x7e528  ldloc.s  0xD
0x7e52a  ldloc.s  0xA
0x7e52c  callvirt instance void PastTaskActivityData::set_EndTime(valuetype [mscorlib]System.DateTime value)
0x7e531  ldloc.s  0xD
0x7e533  ldc.i4.1
0x7e534  callvirt instance void PastTaskActivityData::set_TaskStatus(valuetype TaskStatusEnum value)
0x7e539  ldarg.0
0x7e53a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityData> Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::pastTaskActivityDictionary
0x7e53f  ldloc.s  8
0x7e541  ldloc.s  0xD
0x7e543  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PastTaskActivityData>::Add(var<u1>, !!T0)
0x7e548  br       loc_7E7CA
0x7e54d  ldloc.s  4
0x7e54f  stloc.s  6
0x7e551  ldloc.s  6
0x7e553  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x7e558  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7e55d  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x7e562  unbox.any Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x7e567  stloc.s  7
0x7e569  ldloc.s  7
0x7e56b  call     object Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::VariantToObject(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant var)
0x7e570  callvirt instance string [mscorlib]System.Object::ToString()
0x7e575  stloc.s  8
0x7e577  ldloc.s  6
0x7e579  ldloc.s  7
0x7e57b  box      Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x7e580  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(object)
0x7e585  call     native int Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::AddOffset(native int ptr, int32 offset)
0x7e58a  stloc.s  6
0x7e58c  ldloc.s  6
0x7e58e  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x7e593  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7e598  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x7e59d  unbox.any Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x7e5a2  stloc.s  7
  ... truncated ...
```
