# Broker::ScopedWriteLock::ScopedWriteLock(_RTL_SRWLOCK &,bool)

- ea: `0x18000eb40`
- end: `0x18000eb74`
- name: `??0ScopedWriteLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z`
- size: `52`
- prototype: `__int64 __fastcall(Broker::ScopedWriteLock *__hidden this, struct _RTL_SRWLOCK *, bool)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b3cc`
- `0x18000c970`
- `0x1800119f4`
- `0x1800153e4`
- `0x180017578`
- `0x18001764c`
- `0x180017a9c`
- `0x180018004`
- `0x180019010`

## callees

- `0x18000eb40`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000eb58`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000eb58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eb5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eb5e`

## pseudocode

```c
Broker::ScopedWriteLock *__fastcall Broker::ScopedWriteLock::ScopedWriteLock(
        Broker::ScopedWriteLock *this,
        struct _RTL_SRWLOCK *a2,
        char a3)
{
  *(_QWORD *)this = a2;
  *((_BYTE *)this + 8) = 0;
  if ( a3 )
  {
    RtlAcquireSRWLockExclusive(a2);
    *((_DWORD *)this + 3) = GetCurrentThreadId();
    *((_BYTE *)this + 8) = 1;
  }
  return this;
}

```

## disassembly

```asm
0x18000eb40  push    rbx
0x18000eb42  sub     rsp, 20h
0x18000eb46  mov     [rcx], rdx
0x18000eb49  mov     rbx, rcx
0x18000eb4c  mov     byte ptr [rcx+8], 0
0x18000eb50  test    r8b, r8b
0x18000eb53  jz      short loc_18000EB6B
0x18000eb55  mov     rcx, rdx
0x18000eb58  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000eb5e  call    cs:__imp_GetCurrentThreadId
0x18000eb64  mov     [rbx+0Ch], eax
0x18000eb67  mov     byte ptr [rbx+8], 1
0x18000eb6b  mov     rax, rbx
0x18000eb6e  add     rsp, 20h
0x18000eb72  pop     rbx
0x18000eb73  retn
```
