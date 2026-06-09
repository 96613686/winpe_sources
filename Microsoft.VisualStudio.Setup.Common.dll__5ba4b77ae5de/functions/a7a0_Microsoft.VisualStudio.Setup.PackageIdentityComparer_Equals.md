# Microsoft.VisualStudio.Setup.PackageIdentityComparer::Equals

- ea: `0xa7a0`
- end: `0xa7fd`
- name: `Microsoft.VisualStudio.Setup.PackageIdentityComparer::Equals`
- size: `93`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x9f70`
- `0xa470`
- `0x158c0`
- `0x162e0`
- `0x17cd0`
- `0x18120`
- `0x1bb40`
- `0x1bc10`
- `0x1bdf0`
- `0x1c4d0`
- `0x1d3c0`

## callees

- `0xa7a0`

## pseudocode

```c

```

## disassembly

```asm
0xa7a0  ldarg.0
0xa7a1  ldarg.1
0xa7a2  ldarg.2
0xa7a3  ldsfld   class [mscorlib]System.Func`4<string, string, valuetype [mscorlib]System.StringComparison, bool> <>O::<3>__Equals
0xa7a8  dup
0xa7a9  brtrue.s loc_A7BE
0xa7ab  pop
0xa7ac  ldnull
0xa7ad  ldftn    bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xa7b3  newobj   instance void class [mscorlib]System.Func`4<string, string, valuetype [mscorlib]System.StringComparison, bool>::.ctor(object, native int)
0xa7b8  dup
0xa7b9  stsfld   class [mscorlib]System.Func`4<string, string, valuetype [mscorlib]System.StringComparison, bool> <>O::<3>__Equals
0xa7be  ldsfld   class [mscorlib]System.Func`3<class [mscorlib]System.Version, class [mscorlib]System.Version, bool> <>O::<4>__AreVersionsEqual
0xa7c3  dup
0xa7c4  brtrue.s loc_A7D9
0xa7c6  pop
0xa7c7  ldnull
0xa7c8  ldftn    bool Microsoft.VisualStudio.Setup.PackageIdentityComparer::AreVersionsEqual(class [mscorlib]System.Version x, class [mscorlib]System.Version y)
0xa7ce  newobj   instance void class [mscorlib]System.Func`3<class [mscorlib]System.Version, class [mscorlib]System.Version, bool>::.ctor(object, native int)
0xa7d3  dup
0xa7d4  stsfld   class [mscorlib]System.Func`3<class [mscorlib]System.Version, class [mscorlib]System.Version, bool> <>O::<4>__AreVersionsEqual
0xa7d9  ldsfld   class [mscorlib]System.Func`2<bool, bool> <>O::<5>__IsEqualEqualityResult
0xa7de  dup
0xa7df  brtrue.s loc_A7F4
0xa7e1  pop
0xa7e2  ldnull
0xa7e3  ldftn    bool Microsoft.VisualStudio.Setup.PackageIdentityComparer::IsEqualEqualityResult(bool result)
0xa7e9  newobj   instance void class [mscorlib]System.Func`2<bool, bool>::.ctor(object, native int)
0xa7ee  dup
0xa7ef  stsfld   class [mscorlib]System.Func`2<bool, bool> <>O::<5>__IsEqualEqualityResult
0xa7f4  ldc.i4.1
0xa7f5  ldc.i4.0
0xa7f6  ldc.i4.0
0xa7f7  call     T0x2B000052
0xa7fc  ret
```
