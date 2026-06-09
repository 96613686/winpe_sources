# Microsoft.Windows.Diagnosis.ManagedHost::ExecuteCommand

- ea: `0x200`
- end: `0x329`
- name: `Microsoft.Windows.Diagnosis.ManagedHost::ExecuteCommand`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x330`

## callees

- `0x200`
- `0x520`
- `0x790`
- `0x840`

## pseudocode

```c

```

## disassembly

```asm
0x200  ldnull
0x201  stloc.0
0x202  ldc.i4.0
0x203  stloc.1
0x204  ldnull
0x205  stloc.2
0x206  ldarg.0
0x207  ldfld    object Microsoft.Windows.Diagnosis.ManagedHost::m_Lock
0x20c  stloc.3
0x20d  ldc.i4.0
0x20e  stloc.s  4
0x210  ldloc.3
0x211  ldloca.s 4
0x213  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x218  ldarg.0
0x219  ldarg.1
0x21a  stfld    class [System.Management.Automation]System.Management.Automation.PowerShell Microsoft.Windows.Diagnosis.ManagedHost::m_PowerShell
0x21f  leave.s  loc_22C
0x221  ldloc.s  4
0x223  brfalse.s loc_22B
0x225  ldloc.3
0x226  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x22b  endfinally
0x22c  ldarg.1
0x22d  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Management.Automation]System.Management.Automation.PSObject> [System.Management.Automation]System.Management.Automation.PowerShell::Invoke()
0x232  pop
0x233  leave    loc_2CF
0x238  stloc.s  5
0x23a  ldarg.1
0x23b  callvirt instance class [System.Management.Automation]System.Management.Automation.PSInvocationStateInfo [System.Management.Automation]System.Management.Automation.PowerShell::get_InvocationStateInfo()
0x240  callvirt instance valuetype [System.Management.Automation]System.Management.Automation.PSInvocationState [System.Management.Automation]System.Management.Automation.PSInvocationStateInfo::get_State()
0x245  ldc.i4.5
0x246  beq.s    loc_267
0x248  ldarg.0
0x249  ldloc.s  5
0x24b  callvirt instance string [mscorlib]System.Object::ToString()
0x250  ldstr    aScriptexceptio// "ScriptException"
0x255  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.Windows.Diagnosis.ManagedHost::ConvertStringToXml(string errorString, string tagName)
0x25a  stloc.2
0x25b  ldarg.0
0x25c  ldloc.2
0x25d  ldstr    aScriptexceptio// "ScriptException"
0x262  call     instance void Microsoft.Windows.Diagnosis.ManagedHost::SendErrorToReport(class [System.Xml]System.Xml.XmlDocument errorXml, string tagName)
0x267  leave.s  loc_2CF
0x269  ldarg.0
0x26a  ldfld    object Microsoft.Windows.Diagnosis.ManagedHost::m_Lock
0x26f  stloc.3
0x270  ldc.i4.0
0x271  stloc.s  4
0x273  ldloc.3
0x274  ldloca.s 4
0x276  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x27b  ldarg.0
0x27c  ldnull
0x27d  stfld    class [System.Management.Automation]System.Management.Automation.PowerShell Microsoft.Windows.Diagnosis.ManagedHost::m_PowerShell
0x282  leave.s  loc_28F
0x284  ldloc.s  4
0x286  brfalse.s loc_28E
0x288  ldloc.3
0x289  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x28e  endfinally
0x28f  ldarg.1
0x290  callvirt instance class [System.Management.Automation]System.Management.Automation.PSDataStreams [System.Management.Automation]System.Management.Automation.PowerShell::get_Streams()
0x295  callvirt instance class [System.Management.Automation]System.Management.Automation.PSDataCollection`1<class [System.Management.Automation]System.Management.Automation.ErrorRecord> [System.Management.Automation]System.Management.Automation.PSDataStreams::get_Error()
0x29a  stloc.0
0x29b  ldc.i4.0
0x29c  stloc.1
0x29d  br.s     loc_2BD
0x29f  ldarg.0
0x2a0  ldloc.0
0x2a1  ldloc.1
0x2a2  callvirt instance var<u1> class [System.Management.Automation]System.Management.Automation.PSDataCollection`1<class [System.Management.Automation]System.Management.Automation.ErrorRecord>::get_Item(!!T0)
0x2a7  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.Windows.Diagnosis.ManagedHost::ConvertScriptErrorToXml(class [System.Management.Automation]System.Management.Automation.ErrorRecord scriptError)
0x2ac  stloc.2
0x2ad  ldarg.0
0x2ae  ldloc.2
0x2af  ldstr    aScripterror// "ScriptError"
0x2b4  call     instance void Microsoft.Windows.Diagnosis.ManagedHost::SendErrorToReport(class [System.Xml]System.Xml.XmlDocument errorXml, string tagName)
0x2b9  ldloc.1
0x2ba  ldc.i4.1
0x2bb  add
0x2bc  stloc.1
0x2bd  ldloc.1
0x2be  conv.u8
0x2bf  ldloc.0
0x2c0  callvirt instance int32 class [System.Management.Automation]System.Management.Automation.PSDataCollection`1<class [System.Management.Automation]System.Management.Automation.ErrorRecord>::get_Count()
0x2c5  conv.i8
0x2c6  blt.s    loc_29F
0x2c8  ldloc.0
0x2c9  callvirt instance void class [System.Management.Automation]System.Management.Automation.PSDataCollection`1<class [System.Management.Automation]System.Management.Automation.ErrorRecord>::Clear()
0x2ce  endfinally
0x2cf  ldarg.1
0x2d0  callvirt instance class [System.Management.Automation]System.Management.Automation.PSInvocationStateInfo [System.Management.Automation]System.Management.Automation.PowerShell::get_InvocationStateInfo()
0x2d5  callvirt instance valuetype [System.Management.Automation]System.Management.Automation.PSInvocationState [System.Management.Automation]System.Management.Automation.PSInvocationStateInfo::get_State()
0x2da  ldc.i4.5
0x2db  bne.un.s loc_310
0x2dd  ldarg.0
0x2de  ldarg.1
0x2df  callvirt instance class [System.Management.Automation]System.Management.Automation.PSInvocationStateInfo [System.Management.Automation]System.Management.Automation.PowerShell::get_InvocationStateInfo()
0x2e4  callvirt instance class [mscorlib]System.Exception [System.Management.Automation]System.Management.Automation.PSInvocationStateInfo::get_Reason()
0x2e9  callvirt instance string [mscorlib]System.Object::ToString()
0x2ee  ldstr    aScriptexceptio// "ScriptException"
0x2f3  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.Windows.Diagnosis.ManagedHost::ConvertStringToXml(string errorString, string tagName)
0x2f8  stloc.2
0x2f9  ldarg.0
0x2fa  ldloc.2
0x2fb  ldstr    aScriptexceptio// "ScriptException"
0x300  call     instance void Microsoft.Windows.Diagnosis.ManagedHost::SendErrorToReport(class [System.Xml]System.Xml.XmlDocument errorXml, string tagName)
0x305  ldc.i4   0x803C0101
0x30a  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x30f  ret
0x310  ldarg.1
0x311  callvirt instance class [System.Management.Automation]System.Management.Automation.PSInvocationStateInfo [System.Management.Automation]System.Management.Automation.PowerShell::get_InvocationStateInfo()
0x316  callvirt instance valuetype [System.Management.Automation]System.Management.Automation.PSInvocationState [System.Management.Automation]System.Management.Automation.PSInvocationStateInfo::get_State()
0x31b  ldc.i4.3
0x31c  bne.un.s loc_328
0x31e  ldc.i4   0x803C0100
0x323  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x328  ret
```
