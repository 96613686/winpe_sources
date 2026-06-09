# CSmallSpinLock::TryWriteLock(void)

- ea: `0x180004ba0`
- end: `0x180004bca`
- name: `?TryWriteLock@CSmallSpinLock@@QEAA_NXZ`
- size: `42`
- prototype: `bool __fastcall(CSmallSpinLock *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004ba0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004baf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004baf`

## pseudocode

```c
bool __fastcall CSmallSpinLock::TryWriteLock(CSmallSpinLock *this)
{
  return !*(_DWORD *)this && _InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId(), 0) == 0;
}

```

## disassembly

```asm
0x180004ba0  push    rbx; public: bool CSmallSpinLock::TryReadLock(void)
0x180004ba2  sub     rsp, 20h
0x180004ba6  mov     eax, [rcx]
0x180004ba8  mov     rbx, rcx
0x180004bab  test    eax, eax
0x180004bad  jnz     short loc_180004BC2
0x180004baf  call    cs:__imp_GetCurrentThreadId
0x180004bb5  mov     edx, eax
0x180004bb7  xor     eax, eax
0x180004bb9  lock cmpxchg [rbx], edx
0x180004bbd  setz    al
0x180004bc0  jmp     short loc_180004BC4
0x180004bc2  xor     al, al
0x180004bc4  add     rsp, 20h
0x180004bc8  pop     rbx
0x180004bc9  retn
```
