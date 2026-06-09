# Windows::Compat::Appraiser::Utilities::GetWufbProperties(bool &,bool &,bool &,bool &,bool &,bool &,bool &,bool &,bool &)

- ea: `0x18008cccc`
- end: `0x18008df5f`
- name: `?GetWufbProperties@Utilities@Appraiser@Compat@Windows@@SAXAEA_N00000000@Z`
- size: `4755`
- prototype: `void __fastcall(bool *, bool *, bool *, bool *, bool *, bool *, bool *, bool *, bool *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180031920`
- `0x18005623c`

## callees

- `0x18000147c`
- `0x180008570`
- `0x180008a1c`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002d06c`
- `0x18002ebb8`
- `0x1800301d0`
- `0x18008cccc`
- `0x1800a5d88`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x18008cfd9`
- `KERNEL32!GetSystemTime` at `0x18008d182`
- `KERNEL32!GetSystemTime` at `0x18008d305`
- `KERNEL32!GetSystemTime` at `0x18008d440`
- `KERNEL32!GetSystemTime` at `0x18008d5b9`
- `KERNEL32!GetSystemTime` at `0x18008d798`
- `KERNEL32!GetSystemTime` at `0x18008d8fe`
- `KERNEL32!GetSystemTime` at `0x18008daea`
- `KERNEL32!GetSystemTime` at `0x18008dc82`
- `KERNEL32!GetSystemTime` at `0x18008de2a`
- `KERNEL32!GetSystemTime` at `0x18008cfd9`
- `KERNEL32!GetSystemTime` at `0x18008d182`
- `KERNEL32!GetSystemTime` at `0x18008d305`
- `KERNEL32!GetSystemTime` at `0x18008d440`
- `KERNEL32!GetSystemTime` at `0x18008d5b9`
- `KERNEL32!GetSystemTime` at `0x18008d798`
- `KERNEL32!GetSystemTime` at `0x18008d8fe`
- `KERNEL32!GetSystemTime` at `0x18008daea`
- `KERNEL32!GetSystemTime` at `0x18008dc82`
- `KERNEL32!GetSystemTime` at `0x18008de2a`
- `KERNEL32!LoadLibraryExW` at `0x18008cd91`
- `KERNEL32!LoadLibraryExW` at `0x18008cd91`
- `KERNEL32!FreeLibrary` at `0x18008df36`
- `KERNEL32!FreeLibrary` at `0x18008df36`
- `KERNEL32!GetProcAddress` at `0x18008ce11`
- `KERNEL32!GetProcAddress` at `0x18008ce93`
- `KERNEL32!GetProcAddress` at `0x18008ce11`
- `KERNEL32!GetProcAddress` at `0x18008ce93`
- `KERNEL32!GetLastError` at `0x18008cda4`
- `KERNEL32!GetLastError` at `0x18008cdc5`
- `KERNEL32!GetLastError` at `0x18008ce1f`
- `KERNEL32!GetLastError` at `0x18008ce40`
- `KERNEL32!GetLastError` at `0x18008cec5`
- `KERNEL32!GetLastError` at `0x18008cda4`
- `KERNEL32!GetLastError` at `0x18008cdc5`
- `KERNEL32!GetLastError` at `0x18008ce1f`
- `KERNEL32!GetLastError` at `0x18008ce40`
- `KERNEL32!GetLastError` at `0x18008cec5`

## string_xrefs

