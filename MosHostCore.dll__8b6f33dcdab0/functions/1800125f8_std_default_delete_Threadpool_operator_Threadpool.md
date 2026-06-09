# std::default_delete<Threadpool>::operator()(Threadpool *)

- ea: `0x1800125f8`
- end: `0x180012650`
- name: `??R?$default_delete@VThreadpool@@@std@@QEBAXPEAVThreadpool@@@Z`
- size: `88`
- prototype: `void __fastcall(__int64, struct _TP_POOL **)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800121b4`
- `0x18001cb60`
- `0x18001f1f0`

## callees

- `0x1800033f4`
- `0x1800125f8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180012613`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180012613`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001261d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001261d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180012634`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180012634`

## pseudocode

```c
void __fastcall std::default_delete<Threadpool>::operator()(__int64 a1, struct _TP_POOL **a2)
{
  struct _TP_CLEANUP_GROUP *v2; // rcx
  struct _TP_POOL *v4; // rcx

  if ( a2 )
  {
    v2 = a2[10];
    if ( v2 )
    {
      CloseThreadpoolCleanupGroupMembers(v2, 0, 0);
      CloseThreadpoolCleanupGroup(a2[10]);
      a2[10] = 0;
    }
    v4 = a2[9];
    if ( v4 )
    {
      CloseThreadpool(v4);
      a2[9] = 0;
    }
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x1800125f8  test    rdx, rdx
0x1800125fb  jz      short locret_18001264F
0x1800125fd  push    rbx
0x1800125fe  sub     rsp, 20h
0x180012602  mov     rcx, [rdx+50h]; ptpcg
0x180012606  mov     rbx, rdx
0x180012609  test    rcx, rcx
0x18001260c  jz      short loc_18001262B
0x18001260e  xor     r8d, r8d; pvCleanupContext
0x180012611  xor     edx, edx; fCancelPendingCallbacks
0x180012613  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180012619  mov     rcx, [rbx+50h]; ptpcg
0x18001261d  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180012623  mov     qword ptr [rbx+50h], 0
0x18001262b  mov     rcx, [rbx+48h]; ptpp
0x18001262f  test    rcx, rcx
0x180012632  jz      short loc_180012642
0x180012634  call    cs:__imp_CloseThreadpool
0x18001263a  mov     qword ptr [rbx+48h], 0
0x180012642  mov     rcx, rbx; Block
0x180012645  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001264a  add     rsp, 20h
0x18001264e  pop     rbx
0x18001264f  retn
```
