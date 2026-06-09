# Microsoft.VisualStudio.Setup.Validation.VSProcessesRunning::.cctor

- ea: `0x22520`
- end: `0x22568`
- name: `Microsoft.VisualStudio.Setup.Validation.VSProcessesRunning::.cctor`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x2252b`: `VsixInstaller`
- `0x22537`: `vsixautoupdate`
- `0x22553`: `ServiceHub.`

## pseudocode

```c

```

## disassembly

```asm
0x22520  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_InvariantCultureIgnoreCase()
0x22525  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x2252a  dup
0x2252b  ldstr    aVsixinstaller// "VsixInstaller"
0x22530  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x22535  pop
0x22536  dup
0x22537  ldstr    aVsixautoupdate_0// "vsixautoupdate"
0x2253c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x22541  pop
0x22542  dup
0x22543  ldstr    aPerfwatson2// "perfwatson2"
0x22548  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x2254d  pop
0x2254e  stsfld   class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Validation.VSProcessesRunning::AllowedProcesses
0x22553  ldstr    aServicehub// "ServiceHub."
0x22558  stsfld   string Microsoft.VisualStudio.Setup.Validation.VSProcessesRunning::AllowedProcessPrefix
0x2255d  ldc.i4   0x1F46
0x22562  stsfld   int32 Microsoft.VisualStudio.Setup.Validation.VSProcessesRunning::ErrorCode
0x22567  ret
```
