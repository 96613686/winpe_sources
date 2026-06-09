# CPort::OnIncomingAssociationRequestReceived(ulong,uchar *)

- ea: `0x1400b3c48`
- end: `0x1400b40eb`
- name: `?OnIncomingAssociationRequestReceived@CPort@@QEAAXKPEAE@Z`
- size: `1187`
- prototype: `void __fastcall(CPort *__hidden this, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000e2c0`

## callees

- `0x14000da4c`
- `0x140010390`
- `0x1400109f8`
- `0x140010b20`
- `0x1400122e0`
- `0x140023ae0`
- `0x14002aa28`
- `0x14002ed64`
- `0x140034e04`
- `0x140034ec4`
- `0x1400489f0`
- `0x14005abb4`
- `0x1400611e4`
- `0x14006505c`
- `0x14008d878`
- `0x1400b3c48`
- `0x1400da4f0`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400b3ea5`
- `ntoskrnl!ExAllocatePool2` at `0x1400b3ea5`

## pseudocode

```c
void __fastcall CPort::OnIncomingAssociationRequestReceived(CPort *this, unsigned int a2, unsigned __int8 *a3)
{
  char v3; // r15
  unsigned int v5; // r13d
  int v7; // eax
  int v8; // edx
  int v9; // r8d
  char v10; // di
  int v11; // edx
  struct CConnectedPeer *v12; // rsi
  int v13; // r8d
  _WDI_MAC_ADDRESS *p_BssId; // rdx
  IDisassociationCompleteCallback *m_pDisassociationCompleteCallback; // rcx
  unsigned int v16; // r14d
  char *Pool2; // rsi
  int v18; // r8d
  unsigned int m_NdisPortNumber; // edx
  CAdapter *m_pAdapter; // rcx
  char v21; // al
  CAdapterPropertyCache *v22; // rax
  CAdapterPropertyCache *v23; // rax
  int v24; // edx
  int v25; // r8d
  unsigned __int8 v26[4]; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v27; // [rsp+54h] [rbp-45h] BYREF
  unsigned __int8 *v28; // [rsp+58h] [rbp-41h] BYREF
  _WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED_PARAMETERS v29; // [rsp+60h] [rbp-39h] BYREF
  __int16 v30; // [rsp+A8h] [rbp+Fh]

  *(_DWORD *)&v29.Optional &= ~1u;
  *(_DWORD *)v29.BssId.Address = 0;
  v29.SAECommitResponse.ElementCount = 0;
  v3 = 0;
  v29.SAECommitResponse.pElements = 0;
  v29.SAECommitResponse.MemoryInternallyAllocated = 0;
  v5 = a2;
  v29.SAEConfirmResponse.ElementCount = 0;
  v29.SAEConfirmResponse.pElements = 0;
  v29.SAEConfirmResponse.MemoryInternallyAllocated = 0;
  v27 = 0;
  v28 = 0;
  v26[0] = 0;
  *(_WORD *)&v29.BssId.Address[4] = 0;
  *((_BYTE *)&v29.BssId + 6) = 0;
  *(_QWORD *)&v29.SAEStatus = 0;
  v30 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      353,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids);
  }
  v7 = ParseWdiIndicationApAssociationRequestReceivedFromIhv(v5 - 48, a3 + 48, &this->m_pAdapter->m_TlvContext, &v29);
  v10 = v7;
  if ( v7 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_35;
    LOBYTE(v8) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      v9,
      354,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
      (char)this,
      this->m_WfcPortId,
      v7);
  }
  else
  {
    v12 = this->m_pPeerList->FindPeerByAddress(this->m_pPeerList, &v29.BssId);
    if ( v12 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        p_BssId = &v29.BssId;
        LOBYTE(p_BssId) = 5;
        WPP_RECORDER_SF_qD_MAC_(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)p_BssId,
          v13,
          355,
          (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
          (char)this,
          this->m_WfcPortId,
          (__int64)&v29.BssId);
      }
      CPort::IndicateSinglePeerDisassociated(this, v12, 7u, WDI_ASSOC_STATUS_PEER_DISASSOCIATED);
      this->m_pPeerList->DeletePeer(this->m_pPeerList, (unsigned __int8 *)&v29.BssId);
      m_pDisassociationCompleteCallback = this->m_pDisassociationCompleteCallback;
      if ( m_pDisassociationCompleteCallback )
        m_pDisassociationCompleteCallback->OnDisassociationProcessed(m_pDisassociationCompleteCallback);
    }
    v16 = v29.SAECommitResponse.ElementCount + 20;
    if ( v29.SAECommitResponse.ElementCount < 0xFFFFFFEC )
    {
      Pool2 = (char *)ExAllocatePool2(64, v16, 1198089303);
      if ( Pool2 )
      {
        m_NdisPortNumber = this->m_NdisPortNumber;
        *((_DWORD *)&v29.SAEStatus + 1) = *(_DWORD *)v29.BssId.Address;
        m_pAdapter = this->m_pAdapter;
        v30 = *(_WORD *)&v29.BssId.Address[4];
        v29.SAEStatus = 655744;
        CAdapter::IndicateStatus(m_pAdapter, m_NdisPortNumber, 1073938445, 0, &v29.SAEStatus, 0xAu);
        *(_DWORD *)Pool2 = 1311104;
        *(_WDI_MAC_ADDRESS *)(Pool2 + 4) = v29.BssId;
        v21 = *((_BYTE *)&v29.BssId + 6);
        *((_DWORD *)Pool2 + 3) = 20;
        Pool2[10] = v21;
        *((_DWORD *)Pool2 + 4) = v29.SAECommitResponse.ElementCount;
        if ( !(unsigned int)CPropertyCache::GetPropertyBuffer(&this->m_PortPropertyCache, 0x46u, &v27, &v28)
          && v27 == 16
          && *(_DWORD *)v28 == 3 )
        {
          v22 = this->m_pAdapter->GetAdapterPropertyCache(&this->m_pAdapter->IPropertyCacheDirectory);
          CPropertyCache::GetPropertyUchar(v22, 0x86u, v26);
          v3 = v26[0];
        }
        CopyMgmtFrameFromNetwork(
          0,
          v3,
          (__int16 *)&Pool2[*((unsigned int *)Pool2 + 3)],
          v29.SAECommitResponse.pElements,
          *((_DWORD *)Pool2 + 4));
        v23 = this->m_pAdapter->GetAdapterPropertyCache(&this->m_pAdapter->IPropertyCacheDirectory);
        if ( CPropertyCache::SetPropertyBuffer(v23, 0x32u, v5, a3)
          && *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v24) = 2;
          WPP_RECORDER_SF_qD(
            WPP_GLOBAL_Control->DeviceExtension,
            v24,
            v25,
            358,
            (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
            (char)this,
            this->m_WfcPortId);
        }
        CAdapter::IndicateStatus(this->m_pAdapter, this->m_NdisPortNumber, 1073938446, 0, Pool2, v16);
        operator delete(Pool2);
      }
      else
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v11) = 2;
          WPP_RECORDER_SF_qD(
            WPP_GLOBAL_Control->DeviceExtension,
            v11,
            v18,
            357,
            (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
            (char)this,
            this->m_WfcPortId);
        }
        v10 = -102;
      }
    }
    else
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = 2;
        WPP_RECORDER_SF_qDDDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          v13,
          356,
          (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
          (char)this,
          this->m_WfcPortId,
          v29.SAECommitResponse.ElementCount,
          -1,
          1);
      }
      v10 = 1;
    }
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v11) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      1,
      359,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
      v10);
  }
