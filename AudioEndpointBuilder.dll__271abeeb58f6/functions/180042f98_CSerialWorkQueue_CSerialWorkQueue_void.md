# CSerialWorkQueue::~CSerialWorkQueue(void)

- ea: `0x180042f98`
- end: `0x180042fed`
- name: `??1CSerialWorkQueue@@QEAA@XZ`
- size: `85`
- prototype: `void __fastcall(CSerialWorkQueue *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180042e88`

## callees

- `0x180042f98`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180042fda`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180042fda`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180042fc1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180042fc1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180042fb4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180042fb4`

## pseudocode

```c
void __fastcall CSerialWorkQueue::~CSerialWorkQueue(CSerialWorkQueue *this)
{
  struct _TP_CLEANUP_GROUP *v2; // rcx

  v2 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 21);
  if ( v2 )
  {
    CloseThreadpoolCleanupGroupMembers(v2, 1, 0);
    CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)this + 21));
    *((_QWORD *)this + 21) = 0;
  }
  if ( *(_QWORD *)this )
  {
    CloseThreadpool(*(PTP_POOL *)this);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180042f98  push    rbx
0x180042f9a  sub     rsp, 20h
0x180042f9e  mov     rbx, rcx
0x180042fa1  mov     rcx, [rcx+0A8h]; ptpcg
0x180042fa8  test    rcx, rcx
0x180042fab  jz      short loc_180042FD2
0x180042fad  xor     r8d, r8d; pvCleanupContext
0x180042fb0  lea     edx, [r8+1]; fCancelPendingCallbacks
0x180042fb4  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180042fba  mov     rcx, [rbx+0A8h]; ptpcg
0x180042fc1  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180042fc7  mov     qword ptr [rbx+0A8h], 0
0x180042fd2  mov     rcx, [rbx]; ptpp
0x180042fd5  test    rcx, rcx
0x180042fd8  jz      short loc_180042FE7
0x180042fda  call    cs:__imp_CloseThreadpool
0x180042fe0  mov     qword ptr [rbx], 0
0x180042fe7  add     rsp, 20h
0x180042feb  pop     rbx
0x180042fec  retn
```
