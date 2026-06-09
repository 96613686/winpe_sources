# CConnectJob::FillConnectRoamTaskParameters(_WDI_CONNECT_PARAMETERS_CONTAINER *,ArrayOfElements<_WDI_CONNECT_BSS_ENTRY_CONTAINER> *,bool)

- ea: `0x1400a621c`
- end: `0x1400a6bfe`
- name: `?FillConnectRoamTaskParameters@CConnectJob@@AEAAHPEAU_WDI_CONNECT_PARAMETERS_CONTAINER@@PEAU?$ArrayOfElements@U_WDI_CONNECT_BSS_ENTRY_CONTAINER@@@@_N@Z`
- size: `2530`
- prototype: `__int64 __fastcall(CConnectJob *this, struct _WDI_CONNECT_PARAMETERS_CONTAINER *)`
- caller_count: `2`
- callee_count: `32`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x140030b60`
- `0x140032d30`

## callees

- `0x14000688c`
- `0x14000a34c`
- `0x14000c778`
- `0x14000d054`
- `0x140014b30`
- `0x140016d00`
- `0x14001a630`
- `0x14001c220`
- `0x14001e2c0`
- `0x14002bd34`
- `0x14002ef48`
- `0x140050660`
- `0x140050dc8`
- `0x14005eb84`
- `0x140071720`
- `0x140073410`
- `0x1400735b4`
- `0x1400800d8`
- `0x140080488`
- `0x1400a5b1c`
- `0x1400a621c`
- `0x1400a9fec`
- `0x1400ab4e8`
- `0x1400ab50c`
- `0x1400b1784`
- `0x1400b3118`
- `0x1400b3de4`
- `0x1400b46c4`
- `0x1400dfd00`
- `0x1400dfd40`
- `0x1400dfe00`
- `0x1400e0100`

## pseudocode

```c
__int64 __fastcall CConnectJob::FillConnectRoamTaskParameters(CConnectJob *this, void **a2, __int64 a3, char a4)
{
  char v7; // r15
  int v8; // edx
  CConnectHelpers *v9; // r13
  const struct _DOT11_ADAPTER_CAPABILITIES **v10; // r8
  QoS::QoSManager *v11; // r9
  char v12; // r11
  bool IsDSCPToUPMappingAllowed; // al
  char v14; // al
  unsigned __int8 v15; // r8
  int v16; // edx
  char *v17; // r9
  char v18; // r11
  unsigned int AdapterCapabilitiesFromPropertyCache; // eax
  int v20; // edx
  int v21; // r8d
  unsigned int v22; // ebx
  int v23; // r9d
  unsigned int Elements; // eax
  unsigned int i; // ebx
  unsigned int *v26; // r8
  __int64 v27; // rcx
  int v28; // edx
  int v29; // r8d
  unsigned int j; // edi
  struct CBSSEntry **v31; // r8
  __int64 v32; // rax
  __int64 v33; // r8
  unsigned int *v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rdx
  int v37; // edx
  int v38; // r8d
  CPropertyCache *v39; // r13
  struct _WFC_CONNECTION_PROFILE_PARAMETERS *v40; // r12
  int v41; // edi
  void *v42; // rbx
  int v43; // r12d
  void *v44; // rbx
  int v45; // edx
  int v46; // r8d
  char v47; // al
  unsigned int v48; // edi
  unsigned int v49; // edi
  int v50; // r15d
  void *v51; // rbx
  unsigned int v52; // ebx
  __int64 v53; // rdi
  const void *v54; // r15
  __int64 v55; // rax
  __int64 v56; // rdx
  __int64 v57; // rdx
  int v58; // r8d
  unsigned int v59; // r9d
  unsigned int k; // r8d
  char v61; // r15
  unsigned int v62; // ebx
  CPropertyCache *PortPropertyCache; // rax
  CPropertyCache *v64; // rax
  int v65; // edx
  int v66; // r8d
  struct CPort *v67; // rdx
  CConnectHelpers *v68; // rdi
  int v69; // edx
  char v70; // bl
  struct _DOT11_SSID *v72; // [rsp+20h] [rbp-89h]
  struct CBSSEntry **v73; // [rsp+28h] [rbp-81h]
  int v74; // [rsp+30h] [rbp-79h]
  char v75[8]; // [rsp+38h] [rbp-71h]
  unsigned int v76; // [rsp+70h] [rbp-39h] BYREF
  char v77; // [rsp+74h] [rbp-35h]
  unsigned __int8 *v78; // [rsp+78h] [rbp-31h] BYREF
  __int64 v79; // [rsp+80h] [rbp-29h] BYREF
  CConnectHelpers *PortFromPortId; // [rsp+88h] [rbp-21h]
  __int64 v81; // [rsp+90h] [rbp-19h]
  unsigned int v82[4]; // [rsp+98h] [rbp-11h] BYREF
  __int128 v83; // [rsp+A8h] [rbp-1h]
  int v84; // [rsp+B8h] [rbp+Fh]

  v77 = a4;
  v81 = a3;
  v7 = 0;
  PortFromPortId = CAdapter::GetPortFromPortId(*((CAdapter **)this + 67), *((_WORD *)this + 26));
  v76 = 0;
  v9 = PortFromPortId;
  v78 = 0;
  v79 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v8) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      1,
      348,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids);
  }
  memset(a2, 0, 0x178u);
  v11 = (CConnectHelpers *)((char *)PortFromPortId + 584);
  *(_OWORD *)a3 = 0;
  *(_QWORD *)(a3 + 16) = 0;
  *((_BYTE *)a2 + 5) = *((_BYTE *)this + 1081);
  *((_BYTE *)a2 + 6) = *((_BYTE *)this + 1082);
  *((_BYTE *)a2 + 7) = *((_BYTE *)this + 1083);
  *((_BYTE *)a2 + 8) = *((_BYTE *)this + 1084);
  *((_BYTE *)a2 + 22) = *((_BYTE *)this + 1085);
  if ( !*((_BYTE *)v9 + 594) || (v12 = 1, !*((_BYTE *)v9 + 616)) )
    v12 = 0;
  *((_BYTE *)a2 + 23) = v12;
  if ( !*((_BYTE *)v9 + 593)
    || (IsDSCPToUPMappingAllowed = QoS::QoSManager::IsDSCPToUPMappingAllowed((CConnectHelpers *)((char *)v9 + 584)),
        LOBYTE(v10) = 1,
        !IsDSCPToUPMappingAllowed) )
  {
    LOBYTE(v10) = 0;
  }
  *((_BYTE *)a2 + 24) = (_BYTE)v10;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v14 = QoS::QoSManager::IsDSCPToUPMappingAllowed(v11);
    v16 = v15;
    LOBYTE(v16) = 4;
    WPP_RECORDER_SF_qDdddddd(
      WPP_GLOBAL_Control->DeviceExtension,
      v16,
      (unsigned __int8)v17[32],
      349,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v18,
      v17[10],
      v17[32],
      v15,
      v17[9],
      v14);
  }
  AdapterCapabilitiesFromPropertyCache = CConnectHelpers::GetAdapterCapabilitiesFromPropertyCache(
                                           *((CConnectHelpers **)this + 67),
                                           (struct CAdapter *)&v79,
                                           v10);
  v22 = AdapterCapabilitiesFromPropertyCache;
  if ( AdapterCapabilitiesFromPropertyCache )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v22;
    v23 = 350;
    *(_DWORD *)v75 = AdapterCapabilitiesFromPropertyCache;
    v74 = *((_DWORD *)this + 4);
