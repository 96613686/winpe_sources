# CSubCommand::EnumSubCommands(IEnumExplorerCommand * *)

- ea: `0x180009480`
- end: `0x18000948d`
- name: `?EnumSubCommands@CSubCommand@@UEAAJPEAPEAUIEnumExplorerCommand@@@Z`
- size: `13`
- prototype: `__int64 __fastcall(CSubCommand *__hidden this, struct IEnumExplorerCommand **)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CSubCommand::EnumSubCommands(CSubCommand *this, struct IEnumExplorerCommand **a2)
{
  *a2 = 0;
  return 2147500033LL;
}

```

## disassembly

```asm
0x180009480  mov     qword ptr [rdx], 0
0x180009487  mov     eax, 80004001h
0x18000948c  retn
```
