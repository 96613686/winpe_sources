# Microsoft.VisualStudio.Setup.InstallSize::GetCustomActualAndRequestedSizes

- ea: `0x7cc0`
- end: `0x7dbe`
- name: `Microsoft.VisualStudio.Setup.InstallSize::GetCustomActualAndRequestedSizes`
- size: `254`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x7ad0`
- `0x7b40`
- `0x7cc0`
- `0x7e30`
- `0x7e50`

## pseudocode

```c

```

## disassembly

```asm
0x7cc0  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x7cc5  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.InstallSizePerDrive>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x7cca  stloc.0
0x7ccb  ldarg.0
0x7ccc  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64>::get_Keys()
0x7cd1  ldarg.0
0x7cd2  ldftn    instance bool Microsoft.VisualStudio.Setup.InstallSize::IsCustomFilter(string tokenName)
0x7cd8  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x7cdd  call     T0x2B00003B
0x7ce2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x7ce7  stloc.1
0x7ce8  br.s     loc_7D0F
0x7cea  ldloc.1
0x7ceb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x7cf0  stloc.2
0x7cf1  ldloc.0
0x7cf2  ldloc.2
0x7cf3  ldloca.s 3
0x7cf5  initobj  Microsoft.VisualStudio.Setup.InstallSizePerDrive
0x7cfb  ldloca.s 3
0x7cfd  ldarg.0
0x7cfe  ldloc.2
0x7cff  call     instance int64 Microsoft.VisualStudio.Setup.InstallSize::get_Item(string key)
0x7d04  call     instance void Microsoft.VisualStudio.Setup.InstallSizePerDrive::set_Actual(int64 value)
0x7d09  ldloc.3
0x7d0a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.InstallSizePerDrive>::Add(var<u1>, !!T0)
0x7d0f  ldloc.1
0x7d10  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7d15  brtrue.s loc_7CEA
0x7d17  leave.s  loc_7D23
0x7d19  ldloc.1
0x7d1a  brfalse.s loc_7D22
0x7d1c  ldloc.1
0x7d1d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7d22  endfinally
0x7d23  ldarg.0
0x7d24  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64> Microsoft.VisualStudio.Setup.InstallSize::get_RequestedSizes()
0x7d29  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64>::get_Keys()
0x7d2e  ldarg.0
0x7d2f  ldftn    instance bool Microsoft.VisualStudio.Setup.InstallSize::IsCustomFilter(string tokenName)
0x7d35  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x7d3a  call     T0x2B00003B
0x7d3f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x7d44  stloc.1
0x7d45  br.s     loc_7DA8
0x7d47  ldloc.1
0x7d48  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x7d4d  stloc.s  4
0x7d4f  ldloc.0
0x7d50  ldloc.s  4
0x7d52  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.InstallSizePerDrive>::ContainsKey(var<u1>)
0x7d57  brfalse.s loc_7D83
0x7d59  ldloc.0
0x7d5a  ldloc.s  4
0x7d5c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.InstallSizePerDrive>::get_Item(void)
0x7d61  stloc.s  5
0x7d63  ldloca.s 5
0x7d65  ldarg.0
0x7d66  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64> Microsoft.VisualStudio.Setup.InstallSize::get_RequestedSizes()
0x7d6b  ldloc.s  4
0x7d6d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64>::get_Item(void)
0x7d72  call     instance void Microsoft.VisualStudio.Setup.InstallSizePerDrive::set_Requested(int64 value)
0x7d77  ldloc.0
0x7d78  ldloc.s  4
0x7d7a  ldloc.s  5
0x7d7c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.InstallSizePerDrive>::set_Item(var<u1>, !!T0)
0x7d81  br.s     loc_7DA8
0x7d83  ldloc.0
0x7d84  ldloc.s  4
0x7d86  ldloca.s 3
0x7d88  initobj  Microsoft.VisualStudio.Setup.InstallSizePerDrive
0x7d8e  ldloca.s 3
0x7d90  ldarg.0
0x7d91  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64> Microsoft.VisualStudio.Setup.InstallSize::get_RequestedSizes()
0x7d96  ldloc.s  4
0x7d98  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64>::get_Item(void)
0x7d9d  call     instance void Microsoft.VisualStudio.Setup.InstallSizePerDrive::set_Requested(int64 value)
0x7da2  ldloc.3
0x7da3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.InstallSizePerDrive>::Add(var<u1>, !!T0)
0x7da8  ldloc.1
0x7da9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7dae  brtrue.s loc_7D47
0x7db0  leave.s  loc_7DBC
0x7db2  ldloc.1
0x7db3  brfalse.s loc_7DBB
0x7db5  ldloc.1
0x7db6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7dbb  endfinally
0x7dbc  ldloc.0
0x7dbd  ret
```
