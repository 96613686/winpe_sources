# ShieldProvider::HardwareShield::GetSecureBootCertStatusBasedOnRegistry(PillarStatus *)

- ea: `0x1800b1558`
- end: `0x1800b1c90`
- name: `?GetSecureBootCertStatusBasedOnRegistry@HardwareShield@ShieldProvider@@AEAAJPEAUPillarStatus@@@Z`
- size: `1848`
- prototype: `__int64 __fastcall(ShieldProvider::HardwareShield *__hidden this, struct PillarStatus *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b9f28`

## callees

- `0x180001a1c`
- `0x180002f04`
- `0x180004ae0`
- `0x18000d7fc`
- `0x1800afd00`
- `0x1800b1558`
- `0x1800b2cf0`
- `0x1800b4e34`
- `0x1800bd12c`
- `0x1800be02c`
- `0x1800cd900`
- `0x1800cd944`
- `0x1800ce8f8`
- `0x1800dc038`
- `0x1800dd908`
- `0x1800ddaa8`
- `0x1800dde6c`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800b1734`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800b1755`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800b1776`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800b1797`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800b1875`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800b18b9`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800b1734`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800b1755`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800b1776`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800b1797`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800b1875`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800b18b9`
- `KERNEL32!CompareStringOrdinal` at `0x1800b17c6`
- `KERNEL32!CompareStringOrdinal` at `0x1800b17c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b1664`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b1c74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b1664`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b1c74`

## string_xrefs

- `0x1800b188b`: `KEKLastUpdateErrorReason`
- `0x1800b17bc`: `Updated`
- `0x1800b184f`: `DBLastUpdateErrorReason`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ShieldProvider::HardwareShield::GetSecureBootCertStatusBasedOnRegistry(
        ShieldProvider::HardwareShield *this,
        struct PillarStatus *a2)
{
  int v3; // eax
  HKEY v4; // rdi
  const struct std::nothrow_t *v5; // rdx
  const unsigned __int16 *v6; // r8
  unsigned int *v7; // r9
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  const struct std::nothrow_t *v11; // rdx
  const unsigned __int16 *v12; // r8
  int v13; // eax
  wchar_t *v14; // rbx
  wchar_t *v15; // rax
  wchar_t *v16; // rax
  wchar_t *v17; // rax
  wchar_t *v18; // rax
  wchar_t *v19; // r14
  int v20; // r12d
  int Vuln; // r15d
  int IsPostExpiry; // ecx
  int v23; // r12d
  unsigned int v24; // r13d
  int ValueString; // eax
  wchar_t *v26; // r15
  wchar_t *v27; // rax
  int v28; // ecx
  int v29; // eax
  __int64 v30; // rdx
  wchar_t *v31; // rsi
  wchar_t *v32; // rax
  int v33; // ecx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  char IsEnabled; // al
  __int64 v38; // rcx
  int v39; // ecx
  __int64 v40; // rcx
  const struct std::nothrow_t *v41; // rdx
  __int64 v42; // rsi
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  unsigned int bIgnoreCase; // [rsp+20h] [rbp-79h]
  unsigned __int64 v47; // [rsp+60h] [rbp-39h]
  LPCWCH lpString1; // [rsp+68h] [rbp-31h] BYREF
  wchar_t *Str; // [rsp+70h] [rbp-29h] BYREF
  unsigned __int16 v50[2]; // [rsp+78h] [rbp-21h] BYREF
  int v51; // [rsp+7Ch] [rbp-1Dh]
  int v52; // [rsp+80h] [rbp-19h]
  int v53; // [rsp+84h] [rbp-15h]
  int v54; // [rsp+88h] [rbp-11h]
  HKEY hKey; // [rsp+90h] [rbp-9h] BYREF
  wchar_t *NameForPillarStatus; // [rsp+98h] [rbp-1h] BYREF
  wchar_t *NameForPillarHealth; // [rsp+A0h] [rbp+7h] BYREF
  int v58; // [rsp+A8h] [rbp+Fh]
  int v61; // [rsp+110h] [rbp+77h] BYREF
  int v62; // [rsp+118h] [rbp+7Fh] BYREF

