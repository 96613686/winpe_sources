# CSmallSpinLock::WriteLock(void)

- ea: `0x180004120`
- end: `0x18000414d`
- name: `?WriteLock@CSmallSpinLock@@QEAAXXZ`
- size: `45`
- prototype: `void __fastcall(CSmallSpinLock *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004120`
- `0x18002ef64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000412f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000412f`

## pseudocode

```c
void __fastcall CSmallSpinLock::WriteLock(CSmallSpinLock *this)
{
  if ( *(_DWORD *)this || _InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId(), 0) )
    CSmallSpinLock::_LockSpin(this);
}

```

## disassembly

```asm
0x180004120  push    rbx; public: void CSmallSpinLock::ReadLock(void)
0x180004122  sub     rsp, 20h
0x180004126  mov     eax, [rcx]
0x180004128  mov     rbx, rcx
0x18000412b  test    eax, eax
0x18000412d  jnz     short loc_18000413F
0x18000412f  call    cs:__imp_GetCurrentThreadId
0x180004135  mov     edx, eax
0x180004137  xor     eax, eax
0x180004139  lock cmpxchg [rbx], edx
0x18000413d  jz      short loc_180004147
0x18000413f  mov     rcx, rbx; this
0x180004142  call    ?_LockSpin@CSmallSpinLock@@AEAAXXZ; CSmallSpinLock::_LockSpin(void)
0x180004147  add     rsp, 20h
0x18000414b  pop     rbx
0x18000414c  retn
```
