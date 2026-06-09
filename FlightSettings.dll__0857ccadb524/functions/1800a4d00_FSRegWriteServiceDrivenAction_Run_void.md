# FSRegWriteServiceDrivenAction::Run(void)

- ea: `0x1800a4d00`
- end: `0x1800a5222`
- name: `?Run@FSRegWriteServiceDrivenAction@@UEAAJXZ`
- size: `1314`
- prototype: `__int64 __fastcall(FSRegWriteServiceDrivenAction *__hidden this)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180004b80`
- `0x180005744`
- `0x18000cc8c`
- `0x1800175b4`
- `0x18001b2ec`
- `0x18001c6f4`
- `0x18001d244`
- `0x18001ec78`
- `0x18002035c`
- `0x1800314e0`
- `0x180041c44`
- `0x180089dfc`
- `0x18008b7b8`
- `0x1800a3b80`
- `0x1800a3bdc`
- `0x1800a3c50`
- `0x1800a3f5c`
- `0x1800a4840`
- `0x1800a4d00`
- `0x1800a5228`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800a50c9`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800a50c9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800a50a5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800a50a5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800a502a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800a502a`

## string_xrefs

- `0x1800a4dee`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsallowlist.cpp`
- `0x1800a4d47`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsregwriteservicedrivenaction.cpp`
- `0x1800a4f5c`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsregwriteservicedrivenaction.cpp`
- `0x1800a4fc1`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsregwriteservicedrivenaction.cpp`
- `0x1800a5143`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsregwriteservicedrivenaction.cpp`
- `0x1800a518f`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsregwriteservicedrivenaction.cpp`
- `0x1800a51bd`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsregwriteservicedrivenaction.cpp`
- `0x1800a5200`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsregwriteservicedrivenaction.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall FSRegWriteServiceDrivenAction::Run(FSRegWriteServiceDrivenAction *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  unsigned int v5; // r14d
  const WCHAR *v6; // r15
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rbx
  int v10; // eax
  __int64 v11; // rsi
  _QWORD *v12; // r8
  char v13; // al
  int v14; // eax
  __int64 v15; // rdx
  int CurrentUserSid; // eax
  __int64 v17; // rdx
  __int64 v18; // r9
  __int64 v19; // rdx
  int v20; // eax
  __int64 v21; // rdx
  unsigned __int64 v22; // r9
  LSTATUS v23; // eax
  DWORD v24; // r14d
  unsigned __int64 v25; // r12
  __int64 v26; // r13
  unsigned int v27; // eax
  int v28; // eax
  __int64 v29; // rdx
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-E0h]
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v32[3]; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+80h] [rbp-80h] BYREF
  DWORD cchName; // [rsp+84h] [rbp-7Ch] BYREF
  __int64 v35; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v36; // [rsp+90h] [rbp-70h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 v38; // [rsp+A0h] [rbp-60h]
  LPWSTR StringSid[3]; // [rsp+A8h] [rbp-58h] BYREF
  char *v40[4]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Name[264]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+248h]

  v2 = FSRegWriteServiceDrivenAction::ParseFullPath(this);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsregwriteservicedrivenaction.cpp",
      (const char *)(unsigned int)v2,
      lpcSubKeys);
    return v3;
  }
  v5 = 0;
  if ( !*((_DWORD *)this + 71) )
    return 0;
  while ( 1 )
  {
    memset(v40, 0, 24);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
      v40,
      *(_QWORD *)(*((_QWORD *)this + 7) + 24LL * v5),
      -1);
    v6 = (const WCHAR *)v40[0];
    if ( !FSAllowlist::IsValueInAllowlist(
            *(FSAllowlist **)(*((_QWORD *)this + 33) + 16LL),
            (const unsigned __int16 *)v40[0]) )
    {
      v3 = -2146698746;
      v29 = 219;
      goto LABEL_60;
    }
    v8 = *((_QWORD *)this + 33);
    v9 = *(_QWORD *)(v8 + 16);
    if ( !*(_QWORD *)(v9 + 56) )
    {
      v10 = FSAllowlist::SetInternalList(*(_QWORD *)(v8 + 16), *(wchar_t **)(v9 + 152), v9 + 48);
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4B,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsallowlist.cpp",
          (const char *)(unsigned int)v10,
          lpcSubKeys);
        v11 = 0;
        goto LABEL_13;
      }
    }
    v12 = (_QWORD *)(v9 + 48);
    v13 = *(_BYTE *)(v9 + 176)
        ? FSAllowlist::IsSubStringInList(v7, v6, v12)
        : FSAllowlist::IsStringInList(v7, (__int64)v6, v12);
    v11 = 0;
    if ( v13 )
      break;
LABEL_13:
    memset(v32, 0, sizeof(v32));
    v14 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(v32, v6, -1);
    v3 = v14;
    if ( v14 < 0 )
    {
      v19 = 229;
      goto LABEL_55;
    }
    if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                         (char *)this + 88,
                         L"HKEY_CURRENT_USER",
                         -1) == 2 )
    {
      if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                           (char *)this + 208,
                           L"ALL",
                           -1) != 2 )
      {
        if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                             (char *)this + 208,
                             L"CURRENT",
                             -1) != 2 )
        {
          v3 = -2147024809;
          v18 = 2147942487LL;
          v19 = 299;
LABEL_56:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsregwriteservicedrivenaction.cpp",
            (const char *)v18,
            lpcSubKeys);
          goto LABEL_57;
        }
        memset(StringSid, 0, sizeof(StringSid));
        CurrentUserSid = FlightSettingsAPICommon::GetCurrentUserSid(StringSid);
        v3 = CurrentUserSid;
        if ( CurrentUserSid < 0 )
        {
          v17 = 294;
LABEL_25:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v17,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsregwriteservicedrivenaction.cpp",
            (const char *)(unsigned int)CurrentUserSid,
            lpcSubKeys);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(StringSid);
LABEL_57:
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v32);
          goto LABEL_61;
        }
        CurrentUserSid = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                           v32,
                           L"%s\\%s",
                           StringSid[0],
                           v6);
        v3 = CurrentUserSid;
        if ( CurrentUserSid < 0 )
        {
          v17 = 295;
          goto LABEL_25;
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(StringSid);
        goto LABEL_20;
      }
      v35 = 0;
      v36 = 0;
      v37 = 0;
      v38 = 0;
      v20 = FlightSettingsAPICommon::SplitStringToArray(L".DEFAULT;S-1-5-18;S-1-5-19;S-1-5-20", v15, &v35);
      v3 = v20;
      if ( v20 < 0 )
      {
        v21 = 236;
LABEL_29:
        v22 = (unsigned int)v20;
        goto LABEL_30;
      }
      cSubKeys = 0;
      cbMaxSubKeyLen = 0;
      v23 = RegQueryInfoKeyW(HKEY_USERS, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
      v3 = v23;
      if ( v23 > 0 )
        v3 = (unsigned __int16)v23 | 0x80070000;
      if ( (v3 & 0x80000000) != 0 )
      {
        v22 = v3;
        v21 = 242;
        goto LABEL_30;
      }
      v3 = 0;
      v24 = 0;
      if ( cSubKeys )
      {
        v25 = v36;
        v26 = v35;
        do
        {
          memset_0(Name, 0, 0x208u);
          cchName = 260;
          v27 = RegEnumKeyExW(HKEY_USERS, v24, Name, &cchName, 0, 0, 0, 0);
          if ( v27 == 259 )
            break;
          if ( v27 )
          {
            v3 = wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)0xFE,
                   (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsregwriteservi"
                                 "cedrivenaction.cpp",
                   (const char *)v27,
                   lpcSubKeys);
            goto LABEL_31;
          }
          if ( !wcsstr(Name, L"_Classes") )
          {
            if ( v25 )
            {
              while ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                                      v26 + 24 * v11,
                                      Name,
                                      -1) != 2 )
              {
                if ( ++v11 >= v25 )
                  goto LABEL_44;
              }
              v11 = 0;
            }
            else
            {
LABEL_44:
              v20 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                      v32,
                      L"%s\\%s",
                      Name,
                      v6);
              v3 = v20;
              v11 = 0;
              if ( v20 < 0 )
              {
                v21 = 280;
                goto LABEL_29;
              }
              v28 = FSRegWriteServiceDrivenAction::RunRegAction(this, v32[0]);
              v3 = v28;
              if ( v28 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsregwriteservic"
                                "edrivenaction.cpp",
                  (const char *)(unsigned int)v28,
                  lpcSubKeys);
            }
          }
          ++v24;
        }
        while ( v24 < cSubKeys );
        if ( (v3 & 0x80000000) == 0 )
          goto LABEL_31;
        v22 = v3;
        v21 = 288;
LABEL_30:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsregwriteservicedrivenaction.cpp",
          (const char *)v22,
          lpcSubKeys);
      }
LABEL_31:
      CTSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>,4294967294,CTPolicyCoTaskMem<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>,CSimpleArrayStandardMergeHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>>::RemoveAll(&v35);
      goto LABEL_57;
    }
LABEL_20:
    v14 = FSRegWriteServiceDrivenAction::RunRegAction(this, v32[0]);
    v3 = v14;
    if ( v14 < 0 )
    {
      v19 = 303;
LABEL_55:
      v18 = (unsigned int)v14;
      goto LABEL_56;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v32);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v40);
    if ( ++v5 >= *((_DWORD *)this + 71) )
      return 0;
  }
  v3 = -2146698730;
  v29 = 225;
LABEL_60:
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)v29,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsregwriteservicedrivenaction.cpp",
    (const char *)v3,
    (int)"%ws",
    (const char *)v6);
LABEL_61:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v40);
  return v3;
}

```

