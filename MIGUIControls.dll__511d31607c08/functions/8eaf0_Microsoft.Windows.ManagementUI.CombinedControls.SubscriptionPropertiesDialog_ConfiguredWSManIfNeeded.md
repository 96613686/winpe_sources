# Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::ConfiguredWSManIfNeeded

- ea: `0x8eaf0`
- end: `0x8ec13`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::ConfiguredWSManIfNeeded`
- size: `291`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x8e860`
- `0x8f930`

## callees

- `0xa40`
- `0x2020`
- `0x2210`
- `0x12ed0`
- `0x13280`
- `0x13440`
- `0x8e230`
- `0x8e930`
- `0x8ea60`
- `0x8eaf0`
- `0x8f930`
- `0x9d830`
- `0x9d850`

## string_xrefs

- `0x8ebc5`: `http://schemas.microsoft.com/wbem/wsman/1/config/service`

## pseudocode

```c

```

## disassembly

```asm
0x8eaf0  ldarg.1
0x8eaf1  callvirt instance string[] Microsoft.WindowsEventCollection.Subscription::get_RuntimeSources()
0x8eaf6  stloc.0
0x8eaf7  ldloc.0
0x8eaf8  brfalse  loc_8EC11
0x8eafd  ldc.i4.0
0x8eafe  stloc.1
0x8eaff  br       loc_8EC08
0x8eb04  ldsfld   string [mscorlib]System.String::Empty
0x8eb09  stloc.2
0x8eb0a  ldsfld   string [mscorlib]System.String::Empty
0x8eb0f  stloc.3
0x8eb10  ldarg.2
0x8eb11  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.WindowsEventCollection.SubscriptionSourceStatus> Microsoft.WindowsEventCollection.SubscriptionStatus::get_SourceStatuses()
0x8eb16  ldloc.0
0x8eb17  ldloc.1
0x8eb18  ldelem.ref
0x8eb19  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.WindowsEventCollection.SubscriptionSourceStatus>::ContainsKey(var<u1>)
0x8eb1e  brfalse  loc_8EC04
0x8eb23  ldarg.2
0x8eb24  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.WindowsEventCollection.SubscriptionSourceStatus> Microsoft.WindowsEventCollection.SubscriptionStatus::get_SourceStatuses()
0x8eb29  ldloc.0
0x8eb2a  ldloc.1
0x8eb2b  ldelem.ref
0x8eb2c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.WindowsEventCollection.SubscriptionSourceStatus>::get_Item(void)
0x8eb31  stloc.s  4
0x8eb33  ldarg.0
0x8eb34  ldloc.s  4
0x8eb36  ldloca.s 2
0x8eb38  ldloca.s 3
0x8eb3a  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::ExtractWSManConfigNode(class Microsoft.WindowsEventCollection.SubscriptionSourceStatus sourceStatus, string& xmlToSend, string& xmlToDisplay)
0x8eb3f  brfalse  loc_8EC04
0x8eb44  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x8eb49  dup
0x8eb4a  call     string Microsoft.Windows.ManagementUI.CombinedControls.Resources.SubscriptionResources::get_ConfirmWSManSettingsPrompt()
0x8eb4f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8eb54  pop
0x8eb55  dup
0x8eb56  ldstr    asc_BF510// "\n\n"
0x8eb5b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8eb60  pop
0x8eb61  dup
0x8eb62  ldloc.3
0x8eb63  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8eb68  pop
0x8eb69  dup
0x8eb6a  ldstr    asc_BA972// "\n"
0x8eb6f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8eb74  pop
0x8eb75  dup
0x8eb76  call     string Microsoft.Windows.ManagementUI.CombinedControls.Resources.SubscriptionResources::get_ConfirmWSManSettingsQuestion()
0x8eb7b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8eb80  pop
0x8eb81  callvirt instance string [mscorlib]System.Object::ToString()
0x8eb86  ldstr    aViewername// "ViewerName"
0x8eb8b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x8eb90  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.QueryMessage::QueryUser(string message, string caption)
0x8eb95  ldc.i4.6
0x8eb96  bne.un.s loc_8EC04
0x8eb98  ldnull
0x8eb99  stloc.s  5
0x8eb9b  ldnull
0x8eb9c  stloc.s  6
0x8eb9e  ldloc.s  4
0x8eba0  callvirt instance unsigned int32 Microsoft.WindowsEventCollection.SubscriptionSourceStatus::get_LastError()
0x8eba5  ldc.i4   0x803380AA
0x8ebaa  beq.s    loc_8EBB1
0x8ebac  ldloc.0
0x8ebad  ldloc.1
0x8ebae  ldelem.ref
0x8ebaf  stloc.s  6
0x8ebb1  ldarg.0
0x8ebb2  ldloc.s  6
0x8ebb4  ldloca.s 5
0x8ebb6  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::CreateWSManSession(string connectionString, class Microsoft.Windows.ManagementUI.CombinedControls.IWSManSession& wsManSession)
0x8ebbb  brfalse.s loc_8EBE7
0x8ebbd  ldarg.0
0x8ebbe  ldloc.s  5
0x8ebc0  ldstr    aEnableremoting// "EnableRemoting"
0x8ebc5  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/wbem/wsman"...
0x8ebca  ldloc.2
0x8ebcb  ldc.i4.0
0x8ebcc  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.IWSManSession::Invoke([in] string actionURI, [in] object resourceUri, [in] string parameters, [in] int32 flags)
0x8ebd1  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::wsManInfo
0x8ebd6  ldarg.0
0x8ebd7  ldc.i4.0
0x8ebd8  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::flagNewSubscription
0x8ebdd  ldarg.s  4
0x8ebdf  brfalse.s loc_8EBE7
0x8ebe1  ldarg.0
0x8ebe2  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::ApplyAndClose()
0x8ebe7  leave.s  loc_8EC04
0x8ebe9  stloc.s  7
0x8ebeb  ldarg.0
0x8ebec  ldloc.s  7
0x8ebee  callvirt instance string [mscorlib]System.Exception::get_Message()
0x8ebf3  ldstr    aViewername// "ViewerName"
0x8ebf8  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x8ebfd  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x8ec02  leave.s  loc_8EC04
0x8ec04  ldloc.1
0x8ec05  ldc.i4.1
0x8ec06  add
0x8ec07  stloc.1
0x8ec08  ldloc.1
0x8ec09  ldloc.0
0x8ec0a  ldlen
0x8ec0b  conv.i4
0x8ec0c  blt      loc_8EB04
0x8ec11  ldc.i4.1
0x8ec12  ret
```
