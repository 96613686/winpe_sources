# Broker::ScopedWriteLock::ScopedWriteLock(_RTL_SRWLOCK &,bool)

- ea: `0x180013820`
- end: `0x180013854`
- name: `??0ScopedWriteLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z`
- size: `52`
- prototype: `Broker::ScopedWriteLock *__fastcall(Broker::ScopedWriteLock *this, struct _RTL_SRWLOCK *, char)`
- caller_count: `14`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006e00`
- `0x18000b3d0`
- `0x180016590`
- `0x1800186b8`
- `0x180018754`
- `0x1800198e0`
- `0x180019b60`
- `0x18001a9e8`
- `0x18001b378`
- `0x18001b80c`
- `0x18001bcdc`
- `0x18001be34`
- `0x18001c57c`
- `0x180020d84`

## callees

- `0x180013820`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180013838`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180013838`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001383e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001383e`

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
0x180013820  push    rbx
0x180013822  sub     rsp, 20h
0x180013826  mov     [rcx], rdx
0x180013829  mov     rbx, rcx
0x18001382c  mov     byte ptr [rcx+8], 0
0x180013830  test    r8b, r8b
0x180013833  jz      short loc_18001384B
0x180013835  mov     rcx, rdx
0x180013838  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001383e  call    cs:__imp_GetCurrentThreadId
0x180013844  mov     [rbx+0Ch], eax
0x180013847  mov     byte ptr [rbx+8], 1
0x18001384b  mov     rax, rbx
0x18001384e  add     rsp, 20h
0x180013852  pop     rbx
0x180013853  retn
```
