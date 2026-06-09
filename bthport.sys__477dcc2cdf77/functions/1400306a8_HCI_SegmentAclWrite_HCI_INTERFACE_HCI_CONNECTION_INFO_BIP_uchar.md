# HCI_SegmentAclWrite(HCI_INTERFACE *,_HCI_CONNECTION_INFO *,_BIP *,uchar)

- ea: `0x1400306a8`
- end: `0x140030f0e`
- name: `?HCI_SegmentAclWrite@@YAJPEAUHCI_INTERFACE@@PEAU_HCI_CONNECTION_INFO@@PEAU_BIP@@E@Z`
- size: `2150`
- prototype: `__int64 __fastcall(struct HCI_INTERFACE *, struct _HCI_CONNECTION_INFO *, struct _BIP *, unsigned __int8)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140031b50`

## callees

- `0x140005608`
- `0x140005690`
- `0x140005748`
- `0x14000ac4c`
- `0x1400278d8`
- `0x14002e1b0`
- `0x1400306a8`
- `0x1400321d0`
- `0x1400325ac`
- `0x140161a44`
- `0x140162b70`
- `0x140165940`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140030e67`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140030e67`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140030b18`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140030b18`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140030e4d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140030e4d`

## string_xrefs

- `0x140030ca1`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\hciaclwrite.cpp`

## pseudocode

