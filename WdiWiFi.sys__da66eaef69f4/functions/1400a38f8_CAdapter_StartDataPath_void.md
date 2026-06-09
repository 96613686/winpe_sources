# CAdapter::StartDataPath(void)

- ea: `0x1400a38f8`
- end: `0x1400a3c46`
- name: `?StartDataPath@CAdapter@@QEAAHXZ`
- size: `846`
- prototype: `__int64 __fastcall(CAdapter *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140076da0`

## callees

- `0x140017a90`
- `0x140034e04`
- `0x140034ec4`
- `0x140068504`
- `0x1400685e4`
- `0x14007d678`
- `0x14009b458`
- `0x14009d3b4`
- `0x1400a21b8`
- `0x1400a38f8`
- `0x1400da4f0`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400a3bcd`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400a3bcd`

## pseudocode

```c
__int64 __fastcall CAdapter::StartDataPath(CAdapter *this)
{
  int v2; // r9d
  __int64 v3; // rcx
  unsigned int v4; // ebx
  int v5; // eax
  int v6; // edx
  int v7; // r9d
  void *m_MiniportTalTxRxContext; // rcx
  MINIPORT_WDI_TAL_TXRX_START_HANDLER TalTxRxStartHandler; // rax
  int v10; // r8d
  char v11; // al
  int v12; // edx
  __int64 v14; // [rsp+28h] [rbp-40h]
  unsigned __int16 v15; // [rsp+30h] [rbp-38h] BYREF
  _OWORD v16[2]; // [rsp+38h] [rbp-30h] BYREF

  memset(v16, 0, 28);
  v15 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      148,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
  }
  if ( this == (CAdapter *)-4812LL )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v2 = 149;
LABEL_29:
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        1,
        v2,
        (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
      goto LABEL_30;
    }
    goto LABEL_30;
  }
  v3 = 175;
  if ( ((this->m_MiniportWdiFrameMetadataExtraSpace + 175LL) & 0xFFFFFFFFFFFFFFF0uLL) > 0xFFFF )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v2 = 150;
      goto LABEL_29;
    }
LABEL_30:
    v4 = -1073741823;
    goto LABEL_31;
  }
  LOWORD(v3) = (LOWORD(this->m_MiniportWdiFrameMetadataExtraSpace) + 175) & 0xFFF0;
  this->m_WfcFrameSize = v3;
  CAdapter::InitializeNPagedLookaside((CAdapter *)v3, (unsigned __int16)v3, &this->m_WfcFrameLookaside);
  this->m_WfcFrameLookasideInitialized = 1;
  v4 = CFrameIdLookupTable::Initialize(&this->m_FrameIdTable.m_FrameIdLock);
  if ( v4 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        1,
        151,
        (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
    goto LABEL_31;
  }
  v5 = CPeerTable::Initialize(&this->m_PeerTable.m_PeerTableLock, this->m_DatapathCapabilities.MaxNumPeers);
  v4 = v5;
  if ( v5 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    {
LABEL_31:
      if ( this->m_WfcFrameLookasideInitialized )
      {
        ExDeleteNPagedLookasideList(&this->m_WfcFrameLookaside);
        this->m_WfcFrameLookasideInitialized = 0;
      }
      CTxMgr::Deinitialize(&this->m_TxMgr);
      goto LABEL_34;
    }
    v7 = 152;
LABEL_15:
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      1,
      v7,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
      v5);
    goto LABEL_31;
  }
  v5 = CTxMgr::Initialize(&this->m_TxMgr, this, &this->m_DatapathCapabilities, 5u);
  v4 = v5;
  if ( v5 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_31;
    v7 = 153;
    goto LABEL_15;
  }
  v5 = CRxMgr::Initialize(&this->m_RxMgr, this, &this->m_DatapathCapabilities, &this->m_MiniportDataHandlers);
  v4 = v5;
  if ( v5 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_31;
    v7 = 154;
    goto LABEL_15;
  }
  m_MiniportTalTxRxContext = this->m_MiniportTalTxRxContext;
  BYTE9(v16[1]) = this->m_DatapathCapabilities.MaxNumPeers;
  LODWORD(v16[0]) = this->m_DatapathCapabilities.InterconnectType;
  BYTE4(v16[0]) = this->m_DatapathCapabilities.TxTargetPriorityQueueing;
  BYTE8(v16[0]) = this->m_DatapathCapabilities.TxExplicitSendCompleteFlagRequired;
  WORD3(v16[0]) = this->m_DatapathCapabilities.TxMaxScatterGatherElementsPerFrame;
  *(_DWORD *)((char *)v16 + 10) = *(_DWORD *)&this->m_DatapathCapabilities.TxMinEffectiveFrameSize;
  LOBYTE(v16[1]) = this->m_DatapathCapabilities.RxTxForwarding;
  DWORD1(v16[1]) = this->m_DatapathCapabilities.RxMaxThroughput;
  TalTxRxStartHandler = this->m_MiniportDataHandlers.TalTxRxStartHandler;
  BYTE8(v16[1]) = 5;
  v5 = ((__int64 (__fastcall *)(void *, _OWORD *, unsigned __int16 *))TalTxRxStartHandler)(
         m_MiniportTalTxRxContext,
         v16,
         &v15);
  v4 = v5;
  if ( v5 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_31;
    v7 = 155;
    goto LABEL_15;
  }
  v11 = v15;
  this->m_TxMgr.m_MaxOutstandingTransfers = v15;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    return v4;
  LOBYTE(v6) = 4;
  WPP_RECORDER_SF_d(
    WPP_GLOBAL_Control->DeviceExtension,
    v6,
    v10,
    163,
    (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
    v11);
LABEL_34:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v14) = v4;
    LOBYTE(v12) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      1,
      156,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
      v14);
  }
  return v4;
}

```