LABEL_97:
    LOBYTE(v20) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v20,
      v21,
      v23,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      (char)this,
      v74,
      *(_QWORD *)v75);
    goto LABEL_98;
  }
  *((_BYTE *)a2 + 20) = *(_DWORD *)(v79 + 420) == 1;
  if ( (*((_DWORD *)this + 158) & 0x10) != 0 )
    *((_DWORD *)a2 + 4) = 1;
  Elements = ArrayOfElements<ArrayOfElements<unsigned char>>::AllocateElements(
               a2 + 4,
               *((unsigned __int16 *)this + 488),
               0);
  v22 = Elements;
  if ( Elements )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v22;
    v23 = 351;
    goto LABEL_95;
  }
  for ( i = 0; ; ++i )
  {
    v26 = (unsigned int *)((char *)this + 644);
    if ( i >= *((_DWORD *)this + 161) )
      break;
    v27 = *((_QWORD *)this + i + 82);
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v27 + 32LL))(v27) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v28) = 4;
        WPP_RECORDER_SF_qD_MAC_(
          WPP_GLOBAL_Control->DeviceExtension,
          v28,
          v29,
          352,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          *((_QWORD *)this + i + 82) + 32LL);
      }
      v7 = 1;
      v26 = (unsigned int *)((char *)this + 644);
      *((_BYTE *)a2 + 5) = 1;
      break;
    }
  }
  for ( j = 0; j < *((_DWORD *)a2 + 8); ++j )
  {
    if ( v7 )
    {
      v31 = (struct CBSSEntry **)*v26;
      v84 = 0;
      v32 = *((_QWORD *)this + 123);
      *(_OWORD *)v82 = 0;
      v83 = 0;
      CConnectHelpers::RemapSSID(
        (struct _DOT11_SSID *)(v32 + 36LL * j),
        (struct _DOT11_SSID *)((char *)this + 656),
        v31,
        (unsigned int)v82,
        v72);
      v33 = v82[0];
      v34 = &v82[1];
    }
    else
    {
      v35 = *((_QWORD *)this + 123);
      v36 = v35 + 4;
      v33 = *(unsigned int *)(v35 + 36LL * j);
      v34 = (unsigned int *)(v36 + 36LL * j);
    }
    v22 = ArrayOfElements<unsigned char>::SimpleSet((char *)a2[5] + 24 * j, v34, v33);
    if ( v22 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v22;
      *(_DWORD *)v75 = v22;
      LOBYTE(v37) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v37,
        v38,
        353,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        *(_QWORD *)v75);
LABEL_98:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LODWORD(v73) = v22;
        LOBYTE(v20) = 5;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v20,
          1,
          363,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          v73);
      }
      return v22;
    }
    v26 = (unsigned int *)((char *)this + 644);
  }
  v39 = (CConnectHelpers *)((char *)v9 + 480);
  if ( (unsigned int)Feature_53299205__private_IsEnabledDeviceUsageNoInline() )
    *((_BYTE *)a2 + 25) = (*(_DWORD *)(*((_QWORD *)this + 67) + 4648LL) & 0x4000) != 0;
  v40 = (CConnectJob *)((char *)this + 976);
  v41 = *((unsigned __int16 *)this + 500);
  if ( (_WORD)v41 )
  {
    v42 = (void *)*((_QWORD *)this + 126);
    ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(a2 + 8);
    *((_BYTE *)a2 + 80) = 0;
    *((_DWORD *)a2 + 16) = v41;
    a2[9] = v42;
    v43 = *((unsigned __int16 *)this + 508);
    v44 = (void *)*((_QWORD *)this + 128);
    ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(a2 + 11);
    *((_BYTE *)a2 + 104) = 0;
    *((_DWORD *)a2 + 22) = v43;
    a2[12] = v44;
    v47 = *((_BYTE *)this + 992);
    *(_DWORD *)a2 |= 1u;
    *((_BYTE *)a2 + 56) = v47;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v45) = 4;
      WPP_RECORDER_SF_qDddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v45,
        v46,
        354,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        *((_DWORD *)a2 + 16),
        v47,
        v43);
    }
    v40 = (CConnectJob *)((char *)this + 976);
  }
  if ( !(unsigned int)CPropertyCache::GetPropertyBuffer(v39, 0x87u, &v76, &v78) )
  {
    v48 = v76;
    if ( v76 )
    {
      ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(a2 + 35);
      a2[36] = v78;
      *((_BYTE *)a2 + 296) = 0;
      *((_DWORD *)a2 + 70) = v48;
      *(_DWORD *)a2 |= 0x20u;
    }
  }
  v22 = CConnectJob::SetUnicastAuthCipherInfo(this, (struct _WDI_CONNECT_PARAMETERS_CONTAINER *)a2);
  if ( v22 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v22;
    v23 = 355;
    goto LABEL_49;
  }
  *((_BYTE *)a2 + 21) = *((_BYTE *)this + 1140);
  v22 = CConnectJob::SetRsnaAkmCipherPairs(
          this,
          *((_DWORD *)this + 283),
          *((_DWORD *)this + 284),
          (struct _WDI_CONNECT_PARAMETERS_CONTAINER *)a2);
  if ( v22 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v22;
    v23 = 356;
LABEL_49:
    *(_DWORD *)v75 = v22;
    goto LABEL_96;
  }
  v22 = CConnectJob::SetMultiCastCipherList(this, v39, v40, (struct _WDI_CONNECT_PARAMETERS_CONTAINER *)a2);
  if ( v22 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v22;
    v23 = 357;
    goto LABEL_49;
  }
  if ( !(unsigned int)CPropertyCache::GetPropertyBuffer(v39, 0xEu, &v76, &v78) )
  {
    v49 = v76;
    if ( v76 )
    {
      ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(a2 + 23);
      a2[24] = v78;
      *((_BYTE *)a2 + 200) = 0;
      *((_DWORD *)a2 + 46) = v49;
      *(_DWORD *)a2 |= 2u;
    }
  }
  v50 = *((unsigned __int16 *)this + 544);
  if ( (_WORD)v50 )
  {
    v51 = (void *)*((_QWORD *)this + 137);
    ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(a2 + 32);
    *((_DWORD *)a2 + 64) = v50;
    *((_BYTE *)a2 + 272) = 0;
    a2[33] = v51;
    *(_DWORD *)a2 |= 0x10u;
  }
  v52 = 0;
  v53 = *((unsigned __int16 *)this + 556);
  v54 = 0;
  if ( !*((_BYTE *)this + 2784) && *(_DWORD *)(v79 + 456) == 1 )
  {
    v55 = *((_QWORD *)this + 67);
    v52 = *(_DWORD *)(v55 + 1436);
    v54 = (const void *)(v55 + 1440);
  }
  if ( v52 + (_DWORD)v53 )
  {
    ArrayOfElements<_WDI_MAC_ADDRESS>::AllocateElements(a2 + 29, v52 + (unsigned int)v53, 0);
    *(_DWORD *)a2 |= 8u;
    if ( (_WORD)v53 )
      memmove(a2[30], *((const void **)this + 140), 6 * v53);
    if ( v52 )
      memmove((char *)a2[30] + 6 * v53, v54, 6LL * v52);
  }
  *(_DWORD *)a2 &= ~4u;
  v56 = *((unsigned int *)this + 315);
  if ( (_DWORD)v56 )
  {
    v22 = ArrayOfElements<enum _WDI_BAND_ID>::AllocateElements(a2 + 38, v56, 0);
    if ( v22 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v57) = 2;
        WPP_RECORDER_SF_qDdd(
          WPP_GLOBAL_Control->DeviceExtension,
          v57,
          v58,
          358,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          *((_DWORD *)this + 315),
          v22);
        goto LABEL_98;
      }
      return v22;
    }
    v59 = 0;
    for ( k = 0; k < *((unsigned __int8 *)this + 1160); ++k )
    {
      if ( !*((_DWORD *)this + k + 316) && v59 < *((_DWORD *)this + 315) )
      {
        v57 = v59++;
        *((_DWORD *)a2[39] + v57) = *((_DWORD *)this + 3 * k + 291);
      }
    }
    *(_DWORD *)a2 |= 0x40u;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v57) = 4;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v57,
        1,
        359,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids);
    }
  }
  v61 = v77;
  if ( v77 )
  {
    v62 = *((_DWORD *)this + 156);
    v76 = v62;
    PortPropertyCache = COidJobBase::GetPortPropertyCache(this);
    if ( CPropertyCache::GetPropertyBooleanOrDefault(PortPropertyCache, 0x52u, 0) )
    {
      v64 = COidJobBase::GetPortPropertyCache(this);
      if ( (unsigned int)CPropertyCache::GetPropertyULong(v64, 0x54u, &v76) || (v62 = v76, v76 == 0xFFFF) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v65) = 2;
          WPP_RECORDER_SF_qDD(
            WPP_GLOBAL_Control->DeviceExtension,
            v65,
            v66,
            360,
            (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
            (char)this,
            *((_DWORD *)this + 4));
        }
        v62 = *((_DWORD *)this + 156);
      }
    }
    *((_DWORD *)a2 + 3) = v62;
  }
  v67 = (struct CPort *)*((_QWORD *)this + 67);
  v76 = 0;
  v68 = PortFromPortId;
  CConnectHelpers::GetSupportedAssociationMethods(
    PortFromPortId,
    v67,
    v40,
    (struct _WFC_CONNECTION_PROFILE_PARAMETERS *)&v76,
    &v72->uSSIDLength);
  if ( v61
    && CPropertyCache::GetPropertyBooleanOrDefault(v39, 0x14u, 0)
    && !(unsigned __int8)CConnectHelpers::IsIMDAssocForFTRoamRequired(
                           *((unsigned int *)this + 156),
                           *((unsigned int *)this + 158)) )
  {
    v70 = 1;
  }
  else
  {
    v70 = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v69) = 4;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v69,
        1,
        361,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids);
    }
  }
  Elements = CConnectHelpers::FillConnectBSSEntryTLV(
               v68,
               (unsigned int *)this + 161,
               (struct CBSSEntry **)this + 82,
               v81,
               1,
               v70);
  v22 = Elements;
  if ( !Elements )
    goto LABEL_98;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v23 = 362;
