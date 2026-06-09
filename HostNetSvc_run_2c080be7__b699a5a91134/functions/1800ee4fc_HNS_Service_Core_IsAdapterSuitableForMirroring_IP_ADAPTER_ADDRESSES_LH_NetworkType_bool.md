# HNS::Service::Core::IsAdapterSuitableForMirroring(_IP_ADAPTER_ADDRESSES_LH * &,NetworkType,bool)

- ea: `0x1800ee4fc`
- end: `0x1800eecdb`
- name: `?IsAdapterSuitableForMirroring@Core@Service@HNS@@YA_NAEAPEAU_IP_ADAPTER_ADDRESSES_LH@@W4NetworkType@@_N@Z`
- size: `2015`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800c9bd0`
- `0x1800f4090`

## callees

- `0x180001b68`
- `0x180001d38`
- `0x180002f60`
- `0x18005ecb0`
- `0x18005f0c0`
- `0x18005ffc4`
- `0x180061dc4`
- `0x18007c420`
- `0x18007c7f8`
- `0x18007cbc8`
- `0x1800805c4`
- `0x1800b19e4`
- `0x1800d7b20`
- `0x1800ee2d8`
- `0x1800ee4fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800ee5fa`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800eeb07`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800ee5fa`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800eeb07`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ee646`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ee726`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ee92b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ee9e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eeb52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ee646`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ee726`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ee92b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ee9e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eeb52`
- `IPHLPAPI!GetIfEntry2` at `0x1800ee576`
- `IPHLPAPI!GetIfEntry2` at `0x1800ee576`

## string_xrefs

- `0x1800eecc9`: `onecore\internal\sdk\inc\wil\opensource/wil/stl.h`
- `0x1800eecaf`: `onecore\vm\dv\net\hns\service\common\helperlib\src\iphelper.cpp`
- `0x1800ee5dc`: `HNS::Service::Core::IsAdapterSuitableForMirroring`
- `0x1800ee6c8`: `HNS::Service::Core::IsAdapterSuitableForMirroring`
- `0x1800ee703`: `HNS::Service::Core::IsAdapterSuitableForMirroring`
- `0x1800ee858`: `HNS::Service::Core::IsAdapterSuitableForMirroring`
- `0x1800ee986`: `HNS::Service::Core::IsAdapterSuitableForMirroring`
- `0x1800ee9c1`: `HNS::Service::Core::IsAdapterSuitableForMirroring`
- `0x1800ee9f6`: `HNS::Service::Core::IsAdapterSuitableForMirroring`
- `0x1800eea28`: `HNS::Service::Core::IsAdapterSuitableForMirroring`
- `0x1800eea7a`: `HNS::Service::Core::IsAdapterSuitableForMirroring`
- `0x1800eeae9`: `HNS::Service::Core::IsAdapterSuitableForMirroring`

## pseudocode

```c
unsigned __int8 __fastcall HNS::Service::Core::IsAdapterSuitableForMirroring(HKEY a1, int a2, unsigned __int8 a3)
{
  unsigned __int8 v3; // r15
  int v4; // ebx
  unsigned __int8 v6; // r14
  unsigned int IfEntry2; // eax
  int v8; // r9d
  __int16 PhysicalMediumType; // r13
  __int64 v10; // r8
  __int64 v11; // rsi
  HKEY *v12; // rax
  __int16 *trivial_2; // rax
  const char *v14; // r9
  __int64 v15; // rax
  int v16; // r8d
  int v17; // r9d
  int v18; // r15d
  __int64 v19; // rcx
  char *v20; // rax
  int v21; // ecx
  unsigned int v22; // r8d
  HKEY *v23; // rax
  int v24; // r8d
  int v25; // r9d
  int v26; // esi
  __int64 v27; // rcx
  HKEY *HnsServiceKey; // rax
  int v29; // r8d
  int v30; // r9d
  int v31; // esi
  wil *v33; // rcx
  unsigned int v34; // eax
  __int64 v35; // [rsp+20h] [rbp-6E8h]
  int v36; // [rsp+60h] [rbp-6A8h] BYREF
  _WORD v37[2]; // [rsp+64h] [rbp-6A4h] BYREF
  int v38; // [rsp+68h] [rbp-6A0h] BYREF
  int v39; // [rsp+6Ch] [rbp-69Ch] BYREF
  HKEY hKey[2]; // [rsp+70h] [rbp-698h] BYREF
  int v41; // [rsp+80h] [rbp-688h] BYREF
  int v42; // [rsp+84h] [rbp-684h] BYREF
  __int16 v43; // [rsp+88h] [rbp-680h]
  int v44; // [rsp+8Ch] [rbp-67Ch] BYREF
  int v45; // [rsp+90h] [rbp-678h] BYREF
  const char *v46; // [rsp+98h] [rbp-670h] BYREF
  HKEY v47[2]; // [rsp+A0h] [rbp-668h] BYREF
  int v48; // [rsp+B0h] [rbp-658h]
  char v49; // [rsp+B4h] [rbp-654h]
  HKEY v50[2]; // [rsp+B8h] [rbp-650h] BYREF
  int v51; // [rsp+C8h] [rbp-640h]
  char v52; // [rsp+CCh] [rbp-63Ch]
  struct _MIB_IF_ROW2 Row; // [rsp+D0h] [rbp-638h] BYREF
  _BYTE v54[32]; // [rsp+620h] [rbp-E8h] BYREF
  const char *v55; // [rsp+640h] [rbp-C8h]
  __int64 v56; // [rsp+648h] [rbp-C0h]
  HKEY *v57; // [rsp+650h] [rbp-B8h]
  __int64 v58; // [rsp+658h] [rbp-B0h]
  char *v59; // [rsp+660h] [rbp-A8h]
  int v60; // [rsp+668h] [rbp-A0h]
  int v61; // [rsp+66Ch] [rbp-9Ch]
  const char **v62; // [rsp+670h] [rbp-98h]
  __int64 v63; // [rsp+678h] [rbp-90h]
  int *v64; // [rsp+680h] [rbp-88h]
  __int64 v65; // [rsp+688h] [rbp-80h]
  _WORD *v66; // [rsp+690h] [rbp-78h]
  __int64 v67; // [rsp+698h] [rbp-70h]
  int *v68; // [rsp+6A0h] [rbp-68h]
  __int64 v69; // [rsp+6A8h] [rbp-60h]
  int *v70; // [rsp+6B0h] [rbp-58h]
  __int64 v71; // [rsp+6B8h] [rbp-50h]
  int *v72; // [rsp+6C0h] [rbp-48h]
  __int64 v73; // [rsp+6C8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+708h] [rbp+0h]

  v3 = a3;
  LOBYTE(v37[0]) = a3;
  v4 = a2;
  v38 = a2;
  hKey[0] = a1;
  v6 = 0;
  Row.InterfaceLuid.Value = 0;
  memset_0(&Row.InterfaceIndex, 0, 0x540u);
  Row.InterfaceIndex = *(_DWORD *)(*(_QWORD *)a1 + 4LL);
  IfEntry2 = GetIfEntry2(&Row);
  if ( IfEntry2 )
  {
    try
    {
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x788,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\iphelper.cpp",
        (const char *)IfEntry2,
        v35);
    }
    catch ( ... )
    {
      v34 = wil::ResultFromCaughtException(v33);
      LogError(
        v34,
        L"An exception was thrown while obtaining physical medium type for interface index %lu: %d",
        *(unsigned int *)(*(_QWORD *)hKey[0] + 4LL),
        v34);
      return 0;
    }
  }
  PhysicalMediumType = Row.PhysicalMediumType;
  v10 = *(_QWORD *)a1;
  switch ( *(_DWORD *)(*(_QWORD *)a1 + 100LL) )
  {
    case 6:
      if ( Row.PhysicalMediumType )
      {
        if ( Row.PhysicalMediumType != NdisPhysicalMedium802_3 && Row.PhysicalMediumType != NdisPhysicalMediumOther )
          goto LABEL_52;
      }
      else
      {
        if ( v3 )
        {
          v6 = 0;
LABEL_52:
          if ( !wcsstr(*(const wchar_t **)(v10 + 64), L"Microsoft Kernel Debug Network Adapter") )
            goto LABEL_60;
          v36 = 1;
          HnsServiceKey = (HKEY *)HNS::GetHnsServiceKey(hKey, 1, 131097);
          v47[0] = *HnsServiceKey;
          *HnsServiceKey = 0;
          v48 = 0;
          v49 = 1;
          if ( hKey[0] )
            RegCloseKey(hKey[0]);
          *(_OWORD *)hKey = *(_OWORD *)wil::basic_zstring_view<unsigned short>::basic_zstring_view<unsigned short>(
                                         v50,
                                         L"EnableMirroredKdnet");
          HNS::RegKey::GetValueDw(v47, hKey, &v36);
          v31 = v36;
          if ( *(_DWORD *)qword_1803999A8 > 4u )
          {
            v42 = v36;
            v39 = 132;
            hKey[0] = (HKEY)"HNS::Service::Core::IsAdapterSuitableForMirroring";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              qword_1803999A8,
              (unsigned int)&byte_1803377CF,
              v29,
              v30,
              (__int64)hKey,
              (__int64)&v39,
              (__int64)&v42);
          }
          if ( v31 != 1 )
            v6 = 0;
LABEL_40:
          if ( v47[0] )
          {
            RegCloseKey(v47[0]);
            goto LABEL_9;
          }
LABEL_60:
          v11 = -1;
          goto LABEL_22;
        }
        if ( *(_DWORD *)qword_1803999A8 > 4u )
        {
          v37[0] = v4;
          LOWORD(v36) = 0;
          v27 = *(_QWORD *)a1;
          v39 = *(_DWORD *)(*(_QWORD *)a1 + 100LL);
          v41 = *(_DWORD *)(v27 + 4);
          hKey[0] = *(HKEY *)(v27 + 72);
          v42 = 102;
          v46 = "HNS::Service::Core::IsAdapterSuitableForMirroring";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(
            qword_1803999A8,
            (unsigned int)byte_180337671,
            qword_1803999A8,
            v8,
            (__int64)&v46,
            (__int64)&v42,
            (__int64)hKey,
            (__int64)&v41,
            (__int64)&v39,
            (__int64)&v36,
            (__int64)v37);
        }
        v10 = *(_QWORD *)a1;
      }
      v6 = 1;
      goto LABEL_52;
    case 0x17:
