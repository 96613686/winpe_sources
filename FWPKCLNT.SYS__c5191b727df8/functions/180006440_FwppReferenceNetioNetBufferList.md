# FwppReferenceNetioNetBufferList

- ea: `0x180006440`
- end: `0x1800067bc`
- name: `FwppReferenceNetioNetBufferList`
- size: `892`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18000b550`

## callees

- `0x180004904`
- `0x180006440`
- `0x18000c9b4`
- `0x18000de60`
- `0x1800208c0`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1800064cc`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1800065e7`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1800064cc`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1800065e7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1800064ae`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1800064ae`
- `ntoskrnl!MmBadPointer` at `0x180006470`
- `ntoskrnl!MmBadPointer` at `0x180006518`
- `ntoskrnl!MmBadPointer` at `0x1800065a5`
- `ntoskrnl!MmBadPointer` at `0x18000667c`
- `ntoskrnl!MmBadPointer` at `0x1800066f1`
- `ntoskrnl!MmBadPointer` at `0x18000670a`
- `ntoskrnl!MmBadPointer` at `0x1800067ad`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x180006615`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x180006615`
- `ntoskrnl!KeGetCurrentIrql` at `0x180006493`
- `ntoskrnl!KeGetCurrentIrql` at `0x180006493`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180006724`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180006724`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18000653c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18000653c`
- `NETIO!WfpNblInfoSet` at `0x1800066fe`
- `NETIO!WfpNblInfoSet` at `0x1800066fe`
- `NETIO!WfpNblInfoGet` at `0x18000645b`
- `NETIO!WfpNblInfoGet` at `0x180006503`
- `NETIO!WfpNblInfoGet` at `0x180006590`
- `NETIO!WfpNblInfoGet` at `0x18000666b`
- `NETIO!WfpNblInfoGet` at `0x18000645b`
- `NETIO!WfpNblInfoGet` at `0x180006503`
- `NETIO!WfpNblInfoGet` at `0x180006590`
- `NETIO!WfpNblInfoGet` at `0x18000666b`
- `NETIO!WfpNblInfoAlloc` at `0x180006655`
- `NETIO!WfpNblInfoAlloc` at `0x180006655`
- `NETIO!WfpNblInfoDestroyIfUnused` at `0x18000675a`
- `NETIO!WfpNblInfoDestroyIfUnused` at `0x18000675a`
- `NETIO!NetioReferenceNetBufferList` at `0x180006624`
- `NETIO!NetioReferenceNetBufferList` at `0x180006624`

## string_xrefs

- `0x180006789`: `ExAllocateFromNPagedLookasideList`
- `0x18000679e`: `WfpAllocFromNPagedLookasideList`

## pseudocode

```c
__int64 __fastcall FwppReferenceNetioNetBufferList(__int64 a1, char a2)
{
  _QWORD *v4; // rax
  _DWORD *v5; // r14
  KIRQL CurrentIrql; // di
  __int64 v7; // rdx
  _QWORD *v8; // rax
  PVOID *v9; // rdx
  _DWORD *v10; // rcx
  __int64 v11; // rcx
  _DWORD *v12; // rdi
  _QWORD *v13; // rax
  _DWORD *v14; // rdx
  __int64 result; // rax
  int v16; // ebp
  __int64 v17; // r8
  __int64 v18; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-28h] BYREF

  v4 = (_QWORD *)WfpNblInfoGet(a1);
  if ( !v4 || v4 == MmBadPointer )
    v5 = 0;
  else
    v5 = (_DWORD *)v4[3];
  memset(&LockHandle, 0, sizeof(LockHandle));
  CurrentIrql = KeGetCurrentIrql();
  KeAcquireInStackQueuedSpinLock(&qword_1800482C0, &LockHandle);
  if ( CurrentIrql != 2 && WPP_MAIN_CB.DeviceExtension )
  {
    v7 = *(_QWORD *)((char *)WPP_MAIN_CB.DeviceExtension + WPP_MAIN_CB.DeviceType * KeGetCurrentProcessorNumberEx(0));
    *(_QWORD *)(v7 + 8) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)v7 = 4;
  }
  v8 = (_QWORD *)WfpNblInfoGet(a1);
  if ( !v8 || (v9 = (PVOID *)MmBadPointer, v8 == MmBadPointer) )
  {
    v9 = (PVOID *)MmBadPointer;
    v10 = MmBadPointer;
    if ( v8 != MmBadPointer )
      goto LABEL_11;
  }
  else
  {
    v10 = (_DWORD *)v8[1];
  }
  if ( v10 && v10 != *v9 )
  {
    if ( v10[1] == 2 )
      ++v10[87];
    goto LABEL_19;
  }