- `0x18008cde7`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008ce62`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008cef2`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008cfbf`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008d063`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008d0a7`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008d22a`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008d35b`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008d426`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008d4df`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008d5f0`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008d659`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008d6be`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008d80d`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008d9c2`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008db5a`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008dd0a`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008ce07`: `ReadPolicyWithFallback`
- `0x18008cd8a`: `updatepolicy.dll`
- `0x18008ce51`: `Error getting ReadPolicyWithFallback, swallowing: [%d].`
- `0x18008cee2`: `ReleaseEnterprisePolicyValue not exists in updatepolicy.dll, swallowing: [0x%x].`
- `0x18008d04c`: `ReleaseEnterprisePolicyValue not exists in updatepolicy.dll, swallowing: [0x%x].`
- `0x18008cdd6`: `Error getting updatepolicy.dll, swallowing: [%d].`
- `0x18008cdcf`: `Windows::Compat::Appraiser::Utilities::GetWufbProperties`
- `0x18008ce4a`: `Windows::Compat::Appraiser::Utilities::GetWufbProperties`
- `0x18008cef9`: `Windows::Compat::Appraiser::Utilities::GetWufbProperties`
- `0x18008cfa9`: `Windows::Compat::Appraiser::Utilities::GetWufbProperties`
- `0x18008d057`: `Windows::Compat::Appraiser::Utilities::GetWufbProperties`
- `0x18008d0a0`: `Windows::Compat::Appraiser::Utilities::GetWufbProperties`
- `0x18008d223`: `Windows::Compat::Appraiser::Utilities::GetWufbProperties`
- `0x18008d362`: `Windows::Compat::Appraiser::Utilities::GetWufbProperties`
- `0x18008d410`: `Windows::Compat::Appraiser::Utilities::GetWufbProperties`
- `0x18008d4d8`: `Windows::Compat::Appraiser::Utilities::GetWufbProperties`
- `0x18008d5e4`: `Windows::Compat::Appraiser::Utilities::GetWufbProperties`
- `0x18008d641`: `Windows::Compat::Appraiser::Utilities::GetWufbProperties`
- `0x18008d6b7`: `Windows::Compat::Appraiser::Utilities::GetWufbProperties`
- `0x18008d806`: `Windows::Compat::Appraiser::Utilities::GetWufbProperties`
- `0x18008d9c9`: `Windows::Compat::Appraiser::Utilities::GetWufbProperties`
- `0x18008db47`: `Windows::Compat::Appraiser::Utilities::GetWufbProperties`
- `0x18008dd11`: `Windows::Compat::Appraiser::Utilities::GetWufbProperties`

## pseudocode

```c
void __fastcall Windows::Compat::Appraiser::Utilities::GetWufbProperties(
        bool *a1,
        bool *a2,
        bool *a3,
        bool *a4,
        bool *a5,
        bool *a6,
        bool *a7,
        bool *a8,
        bool *a9)
{
  __int64 (__fastcall *v12)(void **); // rdi
  HMODULE v13; // r15
  HMODULE Library; // rax
  signed int LastError; // eax
  signed int v16; // ebx
  FARPROC ProcAddress; // r15
  signed int v18; // eax
  signed int v19; // ebx
  __int64 (__fastcall *v20)(void **); // rbx
  signed int v21; // eax
  signed int v22; // ebx
  volatile signed __int64 *v23; // rcx
  void **v24; // rdx
  int v25; // edi
  int v26; // r8d
  int v27; // r9d
  int v28; // eax
  int v29; // edi
  volatile signed __int64 *v30; // rcx
  void **v31; // rdx
  int v32; // ebx
  int v33; // r8d
  int v34; // r9d
  char *v35; // rdx
  _QWORD *v36; // rax
  volatile signed __int64 *v37; // rcx
  void **v38; // rdx
  int v39; // eax
  int v40; // edi
  volatile signed __int64 *v41; // rcx
  void **v42; // rdx
  int v43; // ebx
  int v44; // r8d
  int v45; // r9d
  int v46; // eax
  int v47; // edi
  volatile signed __int64 *v48; // rcx
  void **v49; // rdx
  volatile signed __int64 *v50; // rcx
  void **v51; // rdx
  int v52; // eax
  int v53; // edi
  volatile signed __int64 *v54; // rcx
  void **v55; // rdx
  int v56; // ebx
  int v57; // r8d
  int v58; // r9d
  int v59; // edi
  volatile signed __int64 *v60; // rcx
  void **v61; // rdx
  volatile signed __int64 *v62; // rcx
  void **v63; // rdx
  int v64; // eax
  int v65; // edi
  volatile signed __int64 *v66; // rcx
  void **v67; // rdx
  int v68; // ebx
  int v69; // r8d
  int v70; // r9d
  __int64 v71; // rcx
  char *v72; // [rsp+20h] [rbp-E0h]
  const char **v73; // [rsp+28h] [rbp-D8h]
  char *v74; // [rsp+30h] [rbp-D0h]
  const char **v75; // [rsp+38h] [rbp-C8h]
  const char **v76; // [rsp+40h] [rbp-C0h]
  char **v77; // [rsp+50h] [rbp-B0h]
  char v78[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v79; // [rsp+64h] [rbp-9Ch] BYREF
  FARPROC v80; // [rsp+68h] [rbp-98h]
  HMODULE hModule; // [rsp+70h] [rbp-90h]
  void *Block; // [rsp+78h] [rbp-88h] BYREF
  char *v83; // [rsp+80h] [rbp-80h] BYREF
  struct _SYSTEMTIME *v84; // [rsp+88h] [rbp-78h] BYREF
  const char *v85; // [rsp+90h] [rbp-70h] BYREF
  const char *v86; // [rsp+98h] [rbp-68h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+A0h] [rbp-60h] BYREF
  char *v88; // [rsp+B0h] [rbp-50h] BYREF
  char *v89; // [rsp+B8h] [rbp-48h] BYREF
  const char *v90; // [rsp+C0h] [rbp-40h] BYREF
  char *v91; // [rsp+C8h] [rbp-38h] BYREF
  char *v92; // [rsp+D0h] [rbp-30h] BYREF
  struct _SYSTEMTIME v93; // [rsp+E0h] [rbp-20h] BYREF
  char v94[144]; // [rsp+F0h] [rbp-10h] BYREF
  char v95[144]; // [rsp+180h] [rbp+80h] BYREF

  v89 = (char *)a2;
  v12 = 0;
  v92 = (char *)a7;
  v13 = 0;
  v91 = (char *)a8;
  *a8 = 0;
  *a7 = 0;
  *a6 = 0;
  *a3 = 0;
  *a2 = 0;
  *a1 = 0;
  *a9 = 1;
  v90 = (const char *)a9;
  Block = 0;
  *a5 = 1;
  *a4 = 1;
  if ( !IsWindowsVersionOrGreaterEx(0xAu, 0, 0, 0x383Au) )
    goto LABEL_140;
  *a1 = 1;
  Library = LoadLibraryExW(L"updatepolicy.dll", 0, 0x800u);
  hModule = Library;
  v13 = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    if ( v16 >= 0 )
      v16 = -2147467259;
    LODWORD(v74) = GetLastError();
    LODWORD(v72) = v16;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      208,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::GetWufbProperties",
      v72,
      (int)"Error getting updatepolicy.dll, swallowing: [%d].",
      v74);
    goto LABEL_140;
  }
  ProcAddress = GetProcAddress(Library, "ReadPolicyWithFallback");
  if ( ProcAddress )
  {
    v80 = GetProcAddress(hModule, "ReleaseEnterprisePolicyValue");
    v20 = (__int64 (__fastcall *)(void **))v80;
    if ( !v80 && IsWindowsVersionOrGreaterEx(0xAu, 0, 0, 0x3FABu) )
    {
      v21 = GetLastError();
      v22 = v21;
      if ( v21 > 0 )
        v22 = (unsigned __int16)v21 | 0x80070000;
      if ( v22 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x1EDCu,
            "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
            "Windows::Compat::Appraiser::Utilities::GetWufbProperties",
            "ReleaseEnterprisePolicyValue not exists in updatepolicy.dll, swallowing: [0x%x].",
            v22);
      }
      else
      {
        LODWORD(v74) = v22;
        LODWORD(v72) = v22;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          220,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::GetWufbProperties",
          v72,
          (int)"ReleaseEnterprisePolicyValue not exists in updatepolicy.dll, swallowing: [0x%x].",
          v74);
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v94);
        v23 = (volatile signed __int64 *)v94;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v23 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v23,
          _InterlockedExchangeAdd64(v23 + 17, 0),
          v95);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v24);
        v25 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 > 5u
          && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
        {
          *(_DWORD *)v78 = v22;
          v88 = v95;
          v79 = 7900;
          v84 = (struct _SYSTEMTIME *)"Windows::Compat::Appraiser::Utilities::GetWufbProperties";
          v85 = "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
          v86 = (const char *)&szValueBuf;
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          v83 = (char *)&v93;
          v93 = SystemTime;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v25,
            (unsigned int)&word_1802A1A0E,
            v26,
            v27,
            (__int64)&v83,
            (__int64)&v86,
            (__int64)&v79,
            (__int64)&v85,
            (__int64)&v84,
            (__int64)v78,
            (__int64)&v88);
        }
      }
      v20 = (__int64 (__fastcall *)(void **))v80;
    }
    v28 = ((__int64 (__fastcall *)(__int64, void **))ProcAddress)(32, &Block);
    v29 = v28;
    if ( v28 < 0 )
    {
      LODWORD(v74) = v28;
      LODWORD(v72) = v28;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        237,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::GetWufbProperties",
        v72,
        (int)"Error calculating WUfB, swallowing: [0x%x].",
        v74);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v94);
      v30 = (volatile signed __int64 *)v94;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v30 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v30,
        _InterlockedExchangeAdd64(v30 + 17, 0),
        v95);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v31);
      v32 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 <= 5u
        || (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) == 0
        || (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) != *(_QWORD *)(qword_1802C9628 + 24) )
      {
        goto LABEL_41;
      }
      v79 = v29;
      v83 = v95;
      v86 = "Windows::Compat::Appraiser::Utilities::GetWufbProperties";
      v84 = (struct _SYSTEMTIME *)&szValueBuf;
      v85 = "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
      *(_DWORD *)v78 = 7917;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v35 = (char *)&dword_1802A1AD4;
      goto LABEL_39;
    }
    if ( *((_DWORD *)Block + 1) == 1 )
    {
      if ( *((_WORD *)Block + 8) != 3 )
      {
        LODWORD(v72) = -2147467259;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          246,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::GetWufbProperties",
          v72,
          (int)"WUfB policy wrong type, swallowing.",
          v74);
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v94);
        v37 = (volatile signed __int64 *)v94;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v37 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v37,
          _InterlockedExchangeAdd64(v37 + 17, 0),
          v95);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v38);
        v32 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 <= 5u
          || (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) == 0
          || (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) != *(_QWORD *)(qword_1802C9628 + 24) )
        {
          goto LABEL_41;
        }
        v79 = -2147467259;
        v83 = v95;
        v86 = "Windows::Compat::Appraiser::Utilities::GetWufbProperties";
        v84 = (struct _SYSTEMTIME *)&szValueBuf;
        v85 = "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
        *(_DWORD *)v78 = 7926;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v35 = byte_1802A1A71;
        goto LABEL_39;
      }
      if ( *((_DWORD *)Block + 6) )
      {
        *a4 = 0;
        *a3 = 1;
      }
    }
    if ( v20 )
    {
      v39 = v20(&Block);
      Block = 0;
      v40 = v39;
      if ( v39 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x1F03u,
            "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
            "Windows::Compat::Appraiser::Utilities::GetWufbProperties",
            "Error calling ReleaseEnterprisePolicyValue, swallowing: [0x%x].",
            v39);
      }
      else
      {
        LODWORD(v74) = v39;
        LODWORD(v72) = v39;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          3,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::GetWufbProperties",
          v72,
          (int)"Error calling ReleaseEnterprisePolicyValue, swallowing: [0x%x].",
          v74);
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v94);
        v41 = (volatile signed __int64 *)v94;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v41 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v41,
          _InterlockedExchangeAdd64(v41 + 17, 0),
          v95);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v42);
        v43 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 > 5u
          && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
        {
          v79 = v40;
          v83 = v95;
          *(_DWORD *)v78 = 7939;
          v86 = "Windows::Compat::Appraiser::Utilities::GetWufbProperties";
          v85 = "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
          v84 = (struct _SYSTEMTIME *)&szValueBuf;
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          v88 = (char *)&v93;
          v93 = SystemTime;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v43,
            (unsigned int)qword_1802A1948,
            v44,
            v45,
            (__int64)&v88,
            (__int64)&v84,
            (__int64)v78,
            (__int64)&v85,
            (__int64)&v86,
            (__int64)&v79,
            (__int64)&v83);
        }
        v20 = (__int64 (__fastcall *)(void **))v80;
      }
    }
    else if ( IsWindowsVersionOrGreaterEx(0xAu, 0, 0, 0x3FABu) )
    {
      if ( Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors() )
      {
        LODWORD(v72) = -2147024769;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          3,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::GetWufbProperties",
          v72,
          (int)"ReleaseEnterprisePolicyValue not exists, leaking EnterprisePolicyValue.",
          v74);
      }
      else
      {
        Windows::Compat::Appraiser::WriteLog(
          0,
          3,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::GetWufbProperties",
          0,
          (int)"ReleaseEnterprisePolicyValue not exists, leaking EnterprisePolicyValue.",
          v74);
      }
    }
    else if ( Block )
    {
      operator delete(Block);
      Block = 0;
    }
    v46 = ((__int64 (__fastcall *)(__int64, void **))ProcAddress)(5, &Block);
    v47 = v46;
    if ( v46 < 0 )
    {
      LODWORD(v74) = v46;
      LODWORD(v72) = v46;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        8,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::GetWufbProperties",
        v72,
        (int)"Error calculating WUfB, swallowing: [0x%x].",
        v74);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v94);
      v48 = (volatile signed __int64 *)v94;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v48 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v48,
        _InterlockedExchangeAdd64(v48 + 17, 0),
        v95);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v49);
      v32 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 <= 5u
        || (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) == 0
        || (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) != *(_QWORD *)(qword_1802C9628 + 24) )
      {
        goto LABEL_41;
      }
      v79 = v47;
      v83 = v95;
      v86 = "Windows::Compat::Appraiser::Utilities::GetWufbProperties";
      v84 = (struct _SYSTEMTIME *)&szValueBuf;
      v85 = "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
      *(_DWORD *)v78 = 7944;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v35 = byte_1802A18E5;
      goto LABEL_39;
    }
    if ( *((_DWORD *)Block + 2) == 4 && *((_DWORD *)Block + 1) == 1 )
    {
      if ( *((_WORD *)Block + 8) != 3 )
      {
        LODWORD(v72) = -2147467259;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          20,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::GetWufbProperties",
          v72,
          (int)"WUfB policy wrong type, swallowing.",
          v74);
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v94);
        v50 = (volatile signed __int64 *)v94;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v50 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v50,
          _InterlockedExchangeAdd64(v50 + 17, 0),
          v95);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v51);
        v32 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 <= 5u
          || (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) == 0
          || (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) != *(_QWORD *)(qword_1802C9628 + 24) )
        {
          goto LABEL_41;
        }
        v79 = -2147467259;
        v83 = v95;
        v86 = "Windows::Compat::Appraiser::Utilities::GetWufbProperties";
        v84 = (struct _SYSTEMTIME *)&szValueBuf;
        v85 = "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
        *(_DWORD *)v78 = 7956;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v35 = byte_1802A19AB;
