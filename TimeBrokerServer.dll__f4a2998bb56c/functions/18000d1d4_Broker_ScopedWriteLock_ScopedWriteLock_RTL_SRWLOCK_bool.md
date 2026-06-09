# Broker::ScopedWriteLock::ScopedWriteLock(_RTL_SRWLOCK &,bool)

- ea: `0x18000d1d4`
- end: `0x18000d203`
- name: `??0ScopedWriteLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z`
- size: `47`
- prototype: `Broker::ScopedWriteLock *__fastcall(Broker::ScopedWriteLock *this, struct _RTL_SRWLOCK *)`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010350`
- `0x180017e64`
- `0x18001807c`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000d1e7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000d1e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d1ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d1ed`

## pseudocode

```c
Broker::ScopedWriteLock *__fastcall Broker::ScopedWriteLock::ScopedWriteLock(
        Broker::ScopedWriteLock *this,
        struct _RTL_SRWLOCK *a2)
{
  Broker::ScopedWriteLock *result; // rax

  *(_QWORD *)this = a2;
  *((_BYTE *)this + 8) = 0;
  RtlAcquireSRWLockExclusive(a2);
  *((_DWORD *)this + 3) = GetCurrentThreadId();
  result = this;
  *((_BYTE *)this + 8) = 1;
  return result;
}

```

## disassembly

```asm
0x18000d1d4  push    rbx
0x18000d1d6  sub     rsp, 20h
0x18000d1da  mov     rbx, rcx
0x18000d1dd  mov     [rcx], rdx
0x18000d1e0  mov     byte ptr [rcx+8], 0
0x18000d1e4  mov     rcx, rdx
0x18000d1e7  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000d1ed  call    cs:__imp_GetCurrentThreadId
0x18000d1f3  mov     [rbx+0Ch], eax
0x18000d1f6  mov     rax, rbx
0x18000d1f9  mov     byte ptr [rbx+8], 1
0x18000d1fd  add     rsp, 20h
0x18000d201  pop     rbx
0x18000d202  retn
```
