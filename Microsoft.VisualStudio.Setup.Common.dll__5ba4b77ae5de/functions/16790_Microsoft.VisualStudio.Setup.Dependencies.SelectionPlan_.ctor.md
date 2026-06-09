# Microsoft.VisualStudio.Setup.Dependencies.SelectionPlan::.ctor

- ea: `0x16790`
- end: `0x167a9`
- name: `Microsoft.VisualStudio.Setup.Dependencies.SelectionPlan::.ctor`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14fb0`

## callees

- `0xc1a0`

## string_xrefs

- `0x16797`: `updatedSelections`

## pseudocode

```c

```

## disassembly

```asm
0x16790  ldarg.0
0x16791  call     instance void [mscorlib]System.Object::.ctor()
0x16796  ldarg.1
0x16797  ldstr    aUpdatedselecti// "updatedSelections"
0x1679c  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x167a1  ldarg.0
0x167a2  ldarg.1
0x167a3  stfld    class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<class Microsoft.VisualStudio.Setup.IPackageIdentity, class Microsoft.VisualStudio.Setup.ISelectionState> Microsoft.VisualStudio.Setup.Dependencies.SelectionPlan::<UpdatedSelections>k__BackingField
0x167a8  ret
```
