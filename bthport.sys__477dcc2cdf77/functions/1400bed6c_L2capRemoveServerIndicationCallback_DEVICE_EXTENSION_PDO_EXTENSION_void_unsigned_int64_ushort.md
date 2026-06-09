# L2capRemoveServerIndicationCallback(DEVICE_EXTENSION *,PDO_EXTENSION *,void *,unsigned __int64,ushort)

- ea: `0x1400bed6c`
- end: `0x1400bf28c`
- name: `?L2capRemoveServerIndicationCallback@@YAJPEAUDEVICE_EXTENSION@@PEAUPDO_EXTENSION@@PEAX_KG@Z`
- size: `1312`
- prototype: `int(struct DEVICE_EXTENSION *, struct PDO_EXTENSION *, void *, unsigned __int64, unsigned __int16)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400be8dc`

## callees

- `0x140005608`
- `0x140005b4c`
- `0x140006290`
- `0x14000764c`
- `0x14000bdb8`
- `0x14000e39c`
- `0x14001ffe8`
- `0x1400266f4`
- `0x140027c70`
- `0x14002a354`
- `0x1400bed6c`
- `0x140165540`
- `0x140165580`
- `0x140165940`
- `0x1401b9344`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400bf19f`
- `ntoskrnl!ObfDereferenceObject` at `0x1400bf19f`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400bf08d`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400bf08d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400beebe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400beebe`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bf14e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bf14e`

## pseudocode

