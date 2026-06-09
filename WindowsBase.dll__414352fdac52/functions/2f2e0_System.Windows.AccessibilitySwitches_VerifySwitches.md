# System.Windows.AccessibilitySwitches::VerifySwitches

- ea: `0x2f2e0`
- end: `0x2f386`
- name: `System.Windows.AccessibilitySwitches::VerifySwitches`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x3be40`

## callees

- `0x2c100`
- `0x2f2e0`
- `0x2f390`
- `0x2f430`

## string_xrefs

- `0x2f370`: `CombinationOfAccessibilitySwitchesNotSupported`

## pseudocode

```c

```

## disassembly

```asm
0x2f2e0  ldsflda  int32 System.Windows.AccessibilitySwitches::s_SwitchesVerified
0x2f2e5  ldc.i4.1
0x2f2e6  ldc.i4.0
0x2f2e7  call     int32 [mscorlib]System.Threading.Interlocked::CompareExchange(int32&, int32, int32)
0x2f2ec  brtrue   loc_2F385
0x2f2f1  ldloca.s 0
0x2f2f3  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x2f2f9  ldc.i4.0
0x2f2fa  stloc.1
0x2f2fb  ldtoken  System.Windows.AccessibilitySwitches
0x2f300  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2f305  stloc.2
0x2f306  ldsfld   string[] System.Windows.AccessibilitySwitches::AccessibilityPropertyNames
0x2f30b  stloc.3
0x2f30c  ldc.i4.0
0x2f30d  stloc.s  4
0x2f30f  br.s     loc_2F365
0x2f311  ldloc.3
0x2f312  ldloc.s  4
0x2f314  ldelem.ref
0x2f315  stloc.s  5
0x2f317  ldloc.2
0x2f318  ldloc.s  5
0x2f31a  ldc.i4.s 0x18
0x2f31c  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x2f321  stloc.s  6
0x2f323  ldloc.s  6
0x2f325  ldnull
0x2f326  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object)
0x2f32b  unbox.any [mscorlib]System.Boolean
0x2f330  stloc.s  7
0x2f332  ldloc.s  7
0x2f334  brtrue.s loc_2F351
0x2f336  ldloc.0
0x2f337  stloc.s  8
0x2f339  ldc.i4.1
0x2f33a  stloc.s  9
0x2f33c  ldloca.s 8
0x2f33e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x2f343  ldloc.s  9
0x2f345  ceq
0x2f347  ldloca.s 8
0x2f349  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x2f34e  and
0x2f34f  br.s     loc_2F352
0x2f351  ldc.i4.0
0x2f352  dup
0x2f353  stloc.1
0x2f354  brtrue.s loc_2F36C
0x2f356  ldloca.s 0
0x2f358  ldloc.s  7
0x2f35a  call     instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x2f35f  ldloc.s  4
0x2f361  ldc.i4.1
0x2f362  add
0x2f363  stloc.s  4
0x2f365  ldloc.s  4
0x2f367  ldloc.3
0x2f368  ldlen
0x2f369  conv.i4
0x2f36a  blt.s    loc_2F311
0x2f36c  ldloc.1
0x2f36d  brfalse.s loc_2F37F
0x2f36f  ldarg.0
0x2f370  ldstr    aCombinationofa// "CombinationOfAccessibilitySwitchesNotSu"...
0x2f375  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x2f37a  call     void System.Windows.AccessibilitySwitches::DispatchOnError(class System.Windows.Threading.Dispatcher dispatcher, string message)
0x2f37f  ldarg.0
0x2f380  call     void System.Windows.AccessibilitySwitches::VerifyDependencies(class System.Windows.Threading.Dispatcher dispatcher)
0x2f385  ret
```
