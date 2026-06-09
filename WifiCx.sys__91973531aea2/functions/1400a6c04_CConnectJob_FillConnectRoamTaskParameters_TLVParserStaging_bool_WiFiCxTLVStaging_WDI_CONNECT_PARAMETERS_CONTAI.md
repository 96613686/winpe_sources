# CConnectJob::FillConnectRoamTaskParameters_TLVParserStaging(bool,WiFiCxTLVStaging::_WDI_CONNECT_PARAMETERS_CONTAINER *,ArrayOfElements<WiFiCxTLVStaging::_WDI_CONNECT_BSS_ENTRY_CONTAINER> *)

- ea: `0x1400a6c04`
- end: `0x1400a73cd`
- name: `?FillConnectRoamTaskParameters_TLVParserStaging@CConnectJob@@AEAAH_NPEAU_WDI_CONNECT_PARAMETERS_CONTAINER@WiFiCxTLVStaging@@PEAU?$ArrayOfElements@U_WDI_CONNECT_BSS_ENTRY_CONTAINER@WiFiCxTLVStaging@@@@@Z`
- size: `1993`
- prototype: `__int64 __fastcall(CConnectJob *this)`
- caller_count: `2`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x140030d88`
- `0x140032f4c`

## callees

- `0x14000688c`
- `0x14000c778`
- `0x14000d054`
- `0x140014b30`
- `0x14001a630`
- `0x14001c220`
- `0x14001e2c0`
- `0x14002bd34`
- `0x14002ef48`
- `0x140050660`
- `0x140050dc8`
- `0x14005eb84`
- `0x1400735b4`
- `0x1400800d8`
- `0x140080488`
- `0x1400a5b1c`
- `0x1400a5fec`
- `0x1400a6c04`
- `0x1400a9fec`
- `0x1400ab50c`
- `0x1400b1784`
- `0x1400b33c8`
- `0x1400b42a4`
- `0x1400b4980`
- `0x1400dfd00`
- `0x1400dfd40`
- `0x1400dfe00`
- `0x1400e0100`

## pseudocode

```c
__int64 __fastcall CConnectJob::FillConnectRoamTaskParameters_TLVParserStaging(
        CConnectJob *this,
        __int16 a2,
        _DWORD *a3,
        __int64 a4)
{
  int v7; // edx
  unsigned int Elements; // ebx
  int v9; // r8d
  int v10; // r9d
  bool v12; // r15
  unsigned int i; // ebx
  const struct _DOT11_ADAPTER_CAPABILITIES **v14; // r8
  __int64 v15; // rcx
  int v16; // edx
  int v17; // r8d
  unsigned int j; // edi
  struct CBSSEntry **v19; // r8
  __int64 v20; // rax
  __int64 v21; // r8
  unsigned int *v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  CConnectHelpers *v25; // rcx
  struct _DOT11_ADAPTER_CAPABILITIES *v26; // r13
  struct _WFC_CONNECTION_PROFILE_PARAMETERS *v27; // r15
  int v28; // edi
  __int64 v29; // rbx
  int v30; // r12d
  __int64 v31; // rbx
  int v32; // edx
  int v33; // r8d
  char v34; // al
  unsigned __int16 v35; // dx
  CAdapter *v36; // rcx
  struct CPortPropertyCache *v37; // r12
  unsigned int v38; // edi
  unsigned int v39; // edi
  int v40; // r15d
  __int64 v41; // rbx
  unsigned int v42; // ebx
  const void *v43; // r15
  __int64 v44; // rdi
  __int64 v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rdx
  int v48; // r8d
  unsigned int v49; // r9d
  unsigned int k; // r8d
  CConnectHelpers *v51; // rdi
  struct CPort *v52; // rdx
  __int16 v53; // dx
  char v54; // bl
  struct _DOT11_SSID *v55; // [rsp+20h] [rbp-59h]
  struct _DOT11_SSID *v56; // [rsp+20h] [rbp-59h]
  char v57; // [rsp+28h] [rbp-51h]
  int v58; // [rsp+30h] [rbp-49h]
  char v59[8]; // [rsp+38h] [rbp-41h]
  bool v60; // [rsp+50h] [rbp-29h]
  unsigned int v61; // [rsp+54h] [rbp-25h] BYREF
  struct _DOT11_ADAPTER_CAPABILITIES *v62; // [rsp+58h] [rbp-21h] BYREF
  CConnectHelpers *PortFromPortId; // [rsp+60h] [rbp-19h]
  __int64 v64; // [rsp+68h] [rbp-11h]
  unsigned int v65[4]; // [rsp+70h] [rbp-9h] BYREF
  __int128 v66; // [rsp+80h] [rbp+7h]
  int v67; // [rsp+90h] [rbp+17h]

  v60 = a2;
  v64 = a4;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 5;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        334,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids);
  }
  memset(a3, 0, 0x178u);
  *(_OWORD *)a4 = 0;
  *(_QWORD *)(a4 + 16) = 0;
  Elements = ArrayOfElements<ArrayOfElements<unsigned char>>::AllocateElements(
               a3 + 8,
               *((unsigned __int16 *)this + 488),
               0);
  if ( Elements )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v10 = 335;
      goto LABEL_8;
    }
    return Elements;
  }
  v12 = 0;
  for ( i = 0; ; ++i )
  {
    v14 = (const struct _DOT11_ADAPTER_CAPABILITIES **)((char *)this + 644);
    if ( i >= *((_DWORD *)this + 161) )
      break;
    v15 = *((_QWORD *)this + i + 82);
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v15 + 32LL))(v15) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v16) = 4;
        WPP_RECORDER_SF_qD_MAC_(
          WPP_GLOBAL_Control->DeviceExtension,
          v16,
          v17,
          336,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          *((_QWORD *)this + i + 82) + 32LL);
      }
      v12 = 1;
      v14 = (const struct _DOT11_ADAPTER_CAPABILITIES **)((char *)this + 644);
      break;
    }
  }
  for ( j = 0; j < a3[8]; ++j )
  {
    if ( v12 )
    {
      v19 = (struct CBSSEntry **)*(unsigned int *)v14;
      v67 = 0;
      v20 = *((_QWORD *)this + 123);
      *(_OWORD *)v65 = 0;
      v66 = 0;
      CConnectHelpers::RemapSSID(
        (struct _DOT11_SSID *)(v20 + 36LL * j),
        (struct _DOT11_SSID *)((char *)this + 656),
        v19,
        (unsigned int)v65,
        v55);
      v21 = v65[0];
      v22 = &v65[1];
    }
    else
    {
      v23 = *((_QWORD *)this + 123);
      v24 = v23 + 4;
      v21 = *(unsigned int *)(v23 + 36LL * j);
      v22 = (unsigned int *)(v24 + 36LL * j);
    }
    Elements = ArrayOfElements<unsigned char>::SimpleSet(*((_QWORD *)a3 + 5) + 24LL * j, v22, v21);
    if ( Elements )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return Elements;
      v10 = 337;
      *(_DWORD *)v59 = Elements;
      v58 = *((_DWORD *)this + 4);
      goto LABEL_27;
    }
    v14 = (const struct _DOT11_ADAPTER_CAPABILITIES **)((char *)this + 644);
  }
  v25 = (CConnectHelpers *)*((_QWORD *)this + 67);
  v62 = 0;
  Elements = CConnectHelpers::GetAdapterCapabilitiesFromPropertyCache(v25, (struct CAdapter *)&v62, v14);
  if ( Elements )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return Elements;
    v10 = 338;
