# TOKEN_ENTRY::DereferenceCacheData(void)

- ea: `0x1800048b0`
- end: `0x1800048dc`
- name: `?DereferenceCacheData@TOKEN_ENTRY@@UEAAXXZ`
- size: `44`
- prototype: `void __fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800048b0`
- `0x180006010`

## pseudocode

```c
void __fastcall TOKEN_ENTRY::DereferenceCacheData(TOKEN_ENTRY *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 3, 0xFFFFFFFF) == 1 )
  {
    if ( this )
      (*(void (__fastcall **)(TOKEN_ENTRY *, __int64))(*(_QWORD *)this + 80LL))(this, 1);
  }
}

```

## disassembly

```asm
0x1800048b0  sub     rsp, 28h
0x1800048b4  or      eax, 0FFFFFFFFh
0x1800048b7  lock xadd [rcx+0Ch], eax
0x1800048bc  cmp     eax, 1
0x1800048bf  jnz     short loc_1800048D7
0x1800048c1  test    rcx, rcx
0x1800048c4  jz      short loc_1800048D7
0x1800048c6  mov     rax, [rcx]
0x1800048c9  mov     edx, 1
0x1800048ce  mov     rax, [rax+50h]
0x1800048d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048d7  add     rsp, 28h
0x1800048db  retn
```
