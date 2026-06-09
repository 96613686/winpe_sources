# FwppAllocateNetioCloneNetBufferList

- ea: `0x180003fc0`
- end: `0x18000461a`
- name: `FwppAllocateNetioCloneNetBufferList`
- size: `1626`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180009200`

## callees

- `0x180003fc0`
- `0x180004904`
- `0x180004960`
- `0x18000c9b4`
- `0x18000de60`
- `0x1800208c0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1800044a0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1800044a0`
- `ntoskrnl!MmBadPointer` at `0x180004031`
- `ntoskrnl!MmBadPointer` at `0x1800040f1`
- `ntoskrnl!MmBadPointer` at `0x18000411e`
- `ntoskrnl!MmBadPointer` at `0x1800041c7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1800045df`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1800045df`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180004058`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180004058`
- `NDIS!NdisFreeCloneNetBufferList` at `0x1800045ff`
- `NDIS!NdisFreeCloneNetBufferList` at `0x1800045ff`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x180004442`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x180004442`
- `NDIS!NdisAllocateCloneNetBufferList` at `0x180003ffe`
- `NDIS!NdisAllocateCloneNetBufferList` at `0x18000424f`
- `NDIS!NdisAllocateCloneNetBufferList` at `0x180003ffe`
- `NDIS!NdisAllocateCloneNetBufferList` at `0x18000424f`
- `NETIO!NetioCleanupNetBufferListInformation` at `0x18000420a`
- `NETIO!NetioCleanupNetBufferListInformation` at `0x18000420a`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x18000435b`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x18000435b`
- `NETIO!NetioCopyNetBufferListInformation` at `0x1800040a3`
- `NETIO!NetioCopyNetBufferListInformation` at `0x1800040a3`
- `NETIO!WfpNblInfoGet` at `0x180004019`
- `NETIO!WfpNblInfoGet` at `0x1800040e0`
- `NETIO!WfpNblInfoGet` at `0x18000410d`
- `NETIO!WfpNblInfoGet` at `0x1800041b6`
- `NETIO!WfpNblInfoGet` at `0x180004019`
- `NETIO!WfpNblInfoGet` at `0x1800040e0`
- `NETIO!WfpNblInfoGet` at `0x18000410d`
- `NETIO!WfpNblInfoGet` at `0x1800041b6`
- `NETIO!WfpNblInfoAlloc` at `0x1800041a0`
- `NETIO!WfpNblInfoAlloc` at `0x1800041a0`
- `NETIO!WfpNblInfoDestroyIfUnused` at `0x180004421`
- `NETIO!WfpNblInfoDestroyIfUnused` at `0x180004421`
- `NETIO!WfpNblInfoClone` at `0x1800040c0`
- `NETIO!WfpNblInfoClone` at `0x1800040c0`
- `NETIO!NetioReferenceNetBufferList` at `0x180004091`
- `NETIO!NetioReferenceNetBufferList` at `0x180004091`
- `NETIO!NetioAllocateMdl` at `0x1800042ca`
- `NETIO!NetioAllocateMdl` at `0x1800042ca`
- `NETIO!NetioAllocateMdl` at `0x180004432`

## string_xrefs

- `0x1800044dd`: `ExAllocateFromNPagedLookasideList`
- `0x1800044f5`: `WfpAllocFromNPagedLookasideList`

## pseudocode

