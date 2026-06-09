# CConnectJob::FillConnectionProfileParameters(CPortPropertyCache *,_WFC_CONNECTION_PROFILE_PARAMETERS *)

- ea: `0x14004cdb8`
- end: `0x14004d3a3`
- name: `?FillConnectionProfileParameters@CConnectJob@@AEAAHPEAVCPortPropertyCache@@PEAU_WFC_CONNECTION_PROFILE_PARAMETERS@@@Z`
- size: `1515`
- prototype: `int(CConnectJob *__hidden this, struct CPortPropertyCache *, struct _WFC_CONNECTION_PROFILE_PARAMETERS *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x1400c3c60`

## callees

- `0x1400101c8`
- `0x1400109f8`
- `0x1400122e0`
- `0x140013000`
- `0x140024574`
- `0x14002aa28`
- `0x140034e04`
- `0x14004cdb8`
- `0x14004d3ac`
- `0x14004d4c0`
- `0x1400b68dc`

## pseudocode

```c
__int64 __fastcall CConnectJob::FillConnectionProfileParameters(
        CConnectJob *this,
        struct CPortPropertyCache *a2,
        struct _WFC_CONNECTION_PROFILE_PARAMETERS *a3)
{
  CAdapter *m_pAdapter; // r9
  int m_PortId; // r8d
  unsigned int i; // ecx
  CPort *v9; // r14
  __int64 *v10; // rdx
  int v11; // edx
  unsigned int v12; // edi
  int v13; // r8d
  unsigned __int8 PropertyBooleanOrDefault; // r15
  CPropertyCache *p_m_PortPropertyCache; // rcx
  int v16; // edx
  _DOT11_AUTH_ALGORITHM v17; // r8d
  __int64 *p_pBuffer; // r14
  int j; // edx
  int v20; // edx
  unsigned __int16 ElementCount; // ax
  void *DeviceExtension; // rcx
  int v23; // edx
  unsigned __int16 v24; // ax
  void *v25; // rcx
  int v26; // edx
  unsigned __int16 v27; // ax
  void *v28; // rcx
  unsigned __int8 *v30; // rcx
  int v31; // edx
  bool v32; // dl
  int PropertyBuffer; // eax
  int v34; // edx
  int v35; // r9d
  unsigned __int8 *v36; // rax
  int v37; // [rsp+20h] [rbp-30h]
  __int64 v38; // [rsp+38h] [rbp-18h]
  unsigned __int8 *v39[2]; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v40; // [rsp+90h] [rbp+40h] BYREF
  unsigned __int8 *v41; // [rsp+A8h] [rbp+58h] BYREF

  m_pAdapter = this->m_pAdapter;
  m_PortId = this->m_PortId;
  for ( i = 0; i < 5; ++i )
  {
    v9 = m_pAdapter->m_pPortList[i];
    if ( v9 && v9->m_WfcPortId == (_WORD)m_PortId )
      goto LABEL_5;
  }
  v9 = 0;
LABEL_5:
  v10 = WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v10) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v10,
      m_PortId,
      198,
      (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
      (char)this,
      this->m_ActivityId);
  }
  v12 = CConnectHelpers::PopulateConnectionParameters(a2, a3);
  if ( v12 )
    goto LABEL_21;
  if ( !this->m_IsP2PConnect )
  {
    PropertyBooleanOrDefault = CPropertyCache::GetPropertyBooleanOrDefault(&v9->m_PortPropertyCache, 0x55u, 0);
    p_m_PortPropertyCache = &v9->m_PortPropertyCache;
    if ( a3->HostFIPSModeEnabled )
    {
      v12 = CPropertyCache::SetPropertyBoolean(p_m_PortPropertyCache, 0x54u, 1u);
      if ( v12 && *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v31) = 2;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v31,
          v17,
          199,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
          (char)this,
          this->m_ActivityId);
      }
      if ( PropertyBooleanOrDefault == a3->HostFIPSModeEnabled )
        goto LABEL_13;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v31) = 4;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v31,
          1,
          200,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids);
      }
      v32 = 1;
    }
    else
    {
      v12 = CPropertyCache::SetPropertyBoolean(p_m_PortPropertyCache, 0x54u, 0);
      if ( v12 && *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v16) = 2;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v16,
          v17,
          201,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
          (char)this,
          this->m_ActivityId);
      }
      if ( PropertyBooleanOrDefault == a3->HostFIPSModeEnabled )
        goto LABEL_13;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v16) = 4;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v16,
          1,
          202,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids);
      }
      v32 = 0;
    }
    CPort::UpdateTaskOffloadCurrentConfigForFIPS(v9, v32);
LABEL_13:
    p_pBuffer = (__int64 *)&a3->SSIDList.pBuffer;
    goto LABEL_14;
  }
  p_pBuffer = (__int64 *)&a3->SSIDList.pBuffer;
  v41 = 0;
  a3->SSIDList.pBuffer = 0;
  v39[0] = 0;
  v40 = 0;
  a3->SSIDList.ElementCount = 0;
  a3->HostFIPSModeEnabled = 0;
  PropertyBuffer = CPropertyCache::GetPropertyBuffer(a2, 0x39u, &v40, &v41);
  v12 = PropertyBuffer;
  if ( PropertyBuffer )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return v12;
    v35 = 203;
    goto LABEL_53;
  }
  v36 = v41;
  *(_OWORD *)this->m_GroupIdStorage.DeviceAddress = *(_OWORD *)v41;
  *(_OWORD *)&this->m_GroupIdStorage.SSID.ucSSID[4] = *((_OWORD *)v36 + 1);
  *(_OWORD *)&this->m_GroupIdStorage.SSID.ucSSID[16] = *(_OWORD *)(v36 + 28);
  a3->SSIDList.ElementCount = 1;
  *p_pBuffer = (__int64)&this->m_GroupIdStorage.SSID;
  PropertyBuffer = CPropertyCache::GetPropertyBuffer(a2, 0x3Eu, &v40, v39);
  v12 = PropertyBuffer;
  if ( PropertyBuffer )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return v12;
    v35 = 204;
LABEL_53:
    LOBYTE(v34) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v34,
      v17,
      v35,
      (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
      (char)this,
      this->m_ActivityId,
      PropertyBuffer);
LABEL_21:
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v11) = 5;
      LODWORD(v38) = v12;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        v13,
        210,
        (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
        (char)this,
        this->m_ActivityId,
        v38);
    }
    return v12;
  }
  v30 = v39[0];
  this->m_RequireSelectedRegistrar = v39[0][17] != 0;
  this->m_RequireGroupFormationBit = v30[16] != 0;
  if ( (this->m_RoamConfigFlags & 1) != 0 )
  {
    *(_DWORD *)this->m_GOChannelHint.CountryRegionString = *((_DWORD *)v30 + 1);
    this->m_GOChannelHint.ChannelNumber = v30[8];
  }
LABEL_14:
  for ( j = 0; (unsigned __int16)j < a3->AuthAlgoList.ElementCount; LOWORD(j) = j + 1 )
  {
    v17 = a3->AuthAlgoList.pBuffer[(unsigned __int16)j];
    if ( (unsigned int)(v17 - 8) <= 3 || v17 == DOT11_AUTH_ALGO_RSNA )
    {
      v12 = CPropertyCache::SetPropertyBoolean(a2, 0x2Fu, 1u);
      if ( v12 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          return v12;
        LOBYTE(j) = 2;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          j,
          v17,
          205,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
          (char)this,
          this->m_ActivityId);
      }
      break;
    }
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(j) = 4;
    WPP_RECORDER_SF__SSID_(WPP_GLOBAL_Control->DeviceExtension, j, v17, 206, v37, *p_pBuffer);
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      ElementCount = a3->AuthAlgoList.ElementCount;
      *(_OWORD *)v39 = 0;
      LOWORD(v39[0]) = 4 * ElementCount;
      LOBYTE(v20) = 4;
      DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
      v39[1] = (unsigned __int8 *)a3->AuthAlgoList.pBuffer;
      WPP_RECORDER_SF__HEX_(
        (_DWORD)DeviceExtension,
        v20,
        1,
        207,
        (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
        (__int64)v39);
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v24 = a3->MulticastCipherAlgoList.ElementCount;
        *(_OWORD *)v39 = 0;
        LOWORD(v39[0]) = 4 * v24;
        LOBYTE(v23) = 4;
        v25 = WPP_GLOBAL_Control->DeviceExtension;
        v39[1] = (unsigned __int8 *)a3->MulticastCipherAlgoList.pBuffer;
        WPP_RECORDER_SF__HEX_(
          (_DWORD)v25,
          v23,
          1,
          208,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
          (__int64)v39);
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v27 = a3->UnicastCipherAlgoList.ElementCount;
          *(_OWORD *)v39 = 0;
          LOWORD(v39[0]) = 4 * v27;
          LOBYTE(v26) = 4;
          v28 = WPP_GLOBAL_Control->DeviceExtension;
          v39[1] = (unsigned __int8 *)a3->UnicastCipherAlgoList.pBuffer;
          WPP_RECORDER_SF__HEX_(
            (_DWORD)v28,
            v26,
            1,
            209,
            (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
            (__int64)v39);
          goto LABEL_21;
        }
      }
    }
  }
  return v12;
}

```