```c
__int64 __fastcall HCI_SegmentAclWrite(_LIST_ENTRY *a1, struct _HCI_CONNECTION_INFO *a2, struct _BIP *a3, char a4)
{
  struct _BIP *v4; // r13
  struct _HCI_CONNECTION_INFO *v5; // rbx
  char v7; // di
  __int16 DeviceType; // ax
  _HCI_PHY_TYPE PhyType; // al
  unsigned int Flink_low; // ecx
  PDEVICE_OBJECT v11; // rcx
  __int16 v12; // ax
  int v13; // ebx
  RECORDER_LOG__ *Flink; // r9
  unsigned int v15; // r8d
  int v16; // edx
  unsigned int v17; // r15d
  RECORDER_LOG__ **v18; // r12
  _LIST_ENTRY *Blink; // rcx
  _LIST_ENTRY *v20; // rax
  _LIST_ENTRY *v21; // rcx
  struct _LIST_ENTRY *v22; // rdx
  __int64 *v23; // r8
  __int16 v24; // ax
  _QWORD *Context; // rsi
  DEVICE_EXTENSION *v26; // rcx
  unsigned __int8 v27; // al
  __int64 *v28; // r8
  __int16 v29; // ax
  unsigned int v30; // r12d
  __int64 v31; // r9
  _LIST_ENTRY **p_Blink; // rsi
  _LIST_ENTRY *v33; // rax
  _LIST_ENTRY *v34; // rcx
  _LIST_ENTRY *v35; // rax
  _LIST_ENTRY *v36; // rsi
  _LIST_ENTRY *v37; // rax
  unsigned int v38; // eax
  unsigned int v39; // edx
  __int64 *BufferData; // rcx
  _LIST_ENTRY *v41; // r15
  int v42; // edx
  int v43; // r8d
  int v44; // r12d
  unsigned __int16 ConnectionHandle; // ax
  _LIST_ENTRY *v46; // rax
  int v47; // ecx
  _QWORD *v48; // rsi
  int v49; // edx
  int v50; // r8d
  PDEVICE_OBJECT v51; // rcx
  __int16 v52; // r10
  _LIST_ENTRY **v53; // rax
  _LIST_ENTRY *v54; // rax
  _LIST_ENTRY *v55; // rax
  _LIST_ENTRY *v56; // rcx
  _LIST_ENTRY **v57; // rsi
  _LIST_ENTRY *v58; // rdx
  __int16 v59; // ax
  __int16 v61; // [rsp+38h] [rbp-39h]
  char v62; // [rsp+48h] [rbp-29h]
  unsigned int DataLen; // [rsp+68h] [rbp-9h]
  unsigned int v64; // [rsp+6Ch] [rbp-5h]
  unsigned int v65; // [rsp+70h] [rbp-1h]
  int v66; // [rsp+74h] [rbp+3h] BYREF
  _QWORD *v67; // [rsp+78h] [rbp+7h]
  _LIST_ENTRY *v68; // [rsp+80h] [rbp+Fh]
  struct _LIST_ENTRY v69; // [rsp+88h] [rbp+17h] BYREF
  struct _HCI_CONNECTION_INFO *v70; // [rsp+E0h] [rbp+6Fh]
  char v71; // [rsp+E8h] [rbp+77h]

  v70 = a2;
  v4 = a3;
  v69 = 0;
  v5 = a2;
  v7 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    LOBYTE(a2) = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( (_BYTE)a2 || DeviceType )
  {
    LOBYTE(a3) = DeviceType != 0;
    WPP_RECORDER_AND_TRACE_SF_qDq(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      (_DWORD)a3,
      a1[267].Flink,
      5,
      2,
      20,
      (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids,
      (char)a1,
      v5->ConnectionHandle,
      (char)v4);
  }
  v69.Blink = &v69;
  v69.Flink = &v69;
  PhyType = v5->PhyType;
  if ( PhyType )
  {
    if ( PhyType != HciPhyTypeLE )
    {
      v13 = -1073741808;
      goto LABEL_92;
    }
    Flink_low = LOWORD(a1[218].Flink);
  }
  else
  {
    Flink_low = (unsigned int)a1[120].Blink;
  }
  v64 = Flink_low;
  if ( !Flink_low )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(a2) = 0;
    LOBYTE(a3) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      (_DWORD)a3,
      a1[267].Flink,
      2,
      2,
      21,
      (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids);
    v11 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
      LOBYTE(a2) = 0;
    v12 = WPP_GLOBAL_Control->DeviceType;
    v13 = -1073741808;
    LOBYTE(a3) = v12 != 0;
    if ( !(_BYTE)a2 && !v12 )
      goto LABEL_92;
    Flink = (RECORDER_LOG__ *)a1[267].Flink;
    v62 = 16;
    v61 = 22;
LABEL_21:
    WPP_RECORDER_AND_TRACE_SF_d(
      v11->AttachedDevice,
      (_DWORD)a2,
      (_DWORD)a3,
      (_DWORD)Flink,
      5,
      2,
      v61,
      (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids,
      v62);
    goto LABEL_92;
  }
  DataLen = v4->DataLen;
  v15 = DataLen;
  v16 = DataLen % Flink_low;
  v17 = DataLen / Flink_low + 1;
  if ( !(DataLen % Flink_low) )
    v17 = DataLen / Flink_low;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v16) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
    LOBYTE(v16) = 0;
  v18 = (RECORDER_LOG__ **)&a1[267];
  LOBYTE(v15) = 1;
  WPP_RECORDER_AND_TRACE_SF_LL(
    WPP_GLOBAL_Control->AttachedDevice,
    v16,
    v15,
    a1[267].Flink,
    4,
    2,
    23,
    (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids,
    DataLen,
    v17);
  Blink = v69.Blink;
  if ( v69.Blink->Flink != &v69
    || (v4->ListEntry.Blink = v69.Blink,
        v4->ListEntry.Flink = &v69,
        Blink->Flink = &v4->ListEntry,
        v69.Blink = &v4->ListEntry,
        v13 = HCI_AllocateBipContexts(&v69, DATA_PKT_W, 1u, 0, 1),
        v20 = v69.Flink,
        v69.Flink->Blink != &v69)
    || (v21 = v69.Flink->Flink, v69.Flink->Flink->Blink != v69.Flink) )
  {
LABEL_98:
    __fastfail(3u);
  }
  v69.Flink = v69.Flink->Flink;
  v22 = &v69;
  v21->Blink = &v69;
  v20->Blink = v20;
  v20->Flink = v20;
  if ( v13 < 0 )
  {
    LOBYTE(v22) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    v23 = WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids;
    LOBYTE(v23) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v22,
      (_DWORD)v23,
      (unsigned int)*v18,
      2,
      2,
      24,
      (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids);
    v11 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
      LOBYTE(a2) = 0;
    v24 = WPP_GLOBAL_Control->DeviceType;
    v13 = -1073741670;
    LOBYTE(a3) = v24 != 0;
    if ( !(_BYTE)a2 && !v24 )
      goto LABEL_92;
    v62 = -102;
    v61 = 25;
    goto LABEL_41;
  }
  Context = v4->PacketContexts[1].Context;
  Context[2] = a1;
  *((_BYTE *)Context + 104) = a4;
  v26 = (DEVICE_EXTENSION *)a1[74].Blink;
  v67 = Context;
  v27 = HCI_AllocateBips(&v26->BtDevice, &v69, DATA_PKT_W, v17, 0, 0);
  LODWORD(a2) = 0;
  if ( v27 )
  {
    v30 = 0;
    v31 = DataLen;
    Context[3] = v69.Flink[4].Flink;
    p_Blink = &v69.Flink[-6].Blink;
    while ( v30 < v17 )
    {
      *p_Blink = (_LIST_ENTRY *)v4->BtDevice;
      *((_DWORD *)p_Blink + 2) = v4->Type;
      *((_DWORD *)p_Blink + 3) = v4->Status;
      *((_OWORD *)p_Blink + 1) = v4->TrackIrpActivity;
      if ( (v4->Flags & 0x10) != 0 )
        *((_DWORD *)p_Blink + 9) |= 0x10u;
      if ( (v4->Flags & 0x20) != 0 )
        *((_DWORD *)p_Blink + 9) |= 0x20u;
      v33 = (_LIST_ENTRY *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&a1[160]);
      p_Blink[5] = v33;
      if ( !v33 )
      {
        v13 = -1073741670;
        goto LABEL_92;
      }
      memset(v33, 0, v64 + 4);
      v34 = p_Blink[5];
      LODWORD(a2) = 0;
      v31 = DataLen;
      *((_DWORD *)p_Blink + 12) = 0;
      WORD1(v34->Flink) = 0;
      v35 = p_Blink[19];
      v35->Flink = (_LIST_ENTRY *)p_Blink;
      HIDWORD(v35[2].Flink) = v30;
      LODWORD(v35[2].Flink) = DataLen;
      v35->Blink = (_LIST_ENTRY *)v4;
      LODWORD(v35[2].Blink) = v17;
      v35[1].Flink = a1;
      LOBYTE(v35[6].Blink) = a4;
      p_Blink = &p_Blink[11][-6].Blink;
      ++v30;
    }
    v71 = 1;
    *((_DWORD *)v67 + 10) = v17;
    while ( 1 )
    {
      if ( !(_DWORD)v31 )
        goto LABEL_99;
      v36 = v69.Flink;
      if ( v69.Flink->Blink != &v69 )
        goto LABEL_98;
      v37 = v69.Flink->Flink;
      if ( v69.Flink->Flink->Blink != v69.Flink )
        goto LABEL_98;
      v69.Flink = v69.Flink->Flink;
      v37->Blink = &v69;
      v38 = v64;
      v36->Blink = v36;
      v36->Flink = v36;
      if ( (unsigned int)v31 < v64 )
        v38 = v31;
      v68 = v36[4].Flink;
      LODWORD(v36[-3].Blink) = 4;
      v39 = v4->DataLen - v31;
      BufferData = (__int64 *)v4->BufferData;
      v66 = 0;
      v41 = v36[-3].Flink;
      v65 = v38;
      v13 = BthCopyMdlChainToBuffer(BufferData, v39, (char *)&v41->Flink + 4, v31, v38, &v66);
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
        goto LABEL_71;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        LOBYTE(v42) = 1;
      else
LABEL_71:
        LOBYTE(v42) = 0;
      LOBYTE(v43) = 1;
      v44 = v66;
      WPP_RECORDER_AND_TRACE_SF_DDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        v42,
        v43,
        a1[267].Flink,
        4,
        2,
        28,
        (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids,
        v65,
        v66,
        v4->DataLen,
        v13);
      if ( v13 < 0 && v44 != v65 )
        break;
      ConnectionHandle = v70->ConnectionHandle;
      WORD1(v41->Flink) += v65;
      LOWORD(v41->Flink) = ConnectionHandle;
      v46 = v36[-3].Flink;
      LODWORD(v36[-3].Blink) += v65;
      v47 = (int)v36[-3].Blink;
      v36[7].Flink = v46;
      LODWORD(v36[7].Blink) = v47;
      v36[3].Blink = (_LIST_ENTRY *)HCI_AclWriteSegmentComplete;
      v36[-2].Flink = 0;
      v48 = v67;
      RefObj_AddRefEx(v67 + 9, v67, 657, "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciaclwrite.cpp");
      if ( v71 )
      {
        if ( !BYTE4(a1[208].Blink) || (v4->Flags & 8) != 0 )
          LOWORD(v41->Flink) |= 0x2000u;
        v71 = 0;
        v51 = WPP_GLOBAL_Control;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v49) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
          LOBYTE(v49) = 0;
        v52 = 29;
      }
      else
      {
        LOWORD(v41->Flink) |= 0x1000u;
        v51 = WPP_GLOBAL_Control;
        LOBYTE(v49) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        v52 = 30;
      }
      LOBYTE(v50) = 1;
      WPP_RECORDER_AND_TRACE_SF_(
        v51->AttachedDevice,
        v49,
        v50,
        a1[267].Flink,
        4,
        2,
        v52,
        (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids);
      a2 = (struct _HCI_CONNECTION_INFO *)v48[8];
      if ( *(_QWORD **)&a2->State != v48 + 7 )
        goto LABEL_98;
      v13 = 0;
      v31 = DataLen - v65;
      v53 = &v68[3].Blink;
      DataLen -= v65;
      v68[3].Blink = (_LIST_ENTRY *)(v48 + 7);
      v53[1] = (_LIST_ENTRY *)a2;
      *(_QWORD *)&a2->State = v53;
      v48[8] = v53;
    }
    v54 = v69.Flink;
    if ( v69.Flink->Blink == &v69 )
    {
      v36->Flink = v69.Flink;
      v36->Blink = &v69;
      v54->Blink = v36;
      v69.Flink = v36;
      goto LABEL_92;
    }
    goto LABEL_98;
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    LOBYTE(a2) = 1;
  v28 = WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids;
  LOBYTE(v28) = 1;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    (_DWORD)a2,
    (_DWORD)v28,
    (unsigned int)*v18,
    2,
    2,
    26,
    (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids);
  v11 = WPP_GLOBAL_Control;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    LOBYTE(a2) = 0;
  v29 = WPP_GLOBAL_Control->DeviceType;
  v13 = -1073741670;
  LOBYTE(a3) = v29 != 0;
  if ( (_BYTE)a2 || v29 )
  {
    v62 = -102;
    v61 = 27;
LABEL_41:
    Flink = *v18;
    goto LABEL_21;
  }
LABEL_92:
  while ( 1 )
  {
    v55 = v69.Flink;
    if ( v69.Flink == &v69 )
      break;
    if ( v69.Flink->Blink != &v69 )
      goto LABEL_98;
    v56 = v69.Flink->Flink;
    if ( v69.Flink->Flink->Blink != v69.Flink )
      goto LABEL_98;
    v69.Flink = v69.Flink->Flink;
    v57 = &v55[-6].Blink;
    v56->Blink = &v69;
    v58 = v55[-3].Flink;
    if ( v58 )
    {
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&a1[160], v58);
      v57[5] = 0;
    }
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)&(*v57)[7], v57);
  }
LABEL_99:
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v7 = 0;
  v59 = WPP_GLOBAL_Control->DeviceType;
  if ( v7 || v59 )
  {
    LOBYTE(a2) = v7;
    LOBYTE(a3) = v59 != 0;
    WPP_RECORDER_AND_TRACE_SF_DqD(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      (_DWORD)a3,
      a1[267].Flink,
      5,
      2,
      31,
      (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids,
      v70->ConnectionHandle,
      (char)v4,
      v13);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400306a8  mov     rax, rsp
0x1400306ab  mov     [rax+8], rbx
0x1400306af  mov     [rax+20h], r9b
0x1400306b3  mov     [rax+10h], rdx
0x1400306b7  push    rbp
0x1400306b8  push    rsi
0x1400306b9  push    rdi
0x1400306ba  push    r12
0x1400306bc  push    r13
0x1400306be  push    r14
0x1400306c0  push    r15
0x1400306c2  lea     rbp, [rax-5Fh]
0x1400306c6  sub     rsp, 90h
0x1400306cd  xorps   xmm0, xmm0
0x1400306d0  mov     r13, r8
0x1400306d3  movups  xmmword ptr [rbp+57h+var_40.Flink], xmm0
0x1400306d7  mov     rbx, rdx
0x1400306da  mov     r14, rcx
0x1400306dd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400306e4  xor     r15d, r15d
0x1400306e7  mov     eax, [rcx+2Ch]
0x1400306ea  lea     edi, [r15+1]
0x1400306ee  lea     esi, [rdi+1]
0x1400306f1  test    sil, al
0x1400306f4  jz      short loc_1400306FF
0x1400306f6  cmp     byte ptr [rcx+29h], 5
0x1400306fa  mov     dl, dil
0x1400306fd  jnb     short loc_140030702
0x1400306ff  mov     dl, r15b
0x140030702  movzx   eax, word ptr [rcx+48h]
0x140030706  lea     r10, WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids
0x14003070d  test    ax, ax
0x140030710  setnz   r8b
0x140030714  test    dl, dl
0x140030716  jnz     short loc_14003071D
0x140030718  test    ax, ax
0x14003071b  jz      short loc_14003075B
0x14003071d  movzx   eax, word ptr [rbx+28h]
0x140030721  mov     r9, [r14+10B0h]
0x140030728  mov     rcx, [rcx+18h]
0x14003072c  mov     qword ptr [rsp+0C0h+var_70], r13
0x140030731  mov     dword ptr [rsp+0C0h+var_78], eax
0x140030735  mov     [rsp+0C0h+var_80], r14
0x14003073a  mov     [rsp+0C0h+var_88], r10
0x14003073f  mov     word ptr [rsp+0C0h+var_90], 14h
0x140030746  mov     dword ptr [rsp+0C0h+var_98], esi
0x14003074a  mov     [rsp+0C0h+var_A0], 5
0x14003074f  call    WPP_RECORDER_AND_TRACE_SF_qDq
0x140030754  lea     r10, WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids
0x14003075b  lea     rax, [rbp+57h+var_40]
0x14003075f  mov     [rbp+57h+var_40.Blink], rax
0x140030763  lea     rax, [rbp+57h+var_40]
0x140030767  mov     [rbp+57h+var_40.Flink], rax
0x14003076b  mov     al, [rbx+8]
0x14003076e  test    al, al
0x140030770  jnz     short loc_14003077B
0x140030772  mov     ecx, [r14+788h]
0x140030779  jmp     short loc_14003078C
0x14003077b  cmp     al, dil
0x14003077e  jnz     loc_140030E08
0x140030784  movzx   ecx, word ptr [r14+0DA0h]
0x14003078c  mov     [rbp+57h+var_5C], ecx
0x14003078f  test    ecx, ecx
0x140030791  jnz     loc_140030847
0x140030797  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003079e  mov     eax, [rcx+2Ch]
0x1400307a1  test    sil, al
0x1400307a4  jz      short loc_1400307AF
0x1400307a6  mov     dl, dil
0x1400307a9  cmp     [rcx+29h], sil
0x1400307ad  jnb     short loc_1400307B2
0x1400307af  mov     dl, r15b
0x1400307b2  mov     r9, [r14+10B0h]
0x1400307b9  mov     r8b, dil
0x1400307bc  mov     rcx, [rcx+18h]
0x1400307c0  mov     [rsp+0C0h+var_88], r10
0x1400307c5  mov     word ptr [rsp+0C0h+var_90], 15h
0x1400307cc  mov     dword ptr [rsp+0C0h+var_98], esi
0x1400307d0  mov     [rsp+0C0h+var_A0], sil
0x1400307d5  call    WPP_RECORDER_AND_TRACE_SF_
0x1400307da  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400307e1  mov     eax, [rcx+2Ch]
0x1400307e4  test    sil, al
0x1400307e7  jz      short loc_1400307F2
0x1400307e9  cmp     byte ptr [rcx+29h], 5
0x1400307ed  mov     dl, dil
0x1400307f0  jnb     short loc_1400307F5
0x1400307f2  mov     dl, r15b
0x1400307f5  movzx   eax, word ptr [rcx+48h]
0x1400307f9  mov     ebx, 0C0000010h
0x1400307fe  test    ax, ax
0x140030801  setnz   r8b
0x140030805  test    dl, dl
0x140030807  jnz     short loc_140030812
0x140030809  test    ax, ax
0x14003080c  jz      loc_140030E0D
0x140030812  mov     r9, [r14+10B0h]
0x140030819  lea     r11, WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids
0x140030820  mov     dword ptr [rsp+0C0h+var_80], ebx
0x140030824  mov     [rsp+0C0h+var_88], r11
0x140030829  mov     word ptr [rsp+0C0h+var_90], 16h
0x140030830  mov     rcx, [rcx+18h]
0x140030834  mov     dword ptr [rsp+0C0h+var_98], esi
0x140030838  mov     [rsp+0C0h+var_A0], 5
0x14003083d  call    WPP_RECORDER_AND_TRACE_SF_d
0x140030842  jmp     loc_140030E0D
0x140030847  mov     r8d, [r13+30h]
0x14003084b  xor     edx, edx
0x14003084d  mov     eax, r8d
0x140030850  mov     [rbp+57h+var_60], r8d
0x140030854  div     ecx
0x140030856  xor     r9d, r9d
0x140030859  test    edx, edx
0x14003085b  lea     r15d, [rax+1]
0x14003085f  cmovz   r15d, eax
0x140030863  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003086a  mov     eax, [rcx+2Ch]
0x14003086d  test    sil, al
0x140030870  jz      short loc_14003087B
0x140030872  cmp     byte ptr [rcx+29h], 4
0x140030876  mov     dl, dil
0x140030879  jnb     short loc_14003087E
0x14003087b  mov     dl, r9b
0x14003087e  mov     rcx, [rcx+18h]
0x140030882  lea     r12, [r14+10B0h]
0x140030889  mov     r9, [r12]
0x14003088d  mov     dword ptr [rsp+0C0h+var_78], r15d
0x140030892  mov     dword ptr [rsp+0C0h+var_80], r8d
0x140030897  mov     r8b, dil
0x14003089a  mov     [rsp+0C0h+var_88], r10
0x14003089f  mov     word ptr [rsp+0C0h+var_90], 17h
0x1400308a6  mov     dword ptr [rsp+0C0h+var_98], esi
0x1400308aa  mov     [rsp+0C0h+var_A0], 4
0x1400308af  call    WPP_RECORDER_AND_TRACE_SF_LL
0x1400308b4  mov     rcx, [rbp+57h+var_40.Blink]
0x1400308b8  lea     rax, [rbp+57h+var_40]
0x1400308bc  cmp     [rcx], rax
0x1400308bf  jnz     loc_140030E75
0x1400308c5  lea     rax, [r13+58h]
0x1400308c9  mov     [rsp+0C0h+var_A0], dil; char
0x1400308ce  lea     rdx, [rbp+57h+var_40]
0x1400308d2  mov     [rax+8], rcx
0x1400308d6  mov     [rax], rdx
0x1400308d9  xor     r9d, r9d; unsigned __int8
0x1400308dc  mov     [rcx], rax
0x1400308df  mov     r8d, edi; unsigned int
0x1400308e2  lea     rcx, [rbp+57h+var_40]; struct _LIST_ENTRY *
0x1400308e6  mov     [rbp+57h+var_40.Blink], rax
0x1400308ea  lea     edx, [r9+4]; enum _HCI_PKT_TYPE
0x1400308ee  call    ?HCI_AllocateBipContexts@@YAJPEAU_LIST_ENTRY@@W4_HCI_PKT_TYPE@@KEE@Z; HCI_AllocateBipContexts(_LIST_ENTRY *,_HCI_PKT_TYPE,ulong,uchar,uchar)
0x1400308f3  mov     ebx, eax
0x1400308f5  lea     rcx, [rbp+57h+var_40]
0x1400308f9  mov     rax, [rbp+57h+var_40.Flink]
0x1400308fd  cmp     [rax+8], rcx
0x140030901  jnz     loc_140030E75
0x140030907  mov     rcx, [rax]
0x14003090a  cmp     [rcx+8], rax
0x14003090e  jnz     loc_140030E75
0x140030914  mov     [rbp+57h+var_40.Flink], rcx
0x140030918  lea     rdx, [rbp+57h+var_40]
0x14003091c  mov     [rcx+8], rdx
0x140030920  xor     ecx, ecx
0x140030922  mov     [rax+8], rax
0x140030926  mov     [rax], rax
0x140030929  test    ebx, ebx
0x14003092b  jns     loc_1400309D8
0x140030931  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140030938  mov     eax, [rcx+2Ch]
0x14003093b  test    sil, al
0x14003093e  jz      short loc_14003094E
0x140030940  cmp     [rcx+29h], sil
0x140030944  jb      short loc_14003094E
0x140030946  mov     dl, dil
0x140030949  xor     r15d, r15d
0x14003094c  jmp     short loc_140030954
0x14003094e  xor     r15d, r15d
0x140030951  mov     dl, r15b
0x140030954  mov     r9, [r12]
0x140030958  lea     r8, WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids
0x14003095f  mov     rcx, [rcx+18h]
0x140030963  mov     [rsp+0C0h+var_88], r8
0x140030968  mov     r8b, dil
0x14003096b  mov     word ptr [rsp+0C0h+var_90], 18h
0x140030972  mov     dword ptr [rsp+0C0h+var_98], esi
0x140030976  mov     [rsp+0C0h+var_A0], sil
0x14003097b  call    WPP_RECORDER_AND_TRACE_SF_
0x140030980  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140030987  mov     eax, [rcx+2Ch]
0x14003098a  test    sil, al
0x14003098d  jz      short loc_140030998
0x14003098f  cmp     byte ptr [rcx+29h], 5
0x140030993  mov     dl, dil
0x140030996  jnb     short loc_14003099B
0x140030998  mov     dl, r15b
0x14003099b  movzx   eax, word ptr [rcx+48h]
0x14003099f  mov     ebx, 0C000009Ah
0x1400309a4  test    ax, ax
0x1400309a7  setnz   r8b
0x1400309ab  test    dl, dl
0x1400309ad  jnz     short loc_1400309B8
0x1400309af  test    ax, ax
0x1400309b2  jz      loc_140030E0D
0x1400309b8  mov     dword ptr [rsp+0C0h+var_80], ebx
0x1400309bc  lea     r11, WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids
0x1400309c3  mov     [rsp+0C0h+var_88], r11
0x1400309c8  mov     word ptr [rsp+0C0h+var_90], 19h
0x1400309cf  mov     r9, [r12]
0x1400309d3  jmp     loc_140030830
0x1400309d8  mov     rsi, [r13+98h]
0x1400309df  lea     rdx, [rbp+57h+var_40]; struct _LIST_ENTRY *
0x1400309e3  mov     al, [rbp+57h+arg_18]
0x1400309e6  mov     r9d, r15d; unsigned int
0x1400309e9  mov     [rsp+0C0h+var_98], cl; unsigned __int8
0x1400309ed  mov     r8d, 4; enum _HCI_PKT_TYPE
0x1400309f3  mov     [rsp+0C0h+var_A0], cl; unsigned __int8
0x1400309f7  mov     [rsi+10h], r14
0x1400309fb  mov     [rsi+68h], al
0x1400309fe  mov     rcx, [r14+4A8h]; struct _BTDEVICE *
0x140030a05  mov     [rbp+57h+var_50], rsi
0x140030a09  call    ?HCI_AllocateBips@@YAEPEAU_BTDEVICE@@PEAU_LIST_ENTRY@@W4_HCI_PKT_TYPE@@KEE@Z; HCI_AllocateBips(_BTDEVICE *,_LIST_ENTRY *,_HCI_PKT_TYPE,ulong,uchar,uchar)
0x140030a0e  xor     edx, edx
0x140030a10  test    al, al
0x140030a12  jnz     loc_140030AB6
0x140030a18  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140030a1f  lea     esi, [rdx+2]
0x140030a22  mov     eax, [rcx+2Ch]
0x140030a25  test    sil, al
0x140030a28  jz      short loc_140030A33
0x140030a2a  cmp     [rcx+29h], sil
0x140030a2e  jb      short loc_140030A33
0x140030a30  mov     dl, dil
0x140030a33  mov     r9, [r12]
0x140030a37  lea     r8, WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids
0x140030a3e  mov     rcx, [rcx+18h]
0x140030a42  xor     r15d, r15d
0x140030a45  mov     [rsp+0C0h+var_88], r8
0x140030a4a  mov     r8b, dil
0x140030a4d  mov     word ptr [rsp+0C0h+var_90], 1Ah
0x140030a54  mov     dword ptr [rsp+0C0h+var_98], esi
0x140030a58  mov     [rsp+0C0h+var_A0], sil
0x140030a5d  call    WPP_RECORDER_AND_TRACE_SF_
0x140030a62  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140030a69  mov     eax, [rcx+2Ch]
0x140030a6c  test    sil, al
0x140030a6f  jz      short loc_140030A7A
0x140030a71  cmp     byte ptr [rcx+29h], 5
0x140030a75  mov     dl, dil
0x140030a78  jnb     short loc_140030A7D
0x140030a7a  mov     dl, r15b
0x140030a7d  movzx   eax, word ptr [rcx+48h]
0x140030a81  mov     ebx, 0C000009Ah
0x140030a86  test    ax, ax
0x140030a89  setnz   r8b
0x140030a8d  test    dl, dl
0x140030a8f  jnz     short loc_140030A9A
0x140030a91  test    ax, ax
0x140030a94  jz      loc_140030E0D
0x140030a9a  mov     dword ptr [rsp+0C0h+var_80], ebx
0x140030a9e  lea     r11, WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids
0x140030aa5  mov     [rsp+0C0h+var_88], r11
0x140030aaa  mov     word ptr [rsp+0C0h+var_90], 1Bh
0x140030ab1  jmp     loc_1400309CF
0x140030ab6  mov     rax, [rbp+57h+var_40.Flink]
0x140030aba  mov     r12d, edx
0x140030abd  mov     r9d, [rbp+57h+var_60]
0x140030ac1  mov     rcx, [rax+40h]
0x140030ac5  mov     [rsi+18h], rcx
0x140030ac9  mov     rsi, [rbp+57h+var_40.Flink]
0x140030acd  add     rsi, 0FFFFFFFFFFFFFFA8h
0x140030ad1  cmp     r12d, r15d
0x140030ad4  jnb     loc_140030B91
0x140030ada  mov     rax, [r13+0]
0x140030ade  mov     [rsi], rax
0x140030ae1  mov     eax, [r13+8]
0x140030ae5  mov     [rsi+8], eax
0x140030ae8  mov     eax, [r13+0Ch]
0x140030aec  mov     [rsi+0Ch], eax
0x140030aef  movups  xmm0, xmmword ptr [r13+10h]
0x140030af4  movdqu  xmmword ptr [rsi+10h], xmm0
0x140030af9  mov     eax, [r13+24h]
0x140030afd  test    al, 10h
0x140030aff  jz      short loc_140030B05
0x140030b01  or      dword ptr [rsi+24h], 10h
0x140030b05  mov     eax, [r13+24h]
0x140030b09  test    al, 20h
0x140030b0b  jz      short loc_140030B11
0x140030b0d  or      dword ptr [rsi+24h], 20h
0x140030b11  lea     rcx, [r14+0A00h]; Lookaside
0x140030b18  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140030b1f  nop     dword ptr [rax+rax+00h]
0x140030b24  mov     [rsi+28h], rax
0x140030b28  mov     rcx, rax; void *
0x140030b2b  test    rax, rax
0x140030b2e  jz      short loc_140030B84
0x140030b30  mov     r8d, [rbp+57h+var_5C]
0x140030b34  xor     edx, edx; Val
0x140030b36  add     r8d, 4; Size
0x140030b3a  call    memset
0x140030b3f  mov     rcx, [rsi+28h]
0x140030b43  xor     edx, edx
  ... truncated ...
```
