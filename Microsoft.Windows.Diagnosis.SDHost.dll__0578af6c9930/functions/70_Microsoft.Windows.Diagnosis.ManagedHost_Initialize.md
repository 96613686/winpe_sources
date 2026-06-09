# Microsoft.Windows.Diagnosis.ManagedHost::Initialize

- ea: `0x70`
- end: `0xeb`
- name: `Microsoft.Windows.Diagnosis.ManagedHost::Initialize`
- size: `123`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x70`
- `0xf0`

## pseudocode

```c

```

## disassembly

```asm
0x70  ldarg.2
0x71  brfalse.s loc_77
0x73  ldarg.s  4
0x75  brtrue.s loc_81
0x77  ldc.i4   0x803C0103
0x7c  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x81  ldarg.0
0x82  ldarg.2
0x83  stfld    class [Microsoft.Windows.Diagnosis.SDCommon]Microsoft.Windows.Diagnosis.IScriptedDiagnosticInteraction Microsoft.Windows.Diagnosis.ManagedHost::m_Engine
0x88  ldarg.0
0x89  ldarg.s  4
0x8b  stfld    string Microsoft.Windows.Diagnosis.ManagedHost::m_ResultPath
0x90  ldarg.0
0x91  ldstr    aManagedhostres// "ManagedHostResources"
0x96  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x9b  newobj   instance void [mscorlib]System.Resources.ResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0xa0  stfld    class [mscorlib]System.Resources.ResourceManager Microsoft.Windows.Diagnosis.ManagedHost::m_ResourceManager
0xa5  ldarg.3
0xa6  brfalse.s loc_C8
0xa8  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xad  ldarg.3
0xae  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(string)
0xb3  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentCulture(class [mscorlib]System.Globalization.CultureInfo)
0xb8  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xbd  ldarg.3
0xbe  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(string)
0xc3  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentUICulture(class [mscorlib]System.Globalization.CultureInfo)
0xc8  ldarg.0
0xc9  call     instance void Microsoft.Windows.Diagnosis.ManagedHost::InitializeRunspace()
0xce  ldarg.0
0xcf  call     class [System.Management.Automation]System.Management.Automation.PowerShell [System.Management.Automation]System.Management.Automation.PowerShell::Create()
0xd4  stfld    class [System.Management.Automation]System.Management.Automation.PowerShell Microsoft.Windows.Diagnosis.ManagedHost::m_Ps
0xd9  ldarg.0
0xda  ldfld    class [System.Management.Automation]System.Management.Automation.PowerShell Microsoft.Windows.Diagnosis.ManagedHost::m_Ps
0xdf  ldarg.0
0xe0  ldfld    class [System.Management.Automation]System.Management.Automation.Runspaces.Runspace Microsoft.Windows.Diagnosis.ManagedHost::m_Runspace
0xe5  callvirt instance void [System.Management.Automation]System.Management.Automation.PowerShell::set_Runspace(class [System.Management.Automation]System.Management.Automation.Runspaces.Runspace)
0xea  ret
```