## disassembly

```asm
0x14004cdb8  mov     [rsp-38h+arg_8], rbx
0x14004cdbd  push    rbp
0x14004cdbe  push    rsi
0x14004cdbf  push    rdi
0x14004cdc0  push    r12
0x14004cdc2  push    r13
0x14004cdc4  push    r14
0x14004cdc6  push    r15
0x14004cdc8  mov     rbp, rsp
0x14004cdcb  sub     rsp, 50h
0x14004cdcf  mov     r9, [rcx+200h]
0x14004cdd6  mov     rsi, r8
0x14004cdd9  movzx   r8d, word ptr [rcx+34h]
0x14004cdde  xor     r13d, r13d
0x14004cde1  mov     rbx, rcx
0x14004cde4  mov     r12, rdx
0x14004cde7  mov     ecx, r13d
0x14004cdea  cmp     ecx, 5
0x14004cded  jnb     loc_14004D0E2
0x14004cdf3  mov     eax, ecx
0x14004cdf5  mov     r14, [r9+rax*8+1318h]
0x14004cdfd  test    r14, r14
0x14004ce00  jz      loc_14004D053
0x14004ce06  cmp     [r14+64h], r8w
0x14004ce0b  jnz     loc_14004D053
0x14004ce11  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004ce18  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004ce1f  lea     rdx, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x14004ce26  jz      short loc_14004CE44
0x14004ce28  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ce2f  cmp     byte ptr [rcx+29h], 5
0x14004ce33  jnb     loc_14004D134
0x14004ce39  cmp     [rcx+48h], r13w
0x14004ce3e  jnz     loc_14004D134
0x14004ce44  mov     rdx, rsi; struct _WFC_CONNECTION_PROFILE_PARAMETERS *
0x14004ce47  mov     rcx, r12; this
0x14004ce4a  call    ?PopulateConnectionParameters@CConnectHelpers@@SAHPEAVCPortPropertyCache@@PEAU_WFC_CONNECTION_PROFILE_PARAMETERS@@@Z; CConnectHelpers::PopulateConnectionParameters(CPortPropertyCache *,_WFC_CONNECTION_PROFILE_PARAMETERS *)
0x14004ce4f  mov     edi, eax
0x14004ce51  test    eax, eax
0x14004ce53  jnz     loc_14004D07D
0x14004ce59  cmp     [rbx+13C8h], r13b
0x14004ce60  jnz     loc_14004D290
0x14004ce66  lea     rdi, [r14+3A8h]
0x14004ce6d  xor     r8d, r8d; unsigned __int8
0x14004ce70  mov     rcx, rdi; this
0x14004ce73  lea     edx, [rax+55h]; unsigned int
0x14004ce76  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x14004ce7b  mov     r15b, al
0x14004ce7e  mov     edx, 54h ; 'T'; unsigned int
0x14004ce83  mov     rcx, rdi; this
0x14004ce86  cmp     [rsi+6Ch], r13b
0x14004ce8a  jnz     loc_14004D15B
0x14004ce90  xor     r8d, r8d; unsigned __int8
0x14004ce93  call    ?SetPropertyBoolean@CPropertyCache@@QEAAHKE@Z; CPropertyCache::SetPropertyBoolean(ulong,uchar)
0x14004ce98  mov     edi, eax
0x14004ce9a  test    eax, eax
0x14004ce9c  jnz     loc_14004D22E
0x14004cea2  cmp     r15b, [rsi+6Ch]
0x14004cea6  jnz     loc_14004D27B
0x14004ceac  lea     r15, WPP_RECORDER_INITIALIZED
0x14004ceb3  lea     r14, [rsi+8]
0x14004ceb7  mov     r10d, 1
0x14004cebd  movzx   r9d, word ptr [rsi+38h]
0x14004cec2  mov     edx, r13d
0x14004cec5  cmp     dx, r9w
0x14004cec9  jb      loc_14004D05A
0x14004cecf  lea     r12, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x14004ced6  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14004cedd  jz      loc_14004D038
0x14004cee3  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ceea  mov     r9d, 0CEh
0x14004cef0  mov     rax, [r14]
0x14004cef3  mov     dl, 4
0x14004cef5  mov     [rsp+50h+var_28], rax
0x14004cefa  mov     rcx, [rcx+40h]
0x14004cefe  call    WPP_RECORDER_SF__SSID_
0x14004cf03  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14004cf0a  jz      loc_14004D038
0x14004cf10  movzx   eax, word ptr [rsi+38h]
0x14004cf14  xorps   xmm0, xmm0
0x14004cf17  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cf1e  mov     r14d, 1
0x14004cf24  movups  xmmword ptr [rbp+var_10], xmm0
0x14004cf28  shl     ax, 2
0x14004cf2c  mov     r9d, 0CFh
0x14004cf32  mov     word ptr [rbp+var_10], ax
0x14004cf36  mov     r8d, r14d
0x14004cf39  mov     rax, [rsi+40h]
0x14004cf3d  mov     dl, 4
0x14004cf3f  mov     rcx, [rcx+40h]
0x14004cf43  mov     [rbp+var_10+8], rax
0x14004cf47  lea     rax, [rbp+var_10]
0x14004cf4b  movaps  xmm0, xmmword ptr [rbp+var_10]
0x14004cf4f  mov     [rsp+50h+var_28], rax
0x14004cf54  mov     [rsp+50h+var_30], r12
0x14004cf59  movdqa  xmmword ptr [rbp+var_10], xmm0
0x14004cf5e  call    WPP_RECORDER_SF__HEX_
0x14004cf63  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14004cf6a  jz      loc_14004D038
0x14004cf70  movzx   eax, word ptr [rsi+48h]
0x14004cf74  xorps   xmm0, xmm0
0x14004cf77  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cf7e  mov     r9d, 0D0h
0x14004cf84  movups  xmmword ptr [rbp+var_10], xmm0
0x14004cf88  shl     ax, 2
0x14004cf8c  mov     r8d, r14d
0x14004cf8f  mov     word ptr [rbp+var_10], ax
0x14004cf93  mov     dl, 4
0x14004cf95  mov     rax, [rsi+50h]
0x14004cf99  mov     rcx, [rcx+40h]
0x14004cf9d  mov     [rbp+var_10+8], rax
0x14004cfa1  lea     rax, [rbp+var_10]
0x14004cfa5  movaps  xmm0, xmmword ptr [rbp+var_10]
0x14004cfa9  mov     [rsp+50h+var_28], rax
0x14004cfae  mov     [rsp+50h+var_30], r12
0x14004cfb3  movdqa  xmmword ptr [rbp+var_10], xmm0
0x14004cfb8  call    WPP_RECORDER_SF__HEX_
0x14004cfbd  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14004cfc4  jz      short loc_14004D038
0x14004cfc6  movzx   eax, word ptr [rsi+58h]
0x14004cfca  xorps   xmm0, xmm0
0x14004cfcd  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cfd4  mov     r9d, 0D1h
0x14004cfda  movups  xmmword ptr [rbp+var_10], xmm0
0x14004cfde  shl     ax, 2
0x14004cfe2  mov     r8d, r14d
0x14004cfe5  mov     word ptr [rbp+var_10], ax
0x14004cfe9  mov     dl, 4
0x14004cfeb  mov     rax, [rsi+60h]
0x14004cfef  mov     rcx, [rcx+40h]
0x14004cff3  mov     [rbp+var_10+8], rax
0x14004cff7  lea     rax, [rbp+var_10]
0x14004cffb  movaps  xmm0, xmmword ptr [rbp+var_10]
0x14004cfff  mov     [rsp+50h+var_28], rax
0x14004d004  mov     [rsp+50h+var_30], r12
0x14004d009  movdqa  xmmword ptr [rbp+var_10], xmm0
0x14004d00e  call    WPP_RECORDER_SF__HEX_
0x14004d013  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14004d01a  jz      short loc_14004D038
0x14004d01c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d023  cmp     byte ptr [rcx+29h], 5
0x14004d027  jnb     loc_14004D378
0x14004d02d  cmp     [rcx+48h], r13w
0x14004d032  jnz     loc_14004D378
0x14004d038  mov     rbx, [rsp+50h+arg_8]
0x14004d040  mov     eax, edi
0x14004d042  add     rsp, 50h
0x14004d046  pop     r15
0x14004d048  pop     r14
0x14004d04a  pop     r13
0x14004d04c  pop     r12
0x14004d04e  pop     rdi
0x14004d04f  pop     rsi
0x14004d050  pop     rbp
0x14004d051  retn
0x14004d053  inc     ecx
0x14004d055  jmp     loc_14004CDEA
0x14004d05a  mov     rax, [rsi+40h]
0x14004d05e  movzx   ecx, dx
0x14004d061  mov     r8d, [rax+rcx*4]
0x14004d065  lea     eax, [r8-8]
0x14004d069  cmp     eax, 3
0x14004d06c  jbe     short loc_14004D086
0x14004d06e  cmp     r8d, 6
0x14004d072  jz      short loc_14004D086
0x14004d074  add     dx, r10w
0x14004d078  jmp     loc_14004CEC5
0x14004d07d  lea     r12, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x14004d084  jmp     short loc_14004D013
0x14004d086  mov     r8b, r10b; unsigned __int8
0x14004d089  mov     edx, 2Fh ; '/'; unsigned int
0x14004d08e  mov     rcx, r12; this
0x14004d091  call    ?SetPropertyBoolean@CPropertyCache@@QEAAHKE@Z; CPropertyCache::SetPropertyBoolean(ulong,uchar)
0x14004d096  mov     edi, eax
0x14004d098  test    eax, eax
0x14004d09a  jz      loc_14004CECF
0x14004d0a0  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14004d0a7  jz      short loc_14004D038
0x14004d0a9  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d0b0  lea     r12, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x14004d0b7  mov     dword ptr [rsp+50h+var_18], eax
0x14004d0bb  mov     r9d, 0CDh
0x14004d0c1  mov     eax, [rbx+10h]
0x14004d0c4  mov     dl, 2
0x14004d0c6  mov     [rsp+50h+var_20], eax
0x14004d0ca  mov     rcx, [rcx+40h]
0x14004d0ce  mov     [rsp+50h+var_28], rbx
0x14004d0d3  mov     [rsp+50h+var_30], r12
0x14004d0d8  call    WPP_RECORDER_SF_qDD
0x14004d0dd  jmp     loc_14004CED6
0x14004d0e2  mov     r14, r13
0x14004d0e5  jmp     loc_14004CE11
0x14004d0ea  mov     rcx, [rbp+var_10]
0x14004d0ee  mov     r10d, 1
0x14004d0f4  cmp     [rcx+11h], r13b
0x14004d0f8  setnz   al
0x14004d0fb  mov     [rbx+13F8h], al
0x14004d101  cmp     [rcx+10h], r13b
0x14004d105  setnz   al
0x14004d108  mov     [rbx+13F9h], al
0x14004d10e  mov     eax, [rbx+260h]
0x14004d114  test    r10b, al
0x14004d117  jz      loc_14004CEBD
0x14004d11d  mov     eax, [rcx+4]
0x14004d120  mov     [rbx+13FAh], eax
0x14004d126  mov     al, [rcx+8]
0x14004d129  mov     [rbx+13FEh], al
0x14004d12f  jmp     loc_14004CEBD
0x14004d134  mov     eax, [rbx+10h]
0x14004d137  mov     r9d, 0C6h
0x14004d13d  mov     rcx, [rcx+40h]
0x14004d141  mov     [rsp+50h+var_20], eax
0x14004d145  mov     [rsp+50h+var_28], rbx
0x14004d14a  mov     [rsp+50h+var_30], rdx
0x14004d14f  mov     dl, 5
0x14004d151  call    WPP_RECORDER_SF_qD
0x14004d156  jmp     loc_14004CE44
0x14004d15b  mov     r8b, 1; unsigned __int8
0x14004d15e  call    ?SetPropertyBoolean@CPropertyCache@@QEAAHKE@Z; CPropertyCache::SetPropertyBoolean(ulong,uchar)
0x14004d163  mov     edi, eax
0x14004d165  test    eax, eax
0x14004d167  jz      short loc_14004D1AD
0x14004d169  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004d170  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004d177  jz      short loc_14004D1AD
0x14004d179  mov     eax, [rbx+10h]
0x14004d17c  mov     r9d, 0C7h
0x14004d182  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d189  mov     dl, 2
0x14004d18b  mov     dword ptr [rsp+50h+var_18], edi
0x14004d18f  mov     [rsp+50h+var_20], eax
0x14004d193  lea     rax, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x14004d19a  mov     [rsp+50h+var_28], rbx
0x14004d19f  mov     rcx, [rcx+40h]
0x14004d1a3  mov     [rsp+50h+var_30], rax
0x14004d1a8  call    WPP_RECORDER_SF_qDD
0x14004d1ad  cmp     r15b, [rsi+6Ch]
0x14004d1b1  jz      loc_14004CEAC
0x14004d1b7  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004d1be  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004d1c5  jz      short loc_14004D1F1
0x14004d1c7  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d1ce  lea     rax, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x14004d1d5  mov     r9d, 0C8h
0x14004d1db  mov     [rsp+50h+var_30], rax
0x14004d1e0  mov     r8d, 1
0x14004d1e6  mov     dl, 4
0x14004d1e8  mov     rcx, [rcx+40h]
0x14004d1ec  call    WPP_RECORDER_SF_
0x14004d1f1  mov     dl, 1
0x14004d1f3  jmp     short loc_14004D221
0x14004d1f5  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d1fc  lea     rax, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x14004d203  mov     r9d, 0CAh
0x14004d209  mov     [rsp+50h+var_30], rax
0x14004d20e  mov     r8d, 1
0x14004d214  mov     dl, 4
0x14004d216  mov     rcx, [rcx+40h]
0x14004d21a  call    WPP_RECORDER_SF_
0x14004d21f  xor     edx, edx; bool
0x14004d221  mov     rcx, r14; this
0x14004d224  call    ?UpdateTaskOffloadCurrentConfigForFIPS@CPort@@QEAAX_N@Z; CPort::UpdateTaskOffloadCurrentConfigForFIPS(bool)
0x14004d229  jmp     loc_14004CEB3
0x14004d22e  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004d235  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004d23c  jz      loc_14004CEA2
0x14004d242  mov     eax, [rbx+10h]
0x14004d245  mov     r9d, 0C9h
0x14004d24b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d252  mov     dl, 2
0x14004d254  mov     dword ptr [rsp+50h+var_18], edi
0x14004d258  mov     [rsp+50h+var_20], eax
0x14004d25c  lea     rax, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x14004d263  mov     [rsp+50h+var_28], rbx
0x14004d268  mov     rcx, [rcx+40h]
0x14004d26c  mov     [rsp+50h+var_30], rax
0x14004d271  call    WPP_RECORDER_SF_qDD
0x14004d276  jmp     loc_14004CEA2
0x14004d27b  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004d282  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004d289  jz      short loc_14004D21F
0x14004d28b  jmp     loc_14004D1F5
0x14004d290  lea     r14, [rsi+8]
0x14004d294  mov     [rbp+arg_18], r13
0x14004d298  lea     r9, [rbp+arg_18]; unsigned __int8 **
0x14004d29c  mov     [r14], r13
0x14004d29f  lea     r8, [rbp+arg_0]; unsigned int *
0x14004d2a3  mov     [rbp+var_10], r13
0x14004d2a7  mov     edx, 39h ; '9'; unsigned int
0x14004d2ac  mov     [rbp+arg_0], r13d
0x14004d2b0  mov     rcx, r12; this
0x14004d2b3  mov     [rsi], r13w
0x14004d2b7  mov     [rsi+6Ch], r13b
0x14004d2bb  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x14004d2c0  mov     edi, eax
0x14004d2c2  test    eax, eax
0x14004d2c4  jz      short loc_14004D314
0x14004d2c6  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14004d2cd  jz      loc_14004D038
0x14004d2d3  mov     r9d, 0CBh
  ... truncated ...
```