LABEL_39:
        v88 = (char *)&v93;
        v77 = &v83;
        v76 = &v86;
        v75 = &v85;
        v73 = (const char **)&v84;
        v36 = &v88;
LABEL_40:
        v93 = SystemTime;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v32,
          (_DWORD)v35,
          v33,
          v34,
          (__int64)v36,
          (__int64)v73,
          (__int64)v78,
          (__int64)v75,
          (__int64)v76,
          (__int64)&v79,
          (__int64)v77);
LABEL_41:
        v12 = (__int64 (__fastcall *)(void **))v80;
        v13 = hModule;
        goto LABEL_140;
      }
      if ( *((_DWORD *)Block + 6) )
      {
        *a5 = 0;
        *a3 = 1;
      }
    }
    *v89 = 1;
    if ( !IsWindowsVersionOrGreaterEx(0xAu, 0, 0, 0x4563u) )
    {
      v12 = (__int64 (__fastcall *)(void **))v80;
      v13 = hModule;
      goto LABEL_140;
    }
    *a6 = 1;
    if ( Block )
    {
      if ( v20 )
      {
        v52 = v20(&Block);
        Block = 0;
        v53 = v52;
        if ( v52 >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x1F33u,
              "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
              "Windows::Compat::Appraiser::Utilities::GetWufbProperties",
              "Error calling ReleaseEnterprisePolicyValue, swallowing: [0x%x].",
              v52);
        }
        else
        {
          LODWORD(v74) = v52;
          LODWORD(v72) = v52;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            51,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
            "Windows::Compat::Appraiser::Utilities::GetWufbProperties",
            v72,
            (int)"Error calling ReleaseEnterprisePolicyValue, swallowing: [0x%x].",
            v74);
          TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v94);
          v54 = (volatile signed __int64 *)v94;
          if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
            v54 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
          TraceLoggingCorrelationVector::ToStringImpl(
            (TraceLoggingCorrelationVector *)v54,
            _InterlockedExchangeAdd64(v54 + 17, 0),
            v95);
          if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
            UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v55);
          v56 = qword_1802C9628;
          if ( *(_DWORD *)qword_1802C9628 > 5u
            && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
            && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
          {
            v79 = v53;
            v89 = v95;
            v83 = "Windows::Compat::Appraiser::Utilities::GetWufbProperties";
            v85 = (const char *)&szValueBuf;
            v86 = "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
            *(_DWORD *)v78 = 7987;
            SystemTime = 0;
            GetSystemTime(&SystemTime);
            v84 = &v93;
            v93 = SystemTime;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v56,
              (unsigned int)&dword_1802A17BC,
              v57,
              v58,
              (__int64)&v84,
              (__int64)&v85,
              (__int64)v78,
              (__int64)&v86,
              (__int64)&v83,
              (__int64)&v79,
              (__int64)&v89);
          }
        }
      }
      else if ( IsWindowsVersionOrGreaterEx(0xAu, 0, 0, 0x3FABu) )
      {
        if ( Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors() )
        {
          LODWORD(v72) = -2147024769;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            51,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
            "Windows::Compat::Appraiser::Utilities::GetWufbProperties",
            v72,
            (int)"ReleaseEnterprisePolicyValue not exists, leaking EnterprisePolicyValue.",
            v74);
        }
        else
        {
          Windows::Compat::Appraiser::WriteLog(
            0,
            51,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
            "Windows::Compat::Appraiser::Utilities::GetWufbProperties",
            0,
            (int)"ReleaseEnterprisePolicyValue not exists, leaking EnterprisePolicyValue.",
            v74);
        }
      }
      else if ( Block )
      {
        operator delete(Block);
        Block = 0;
      }
    }
    v59 = ((__int64 (__fastcall *)(__int64, void **))ProcAddress)(51, &Block);
    if ( v59 < 0 )
    {
      if ( !IsWindowsVersionOrGreaterEx(0xAu, 0, 0, 0x4C88u) )
        goto LABEL_41;
      LODWORD(v74) = v59;
      LODWORD(v72) = v59;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        59,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::GetWufbProperties",
        v72,
        (int)"Error calculating WUfB, swallowing: [0x%x].",
        v74);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v94);
      v60 = (volatile signed __int64 *)v94;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v60 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v60,
        _InterlockedExchangeAdd64(v60 + 17, 0),
        v95);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v61);
      v32 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 <= 5u
        || (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) == 0
        || (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) != *(_QWORD *)(qword_1802C9628 + 24) )
      {
        goto LABEL_41;
      }
      v79 = v59;
      v89 = v95;
      v83 = "Windows::Compat::Appraiser::Utilities::GetWufbProperties";
      v85 = (const char *)&szValueBuf;
      v86 = "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
      *(_DWORD *)v78 = 7995;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v84 = &v93;
      v35 = (char *)word_1802A1882;
      v77 = &v89;
      v76 = (const char **)&v83;
      v75 = &v86;
      v73 = &v85;
      v36 = &v84;
      goto LABEL_40;
    }
    if ( *((_DWORD *)Block + 1) == 1 )
    {
      if ( *((_WORD *)Block + 8) != 3 )
      {
        LODWORD(v72) = -2147467259;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          70,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::GetWufbProperties",
          v72,
          (int)"WUfB policy wrong type, swallowing.",
          v74);
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v94);
        v62 = (volatile signed __int64 *)v94;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v62 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v62,
          _InterlockedExchangeAdd64(v62 + 17, 0),
          v95);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v63);
        v32 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 <= 5u
          || (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) == 0
          || (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) != *(_QWORD *)(qword_1802C9628 + 24) )
        {
          goto LABEL_41;
        }
        v79 = -2147467259;
        v89 = v95;
        v83 = "Windows::Compat::Appraiser::Utilities::GetWufbProperties";
        v85 = (const char *)&szValueBuf;
        v86 = "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
        *(_DWORD *)v78 = 8006;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v84 = &v93;
        v35 = &byte_1802A181F;
        v77 = &v89;
        v76 = (const char **)&v83;
        v75 = &v86;
        v73 = &v85;
        v36 = &v84;
        goto LABEL_40;
      }
      if ( !*((_DWORD *)Block + 6) )
        *v90 = 0;
      *v91 = 1;
    }
    *v92 = 1;
    goto LABEL_41;
  }
  v18 = GetLastError();
  v19 = v18;
  if ( v18 > 0 )
    v19 = (unsigned __int16)v18 | 0x80070000;
  if ( v19 >= 0 )
    v19 = -2147467259;
  LODWORD(v74) = GetLastError();
  LODWORD(v72) = v19;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    214,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
    "Windows::Compat::Appraiser::Utilities::GetWufbProperties",
    v72,
    (int)"Error getting ReadPolicyWithFallback, swallowing: [%d].",
    v74);
  v13 = hModule;
