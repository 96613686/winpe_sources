# CDateInfo::Init(ulong,ulong,char * *)

- ea: `0x18002bddc`
- end: `0x18002cb3a`
- name: `?Init@CDateInfo@@AEAAJKKPEAPEAD@Z`
- size: `3422`
- prototype: `__int64 __fastcall(CDateInfo *__hidden this, unsigned int, unsigned int, char **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002adc8`

## callees

- `0x1800043d4`
- `0x180004464`
- `0x180005790`
- `0x180007590`
- `0x18002b020`
- `0x18002bddc`
- `0x18002cb40`
- `0x18002cbd8`
- `0x18002ccdc`
- `0x18002cdbc`
- `0x18002cf58`
- `0x18003cc88`
- `0x18004d900`
- `0x18004dcf0`
- `0x180071c58`
- `0x1800770b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18002bfbf`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18002bfbf`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18002c392`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18002c3c6`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18002c3ec`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18002c392`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18002c3c6`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18002c3ec`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002c384`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002c3b9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002c44a`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002c479`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002c49f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002c384`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002c3b9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002c44a`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002c479`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002c49f`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18002bffc`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18002c024`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18002bffc`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18002c024`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18002c06b`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18002c092`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18002c06b`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18002c092`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x18002be6e`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x18002bec1`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x18002be6e`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x18002bec1`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18002be7a`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18002beb9`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18002be7a`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18002beb9`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002c32e`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002c32e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002c67b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002c67b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c2c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c2c3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002c0b1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002c0b1`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x18002cafd`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x18002cafd`

## pseudocode

