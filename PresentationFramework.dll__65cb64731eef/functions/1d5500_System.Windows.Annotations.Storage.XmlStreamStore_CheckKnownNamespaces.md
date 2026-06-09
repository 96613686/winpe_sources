# System.Windows.Annotations.Storage.XmlStreamStore::CheckKnownNamespaces

- ea: `0x1d5500`
- end: `0x1d5664`
- name: `System.Windows.Annotations.Storage.XmlStreamStore::CheckKnownNamespaces`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1d5400`

## callees

- `0x38c40`
- `0x1d5500`

## string_xrefs

- `0x1d5564`: `NullUri`
- `0x1d55f6`: `NullUri`
- `0x1d5583`: `DuplicatedUri`
- `0x1d5615`: `DuplicatedCompatibleUri`

## pseudocode

```c

```

## disassembly

```asm
0x1d5500  ldarg.1
0x1d5501  brtrue.s loc_1D5504
0x1d5503  ret
0x1d5504  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.Uri>::.ctor()
0x1d5509  stloc.0
0x1d550a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>> System.Windows.Annotations.Storage.XmlStreamStore::_predefinedNamespaces
0x1d550f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>>::get_Keys()
0x1d5514  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<class [System]System.Uri, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>>::GetEnumerator()
0x1d5519  stloc.1
0x1d551a  br.s     loc_1D552B
0x1d551c  ldloca.s 1
0x1d551e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<class [System]System.Uri, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>>::get_Current()
0x1d5523  stloc.2
0x1d5524  ldloc.0
0x1d5525  ldloc.2
0x1d5526  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [System]System.Uri>::Add(var<u1>)
0x1d552b  ldloca.s 1
0x1d552d  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<class [System]System.Uri, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>>::MoveNext()
0x1d5532  brtrue.s loc_1D551C
0x1d5534  leave.s  loc_1D5544
0x1d5536  ldloca.s 1
0x1d5538  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<class [System]System.Uri, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>>
0x1d553e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d5543  endfinally
0x1d5544  ldarg.1
0x1d5545  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<class [System]System.Uri, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>>::get_Keys()
0x1d554a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System]System.Uri>::GetEnumerator()
0x1d554f  stloc.3
0x1d5550  br.s     loc_1D55A0
0x1d5552  ldloc.3
0x1d5553  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System]System.Uri>::get_Current()
0x1d5558  stloc.s  4
0x1d555a  ldloc.s  4
0x1d555c  ldnull
0x1d555d  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x1d5562  brfalse.s loc_1D5579
0x1d5564  ldstr    aNulluri// "NullUri"
0x1d5569  call     string System.Windows.SR::Get(string id)
0x1d556e  ldstr    aKnownnamespace// "knownNamespaces"
0x1d5573  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1d5578  throw
0x1d5579  ldloc.0
0x1d557a  ldloc.s  4
0x1d557c  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<class [System]System.Uri>::Contains(var<u1>)
0x1d5581  brfalse.s loc_1D5598
0x1d5583  ldstr    aDuplicateduri// "DuplicatedUri"
0x1d5588  call     string System.Windows.SR::Get(string id)
0x1d558d  ldstr    aKnownnamespace// "knownNamespaces"
0x1d5592  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1d5597  throw
0x1d5598  ldloc.0
0x1d5599  ldloc.s  4
0x1d559b  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [System]System.Uri>::Add(var<u1>)
0x1d55a0  ldloc.3
0x1d55a1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1d55a6  brtrue.s loc_1D5552
0x1d55a8  leave.s  loc_1D55B4
0x1d55aa  ldloc.3
0x1d55ab  brfalse.s loc_1D55B3
0x1d55ad  ldloc.3
0x1d55ae  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d55b3  endfinally
0x1d55b4  ldarg.1
0x1d55b5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [System]System.Uri, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>>>::GetEnumerator()
0x1d55ba  stloc.s  5
0x1d55bc  br       loc_1D5649
0x1d55c1  ldloc.s  5
0x1d55c3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [System]System.Uri, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>>>::get_Current()
0x1d55c8  stloc.s  6
0x1d55ca  ldloca.s 6
0x1d55cc  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [System]System.Uri, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>>::get_Value()
0x1d55d1  brfalse.s loc_1D5649
0x1d55d3  ldloca.s 6
0x1d55d5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [System]System.Uri, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>>::get_Value()
0x1d55da  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System]System.Uri>::GetEnumerator()
0x1d55df  stloc.s  7
0x1d55e1  br.s     loc_1D5632
0x1d55e3  ldloc.s  7
0x1d55e5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System]System.Uri>::get_Current()
0x1d55ea  stloc.s  8
0x1d55ec  ldloc.s  8
0x1d55ee  ldnull
0x1d55ef  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x1d55f4  brfalse.s loc_1D560B
0x1d55f6  ldstr    aNulluri// "NullUri"
0x1d55fb  call     string System.Windows.SR::Get(string id)
0x1d5600  ldstr    aKnownnamespace// "knownNamespaces"
0x1d5605  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1d560a  throw
0x1d560b  ldloc.0
0x1d560c  ldloc.s  8
0x1d560e  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<class [System]System.Uri>::Contains(var<u1>)
0x1d5613  brfalse.s loc_1D562A
0x1d5615  ldstr    aDuplicatedcomp// "DuplicatedCompatibleUri"
0x1d561a  call     string System.Windows.SR::Get(string id)
0x1d561f  ldstr    aKnownnamespace// "knownNamespaces"
0x1d5624  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1d5629  throw
0x1d562a  ldloc.0
0x1d562b  ldloc.s  8
0x1d562d  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [System]System.Uri>::Add(var<u1>)
0x1d5632  ldloc.s  7
0x1d5634  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1d5639  brtrue.s loc_1D55E3
0x1d563b  leave.s  loc_1D5649
0x1d563d  ldloc.s  7
0x1d563f  brfalse.s loc_1D5648
0x1d5641  ldloc.s  7
0x1d5643  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d5648  endfinally
0x1d5649  ldloc.s  5
0x1d564b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1d5650  brtrue   loc_1D55C1
0x1d5655  leave.s  loc_1D5663
0x1d5657  ldloc.s  5
0x1d5659  brfalse.s loc_1D5662
0x1d565b  ldloc.s  5
0x1d565d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d5662  endfinally
0x1d5663  ret
```