```c
__int64 __fastcall L2capRemoveServerIndicationCallback(
        struct DEVICE_EXTENSION *a1,
        struct PDO_EXTENSION *a2,
        L2CAP_SERVER_INFO *a3,
        unsigned __int64 a4,
        unsigned __int16 a5)
{
  int v8; // edx
  int v9; // r8d
  char v10; // di
  __int16 DeviceType; // ax
  PDEVICE_OBJECT v12; // rcx
  unsigned int v13; // ebp
  unsigned __int64 v14; // r8
  unsigned __int64 v15; // r9
  int v16; // edx
  int v17; // r8d
  struct DEVICE_EXTENSION *DevExtFromWdmDevice; // rax
  struct DEVICE_EXTENSION *v19; // r14
  KSPIN_LOCK *p_AllChildPdoLock; // r13
  int v21; // edx
  L2CAP_SERVER_INFO *ServerInfo; // rsi
  PDEVICE_OBJECT v23; // rcx
  __int64 *v24; // r8
  unsigned __int64 v25; // r8
  unsigned __int64 v26; // r9
  __int64 *v27; // r8
  _RTL_RB_TREE *p_ClientRbTree; // r14
  unsigned __int64 Root; // rbx
  int v30; // esi
  int v31; // eax
  unsigned __int64 v32; // rax
  int v33; // edx
  __int64 *v34; // r8
  __int64 *v35; // r8
  void *ReferenceObject; // rbx
  __int16 v37; // ax
  __int16 v39; // [rsp+30h] [rbp-1E8h]
  __int16 v40; // [rsp+30h] [rbp-1E8h]
  char v41; // [rsp+40h] [rbp-1D8h]
  char v42; // [rsp+48h] [rbp-1D0h]
  char v43; // [rsp+50h] [rbp-1C8h]
  KIRQL NewIrql; // [rsp+60h] [rbp-1B8h]
  L2CAP_SERVER_INFO v45; // [rsp+70h] [rbp-1A8h] BYREF
  _INDICATION_PARAMETERS v46; // [rsp+E0h] [rbp-138h] BYREF

  L2CAP_SERVER_INFO::L2CAP_SERVER_INFO(&v45);
  v10 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    LOBYTE(v8) = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( (_BYTE)v8 || DeviceType )
  {
    LOBYTE(v9) = DeviceType != 0;
    WPP_RECORDER_AND_TRACE_SF_qLdL(
      WPP_GLOBAL_Control->AttachedDevice,
      v8,
      v9,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      3,
      10,
      (__int64)WPP_0a9faf4aee2b38bd582dec00ce311dfa_Traceguids,
      (char)a3,
      SBYTE4(a4),
      a4,
      a5);
  }
  if ( !a3 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v8) = 0;
    v39 = 11;
LABEL_12:
    LOBYTE(v9) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      v12->AttachedDevice,
      v8,
      v9,
      v12->DeviceExtension,
      2,
      3,
      v39,
      (__int64)WPP_0a9faf4aee2b38bd582dec00ce311dfa_Traceguids);
    v13 = -1073741811;
    BthVerif_BugCheckIfVerifierOn(7u, 0, v14, v15);
    goto LABEL_58;
  }
  if ( a2->PdoSignature != 1347571780
    || (DevExtFromWdmDevice = Fdo::GetDevExtFromWdmDevice(a2->Fdo), v19 = DevExtFromWdmDevice, !a2) )
  {
    v12 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v8) = 0;
    v39 = 12;
    goto LABEL_12;
  }
  p_AllChildPdoLock = &DevExtFromWdmDevice->AllChildPdoLock;
  v13 = 0;
  NewIrql = KeAcquireSpinLockRaiseToDpc(&DevExtFromWdmDevice->AllChildPdoLock);
  if ( !a4 )
  {
    ServerInfo = a2->ServerInfo;
    a2->ServerInfo = 0;
    if ( ServerInfo == a3 )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v21) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
        LOBYTE(v21) = 0;
      v27 = WPP_0a9faf4aee2b38bd582dec00ce311dfa_Traceguids;
      LOBYTE(v27) = 1;
      WPP_RECORDER_AND_TRACE_SF_qi(
        WPP_GLOBAL_Control->AttachedDevice,
        v21,
        (_DWORD)v27,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        3,
        14,
        (__int64)WPP_0a9faf4aee2b38bd582dec00ce311dfa_Traceguids,
        (char)ServerInfo,
        a2);
      goto LABEL_55;
    }
    v23 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v21) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v21) = 0;
    v43 = 0;
    v24 = WPP_0a9faf4aee2b38bd582dec00ce311dfa_Traceguids;
    v42 = 0;
    v41 = (char)a3;
    v40 = 13;
    goto LABEL_21;
  }
  p_ClientRbTree = &v19->ClientRbTree;
  v45.BtAddr = a4;
  v45.Psm = a5;
  Root = (unsigned __int64)p_ClientRbTree->Root;
  if ( (*(_BYTE *)&p_ClientRbTree->0 & 1) != 0 )
  {
    if ( !Root )
    {
LABEL_51:
      ServerInfo = 0;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || (LOBYTE(v21) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v21) = 0;
      v35 = WPP_0a9faf4aee2b38bd582dec00ce311dfa_Traceguids;
      LOBYTE(v35) = 1;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v21,
        (_DWORD)v35,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        3,
        17,
        (__int64)WPP_0a9faf4aee2b38bd582dec00ce311dfa_Traceguids);
      v13 = -1073741811;
      goto LABEL_55;
    }
    Root ^= (unsigned __int64)p_ClientRbTree;
  }
  v30 = *(_BYTE *)&p_ClientRbTree->0 & 1;
  if ( !Root )
    goto LABEL_51;
  do
  {
    v31 = BthServerNodeCompare(&v45, (struct _RTL_BALANCED_NODE *)Root);
    if ( v31 >= 0 )
    {
      if ( v31 <= 0 )
        break;
      v32 = *(_QWORD *)(Root + 8);
    }
    else
    {
      v32 = *(_QWORD *)Root;
    }
    if ( v30 && v32 )
      Root ^= v32;
    else
      Root = v32;
  }
  while ( Root );
  if ( !Root )
    goto LABEL_51;
  ServerInfo = (L2CAP_SERVER_INFO *)(Root - 80);
  if ( (L2CAP_SERVER_INFO *)(Root - 80) != a3 )
  {
    v23 = WPP_GLOBAL_Control;
    LOBYTE(v21) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    v43 = a4;
    v42 = BYTE4(a4);
    v24 = WPP_0a9faf4aee2b38bd582dec00ce311dfa_Traceguids;
    v41 = (char)a3;
    v40 = 15;
LABEL_21:
    LOBYTE(v24) = 1;
    WPP_RECORDER_AND_TRACE_SF_qLL(
      v23->AttachedDevice,
      v21,
      (_DWORD)v24,
      v23->DeviceExtension,
      2,
      3,
      v40,
      (__int64)WPP_0a9faf4aee2b38bd582dec00ce311dfa_Traceguids,
      v41,
      v42,
      v43);
    v13 = -1073741811;
    BthVerif_BugCheckIfVerifierOn(7u, (ULONG_PTR)a3, v25, v26);
    ServerInfo = 0;
    goto LABEL_55;
  }
  RtlRbRemoveNode(p_ClientRbTree, Root);
  LOBYTE(v33) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  v34 = WPP_0a9faf4aee2b38bd582dec00ce311dfa_Traceguids;
  LOBYTE(v34) = 1;
  WPP_RECORDER_AND_TRACE_SF_q(
    WPP_GLOBAL_Control->AttachedDevice,
    v33,
    (_DWORD)v34,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    3,
    16,
    (__int64)WPP_0a9faf4aee2b38bd582dec00ce311dfa_Traceguids,
    Root - 80);
LABEL_55:
  KeReleaseSpinLock(p_AllChildPdoLock, NewIrql);
  if ( ServerInfo )
  {
    memset(&v46, 0, sizeof(v46));
    ServerInfo->IndicationCallback(ServerInfo->IndicationContext, IndicationReleaseReference, &v46);
    ReferenceObject = ServerInfo->ReferenceObject;
    BthSynchFreeL2capServerInfo(ServerInfo);
    if ( ReferenceObject )
      ObfDereferenceObject(ReferenceObject);
  }
LABEL_58:
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v10 = 0;
  v37 = WPP_GLOBAL_Control->DeviceType;
  if ( v10 || v37 )
  {
    LOBYTE(v16) = v10;
    LOBYTE(v17) = v37 != 0;
    WPP_RECORDER_AND_TRACE_SF_qLdL(
      WPP_GLOBAL_Control->AttachedDevice,
      v16,
      v17,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      3,
      18,
      (__int64)WPP_0a9faf4aee2b38bd582dec00ce311dfa_Traceguids,
      (char)a3,
      SBYTE4(a4),
      a4,
      v13);
  }
  wil::operation_guard::~operation_guard(&v45.CallbackGuard);
  return v13;
}

```

