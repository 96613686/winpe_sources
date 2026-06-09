# System.Printing.PrintQueue::get_Comment

- ea: `0xe9f0`
- end: `0xea0b`
- name: `System.Printing.PrintQueue::get_Comment`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x110d0`
- `0x11340`

## string_xrefs

- `0xe9f6`: `Comment`

## pseudocode

```c

```

## disassembly

```asm
0xe9f0  ldarg.0
0xe9f1  call     instance void System.Printing.PrintQueue::VerifyAccess()
0xe9f6  ldstr    aComment// "Comment"
0xe9fb  stloc.0
0xe9fc  ldarg.0
0xe9fd  ldloc.0
0xe9fe  dup
0xe9ff  call     instance void System.Printing.PrintQueue::GetUnInitializedData(string upLevelPropertyName, string downlevelPropertyName)
0xea04  ldarg.0
0xea05  ldfld    string System.Printing.PrintQueue::comment
0xea0a  ret
```