LABEL_140:
  if ( Block )
  {
    if ( v12 )
    {
      v64 = v12(&Block);
      Block = 0;
      v65 = v64;
      if ( v64 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x1F55u,
            "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
            "Windows::Compat::Appraiser::Utilities::GetWufbProperties",
            "Error calling ReleaseEnterprisePolicyValue, swallowing: [0x%x].",
            v64);
      }
      else
      {
        LODWORD(v74) = v64;
        LODWORD(v72) = v64;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          85,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::GetWufbProperties",
          v72,
          (int)"Error calling ReleaseEnterprisePolicyValue, swallowing: [0x%x].",
          v74);
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v94);
        v66 = (volatile signed __int64 *)v94;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v66 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v66,
          _InterlockedExchangeAdd64(v66 + 17, 0),
          v95);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v67);
        v68 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 > 5u
          && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
        {
          v79 = v65;
          v92 = v95;
          v91 = "Windows::Compat::Appraiser::Utilities::GetWufbProperties";
          v89 = (char *)&szValueBuf;
          v90 = "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
          *(_DWORD *)v78 = 8021;
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          v83 = (char *)&v93;
          v93 = SystemTime;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v68,
            (unsigned int)byte_1802A1759,
            v69,
            v70,
            (__int64)&v83,
            (__int64)&v89,
            (__int64)v78,
            (__int64)&v90,
            (__int64)&v91,
            (__int64)&v79,
            (__int64)&v92);
        }
      }
    }
    else if ( IsWindowsVersionOrGreaterEx(0xAu, 0, 0, 0x3FABu) )
    {
      if ( Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors() )
      {
        LODWORD(v72) = -2147024769;
        v71 = 1;
      }
      else
      {
        v72 = 0;
        v71 = 0;
      }
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)v71,
        85,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::GetWufbProperties",
        v72,
        (int)"ReleaseEnterprisePolicyValue not exists, leaking EnterprisePolicyValue.",
        v74);
    }
    else if ( Block )
    {
      operator delete(Block);
      Block = 0;
    }
  }
  if ( v13 )
    FreeLibrary(v13);
}

