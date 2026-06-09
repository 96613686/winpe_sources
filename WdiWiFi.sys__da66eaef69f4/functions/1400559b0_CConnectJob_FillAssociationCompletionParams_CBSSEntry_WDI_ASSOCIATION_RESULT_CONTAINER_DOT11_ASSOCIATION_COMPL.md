# CConnectJob::FillAssociationCompletionParams(CBSSEntry *,_WDI_ASSOCIATION_RESULT_CONTAINER *,DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS * *,ulong *,uchar *)

- ea: `0x1400559b0`
- end: `0x140055f8a`
- name: `?FillAssociationCompletionParams@CConnectJob@@AEAAKPEAVCBSSEntry@@PEAU_WDI_ASSOCIATION_RESULT_CONTAINER@@PEAPEAUDOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS@@PEAKPEAE@Z`
- size: `1498`
- prototype: `unsigned int __usercall@<eax>(CConnectJob *__hidden this@<rcx>, struct CBSSEntry *@<rdx>, struct _WDI_ASSOCIATION_RESULT_CONTAINER *@<r8>, struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS **@<r9>, unsigned int *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400556b8`

## callees

- `0x140010730`
- `0x140010b20`
- `0x1400147e8`
- `0x1400559b0`
- `0x1400574c0`
- `0x140057794`
- `0x1400579f0`
- `0x14005f628`
- `0x1400da680`
- `0x1400da740`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140055ab2`
- `ntoskrnl!ExAllocatePool2` at `0x140055ab2`

## pseudocode

```c
__int64 __fastcall CConnectJob::FillAssociationCompletionParams(
        CConnectJob *this,
        struct CBSSEntry *a2,
        struct _WDI_ASSOCIATION_RESULT_CONTAINER *a3,
        struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS **a4,
        unsigned int *a5,
        unsigned __int8 *a6)
{
  unsigned __int8 *v6; // rax
  DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *Src; // r14
  bool v11; // zf
  char v12; // r13
  CAdapterPropertyCache *v13; // rax
  int v14; // edx
  unsigned int v15; // ebx
  int v16; // r8d
  int v17; // edx
  struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *Pool2; // rdi
  int v19; // r8d
  size_t v20; // r8
  int v21; // edx
  int v22; // r8d
  int v23; // eax
  _WDI_ASSOC_STATUS AssociationStatus; // ecx
  int StatusCode_low; // r8d
  struct CPortPropertyCache *PortPropertyCache; // rax
  bool v28; // [rsp+40h] [rbp-18h]
  unsigned __int8 v29; // [rsp+A0h] [rbp+48h] BYREF
  struct CBSSEntry *v30; // [rsp+A8h] [rbp+50h]
  size_t Size; // [rsp+B0h] [rbp+58h] BYREF
  struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS **v32; // [rsp+B8h] [rbp+60h]

  v32 = a4;
  v30 = a2;
  v6 = a6;
  Src = &this->m_StaticAssociationCompletionExParameters;
  *a4 = 0;
  *v6 = 0;
  *a5 = 0;
  memset(&this->m_StaticAssociationCompletionExParameters, 0, sizeof(this->m_StaticAssociationCompletionExParameters));
  v11 = a3->AssociationResultParameters.BandID == WDI_BAND_ID_60000;
  v28 = 0;
  v12 = 0;
  v29 = 0;
  if ( v11 )
  {
    v13 = this->m_pAdapter->GetAdapterPropertyCache(&this->m_pAdapter->IPropertyCacheDirectory);
    CPropertyCache::GetPropertyUchar(v13, 0x86u, &v29);
    v12 = v29;
    if ( v29 )
      v28 = (a2->m_OriginalProbeFrameCapability.DMG.DMGParameters.ucValue & 3) == 2;
  }
  LODWORD(Size) = 0;
  v15 = CConnectJob::SetAssociationCompletionOffsetData(this, a2, a3, 0x74u, Src, v12, 1u, (unsigned int *)&Size);
  if ( v15 )
  {
    Pool2 = 0;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_qDL(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        v16,
        84,
        (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
        (char)this,
        this->m_ActivityId,
        v15);
      goto LABEL_10;
    }
  }
  else
  {
    Pool2 = (struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *)ExAllocatePool2(64, (unsigned int)Size, 1198089303);
    if ( !Pool2 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v17) = 2;
        WPP_RECORDER_SF_qDL(
          WPP_GLOBAL_Control->DeviceExtension,
          v17,
          v19,
          83,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
          (char)this,
          this->m_ActivityId,
          Size);
      }
      v15 = 10;
    }
  }
  if ( v15 )
  {
LABEL_10:
    LODWORD(Size) = 116;
    Pool2 = Src;
    memset(Src, 0, sizeof(DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS));
    goto LABEL_14;
  }
  v20 = (unsigned int)Size;
  *a6 = 1;
  memset(Pool2, 0, v20);
  *(_OWORD *)&Pool2->CompletionParams.Header.Type = *(_OWORD *)&Src->CompletionParams.Header.Type;
  *(_OWORD *)&Pool2->CompletionParams.bReAssocReq = *(_OWORD *)&Src->CompletionParams.bReAssocReq;
  *(_OWORD *)&Pool2->CompletionParams.uAssocRespSize = *(_OWORD *)&Src->CompletionParams.uAssocRespSize;
  *(_OWORD *)&Pool2->CompletionParams.uIHVDataSize = *(_OWORD *)&Src->CompletionParams.uIHVDataSize;
  *(_OWORD *)&Pool2->CompletionParams.uActivePhyListOffset = *(_OWORD *)&Src->CompletionParams.uActivePhyListOffset;
  *(_OWORD *)&Pool2->CompletionParams.uEncapTableOffset = *(_OWORD *)&Src->CompletionParams.uEncapTableOffset;
  *(_OWORD *)&Pool2->AssociationType = *(_OWORD *)&Src->AssociationType;
  Pool2->ftMicDataSize = Src->ftMicDataSize;
