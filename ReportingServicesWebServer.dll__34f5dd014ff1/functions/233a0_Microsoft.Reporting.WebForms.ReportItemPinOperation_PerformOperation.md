# Microsoft.Reporting.WebForms.ReportItemPinOperation::PerformOperation

- ea: `0x233a0`
- end: `0x23532`
- name: `Microsoft.Reporting.WebForms.ReportItemPinOperation::PerformOperation`
- size: `402`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x2d70`
- `0x233a0`
- `0x24dc0`
- `0x24fb0`
- `0x3b6f0`
- `0x3b710`

## string_xrefs

- `0x234af`: `ReportItemPath`
- `0x23522`: `ReportItemPath`

## pseudocode

```c

```

## disassembly

```asm
0x233a0  newobj   instance void <>c__DisplayClass11_0::.ctor()
0x233a5  stloc.0
0x233a6  ldloc.0
0x233a7  ldarg.0
0x233a8  stfld    class Microsoft.Reporting.WebForms.ReportItemPinOperation <>c__DisplayClass11_0::<>4__this
0x233ad  ldloc.0
0x233ae  ldarg.1
0x233af  stfld    class [System]System.Collections.Specialized.NameValueCollection <>c__DisplayClass11_0::urlQuery
0x233b4  ldloc.0
0x233b5  ldfld    class [System]System.Collections.Specialized.NameValueCollection <>c__DisplayClass11_0::urlQuery
0x233ba  ldstr    aAction// "Action"
0x233bf  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x233c4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x233c9  brfalse.s loc_233DB
0x233cb  ldstr    aAction// "Action"
0x233d0  call     string Microsoft.Reporting.WebForms.Errors::MissingUrlParameter(string paramName)
0x233d5  newobj   instance void Microsoft.Reporting.WebForms.HttpHandlerInputException::.ctor(string message)
0x233da  throw
0x233db  ldtoken  ReportItemPinOperationActionType
0x233e0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x233e5  ldloc.0
0x233e6  ldfld    class [System]System.Collections.Specialized.NameValueCollection <>c__DisplayClass11_0::urlQuery
0x233eb  ldstr    aAction// "Action"
0x233f0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x233f5  ldc.i4.1
0x233f6  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x233fb  unbox.any ReportItemPinOperationActionType
0x23400  stloc.1
0x23401  newobj   instance void <>c__DisplayClass11_1::.ctor()
0x23406  stloc.2
0x23407  ldloc.2
0x23408  ldloc.0
0x23409  stfld    class <>c__DisplayClass11_0 <>c__DisplayClass11_1::CS$<>8__locals1
0x2340e  ldloc.1
0x2340f  switch   loc_23429, loc_2344F, loc_234A3, loc_2347D
0x23424  br       loc_23522
0x23429  ldsfld   class [mscorlib]System.Func`1<bool> <>c::<>9__11_0
0x2342e  dup
0x2342f  brtrue.s loc_23448
0x23431  pop
0x23432  ldsfld   class <>c <>c::<>9
0x23437  ldftn    instance bool <>c::<PerformOperation>b__11_0()
0x2343d  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x23442  dup
0x23443  stsfld   class [mscorlib]System.Func`1<bool> <>c::<>9__11_0
0x23448  ldarg.2
0x23449  call     T0x2B000030
0x2344e  ret
0x2344f  ldloc.2
0x23450  ldloc.2
0x23451  ldfld    class <>c__DisplayClass11_0 <>c__DisplayClass11_1::CS$<>8__locals1
0x23456  ldfld    class [System]System.Collections.Specialized.NameValueCollection <>c__DisplayClass11_0::urlQuery
0x2345b  ldstr    aGroupid// "GroupID"
0x23460  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x23465  stfld    string <>c__DisplayClass11_1::groupId
0x2346a  ldloc.2
0x2346b  ldftn    instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Dashboarding]Microsoft.ReportingServices.Dashboarding.Dashboard> <>c__DisplayClass11_1::<PerformOperation>b__1()
0x23471  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Dashboarding]Microsoft.ReportingServices.Dashboarding.Dashboard>>::.ctor(object, native int)
0x23476  ldarg.2
0x23477  call     T0x2B000031
0x2347c  ret
0x2347d  ldsfld   class [mscorlib]System.Func`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Dashboarding]Microsoft.ReportingServices.Dashboarding.Group>> <>c::<>9__11_2
0x23482  dup
0x23483  brtrue.s loc_2349C
0x23485  pop
0x23486  ldsfld   class <>c <>c::<>9
0x2348b  ldftn    instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Dashboarding]Microsoft.ReportingServices.Dashboarding.Group> <>c::<PerformOperation>b__11_2()
0x23491  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Dashboarding]Microsoft.ReportingServices.Dashboarding.Group>>::.ctor(object, native int)
0x23496  dup
0x23497  stsfld   class [mscorlib]System.Func`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Dashboarding]Microsoft.ReportingServices.Dashboarding.Group>> <>c::<>9__11_2
0x2349c  ldarg.2
0x2349d  call     T0x2B000032
0x234a2  ret
0x234a3  ldloc.2
0x234a4  ldloc.2
0x234a5  ldfld    class <>c__DisplayClass11_0 <>c__DisplayClass11_1::CS$<>8__locals1
0x234aa  ldfld    class [System]System.Collections.Specialized.NameValueCollection <>c__DisplayClass11_0::urlQuery
0x234af  ldstr    aReportitempath_0// "ReportItemPath"
0x234b4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x234b9  stfld    string <>c__DisplayClass11_1::reportItemName
0x234be  ldloc.2
0x234bf  ldloc.2
0x234c0  ldfld    class <>c__DisplayClass11_0 <>c__DisplayClass11_1::CS$<>8__locals1
0x234c5  ldfld    class [System]System.Collections.Specialized.NameValueCollection <>c__DisplayClass11_0::urlQuery
0x234ca  ldstr    aPinsettingsDas// "PinSettings[dashboardId]"
0x234cf  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x234d4  stfld    string <>c__DisplayClass11_1::dashboardId
0x234d9  ldloc.2
0x234da  ldloc.2
0x234db  ldfld    class <>c__DisplayClass11_0 <>c__DisplayClass11_1::CS$<>8__locals1
0x234e0  ldfld    class [System]System.Collections.Specialized.NameValueCollection <>c__DisplayClass11_0::urlQuery
0x234e5  ldstr    aPinsettingsDas_0// "PinSettings[dashboardName]"
0x234ea  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x234ef  stfld    string <>c__DisplayClass11_1::dashboardName
0x234f4  ldloc.2
0x234f5  ldloc.2
0x234f6  ldfld    class <>c__DisplayClass11_0 <>c__DisplayClass11_1::CS$<>8__locals1
0x234fb  ldfld    class [System]System.Collections.Specialized.NameValueCollection <>c__DisplayClass11_0::urlQuery
0x23500  ldstr    aPinsettingsGro// "PinSettings[groupId]"
0x23505  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2350a  stfld    string <>c__DisplayClass11_1::addGroupId
0x2350f  ldloc.2
0x23510  ldftn    instance class AddToDashboardsResults <>c__DisplayClass11_1::<PerformOperation>b__3()
0x23516  newobj   instance void class [mscorlib]System.Func`1<class AddToDashboardsResults>::.ctor(object, native int)
0x2351b  ldarg.2
0x2351c  call     T0x2B000033
0x23521  ret
0x23522  ldstr    aReportitempath_0// "ReportItemPath"
0x23527  call     string Microsoft.Reporting.WebForms.Strings::MissingUrlParameter(string paramName)
0x2352c  newobj   instance void Microsoft.Reporting.WebForms.HttpHandlerInputException::.ctor(string message)
0x23531  throw
```