## disassembly

```asm
0x1800a4d00  push    rbp
0x1800a4d02  push    rbx
0x1800a4d03  push    rsi
0x1800a4d04  push    rdi
0x1800a4d05  push    r12
0x1800a4d07  push    r13
0x1800a4d09  push    r14
0x1800a4d0b  push    r15
0x1800a4d0d  lea     rbp, [rsp-208h]
0x1800a4d15  sub     rsp, 308h
0x1800a4d1c  mov     rax, cs:__security_cookie
0x1800a4d23  xor     rax, rsp
0x1800a4d26  mov     [rbp+240h+var_50], rax
0x1800a4d2d  mov     rdi, rcx
0x1800a4d30  call    ?ParseFullPath@FSRegWriteServiceDrivenAction@@QEAAJXZ; FSRegWriteServiceDrivenAction::ParseFullPath(void)
0x1800a4d35  mov     ebx, eax
0x1800a4d37  xor     esi, esi
0x1800a4d39  test    eax, eax
0x1800a4d3b  jns     short loc_1800A4D5F
0x1800a4d3d  mov     rcx, [rbp+248h]; this
0x1800a4d44  mov     r9d, eax; char *
0x1800a4d47  lea     r8, aOnecoreBaseFli_74; "onecore\\base\\flighting\\flightsetting"...
0x1800a4d4e  mov     edx, 0D2h; void *
0x1800a4d53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4d58  mov     eax, ebx
0x1800a4d5a  jmp     loc_1800A4F2D
0x1800a4d5f  mov     r14d, esi
0x1800a4d62  cmp     [rdi+11Ch], esi
0x1800a4d68  jbe     loc_1800A4F2B
0x1800a4d6e  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800a4d72  mov     [rbp+240h+var_280], rsi
0x1800a4d76  mov     [rbp+240h+var_278], rsi
0x1800a4d7a  mov     [rbp+240h+var_270], rsi
0x1800a4d7e  mov     eax, r14d
0x1800a4d81  lea     rcx, [rax+rax*2]
0x1800a4d85  mov     rdx, [rdi+38h]
0x1800a4d89  mov     r8, r12
0x1800a4d8c  mov     rdx, [rdx+rcx*8]
0x1800a4d90  lea     rcx, [rbp+240h+var_280]
0x1800a4d94  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800a4d99  mov     rcx, [rdi+108h]
0x1800a4da0  mov     r15, [rbp+240h+var_280]
0x1800a4da4  mov     rdx, r15; unsigned __int16 *
0x1800a4da7  mov     rcx, [rcx+10h]; this
0x1800a4dab  call    ?IsValueInAllowlist@FSAllowlist@@QEAA_NPEBG@Z; FSAllowlist::IsValueInAllowlist(ushort const *)
0x1800a4db0  test    al, al
0x1800a4db2  jz      loc_1800A51E2
0x1800a4db8  mov     rax, [rdi+108h]
0x1800a4dbf  mov     rbx, [rax+10h]
0x1800a4dc3  lea     rsi, [rbx+30h]
0x1800a4dc7  cmp     qword ptr [rsi+8], 0
0x1800a4dcc  jnz     short loc_1800A4E03
0x1800a4dce  mov     r8, rsi
0x1800a4dd1  mov     rdx, [rbx+98h]
0x1800a4dd8  mov     rcx, rbx
0x1800a4ddb  call    ?SetInternalList@FSAllowlist@@AEAAJPEBGAEAV?$CCoSimpleArray@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@@@@Z; FSAllowlist::SetInternalList(ushort const *,CCoSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>,4294967294,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>> &)
0x1800a4de0  test    eax, eax
0x1800a4de2  jns     short loc_1800A4E03
0x1800a4de4  mov     rcx, [rbp+248h]; this
0x1800a4deb  mov     r9d, eax; char *
0x1800a4dee  lea     r8, aOnecoreBaseFli_72; "onecore\\base\\flighting\\flightsetting"...
0x1800a4df5  mov     edx, 4Bh ; 'K'; void *
0x1800a4dfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4dff  xor     esi, esi
0x1800a4e01  jmp     short loc_1800A4E28
0x1800a4e03  mov     r8, rsi
0x1800a4e06  mov     rdx, r15
0x1800a4e09  cmp     byte ptr [rbx+0B0h], 0
0x1800a4e10  jz      short loc_1800A4E19
0x1800a4e12  call    ?IsSubStringInList@FSAllowlist@@AEAA_NPEBGAEAV?$CCoSimpleArray@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@@@@Z; FSAllowlist::IsSubStringInList(ushort const *,CCoSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>,4294967294,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>> &)
0x1800a4e17  jmp     short loc_1800A4E1E
0x1800a4e19  call    ?IsStringInList@FSAllowlist@@AEAA_NPEBGAEAV?$CCoSimpleArray@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@@@@Z; FSAllowlist::IsStringInList(ushort const *,CCoSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>,4294967294,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>> &)
0x1800a4e1e  xor     esi, esi
0x1800a4e20  test    al, al
0x1800a4e22  jnz     loc_1800A51D6
0x1800a4e28  mov     [rsp+340h+var_2D8], rsi
0x1800a4e2d  mov     [rsp+340h+var_2D0], rsi
0x1800a4e32  mov     [rsp+340h+var_2C8], rsi
0x1800a4e37  mov     r8, r12
0x1800a4e3a  mov     rdx, r15
0x1800a4e3d  lea     rcx, [rsp+340h+var_2D8]
0x1800a4e42  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800a4e47  mov     ebx, eax
0x1800a4e49  test    eax, eax
0x1800a4e4b  js      loc_1800A51AE
0x1800a4e51  lea     rcx, [rdi+58h]
0x1800a4e55  mov     r8, r12
0x1800a4e58  lea     rdx, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x1800a4e5f  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a4e64  cmp     eax, 2
0x1800a4e67  jnz     loc_1800A4EF0
0x1800a4e6d  lea     rbx, [rdi+0D0h]
0x1800a4e74  mov     r8, r12
0x1800a4e77  lea     rdx, aAll; "ALL"
0x1800a4e7e  mov     rcx, rbx
0x1800a4e81  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a4e86  cmp     eax, 2
0x1800a4e89  jz      loc_1800A4F93
0x1800a4e8f  mov     r8, r12
0x1800a4e92  lea     rdx, aCurrent; "CURRENT"
0x1800a4e99  mov     rcx, rbx
0x1800a4e9c  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a4ea1  cmp     eax, 2
0x1800a4ea4  jnz     loc_1800A4F81
0x1800a4eaa  mov     [rbp+240h+StringSid], rsi
0x1800a4eae  mov     [rbp+240h+var_290], rsi
0x1800a4eb2  mov     [rbp+240h+var_288], rsi
0x1800a4eb6  lea     rcx, [rbp+240h+StringSid]; StringSid
0x1800a4eba  call    ?GetCurrentUserSid@FlightSettingsAPICommon@@SAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; FlightSettingsAPICommon::GetCurrentUserSid(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800a4ebf  mov     ebx, eax
0x1800a4ec1  test    eax, eax
0x1800a4ec3  js      loc_1800A4F57
0x1800a4ec9  mov     r9, r15
0x1800a4ecc  mov     r8, [rbp+240h+StringSid]
0x1800a4ed0  lea     rdx, aSS_2; "%s\\%s"
0x1800a4ed7  lea     rcx, [rsp+340h+var_2D8]
0x1800a4edc  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800a4ee1  mov     ebx, eax
0x1800a4ee3  test    eax, eax
0x1800a4ee5  js      short loc_1800A4F50
0x1800a4ee7  lea     rcx, [rbp+240h+StringSid]
0x1800a4eeb  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800a4ef0  mov     rdx, [rsp+340h+var_2D8]; unsigned __int16 *
0x1800a4ef5  mov     rcx, rdi; this
0x1800a4ef8  call    ?RunRegAction@FSRegWriteServiceDrivenAction@@AEAAJPEBG@Z; FSRegWriteServiceDrivenAction::RunRegAction(ushort const *)
0x1800a4efd  mov     ebx, eax
0x1800a4eff  test    eax, eax
0x1800a4f01  js      loc_1800A51A7
0x1800a4f07  lea     rcx, [rsp+340h+var_2D8]
0x1800a4f0c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800a4f11  nop
0x1800a4f12  lea     rcx, [rbp+240h+var_280]
0x1800a4f16  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800a4f1b  inc     r14d
0x1800a4f1e  cmp     r14d, [rdi+11Ch]
0x1800a4f25  jb      loc_1800A4D72
0x1800a4f2b  xor     eax, eax
0x1800a4f2d  mov     rcx, [rbp+240h+var_50]
0x1800a4f34  xor     rcx, rsp; StackCookie
0x1800a4f37  call    __security_check_cookie
0x1800a4f3c  add     rsp, 308h
0x1800a4f43  pop     r15
0x1800a4f45  pop     r14
0x1800a4f47  pop     r13
0x1800a4f49  pop     r12
0x1800a4f4b  pop     rdi
0x1800a4f4c  pop     rsi
0x1800a4f4d  pop     rbx
0x1800a4f4e  pop     rbp
0x1800a4f4f  retn
0x1800a4f50  mov     edx, 127h
0x1800a4f55  jmp     short loc_1800A4F5C
0x1800a4f57  mov     edx, 126h; void *
0x1800a4f5c  lea     r8, aOnecoreBaseFli_74; "onecore\\base\\flighting\\flightsetting"...
0x1800a4f63  mov     r9d, eax; char *
0x1800a4f66  mov     rcx, [rbp+248h]; this
0x1800a4f6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4f72  nop
0x1800a4f73  lea     rcx, [rbp+240h+StringSid]
0x1800a4f77  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800a4f7c  jmp     loc_1800A51CA
0x1800a4f81  mov     ebx, 80070057h
0x1800a4f86  mov     r9d, ebx
0x1800a4f89  mov     edx, 12Bh
0x1800a4f8e  jmp     loc_1800A51B6
0x1800a4f93  mov     [rbp+240h+var_2B8], rsi
0x1800a4f97  mov     [rbp+240h+var_2B0], rsi
0x1800a4f9b  mov     [rbp+240h+var_2A8], rsi
0x1800a4f9f  mov     [rbp+240h+var_2A0], rsi
0x1800a4fa3  lea     r8, [rbp+240h+var_2B8]
0x1800a4fa7  lea     rcx, aDefaultS1518S1; ".DEFAULT;S-1-5-18;S-1-5-19;S-1-5-20"
0x1800a4fae  call    ?SplitStringToArray@FlightSettingsAPICommon@@SAJPEBG0AEAV?$CCoSimpleArray@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@@@@Z; FlightSettingsAPICommon::SplitStringToArray(ushort const *,ushort const *,CCoSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>,4294967294,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>> &)
0x1800a4fb3  mov     ebx, eax
0x1800a4fb5  test    eax, eax
0x1800a4fb7  jns     short loc_1800A4FE3
0x1800a4fb9  mov     edx, 0ECh; void *
0x1800a4fbe  mov     r9d, eax; char *
0x1800a4fc1  lea     r8, aOnecoreBaseFli_74; "onecore\\base\\flighting\\flightsetting"...
0x1800a4fc8  mov     rcx, [rbp+248h]; this
0x1800a4fcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4fd4  nop
0x1800a4fd5  lea     rcx, [rbp+240h+var_2B8]
0x1800a4fd9  call    ?RemoveAll@?$CTSimpleArray@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@V?$CSimpleArrayStandardCompareHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@V?$CSimpleArrayStandardMergeHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@@@QEAAXXZ; CTSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>,4294967294,CTPolicyCoTaskMem<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>,CSimpleArrayStandardMergeHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>>::RemoveAll(void)
0x1800a4fde  jmp     loc_1800A51CA
0x1800a4fe3  mov     [rsp+340h+cSubKeys], esi
0x1800a4fe7  mov     [rbp+240h+cbMaxSubKeyLen], esi
0x1800a4fea  mov     [rsp+340h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1800a4fef  mov     [rsp+340h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x1800a4ff4  mov     [rsp+340h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x1800a4ff9  mov     [rsp+340h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x1800a4ffe  mov     [rsp+340h+lpcValues], rsi; lpcValues
0x1800a5003  mov     [rsp+340h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x1800a5008  lea     rax, [rbp+240h+cbMaxSubKeyLen]
0x1800a500c  mov     [rsp+340h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800a5011  lea     rax, [rsp+340h+cSubKeys]
0x1800a5016  mov     [rsp+340h+lpcSubKeys], rax; lpcSubKeys
0x1800a501b  xor     r9d, r9d; lpReserved
0x1800a501e  xor     r8d, r8d; lpcchClass
0x1800a5021  xor     edx, edx; lpClass
0x1800a5023  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800a502a  call    cs:__imp_RegQueryInfoKeyW
0x1800a5030  mov     ebx, eax
0x1800a5032  test    eax, eax
0x1800a5034  jle     short loc_1800A503F
0x1800a5036  movzx   ebx, ax
0x1800a5039  or      ebx, 80070000h
0x1800a503f  test    ebx, ebx
0x1800a5041  jns     short loc_1800A5050
0x1800a5043  mov     r9d, ebx
0x1800a5046  mov     edx, 0F2h
0x1800a504b  jmp     loc_1800A4FC1
0x1800a5050  mov     ebx, esi
0x1800a5052  mov     r14d, esi
0x1800a5055  cmp     [rsp+340h+cSubKeys], esi
0x1800a5059  jbe     loc_1800A4FD5
0x1800a505f  mov     r12, [rbp+240h+var_2B0]
0x1800a5063  mov     r13, [rbp+240h+var_2B8]
0x1800a5067  xor     edx, edx; Val
0x1800a5069  mov     r8d, 208h; Size
0x1800a506f  lea     rcx, [rbp+240h+Name]; void *
0x1800a5073  call    memset_0
0x1800a5078  mov     [rbp+240h+cchName], 104h
0x1800a507f  mov     [rsp+340h+lpcValues], rsi; lpftLastWriteTime
0x1800a5084  mov     [rsp+340h+lpcbMaxClassLen], rsi; lpcchClass
0x1800a5089  mov     [rsp+340h+lpcbMaxSubKeyLen], rsi; lpClass
0x1800a508e  mov     [rsp+340h+lpcSubKeys], rsi; unsigned int
0x1800a5093  lea     r9, [rbp+240h+cchName]; lpcchName
0x1800a5097  lea     r8, [rbp+240h+Name]; lpName
0x1800a509b  mov     edx, r14d; dwIndex
0x1800a509e  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800a50a5  call    cs:__imp_RegEnumKeyExW
0x1800a50ab  cmp     eax, 103h
0x1800a50b0  jz      loc_1800A5166
0x1800a50b6  test    eax, eax
0x1800a50b8  jnz     loc_1800A5185
0x1800a50be  lea     rdx, aClasses; "_Classes"
0x1800a50c5  lea     rcx, [rbp+240h+Name]; Str
0x1800a50c9  call    cs:__imp_wcsstr
0x1800a50cf  test    rax, rax
0x1800a50d2  jnz     loc_1800A5158
0x1800a50d8  test    r12, r12
0x1800a50db  jz      short loc_1800A5106
0x1800a50dd  lea     rax, [rsi+rsi*2]
0x1800a50e1  lea     rcx, ds:0[rax*8]
0x1800a50e9  add     rcx, r13
0x1800a50ec  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800a50f0  lea     rdx, [rbp+240h+Name]
0x1800a50f4  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a50f9  cmp     eax, 2
0x1800a50fc  jz      short loc_1800A5156
0x1800a50fe  inc     rsi
0x1800a5101  cmp     rsi, r12
0x1800a5104  jb      short loc_1800A50DD
0x1800a5106  mov     r9, r15
0x1800a5109  lea     r8, [rbp+240h+Name]
0x1800a510d  lea     rdx, aSS_2; "%s\\%s"
0x1800a5114  lea     rcx, [rsp+340h+var_2D8]
0x1800a5119  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800a511e  mov     ebx, eax
0x1800a5120  xor     esi, esi
0x1800a5122  test    eax, eax
0x1800a5124  js      short loc_1800A517B
0x1800a5126  mov     rdx, [rsp+340h+var_2D8]; unsigned __int16 *
0x1800a512b  mov     rcx, rdi; this
0x1800a512e  call    ?RunRegAction@FSRegWriteServiceDrivenAction@@AEAAJPEBG@Z; FSRegWriteServiceDrivenAction::RunRegAction(ushort const *)
0x1800a5133  mov     ebx, eax
0x1800a5135  mov     rcx, [rbp+248h]; this
0x1800a513c  test    eax, eax
0x1800a513e  jns     short loc_1800A5158
0x1800a5140  mov     r9d, eax; char *
0x1800a5143  lea     r8, aOnecoreBaseFli_74; "onecore\\base\\flighting\\flightsetting"...
0x1800a514a  mov     edx, 11Ah; void *
0x1800a514f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a5154  jmp     short loc_1800A5158
0x1800a5156  xor     esi, esi
0x1800a5158  inc     r14d
0x1800a515b  cmp     r14d, [rsp+340h+cSubKeys]
0x1800a5160  jb      loc_1800A5067
0x1800a5166  test    ebx, ebx
0x1800a5168  jns     loc_1800A4FD5
0x1800a516e  mov     r9d, ebx
0x1800a5171  mov     edx, 120h
0x1800a5176  jmp     loc_1800A4FC1
0x1800a517b  mov     edx, 118h
0x1800a5180  jmp     loc_1800A4FBE
0x1800a5185  mov     rcx, [rbp+248h]; this
0x1800a518c  mov     r9d, eax; char *
0x1800a518f  lea     r8, aOnecoreBaseFli_74; "onecore\\base\\flighting\\flightsetting"...
0x1800a5196  mov     edx, 0FEh; void *
0x1800a519b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a51a0  mov     ebx, eax
0x1800a51a2  jmp     loc_1800A4FD5
0x1800a51a7  mov     edx, 12Fh
0x1800a51ac  jmp     short loc_1800A51B3
0x1800a51ae  mov     edx, 0E5h; void *
0x1800a51b3  mov     r9d, eax; char *
0x1800a51b6  mov     rcx, [rbp+248h]; this
0x1800a51bd  lea     r8, aOnecoreBaseFli_74; "onecore\\base\\flighting\\flightsetting"...
0x1800a51c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a51c9  nop
  ... truncated ...
```
