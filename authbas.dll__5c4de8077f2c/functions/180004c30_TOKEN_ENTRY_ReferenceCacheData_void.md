# TOKEN_ENTRY::ReferenceCacheData(void)

- ea: `0x180004c30`
- end: `0x180004c35`
- name: `?ReferenceCacheData@TOKEN_ENTRY@@UEAAXXZ`
- size: `5`
- prototype: `void __fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall TOKEN_ENTRY::ReferenceCacheData(TOKEN_ENTRY *this)
{
  _InterlockedIncrement((volatile signed __int32 *)this + 3);
}

```

## disassembly

```asm
0x180004c30  lock inc dword ptr [rcx+0Ch]
0x180004c34  retn
```
