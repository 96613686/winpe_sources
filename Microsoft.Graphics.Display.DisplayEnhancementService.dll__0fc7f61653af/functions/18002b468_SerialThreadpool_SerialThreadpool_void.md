# SerialThreadpool::~SerialThreadpool(void)

- ea: `0x18002b468`
- end: `0x18002b4a4`
- name: `??1SerialThreadpool@@QEAA@XZ`
- size: `60`
- prototype: `void __fastcall(SerialThreadpool *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002b9d0`

## callees

- `0x18002b468`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18002b48f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18002b48f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002b485`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002b485`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18002b498`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18002b498`

## pseudocode

```c
void __fastcall SerialThreadpool::~SerialThreadpool(SerialThreadpool *this)
{
  struct _TP_CLEANUP_GROUP *v2; // rcx

  if ( *(_QWORD *)this )
  {
    v2 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 1);
    if ( v2 )
    {
      CloseThreadpoolCleanupGroupMembers(v2, 0, 0);
      CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)this + 1));
    }
    CloseThreadpool(*(PTP_POOL *)this);
  }
}

```

## disassembly

```asm
0x18002b468  push    rbx
0x18002b46a  sub     rsp, 20h
0x18002b46e  cmp     qword ptr [rcx], 0
0x18002b472  mov     rbx, rcx
0x18002b475  jz      short loc_18002B49E
0x18002b477  mov     rcx, [rcx+8]; ptpcg
0x18002b47b  test    rcx, rcx
0x18002b47e  jz      short loc_18002B495
0x18002b480  xor     r8d, r8d; pvCleanupContext
0x18002b483  xor     edx, edx; fCancelPendingCallbacks
0x18002b485  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18002b48b  mov     rcx, [rbx+8]; ptpcg
0x18002b48f  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18002b495  mov     rcx, [rbx]; ptpp
0x18002b498  call    cs:__imp_CloseThreadpool
0x18002b49e  add     rsp, 20h
0x18002b4a2  pop     rbx
0x18002b4a3  retn
```
