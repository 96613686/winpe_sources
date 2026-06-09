# Microsoft.Reporting.WebForms.ResourceReader::GetResource

- ea: `0x17b70`
- end: `0x17ba3`
- name: `Microsoft.Reporting.WebForms.ResourceReader::GetResource`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x17bf0`
- `0x17c20`

## callees

- `0x17b70`
- `0x17bb0`

## string_xrefs

- `0x17b90`: `Failed to read `

## pseudocode

```c

```

## disassembly

```asm
0x17b70  ldarg.0
0x17b71  call     class [mscorlib]System.IO.Stream Microsoft.Reporting.WebForms.ResourceReader::GetStream(string name)
0x17b76  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x17b7b  stloc.0
0x17b7c  ldloc.0
0x17b7d  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x17b82  stloc.1
0x17b83  leave.s  loc_17BA1
0x17b85  ldloc.0
0x17b86  brfalse.s loc_17B8E
0x17b88  ldloc.0
0x17b89  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17b8e  endfinally
0x17b8f  pop
0x17b90  ldstr    aFailedToRead// "Failed to read "
0x17b95  ldarg.0
0x17b96  call     string [mscorlib]System.String::Concat(string, string)
0x17b9b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x17ba0  throw
0x17ba1  ldloc.1
0x17ba2  ret
```
