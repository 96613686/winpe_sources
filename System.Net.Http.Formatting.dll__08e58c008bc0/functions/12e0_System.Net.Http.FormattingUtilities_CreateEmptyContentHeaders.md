# System.Net.Http.FormattingUtilities::CreateEmptyContentHeaders

- ea: `0x12e0`
- end: `0x130a`
- name: `System.Net.Http.FormattingUtilities::CreateEmptyContentHeaders`
- size: `42`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1ba0`
- `0x27d0`

## callees

- `0x12e0`

## pseudocode

```c

```

## disassembly

```asm
0x12e0  ldnull
0x12e1  stloc.0
0x12e2  ldnull
0x12e3  stloc.1
0x12e4  ldsfld   string [mscorlib]System.String::Empty
0x12e9  newobj   instance void [System.Net.Http]System.Net.Http.StringContent::.ctor(string)
0x12ee  stloc.0
0x12ef  ldloc.0
0x12f0  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x12f5  stloc.1
0x12f6  ldloc.1
0x12f7  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpHeaders::Clear()
0x12fc  leave.s  loc_1308
0x12fe  ldloc.0
0x12ff  brfalse.s loc_1307
0x1301  ldloc.0
0x1302  callvirt instance void [System.Net.Http]System.Net.Http.HttpContent::Dispose()
0x1307  endfinally
0x1308  ldloc.1
0x1309  ret
```
