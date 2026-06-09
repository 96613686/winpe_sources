# Broker::ScopedWriteLock::Acquire(void)

- ea: `0x180012a50`
- end: `0x180012a75`
- name: `?Acquire@ScopedWriteLock@Broker@@QEAAXXZ`
- size: `37`
- prototype: `void __fastcall(Broker::ScopedWriteLock *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b378`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180012a5c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180012a5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012a62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012a62`

## pseudocode

```c
void __fastcall Broker::ScopedWriteLock::Acquire(Broker::ScopedWriteLock *this)
{
  RtlAcquireSRWLockExclusive(*(_QWORD *)this);
  *((_DWORD *)this + 3) = GetCurrentThreadId();
  *((_BYTE *)this + 8) = 1;
}

```

## disassembly

```asm
0x180012a50  push    rbx
0x180012a52  sub     rsp, 20h
0x180012a56  mov     rbx, rcx
0x180012a59  mov     rcx, [rcx]
0x180012a5c  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180012a62  call    cs:__imp_GetCurrentThreadId
0x180012a68  mov     [rbx+0Ch], eax
0x180012a6b  mov     byte ptr [rbx+8], 1
0x180012a6f  add     rsp, 20h
0x180012a73  pop     rbx
0x180012a74  retn
```
