# CAdapter::CopyNetBufferLists(_NET_BUFFER_LIST *,_NET_BUFFER_LIST * *,ulong,bool)

- ea: `0x14006048c`
- end: `0x140060880`
- name: `?CopyNetBufferLists@CAdapter@@QEAAHPEAU_NET_BUFFER_LIST@@PEAPEAU2@K_N@Z`
- size: `1012`
- prototype: `__int64 __usercall@<rax>(CAdapter *__hidden this@<rcx>, PNET_BUFFER_LIST OriginalNetBufferList@<rdx>, struct _NET_BUFFER_LIST **@<r8>, unsigned int@<r9d>, bool)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140037f80`
- `0x140042b64`
- `0x14009c1f0`

## callees

- `0x1400174e8`
- `0x140034e04`
- `0x140034ec4`
- `0x14003e9f0`
- `0x140046674`
- `0x14006048c`

## import_xrefs

- `NDIS!NdisCopyFromNetBufferToNetBuffer` at `0x140060647`
- `NDIS!NdisCopyFromNetBufferToNetBuffer` at `0x140060647`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140060614`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140060614`
- `NDIS!NdisAllocateCloneNetBufferList` at `0x140060528`
- `NDIS!NdisAllocateCloneNetBufferList` at `0x140060528`

## pseudocode

