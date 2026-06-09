# Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionStatusDialog::ConfiguredWSManIfNeeded

- ea: `0x916e0`
- end: `0x91803`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionStatusDialog::ConfiguredWSManIfNeeded`
- size: `291`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x91340`
- `0x921e0`

## callees

- `0xab0`
- `0x1db0`
- `0x2020`
- `0x2210`
- `0x12ed0`
- `0x13280`
- `0x13440`
- `0x8e230`
- `0x91520`
- `0x91650`
- `0x916e0`
- `0x9d830`
- `0x9d850`

## string_xrefs

- `0x917be`: `http://schemas.microsoft.com/wbem/wsman/1/config/service`

## pseudocode

```c

```

## disassembly

```asm
0x916e0  ldc.i4.0
0x916e1  stloc.0
0x916e2  br       loc_917F0
0x916e7  ldsfld   string [mscorlib]System.String::Empty
0x916ec  stloc.1
0x916ed  ldsfld   string [mscorlib]System.String::Empty
0x916f2  stloc.2
0x916f3  ldarg.1
0x916f4  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class Microsoft.WindowsEventCollection.SubscriptionSource> Microsoft.WindowsEventCollection.Subscription::get_Sources()
0x916f9  ldloc.0
0x916fa  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class Microsoft.WindowsEventCollection.SubscriptionSource>::get_Item(!!T0)
0x916ff  stloc.3
0x91700  ldarg.2
0x91701  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.WindowsEventCollection.SubscriptionSourceStatus> Microsoft.WindowsEventCollection.SubscriptionStatus::get_SourceStatuses()
0x91706  ldloc.3
0x91707  callvirt instance string Microsoft.WindowsEventCollection.SubscriptionSource::get_ComputerName()
0x9170c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.WindowsEventCollection.SubscriptionSourceStatus>::ContainsKey(var<u1>)
0x91711  brfalse  loc_917EC
0x91716  ldarg.2
0x91717  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.WindowsEventCollection.SubscriptionSourceStatus> Microsoft.WindowsEventCollection.SubscriptionStatus::get_SourceStatuses()
0x9171c  ldloc.3
0x9171d  callvirt instance string Microsoft.WindowsEventCollection.SubscriptionSource::get_ComputerName()
0x91722  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.WindowsEventCollection.SubscriptionSourceStatus>::get_Item(void)
0x91727  stloc.s  4
0x91729  ldarg.0
0x9172a  ldloc.s  4
0x9172c  ldloca.s 1
0x9172e  ldloca.s 2
0x91730  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionStatusDialog::ExtractWSManConfigNode(class Microsoft.WindowsEventCollection.SubscriptionSourceStatus sourceStatus, string& xmlToSend, string& xmlToDisplay)
0x91735  brfalse  loc_917EC
0x9173a  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x9173f  dup
0x91740  call     string Microsoft.Windows.ManagementUI.CombinedControls.Resources.SubscriptionResources::get_ConfirmWSManSettingsPrompt()
0x91745  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9174a  pop
0x9174b  dup
0x9174c  ldstr    asc_BF510// "\n\n"
0x91751  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x91756  pop
0x91757  dup
0x91758  ldloc.2
0x91759  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9175e  pop
0x9175f  dup
0x91760  ldstr    asc_BA972// "\n"
0x91765  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9176a  pop
0x9176b  dup
0x9176c  call     string Microsoft.Windows.ManagementUI.CombinedControls.Resources.SubscriptionResources::get_ConfirmWSManSettingsQuestion()
0x91771  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x91776  pop
0x91777  callvirt instance string [mscorlib]System.Object::ToString()
0x9177c  ldstr    aViewername// "ViewerName"
0x91781  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x91786  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.QueryMessage::QueryUser(string message, string caption)
0x9178b  ldc.i4.6
0x9178c  bne.un.s loc_917EC
0x9178e  ldnull
0x9178f  stloc.s  5
0x91791  ldnull
0x91792  stloc.s  6
0x91794  ldloc.s  4
0x91796  callvirt instance unsigned int32 Microsoft.WindowsEventCollection.SubscriptionSourceStatus::get_LastError()
0x9179b  ldc.i4   0x803380AA
0x917a0  beq.s    loc_917AA
0x917a2  ldloc.3
0x917a3  callvirt instance string Microsoft.WindowsEventCollection.SubscriptionSource::get_ComputerName()
0x917a8  stloc.s  6
0x917aa  ldarg.0
0x917ab  ldloc.s  6
0x917ad  ldloca.s 5
0x917af  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionStatusDialog::CreateWSManSession(string connectionString, class Microsoft.Windows.ManagementUI.CombinedControls.IWSManSession& wsManSession)
0x917b4  brfalse.s loc_917CF
0x917b6  ldarg.0
0x917b7  ldloc.s  5
0x917b9  ldstr    aEnableremoting// "EnableRemoting"
0x917be  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/wbem/wsman"...
0x917c3  ldloc.1
0x917c4  ldc.i4.0
0x917c5  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.IWSManSession::Invoke([in] string actionURI, [in] object resourceUri, [in] string parameters, [in] int32 flags)
0x917ca  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionStatusDialog::wsManInfo
0x917cf  leave.s  loc_917EC
0x917d1  stloc.s  7
0x917d3  ldarg.0
0x917d4  ldloc.s  7
0x917d6  callvirt instance string [mscorlib]System.Exception::get_Message()
0x917db  ldstr    aViewername// "ViewerName"
0x917e0  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x917e5  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x917ea  leave.s  loc_917EC
0x917ec  ldloc.0
0x917ed  ldc.i4.1
0x917ee  add
0x917ef  stloc.0
0x917f0  ldloc.0
0x917f1  ldarg.1
0x917f2  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class Microsoft.WindowsEventCollection.SubscriptionSource> Microsoft.WindowsEventCollection.Subscription::get_Sources()
0x917f7  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class Microsoft.WindowsEventCollection.SubscriptionSource>::get_Count()
0x917fc  blt      loc_916E7
0x91801  ldc.i4.1
0x91802  ret
```
