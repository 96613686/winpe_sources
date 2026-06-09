# System.IO.Packaging.PackagePart::DeleteRelationship

- ea: `0x49b80`
- end: `0x49bc8`
- name: `System.IO.Packaging.PackagePart::DeleteRelationship`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x4cad0`

## callees

- `0x210b0`
- `0x211e0`
- `0x49220`
- `0x49280`
- `0x49b80`
- `0x49e50`
- `0x49ee0`

## string_xrefs

- `0x49b97`: `DeleteRelationship`

## pseudocode

```c

```

## disassembly

```asm
0x49b80  ldarg.0
0x49b81  call     instance void System.IO.Packaging.PackagePart::CheckInvalidState()
0x49b86  ldarg.0
0x49b87  ldfld    class System.IO.Packaging.Package System.IO.Packaging.PackagePart::_container
0x49b8c  callvirt instance void System.IO.Packaging.Package::ThrowIfReadOnly()
0x49b91  ldarg.0
0x49b92  ldfld    class System.IO.Packaging.Package System.IO.Packaging.PackagePart::_container
0x49b97  ldstr    aDeleterelation// "DeleteRelationship"
0x49b9c  callvirt instance void System.IO.Packaging.Package::ThrowIfInStreamingCreation(string methodName)
0x49ba1  ldarg.1
0x49ba2  brtrue.s loc_49BAF
0x49ba4  ldstr    aId_1// "id"
0x49ba9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x49bae  throw
0x49baf  ldarg.1
0x49bb0  call     void MS.Internal.IO.Packaging.InternalRelationshipCollection::ThrowIfInvalidXsdId(string id)
0x49bb5  ldarg.0
0x49bb6  call     instance void System.IO.Packaging.PackagePart::EnsureRelationships()
0x49bbb  ldarg.0
0x49bbc  ldfld    class MS.Internal.IO.Packaging.InternalRelationshipCollection System.IO.Packaging.PackagePart::_relationships
0x49bc1  ldarg.1
0x49bc2  callvirt instance void MS.Internal.IO.Packaging.InternalRelationshipCollection::Delete(string id)
0x49bc7  ret
```
