# ThreadPool::`vector deleting destructor'(uint)

- ea: `0x18004fa00`
- end: `0x18004fa6b`
- name: `??_EThreadPool@@UEAAPEAXI@Z`
- size: `107`
- prototype: `ThreadPool *__fastcall(ThreadPool *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180003ea0`
- `0x18004fa00`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18004fa1d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18004fa1d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18004fa3f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18004fa3f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18004fa36`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18004fa36`

## pseudocode

```c
ThreadPool *__fastcall ThreadPool::`vector deleting destructor'(ThreadPool *this, char a2)
{
  struct _TP_POOL *v4; // rcx
  struct _TP_CLEANUP_GROUP *v5; // rdi

  v4 = (struct _TP_POOL *)*((_QWORD *)this + 11);
  if ( v4 )
    CloseThreadpool(v4);
  v5 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 10);
  if ( v5 )
  {
    CloseThreadpoolCleanupGroupMembers(*((PTP_CLEANUP_GROUP *)this + 10), 1, 0);
    CloseThreadpoolCleanupGroup(v5);
  }
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18004fa00  mov     [rsp+arg_0], rbx
0x18004fa05  mov     [rsp+arg_8], rsi
0x18004fa0a  push    rdi
0x18004fa0b  sub     rsp, 20h
0x18004fa0f  mov     rbx, rcx
0x18004fa12  mov     esi, edx
0x18004fa14  mov     rcx, [rcx+58h]; ptpp
0x18004fa18  test    rcx, rcx
0x18004fa1b  jz      short loc_18004FA23
0x18004fa1d  call    cs:__imp_CloseThreadpool
0x18004fa23  mov     rdi, [rbx+50h]
0x18004fa27  test    rdi, rdi
0x18004fa2a  jz      short loc_18004FA45
0x18004fa2c  xor     r8d, r8d; pvCleanupContext
0x18004fa2f  mov     rcx, rdi; ptpcg
0x18004fa32  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18004fa36  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18004fa3c  mov     rcx, rdi; ptpcg
0x18004fa3f  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18004fa45  test    sil, 1
0x18004fa49  jz      short loc_18004FA58
0x18004fa4b  mov     edx, 60h ; '`'; unsigned __int64
0x18004fa50  mov     rcx, rbx; void *
0x18004fa53  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004fa58  mov     rsi, [rsp+28h+arg_8]
0x18004fa5d  mov     rax, rbx
0x18004fa60  mov     rbx, [rsp+28h+arg_0]
0x18004fa65  add     rsp, 20h
0x18004fa69  pop     rdi
0x18004fa6a  retn
```