LABEL_11:
  v12 = ExAllocateFromNPagedLookasideList(&gFwpNblInfo);
  if ( v12 || (v18 = WfpReportSysErrorAsNtStatus(v11, (int)"ExAllocateFromNPagedLookasideList", -1073741801)) == 0 )
  {
    memset(v12, 0, 0x178u);
    v12[1] = 2;
    v12[44] = 1;
    if ( v5 )
    {
      v12[86] = *v5;
      *((_QWORD *)v12 + 42) = v12 + 86;
    }
    v12[87] = 1;
  }
  else
  {
    WfpReportError(v18, (int)"WfpAllocFromNPagedLookasideList");
    v12 = MmBadPointer;
  }
  v13 = (_QWORD *)WfpNblInfoGet(a1);
  if ( v13 && v13 != MmBadPointer )
    goto LABEL_17;
  v16 = WfpNblInfoAlloc(a1);
  if ( !v16 )
  {
    v13 = (_QWORD *)WfpNblInfoGet(a1);
LABEL_17:
    if ( v12 )
    {
      *v12 = 1852864326;
      *((_QWORD *)v12 + 1) = v13;
      v13[1] = v12;
    }
    else
    {
      v13[1] = 0;
      WfpNblInfoDestroyIfUnused(a1);
    }
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xAu, v17, "WfpNblInfoAlloc", v16);
  }
  WfpReportError(v16, (int)"FwppSetPacketInfo");
  WfpNblInfoSet(a1, MmBadPointer);
  if ( v12 != MmBadPointer )
    ExFreeToNPagedLookasideList(&gFwpNblInfo, v12);
LABEL_19:
  if ( WPP_MAIN_CB.DeviceExtension )
  {
    v14 = *(_DWORD **)((char *)WPP_MAIN_CB.DeviceExtension + WPP_MAIN_CB.DeviceType * KeGetCurrentProcessorNumberEx(0));
    if ( *v14 == 4 )
      *v14 = 0;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  result = NetioReferenceNetBufferList(a1);
  if ( a2 )
    *(_DWORD *)(a1 + 136) |= 0x800000u;
  _InterlockedIncrement(&dword_180048700);
  return result;
}