LABEL_35:
  _WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED_PARAMETERS::~_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED_PARAMETERS(&v29);
}

```

## disassembly

```asm
0x1400b3c48  mov     [rsp-8+arg_18], rbx
0x1400b3c4d  push    rbp
0x1400b3c4e  push    rsi
0x1400b3c4f  push    rdi
0x1400b3c50  push    r12
0x1400b3c52  push    r13
0x1400b3c54  push    r14
0x1400b3c56  push    r15
0x1400b3c58  lea     rbp, [rsp-27h]
0x1400b3c5d  sub     rsp, 0C0h
0x1400b3c64  mov     rax, cs:__security_cookie
0x1400b3c6b  xor     rax, rsp
0x1400b3c6e  mov     [rbp+57h+var_40], rax
0x1400b3c72  and     dword ptr [rbp+57h+var_90.Optional.SAECommitResponse_IsPresent], 0FFFFFFFEh
0x1400b3c76  xor     eax, eax
0x1400b3c78  xor     r14d, r14d
0x1400b3c7b  mov     dword ptr [rbp+57h+var_90.BssId.Address], eax
0x1400b3c7e  mov     [rbp+57h+var_90.SAECommitResponse.ElementCount], r14d
0x1400b3c82  mov     r15b, r14b
0x1400b3c85  mov     [rbp+57h+var_90.SAECommitResponse.pElements], r14
0x1400b3c89  mov     r12, r8
0x1400b3c8c  mov     [rbp+57h+var_90.SAECommitResponse.MemoryInternallyAllocated], r14b
0x1400b3c90  mov     r13d, edx
0x1400b3c93  mov     [rbp+57h+var_90.SAEConfirmResponse.ElementCount], r14d
0x1400b3c97  mov     rbx, rcx
0x1400b3c9a  mov     [rbp+57h+var_90.SAEConfirmResponse.pElements], r14
0x1400b3c9e  mov     [rbp+57h+var_90.SAEConfirmResponse.MemoryInternallyAllocated], r14b
0x1400b3ca2  mov     [rbp+57h+var_9C], r14d
0x1400b3ca6  mov     [rbp+57h+var_98], r14
0x1400b3caa  mov     [rbp+57h+var_A0], r14b
0x1400b3cae  mov     word ptr [rbp+57h+var_90.BssId.Address+4], ax
0x1400b3cb2  mov     byte ptr [rbp+57h+var_90+0Ah], al
0x1400b3cb5  mov     qword ptr [rbp+57h+var_90.SAEStatus], rax
0x1400b3cb9  mov     [rbp+57h+var_48], ax
0x1400b3cbd  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400b3cc4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b3ccb  lea     rsi, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400b3cd2  jz      short loc_1400B3D04
0x1400b3cd4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3cdb  cmp     byte ptr [rcx+29h], 5
0x1400b3cdf  jnb     short loc_1400B3CE8
0x1400b3ce1  cmp     [rcx+48h], r14w
0x1400b3ce6  jz      short loc_1400B3D04
0x1400b3ce8  mov     rcx, [rcx+40h]
0x1400b3cec  mov     r9d, 161h
0x1400b3cf2  mov     r8d, 1
0x1400b3cf8  mov     [rsp+0F0h+var_D0], rsi
0x1400b3cfd  mov     dl, 5
0x1400b3cff  call    WPP_RECORDER_SF_
0x1400b3d04  mov     r8, [rbx+58h]
0x1400b3d08  lea     rdx, [r12+30h]
0x1400b3d0d  add     r8, 3FF8h
0x1400b3d14  lea     ecx, [r13-30h]
0x1400b3d18  lea     r9, [rbp+57h+var_90]
0x1400b3d1c  call    ParseWdiIndicationApAssociationRequestReceivedFromIhv
0x1400b3d21  mov     edi, eax
0x1400b3d23  test    eax, eax
0x1400b3d25  jz      short loc_1400B3D6E
0x1400b3d27  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400b3d2e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b3d35  jz      loc_1400B40BA
0x1400b3d3b  movzx   ecx, word ptr [rbx+64h]
0x1400b3d3f  mov     r9d, 162h
0x1400b3d45  mov     dword ptr [rsp+0F0h+var_B8], edi
0x1400b3d49  mov     dl, 2
0x1400b3d4b  mov     [rsp+0F0h+var_C0], ecx
0x1400b3d4f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3d56  mov     qword ptr [rsp+0F0h+var_C8], rbx
0x1400b3d5b  mov     [rsp+0F0h+var_D0], rsi
0x1400b3d60  mov     rcx, [rcx+40h]
0x1400b3d64  call    WPP_RECORDER_SF_qDD
0x1400b3d69  jmp     loc_1400B4076
0x1400b3d6e  mov     rcx, [rbx+398h]
0x1400b3d75  lea     rdx, [rbp+57h+var_90.BssId]
0x1400b3d79  mov     rax, [rcx]
0x1400b3d7c  mov     rax, [rax+10h]
0x1400b3d80  call    _guard_dispatch_icall
0x1400b3d85  mov     rsi, rax
0x1400b3d88  test    rax, rax
0x1400b3d8b  jz      loc_1400B3E2B
0x1400b3d91  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400b3d98  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b3d9f  jz      short loc_1400B3DE8
0x1400b3da1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3da8  cmp     byte ptr [rcx+29h], 5
0x1400b3dac  jnb     short loc_1400B3DB5
0x1400b3dae  cmp     [rcx+48h], r14w
0x1400b3db3  jz      short loc_1400B3DE8
0x1400b3db5  movzx   eax, word ptr [rbx+64h]
0x1400b3db9  lea     rdx, [rbp+57h+var_90.BssId]
0x1400b3dbd  mov     rcx, [rcx+40h]
0x1400b3dc1  mov     r9d, 163h
0x1400b3dc7  mov     [rsp+0F0h+var_B8], rdx
0x1400b3dcc  mov     dl, 5
0x1400b3dce  mov     [rsp+0F0h+var_C0], eax
0x1400b3dd2  lea     rax, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400b3dd9  mov     qword ptr [rsp+0F0h+var_C8], rbx
0x1400b3dde  mov     [rsp+0F0h+var_D0], rax
0x1400b3de3  call    WPP_RECORDER_SF_qD_MAC_
0x1400b3de8  mov     r8d, 7; unsigned __int16
0x1400b3dee  mov     rdx, rsi; struct CConnectedPeer *
0x1400b3df1  mov     rcx, rbx; this
0x1400b3df4  lea     r9d, [r8+7]; enum _WDI_ASSOC_STATUS
0x1400b3df8  call    ?IndicateSinglePeerDisassociated@CPort@@QEAAXPEAVCConnectedPeer@@GW4_WDI_ASSOC_STATUS@@@Z; CPort::IndicateSinglePeerDisassociated(CConnectedPeer *,ushort,_WDI_ASSOC_STATUS)
0x1400b3dfd  mov     rcx, [rbx+398h]
0x1400b3e04  lea     rdx, [rbp+57h+var_90.BssId]
0x1400b3e08  mov     rax, [rcx]
0x1400b3e0b  mov     rax, [rax+8]
0x1400b3e0f  call    _guard_dispatch_icall
0x1400b3e14  mov     rcx, [rbx+408h]
0x1400b3e1b  test    rcx, rcx
0x1400b3e1e  jz      short loc_1400B3E2B
0x1400b3e20  mov     rax, [rcx]
0x1400b3e23  mov     rax, [rax]
0x1400b3e26  call    _guard_dispatch_icall
0x1400b3e2b  mov     ecx, [rbp+57h+var_90.SAECommitResponse.ElementCount]
0x1400b3e2e  lea     r14d, [rcx+14h]
0x1400b3e32  cmp     r14d, 14h
0x1400b3e36  jnb     short loc_1400B3E97
0x1400b3e38  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400b3e3f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b3e46  lea     rsi, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400b3e4d  jz      short loc_1400B3E8D
0x1400b3e4f  movzx   eax, word ptr [rbx+64h]
0x1400b3e53  mov     r9d, 164h
0x1400b3e59  mov     [rsp+0F0h+var_A8], 0C0000001h
0x1400b3e61  mov     dl, 2
0x1400b3e63  mov     [rsp+0F0h+var_B0], 0FFFFFFFFh
0x1400b3e6b  mov     dword ptr [rsp+0F0h+var_B8], ecx
0x1400b3e6f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3e76  mov     [rsp+0F0h+var_C0], eax
0x1400b3e7a  mov     qword ptr [rsp+0F0h+var_C8], rbx
0x1400b3e7f  mov     [rsp+0F0h+var_D0], rsi
0x1400b3e84  mov     rcx, [rcx+40h]
0x1400b3e88  call    WPP_RECORDER_SF_qDDDD
0x1400b3e8d  mov     edi, 0C0000001h
0x1400b3e92  jmp     loc_1400B4073
0x1400b3e97  mov     edx, r14d
0x1400b3e9a  mov     ecx, 40h ; '@'
0x1400b3e9f  mov     r8d, 47696457h
0x1400b3ea5  call    cs:__imp_ExAllocatePool2
0x1400b3eac  nop     dword ptr [rax+rax+00h]
0x1400b3eb1  mov     rsi, rax
0x1400b3eb4  test    rax, rax
0x1400b3eb7  jnz     short loc_1400B3F04
0x1400b3eb9  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400b3ec0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b3ec7  lea     rsi, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400b3ece  jz      short loc_1400B3EFA
0x1400b3ed0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3ed7  mov     r9d, 165h
0x1400b3edd  movzx   eax, word ptr [rbx+64h]
0x1400b3ee1  mov     dl, 2
0x1400b3ee3  mov     [rsp+0F0h+var_C0], eax
0x1400b3ee7  mov     qword ptr [rsp+0F0h+var_C8], rbx
0x1400b3eec  mov     rcx, [rcx+40h]
0x1400b3ef0  mov     [rsp+0F0h+var_D0], rsi
0x1400b3ef5  call    WPP_RECORDER_SF_qD
0x1400b3efa  mov     edi, 0C000009Ah
0x1400b3eff  jmp     loc_1400B4073
0x1400b3f04  mov     eax, dword ptr [rbp+57h+var_90.BssId.Address]
0x1400b3f07  mov     ecx, 0Ah
0x1400b3f0c  mov     edx, [rbx+60h]; unsigned int
0x1400b3f0f  xor     r9d, r9d; void *
0x1400b3f12  mov     dword ptr [rbp+57h+var_90+44h], eax
0x1400b3f15  mov     r8d, 4003000Dh; int
0x1400b3f1b  movzx   eax, word ptr [rbp+57h+var_90.BssId.Address+4]
0x1400b3f1f  mov     [rsp+0F0h+var_C8], ecx; unsigned int
0x1400b3f23  mov     rcx, [rbx+58h]; this
0x1400b3f27  mov     [rbp+57h+var_48], ax
0x1400b3f2b  lea     rax, [rbp+57h+var_90.SAEStatus]
0x1400b3f2f  mov     [rsp+0F0h+var_D0], rax; void *
0x1400b3f34  mov     [rbp+57h+var_90.SAEStatus], 0A0180h
0x1400b3f3b  call    ?IndicateStatus@CAdapter@@QEAAXKHPEAX0K@Z; CAdapter::IndicateStatus(ulong,int,void *,void *,ulong)
0x1400b3f40  mov     dword ptr [rsi], 140180h
0x1400b3f46  lea     r9, [rbp+57h+var_98]; unsigned __int8 **
0x1400b3f4a  mov     eax, dword ptr [rbp+57h+var_90.BssId.Address]
0x1400b3f4d  lea     r8, [rbp+57h+var_9C]; unsigned int *
0x1400b3f51  mov     [rsi+4], eax
0x1400b3f54  mov     ecx, 14h
0x1400b3f59  movzx   eax, word ptr [rbp+57h+var_90.BssId.Address+4]
0x1400b3f5d  mov     edx, 46h ; 'F'; unsigned int
0x1400b3f62  mov     [rsi+8], ax
0x1400b3f66  mov     al, byte ptr [rbp+57h+var_90+0Ah]
0x1400b3f69  mov     [rsi+0Ch], ecx
0x1400b3f6c  lea     rcx, [rbx+3A8h]; this
0x1400b3f73  mov     [rsi+0Ah], al
0x1400b3f76  mov     eax, [rbp+57h+var_90.SAECommitResponse.ElementCount]
0x1400b3f79  mov     [rsi+10h], eax
0x1400b3f7c  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x1400b3f81  test    eax, eax
0x1400b3f83  jnz     short loc_1400B3FBD
0x1400b3f85  cmp     [rbp+57h+var_9C], 10h
0x1400b3f89  jnz     short loc_1400B3FBD
0x1400b3f8b  mov     rax, [rbp+57h+var_98]
0x1400b3f8f  cmp     dword ptr [rax], 3
0x1400b3f92  jnz     short loc_1400B3FBD
0x1400b3f94  mov     rcx, [rbx+58h]
0x1400b3f98  add     rcx, 8
0x1400b3f9c  mov     rax, [rcx]
0x1400b3f9f  mov     rax, [rax+8]
0x1400b3fa3  call    _guard_dispatch_icall
0x1400b3fa8  lea     r8, [rbp+57h+var_A0]; unsigned __int8 *
0x1400b3fac  mov     edx, 86h; unsigned int
0x1400b3fb1  mov     rcx, rax; this
0x1400b3fb4  call    ?GetPropertyUchar@CPropertyCache@@QEAAHKPEAE@Z; CPropertyCache::GetPropertyUchar(ulong,uchar *)
0x1400b3fb9  mov     r15b, [rbp+57h+var_A0]
0x1400b3fbd  mov     r8d, [rsi+0Ch]
0x1400b3fc1  mov     dl, r15b
0x1400b3fc4  mov     eax, [rsi+10h]
0x1400b3fc7  add     r8, rsi
0x1400b3fca  mov     r9, [rbp+57h+var_90.SAECommitResponse.pElements]
0x1400b3fce  xor     ecx, ecx
0x1400b3fd0  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1400b3fd4  call    ?CopyMgmtFrameFromNetwork@@YAHW4DOT11_MGMT_SUBTYPE@@EPEAE1K@Z; CopyMgmtFrameFromNetwork(DOT11_MGMT_SUBTYPE,uchar,uchar *,uchar *,ulong)
0x1400b3fd9  mov     rcx, [rbx+58h]
0x1400b3fdd  add     rcx, 8
0x1400b3fe1  mov     rax, [rcx]
0x1400b3fe4  mov     rax, [rax+8]
0x1400b3fe8  call    _guard_dispatch_icall
0x1400b3fed  mov     r9, r12; unsigned __int8 *
0x1400b3ff0  mov     r8d, r13d; unsigned int
0x1400b3ff3  mov     edx, 32h ; '2'; unsigned int
0x1400b3ff8  mov     rcx, rax; this
0x1400b3ffb  call    ?SetPropertyBuffer@CPropertyCache@@QEAAHKKPEAE@Z; CPropertyCache::SetPropertyBuffer(ulong,ulong,uchar *)
0x1400b4000  test    eax, eax
0x1400b4002  jz      short loc_1400B4045
0x1400b4004  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400b400b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b4012  jz      short loc_1400B4045
0x1400b4014  movzx   eax, word ptr [rbx+64h]
0x1400b4018  mov     r9d, 166h
0x1400b401e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4025  mov     dl, 2
0x1400b4027  mov     [rsp+0F0h+var_C0], eax
0x1400b402b  lea     rax, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400b4032  mov     qword ptr [rsp+0F0h+var_C8], rbx
0x1400b4037  mov     [rsp+0F0h+var_D0], rax
0x1400b403c  mov     rcx, [rcx+40h]
0x1400b4040  call    WPP_RECORDER_SF_qD
0x1400b4045  mov     edx, [rbx+60h]; unsigned int
0x1400b4048  xor     r9d, r9d; void *
0x1400b404b  mov     rcx, [rbx+58h]; this
0x1400b404f  mov     r8d, 4003000Eh; int
0x1400b4055  mov     [rsp+0F0h+var_C8], r14d; unsigned int
0x1400b405a  mov     [rsp+0F0h+var_D0], rsi; void *
0x1400b405f  call    ?IndicateStatus@CAdapter@@QEAAXKHPEAX0K@Z; CAdapter::IndicateStatus(ulong,int,void *,void *,ulong)
0x1400b4064  mov     rcx, rsi; void *
0x1400b4067  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b406c  lea     rsi, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400b4073  xor     r14d, r14d
0x1400b4076  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400b407d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b4084  jz      short loc_1400B40BA
0x1400b4086  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b408d  cmp     byte ptr [rcx+29h], 5
0x1400b4091  jnb     short loc_1400B409A
0x1400b4093  cmp     [rcx+48h], r14w
0x1400b4098  jz      short loc_1400B40BA
0x1400b409a  mov     rcx, [rcx+40h]
0x1400b409e  mov     r9d, 167h
0x1400b40a4  mov     [rsp+0F0h+var_C8], edi
0x1400b40a8  mov     r8d, 1
0x1400b40ae  mov     dl, 5
0x1400b40b0  mov     [rsp+0F0h+var_D0], rsi
0x1400b40b5  call    WPP_RECORDER_SF_D
0x1400b40ba  lea     rcx, [rbp+57h+var_90]; this
0x1400b40be  call    ??1_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED_PARAMETERS@@QEAA@XZ; _WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED_PARAMETERS::~_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED_PARAMETERS(void)
0x1400b40c3  mov     rcx, [rbp+57h+var_40]
0x1400b40c7  xor     rcx, rsp; StackCookie
0x1400b40ca  call    __security_check_cookie
0x1400b40cf  mov     rbx, [rsp+0F0h+arg_18]
0x1400b40d7  add     rsp, 0C0h
0x1400b40de  pop     r15
0x1400b40e0  pop     r14
0x1400b40e2  pop     r13
0x1400b40e4  pop     r12
0x1400b40e6  pop     rdi
0x1400b40e7  pop     rsi
0x1400b40e8  pop     rbp
0x1400b40e9  retn
```
