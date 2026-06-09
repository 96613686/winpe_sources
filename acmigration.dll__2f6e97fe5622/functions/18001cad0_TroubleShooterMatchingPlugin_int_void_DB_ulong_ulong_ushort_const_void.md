# TroubleShooterMatchingPlugin(int *,void *,_DB *,ulong,ulong,ushort const *,void *)

- ea: `0x18001cad0`
- end: `0x18001dca6`
- name: `?TroubleShooterMatchingPlugin@@YAHPEAHPEAXPEAU_DB@@KKPEBG1@Z`
- size: `4566`
- prototype: `__int64 __fastcall(int *, void *, struct _DB *, unsigned int, unsigned __int16 *, STRSAFE_LPCWSTR pszSrc, void *)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x18000a51c`
- `0x18000b720`
- `0x18000bbbc`
- `0x18000c190`
- `0x18000e504`
- `0x1800118f4`
- `0x18001cad0`
- `0x18001dcac`
- `0x18003f0b0`
- `0x18003fa7c`
- `0x1800514a8`
- `0x1800543c0`
- `0x180065120`
- `0x180065150`
- `0x18006a010`

## import_xrefs

- `KERNEL32!CreateThread` at `0x18001d700`
- `KERNEL32!CreateThread` at `0x18001d700`
- `KERNEL32!FreeLibrary` at `0x18001db1f`
- `KERNEL32!FreeLibrary` at `0x18001db1f`
- `KERNEL32!LocalFree` at `0x18001db2f`
- `KERNEL32!LocalFree` at `0x18001db2f`
- `KERNEL32!GetTickCount64` at `0x18001cb51`
- `KERNEL32!GetTickCount64` at `0x18001dbb6`
- `KERNEL32!GetTickCount64` at `0x18001cb51`
- `KERNEL32!GetTickCount64` at `0x18001dbb6`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001ccbe`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001ccbe`
- `KERNEL32!LoadLibraryExW` at `0x18001d5cf`
- `KERNEL32!LoadLibraryExW` at `0x18001d5cf`
- `KERNEL32!GetProcAddress` at `0x18001d623`
- `KERNEL32!GetProcAddress` at `0x18001d623`
- `KERNEL32!CloseHandle` at `0x18001d794`
- `KERNEL32!CloseHandle` at `0x18001d794`
- `KERNEL32!GetLastError` at `0x18001d5df`
- `KERNEL32!GetLastError` at `0x18001d62e`
- `KERNEL32!GetLastError` at `0x18001d713`
- `KERNEL32!GetLastError` at `0x18001d776`
- `KERNEL32!GetLastError` at `0x18001daae`
- `KERNEL32!GetLastError` at `0x18001d5df`
- `KERNEL32!GetLastError` at `0x18001d62e`
- `KERNEL32!GetLastError` at `0x18001d713`
- `KERNEL32!GetLastError` at `0x18001d776`
- `KERNEL32!GetLastError` at `0x18001daae`
- `KERNEL32!WaitForSingleObject` at `0x18001d758`
- `KERNEL32!WaitForSingleObject` at `0x18001d758`
- `ntdll!RtlGUIDFromString` at `0x18001d068`
- `ntdll!RtlGUIDFromString` at `0x18001d068`
- `ntdll!RtlInitUnicodeString` at `0x18001d052`
- `ntdll!RtlInitUnicodeString` at `0x18001d052`
- `ADVAPI32!RegGetValueW` at `0x18001d51e`
- `ADVAPI32!RegGetValueW` at `0x18001d834`
- `ADVAPI32!RegGetValueW` at `0x18001d9f7`
- `ADVAPI32!RegGetValueW` at `0x18001d51e`
- `ADVAPI32!RegGetValueW` at `0x18001d834`
- `ADVAPI32!RegGetValueW` at `0x18001d9f7`
- `ole32!CoInitializeEx` at `0x18001cc69`
- `ole32!CoInitializeEx` at `0x18001cc69`
- `ole32!CoUninitialize` at `0x18001cd7c`
- `ole32!CoUninitialize` at `0x18001dc23`
- `ole32!CoUninitialize` at `0x18001cd7c`
- `ole32!CoUninitialize` at `0x18001dc23`
- `SHLWAPI!StrToIntExW` at `0x18001d22b`
- `SHLWAPI!StrToIntExW` at `0x18001d2db`
- `SHLWAPI!StrToIntExW` at `0x18001d22b`
- `SHLWAPI!StrToIntExW` at `0x18001d2db`
- `SHELL32!CommandLineToArgvW` at `0x18001cdd8`
- `SHELL32!CommandLineToArgvW` at `0x18001cdd8`

## string_xrefs

