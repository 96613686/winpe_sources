# FwpsReassembleForwardFragmentGroup0

- ea: `0x18001ce30`
- end: `0x18001d39c`
- name: `FwpsReassembleForwardFragmentGroup0`
- size: `1388`
- prototype: `NTSTATUS __stdcall(ADDRESS_FAMILY addressFamily, NET_BUFFER_LIST *fragmentGroupNblChain, NDIS_HANDLE netBufferAndNetBufferListPoolHandle, ULONG dataBackFill, ULONG flags, NET_BUFFER_LIST **reassembledNbl)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004904`
- `0x180007ec0`
- `0x1800080f0`
- `0x180008480`
- `0x180008530`
- `0x18000891c`
- `0x18000c9b4`
- `0x18001ce30`
- `0x18001d3a4`
- `0x1800203c0`
- `0x180020400`
- `0x1800205c0`
- `0x1800208c0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18001d303`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18001d303`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x18001d020`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x18001d020`
- `NDIS!NdisAllocateReassembledNetBufferList` at `0x18001d209`
- `NDIS!NdisAllocateReassembledNetBufferList` at `0x18001d209`
- `NDIS!NdisFreeReassembledNetBufferList` at `0x18001d31c`
- `NDIS!NdisFreeReassembledNetBufferList` at `0x18001d31c`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x18001cfeb`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x18001cfeb`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x18001d04a`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x18001d04a`
- `NETIO!NetioReferenceNetBufferListChain` at `0x18001d269`
- `NETIO!NetioReferenceNetBufferListChain` at `0x18001d269`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
NTSTATUS __stdcall FwpsReassembleForwardFragmentGroup0(
        ADDRESS_FAMILY addressFamily,
        NET_BUFFER_LIST *fragmentGroupNblChain,
        NDIS_HANDLE netBufferAndNetBufferListPoolHandle,
        ULONG dataBackFill,
        ULONG flags,
        NET_BUFFER_LIST **reassembledNbl)
{
  struct _NET_BUFFER_LIST *ReassembledNetBufferList; // rsi
  _DWORD *v7; // rdi
  PVOID v8; // r15
  NET_BUFFER_LIST *v9; // r14
  ADDRESS_FAMILY v10; // bx
  __int128 v11; // xmm6
  int v12; // r8d
  const char *v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rbx
  PNET_BUFFER FirstNetBuffer; // rsi
  int v17; // r8d
  const char *v18; // rdx
  int v19; // eax
  unsigned int v20; // ebx
  __int64 v21; // rax
  _BYTE *v22; // r12
  unsigned int v23; // ecx
  __int64 v24; // r12
  __int64 v25; // r9
  __int64 v26; // r13
  __int64 DataBufferIfSafe; // rax
  _QWORD *Alignment; // rax
  struct _NET_BUFFER *v29; // rbx
  __int64 (__fastcall *v30)(_QWORD, struct _NET_BUFFER *, _QWORD, __int64, _QWORD, _QWORD, _QWORD, unsigned int *); // rax
  int v31; // edx
  __int64 v32; // rcx
  __int64 v33; // rax
  SLIST_HEADER *v34; // rax
  __int16 v35; // r12
  __int64 v36; // rax
  bool v37; // zf
  unsigned int v38; // ebx
  int v39; // eax
  PNET_BUFFER v40; // rdi
  __int64 v41; // rdx
  char v43[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v44; // [rsp+54h] [rbp-ACh] BYREF
  ADDRESS_FAMILY v45; // [rsp+58h] [rbp-A8h]
  unsigned int Size; // [rsp+68h] [rbp-98h]
  unsigned int Size_4; // [rsp+6Ch] [rbp-94h]
  PVOID v48; // [rsp+70h] [rbp-90h] BYREF
  PNET_BUFFER v49; // [rsp+78h] [rbp-88h] BYREF
  ULONG DataBackFill; // [rsp+80h] [rbp-80h]
  void *v51; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v52; // [rsp+90h] [rbp-70h]
  __int64 v53; // [rsp+98h] [rbp-68h]
  __int64 v54; // [rsp+A0h] [rbp-60h]
  struct _NET_BUFFER *v55; // [rsp+A8h] [rbp-58h]
  NDIS_HANDLE NetBufferAndNetBufferListPoolHandle; // [rsp+B0h] [rbp-50h]
  NET_BUFFER_LIST **v57; // [rsp+B8h] [rbp-48h]
  _BYTE Src[128]; // [rsp+C0h] [rbp-40h] BYREF

  ReassembledNetBufferList = 0;
  DataBackFill = dataBackFill;
  v7 = 0;
  NetBufferAndNetBufferListPoolHandle = netBufferAndNetBufferListPoolHandle;
  v8 = 0;
  v45 = addressFamily;
  v9 = fragmentGroupNblChain;
  v51 = 0;
  v54 = 0;
  v10 = addressFamily;
  v57 = reassembledNbl;
  v11 = 0;
  v44 = 0;
  v48 = 0;
  if ( _InterlockedAdd(&gFwpTcpIp, 1u) < 0 )
  {
    v12 = -1071513344;
LABEL_3:
    v13 = "FwpsReassembleForwardFragmentGroup0";
LABEL_4:
    v15 = WfpReportSysErrorAsNtStatus(addressFamily, (int)v13, v12);
    goto LABEL_58;
  }
  if ( addressFamily != 2 && addressFamily != 23 )
  {
    v12 = -1071513547;
    goto LABEL_3;
  }
  *(_QWORD *)&addressFamily = addressFamily != 2 ? 0x29 : 0;
  Size_4 = v10 != 2 ? 0x29 : 0;
  if ( !fragmentGroupNblChain || !reassembledNbl )
  {
    v12 = -1071513572;
    goto LABEL_3;
  }
  FirstNetBuffer = fragmentGroupNblChain->FirstNetBuffer;
  if ( !FirstNetBuffer )
  {
    v17 = -1071513572;
LABEL_13:
    v18 = "FwpsReassembleForwardFragmentGroup0";
LABEL_14:
    v15 = WfpReportSysErrorAsNtStatus(addressFamily, (int)v18, v17);
LABEL_15:
    ReassembledNetBufferList = 0;
    goto LABEL_58;
  }
  if ( flags )
  {
LABEL_17:
    v17 = -1071513547;
    goto LABEL_13;
  }
  if ( v10 == 2 )
  {
    DataBufferIfSafe = NetioGetDataBufferIfSafe(fragmentGroupNblChain->Link.Region, 20);
    v26 = DataBufferIfSafe;
    if ( !DataBufferIfSafe )
      goto LABEL_17;
    v11 = *(_OWORD *)DataBufferIfSafe;
    LODWORD(v54) = *(_DWORD *)(DataBufferIfSafe + 16);
    *(_WORD *)(DataBufferIfSafe + 6) = 0;
    if ( FirstNetBuffer->DataLength > 0xFFFF )
      goto LABEL_17;
    LOWORD(v24) = *((_WORD *)&FirstNetBuffer->NetBufferHeader.Link + 12);
    Size = 0;
    v53 = 0;
  }
  else
  {
    LOBYTE(dataBackFill) = 44;
    v49 = 0;
    v43[0] = 0;
    v19 = (*((__int64 (__fastcall **)(_QWORD, PNET_BUFFER, _QWORD, ULONG, _QWORD, _QWORD, char *, unsigned int *))qword_180048208
           + 5))(
            addressFamily,
            FirstNetBuffer,
            0,
            dataBackFill,
            0,
            0,
            v43,
            &v44);
    if ( v19 )
    {
LABEL_20:
      v17 = v19;
      v18 = "SkipNetworkLayerHeaders";
      goto LABEL_14;
    }
    v20 = v44;
    Size = v44;
    if ( v44 <= 0x80 )
    {
      v22 = Src;
    }
    else
    {
      v21 = WfpPoolAllocNonPaged(v44, 1886418758, &v48);
      v8 = v48;
      v15 = v21;
      if ( v21 )
        goto LABEL_15;
      v20 = v44;
      v22 = v48;
      Size = v44;
    }
    NetioRetreatNetBuffer(FirstNetBuffer, v20);
    RtlCopyMdlToKernelBuffer(FirstNetBuffer->MdlChain, FirstNetBuffer->DataOffset, v22, v44, &v49);
    v23 = FirstNetBuffer->CurrentMdlOffset + 8;
    if ( v23 >= *(_DWORD *)(FirstNetBuffer->Link.Region + 40) )
    {
      NdisAdvanceNetBufferDataStart(FirstNetBuffer, 8u, 0, 0);
    }
    else
    {
      FirstNetBuffer->DataOffset += 8;
      FirstNetBuffer->DataLength -= 8;
      FirstNetBuffer->CurrentMdlOffset = v23;
    }
    RtlCopyKernelBufferToMdl(v22, FirstNetBuffer->Link.Region, FirstNetBuffer->CurrentMdlOffset, v44 - 8, &v49);
    if ( (unsigned __int64)FirstNetBuffer->DataLength - 40 > 0xFFFF )
      goto LABEL_17;
    v24 = (unsigned __int16)(*((_WORD *)&FirstNetBuffer->NetBufferHeader.Link + 12) - 40);
    v53 = NetioGetDataBufferIfSafe(FirstNetBuffer, 40);
    *(_QWORD *)&addressFamily = v53;
    if ( !v53 )
      goto LABEL_17;
    FirstNetBuffer = 0;
    v26 = 0;
    *(_BYTE *)(v53 + 6) = v43[0];
  }
  Alignment = (_QWORD *)v9->Link.Alignment;
  v49 = v9->FirstNetBuffer;
  while ( 1 )
  {
    v52 = Alignment;
    if ( !Alignment )
      break;
    v29 = (struct _NET_BUFFER *)Alignment[1];
    LOBYTE(v25) = 44;
    v30 = (__int64 (__fastcall *)(_QWORD, struct _NET_BUFFER *, _QWORD, __int64, _QWORD, _QWORD, _QWORD, unsigned int *))*((_QWORD *)qword_180048208 + 5);
    v55 = v29;
    v19 = v30(Size_4, v29, 0, v25, 0, 0, 0, &v44);
    if ( v19 )
      goto LABEL_20;
    if ( v29->DataLength - 1 > 0xFFFE )
      goto LABEL_17;
    v31 = *((unsigned __int16 *)&v29->NetBufferHeader.Link + 12);
    v32 = (unsigned int)(0xFFFF - v31);
    if ( (unsigned __int16)v24 <= (int)v32 )
    {
      LOWORD(v24) = v31 + v24;
    }
    else
    {
      v33 = WfpReportSysErrorAsNtStatus(v32, (int)"WfpUINT16Add", -1073741675);
      v15 = v33;
      if ( v33 )
      {
        WfpReportError(v33, (int)"WfpUINT16Add");
        goto LABEL_15;
      }
      v29 = v55;
    }
    v29->ProtocolReserved[2] = (PVOID)v44;
    v34 = (SLIST_HEADER *)v49;
    v49 = v29;
    v34->Alignment = (ULONGLONG)v29;
    Alignment = (_QWORD *)*v52;
  }
  v35 = __ROR2__(v24, 8);
  if ( v45 == 2 )
  {
    *(_WORD *)(v26 + 2) = v35;
    *(_WORD *)(v26 + 10) = 0;
    (*((void (__fastcall **)(PNET_BUFFER))qword_180048208 + 6))(FirstNetBuffer);
  }
  else
  {
    *(_WORD *)(v53 + 4) = v35;
  }
  ReassembledNetBufferList = NdisAllocateReassembledNetBufferList(
                               v9,
                               NetBufferAndNetBufferListPoolHandle,
                               0,
                               0,
                               DataBackFill,
                               0);
  if ( !ReassembledNetBufferList )
  {
    v12 = -1073741801;
    v13 = "NdisAllocateReassembledNetBufferList";
    goto LABEL_4;
  }
  v36 = WfpAllocFromNPagedLookasideList(&gFwpNblInfo, &v51);
  v7 = v51;
  v15 = v36;
  if ( !v36 )
  {
    memset(v51, 0, 0x178u);
    v7[1] = 0;
    *((_QWORD *)v7 + 2) = v9;
    NetioReferenceNetBufferListChain(v9);
    v37 = v45 == 2;
    v7[6] = Size_4;
    if ( v37 )
    {
      v39 = v54;
      *((_OWORD *)v7 + 2) = v11;
      v7[12] = v39;
    }
    else
    {
      v38 = Size;
      if ( v8 )
      {
        *((_QWORD *)v7 + 20) = v8;
        v8 = 0;
        v48 = 0;
      }
      else
      {
        memmove(v7 + 8, Src, Size);
      }
      v7[42] = v38;
    }
    v15 = FwppSetPacketInfo(ReassembledNetBufferList, v7);
    if ( !v15 )
    {
      v7 = 0;
      *v57 = ReassembledNetBufferList;
      _InterlockedIncrement(&dword_180048700);
    }
  }
LABEL_58:
  _InterlockedDecrement(&gFwpTcpIp);
  if ( v15 )
  {
    if ( v7 )
      ExFreeToNPagedLookasideList(&gFwpNblInfo, v7);
    if ( ReassembledNetBufferList )
      NdisFreeReassembledNetBufferList(ReassembledNetBufferList, 0, 0);
  }
  if ( v8 )
    WfpNamedPoolFree(v14, &v48);
  while ( v9 )
  {
    v40 = v9->FirstNetBuffer;
    if ( v40->Link.Alignment )
      v40->Link.Alignment = 0;
    v41 = LODWORD(v40->ProtocolReserved[2]);
    v44 = v41;
    if ( (_DWORD)v41 )
    {
      NetioRetreatNetBuffer(v40, v41);
      v40->ProtocolReserved[2] = 0;
    }
    v9 = (NET_BUFFER_LIST *)v9->Link.Alignment;
  }
  return v15;
}

```

