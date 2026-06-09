# ObjectMarkupInfo::EnsureNoDuplicateNames

- ea: `0x2b160`
- end: `0x2b213`
- name: `ObjectMarkupInfo::EnsureNoDuplicateNames`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x29160`

## callees

- `0x8810`
- `0x11f50`
- `0x29240`
- `0x2a0c0`
- `0x2a0f0`
- `0x2a100`
- `0x2b160`

## string_xrefs

- `0x2b180`: `ObjectReaderXamlNamedElementAlreadyRegistered`

## pseudocode

```c

```

## disassembly

```asm
0x2b160  ldarg.0
0x2b161  call     instance string ObjectMarkupInfo::get_Name()
0x2b166  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2b16b  brtrue.s loc_2B19F
0x2b16d  ldarg.1
0x2b16e  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class HashSet`1<string>>::Peek()
0x2b173  ldarg.0
0x2b174  call     instance string ObjectMarkupInfo::get_Name()
0x2b179  callvirt instance bool class HashSet`1<string>::Add(var<u1>)
0x2b17e  brtrue.s loc_2B19F
0x2b180  ldstr    aObjectreaderxa// "ObjectReaderXamlNamedElementAlreadyRegi"...
0x2b185  ldc.i4.1
0x2b186  newarr   [mscorlib]System.Object
0x2b18b  dup
0x2b18c  ldc.i4.0
0x2b18d  ldarg.0
0x2b18e  call     instance string ObjectMarkupInfo::get_Name()
0x2b193  stelem.ref
0x2b194  call     string System.Xaml.SR::Get(string id, object[] args)
0x2b199  newobj   instance void System.Xaml.XamlObjectReaderException::.ctor(string message)
0x2b19e  throw
0x2b19f  ldarg.0
0x2b1a0  call     instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> ObjectMarkupInfo::get_Properties()
0x2b1a5  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::GetEnumerator()
0x2b1aa  stloc.0
0x2b1ab  br.s     loc_2B1F9
0x2b1ad  ldloca.s 0
0x2b1af  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class MarkupInfo>::get_Current()
0x2b1b4  stloc.1
0x2b1b5  ldloc.1
0x2b1b6  castclass MemberMarkupInfo
0x2b1bb  stloc.2
0x2b1bc  ldloc.2
0x2b1bd  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> MemberMarkupInfo::get_Children()
0x2b1c2  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::GetEnumerator()
0x2b1c7  stloc.3
0x2b1c8  br.s     loc_2B1E0
0x2b1ca  ldloca.s 3
0x2b1cc  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class MarkupInfo>::get_Current()
0x2b1d1  stloc.s  4
0x2b1d3  ldloc.s  4
0x2b1d5  castclass ObjectOrValueMarkupInfo
0x2b1da  ldarg.1
0x2b1db  callvirt instance void ObjectOrValueMarkupInfo::EnsureNoDuplicateNames(class [System]System.Collections.Generic.Stack`1<class HashSet`1<string>> namesInCurrentScope)
0x2b1e0  ldloca.s 3
0x2b1e2  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class MarkupInfo>::MoveNext()
0x2b1e7  brtrue.s loc_2B1CA
0x2b1e9  leave.s  loc_2B1F9
0x2b1eb  ldloca.s 3
0x2b1ed  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class MarkupInfo>
0x2b1f3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b1f8  endfinally
0x2b1f9  ldloca.s 0
0x2b1fb  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class MarkupInfo>::MoveNext()
0x2b200  brtrue.s loc_2B1AD
0x2b202  leave.s  loc_2B212
0x2b204  ldloca.s 0
0x2b206  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class MarkupInfo>
0x2b20c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b211  endfinally
0x2b212  ret
```
