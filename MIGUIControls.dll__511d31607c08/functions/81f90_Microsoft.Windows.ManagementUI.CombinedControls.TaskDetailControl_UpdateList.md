# Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::UpdateList

- ea: `0x81f90`
- end: `0x8214f`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::UpdateList`
- size: `447`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x12ed0`
- `0x13430`
- `0x16330`
- `0x80930`
- `0x81f90`
- `0x82150`

## string_xrefs

- `0x81ffc`: `TaskName`
- `0x8209c`: `StatusIdle`
- `0x820bd`: `StatusIdle`
- `0x820de`: `StatusIdle`
- `0x820ff`: `StatusIdle`

## pseudocode

```c

```

## disassembly

```asm
0x81f90  ldarg.0
0x81f91  ldfld    object Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::listViewMainSyncRoot
0x81f96  stloc.0
0x81f97  ldc.i4.0
0x81f98  stloc.1
0x81f99  ldloc.0
0x81f9a  ldloca.s 1
0x81f9c  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x81fa1  ldsfld   string [mscorlib]System.String::Empty
0x81fa6  stloc.2
0x81fa7  ldarg.1
0x81fa8  castclass [mscorlib]System.String
0x81fad  stloc.3
0x81fae  ldsfld   string [mscorlib]System.String::Empty
0x81fb3  stloc.s  4
0x81fb5  ldloc.3
0x81fb6  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x81fbb  call     class [System.Xml]System.Xml.XmlTextReader Microsoft.Windows.ManagementUI.CombinedControls.XmlConfigHelper::CreateXmlTextReader(class [mscorlib]System.IO.TextReader input)
0x81fc0  stloc.s  6
0x81fc2  br       loc_82112
0x81fc7  ldloc.s  6
0x81fc9  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x81fce  stloc.s  7
0x81fd0  ldloc.s  7
0x81fd2  ldstr    aData// "Data"
0x81fd7  ldc.i4.5
0x81fd8  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x81fdd  brtrue.s loc_8204A
0x81fdf  ldloc.s  6
0x81fe1  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x81fe6  pop
0x81fe7  ldc.i4.0
0x81fe8  stloc.s  5
0x81fea  br.s     loc_8202A
0x81fec  ldloc.s  6
0x81fee  ldloc.s  5
0x81ff0  callvirt instance void [System.Xml]System.Xml.XmlReader::MoveToAttribute(int32)
0x81ff5  ldloc.s  6
0x81ff7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x81ffc  ldstr    aTaskname// "TaskName"
0x82001  ldc.i4.5
0x82002  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x82007  brfalse.s loc_82024
0x82009  ldloc.s  6
0x8200b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x82010  ldc.i4.1
0x82011  newarr   [mscorlib]System.Char
0x82016  dup
0x82017  ldc.i4.0
0x82018  ldc.i4.s 0x5C
0x8201a  stelem.i2
0x8201b  callvirt instance string [mscorlib]System.String::Trim(char[])
0x82020  stloc.s  4
0x82022  br.s     loc_82035
0x82024  ldloc.s  5
0x82026  ldc.i4.1
0x82027  add
0x82028  stloc.s  5
0x8202a  ldloc.s  5
0x8202c  ldloc.s  6
0x8202e  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_AttributeCount()
0x82033  blt.s    loc_81FEC
0x82035  ldloc.s  6
0x82037  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x8203c  pop
0x8203d  ldloc.s  6
0x8203f  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x82044  pop
0x82045  br       loc_82112
0x8204a  ldloc.s  7
0x8204c  ldstr    aEventid_0// "EventID"
0x82051  ldc.i4.5
0x82052  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x82057  brfalse  loc_82112
0x8205c  ldloc.s  6
0x8205e  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x82063  pop
0x82064  ldloc.s  6
0x82066  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x8206b  ldstr    a100// "100"
0x82070  ldc.i4.5
0x82071  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x82076  brfalse.s loc_82088
0x82078  ldstr    aStatusrunning// "StatusRunning"
0x8207d  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x82082  stloc.2
0x82083  br       loc_8210A
0x82088  ldloc.s  6
0x8208a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x8208f  ldstr    a101// "101"
0x82094  ldc.i4.5
0x82095  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x8209a  brfalse.s loc_820A9
0x8209c  ldstr    aStatusidle// "StatusIdle"
0x820a1  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x820a6  stloc.2
0x820a7  br.s     loc_8210A
0x820a9  ldloc.s  6
0x820ab  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x820b0  ldstr    a102// "102"
0x820b5  ldc.i4.5
0x820b6  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x820bb  brfalse.s loc_820CA
0x820bd  ldstr    aStatusidle// "StatusIdle"
0x820c2  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x820c7  stloc.2
0x820c8  br.s     loc_8210A
0x820ca  ldloc.s  6
0x820cc  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x820d1  ldstr    a103// "103"
0x820d6  ldc.i4.5
0x820d7  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x820dc  brfalse.s loc_820EB
0x820de  ldstr    aStatusidle// "StatusIdle"
0x820e3  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x820e8  stloc.2
0x820e9  br.s     loc_8210A
0x820eb  ldloc.s  6
0x820ed  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x820f2  ldstr    a111// "111"
0x820f7  ldc.i4.5
0x820f8  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x820fd  brfalse.s loc_8210A
0x820ff  ldstr    aStatusidle// "StatusIdle"
0x82104  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x82109  stloc.2
0x8210a  ldloc.s  6
0x8210c  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x82111  pop
0x82112  ldloc.s  6
0x82114  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x82119  brtrue   loc_81FC7
0x8211e  ldarg.0
0x8211f  ldloc.s  4
0x82121  call     instance int32 Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::FindTaskInList(string taskName)
0x82126  stloc.s  5
0x82128  ldloc.s  5
0x8212a  ldc.i4.m1
0x8212b  beq.s    loc_82136
0x8212d  ldarg.0
0x8212e  ldloc.s  5
0x82130  ldloc.2
0x82131  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::UpdateStatusColumnForTask(int32 index, string status)
0x82136  leave.s  loc_8214E
0x82138  callvirt instance string [mscorlib]System.Object::ToString()
0x8213d  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x82142  leave.s  loc_8214E
0x82144  ldloc.1
0x82145  brfalse.s loc_8214D
0x82147  ldloc.0
0x82148  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x8214d  endfinally
0x8214e  ret
```
