# RtlSrwLock::AcquireExclusive(void)

- ea: `0x180028b20`
- end: `0x180028b3e`
- name: `?AcquireExclusive@RtlSrwLock@@QEAAXXZ`
- size: `30`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180008b70`
- `0x18000fb84`
- `0x18000fcb4`
- `0x18000fd7c`
- `0x18000ffd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028b29`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028b29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028b2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028b2f`

## pseudocode

```c
void __fastcall RtlSrwLock::AcquireExclusive(RTL_SRWLOCK *this)
{
  AcquireSRWLockExclusive(this);
  LODWORD(this[1].Ptr) = GetCurrentThreadId();
}

```

## disassembly

```asm
0x180028b20  push    rbx
0x180028b22  sub     rsp, 20h
0x180028b26  mov     rbx, rcx
0x180028b29  call    cs:__imp_AcquireSRWLockExclusive
0x180028b2f  call    cs:__imp_GetCurrentThreadId
0x180028b35  mov     [rbx+8], eax
0x180028b38  add     rsp, 20h
0x180028b3c  pop     rbx
0x180028b3d  retn
```