LABEL_34:
      v36 = 1;
      v23 = (HKEY *)HNS::GetHnsServiceKey(hKey, 1, 131097);
      v47[0] = *v23;
      *v23 = 0;
      v48 = 0;
      v49 = 1;
      if ( hKey[0] )
        RegCloseKey(hKey[0]);
      *(_OWORD *)hKey = *(_OWORD *)wil::basic_zstring_view<unsigned short>::basic_zstring_view<unsigned short>(
                                     v50,
                                     L"EnableMirroredVpn");
      HNS::RegKey::GetValueDw(v47, hKey, &v36);
      v26 = v36;
      if ( *(_DWORD *)qword_1803999A8 > 4u )
      {
        v39 = v36;
        v41 = 219;
        hKey[0] = (HKEY)"HNS::Service::Core::IsAdapterSuitableForMirroring";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_1803999A8,
          (unsigned int)byte_180337701,
          v24,
          v25,
          (__int64)hKey,
          (__int64)&v41,
          (__int64)&v39);
      }
      if ( v26 == 1 )
        v6 = 1;
      goto LABEL_40;
    case 0x18:
      if ( v4 == 9 )
      {
        v22 = *(_DWORD *)Feature_HnsWcosLoopback__descriptor;
        if ( (*(_DWORD *)Feature_HnsWcosLoopback__descriptor & 4) == 0 )
        {
          hKey[0] = *(HKEY *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HnsWcosLoopback>::GetCachedFeatureEnabledState(
                               (unsigned int)(*(_DWORD *)(*(_QWORD *)a1 + 100LL) - 24),
                               hKey);
          v22 = (unsigned int)hKey[0];
        }
        v42 = 0;
        v43 = 3;
        wil::details::ReportUsageToService(&qword_1803A5CE0, 23636350, (v22 >> 10) & 1, (v22 >> 11) & 1, &v42, 1, 3);
        v6 = 1;
        goto LABEL_9;
      }
      goto LABEL_29;
    case 0x35:
      if ( v4 != 9 )
      {
        v6 = 0;
        goto LABEL_29;
      }
      goto LABEL_34;
    case 0x47:
      if ( wcsstr(*(const wchar_t **)(v10 + 64), L"Microsoft Wi-Fi Direct Virtual Adapter") )
      {
        v36 = 0;
        v12 = (HKEY *)HNS::GetHnsServiceKey(hKey, 1, 131097);
        v50[0] = *v12;
        *v12 = 0;
        v51 = 0;
        v52 = 1;
        if ( hKey[0] )
          RegCloseKey(hKey[0]);
        trivial_2 = (__int16 *)_std_find_trivial_2(L"EnableMirroredWiFiDirect", word_1802F4682, 0);
        if ( trivial_2 == word_1802F4682
          || (v15 = ((char *)trivial_2 - (char *)L"EnableMirroredWiFiDirect") >> 1, v11 = -1, v15 == -1) )
        {
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xEB,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/stl.h",
            v14);
        }
        hKey[0] = (HKEY)L"EnableMirroredWiFiDirect";
        hKey[1] = (HKEY)v15;
        HNS::RegKey::GetValueDw(v50, hKey, &v36);
        v18 = v36;
        if ( *(_DWORD *)qword_1803999A8 > 4u )
        {
          v41 = v36;
          v39 = 165;
          hKey[0] = (HKEY)"HNS::Service::Core::IsAdapterSuitableForMirroring";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            qword_1803999A8,
            (unsigned int)word_18033780A,
            v16,
            v17,
            (__int64)hKey,
            (__int64)&v39,
            (__int64)&v41);
        }
        if ( v18 == 1 )
          v6 = 1;
        if ( v50[0] )
          RegCloseKey(v50[0]);
        v3 = v37[0];
        goto LABEL_22;
      }
      goto LABEL_8;
  }
  if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)a1 + 100LL) - 243) <= 1 )
  {
LABEL_8:
    v6 = 1;
LABEL_9:
    v11 = -1;
LABEL_22:
    LOWORD(v4) = v38;
    goto LABEL_23;
  }