LABEL_95:
    *(_DWORD *)v75 = Elements;
LABEL_96:
    v74 = *((_DWORD *)this + 4);
    goto LABEL_97;
  }
  return v22;
}

```

## disassembly

```asm
0x1400a621c  mov     [rsp-8+arg_18], rbx
0x1400a6221  push    rbp
0x1400a6222  push    rsi
0x1400a6223  push    rdi
0x1400a6224  push    r12
0x1400a6226  push    r13
0x1400a6228  push    r14
0x1400a622a  push    r15
0x1400a622c  lea     rbp, [rsp-27h]
0x1400a6231  sub     rsp, 0D0h
0x1400a6238  mov     rax, cs:__security_cookie
0x1400a623f  xor     rax, rsp
0x1400a6242  mov     [rbp+57h+var_40], rax
0x1400a6246  mov     rbx, r8
0x1400a6249  mov     [rbp+57h+var_8C], r9b
0x1400a624d  mov     r14, rdx
0x1400a6250  mov     [rbp+57h+var_70], rbx
0x1400a6254  movzx   edx, word ptr [rcx+34h]; unsigned __int16
0x1400a6258  mov     rsi, rcx
0x1400a625b  mov     rcx, [rcx+218h]; this
0x1400a6262  call    ?GetPortFromPortId@CAdapter@@QEAAPEAVCPort@@G@Z; CAdapter::GetPortFromPortId(ushort)
0x1400a6267  xor     r15d, r15d
0x1400a626a  mov     [rbp+57h+var_78], rax
0x1400a626e  mov     [rbp+57h+var_90], r15d
0x1400a6272  mov     r13, rax
0x1400a6275  mov     [rbp+57h+var_88], r15
0x1400a6279  mov     [rbp+57h+var_80], r15
0x1400a627d  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a6284  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a628b  lea     r12, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a6292  jz      short loc_1400A62C4
0x1400a6294  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a629b  cmp     byte ptr [rcx+29h], 5
0x1400a629f  jnb     short loc_1400A62A8
0x1400a62a1  cmp     [rcx+48h], r15w
0x1400a62a6  jz      short loc_1400A62C4
0x1400a62a8  mov     rcx, [rcx+40h]
0x1400a62ac  mov     r9d, 15Ch
0x1400a62b2  mov     r8d, 1
0x1400a62b8  mov     [rsp+100h+var_E0], r12
0x1400a62bd  mov     dl, 5
0x1400a62bf  call    WPP_RECORDER_SF_
0x1400a62c4  xor     edx, edx; Val
0x1400a62c6  mov     r8d, 178h; Size
0x1400a62cc  mov     rcx, r14; void *
0x1400a62cf  call    memset
0x1400a62d4  xor     eax, eax
0x1400a62d6  lea     r9, [r13+248h]
0x1400a62dd  xorps   xmm0, xmm0
0x1400a62e0  movups  xmmword ptr [rbx], xmm0
0x1400a62e3  mov     [rbx+10h], rax
0x1400a62e7  mov     al, [rsi+439h]
0x1400a62ed  mov     [r14+5], al
0x1400a62f1  mov     al, [rsi+43Ah]
0x1400a62f7  mov     [r14+6], al
0x1400a62fb  mov     al, [rsi+43Bh]
0x1400a6301  mov     [r14+7], al
0x1400a6305  mov     al, [rsi+43Ch]
0x1400a630b  mov     [r14+8], al
0x1400a630f  mov     al, [rsi+43Dh]
0x1400a6315  mov     [r14+16h], al
0x1400a6319  cmp     [r9+0Ah], r15b
0x1400a631d  jz      short loc_1400A6328
0x1400a631f  mov     r11b, 1
0x1400a6322  cmp     [r9+20h], r15b
0x1400a6326  jnz     short loc_1400A632B
0x1400a6328  mov     r11b, r15b
0x1400a632b  mov     [r14+17h], r11b
0x1400a632f  cmp     [r9+9], r15b
0x1400a6333  jz      short loc_1400A6344
0x1400a6335  mov     rcx, r9; this
0x1400a6338  call    ?IsDSCPToUPMappingAllowed@QoSManager@QoS@@QEBA_NXZ; QoS::QoSManager::IsDSCPToUPMappingAllowed(void)
0x1400a633d  mov     r8b, 1
0x1400a6340  test    al, al
0x1400a6342  jnz     short loc_1400A6347
0x1400a6344  mov     r8b, r15b
0x1400a6347  mov     [r14+18h], r8b
0x1400a634b  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400a6352  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400a6359  jz      short loc_1400A63C1
0x1400a635b  mov     rcx, r9; this
0x1400a635e  call    ?IsDSCPToUPMappingAllowed@QoSManager@QoS@@QEBA_NXZ; QoS::QoSManager::IsDSCPToUPMappingAllowed(void)
0x1400a6363  movzx   r10d, byte ptr [r9+0Ah]
0x1400a6368  movzx   ecx, al
0x1400a636b  movzx   eax, byte ptr [r9+9]
0x1400a6370  mov     [rsp+100h+var_A0], ecx
0x1400a6374  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a637b  mov     [rsp+100h+var_A8], eax
0x1400a637f  mov     eax, [rsi+10h]
0x1400a6382  movzx   edx, r8b
0x1400a6386  movzx   r8d, byte ptr [r9+20h]
0x1400a638b  mov     r9d, 15Dh
0x1400a6391  mov     rcx, [rcx+40h]
0x1400a6395  mov     [rsp+100h+var_B0], edx
0x1400a6399  mov     dl, 4
0x1400a639b  mov     [rsp+100h+var_B8], r8d
0x1400a63a0  mov     dword ptr [rsp+100h+var_C0], r10d
0x1400a63a5  movzx   r11d, r11b
0x1400a63a9  mov     dword ptr [rsp+100h+var_C8], r11d
0x1400a63ae  mov     dword ptr [rsp+100h+var_D0], eax
0x1400a63b2  mov     [rsp+100h+var_D8], rsi
0x1400a63b7  mov     [rsp+100h+var_E0], r12
0x1400a63bc  call    WPP_RECORDER_SF_qDdddddd
0x1400a63c1  mov     rcx, [rsi+218h]; this
0x1400a63c8  lea     rdx, [rbp+57h+var_80]; struct CAdapter *
0x1400a63cc  call    ?GetAdapterCapabilitiesFromPropertyCache@CConnectHelpers@@YAHPEAVCAdapter@@PEAPEBU_DOT11_ADAPTER_CAPABILITIES@@@Z; CConnectHelpers::GetAdapterCapabilitiesFromPropertyCache(CAdapter *,_DOT11_ADAPTER_CAPABILITIES const * *)
0x1400a63d1  mov     ebx, eax
0x1400a63d3  test    eax, eax
0x1400a63d5  jz      short loc_1400A63FA
0x1400a63d7  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400a63de  jz      loc_1400A6B8B
0x1400a63e4  mov     ecx, [rsi+10h]
0x1400a63e7  mov     r9d, 15Eh
0x1400a63ed  mov     dword ptr [rsp+100h+var_C8], eax
0x1400a63f1  mov     dword ptr [rsp+100h+var_D0], ecx
0x1400a63f5  jmp     loc_1400A6B2B
0x1400a63fa  mov     rax, [rbp+57h+var_80]
0x1400a63fe  cmp     dword ptr [rax+1A4h], 1
0x1400a6405  setz    al
0x1400a6408  mov     [r14+14h], al
0x1400a640c  mov     eax, [rsi+278h]
0x1400a6412  test    al, 10h
0x1400a6414  jz      short loc_1400A641E
0x1400a6416  mov     dword ptr [r14+10h], 1
0x1400a641e  movzx   edx, word ptr [rsi+3D0h]
0x1400a6425  lea     rcx, [r14+20h]
0x1400a6429  xor     r8d, r8d
0x1400a642c  call    ?AllocateElements@?$ArrayOfElements@U?$ArrayOfElements@E@@@@QEAAHI_K@Z; ArrayOfElements<ArrayOfElements<uchar>>::AllocateElements(uint,unsigned __int64)
0x1400a6431  mov     ebx, eax
0x1400a6433  test    eax, eax
0x1400a6435  jz      short loc_1400A6456
0x1400a6437  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400a643e  jz      loc_1400A6B8B
0x1400a6444  mov     r9d, 15Fh
0x1400a644a  lea     r12, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a6451  jmp     loc_1400A6B20
0x1400a6456  xor     ecx, ecx
0x1400a6458  mov     ebx, ecx
0x1400a645a  lea     r8, [rsi+284h]
0x1400a6461  cmp     ebx, [r8]
0x1400a6464  jnb     loc_1400A64EB
0x1400a646a  mov     edi, ebx
0x1400a646c  mov     rcx, [rsi+rdi*8+290h]
0x1400a6474  mov     rax, [rcx]
0x1400a6477  mov     rax, [rax+20h]
0x1400a647b  call    _guard_dispatch_icall
0x1400a6480  xor     ecx, ecx
0x1400a6482  test    al, al
0x1400a6484  jnz     short loc_1400A648A
0x1400a6486  inc     ebx
0x1400a6488  jmp     short loc_1400A645A
0x1400a648a  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a6491  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a6498  jz      short loc_1400A64DD
0x1400a649a  mov     rax, [rsi+rdi*8+290h]
0x1400a64a2  mov     r9d, 160h
0x1400a64a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a64af  add     rax, 20h ; ' '
0x1400a64b3  mov     qword ptr [rsp+100h+var_C8], rax
0x1400a64b8  mov     dl, 4
0x1400a64ba  mov     eax, [rsi+10h]
0x1400a64bd  mov     dword ptr [rsp+100h+var_D0], eax
0x1400a64c1  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a64c8  mov     rcx, [rcx+40h]
0x1400a64cc  mov     [rsp+100h+var_D8], rsi
0x1400a64d1  mov     [rsp+100h+var_E0], rax; struct _DOT11_SSID *
0x1400a64d6  call    WPP_RECORDER_SF_qD_MAC_
0x1400a64db  xor     ecx, ecx
0x1400a64dd  mov     r15b, 1
0x1400a64e0  lea     r8, [rsi+284h]
0x1400a64e7  mov     [r14+5], r15b
0x1400a64eb  mov     edi, ecx
0x1400a64ed  cmp     edi, [r14+20h]
0x1400a64f1  jnb     loc_1400A65C2
0x1400a64f7  mov     eax, edi
0x1400a64f9  lea     r9, [rax+rax*8]
0x1400a64fd  lea     rbx, [rax+rax*2]
0x1400a6501  test    r15b, r15b
0x1400a6504  jz      short loc_1400A653E
0x1400a6506  mov     r8d, [r8]; struct CBSSEntry **
0x1400a6509  lea     rdx, [rsi+290h]; struct _DOT11_SSID *
0x1400a6510  xor     eax, eax
0x1400a6512  xorps   xmm0, xmm0
0x1400a6515  mov     [rbp+57h+var_48], eax
0x1400a6518  mov     rax, [rsi+3D8h]
0x1400a651f  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x1400a6523  movups  [rbp+57h+var_58], xmm0
0x1400a6527  lea     rcx, [rax+r9*4]; this
0x1400a652b  lea     r9, [rbp+57h+var_68]; unsigned int
0x1400a652f  call    ?RemapSSID@CConnectHelpers@@YAHAEAU_DOT11_SSID@@QEAPEAVCBSSEntry@@K0@Z; CConnectHelpers::RemapSSID(_DOT11_SSID &,CBSSEntry * * const,ulong,_DOT11_SSID &)
0x1400a6534  mov     r8d, [rbp+57h+var_68]
0x1400a6538  lea     rdx, [rbp+57h+var_68+4]
0x1400a653c  jmp     short loc_1400A6551
0x1400a653e  mov     r8, [rsi+3D8h]
0x1400a6545  lea     rdx, [r8+4]
0x1400a6549  mov     r8d, [r8+r9*4]
0x1400a654d  lea     rdx, [rdx+r9*4]
0x1400a6551  mov     rax, [r14+28h]
0x1400a6555  lea     rcx, [rax+rbx*8]
0x1400a6559  call    ?SimpleSet@?$ArrayOfElements@E@@QEAAHPEBEI_K@Z; ArrayOfElements<uchar>::SimpleSet(uchar const *,uint,unsigned __int64)
0x1400a655e  mov     ebx, eax
0x1400a6560  test    eax, eax
0x1400a6562  jnz     short loc_1400A6572
0x1400a6564  inc     edi
0x1400a6566  lea     r8, [rsi+284h]
0x1400a656d  jmp     loc_1400A64ED
0x1400a6572  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a6579  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a6580  jz      loc_1400A6B8B
0x1400a6586  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a658d  lea     r12, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a6594  mov     eax, [rsi+10h]
0x1400a6597  mov     r9d, 161h
0x1400a659d  mov     dword ptr [rsp+100h+var_C8], ebx
0x1400a65a1  mov     dl, 2
0x1400a65a3  mov     dword ptr [rsp+100h+var_D0], eax
0x1400a65a7  mov     rcx, [rcx+40h]
0x1400a65ab  mov     [rsp+100h+var_D8], rsi
0x1400a65b0  mov     [rsp+100h+var_E0], r12
0x1400a65b5  call    WPP_RECORDER_SF_qDD
0x1400a65ba  xor     r15d, r15d
0x1400a65bd  jmp     loc_1400A6B47
0x1400a65c2  add     r13, 1E0h
0x1400a65c9  call    Feature_53299205__private_IsEnabledDeviceUsageNoInline
0x1400a65ce  xor     r15d, r15d
0x1400a65d1  test    eax, eax
0x1400a65d3  jz      short loc_1400A65EC
0x1400a65d5  mov     rax, [rsi+218h]
0x1400a65dc  mov     ecx, [rax+1228h]
0x1400a65e2  shr     ecx, 0Eh
0x1400a65e5  and     cl, 1
0x1400a65e8  mov     [r14+19h], cl
0x1400a65ec  lea     r12, [rsi+3D0h]
0x1400a65f3  movzx   edi, word ptr [r12+18h]
0x1400a65f9  test    di, di
0x1400a65fc  jz      loc_1400A66AF
0x1400a6602  mov     rbx, [rsi+3F0h]
0x1400a6609  lea     r15, [r14+40h]
0x1400a660d  mov     rcx, r15; void *
0x1400a6610  call    ?Cleanup@?$ArrayOfElements@U_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER@WiFiCxTLVStaging@@@@QEAAXXZ; ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(void)
0x1400a6615  mov     byte ptr [r15+10h], 0
0x1400a661a  lea     rcx, [r14+58h]; void *
0x1400a661e  mov     [r15], edi
0x1400a6621  mov     [r15+8], rbx
0x1400a6625  movzx   r12d, word ptr [rsi+3F8h]
0x1400a662d  mov     rbx, [rsi+400h]
0x1400a6634  call    ?Cleanup@?$ArrayOfElements@U_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER@WiFiCxTLVStaging@@@@QEAAXXZ; ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(void)
0x1400a6639  mov     byte ptr [r14+68h], 0
0x1400a663e  mov     [r14+58h], r12d
0x1400a6642  mov     [r14+60h], rbx
0x1400a6646  movzx   eax, byte ptr [rsi+3E0h]
0x1400a664d  or      dword ptr [r14], 1
0x1400a6651  mov     [r14+38h], al
0x1400a6655  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400a665c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400a6663  jz      short loc_1400A66A5
0x1400a6665  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a666c  mov     r9d, 162h
0x1400a6672  mov     [rsp+100h+var_B8], r12d
0x1400a6677  mov     dl, 4
0x1400a6679  mov     dword ptr [rsp+100h+var_C0], eax
0x1400a667d  mov     eax, [r15]
0x1400a6680  mov     rcx, [rcx+40h]
0x1400a6684  mov     dword ptr [rsp+100h+var_C8], eax
0x1400a6688  mov     eax, [rsi+10h]
0x1400a668b  mov     dword ptr [rsp+100h+var_D0], eax
0x1400a668f  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a6696  mov     [rsp+100h+var_D8], rsi
0x1400a669b  mov     [rsp+100h+var_E0], rax
0x1400a66a0  call    WPP_RECORDER_SF_qDddd
0x1400a66a5  xor     r15d, r15d
0x1400a66a8  lea     r12, [rsi+3D0h]
0x1400a66af  lea     r9, [rbp+57h+var_88]; unsigned __int8 **
0x1400a66b3  mov     edx, 87h; unsigned int
0x1400a66b8  lea     r8, [rbp+57h+var_90]; unsigned int *
0x1400a66bc  mov     rcx, r13; this
0x1400a66bf  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x1400a66c4  test    eax, eax
0x1400a66c6  jnz     short loc_1400A66F0
0x1400a66c8  mov     edi, [rbp+57h+var_90]
0x1400a66cb  test    edi, edi
0x1400a66cd  jz      short loc_1400A66F0
0x1400a66cf  lea     rbx, [r14+118h]
0x1400a66d6  mov     rcx, rbx; void *
0x1400a66d9  call    ?Cleanup@?$ArrayOfElements@U_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER@WiFiCxTLVStaging@@@@QEAAXXZ; ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(void)
0x1400a66de  mov     rax, [rbp+57h+var_88]
0x1400a66e2  mov     [rbx+8], rax
0x1400a66e6  mov     [rbx+10h], r15b
0x1400a66ea  mov     [rbx], edi
0x1400a66ec  or      dword ptr [r14], 20h
0x1400a66f0  mov     rdx, r14; struct _WDI_CONNECT_PARAMETERS_CONTAINER *
0x1400a66f3  mov     rcx, rsi; this
0x1400a66f6  call    ?SetUnicastAuthCipherInfo@CConnectJob@@AEAAHPEAU_WDI_CONNECT_PARAMETERS_CONTAINER@@@Z; CConnectJob::SetUnicastAuthCipherInfo(_WDI_CONNECT_PARAMETERS_CONTAINER *)
0x1400a66fb  mov     ebx, eax
0x1400a66fd  test    eax, eax
0x1400a66ff  jz      short loc_1400A672B
0x1400a6701  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a6708  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a670f  jz      loc_1400A6B8B
0x1400a6715  mov     r9d, 163h
  ... truncated ...
```
