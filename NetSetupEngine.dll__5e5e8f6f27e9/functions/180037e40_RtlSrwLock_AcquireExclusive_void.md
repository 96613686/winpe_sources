# RtlSrwLock::AcquireExclusive(void)

- ea: `0x180037e40`
- end: `0x180037e5e`
- name: `?AcquireExclusive@RtlSrwLock@@QEAAXXZ`
- size: `30`
- prototype: `void __fastcall(RtlSrwLock *__hidden this)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x1800377b8`
- `0x180037ba0`
- `0x180037c74`
- `0x180037d30`
- `0x1800391f4`
- `0x18004d764`
- `0x18004de5c`
- `0x18004f540`
- `0x1800530c8`
- `0x180053168`
- `0x1800587b4`
- `0x18005a654`
- `0x18005ca14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180037e49`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180037e49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037e4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037e4f`

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
0x180037e40  push    rbx
0x180037e42  sub     rsp, 20h
0x180037e46  mov     rbx, rcx
0x180037e49  call    cs:__imp_AcquireSRWLockExclusive
0x180037e4f  call    cs:__imp_GetCurrentThreadId
0x180037e55  mov     [rbx+8], eax
0x180037e58  add     rsp, 20h
0x180037e5c  pop     rbx
0x180037e5d  retn
```
