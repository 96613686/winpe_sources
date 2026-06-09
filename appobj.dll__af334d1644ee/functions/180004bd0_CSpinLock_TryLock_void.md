# CSpinLock::_TryLock(void)

- ea: `0x180004bd0`
- end: `0x180004c00`
- name: `?_TryLock@CSpinLock@@AEAA_NXZ`
- size: `48`
- prototype: `bool __fastcall(CSpinLock *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004bd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004bdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004bdf`

## pseudocode

```c
bool __fastcall CSpinLock::_TryLock(CSpinLock *this)
{
  return !*(_DWORD *)this
      && _InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId() & 0xFFFFFFFC | 1, 0) == 0;
}

```

## disassembly

```asm
0x180004bd0  push    rbx; public: bool CSpinLock::TryReadLock(void)
0x180004bd2  sub     rsp, 20h
0x180004bd6  mov     eax, [rcx]
0x180004bd8  mov     rbx, rcx
0x180004bdb  test    eax, eax
0x180004bdd  jnz     short loc_180004BF8
0x180004bdf  call    cs:__imp_GetCurrentThreadId
0x180004be5  mov     edx, eax
0x180004be7  and     edx, 0FFFFFFFDh
0x180004bea  or      edx, 1
0x180004bed  xor     eax, eax
0x180004bef  lock cmpxchg [rbx], edx
0x180004bf3  setz    al
0x180004bf6  jmp     short loc_180004BFA
0x180004bf8  xor     al, al
0x180004bfa  add     rsp, 20h
0x180004bfe  pop     rbx
0x180004bff  retn
```
