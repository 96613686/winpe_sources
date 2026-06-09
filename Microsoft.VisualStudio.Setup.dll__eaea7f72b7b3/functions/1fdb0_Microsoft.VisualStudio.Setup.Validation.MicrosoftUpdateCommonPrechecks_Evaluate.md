# Microsoft.VisualStudio.Setup.Validation.MicrosoftUpdateCommonPrechecks::Evaluate

- ea: `0x1fdb0`
- end: `0x1fe76`
- name: `Microsoft.VisualStudio.Setup.Validation.MicrosoftUpdateCommonPrechecks::Evaluate`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x199a0`
- `0x1fdb0`
- `0x21b80`
- `0x21c50`
- `0x21ce0`
- `0x282b0`
- `0x282d0`
- `0x3ea80`
- `0x3ea90`
- `0x3ec40`

## string_xrefs

- `0x1fdd6`: `PreCheck_AdminUpdateNotEnabled`
- `0x1fe0a`: `PreCheck_AdminUpdateOptedOut`
- `0x1fe52`: `PreCheck_ConsumerUpdateOptedOut`

## pseudocode

```c

```

## disassembly

```asm
0x1fdb0  ldarg.0
0x1fdb1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry Microsoft.VisualStudio.Setup.Validation.MicrosoftUpdateCommonPrechecks::registry
0x1fdb6  ldarg.0
0x1fdb7  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Validation.MicrosoftUpdateCommonPrechecks::logger
0x1fdbc  call     int32 Microsoft.VisualStudio.Setup.Utility.MicrosoftUpdateUtilities::GetEnterpriseAutomaticUpdateRegKey(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry registry, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x1fdc1  ldc.i4.1
0x1fdc2  bne.un.s loc_1FE2C
0x1fdc4  ldarg.0
0x1fdc5  ldfld    class Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.Validation.MicrosoftUpdateCommonPrechecks::policy
0x1fdca  callvirt instance valuetype Microsoft.VisualStudio.Setup.Services.AutomaticUpdatesValue Microsoft.VisualStudio.Setup.Services.IPolicyService::get_AdministratorUpdatesEnabled()
0x1fdcf  brtrue.s loc_1FDF8
0x1fdd1  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x1fdd6  ldstr    aPrecheckAdminu// "PreCheck_AdminUpdateNotEnabled"
0x1fddb  call     T0x2B000003
0x1fde0  newobj   instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::.ctor(class [mscorlib]System.Resources.ResourceManager resourceManager, string resourceId, object[] args)
0x1fde5  dup
0x1fde6  ldc.i4.0
0x1fde7  callvirt instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::set_IsWarning(bool value)
0x1fdec  dup
0x1fded  ldsfld   int32 Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::AdministratorUpdatesEnabledRegValueZeroOrNotSetExitCode
0x1fdf2  callvirt instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::set_ErrorCode(int32 value)
0x1fdf7  ret
0x1fdf8  ldarg.0
0x1fdf9  ldfld    class Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.Validation.MicrosoftUpdateCommonPrechecks::policy
0x1fdfe  callvirt instance bool Microsoft.VisualStudio.Setup.Services.IPolicyService::get_AdministratorUpdatesOptOut()
0x1fe03  brfalse.s loc_1FE74
0x1fe05  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x1fe0a  ldstr    aPrecheckAdminu_0// "PreCheck_AdminUpdateOptedOut"
0x1fe0f  call     T0x2B000003
0x1fe14  newobj   instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::.ctor(class [mscorlib]System.Resources.ResourceManager resourceManager, string resourceId, object[] args)
0x1fe19  dup
0x1fe1a  ldc.i4.0
0x1fe1b  callvirt instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::set_IsWarning(bool value)
0x1fe20  dup
0x1fe21  ldsfld   int32 Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::AdministratorUpdatesOptOutRegValueSetExitCode
0x1fe26  callvirt instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::set_ErrorCode(int32 value)
0x1fe2b  ret
0x1fe2c  ldarg.0
0x1fe2d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry Microsoft.VisualStudio.Setup.Validation.MicrosoftUpdateCommonPrechecks::registry
0x1fe32  ldarg.0
0x1fe33  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Validation.MicrosoftUpdateCommonPrechecks::logger
0x1fe38  call     int32 Microsoft.VisualStudio.Setup.Utility.MicrosoftUpdateUtilities::GetConsumerAutomaticUpdateRegKey(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry registry, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x1fe3d  ldc.i4.1
0x1fe3e  bne.un.s loc_1FE74
0x1fe40  ldarg.0
0x1fe41  ldfld    class Microsoft.VisualStudio.Setup.Services.IPolicyService Microsoft.VisualStudio.Setup.Validation.MicrosoftUpdateCommonPrechecks::policy
0x1fe46  callvirt instance bool Microsoft.VisualStudio.Setup.Services.IPolicyService::get_VSthroughMUUpdatesOptOut()
0x1fe4b  brfalse.s loc_1FE74
0x1fe4d  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x1fe52  ldstr    aPrecheckConsum// "PreCheck_ConsumerUpdateOptedOut"
0x1fe57  call     T0x2B000003
0x1fe5c  newobj   instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::.ctor(class [mscorlib]System.Resources.ResourceManager resourceManager, string resourceId, object[] args)
0x1fe61  dup
0x1fe62  ldc.i4.0
0x1fe63  callvirt instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::set_IsWarning(bool value)
0x1fe68  dup
0x1fe69  ldsfld   int32 Microsoft.VisualStudio.Setup.MicrosoftUpdateConstants::VSthroughMUUpdatesOptOutRegValueSetExitCode
0x1fe6e  callvirt instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::set_ErrorCode(int32 value)
0x1fe73  ret
0x1fe74  ldnull
0x1fe75  ret
```
