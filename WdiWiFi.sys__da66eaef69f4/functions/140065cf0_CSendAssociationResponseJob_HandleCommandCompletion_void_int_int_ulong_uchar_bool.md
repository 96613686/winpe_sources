# CSendAssociationResponseJob::HandleCommandCompletion(void *,int,int,ulong,uchar *,bool *)

- ea: `0x140065cf0`
- end: `0x140066360`
- name: `?HandleCommandCompletion@CSendAssociationResponseJob@@UEAAHPEAXHHKPEAEPEA_N@Z`
- size: `1648`
- prototype: `__int64 __usercall@<rax>(CSendAssociationResponseJob *__hidden this@<rcx>, void *@<rdx>, int@<r8d>, int@<r9d>, unsigned int, unsigned __int8 *, bool *)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400109f8`
- `0x140010b20`
- `0x1400122e0`
- `0x1400147e8`
- `0x14001a808`
- `0x140021280`
- `0x1400297a0`
- `0x14002aa28`
- `0x14002ed64`
- `0x140049c08`
- `0x1400611e4`
- `0x140065cf0`
- `0x14007d4d0`
- `0x14008dd48`
- `0x1400da4f0`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400660b4`
- `ntoskrnl!ExAllocatePool2` at `0x1400660b4`

## pseudocode

```c
__int64 __fastcall CSendAssociationResponseJob::HandleCommandCompletion(
        CSendAssociationResponseJob *this,
        void *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned __int8 *a6,
        bool *a7)
{
  char v7; // r15
  unsigned int v9; // edi
  __int64 *v11; // rdx
  int v12; // r9d
  unsigned int v13; // edx
  unsigned int v14; // r8d
  unsigned int v16; // eax
  int v17; // r9d
  unsigned __int64 v18; // rcx
  unsigned int v19; // eax
  int v20; // r9d
  unsigned int v21; // r13d
  _WORD *v22; // r14
  __int64 Pool2; // rax
  __int64 v24; // rsi
  struct CPortPropertyCache *PortPropertyCache; // rax
  CAdapterPropertyCache *v26; // rax
  unsigned int ElementCount; // eax
  unsigned int v28; // r14d
  unsigned int v29; // eax
  unsigned int v30; // r14d
  unsigned int *v31; // r12
  unsigned int i; // r13d
  CAdapterPropertyCache *v33; // rax
  unsigned int v34; // ecx
  unsigned int v35; // eax
  unsigned __int16 m_PortId; // dx
  CAdapter *m_pAdapter; // rcx
  struct CPort *PortFromPortId; // rax
  int v39; // edx
  int v40; // r8d
  unsigned int m_ActivityId; // [rsp+30h] [rbp-B1h]
  __int64 v42; // [rsp+38h] [rbp-A9h]
  unsigned int v43; // [rsp+38h] [rbp-A9h]
  int v44; // [rsp+38h] [rbp-A9h]
  char v45; // [rsp+40h] [rbp-A1h]
  char v46; // [rsp+48h] [rbp-99h]
  unsigned __int8 v47[4]; // [rsp+50h] [rbp-91h] BYREF
  unsigned int v48; // [rsp+54h] [rbp-8Dh] BYREF
  unsigned int v49; // [rsp+58h] [rbp-89h]
  unsigned __int8 *v50; // [rsp+60h] [rbp-81h] BYREF
  __int128 v51; // [rsp+70h] [rbp-71h] BYREF
  int v52; // [rsp+80h] [rbp-61h]
  unsigned int v53; // [rsp+88h] [rbp-59h] BYREF
  _WORD *v54; // [rsp+90h] [rbp-51h]
  char v55; // [rsp+98h] [rbp-49h]
  int v56; // [rsp+A0h] [rbp-41h] BYREF
  const void *v57; // [rsp+A8h] [rbp-39h]
  char v58; // [rsp+B0h] [rbp-31h]
  unsigned int v59; // [rsp+B8h] [rbp-29h] BYREF
  __int64 v60; // [rsp+C0h] [rbp-21h]
  char v61; // [rsp+C8h] [rbp-19h]

  v53 = 0;
  v54 = 0;
  v7 = 0;
  v55 = 0;
  v56 = 0;
  v9 = a3;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v48 = 0;
  v50 = 0;
  v47[0] = 0;
  v51 = 0;
  v52 = 0;
  v11 = WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v11) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v11,
      a3,
      51,
      (__int64)WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids,
      (char)this,
      this->m_ActivityId);
    v11 = WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids;
  }
  *a7 = 0;
  if ( v9 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_13;
    v12 = 52;
    v43 = v9;
    goto LABEL_8;
  }
  if ( a4 )
  {
    v9 = a4;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_13;
    v12 = 53;
    v43 = a4;
LABEL_8:
    LOBYTE(v11) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v11,
      a3,
      v12,
      (__int64)WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids,
      (char)this,
      this->m_ActivityId,
      v43);
    goto LABEL_9;
  }
  v16 = ParseWdiIndicationSendApAssociationResponseCompleteFromIhv(
          a5 - 48,
          a6 + 48,
          &this->m_pAdapter->m_TlvContext,
          &v51);
  v9 = v16;
  if ( v16 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_13;
    v17 = 54;
    v44 = v16;
    m_ActivityId = this->m_ActivityId;
    goto LABEL_20;
  }
  LODWORD(v18) = this->m_ResponseParameters.IncomingRequestInfo.AssocRequestFrame.ElementCount;
  v19 = v18 + 64;
  if ( (unsigned int)(v18 + 64) < 0x40 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    {
LABEL_27:
      v9 = -1073741823;
      goto LABEL_9;
    }
    v20 = 55;
    goto LABEL_24;
  }
  LOBYTE(v18) = v53;
  if ( v53 < 6 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_qDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        v14,
        56,
        (__int64)WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids,
        (char)this,
        this->m_ActivityId,
        0,
        v53);
    }
    v9 = -1073676267;
    goto LABEL_9;
  }
  v13 = v19 + v53;
  if ( v19 + v53 < v19 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_27;
    v20 = 57;
LABEL_24:
    v46 = -1;
LABEL_25:
    v45 = v18;
LABEL_26:
    LOBYTE(v13) = 2;
    WPP_RECORDER_SF_qDDDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      v14,
      v20,
      (__int64)WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids,
      (char)this,
      this->m_ActivityId,
      1,
      v45,
      v46);
    goto LABEL_27;
  }
  v14 = v59;
  v18 = 4LL * v59;
  if ( v18 > 0xFFFFFFFF )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_27;
    v46 = 4;
    v20 = 58;
    v45 = v59;
    goto LABEL_26;
  }
  v14 = v18 + v13;
  if ( (unsigned int)v18 + v13 < v13 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_27;
    v20 = 59;
    goto LABEL_39;
  }
  LOBYTE(v18) = v56;
  v21 = v14 + v56;
  v49 = v14 + v56;
  if ( v14 + v56 < v14 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_27;
    v20 = 60;
LABEL_39:
    v46 = -1;
    goto LABEL_25;
  }
  v22 = v54;
  Pool2 = ExAllocatePool2(64, v21, 1198089303);
  v24 = Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)Pool2 = 4194688;
    *(_DWORD *)(Pool2 + 4) = v51;
    *(_WORD *)(Pool2 + 8) = WORD2(v51);
    *(_DWORD *)(Pool2 + 12) = (unsigned __int16)v22[1];
    if ( v22[1] )
      *(_BYTE *)(Pool2 + 16) = 1;
    *(_WORD *)(Pool2 + 17) = WORD3(v51);
    *(_QWORD *)(Pool2 + 36) = *((_QWORD *)&v51 + 1);
    *(_DWORD *)(Pool2 + 44) = v52;
    PortPropertyCache = COidJobBase::GetPortPropertyCache(this);
    if ( !(unsigned int)CPropertyCache::GetPropertyBuffer(PortPropertyCache, 0x46u, &v48, &v50)
      && v48 == 16
      && *(_DWORD *)v50 == 3 )
    {
      v26 = this->m_pAdapter->GetAdapterPropertyCache(&this->m_pAdapter->IPropertyCacheDirectory);
      CPropertyCache::GetPropertyUchar(v26, 0x86u, v47);
      v7 = v47[0];
    }
    *(_DWORD *)(v24 + 20) = 64;
    ElementCount = this->m_ResponseParameters.IncomingRequestInfo.AssocRequestFrame.ElementCount;
    *(_DWORD *)(v24 + 24) = ElementCount;
    if ( ElementCount )
      CopyMgmtFrameFromNetwork(
        0,
        v7,
        (__int16 *)(v24 + 64),
        this->m_ResponseParameters.IncomingRequestInfo.AssocRequestFrame.pElements,
        ElementCount);
    v28 = *(_DWORD *)(v24 + 24) + 64;
    *(_DWORD *)(v24 + 28) = v28;
    v29 = v53;
    *(_DWORD *)(v24 + 32) = v53;
    if ( v29 )
      CopyMgmtFrameFromNetwork(1, v7, (__int16 *)(v24 + v28), v54, v29);
    v30 = *(_DWORD *)(v24 + 32) + v28;
    *(_DWORD *)(v24 + 48) = v30;
    v31 = (unsigned int *)(v24 + v30);
    *(_DWORD *)(v24 + 52) = 4 * v59;
    v48 = 0;
    if ( v59 )
    {
      for ( i = v48; i < v59; ++i )
      {
        v33 = this->m_pAdapter->GetAdapterPropertyCache(&this->m_pAdapter->IPropertyCacheDirectory);
        CAdapterPropertyCache::GetDot11PhyIDFromPhyType(v33, *(_DWORD *)(v60 + 4LL * i), v31++);
      }
      v21 = v49;
    }
    v34 = v30 + *(_DWORD *)(v24 + 52);
    *(_DWORD *)(v24 + 56) = v34;
    v35 = v56;
    *(_DWORD *)(v24 + 60) = v56;
    if ( v35 )
      CopyMgmtFrameFromNetwork(5, v7, (__int16 *)(v24 + v34), v57, v35);
    m_PortId = this->m_PortId;
    m_pAdapter = this->m_pAdapter;
    this->m_pSendCompleteIndication = (unsigned __int8 *)v24;
    this->m_SendCompleteIndicationLength = v21;
    PortFromPortId = CAdapter::GetPortFromPortId(m_pAdapter, m_PortId);
    ((void (__fastcall *)(CConnectedPeerList *, __int64, __int64))PortFromPortId->m_pPeerList->AddPeer)(
      PortFromPortId->m_pPeerList,
      v24 + 4,
      3);
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v39) = 4;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v39,
        v40,
        62,
        (__int64)WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids,
        (char)this,
        this->m_ActivityId);
    }
    CAdapter::SetNextAllowedScanTime(this->m_pAdapter, 0x7530u);
    goto LABEL_9;
  }
  v9 = -1073741670;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v17 = 61;
    v44 = -1073741670;
    m_ActivityId = this->m_ActivityId;