LABEL_31:
    *(_DWORD *)v59 = Elements;
    v58 = *((_DWORD *)this + 4);
LABEL_27:
    v57 = (char)this;
    goto LABEL_9;
  }
  v26 = v62;
  Elements = CConnectJob::FillConnectRoamTaskConnectionSettings(
               this,
               v60,
               v12,
               v62,
               (struct _WDI_CONNECT_PARAMETERS_CONTAINER *)a3);
  if ( Elements )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return Elements;
    v10 = 339;
    goto LABEL_31;
  }
  v27 = (CConnectJob *)((char *)this + 976);
  v28 = *((unsigned __int16 *)this + 500);
  if ( (_WORD)v28 )
  {
    v29 = *((_QWORD *)this + 126);
    ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(a3 + 16);
    *((_BYTE *)a3 + 80) = 0;
    a3[16] = v28;
    *((_QWORD *)a3 + 9) = v29;
    v30 = *((unsigned __int16 *)this + 508);
    v31 = *((_QWORD *)this + 128);
    ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(a3 + 22);
    *((_BYTE *)a3 + 104) = 0;
    a3[22] = v30;
    *((_QWORD *)a3 + 12) = v31;
    v34 = *((_BYTE *)this + 992);
    *a3 |= 1u;
    *((_BYTE *)a3 + 56) = v34;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v32) = 4;
      WPP_RECORDER_SF_qDddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v32,
        v33,
        340,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        a3[16],
        v34,
        v30);
    }
    v27 = (CConnectJob *)((char *)this + 976);
  }
  v35 = *((_WORD *)this + 26);
  v36 = (CAdapter *)*((_QWORD *)this + 67);
  v61 = 0;
  v62 = 0;
  PortFromPortId = CAdapter::GetPortFromPortId(v36, v35);
  v37 = (CConnectHelpers *)((char *)PortFromPortId + 480);
  if ( !(unsigned int)CPropertyCache::GetPropertyBuffer(
                        (CConnectHelpers *)((char *)PortFromPortId + 480),
                        0x87u,
                        &v61,
                        (unsigned __int8 **)&v62) )
  {
    v38 = v61;
    if ( v61 )
    {
      ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(a3 + 70);
      *((_QWORD *)a3 + 36) = v62;
      *((_BYTE *)a3 + 296) = 0;
      a3[70] = v38;
      *a3 |= 0x20u;
    }
  }
  Elements = CConnectJob::SetUnicastAuthCipherInfo_TLVParserStaging(
               this,
               (struct _WDI_CONNECT_PARAMETERS_CONTAINER *)a3);
  if ( Elements )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return Elements;
    v10 = 341;
    goto LABEL_31;
  }
  Elements = CConnectJob::SetMultiCastCipherList_TLVParserStaging(
               this,
               v37,
               v27,
               (struct _WDI_CONNECT_PARAMETERS_CONTAINER *)a3);
  if ( Elements )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return Elements;
    v10 = 342;
    goto LABEL_31;
  }
  Elements = CConnectJob::SetRsnaAkmCipherPairs_TLVParserStaging(
               this,
               *((_BYTE *)a3 + 21) != 0,
               *((_DWORD *)this + 283),
               *((_DWORD *)this + 284),
               (struct _WDI_CONNECT_PARAMETERS_CONTAINER *)a3);
  if ( Elements )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return Elements;
    v10 = 343;
    goto LABEL_31;
  }
  if ( !(unsigned int)CPropertyCache::GetPropertyBuffer(v37, 0xEu, &v61, (unsigned __int8 **)&v62) )
  {
    v39 = v61;
    if ( v61 )
    {
      ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(a3 + 46);
      *((_QWORD *)a3 + 24) = v62;
      *((_BYTE *)a3 + 200) = 0;
      a3[46] = v39;
      *a3 |= 2u;
    }
  }
  v40 = *((unsigned __int16 *)this + 544);
  if ( (_WORD)v40 )
  {
    v41 = *((_QWORD *)this + 137);
    ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(a3 + 64);
    *((_BYTE *)a3 + 272) = 0;
    a3[64] = v40;
    *((_QWORD *)a3 + 33) = v41;
    *a3 |= 0x10u;
  }
  v42 = 0;
  v43 = 0;
  v44 = *((unsigned __int16 *)this + 556);
  if ( !*((_BYTE *)this + 2784) && *((_DWORD *)v26 + 114) == 1 )
  {
    v45 = *((_QWORD *)this + 67);
    v42 = *(_DWORD *)(v45 + 1436);
    v43 = (const void *)(v45 + 1440);
  }
  if ( v42 + (_DWORD)v44 )
  {
    ArrayOfElements<_WDI_MAC_ADDRESS>::AllocateElements(a3 + 58, v42 + (unsigned int)v44, 0);
    *a3 |= 8u;
    if ( (_WORD)v44 )
      memmove(*((void **)a3 + 30), *((const void **)this + 140), 6 * v44);
    if ( v42 )
      memmove((void *)(*((_QWORD *)a3 + 30) + 6 * v44), v43, 6LL * v42);
  }
  *a3 &= ~4u;
  v46 = *((unsigned int *)this + 315);
  if ( (_DWORD)v46 )
  {
    Elements = ArrayOfElements<enum _WDI_BAND_ID>::AllocateElements(a3 + 76, v46, 0);
    if ( Elements )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v47) = 2;
        WPP_RECORDER_SF_qDdd(
          WPP_GLOBAL_Control->DeviceExtension,
          v47,
          v48,
          344,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          *((_DWORD *)this + 315),
          Elements);
      }
      return Elements;
    }
    v49 = 0;
    for ( k = 0; k < *((unsigned __int8 *)this + 1160); ++k )
    {
      if ( !*((_DWORD *)this + k + 316) && v49 < *((_DWORD *)this + 315) )
      {
        v47 = v49++;
        *(_DWORD *)(*((_QWORD *)a3 + 39) + 4 * v47) = *((_DWORD *)this + 3 * k + 291);
      }
    }
    *a3 |= 0x40u;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v47) = 4;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v47,
        1,
        345,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids);
    }
  }
  v51 = PortFromPortId;
  v52 = (struct CPort *)*((_QWORD *)this + 67);
  v61 = 0;
  CConnectHelpers::GetSupportedAssociationMethods(
    PortFromPortId,
    v52,
    (CConnectJob *)((char *)this + 976),
    (struct _WFC_CONNECTION_PROFILE_PARAMETERS *)&v61,
    &v56->uSSIDLength);
  if ( v60
    && CPropertyCache::GetPropertyBooleanOrDefault(v37, 0x14u, 0)
    && !(unsigned __int8)CConnectHelpers::IsIMDAssocForFTRoamRequired(
                           *((unsigned int *)this + 156),
                           *((unsigned int *)this + 158)) )
  {
    v54 = 1;
  }
  else
  {
    v54 = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v53) = 4;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v53,
        1,
        346,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids);
    }
  }
  Elements = CConnectHelpers::FillConnectBSSEntryTLV(
               v51,
               (unsigned int *)this + 161,
               (struct CBSSEntry **)this + 82,
               v64,
               1,
               v54);
  if ( Elements )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v10 = 347;
