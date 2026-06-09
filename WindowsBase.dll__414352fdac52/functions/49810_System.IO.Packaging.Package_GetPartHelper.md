# System.IO.Packaging.Package::GetPartHelper

- ea: `0x49810`
- end: `0x49867`
- name: `System.IO.Packaging.Package::GetPartHelper`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x48ca0`
- `0x48cc0`

## callees

- `0x49170`
- `0x492a0`
- `0x49470`
- `0x49660`
- `0x49810`
- `0x4aa10`

## string_xrefs

- `0x49825`: `partUri`

## pseudocode

```c

```

## disassembly

```asm
0x49810  ldarg.0
0x49811  call     instance void System.IO.Packaging.Package::ThrowIfObjectDisposed()
0x49816  ldarg.0
0x49817  call     instance void System.IO.Packaging.Package::ThrowIfWriteOnly()
0x4981c  ldarg.1
0x4981d  ldnull
0x4981e  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x49823  brfalse.s loc_49830
0x49825  ldstr    aParturi// "partUri"
0x4982a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4982f  throw
0x49830  ldarg.1
0x49831  call     class ValidatedPartUri System.IO.Packaging.PackUriHelper::ValidatePartUri(class [System]System.Uri partUri)
0x49836  stloc.0
0x49837  ldarg.0
0x49838  ldfld    class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart> System.IO.Packaging.Package::_partList
0x4983d  ldloc.0
0x4983e  callvirt instance bool class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart>::ContainsKey(var<u1>)
0x49843  brfalse.s loc_49852
0x49845  ldarg.0
0x49846  ldfld    class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart> System.IO.Packaging.Package::_partList
0x4984b  ldloc.0
0x4984c  callvirt instance var<u1> class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart>::get_Item(void)
0x49851  ret
0x49852  ldarg.0
0x49853  ldloc.0
0x49854  callvirt instance class System.IO.Packaging.PackagePart System.IO.Packaging.Package::GetPartCore(class [System]System.Uri partUri)
0x49859  stloc.1
0x4985a  ldloc.1
0x4985b  brfalse.s loc_49865
0x4985d  ldarg.0
0x4985e  ldloc.0
0x4985f  ldloc.1
0x49860  call     instance void System.IO.Packaging.Package::AddIfNoPrefixCollisionDetected(class ValidatedPartUri partUri, class System.IO.Packaging.PackagePart part)
0x49865  ldloc.1
0x49866  ret
```
