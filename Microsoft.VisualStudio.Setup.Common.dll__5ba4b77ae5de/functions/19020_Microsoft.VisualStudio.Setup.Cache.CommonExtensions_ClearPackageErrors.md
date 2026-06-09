# Microsoft.VisualStudio.Setup.Cache.CommonExtensions::ClearPackageErrors

- ea: `0x19020`
- end: `0x1905c`
- name: `Microsoft.VisualStudio.Setup.Cache.CommonExtensions::ClearPackageErrors`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0xc1a0`
- `0x19020`
- `0x19360`
- `0x19470`
- `0x19480`
- `0x1aa60`
- `0x1aa70`

## pseudocode

```c

```

## disassembly

```asm
0x19020  ldarg.0
0x19021  ldstr    aInstance// "instance"
0x19026  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x1902b  ldarg.0
0x1902c  callvirt instance class Microsoft.VisualStudio.Setup.Cache.ErrorState Microsoft.VisualStudio.Setup.Cache.Instance::get_Errors()
0x19031  dup
0x19032  brtrue.s loc_19038
0x19034  pop
0x19035  ldnull
0x19036  br.s     loc_1903D
0x19038  call     instance class [mscorlib]System.Exception Microsoft.VisualStudio.Setup.Cache.ErrorState::get_RuntimeError()
0x1903d  stloc.0
0x1903e  ldloc.0
0x1903f  brfalse.s loc_19054
0x19041  ldarg.0
0x19042  newobj   instance void Microsoft.VisualStudio.Setup.Cache.ErrorState::.ctor()
0x19047  dup
0x19048  ldloc.0
0x19049  callvirt instance void Microsoft.VisualStudio.Setup.Cache.ErrorState::set_RuntimeError(class [mscorlib]System.Exception value)
0x1904e  callvirt instance void Microsoft.VisualStudio.Setup.Cache.Instance::set_Errors(class Microsoft.VisualStudio.Setup.Cache.ErrorState value)
0x19053  ret
0x19054  ldarg.0
0x19055  ldnull
0x19056  callvirt instance void Microsoft.VisualStudio.Setup.Cache.Instance::set_Errors(class Microsoft.VisualStudio.Setup.Cache.ErrorState value)
0x1905b  ret
```