LABEL_14:
  *(_DWORD *)Pool2->CompletionParams.MacAddr = *(_DWORD *)a3->BSSID.Address;
  *(_WORD *)&Pool2->CompletionParams.MacAddr[4] = *(_WORD *)&a3->BSSID.Address[4];
  Pool2->CompletionParams.bReAssocReq = a3->AssociationResultParameters.ReAssociation;
  Pool2->CompletionParams.bReAssocResp = a3->AssociationResultParameters.ReAssociation;
  Pool2->CompletionParams.AuthAlgo = CWabiToDot11Converter::MapAuthAlgorithm(a3->AssociationResultParameters.AuthAlgorithm);
  Pool2->CompletionParams.UnicastCipher = CWabiToDot11Converter::MapCipherAlgorithm(a3->AssociationResultParameters.UnicastCipherAlgorithm);
  Pool2->CompletionParams.MulticastCipher = CWabiToDot11Converter::MapCipherAlgorithm(a3->AssociationResultParameters.MulticastDataCipherAlgorithm);
  Pool2->CompletionParams.MulticastMgmtCipher = CWabiToDot11Converter::MapCipherAlgorithm(a3->AssociationResultParameters.MulticastMgmtCipherAlgorithm);
  Pool2->CompletionParams.bFourAddressSupported = a3->AssociationResultParameters.FourAddressSupported;
  Pool2->CompletionParams.bPortAuthorized = a3->AssociationResultParameters.PortAuthorized;
  Pool2->CompletionParams.ucActiveQoSProtocol = a3->AssociationResultParameters.WMMQoSEnabled != 0;
  if ( a3->AssociationResultParameters.DSInfo == WDI_DS_CHANGED )
  {
    v23 = 0;
  }
  else if ( a3->AssociationResultParameters.DSInfo == WDI_DS_UNCHANGED )
  {
    v23 = 1;
  }
  else
  {
    v23 = 2;
  }
  Pool2->CompletionParams.DSInfo = v23;
  Pool2->CompletionParams.uAssocComebackTime = a3->AssociationResultParameters.AssociationComebackTime;
  if ( !v15 )
  {
    v15 = CConnectJob::SetAssociationCompletionOffsetData(this, v30, a3, Size, Pool2, v12, 0, (unsigned int *)&Size);
    if ( v15 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v21) = 2;
        WPP_RECORDER_SF_qDL(
          WPP_GLOBAL_Control->DeviceExtension,
          v21,
          v22,
          85,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
          (char)this,
          this->m_ActivityId,
          v15);
      }
    }
  }
  AssociationStatus = a3->AssociationResultParameters.AssociationStatus;
  if ( AssociationStatus )
  {
    v15 = 0x1000000;
    if ( AssociationStatus > WDI_ASSOC_STATUS_RESERVED_0 )
    {
      v15 = 16777217;
      if ( AssociationStatus == WDI_ASSOC_STATUS_RESERVED_1 )
        goto LABEL_94;
      if ( AssociationStatus == WDI_ASSOC_STATUS_RESERVED_2 )
      {
        v15 = 16777218;
        goto LABEL_94;
      }
      goto LABEL_90;
    }
    if ( AssociationStatus == WDI_ASSOC_STATUS_RESERVED_0 )
      goto LABEL_94;
  }
  else if ( v15 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v21) = 2;
      WPP_RECORDER_SF_qDL(
        WPP_GLOBAL_Control->DeviceExtension,
        v21,
        v22,
        86,
        (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
        (char)this,
        this->m_ActivityId,
        v15);
    }
    goto LABEL_94;
  }
  StatusCode_low = LOWORD(a3->AssociationResultParameters.StatusCode);
  v15 = 40;
  if ( AssociationStatus <= WDI_ASSOC_STATUS_AUTH_REQUEST_NO_ACK )
  {
    if ( AssociationStatus == WDI_ASSOC_STATUS_AUTH_REQUEST_NO_ACK )
      goto LABEL_94;
    v15 = 7;
    if ( AssociationStatus > WDI_ASSOC_STATUS_DISASSOCIATED_BY_HOST )
    {
      switch ( AssociationStatus )
      {
        case WDI_ASSOC_STATUS_ROAMING_BETTER_AP_FOUND:
          v15 = 11;
          goto LABEL_94;
        case WDI_ASSOC_STATUS_ROAMING_ASSOCIATION_LOST:
          v15 = 12;
          goto LABEL_94;
        case WDI_ASSOC_STATUS_PEER_DEAUTHENTICATED:
          v15 = StatusCode_low | 0x10000;
          goto LABEL_94;
        case WDI_ASSOC_STATUS_PEER_DISASSOCIATED:
          v15 = StatusCode_low | 0x20000;
          goto LABEL_94;
        case WDI_ASSOC_STATUS_ROAMING_LOW_LINK_QUALITY:
          v15 = 15;
          goto LABEL_94;
        case WDI_ASSOC_STATUS_PROBE_TX_FAILURE:
          v15 = 30;
          goto LABEL_94;
        case WDI_ASSOC_STATUS_NO_BEACON_PROBE_RESPONSE:
          v15 = 31;
          goto LABEL_94;
      }
    }
    else
    {
      switch ( AssociationStatus )
      {
        case WDI_ASSOC_STATUS_DISASSOCIATED_BY_HOST:
          goto LABEL_94;
        case WDI_ASSOC_STATUS_SUCCESS:
          v15 = 0;
          goto LABEL_94;
        case WDI_ASSOC_STATUS_FAILURE:
          v15 = 1;
          goto LABEL_94;
        case WDI_ASSOC_STATUS_UNREACHABLE:
          v15 = 2;
          goto LABEL_94;
        case WDI_ASSOC_STATUS_RADIO_OFF:
          v15 = 3;
          goto LABEL_94;
        case WDI_ASSOC_STATUS_PHY_DISABLED:
          v15 = 4;
          goto LABEL_94;
        case WDI_ASSOC_STATUS_ABORTED:
          v15 = 5;
          goto LABEL_94;
        case WDI_ASSOC_STATUS_CANDIDATE_LIST_EXHAUSTED:
          v15 = 6;
          goto LABEL_94;
      }
    }
    goto LABEL_90;
  }
  v15 = 52;
  if ( AssociationStatus <= WDI_ASSOC_STATUS_ASSOC_RESPONSE_CAPABILITY_MISMATCH )
  {
    if ( AssociationStatus == WDI_ASSOC_STATUS_ASSOC_RESPONSE_CAPABILITY_MISMATCH )
      goto LABEL_94;
    v15 = 41;
    switch ( AssociationStatus )
    {
      case WDI_ASSOC_STATUS_NO_AUTH_RESPONSE:
        goto LABEL_94;
      case WDI_ASSOC_STATUS_AUTH_RESPONSE_CAPABILITY_MISMATCH:
        v15 = 42;
        goto LABEL_94;
      case WDI_ASSOC_STATUS_BAD_AUTH_RESPONSE:
        v15 = 43;
        goto LABEL_94;
    }
    if ( AssociationStatus != WDI_ASSOC_STATUS_AUTH_FAILED_BY_PEER )
    {
      switch ( AssociationStatus )
      {
        case WDI_ASSOC_STATUS_AUTH_EXCHANGE_FAILURE:
          v15 = 45;
          goto LABEL_94;
        case WDI_ASSOC_STATUS_ASSOC_REQUEST_NO_ACK:
          v15 = 50;
          goto LABEL_94;
        case WDI_ASSOC_STATUS_NO_ASSOC_RESPONSE:
          v15 = 51;
          goto LABEL_94;
      }
      goto LABEL_90;
    }
LABEL_73:
    v15 = StatusCode_low | 0x30000;
    goto LABEL_94;
  }
  v15 = 53;
  switch ( AssociationStatus )
  {
    case WDI_ASSOC_STATUS_BAD_ASSOC_RESPONSE:
      goto LABEL_94;
    case WDI_ASSOC_STATUS_ASSOC_FAILED_BY_PEER:
      goto LABEL_73;
    case WDI_ASSOC_STATUS_ASSOC_EXCHANGE_FAILURE:
      v15 = 55;
      goto LABEL_94;
    case WDI_ASSOC_STATUS_DISASSOCIATE_BY_DEVICE_RESET:
      v15 = 60;
      goto LABEL_94;
    case WDI_ASSOC_STATUS_DISASSOCIATE_UNABLE_TO_MAINTAIN:
      v15 = 61;
      goto LABEL_94;
    case WDI_ASSOC_STATUS_DISASSOCIATE_NOT_VISIBLE:
      v15 = 62;
      goto LABEL_94;
    case WDI_ASSOC_STATUS_DISASSOCIATE_NEEDED_REASSOC:
      v15 = 63;
      goto LABEL_94;
  }
