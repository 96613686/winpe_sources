# OnlineScanAllowedInInterval(Microsoft::WRL::Wrappers::HString const &,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>,bool)

- ea: `0x1800db7b4`
- end: `0x1800dbfb1`
- name: `?OnlineScanAllowedInInterval@@YA_NAEBVHString@Wrappers@WRL@Microsoft@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@_N@Z`
- size: `2045`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801cedf0`

## callees

- `0x180009ea0`
- `0x180010b74`
- `0x18001c144`
- `0x18001c414`
- `0x18001c964`
- `0x1800370f4`
- `0x180037880`
- `0x18003eb2c`
- `0x18003eb7c`
- `0x18003ebcc`
- `0x1800465b8`
- `0x1800d982c`
- `0x1800d9ad0`
- `0x1800d9b1c`
- `0x1800dae90`
- `0x1800db024`
- `0x1800db7b4`
- `0x1800dbfb8`
- `0x1800dc2cc`
- `0x1800dc4b4`
- `0x1800dc9c4`
- `0x1800dd158`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db7f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db828`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbf81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db7f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db828`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbf81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800db810`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800db855`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800db878`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800db8be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dba55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dbb4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dbcbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dbd7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dbe09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dbeec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800db810`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800db855`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800db878`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800db8be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dba55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dbb4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dbcbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dbd7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dbe09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dbeec`

## string_xrefs