## disassembly

```asm
0x1400bed6c  mov     [rsp+arg_0], rbx
0x1400bed71  push    rbp
0x1400bed72  push    rsi
0x1400bed73  push    rdi
0x1400bed74  push    r12
0x1400bed76  push    r13
0x1400bed78  push    r14
0x1400bed7a  push    r15
0x1400bed7c  sub     rsp, 1E0h
0x1400bed83  mov     rax, cs:__security_cookie
0x1400bed8a  xor     rax, rsp
0x1400bed8d  mov     [rsp+218h+var_48], rax
0x1400bed95  lea     rcx, [rsp+218h+var_1A8]; this
0x1400bed9a  mov     r12, r9
0x1400bed9d  mov     r15, r8
0x1400beda0  mov     rbx, rdx
0x1400beda3  call    ??0L2CAP_SERVER_INFO@@QEAA@XZ; L2CAP_SERVER_INFO::L2CAP_SERVER_INFO(void)
0x1400beda8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400bedaf  xor     r14d, r14d
0x1400bedb2  mov     bpl, 4
0x1400bedb5  mov     eax, [rcx+2Ch]
0x1400bedb8  lea     edi, [r14+1]
0x1400bedbc  test    bpl, al
0x1400bedbf  jz      short loc_1400BEDCA
0x1400bedc1  cmp     byte ptr [rcx+29h], 5
0x1400bedc5  mov     dl, dil
0x1400bedc8  jnb     short loc_1400BEDCD
0x1400bedca  mov     dl, r14b
0x1400bedcd  movzx   eax, word ptr [rcx+48h]
0x1400bedd1  lea     r13, WPP_0a9faf4aee2b38bd582dec00ce311dfa_Traceguids
0x1400bedd8  movzx   esi, [rsp+218h+arg_20]
0x1400bede0  test    ax, ax
0x1400bede3  setnz   r8b
0x1400bede7  test    dl, dl
0x1400bede9  jnz     short loc_1400BEDF0
0x1400bedeb  test    ax, ax
0x1400bedee  jz      short loc_1400BEE34
0x1400bedf0  mov     [rsp+218h+var_1C0], esi
0x1400bedf4  mov     rax, r12
0x1400bedf7  mov     dword ptr [rsp+218h+var_1C8], r12d
0x1400bedfc  shr     rax, 20h
0x1400bee00  movzx   r9d, ax
0x1400bee04  mov     dword ptr [rsp+218h+var_1D0], r9d
0x1400bee09  mov     r9, [rcx+40h]
0x1400bee0d  mov     rcx, [rcx+18h]
0x1400bee11  mov     [rsp+218h+var_1D8], r15
0x1400bee16  mov     [rsp+218h+var_1E0], r13
0x1400bee1b  mov     [rsp+218h+var_1E8], 0Ah
0x1400bee22  mov     [rsp+218h+var_1F0], 3
0x1400bee2a  mov     [rsp+218h+var_1F8], 5
0x1400bee2f  call    WPP_RECORDER_AND_TRACE_SF_qLdL
0x1400bee34  test    r15, r15
0x1400bee37  jnz     short loc_1400BEE91
0x1400bee39  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400bee40  mov     eax, [rcx+2Ch]
0x1400bee43  test    bpl, al
0x1400bee46  jz      short loc_1400BEE51
0x1400bee48  cmp     byte ptr [rcx+29h], 2
0x1400bee4c  mov     dl, dil
0x1400bee4f  jnb     short loc_1400BEE54
0x1400bee51  mov     dl, r14b
0x1400bee54  mov     [rsp+218h+var_1E0], r13
0x1400bee59  mov     [rsp+218h+var_1E8], 0Bh
0x1400bee60  mov     r9, [rcx+40h]
0x1400bee64  mov     r8b, dil
0x1400bee67  mov     rcx, [rcx+18h]
0x1400bee6b  mov     [rsp+218h+var_1F0], 3
0x1400bee73  mov     [rsp+218h+var_1F8], 2
0x1400bee78  call    WPP_RECORDER_AND_TRACE_SF_
0x1400bee7d  xor     edx, edx; BugCheckParameter2
0x1400bee7f  mov     ebp, 0C000000Dh
0x1400bee84  lea     ecx, [rdx+7]; BugCheckParameter1
0x1400bee87  call    ?BthVerif_BugCheckIfVerifierOn@@YAXK_K00@Z; BthVerif_BugCheckIfVerifierOn(ulong,unsigned __int64,unsigned __int64,unsigned __int64)
0x1400bee8c  jmp     loc_1400BF1B2
0x1400bee91  cmp     dword ptr [rbx], 50525044h
0x1400bee97  jnz     loc_1400BF260
0x1400bee9d  mov     rcx, [rbx+40h]; struct _DEVICE_OBJECT *
0x1400beea1  call    ?GetDevExtFromWdmDevice@Fdo@@SAPEAUDEVICE_EXTENSION@@PEAU_DEVICE_OBJECT@@@Z; Fdo::GetDevExtFromWdmDevice(_DEVICE_OBJECT *)
0x1400beea6  mov     r14, rax
0x1400beea9  test    rbx, rbx
0x1400beeac  jz      loc_1400BF25D
0x1400beeb2  lea     r13, [rax+110h]
0x1400beeb9  xor     ebp, ebp
0x1400beebb  mov     rcx, r13; SpinLock
0x1400beebe  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400beec5  nop     dword ptr [rax+rax+00h]
0x1400beeca  mov     [rsp+218h+NewIrql], al
0x1400beece  test    r12, r12
0x1400beed1  jnz     loc_1400BEFB3
0x1400beed7  mov     rsi, [rbx+30h]
0x1400beedb  xor     r14d, r14d
0x1400beede  mov     [rbx+30h], r14
0x1400beee2  cmp     rsi, r15
0x1400beee5  jz      short loc_1400BEF5A
0x1400beee7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400beeee  mov     eax, [rcx+2Ch]
0x1400beef1  test    al, 4
0x1400beef3  jz      short loc_1400BEEFE
0x1400beef5  cmp     byte ptr [rcx+29h], 2
0x1400beef9  mov     dl, dil
0x1400beefc  jnb     short loc_1400BEF01
0x1400beefe  mov     dl, r14b
0x1400bef01  mov     dword ptr [rsp+218h+var_1C8], r14d
0x1400bef06  lea     r8, WPP_0a9faf4aee2b38bd582dec00ce311dfa_Traceguids
0x1400bef0d  mov     dword ptr [rsp+218h+var_1D0], r14d
0x1400bef12  mov     [rsp+218h+var_1D8], r15
0x1400bef17  mov     [rsp+218h+var_1E0], r8
0x1400bef1c  mov     [rsp+218h+var_1E8], 0Dh
0x1400bef23  mov     r9, [rcx+40h]
0x1400bef27  mov     r8b, dil
0x1400bef2a  mov     rcx, [rcx+18h]
0x1400bef2e  mov     [rsp+218h+var_1F0], 3
0x1400bef36  mov     [rsp+218h+var_1F8], 2
0x1400bef3b  call    WPP_RECORDER_AND_TRACE_SF_qLL
0x1400bef40  mov     rdx, r15; BugCheckParameter2
0x1400bef43  mov     ecx, 7; BugCheckParameter1
0x1400bef48  mov     ebp, 0C000000Dh
0x1400bef4d  call    ?BthVerif_BugCheckIfVerifierOn@@YAXK_K00@Z; BthVerif_BugCheckIfVerifierOn(ulong,unsigned __int64,unsigned __int64,unsigned __int64)
0x1400bef52  mov     rsi, r14
0x1400bef55  jmp     loc_1400BF147
0x1400bef5a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400bef61  mov     eax, [rcx+2Ch]
0x1400bef64  test    al, 4
0x1400bef66  jz      short loc_1400BEF71
0x1400bef68  cmp     byte ptr [rcx+29h], 4
0x1400bef6c  mov     dl, dil
0x1400bef6f  jnb     short loc_1400BEF74
0x1400bef71  mov     dl, r14b
0x1400bef74  mov     r9, [rcx+40h]
0x1400bef78  lea     r8, WPP_0a9faf4aee2b38bd582dec00ce311dfa_Traceguids
0x1400bef7f  mov     rcx, [rcx+18h]
0x1400bef83  mov     [rsp+218h+var_1D0], rbx
0x1400bef88  mov     [rsp+218h+var_1D8], rsi
0x1400bef8d  mov     [rsp+218h+var_1E0], r8
0x1400bef92  mov     r8b, dil
0x1400bef95  mov     [rsp+218h+var_1E8], 0Eh
0x1400bef9c  mov     [rsp+218h+var_1F0], 3
0x1400befa4  mov     [rsp+218h+var_1F8], 4
0x1400befa9  call    WPP_RECORDER_AND_TRACE_SF_qi
0x1400befae  jmp     loc_1400BF147
0x1400befb3  add     r14, 0E0h
0x1400befba  mov     [rsp+218h+var_1A8.BtAddr], r12
0x1400befc2  mov     [rsp+218h+var_1A8.Psm], si
0x1400befca  mov     rbx, [r14]
0x1400befcd  test    [r14+8], dil
0x1400befd1  jz      short loc_1400BEFDF
0x1400befd3  test    rbx, rbx
0x1400befd6  jz      loc_1400BF0F2
0x1400befdc  xor     rbx, r14
0x1400befdf  movzx   esi, byte ptr [r14+8]
0x1400befe4  and     esi, edi
0x1400befe6  test    rbx, rbx
0x1400befe9  jz      loc_1400BF0F2
0x1400befef  mov     rdx, rbx; struct _RTL_BALANCED_NODE *
0x1400beff2  lea     rcx, [rsp+218h+var_1A8]; void *
0x1400beff7  call    ?BthServerNodeCompare@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; BthServerNodeCompare(void *,_RTL_BALANCED_NODE *)
0x1400beffc  test    eax, eax
0x1400beffe  jns     short loc_1400BF005
0x1400bf000  mov     rax, [rbx]
0x1400bf003  jmp     short loc_1400BF00B
0x1400bf005  jle     short loc_1400BF021
0x1400bf007  mov     rax, [rbx+8]
0x1400bf00b  test    esi, esi
0x1400bf00d  jz      short loc_1400BF019
0x1400bf00f  test    rax, rax
0x1400bf012  jz      short loc_1400BF019
0x1400bf014  xor     rbx, rax
0x1400bf017  jmp     short loc_1400BF01C
0x1400bf019  mov     rbx, rax
0x1400bf01c  test    rbx, rbx
0x1400bf01f  jnz     short loc_1400BEFEF
0x1400bf021  test    rbx, rbx
0x1400bf024  jz      loc_1400BF0F2
0x1400bf02a  lea     rsi, [rbx-50h]
0x1400bf02e  cmp     rsi, r15
0x1400bf031  jz      short loc_1400BF087
0x1400bf033  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400bf03a  mov     eax, [rcx+2Ch]
0x1400bf03d  test    al, 4
0x1400bf03f  jz      short loc_1400BF04F
0x1400bf041  cmp     byte ptr [rcx+29h], 2
0x1400bf045  jb      short loc_1400BF04F
0x1400bf047  mov     dl, dil
0x1400bf04a  xor     r14d, r14d
0x1400bf04d  jmp     short loc_1400BF055
0x1400bf04f  xor     r14d, r14d
0x1400bf052  mov     dl, r14b
0x1400bf055  mov     dword ptr [rsp+218h+var_1C8], r12d
0x1400bf05a  mov     rax, r12
0x1400bf05d  shr     rax, 20h
0x1400bf061  movzx   r8d, ax
0x1400bf065  mov     dword ptr [rsp+218h+var_1D0], r8d
0x1400bf06a  lea     r8, WPP_0a9faf4aee2b38bd582dec00ce311dfa_Traceguids
0x1400bf071  mov     [rsp+218h+var_1D8], r15
0x1400bf076  mov     [rsp+218h+var_1E0], r8
0x1400bf07b  mov     [rsp+218h+var_1E8], 0Fh
0x1400bf082  jmp     loc_1400BEF23
0x1400bf087  mov     rdx, rbx
0x1400bf08a  mov     rcx, r14
0x1400bf08d  call    cs:__imp_RtlRbRemoveNode
0x1400bf094  nop     dword ptr [rax+rax+00h]
0x1400bf099  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400bf0a0  mov     eax, [rcx+2Ch]
0x1400bf0a3  test    al, 4
0x1400bf0a5  jz      short loc_1400BF0B5
0x1400bf0a7  cmp     byte ptr [rcx+29h], 4
0x1400bf0ab  jb      short loc_1400BF0B5
0x1400bf0ad  mov     dl, dil
0x1400bf0b0  xor     r14d, r14d
0x1400bf0b3  jmp     short loc_1400BF0BB
0x1400bf0b5  xor     r14d, r14d
0x1400bf0b8  mov     dl, r14b
0x1400bf0bb  mov     r9, [rcx+40h]
0x1400bf0bf  lea     r8, WPP_0a9faf4aee2b38bd582dec00ce311dfa_Traceguids
0x1400bf0c6  mov     rcx, [rcx+18h]
0x1400bf0ca  mov     [rsp+218h+var_1D8], rsi
0x1400bf0cf  mov     [rsp+218h+var_1E0], r8
0x1400bf0d4  mov     r8b, dil
0x1400bf0d7  mov     [rsp+218h+var_1E8], 10h
0x1400bf0de  mov     [rsp+218h+var_1F0], 3
0x1400bf0e6  mov     [rsp+218h+var_1F8], 4
0x1400bf0eb  call    WPP_RECORDER_AND_TRACE_SF_q
0x1400bf0f0  jmp     short loc_1400BF147
0x1400bf0f2  xor     r14d, r14d
0x1400bf0f5  mov     esi, r14d
0x1400bf0f8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400bf0ff  mov     eax, [rcx+2Ch]
0x1400bf102  test    al, 4
0x1400bf104  jz      short loc_1400BF10F
0x1400bf106  cmp     byte ptr [rcx+29h], 2
0x1400bf10a  mov     dl, dil
0x1400bf10d  jnb     short loc_1400BF112
0x1400bf10f  mov     dl, r14b
0x1400bf112  mov     r9, [rcx+40h]
0x1400bf116  lea     r8, WPP_0a9faf4aee2b38bd582dec00ce311dfa_Traceguids
0x1400bf11d  mov     rcx, [rcx+18h]
0x1400bf121  mov     [rsp+218h+var_1E0], r8
0x1400bf126  mov     r8b, dil
0x1400bf129  mov     [rsp+218h+var_1E8], 11h
0x1400bf130  mov     [rsp+218h+var_1F0], 3
0x1400bf138  mov     [rsp+218h+var_1F8], 2
0x1400bf13d  call    WPP_RECORDER_AND_TRACE_SF_
0x1400bf142  mov     ebp, 0C000000Dh
0x1400bf147  mov     dl, [rsp+218h+NewIrql]; NewIrql
0x1400bf14b  mov     rcx, r13; SpinLock
0x1400bf14e  call    cs:__imp_KeReleaseSpinLock
0x1400bf155  nop     dword ptr [rax+rax+00h]
0x1400bf15a  test    rsi, rsi
0x1400bf15d  jz      short loc_1400BF1AB
0x1400bf15f  xor     edx, edx; Val
0x1400bf161  lea     rcx, [rsp+218h+var_138]; void *
0x1400bf169  mov     r8d, 0E8h; Size
0x1400bf16f  call    memset
0x1400bf174  mov     rax, [rsi+28h]
0x1400bf178  lea     r8, [rsp+218h+var_138]
0x1400bf180  mov     rcx, [rsi+30h]
0x1400bf184  mov     edx, edi
0x1400bf186  call    _guard_dispatch_icall
0x1400bf18b  mov     rbx, [rsi+38h]
0x1400bf18f  mov     rcx, rsi; this
0x1400bf192  call    ?BthSynchFreeL2capServerInfo@@YAXPEAUL2CAP_SERVER_INFO@@@Z; BthSynchFreeL2capServerInfo(L2CAP_SERVER_INFO *)
0x1400bf197  test    rbx, rbx
0x1400bf19a  jz      short loc_1400BF1AB
0x1400bf19c  mov     rcx, rbx; Object
0x1400bf19f  call    cs:__imp_ObfDereferenceObject
0x1400bf1a6  nop     dword ptr [rax+rax+00h]
0x1400bf1ab  lea     r13, WPP_0a9faf4aee2b38bd582dec00ce311dfa_Traceguids
0x1400bf1b2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400bf1b9  mov     eax, [rcx+2Ch]
0x1400bf1bc  test    al, 4
0x1400bf1be  jz      short loc_1400BF1C6
0x1400bf1c0  cmp     byte ptr [rcx+29h], 5
0x1400bf1c4  jnb     short loc_1400BF1C9
0x1400bf1c6  mov     dil, r14b
0x1400bf1c9  movzx   eax, word ptr [rcx+48h]
0x1400bf1cd  test    ax, ax
0x1400bf1d0  setnz   r8b
0x1400bf1d4  test    dil, dil
0x1400bf1d7  jnz     short loc_1400BF1DE
0x1400bf1d9  test    ax, ax
0x1400bf1dc  jz      short loc_1400BF225
0x1400bf1de  mov     [rsp+218h+var_1C0], ebp
0x1400bf1e2  mov     rax, r12
0x1400bf1e5  mov     dword ptr [rsp+218h+var_1C8], r12d
0x1400bf1ea  mov     dl, dil
0x1400bf1ed  shr     rax, 20h
0x1400bf1f1  movzx   r9d, ax
0x1400bf1f5  mov     dword ptr [rsp+218h+var_1D0], r9d
0x1400bf1fa  mov     r9, [rcx+40h]
0x1400bf1fe  mov     rcx, [rcx+18h]
0x1400bf202  mov     [rsp+218h+var_1D8], r15
0x1400bf207  mov     [rsp+218h+var_1E0], r13
0x1400bf20c  mov     [rsp+218h+var_1E8], 12h
0x1400bf213  mov     [rsp+218h+var_1F0], 3
0x1400bf21b  mov     [rsp+218h+var_1F8], 5
0x1400bf220  call    WPP_RECORDER_AND_TRACE_SF_qLdL
0x1400bf225  lea     rcx, [rsp+218h+var_1A8]; this
0x1400bf22a  call    ??1operation_guard@wil@@QEAA@XZ; wil::operation_guard::~operation_guard(void)
0x1400bf22f  mov     eax, ebp
0x1400bf231  mov     rcx, [rsp+218h+var_48]
  ... truncated ...
```
