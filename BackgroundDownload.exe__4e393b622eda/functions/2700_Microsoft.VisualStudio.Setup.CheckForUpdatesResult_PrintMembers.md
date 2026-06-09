# Microsoft.VisualStudio.Setup.CheckForUpdatesResult::PrintMembers

- ea: `0x2700`
- end: `0x2787`
- name: `Microsoft.VisualStudio.Setup.CheckForUpdatesResult::PrintMembers`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x26c0`

## callees

- `0x2640`
- `0x2660`
- `0x2680`
- `0x26a0`

## string_xrefs

- `0x2706`: `EngineUpdateRequired = `
- `0x275f`: `, UpdateResultCode = `

## pseudocode

```c

```

## disassembly

```asm
0x2700  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::EnsureSufficientExecutionStack()
0x2705  ldarg.1
0x2706  ldstr    aEngineupdatere// "EngineUpdateRequired = "
0x270b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2710  pop
0x2711  ldarg.1
0x2712  ldarg.0
0x2713  call     instance bool Microsoft.VisualStudio.Setup.CheckForUpdatesResult::get_EngineUpdateRequired()
0x2718  stloc.0
0x2719  ldloca.s 0
0x271b  constrained. [mscorlib]System.Boolean
0x2721  callvirt instance string [mscorlib]System.Object::ToString()
0x2726  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x272b  pop
0x272c  ldarg.1
0x272d  ldstr    aOpcurl// ", OpcUrl = "
0x2732  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2737  pop
0x2738  ldarg.1
0x2739  ldarg.0
0x273a  call     instance string Microsoft.VisualStudio.Setup.CheckForUpdatesResult::get_OpcUrl()
0x273f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x2744  pop
0x2745  ldarg.1
0x2746  ldstr    aOpcversion// ", OpcVersion = "
0x274b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2750  pop
0x2751  ldarg.1
0x2752  ldarg.0
0x2753  call     instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.CheckForUpdatesResult::get_OpcVersion()
0x2758  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x275d  pop
0x275e  ldarg.1
0x275f  ldstr    aUpdateresultco// ", UpdateResultCode = "
0x2764  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2769  pop
0x276a  ldarg.1
0x276b  ldarg.0
0x276c  call     instance int32 Microsoft.VisualStudio.Setup.CheckForUpdatesResult::get_UpdateResultCode()
0x2771  stloc.1
0x2772  ldloca.s 1
0x2774  constrained. [mscorlib]System.Int32
0x277a  callvirt instance string [mscorlib]System.Object::ToString()
0x277f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2784  pop
0x2785  ldc.i4.1
0x2786  ret
```
