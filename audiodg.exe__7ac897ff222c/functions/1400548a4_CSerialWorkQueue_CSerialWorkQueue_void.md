# CSerialWorkQueue::~CSerialWorkQueue(void)

- ea: `0x1400548a4`
- end: `0x1400548f9`
- name: `??1CSerialWorkQueue@@QEAA@XZ`
- size: `85`
- prototype: `void __fastcall(CSerialWorkQueue *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14003b170`

## callees

- `0x1400548a4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1400548c0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1400548c0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1400548e6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1400548e6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1400548cd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1400548cd`

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
0x1400548a4  push    rbx
0x1400548a6  sub     rsp, 20h
0x1400548aa  mov     rbx, rcx
0x1400548ad  mov     rcx, [rcx+0A8h]; ptpcg
0x1400548b4  test    rcx, rcx
0x1400548b7  jz      short loc_1400548DE
0x1400548b9  xor     r8d, r8d; pvCleanupContext
0x1400548bc  lea     edx, [r8+1]; fCancelPendingCallbacks
0x1400548c0  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1400548c6  mov     rcx, [rbx+0A8h]; ptpcg
0x1400548cd  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1400548d3  mov     qword ptr [rbx+0A8h], 0
0x1400548de  mov     rcx, [rbx]; ptpp
0x1400548e1  test    rcx, rcx
0x1400548e4  jz      short loc_1400548F3
0x1400548e6  call    cs:__imp_CloseThreadpool
0x1400548ec  mov     qword ptr [rbx], 0
0x1400548f3  add     rsp, 20h
0x1400548f7  pop     rbx
0x1400548f8  retn
```