```c
__int64 __fastcall CAdapter::CopyNetBufferLists(
        CAdapter *this,
        PNET_BUFFER_LIST OriginalNetBufferList,
        struct _NET_BUFFER_LIST **a3,
        ULONG a4,
        bool a5)
{
  int v7; // edx
  int v10; // ebx
  PNET_BUFFER_LIST *p_CloneNetBufferList; // rdi
  PNET_BUFFER_LIST v13; // rax
  PNET_BUFFER_LIST v14; // rsi
  PNET_BUFFER i; // rax
  PNET_BUFFER FirstNetBuffer; // rdi
  struct _NET_BUFFER *j; // r15
  NDIS_STATUS v18; // eax
  ULONG DataLength; // eax
  struct _WFC_FRAME *WfcFrame; // rax
  LIST_ENTRY *v21; // rcx
  int v22; // r9d
  int v23; // r9d
  PULONG BytesCopied; // [rsp+28h] [rbp-70h]
  PNET_BUFFER_LIST CloneNetBufferList; // [rsp+40h] [rbp-58h] BYREF
  ULONG v26; // [rsp+A8h] [rbp+10h] BYREF

  v7 = 0;
  CloneNetBufferList = 0;
  v10 = -1073741811;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v7) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      1,
      174,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
    v7 = 0;
  }
  p_CloneNetBufferList = &CloneNetBufferList;
LABEL_3:
  if ( !OriginalNetBufferList )
  {
    if ( v10 )
      goto LABEL_27;
    *a3 = CloneNetBufferList;
    goto LABEL_6;
  }
  v13 = NdisAllocateCloneNetBufferList(OriginalNetBufferList, 0, 0, 2u);
  v7 = 0;
  v14 = v13;
  if ( !v13 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v23 = 175;
      goto LABEL_46;
    }
LABEL_26:
    v10 = -1073741670;
    goto LABEL_27;
  }
  *p_CloneNetBufferList = v13;
  v13->MiniportReserved[0] = 0;
  for ( i = v13->FirstNetBuffer; i; i = (PNET_BUFFER)i->Link.Alignment )
  {
    i->Link.Region = 0;
    i->CurrentMdlOffset = 0;
    i->DataLength = 0;
    i->DataOffset = 0;
    i->MdlChain = 0;
  }
  FirstNetBuffer = OriginalNetBufferList->FirstNetBuffer;
  for ( j = v14->FirstNetBuffer; ; j = (struct _NET_BUFFER *)j->Link.Alignment )
  {
    if ( !FirstNetBuffer )
    {
      if ( !a5 )
      {
LABEL_15:
        OriginalNetBufferList = (PNET_BUFFER_LIST)OriginalNetBufferList->Link.Alignment;
        p_CloneNetBufferList = &v14->Next;
        goto LABEL_3;
      }
      WfcFrame = CAdapter::AllocateWfcFrame(this);
      v7 = (int)WfcFrame;
      if ( WfcFrame )
      {
        v21 = (LIST_ENTRY *)OriginalNetBufferList->MiniportReserved[0];
        *(LIST_ENTRY *)&WfcFrame->ulSizeOfThis = v21[-4];
        WfcFrame->u.Tx.FrameTableLink = v21[-3];
        *(LIST_ENTRY *)&WfcFrame->u.Rx.cbMSDUFragmentMPDUHeaderSize = v21[-2];
        *(LIST_ENTRY *)&WfcFrame->u.Rx.Rssi = v21[-1];
        WfcFrame->WiFiFrameMetadata.Linkage = *v21;
        *(LIST_ENTRY *)&WfcFrame->WiFiFrameMetadata.pNBL = v21[1];
        *(LIST_ENTRY *)&WfcFrame->WiFiFrameMetadata.u.txMetaData.PortID = v21[2];
        *((LIST_ENTRY *)&WfcFrame->WiFiFrameMetadata.u.rxMetaData + 1) = v21[3];
        *((LIST_ENTRY *)&WfcFrame->WiFiFrameMetadata.u.rxMetaData + 2) = v21[4];
        *((LIST_ENTRY *)&WfcFrame->WiFiFrameMetadata.u.rxMetaData + 3) = v21[5];
        v14->MiniportReserved[0] = &WfcFrame->WiFiFrameMetadata;
        WfcFrame->WiFiFrameMetadata.pNBL = v14;
        v7 = 0;
        goto LABEL_15;
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v23 = 179;
LABEL_46:
        LOBYTE(v7) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v7,
          1,
          v23,
          (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
        goto LABEL_26;
      }
      goto LABEL_26;
    }
    v26 = 0;
    v18 = NdisRetreatNetBufferDataStart(j, FirstNetBuffer->DataLength, a4, 0);
    v10 = v18;
    if ( v18 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_27;
      v22 = 176;
      goto LABEL_42;
    }
    v18 = NdisCopyFromNetBufferToNetBuffer(j, 0, FirstNetBuffer->DataLength, FirstNetBuffer, 0, &v26);
    v7 = 0;
    v10 = v18;
    if ( v18 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_27;
      v22 = 177;
LABEL_42:
      LODWORD(BytesCopied) = v18;
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        1,
        v22,
        (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
        BytesCopied);
      goto LABEL_27;
    }
    DataLength = FirstNetBuffer->DataLength;
    if ( v26 != DataLength )
      break;
    FirstNetBuffer = (PNET_BUFFER)FirstNetBuffer->Link.Alignment;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      1,
      178,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
      DataLength,
      v26);
  }
  v10 = -1073676267;
LABEL_27:
  CAdapter::FreeCopiedNetBufferLists(this, CloneNetBufferList);
  v7 = 0;
  *a3 = 0;
  if ( v10 > 0 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LODWORD(BytesCopied) = v10;
      LOBYTE(v7) = 4;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        1,
        180,
        (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
        BytesCopied);
      v7 = 0;
    }
    v10 = -1073741823;
  }
LABEL_6:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(BytesCopied) = v10;
    LOBYTE(v7) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      1,
      181,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
      BytesCopied);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14006048c  push    rbx
0x14006048e  push    rbp
0x14006048f  push    rsi
0x140060490  push    rdi
0x140060491  push    r12
0x140060493  push    r13
0x140060495  push    r14
0x140060497  push    r15
0x140060499  sub     rsp, 58h
0x14006049d  mov     r14, rdx
0x1400604a0  mov     r13d, r9d
0x1400604a3  xor     edx, edx
0x1400604a5  mov     rbp, r8
0x1400604a8  mov     [rsp+98h+CloneNetBufferList], rdx
0x1400604ad  mov     r12, rcx
0x1400604b0  mov     ebx, 0C000000Dh
0x1400604b5  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400604bc  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400604c3  lea     rsi, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x1400604ca  jnz     loc_140060591
0x1400604d0  lea     rdi, [rsp+98h+CloneNetBufferList]
0x1400604d5  test    r14, r14
0x1400604d8  jnz     short loc_14006051A
0x1400604da  lea     r15, WPP_RECORDER_INITIALIZED
0x1400604e1  lea     rsi, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x1400604e8  test    ebx, ebx
0x1400604ea  jnz     loc_14006069C
0x1400604f0  mov     rax, [rsp+98h+CloneNetBufferList]
0x1400604f5  mov     [rbp+0], rax
0x1400604f9  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140060500  jnz     loc_1400605C5
0x140060506  mov     eax, ebx
0x140060508  add     rsp, 58h
0x14006050c  pop     r15
0x14006050e  pop     r14
0x140060510  pop     r13
0x140060512  pop     r12
0x140060514  pop     rdi
0x140060515  pop     rsi
0x140060516  pop     rbp
0x140060517  pop     rbx
0x140060518  retn
0x14006051a  mov     r9d, 2; AllocateCloneFlags
0x140060520  xor     r8d, r8d; NetBufferPoolHandle
0x140060523  xor     edx, edx; NetBufferListPoolHandle
0x140060525  mov     rcx, r14; OriginalNetBufferList
0x140060528  call    cs:__imp_NdisAllocateCloneNetBufferList
0x14006052f  nop     dword ptr [rax+rax+00h]
0x140060534  xor     edx, edx
0x140060536  mov     rsi, rax
0x140060539  test    rax, rax
0x14006053c  jz      loc_14006067C
0x140060542  mov     [rdi], rax
0x140060545  mov     [rax+60h], rdx
0x140060549  mov     rax, [rax+8]
0x14006054d  jmp     short loc_140060563
0x14006054f  mov     [rax+8], rdx
0x140060553  mov     [rax+10h], edx
0x140060556  mov     [rax+18h], edx
0x140060559  mov     [rax+28h], edx
0x14006055c  mov     [rax+20h], rdx
0x140060560  mov     rax, [rax]
0x140060563  test    rax, rax
0x140060566  jnz     short loc_14006054F
0x140060568  mov     rdi, [r14+8]
0x14006056c  mov     r15, [rsi+8]
0x140060570  test    rdi, rdi
0x140060573  jnz     loc_140060601
0x140060579  cmp     [rsp+98h+arg_20], dl
0x140060580  jnz     loc_140060700
0x140060586  mov     r14, [r14]
0x140060589  mov     rdi, rsi
0x14006058c  jmp     loc_1400604D5
0x140060591  mov     rcx, cs:WPP_GLOBAL_Control
0x140060598  cmp     byte ptr [rcx+29h], 5
0x14006059c  jb      loc_1400606F1
0x1400605a2  mov     rcx, [rcx+40h]
0x1400605a6  mov     r9d, 0AEh
0x1400605ac  mov     r8d, 1
0x1400605b2  mov     qword ptr [rsp+98h+SourceOffset], rsi
0x1400605b7  mov     dl, 5
0x1400605b9  call    WPP_RECORDER_SF_
0x1400605be  xor     edx, edx
0x1400605c0  jmp     loc_1400604D0
0x1400605c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400605cc  cmp     byte ptr [rcx+29h], 5
0x1400605d0  jnb     short loc_1400605DC
0x1400605d2  cmp     [rcx+48h], dx
0x1400605d6  jz      loc_140060506
0x1400605dc  mov     rcx, [rcx+40h]
0x1400605e0  mov     r9d, 0B5h
0x1400605e6  mov     dword ptr [rsp+98h+BytesCopied], ebx
0x1400605ea  mov     r8d, 1
0x1400605f0  mov     dl, 5
0x1400605f2  mov     qword ptr [rsp+98h+SourceOffset], rsi
0x1400605f7  call    WPP_RECORDER_SF_D
0x1400605fc  jmp     loc_140060506
0x140060601  mov     [rsp+98h+arg_8], edx
0x140060608  xor     r9d, r9d; AllocateMdlHandler
0x14006060b  mov     edx, [rdi+18h]; DataOffsetDelta
0x14006060e  mov     r8d, r13d; DataBackFill
0x140060611  mov     rcx, r15; NetBuffer
0x140060614  call    cs:__imp_NdisRetreatNetBufferDataStart
0x14006061b  nop     dword ptr [rax+rax+00h]
0x140060620  mov     ebx, eax
0x140060622  test    eax, eax
0x140060624  jnz     loc_1400607EE
0x14006062a  mov     r8d, [rdi+18h]; BytesToCopy
0x14006062e  lea     rax, [rsp+98h+arg_8]
0x140060636  mov     [rsp+98h+BytesCopied], rax; BytesCopied
0x14006063b  mov     r9, rdi; Source
0x14006063e  xor     edx, edx; DestinationOffset
0x140060640  mov     [rsp+98h+SourceOffset], ebx; SourceOffset
0x140060644  mov     rcx, r15; Destination
0x140060647  call    cs:__imp_NdisCopyFromNetBufferToNetBuffer
0x14006064e  nop     dword ptr [rax+rax+00h]
0x140060653  xor     edx, edx
0x140060655  mov     ebx, eax
0x140060657  test    eax, eax
0x140060659  jnz     loc_1400607CB
0x14006065f  mov     eax, [rdi+18h]
0x140060662  mov     ecx, [rsp+98h+arg_8]
0x140060669  cmp     ecx, eax
0x14006066b  jnz     loc_14006077F
0x140060671  mov     rdi, [rdi]
0x140060674  mov     r15, [r15]
0x140060677  jmp     loc_140060570
0x14006067c  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140060683  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14006068a  lea     rsi, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x140060691  jnz     loc_140060858
0x140060697  mov     ebx, 0C000009Ah
0x14006069c  mov     rdx, [rsp+98h+CloneNetBufferList]; CloneNetBufferList
0x1400606a1  mov     rcx, r12; this
0x1400606a4  call    ?FreeCopiedNetBufferLists@CAdapter@@QEAAXPEAU_NET_BUFFER_LIST@@@Z; CAdapter::FreeCopiedNetBufferLists(_NET_BUFFER_LIST *)
0x1400606a9  xor     edx, edx
0x1400606ab  mov     [rbp+0], rdx
0x1400606af  test    ebx, ebx
0x1400606b1  jle     loc_1400604F9
0x1400606b7  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400606be  jz      short loc_1400606E7
0x1400606c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400606c7  lea     r8d, [rdx+1]
0x1400606cb  mov     r9d, 0B4h
0x1400606d1  mov     dword ptr [rsp+98h+BytesCopied], ebx
0x1400606d5  mov     dl, 4
0x1400606d7  mov     qword ptr [rsp+98h+SourceOffset], rsi
0x1400606dc  mov     rcx, [rcx+40h]
0x1400606e0  call    WPP_RECORDER_SF_D
0x1400606e5  xor     edx, edx
0x1400606e7  mov     ebx, 0C0000001h
0x1400606ec  jmp     loc_1400604F9
0x1400606f1  cmp     [rcx+48h], dx
0x1400606f5  jz      loc_1400604D0
0x1400606fb  jmp     loc_1400605A2
0x140060700  mov     rcx, r12; this
0x140060703  call    ?AllocateWfcFrame@CAdapter@@QEAAPEAU_WFC_FRAME@@XZ; CAdapter::AllocateWfcFrame(void)
0x140060708  mov     rdx, rax
0x14006070b  test    rax, rax
0x14006070e  jz      loc_140060835
0x140060714  mov     rcx, [r14+60h]
0x140060718  movups  xmm0, xmmword ptr [rcx-40h]
0x14006071c  movups  xmmword ptr [rax], xmm0
0x14006071f  movups  xmm1, xmmword ptr [rcx-30h]
0x140060723  movups  xmmword ptr [rax+10h], xmm1
0x140060727  movups  xmm0, xmmword ptr [rcx-20h]
0x14006072b  movups  xmmword ptr [rax+20h], xmm0
0x14006072f  movups  xmm1, xmmword ptr [rcx-10h]
0x140060733  movups  xmmword ptr [rax+30h], xmm1
0x140060737  movups  xmm0, xmmword ptr [rcx]
0x14006073a  movups  xmmword ptr [rax+40h], xmm0
0x14006073e  movups  xmm1, xmmword ptr [rcx+10h]
0x140060742  movups  xmmword ptr [rax+50h], xmm1
0x140060746  movups  xmm0, xmmword ptr [rcx+20h]
0x14006074a  movups  xmmword ptr [rax+60h], xmm0
0x14006074e  movups  xmm1, xmmword ptr [rcx+30h]
0x140060752  movups  xmmword ptr [rax+70h], xmm1
0x140060756  movups  xmm0, xmmword ptr [rcx+40h]
0x14006075a  movups  xmmword ptr [rax+80h], xmm0
0x140060761  movups  xmm1, xmmword ptr [rcx+50h]
0x140060765  movups  xmmword ptr [rax+90h], xmm1
0x14006076c  add     rax, 40h ; '@'
0x140060770  mov     [rsi+60h], rax
0x140060774  mov     [rdx+50h], rsi
0x140060778  xor     edx, edx
0x14006077a  jmp     loc_140060586
0x14006077f  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140060786  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14006078d  lea     rsi, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x140060794  jz      short loc_1400607C1
0x140060796  mov     [rsp+98h+var_68], ecx
0x14006079a  mov     r9d, 0B2h
0x1400607a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400607a7  mov     r8d, 1
0x1400607ad  mov     dword ptr [rsp+98h+BytesCopied], eax
0x1400607b1  mov     dl, 2
0x1400607b3  mov     qword ptr [rsp+98h+SourceOffset], rsi
0x1400607b8  mov     rcx, [rcx+40h]
0x1400607bc  call    WPP_RECORDER_SF_DD
0x1400607c1  mov     ebx, 0C0010015h
0x1400607c6  jmp     loc_14006069C
0x1400607cb  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400607d2  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400607d9  lea     rsi, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x1400607e0  jz      loc_14006069C
0x1400607e6  mov     r9d, 0B1h
0x1400607ec  jmp     short loc_14006080F
0x1400607ee  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400607f5  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400607fc  lea     rsi, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x140060803  jz      loc_14006069C
0x140060809  mov     r9d, 0B0h
0x14006080f  mov     rcx, cs:WPP_GLOBAL_Control
0x140060816  mov     r8d, 1
0x14006081c  mov     dword ptr [rsp+98h+BytesCopied], eax
0x140060820  mov     dl, 2
0x140060822  mov     qword ptr [rsp+98h+SourceOffset], rsi
0x140060827  mov     rcx, [rcx+40h]
0x14006082b  call    WPP_RECORDER_SF_D
0x140060830  jmp     loc_14006069C
0x140060835  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14006083c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140060843  lea     rsi, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x14006084a  jz      loc_140060697
0x140060850  mov     r9d, 0B3h
0x140060856  jmp     short loc_14006085E
0x140060858  mov     r9d, 0AFh
0x14006085e  mov     rcx, cs:WPP_GLOBAL_Control
0x140060865  mov     r8d, 1
0x14006086b  mov     dl, 2
0x14006086d  mov     qword ptr [rsp+98h+SourceOffset], rsi
0x140060872  mov     rcx, [rcx+40h]
0x140060876  call    WPP_RECORDER_SF_
0x14006087b  jmp     loc_140060697
```
