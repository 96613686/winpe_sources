# System.Net.Http.Formatting.FormUrlEncodedJson::CanBecomeArray

- ea: `0x6790`
- end: `0x6888`
- name: `System.Net.Http.Formatting.FormUrlEncodedJson::CanBecomeArray`
- size: `248`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6720`

## callees

- `0x6790`
- `0xd550`
- `0xd570`

## pseudocode

```c

```

## disassembly

```asm
0x6790  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class ArrayCandidate>::.ctor()
0x6795  stloc.0
0x6796  ldarg.1
0x6797  ldnull
0x6798  stind.ref
0x6799  ldc.i4.1
0x679a  stloc.1
0x679b  ldarg.0
0x679c  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x67a1  stloc.2
0x67a2  br.s     loc_67EC
0x67a4  ldloca.s 2
0x67a6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x67ab  stloc.3
0x67ac  ldloc.3
0x67ad  ldc.i4.0
0x67ae  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x67b3  ldloca.s 4
0x67b5  call     bool [mscorlib]System.Int32::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int32&)
0x67ba  brtrue.s loc_67C0
0x67bc  ldc.i4.0
0x67bd  stloc.1
0x67be  leave.s  loc_6805
0x67c0  ldloca.s 4
0x67c2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x67c7  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x67cc  stloc.s  5
0x67ce  ldloc.s  5
0x67d0  ldloc.3
0x67d1  ldc.i4.4
0x67d2  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x67d7  brtrue.s loc_67DD
0x67d9  ldc.i4.0
0x67da  stloc.1
0x67db  leave.s  loc_6805
0x67dd  ldloc.0
0x67de  ldloc.s  4
0x67e0  ldloc.s  5
0x67e2  newobj   instance void ArrayCandidate::.ctor(int32 key, string value)
0x67e7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class ArrayCandidate>::Add(var<u1>)
0x67ec  ldloca.s 2
0x67ee  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x67f3  brtrue.s loc_67A4
0x67f5  leave.s  loc_6805
0x67f7  ldloca.s 2
0x67f9  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x67ff  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6804  endfinally
0x6805  ldloc.1
0x6806  brfalse.s loc_6857
0x6808  ldloc.0
0x6809  ldsfld   class [mscorlib]System.Comparison`1<class ArrayCandidate> <>c::<>9__16_0
0x680e  dup
0x680f  brtrue.s loc_6828
0x6811  pop
0x6812  ldsfld   class <>c <>c::<>9
0x6817  ldftn    instance int32 <>c::<CanBecomeArray>b__16_0(class ArrayCandidate x, class ArrayCandidate y)
0x681d  newobj   instance void class [mscorlib]System.Comparison`1<class ArrayCandidate>::.ctor(object, native int)
0x6822  dup
0x6823  stsfld   class [mscorlib]System.Comparison`1<class ArrayCandidate> <>c::<>9__16_0
0x6828  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class ArrayCandidate>::Sort(class [mscorlib]System.Comparison`1<var<u1>>)
0x682d  ldc.i4.0
0x682e  stloc.s  6
0x6830  br.s     loc_684D
0x6832  ldloc.0
0x6833  ldloc.s  6
0x6835  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class ArrayCandidate>::get_Item(!!T0)
0x683a  callvirt instance int32 ArrayCandidate::get_Key()
0x683f  ldloc.s  6
0x6841  beq.s    loc_6847
0x6843  ldc.i4.0
0x6844  stloc.1
0x6845  br.s     loc_6857
0x6847  ldloc.s  6
0x6849  ldc.i4.1
0x684a  add
0x684b  stloc.s  6
0x684d  ldloc.s  6
0x684f  ldloc.0
0x6850  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class ArrayCandidate>::get_Count()
0x6855  blt.s    loc_6832
0x6857  ldloc.1
0x6858  brfalse.s loc_6886
0x685a  ldarg.1
0x685b  ldloc.0
0x685c  ldsfld   class [mscorlib]System.Func`2<class ArrayCandidate, string> <>c::<>9__16_1
0x6861  dup
0x6862  brtrue.s loc_687B
0x6864  pop
0x6865  ldsfld   class <>c <>c::<>9
0x686a  ldftn    instance string <>c::<CanBecomeArray>b__16_1(class ArrayCandidate x)
0x6870  newobj   instance void class [mscorlib]System.Func`2<class ArrayCandidate, string>::.ctor(object, native int)
0x6875  dup
0x6876  stsfld   class [mscorlib]System.Func`2<class ArrayCandidate, string> <>c::<>9__16_1
0x687b  call     T0x2B000046
0x6880  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x6885  stind.ref
0x6886  ldloc.1
0x6887  ret
```
