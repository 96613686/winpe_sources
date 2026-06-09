# Microsoft.VisualStudio.Setup.PackageIdentityComparer::.ctor

- ea: `0xa4a0`
- end: `0xa51b`
- name: `Microsoft.VisualStudio.Setup.PackageIdentityComparer::.ctor`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0xa920`

## callees

- `0xa4a0`

## string_xrefs

- `0xa50b`: `The comparison type is not supported`
- `0xa510`: `comparisonType`

## pseudocode

```c

```

## disassembly

```asm
0xa4a0  ldarg.0
0xa4a1  call     instance void [mscorlib]System.Object::.ctor()
0xa4a6  ldarg.0
0xa4a7  ldarg.1
0xa4a8  stfld    bool Microsoft.VisualStudio.Setup.PackageIdentityComparer::excludeVersion
0xa4ad  ldarg.0
0xa4ae  ldarg.2
0xa4af  stfld    valuetype [mscorlib]System.StringComparison Microsoft.VisualStudio.Setup.PackageIdentityComparer::comparisonType
0xa4b4  ldarg.0
0xa4b5  ldarg.3
0xa4b6  stfld    bool Microsoft.VisualStudio.Setup.PackageIdentityComparer::excludeBranch
0xa4bb  ldarg.2
0xa4bc  switch   loc_A4DB, loc_A4E7, loc_A50B, loc_A50B, loc_A4F3, loc_A4FF
0xa4d9  br.s     loc_A50B
0xa4db  ldarg.0
0xa4dc  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_CurrentCulture()
0xa4e1  stfld    class [mscorlib]System.StringComparer Microsoft.VisualStudio.Setup.PackageIdentityComparer::comparer
0xa4e6  ret
0xa4e7  ldarg.0
0xa4e8  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_CurrentCultureIgnoreCase()
0xa4ed  stfld    class [mscorlib]System.StringComparer Microsoft.VisualStudio.Setup.PackageIdentityComparer::comparer
0xa4f2  ret
0xa4f3  ldarg.0
0xa4f4  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_Ordinal()
0xa4f9  stfld    class [mscorlib]System.StringComparer Microsoft.VisualStudio.Setup.PackageIdentityComparer::comparer
0xa4fe  ret
0xa4ff  ldarg.0
0xa500  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xa505  stfld    class [mscorlib]System.StringComparer Microsoft.VisualStudio.Setup.PackageIdentityComparer::comparer
0xa50a  ret
0xa50b  ldstr    aTheComparisonT// "The comparison type is not supported"
0xa510  ldstr    aComparisontype// "comparisonType"
0xa515  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xa51a  throw
```