```c
int __fastcall CDateInfo::Init(CDateInfo *this, LCID a2, int a3, char **a4)
{
  LCID v6; // r15d
  int v7; // eax
  LCID UserDefaultLCID; // ecx
  __int16 v9; // cx
  LCID SystemDefaultLCID; // eax
  int result; // eax
  __int16 v12; // cx
  __int16 v13; // ax
  int v14; // edi
  int v15; // r13d
  const WCHAR *v16; // r8
  int v17; // edi
  int v18; // eax
  int *v19; // r9
  int v20; // ebx
  int *v21; // r9
  __int64 v22; // rax
  __int64 i; // rcx
  __int64 v24; // rax
  __int64 v25; // r8
  int v26; // edi
  LSTATUS v27; // eax
  signed int v28; // ebx
  DWORD v29; // r12d
  DWORD v30; // ecx
  __int16 v31; // si
  __int64 v32; // rcx
  const wchar_t *v33; // rbx
  unsigned int v34; // eax
  __int16 v35; // di
  __int64 v36; // rcx
  unsigned int v37; // eax
  __int64 v38; // rbx
  __int64 v39; // rax
  wchar_t *v40; // rdi
  __int64 v41; // rax
  const wchar_t *v42; // rsi
  __int64 v43; // rax
  unsigned __int16 *v44; // rax
  unsigned __int16 *v45; // r8
  unsigned __int64 v46; // rdx
  unsigned __int16 *v47; // r10
  unsigned __int16 *v48; // rax
  unsigned __int64 v49; // rcx
  unsigned __int16 *v50; // rdx
  unsigned __int16 *v51; // r9
  unsigned __int64 v52; // rcx
  unsigned __int64 v53; // rax
  unsigned __int64 v54; // rcx
  unsigned __int64 v55; // rax
  DWORD v56; // edx
  __int64 v57; // rcx
  bool v58; // zf
  int v59; // eax
  int *v60; // rcx
  char *v61; // rcx
  int *v62; // rcx
  char *v63; // rcx
  int *v64; // rcx
  char *v65; // rcx
  int j; // ebx
  int CacheUpdateCount; // eax
  char **v68; // rcx
  int cchDest; // [rsp+28h] [rbp-D8h]
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchValueName; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcbData; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD pdwType; // [rsp+60h] [rbp-A0h] BYREF
  char **v77; // [rsp+68h] [rbp-98h]
  unsigned __int16 v78; // [rsp+70h] [rbp-90h] BYREF
  _WORD pvData[4]; // [rsp+78h] [rbp-88h] BYREF
  BYTE Data[128]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[128]; // [rsp+100h] [rbp+0h] BYREF

  *((_QWORD *)this + 297) = 0;
  *((_QWORD *)this + 298) = (char *)this + 2400;
  v77 = a4;
  *((_QWORD *)this + 299) = (char *)this + 3248;
  v6 = a2;
  v7 = IsDBCS(a2);
  *((_DWORD *)this + 293) = v7;
  if ( !v7 )
  {
    if ( (v6 & 0xFFFFFBFF) != 0 )
      UserDefaultLCID = v6;
    else
      UserDefaultLCID = GetUserDefaultLCID();
    if ( UserDefaultLCID == 2048 )
      LOWORD(UserDefaultLCID) = GetSystemDefaultLCID();
    v9 = UserDefaultLCID & 0x3FF;
    *((_DWORD *)this + 581) = v9 == 1;
    if ( v9 != 1 )
      *((_DWORD *)this + 582) = IsThai(v6);
  }
  if ( v6 == 1024 )
  {
    SystemDefaultLCID = GetUserDefaultLCID();
  }
  else
  {
    if ( v6 != 2048 )
      goto LABEL_14;
    SystemDefaultLCID = GetSystemDefaultLCID();
  }
  v6 = SystemDefaultLCID;
LABEL_14:
  *((_DWORD *)this + 4) = v6;
  result = SafeGetLocaleInfo(v6, a3 | 0x21u, &v78, 4);
  if ( result > -1 )
  {
    *((_DWORD *)this + 6) = v78 - 48;
    result = SafeGetLocaleInfo(v6, a3 | 0x100Cu, &v78, 4);
    if ( result > -1 )
    {
      *((_WORD *)this + 1169) = (v78 - 47) % 7 + 1;
      result = SafeGetLocaleInfo(v6, a3 | 0x100Du, &v78, 4);
      if ( result > -1 )
      {
        v12 = (unsigned __int16)(v78 - 48) > 2u ? 1 : *((_WORD *)qword_1800AD598 + 2 * (__int16)(v78 - 48));
        *((_WORD *)this + 1170) = v12;
        result = SafeGetLocaleInfo(v6, a3 | 0x1009u, &v78, 4);
        if ( result > -1 )
        {
          v13 = _o__wtoi(&v78);
          *((_WORD *)this + 1171) = v13;
          if ( (unsigned __int16)(v13 - 1) > 7u )
            *((_WORD *)this + 1171) = 1;
          *((_DWORD *)this + 29) = 0;
          v14 = GetLocaleInfoW(v6, a3 | 0x28, (LPWSTR)this + 14, 12) + 1;
          if ( v14 <= 1 )
            *((_WORD *)this + 14) = 0;
          v15 = GetLocaleInfoW(v6, a3 | 0x29, (LPWSTR)this + 26, 12) + 1;
          if ( v15 <= 1 )
            *((_WORD *)this + 26) = 0;
          v16 = (const WCHAR *)((char *)this + 28);
          if ( *((_DWORD *)this + 293) )
          {
            v17 = LCMapStringW(v6, 0x400000u, v16, v14, (LPWSTR)this + 560, v14);
            cchDest = LCMapStringW(v6, 0x400000u, (LPCWSTR)this + 26, v15, (LPWSTR)this + 572, v15);
            v18 = CompareStringW(v6, 1u, (PCNZWCH)this + 560, v17, (PCNZWCH)this + 572, cchDest);
          }
          else
          {
            v18 = CompareStringW(v6, 1u, v16, v14, (PCNZWCH)this + 26, v15);
          }
          if ( v18 == 2 )
            *((_DWORD *)this + 29) = 1;
          result = GetDateWindow(v6, this, a3 & 0x80000000);
          if ( result > -1 )
          {
            result = SafeGetLocaleInfo(v6, a3 | 0x1Du, (unsigned __int16 *)this + 38, 8);
            if ( result > -1 )
            {
              result = SafeGetLocaleInfo(v6, a3 | 0x1Eu, (unsigned __int16 *)this + 46, 8);
              if ( result > -1 )
              {
                result = SafeGetLocaleInfo(v6, a3 | 0x25u, &v78, 4);
                if ( result > -1 )
                {
                  *((_DWORD *)this + 27) = v78 - 48;
                  result = SafeGetLocaleInfo(v6, a3 | 0x23u, &v78, 4);
                  if ( result > -1 )
                  {
                    v20 = 0;
                    *((_DWORD *)this + 28) = v78 == 48;
                    while ( v20 < 12 )
                    {
                      result = SafeGetLocaleInfoPooled(this, v20 + 56, (unsigned __int16 **)this + v20 + 15, v19);
                      if ( result < 0 )
                        return result;
                      result = SafeGetLocaleInfoPooled(this, v20 + 68, (unsigned __int16 **)this + v20 + 27, v21);
                      if ( result < 0 )
                        return result;
                      v22 = -1;
                      do
                        ++v22;
                      while ( *(_WORD *)(*((_QWORD *)this + v20 + 27) + 2 * v22) );
                      *((_BYTE *)this + v20++ + 312) = v22;
                    }
                    if ( !*((_DWORD *)this + 293) && !*((_DWORD *)this + 582) )
                    {
                      for ( i = 0; i != 12; ++i )
                      {
                        v24 = *((unsigned __int8 *)this + i + 312);
                        if ( (_BYTE)v24 )
                        {
                          v25 = *((_QWORD *)this + i + 27);
                          if ( *(_WORD *)(v25 + 2 * v24 - 2) == 46 )
                            *(_WORD *)(v25 + 2 * v24 - 2) = 0;
                        }
                      }
                    }
                    result = GetDayNameInfo(this);
                    if ( result > -1 )
                    {
                      v26 = a3;
                      *((_QWORD *)this + 293) = 0;
                      *((_QWORD *)this + 294) = 0;
                      *((_QWORD *)this + 295) = 0;
                      *((_QWORD *)this + 296) = 0;
                      result = SafeGetLocaleInfo(v6, a3 | 0x1Fu, (unsigned __int16 *)this + 162, 64);
                      if ( result > -1 )
                      {
                        if ( (unsigned int)IsJapan(v6) )
                        {
                          phkResult = 0;
                          v27 = RegOpenKeyExW(
                                  HKEY_LOCAL_MACHINE,
                                  L"SYSTEM\\CurrentControlSet\\Control\\Nls\\Calendars\\Japanese\\Eras",
                                  0,
                                  0x80000000,
                                  &phkResult);
                          v28 = v27;
                          if ( v27 > 0 )
                            v28 = (unsigned __int16)v27 | 0x80070000;
                          if ( v28 <= -1 )
                          {
LABEL_97:
                            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
                            return v28;
                          }
                          v29 = 0;
                          Type = 0;
                          while ( 1 )
                          {
                            cbData = 128;
                            cchValueName = 128;
                            if ( RegEnumValueW(phkResult, v29, ValueName, &cchValueName, 0, &Type, Data, &cbData) )
                              break;
                            v30 = cbData;
                            if ( cbData < 0x82 && (cbData & 1) == 0 )
                            {
                              if ( cbData + 1 >= 0x80uLL || (Data[cbData + 1] = 0, v30 + 2 >= 0x80uLL) )
                                _report_rangecheckfailure();
                              Data[v30 + 2] = 0;
                              *wcschr(ValueName, 0x20u) = 0;
                              v31 = _o__wtol(ValueName);
                              v32 = -1;
                              do
                                ++v32;
                              while ( ValueName[v32] );
                              v33 = &ValueName[v32 + 1];
                              *wcschr(v33, 0x20u) = 0;
                              v34 = _o__wtol(v33);
                              v35 = v34;
                              if ( v34 <= 0xC )
                              {
                                v36 = -1;
                                do
                                  ++v36;
                                while ( v33[v36] );
                                v37 = _o__wtol(&v33[v36 + 1]);
                                if ( v37 <= 0x1F )
                                {
                                  v38 = 6LL * v29;
                                  *((_WORD *)this + 4 * v38 + 284) = v31;
                                  *((_WORD *)this + 4 * v38 + 285) = v35;
                                  *((_WORD *)this + 24 * v29 + 288) = 0;
                                  *((_WORD *)this + 4 * v38 + 287) = v37;
                                  *(_QWORD *)((char *)this + 8 * v38 + 578) = 0;
                                  *((_WORD *)this + 4 * v38 + 286) = 0;
                                  *wcschr((const wchar_t *)Data, 0x5Fu) = 0;
                                  v39 = -1;
                                  do
                                    ++v39;
                                  while ( *(_WORD *)&Data[2 * v39] );
                                  v40 = (wchar_t *)&Data[2 * v39 + 2];
                                  *wcschr(v40, 0x5Fu) = 0;
                                  v41 = -1;
                                  do
                                    ++v41;
                                  while ( v40[v41] );
                                  v42 = &v40[v41 + 1];
                                  *wcschr(v42, 0x5Fu) = 0;
                                  v43 = -1;
                                  do
                                    ++v43;
                                  while ( v42[v43] );
                                  *((_QWORD *)this + 6 * v29 + 74) = DuplicateString((unsigned __int16 *)&v42[v43 + 1]);
                                  *((_QWORD *)this + 6 * v29 + 75) = DuplicateString(v40);
                                  v44 = DuplicateString((unsigned __int16 *)Data);
                                  v45 = (unsigned __int16 *)*((_QWORD *)this + 6 * v29 + 75);
                                  v46 = -1;
                                  *((_QWORD *)this + 6 * v29 + 76) = v44;
                                  v47 = v44;
                                  do
                                    ++v46;
                                  while ( v45[v46] );
                                  v48 = (unsigned __int16 *)*((_QWORD *)this + 6 * v29 + 74);
                                  v49 = -1;
                                  do
                                    ++v49;
                                  while ( v48[v49] );
                                  if ( v49 <= v46 )
                                  {
                                    v50 = v45;
                                    v51 = v45;
                                    v45 = (unsigned __int16 *)*((_QWORD *)this + 6 * v29 + 74);
                                  }
                                  else
                                  {
                                    *((_QWORD *)this + 6 * v29 + 74) = v45;
                                    v50 = v48;
                                    *((_QWORD *)this + 6 * v29 + 75) = v48;
                                    v51 = v48;
                                  }
                                  v52 = -1;
                                  do
                                    ++v52;
                                  while ( v47[v52] );
                                  v53 = -1;
                                  do
                                    ++v53;
                                  while ( v50[v53] );
                                  if ( v53 <= v52 )
                                  {
                                    v47 = v51;
                                  }
                                  else
                                  {
                                    *((_QWORD *)this + 6 * v29 + 75) = v47;
                                    *((_QWORD *)this + 6 * v29 + 76) = v50;
                                  }
                                  v54 = -1;
                                  do
                                    ++v54;
                                  while ( v47[v54] );
                                  v55 = -1;
                                  do
                                    ++v55;
                                  while ( v45[v55] );
                                  if ( v55 > v54 )
                                  {
                                    *((_QWORD *)this + 6 * v29 + 74) = v47;
                                    *((_QWORD *)this + 6 * v29 + 75) = v45;
                                  }
                                  ++*((_WORD *)this + 524);
                                  if ( ++v29 <= 0xA )
                                    continue;
                                }
                              }
                            }
                            v28 = -2147024809;
                            goto LABEL_97;
                          }
                          v56 = 0;
                          if ( v29 )
                          {
                            v57 = 0;
                            do
                            {
                              if ( *((_WORD *)this + 24 * v57 + 284) == 1868
                                && *((_WORD *)this + 24 * v57 + 285) == 1
                                && *((_WORD *)this + 24 * v57 + 287) == 1 )
                              {
                                *((_WORD *)this + 24 * v57 + 285) = 10;
                                *((_WORD *)this + 24 * v57 + 287) = 23;
                              }
                              ++v56;
                              ++v57;
                            }
                            while ( v56 < v29 );
                          }
                          pdwType = 0;
                          pcbData = 8;
                          if ( !RegGetValueW(
                                  HKEY_LOCAL_MACHINE,
                                  L"SYSTEM\\CurrentControlSet\\Control\\Nls\\Calendars\\Japanese",
                                  L"InitialEraYear",
                                  2u,
                                  &pdwType,
                                  pvData,
                                  &pcbData)
                            && pvData[0] == 49
                            && pvData[1] == 24180 )
                          {
                            *((_DWORD *)this + 812) = 1;
                          }
                          *((_WORD *)this + 1160) = 20803;
                          *((_QWORD *)this + 132) = &dword_1800B4324;
                          *((_QWORD *)this + 133) = byte_1800B4320;
                          *((_QWORD *)this + 134) = &dword_1800B431C;
                          *((_QWORD *)this + 135) = byte_1800B4318;
                          *((_QWORD *)this + 136) = &dword_1800B4314;
                          *((_QWORD *)this + 137) = byte_1800B4310;
                          *((_QWORD *)this + 138) = "HSMR";
                          *((_QWORD *)this + 139) = &qword_1800B4300;
                          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
                          v26 = a3;
                        }
                        else if ( (unsigned int)IsKorea(v6) )
                        {
                          *((_QWORD *)this + 132) = qword_1800AD600;
                          *((_QWORD *)this + 133) = &dword_1800AD5DC;
                          *((_QWORD *)this + 134) = byte_1800AD5E0;
                          *((_QWORD *)this + 135) = byte_1800AD5E8;
                          *((_QWORD *)this + 136) = &dword_1800AD5E4;
                          *((_QWORD *)this + 137) = &dword_1800AD5EC;
                          *((_QWORD *)this + 138) = &qword_1800AD5F0;
                          *((_QWORD *)this + 139) = &qword_1800AD5F8;
                        }
                        else if ( (unsigned int)IsThai(v6) )
                        {
                          *((_DWORD *)this + 142) = 0;
                          *((_QWORD *)this + 72) = L"G";
                          *((_QWORD *)this + 73) = &dword_1800B3F64;
                          *((_QWORD *)this + 74) = qword_1800B3F48;
                          *((_QWORD *)this + 75) = &dword_1800B3F34;
                          *((_DWORD *)this + 152) = 1;
                          *((_QWORD *)this + 77) = L"B";
                          *((_QWORD *)this + 78) = &qword_1800B3F68;
                          *((_QWORD *)this + 79) = &qword_1800B3F58;
                          *((_QWORD *)this + 80) = &dword_1800B3F3C;
                        }
                        else if ( (unsigned int)IsTaiwan(v6) )
                        {
                          v58 = dword_1800C360C == 0;
                          *((_DWORD *)this + 583) = 0;
                          if ( !v58 )
                          {
                            if ( *((_WORD *)this + 1171) == 4 )
                              goto LABEL_120;
                            result = SafeGetLocaleInfo(v6, a3 | 0x100Bu, &v78, 4);
                            if ( result <= -1 )
                              return result;
                            if ( v78 == 52 )
LABEL_120:
                              *((_DWORD *)this + 583) = 1;
                          }
                          *((_QWORD *)this + 132) = &dword_1800B42E4;
                          *((_QWORD *)this + 138) = "\nNHS";
                          *((_QWORD *)this + 133) = byte_1800B42E0;
                          *((_QWORD *)this + 139) = "\vNHS";
                          *((_QWORD *)this + 134) = &dword_1800B42DC;
                          *((_QWORD *)this + 135) = byte_1800B42D8;
                          *((_QWORD *)this + 136) = &dword_1800B42D4;
                          *((_QWORD *)this + 137) = byte_1800B42D0;
                          *((_QWORD *)this + 72) = &qword_1800C2998;
                          *((_QWORD *)this + 73) = qword_1800C2980;
                          *((_QWORD *)this + 74) = qword_1800C2968;
                          *((_QWORD *)this + 76) = qword_1800C2950;
                          *((_QWORD *)this + 77) = qword_1800C2938;
                          *((_QWORD *)this + 78) = qword_1800C2920;
                          *((_DWORD *)this + 142) = 1;
                          *((_DWORD *)this + 150) = 0;
                        }
                        else if ( (unsigned int)IsChina(v6) )
                        {
                          v59 = IsChinaT(v6);
                          v60 = &dword_1800B42E4;
                          if ( !v59 )
                            v60 = &dword_1800B42BC;
                          *((_QWORD *)this + 132) = v60;
                          v61 = byte_1800B42E0;
                          if ( !v59 )
                            v61 = byte_1800B42B8;
                          *((_QWORD *)this + 133) = v61;
                          v62 = &dword_1800B42DC;
                          if ( !v59 )
                            v62 = &dword_1800B42B4;
                          *((_QWORD *)this + 134) = v62;
                          v63 = byte_1800B42D8;
                          if ( !v59 )
                            v63 = byte_1800B42B0;
                          *((_QWORD *)this + 135) = v63;
                          v64 = &dword_1800B42D4;
                          if ( !v59 )
                            v64 = &dword_1800B42AC;
                          *((_QWORD *)this + 136) = v64;
                          v65 = byte_1800B42D0;
                          if ( !v59 )
                            v65 = byte_1800B42A8;
                          *((_QWORD *)this + 137) = v65;
                          *((_QWORD *)this + 138) = "\nNHS";
                          *((_QWORD *)this + 139) = "\vNHS";
                          *((_QWORD *)this + 71) = "lQCQ";
                        }
                        result = SafeGetLocaleInfo(v6, v26 | 0x1005u, &v78, 4);
                        if ( result > -1 )
                        {
                          *((_DWORD *)this + 292) = v78 == 49;
                          if ( *((_DWORD *)this + 293) || *((_DWORD *)this + 582) )
                          {
                            for ( j = 0; j < 12; ++j )
                            {
                              result = SafeGetLocaleInfo(
                                         0x409u,
                                         j + 56,
                                         (unsigned __int16 *)this + 32 * (__int64)j + 588,
                                         32);
                              if ( result < 0 )
                                return result;
                              result = SafeGetLocaleInfo(0x409u, j + 68, (unsigned __int16 *)this + 4 * j + 972, 4);
                              if ( result < 0 )
                                return result;
                            }
                            v26 = a3;
                          }
                          *((_DWORD *)this + 5) = v26;
                          CacheUpdateCount = NlsGetCacheUpdateCount();
                          v68 = v77;
                          *(_DWORD *)this = CacheUpdateCount;
                          *((_QWORD *)this + 1) = *v68;
                          result = 0;
                          *v68 = 0;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002bddc  push    rbp
0x18002bdde  push    rbx
0x18002bddf  push    rsi
0x18002bde0  push    rdi
0x18002bde1  push    r12
0x18002bde3  push    r13
0x18002bde5  push    r14
0x18002bde7  push    r15
0x18002bde9  lea     rbp, [rsp-118h]
0x18002bdf1  sub     rsp, 218h
0x18002bdf8  mov     rax, cs:__security_cookie
0x18002bdff  xor     rax, rsp
0x18002be02  mov     [rbp+150h+var_50], rax
0x18002be09  lea     rax, [rcx+960h]
0x18002be10  mov     qword ptr [rcx+948h], 0
0x18002be1b  mov     [rcx+950h], rax
0x18002be22  mov     r14, rcx
0x18002be25  lea     rax, [rcx+0CB0h]
0x18002be2c  mov     [rsp+250h+var_1E8], r9
0x18002be31  mov     [rcx+958h], rax
0x18002be38  mov     esi, r8d
0x18002be3b  mov     ecx, edx
0x18002be3d  mov     [rsp+250h+var_210], r8d
0x18002be42  mov     r15d, edx
0x18002be45  call    IsDBCS
0x18002be4a  mov     [r14+494h], eax
0x18002be51  mov     ebx, 800h
0x18002be56  mov     r12d, 1
0x18002be5c  test    eax, eax
0x18002be5e  jnz     short loc_18002BEAB
0x18002be60  test    r15d, 0FFFFFBFFh
0x18002be67  jz      short loc_18002BE6E
0x18002be69  mov     ecx, r15d
0x18002be6c  jmp     short loc_18002BE76
0x18002be6e  call    cs:__imp_GetUserDefaultLCID
0x18002be74  mov     ecx, eax
0x18002be76  cmp     ecx, ebx
0x18002be78  jnz     short loc_18002BE82
0x18002be7a  call    cs:__imp_GetSystemDefaultLCID
0x18002be80  mov     ecx, eax
0x18002be82  mov     eax, 3FFh
0x18002be87  and     cx, ax
0x18002be8a  xor     eax, eax
0x18002be8c  cmp     cx, r12w
0x18002be90  setz    al
0x18002be93  mov     [r14+914h], eax
0x18002be9a  jz      short loc_18002BEAB
0x18002be9c  mov     ecx, r15d
0x18002be9f  call    IsThai
0x18002bea4  mov     [r14+918h], eax
0x18002beab  cmp     r15d, 400h
0x18002beb2  jz      short loc_18002BEC1
0x18002beb4  cmp     r15d, ebx
0x18002beb7  jnz     short loc_18002BECA
0x18002beb9  call    cs:__imp_GetSystemDefaultLCID
0x18002bebf  jmp     short loc_18002BEC7
0x18002bec1  call    cs:__imp_GetUserDefaultLCID
0x18002bec7  mov     r15d, eax
0x18002beca  mov     edx, esi
0x18002becc  mov     [r14+10h], r15d
0x18002bed0  mov     edi, 4
0x18002bed5  lea     r8, [rsp+250h+var_1E0]; unsigned __int16 *
0x18002beda  or      edx, 21h; unsigned int
0x18002bedd  mov     r9d, edi; int
0x18002bee0  mov     ecx, r15d; Locale
0x18002bee3  call    ?SafeGetLocaleInfo@@YAJKKPEAGH@Z; SafeGetLocaleInfo(ulong,ulong,ushort *,int)
0x18002bee8  cmp     eax, 0FFFFFFFFh
0x18002beeb  jle     loc_18002CB17
0x18002bef1  movzx   eax, [rsp+250h+var_1E0]
0x18002bef6  lea     ebx, [rdi+2Ch]
0x18002bef9  mov     edx, esi
0x18002befb  lea     r8, [rsp+250h+var_1E0]; unsigned __int16 *
0x18002bf00  sub     eax, ebx
0x18002bf02  or      edx, 100Ch; unsigned int
0x18002bf08  mov     r9d, edi; int
0x18002bf0b  mov     [r14+18h], eax
0x18002bf0f  mov     ecx, r15d; Locale
0x18002bf12  call    ?SafeGetLocaleInfo@@YAJKKPEAGH@Z; SafeGetLocaleInfo(ulong,ulong,ushort *,int)
0x18002bf17  cmp     eax, 0FFFFFFFFh
0x18002bf1a  jle     loc_18002CB17
0x18002bf20  movzx   ecx, [rsp+250h+var_1E0]
0x18002bf25  lea     r8, [rsp+250h+var_1E0]; unsigned __int16 *
0x18002bf2a  sub     ecx, 2Fh ; '/'
0x18002bf2d  mov     eax, 92492493h
0x18002bf32  imul    ecx
0x18002bf34  mov     r9d, edi; int
0x18002bf37  add     edx, ecx
0x18002bf39  sar     edx, 2
0x18002bf3c  mov     eax, edx
0x18002bf3e  shr     eax, 1Fh
0x18002bf41  add     edx, eax
0x18002bf43  imul    eax, edx, 7
0x18002bf46  mov     edx, esi
0x18002bf48  or      edx, 100Dh; unsigned int
0x18002bf4e  sub     ecx, eax
0x18002bf50  add     cx, r12w
0x18002bf54  mov     [r14+922h], cx
0x18002bf5c  mov     ecx, r15d; Locale
0x18002bf5f  call    ?SafeGetLocaleInfo@@YAJKKPEAGH@Z; SafeGetLocaleInfo(ulong,ulong,ushort *,int)
0x18002bf64  cmp     eax, 0FFFFFFFFh
0x18002bf67  jle     loc_18002CB17
0x18002bf6d  movzx   eax, [rsp+250h+var_1E0]
0x18002bf72  lea     ecx, [rdi-2]
0x18002bf75  sub     ax, bx
0x18002bf78  cmp     ax, cx
0x18002bf7b  ja      short loc_18002BF8E
0x18002bf7d  movsx   rax, ax
0x18002bf81  lea     rcx, qword_1800AD598
0x18002bf88  movzx   ecx, word ptr [rcx+rax*4]
0x18002bf8c  jmp     short loc_18002BF91
0x18002bf8e  mov     ecx, r12d
0x18002bf91  mov     edx, esi
0x18002bf93  mov     [r14+924h], cx
0x18002bf9b  or      edx, 1009h; unsigned int
0x18002bfa1  lea     r8, [rsp+250h+var_1E0]; unsigned __int16 *
0x18002bfa6  mov     r9d, edi; int
0x18002bfa9  mov     ecx, r15d; Locale
0x18002bfac  call    ?SafeGetLocaleInfo@@YAJKKPEAGH@Z; SafeGetLocaleInfo(ulong,ulong,ushort *,int)
0x18002bfb1  cmp     eax, 0FFFFFFFFh
0x18002bfb4  jle     loc_18002CB17
0x18002bfba  lea     rcx, [rsp+250h+var_1E0]
0x18002bfbf  call    cs:__imp__o__wtoi
0x18002bfc5  mov     [r14+926h], ax
0x18002bfcd  sub     ax, r12w
0x18002bfd1  cmp     ax, 7
0x18002bfd5  jbe     short loc_18002BFDF
0x18002bfd7  mov     [r14+926h], r12w
0x18002bfdf  mov     edx, esi
0x18002bfe1  mov     dword ptr [r14+74h], 0
0x18002bfe9  lea     rbx, [r14+1Ch]
0x18002bfed  or      edx, 28h; LCType
0x18002bff0  mov     r8, rbx; lpLCData
0x18002bff3  mov     r9d, 0Ch; cchData
0x18002bff9  mov     ecx, r15d; Locale
0x18002bffc  call    cs:__imp_GetLocaleInfoW
0x18002c002  lea     edi, [rax+1]
0x18002c005  cmp     edi, r12d
0x18002c008  jg      short loc_18002C00F
0x18002c00a  xor     eax, eax
0x18002c00c  mov     [rbx], ax
0x18002c00f  mov     edx, esi
0x18002c011  lea     r12, [r14+34h]
0x18002c015  or      edx, 29h; LCType
0x18002c018  mov     r8, r12; lpLCData
0x18002c01b  mov     r9d, 0Ch; cchData
0x18002c021  mov     ecx, r15d; Locale
0x18002c024  call    cs:__imp_GetLocaleInfoW
0x18002c02a  mov     esi, 1
0x18002c02f  lea     r13d, [rax+1]
0x18002c033  cmp     r13d, esi
0x18002c036  jg      short loc_18002C03F
0x18002c038  xor     eax, eax
0x18002c03a  mov     [r12], ax
0x18002c03f  cmp     dword ptr [r14+494h], 0
0x18002c047  mov     r9d, edi; cchSrc
0x18002c04a  mov     r8, rbx; lpSrcStr
0x18002c04d  mov     ecx, r15d; Locale
0x18002c050  jz      loc_18002C1EA
0x18002c056  lea     rsi, [r14+460h]
0x18002c05d  mov     [rsp+250h+cchDest], edi; cchDest
0x18002c061  mov     edx, 400000h; dwMapFlags
0x18002c066  mov     [rsp+250h+lpDestStr], rsi; lpDestStr
0x18002c06b  call    cs:__imp_LCMapStringW
0x18002c071  lea     rbx, [r14+478h]
0x18002c078  mov     [rsp+250h+cchDest], r13d; cchDest
0x18002c07d  mov     r9d, r13d; cchSrc
0x18002c080  mov     [rsp+250h+lpDestStr], rbx; lpDestStr
0x18002c085  mov     r8, r12; lpSrcStr
0x18002c088  mov     edx, 400000h; dwMapFlags
0x18002c08d  mov     ecx, r15d; Locale
0x18002c090  mov     edi, eax
0x18002c092  call    cs:__imp_LCMapStringW
0x18002c098  mov     [rsp+250h+cchDest], eax; cchCount2
0x18002c09c  mov     r8, rsi; lpString1
0x18002c09f  mov     [rsp+250h+lpDestStr], rbx; lpString2
0x18002c0a4  mov     r9d, edi; cchCount1
0x18002c0a7  mov     esi, 1
0x18002c0ac  mov     ecx, r15d; Locale
0x18002c0af  mov     edx, esi; dwCmpFlags
0x18002c0b1  call    cs:__imp_CompareStringW
0x18002c0b7  cmp     eax, 2
0x18002c0ba  jnz     short loc_18002C0C0
0x18002c0bc  mov     [r14+74h], esi
0x18002c0c0  mov     edi, [rsp+250h+var_210]
0x18002c0c4  mov     r12d, 80000000h
0x18002c0ca  mov     r8d, edi
0x18002c0cd  mov     rdx, r14; struct tagDATEINFO *
0x18002c0d0  and     r8d, r12d; unsigned int
0x18002c0d3  mov     ecx, r15d; unsigned int
0x18002c0d6  call    ?GetDateWindow@@YAJKPEAUtagDATEINFO@@K@Z; GetDateWindow(ulong,tagDATEINFO *,ulong)
0x18002c0db  cmp     eax, 0FFFFFFFFh
0x18002c0de  jle     loc_18002CB17
0x18002c0e4  mov     edx, edi
0x18002c0e6  lea     r8, [r14+4Ch]; unsigned __int16 *
0x18002c0ea  mov     ebx, 8
0x18002c0ef  or      edx, 1Dh; unsigned int
0x18002c0f2  mov     r9d, ebx; int
0x18002c0f5  mov     ecx, r15d; Locale
0x18002c0f8  call    ?SafeGetLocaleInfo@@YAJKKPEAGH@Z; SafeGetLocaleInfo(ulong,ulong,ushort *,int)
0x18002c0fd  cmp     eax, 0FFFFFFFFh
0x18002c100  jle     loc_18002CB17
0x18002c106  mov     edx, edi
0x18002c108  lea     r8, [r14+5Ch]; unsigned __int16 *
0x18002c10c  or      edx, 1Eh; unsigned int
0x18002c10f  mov     r9d, ebx; int
0x18002c112  mov     ecx, r15d; Locale
0x18002c115  call    ?SafeGetLocaleInfo@@YAJKKPEAGH@Z; SafeGetLocaleInfo(ulong,ulong,ushort *,int)
0x18002c11a  cmp     eax, 0FFFFFFFFh
0x18002c11d  jle     loc_18002CB17
0x18002c123  mov     edx, edi
0x18002c125  lea     r13d, [rbx-4]
0x18002c129  or      edx, 25h; unsigned int
0x18002c12c  lea     r8, [rsp+250h+var_1E0]; unsigned __int16 *
0x18002c131  mov     r9d, r13d; int
0x18002c134  mov     ecx, r15d; Locale
0x18002c137  call    ?SafeGetLocaleInfo@@YAJKKPEAGH@Z; SafeGetLocaleInfo(ulong,ulong,ushort *,int)
0x18002c13c  cmp     eax, 0FFFFFFFFh
0x18002c13f  jle     loc_18002CB17
0x18002c145  movzx   eax, [rsp+250h+var_1E0]
0x18002c14a  lea     ebx, [r13+2Ch]
0x18002c14e  mov     edx, edi
0x18002c150  lea     r8, [rsp+250h+var_1E0]; unsigned __int16 *
0x18002c155  sub     eax, ebx
0x18002c157  or      edx, 23h; unsigned int
0x18002c15a  mov     r9d, r13d; int
0x18002c15d  mov     [r14+6Ch], eax
0x18002c161  mov     ecx, r15d; Locale
0x18002c164  call    ?SafeGetLocaleInfo@@YAJKKPEAGH@Z; SafeGetLocaleInfo(ulong,ulong,ushort *,int)
0x18002c169  cmp     eax, 0FFFFFFFFh
0x18002c16c  jle     loc_18002CB17
0x18002c172  xor     r13d, r13d
0x18002c175  cmp     [rsp+250h+var_1E0], bx
0x18002c17a  mov     eax, r13d
0x18002c17d  mov     ebx, r13d
0x18002c180  setz    al
0x18002c183  mov     [r14+70h], eax
0x18002c187  cmp     ebx, 0Ch
0x18002c18a  jge     short loc_18002C1F9
0x18002c18c  movsxd  rdi, ebx
0x18002c18f  lea     r8, [r14+78h]
0x18002c193  lea     edx, [rbx+38h]; unsigned int
0x18002c196  mov     rcx, r14; struct tagDATEINFO *
0x18002c199  lea     r8, [r8+rdi*8]; unsigned __int16 **
0x18002c19d  call    ?SafeGetLocaleInfoPooled@@YAJPEAUtagDATEINFO@@KPEAPEAGPEAH@Z; SafeGetLocaleInfoPooled(tagDATEINFO *,ulong,ushort * *,int *)
0x18002c1a2  test    eax, eax
0x18002c1a4  js      loc_18002CB17
0x18002c1aa  lea     r8, [r14+0D8h]
0x18002c1b1  mov     rcx, r14; struct tagDATEINFO *
0x18002c1b4  lea     r8, [r8+rdi*8]; unsigned __int16 **
0x18002c1b8  lea     edx, [rbx+44h]; unsigned int
0x18002c1bb  call    ?SafeGetLocaleInfoPooled@@YAJPEAUtagDATEINFO@@KPEAPEAGPEAH@Z; SafeGetLocaleInfoPooled(tagDATEINFO *,ulong,ushort * *,int *)
0x18002c1c0  test    eax, eax
0x18002c1c2  js      loc_18002CB17
0x18002c1c8  mov     rcx, [r14+rdi*8+0D8h]
0x18002c1d0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002c1d4  inc     rax
0x18002c1d7  cmp     [rcx+rax*2], r13w
0x18002c1dc  jnz     short loc_18002C1D4
0x18002c1de  mov     [r14+rdi+138h], al
0x18002c1e6  add     ebx, esi
0x18002c1e8  jmp     short loc_18002C187
0x18002c1ea  mov     [rsp+250h+cchDest], r13d
0x18002c1ef  mov     [rsp+250h+lpDestStr], r12
0x18002c1f4  jmp     loc_18002C0AF
0x18002c1f9  cmp     [r14+494h], r13d
0x18002c200  jnz     short loc_18002C23C
0x18002c202  cmp     [r14+918h], r13d
0x18002c209  jnz     short loc_18002C23C
0x18002c20b  mov     rcx, r13
0x18002c20e  movzx   eax, byte ptr [r14+rcx+138h]
0x18002c217  cmp     al, sil
0x18002c21a  jb      short loc_18002C233
0x18002c21c  mov     r8, [r14+rcx*8+0D8h]
0x18002c224  cmp     word ptr [r8+rax*2-2], 2Eh ; '.'
0x18002c22b  jnz     short loc_18002C233
0x18002c22d  mov     [r8+rax*2-2], r13w
0x18002c233  add     rcx, rsi
0x18002c236  cmp     rcx, 0Ch
0x18002c23a  jnz     short loc_18002C20E
0x18002c23c  mov     rcx, r14
0x18002c23f  call    GetDayNameInfo
0x18002c244  cmp     eax, 0FFFFFFFFh
0x18002c247  jle     loc_18002CB17
0x18002c24d  mov     edi, [rsp+250h+var_210]
0x18002c251  lea     r8, [r14+144h]; unsigned __int16 *
0x18002c258  mov     edx, edi
0x18002c25a  mov     [r14+928h], r13
0x18002c261  or      edx, 1Fh; unsigned int
0x18002c264  mov     [r14+930h], r13
0x18002c26b  mov     r9d, 40h ; '@'; int
0x18002c271  mov     [r14+938h], r13
0x18002c278  mov     ecx, r15d; Locale
0x18002c27b  mov     [r14+940h], r13
0x18002c282  call    ?SafeGetLocaleInfo@@YAJKKPEAGH@Z; SafeGetLocaleInfo(ulong,ulong,ushort *,int)
0x18002c287  cmp     eax, 0FFFFFFFFh
0x18002c28a  jle     loc_18002CB17
0x18002c290  mov     ecx, r15d
0x18002c293  call    IsJapan
0x18002c298  test    eax, eax
0x18002c29a  jz      loc_18002C72D
  ... truncated ...
```