LABEL_20:
    LOBYTE(v13) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      v14,
      v17,
      (__int64)WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids,
      (char)this,
      m_ActivityId,
      v44);
  }
LABEL_9:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v13) = 5;
    LODWORD(v42) = v9;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      v14,
      63,
      (__int64)WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids,
      (char)this,
      this->m_ActivityId,
      v42);
  }
LABEL_13:
  ArrayOfElements<enum _WDI_BAND_ID>::Cleanup(&v59);
  ArrayOfElements<enum _WDI_BAND_ID>::Cleanup(&v56);
  ArrayOfElements<enum _WDI_BAND_ID>::Cleanup(&v53);
  return v9;
}

```

## disassembly

```asm
0x140065cf0  push    rbp
0x140065cf2  push    rbx
0x140065cf3  push    rsi
0x140065cf4  push    rdi
0x140065cf5  push    r12
0x140065cf7  push    r13
0x140065cf9  push    r14
0x140065cfb  push    r15
0x140065cfd  lea     rbp, [rsp-7]
0x140065d02  sub     rsp, 0E8h
0x140065d09  mov     rax, cs:__security_cookie
0x140065d10  xor     rax, rsp
0x140065d13  mov     [rbp+3Fh+var_50], rax
0x140065d17  mov     r13, [rbp+3Fh+arg_28]
0x140065d1b  xor     eax, eax
0x140065d1d  mov     r14, [rbp+3Fh+arg_30]
0x140065d21  xor     r12d, r12d
0x140065d24  xorps   xmm0, xmm0
0x140065d27  mov     [rbp+3Fh+var_98], r12d
0x140065d2b  mov     [rbp+3Fh+var_90], r12
0x140065d2f  mov     r15b, r12b
0x140065d32  mov     [rbp+3Fh+var_88], r12b
0x140065d36  mov     esi, r9d
0x140065d39  mov     [rbp+3Fh+var_80], r12d
0x140065d3d  mov     edi, r8d
0x140065d40  mov     [rbp+3Fh+var_78], r12
0x140065d44  mov     rbx, rcx
0x140065d47  mov     [rbp+3Fh+var_70], r12b
0x140065d4b  mov     [rbp+3Fh+var_68], r12d
0x140065d4f  mov     [rbp+3Fh+var_60], r12
0x140065d53  mov     [rbp+3Fh+var_58], r12b
0x140065d57  mov     [rsp+120h+var_CC], r12d
0x140065d5c  mov     [rsp+120h+var_C0], r12
0x140065d61  mov     [rsp+120h+var_D0], r12b
0x140065d66  movups  [rbp+3Fh+var_B0], xmm0
0x140065d6a  mov     [rbp+3Fh+var_A0], eax
0x140065d6d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140065d74  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140065d7b  lea     rdx, WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids
0x140065d82  jz      short loc_140065DC8
0x140065d84  mov     rcx, cs:WPP_GLOBAL_Control
0x140065d8b  cmp     byte ptr [rcx+29h], 5
0x140065d8f  jnb     short loc_140065D98
0x140065d91  cmp     [rcx+48h], r12w
0x140065d96  jz      short loc_140065DC8
0x140065d98  mov     eax, [rbx+10h]
0x140065d9b  mov     r9d, 33h ; '3'
0x140065da1  mov     rcx, [rcx+40h]
0x140065da5  mov     [rsp+120h+var_F0], eax
0x140065da9  mov     [rsp+120h+var_F8], rbx
0x140065dae  mov     [rsp+120h+var_100], rdx
0x140065db3  mov     dl, 5
0x140065db5  call    WPP_RECORDER_SF_qD
0x140065dba  lea     rax, WPP_RECORDER_INITIALIZED
0x140065dc1  lea     rdx, WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids
0x140065dc8  mov     [r14], r12b
0x140065dcb  test    edi, edi
0x140065dcd  jz      loc_140065E98
0x140065dd3  cmp     cs:WPP_RECORDER_INITIALIZED, rax; __annotation("TMF:",
0x140065dda  jz      short loc_140065E5A
0x140065ddc  mov     r9d, 34h ; '4'
0x140065de2  mov     dword ptr [rsp+120h+var_E8], edi
0x140065de6  mov     rcx, cs:WPP_GLOBAL_Control
0x140065ded  mov     eax, [rbx+10h]
0x140065df0  mov     [rsp+120h+var_F0], eax
0x140065df4  mov     [rsp+120h+var_F8], rbx
0x140065df9  mov     rcx, [rcx+40h]
0x140065dfd  mov     [rsp+120h+var_100], rdx
0x140065e02  mov     dl, 2
0x140065e04  call    WPP_RECORDER_SF_qDD
0x140065e09  lea     rsi, WPP_RECORDER_INITIALIZED
0x140065e10  lea     r14, WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids
0x140065e17  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140065e1e  jz      short loc_140065E5A
0x140065e20  mov     rcx, cs:WPP_GLOBAL_Control
0x140065e27  cmp     byte ptr [rcx+29h], 5
0x140065e2b  jnb     short loc_140065E34
0x140065e2d  cmp     [rcx+48h], r12w
0x140065e32  jz      short loc_140065E5A
0x140065e34  mov     eax, [rbx+10h]
0x140065e37  mov     r9d, 3Fh ; '?'
0x140065e3d  mov     rcx, [rcx+40h]
0x140065e41  mov     dl, 5
0x140065e43  mov     dword ptr [rsp+120h+var_E8], edi
0x140065e47  mov     [rsp+120h+var_F0], eax
0x140065e4b  mov     [rsp+120h+var_F8], rbx
0x140065e50  mov     [rsp+120h+var_100], r14
0x140065e55  call    WPP_RECORDER_SF_qDD
0x140065e5a  lea     rcx, [rbp+3Fh+var_68]
0x140065e5e  call    ?Cleanup@?$ArrayOfElements@W4_WDI_BAND_ID@@@@QEAAXXZ; ArrayOfElements<_WDI_BAND_ID>::Cleanup(void)
0x140065e63  lea     rcx, [rbp+3Fh+var_80]
0x140065e67  call    ?Cleanup@?$ArrayOfElements@W4_WDI_BAND_ID@@@@QEAAXXZ; ArrayOfElements<_WDI_BAND_ID>::Cleanup(void)
0x140065e6c  lea     rcx, [rbp+3Fh+var_98]
0x140065e70  call    ?Cleanup@?$ArrayOfElements@W4_WDI_BAND_ID@@@@QEAAXXZ; ArrayOfElements<_WDI_BAND_ID>::Cleanup(void)
0x140065e75  mov     eax, edi
0x140065e77  mov     rcx, [rbp+3Fh+var_50]
0x140065e7b  xor     rcx, rsp; StackCookie
0x140065e7e  call    __security_check_cookie
0x140065e83  add     rsp, 0E8h
0x140065e8a  pop     r15
0x140065e8c  pop     r14
0x140065e8e  pop     r13
0x140065e90  pop     r12
0x140065e92  pop     rdi
0x140065e93  pop     rsi
0x140065e94  pop     rbx
0x140065e95  pop     rbp
0x140065e96  retn
0x140065e98  test    esi, esi
0x140065e9a  jz      short loc_140065EB6
0x140065e9c  mov     edi, esi
0x140065e9e  cmp     cs:WPP_RECORDER_INITIALIZED, rax; __annotation("TMF:",
0x140065ea5  jz      short loc_140065E5A
0x140065ea7  mov     r9d, 35h ; '5'
0x140065ead  mov     dword ptr [rsp+120h+var_E8], esi
0x140065eb1  jmp     loc_140065DE6
0x140065eb6  mov     r8, [rbx+200h]
0x140065ebd  lea     rdx, [r13+30h]
0x140065ec1  mov     ecx, [rbp+3Fh+arg_20]
0x140065ec4  lea     r9, [rbp+3Fh+var_B0]
0x140065ec8  add     r8, 3FF8h
0x140065ecf  add     ecx, 0FFFFFFD0h
0x140065ed2  call    ParseWdiIndicationSendApAssociationResponseCompleteFromIhv
0x140065ed7  mov     edi, eax
0x140065ed9  test    eax, eax
0x140065edb  jz      short loc_140065F2A
0x140065edd  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140065ee4  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140065eeb  jz      loc_140065E5A
0x140065ef1  mov     ecx, [rbx+10h]
0x140065ef4  mov     r9d, 36h ; '6'
0x140065efa  mov     dword ptr [rsp+120h+var_E8], eax
0x140065efe  mov     [rsp+120h+var_F0], ecx
0x140065f02  mov     rcx, cs:WPP_GLOBAL_Control
0x140065f09  lea     r14, WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids
0x140065f10  mov     [rsp+120h+var_F8], rbx
0x140065f15  mov     dl, 2
0x140065f17  mov     [rsp+120h+var_100], r14
0x140065f1c  mov     rcx, [rcx+40h]
0x140065f20  call    WPP_RECORDER_SF_qDD
0x140065f25  jmp     loc_140065E17
0x140065f2a  mov     ecx, [rbx+480h]
0x140065f30  mov     r9d, 40h ; '@'
0x140065f36  lea     eax, [rcx+40h]
0x140065f39  cmp     eax, r9d
0x140065f3c  jnb     short loc_140065F9C
0x140065f3e  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140065f45  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140065f4c  lea     r14, WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids
0x140065f53  jz      short loc_140065F92
0x140065f55  mov     r9d, 37h ; '7'
0x140065f5b  mov     dword ptr [rsp+120h+var_D8], 0FFFFFFFFh
0x140065f63  mov     dword ptr [rsp+120h+var_E0], ecx
0x140065f67  mov     rcx, cs:WPP_GLOBAL_Control
0x140065f6e  mov     dl, 2
0x140065f70  mov     eax, [rbx+10h]
0x140065f73  mov     dword ptr [rsp+120h+var_E8], 0C0000001h
0x140065f7b  mov     [rsp+120h+var_F0], eax
0x140065f7f  mov     rcx, [rcx+40h]
0x140065f83  mov     [rsp+120h+var_F8], rbx
0x140065f88  mov     [rsp+120h+var_100], r14
0x140065f8d  call    WPP_RECORDER_SF_qDDDD
0x140065f92  mov     edi, 0C0000001h
0x140065f97  jmp     loc_140065E17
0x140065f9c  mov     ecx, [rbp+3Fh+var_98]
0x140065f9f  cmp     ecx, 6
0x140065fa2  jnb     short loc_140065FF7
0x140065fa4  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140065fab  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140065fb2  lea     r14, WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids
0x140065fb9  jz      short loc_140065FED
0x140065fbb  mov     eax, [rbx+10h]
0x140065fbe  mov     r9d, 38h ; '8'
0x140065fc4  mov     dword ptr [rsp+120h+var_E0], ecx
0x140065fc8  mov     dl, 2
0x140065fca  mov     rcx, cs:WPP_GLOBAL_Control
0x140065fd1  mov     dword ptr [rsp+120h+var_E8], r12d
0x140065fd6  mov     [rsp+120h+var_F0], eax
0x140065fda  mov     [rsp+120h+var_F8], rbx
0x140065fdf  mov     rcx, [rcx+40h]
0x140065fe3  mov     [rsp+120h+var_100], r14
0x140065fe8  call    WPP_RECORDER_SF_qDdd
0x140065fed  mov     edi, 0C0010015h
0x140065ff2  jmp     loc_140065E17
0x140065ff7  lea     edx, [rax+rcx]
0x140065ffa  cmp     edx, eax
0x140065ffc  jnb     short loc_140066024
0x140065ffe  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140066005  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14006600c  lea     r14, WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids
0x140066013  jz      loc_140065F92
0x140066019  mov     r9d, 39h ; '9'
0x14006601f  jmp     loc_140065F5B
0x140066024  mov     r8d, [rbp+3Fh+var_68]
0x140066028  mov     eax, 0FFFFFFFFh
0x14006602d  mov     ecx, r8d
0x140066030  shl     rcx, 2
0x140066034  cmp     rcx, rax
0x140066037  ja      loc_14006632D
0x14006603d  lea     r8d, [rcx+rdx]
0x140066041  cmp     r8d, edx
0x140066044  jnb     short loc_140066070
0x140066046  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14006604d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140066054  lea     r14, WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids
0x14006605b  jz      loc_140065F92
0x140066061  mov     r9d, 3Bh ; ';'
0x140066067  mov     dword ptr [rsp+120h+var_D8], eax
0x14006606b  jmp     loc_140065F63
0x140066070  mov     ecx, [rbp+3Fh+var_80]
0x140066073  lea     r13d, [r8+rcx]
0x140066077  mov     [rsp+120h+var_C8], r13d
0x14006607c  cmp     r13d, r8d
0x14006607f  jnb     short loc_1400660A4
0x140066081  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140066088  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14006608f  lea     r14, WPP_b65a5b6e1195329bfe554b9f26932b28_Traceguids
0x140066096  jz      loc_140065F92
0x14006609c  mov     r9d, 3Ch ; '<'
0x1400660a2  jmp     short loc_140066067
0x1400660a4  mov     r14, [rbp+3Fh+var_90]
0x1400660a8  mov     r8d, 47696457h
0x1400660ae  mov     edx, r13d
0x1400660b1  mov     rcx, r9
0x1400660b4  call    cs:__imp_ExAllocatePool2
0x1400660bb  nop     dword ptr [rax+rax+00h]
0x1400660c0  mov     rsi, rax
0x1400660c3  test    rax, rax
0x1400660c6  jnz     short loc_1400660F9
0x1400660c8  mov     edi, 0C000009Ah
0x1400660cd  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400660d4  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400660db  jz      loc_140065E10
0x1400660e1  lea     r9d, [rax+3Dh]
0x1400660e5  mov     dword ptr [rsp+120h+var_E8], 0C000009Ah
0x1400660ed  mov     eax, [rbx+10h]
0x1400660f0  mov     [rsp+120h+var_F0], eax
0x1400660f4  jmp     loc_140065F02
0x1400660f9  mov     dword ptr [rax], 400180h
0x1400660ff  mov     eax, dword ptr [rbp+3Fh+var_B0]
0x140066102  mov     [rsi+4], eax
0x140066105  movzx   eax, word ptr [rbp+3Fh+var_B0+4]
0x140066109  mov     [rsi+8], ax
0x14006610d  movzx   eax, word ptr [r14+2]
0x140066112  mov     [rsi+0Ch], eax
0x140066115  cmp     [r14+2], r12w
0x14006611a  jz      short loc_140066120
0x14006611c  mov     byte ptr [rsi+10h], 1
0x140066120  mov     al, byte ptr [rbp+3Fh+var_B0+6]
0x140066123  mov     rcx, rbx; this
0x140066126  mov     [rsi+11h], al
0x140066129  mov     al, byte ptr [rbp+3Fh+var_B0+7]
0x14006612c  mov     [rsi+12h], al
0x14006612f  mov     eax, dword ptr [rbp+3Fh+var_B0+8]
0x140066132  mov     [rsi+24h], eax
0x140066135  mov     eax, dword ptr [rbp+3Fh+var_B0+0Ch]
0x140066138  mov     [rsi+28h], eax
0x14006613b  mov     eax, [rbp+3Fh+var_A0]
0x14006613e  mov     [rsi+2Ch], eax
0x140066141  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x140066146  lea     r9, [rsp+120h+var_C0]; unsigned __int8 **
0x14006614b  mov     edx, 46h ; 'F'; unsigned int
0x140066150  lea     r8, [rsp+120h+var_CC]; unsigned int *
0x140066155  mov     rcx, rax; this
0x140066158  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x14006615d  test    eax, eax
0x14006615f  jnz     short loc_1400661A0
0x140066161  cmp     [rsp+120h+var_CC], 10h
0x140066166  jnz     short loc_1400661A0
0x140066168  mov     rax, [rsp+120h+var_C0]
0x14006616d  cmp     dword ptr [rax], 3
0x140066170  jnz     short loc_1400661A0
0x140066172  mov     rcx, [rbx+200h]
0x140066179  add     rcx, 8
0x14006617d  mov     rax, [rcx]
0x140066180  mov     rax, [rax+8]
0x140066184  call    _guard_dispatch_icall
0x140066189  lea     r8, [rsp+120h+var_D0]; unsigned __int8 *
0x14006618e  mov     edx, 86h; unsigned int
0x140066193  mov     rcx, rax; this
0x140066196  call    ?GetPropertyUchar@CPropertyCache@@QEAAHKPEAE@Z; CPropertyCache::GetPropertyUchar(ulong,uchar *)
0x14006619b  mov     r15b, [rsp+120h+var_D0]
0x1400661a0  mov     dword ptr [rsi+14h], 40h ; '@'
0x1400661a7  mov     eax, [rbx+480h]
0x1400661ad  mov     [rsi+18h], eax
0x1400661b0  test    eax, eax
0x1400661b2  jz      short loc_1400661CD
0x1400661b4  mov     r9, [rbx+488h]
0x1400661bb  lea     r8, [rsi+40h]
0x1400661bf  mov     dl, r15b
0x1400661c2  mov     dword ptr [rsp+120h+var_100], eax
0x1400661c6  xor     ecx, ecx
0x1400661c8  call    ?CopyMgmtFrameFromNetwork@@YAHW4DOT11_MGMT_SUBTYPE@@EPEAE1K@Z; CopyMgmtFrameFromNetwork(DOT11_MGMT_SUBTYPE,uchar,uchar *,uchar *,ulong)
0x1400661cd  mov     r14d, [rsi+18h]
0x1400661d1  add     r14d, 40h ; '@'
0x1400661d5  mov     [rsi+1Ch], r14d
0x1400661d9  mov     eax, [rbp+3Fh+var_98]
0x1400661dc  mov     [rsi+20h], eax
0x1400661df  test    eax, eax
0x1400661e1  jz      short loc_1400661FE
  ... truncated ...
```
