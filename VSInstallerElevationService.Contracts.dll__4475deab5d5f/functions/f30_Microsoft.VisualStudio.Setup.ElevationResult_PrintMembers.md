# Microsoft.VisualStudio.Setup.ElevationResult::PrintMembers

- ea: `0xf30`
- end: `0xf77`
- name: `Microsoft.VisualStudio.Setup.ElevationResult::PrintMembers`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xef0`

## callees

- `0xeb0`
- `0xed0`

## pseudocode

```c

```

## disassembly

```asm
0xf30  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::EnsureSufficientExecutionStack()
0xf35  ldarg.1
0xf36  ldstr    aIssuccess// "IsSuccess = "
0xf3b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf40  pop
0xf41  ldarg.1
0xf42  ldarg.0
0xf43  call     instance bool Microsoft.VisualStudio.Setup.ElevationResult::get_IsSuccess()
0xf48  stloc.0
0xf49  ldloca.s 0
0xf4b  constrained. [mscorlib]System.Boolean
0xf51  callvirt instance string [mscorlib]System.Object::ToString()
0xf56  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf5b  pop
0xf5c  ldarg.1
0xf5d  ldstr    aPipename// ", PipeName = "
0xf62  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf67  pop
0xf68  ldarg.1
0xf69  ldarg.0
0xf6a  call     instance string Microsoft.VisualStudio.Setup.ElevationResult::get_PipeName()
0xf6f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0xf74  pop
0xf75  ldc.i4.1
0xf76  ret
```
