# TOKEN_ENTRY::DereferenceCacheData(void)

- ea: `0x180003d00`
- end: `0x180003d2c`
- name: `?DereferenceCacheData@TOKEN_ENTRY@@UEAAXXZ`
- size: `44`
- prototype: `void __fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003d00`
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
0x180003d00  sub     rsp, 28h
0x180003d04  or      eax, 0FFFFFFFFh
0x180003d07  lock xadd [rcx+0Ch], eax
0x180003d0c  cmp     eax, 1
0x180003d0f  jnz     short loc_180003D27
0x180003d11  test    rcx, rcx
0x180003d14  jz      short loc_180003D27
0x180003d16  mov     rax, [rcx]
0x180003d19  mov     edx, 1
0x180003d1e  mov     rax, [rax+50h]
0x180003d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d27  add     rsp, 28h
0x180003d2b  retn
```