- `0x18001d5c8`: `ntdll.dll`
- `0x18001db40`: `CommandLine is null/empty`
- `0x18001dac1`: `CommandLineToArgvW failed %d, %ws, numArgs=%d`
- `0x18001cc46`: `Enter TroubleShooterMatchingPlugin`
- `0x18001cc53`: `TroubleShooterMatchingPlugin`
- `0x18001daec`: `TroubleShooterMatchingPlugin`
- `0x18001db95`: `TroubleShooterMatchingPlugin`
- `0x18001cccc`: `TroubleShooterMatchingPlugin `
- `0x18001ce04`: `-PluginExists`
- `0x18001ce14`: `Plugin exists`
- `0x18001d0c2`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\TroubleShooter\`
- `0x18001d3af`: `Wrong command line, %ws`
- `0x18001d499`: `Failed to write MigGuid 0x%x`
- `0x18001d58a`: `Failed to write LastStartTime 0x%x`
- `0x18001d5e9`: `LoadLibraryExW failed %d`
- `0x18001d71d`: `Failed to create thread %d`
- `0x18001d826`: `LastCompletionTime`
- `0x18001d861`: `Async first time failed to read LastCompletionTime 0x%x`
- `0x18001d881`: `Failed to read LastCompletionTime 0x%x`
- `0x18001d8de`: `DeltaSec:%lld, StartTime:%llu, CompTime:%llu`
- `0x18001d90f`: `CompletionAfterRequest_Sec`
- `0x18001d92e`: `RequestAfterCompletion_Sec`
- `0x18001da58`: `Sync call, completion timestamp is before request, %d sec`
- `0x18001d97d`: `LastCompletionTime is too old, %f days`
- `0x18001da1a`: `FinalResult read failed, 0x%x`
- `0x18001dbc5`: `TroubleShooterPluginDuration_Ms`
- `0x18001dbdb`: `TroubleShooterPluginFinalHr`
- `0x18001dc01`: `TroubleShooterMatchingPlugin Matched = %d, duration = %d, hr = 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall TroubleShooterMatchingPlugin(
        AppCompatUtility *a1,
        void *a2,
        struct _DB *a3,
        __int64 a4,
        unsigned __int16 *a5,
        STRSAFE_LPCWSTR pszSrc,
        void *a7)
{
  AppCompatUtility *v7; // rbx
  STRSAFE_LPCWSTR v8; // rsi
  ULONGLONG TickCount64; // r14
  HRESULT v10; // eax
  int LastError; // edi
  unsigned int v12; // r9d
  void *v13; // rbx
  unsigned int v14; // r9d
  LPWSTR *v16; // rax
  int v17; // edi
  HLOCAL v18; // rcx
  unsigned __int64 v19; // rdx
  PCWSTR *v20; // rsi
  __int64 v21; // rdi
  PCWSTR *v22; // rax
  _WORD *v23; // r9
  __int64 v24; // rsi
  unsigned __int64 v25; // rdx
  void **v26; // rsi
  __int64 v27; // rdi
  const WCHAR *v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // r8
  void **v31; // rax
  int v32; // eax
  signed int i; // edi
  void *v34; // rsi
  unsigned __int64 v35; // rdx
  void **v36; // rsi
  __int64 v37; // rdi
  __int128 *v38; // rax
  HKEY v39; // r9
  const WCHAR *v40; // rax
  BYTE *v41; // rcx
  signed int v42; // eax
  const WCHAR *v43; // rdx
  LSTATUS ValueW; // eax
  HKEY v45; // r9
  signed int v46; // esi
  const WCHAR *v47; // rax
  signed int v48; // eax
  HMODULE Library; // rax
  DWORD v50; // eax
  FARPROC ProcAddress; // rax
  HMODULE v52; // rcx
  int v53; // edi
  PCWSTR *v54; // rax
  HANDLE v55; // rax
  DWORD v56; // eax
  const WCHAR *v57; // rdx
  LSTATUS v58; // eax
  __int64 v59; // rsi
  __int64 v60; // rdi
  unsigned int v61; // eax
  __int64 v62; // rdi
  const WCHAR *v63; // rdx
  LSTATUS v64; // eax
  __int64 v65; // rbx
  DWORD pdwTypea; // [rsp+20h] [rbp-7D8h]
  LPDWORD pdwType; // [rsp+20h] [rbp-7D8h]
  DWORD pdwTypeb; // [rsp+20h] [rbp-7D8h]
  DWORD pdwTypec; // [rsp+20h] [rbp-7D8h]
  void **pvData; // [rsp+28h] [rbp-7D0h]
  LPDWORD pcbData; // [rsp+30h] [rbp-7C8h]
  int pcbDataa; // [rsp+30h] [rbp-7C8h]
  DWORD v73; // [rsp+40h] [rbp-7B8h] BYREF
  STRSAFE_LPCWSTR v74; // [rsp+48h] [rbp-7B0h]
  HLOCAL hMem; // [rsp+50h] [rbp-7A8h]
  int pNumArgs; // [rsp+58h] [rbp-7A0h] BYREF
  char v77; // [rsp+5Dh] [rbp-79Bh]
  AppCompatUtility *v78; // [rsp+60h] [rbp-798h]
  int v79; // [rsp+68h] [rbp-790h] BYREF
  int piRet; // [rsp+6Ch] [rbp-78Ch] BYREF
  int v81; // [rsp+70h] [rbp-788h] BYREF
  HMODULE hLibModule; // [rsp+78h] [rbp-780h]
  __int64 v83; // [rsp+80h] [rbp-778h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+88h] [rbp-770h] BYREF
  __int64 v85; // [rsp+90h] [rbp-768h] BYREF
  AppCompatUtility *v86; // [rsp+98h] [rbp-760h]
  ULONGLONG v87; // [rsp+A0h] [rbp-758h]
  __int64 v88; // [rsp+A8h] [rbp-750h]
  PCWSTR SourceString[2]; // [rsp+B0h] [rbp-748h] BYREF
  unsigned __int64 v90; // [rsp+C0h] [rbp-738h]
  unsigned __int64 v91; // [rsp+C8h] [rbp-730h]
  LPCWSTR lpSubKey[2]; // [rsp+D0h] [rbp-728h] BYREF
  __m128i si128; // [rsp+E0h] [rbp-718h]
  void *v94[2]; // [rsp+F0h] [rbp-708h] BYREF
  DWORD *v95; // [rsp+100h] [rbp-6F8h]
  unsigned __int64 v96; // [rsp+108h] [rbp-6F0h]
  __int128 v97; // [rsp+110h] [rbp-6E8h] BYREF
  unsigned __int64 v98; // [rsp+120h] [rbp-6D8h]
  unsigned __int64 v99; // [rsp+128h] [rbp-6D0h]
  void *Src[2]; // [rsp+130h] [rbp-6C8h] BYREF
  void *v101[2]; // [rsp+150h] [rbp-6A8h] BYREF
  unsigned __int64 v102; // [rsp+160h] [rbp-698h]
  unsigned __int64 v103; // [rsp+168h] [rbp-690h]
  unsigned int Parameter; // [rsp+170h] [rbp-688h] BYREF
  __int128 v105; // [rsp+174h] [rbp-684h]
  GUID Guid; // [rsp+188h] [rbp-670h] BYREF
  int pszDest[392]; // [rsp+1A0h] [rbp-658h] BYREF

  v88 = -2;
  v7 = a1;
  v78 = a1;
  v86 = a1;
  v8 = pszSrc;
  v74 = pszSrc;
  pNumArgs = 0;
  v81 = 7;
  piRet = 610;
  memset_0(pszDest, 0, 0x618u);
  TickCount64 = GetTickCount64();
  v87 = TickCount64;
  Guid = 0;
  *(_OWORD *)SourceString = 0;
  v90 = 0;
  v91 = 7;
  LOWORD(SourceString[0]) = 0;
  *(_OWORD *)v101 = 0;
  v102 = 0;
  v103 = 7;
  LOWORD(v101[0]) = 0;
  v97 = 0;
  v98 = 0;
  v99 = 7;
  LOWORD(v97) = 0;
  *(_OWORD *)lpSubKey = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpSubKey[0]) = 0;
  *(_OWORD *)v94 = 0;
  v95 = 0;
  v96 = 7;
  LOWORD(v94[0]) = 0;
  Parameter = 0;
  v105 = 0;
  SystemTimeAsFileTime = 0;
  v83 = 0;
  v85 = 0;
  v79 = 0;
  *(_DWORD *)v7 = 0;
  AslLogCallPrintf(3, "TroubleShooterMatchingPlugin", 307, "Enter TroubleShooterMatchingPlugin");
  v10 = CoInitializeEx(0, 0);
  LastError = v10;
  v73 = v10;
  v77 = 1;
  if ( v10 < 0 )
  {
    AslLogCallPrintf(1, "TroubleShooterMatchingPlugin", 316, "CoInitializeEx failed 0x%x", v10);
LABEL_159:
    v74 = (STRSAFE_LPCWSTR)TickCount64;
LABEL_160:
    if ( v98 )
      *(_DWORD *)v7 = 1;
    goto LABEL_167;
  }
  if ( !pszSrc || !*pszSrc )
  {
    AslLogCallPrintf(1, "TroubleShooterMatchingPlugin", 322, "CommandLine is null/empty");
    LastError = -2147024809;
    v73 = -2147024809;
    goto LABEL_159;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v13 = (void *)SystemTimeAsFileTime;
  LastError = StringCchCatW((STRSAFE_LPWSTR)pszDest, 0x30Cu, L"TroubleShooterMatchingPlugin ");
  v73 = LastError;
  if ( LastError < 0 )
  {
    AslLogCallPrintf(1, "TroubleShooterMatchingPlugin", 334, "StringCchCatW failed.");
LABEL_7:
    v7 = v78;
    goto LABEL_159;
  }
  hMem = 0;
  hLibModule = 0;
  LastError = StringCchCatW((STRSAFE_LPWSTR)pszDest, 0x30Cu, pszSrc);
  v73 = LastError;
  if ( LastError < 0 )
  {
    AslLogCallPrintf(1, "TroubleShooterMatchingPlugin", 341, "StringCchCatW failed; %ws", pszSrc);
    goto LABEL_7;
  }
  if ( (unsigned int)AppCompatUtility::CheckCacheMatchingPlugin(
                       v78,
                       pszDest,
                       (const unsigned __int16 *)(unsigned int)a5,
                       v14) )
  {
    v77 = 0;
    CoUninitialize();
    std::wstring::~wstring(v94);
    std::wstring::~wstring(lpSubKey);
    std::wstring::~wstring(&v97);
    std::wstring::~wstring(v101);
    std::wstring::~wstring(SourceString);
    return 1;
  }
  v16 = CommandLineToArgvW(pszSrc, &pNumArgs);
  hMem = v16;
  v17 = pNumArgs;
  if ( !v16 || pNumArgs < 1 )
  {
    pcbDataa = pNumArgs;
    pdwTypec = GetLastError();
    AslLogCallPrintf(
      1,
      "TroubleShooterMatchingPlugin",
      361,
      "CommandLineToArgvW failed %d, %ws, numArgs=%d",
      pdwTypec,
      pszSrc,
      pcbDataa);
    LastError = -2147024809;
    v73 = -2147024809;
    v74 = (STRSAFE_LPCWSTR)TickCount64;
    goto LABEL_154;
  }
  Src[0] = *v16;
  if ( wcscmp_0(L"-PluginExists", (const wchar_t *)Src[0]) )
  {
    if ( v17 < 3 )
    {
      AslLogCallPrintf(1, "TroubleShooterMatchingPlugin", 376, "Num of arguments too few, %ws, numArgs=%d", pszSrc, v17);
      LastError = -2147024809;
      v73 = -2147024809;
      v74 = (STRSAFE_LPCWSTR)TickCount64;
      v18 = hMem;
      goto LABEL_155;
    }
    v19 = -1;
    do
      ++v19;
    while ( *((_WORD *)Src[0] + v19) );
    if ( v19 > v91 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(SourceString);
    }
    else
    {
      v20 = SourceString;
      if ( v91 > 7 )
        v20 = (PCWSTR *)SourceString[0];
      v90 = v19;
      v21 = 2 * v19;
      memmove_0(v20, Src[0], 2 * v19);
      *(_WORD *)((char *)v20 + v21) = 0;
      v8 = v74;
    }
    v22 = SourceString;
    if ( v91 > 7 )
      v22 = (PCWSTR *)SourceString[0];
    AslLogCallPrintf(3, "TroubleShooterMatchingPlugin", 382, "MigGuid=%ws", v22);
    if ( wcscmp_0(L"-Name", *((const wchar_t **)hMem + 1)) )
    {
      AslLogCallPrintf(1, "TroubleShooterMatchingPlugin", 386, "Missing -Name switch, %ws", v8);
      LastError = -2147024809;
      v73 = -2147024809;
      v74 = (STRSAFE_LPCWSTR)TickCount64;
      v18 = hMem;
      goto LABEL_155;
    }
    v23 = (_WORD *)*((_QWORD *)hMem + 2);
    v24 = -1;
    v25 = -1;
    do
      ++v25;
    while ( v23[v25] );
    if ( v25 > v96 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v94);
    }
    else
    {
      v26 = v94;
      if ( v96 > 7 )
        v26 = (void **)v94[0];
      v95 = (DWORD *)v25;
      v27 = 2 * v25;
      memmove_0(v26, v23, 2 * v25);
      *(_WORD *)((char *)v26 + v27) = 0;
      v24 = -1;
    }
    if ( !v90 )
    {
      AslLogCallPrintf(1, "TroubleShooterMatchingPlugin", 397, "Empty MigGuidStr.");
      LastError = -2147024809;
      v73 = -2147024809;
      v74 = (STRSAFE_LPCWSTR)TickCount64;
      v18 = hMem;
      goto LABEL_155;
    }
    v28 = (const WCHAR *)SourceString;
    if ( v91 > 7 )
      v28 = SourceString[0];
    *(_OWORD *)Src = 0;
    RtlInitUnicodeString((PUNICODE_STRING)Src, v28);
    if ( RtlGUIDFromString((PUNICODE_STRING)Src, &Guid) < 0 )
    {
      AslLogCallPrintf(1, "TroubleShooterMatchingPlugin", 405, "GUIDFromString failed.");
      LastError = -2147024809;
      v73 = -2147024809;
      v74 = (STRSAFE_LPCWSTR)TickCount64;
      v18 = hMem;
      goto LABEL_155;
    }
    if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - (_QWORD)v95) < 0x4B )
      std::_Xlen_string();
    v31 = v94;
    if ( v96 > 7 )
      v31 = (void **)v94[0];
    pcbData = v95;
    pvData = v31;
    std::wstring::wstring(
      Src,
      v29,
      v30,
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\TroubleShooter\\");
    std::wstring::operator=(lpSubKey, Src);
    std::wstring::~wstring(Src);
    Parameter = Guid.Data1;
    *(_QWORD *)&v105 = *(_QWORD *)&Guid.Data2;
    *((_QWORD *)&v105 + 1) = *(unsigned int *)&Guid.Data4[4] | 0x100000000LL;
    v32 = pNumArgs;
    if ( pNumArgs > 3 )
    {
      for ( i = 3; ; ++i )
      {
        v73 = i;
        if ( i >= v32 )
        {
          v24 = -1;
          goto LABEL_78;
        }
        v34 = (void *)*((_QWORD *)hMem + i);
        Src[0] = v34;
        if ( !wcscmp_0(L"-Sync", (const wchar_t *)v34) )
          break;
        if ( !wcscmp_0(L"-Timeout", (const wchar_t *)v34) )
        {
          if ( pNumArgs < i + 2 )
          {
            AslLogCallPrintf(1, "TroubleShooterMatchingPlugin", 427, "Wrong argument format", 75, pvData, pcbData);
            LastError = -2147024809;
            v73 = -2147024809;
            v74 = (STRSAFE_LPCWSTR)TickCount64;
            v18 = hMem;
            goto LABEL_155;
          }
          if ( !StrToIntExW(*((PCWSTR *)hMem + i + 1), 0, &piRet) )
          {
            AslLogCallPrintf(
              1,
              "TroubleShooterMatchingPlugin",
              433,
              "Convert TimeoutValueSec integer failed, %ws",
              v74,
              pvData,
              pcbData);
            LastError = -2147024809;
            v73 = -2147024809;
            v74 = (STRSAFE_LPCWSTR)TickCount64;
            v18 = hMem;
            goto LABEL_155;
          }
LABEL_60:
          ++i;
          goto LABEL_75;
        }
        if ( !wcscmp_0(L"-FreshDays", (const wchar_t *)v34) )
        {
          if ( pNumArgs < i + 2 )
          {
            AslLogCallPrintf(1, "TroubleShooterMatchingPlugin", 444, "Wrong argument format", 75, pvData, pcbData);
            LastError = -2147024809;
            v73 = -2147024809;
            v74 = (STRSAFE_LPCWSTR)TickCount64;
            v18 = hMem;
            goto LABEL_155;
          }
          if ( !StrToIntExW(*((PCWSTR *)hMem + i + 1), 0, &v81) )
          {
            AslLogCallPrintf(
              1,
              "TroubleShooterMatchingPlugin",
              450,
              "Convert FreshDays integer failed, %ws",
              v74,
              pvData,
              pcbData);
            LastError = -2147024809;
            v73 = -2147024809;
            v74 = (STRSAFE_LPCWSTR)TickCount64;
            v18 = hMem;
            goto LABEL_155;
          }
          goto LABEL_60;
        }
        if ( wcscmp_0(L"-ReturnTrueOnFailure", (const wchar_t *)v34) )
        {
          AslLogCallPrintf(1, "TroubleShooterMatchingPlugin", 463, "Wrong command line, %ws", v34, pvData, pcbData);
          LastError = -2147024809;
          v73 = -2147024809;
          v74 = (STRSAFE_LPCWSTR)TickCount64;
          v18 = hMem;
          goto LABEL_155;
        }
        v35 = -1;
        do
          ++v35;
        while ( *((_WORD *)v34 + v35) );
        if ( v35 <= v99 )
        {
          v36 = (void **)&v97;
          if ( v99 > 7 )
            v36 = (void **)v97;
          v98 = v35;
LABEL_73:
          v37 = 2 * v35;
          memmove_0(v36, Src[0], 2 * v35);
          *(_WORD *)((char *)v36 + v37) = 0;
          i = v73;
          goto LABEL_75;
        }
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(&v97);
LABEL_75:
        v32 = pNumArgs;
      }
      v35 = -1;
      do
        ++v35;
      while ( *((_WORD *)v34 + v35) );
      if ( v35 > v103 )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v101);
        goto LABEL_75;
      }
      v36 = v101;
      if ( v103 > 7 )
        v36 = (void **)v101[0];
      v102 = v35;
      goto LABEL_73;
    }
