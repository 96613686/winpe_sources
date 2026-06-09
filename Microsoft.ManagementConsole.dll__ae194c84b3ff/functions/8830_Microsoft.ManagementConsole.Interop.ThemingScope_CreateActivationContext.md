# Microsoft.ManagementConsole.Interop.ThemingScope::CreateActivationContext

- ea: `0x8830`
- end: `0x88e7`
- name: `Microsoft.ManagementConsole.Interop.ThemingScope::CreateActivationContext`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x8960`

## callees

- `0x8740`
- `0x8830`

## pseudocode

```c

```

## disassembly

```asm
0x8830  ldtoken  Microsoft.ManagementConsole.Interop.ThemingScope
0x8835  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x883a  dup
0x883b  stloc.1
0x883c  call     void [mscorlib]System.Threading.Monitor::Enter(object)
0x8841  ldarg.0
0x8842  ldfld    bool Microsoft.ManagementConsole.Interop.ThemingScope::contextCreationSucceeded
0x8847  brtrue   loc_88D5
0x884c  call     class [System.Windows.Forms]System.Windows.Forms.OSFeature [System.Windows.Forms]System.Windows.Forms.OSFeature::get_Feature()
0x8851  ldsfld   object [System.Windows.Forms]System.Windows.Forms.OSFeature::Themes
0x8856  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.FeatureSupport::IsPresent(object)
0x885b  brfalse.s loc_88D5
0x885d  ldarg.0
0x885e  ldflda   valuetype ACTCTX Microsoft.ManagementConsole.Interop.ThemingScope::enableThemingActivationContext
0x8863  initobj  ACTCTX
0x8869  ldarg.0
0x886a  ldflda   valuetype ACTCTX Microsoft.ManagementConsole.Interop.ThemingScope::enableThemingActivationContext
0x886f  ldtoken  ACTCTX
0x8874  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8879  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(class [mscorlib]System.Type)
0x887e  stfld    int32 ACTCTX::cbSize
0x8883  ldarg.0
0x8884  ldflda   valuetype ACTCTX Microsoft.ManagementConsole.Interop.ThemingScope::enableThemingActivationContext
0x8889  ldarg.1
0x888a  stfld    string ACTCTX::lpSource
0x888f  ldarg.0
0x8890  ldflda   valuetype ACTCTX Microsoft.ManagementConsole.Interop.ThemingScope::enableThemingActivationContext
0x8895  ldc.i4.s 0x65
0x8897  call     native int [mscorlib]System.IntPtr::op_Explicit(int32)
0x889c  stfld    native int ACTCTX::lpResourceName
0x88a1  ldarg.0
0x88a2  ldflda   valuetype ACTCTX Microsoft.ManagementConsole.Interop.ThemingScope::enableThemingActivationContext
0x88a7  ldc.i4.8
0x88a8  stfld    unsigned int32 ACTCTX::dwFlags
0x88ad  ldarg.0
0x88ae  ldarg.0
0x88af  ldflda   valuetype ACTCTX Microsoft.ManagementConsole.Interop.ThemingScope::enableThemingActivationContext
0x88b4  call     native int Microsoft.ManagementConsole.Interop.ThemingScope::CreateActCtx(valuetype ACTCTX& actctx)
0x88b9  stfld    native int Microsoft.ManagementConsole.Interop.ThemingScope::hActCtx
0x88be  ldarg.0
0x88bf  ldarg.0
0x88c0  ldfld    native int Microsoft.ManagementConsole.Interop.ThemingScope::hActCtx
0x88c5  ldc.i4.m1
0x88c6  newobj   instance void [mscorlib]System.IntPtr::.ctor(int32)
0x88cb  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x88d0  stfld    bool Microsoft.ManagementConsole.Interop.ThemingScope::contextCreationSucceeded
0x88d5  ldarg.0
0x88d6  ldfld    bool Microsoft.ManagementConsole.Interop.ThemingScope::contextCreationSucceeded
0x88db  stloc.0
0x88dc  leave.s  loc_88E5
0x88de  ldloc.1
0x88df  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x88e4  endfinally
0x88e5  ldloc.0
0x88e6  ret
```
