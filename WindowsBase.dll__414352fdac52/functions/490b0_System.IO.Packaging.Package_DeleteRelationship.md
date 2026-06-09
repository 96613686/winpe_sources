# System.IO.Packaging.Package::DeleteRelationship

- ea: `0x490b0`
- end: `0x490ee`
- name: `System.IO.Packaging.Package::DeleteRelationship`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x4ca80`

## callees

- `0x210b0`
- `0x211e0`
- `0x490b0`
- `0x49220`
- `0x49280`
- `0x49660`
- `0x49680`

## string_xrefs

- `0x490bd`: `DeleteRelationship`

## pseudocode

```c

```

## disassembly

```asm
0x490b0  ldarg.0
0x490b1  call     instance void System.IO.Packaging.Package::ThrowIfObjectDisposed()
0x490b6  ldarg.0
0x490b7  call     instance void System.IO.Packaging.Package::ThrowIfReadOnly()
0x490bc  ldarg.0
0x490bd  ldstr    aDeleterelation// "DeleteRelationship"
0x490c2  call     instance void System.IO.Packaging.Package::ThrowIfInStreamingCreation(string methodName)
0x490c7  ldarg.1
0x490c8  brtrue.s loc_490D5
0x490ca  ldstr    aId_1// "id"
0x490cf  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x490d4  throw
0x490d5  ldarg.1
0x490d6  call     void MS.Internal.IO.Packaging.InternalRelationshipCollection::ThrowIfInvalidXsdId(string id)
0x490db  ldarg.0
0x490dc  call     instance void System.IO.Packaging.Package::EnsureRelationships()
0x490e1  ldarg.0
0x490e2  ldfld    class MS.Internal.IO.Packaging.InternalRelationshipCollection System.IO.Packaging.Package::_relationships
0x490e7  ldarg.1
0x490e8  callvirt instance void MS.Internal.IO.Packaging.InternalRelationshipCollection::Delete(string id)
0x490ed  ret
```
