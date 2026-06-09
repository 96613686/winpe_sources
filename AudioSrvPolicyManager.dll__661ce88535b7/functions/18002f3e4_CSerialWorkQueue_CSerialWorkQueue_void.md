# CSerialWorkQueue::~CSerialWorkQueue(void)

- ea: `0x18002f3e4`
- end: `0x18002f439`
- name: `??1CSerialWorkQueue@@QEAA@XZ`
- size: `85`
- prototype: `void __fastcall(CSerialWorkQueue *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002f33c`

## callees

- `0x18002f3e4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002f400`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002f400`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18002f426`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18002f426`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18002f40d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18002f40d`

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
0x18002f3e4  push    rbx
0x18002f3e6  sub     rsp, 20h
0x18002f3ea  mov     rbx, rcx
0x18002f3ed  mov     rcx, [rcx+0A8h]; ptpcg
0x18002f3f4  test    rcx, rcx
0x18002f3f7  jz      short loc_18002F41E
0x18002f3f9  xor     r8d, r8d; pvCleanupContext
0x18002f3fc  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18002f400  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18002f406  mov     rcx, [rbx+0A8h]; ptpcg
0x18002f40d  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18002f413  mov     qword ptr [rbx+0A8h], 0
0x18002f41e  mov     rcx, [rbx]; ptpp
0x18002f421  test    rcx, rcx
0x18002f424  jz      short loc_18002F433
0x18002f426  call    cs:__imp_CloseThreadpool
0x18002f42c  mov     qword ptr [rbx], 0
0x18002f433  add     rsp, 20h
0x18002f437  pop     rbx
0x18002f438  retn
```
