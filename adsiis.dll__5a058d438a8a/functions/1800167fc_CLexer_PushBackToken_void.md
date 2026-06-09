# CLexer::PushBackToken(void)

- ea: `0x1800167fc`
- end: `0x180016811`
- name: `?PushBackToken@CLexer@@QEAAJXZ`
- size: `21`
- prototype: `__int64 __fastcall(CLexer *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800160d0`
- `0x1800164f8`
- `0x180016630`

## callees

- `0x1800167fc`

## pseudocode

```c
__int64 __fastcall CLexer::PushBackToken(CLexer *this)
{
  if ( *((_DWORD *)this + 5) != 4 )
    *(_QWORD *)this += -2LL * *((unsigned int *)this + 4);
  return 0;
}

```

## disassembly

```asm
0x1800167fc  cmp     dword ptr [rcx+14h], 4
0x180016800  jz      short loc_18001680E
0x180016802  mov     eax, [rcx+10h]
0x180016805  neg     rax
0x180016808  add     rax, rax
0x18001680b  add     [rcx], rax
0x18001680e  xor     eax, eax
0x180016810  retn
```
