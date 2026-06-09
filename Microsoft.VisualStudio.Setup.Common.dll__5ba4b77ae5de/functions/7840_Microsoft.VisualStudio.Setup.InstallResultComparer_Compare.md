# Microsoft.VisualStudio.Setup.InstallResultComparer::Compare

- ea: `0x7840`
- end: `0x78c5`
- name: `Microsoft.VisualStudio.Setup.InstallResultComparer::Compare`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x78d0`

## callees

- `0x4c10`
- `0x73f0`
- `0x7490`
- `0x7840`
- `0x7940`

## pseudocode

```c

```

## disassembly

```asm
0x7840  ldarg.1
0x7841  ldarg.2
0x7842  bne.un.s loc_7846
0x7844  ldc.i4.0
0x7845  ret
0x7846  ldarg.1
0x7847  brtrue.s loc_784B
0x7849  ldc.i4.m1
0x784a  ret
0x784b  ldarg.2
0x784c  brtrue.s loc_7850
0x784e  ldc.i4.1
0x784f  ret
0x7850  ldc.i4.0
0x7851  stloc.0
0x7852  ldarg.0
0x7853  ldfld    valuetype Comparisons Microsoft.VisualStudio.Setup.InstallResultComparer::comparison
0x7858  ldc.i4.1
0x7859  and
0x785a  ldc.i4.1
0x785b  bne.un.s loc_78A2
0x785d  ldarg.0
0x785e  ldfld    bool Microsoft.VisualStudio.Setup.InstallResultComparer::hResultCompatible
0x7863  brfalse.s loc_788B
0x7865  ldarg.1
0x7866  callvirt instance int32 Microsoft.VisualStudio.Setup.InstallResult::get_ReturnCode()
0x786b  ldloca.s 1
0x786d  call     bool Microsoft.VisualStudio.Setup.ErrorCode::TryGetWin32Error(int32 hresult, [out] int32& error)
0x7872  pop
0x7873  ldarg.2
0x7874  callvirt instance int32 Microsoft.VisualStudio.Setup.InstallResult::get_ReturnCode()
0x7879  ldloca.s 2
0x787b  call     bool Microsoft.VisualStudio.Setup.ErrorCode::TryGetWin32Error(int32 hresult, [out] int32& error)
0x7880  pop
0x7881  ldloc.1
0x7882  ldloc.2
0x7883  call     int32 Microsoft.VisualStudio.Setup.InstallResultComparer::Compare(int32 x, int32 y)
0x7888  stloc.0
0x7889  br.s     loc_789D
0x788b  ldarg.1
0x788c  callvirt instance int32 Microsoft.VisualStudio.Setup.InstallResult::get_ReturnCode()
0x7891  ldarg.2
0x7892  callvirt instance int32 Microsoft.VisualStudio.Setup.InstallResult::get_ReturnCode()
0x7897  call     int32 Microsoft.VisualStudio.Setup.InstallResultComparer::Compare(int32 x, int32 y)
0x789c  stloc.0
0x789d  ldloc.0
0x789e  brfalse.s loc_78A2
0x78a0  ldloc.0
0x78a1  ret
0x78a2  ldarg.0
0x78a3  ldfld    valuetype Comparisons Microsoft.VisualStudio.Setup.InstallResultComparer::comparison
0x78a8  ldc.i4.2
0x78a9  and
0x78aa  ldc.i4.2
0x78ab  bne.un.s loc_78C3
0x78ad  ldarg.1
0x78ae  callvirt instance int32 Microsoft.VisualStudio.Setup.InstallResult::get_MessageId()
0x78b3  ldarg.2
0x78b4  callvirt instance int32 Microsoft.VisualStudio.Setup.InstallResult::get_MessageId()
0x78b9  call     int32 Microsoft.VisualStudio.Setup.InstallResultComparer::Compare(int32 x, int32 y)
0x78be  stloc.0
0x78bf  ldloc.0
0x78c0  pop
0x78c1  ldloc.0
0x78c2  ret
0x78c3  ldloc.0
0x78c4  ret
```