LABEL_78:
    v38 = &v97;
    if ( v99 > 7 )
      v38 = (__int128 *)v97;
    LODWORD(pvData) = piRet;
    AslLogCallPrintf(
      3,
      "TroubleShooterMatchingPlugin",
      469,
      "Freshdays:%d, Timeout:%d, RetOnF:%ws, ",
      (unsigned int)v81,
      pvData,
      v38);
    v40 = (const WCHAR *)lpSubKey;
    if ( si128.m128i_i64[1] > 7uLL )
      v40 = lpSubKey[0];
    v41 = (BYTE *)SourceString;
    if ( v91 > 7 )
      v41 = (BYTE *)SourceString[0];
    do
      ++v24;
    while ( *(_WORD *)&v41[2 * v24] );
    v42 = Windows::Compat::Shared::Registry::WriteValue(v41, 2 * (int)v24 + 2, 1u, v39, v40, L"MigGuid");
    LastError = v42;
    v73 = v42;
    if ( v42 < 0 )
    {
      AslLogCallPrintf(1, "TroubleShooterMatchingPlugin", 474, "Failed to write MigGuid 0x%x", v42);
      v74 = (STRSAFE_LPCWSTR)TickCount64;
      v18 = hMem;
      goto LABEL_155;
    }
    v43 = (const WCHAR *)lpSubKey;
    if ( si128.m128i_i64[1] > 7uLL )
      v43 = lpSubKey[0];
    v85 = 0;
    v73 = 8;
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v43, L"LastRequestTime", 0x20000040u, 0, &v85, &v73);
    v46 = ValueW;
    if ( ValueW )
    {
      if ( ValueW > 0 )
        v46 = (unsigned __int16)ValueW | 0x80070000;
    }
    else
    {
      v46 = 0;
    }
    v47 = (const WCHAR *)lpSubKey;
    if ( si128.m128i_i64[1] > 7uLL )
      v47 = lpSubKey[0];
    Src[0] = v13;
    v48 = Windows::Compat::Shared::Registry::WriteValue((BYTE *)Src, 8u, 0xBu, v45, v47, L"LastRequestTime");
    LastError = v48;
    v73 = v48;
    if ( v48 < 0 )
    {
      AslLogCallPrintf(1, "TroubleShooterMatchingPlugin", 487, "Failed to write LastStartTime 0x%x", v48);
      v74 = (STRSAFE_LPCWSTR)TickCount64;
      v18 = hMem;
      goto LABEL_155;
    }
    if ( v102 )
    {
      v55 = CreateThread(0, 0, SyncCallThread, &Parameter, 0, 0);
      Src[0] = v55;
      if ( !v55 )
      {
        pdwTypeb = GetLastError();
        AslLogCallPrintf(1, "TroubleShooterMatchingPlugin", 530, "Failed to create thread %d", pdwTypeb);
        LastError = -2147418113;
        v73 = -2147418113;
        v74 = (STRSAFE_LPCWSTR)TickCount64;
        v18 = hMem;
        goto LABEL_155;
      }
      v56 = WaitForSingleObject(v55, 1000 * piRet);
      switch ( v56 )
      {
        case 0x80u:
          LastError = 735;
          break;
        case 0x102u:
          LastError = 1460;
          break;
        case 0xFFFFFFFF:
          LastError = GetLastError();
          break;
        default:
          LastError = 0;
          break;
      }
      CloseHandle(Src[0]);
      if ( LastError )
      {
        AslLogCallPrintf(1, "TroubleShooterMatchingPlugin", 560, "Wait failed %d", LastError);
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v73 = LastError;
        v74 = (STRSAFE_LPCWSTR)TickCount64;
        v18 = hMem;
        goto LABEL_155;
      }
    }
    else
    {
      Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
      hLibModule = Library;
      if ( !Library )
      {
        v50 = GetLastError();
        AslLogCallPrintf(1, "TroubleShooterMatchingPlugin", 496, "LoadLibraryExW failed %d", v50);
        LastError = -2147418113;
        v73 = -2147418113;
        v74 = (STRSAFE_LPCWSTR)TickCount64;
        v18 = hMem;
        goto LABEL_155;
      }
      ProcAddress = GetProcAddress(Library, "RtlPublishWnfStateData");
      if ( !ProcAddress )
      {
        pdwTypea = GetLastError();
        AslLogCallPrintf(1, "TroubleShooterMatchingPlugin", 504, "Get RtlPublishWnfStateData failed %d", pdwTypea);
        LastError = -2147418113;
        v73 = -2147418113;
        v74 = (STRSAFE_LPCWSTR)TickCount64;
        v52 = hLibModule;
LABEL_153:
        FreeLibrary(v52);
LABEL_154:
        v18 = hMem;
        if ( !hMem )
          goto LABEL_156;
        goto LABEL_155;
      }
      v53 = ((__int64 (__fastcall *)(__int64, _QWORD, unsigned int *, __int64, _QWORD))ProcAddress)(
              WNF_RTSC_INVOKE_TROUBLESHOOTER,
              0,
              &Parameter,
              20,
              0);
      if ( v53 < 0 )
      {
        v54 = SourceString;
        if ( v91 > 7 )
          v54 = (PCWSTR *)SourceString[0];
        LODWORD(pdwType) = v53;
        AslLogCallPrintf(
          1,
          "TroubleShooterMatchingPlugin",
          515,
          "RtlPublishWnfStateData failed, 0x%x, %ws",
          pdwType,
          v54);
        LastError = v53 | 0x10000000;
        v73 = LastError;
        v74 = (STRSAFE_LPCWSTR)TickCount64;
        v52 = hLibModule;
        goto LABEL_153;
      }
    }
    v57 = (const WCHAR *)lpSubKey;
    if ( si128.m128i_i64[1] > 7uLL )
      v57 = lpSubKey[0];
    v83 = 0;
    v73 = 8;
    v58 = RegGetValueW(HKEY_LOCAL_MACHINE, v57, L"LastCompletionTime", 0x20000040u, 0, &v83, &v73);
    LastError = v58;
    if ( !v58 )
      goto LABEL_130;
    if ( v58 > 0 )
      LastError = (unsigned __int16)v58 | 0x80070000;
    if ( LastError < 0 )
    {
      if ( v46 >= 0 || v102 )
        AslLogCallPrintf(1, "TroubleShooterMatchingPlugin", 579, "Failed to read LastCompletionTime 0x%x", LastError);
      else
        AslLogCallPrintf(
          3,
          "TroubleShooterMatchingPlugin",
          575,
          "Async first time failed to read LastCompletionTime 0x%x",
          LastError);
      v73 = LastError;
    }
    else
    {
LABEL_130:
      v59 = (__int64)v13 - v83;
      v60 = ((__int64)v13 - v83) / 10000000;
      AslLogCallPrintf(
        3,
        "TroubleShooterMatchingPlugin",
        591,
        "DeltaSec:%lld, StartTime:%llu, CompTime:%llu",
        v60,
        v13,
        v83);
      v61 = 0x7FFFFFFF;
      if ( v59 > 0 )
      {
        if ( v60 > 0x7FFFFFFF )
          LODWORD(v60) = 0x7FFFFFFF;
        AslTelemetryTrackMetric(P, "RequestAfterCompletion_Sec", (unsigned int)v60);
        if ( v102 )
        {
          AslLogCallPrintf(
            1,
            "TroubleShooterMatchingPlugin",
            606,
            "Sync call, completion timestamp is before request, %d sec",
            v60);
          LastError = -2147023893;
          v73 = -2147023893;
          goto LABEL_152;
        }
        if ( (double)(int)v60 / 3600.0 / 24.0 > (double)v81 )
        {
          AslLogCallPrintf(
            1,
            "TroubleShooterMatchingPlugin",
            613,
            "LastCompletionTime is too old, %f days",
            (double)(int)v60 / 3600.0 / 24.0);
          LastError = -2147020495;
          v73 = -2147020495;
          goto LABEL_152;
        }
      }
      else
      {
        v62 = -v60;
        if ( v62 <= 0x7FFFFFFF )
          v61 = v62;
        AslTelemetryTrackMetric(P, "CompletionAfterRequest_Sec", v61);
      }
      v63 = (const WCHAR *)lpSubKey;
      if ( si128.m128i_i64[1] > 7uLL )
        v63 = lpSubKey[0];
      v79 = 0;
      v73 = 4;
      v64 = RegGetValueW(HKEY_LOCAL_MACHINE, v63, L"MatchResult", 0x20000010u, 0, &v79, &v73);
      LastError = v64;
      if ( !v64 )
        goto LABEL_146;
      if ( v64 > 0 )
        LastError = (unsigned __int16)v64 | 0x80070000;
      if ( LastError < 0 )
      {
        v73 = LastError;
        AslLogCallPrintf(1, "TroubleShooterMatchingPlugin", 626, "FinalResult read failed, 0x%x", LastError);
      }
      else
      {
LABEL_146:
        if ( v79 == 1 )
          *(_DWORD *)v78 = 1;
        LastError = 0;
        v73 = 0;
      }
    }