  if ( !a2 )
    return 2147942487LL;
  hKey = 0;
  v3 = CommonUtil::UtilRegOpenKey(
         (CommonUtil *)&hKey,
         (HKEY *)0xFFFFFFFF80000002LL,
         (HKEY)&stru_1800FF4B0,
         (const unsigned __int16 *)0x20019,
         bIgnoreCase);
  v4 = hKey;
  if ( v3 >= 0 )
  {
    *(_DWORD *)v50 = 0;
    lpString1 = 0;
    if ( (unsigned int)CommonUtil::UtilRegGetValueString(hKey, L"UEFICA2023Status", &lpString1) == -2147024894 )
    {
      if ( lpString1 )
      {
        operator delete((void *)lpString1, v5);
        lpString1 = 0;
      }
      v8 = CommonUtil::NewSprintfW((CommonUtil *)&lpString1, (unsigned __int16 **)&word_1800F4E78, v6);
      v9 = v8;
      if ( v8 < 0 )
      {
        v10 = (__int64)&WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          v10 = 1;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              332,
              &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
              (unsigned int)v8);
        }
LABEL_11:
        if ( lpString1 )
          operator delete((void *)lpString1, (const struct std::nothrow_t *)v10);
        if ( v4 )
          RegCloseKey(v4);
        return v9;
      }
    }
    if ( (unsigned int)CommonUtil::UtilRegGetValueDword((CommonUtil *)v4, (HKEY)&stru_1800FF5E0, v50, v7) == -2147024894 )
      *(_DWORD *)v50 = 0;
    Str = 0;
    if ( (unsigned int)CommonUtil::UtilRegGetValueString(v4, L"ConfidenceLevel", &Str) == -2147024894 )
    {
      if ( Str )
      {
        operator delete(Str, v11);
        Str = 0;
      }
      v13 = CommonUtil::NewSprintfW((CommonUtil *)&Str, (unsigned __int16 **)&word_1800F4E78, v12);
      v9 = v13;
      if ( v13 < 0 )
      {
        v10 = (__int64)&WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          v10 = 1;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              333,
              &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
              (unsigned int)v13);
        }
        if ( Str )
          operator delete(Str, (const struct std::nothrow_t *)v10);
        goto LABEL_11;
      }
    }
    v14 = Str;
    if ( !Str || (v15 = wcsstr(Str, L"Paused"), v51 = 1, !v15) )
      v51 = 0;
    if ( !v14 || (v16 = wcsstr(v14, L"Not Supported"), v54 = 1, !v16) )
      v54 = 0;
    if ( !v14 || (v17 = wcsstr(v14, L"Under Observation"), v52 = 1, !v17) )
      v52 = 0;
    if ( !v14 || (v18 = wcsstr(v14, L"No Data Observed"), v53 = 1, !v18) )
      v53 = 0;
    v19 = (wchar_t *)lpString1;
    if ( !lpString1 || (v20 = 1, CompareStringOrdinal(lpString1, -1, L"Updated", -1, 1) != 2) )
      v20 = 0;
    Vuln = ShieldProvider::HardwareShield::IsAfterFirstVuln();
    v61 = Vuln;
    IsPostExpiry = ShieldProvider::HardwareShield::IsPostExpiry();
    v58 = IsPostExpiry;
    if ( v20 )
    {
      v23 = 2044;
      v47 = 0x2000007FCLL;
      v24 = 2;
LABEL_101:
      v42 = v47;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Secureboot_states_phase2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Secureboot_states_phase2>::GetImpl'::`2'::impl)
        && !(unsigned __int8)ShieldProvider::IsEqualPillarStatus(v47, *((_QWORD *)this + 28))
        && (unsigned int)dword_18012F280 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18012F280, 0x800000000000LL) )
      {
        v61 = v58;
        v62 = Vuln;
        NameForPillarHealth = (wchar_t *)ShieldProvider::GetNameForPillarHealth(v24);
        NameForPillarStatus = (wchar_t *)ShieldProvider::GetNameForPillarStatus(v23);
        hKey = (HKEY)v14;
        Str = v19;
        lpString1 = (LPCWCH)0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v43,
          (unsigned int)&dword_18012255C,
          v44,
          v45,
          (__int64)&lpString1,
          (__int64)&Str,
          (__int64)&hKey,
          (__int64)&NameForPillarStatus,
          (__int64)&NameForPillarHealth,
          (__int64)&v62,
          (__int64)&v61);
      }
      if ( v14 )
        operator delete(v14, v41);
      if ( v19 )
        operator delete(v19, v41);
      goto LABEL_111;
    }
    v24 = Vuln != 0 ? 8 : 2;
    if ( IsPostExpiry )
    {
      if ( Vuln )
      {
        v23 = 2047;
        LODWORD(v47) = 2047;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Secureboot_states_phase2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Secureboot_states_phase2>::GetImpl'::`2'::impl) )
        {
          v62 = 0;
          HIDWORD(v47) = Vuln != 0 ? 8 : 2;
          if ( (int)ShieldProvider::HardwareShield::GetIsErrorStateDismissed(v34, 2047, &v62) >= 0 )
          {
            HIDWORD(v47) = Vuln != 0 ? 8 : 2;
            if ( v62 )
            {
              v23 = 2055;
              v47 = 0x200000807LL;
              v24 = 2;
            }
          }
          ShieldProvider::HardwareShield::SendSecureBootCertToast(v35, 309);
LABEL_47:
          v62 = 0;
          NameForPillarStatus = 0;
          NameForPillarHealth = 0;
          ValueString = CommonUtil::UtilRegGetValueString(v4, L"DBLastUpdateErrorReason", &NameForPillarStatus);
          v26 = NameForPillarStatus;
          if ( ValueString >= 0 && NameForPillarStatus )
          {
            v27 = wcsstr(NameForPillarStatus, L"Firmware");
            v28 = v62;
            if ( v27 )
              v28 = 1;
            v62 = v28;
          }
          v29 = CommonUtil::UtilRegGetValueString(v4, L"KEKLastUpdateErrorReason", &NameForPillarHealth);
          v31 = NameForPillarHealth;
          if ( v29 >= 0 && NameForPillarHealth )
          {
            v32 = wcsstr(NameForPillarHealth, L"Firmware");
            v33 = v62;
            v30 = 1;
            if ( v32 )
              v33 = 1;
          }
          else
          {
            v33 = v62;
          }
          if ( v51 )
          {
            v23 = 2048;
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Secureboot_states_phase2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Secureboot_states_phase2>::GetImpl'::`2'::impl) )
            {
              LODWORD(v47) = 2048;
              v62 = 0;
              if ( !v61 )
                goto LABEL_96;
              v23 = 2049;
              v47 = 0x800000801LL;
              v24 = 8;
              if ( (int)ShieldProvider::HardwareShield::GetIsErrorStateDismissed(v36, 2049, &v62) < 0 || !v62 )
                goto LABEL_96;
              v23 = 2056;
              goto LABEL_92;
            }
          }
          else
          {
            if ( !v52 && !v53 )
            {
              if ( !v54 && !v33 )
                goto LABEL_96;
              IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Secureboot_states_phase2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Secureboot_states_phase2>::GetImpl'::`2'::impl);
              v23 = 2052;
              v62 = 0;
              if ( IsEnabled )
              {
                v47 = 0x400000804LL;
                v24 = 4;
                if ( !v61 )
                {
                  if ( (*(int (__fastcall **)(ShieldProvider::HardwareShield *, __int64, int *))(*(_QWORD *)this + 48LL))(
                         this,
                         2052,
                         &v62) >= 0
                    && v62 )
                  {
                    v23 = 2053;
                    v47 = 0x200000805LL;
                    v24 = 2;
                  }
                  ShieldProvider::HardwareShield::SendSecureBootCertToast(v38, 308);
                  goto LABEL_96;
                }
                v23 = 2054;
                v47 = 0x800000806LL;
                v24 = 8;
                if ( (int)ShieldProvider::HardwareShield::GetIsErrorStateDismissed(0, 2054, &v62) < 0 || !v62 )
                {
LABEL_96:
                  if ( v31 )
                    operator delete(v31, (const struct std::nothrow_t *)v30);
                  if ( v26 )
                    operator delete(v26, (const struct std::nothrow_t *)v30);
                  Vuln = v61;
                  goto LABEL_101;
                }
                v23 = 2053;
                goto LABEL_92;
              }
              (*(void (__fastcall **)(ShieldProvider::HardwareShield *, __int64, int *))(*(_QWORD *)this + 48LL))(
                this,
                2052,
                &v62);
              if ( v61 )
              {
                v23 = 2054;
                v24 = 8;
LABEL_93:
                v47 = __PAIR64__(v24, v23);
                goto LABEL_96;
              }
              v39 = (v62 != 0) + 2052;
              v30 = (unsigned int)-v62;
              v24 = v62 != 0 ? 2 : 4;
              HIDWORD(v47) = v24;
LABEL_95:
              v23 = v39;
              LODWORD(v47) = v39;
              goto LABEL_96;
            }
            v23 = 2050;
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Secureboot_states_phase2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Secureboot_states_phase2>::GetImpl'::`2'::impl) )
            {
              LODWORD(v47) = 2050;
              v62 = 0;
              if ( !v61 )
                goto LABEL_96;
              v23 = 2051;
              v47 = 0x800000803LL;
              v24 = 8;
              if ( (int)ShieldProvider::HardwareShield::GetIsErrorStateDismissed(v40, 2051, &v62) < 0 || !v62 )
                goto LABEL_96;
              v23 = 2057;
LABEL_92:
              v24 = 2;
              goto LABEL_93;
            }
          }
          v39 = v23 + (v61 != 0);
          goto LABEL_95;
        }
      }
      else
      {
        v23 = 2046;
        LODWORD(v47) = 2046;
      }
    }
    else
    {
      v23 = 2045;
      LODWORD(v47) = 2045;
      v24 = 2;
    }
    HIDWORD(v47) = v24;
    goto LABEL_47;
  }
  v42 = 0x2000007D1LL;