LABEL_8:
      *(_DWORD *)v59 = Elements;
      v58 = *((_DWORD *)this + 4);
      v57 = (char)this;
LABEL_9:
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        v9,
        v10,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        v57,
        v58,
        *(_QWORD *)v59);
    }
    return Elements;
  }
  return 0;
}

```

## disassembly

```asm
0x1400a6c04  mov     [rsp-8+arg_8], rbx
0x1400a6c09  push    rbp
0x1400a6c0a  push    rsi
0x1400a6c0b  push    rdi
0x1400a6c0c  push    r12
0x1400a6c0e  push    r13
0x1400a6c10  push    r14
0x1400a6c12  push    r15
0x1400a6c14  lea     rbp, [rsp-27h]
0x1400a6c19  sub     rsp, 0A0h
0x1400a6c20  mov     rax, cs:__security_cookie
0x1400a6c27  xor     rax, rsp
0x1400a6c2a  mov     [rbp+57h+var_38], rax
0x1400a6c2e  mov     rbx, r9
0x1400a6c31  mov     [rbp+57h+var_80], dl
0x1400a6c34  mov     [rbp+57h+var_68], rbx
0x1400a6c38  mov     r14, r8
0x1400a6c3b  mov     rsi, rcx
0x1400a6c3e  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400a6c45  xor     r13d, r13d
0x1400a6c48  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400a6c4f  lea     r15, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a6c56  jz      short loc_1400A6C87
0x1400a6c58  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6c5f  mov     dl, 5
0x1400a6c61  cmp     [rcx+29h], dl
0x1400a6c64  jnb     short loc_1400A6C6D
0x1400a6c66  cmp     [rcx+48h], r13w
0x1400a6c6b  jz      short loc_1400A6C87
0x1400a6c6d  mov     rcx, [rcx+40h]
0x1400a6c71  mov     r9d, 14Eh
0x1400a6c77  mov     r8d, 1
0x1400a6c7d  mov     [rsp+0D0h+var_B0], r15
0x1400a6c82  call    WPP_RECORDER_SF_
0x1400a6c87  xor     edx, edx; Val
0x1400a6c89  mov     r8d, 178h; Size
0x1400a6c8f  mov     rcx, r14; void *
0x1400a6c92  call    memset
0x1400a6c97  xorps   xmm0, xmm0
0x1400a6c9a  lea     rcx, [r14+20h]
0x1400a6c9e  movups  xmmword ptr [rbx], xmm0
0x1400a6ca1  xor     eax, eax
0x1400a6ca3  xor     r8d, r8d
0x1400a6ca6  mov     [rbx+10h], rax
0x1400a6caa  movzx   edx, word ptr [rsi+3D0h]
0x1400a6cb1  call    ?AllocateElements@?$ArrayOfElements@U?$ArrayOfElements@E@@@@QEAAHI_K@Z
0x1400a6cb6  mov     ebx, eax
0x1400a6cb8  test    eax, eax
0x1400a6cba  jz      short loc_1400A6CF9
0x1400a6cbc  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400a6cc3  jz      short loc_1400A6CF2
0x1400a6cc5  mov     r9d, 14Fh
0x1400a6ccb  mov     ecx, [rsi+10h]
0x1400a6cce  mov     dword ptr [rsp+0D0h+var_98], ebx
0x1400a6cd2  mov     dword ptr [rsp+0D0h+var_A0], ecx
0x1400a6cd6  mov     [rsp+0D0h+var_A8], rsi
0x1400a6cdb  mov     [rsp+0D0h+var_B0], r15
0x1400a6ce0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6ce7  mov     dl, 2
0x1400a6ce9  mov     rcx, [rcx+40h]
0x1400a6ced  call    WPP_RECORDER_SF_qDD
0x1400a6cf2  mov     eax, ebx
0x1400a6cf4  jmp     loc_1400A73A5
0x1400a6cf9  mov     r15b, r13b
0x1400a6cfc  mov     ebx, r13d
0x1400a6cff  lea     r8, [rsi+284h]
0x1400a6d06  cmp     ebx, [r8]
0x1400a6d09  jnb     short loc_1400A6D84
0x1400a6d0b  mov     edi, ebx
0x1400a6d0d  mov     rcx, [rsi+rdi*8+290h]
0x1400a6d15  mov     rax, [rcx]
0x1400a6d18  mov     rax, [rax+20h]
0x1400a6d1c  call    _guard_dispatch_icall
0x1400a6d21  test    al, al
0x1400a6d23  jnz     short loc_1400A6D29
0x1400a6d25  inc     ebx
0x1400a6d27  jmp     short loc_1400A6CFF
0x1400a6d29  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a6d30  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a6d37  jz      short loc_1400A6D7A
0x1400a6d39  mov     rax, [rsi+rdi*8+290h]
0x1400a6d41  mov     r9d, 150h
0x1400a6d47  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6d4e  add     rax, 20h ; ' '
0x1400a6d52  mov     qword ptr [rsp+0D0h+var_98], rax
0x1400a6d57  mov     dl, 4
0x1400a6d59  mov     eax, [rsi+10h]
0x1400a6d5c  mov     dword ptr [rsp+0D0h+var_A0], eax
0x1400a6d60  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a6d67  mov     rcx, [rcx+40h]
0x1400a6d6b  mov     [rsp+0D0h+var_A8], rsi
0x1400a6d70  mov     [rsp+0D0h+var_B0], rax; struct _DOT11_SSID *
0x1400a6d75  call    WPP_RECORDER_SF_qD_MAC_
0x1400a6d7a  mov     r15b, 1
0x1400a6d7d  lea     r8, [rsi+284h]; struct _DOT11_ADAPTER_CAPABILITIES **
0x1400a6d84  mov     edi, r13d
0x1400a6d87  cmp     edi, [r14+20h]
0x1400a6d8b  jnb     loc_1400A6E47
0x1400a6d91  mov     eax, edi
0x1400a6d93  lea     r9, [rax+rax*8]
0x1400a6d97  lea     rbx, [rax+rax*2]
0x1400a6d9b  test    r15b, r15b
0x1400a6d9e  jz      short loc_1400A6DD8
0x1400a6da0  mov     r8d, [r8]; struct CBSSEntry **
0x1400a6da3  lea     rdx, [rsi+290h]; struct _DOT11_SSID *
0x1400a6daa  xor     eax, eax
0x1400a6dac  xorps   xmm0, xmm0
0x1400a6daf  mov     [rbp+57h+var_40], eax
0x1400a6db2  mov     rax, [rsi+3D8h]
0x1400a6db9  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1400a6dbd  movups  [rbp+57h+var_50], xmm0
0x1400a6dc1  lea     rcx, [rax+r9*4]; this
0x1400a6dc5  lea     r9, [rbp+57h+var_60]; unsigned int
0x1400a6dc9  call    ?RemapSSID@CConnectHelpers@@YAHAEAU_DOT11_SSID@@QEAPEAVCBSSEntry@@K0@Z
0x1400a6dce  mov     r8d, [rbp+57h+var_60]
0x1400a6dd2  lea     rdx, [rbp+57h+var_60+4]
0x1400a6dd6  jmp     short loc_1400A6DEB
0x1400a6dd8  mov     r8, [rsi+3D8h]
0x1400a6ddf  lea     rdx, [r8+4]
0x1400a6de3  mov     r8d, [r8+r9*4]
0x1400a6de7  lea     rdx, [rdx+r9*4]
0x1400a6deb  mov     rax, [r14+28h]
0x1400a6def  lea     rcx, [rax+rbx*8]
0x1400a6df3  call    ?SimpleSet@?$ArrayOfElements@E@@QEAAHPEBEI_K@Z
0x1400a6df8  mov     ebx, eax
0x1400a6dfa  test    eax, eax
0x1400a6dfc  jnz     short loc_1400A6E0C
0x1400a6dfe  inc     edi
0x1400a6e00  lea     r8, [rsi+284h]
0x1400a6e07  jmp     loc_1400A6D87
0x1400a6e0c  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a6e13  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a6e1a  jz      loc_1400A6CF2
0x1400a6e20  mov     eax, [rsi+10h]
0x1400a6e23  mov     r9d, 151h
0x1400a6e29  mov     dword ptr [rsp+0D0h+var_98], ebx
0x1400a6e2d  mov     dword ptr [rsp+0D0h+var_A0], eax
0x1400a6e31  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a6e38  mov     [rsp+0D0h+var_A8], rsi
0x1400a6e3d  mov     [rsp+0D0h+var_B0], rax
0x1400a6e42  jmp     loc_1400A6CE0
0x1400a6e47  mov     rcx, [rsi+218h]; this
0x1400a6e4e  lea     rdx, [rbp+57h+var_78]; struct CAdapter *
0x1400a6e52  mov     [rbp+57h+var_78], r13
0x1400a6e56  call    ?GetAdapterCapabilitiesFromPropertyCache@CConnectHelpers@@YAHPEAVCAdapter@@PEAPEBU_DOT11_ADAPTER_CAPABILITIES@@@Z
0x1400a6e5b  mov     ebx, eax
0x1400a6e5d  test    eax, eax
0x1400a6e5f  jz      short loc_1400A6E88
0x1400a6e61  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a6e68  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a6e6f  jz      loc_1400A6CF2
0x1400a6e75  mov     r9d, 152h
0x1400a6e7b  mov     ecx, [rsi+10h]
0x1400a6e7e  mov     dword ptr [rsp+0D0h+var_98], ebx
0x1400a6e82  mov     dword ptr [rsp+0D0h+var_A0], ecx
0x1400a6e86  jmp     short loc_1400A6E31
0x1400a6e88  mov     r13, [rbp+57h+var_78]
0x1400a6e8c  mov     r8b, r15b; bool
0x1400a6e8f  mov     dl, [rbp+57h+var_80]; bool
0x1400a6e92  mov     r9, r13; struct _DOT11_ADAPTER_CAPABILITIES *
0x1400a6e95  mov     rcx, rsi; this
0x1400a6e98  mov     [rsp+0D0h+var_B0], r14; struct _WDI_CONNECT_PARAMETERS_CONTAINER *
0x1400a6e9d  call    ?FillConnectRoamTaskConnectionSettings@CConnectJob@@AEAAH_N0PEBU_DOT11_ADAPTER_CAPABILITIES@@PEAU_WDI_CONNECT_PARAMETERS_CONTAINER@WiFiCxTLVStaging@@@Z
0x1400a6ea2  xor     r12d, r12d
0x1400a6ea5  mov     ebx, eax
0x1400a6ea7  test    eax, eax
0x1400a6ea9  jz      short loc_1400A6EC7
0x1400a6eab  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a6eb2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a6eb9  jz      loc_1400A6CF2
0x1400a6ebf  mov     r9d, 153h
0x1400a6ec5  jmp     short loc_1400A6E7B
0x1400a6ec7  lea     r15, [rsi+3D0h]
0x1400a6ece  movzx   edi, word ptr [r15+18h]
0x1400a6ed3  test    di, di
0x1400a6ed6  jz      loc_1400A6F85
0x1400a6edc  mov     rbx, [rsi+3F0h]
0x1400a6ee3  lea     r15, [r14+40h]
0x1400a6ee7  mov     rcx, r15; void *
0x1400a6eea  call    ?Cleanup@?$ArrayOfElements@U_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER@WiFiCxTLVStaging@@@@QEAAXXZ
0x1400a6eef  mov     [r15+10h], r12b
0x1400a6ef3  lea     rcx, [r14+58h]; void *
0x1400a6ef7  mov     [r15], edi
0x1400a6efa  mov     [r15+8], rbx
0x1400a6efe  movzx   r12d, word ptr [rsi+3F8h]
0x1400a6f06  mov     rbx, [rsi+400h]
0x1400a6f0d  call    ?Cleanup@?$ArrayOfElements@U_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER@WiFiCxTLVStaging@@@@QEAAXXZ
0x1400a6f12  mov     byte ptr [r14+68h], 0
0x1400a6f17  mov     [r14+58h], r12d
0x1400a6f1b  mov     [r14+60h], rbx
0x1400a6f1f  movzx   eax, byte ptr [rsi+3E0h]
0x1400a6f26  or      dword ptr [r14], 1
0x1400a6f2a  mov     [r14+38h], al
0x1400a6f2e  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400a6f35  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400a6f3c  jz      short loc_1400A6F7E
0x1400a6f3e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6f45  mov     r9d, 154h
0x1400a6f4b  mov     [rsp+0D0h+var_88], r12d
0x1400a6f50  mov     dl, 4
0x1400a6f52  mov     dword ptr [rsp+0D0h+var_90], eax
0x1400a6f56  mov     eax, [r15]
0x1400a6f59  mov     rcx, [rcx+40h]
0x1400a6f5d  mov     dword ptr [rsp+0D0h+var_98], eax
0x1400a6f61  mov     eax, [rsi+10h]
0x1400a6f64  mov     dword ptr [rsp+0D0h+var_A0], eax
0x1400a6f68  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a6f6f  mov     [rsp+0D0h+var_A8], rsi
0x1400a6f74  mov     [rsp+0D0h+var_B0], rax
0x1400a6f79  call    WPP_RECORDER_SF_qDddd
0x1400a6f7e  lea     r15, [rsi+3D0h]
0x1400a6f85  movzx   edx, word ptr [rsi+34h]; unsigned __int16
0x1400a6f89  xor     edi, edi
0x1400a6f8b  mov     rcx, [rsi+218h]; this
0x1400a6f92  mov     [rbp+57h+var_7C], edi
0x1400a6f95  mov     [rbp+57h+var_78], rdi
0x1400a6f99  call    ?GetPortFromPortId@CAdapter@@QEAAPEAVCPort@@G@Z
0x1400a6f9e  lea     r9, [rbp+57h+var_78]; unsigned __int8 **
0x1400a6fa2  mov     [rbp+57h+var_70], rax
0x1400a6fa6  lea     r8, [rbp+57h+var_7C]; unsigned int *
0x1400a6faa  mov     edx, 87h; unsigned int
0x1400a6faf  lea     r12, [rax+1E0h]
0x1400a6fb6  mov     rcx, r12; this
0x1400a6fb9  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z
0x1400a6fbe  test    eax, eax
0x1400a6fc0  jnz     short loc_1400A6FEC
0x1400a6fc2  mov     edi, [rbp+57h+var_7C]
0x1400a6fc5  test    edi, edi
0x1400a6fc7  jz      short loc_1400A6FEA
0x1400a6fc9  lea     rbx, [r14+118h]
0x1400a6fd0  mov     rcx, rbx; void *
0x1400a6fd3  call    ?Cleanup@?$ArrayOfElements@U_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER@WiFiCxTLVStaging@@@@QEAAXXZ
0x1400a6fd8  mov     rax, [rbp+57h+var_78]
0x1400a6fdc  mov     [rbx+8], rax
0x1400a6fe0  mov     byte ptr [rbx+10h], 0
0x1400a6fe4  mov     [rbx], edi
0x1400a6fe6  or      dword ptr [r14], 20h
0x1400a6fea  xor     edi, edi
0x1400a6fec  mov     rdx, r14; struct _WDI_CONNECT_PARAMETERS_CONTAINER *
0x1400a6fef  mov     rcx, rsi; this
0x1400a6ff2  call    ?SetUnicastAuthCipherInfo_TLVParserStaging@CConnectJob@@AEAAHPEAU_WDI_CONNECT_PARAMETERS_CONTAINER@WiFiCxTLVStaging@@@Z
0x1400a6ff7  mov     ebx, eax
0x1400a6ff9  test    eax, eax
0x1400a6ffb  jz      short loc_1400A701C
0x1400a6ffd  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a7004  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a700b  jz      loc_1400A6CF2
0x1400a7011  mov     r9d, 155h
0x1400a7017  jmp     loc_1400A6E7B
0x1400a701c  mov     r9, r14; struct _WDI_CONNECT_PARAMETERS_CONTAINER *
0x1400a701f  mov     r8, r15; struct _WFC_CONNECTION_PROFILE_PARAMETERS *
0x1400a7022  mov     rdx, r12; struct CPortPropertyCache *
0x1400a7025  mov     rcx, rsi; this
0x1400a7028  call    ?SetMultiCastCipherList_TLVParserStaging@CConnectJob@@AEAAHPEAVCPortPropertyCache@@PEAU_WFC_CONNECTION_PROFILE_PARAMETERS@@PEAU_WDI_CONNECT_PARAMETERS_CONTAINER@WiFiCxTLVStaging@@@Z
0x1400a702d  mov     ebx, eax
0x1400a702f  test    eax, eax
0x1400a7031  jz      short loc_1400A7052
0x1400a7033  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a703a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a7041  jz      loc_1400A6CF2
0x1400a7047  mov     r9d, 156h
0x1400a704d  jmp     loc_1400A6E7B
0x1400a7052  cmp     [r14+15h], dil
0x1400a7056  mov     rcx, rsi; this
0x1400a7059  mov     r9d, [rsi+470h]; unsigned int
0x1400a7060  mov     r8d, [rsi+46Ch]; unsigned int
0x1400a7067  setnz   dl; bool
0x1400a706a  mov     [rsp+0D0h+var_B0], r14; unsigned int *
0x1400a706f  call    ?SetRsnaAkmCipherPairs_TLVParserStaging@CConnectJob@@AEAAH_NKKPEAU_WDI_CONNECT_PARAMETERS_CONTAINER@WiFiCxTLVStaging@@@Z
0x1400a7074  mov     ebx, eax
0x1400a7076  test    eax, eax
0x1400a7078  jz      short loc_1400A7099
0x1400a707a  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a7081  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a7088  jz      loc_1400A6CF2
0x1400a708e  mov     r9d, 157h
0x1400a7094  jmp     loc_1400A6E7B
0x1400a7099  lea     r9, [rbp+57h+var_78]; unsigned __int8 **
0x1400a709d  mov     edx, 0Eh; unsigned int
0x1400a70a2  lea     r8, [rbp+57h+var_7C]; unsigned int *
0x1400a70a6  mov     rcx, r12; this
0x1400a70a9  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z
0x1400a70ae  test    eax, eax
0x1400a70b0  jnz     short loc_1400A70DF
0x1400a70b2  mov     edi, [rbp+57h+var_7C]
0x1400a70b5  xor     r15d, r15d
0x1400a70b8  test    edi, edi
0x1400a70ba  jz      short loc_1400A70DD
0x1400a70bc  lea     rbx, [r14+0B8h]
0x1400a70c3  mov     rcx, rbx; void *
0x1400a70c6  call    ?Cleanup@?$ArrayOfElements@U_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER@WiFiCxTLVStaging@@@@QEAAXXZ
0x1400a70cb  mov     rax, [rbp+57h+var_78]
0x1400a70cf  mov     [rbx+8], rax
0x1400a70d3  mov     [rbx+10h], r15b
0x1400a70d7  mov     [rbx], edi
0x1400a70d9  or      dword ptr [r14], 2
0x1400a70dd  xor     edi, edi
0x1400a70df  movzx   r15d, word ptr [rsi+440h]
0x1400a70e7  test    r15w, r15w
0x1400a70eb  jz      short loc_1400A7114
  ... truncated ...
```
