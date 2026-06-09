# System.Printing.PrintQueue::get_ShareName

- ea: `0xe910`
- end: `0xe92b`
- name: `System.Printing.PrintQueue::get_ShareName`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x110d0`
- `0x11340`

## string_xrefs

- `0xe916`: `ShareName`

## pseudocode

```c

```

## disassembly

```asm
0xe910  ldarg.0
0xe911  call     instance void System.Printing.PrintQueue::VerifyAccess()
0xe916  ldstr    aSharename// "ShareName"
0xe91b  stloc.0
0xe91c  ldarg.0
0xe91d  ldloc.0
0xe91e  dup
0xe91f  call     instance void System.Printing.PrintQueue::GetUnInitializedData(string upLevelPropertyName, string downlevelPropertyName)
0xe924  ldarg.0
0xe925  ldfld    string System.Printing.PrintQueue::shareName
0xe92a  ret
```
