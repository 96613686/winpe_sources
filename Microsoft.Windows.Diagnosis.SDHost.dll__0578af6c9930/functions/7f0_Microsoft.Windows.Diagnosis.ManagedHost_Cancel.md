# Microsoft.Windows.Diagnosis.ManagedHost::Cancel

- ea: `0x7f0`
- end: `0x833`
- name: `Microsoft.Windows.Diagnosis.ManagedHost::Cancel`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x7f0`

## pseudocode

```c

```

## disassembly

```asm
0x7f0  ldnull
0x7f1  stloc.0
0x7f2  ldarg.0
0x7f3  ldfld    object Microsoft.Windows.Diagnosis.ManagedHost::m_Lock
0x7f8  stloc.1
0x7f9  ldc.i4.0
0x7fa  stloc.2
0x7fb  ldloc.1
0x7fc  ldloca.s 2
0x7fe  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x803  ldarg.0
0x804  ldfld    class [System.Management.Automation]System.Management.Automation.PowerShell Microsoft.Windows.Diagnosis.ManagedHost::m_PowerShell
0x809  stloc.0
0x80a  leave.s  loc_816
0x80c  ldloc.2
0x80d  brfalse.s loc_815
0x80f  ldloc.1
0x810  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x815  endfinally
0x816  nop
0x817  ldloc.0
0x818  brfalse.s loc_823
0x81a  ldloc.0
0x81b  ldnull
0x81c  ldnull
0x81d  callvirt instance class [mscorlib]System.IAsyncResult [System.Management.Automation]System.Management.Automation.PowerShell::BeginStop(class [mscorlib]System.AsyncCallback, object)
0x822  pop
0x823  leave.s  loc_832
0x825  pop
0x826  ldc.i4   0x803C0102
0x82b  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x830  leave.s  loc_832
0x832  ret
```