```

## disassembly

```asm
0x180006440  push    rbx
0x180006442  sub     rsp, 50h
0x180006446  mov     [rsp+58h+arg_8], rsi
0x18000644b  mov     rbx, rcx
0x18000644e  mov     [rsp+58h+arg_10], rdi
0x180006453  movzx   esi, dl
0x180006456  mov     [rsp+58h+arg_18], r14
0x18000645b  call    cs:__imp_WfpNblInfoGet
0x180006462  nop     dword ptr [rax+rax+00h]
0x180006467  test    rax, rax
0x18000646a  jz      loc_180006694
0x180006470  mov     rcx, cs:MmBadPointer
0x180006477  cmp     rax, [rcx]
0x18000647a  jz      loc_180006694
0x180006480  mov     r14, [rax+18h]
0x180006484  xorps   xmm0, xmm0
0x180006487  xor     eax, eax
0x180006489  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x18000648e  mov     qword ptr [rsp+58h+LockHandle.OldIrql], rax
0x180006493  call    cs:__imp_KeGetCurrentIrql
0x18000649a  nop     dword ptr [rax+rax+00h]
0x18000649f  lea     rdx, [rsp+58h+LockHandle]; LockHandle
0x1800064a4  movzx   edi, al
0x1800064a7  lea     rcx, qword_1800482C0; SpinLock
0x1800064ae  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1800064b5  nop     dword ptr [rax+rax+00h]
0x1800064ba  cmp     dil, 2
0x1800064be  jz      short loc_180006500
0x1800064c0  cmp     cs:WPP_MAIN_CB.DeviceExtension, 0
0x1800064c8  jz      short loc_180006500
0x1800064ca  xor     ecx, ecx; ProcNumber
0x1800064cc  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1800064d3  nop     dword ptr [rax+rax+00h]
0x1800064d8  imul    eax, cs:WPP_MAIN_CB.DeviceType
0x1800064df  mov     ecx, eax
0x1800064e1  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x1800064e8  mov     rdx, [rcx+rax]
0x1800064ec  mov     rax, ds:0FFFFF78000000008h
0x1800064f6  mov     [rdx+8], rax
0x1800064fa  mov     dword ptr [rdx], 4
0x180006500  mov     rcx, rbx
0x180006503  call    cs:__imp_WfpNblInfoGet
0x18000650a  nop     dword ptr [rax+rax+00h]
0x18000650f  test    rax, rax
0x180006512  jz      loc_18000667C
0x180006518  mov     rdx, cs:MmBadPointer
0x18000651f  cmp     rax, [rdx]
0x180006522  jz      loc_18000667C
0x180006528  mov     rcx, [rax+8]
0x18000652c  test    rcx, rcx
0x18000652f  jnz     loc_180006735
0x180006535  lea     rcx, gFwpNblInfo; Lookaside
0x18000653c  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x180006543  nop     dword ptr [rax+rax+00h]
0x180006548  mov     rdi, rax
0x18000654b  test    rax, rax
0x18000654e  jz      loc_180006783
0x180006554  xor     edx, edx; Val
0x180006556  mov     r8d, 178h; Size
0x18000655c  mov     rcx, rdi; void *
0x18000655f  call    memset
0x180006564  mov     dword ptr [rdi+4], 2
0x18000656b  mov     dword ptr [rdi+0B0h], 1
0x180006575  test    r14, r14
0x180006578  jnz     loc_18000676B
0x18000657e  mov     dword ptr [rdi+15Ch], 1
0x180006588  mov     rcx, rbx
0x18000658b  mov     [rsp+58h+arg_0], rbp
0x180006590  call    cs:__imp_WfpNblInfoGet
0x180006597  nop     dword ptr [rax+rax+00h]
0x18000659c  test    rax, rax
0x18000659f  jz      loc_180006652
0x1800065a5  mov     rcx, cs:MmBadPointer
0x1800065ac  cmp     rax, [rcx]
0x1800065af  jz      loc_180006652
0x1800065b5  test    rdi, rdi
0x1800065b8  jz      loc_180006753
0x1800065be  mov     dword ptr [rdi], 6E707746h
0x1800065c4  mov     [rdi+8], rax
0x1800065c8  mov     [rax+8], rdi
0x1800065cc  mov     rbp, [rsp+58h+arg_0]
0x1800065d1  cmp     cs:WPP_MAIN_CB.DeviceExtension, 0
0x1800065d9  mov     r14, [rsp+58h+arg_18]
0x1800065de  mov     rdi, [rsp+58h+arg_10]
0x1800065e3  jz      short loc_180006610
0x1800065e5  xor     ecx, ecx; ProcNumber
0x1800065e7  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1800065ee  nop     dword ptr [rax+rax+00h]
0x1800065f3  imul    eax, cs:WPP_MAIN_CB.DeviceType
0x1800065fa  mov     ecx, eax
0x1800065fc  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x180006603  mov     rdx, [rcx+rax]
0x180006607  cmp     dword ptr [rdx], 4
0x18000660a  jz      loc_18000669C
0x180006610  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x180006615  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x18000661c  nop     dword ptr [rax+rax+00h]
0x180006621  mov     rcx, rbx
0x180006624  call    cs:__imp_NetioReferenceNetBufferList
0x18000662b  nop     dword ptr [rax+rax+00h]
0x180006630  test    sil, sil
0x180006633  mov     rsi, [rsp+58h+arg_8]
0x180006638  jz      short loc_180006644
0x18000663a  or      dword ptr [rbx+88h], 800000h
0x180006644  lock inc cs:dword_180048700
0x18000664b  add     rsp, 50h
0x18000664f  pop     rbx
0x180006650  retn
0x180006652  mov     rcx, rbx
0x180006655  call    cs:__imp_WfpNblInfoAlloc
0x18000665c  nop     dword ptr [rax+rax+00h]
0x180006661  movsxd  rbp, eax
0x180006664  test    eax, eax
0x180006666  jnz     short loc_1800066A7
0x180006668  mov     rcx, rbx
0x18000666b  call    cs:__imp_WfpNblInfoGet
0x180006672  nop     dword ptr [rax+rax+00h]
0x180006677  jmp     loc_1800065B5
0x18000667c  mov     rdx, cs:MmBadPointer
0x180006683  mov     rcx, [rdx]
0x180006686  cmp     rax, rcx
0x180006689  jz      loc_18000652C
0x18000668f  jmp     loc_180006535
0x180006694  xor     r14d, r14d
0x180006697  jmp     loc_180006484
0x18000669c  mov     dword ptr [rdx], 0
0x1800066a2  jmp     loc_180006610
0x1800066a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066ae  lea     rax, WPP_GLOBAL_Control
0x1800066b5  cmp     rcx, rax
0x1800066b8  jz      short loc_1800066E2
0x1800066ba  cmp     byte ptr [rcx+29h], 2
0x1800066be  jb      short loc_1800066E2
0x1800066c0  test    dword ptr [rcx+2Ch], 1000h
0x1800066c7  jz      short loc_1800066E2
0x1800066c9  mov     rcx, [rcx+18h]
0x1800066cd  lea     r9, aWfpnblinfoallo; "WfpNblInfoAlloc"
0x1800066d4  mov     edx, 0Ah
0x1800066d9  mov     [rsp+58h+var_38], ebp
0x1800066dd  call    WPP_SF_sd
0x1800066e2  mov     rcx, rbp
0x1800066e5  lea     rdx, aFwppsetpacketi; "FwppSetPacketInfo"
0x1800066ec  call    WfpReportError
0x1800066f1  mov     rdx, cs:MmBadPointer
0x1800066f8  mov     rcx, rbx
0x1800066fb  mov     rdx, [rdx]
0x1800066fe  call    cs:__imp_WfpNblInfoSet
0x180006705  nop     dword ptr [rax+rax+00h]
0x18000670a  mov     rax, cs:MmBadPointer
0x180006711  cmp     rdi, [rax]
0x180006714  jz      loc_1800065CC
0x18000671a  mov     rdx, rdi; Entry
0x18000671d  lea     rcx, gFwpNblInfo; Lookaside
0x180006724  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000672b  nop     dword ptr [rax+rax+00h]
0x180006730  jmp     loc_1800065CC
0x180006735  cmp     rcx, [rdx]
0x180006738  jz      loc_180006535
0x18000673e  cmp     dword ptr [rcx+4], 2
0x180006742  jnz     loc_1800065D1
0x180006748  inc     dword ptr [rcx+15Ch]
0x18000674e  jmp     loc_1800065D1
0x180006753  mov     rcx, rbx
0x180006756  mov     [rax+8], rdi
0x18000675a  call    cs:__imp_WfpNblInfoDestroyIfUnused
0x180006761  nop     dword ptr [rax+rax+00h]
0x180006766  jmp     loc_1800065CC
0x18000676b  mov     eax, [r14]
0x18000676e  lea     rcx, [rdi+158h]
0x180006775  mov     [rcx], eax
0x180006777  mov     [rdi+150h], rcx
0x18000677e  jmp     loc_18000657E
0x180006783  mov     r8d, 0C0000017h
0x180006789  lea     rdx, aExallocatefrom; "ExAllocateFromNPagedLookasideList"
0x180006790  call    WfpReportSysErrorAsNtStatus
0x180006795  test    rax, rax
0x180006798  jz      loc_180006554
0x18000679e  lea     rdx, aWfpallocfromnp; "WfpAllocFromNPagedLookasideList"
0x1800067a5  mov     rcx, rax
0x1800067a8  call    WfpReportError
0x1800067ad  mov     rax, cs:MmBadPointer
0x1800067b4  mov     rdi, [rax]
0x1800067b7  jmp     loc_180006588
```
