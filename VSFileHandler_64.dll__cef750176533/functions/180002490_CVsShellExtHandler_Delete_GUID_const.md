# CVsShellExtHandler::Delete(_GUID const &)

- ea: `0x180002490`
- end: `0x180002496`
- name: `?Delete@CVsShellExtHandler@@UEAAJAEBU_GUID@@@Z`
- size: `6`
- prototype: `__int64 __fastcall(CVsShellExtHandler *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, loader_planting`

## pseudocode

```c
__int64 __fastcall CVsShellExtHandler::Delete(CVsShellExtHandler *this, const struct _GUID *a2)
{
  return 2147680261LL;
}

```

## disassembly

```asm
0x180002490  mov     eax, 80030005h
0x180002495  retn
```
