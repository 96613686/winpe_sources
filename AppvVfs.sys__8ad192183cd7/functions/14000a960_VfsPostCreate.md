# VfsPostCreate

- ea: `0x14000a960`
- end: `0x14000a981`
- name: `VfsPostCreate`
- size: `33`
- prototype: `__int64 __fastcall(struct _FLT_CALLBACK_DATA *, __int64, char *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140003f24`
- `0x140005308`
- `0x14000a960`

## pseudocode

```c
__int64 __fastcall VfsPostCreate(struct _FLT_CALLBACK_DATA *a1, __int64 a2, char *a3, char a4)
{
  if ( (a4 & 1) != 0 )
    VfsDeleteCreateCompletionContext(a3);
  else
    VfsCreateCompletion(a1, a2, a3);
  return 0;
}

```

## disassembly

```asm
0x14000a960  sub     rsp, 28h
0x14000a964  test    r9b, 1
0x14000a968  jz      short loc_14000A974
0x14000a96a  mov     rcx, r8; Entry
0x14000a96d  call    VfsDeleteCreateCompletionContext
0x14000a972  jmp     short loc_14000A979
0x14000a974  call    VfsCreateCompletion
0x14000a979  xor     eax, eax
0x14000a97b  add     rsp, 28h
0x14000a97f  retn
```