```c
__int64 __fastcall FwppAllocateNetioCloneNetBufferList(
        struct _NET_BUFFER_LIST *a1,
        void *a2,
        void *a3,
        ULONG a4,
        PNET_BUFFER_LIST *a5)
{
  _DWORD *v5; // rsi
  int v6; // r14d
  ULONG v7; // r12d
  int v9; // r15d
  __int64 v10; // rcx
  PNET_BUFFER_LIST CloneNetBufferList; // rbp
  _QWORD *v12; // rdx
  PVOID v13; // rcx
  _QWORD *v14; // rax
  _QWORD *v15; // r14
  __int64 v16; // rcx
  __int64 v17; // r9
  int v18; // eax
  __int64 v19; // rcx
  _QWORD *v20; // rax
  _DWORD *v21; // rax
  _QWORD *v22; // rax
  PNET_BUFFER_LIST *v23; // rax
  unsigned int v24; // ebx
  __int64 v25; // rax
  unsigned int v27; // eax
  __int64 v28; // r8
  _DWORD *v29; // rax
  PNET_BUFFER_LIST v30; // rax
  __int64 v31; // r8
  struct _NET_BUFFER *FirstNetBuffer; // r14
  int v33; // r15d
  __int64 DataLength; // r12
  __int64 DataOffset; // r13
  PMDL v36; // rax
  __int64 v37; // r8
  ULONG v38; // edx
  ULONG v39; // eax
  PMDL CurrentMdl; // rcx
  char *MappedSystemVa; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  ULONG BugCheckOnFailure[2]; // [rsp+20h] [rbp-68h]
  ULONG BugCheckOnFailurea[2]; // [rsp+20h] [rbp-68h]
  __int64 v46; // [rsp+38h] [rbp-50h] BYREF
  PMDL MdlChain; // [rsp+40h] [rbp-48h]
  ULONG BufferSize; // [rsp+90h] [rbp+8h] BYREF
  ULONG v49; // [rsp+A8h] [rbp+20h]

  v49 = a4;
  v5 = 0;
  v6 = 0;
  v7 = a4;
  if ( (a1->Flags & 0x800000) == 0 )
  {
    v9 = 0;
    CloneNetBufferList = NdisAllocateCloneNetBufferList(a1, a2, a3, a4);
    if ( CloneNetBufferList )
      goto LABEL_3;
    v25 = WfpReportSysErrorAsNtStatus(v10, (int)"NdisAllocateCloneNetBufferList", -1073741801);
LABEL_19:
    v24 = v25;
    if ( !v25 )
      return v24;
    if ( v6 )
      goto LABEL_28;
    goto LABEL_74;
  }
  BufferSize = 0;
  v30 = NdisAllocateCloneNetBufferList(a1, a2, a3, 2u);
  CloneNetBufferList = v30;
  v24 = -1073741801;
  if ( !v30 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      WPP_SF_sd((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xAu, v31, "NdisAllocateCloneNetBufferList", -1073741801);
    }
    goto LABEL_49;
  }
  FirstNetBuffer = v30->FirstNetBuffer;
  v33 = 0;
  if ( !FirstNetBuffer )
    goto LABEL_44;
  do
  {
    DataLength = FirstNetBuffer->DataLength;
    DataOffset = FirstNetBuffer->DataOffset;
    MdlChain = FirstNetBuffer->MdlChain;
    v46 = 0;
    FirstNetBuffer->MdlChain = 0;
    FirstNetBuffer->Link.Region = 0;
    FirstNetBuffer->CurrentMdlOffset = 0;
    if ( (unsigned int)DataOffset <= ~(_DWORD)DataLength )
    {
      BufferSize = DataLength + DataOffset;
LABEL_35:
      v36 = NetioAllocateMdl(&BufferSize);
      FirstNetBuffer->MdlChain = v36;
      if ( v36 )
      {
        FirstNetBuffer->DataOffset = BufferSize;
        v38 = BufferSize;
        FirstNetBuffer->DataLength = 0;
        FirstNetBuffer->Link.Region = (ULONGLONG)v36;
        FirstNetBuffer->CurrentMdlOffset = BufferSize;
        v39 = BufferSize;
        if ( BufferSize < (unsigned int)DataLength )
        {
          NdisRetreatNetBufferDataStart(FirstNetBuffer, DataLength, 0, NetioAllocateMdl);
        }
        else
        {
          FirstNetBuffer->DataLength = DataLength;
          FirstNetBuffer->CurrentMdlOffset = v39 - DataLength;
          FirstNetBuffer->DataOffset = v38 - DataLength;
        }
        CurrentMdl = FirstNetBuffer->CurrentMdl;
        if ( (CurrentMdl->MdlFlags & 5) != 0 )
          MappedSystemVa = (char *)CurrentMdl->MappedSystemVa;
        else
          MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(CurrentMdl, 0, MmCached, 0, 0, 0x40000000u);
        RtlCopyMdlToKernelBuffer(
          MdlChain,
          DataOffset,
          &MappedSystemVa[FirstNetBuffer->CurrentMdlOffset],
          DataLength,
          &v46);
      }
      else
      {
        v33 = 1;
      }
      goto LABEL_41;
    }
    v42 = WfpReportSysErrorAsNtStatus(0, (int)"WfpUINT32Add", -1073741675);
    if ( !v42 )
      goto LABEL_35;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      BugCheckOnFailure[0] = v42;
      WPP_SF_sd((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xFu, v37, "WfpUINT32Add", *(_QWORD *)BugCheckOnFailure);
    }
    v33 = 1;
LABEL_41:
    FirstNetBuffer = (struct _NET_BUFFER *)FirstNetBuffer->Link.Alignment;
  }
  while ( FirstNetBuffer );
  v24 = -1073741801;
  if ( v33 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      BugCheckOnFailure[0] = -1073741801;
      WPP_SF_sd(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0xAu,
        v37,
        "NdisAllocateCloneNetBufferList",
        *(_QWORD *)BugCheckOnFailure);
    }
    FwppFreeDeepCloneNetBufferList(CloneNetBufferList);
LABEL_49:
    WfpReportError(-1073741801, (int)"FwppDeepCloneNetBufferList");
    return v24;
  }
  v7 = v49;
LABEL_44:
  v9 = 1;
LABEL_3:
  v12 = (_QWORD *)WfpNblInfoGet(a1);
  if ( v12 )
  {
    v13 = MmBadPointer;
    v14 = MmBadPointer;
    if ( v12 != MmBadPointer )
    {
      v15 = (_QWORD *)v12[1];
      goto LABEL_6;
    }
  }
  v14 = MmBadPointer;
  if ( v12 == MmBadPointer )
    goto LABEL_72;
  v15 = 0;
LABEL_6:
  if ( v15 == v14 )
  {
LABEL_72:
    v25 = WfpReportSysErrorAsNtStatus((__int64)v13, (int)"FwpsAllocateCloneNetBufferList0", -1073741801);
    v6 = 0;
    goto LABEL_19;
  }
  v5 = ExAllocateFromNPagedLookasideList(&gFwpNblInfo);
  if ( !v5 )
  {
    v43 = WfpReportSysErrorAsNtStatus(v16, (int)"ExAllocateFromNPagedLookasideList", -1073741801);
    v24 = v43;
    if ( v43 )
    {
      WfpReportError(v43, (int)"WfpAllocFromNPagedLookasideList");
      goto LABEL_76;
    }
  }
  memset(v5, 0, 0x178u);
  v5[1] = 1;
  v5[45] = v9;
  NetioReferenceNetBufferList(a1);
  NetioCopyNetBufferListInformation(CloneNetBufferList, a1);
  LOBYTE(v17) = 1;
  LOBYTE(BugCheckOnFailure[0]) = 0;
  v18 = WfpNblInfoClone(a1, CloneNetBufferList, 0, v17, BugCheckOnFailure[0]);
  if ( v18 )
  {
    v6 = 1;
    v25 = WfpReportSysErrorAsNtStatus(v19, (int)"WfpNblInfoClone", v18);
    goto LABEL_19;
  }
  if ( v15 )
  {
    v29 = (_DWORD *)v15[42];
    if ( v29 )
    {
      v5[86] = *v29;
      *((_QWORD *)v5 + 42) = v5 + 86;
    }
  }
  v20 = (_QWORD *)WfpNblInfoGet(a1);
  if ( v20 )
  {
    if ( v20 != MmBadPointer )
    {
      v21 = (_DWORD *)v20[3];
      if ( v21 )
      {
        if ( !*((_QWORD *)v5 + 42) )
        {
          v5[86] = *v21;
          *((_QWORD *)v5 + 42) = v5 + 86;
        }
      }
    }
  }
  v22 = (_QWORD *)WfpNblInfoGet(CloneNetBufferList);
  if ( v22 && v22 != MmBadPointer )
  {
LABEL_15:
    if ( v5 )
    {
      *v5 = 1852864326;
      *((_QWORD *)v5 + 1) = v22;
      v22[1] = v5;
    }
    else
    {
      v22[1] = 0;
      WfpNblInfoDestroyIfUnused(CloneNetBufferList);
    }
    v23 = a5;
    v24 = 0;
    CloneNetBufferList->ParentNetBufferList = a1;
    ++a1->ChildRefCount;
    *v23 = CloneNetBufferList;
    _InterlockedIncrement(&dword_180048700);
    return v24;
  }
  v27 = WfpNblInfoAlloc(CloneNetBufferList);
  v24 = v27;
  if ( !v27 )
  {
    v22 = (_QWORD *)WfpNblInfoGet(CloneNetBufferList);
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    BugCheckOnFailurea[0] = v27;
    WPP_SF_sd((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xAu, v28, "WfpNblInfoAlloc", *(_QWORD *)BugCheckOnFailurea);
  }
  WfpReportError(v24, (int)"FwppSetPacketInfo");
LABEL_28:
  NetioCleanupNetBufferListInformation(CloneNetBufferList);
LABEL_74:
  if ( v5 )
    ExFreeToNPagedLookasideList(&gFwpNblInfo, v5);
LABEL_76:
  if ( CloneNetBufferList )
  {
    if ( v9 )
      FwppFreeDeepCloneNetBufferList(CloneNetBufferList);
    else
      NdisFreeCloneNetBufferList(CloneNetBufferList, v7);
  }
  return v24;
}

```