LABEL_152:
    v74 = (STRSAFE_LPCWSTR)TickCount64;
    v52 = hLibModule;
    if ( !hLibModule )
      goto LABEL_154;
    goto LABEL_153;
  }
  AslLogCallPrintf(3, "TroubleShooterMatchingPlugin", 368, "Plugin exists");
  *(_DWORD *)v78 = 1;
  LastError = 0;
  v73 = 0;
  v74 = (STRSAFE_LPCWSTR)TickCount64;
  v18 = hMem;
LABEL_155:
  LocalFree(v18);
LABEL_156:
  if ( LastError < 0 )
  {
    v7 = v78;
    goto LABEL_160;
  }
LABEL_167:
  try
  {
    AppCompatUtility::AddCacheMatchingPlugin(
      (AppCompatUtility *)*(unsigned int *)v78,
      (int)pszDest,
      (const unsigned __int16 *)(unsigned int)a5,
      v12);
  }
  catch ( ... )
  {
    AslLogCallPrintf(1, "TroubleShooterMatchingPlugin", 671, "Unhandled exception");
    LastError = v73;
    LODWORD(TickCount64) = (_DWORD)v74;
    v78 = v86;
  }
  v65 = (unsigned int)GetTickCount64() - (unsigned int)TickCount64;
  AslTelemetryTrackMetric(P, "TroubleShooterPluginDuration_Ms", v65);
  AslTelemetryTrackMetric(P, "TroubleShooterPluginFinalHr", (unsigned int)LastError);
  AslLogCallPrintf(
    3,
    "TroubleShooterMatchingPlugin",
    678,
    "TroubleShooterMatchingPlugin Matched = %d, duration = %d, hr = 0x%x",
    *(_DWORD *)v78,
    v65,
    LastError);
  if ( v77 )
    CoUninitialize();
  std::wstring::~wstring(v94);
  std::wstring::~wstring(lpSubKey);
  std::wstring::~wstring(&v97);
  std::wstring::~wstring(v101);
  std::wstring::~wstring(SourceString);
  return 1;
}

