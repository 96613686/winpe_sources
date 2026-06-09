# CSpinLock::_Lock(void)

- ea: `0x1800051f0`
- end: `0x180005221`
- name: `?_Lock@CSpinLock@@AEAAXXZ`
- size: `49`
- prototype: `void __fastcall(CSpinLock *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004160`

## callees

- `0x1800051f0`
- `0x18002f06c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051f9`

## pseudocode

```c
void __fastcall CSpinLock::_Lock(CSpinLock *this)
{
  if ( (*(_DWORD *)this & 0xFFFFFFFC) == (GetCurrentThreadId() & 0xFFFFFFFC) )
    _InterlockedIncrement((volatile signed __int32 *)this);
  else
    CSpinLock::_LockSpin(this);
}

```

## disassembly

```asm
0x1800051f0  push    rbx
0x1800051f2  sub     rsp, 20h
0x1800051f6  mov     rbx, rcx
0x1800051f9  call    cs:__imp_GetCurrentThreadId
0x1800051ff  mov     edx, [rbx]
0x180005201  and     eax, 0FFFFFFFCh
0x180005204  and     edx, 0FFFFFFFCh
0x180005207  cmp     edx, eax
0x180005209  jnz     short loc_180005214
0x18000520b  lock inc dword ptr [rbx]
0x18000520e  add     rsp, 20h
0x180005212  pop     rbx
0x180005213  retn
0x180005214  mov     rcx, rbx; this
0x180005217  add     rsp, 20h
0x18000521b  pop     rbx
0x18000521c  jmp     ?_LockSpin@CSpinLock@@AEAAXXZ; CSpinLock::_LockSpin(void)
```