LABEL_29:
  v11 = -1;
LABEL_23:
  if ( *(_DWORD *)qword_1803999A8 > 4u )
  {
    v38 = v3;
    LOWORD(v36) = v4;
    v44 = v6;
    v37[0] = PhysicalMediumType;
    v19 = *(_QWORD *)a1;
    v45 = *(_DWORD *)(*(_QWORD *)a1 + 100LL);
    LODWORD(v46) = *(_DWORD *)(v19 + 4);
    v20 = *(char **)(v19 + 72);
    LODWORD(hKey[0]) = 253;
    v72 = &v38;
    v73 = 4;
    v70 = &v36;
    v21 = 2;
    v71 = 2;
    v68 = &v44;
    v69 = 4;
    v66 = v37;
    v67 = 2;
    v64 = &v45;
    v65 = 4;
    v62 = &v46;
    v63 = 4;
    if ( v20 )
    {
      do
        ++v11;
      while ( *(_WORD *)&v20[2 * v11] );
      v21 = 2 * v11 + 2;
    }
    else
    {
      v20 = byte_1802E2A80;
    }
    v59 = v20;
    v60 = v21;
    v61 = 0;
    v57 = hKey;
    v58 = 4;
    v55 = "HNS::Service::Core::IsAdapterSuitableForMirroring";
    v56 = 50;
    tlgWriteTransfer_EventWriteTransfer(qword_1803999A8, word_18033773A, 0, 0, 11, v54);
  }
  return v6;
}

