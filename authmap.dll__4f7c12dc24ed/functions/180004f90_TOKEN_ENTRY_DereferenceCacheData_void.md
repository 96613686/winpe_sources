# TOKEN_ENTRY::DereferenceCacheData(void)

- ea: `0x180004f90`
- end: `0x180004fbc`
- name: `?DereferenceCacheData@TOKEN_ENTRY@@UEAAXXZ`
- size: `44`
- prototype: `void __fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004f90`
- `0x180008010`

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
0x180004f90  sub     rsp, 28h
0x180004f94  or      eax, 0FFFFFFFFh
0x180004f97  lock xadd [rcx+0Ch], eax
0x180004f9c  cmp     eax, 1
0x180004f9f  jnz     short loc_180004FB7
0x180004fa1  test    rcx, rcx
0x180004fa4  jz      short loc_180004FB7
0x180004fa6  mov     rax, [rcx]
0x180004fa9  mov     edx, 1
0x180004fae  mov     rax, [rax+50h]
0x180004fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fb7  add     rsp, 28h
0x180004fbb  retn
```
