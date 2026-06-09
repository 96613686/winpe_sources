# RtlLockThisExclusive::RtlLockThisExclusive(RtlSrwLock &)

- ea: `0x180039b40`
- end: `0x180039b80`
- name: `??0RtlLockThisExclusive@@QEAA@AEAVRtlSrwLock@@@Z`
- size: `64`
- prototype: `RtlLockThisExclusive *__fastcall(RtlLockThisExclusive *this, RTL_SRWLOCK *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001ef74`
- `0x1800841a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180039b5d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180039b5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039b63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039b63`

## pseudocode

```c
RtlLockThisExclusive *__fastcall RtlLockThisExclusive::RtlLockThisExclusive(
        RtlLockThisExclusive *this,
        RTL_SRWLOCK *a2)
{
  RtlLockThisExclusive *result; // rax

  *(_DWORD *)this = 0;
  *((_QWORD *)this + 1) = a2;
  AcquireSRWLockExclusive(a2);
  LODWORD(a2[1].Ptr) = GetCurrentThreadId();
  result = this;
  *(_DWORD *)this = 2;
  return result;
}

```

## disassembly

```asm
0x180039b40  mov     [rsp+arg_0], rbx
0x180039b45  push    rdi
0x180039b46  sub     rsp, 20h
0x180039b4a  mov     rdi, rcx
0x180039b4d  mov     dword ptr [rcx], 0
0x180039b53  mov     [rcx+8], rdx
0x180039b57  mov     rbx, rdx
0x180039b5a  mov     rcx, rdx; SRWLock
0x180039b5d  call    cs:__imp_AcquireSRWLockExclusive
0x180039b63  call    cs:__imp_GetCurrentThreadId
0x180039b69  mov     [rbx+8], eax
0x180039b6c  mov     rax, rdi
0x180039b6f  mov     rbx, [rsp+28h+arg_0]
0x180039b74  mov     dword ptr [rdi], 2
0x180039b7a  add     rsp, 20h
0x180039b7e  pop     rdi
0x180039b7f  retn
```