## disassembly

```asm
0x1400a38f8  push    rbp
0x1400a38fa  push    rbx
0x1400a38fb  push    rsi
0x1400a38fc  push    rdi
0x1400a38fd  push    r12
0x1400a38ff  push    r13
0x1400a3901  push    r14
0x1400a3903  push    r15
0x1400a3905  mov     rbp, rsp
0x1400a3908  sub     rsp, 68h
0x1400a390c  mov     rax, cs:__security_cookie
0x1400a3913  xor     rax, rsp
0x1400a3916  mov     [rbp+var_10], rax
0x1400a391a  xorps   xmm0, xmm0
0x1400a391d  xor     r15d, r15d
0x1400a3920  movups  [rbp+var_30], xmm0
0x1400a3924  mov     rdi, rcx
0x1400a3927  mov     [rbp+var_38], r15w
0x1400a392c  movups  [rbp+var_30+0Ch], xmm0
0x1400a3930  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a3937  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400a393e  lea     r13, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x1400a3945  lea     r12d, [r15+1]
0x1400a3949  jz      short loc_1400A3978
0x1400a394b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3952  cmp     byte ptr [rcx+29h], 5
0x1400a3956  jnb     short loc_1400A395F
0x1400a3958  cmp     [rcx+48h], r15w
0x1400a395d  jz      short loc_1400A3978
0x1400a395f  mov     rcx, [rcx+40h]
0x1400a3963  mov     r9d, 94h
0x1400a3969  mov     r8d, r12d
0x1400a396c  mov     [rsp+68h+var_48], r13
0x1400a3971  mov     dl, 5
0x1400a3973  call    WPP_RECORDER_SF_
0x1400a3978  lea     rsi, [rdi+12CCh]
0x1400a397f  test    rsi, rsi
0x1400a3982  jnz     short loc_1400A399C
0x1400a3984  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400a398b  jz      loc_1400A3BB8
0x1400a3991  mov     r9d, 95h
0x1400a3997  jmp     loc_1400A3B9E
0x1400a399c  mov     eax, [rdi+3F0Ch]
0x1400a39a2  mov     ecx, 0AFh
0x1400a39a7  add     rax, rcx
0x1400a39aa  and     rax, 0FFFFFFFFFFFFFFF0h
0x1400a39ae  cmp     rax, 0FFFFh
0x1400a39b4  ja      loc_1400A3B8F
0x1400a39ba  add     cx, [rdi+3F0Ch]
0x1400a39c1  lea     r8, [rdi+1540h]; struct _NPAGED_LOOKASIDE_LIST *
0x1400a39c8  mov     eax, 0FFF0h
0x1400a39cd  and     cx, ax; this
0x1400a39d0  movzx   edx, cx; unsigned int
0x1400a39d3  mov     [rdi+15C2h], dx
0x1400a39da  call    ?InitializeNPagedLookaside@CAdapter@@AEAAXKPEAU_NPAGED_LOOKASIDE_LIST@@@Z; CAdapter::InitializeNPagedLookaside(ulong,_NPAGED_LOOKASIDE_LIST *)
0x1400a39df  lea     rcx, [rdi+15E0h]; this
0x1400a39e6  mov     [rdi+15C0h], r12b
0x1400a39ed  call    ?Initialize@CFrameIdLookupTable@@QEAAHXZ; CFrameIdLookupTable::Initialize(void)
0x1400a39f2  mov     ebx, eax
0x1400a39f4  test    eax, eax
0x1400a39f6  jz      short loc_1400A3A2A
0x1400a39f8  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400a39ff  jz      loc_1400A3BBD
0x1400a3a05  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3a0c  mov     r9d, 97h
0x1400a3a12  mov     r8d, r12d
0x1400a3a15  mov     [rsp+68h+var_48], r13
0x1400a3a1a  mov     dl, 2
0x1400a3a1c  mov     rcx, [rcx+40h]
0x1400a3a20  call    WPP_RECORDER_SF_
0x1400a3a25  jmp     loc_1400A3BBD
0x1400a3a2a  mov     dl, [rsi+4]; unsigned __int8
0x1400a3a2d  lea     rcx, [rdi+39F8h]; this
0x1400a3a34  call    ?Initialize@CPeerTable@@QEAAHE@Z; CPeerTable::Initialize(uchar)
0x1400a3a39  mov     ebx, eax
0x1400a3a3b  test    eax, eax
0x1400a3a3d  jz      short loc_1400A3A75
0x1400a3a3f  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400a3a46  jz      loc_1400A3BBD
0x1400a3a4c  mov     r9d, 98h
0x1400a3a52  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3a59  mov     r8d, r12d
0x1400a3a5c  mov     dword ptr [rsp+68h+var_40], eax
0x1400a3a60  mov     dl, 2
0x1400a3a62  mov     [rsp+68h+var_48], r13
0x1400a3a67  mov     rcx, [rcx+40h]
0x1400a3a6b  call    WPP_RECORDER_SF_D
0x1400a3a70  jmp     loc_1400A3BBD
0x1400a3a75  lea     rcx, [rdi+3A10h]; this
0x1400a3a7c  mov     r9b, 5; unsigned __int8
0x1400a3a7f  mov     r8, rsi; struct _WFC_DATAPATH_CAPABILITIES *
0x1400a3a82  mov     rdx, rdi; struct CAdapter *
0x1400a3a85  call    ?Initialize@CTxMgr@@QEAAHPEAVCAdapter@@PEAU_WFC_DATAPATH_CAPABILITIES@@E@Z; CTxMgr::Initialize(CAdapter *,_WFC_DATAPATH_CAPABILITIES *,uchar)
0x1400a3a8a  mov     ebx, eax
0x1400a3a8c  test    eax, eax
0x1400a3a8e  jz      short loc_1400A3AA5
0x1400a3a90  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400a3a97  jz      loc_1400A3BBD
0x1400a3a9d  mov     r9d, 99h
0x1400a3aa3  jmp     short loc_1400A3A52
0x1400a3aa5  lea     r9, [rdi+3E40h]; struct _NDIS_MINIPORT_WDI_DATA_HANDLERS *
0x1400a3aac  mov     r8, rsi; struct _WFC_DATAPATH_CAPABILITIES *
0x1400a3aaf  lea     rcx, [rdi+3BB0h]; this
0x1400a3ab6  mov     rdx, rdi; struct CAdapter *
0x1400a3ab9  call    ?Initialize@CRxMgr@@QEAAHPEAVCAdapter@@PEAU_WFC_DATAPATH_CAPABILITIES@@PEAU_NDIS_MINIPORT_WDI_DATA_HANDLERS@@@Z; CRxMgr::Initialize(CAdapter *,_WFC_DATAPATH_CAPABILITIES *,_NDIS_MINIPORT_WDI_DATA_HANDLERS *)
0x1400a3abe  mov     ebx, eax
0x1400a3ac0  test    eax, eax
0x1400a3ac2  jz      short loc_1400A3ADC
0x1400a3ac4  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400a3acb  jz      loc_1400A3BBD
0x1400a3ad1  mov     r9d, 9Ah
0x1400a3ad7  jmp     loc_1400A3A52
0x1400a3adc  mov     al, [rsi+4]
0x1400a3adf  lea     r8, [rbp+var_38]
0x1400a3ae3  mov     rcx, [rdi+70h]
0x1400a3ae7  lea     rdx, [rbp+var_30]
0x1400a3aeb  mov     [rbp+var_17], al
0x1400a3aee  mov     eax, [rsi]
0x1400a3af0  mov     dword ptr [rbp+var_30], eax
0x1400a3af3  mov     al, [rsi+5]
0x1400a3af6  mov     byte ptr [rbp+var_30+4], al
0x1400a3af9  mov     al, [rsi+8]
0x1400a3afc  mov     byte ptr [rbp+var_30+8], al
0x1400a3aff  movzx   eax, word ptr [rsi+6]
0x1400a3b03  mov     word ptr [rbp+var_30+6], ax
0x1400a3b07  movzx   eax, word ptr [rsi+0Ah]
0x1400a3b0b  mov     word ptr [rbp+var_30+0Ah], ax
0x1400a3b0f  movzx   eax, word ptr [rsi+0Ch]
0x1400a3b13  mov     word ptr [rbp+var_30+0Ch], ax
0x1400a3b17  mov     al, [rsi+0Eh]
0x1400a3b1a  mov     [rbp+var_20], al
0x1400a3b1d  mov     eax, [rsi+10h]
0x1400a3b20  mov     [rbp+var_1C], eax
0x1400a3b23  mov     rax, [rdi+3EC4h]
0x1400a3b2a  mov     [rbp+var_18], 5
0x1400a3b2e  call    _guard_dispatch_icall
0x1400a3b33  mov     ebx, eax
0x1400a3b35  test    eax, eax
0x1400a3b37  jz      short loc_1400A3B4D
0x1400a3b39  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400a3b40  jz      short loc_1400A3BBD
0x1400a3b42  mov     r9d, 9Bh
0x1400a3b48  jmp     loc_1400A3A52
0x1400a3b4d  movzx   eax, [rbp+var_38]
0x1400a3b51  mov     [rdi+3A50h], ax
0x1400a3b58  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400a3b5f  jz      loc_1400A3C26
0x1400a3b65  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3b6c  mov     r9d, 0A3h
0x1400a3b72  mov     dword ptr [rsp+68h+var_40], eax
0x1400a3b76  mov     dl, 4
0x1400a3b78  lea     rax, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x1400a3b7f  mov     [rsp+68h+var_48], rax
0x1400a3b84  mov     rcx, [rcx+40h]
0x1400a3b88  call    WPP_RECORDER_SF_d
0x1400a3b8d  jmp     short loc_1400A3BEC
0x1400a3b8f  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400a3b96  jz      short loc_1400A3BB8
0x1400a3b98  mov     r9d, 96h
0x1400a3b9e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3ba5  mov     r8d, r12d
0x1400a3ba8  mov     dl, 2
0x1400a3baa  mov     [rsp+68h+var_48], r13
0x1400a3baf  mov     rcx, [rcx+40h]
0x1400a3bb3  call    WPP_RECORDER_SF_
0x1400a3bb8  mov     ebx, 0C0000001h
0x1400a3bbd  cmp     [rdi+15C0h], r15b
0x1400a3bc4  jz      short loc_1400A3BE0
0x1400a3bc6  lea     rcx, [rdi+1540h]; Lookaside
0x1400a3bcd  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400a3bd4  nop     dword ptr [rax+rax+00h]
0x1400a3bd9  mov     [rdi+15C0h], r15b
0x1400a3be0  lea     rcx, [rdi+3A10h]; this
0x1400a3be7  call    ?Deinitialize@CTxMgr@@QEAAHXZ; CTxMgr::Deinitialize(void)
0x1400a3bec  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400a3bf3  jz      short loc_1400A3C26
0x1400a3bf5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3bfc  cmp     byte ptr [rcx+29h], 5
0x1400a3c00  jnb     short loc_1400A3C09
0x1400a3c02  cmp     [rcx+48h], r15w
0x1400a3c07  jz      short loc_1400A3C26
0x1400a3c09  mov     rcx, [rcx+40h]
0x1400a3c0d  mov     r9d, 9Ch
0x1400a3c13  mov     dword ptr [rsp+68h+var_40], ebx
0x1400a3c17  mov     r8d, r12d
0x1400a3c1a  mov     dl, 5
0x1400a3c1c  mov     [rsp+68h+var_48], r13
0x1400a3c21  call    WPP_RECORDER_SF_D
0x1400a3c26  mov     eax, ebx
0x1400a3c28  mov     rcx, [rbp+var_10]
0x1400a3c2c  xor     rcx, rsp; StackCookie
0x1400a3c2f  call    __security_check_cookie
0x1400a3c34  add     rsp, 68h
0x1400a3c38  pop     r15
0x1400a3c3a  pop     r14
0x1400a3c3c  pop     r13
0x1400a3c3e  pop     r12
0x1400a3c40  pop     rdi
0x1400a3c41  pop     rsi
0x1400a3c42  pop     rbx
0x1400a3c43  pop     rbp
0x1400a3c44  retn
```