- `0x1800db82e`: `onecoreuap\enduser\winstore\installservice\lib\stringhelpers.cpp`
- `0x1800dba98`: `onecoreuap\enduser\winstore\installservice\lib\stringhelpers.cpp`
- `0x1800dbad0`: `onecoreuap\enduser\winstore\installservice\lib\stringhelpers.cpp`
- `0x1800dbb91`: `onecoreuap\enduser\winstore\installservice\lib\stringhelpers.cpp`
- `0x1800dbbc9`: `onecoreuap\enduser\winstore\installservice\lib\stringhelpers.cpp`
- `0x1800dbd00`: `onecoreuap\enduser\winstore\installservice\lib\stringhelpers.cpp`
- `0x1800dbd38`: `onecoreuap\enduser\winstore\installservice\lib\stringhelpers.cpp`
- `0x1800dbdc0`: `onecoreuap\enduser\winstore\installservice\lib\stringhelpers.cpp`
- `0x1800dbe4c`: `onecoreuap\enduser\winstore\installservice\lib\stringhelpers.cpp`
- `0x1800db860`: `Error while setting fulfillment cache placeholder for %s`
- `0x1800dba77`: `Forced cooldown exemption for %s. Current last scan time cache: %s`
- `0x1800dbb70`: `Least recent scan outside of interval for %s. Current last scan time cache: %s`
- `0x1800db883`: `Error while getting cached last scan time for %s`
- `0x1800dbf06`: `Scan time vector found empty for %s. Current last scan time cache: %s`
- `0x1800dbe2b`: `Scan not allowed inside interval for %s. Current last scan time cache: %s`
- `0x1800dbcdf`: `Scan allowed inside interval for %s. Current last scan time cache: %s`
- `0x1800dbd9f`: `Online scan not allowed due to cooldown period for %s. Current last scan time cache: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
char __fastcall OnlineScanAllowedInInterval(Microsoft::WRL::Wrappers::Details **a1, __int64 a2, char a3)
{
  HSTRING v5; // r8
  const WCHAR *StringRawBuffer; // rax
  int CachedLastScanTime; // ebx
  char v8; // r14
  int v9; // ebx
  HSTRING v10; // rbx
  PCWSTR v11; // rax
  __int64 v12; // r12
  __int64 OnlineScanIntervalLengthFromOneSettings; // r13
  __int64 v14; // rsi
  __int64 OnlineScanCooldownFromOneSettings; // r8
  __int64 v16; // rax
  char *v17; // rdx
  __int64 v18; // rax
  const unsigned __int16 *v19; // r8
  int v20; // eax
  const unsigned __int16 *v21; // r8
  int v22; // eax
  char *v23; // rdx
  const unsigned __int16 *v24; // r8
  int v25; // eax
  wchar_t *v26; // rdi
  PCWSTR v27; // rax
  wchar_t *v28; // rcx
  _QWORD *v29; // rdi
  PCWSTR v30; // rax
  char *v31; // rdx
  const unsigned __int16 *v32; // r8
  int ScanTime; // eax
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+20h] [rbp-E0h]
  int v37; // [rsp+20h] [rbp-E0h]
  int v38; // [rsp+20h] [rbp-E0h]
  PCWSTR v39; // [rsp+40h] [rbp-C0h]
  PCWSTR v40; // [rsp+40h] [rbp-C0h]
  char *v42; // [rsp+58h] [rbp-A8h] BYREF
  char *v43; // [rsp+60h] [rbp-A0h]
  char *v44; // [rsp+68h] [rbp-98h]
  wchar_t *v45; // [rsp+70h] [rbp-90h] BYREF
  _BYTE *v46; // [rsp+78h] [rbp-88h]
  HSTRING string; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v48[24]; // [rsp+88h] [rbp-78h] BYREF
  HSTRING v49; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v50[3]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v51; // [rsp+C0h] [rbp-40h]
  wchar_t v52[8]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v53; // [rsp+D8h] [rbp-28h]
  __int128 v54; // [rsp+E8h] [rbp-18h]
  int v55; // [rsp+F8h] [rbp-8h]
  wchar_t Buffer[8]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v57; // [rsp+110h] [rbp+10h]
  __int128 v58; // [rsp+120h] [rbp+20h]
  int v59; // [rsp+130h] [rbp+30h]
  _BYTE v60[4]; // [rsp+134h] [rbp+34h] BYREF
  _QWORD Src[4]; // [rsp+138h] [rbp+38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  WindowsDeleteString(0);
  v49 = 0;
  GetCategoryIdFromPackageFamilyNameOrEmpty(&string, a1, v5);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  CachedLastScanTime = GetCachedLastScanTime(StringRawBuffer, &v49);
  WindowsDeleteString(string);
  v8 = 1;
  if ( CachedLastScanTime == -2147024894 )
  {
    v9 = SetFulfillmentCachePlaceholder((const struct Microsoft::WRL::Wrappers::HString *)a1);
    if ( v9 < 0 )
    {
      v39 = WindowsGetStringRawBuffer((HSTRING)*a1, 0);
      LogMessage(
        1u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\stringhelpers.cpp",
        0x1A0u,
        "OnlineScanAllowedInInterval",
        v9,
        L"Error while setting fulfillment cache placeholder for %s",
        0,
        0,
        v39);
    }
  }
  else if ( CachedLastScanTime < 0 )
  {
    v40 = WindowsGetStringRawBuffer((HSTRING)*a1, 0);
    LogMessage(
      1u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\stringhelpers.cpp",
      0x1A6u,
      "OnlineScanAllowedInInterval",
      CachedLastScanTime,
      L"Error while getting cached last scan time for %s",
      0,
      0,
      v40);
  }
  v10 = v49;
  v11 = WindowsGetStringRawBuffer(v49, 0);
  ScanTimesToVector(&v42, v11);
  if ( v42 == v43 )
  {
    time_point_iso8601::time_point_iso8601(Buffer);
    v31 = v43;
    if ( v43 == v44 )
    {
      std::vector<time_point_iso8601>::_Emplace_reallocate<time_point_iso8601 const &>(&v42, v43, Buffer);
    }
    else
    {
      *(_OWORD *)v43 = *(_OWORD *)Buffer;
      *((_OWORD *)v31 + 1) = v57;
      *((_OWORD *)v31 + 2) = v58;
      *((_DWORD *)v31 + 12) = v59;
      v43 += 52;
    }
    std::vector<time_point_iso8601>::vector<time_point_iso8601>(v48, &v42);
    TimepointVectorToString(v50);
    WindowsGetStringRawBuffer((HSTRING)*a1, 0);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\stringhelpers.cpp",
      0x1AFu,
      "OnlineScanAllowedInInterval",
      -1,
      L"Scan time vector found empty for %s. Current last scan time cache: %s",
      0,
      0);
    v32 = (const unsigned __int16 *)v50;
    if ( v51 > 7 )
      v32 = (const unsigned __int16 *)v50[0];
    ScanTime = SetCachedLastScanTime(a1, a2, v32);
    if ( ScanTime < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B0,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\stringhelpers.cpp",
        (const char *)(unsigned int)ScanTime,
        v38);
    goto LABEL_49;
  }
  time_point_iso8601::parse(&v45, v43 - 52);
  time_point_iso8601::parse(&string, v42);
  v12 = (a2 - (__int64)string) / 10000000;
  OnlineScanIntervalLengthFromOneSettings = GetOnlineScanIntervalLengthFromOneSettings();
  v14 = v43 - v42;
  LODWORD(string) = GetOnlineScansAllowedInIntervalFromOneSettings();
  OnlineScanCooldownFromOneSettings = GetOnlineScanCooldownFromOneSettings();
  if ( a3 )
  {
    std::wstring::wstring(v50);
    if ( v12 < OnlineScanIntervalLengthFromOneSettings )
    {
      time_point_iso8601::time_point_iso8601(v52);
      v17 = v43;
      if ( v43 == v44 )
      {
        std::vector<time_point_iso8601>::_Emplace_reallocate<time_point_iso8601 const &>(&v42, v43, v52);
      }
      else
      {
        *(_OWORD *)v43 = *(_OWORD *)v52;
        *((_OWORD *)v17 + 1) = v53;
        *((_OWORD *)v17 + 2) = v54;
        *((_DWORD *)v17 + 12) = v55;
        v43 += 52;
      }
      std::vector<time_point_iso8601>::vector<time_point_iso8601>(v48, &v42);
      v18 = TimepointVectorToString(Src);
      std::wstring::operator=(v50, v18);
      std::wstring::_Tidy_deallocate(Src);
    }
    else
    {
      time_point_iso8601::time_point_iso8601(Buffer);
      v45 = Buffer;
      v46 = v60;
      std::vector<time_point_iso8601>::vector<time_point_iso8601>(v52, &v45);
      std::vector<time_point_iso8601>::vector<time_point_iso8601>(v48, v52);
      v16 = TimepointVectorToString(Src);
      std::wstring::operator=(v50, v16);
      std::wstring::_Tidy_deallocate(Src);
      std::vector<time_point_iso8601>::_Tidy(v52);
    }
    WindowsGetStringRawBuffer((HSTRING)*a1, 0);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\stringhelpers.cpp",
      0x1CCu,
      "OnlineScanAllowedInInterval",
      -1,
      L"Forced cooldown exemption for %s. Current last scan time cache: %s",
      0,
      0);
    v19 = (const unsigned __int16 *)v50;
    if ( v51 > 7 )
      v19 = (const unsigned __int16 *)v50[0];
    v20 = SetCachedLastScanTime(a1, a2, v19);
    if ( v20 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CD,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\stringhelpers.cpp",
        (const char *)(unsigned int)v20,
        v35);
LABEL_49:
    std::wstring::_Tidy_deallocate(v50);
    goto LABEL_50;
  }
  if ( v12 < OnlineScanIntervalLengthFromOneSettings )
  {
    if ( 0x4EC4EC4EC4EC4EC5LL * (v14 >> 2) >= (unsigned __int64)(unsigned int)string )
    {
      std::vector<time_point_iso8601>::vector<time_point_iso8601>(v48, &v42);
      TimepointVectorToString(Src);
      v29 = Src;
      if ( Src[3] > 7u )
        v29 = (_QWORD *)Src[0];
      v30 = WindowsGetStringRawBuffer((HSTRING)*a1, 0);
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\stringhelpers.cpp",
        0x1EEu,
        "OnlineScanAllowedInInterval",
        -1,
        L"Scan not allowed inside interval for %s. Current last scan time cache: %s",
        0,
        0,
        v30,
        v29);
      v28 = (wchar_t *)Src;
    }
    else
    {
      if ( (a2 - (__int64)v45) / 10000000 >= OnlineScanCooldownFromOneSettings )
      {
        time_point_iso8601::time_point_iso8601(Buffer);
        v23 = v43;
        if ( v43 == v44 )
        {
          std::vector<time_point_iso8601>::_Emplace_reallocate<time_point_iso8601 const &>(&v42, v43, Buffer);
        }
        else
        {
          *(_OWORD *)v43 = *(_OWORD *)Buffer;
          *((_OWORD *)v23 + 1) = v57;
          *((_OWORD *)v23 + 2) = v58;
          *((_DWORD *)v23 + 12) = v59;
          v43 += 52;
        }
        std::vector<time_point_iso8601>::vector<time_point_iso8601>(v48, &v42);
        TimepointVectorToString(v50);
        WindowsGetStringRawBuffer((HSTRING)*a1, 0);
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\stringhelpers.cpp",
          0x1DFu,
          "OnlineScanAllowedInInterval",
          -1,
          L"Scan allowed inside interval for %s. Current last scan time cache: %s",
          0,
          0);
        v24 = (const unsigned __int16 *)v50;
        if ( v51 > 7 )
          v24 = (const unsigned __int16 *)v50[0];
        v25 = SetCachedLastScanTime(a1, a2, v24);
        if ( v25 < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1E0,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\stringhelpers.cpp",
            (const char *)(unsigned int)v25,
            v37);
        goto LABEL_49;
      }
      std::vector<time_point_iso8601>::vector<time_point_iso8601>(v48, &v42);
      TimepointVectorToString(v52);
      v26 = v52;
      if ( *((_QWORD *)&v53 + 1) > 7u )
        v26 = *(wchar_t **)v52;
      v27 = WindowsGetStringRawBuffer((HSTRING)*a1, 0);
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\stringhelpers.cpp",
        0x1E6u,
        "OnlineScanAllowedInInterval",
        -1,
        L"Online scan not allowed due to cooldown period for %s. Current last scan time cache: %s",
        0,
        0,
        v27,
        v26);
      v28 = v52;
    }
    std::wstring::_Tidy_deallocate(v28);
    v8 = 0;
  }
  else
  {
    time_point_iso8601::time_point_iso8601(Buffer);
    v45 = Buffer;
    v46 = v60;
    std::vector<time_point_iso8601>::vector<time_point_iso8601>(v52, &v45);
    std::vector<time_point_iso8601>::vector<time_point_iso8601>(v48, v52);
    TimepointVectorToString(v50);
    WindowsGetStringRawBuffer((HSTRING)*a1, 0);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\stringhelpers.cpp",
      0x1D4u,
      "OnlineScanAllowedInInterval",
      -1,
      L"Least recent scan outside of interval for %s. Current last scan time cache: %s",
      0,
      0);
    v21 = (const unsigned __int16 *)v50;
    if ( v51 > 7 )
      v21 = (const unsigned __int16 *)v50[0];
    v22 = SetCachedLastScanTime(a1, a2, v21);
    if ( v22 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D5,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\stringhelpers.cpp",
        (const char *)(unsigned int)v22,
        v36);
    std::wstring::_Tidy_deallocate(v50);
    std::vector<time_point_iso8601>::_Tidy(v52);
  }
LABEL_50:
  std::vector<time_point_iso8601>::_Tidy(&v42);
  WindowsDeleteString(v10);
  return v8;
}

```

