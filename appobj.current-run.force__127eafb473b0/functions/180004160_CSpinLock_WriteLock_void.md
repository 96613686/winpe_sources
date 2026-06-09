# CSpinLock::WriteLock(void)

- ea: `0x180004160`
- end: `0x180004193`
- name: `?WriteLock@CSpinLock@@QEAAXXZ`
- size: `51`
- prototype: `void __fastcall(CSpinLock *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800038b0`
- `0x180003990`
- `0x180003dc0`
- `0x180003f00`
- `0x180003f60`
- `0x180004210`
- `0x1800043c0`
- `0x180004430`
- `0x1800044a0`

## callees

- `0x180004160`
- `0x1800051f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000416f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000416f`

## pseudocode

```c
void __fastcall CSpinLock::WriteLock(CSpinLock *this)
{
  if ( *(_DWORD *)this
    || _InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId() & 0xFFFFFFFC | 1, 0) )
  {
    CSpinLock::_Lock(this);
  }
}

```

## disassembly

```asm
0x180004160  push    rbx; public: void CSpinLock::ReadLock(void)
0x180004162  sub     rsp, 20h
0x180004166  mov     eax, [rcx]
0x180004168  mov     rbx, rcx
0x18000416b  test    eax, eax
0x18000416d  jnz     short loc_180004185
0x18000416f  call    cs:__imp_GetCurrentThreadId
0x180004175  mov     edx, eax
0x180004177  and     edx, 0FFFFFFFDh
0x18000417a  or      edx, 1
0x18000417d  xor     eax, eax
0x18000417f  lock cmpxchg [rbx], edx
0x180004183  jz      short loc_18000418D
0x180004185  mov     rcx, rbx; this
0x180004188  call    ?_Lock@CSpinLock@@AEAAXXZ; CSpinLock::_Lock(void)
0x18000418d  add     rsp, 20h
0x180004191  pop     rbx
0x180004192  retn
```
