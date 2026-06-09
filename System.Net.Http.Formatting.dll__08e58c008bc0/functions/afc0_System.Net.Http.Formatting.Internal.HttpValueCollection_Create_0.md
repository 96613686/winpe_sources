# System.Net.Http.Formatting.Internal.HttpValueCollection::Create_0

- ea: `0xafc0`
- end: `0xb007`
- name: `System.Net.Http.Formatting.Internal.HttpValueCollection::Create_0`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x5fd0`

## callees

- `0xafa0`
- `0xafc0`

## pseudocode

```c

```

## disassembly

```asm
0xafc0  newobj   instance void System.Net.Http.Formatting.Internal.HttpValueCollection::.ctor()
0xafc5  stloc.0
0xafc6  ldarg.0
0xafc7  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::GetEnumerator()
0xafcc  stloc.1
0xafcd  br.s     loc_AFEA
0xafcf  ldloc.1
0xafd0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Current()
0xafd5  stloc.2
0xafd6  ldloc.0
0xafd7  ldloca.s 2
0xafd9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0xafde  ldloca.s 2
0xafe0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0xafe5  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0xafea  ldloc.1
0xafeb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xaff0  brtrue.s loc_AFCF
0xaff2  leave.s  loc_AFFE
0xaff4  ldloc.1
0xaff5  brfalse.s loc_AFFD
0xaff7  ldloc.1
0xaff8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xaffd  endfinally
0xaffe  ldloc.0
0xafff  ldc.i4.0
0xb000  callvirt instance void [System]System.Collections.Specialized.NameObjectCollectionBase::set_IsReadOnly(bool)
0xb005  ldloc.0
0xb006  ret
```