## disassembly

```asm
0x1800db7b4  mov     [rsp-8+arg_10], rbx
0x1800db7b9  mov     [rsp-8+arg_8], rdx
0x1800db7be  push    rbp
0x1800db7bf  push    rsi
0x1800db7c0  push    rdi
0x1800db7c1  push    r12
0x1800db7c3  push    r13
0x1800db7c5  push    r14
0x1800db7c7  push    r15
0x1800db7c9  lea     rbp, [rsp-60h]
0x1800db7ce  sub     rsp, 160h
0x1800db7d5  mov     rax, cs:__security_cookie
0x1800db7dc  xor     rax, rsp
0x1800db7df  mov     [rbp+90h+var_38], rax
0x1800db7e3  mov     [rsp+190h+var_140], r8b
0x1800db7e8  mov     rdi, rdx
0x1800db7eb  mov     r15, rcx
0x1800db7ee  xor     ecx, ecx; string
0x1800db7f0  call    cs:__imp_WindowsDeleteString
0x1800db7f6  xor     r12d, r12d
0x1800db7f9  mov     [rbp+90h+var_F0], r12
0x1800db7fd  mov     rdx, r15
0x1800db800  lea     rcx, [rbp+90h+string]
0x1800db804  call    ?GetCategoryIdFromPackageFamilyNameOrEmpty@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV1234@PEAUHKEY__@@@Z; GetCategoryIdFromPackageFamilyNameOrEmpty(Microsoft::WRL::Wrappers::HString const &,HKEY__ *)
0x1800db809  nop
0x1800db80a  xor     edx, edx; length
0x1800db80c  mov     rcx, [rbp+90h+string]; string
0x1800db810  call    cs:__imp_WindowsGetStringRawBuffer
0x1800db816  lea     rdx, [rbp+90h+var_F0]; HSTRING *
0x1800db81a  mov     rcx, rax; lpValue
0x1800db81d  call    ?GetCachedLastScanTime@@YAJPEBGPEAPEAUHSTRING__@@@Z; GetCachedLastScanTime(ushort const *,HSTRING__ * *)
0x1800db822  mov     ebx, eax
0x1800db824  mov     rcx, [rbp+90h+string]; string
0x1800db828  call    cs:__imp_WindowsDeleteString
0x1800db82e  lea     r13, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\installs"...
0x1800db835  lea     r14d, [r12+1]
0x1800db83a  cmp     ebx, 80070002h
0x1800db840  jnz     short loc_1800DB86F
0x1800db842  mov     rcx, r15; struct Microsoft::WRL::Wrappers::HString *
0x1800db845  call    ?SetFulfillmentCachePlaceholder@@YAJAEBVHString@Wrappers@WRL@Microsoft@@@Z; SetFulfillmentCachePlaceholder(Microsoft::WRL::Wrappers::HString const &)
0x1800db84a  mov     ebx, eax
0x1800db84c  test    eax, eax
0x1800db84e  jns     short loc_1800DB8B5
0x1800db850  xor     edx, edx; length
0x1800db852  mov     rcx, [r15]; string
0x1800db855  call    cs:__imp_WindowsGetStringRawBuffer
0x1800db85b  mov     [rsp+190h+var_150], rax
0x1800db860  lea     rax, aErrorWhileSett; "Error while setting fulfillment cache p"...
0x1800db867  mov     r8d, 1A0h
0x1800db86d  jmp     short loc_1800DB890
0x1800db86f  test    ebx, ebx
0x1800db871  jns     short loc_1800DB8B5
0x1800db873  xor     edx, edx; length
0x1800db875  mov     rcx, [r15]; string
0x1800db878  call    cs:__imp_WindowsGetStringRawBuffer
0x1800db87e  mov     [rsp+190h+var_150], rax
0x1800db883  lea     rax, aErrorWhileGett; "Error while getting cached last scan ti"...
0x1800db88a  mov     r8d, 1A6h; unsigned int
0x1800db890  mov     [rsp+190h+var_158], r12; unsigned __int16 *
0x1800db895  mov     [rsp+190h+var_160], r12; char *
0x1800db89a  mov     [rsp+190h+var_168], rax; unsigned __int16 *
0x1800db89f  mov     [rsp+190h+var_170], ebx; int
0x1800db8a3  lea     r9, aOnlinescanallo; "OnlineScanAllowedInInterval"
0x1800db8aa  mov     rdx, r13; char *
0x1800db8ad  mov     ecx, r14d; unsigned int
0x1800db8b0  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800db8b5  xor     edx, edx; length
0x1800db8b7  mov     rbx, [rbp+90h+var_F0]
0x1800db8bb  mov     rcx, rbx; string
0x1800db8be  call    cs:__imp_WindowsGetStringRawBuffer
0x1800db8c4  mov     rdx, rax
0x1800db8c7  lea     rcx, [rsp+190h+var_138]
0x1800db8cc  call    ?ScanTimesToVector@@YA?AV?$vector@Utime_point_iso8601@@V?$allocator@Utime_point_iso8601@@@std@@@std@@PEBG@Z; ScanTimesToVector(ushort const *)
0x1800db8d1  nop
0x1800db8d2  mov     rdx, [rsp+190h+var_130]
0x1800db8d7  cmp     [rsp+190h+var_138], rdx
0x1800db8dc  jz      loc_1800DBE6F
0x1800db8e2  add     rdx, 0FFFFFFFFFFFFFFCCh
0x1800db8e6  lea     rcx, [rsp+190h+var_120]
0x1800db8eb  call    ?parse@time_point_iso8601@@SA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@PEBG@Z; time_point_iso8601::parse(ushort const *)
0x1800db8f0  mov     rdx, [rsp+190h+var_138]
0x1800db8f5  lea     rcx, [rbp+90h+string]
0x1800db8f9  call    ?parse@time_point_iso8601@@SA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@PEBG@Z; time_point_iso8601::parse(ushort const *)
0x1800db8fe  mov     rcx, rdi
0x1800db901  sub     rcx, [rbp+90h+string]
0x1800db905  mov     rax, 0D6BF94D5E57A42BDh
0x1800db90f  imul    rcx
0x1800db912  lea     r12, [rcx+rdx]
0x1800db916  sar     r12, 17h
0x1800db91a  mov     rax, r12
0x1800db91d  shr     rax, 3Fh
0x1800db921  add     r12, rax
0x1800db924  call    ?GetOnlineScanIntervalLengthFromOneSettings@@YA_JXZ; GetOnlineScanIntervalLengthFromOneSettings(void)
0x1800db929  mov     r13, rax
0x1800db92c  mov     rsi, [rsp+190h+var_130]
0x1800db931  sub     rsi, [rsp+190h+var_138]
0x1800db936  call    ?GetOnlineScansAllowedInIntervalFromOneSettings@@YAIXZ; GetOnlineScansAllowedInIntervalFromOneSettings(void)
0x1800db93b  mov     dword ptr [rbp+90h+string], eax
0x1800db93e  call    ?GetOnlineScanCooldownFromOneSettings@@YA_JXZ; GetOnlineScanCooldownFromOneSettings(void)
0x1800db943  mov     r8, rax
0x1800db946  cmp     [rsp+190h+var_140], 0
0x1800db94b  jz      loc_1800DBAE7
0x1800db951  lea     rcx, [rbp+90h+var_E8]
0x1800db955  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800db95a  nop
0x1800db95b  lea     rdx, [rbp+90h+arg_8]
0x1800db962  cmp     r12, r13
0x1800db965  jl      short loc_1800DB9CB
0x1800db967  lea     rcx, [rbp+90h+Buffer]; Buffer
0x1800db96b  call    ??0time_point_iso8601@@QEAA@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; time_point_iso8601::time_point_iso8601(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x1800db970  lea     rax, [rbp+90h+Buffer]
0x1800db974  mov     [rsp+190h+var_120], rax
0x1800db979  lea     rax, [rbp+90h+var_5C]
0x1800db97d  mov     [rsp+190h+var_118], rax
0x1800db982  lea     rdx, [rsp+190h+var_120]
0x1800db987  lea     rcx, [rbp+90h+var_C8]
0x1800db98b  call    ??0?$vector@Utime_point_iso8601@@V?$allocator@Utime_point_iso8601@@@std@@@std@@QEAA@V?$initializer_list@Utime_point_iso8601@@@1@AEBV?$allocator@Utime_point_iso8601@@@1@@Z; std::vector<time_point_iso8601>::vector<time_point_iso8601>(std::initializer_list<time_point_iso8601>,std::allocator<time_point_iso8601> const &)
0x1800db990  nop
0x1800db991  lea     rdx, [rbp+90h+var_C8]
0x1800db995  lea     rcx, [rbp+90h+var_108]
0x1800db999  call    ??0?$vector@Utime_point_iso8601@@V?$allocator@Utime_point_iso8601@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<time_point_iso8601>::vector<time_point_iso8601>(std::vector<time_point_iso8601> const &)
0x1800db99e  mov     rdx, rax
0x1800db9a1  lea     rcx, [rbp+90h+Src]; Src
0x1800db9a5  call    ?TimepointVectorToString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@Utime_point_iso8601@@V?$allocator@Utime_point_iso8601@@@std@@@2@@Z; TimepointVectorToString(std::vector<time_point_iso8601>)
0x1800db9aa  mov     rdx, rax
0x1800db9ad  lea     rcx, [rbp+90h+var_E8]
0x1800db9b1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800db9b6  lea     rcx, [rbp+90h+Src]
0x1800db9ba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800db9bf  nop
0x1800db9c0  lea     rcx, [rbp+90h+var_C8]
0x1800db9c4  call    ?_Tidy@?$vector@Utime_point_iso8601@@V?$allocator@Utime_point_iso8601@@@std@@@std@@AEAAXXZ; std::vector<time_point_iso8601>::_Tidy(void)
0x1800db9c9  jmp     short loc_1800DBA42
0x1800db9cb  lea     rcx, [rbp+90h+var_C8]; Buffer
0x1800db9cf  call    ??0time_point_iso8601@@QEAA@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; time_point_iso8601::time_point_iso8601(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x1800db9d4  mov     rdx, [rsp+190h+var_130]
0x1800db9d9  cmp     rdx, [rsp+190h+var_128]
0x1800db9de  jz      short loc_1800DBA05
0x1800db9e0  movups  xmm0, xmmword ptr [rbp+90h+var_C8]
0x1800db9e4  movups  xmmword ptr [rdx], xmm0
0x1800db9e7  movups  xmm1, [rbp+90h+var_B8]
0x1800db9eb  movups  xmmword ptr [rdx+10h], xmm1
0x1800db9ef  movups  xmm0, [rbp+90h+var_A8]
0x1800db9f3  movups  xmmword ptr [rdx+20h], xmm0
0x1800db9f7  mov     eax, [rbp+90h+var_98]
0x1800db9fa  mov     [rdx+30h], eax
0x1800db9fd  add     [rsp+190h+var_130], 34h ; '4'
0x1800dba03  jmp     short loc_1800DBA13
0x1800dba05  lea     r8, [rbp+90h+var_C8]
0x1800dba09  lea     rcx, [rsp+190h+var_138]
0x1800dba0e  call    ??$_Emplace_reallocate@AEBUtime_point_iso8601@@@?$vector@Utime_point_iso8601@@V?$allocator@Utime_point_iso8601@@@std@@@std@@AEAAPEAUtime_point_iso8601@@QEAU2@AEBU2@@Z; std::vector<time_point_iso8601>::_Emplace_reallocate<time_point_iso8601 const &>(time_point_iso8601 * const,time_point_iso8601 const &)
0x1800dba13  lea     rdx, [rsp+190h+var_138]
0x1800dba18  lea     rcx, [rbp+90h+var_108]
0x1800dba1c  call    ??0?$vector@Utime_point_iso8601@@V?$allocator@Utime_point_iso8601@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<time_point_iso8601>::vector<time_point_iso8601>(std::vector<time_point_iso8601> const &)
0x1800dba21  mov     rdx, rax
0x1800dba24  lea     rcx, [rbp+90h+Src]; Src
0x1800dba28  call    ?TimepointVectorToString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@Utime_point_iso8601@@V?$allocator@Utime_point_iso8601@@@std@@@2@@Z; TimepointVectorToString(std::vector<time_point_iso8601>)
0x1800dba2d  mov     rdx, rax
0x1800dba30  lea     rcx, [rbp+90h+var_E8]
0x1800dba34  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800dba39  lea     rcx, [rbp+90h+Src]
0x1800dba3d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800dba42  lea     rsi, [rbp+90h+var_E8]
0x1800dba46  cmp     [rbp+90h+var_D0], 7
0x1800dba4b  cmova   rsi, [rbp+90h+var_E8]
0x1800dba50  xor     edx, edx; length
0x1800dba52  mov     rcx, [r15]; string
0x1800dba55  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dba5b  mov     [rsp+190h+var_148], rsi
0x1800dba60  mov     [rsp+190h+var_150], rax
0x1800dba65  mov     [rsp+190h+var_158], 0; unsigned __int16 *
0x1800dba6e  mov     [rsp+190h+var_160], 0; char *
0x1800dba77  lea     rax, aForcedCooldown; "Forced cooldown exemption for %s. Curre"...
0x1800dba7e  mov     [rsp+190h+var_168], rax; unsigned __int16 *
0x1800dba83  mov     [rsp+190h+var_170], 0FFFFFFFFh; int
0x1800dba8b  lea     r9, aOnlinescanallo; "OnlineScanAllowedInInterval"
0x1800dba92  mov     r8d, 1CCh; unsigned int
0x1800dba98  lea     rdx, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\installs"...
0x1800dba9f  mov     ecx, 3; unsigned int
0x1800dbaa4  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800dbaa9  lea     r8, [rbp+90h+var_E8]
0x1800dbaad  cmp     [rbp+90h+var_D0], 7
0x1800dbab2  cmova   r8, [rbp+90h+var_E8]
0x1800dbab7  mov     rdx, rdi
0x1800dbaba  mov     rcx, r15
0x1800dbabd  call    ?SetCachedLastScanTime@@YAJAEBVHString@Wrappers@WRL@Microsoft@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@PEBG@Z; SetCachedLastScanTime(Microsoft::WRL::Wrappers::HString const &,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>,ushort const *)
0x1800dbac2  test    eax, eax
0x1800dbac4  jns     short loc_1800DBAE2
0x1800dbac6  mov     rcx, [rbp+98h]; this
0x1800dbacd  mov     r9d, eax; char *
0x1800dbad0  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\installs"...
0x1800dbad7  mov     edx, 1CDh; void *
0x1800dbadc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dbae1  nop
0x1800dbae2  jmp     loc_1800DBF69
0x1800dbae7  cmp     r12, r13
0x1800dbaea  jl      loc_1800DBBF3
0x1800dbaf0  lea     rdx, [rbp+90h+arg_8]
0x1800dbaf7  lea     rcx, [rbp+90h+Buffer]; Buffer
0x1800dbafb  call    ??0time_point_iso8601@@QEAA@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; time_point_iso8601::time_point_iso8601(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x1800dbb00  lea     rax, [rbp+90h+Buffer]
0x1800dbb04  mov     [rsp+190h+var_120], rax
0x1800dbb09  lea     rax, [rbp+90h+var_5C]
0x1800dbb0d  mov     [rsp+190h+var_118], rax
0x1800dbb12  lea     rdx, [rsp+190h+var_120]
0x1800dbb17  lea     rcx, [rbp+90h+var_C8]
0x1800dbb1b  call    ??0?$vector@Utime_point_iso8601@@V?$allocator@Utime_point_iso8601@@@std@@@std@@QEAA@V?$initializer_list@Utime_point_iso8601@@@1@AEBV?$allocator@Utime_point_iso8601@@@1@@Z; std::vector<time_point_iso8601>::vector<time_point_iso8601>(std::initializer_list<time_point_iso8601>,std::allocator<time_point_iso8601> const &)
0x1800dbb20  nop
0x1800dbb21  lea     rdx, [rbp+90h+var_C8]
0x1800dbb25  lea     rcx, [rbp+90h+var_108]
0x1800dbb29  call    ??0?$vector@Utime_point_iso8601@@V?$allocator@Utime_point_iso8601@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<time_point_iso8601>::vector<time_point_iso8601>(std::vector<time_point_iso8601> const &)
0x1800dbb2e  mov     rdx, rax
0x1800dbb31  lea     rcx, [rbp+90h+var_E8]; Src
0x1800dbb35  call    ?TimepointVectorToString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@Utime_point_iso8601@@V?$allocator@Utime_point_iso8601@@@std@@@2@@Z; TimepointVectorToString(std::vector<time_point_iso8601>)
0x1800dbb3a  nop
0x1800dbb3b  lea     rsi, [rbp+90h+var_E8]
0x1800dbb3f  cmp     [rbp+90h+var_D0], 7
0x1800dbb44  cmova   rsi, [rbp+90h+var_E8]
0x1800dbb49  xor     edx, edx; length
0x1800dbb4b  mov     rcx, [r15]; string
0x1800dbb4e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dbb54  mov     [rsp+190h+var_148], rsi
0x1800dbb59  mov     [rsp+190h+var_150], rax
0x1800dbb5e  mov     [rsp+190h+var_158], 0; unsigned __int16 *
0x1800dbb67  mov     [rsp+190h+var_160], 0; char *
0x1800dbb70  lea     rax, aLeastRecentSca; "Least recent scan outside of interval f"...
0x1800dbb77  mov     [rsp+190h+var_168], rax; unsigned __int16 *
0x1800dbb7c  mov     [rsp+190h+var_170], 0FFFFFFFFh; int
0x1800dbb84  lea     r9, aOnlinescanallo; "OnlineScanAllowedInInterval"
0x1800dbb8b  mov     r8d, 1D4h; unsigned int
0x1800dbb91  lea     rdx, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\installs"...
0x1800dbb98  mov     ecx, 3; unsigned int
0x1800dbb9d  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800dbba2  lea     r8, [rbp+90h+var_E8]
0x1800dbba6  cmp     [rbp+90h+var_D0], 7
0x1800dbbab  cmova   r8, [rbp+90h+var_E8]
0x1800dbbb0  mov     rdx, rdi
0x1800dbbb3  mov     rcx, r15
0x1800dbbb6  call    ?SetCachedLastScanTime@@YAJAEBVHString@Wrappers@WRL@Microsoft@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@PEBG@Z; SetCachedLastScanTime(Microsoft::WRL::Wrappers::HString const &,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>,ushort const *)
0x1800dbbbb  test    eax, eax
0x1800dbbbd  jns     short loc_1800DBBDB
0x1800dbbbf  mov     rcx, [rbp+98h]; this
0x1800dbbc6  mov     r9d, eax; char *
0x1800dbbc9  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\installs"...
0x1800dbbd0  mov     edx, 1D5h; void *
0x1800dbbd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dbbda  nop
0x1800dbbdb  lea     rcx, [rbp+90h+var_E8]
0x1800dbbdf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800dbbe4  nop
0x1800dbbe5  lea     rcx, [rbp+90h+var_C8]
0x1800dbbe9  call    ?_Tidy@?$vector@Utime_point_iso8601@@V?$allocator@Utime_point_iso8601@@@std@@@std@@AEAAXXZ; std::vector<time_point_iso8601>::_Tidy(void)
0x1800dbbee  jmp     loc_1800DBF73
0x1800dbbf3  sar     rsi, 2
0x1800dbbf7  mov     rcx, 4EC4EC4EC4EC4EC5h
0x1800dbc01  imul    rsi, rcx
0x1800dbc05  mov     ecx, dword ptr [rbp+90h+string]
0x1800dbc08  cmp     rsi, rcx
0x1800dbc0b  jnb     loc_1800DBDDB
0x1800dbc11  mov     rcx, rdi
0x1800dbc14  sub     rcx, [rsp+190h+var_120]
0x1800dbc19  mov     rax, 0D6BF94D5E57A42BDh
0x1800dbc23  imul    rcx
0x1800dbc26  add     rdx, rcx
0x1800dbc29  sar     rdx, 17h
0x1800dbc2d  mov     rax, rdx
0x1800dbc30  shr     rax, 3Fh
0x1800dbc34  add     rdx, rax
0x1800dbc37  cmp     rdx, r8
0x1800dbc3a  jl      loc_1800DBD4F
0x1800dbc40  lea     rdx, [rbp+90h+arg_8]
0x1800dbc47  lea     rcx, [rbp+90h+Buffer]; Buffer
0x1800dbc4b  call    ??0time_point_iso8601@@QEAA@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; time_point_iso8601::time_point_iso8601(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x1800dbc50  mov     rdx, [rsp+190h+var_130]
0x1800dbc55  cmp     rdx, [rsp+190h+var_128]
0x1800dbc5a  jz      short loc_1800DBC81
0x1800dbc5c  movups  xmm0, xmmword ptr [rbp+90h+Buffer]
0x1800dbc60  movups  xmmword ptr [rdx], xmm0
0x1800dbc63  movups  xmm1, [rbp+90h+var_80]
0x1800dbc67  movups  xmmword ptr [rdx+10h], xmm1
0x1800dbc6b  movups  xmm0, [rbp+90h+var_70]
0x1800dbc6f  movups  xmmword ptr [rdx+20h], xmm0
0x1800dbc73  mov     eax, [rbp+90h+var_60]
0x1800dbc76  mov     [rdx+30h], eax
0x1800dbc79  add     [rsp+190h+var_130], 34h ; '4'
0x1800dbc7f  jmp     short loc_1800DBC8F
0x1800dbc81  lea     r8, [rbp+90h+Buffer]
0x1800dbc85  lea     rcx, [rsp+190h+var_138]
0x1800dbc8a  call    ??$_Emplace_reallocate@AEBUtime_point_iso8601@@@?$vector@Utime_point_iso8601@@V?$allocator@Utime_point_iso8601@@@std@@@std@@AEAAPEAUtime_point_iso8601@@QEAU2@AEBU2@@Z; std::vector<time_point_iso8601>::_Emplace_reallocate<time_point_iso8601 const &>(time_point_iso8601 * const,time_point_iso8601 const &)
0x1800dbc8f  lea     rdx, [rsp+190h+var_138]
0x1800dbc94  lea     rcx, [rbp+90h+var_108]
0x1800dbc98  call    ??0?$vector@Utime_point_iso8601@@V?$allocator@Utime_point_iso8601@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<time_point_iso8601>::vector<time_point_iso8601>(std::vector<time_point_iso8601> const &)
0x1800dbc9d  mov     rdx, rax
0x1800dbca0  lea     rcx, [rbp+90h+var_E8]; Src
0x1800dbca4  call    ?TimepointVectorToString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@Utime_point_iso8601@@V?$allocator@Utime_point_iso8601@@@std@@@2@@Z; TimepointVectorToString(std::vector<time_point_iso8601>)
0x1800dbca9  nop
0x1800dbcaa  lea     rsi, [rbp+90h+var_E8]
0x1800dbcae  cmp     [rbp+90h+var_D0], 7
0x1800dbcb3  cmova   rsi, [rbp+90h+var_E8]
0x1800dbcb8  xor     edx, edx; length
  ... truncated ...
```