```

## disassembly

```asm
0x1800ee4fc  mov     r11, rsp
0x1800ee4ff  mov     [r11+10h], rbx
0x1800ee503  mov     [r11+18h], rsi
0x1800ee507  push    rdi
0x1800ee508  push    r12
0x1800ee50a  push    r13
0x1800ee50c  push    r14
0x1800ee50e  push    r15
0x1800ee510  sub     rsp, 6E0h
0x1800ee517  mov     rax, cs:__security_cookie
0x1800ee51e  xor     rax, rsp
0x1800ee521  mov     [rsp+708h+var_38], rax
0x1800ee529  mov     r15b, r8b
0x1800ee52c  mov     byte ptr [rsp+708h+var_6A4], r8b
0x1800ee531  mov     ebx, edx
0x1800ee533  mov     [rsp+708h+var_6A0], edx
0x1800ee537  mov     r12, rcx
0x1800ee53a  mov     [rsp+708h+hKey], rcx
0x1800ee53f  xor     esi, esi
0x1800ee541  movzx   r14d, sil
0x1800ee545  mov     [r11-638h], rsi
0x1800ee54c  xor     edx, edx; Val
0x1800ee54e  mov     r8d, 540h; Size
0x1800ee554  lea     rcx, [r11-630h]; void *
0x1800ee55b  call    memset_0
0x1800ee560  mov     rax, [r12]
0x1800ee564  mov     ecx, [rax+4]
0x1800ee567  mov     [rsp+708h+Row.InterfaceIndex], ecx
0x1800ee56e  lea     rcx, [rsp+708h+Row]; Row
0x1800ee576  call    cs:__imp_GetIfEntry2
0x1800ee57c  mov     rcx, [rsp+708h]; this
0x1800ee584  test    eax, eax
0x1800ee586  jnz     loc_1800EECAC
0x1800ee58c  mov     r13d, [rsp+708h+Row.PhysicalMediumType]
0x1800ee594  mov     r8, [r12]
0x1800ee598  mov     ecx, [r8+64h]
0x1800ee59c  sub     ecx, 6
0x1800ee59f  jz      loc_1800EE9F1
0x1800ee5a5  sub     ecx, 11h
0x1800ee5a8  jz      loc_1800EE8EA
0x1800ee5ae  sub     ecx, 1
0x1800ee5b1  jz      loc_1800EE867
0x1800ee5b7  sub     ecx, 1Dh
0x1800ee5ba  jz      loc_1800EE848
0x1800ee5c0  sub     ecx, 12h
0x1800ee5c3  jz      short loc_1800EE5EF
0x1800ee5c5  sub     ecx, 0ACh
0x1800ee5cb  jz      short loc_1800EE5D6
0x1800ee5cd  cmp     ecx, 1
0x1800ee5d0  jnz     loc_1800EE854
0x1800ee5d6  mov     r14d, 1
0x1800ee5dc  lea     rdi, aHnsServiceCore_133; "HNS::Service::Core::IsAdapterSuitableFo"...
0x1800ee5e3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800ee5e7  xor     r8d, r8d
0x1800ee5ea  jmp     loc_1800EE734
0x1800ee5ef  lea     rdx, aMicrosoftWiFiD; "Microsoft Wi-Fi Direct Virtual Adapter"
0x1800ee5f6  mov     rcx, [r8+40h]; Str
0x1800ee5fa  call    cs:__imp_wcsstr
0x1800ee600  test    rax, rax
0x1800ee603  jz      short loc_1800EE5D6
0x1800ee605  mov     [rsp+708h+var_6A8], esi
0x1800ee609  mov     ebx, 1
0x1800ee60e  mov     r8d, 20019h
0x1800ee614  mov     edx, ebx
0x1800ee616  lea     rcx, [rsp+708h+hKey]
0x1800ee61b  call    ?GetHnsServiceKey@HNS@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@W4SERVICE_REGISTRY_STATE_TYPE@@K@Z; HNS::GetHnsServiceKey(SERVICE_REGISTRY_STATE_TYPE,ulong)
0x1800ee620  mov     rcx, [rax]
0x1800ee623  mov     [rsp+708h+var_650], rcx
0x1800ee62b  mov     [rax], rsi
0x1800ee62e  mov     [rsp+708h+var_640], esi
0x1800ee635  mov     [rsp+708h+var_63C], bl
0x1800ee63c  mov     rcx, [rsp+708h+hKey]; hKey
0x1800ee641  test    rcx, rcx
0x1800ee644  jz      short loc_1800EE64C
0x1800ee646  call    cs:__imp_RegCloseKey
0x1800ee64c  xor     r8d, r8d
0x1800ee64f  lea     rdi, word_1802F4682
0x1800ee656  mov     rdx, rdi
0x1800ee659  lea     r15, aEnablemirrored_1; "EnableMirroredWiFiDirect"
0x1800ee660  mov     rcx, r15
0x1800ee663  call    __std_find_trivial_2
0x1800ee668  cmp     rax, rdi
0x1800ee66b  jz      loc_1800EECC1
0x1800ee671  sub     rax, r15
0x1800ee674  sar     rax, 1
0x1800ee677  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800ee67b  cmp     rax, rsi
0x1800ee67e  jz      loc_1800EECC1
0x1800ee684  mov     [rsp+708h+hKey], r15
0x1800ee689  mov     [rsp+708h+hKey+8], rax
0x1800ee68e  lea     r8, [rsp+708h+var_6A8]
0x1800ee693  lea     rdx, [rsp+708h+hKey]
0x1800ee698  lea     rcx, [rsp+708h+var_650]
0x1800ee6a0  call    ?GetValueDw@RegKey@HNS@@QEAA_NV?$basic_zstring_view@G@wil@@AEAK@Z; HNS::RegKey::GetValueDw(wil::basic_zstring_view<ushort>,ulong &)
0x1800ee6a5  mov     rcx, cs:qword_1803999A8
0x1800ee6ac  mov     eax, [rcx]
0x1800ee6ae  cmp     eax, 4
0x1800ee6b1  jbe     short loc_1800EE703
0x1800ee6b3  mov     r15d, [rsp+708h+var_6A8]
0x1800ee6b8  mov     [rsp+708h+var_688], r15d
0x1800ee6c0  mov     [rsp+708h+var_69C], 0A5h
0x1800ee6c8  lea     rdi, aHnsServiceCore_133; "HNS::Service::Core::IsAdapterSuitableFo"...
0x1800ee6cf  mov     [rsp+708h+hKey], rdi
0x1800ee6d4  lea     rax, [rsp+708h+var_688]
0x1800ee6dc  mov     [rsp+708h+var_6D8], rax
0x1800ee6e1  lea     rax, [rsp+708h+var_69C]
0x1800ee6e6  mov     [rsp+708h+var_6E0], rax
0x1800ee6eb  lea     rax, [rsp+708h+hKey]
0x1800ee6f0  mov     [rsp+708h+var_6E8], rax
0x1800ee6f5  lea     rdx, word_18033780A
0x1800ee6fc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ee701  jmp     short loc_1800EE70F
0x1800ee703  lea     rdi, aHnsServiceCore_133; "HNS::Service::Core::IsAdapterSuitableFo"...
0x1800ee70a  mov     r15d, [rsp+708h+var_6A8]
0x1800ee70f  cmp     r15d, ebx
0x1800ee712  cmovz   r14d, ebx
0x1800ee716  mov     rcx, [rsp+708h+var_650]; hKey
0x1800ee71e  xor     r8d, r8d
0x1800ee721  test    rcx, rcx
0x1800ee724  jz      short loc_1800EE72F
0x1800ee726  call    cs:__imp_RegCloseKey
0x1800ee72c  xor     r8d, r8d
0x1800ee72f  mov     r15b, byte ptr [rsp+708h+var_6A4]
0x1800ee734  mov     ebx, [rsp+708h+var_6A0]
0x1800ee738  mov     r10, cs:qword_1803999A8
0x1800ee73f  mov     eax, [r10]
0x1800ee742  cmp     eax, 4
0x1800ee745  jbe     loc_1800EEC78
0x1800ee74b  movzx   eax, r15b
0x1800ee74f  mov     [rsp+708h+var_6A0], eax
0x1800ee753  mov     word ptr [rsp+708h+var_6A8], bx
0x1800ee758  movzx   eax, r14b
0x1800ee75c  mov     [rsp+708h+var_67C], eax
0x1800ee763  mov     [rsp+708h+var_6A4], r13w
0x1800ee769  mov     rcx, [r12]
0x1800ee76d  mov     eax, [rcx+64h]
0x1800ee770  mov     [rsp+708h+var_678], eax
0x1800ee777  mov     eax, [rcx+4]
0x1800ee77a  mov     dword ptr [rsp+708h+var_670], eax
0x1800ee781  mov     rax, [rcx+48h]
0x1800ee785  mov     dword ptr [rsp+708h+hKey], 0FDh
0x1800ee78d  lea     rcx, [rsp+708h+var_6A0]
0x1800ee792  mov     [rsp+708h+var_48], rcx
0x1800ee79a  mov     [rsp+708h+var_40], 4
0x1800ee7a6  lea     rcx, [rsp+708h+var_6A8]
0x1800ee7ab  mov     [rsp+708h+var_58], rcx
0x1800ee7b3  mov     ecx, 2
0x1800ee7b8  mov     [rsp+708h+var_50], rcx
0x1800ee7c0  lea     rdx, [rsp+708h+var_67C]
0x1800ee7c8  mov     [rsp+708h+var_68], rdx
0x1800ee7d0  mov     [rsp+708h+var_60], 4
0x1800ee7dc  lea     rdx, [rsp+708h+var_6A4]
0x1800ee7e1  mov     [rsp+708h+var_78], rdx
0x1800ee7e9  mov     [rsp+708h+var_70], rcx
0x1800ee7f1  lea     rdx, [rsp+708h+var_678]
0x1800ee7f9  mov     [rsp+708h+var_88], rdx
0x1800ee801  mov     [rsp+708h+var_80], 4
0x1800ee80d  lea     rdx, [rsp+708h+var_670]
0x1800ee815  mov     [rsp+708h+var_98], rdx
0x1800ee81d  mov     [rsp+708h+var_90], 4
0x1800ee829  test    rax, rax
0x1800ee82c  jz      loc_1800EEC03
0x1800ee832  inc     rsi
0x1800ee835  cmp     [rax+rsi*2], r8w
0x1800ee83a  jnz     short loc_1800EE832
0x1800ee83c  lea     ecx, ds:2[rsi*2]
0x1800ee843  jmp     loc_1800EEC0A
0x1800ee848  cmp     ebx, 9
0x1800ee84b  jz      loc_1800EE8EA
0x1800ee851  mov     r14b, sil
0x1800ee854  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800ee858  lea     rdi, aHnsServiceCore_133; "HNS::Service::Core::IsAdapterSuitableFo"...
0x1800ee85f  xor     r8d, r8d
0x1800ee862  jmp     loc_1800EE738
0x1800ee867  cmp     ebx, 9
0x1800ee86a  jnz     short loc_1800EE854
0x1800ee86c  mov     rax, cs:Feature_HnsWcosLoopback__descriptor
0x1800ee873  mov     r8d, [rax]
0x1800ee876  test    r8b, 4
0x1800ee87a  jnz     short loc_1800EE891
0x1800ee87c  lea     rdx, [rsp+708h+hKey]
0x1800ee881  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_HnsWcosLoopback@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HnsWcosLoopback>::GetCachedFeatureEnabledState(void)
0x1800ee886  mov     rcx, [rax]
0x1800ee889  mov     [rsp+708h+hKey], rcx
0x1800ee88e  mov     r8d, ecx
0x1800ee891  mov     [rsp+708h+var_684], esi
0x1800ee898  mov     [rsp+708h+var_680], 3
0x1800ee8a2  mov     r9d, r8d
0x1800ee8a5  shr     r9d, 0Bh
0x1800ee8a9  mov     ebx, 1
0x1800ee8ae  and     r9d, ebx
0x1800ee8b1  shr     r8d, 0Ah
0x1800ee8b5  and     r8d, ebx
0x1800ee8b8  mov     dword ptr [rsp+708h+var_6D8], 3
0x1800ee8c0  mov     dword ptr [rsp+708h+var_6E0], ebx
0x1800ee8c4  lea     rax, [rsp+708h+var_684]
0x1800ee8cc  mov     [rsp+708h+var_6E8], rax
0x1800ee8d1  mov     edx, 168A97Eh
0x1800ee8d6  lea     rcx, qword_1803A5CE0
0x1800ee8dd  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800ee8e2  mov     r14b, bl
0x1800ee8e5  jmp     loc_1800EE5DC
0x1800ee8ea  mov     ebx, 1
0x1800ee8ef  mov     [rsp+708h+var_6A8], ebx
0x1800ee8f3  mov     r8d, 20019h
0x1800ee8f9  mov     edx, ebx
0x1800ee8fb  lea     rcx, [rsp+708h+hKey]
0x1800ee900  call    ?GetHnsServiceKey@HNS@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@W4SERVICE_REGISTRY_STATE_TYPE@@K@Z; HNS::GetHnsServiceKey(SERVICE_REGISTRY_STATE_TYPE,ulong)
0x1800ee905  mov     rcx, [rax]
0x1800ee908  mov     [rsp+708h+var_668], rcx
0x1800ee910  mov     [rax], rsi
0x1800ee913  mov     [rsp+708h+var_658], esi
0x1800ee91a  mov     [rsp+708h+var_654], bl
0x1800ee921  mov     rcx, [rsp+708h+hKey]; hKey
0x1800ee926  test    rcx, rcx
0x1800ee929  jz      short loc_1800EE931
0x1800ee92b  call    cs:__imp_RegCloseKey
0x1800ee931  lea     rdx, aEnablemirrored_0; "EnableMirroredVpn"
0x1800ee938  lea     rcx, [rsp+708h+var_650]
0x1800ee940  call    ??$?0$0BC@@?$basic_zstring_view@G@wil@@QEAA@AEAY0BC@$$CBG@Z; wil::basic_zstring_view<ushort>::basic_zstring_view<ushort>(ushort const (&)[18])
0x1800ee945  movups  xmm0, xmmword ptr [rax]
0x1800ee948  movdqu  xmmword ptr [rsp+708h+hKey], xmm0
0x1800ee94e  lea     r8, [rsp+708h+var_6A8]
0x1800ee953  lea     rdx, [rsp+708h+hKey]
0x1800ee958  lea     rcx, [rsp+708h+var_668]
0x1800ee960  call    ?GetValueDw@RegKey@HNS@@QEAA_NV?$basic_zstring_view@G@wil@@AEAK@Z; HNS::RegKey::GetValueDw(wil::basic_zstring_view<ushort>,ulong &)
0x1800ee965  mov     rcx, cs:qword_1803999A8
0x1800ee96c  mov     eax, [rcx]
0x1800ee96e  cmp     eax, 4
0x1800ee971  jbe     short loc_1800EE9C1
0x1800ee973  mov     esi, [rsp+708h+var_6A8]
0x1800ee977  mov     [rsp+708h+var_69C], esi
0x1800ee97b  mov     [rsp+708h+var_688], 0DBh
0x1800ee986  lea     rdi, aHnsServiceCore_133; "HNS::Service::Core::IsAdapterSuitableFo"...
0x1800ee98d  mov     [rsp+708h+hKey], rdi
0x1800ee992  lea     rax, [rsp+708h+var_69C]
0x1800ee997  mov     [rsp+708h+var_6D8], rax
0x1800ee99c  lea     rax, [rsp+708h+var_688]
0x1800ee9a4  mov     [rsp+708h+var_6E0], rax
0x1800ee9a9  lea     rax, [rsp+708h+hKey]
0x1800ee9ae  mov     [rsp+708h+var_6E8], rax
0x1800ee9b3  lea     rdx, byte_180337701
0x1800ee9ba  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ee9bf  jmp     short loc_1800EE9CC
0x1800ee9c1  lea     rdi, aHnsServiceCore_133; "HNS::Service::Core::IsAdapterSuitableFo"...
0x1800ee9c8  mov     esi, [rsp+708h+var_6A8]
0x1800ee9cc  cmp     esi, ebx
0x1800ee9ce  cmovz   r14d, ebx
0x1800ee9d2  xor     r8d, r8d
0x1800ee9d5  mov     rcx, [rsp+708h+var_668]; hKey
0x1800ee9dd  test    rcx, rcx
0x1800ee9e0  jz      loc_1800EEBFA
0x1800ee9e6  call    cs:__imp_RegCloseKey
0x1800ee9ec  jmp     loc_1800EE5E3
0x1800ee9f1  test    r13d, r13d
0x1800ee9f4  jz      short loc_1800EEA1B
0x1800ee9f6  lea     rdi, aHnsServiceCore_133; "HNS::Service::Core::IsAdapterSuitableFo"...
0x1800ee9fd  cmp     r13d, 0Eh
0x1800eea01  jz      loc_1800EEAF4
0x1800eea07  cmp     r13d, 13h
0x1800eea0b  jz      loc_1800EEAF4
0x1800eea11  mov     ebx, 1
0x1800eea16  jmp     loc_1800EEAFC
0x1800eea1b  test    r15b, r15b
0x1800eea1e  jz      short loc_1800EEA34
0x1800eea20  mov     r14b, sil
0x1800eea23  mov     ebx, 1
0x1800eea28  lea     rdi, aHnsServiceCore_133; "HNS::Service::Core::IsAdapterSuitableFo"...
0x1800eea2f  jmp     loc_1800EEAFC
0x1800eea34  mov     r8, cs:qword_1803999A8
0x1800eea3b  mov     eax, [r8]
0x1800eea3e  cmp     eax, 4
0x1800eea41  jbe     loc_1800EEAE9
0x1800eea47  mov     [rsp+708h+var_6A4], bx
0x1800eea4c  mov     word ptr [rsp+708h+var_6A8], si
0x1800eea51  mov     rcx, [r12]
0x1800eea55  mov     eax, [rcx+64h]
0x1800eea58  mov     [rsp+708h+var_69C], eax
0x1800eea5c  mov     eax, [rcx+4]
0x1800eea5f  mov     [rsp+708h+var_688], eax
0x1800eea66  mov     rax, [rcx+48h]
0x1800eea6a  mov     [rsp+708h+hKey], rax
0x1800eea6f  mov     [rsp+708h+var_684], 66h ; 'f'
0x1800eea7a  lea     rdi, aHnsServiceCore_133; "HNS::Service::Core::IsAdapterSuitableFo"...
0x1800eea81  mov     [rsp+708h+var_670], rdi
0x1800eea89  lea     rax, [rsp+708h+var_6A4]
0x1800eea8e  mov     [rsp+708h+var_6B8], rax
0x1800eea93  lea     rax, [rsp+708h+var_6A8]
0x1800eea98  mov     [rsp+708h+var_6C0], rax
0x1800eea9d  lea     rax, [rsp+708h+var_69C]
0x1800eeaa2  mov     [rsp+708h+var_6C8], rax
0x1800eeaa7  lea     rax, [rsp+708h+var_688]
0x1800eeaaf  mov     [rsp+708h+var_6D0], rax
0x1800eeab4  lea     rax, [rsp+708h+hKey]
0x1800eeab9  mov     [rsp+708h+var_6D8], rax
0x1800eeabe  lea     rax, [rsp+708h+var_684]
0x1800eeac6  mov     [rsp+708h+var_6E0], rax
0x1800eeacb  lea     rax, [rsp+708h+var_670]
0x1800eead3  mov     [rsp+708h+var_6E8], rax
0x1800eead8  lea     rdx, byte_180337671
  ... truncated ...
```