## disassembly

```asm
0x18001ce30  mov     rax, rsp
0x18001ce33  mov     [rax+8], rbx
0x18001ce37  push    rbp
0x18001ce38  push    rsi
0x18001ce39  push    rdi
0x18001ce3a  push    r12
0x18001ce3c  push    r13
0x18001ce3e  push    r14
0x18001ce40  push    r15
0x18001ce42  lea     rbp, [rsp-60h]
0x18001ce47  sub     rsp, 160h
0x18001ce4e  movaps  xmmword ptr [rax-48h], xmm6
0x18001ce52  mov     rax, cs:__security_cookie
0x18001ce59  xor     rax, rsp
0x18001ce5c  mov     [rbp+90h+var_50], rax
0x18001ce60  xor     esi, esi
0x18001ce62  mov     [rbp+90h+var_110], r9d
0x18001ce66  xor     edi, edi
0x18001ce68  mov     [rbp+90h+NetBufferAndNetBufferListPoolHandle], r8
0x18001ce6c  xor     r15d, r15d
0x18001ce6f  mov     [rsp+190h+var_138], cx
0x18001ce74  mov     r14, rdx
0x18001ce77  mov     [rbp+90h+var_108], rdi
0x18001ce7b  mov     rdx, [rbp+90h+reassembledNbl]
0x18001ce82  xor     eax, eax
0x18001ce84  mov     [rbp+90h+var_F0], rax
0x18001ce88  movzx   ebx, cx
0x18001ce8b  mov     [rbp+90h+var_D8], rdx
0x18001ce8f  xorps   xmm6, xmm6
0x18001ce92  mov     [rsp+190h+var_13C], esi
0x18001ce96  mov     [rsp+190h+var_120], r15
0x18001ce9b  lock add cs:gFwpTcpIp, 1
0x18001cea3  jns     short loc_18001CEBF
0x18001cea5  mov     r8d, 0C0220100h
0x18001ceab  lea     rdx, aFwpsreassemble; "FwpsReassembleForwardFragmentGroup0"
0x18001ceb2  call    WfpReportSysErrorAsNtStatus
0x18001ceb7  mov     rbx, rax
0x18001ceba  jmp     loc_18001D2E8
0x18001cebf  cmp     bx, 2
0x18001cec3  jz      short loc_18001CED3
0x18001cec5  cmp     bx, 17h
0x18001cec9  jz      short loc_18001CED3
0x18001cecb  mov     r8d, 0C0220035h
0x18001ced1  jmp     short loc_18001CEAB
0x18001ced3  lea     eax, [rbx-2]
0x18001ced6  neg     ax
0x18001ced9  sbb     ecx, ecx
0x18001cedb  and     ecx, 29h
0x18001cede  mov     dword ptr [rsp+190h+Size+4], ecx
0x18001cee2  test    r14, r14
0x18001cee5  jnz     short loc_18001CEEF
0x18001cee7  mov     r8d, 0C022001Ch
0x18001ceed  jmp     short loc_18001CEAB
0x18001ceef  test    rdx, rdx
0x18001cef2  jz      short loc_18001CEE7
0x18001cef4  mov     rsi, [r14+8]
0x18001cef8  test    rsi, rsi
0x18001cefb  jnz     short loc_18001CF1A
0x18001cefd  mov     r8d, 0C022001Ch
0x18001cf03  lea     rdx, aFwpsreassemble; "FwpsReassembleForwardFragmentGroup0"
0x18001cf0a  call    WfpReportSysErrorAsNtStatus
0x18001cf0f  mov     rbx, rax
0x18001cf12  mov     rsi, rdi
0x18001cf15  jmp     loc_18001D2E8
0x18001cf1a  cmp     [rbp+90h+flags], edi
0x18001cf20  jz      short loc_18001CF2A
0x18001cf22  mov     r8d, 0C0220035h
0x18001cf28  jmp     short loc_18001CF03
0x18001cf2a  cmp     bx, 2
0x18001cf2e  jz      loc_18001D09C
0x18001cf34  mov     rax, cs:qword_180048208
0x18001cf3b  lea     rdx, [rsp+190h+var_13C]
0x18001cf40  mov     [rsp+190h+var_158], rdx
0x18001cf45  mov     r9b, 2Ch ; ','
0x18001cf48  lea     rdx, [rsp+190h+var_140]
0x18001cf4d  mov     [rsp+190h+var_118], rdi
0x18001cf52  mov     [rsp+190h+var_160], rdx
0x18001cf57  xor     r8d, r8d
0x18001cf5a  mov     [rsp+190h+var_140], dil
0x18001cf5f  mov     rdx, rsi
0x18001cf62  mov     rax, [rax+28h]
0x18001cf66  mov     qword ptr [rsp+190h+AllocateReassembleFlags], rdi
0x18001cf6b  mov     qword ptr [rsp+190h+DataBackFill], rdi
0x18001cf70  call    _guard_dispatch_icall
0x18001cf75  test    eax, eax
0x18001cf77  jz      short loc_18001CF85
0x18001cf79  mov     r8d, eax
0x18001cf7c  lea     rdx, aSkipnetworklay; "SkipNetworkLayerHeaders"
0x18001cf83  jmp     short loc_18001CF0A
0x18001cf85  mov     ebx, [rsp+190h+var_13C]
0x18001cf89  mov     dword ptr [rsp+190h+Size], ebx
0x18001cf8d  cmp     ebx, 80h
0x18001cf93  jbe     short loc_18001CFC4
0x18001cf95  mov     ecx, ebx
0x18001cf97  lea     r8, [rsp+190h+var_120]
0x18001cf9c  mov     edx, 70707746h
0x18001cfa1  call    WfpPoolAllocNonPaged
0x18001cfa6  mov     r15, [rsp+190h+var_120]
0x18001cfab  mov     rbx, rax
0x18001cfae  test    rax, rax
0x18001cfb1  jnz     loc_18001CF12
0x18001cfb7  mov     ebx, [rsp+190h+var_13C]
0x18001cfbb  mov     r12, r15
0x18001cfbe  mov     dword ptr [rsp+190h+Size], ebx
0x18001cfc2  jmp     short loc_18001CFC8
0x18001cfc4  lea     r12, [rbp+90h+Src]
0x18001cfc8  mov     edx, ebx
0x18001cfca  mov     rcx, rsi
0x18001cfcd  call    NetioRetreatNetBuffer
0x18001cfd2  mov     r9d, [rsp+190h+var_13C]
0x18001cfd7  lea     rax, [rsp+190h+var_118]
0x18001cfdc  mov     edx, [rsi+28h]
0x18001cfdf  mov     r8, r12
0x18001cfe2  mov     rcx, [rsi+20h]
0x18001cfe6  mov     qword ptr [rsp+190h+DataBackFill], rax
0x18001cfeb  call    cs:__imp_RtlCopyMdlToKernelBuffer
0x18001cff2  nop     dword ptr [rax+rax+00h]
0x18001cff7  mov     rax, [rsi+8]
0x18001cffb  mov     ecx, [rsi+10h]
0x18001cffe  add     ecx, 8
0x18001d001  cmp     ecx, [rax+28h]
0x18001d004  jnb     short loc_18001D013
0x18001d006  add     dword ptr [rsi+28h], 8
0x18001d00a  add     dword ptr [rsi+18h], 0FFFFFFF8h
0x18001d00e  mov     [rsi+10h], ecx
0x18001d011  jmp     short loc_18001D02C
0x18001d013  xor     r9d, r9d; FreeMdlHandler
0x18001d016  xor     r8d, r8d; FreeMdl
0x18001d019  mov     rcx, rsi; NetBuffer
0x18001d01c  lea     edx, [r9+8]; DataOffsetDelta
0x18001d020  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x18001d027  nop     dword ptr [rax+rax+00h]
0x18001d02c  mov     r9d, [rsp+190h+var_13C]
0x18001d031  lea     rax, [rsp+190h+var_118]
0x18001d036  mov     r8d, [rsi+10h]
0x18001d03a  add     r9d, 0FFFFFFF8h
0x18001d03e  mov     rdx, [rsi+8]
0x18001d042  mov     rcx, r12
0x18001d045  mov     qword ptr [rsp+190h+DataBackFill], rax
0x18001d04a  call    cs:__imp_RtlCopyKernelBufferToMdl
0x18001d051  nop     dword ptr [rax+rax+00h]
0x18001d056  mov     eax, [rsi+18h]
0x18001d059  mov     edx, 28h ; '('
0x18001d05e  sub     rax, rdx
0x18001d061  cmp     rax, 0FFFFh
0x18001d067  ja      loc_18001CF22
0x18001d06d  movzx   r12d, word ptr [rsi+18h]
0x18001d072  mov     rcx, rsi
0x18001d075  sub     r12w, dx
0x18001d079  call    NetioGetDataBufferIfSafe
0x18001d07e  mov     [rbp+90h+var_F8], rax
0x18001d082  mov     rcx, rax
0x18001d085  test    rax, rax
0x18001d088  jz      loc_18001CF22
0x18001d08e  mov     al, [rsp+190h+var_140]
0x18001d092  xor     esi, esi
0x18001d094  xor     r13d, r13d
0x18001d097  mov     [rcx+6], al
0x18001d09a  jmp     short loc_18001D0DF
0x18001d09c  mov     edx, 14h
0x18001d0a1  mov     rcx, rsi
0x18001d0a4  call    NetioGetDataBufferIfSafe
0x18001d0a9  mov     r13, rax
0x18001d0ac  test    rax, rax
0x18001d0af  jz      loc_18001CF22
0x18001d0b5  movups  xmm6, xmmword ptr [rax]
0x18001d0b8  mov     eax, [rax+10h]
0x18001d0bb  mov     dword ptr [rbp+90h+var_F0], eax
0x18001d0be  xor     eax, eax
0x18001d0c0  mov     [r13+6], ax
0x18001d0c5  cmp     dword ptr [rsi+18h], 0FFFFh
0x18001d0cc  ja      loc_18001CF22
0x18001d0d2  movzx   r12d, word ptr [rsi+18h]
0x18001d0d7  mov     dword ptr [rsp+190h+Size], eax
0x18001d0db  mov     [rbp+90h+var_F8], rax
0x18001d0df  mov     rcx, [r14+8]
0x18001d0e3  mov     rax, [r14]
0x18001d0e6  mov     [rsp+190h+var_118], rcx
0x18001d0eb  mov     [rbp+90h+var_100], rax
0x18001d0ef  test    rax, rax
0x18001d0f2  jz      loc_18001D1BA
0x18001d0f8  mov     rbx, [rax+8]
0x18001d0fc  lea     rcx, [rsp+190h+var_13C]
0x18001d101  mov     rax, cs:qword_180048208
0x18001d108  mov     r9b, 2Ch ; ','
0x18001d10b  mov     [rsp+190h+var_158], rcx
0x18001d110  xor     r8d, r8d
0x18001d113  mov     ecx, dword ptr [rsp+190h+Size+4]
0x18001d117  mov     rdx, rbx
0x18001d11a  mov     [rsp+190h+var_160], rdi
0x18001d11f  mov     rax, [rax+28h]
0x18001d123  mov     qword ptr [rsp+190h+AllocateReassembleFlags], rdi
0x18001d128  mov     [rbp+90h+var_E8], rbx
0x18001d12c  mov     qword ptr [rsp+190h+DataBackFill], rdi
0x18001d131  call    _guard_dispatch_icall
0x18001d136  test    eax, eax
0x18001d138  jnz     loc_18001CF79
0x18001d13e  mov     eax, [rbx+18h]
0x18001d141  dec     eax
0x18001d143  cmp     eax, 0FFFEh
0x18001d148  ja      loc_18001CF22
0x18001d14e  movzx   edx, word ptr [rbx+18h]
0x18001d152  mov     ecx, 0FFFFh
0x18001d157  sub     ecx, edx
0x18001d159  movzx   eax, r12w
0x18001d15d  cmp     eax, ecx
0x18001d15f  jle     short loc_18001D181
0x18001d161  mov     r8d, 0C0000095h
0x18001d167  lea     rdx, aWfpuint16add; "WfpUINT16Add"
0x18001d16e  call    WfpReportSysErrorAsNtStatus
0x18001d173  mov     rbx, rax
0x18001d176  test    rax, rax
0x18001d179  jnz     short loc_18001D1A6
0x18001d17b  mov     rbx, [rbp+90h+var_E8]
0x18001d17f  jmp     short loc_18001D185
0x18001d181  add     r12w, dx
0x18001d185  mov     eax, [rsp+190h+var_13C]
0x18001d189  mov     [rbx+60h], rax
0x18001d18d  mov     rax, [rsp+190h+var_118]
0x18001d192  mov     [rsp+190h+var_118], rbx
0x18001d197  mov     [rax], rbx
0x18001d19a  mov     rax, [rbp+90h+var_100]
0x18001d19e  mov     rax, [rax]
0x18001d1a1  jmp     loc_18001D0EB
0x18001d1a6  lea     rdx, aWfpuint16add; "WfpUINT16Add"
0x18001d1ad  mov     rcx, rax
0x18001d1b0  call    WfpReportError
0x18001d1b5  jmp     loc_18001CF12
0x18001d1ba  ror     r12w, 8
0x18001d1bf  cmp     [rsp+190h+var_138], 2
0x18001d1c5  jz      short loc_18001D1D2
0x18001d1c7  mov     rax, [rbp+90h+var_F8]
0x18001d1cb  mov     [rax+4], r12w
0x18001d1d0  jmp     short loc_18001D1F1
0x18001d1d2  xor     eax, eax
0x18001d1d4  mov     [r13+2], r12w
0x18001d1d9  mov     [r13+0Ah], ax
0x18001d1de  mov     rcx, rsi
0x18001d1e1  mov     rax, cs:qword_180048208
0x18001d1e8  mov     rax, [rax+30h]
0x18001d1ec  call    _guard_dispatch_icall
0x18001d1f1  mov     eax, [rbp+90h+var_110]
0x18001d1f4  xor     r9d, r9d; DataOffsetDelta
0x18001d1f7  mov     rdx, [rbp+90h+NetBufferAndNetBufferListPoolHandle]; NetBufferAndNetBufferListPoolHandle
0x18001d1fb  xor     r8d, r8d; StartOffset
0x18001d1fe  mov     [rsp+190h+AllocateReassembleFlags], edi; AllocateReassembleFlags
0x18001d202  mov     rcx, r14; FragmentNetBufferList
0x18001d205  mov     [rsp+190h+DataBackFill], eax; DataBackFill
0x18001d209  call    cs:__imp_NdisAllocateReassembledNetBufferList
0x18001d210  nop     dword ptr [rax+rax+00h]
0x18001d215  mov     rsi, rax
0x18001d218  test    rax, rax
0x18001d21b  jnz     short loc_18001D22F
0x18001d21d  mov     r8d, 0C0000017h
0x18001d223  lea     rdx, aNdisallocatere; "NdisAllocateReassembledNetBufferList"
0x18001d22a  jmp     loc_18001CEB2
0x18001d22f  lea     rdx, [rbp+90h+var_108]
0x18001d233  lea     rcx, gFwpNblInfo
0x18001d23a  call    WfpAllocFromNPagedLookasideList
0x18001d23f  mov     rdi, [rbp+90h+var_108]
0x18001d243  mov     rbx, rax
0x18001d246  test    rax, rax
0x18001d249  jnz     loc_18001D2E8
0x18001d24f  xor     edx, edx; Val
0x18001d251  mov     r8d, 178h; Size
0x18001d257  mov     rcx, rdi; void *
0x18001d25a  call    memset
0x18001d25f  mov     [rdi+4], ebx
0x18001d262  mov     rcx, r14
0x18001d265  mov     [rdi+10h], r14
0x18001d269  call    cs:__imp_NetioReferenceNetBufferListChain
0x18001d270  nop     dword ptr [rax+rax+00h]
0x18001d275  cmp     [rsp+190h+var_138], 2
0x18001d27b  mov     eax, dword ptr [rsp+190h+Size+4]
0x18001d27f  mov     [rdi+18h], eax
0x18001d282  jz      short loc_18001D2BA
0x18001d284  test    r15, r15
0x18001d287  jz      short loc_18001D29E
0x18001d289  mov     ebx, dword ptr [rsp+190h+Size]
0x18001d28d  mov     [rdi+0A0h], r15
0x18001d294  xor     r15d, r15d
0x18001d297  mov     [rsp+190h+var_120], r15
0x18001d29c  jmp     short loc_18001D2B2
0x18001d29e  mov     ebx, dword ptr [rsp+190h+Size]
0x18001d2a2  lea     rcx, [rdi+20h]; void *
0x18001d2a6  mov     r8d, ebx; Size
0x18001d2a9  lea     rdx, [rbp+90h+Src]; Src
0x18001d2ad  call    memmove
0x18001d2b2  mov     [rdi+0A8h], ebx
0x18001d2b8  jmp     short loc_18001D2C5
0x18001d2ba  mov     rax, [rbp+90h+var_F0]
0x18001d2be  movups  xmmword ptr [rdi+20h], xmm6
0x18001d2c2  mov     [rdi+30h], eax
0x18001d2c5  mov     rdx, rdi
0x18001d2c8  mov     rcx, rsi
0x18001d2cb  call    FwppSetPacketInfo
0x18001d2d0  mov     rbx, rax
0x18001d2d3  test    rax, rax
0x18001d2d6  jnz     short loc_18001D2E8
0x18001d2d8  mov     rax, [rbp+90h+var_D8]
  ... truncated ...
```
