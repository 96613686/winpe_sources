# Microsoft.VisualStudio.Setup.ElevationRequest::PrintMembers

- ea: `0xb50`
- end: `0xc30`
- name: `Microsoft.VisualStudio.Setup.ElevationRequest::PrintMembers`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0xb10`

## callees

- `0xa30`
- `0xa50`
- `0xa70`
- `0xa90`
- `0xab0`
- `0xad0`
- `0xaf0`

## pseudocode

```c

```

## disassembly

```asm
0xb50  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::EnsureSufficientExecutionStack()
0xb55  ldarg.1
0xb56  ldstr    aActivityid// "ActivityId = "
0xb5b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb60  pop
0xb61  ldarg.1
0xb62  ldarg.0
0xb63  call     instance string Microsoft.VisualStudio.Setup.ElevationRequest::get_ActivityId()
0xb68  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0xb6d  pop
0xb6e  ldarg.1
0xb6f  ldstr    aSerializedsess// ", SerializedSession = "
0xb74  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb79  pop
0xb7a  ldarg.1
0xb7b  ldarg.0
0xb7c  call     instance string Microsoft.VisualStudio.Setup.ElevationRequest::get_SerializedSession()
0xb81  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0xb86  pop
0xb87  ldarg.1
0xb88  ldstr    aLocale// ", Locale = "
0xb8d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xb92  pop
0xb93  ldarg.1
0xb94  ldarg.0
0xb95  call     instance string Microsoft.VisualStudio.Setup.ElevationRequest::get_Locale()
0xb9a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0xb9f  pop
0xba0  ldarg.1
0xba1  ldstr    aCampaignid// ", CampaignId = "
0xba6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xbab  pop
0xbac  ldarg.1
0xbad  ldarg.0
0xbae  call     instance string Microsoft.VisualStudio.Setup.ElevationRequest::get_CampaignId()
0xbb3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0xbb8  pop
0xbb9  ldarg.1
0xbba  ldstr    aHandle// ", Handle = "
0xbbf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xbc4  pop
0xbc5  ldarg.1
0xbc6  ldarg.0
0xbc7  call     instance int64 Microsoft.VisualStudio.Setup.ElevationRequest::get_Handle()
0xbcc  stloc.0
0xbcd  ldloca.s 0
0xbcf  constrained. [mscorlib]System.Int64
0xbd5  callvirt instance string [mscorlib]System.Object::ToString()
0xbda  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xbdf  pop
0xbe0  ldarg.1
0xbe1  ldstr    aIsquiet// ", IsQuiet = "
0xbe6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xbeb  pop
0xbec  ldarg.1
0xbed  ldarg.0
0xbee  call     instance bool Microsoft.VisualStudio.Setup.ElevationRequest::get_IsQuiet()
0xbf3  stloc.1
0xbf4  ldloca.s 1
0xbf6  constrained. [mscorlib]System.Boolean
0xbfc  callvirt instance string [mscorlib]System.Object::ToString()
0xc01  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc06  pop
0xc07  ldarg.1
0xc08  ldstr    aIspassive// ", IsPassive = "
0xc0d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc12  pop
0xc13  ldarg.1
0xc14  ldarg.0
0xc15  call     instance bool Microsoft.VisualStudio.Setup.ElevationRequest::get_IsPassive()
0xc1a  stloc.1
0xc1b  ldloca.s 1
0xc1d  constrained. [mscorlib]System.Boolean
0xc23  callvirt instance string [mscorlib]System.Object::ToString()
0xc28  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc2d  pop
0xc2e  ldc.i4.1
0xc2f  ret
```