## disassembly

```asm
0x180003fc0  mov     [rsp+arg_8], rbx
0x180003fc5  mov     [rsp+arg_18], r9d
0x180003fca  push    rbp
0x180003fcb  push    rsi
0x180003fcc  push    rdi
0x180003fcd  push    r12
0x180003fcf  push    r13
0x180003fd1  push    r14
0x180003fd3  push    r15
0x180003fd5  sub     rsp, 50h
0x180003fd9  xor     esi, esi
0x180003fdb  lea     r13, WPP_GLOBAL_Control
0x180003fe2  xor     r14d, r14d
0x180003fe5  mov     r12d, r9d
0x180003fe8  test    dword ptr [rcx+88h], 800000h
0x180003ff2  mov     rdi, rcx
0x180003ff5  jnz     loc_180004242
0x180003ffb  xor     r15d, r15d
0x180003ffe  call    cs:__imp_NdisAllocateCloneNetBufferList
0x180004005  nop     dword ptr [rax+rax+00h]
0x18000400a  mov     rbp, rax
0x18000400d  test    rax, rax
0x180004010  jz      loc_180004569
0x180004016  mov     rcx, rdi
0x180004019  call    cs:__imp_WfpNblInfoGet
0x180004020  nop     dword ptr [rax+rax+00h]
0x180004025  mov     rdx, rax
0x180004028  test    rax, rax
0x18000402b  jz      loc_1800041C7
0x180004031  mov     rcx, cs:MmBadPointer
0x180004038  mov     rax, [rcx]
0x18000403b  cmp     rdx, rax
0x18000403e  jz      loc_1800041C7
0x180004044  mov     r14, [rdx+8]
0x180004048  cmp     r14, rax
0x18000404b  jz      loc_1800045AC
0x180004051  lea     rcx, gFwpNblInfo; Lookaside
0x180004058  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x18000405f  nop     dword ptr [rax+rax+00h]
0x180004064  mov     rsi, rax
0x180004067  test    rax, rax
0x18000406a  jz      loc_1800044D6
0x180004070  xor     edx, edx; Val
0x180004072  mov     r8d, 178h; Size
0x180004078  mov     rcx, rsi; void *
0x18000407b  call    memset
0x180004080  mov     rcx, rdi
0x180004083  mov     dword ptr [rsi+4], 1
0x18000408a  mov     [rsi+0B4h], r15d
0x180004091  call    cs:__imp_NetioReferenceNetBufferList
0x180004098  nop     dword ptr [rax+rax+00h]
0x18000409d  mov     rdx, rdi
0x1800040a0  mov     rcx, rbp
0x1800040a3  call    cs:__imp_NetioCopyNetBufferListInformation
0x1800040aa  nop     dword ptr [rax+rax+00h]
0x1800040af  mov     r9b, 1
0x1800040b2  mov     byte ptr [rsp+88h+BugCheckOnFailure], 0
0x1800040b7  xor     r8d, r8d
0x1800040ba  mov     rdx, rbp
0x1800040bd  mov     rcx, rdi
0x1800040c0  call    cs:__imp_WfpNblInfoClone
0x1800040c7  nop     dword ptr [rax+rax+00h]
0x1800040cc  test    eax, eax
0x1800040ce  jnz     loc_180004161
0x1800040d4  test    r14, r14
0x1800040d7  jnz     loc_18000421B
0x1800040dd  mov     rcx, rdi
0x1800040e0  call    cs:__imp_WfpNblInfoGet
0x1800040e7  nop     dword ptr [rax+rax+00h]
0x1800040ec  test    rax, rax
0x1800040ef  jz      short loc_18000410A
0x1800040f1  mov     rcx, cs:MmBadPointer
0x1800040f8  cmp     rax, [rcx]
0x1800040fb  jz      short loc_18000410A
0x1800040fd  mov     rax, [rax+18h]
0x180004101  test    rax, rax
0x180004104  jnz     loc_1800044B1
0x18000410a  mov     rcx, rbp
0x18000410d  call    cs:__imp_WfpNblInfoGet
0x180004114  nop     dword ptr [rax+rax+00h]
0x180004119  test    rax, rax
0x18000411c  jz      short loc_18000419D
0x18000411e  mov     rcx, cs:MmBadPointer
0x180004125  cmp     rax, [rcx]
0x180004128  jz      short loc_18000419D
0x18000412a  test    rsi, rsi
0x18000412d  jz      loc_18000441A
0x180004133  mov     dword ptr [rsi], 6E707746h
0x180004139  mov     [rsi+8], rax
0x18000413d  mov     [rax+8], rsi
0x180004141  mov     rax, [rsp+88h+arg_20]
0x180004149  xor     ebx, ebx
0x18000414b  mov     [rbp+18h], rdi
0x18000414f  inc     dword ptr [rdi+84h]
0x180004155  mov     [rax], rbp
0x180004158  lock inc cs:dword_180048700
0x18000415f  jmp     short loc_180004182
0x180004161  mov     r8d, eax
0x180004164  lea     rdx, aWfpnblinfoclon; "WfpNblInfoClone"
0x18000416b  mov     r14d, 1
0x180004171  call    WfpReportSysErrorAsNtStatus
0x180004176  mov     rbx, rax
0x180004179  test    rax, rax
0x18000417c  jnz     loc_1800045C7
0x180004182  mov     eax, ebx
0x180004184  mov     rbx, [rsp+88h+arg_8]
0x18000418c  add     rsp, 50h
0x180004190  pop     r15
0x180004192  pop     r14
0x180004194  pop     r13
0x180004196  pop     r12
0x180004198  pop     rdi
0x180004199  pop     rsi
0x18000419a  pop     rbp
0x18000419b  retn
0x18000419d  mov     rcx, rbp
0x1800041a0  call    cs:__imp_WfpNblInfoAlloc
0x1800041a7  nop     dword ptr [rax+rax+00h]
0x1800041ac  movsxd  rbx, eax
0x1800041af  test    eax, eax
0x1800041b1  jnz     short loc_1800041E2
0x1800041b3  mov     rcx, rbp
0x1800041b6  call    cs:__imp_WfpNblInfoGet
0x1800041bd  nop     dword ptr [rax+rax+00h]
0x1800041c2  jmp     loc_18000412A
0x1800041c7  mov     rax, cs:MmBadPointer
0x1800041ce  mov     rax, [rax]
0x1800041d1  cmp     rdx, rax
0x1800041d4  jz      loc_1800045AC
0x1800041da  xor     r14d, r14d
0x1800041dd  jmp     loc_180004048
0x1800041e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800041e9  cmp     rcx, r13
0x1800041ec  jz      short loc_1800041F8
0x1800041ee  cmp     byte ptr [rcx+29h], 2
0x1800041f2  jnb     loc_180004581
0x1800041f8  lea     rdx, aFwppsetpacketi; "FwppSetPacketInfo"
0x1800041ff  mov     rcx, rbx
0x180004202  call    WfpReportError
0x180004207  mov     rcx, rbp
0x18000420a  call    cs:__imp_NetioCleanupNetBufferListInformation
0x180004211  nop     dword ptr [rax+rax+00h]
0x180004216  jmp     loc_1800045D0
0x18000421b  mov     rax, [r14+150h]
0x180004222  test    rax, rax
0x180004225  jz      loc_1800040DD
0x18000422b  mov     eax, [rax]
0x18000422d  lea     rcx, [rsi+158h]; OriginalNetBufferList
0x180004234  mov     [rcx], eax
0x180004236  mov     [rsi+150h], rcx
0x18000423d  jmp     loc_1800040DD
0x180004242  mov     r9d, 2; AllocateCloneFlags
0x180004248  mov     [rsp+88h+BufferSize], esi
0x18000424f  call    cs:__imp_NdisAllocateCloneNetBufferList
0x180004256  nop     dword ptr [rax+rax+00h]
0x18000425b  mov     rbp, rax
0x18000425e  mov     rbx, 0FFFFFFFFC0000017h
0x180004265  test    rax, rax
0x180004268  jz      loc_1800043DD
0x18000426e  mov     r14, [rax+8]
0x180004272  xor     ecx, ecx
0x180004274  mov     r15d, ecx
0x180004277  test    r14, r14
0x18000427a  jz      loc_180004391
0x180004280  lea     rbx, WPP_GLOBAL_Control
0x180004287  mov     rax, [r14+20h]
0x18000428b  mov     r12d, [r14+18h]
0x18000428f  mov     r13d, [r14+28h]
0x180004293  mov     [rsp+88h+var_48], rax
0x180004298  mov     eax, r12d
0x18000429b  not     eax
0x18000429d  mov     [rsp+88h+var_50], rcx
0x1800042a2  mov     [r14+20h], rcx
0x1800042a6  mov     [r14+8], rcx
0x1800042aa  mov     [r14+10h], ecx
0x1800042ae  cmp     r13d, eax
0x1800042b1  ja      loc_180004453
0x1800042b7  lea     eax, [r12+r13]
0x1800042bb  mov     [rsp+88h+BufferSize], eax
0x1800042c2  lea     rcx, [rsp+88h+BufferSize]; BufferSize
0x1800042ca  call    cs:__imp_NetioAllocateMdl
0x1800042d1  nop     dword ptr [rax+rax+00h]
0x1800042d6  mov     [r14+20h], rax
0x1800042da  mov     rcx, rax
0x1800042dd  test    rax, rax
0x1800042e0  jz      loc_18000439C
0x1800042e6  mov     eax, [rsp+88h+BufferSize]
0x1800042ed  mov     [r14+28h], eax
0x1800042f1  mov     edx, [rsp+88h+BufferSize]
0x1800042f8  mov     [r14+18h], esi
0x1800042fc  mov     [r14+8], rcx
0x180004300  mov     eax, [rsp+88h+BufferSize]
0x180004307  mov     [r14+10h], eax
0x18000430b  mov     eax, [rsp+88h+BufferSize]
0x180004312  cmp     eax, r12d
0x180004315  jb      loc_180004432
0x18000431b  sub     eax, r12d
0x18000431e  mov     [r14+18h], r12d
0x180004322  sub     edx, r12d
0x180004325  mov     [r14+10h], eax
0x180004329  mov     [r14+28h], edx
0x18000432d  mov     rcx, [r14+8]; MemoryDescriptorList
0x180004331  test    byte ptr [rcx+0Ah], 5
0x180004335  jz      loc_180004489
0x18000433b  mov     rax, [rcx+18h]
0x18000433f  mov     r8d, [r14+10h]
0x180004343  mov     r9, r12
0x180004346  mov     rcx, [rsp+88h+var_48]
0x18000434b  add     r8, rax
0x18000434e  lea     rax, [rsp+88h+var_50]
0x180004353  mov     rdx, r13
0x180004356  mov     qword ptr [rsp+88h+BugCheckOnFailure], rax
0x18000435b  call    cs:__imp_RtlCopyMdlToKernelBuffer
0x180004362  nop     dword ptr [rax+rax+00h]
0x180004367  mov     r14, [r14]
0x18000436a  mov     rcx, rsi
0x18000436d  test    r14, r14
0x180004370  jnz     loc_180004287
0x180004376  mov     rbx, 0FFFFFFFFC0000017h
0x18000437d  test    r15d, r15d
0x180004380  jnz     short loc_1800043A4
0x180004382  mov     r12d, [rsp+88h+arg_18]
0x18000438a  lea     r13, WPP_GLOBAL_Control
0x180004391  mov     r15d, 1
0x180004397  jmp     loc_180004016
0x18000439c  mov     r15d, 1
0x1800043a2  jmp     short loc_180004367
0x1800043a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043ab  lea     r13, WPP_GLOBAL_Control
0x1800043b2  cmp     rcx, r13
0x1800043b5  jz      short loc_1800043C1
0x1800043b7  cmp     byte ptr [rcx+29h], 2
0x1800043bb  jnb     loc_180004509
0x1800043c1  mov     rcx, rbp; CloneNetBufferList
0x1800043c4  call    FwppFreeDeepCloneNetBufferList
0x1800043c9  lea     rdx, aFwppdeepclonen; "FwppDeepCloneNetBufferList"
0x1800043d0  mov     rcx, rbx
0x1800043d3  call    WfpReportError
0x1800043d8  jmp     loc_180004182
0x1800043dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043e4  lea     r13, WPP_GLOBAL_Control
0x1800043eb  cmp     rcx, r13
0x1800043ee  jz      short loc_1800043C9
0x1800043f0  cmp     byte ptr [rcx+29h], 2
0x1800043f4  jb      short loc_1800043C9
0x1800043f6  test    dword ptr [rcx+2Ch], 1000h
0x1800043fd  jz      short loc_1800043C9
0x1800043ff  mov     rcx, [rcx+18h]
0x180004403  lea     r9, aNdisallocatecl; "NdisAllocateCloneNetBufferList"
0x18000440a  mov     edx, 0Ah
0x18000440f  mov     [rsp+88h+BugCheckOnFailure], ebx
0x180004413  call    WPP_SF_sd
0x180004418  jmp     short loc_1800043C9
0x18000441a  mov     rcx, rbp
0x18000441d  mov     [rax+8], rsi
0x180004421  call    cs:__imp_WfpNblInfoDestroyIfUnused
0x180004428  nop     dword ptr [rax+rax+00h]
0x18000442d  jmp     loc_180004141
0x180004432  mov     r9, cs:__imp_NetioAllocateMdl; AllocateMdlHandler
0x180004439  xor     r8d, r8d; DataBackFill
0x18000443c  mov     edx, r12d; DataOffsetDelta
0x18000443f  mov     rcx, r14; NetBuffer
0x180004442  call    cs:__imp_NdisRetreatNetBufferDataStart
0x180004449  nop     dword ptr [rax+rax+00h]
0x18000444e  jmp     loc_18000432D
0x180004453  mov     r8d, 0C0000095h
0x180004459  lea     rdx, aWfpuint32add; "WfpUINT32Add"
0x180004460  call    WfpReportSysErrorAsNtStatus
0x180004465  test    rax, rax
0x180004468  jz      loc_1800042C2
0x18000446e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004475  cmp     rcx, rbx
0x180004478  jnz     loc_180004534
0x18000447e  mov     r15d, 1
0x180004484  jmp     loc_180004367
0x180004489  mov     [rsp+88h+Priority], 40000000h; Priority
0x180004491  xor     r9d, r9d; RequestedAddress
0x180004494  xor     edx, edx; AccessMode
0x180004496  mov     [rsp+88h+BugCheckOnFailure], esi; BugCheckOnFailure
0x18000449a  mov     r8d, 1; CacheType
0x1800044a0  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1800044a7  nop     dword ptr [rax+rax+00h]
0x1800044ac  jmp     loc_18000433F
0x1800044b1  cmp     qword ptr [rsi+150h], 0
0x1800044b9  jnz     loc_18000410A
0x1800044bf  mov     eax, [rax]
0x1800044c1  lea     rcx, [rsi+158h]
0x1800044c8  mov     [rcx], eax
0x1800044ca  mov     [rsi+150h], rcx
0x1800044d1  jmp     loc_18000410A
0x1800044d6  mov     r8, 0FFFFFFFFC0000017h
0x1800044dd  lea     rdx, aExallocatefrom; "ExAllocateFromNPagedLookasideList"
0x1800044e4  call    WfpReportSysErrorAsNtStatus
0x1800044e9  mov     rbx, rax
0x1800044ec  test    rax, rax
0x1800044ef  jz      loc_180004070
0x1800044f5  lea     rdx, aWfpallocfromnp; "WfpAllocFromNPagedLookasideList"
0x1800044fc  mov     rcx, rax
0x1800044ff  call    WfpReportError
0x180004504  jmp     loc_1800045EB
  ... truncated ...
```