LABEL_111:
  *(_QWORD *)a2 = v42;
  if ( v4 )
    RegCloseKey(v4);
  return 0;
}

```

## disassembly

```asm
0x1800b1558  mov     [rsp-8+arg_8], rdx
0x1800b155d  mov     [rsp-8+arg_0], rcx
0x1800b1562  push    rbp
0x1800b1563  push    rbx
0x1800b1564  push    rsi
0x1800b1565  push    rdi
0x1800b1566  push    r12
0x1800b1568  push    r13
0x1800b156a  push    r14
0x1800b156c  push    r15
0x1800b156e  lea     rbp, [rsp-1Fh]
0x1800b1573  sub     rsp, 0B8h
0x1800b157a  xor     r13d, r13d
0x1800b157d  test    rdx, rdx
0x1800b1580  jnz     short loc_1800B158C
0x1800b1582  mov     eax, 80070057h
0x1800b1587  jmp     loc_1800B1C7C
0x1800b158c  mov     dword ptr [rbp+57h+var_90], 7D1h
0x1800b1593  mov     dword ptr [rbp+57h+var_90+4], 2
0x1800b159a  mov     [rbp+57h+hKey], r13
0x1800b159e  mov     r9d, 20019h; unsigned __int16 *
0x1800b15a4  lea     r8, stru_1800FF4B0; HKEY
0x1800b15ab  mov     rdx, 0FFFFFFFF80000002h; HKEY *
0x1800b15b2  lea     rcx, [rbp+57h+hKey]; this
0x1800b15b6  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEBGK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,ushort const *,ulong)
0x1800b15bb  mov     rdi, [rbp+57h+hKey]
0x1800b15bf  test    eax, eax
0x1800b15c1  js      loc_1800B1C61
0x1800b15c7  mov     dword ptr [rbp+57h+var_78], r13d
0x1800b15cb  mov     [rbp+57h+lpString1], r13
0x1800b15cf  lea     r8, [rbp+57h+lpString1]
0x1800b15d3  lea     rdx, aUefica2023stat; "UEFICA2023Status"
0x1800b15da  mov     rcx, rdi
0x1800b15dd  call    ?UtilRegGetValueString@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAPEAGW4UTIL_REG_EXPAND_STRING@1@PEAK@Z; CommonUtil::UtilRegGetValueString(HKEY__ *,ushort const *,ushort * *,CommonUtil::UTIL_REG_EXPAND_STRING,ulong *)
0x1800b15e2  mov     esi, 80070002h
0x1800b15e7  cmp     eax, esi
0x1800b15e9  jnz     loc_1800B1671
0x1800b15ef  mov     rcx, [rbp+57h+lpString1]; void *
0x1800b15f3  test    rcx, rcx
0x1800b15f6  jz      short loc_1800B1601
0x1800b15f8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b15fd  mov     [rbp+57h+lpString1], r13
0x1800b1601  lea     rdx, word_1800F4E78; unsigned __int16 **
0x1800b1608  lea     rcx, [rbp+57h+lpString1]; this
0x1800b160c  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x1800b1611  mov     ebx, eax
0x1800b1613  test    eax, eax
0x1800b1615  jns     short loc_1800B1671
0x1800b1617  lea     rdx, WPP_GLOBAL_Control
0x1800b161e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b1625  cmp     rcx, rdx
0x1800b1628  jz      short loc_1800B164D
0x1800b162a  mov     edx, 1
0x1800b162f  test    [rcx+1Ch], dl
0x1800b1632  jz      short loc_1800B164D
0x1800b1634  mov     edx, 14Ch
0x1800b1639  mov     r9d, eax
0x1800b163c  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800b1643  mov     rcx, [rcx+10h]
0x1800b1647  call    WPP_SF_d
0x1800b164c  nop
0x1800b164d  mov     rcx, [rbp+57h+lpString1]; void *
0x1800b1651  test    rcx, rcx
0x1800b1654  jz      short loc_1800B165C
0x1800b1656  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b165b  nop
0x1800b165c  test    rdi, rdi
0x1800b165f  jz      short loc_1800B166A
0x1800b1661  mov     rcx, rdi; hKey
0x1800b1664  call    cs:__imp_RegCloseKey
0x1800b166a  mov     eax, ebx
0x1800b166c  jmp     loc_1800B1C7C
0x1800b1671  lea     r8, [rbp+57h+var_78]; unsigned __int16 *
0x1800b1675  lea     rdx, stru_1800FF5E0; HKEY
0x1800b167c  mov     rcx, rdi; this
0x1800b167f  call    ?UtilRegGetValueDword@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAK@Z; CommonUtil::UtilRegGetValueDword(HKEY__ *,ushort const *,ulong *)
0x1800b1684  cmp     eax, esi
0x1800b1686  jnz     short loc_1800B168C
0x1800b1688  mov     dword ptr [rbp+57h+var_78], r13d
0x1800b168c  mov     [rbp+57h+Str], r13
0x1800b1690  lea     r8, [rbp+57h+Str]
0x1800b1694  lea     rdx, aConfidenceleve; "ConfidenceLevel"
0x1800b169b  mov     rcx, rdi
0x1800b169e  call    ?UtilRegGetValueString@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAPEAGW4UTIL_REG_EXPAND_STRING@1@PEAK@Z; CommonUtil::UtilRegGetValueString(HKEY__ *,ushort const *,ushort * *,CommonUtil::UTIL_REG_EXPAND_STRING,ulong *)
0x1800b16a3  cmp     eax, esi
0x1800b16a5  jnz     short loc_1800B171C
0x1800b16a7  mov     rcx, [rbp+57h+Str]; void *
0x1800b16ab  test    rcx, rcx
0x1800b16ae  jz      short loc_1800B16B9
0x1800b16b0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b16b5  mov     [rbp+57h+Str], r13
0x1800b16b9  lea     rdx, word_1800F4E78; unsigned __int16 **
0x1800b16c0  lea     rcx, [rbp+57h+Str]; this
0x1800b16c4  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x1800b16c9  mov     ebx, eax
0x1800b16cb  test    eax, eax
0x1800b16cd  jns     short loc_1800B171C
0x1800b16cf  lea     rdx, WPP_GLOBAL_Control
0x1800b16d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b16dd  cmp     rcx, rdx
0x1800b16e0  jz      short loc_1800B1705
0x1800b16e2  mov     edx, 1
0x1800b16e7  test    [rcx+1Ch], dl
0x1800b16ea  jz      short loc_1800B1705
0x1800b16ec  mov     edx, 14Dh
0x1800b16f1  mov     r9d, eax
0x1800b16f4  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800b16fb  mov     rcx, [rcx+10h]
0x1800b16ff  call    WPP_SF_d
0x1800b1704  nop
0x1800b1705  mov     rcx, [rbp+57h+Str]; void *
0x1800b1709  test    rcx, rcx
0x1800b170c  jz      loc_1800B164D
0x1800b1712  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b1717  jmp     loc_1800B164D
0x1800b171c  mov     esi, 1
0x1800b1721  mov     rbx, [rbp+57h+Str]
0x1800b1725  test    rbx, rbx
0x1800b1728  jz      short loc_1800B1742
0x1800b172a  lea     rdx, aPaused; "Paused"
0x1800b1731  mov     rcx, rbx; Str
0x1800b1734  call    cs:__imp_wcsstr
0x1800b173a  test    rax, rax
0x1800b173d  mov     [rbp+57h+var_74], esi
0x1800b1740  jnz     short loc_1800B1746
0x1800b1742  mov     [rbp+57h+var_74], r13d
0x1800b1746  test    rbx, rbx
0x1800b1749  jz      short loc_1800B1763
0x1800b174b  lea     rdx, aNotSupported; "Not Supported"
0x1800b1752  mov     rcx, rbx; Str
0x1800b1755  call    cs:__imp_wcsstr
0x1800b175b  test    rax, rax
0x1800b175e  mov     [rbp+57h+var_68], esi
0x1800b1761  jnz     short loc_1800B1767
0x1800b1763  mov     [rbp+57h+var_68], r13d
0x1800b1767  test    rbx, rbx
0x1800b176a  jz      short loc_1800B1784
0x1800b176c  lea     rdx, aUnderObservati; "Under Observation"
0x1800b1773  mov     rcx, rbx; Str
0x1800b1776  call    cs:__imp_wcsstr
0x1800b177c  test    rax, rax
0x1800b177f  mov     [rbp+57h+var_70], esi
0x1800b1782  jnz     short loc_1800B1788
0x1800b1784  mov     [rbp+57h+var_70], r13d
0x1800b1788  test    rbx, rbx
0x1800b178b  jz      short loc_1800B17A5
0x1800b178d  lea     rdx, aNoDataObserved; "No Data Observed"
0x1800b1794  mov     rcx, rbx; Str
0x1800b1797  call    cs:__imp_wcsstr
0x1800b179d  test    rax, rax
0x1800b17a0  mov     [rbp+57h+var_6C], esi
0x1800b17a3  jnz     short loc_1800B17A9
0x1800b17a5  mov     [rbp+57h+var_6C], r13d
0x1800b17a9  mov     r14, [rbp+57h+lpString1]
0x1800b17ad  test    r14, r14
0x1800b17b0  jz      short loc_1800B17D4
0x1800b17b2  mov     [rsp+0F0h+bIgnoreCase], esi; bIgnoreCase
0x1800b17b6  or      edx, 0FFFFFFFFh; cchCount1
0x1800b17b9  mov     r9d, edx; cchCount2
0x1800b17bc  lea     r8, aUpdated; "Updated"
0x1800b17c3  mov     rcx, r14; lpString1
0x1800b17c6  call    cs:__imp_CompareStringOrdinal
0x1800b17cc  cmp     eax, 2
0x1800b17cf  mov     r12d, esi
0x1800b17d2  jz      short loc_1800B17D7
0x1800b17d4  mov     r12d, r13d
0x1800b17d7  call    ?IsAfterFirstVuln@HardwareShield@ShieldProvider@@CAHXZ; ShieldProvider::HardwareShield::IsAfterFirstVuln(void)
0x1800b17dc  mov     r15d, eax
0x1800b17df  mov     [rbp+57h+arg_10], eax
0x1800b17e2  call    ?IsPostExpiry@HardwareShield@ShieldProvider@@CAHXZ; ShieldProvider::HardwareShield::IsPostExpiry(void)
0x1800b17e7  mov     ecx, eax
0x1800b17e9  mov     [rbp+57h+var_48], eax
0x1800b17ec  test    r12d, r12d
0x1800b17ef  jz      short loc_1800B180A
0x1800b17f1  mov     r12d, 7FCh
0x1800b17f7  mov     dword ptr [rbp+57h+var_90], r12d
0x1800b17fb  mov     r13d, 2
0x1800b1801  mov     dword ptr [rbp+57h+var_90+4], r13d
0x1800b1805  jmp     loc_1800B1B6A
0x1800b180a  mov     eax, r15d
0x1800b180d  neg     eax
0x1800b180f  sbb     r13d, r13d
0x1800b1812  and     r13d, 6
0x1800b1816  add     r13d, 2
0x1800b181a  test    ecx, ecx
0x1800b181c  jnz     loc_1800B18CF
0x1800b1822  mov     r12d, 7FDh
0x1800b1828  mov     dword ptr [rbp+57h+var_90], r12d
0x1800b182c  lea     r13d, [rcx+2]
0x1800b1830  mov     dword ptr [rbp+57h+var_90+4], r13d
0x1800b1834  mov     [rbp+57h+arg_18], 0
0x1800b183b  mov     [rbp+57h+var_58], 0
0x1800b1843  mov     [rbp+57h+var_50], 0
0x1800b184b  lea     r8, [rbp+57h+var_58]
0x1800b184f  lea     rdx, aDblastupdateer; "DBLastUpdateErrorReason"
0x1800b1856  mov     rcx, rdi
0x1800b1859  call    ?UtilRegGetValueString@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAPEAGW4UTIL_REG_EXPAND_STRING@1@PEAK@Z; CommonUtil::UtilRegGetValueString(HKEY__ *,ushort const *,ushort * *,CommonUtil::UTIL_REG_EXPAND_STRING,ulong *)
0x1800b185e  mov     r15, [rbp+57h+var_58]
0x1800b1862  test    eax, eax
0x1800b1864  js      short loc_1800B1887
0x1800b1866  test    r15, r15
0x1800b1869  jz      short loc_1800B1887
0x1800b186b  lea     rdx, aFirmware; "Firmware"
0x1800b1872  mov     rcx, r15; Str
0x1800b1875  call    cs:__imp_wcsstr
0x1800b187b  mov     ecx, [rbp+57h+arg_18]
0x1800b187e  test    rax, rax
0x1800b1881  cmovnz  ecx, esi
0x1800b1884  mov     [rbp+57h+arg_18], ecx
0x1800b1887  lea     r8, [rbp+57h+var_50]
0x1800b188b  lea     rdx, aKeklastupdatee; "KEKLastUpdateErrorReason"
0x1800b1892  mov     rcx, rdi
0x1800b1895  call    ?UtilRegGetValueString@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAPEAGW4UTIL_REG_EXPAND_STRING@1@PEAK@Z; CommonUtil::UtilRegGetValueString(HKEY__ *,ushort const *,ushort * *,CommonUtil::UTIL_REG_EXPAND_STRING,ulong *)
0x1800b189a  mov     rsi, [rbp+57h+var_50]
0x1800b189e  test    eax, eax
0x1800b18a0  js      loc_1800B1949
0x1800b18a6  test    rsi, rsi
0x1800b18a9  jz      loc_1800B1949
0x1800b18af  lea     rdx, aFirmware; "Firmware"
0x1800b18b6  mov     rcx, rsi; Str
0x1800b18b9  call    cs:__imp_wcsstr
0x1800b18bf  mov     ecx, [rbp+57h+arg_18]
0x1800b18c2  test    rax, rax
0x1800b18c5  mov     edx, 1
0x1800b18ca  cmovnz  ecx, edx
0x1800b18cd  jmp     short loc_1800B194C
0x1800b18cf  test    r15d, r15d
0x1800b18d2  jnz     short loc_1800B18E3
0x1800b18d4  mov     r12d, 7FEh
0x1800b18da  mov     dword ptr [rbp+57h+var_90], r12d
0x1800b18de  jmp     loc_1800B1830
0x1800b18e3  mov     r12d, 7FFh
0x1800b18e9  mov     dword ptr [rbp+57h+var_90], r12d
0x1800b18ed  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Secureboot_states_phase2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Secureboot_states_phase2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Secureboot_states_phase2> `wil::Feature<__WilFeatureTraits_Feature_Secureboot_states_phase2>::GetImpl(void)'::`2'::impl
0x1800b18f4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Secureboot_states_phase2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Secureboot_states_phase2>::__private_IsEnabled(void)
0x1800b18f9  test    al, al
0x1800b18fb  jz      loc_1800B1830
0x1800b1901  mov     [rbp+57h+arg_18], 0
0x1800b1908  mov     dword ptr [rbp+57h+var_90+4], r13d
0x1800b190c  lea     r8, [rbp+57h+arg_18]
0x1800b1910  mov     edx, r12d
0x1800b1913  call    ?GetIsErrorStateDismissed@HardwareShield@ShieldProvider@@AEAAJW4PillarStatusFlag@@PEAH@Z; ShieldProvider::HardwareShield::GetIsErrorStateDismissed(PillarStatusFlag,int *)
0x1800b1918  test    eax, eax
0x1800b191a  js      short loc_1800B193A
0x1800b191c  mov     dword ptr [rbp+57h+var_90+4], r13d
0x1800b1920  cmp     [rbp+57h+arg_18], 0
0x1800b1924  jz      short loc_1800B193A
0x1800b1926  mov     r12d, 807h
0x1800b192c  mov     dword ptr [rbp+57h+var_90], r12d
0x1800b1930  mov     r13d, 2
0x1800b1936  mov     dword ptr [rbp+57h+var_90+4], r13d
0x1800b193a  mov     edx, 135h
0x1800b193f  call    ?SendSecureBootCertToast@HardwareShield@ShieldProvider@@AEAAJW4ToastType@@@Z; ShieldProvider::HardwareShield::SendSecureBootCertToast(ToastType)
0x1800b1944  jmp     loc_1800B1834
0x1800b1949  mov     ecx, [rbp+57h+arg_18]
0x1800b194c  cmp     [rbp+57h+var_74], 0
0x1800b1950  jz      short loc_1800B19BE
0x1800b1952  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Secureboot_states_phase2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Secureboot_states_phase2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Secureboot_states_phase2> `wil::Feature<__WilFeatureTraits_Feature_Secureboot_states_phase2>::GetImpl(void)'::`2'::impl
0x1800b1959  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Secureboot_states_phase2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Secureboot_states_phase2>::__private_IsEnabled(void)
0x1800b195e  mov     r12d, 800h
0x1800b1964  test    al, al
0x1800b1966  jz      loc_1800B1B39
0x1800b196c  mov     dword ptr [rbp+57h+var_90], r12d
0x1800b1970  mov     [rbp+57h+arg_18], 0
0x1800b1977  cmp     [rbp+57h+arg_10], 0
0x1800b197b  jz      loc_1800B1B4B
0x1800b1981  mov     r12d, 801h
0x1800b1987  mov     dword ptr [rbp+57h+var_90], r12d
0x1800b198b  mov     r13d, 8
0x1800b1991  mov     dword ptr [rbp+57h+var_90+4], r13d
0x1800b1995  lea     r8, [rbp+57h+arg_18]
0x1800b1999  mov     edx, r12d
0x1800b199c  call    ?GetIsErrorStateDismissed@HardwareShield@ShieldProvider@@AEAAJW4PillarStatusFlag@@PEAH@Z; ShieldProvider::HardwareShield::GetIsErrorStateDismissed(PillarStatusFlag,int *)
0x1800b19a1  test    eax, eax
0x1800b19a3  js      loc_1800B1B4B
0x1800b19a9  cmp     [rbp+57h+arg_18], 0
0x1800b19ad  jz      loc_1800B1B4B
0x1800b19b3  mov     r12d, 808h
0x1800b19b9  jmp     loc_1800B1B29
0x1800b19be  cmp     [rbp+57h+var_70], 0
0x1800b19c2  jnz     loc_1800B1AD2
0x1800b19c8  cmp     [rbp+57h+var_6C], 0
0x1800b19cc  jnz     loc_1800B1AD2
0x1800b19d2  cmp     [rbp+57h+var_68], 0
0x1800b19d6  jnz     short loc_1800B19E0
0x1800b19d8  test    ecx, ecx
0x1800b19da  jz      loc_1800B1B4B
0x1800b19e0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Secureboot_states_phase2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Secureboot_states_phase2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Secureboot_states_phase2> `wil::Feature<__WilFeatureTraits_Feature_Secureboot_states_phase2>::GetImpl(void)'::`2'::impl
0x1800b19e7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Secureboot_states_phase2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Secureboot_states_phase2>::__private_IsEnabled(void)
0x1800b19ec  xor     ecx, ecx
0x1800b19ee  mov     r12d, 804h
0x1800b19f4  mov     [rbp+57h+arg_18], ecx
0x1800b19f7  lea     r8, [rbp+57h+arg_18]
0x1800b19fb  test    al, al
0x1800b19fd  jz      loc_1800B1A8B
0x1800b1a03  mov     dword ptr [rbp+57h+var_90], r12d
0x1800b1a07  lea     r13d, [rcx+4]
0x1800b1a0b  mov     dword ptr [rbp+57h+var_90+4], r13d
0x1800b1a0f  cmp     [rbp+57h+arg_10], ecx
0x1800b1a12  jz      short loc_1800B1A4B
  ... truncated ...
```