```

## disassembly

```asm
0x18008cccc  push    rbp
0x18008ccce  push    rbx
0x18008cccf  push    rsi
0x18008ccd0  push    rdi
0x18008ccd1  push    r12
0x18008ccd3  push    r13
0x18008ccd5  push    r14
0x18008ccd7  push    r15
0x18008ccd9  lea     rbp, [rsp-128h]
0x18008cce1  sub     rsp, 228h
0x18008cce8  mov     rax, cs:__security_cookie
0x18008ccef  xor     rax, rsp
0x18008ccf2  mov     [rbp+160h+var_50], rax
0x18008ccf9  mov     r13, [rbp+160h+arg_28]
0x18008cd00  mov     rax, rdx
0x18008cd03  mov     r12, [rbp+160h+arg_20]
0x18008cd0a  mov     r14, r8
0x18008cd0d  mov     r8, [rbp+160h+arg_30]
0x18008cd14  mov     rsi, r9
0x18008cd17  xor     r9d, r9d
0x18008cd1a  mov     [rbp+160h+var_1A8], rdx
0x18008cd1e  mov     rdx, [rbp+160h+arg_38]
0x18008cd25  mov     rbx, rcx
0x18008cd28  mov     rcx, [rbp+160h+arg_40]
0x18008cd2f  mov     edi, r9d
0x18008cd32  mov     [rbp+160h+var_190], r8
0x18008cd36  mov     r15d, r9d
0x18008cd39  mov     [rbp+160h+var_198], rdx
0x18008cd3d  mov     [rdx], r9b
0x18008cd40  xor     edx, edx; unsigned __int16
0x18008cd42  mov     [r8], r9b
0x18008cd45  xor     r8d, r8d; unsigned __int16
0x18008cd48  mov     [r13+0], r9b
0x18008cd4c  mov     [r14], r9b
0x18008cd4f  mov     [rax], r9b
0x18008cd52  mov     [rbx], r9b
0x18008cd55  mov     byte ptr [rcx], 1
0x18008cd58  mov     [rbp+160h+var_1A0], rcx
0x18008cd5c  lea     ecx, [rdi+0Ah]; unsigned __int16
0x18008cd5f  mov     [rsp+260h+Block], r9
0x18008cd64  mov     r9d, 383Ah; unsigned __int16
0x18008cd6a  mov     byte ptr [r12], 1
0x18008cd6f  mov     byte ptr [rsi], 1
0x18008cd72  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x18008cd77  test    al, al
0x18008cd79  jz      loc_18008DD08
0x18008cd7f  xor     edx, edx; hFile
0x18008cd81  mov     byte ptr [rbx], 1
0x18008cd84  mov     r8d, 800h; dwFlags
0x18008cd8a  lea     rcx, aUpdatepolicyDl; "updatepolicy.dll"
0x18008cd91  call    cs:__imp_LoadLibraryExW
0x18008cd97  mov     [rsp+260h+hModule], rax
0x18008cd9c  mov     r15, rax
0x18008cd9f  test    rax, rax
0x18008cda2  jnz     short loc_18008CE07
0x18008cda4  call    cs:__imp_GetLastError
0x18008cdaa  xor     esi, esi
0x18008cdac  mov     ebx, eax
0x18008cdae  test    eax, eax
0x18008cdb0  jle     short loc_18008CDBB
0x18008cdb2  movzx   ebx, ax
0x18008cdb5  or      ebx, 80070000h
0x18008cdbb  mov     eax, 80004005h
0x18008cdc0  test    ebx, ebx
0x18008cdc2  cmovns  ebx, eax
0x18008cdc5  call    cs:__imp_GetLastError
0x18008cdcb  mov     dword ptr [rsp+260h+var_230], eax; char *
0x18008cdcf  lea     r14, aWindowsCompatA_757; "Windows::Compat::Appraiser::Utilities::"...
0x18008cdd6  lea     rax, aErrorGettingUp_1; "Error getting updatepolicy.dll, swallow"...
0x18008cddd  mov     edx, 1ED0h; bool
0x18008cde2  mov     qword ptr [rsp+260h+var_238], rax; int
0x18008cde7  lea     r12, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x18008cdee  mov     r9, r14; char *
0x18008cdf1  mov     dword ptr [rsp+260h+var_240], ebx; char *
0x18008cdf5  mov     r8, r12; unsigned int
0x18008cdf8  mov     ecx, 1; this
0x18008cdfd  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18008ce02  jmp     loc_18008DD18
0x18008ce07  lea     rdx, aReadpolicywith; "ReadPolicyWithFallback"
0x18008ce0e  mov     rcx, rax; hModule
0x18008ce11  call    cs:__imp_GetProcAddress
0x18008ce17  mov     r15, rax
0x18008ce1a  test    rax, rax
0x18008ce1d  jnz     short loc_18008CE87
0x18008ce1f  call    cs:__imp_GetLastError
0x18008ce25  xor     esi, esi
0x18008ce27  mov     ebx, eax
0x18008ce29  test    eax, eax
0x18008ce2b  jle     short loc_18008CE36
0x18008ce2d  movzx   ebx, ax
0x18008ce30  or      ebx, 80070000h
0x18008ce36  mov     eax, 80004005h
0x18008ce3b  test    ebx, ebx
0x18008ce3d  cmovns  ebx, eax
0x18008ce40  call    cs:__imp_GetLastError
0x18008ce46  mov     dword ptr [rsp+260h+var_230], eax; char *
0x18008ce4a  lea     r14, aWindowsCompatA_757; "Windows::Compat::Appraiser::Utilities::"...
0x18008ce51  lea     rax, aErrorGettingRe; "Error getting ReadPolicyWithFallback, s"...
0x18008ce58  mov     edx, 1ED6h; bool
0x18008ce5d  mov     qword ptr [rsp+260h+var_238], rax; int
0x18008ce62  lea     r12, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x18008ce69  mov     r9, r14; char *
0x18008ce6c  mov     dword ptr [rsp+260h+var_240], ebx; char *
0x18008ce70  mov     r8, r12; unsigned int
0x18008ce73  mov     ecx, 1; this
0x18008ce78  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18008ce7d  mov     r15, [rsp+260h+hModule]
0x18008ce82  jmp     loc_18008DD18
0x18008ce87  mov     rcx, [rsp+260h+hModule]; hModule
0x18008ce8c  lea     rdx, aReleaseenterpr_0; "ReleaseEnterprisePolicyValue"
0x18008ce93  call    cs:__imp_GetProcAddress
0x18008ce99  mov     [rsp+260h+var_1F8], rax
0x18008ce9e  mov     rbx, rax
0x18008cea1  test    rax, rax
0x18008cea4  jnz     loc_18008D074
0x18008ceaa  mov     r9d, 3FABh; unsigned __int16
0x18008ceb0  lea     ecx, [rax+0Ah]; unsigned __int16
0x18008ceb3  xor     r8d, r8d; unsigned __int16
0x18008ceb6  xor     edx, edx; unsigned __int16
0x18008ceb8  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x18008cebd  test    al, al
0x18008cebf  jz      loc_18008D074
0x18008cec5  call    cs:__imp_GetLastError
0x18008cecb  mov     ebx, eax
0x18008cecd  test    eax, eax
0x18008cecf  jle     short loc_18008CEDA
0x18008ced1  movzx   ebx, ax
0x18008ced4  or      ebx, 80070000h
0x18008ceda  test    ebx, ebx
0x18008cedc  jns     loc_18008D042
0x18008cee2  lea     r9, aReleaseenterpr_1; "ReleaseEnterprisePolicyValue not exists"...
0x18008cee9  mov     dword ptr [rsp+260h+var_230], ebx; char *
0x18008ceed  mov     qword ptr [rsp+260h+var_238], r9; int
0x18008cef2  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x18008cef9  lea     r9, aWindowsCompatA_757; "Windows::Compat::Appraiser::Utilities::"...
0x18008cf00  mov     dword ptr [rsp+260h+var_240], ebx; char *
0x18008cf04  mov     edx, 1EDCh; bool
0x18008cf09  mov     ecx, 1; this
0x18008cf0e  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18008cf13  lea     rcx, [rbp+160h+var_170]; this
0x18008cf17  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x18008cf1c  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x18008cf23  lea     rcx, [rbp+160h+var_170]
0x18008cf27  test    rax, rax
0x18008cf2a  cmovnz  rcx, rax; this
0x18008cf2e  xor     edx, edx
0x18008cf30  lock xadd [rcx+88h], rdx; unsigned __int64
0x18008cf39  lea     r8, [rbp+160h+var_E0]; char *
0x18008cf40  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18008cf45  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, dil; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x18008cf4c  jz      short loc_18008CF5A
0x18008cf4e  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x18008cf55  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x18008cf5a  mov     rdi, cs:qword_1802C9628
0x18008cf61  mov     eax, [rdi]
0x18008cf63  cmp     eax, 5
0x18008cf66  jbe     loc_18008D06F
0x18008cf6c  mov     rcx, [rdi+18h]
0x18008cf70  mov     rdx, 200000000000h
0x18008cf7a  mov     rax, [rdi+10h]
0x18008cf7e  test    rdx, rax
0x18008cf81  jz      loc_18008D06F
0x18008cf87  mov     rax, rcx
0x18008cf8a  and     rax, rdx
0x18008cf8d  cmp     rax, rcx
0x18008cf90  jnz     loc_18008D06F
0x18008cf96  lea     rax, [rbp+160h+var_E0]
0x18008cf9d  mov     dword ptr [rsp+260h+var_200], ebx
0x18008cfa1  mov     [rbp+160h+var_1B0], rax
0x18008cfa5  lea     rcx, [rbp+160h+SystemTime]; lpSystemTime
0x18008cfa9  lea     rax, aWindowsCompatA_757; "Windows::Compat::Appraiser::Utilities::"...
0x18008cfb0  mov     [rsp+260h+var_1FC], 1EDCh
0x18008cfb8  mov     [rbp+160h+var_1D8], rax
0x18008cfbc  xorps   xmm0, xmm0
0x18008cfbf  lea     rax, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x18008cfc6  mov     [rbp+160h+var_1D0], rax
0x18008cfca  lea     rax, szValueBuf
0x18008cfd1  mov     [rbp+160h+var_1C8], rax
0x18008cfd5  movups  xmmword ptr [rbp+160h+SystemTime.wYear], xmm0
0x18008cfd9  call    cs:__imp_GetSystemTime
0x18008cfdf  movaps  xmm0, xmmword ptr [rbp+160h+SystemTime.wYear]
0x18008cfe3  lea     rax, [rbp+160h+var_180]
0x18008cfe7  mov     [rbp+160h+var_1E0], rax
0x18008cfeb  lea     rdx, word_1802A1A0E
0x18008cff2  lea     rax, [rbp+160h+var_1B0]
0x18008cff6  movdqa  [rbp+160h+var_180], xmm0
0x18008cffb  mov     [rsp+260h+var_210], rax
0x18008d000  mov     rcx, rdi
0x18008d003  lea     rax, [rsp+260h+var_200]
0x18008d008  mov     [rsp+260h+var_218], rax
0x18008d00d  lea     rax, [rbp+160h+var_1D8]
0x18008d011  mov     [rsp+260h+var_220], rax
0x18008d016  lea     rax, [rbp+160h+var_1D0]
0x18008d01a  mov     [rsp+260h+var_228], rax
0x18008d01f  lea     rax, [rsp+260h+var_1FC]
0x18008d024  mov     [rsp+260h+var_230], rax
0x18008d029  lea     rax, [rbp+160h+var_1C8]
0x18008d02d  mov     qword ptr [rsp+260h+var_238], rax
0x18008d032  lea     rax, [rbp+160h+var_1E0]
0x18008d036  mov     [rsp+260h+var_240], rax
0x18008d03b  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18008d040  jmp     short loc_18008D06F
0x18008d042  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18008d048  test    al, 1
0x18008d04a  jz      short loc_18008D06F
0x18008d04c  lea     r9, aReleaseenterpr_1; "ReleaseEnterprisePolicyValue not exists"...
0x18008d053  mov     dword ptr [rsp+260h+var_240], ebx
0x18008d057  lea     r8, aWindowsCompatA_757; "Windows::Compat::Appraiser::Utilities::"...
0x18008d05e  mov     ecx, 1EDCh; unsigned int
0x18008d063  lea     rdx, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x18008d06a  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18008d06f  mov     rbx, [rsp+260h+var_1F8]
0x18008d074  lea     rdx, [rsp+260h+Block]
0x18008d079  mov     ecx, 20h ; ' '
0x18008d07e  mov     rax, r15
0x18008d081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d086  mov     edi, eax
0x18008d088  test    eax, eax
0x18008d08a  jns     loc_18008D1F8
0x18008d090  lea     rcx, aErrorCalculati_1; "Error calculating WUfB, swallowing: [0x"...
0x18008d097  mov     dword ptr [rsp+260h+var_230], eax; char *
0x18008d09b  mov     qword ptr [rsp+260h+var_238], rcx; int
0x18008d0a0  lea     r14, aWindowsCompatA_757; "Windows::Compat::Appraiser::Utilities::"...
0x18008d0a7  lea     r12, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x18008d0ae  mov     dword ptr [rsp+260h+var_240], eax; char *
0x18008d0b2  mov     r15d, 1EEDh
0x18008d0b8  mov     ecx, 1; this
0x18008d0bd  mov     r9, r14; char *
0x18008d0c0  mov     r8, r12; unsigned int
0x18008d0c3  mov     edx, r15d; bool
0x18008d0c6  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18008d0cb  lea     rcx, [rbp+160h+var_170]; this
0x18008d0cf  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x18008d0d4  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x18008d0db  lea     rcx, [rbp+160h+var_170]
0x18008d0df  xor     esi, esi
0x18008d0e1  test    rax, rax
0x18008d0e4  mov     edx, esi
0x18008d0e6  cmovnz  rcx, rax; this
0x18008d0ea  lock xadd [rcx+88h], rdx; unsigned __int64
0x18008d0f3  lea     r8, [rbp+160h+var_E0]; char *
0x18008d0fa  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18008d0ff  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, sil; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x18008d106  jz      short loc_18008D114
0x18008d108  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x18008d10f  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x18008d114  mov     rbx, cs:qword_1802C9628
0x18008d11b  mov     r13, 200000000000h
0x18008d125  mov     eax, [rbx]
0x18008d127  cmp     eax, 5
0x18008d12a  jbe     loc_18008D1E9
0x18008d130  mov     rcx, [rbx+18h]
0x18008d134  mov     rax, [rbx+10h]
0x18008d138  test    r13, rax
0x18008d13b  jz      loc_18008D1E9
0x18008d141  mov     rax, rcx
0x18008d144  and     rax, r13
0x18008d147  cmp     rax, rcx
0x18008d14a  jnz     loc_18008D1E9
0x18008d150  lea     rax, [rbp+160h+var_E0]
0x18008d157  mov     [rsp+260h+var_1FC], edi
0x18008d15b  mov     [rbp+160h+var_1E0], rax
0x18008d15f  lea     rcx, [rbp+160h+SystemTime]; lpSystemTime
0x18008d163  lea     rax, szValueBuf
0x18008d16a  mov     [rbp+160h+var_1C8], r14
0x18008d16e  xorps   xmm0, xmm0
0x18008d171  mov     [rbp+160h+var_1D8], rax
0x18008d175  mov     [rbp+160h+var_1D0], r12
0x18008d179  mov     dword ptr [rsp+260h+var_200], r15d
0x18008d17e  movups  xmmword ptr [rbp+160h+SystemTime.wYear], xmm0
0x18008d182  call    cs:__imp_GetSystemTime
0x18008d188  lea     rdx, dword_1802A1AD4
0x18008d18f  lea     rax, [rbp+160h+var_180]
0x18008d193  mov     [rbp+160h+var_1B0], rax
0x18008d197  lea     rax, [rbp+160h+var_1E0]
0x18008d19b  mov     [rsp+260h+var_210], rax
0x18008d1a0  lea     rax, [rsp+260h+var_1FC]
0x18008d1a5  mov     [rsp+260h+var_218], rax
0x18008d1aa  lea     rax, [rbp+160h+var_1C8]
0x18008d1ae  mov     [rsp+260h+var_220], rax
0x18008d1b3  lea     rax, [rbp+160h+var_1D0]
0x18008d1b7  mov     [rsp+260h+var_228], rax
0x18008d1bc  lea     rax, [rsp+260h+var_200]
0x18008d1c1  mov     [rsp+260h+var_230], rax
0x18008d1c6  lea     rax, [rbp+160h+var_1D8]
0x18008d1ca  mov     qword ptr [rsp+260h+var_238], rax
0x18008d1cf  lea     rax, [rbp+160h+var_1B0]
0x18008d1d3  movaps  xmm0, xmmword ptr [rbp+160h+SystemTime.wYear]
0x18008d1d7  mov     rcx, rbx
0x18008d1da  movdqa  [rbp+160h+var_180], xmm0
0x18008d1df  mov     [rsp+260h+var_240], rax
0x18008d1e4  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18008d1e9  mov     rdi, [rsp+260h+var_1F8]
0x18008d1ee  mov     r15, [rsp+260h+hModule]
0x18008d1f3  jmp     loc_18008DD22
0x18008d1f8  mov     rax, [rsp+260h+Block]
0x18008d1fd  cmp     dword ptr [rax+4], 1
0x18008d201  jnz     loc_18008D324
0x18008d207  cmp     word ptr [rax+10h], 3
0x18008d20c  jz      loc_18008D317
  ... truncated ...
```