```

## disassembly

```asm
0x18001cad0  mov     r11, rsp
0x18001cad3  push    rdi
0x18001cad4  push    r12
0x18001cad6  push    r13
0x18001cad8  push    r14
0x18001cada  push    r15
0x18001cadc  sub     rsp, 7D0h
0x18001cae3  mov     qword ptr [r11-750h], 0FFFFFFFFFFFFFFFEh
0x18001caee  mov     [r11+10h], rbx
0x18001caf2  mov     [r11+18h], rsi
0x18001caf6  mov     rax, cs:__security_cookie
0x18001cafd  xor     rax, rsp
0x18001cb00  mov     [rsp+7F8h+var_38], rax
0x18001cb08  mov     rbx, rcx
0x18001cb0b  mov     [rsp+7F8h+var_798], rcx
0x18001cb10  mov     [rsp+7F8h+var_760], rcx
0x18001cb18  mov     rsi, [rsp+7F8h+pszSrc]
0x18001cb20  mov     [rsp+7F8h+var_7B0], rsi
0x18001cb25  xor     r15d, r15d
0x18001cb28  mov     [rsp+7F8h+pNumArgs], r15d
0x18001cb2d  lea     edi, [r15+7]
0x18001cb31  mov     [rsp+7F8h+var_788], edi
0x18001cb35  mov     [rsp+7F8h+piRet], 262h
0x18001cb3d  xor     edx, edx; Val
0x18001cb3f  mov     r8d, 618h; Size
0x18001cb45  lea     rcx, [r11-658h]; void *
0x18001cb4c  call    memset_0
0x18001cb51  call    cs:__imp_GetTickCount64
0x18001cb57  mov     r14, rax
0x18001cb5a  mov     [rsp+7F8h+var_758], rax
0x18001cb62  xorps   xmm0, xmm0
0x18001cb65  movups  xmmword ptr [rsp+7F8h+Guid.Data1], xmm0
0x18001cb6d  xorps   xmm1, xmm1
0x18001cb70  movups  xmmword ptr [rsp+7F8h+SourceString], xmm1
0x18001cb78  mov     [rsp+7F8h+var_738], r15
0x18001cb80  mov     [rsp+7F8h+var_730], rdi
0x18001cb88  mov     word ptr [rsp+7F8h+SourceString], r15w
0x18001cb91  movups  xmmword ptr [rsp+7F8h+var_6A8], xmm0
0x18001cb99  mov     [rsp+7F8h+var_698], r15
0x18001cba1  mov     [rsp+7F8h+var_690], rdi
0x18001cba9  mov     word ptr [rsp+7F8h+var_6A8], r15w
0x18001cbb2  movups  [rsp+7F8h+var_6E8], xmm0
0x18001cbba  mov     [rsp+7F8h+var_6D8], r15
0x18001cbc2  mov     [rsp+7F8h+var_6D0], rdi
0x18001cbca  mov     word ptr [rsp+7F8h+var_6E8], r15w
0x18001cbd3  movups  xmmword ptr [rsp+7F8h+lpSubKey], xmm0
0x18001cbdb  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001cbe3  movdqu  [rsp+7F8h+var_718], xmm1
0x18001cbec  mov     word ptr [rsp+7F8h+lpSubKey], r15w
0x18001cbf5  movups  xmmword ptr [rsp+7F8h+var_708], xmm0
0x18001cbfd  mov     [rsp+7F8h+var_6F8], r15
0x18001cc05  mov     [rsp+7F8h+var_6F0], rdi
0x18001cc0d  mov     word ptr [rsp+7F8h+var_708], r15w
0x18001cc16  mov     [rsp+7F8h+Parameter], r15d
0x18001cc1e  movups  [rsp+7F8h+var_684], xmm0
0x18001cc26  mov     qword ptr [rsp+7F8h+SystemTimeAsFileTime.dwLowDateTime], r15
0x18001cc2e  mov     [rsp+7F8h+var_778], r15
0x18001cc36  mov     [rsp+7F8h+var_768], r15
0x18001cc3e  mov     [rsp+7F8h+var_790], r15d
0x18001cc43  mov     [rbx], r15d
0x18001cc46  lea     r9, aEnterTroublesh; "Enter TroubleShooterMatchingPlugin"
0x18001cc4d  mov     r8d, 133h
0x18001cc53  lea     r13, aTroubleshooter_2; "TroubleShooterMatchingPlugin"
0x18001cc5a  mov     rdx, r13
0x18001cc5d  lea     ecx, [rdi-4]
0x18001cc60  call    AslLogCallPrintf
0x18001cc65  xor     edx, edx; dwCoInit
0x18001cc67  xor     ecx, ecx; pvReserved
0x18001cc69  call    cs:__imp_CoInitializeEx
0x18001cc6f  mov     edi, eax
0x18001cc71  mov     [rsp+7F8h+var_7B8], eax
0x18001cc75  lea     r12d, [r15+1]
0x18001cc79  mov     [rsp+7F8h+var_79B], r12b
0x18001cc7e  test    eax, eax
0x18001cc80  jns     short loc_18001CCA3
0x18001cc82  mov     dword ptr [rsp+7F8h+pdwType], eax
0x18001cc86  lea     r9, aCoinitializeex; "CoInitializeEx failed 0x%x"
0x18001cc8d  mov     r8d, 13Ch
0x18001cc93  mov     rdx, r13
0x18001cc96  mov     ecx, r12d
0x18001cc99  call    AslLogCallPrintf
0x18001cc9e  jmp     loc_18001DB61
0x18001cca3  test    rsi, rsi
0x18001cca6  jz      loc_18001DB40
0x18001ccac  cmp     r15w, [rsi]
0x18001ccb0  jz      loc_18001DB40
0x18001ccb6  lea     rcx, [rsp+7F8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001ccbe  call    cs:__imp_GetSystemTimeAsFileTime
0x18001ccc4  mov     rbx, qword ptr [rsp+7F8h+SystemTimeAsFileTime.dwLowDateTime]
0x18001cccc  lea     r8, aTroubleshooter; "TroubleShooterMatchingPlugin "
0x18001ccd3  mov     edx, 30Ch; cchDest
0x18001ccd8  lea     rcx, [rsp+7F8h+pszDest]; pszDest
0x18001cce0  call    StringCchCatW
0x18001cce5  mov     edi, eax
0x18001cce7  mov     [rsp+7F8h+var_7B8], eax
0x18001cceb  test    eax, eax
0x18001cced  jns     short loc_18001CD11
0x18001ccef  lea     r9, aStringcchcatwF_0; "StringCchCatW failed."
0x18001ccf6  mov     r8d, 14Eh
0x18001ccfc  mov     rdx, r13
0x18001ccff  mov     ecx, r12d
0x18001cd02  call    AslLogCallPrintf
0x18001cd07  mov     rbx, [rsp+7F8h+var_798]
0x18001cd0c  jmp     loc_18001DB61
0x18001cd11  mov     [rsp+7F8h+hMem], r15
0x18001cd16  mov     [rsp+7F8h+hLibModule], r15
0x18001cd1b  mov     r8, rsi; pszSrc
0x18001cd1e  mov     edx, 30Ch; cchDest
0x18001cd23  lea     rcx, [rsp+7F8h+pszDest]; pszDest
0x18001cd2b  call    StringCchCatW
0x18001cd30  mov     edi, eax
0x18001cd32  mov     [rsp+7F8h+var_7B8], eax
0x18001cd36  test    eax, eax
0x18001cd38  jns     short loc_18001CD59
0x18001cd3a  mov     [rsp+7F8h+pdwType], rsi
0x18001cd3f  lea     r9, aStringcchcatwF; "StringCchCatW failed; %ws"
0x18001cd46  mov     r8d, 155h
0x18001cd4c  mov     rdx, r13
0x18001cd4f  mov     ecx, r12d
0x18001cd52  call    AslLogCallPrintf
0x18001cd57  jmp     short loc_18001CD07
0x18001cd59  mov     r8d, dword ptr [rsp+7F8h+arg_20]; unsigned __int16 *
0x18001cd61  lea     rdx, [rsp+7F8h+pszDest]; int *
0x18001cd69  mov     rcx, [rsp+7F8h+var_798]; this
0x18001cd6e  call    ?CheckCacheMatchingPlugin@AppCompatUtility@@YAHPEAHPEBGK@Z; AppCompatUtility::CheckCacheMatchingPlugin(int *,ushort const *,ulong)
0x18001cd73  test    eax, eax
0x18001cd75  jz      short loc_18001CDD0
0x18001cd77  mov     [rsp+7F8h+var_79B], r15b
0x18001cd7c  call    cs:__imp_CoUninitialize
0x18001cd82  nop
0x18001cd83  lea     rcx, [rsp+7F8h+var_708]; void *
0x18001cd8b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cd90  nop
0x18001cd91  lea     rcx, [rsp+7F8h+lpSubKey]; void *
0x18001cd99  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cd9e  nop
0x18001cd9f  lea     rcx, [rsp+7F8h+var_6E8]; void *
0x18001cda7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cdac  nop
0x18001cdad  lea     rcx, [rsp+7F8h+var_6A8]; void *
0x18001cdb5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cdba  nop
0x18001cdbb  lea     rcx, [rsp+7F8h+SourceString]; void *
0x18001cdc3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cdc8  mov     eax, r12d
0x18001cdcb  jmp     loc_18001DC72
0x18001cdd0  lea     rdx, [rsp+7F8h+pNumArgs]; pNumArgs
0x18001cdd5  mov     rcx, rsi; lpCmdLine
0x18001cdd8  call    cs:__imp_CommandLineToArgvW
0x18001cdde  mov     [rsp+7F8h+hMem], rax
0x18001cde3  mov     edi, [rsp+7F8h+pNumArgs]
0x18001cde7  test    rax, rax
0x18001cdea  jz      loc_18001DAAE
0x18001cdf0  cmp     edi, r12d
0x18001cdf3  jl      loc_18001DAAE
0x18001cdf9  mov     rdx, [rax]; String2
0x18001cdfc  mov     [rsp+7F8h+Src], rdx
0x18001ce04  lea     rcx, aPluginexists; "-PluginExists"
0x18001ce0b  call    wcscmp_0
0x18001ce10  test    eax, eax
0x18001ce12  jnz     short loc_18001CE4B
0x18001ce14  lea     r9, aPluginExists; "Plugin exists"
0x18001ce1b  mov     r8d, 170h
0x18001ce21  mov     rdx, r13
0x18001ce24  lea     ecx, [rax+3]
0x18001ce27  call    AslLogCallPrintf
0x18001ce2c  mov     rax, [rsp+7F8h+var_798]
0x18001ce31  mov     [rax], r12d
0x18001ce34  mov     edi, r15d
0x18001ce37  mov     [rsp+7F8h+var_7B8], r15d
0x18001ce3c  mov     [rsp+7F8h+var_7B0], r14
0x18001ce41  mov     rcx, [rsp+7F8h+hMem]
0x18001ce46  jmp     loc_18001DB2F
0x18001ce4b  cmp     edi, 3
0x18001ce4e  jge     short loc_18001CE89
0x18001ce50  mov     dword ptr [rsp+7F8h+pvData], edi
0x18001ce54  mov     [rsp+7F8h+pdwType], rsi
0x18001ce59  lea     r9, aNumOfArguments; "Num of arguments too few, %ws, numArgs="...
0x18001ce60  mov     r8d, 178h
0x18001ce66  mov     rdx, r13
0x18001ce69  mov     ecx, r12d
0x18001ce6c  call    AslLogCallPrintf
0x18001ce71  mov     edi, 80070057h
0x18001ce76  mov     [rsp+7F8h+var_7B8], edi
0x18001ce7a  mov     [rsp+7F8h+var_7B0], r14
0x18001ce7f  mov     rcx, [rsp+7F8h+hMem]
0x18001ce84  jmp     loc_18001DB2F
0x18001ce89  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001ce8d  mov     rax, [rsp+7F8h+Src]
0x18001ce95  inc     rdx
0x18001ce98  cmp     [rax+rdx*2], r15w
0x18001ce9d  jnz     short loc_18001CE95
0x18001ce9f  cmp     rdx, [rsp+7F8h+var_730]
0x18001cea7  ja      short loc_18001CEE9
0x18001cea9  lea     rsi, [rsp+7F8h+SourceString]
0x18001ceb1  cmp     [rsp+7F8h+var_730], 7
0x18001ceba  cmova   rsi, [rsp+7F8h+SourceString]
0x18001cec3  mov     [rsp+7F8h+var_738], rdx
0x18001cecb  lea     rdi, [rdx+rdx]
0x18001cecf  mov     r8, rdi; Size
0x18001ced2  mov     rdx, rax; Src
0x18001ced5  mov     rcx, rsi; void *
0x18001ced8  call    memmove_0
0x18001cedd  mov     [rdi+rsi], r15w
0x18001cee2  mov     rsi, [rsp+7F8h+var_7B0]
0x18001cee7  jmp     short loc_18001CEF9
0x18001cee9  mov     r9, rax
0x18001ceec  lea     rcx, [rsp+7F8h+SourceString]
0x18001cef4  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001cef9  lea     rax, [rsp+7F8h+SourceString]
0x18001cf01  cmp     [rsp+7F8h+var_730], 7
0x18001cf0a  cmova   rax, [rsp+7F8h+SourceString]
0x18001cf13  mov     [rsp+7F8h+pdwType], rax
0x18001cf18  lea     r9, aMigguidWs; "MigGuid=%ws"
0x18001cf1f  mov     r8d, 17Eh
0x18001cf25  mov     rdx, r13
0x18001cf28  mov     ecx, 3
0x18001cf2d  call    AslLogCallPrintf
0x18001cf32  mov     rdi, [rsp+7F8h+hMem]
0x18001cf37  mov     rdx, [rdi+8]; String2
0x18001cf3b  lea     rcx, aName; "-Name"
0x18001cf42  call    wcscmp_0
0x18001cf47  test    eax, eax
0x18001cf49  jz      short loc_18001CF80
0x18001cf4b  mov     [rsp+7F8h+pdwType], rsi
0x18001cf50  lea     r9, aMissingNameSwi; "Missing -Name switch, %ws"
0x18001cf57  mov     r8d, 182h
0x18001cf5d  mov     rdx, r13
0x18001cf60  mov     ecx, r12d
0x18001cf63  call    AslLogCallPrintf
0x18001cf68  mov     edi, 80070057h
0x18001cf6d  mov     [rsp+7F8h+var_7B8], edi
0x18001cf71  mov     [rsp+7F8h+var_7B0], r14
0x18001cf76  mov     rcx, [rsp+7F8h+hMem]
0x18001cf7b  jmp     loc_18001DB2F
0x18001cf80  mov     r9, [rdi+10h]
0x18001cf84  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001cf88  mov     rdx, rsi
0x18001cf8b  inc     rdx
0x18001cf8e  cmp     [r9+rdx*2], r15w
0x18001cf93  jnz     short loc_18001CF8B
0x18001cf95  cmp     rdx, [rsp+7F8h+var_6F0]
0x18001cf9d  ja      short loc_18001CFDE
0x18001cf9f  lea     rsi, [rsp+7F8h+var_708]
0x18001cfa7  cmp     [rsp+7F8h+var_6F0], 7
0x18001cfb0  cmova   rsi, [rsp+7F8h+var_708]
0x18001cfb9  mov     [rsp+7F8h+var_6F8], rdx
0x18001cfc1  lea     rdi, [rdx+rdx]
0x18001cfc5  mov     r8, rdi; Size
0x18001cfc8  mov     rdx, r9; Src
0x18001cfcb  mov     rcx, rsi; void *
0x18001cfce  call    memmove_0
0x18001cfd3  mov     [rdi+rsi], r15w
0x18001cfd8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001cfdc  jmp     short loc_18001CFEB
0x18001cfde  lea     rcx, [rsp+7F8h+var_708]
0x18001cfe6  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001cfeb  cmp     [rsp+7F8h+var_738], r15
0x18001cff3  jnz     short loc_18001D025
0x18001cff5  lea     r9, aEmptyMigguidst; "Empty MigGuidStr."
0x18001cffc  mov     r8d, 18Dh
0x18001d002  mov     rdx, r13
0x18001d005  mov     ecx, r12d
0x18001d008  call    AslLogCallPrintf
0x18001d00d  mov     edi, 80070057h
0x18001d012  mov     [rsp+7F8h+var_7B8], edi
0x18001d016  mov     [rsp+7F8h+var_7B0], r14
0x18001d01b  mov     rcx, [rsp+7F8h+hMem]
0x18001d020  jmp     loc_18001DB2F
0x18001d025  lea     rdx, [rsp+7F8h+SourceString]
0x18001d02d  cmp     [rsp+7F8h+var_730], 7
0x18001d036  cmova   rdx, [rsp+7F8h+SourceString]; SourceString
0x18001d03f  xorps   xmm0, xmm0
0x18001d042  movups  xmmword ptr [rsp+7F8h+Src], xmm0
0x18001d04a  lea     rcx, [rsp+7F8h+Src]; DestinationString
0x18001d052  call    cs:__imp_RtlInitUnicodeString
0x18001d058  lea     rdx, [rsp+7F8h+Guid]; Guid
0x18001d060  lea     rcx, [rsp+7F8h+Src]; GuidString
0x18001d068  call    cs:__imp_RtlGUIDFromString
0x18001d06e  test    eax, eax
0x18001d070  js      loc_18001DA7E
0x18001d076  mov     rcx, [rsp+7F8h+var_6F8]
0x18001d07e  mov     rax, 7FFFFFFFFFFFFFFEh
0x18001d088  sub     rax, rcx
0x18001d08b  cmp     rax, 4Bh ; 'K'
0x18001d08f  jb      loc_18001DC9F
0x18001d095  lea     rax, [rsp+7F8h+var_708]
0x18001d09d  cmp     [rsp+7F8h+var_6F0], 7
0x18001d0a6  cmova   rax, [rsp+7F8h+var_708]
0x18001d0af  mov     [rsp+7F8h+pcbData], rcx
0x18001d0b4  mov     [rsp+7F8h+pvData], rax
0x18001d0b9  mov     [rsp+7F8h+pdwType], 4Bh ; 'K'
0x18001d0c2  lea     r9, aSoftwareMicros_14; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001d0c9  lea     rcx, [rsp+7F8h+Src]
0x18001d0d1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18001d0d6  lea     rdx, [rsp+7F8h+Src]
0x18001d0de  lea     rcx, [rsp+7F8h+lpSubKey]
0x18001d0e6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001d0eb  lea     rcx, [rsp+7F8h+Src]; void *
0x18001d0f3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
  ... truncated ...
```