LABEL_90:
  v15 = 1;
  if ( (unsigned int)AssociationStatus > 0x80000000 )
    v15 = a3->AssociationResultParameters.AssociationStatus;
LABEL_94:
  Pool2->CompletionParams.uStatus = v15;
  LOBYTE(a6) = 0;
  PortPropertyCache = COidJobBase::GetPortPropertyCache(this);
  CPropertyCache::GetPropertyUchar(PortPropertyCache, 0x14u, (unsigned __int8 *)&a6);
  if ( this->m_IsRoam
    && (_BYTE)a6
    && !CConnectHelpers::IsIMDAssocForFTRoamRequired(this->m_RoamWabiReason, this->m_RoamConfigFlags) )
  {
    Pool2->AssociationType = DOT11_ASSOCIATION_TYPE_FT;
  }
  else
  {
    Pool2->AssociationType = v28 ? DOT11_ASSOCIATION_TYPE_PBSS_NOT_IN_DS : DOT11_ASSOCIATION_TYPE_GENERAL;
  }
  *a5 = Size;
  *v32 = Pool2;
  return v15;
}

```

## disassembly

```asm
0x1400559b0  mov     [rsp-40h+arg_18], r9
0x1400559b5  mov     [rsp-40h+arg_8], rdx
0x1400559ba  push    rbp
0x1400559bb  push    rbx
0x1400559bc  push    rsi
0x1400559bd  push    rdi
0x1400559be  push    r12
0x1400559c0  push    r13
0x1400559c2  push    r14
0x1400559c4  push    r15
0x1400559c6  mov     rbp, rsp
0x1400559c9  sub     rsp, 58h
0x1400559cd  mov     rax, [rbp+arg_28]
0x1400559d1  lea     r14, [rcx+4ACh]
0x1400559d8  xor     r12d, r12d
0x1400559db  mov     r15, r8
0x1400559de  mov     rbx, rdx
0x1400559e1  mov     [r9], r12
0x1400559e4  mov     rsi, rcx
0x1400559e7  xor     edx, edx; Val
0x1400559e9  mov     [rax], r12b
0x1400559ec  mov     rcx, r14; void *
0x1400559ef  mov     rax, [rbp+arg_20]
0x1400559f3  lea     r8d, [r12+74h]; Size
0x1400559f8  mov     [rax], r12d
0x1400559fb  call    memset
0x140055a00  cmp     dword ptr [r15+34h], 3
0x140055a05  mov     dil, r12b
0x140055a08  mov     dword ptr [rbp+var_18], edi
0x140055a0b  mov     r13b, r12b
0x140055a0e  mov     [rbp+arg_0], r12b
0x140055a12  jnz     short loc_140055A5E
0x140055a14  mov     rcx, [rsi+200h]
0x140055a1b  add     rcx, 8
0x140055a1f  mov     rax, [rcx]
0x140055a22  mov     rax, [rax+8]
0x140055a26  call    _guard_dispatch_icall
0x140055a2b  lea     r8, [rbp+arg_0]; unsigned __int8 *
0x140055a2f  mov     edx, 86h; unsigned int
0x140055a34  mov     rcx, rax; this
0x140055a37  call    ?GetPropertyUchar@CPropertyCache@@QEAAHKPEAE@Z; CPropertyCache::GetPropertyUchar(ulong,uchar *)
0x140055a3c  mov     r13b, [rbp+arg_0]
0x140055a40  test    r13b, r13b
0x140055a43  jz      short loc_140055A5E
0x140055a45  mov     al, [rbx+27Dh]
0x140055a4b  lea     ecx, [r12+1]
0x140055a50  and     al, 3
0x140055a52  movzx   edi, r12b
0x140055a56  cmp     al, 2
0x140055a58  cmovz   edi, ecx
0x140055a5b  mov     dword ptr [rbp+var_18], edi
0x140055a5e  lea     rax, [rbp+Size]
0x140055a62  mov     dword ptr [rbp+Size], r12d
0x140055a66  mov     [rsp+58h+var_20], rax; unsigned int *
0x140055a6b  mov     r9d, 74h ; 't'; unsigned int
0x140055a71  mov     [rsp+58h+var_28], 1; unsigned __int8
0x140055a76  mov     r8, r15; struct _WDI_ASSOCIATION_RESULT_CONTAINER *
0x140055a79  mov     [rsp+58h+var_30], r13b; unsigned __int8
0x140055a7e  mov     rdx, rbx; struct CBSSEntry *
0x140055a81  mov     rcx, rsi; this
0x140055a84  mov     [rsp+58h+Src], r14; Src
0x140055a89  call    ?SetAssociationCompletionOffsetData@CConnectJob@@AEAAKPEAVCBSSEntry@@PEAU_WDI_ASSOCIATION_RESULT_CONTAINER@@KPEAUDOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS@@EEPEAK@Z; CConnectJob::SetAssociationCompletionOffsetData(CBSSEntry *,_WDI_ASSOCIATION_RESULT_CONTAINER *,ulong,DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *,uchar,uchar,ulong *)
0x140055a8e  mov     ebx, eax
0x140055a90  lea     r12, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x140055a97  lea     rax, WPP_RECORDER_INITIALIZED
0x140055a9e  test    ebx, ebx
0x140055aa0  jnz     loc_140055B2A
0x140055aa6  mov     edx, dword ptr [rbp+Size]
0x140055aa9  lea     ecx, [rbx+40h]
0x140055aac  mov     r8d, 47696457h
0x140055ab2  call    cs:__imp_ExAllocatePool2
0x140055ab9  nop     dword ptr [rax+rax+00h]
0x140055abe  mov     rdi, rax
0x140055ac1  test    rax, rax
0x140055ac4  jnz     short loc_140055B09
0x140055ac6  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140055acd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140055ad4  jz      short loc_140055B04
0x140055ad6  mov     ecx, dword ptr [rbp+Size]
0x140055ad9  lea     r9d, [rbx+53h]
0x140055add  mov     dword ptr [rsp+58h+var_20], ecx
0x140055ae1  mov     dl, 2
0x140055ae3  mov     ecx, [rsi+10h]
0x140055ae6  mov     dword ptr [rsp+58h+var_28], ecx
0x140055aea  mov     rcx, cs:WPP_GLOBAL_Control
0x140055af1  mov     qword ptr [rsp+58h+var_30], rsi
0x140055af6  mov     [rsp+58h+Src], r12
0x140055afb  mov     rcx, [rcx+40h]
0x140055aff  call    WPP_RECORDER_SF_qDL
0x140055b04  mov     ebx, 0Ah
0x140055b09  test    ebx, ebx
0x140055b0b  jz      short loc_140055B69
0x140055b0d  mov     eax, 74h ; 't'
0x140055b12  xor     edx, edx; Val
0x140055b14  mov     r8d, eax; Size
0x140055b17  mov     dword ptr [rbp+Size], eax
0x140055b1a  mov     rcx, r14; void *
0x140055b1d  mov     rdi, r14
0x140055b20  call    memset
0x140055b25  jmp     loc_140055BC2
0x140055b2a  xor     edi, edi; __annotation("TMF:",
0x140055b2c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140055b33  jz      short loc_140055B09
0x140055b35  mov     rcx, cs:WPP_GLOBAL_Control
0x140055b3c  lea     r12, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x140055b43  mov     eax, [rsi+10h]
0x140055b46  lea     r9d, [rdi+54h]
0x140055b4a  mov     dword ptr [rsp+58h+var_20], ebx
0x140055b4e  mov     dl, 2
0x140055b50  mov     dword ptr [rsp+58h+var_28], eax
0x140055b54  mov     rcx, [rcx+40h]
0x140055b58  mov     qword ptr [rsp+58h+var_30], rsi
0x140055b5d  mov     [rsp+58h+Src], r12
0x140055b62  call    WPP_RECORDER_SF_qDL
0x140055b67  jmp     short loc_140055B0D
0x140055b69  mov     rax, [rbp+arg_28]
0x140055b6d  xor     edx, edx; Val
0x140055b6f  mov     r8d, dword ptr [rbp+Size]; Size
0x140055b73  mov     rcx, rdi; void *
0x140055b76  mov     byte ptr [rax], 1
0x140055b79  call    memset
0x140055b7e  movups  xmm0, xmmword ptr [r14]
0x140055b82  movups  xmmword ptr [rdi], xmm0
0x140055b85  movups  xmm1, xmmword ptr [r14+10h]
0x140055b8a  movups  xmmword ptr [rdi+10h], xmm1
0x140055b8e  movups  xmm0, xmmword ptr [r14+20h]
0x140055b93  movups  xmmword ptr [rdi+20h], xmm0
0x140055b97  movups  xmm1, xmmword ptr [r14+30h]
0x140055b9c  movups  xmmword ptr [rdi+30h], xmm1
0x140055ba0  movups  xmm0, xmmword ptr [r14+40h]
0x140055ba5  movups  xmmword ptr [rdi+40h], xmm0
0x140055ba9  movups  xmm1, xmmword ptr [r14+50h]
0x140055bae  movups  xmmword ptr [rdi+50h], xmm1
0x140055bb2  movups  xmm0, xmmword ptr [r14+60h]
0x140055bb7  movups  xmmword ptr [rdi+60h], xmm0
0x140055bbb  mov     eax, [r14+70h]
0x140055bbf  mov     [rdi+70h], eax
0x140055bc2  mov     eax, [r15+4]
0x140055bc6  mov     [rdi+4], eax
0x140055bc9  movzx   eax, word ptr [r15+8]
0x140055bce  mov     [rdi+8], ax
0x140055bd2  mov     al, [r15+14h]
0x140055bd6  mov     [rdi+10h], al
0x140055bd9  mov     al, [r15+14h]
0x140055bdd  mov     [rdi+11h], al
0x140055be0  mov     ecx, [r15+18h]; enum _WDI_AUTH_ALGORITHM
0x140055be4  call    ?MapAuthAlgorithm@CWabiToDot11Converter@@SA?AW4_DOT11_AUTH_ALGORITHM@@W4_WDI_AUTH_ALGORITHM@@@Z; CWabiToDot11Converter::MapAuthAlgorithm(_WDI_AUTH_ALGORITHM)
0x140055be9  mov     [rdi+34h], eax
0x140055bec  mov     ecx, [r15+1Ch]; enum _WDI_CIPHER_ALGORITHM
0x140055bf0  call    ?MapCipherAlgorithm@CWabiToDot11Converter@@SA?AW4_DOT11_CIPHER_ALGORITHM@@W4_WDI_CIPHER_ALGORITHM@@@Z; CWabiToDot11Converter::MapCipherAlgorithm(_WDI_CIPHER_ALGORITHM)
0x140055bf5  mov     [rdi+38h], eax
0x140055bf8  mov     ecx, [r15+20h]; enum _WDI_CIPHER_ALGORITHM
0x140055bfc  call    ?MapCipherAlgorithm@CWabiToDot11Converter@@SA?AW4_DOT11_CIPHER_ALGORITHM@@W4_WDI_CIPHER_ALGORITHM@@@Z; CWabiToDot11Converter::MapCipherAlgorithm(_WDI_CIPHER_ALGORITHM)
0x140055c01  mov     [rdi+3Ch], eax
0x140055c04  mov     ecx, [r15+24h]; enum _WDI_CIPHER_ALGORITHM
0x140055c08  call    ?MapCipherAlgorithm@CWabiToDot11Converter@@SA?AW4_DOT11_CIPHER_ALGORITHM@@W4_WDI_CIPHER_ALGORITHM@@@Z; CWabiToDot11Converter::MapCipherAlgorithm(_WDI_CIPHER_ALGORITHM)
0x140055c0d  mov     [rdi+58h], eax
0x140055c10  xor     r14d, r14d
0x140055c13  mov     al, [r15+28h]
0x140055c17  mov     [rdi+48h], al
0x140055c1a  mov     al, [r15+29h]
0x140055c1e  mov     [rdi+49h], al
0x140055c21  cmp     [r15+2Ah], r14b
0x140055c25  setnz   al
0x140055c28  mov     [rdi+4Ah], al
0x140055c2b  mov     ecx, [r15+2Ch]
0x140055c2f  sub     ecx, 1
0x140055c32  jz      short loc_140055C46
0x140055c34  sub     ecx, 1
0x140055c37  jz      short loc_140055C3F
0x140055c39  lea     eax, [r14+2]
0x140055c3d  jmp     short loc_140055C49
0x140055c3f  mov     eax, 1
0x140055c44  jmp     short loc_140055C49
0x140055c46  mov     eax, r14d
0x140055c49  mov     [rdi+4Ch], eax
0x140055c4c  mov     eax, [r15+30h]
0x140055c50  mov     [rdi+5Ch], eax
0x140055c53  test    ebx, ebx
0x140055c55  jnz     short loc_140055CC5
0x140055c57  mov     r9d, dword ptr [rbp+Size]; unsigned int
0x140055c5b  lea     rax, [rbp+Size]
0x140055c5f  mov     rdx, [rbp+arg_8]; struct CBSSEntry *
0x140055c63  mov     r8, r15; struct _WDI_ASSOCIATION_RESULT_CONTAINER *
0x140055c66  mov     [rsp+58h+var_20], rax; unsigned int *
0x140055c6b  mov     rcx, rsi; this
0x140055c6e  mov     [rsp+58h+var_28], r14b; unsigned __int8
0x140055c73  mov     [rsp+58h+var_30], r13b; unsigned __int8
0x140055c78  mov     [rsp+58h+Src], rdi; Src
0x140055c7d  call    ?SetAssociationCompletionOffsetData@CConnectJob@@AEAAKPEAVCBSSEntry@@PEAU_WDI_ASSOCIATION_RESULT_CONTAINER@@KPEAUDOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS@@EEPEAK@Z; CConnectJob::SetAssociationCompletionOffsetData(CBSSEntry *,_WDI_ASSOCIATION_RESULT_CONTAINER *,ulong,DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *,uchar,uchar,ulong *)
0x140055c82  mov     ebx, eax
0x140055c84  test    eax, eax
0x140055c86  jz      short loc_140055CC5
0x140055c88  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140055c8f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140055c96  jz      short loc_140055CCC
0x140055c98  mov     rcx, cs:WPP_GLOBAL_Control
0x140055c9f  mov     r9d, 55h ; 'U'
0x140055ca5  mov     eax, [rsi+10h]
0x140055ca8  mov     dl, 2
0x140055caa  mov     dword ptr [rsp+58h+var_20], ebx
0x140055cae  mov     dword ptr [rsp+58h+var_28], eax
0x140055cb2  mov     rcx, [rcx+40h]
0x140055cb6  mov     qword ptr [rsp+58h+var_30], rsi
0x140055cbb  mov     [rsp+58h+Src], r12
0x140055cc0  call    WPP_RECORDER_SF_qDL
0x140055cc5  lea     rax, WPP_RECORDER_INITIALIZED
0x140055ccc  mov     ecx, [r15+0Ch]
0x140055cd0  test    ecx, ecx
0x140055cd2  jnz     short loc_140055D15
0x140055cd4  test    ebx, ebx
0x140055cd6  jz      short loc_140055D28
0x140055cd8  cmp     cs:WPP_RECORDER_INITIALIZED, rax; __annotation("TMF:",
0x140055cdf  jz      loc_140055F0E
0x140055ce5  mov     eax, [rsi+10h]
0x140055ce8  lea     r9d, [rcx+56h]
0x140055cec  mov     rcx, cs:WPP_GLOBAL_Control
0x140055cf3  mov     dl, 2
0x140055cf5  mov     dword ptr [rsp+58h+var_20], ebx
0x140055cf9  mov     dword ptr [rsp+58h+var_28], eax
0x140055cfd  mov     qword ptr [rsp+58h+var_30], rsi
0x140055d02  mov     rcx, [rcx+40h]
0x140055d06  mov     [rsp+58h+Src], r12
0x140055d0b  call    WPP_RECORDER_SF_qDL
0x140055d10  jmp     loc_140055F0E
0x140055d15  mov     ebx, 1000000h
0x140055d1a  cmp     ecx, ebx
0x140055d1c  jg      loc_140055EE9
0x140055d22  jz      loc_140055F0E
0x140055d28  movzx   r8d, word ptr [r15+10h]
0x140055d2d  mov     ebx, 28h ; '('
0x140055d32  cmp     ecx, ebx
0x140055d34  jg      loc_140055E2A
0x140055d3a  jz      loc_140055F0E
0x140055d40  mov     ebx, 7
0x140055d45  cmp     ecx, ebx
0x140055d47  jg      short loc_140055DB9
0x140055d49  jz      loc_140055F0E
0x140055d4f  mov     edx, ecx
0x140055d51  test    ecx, ecx
0x140055d53  jz      short loc_140055DB1
0x140055d55  sub     edx, 1
0x140055d58  jz      short loc_140055DA7
0x140055d5a  sub     edx, 1
0x140055d5d  jz      short loc_140055D9D
0x140055d5f  sub     edx, 1
0x140055d62  jz      short loc_140055D93
0x140055d64  sub     edx, 1
0x140055d67  jz      short loc_140055D89
0x140055d69  sub     edx, 1
0x140055d6c  jz      short loc_140055D7F
0x140055d6e  cmp     edx, 1
0x140055d71  jnz     loc_140055EF9
0x140055d77  lea     ebx, [rdx+5]
0x140055d7a  jmp     loc_140055F0E
0x140055d7f  mov     ebx, 5
0x140055d84  jmp     loc_140055F0E
0x140055d89  mov     ebx, 4
0x140055d8e  jmp     loc_140055F0E
0x140055d93  mov     ebx, 3
0x140055d98  jmp     loc_140055F0E
0x140055d9d  mov     ebx, 2
0x140055da2  jmp     loc_140055F0E
0x140055da7  mov     ebx, 1
0x140055dac  jmp     loc_140055F0E
0x140055db1  mov     ebx, r14d
0x140055db4  jmp     loc_140055F0E
0x140055db9  mov     edx, ecx
0x140055dbb  sub     edx, 0Ah
0x140055dbe  jz      short loc_140055E20
0x140055dc0  sub     edx, 1
0x140055dc3  jz      short loc_140055E16
0x140055dc5  sub     edx, 2
0x140055dc8  jz      short loc_140055E0A
0x140055dca  sub     edx, 1
0x140055dcd  jz      short loc_140055DFE
0x140055dcf  sub     edx, 1
0x140055dd2  jz      short loc_140055DF4
0x140055dd4  sub     edx, 0Fh
0x140055dd7  jz      short loc_140055DEA
0x140055dd9  cmp     edx, 1
0x140055ddc  jnz     loc_140055EF9
0x140055de2  lea     ebx, [rdx+1Eh]
0x140055de5  jmp     loc_140055F0E
0x140055dea  mov     ebx, 1Eh
0x140055def  jmp     loc_140055F0E
0x140055df4  mov     ebx, 0Fh
0x140055df9  jmp     loc_140055F0E
0x140055dfe  mov     ebx, r8d
0x140055e01  bts     ebx, 11h
0x140055e05  jmp     loc_140055F0E
0x140055e0a  mov     ebx, r8d
0x140055e0d  bts     ebx, 10h
0x140055e11  jmp     loc_140055F0E
0x140055e16  mov     ebx, 0Ch
0x140055e1b  jmp     loc_140055F0E
0x140055e20  mov     ebx, 0Bh
0x140055e25  jmp     loc_140055F0E
0x140055e2a  mov     ebx, 34h ; '4'
0x140055e2f  cmp     ecx, ebx
  ... truncated ...
```
