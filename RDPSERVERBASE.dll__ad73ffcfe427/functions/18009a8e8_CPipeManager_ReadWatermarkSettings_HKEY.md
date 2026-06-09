# CPipeManager::ReadWatermarkSettings(HKEY__ *)

- ea: `0x18009a8e8`
- end: `0x18009b31b`
- name: `?ReadWatermarkSettings@CPipeManager@@AEAAJPEAUHKEY__@@@Z`
- size: `2611`
- prototype: `__int64 __fastcall(CPipeManager *__hidden this, HKEY hKey)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x180093580`

## callees

- `0x18000116c`
- `0x1800012dc`
- `0x180001f84`
- `0x18000202c`
- `0x18000305c`
- `0x1800032bc`
- `0x18004d52c`
- `0x18007e9e0`
- `0x18007fd20`
- `0x18009707c`
- `0x18009a8e8`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009aece`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009aee1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009aece`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009aee1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009b2eb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009b2eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18009ae12`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18009ae12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ae31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ae31`
- `RDPBASE!RDPServerStackDiagnostics_LogCheckpoint` at `0x18009acf4`
- `RDPBASE!RDPServerStackDiagnostics_LogCheckpoint` at `0x18009acf4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009a957`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009ab21`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009ab54`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009ab87`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009abba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009abea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009a957`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009ab21`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009ab54`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009ab87`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009abba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009abea`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18009ae1f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18009ae1f`

## string_xrefs

- `0x18009a9b2`: `ReadWatermarkSettings`
- `0x18009acb9`: `ReadWatermarkSettings`
- `0x18009af3c`: `ReadWatermarkSettings`
- `0x18009afd3`: `ReadWatermarkSettings`
- `0x18009b0c9`: `ReadWatermarkSettings`
- `0x18009b150`: `ReadWatermarkSettings`
- `0x18009a9e7`: `rdpqrcodehelper.dll is not found. Disabling WatermarkingMode`
- `0x18009ae18`: `netapi32.dll`
- `0x18009ae57`: `LoadLibrary(netapi32.dll)`

## pseudocode

```c
__int64 __fastcall CPipeManager::ReadWatermarkSettings(CPipeManager *this, HKEY hKey)
{
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  int QrCodeHelper; // eax
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned int v12; // r15d
  int v13; // ecx
  __int16 *v14; // rdx
  const char *v15; // rax
  HMODULE v16; // r12
  _DWORD *v17; // r14
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int v21; // eax
  struct _GUID *CurrentActivityId; // rax
  const char *v23; // rsi
  __int64 v24; // r8
  __int64 v25; // r9
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  HMODULE LibraryW; // rax
  signed int LastError; // eax
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  FARPROC ProcAddress; // rbx
  FARPROC v35; // rax
  int v36; // ecx
  int v37; // r8d
  int v38; // r9d
  void (__fastcall *v39)(const char *); // rdi
  int v40; // ecx
  int v41; // r8d
  int v42; // r9d
  int v43; // ebx
  int v44; // r8d
  int v45; // r9d
  int v46; // ecx
  int v47; // r8d
  int v48; // r9d
  LPBYTE lpData; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  __int64 v52; // [rsp+30h] [rbp-D0h]
  __int64 v53; // [rsp+38h] [rbp-C8h]
  __int64 v54; // [rsp+40h] [rbp-C0h]
  int v55; // [rsp+80h] [rbp-80h] BYREF
  int v56; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD cbData; // [rsp+88h] [rbp-78h] BYREF
  const char *v58; // [rsp+90h] [rbp-70h] BYREF
  const char *v59; // [rsp+98h] [rbp-68h] BYREF
  DWORD Type; // [rsp+A0h] [rbp-60h] BYREF
  const char *v61; // [rsp+A8h] [rbp-58h] BYREF
  const char *v62; // [rsp+B0h] [rbp-50h] BYREF
  const char *v63; // [rsp+B8h] [rbp-48h] BYREF
  BYTE Data[4]; // [rsp+C0h] [rbp-40h] BYREF
  BYTE v65[4]; // [rsp+C4h] [rbp-3Ch] BYREF
  const char *v66; // [rsp+C8h] [rbp-38h] BYREF
  const char *v67; // [rsp+D0h] [rbp-30h] BYREF
  const char *v68; // [rsp+D8h] [rbp-28h] BYREF
  const char *v69; // [rsp+E0h] [rbp-20h] BYREF
  const char *v70; // [rsp+E8h] [rbp-18h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+F0h] [rbp-10h] BYREF

  *(_DWORD *)v65 = 0;
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"fEnableWatermarking", 0, &Type, Data, &cbData) )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      v55 = *(_DWORD *)Data;
      v62 = "Using WatermarkingMode Policy (0=Off, 1=On)";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v4,
        (unsigned int)&word_1802755BE,
        v5,
        v6,
        (__int64)&v62,
        (__int64)&v55);
    }
    *((_DWORD *)this + 13440) = *(_DWORD *)Data != 0;
  }
  if ( *((_DWORD *)this + 13440) )
  {
    QrCodeHelper = CPipeManager::LoadQrCodeHelper(this);
    if ( QrCodeHelper < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v56 = QrCodeHelper;
        v62 = "ReadWatermarkSettings";
        v59 = "rdpqrcodehelper.dll is not found. Disabling WatermarkingMode";
        v55 = 9727;
        v58 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)&dword_180275574,
          v8,
          v9,
          (__int64)&v59,
          (__int64)&v56,
          (__int64)&v58,
          (__int64)&v55,
          (__int64)&v62);
      }
      *((_DWORD *)this + 13440) = 0;
    }
  }
  v12 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD))(**((_QWORD **)this + 1627) + 64LL))(
          *((_QWORD *)this + 1627),
          L"EnableWatermarking",
          *((unsigned int *)this + 13440));
  if ( (v12 & 0x80000000) != 0 )
  {
    v13 = (int)CallbackContext;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v58 = "ReadWatermarkSettings";
      v62 = "Failed to set CONN_PROPERTY_ENABLE_WATERMARKING property";
      v14 = word_180275522;
      v15 = "Error HResult failed";
      v56 = 9737;
      v59 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v55 = v12;
LABEL_13:
      v61 = v15;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v13,
        (_DWORD)v14,
        v10,
        v11,
        (__int64)&v61,
        (__int64)&v55,
        (__int64)&v59,
        (__int64)&v56,
        (__int64)&v58,
        (__int64)&v62);
      return v12;
    }
    return v12;
  }
  v16 = 0;
  if ( !*((_DWORD *)this + 13440) )
  {
    if ( (unsigned int)CallbackContext <= 4
      || !(unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL, v10, v11) )
    {
      return v12;
    }
    LODWORD(v58) = *((_DWORD *)this + 13440);
    v69 = (char *)this + 13552;
    v68 = "PipeMgr";
    v67 = "Stack";
    v70 = "Checkpoint";
    v66 = (const char *)0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      v46,
      (unsigned int)&unk_1802751F0,
      v47,
      v48,
      (__int64)&v70,
      (__int64)&v66,
      (__int64)&v67,
      (__int64)&v68,
      (__int64)&v69,
      (__int64)&v58);
    goto LABEL_51;
  }
  cbData = 4;
  v17 = (_DWORD *)((char *)this + 53784);
  RegQueryValueExW(hKey, L"WatermarkingQrScale", 0, &Type, (LPBYTE)this + 53784, &cbData);
  cbData = 4;
  RegQueryValueExW(hKey, L"WatermarkingOpacity", 0, &Type, (LPBYTE)this + 53788, &cbData);
  cbData = 4;
  RegQueryValueExW(hKey, L"WatermarkingWidthFactor", 0, &Type, (LPBYTE)this + 53792, &cbData);
  cbData = 4;
  RegQueryValueExW(hKey, L"WatermarkingHeightFactor", 0, &Type, (LPBYTE)this + 53796, &cbData);
  cbData = 4;
  RegQueryValueExW(hKey, L"WatermarkingContent", 0, &Type, v65, &cbData);
  v21 = *(_DWORD *)v65;
  if ( *(_DWORD *)v65 > 1u )
  {
    v21 = 0;
    *(_DWORD *)v65 = 0;
  }
  if ( v21 )
  {
    if ( v21 != 1 )
    {
      v12 = -2147418113;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v68 = "ReadWatermarkSettings";
        v69 = "Unexpected content type for watermark";
        LODWORD(v58) = 9867;
        v67 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v66 = "Error HResult failed";
        LODWORD(v59) = -2147418113;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v18,
          (unsigned int)qword_180275300,
          v19,
          v20,
          (__int64)&v66,
          (__int64)&v59,
          (__int64)&v67,
          (__int64)&v58,
          (__int64)&v68,
          (__int64)&v69);
      }
      return v12;
    }
    v62 = 0;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    LibraryW = LoadLibraryW(L"netapi32.dll");
    v16 = LibraryW;
    if ( !LibraryW )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v59 = "ReadWatermarkSettings";
        v58 = "LoadLibrary(netapi32.dll)";
        v56 = 9833;
        v61 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v63 = "Error condition failed";
        v55 = v12;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v31,
          (unsigned int)&word_180275486,
          v32,
          v33,
          (__int64)&v63,
          (__int64)&v55,
          (__int64)&v61,
          (__int64)&v56,
          (__int64)&v59,
          (__int64)&v58);
      }
      return v12;
    }
    ProcAddress = GetProcAddress(LibraryW, "NetGetAadJoinInformation");
    v35 = GetProcAddress(v16, "NetFreeAadJoinInformation");
    v39 = (void (__fastcall *)(const char *))v35;
    if ( !ProcAddress || !v35 )
    {
      v12 = -2147467263;
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v58) = 9842;
        v69 = "AAD Device ID can't be acquired on this OS version";
        LODWORD(v59) = -2147467263;
        v68 = "ReadWatermarkSettings";
        v67 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v66 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v36,
          (unsigned int)qword_180275438,
          v37,
          v38,
          (__int64)&v66,
          (__int64)&v59,
          (__int64)&v67,
          (__int64)&v58,
          (__int64)&v68,
          (__int64)&v69);
      }
      goto LABEL_52;
    }
    v12 = ((__int64 (__fastcall *)(_QWORD, const char **))ProcAddress)(0, &v62);
    if ( (v12 & 0x80000000) != 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v56 = 9845;
        v63 = "NetGetAadJoinInformation failed";
        v55 = v12;
        v58 = "ReadWatermarkSettings";
        v59 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v61 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v40,
          (unsigned int)word_1802753EA,
          v41,
          v42,
          (__int64)&v61,
          (__int64)&v55,
          (__int64)&v59,
          (__int64)&v56,
          (__int64)&v58,
          (__int64)&v63);
      }
      goto LABEL_52;
    }
    if ( !v62 )
    {
      v12 = -2147467259;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v56 = 9846;
        v63 = "AAD Join info is null";
        v55 = -2147467259;
        v58 = "ReadWatermarkSettings";
        v59 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v61 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          -2147467259,
          (unsigned int)&dword_18027539C,
          v41,
          0,
          (__int64)&v61,
          (__int64)&v55,
          (__int64)&v59,
          (__int64)&v56,
          (__int64)&v58,
          (__int64)&v63);
      }
      goto LABEL_52;
    }
    v23 = (char *)this + 53800;
    LODWORD(v54) = SystemTime.wMinute;
    LODWORD(v53) = SystemTime.wHour;
    LODWORD(v52) = SystemTime.wYear;
    LODWORD(lpcbData) = SystemTime.wDay;
    LODWORD(lpData) = SystemTime.wMonth;
    v43 = swprintf_s(
            (wchar_t *const)this + 26900,
            0x64u,
            L"%s, %02d/%02d/%04d:%02d:%02d:%02d",
            *((_QWORD *)v62 + 2),
            lpData,
            lpcbData,
            v52,
            v53,
            v54,
            SystemTime.wSecond);
    v39(v62);
    if ( v43 == -1 )
    {
      v12 = -2147467259;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v56 = 9861;
        v63 = "Failed to generate deviceid, timestamp content for QRCode";
        v55 = -2147467259;
        v58 = "ReadWatermarkSettings";
        v59 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v61 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          -2147467259,
          (unsigned int)&word_18027534E,
          v44,
          v45,
          (__int64)&v61,
          (__int64)&v55,
          (__int64)&v59,
          (__int64)&v56,
          (__int64)&v58,
          (__int64)&v63);
      }
      goto LABEL_52;
    }
    goto LABEL_23;
  }
  CurrentActivityId = RdpActivityId::GetCurrentActivityId((LPGUID)&SystemTime);
  LODWORD(v54) = CurrentActivityId->Data4[2];
  LODWORD(v53) = CurrentActivityId->Data4[1];
  LODWORD(v52) = CurrentActivityId->Data4[0];
  v23 = (char *)this + 53800;
  LODWORD(lpcbData) = CurrentActivityId->Data3;
  LODWORD(lpData) = CurrentActivityId->Data2;
  if ( swprintf_s(
         (wchar_t *const)this + 26900,
         0x64u,
         L"%08lX-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X",
         CurrentActivityId->Data1,
         lpData,
         lpcbData,
         v52,
         v53,
         v54,
         CurrentActivityId->Data4[3],
         CurrentActivityId->Data4[4],
         CurrentActivityId->Data4[5],
         CurrentActivityId->Data4[6],
         CurrentActivityId->Data4[7]) != -1 )
  {
    v17 = (_DWORD *)((char *)this + 53784);
LABEL_23:
    RDPServerStackDiagnostics_LogCheckpoint((char *)this + 13552, 781);
    if ( (unsigned int)CallbackContext > 4
      && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL, v24, v25) )
    {
      v56 = *((_DWORD *)this + 13449);
      v55 = *((_DWORD *)this + 13448);
      LODWORD(v61) = *((_DWORD *)this + 13447);
      LODWORD(v59) = *v17;
      LODWORD(v58) = *((_DWORD *)this + 13440);
      v66 = "PipeMgr";
      v67 = "Stack";
      v69 = "Checkpoint";
      v63 = v23;
      v70 = (char *)this + 13552;
      v68 = (const char *)0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v26,
        (unsigned int)word_18027525A,
        v27,
        v28,
        (__int64)&v69,
        (__int64)&v68,
        (__int64)&v67,
        (__int64)&v66,
        (__int64)&v70,
        (__int64)&v58,
        (__int64)&v59,
        (__int64)&v61,
        (__int64)&v55,
        (__int64)&v56,
        (__int64)&v63);
    }
LABEL_51:
    if ( !v16 )
      return v12;
LABEL_52:
    FreeLibrary(v16);
    return v12;
  }
  v13 = -2147467259;
  v12 = -2147467259;
  if ( (unsigned int)CallbackContext > 2 )
  {
    v56 = 9816;
    v62 = "Failed to generate activityid content for QRCode";
    v14 = (__int16 *)&dword_1802754D4;
    v55 = -2147467259;
    v58 = "ReadWatermarkSettings";
    v59 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
    v15 = "Error condition failed";
    goto LABEL_13;
  }
  return v12;
}

```

## disassembly

```asm
0x18009a8e8  mov     [rsp-8+arg_10], rbx
0x18009a8ed  push    rbp
0x18009a8ee  push    rsi
0x18009a8ef  push    rdi
0x18009a8f0  push    r12
0x18009a8f2  push    r13
0x18009a8f4  push    r14
0x18009a8f6  push    r15
0x18009a8f8  lea     rbp, [rsp-10h]
0x18009a8fd  sub     rsp, 110h
0x18009a904  mov     rax, cs:__security_cookie
0x18009a90b  xor     rax, rsp
0x18009a90e  mov     [rbp+40h+var_40], rax
0x18009a912  mov     rbx, rdx
0x18009a915  mov     dword ptr [rbp+40h+var_7C], 0
0x18009a91c  lea     rax, [rbp+40h+cbData]
0x18009a920  mov     dword ptr [rbp+40h+Data], 0
0x18009a927  mov     [rsp+140h+lpcbData], rax; lpcbData
0x18009a92c  lea     r9, [rbp+40h+Type]; lpType
0x18009a930  lea     rax, [rbp+40h+Data]
0x18009a934  mov     [rbp+40h+Type], 0
0x18009a93b  mov     r13, rcx
0x18009a93e  mov     [rsp+140h+lpData], rax; lpData
0x18009a943  xor     r8d, r8d; lpReserved
0x18009a946  mov     [rbp+40h+cbData], 4
0x18009a94d  lea     rdx, aFenablewaterma; "fEnableWatermarking"
0x18009a954  mov     rcx, rbx; hKey
0x18009a957  call    cs:__imp_RegQueryValueExW
0x18009a95d  test    eax, eax
0x18009a95f  jnz     short loc_18009A9AA
0x18009a961  mov     eax, cs:CallbackContext
0x18009a967  cmp     eax, 4
0x18009a96a  jbe     short loc_18009A99B
0x18009a96c  mov     eax, dword ptr [rbp+40h+Data]
0x18009a96f  lea     rdx, word_1802755BE
0x18009a976  mov     [rbp+40h+var_C0], eax
0x18009a979  lea     rax, aUsingWatermark; "Using WatermarkingMode Policy (0=Off, 1"...
0x18009a980  mov     [rbp+40h+var_90], rax
0x18009a984  lea     rax, [rbp+40h+var_C0]
0x18009a988  mov     [rsp+140h+lpcbData], rax
0x18009a98d  lea     rax, [rbp+40h+var_90]
0x18009a991  mov     [rsp+140h+lpData], rax
0x18009a996  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18009a99b  xor     eax, eax
0x18009a99d  cmp     dword ptr [rbp+40h+Data], eax
0x18009a9a0  setnz   al
0x18009a9a3  mov     [r13+0D200h], eax
0x18009a9aa  cmp     dword ptr [r13+0D200h], 0
0x18009a9b2  lea     rdi, aReadwatermarks; "ReadWatermarkSettings"
0x18009a9b9  mov     esi, 2
0x18009a9be  lea     r14, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18009a9c5  jz      short loc_18009AA3E
0x18009a9c7  mov     rcx, r13; this
0x18009a9ca  call    ?LoadQrCodeHelper@CPipeManager@@IEAAJXZ; CPipeManager::LoadQrCodeHelper(void)
0x18009a9cf  test    eax, eax
0x18009a9d1  jns     short loc_18009AA3E
0x18009a9d3  mov     ecx, cs:CallbackContext
0x18009a9d9  cmp     ecx, esi
0x18009a9db  jbe     short loc_18009AA33
0x18009a9dd  mov     [rbp+40h+var_BC], eax
0x18009a9e0  lea     rdx, dword_180275574
0x18009a9e7  lea     rax, aRdpqrcodehelpe_1; "rdpqrcodehelper.dll is not found. Disab"...
0x18009a9ee  mov     [rbp+40h+var_90], rdi
0x18009a9f2  mov     [rbp+40h+var_A8], rax
0x18009a9f6  lea     rax, [rbp+40h+var_90]
0x18009a9fa  mov     [rsp+140h+var_100], rax
0x18009a9ff  lea     rax, [rbp+40h+var_C0]
0x18009aa03  mov     [rsp+140h+var_108], rax
0x18009aa08  lea     rax, [rbp+40h+var_B0]
0x18009aa0c  mov     [rsp+140h+var_110], rax
0x18009aa11  lea     rax, [rbp+40h+var_BC]
0x18009aa15  mov     [rsp+140h+lpcbData], rax
0x18009aa1a  lea     rax, [rbp+40h+var_A8]
0x18009aa1e  mov     [rsp+140h+lpData], rax
0x18009aa23  mov     [rbp+40h+var_C0], 25FFh
0x18009aa2a  mov     [rbp+40h+var_B0], r14
0x18009aa2e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18009aa33  mov     dword ptr [r13+0D200h], 0
0x18009aa3e  mov     rcx, [r13+32D8h]
0x18009aa45  lea     rdx, aEnablewatermar; "EnableWatermarking"
0x18009aa4c  mov     r8d, [r13+0D200h]
0x18009aa53  mov     rax, [rcx]
0x18009aa56  mov     rax, [rax+40h]
0x18009aa5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aa5f  mov     r15d, eax
0x18009aa62  test    eax, eax
0x18009aa64  jns     short loc_18009AAE4
0x18009aa66  mov     ecx, cs:CallbackContext
0x18009aa6c  cmp     ecx, esi
0x18009aa6e  jbe     loc_18009B2F1
0x18009aa74  lea     rax, aFailedToSetCon_2; "Failed to set CONN_PROPERTY_ENABLE_WATE"...
0x18009aa7b  mov     [rbp+40h+var_B0], rdi
0x18009aa7f  mov     [rbp+40h+var_90], rax
0x18009aa83  lea     rdx, word_180275522
0x18009aa8a  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18009aa91  mov     [rbp+40h+var_BC], 2609h
0x18009aa98  mov     [rbp+40h+var_A8], r14
0x18009aa9c  mov     [rbp+40h+var_C0], r15d
0x18009aaa0  mov     [rbp+40h+var_98], rax
0x18009aaa4  lea     rax, [rbp+40h+var_90]
0x18009aaa8  mov     [rsp+140h+var_F8], rax
0x18009aaad  lea     rax, [rbp+40h+var_B0]
0x18009aab1  mov     [rsp+140h+var_100], rax
0x18009aab6  lea     rax, [rbp+40h+var_BC]
0x18009aaba  mov     [rsp+140h+var_108], rax
0x18009aabf  lea     rax, [rbp+40h+var_A8]
0x18009aac3  mov     [rsp+140h+var_110], rax
0x18009aac8  lea     rax, [rbp+40h+var_C0]
0x18009aacc  mov     [rsp+140h+lpcbData], rax
0x18009aad1  lea     rax, [rbp+40h+var_98]
0x18009aad5  mov     [rsp+140h+lpData], rax
0x18009aada  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18009aadf  jmp     loc_18009B2F1
0x18009aae4  xor     r12d, r12d
0x18009aae7  cmp     [r13+0D200h], r12d
0x18009aaee  jz      loc_18009B236
0x18009aaf4  lea     rax, [rbp+40h+cbData]
0x18009aaf8  mov     [rbp+40h+cbData], 4
0x18009aaff  mov     [rsp+140h+lpcbData], rax; lpcbData
0x18009ab04  lea     r14, [r13+0D218h]
0x18009ab0b  lea     r9, [rbp+40h+Type]; lpType
0x18009ab0f  mov     [rsp+140h+lpData], r14; lpData
0x18009ab14  xor     r8d, r8d; lpReserved
0x18009ab17  lea     rdx, aWatermarkingqr; "WatermarkingQrScale"
0x18009ab1e  mov     rcx, rbx; hKey
0x18009ab21  call    cs:__imp_RegQueryValueExW
0x18009ab27  lea     rcx, [rbp+40h+cbData]
0x18009ab2b  mov     [rbp+40h+cbData], 4
0x18009ab32  mov     [rsp+140h+lpcbData], rcx; lpcbData
0x18009ab37  lea     rax, [r13+0D21Ch]
0x18009ab3e  mov     rcx, rbx; hKey
0x18009ab41  mov     [rsp+140h+lpData], rax; lpData
0x18009ab46  lea     r9, [rbp+40h+Type]; lpType
0x18009ab4a  xor     r8d, r8d; lpReserved
0x18009ab4d  lea     rdx, aWatermarkingop; "WatermarkingOpacity"
0x18009ab54  call    cs:__imp_RegQueryValueExW
0x18009ab5a  lea     rcx, [rbp+40h+cbData]
0x18009ab5e  mov     [rbp+40h+cbData], 4
0x18009ab65  mov     [rsp+140h+lpcbData], rcx; lpcbData
0x18009ab6a  lea     rax, [r13+0D220h]
0x18009ab71  mov     rcx, rbx; hKey
0x18009ab74  mov     [rsp+140h+lpData], rax; lpData
0x18009ab79  lea     r9, [rbp+40h+Type]; lpType
0x18009ab7d  xor     r8d, r8d; lpReserved
0x18009ab80  lea     rdx, aWatermarkingwi; "WatermarkingWidthFactor"
0x18009ab87  call    cs:__imp_RegQueryValueExW
0x18009ab8d  lea     rcx, [rbp+40h+cbData]
0x18009ab91  mov     [rbp+40h+cbData], 4
0x18009ab98  mov     [rsp+140h+lpcbData], rcx; lpcbData
0x18009ab9d  lea     rax, [r13+0D224h]
0x18009aba4  mov     rcx, rbx; hKey
0x18009aba7  mov     [rsp+140h+lpData], rax; lpData
0x18009abac  lea     r9, [rbp+40h+Type]; lpType
0x18009abb0  xor     r8d, r8d; lpReserved
0x18009abb3  lea     rdx, aWatermarkinghe; "WatermarkingHeightFactor"
0x18009abba  call    cs:__imp_RegQueryValueExW
0x18009abc0  lea     rax, [rbp+40h+cbData]
0x18009abc4  mov     [rbp+40h+cbData], 4
0x18009abcb  mov     [rsp+140h+lpcbData], rax; lpcbData
0x18009abd0  lea     r9, [rbp+40h+Type]; lpType
0x18009abd4  lea     rax, [rbp+40h+var_7C]
0x18009abd8  xor     r8d, r8d; lpReserved
0x18009abdb  lea     rdx, aWatermarkingco; "WatermarkingContent"
0x18009abe2  mov     [rsp+140h+lpData], rax; lpData
0x18009abe7  mov     rcx, rbx; hKey
0x18009abea  call    cs:__imp_RegQueryValueExW
0x18009abf0  mov     eax, dword ptr [rbp+40h+var_7C]
0x18009abf3  cmp     eax, 1
0x18009abf6  jbe     short loc_18009ABFD
0x18009abf8  xor     eax, eax
0x18009abfa  mov     dword ptr [rbp+40h+var_7C], eax
0x18009abfd  test    eax, eax
0x18009abff  jnz     loc_18009ADFA
0x18009ac05  lea     rcx, [rbp+40h+SystemTime]; ActivityId
0x18009ac09  call    ?GetCurrentActivityId@RdpActivityId@@SA?AU_GUID@@XZ; RdpActivityId::GetCurrentActivityId(void)
0x18009ac0e  movzx   ecx, byte ptr [rax+0Fh]
0x18009ac12  movzx   edx, byte ptr [rax+0Eh]
0x18009ac16  movzx   r8d, byte ptr [rax+0Dh]
0x18009ac1b  movzx   esi, byte ptr [rax+8]
0x18009ac1f  movzx   r10d, byte ptr [rax+0Ch]
0x18009ac24  movzx   r11d, byte ptr [rax+0Bh]
0x18009ac29  movzx   ebx, byte ptr [rax+0Ah]
0x18009ac2d  movzx   edi, byte ptr [rax+9]
0x18009ac31  movzx   r14d, word ptr [rax+6]
0x18009ac36  mov     r9d, [rax]
0x18009ac39  movzx   eax, word ptr [rax+4]
0x18009ac3d  mov     dword ptr [rsp+140h+var_D8], ecx
0x18009ac41  mov     dword ptr [rsp+140h+var_E0], edx
0x18009ac45  mov     edx, 64h ; 'd'; BufferCount
0x18009ac4a  mov     dword ptr [rsp+140h+var_E8], r8d
0x18009ac4f  lea     r8, a08lx04x04x02x0; "%08lX-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x18009ac56  mov     dword ptr [rsp+140h+var_F0], r10d
0x18009ac5b  mov     dword ptr [rsp+140h+var_F8], r11d
0x18009ac60  mov     dword ptr [rsp+140h+var_100], ebx
0x18009ac64  mov     dword ptr [rsp+140h+var_108], edi
0x18009ac68  mov     dword ptr [rsp+140h+var_110], esi
0x18009ac6c  lea     rsi, [r13+0D228h]
0x18009ac73  mov     rcx, rsi; Buffer
0x18009ac76  mov     dword ptr [rsp+140h+lpcbData], r14d
0x18009ac7b  mov     dword ptr [rsp+140h+lpData], eax
0x18009ac7f  call    swprintf_s
0x18009ac84  cmp     eax, 0FFFFFFFFh
0x18009ac87  jnz     short loc_18009ACDE
0x18009ac89  mov     eax, cs:CallbackContext
0x18009ac8f  mov     ecx, 80004005h
0x18009ac94  mov     r15d, ecx
0x18009ac97  cmp     eax, 2
0x18009ac9a  jbe     loc_18009B2F1
0x18009aca0  lea     rax, aFailedToGenera_1; "Failed to generate activityid content f"...
0x18009aca7  mov     [rbp+40h+var_BC], 2658h
0x18009acae  mov     [rbp+40h+var_90], rax
0x18009acb2  lea     rdx, dword_1802754D4
0x18009acb9  lea     rax, aReadwatermarks; "ReadWatermarkSettings"
0x18009acc0  mov     [rbp+40h+var_C0], ecx
0x18009acc3  mov     [rbp+40h+var_B0], rax
0x18009acc7  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18009acce  mov     [rbp+40h+var_A8], rax
0x18009acd2  lea     rax, aErrorCondition; "Error condition failed"
0x18009acd9  jmp     loc_18009AAA0
0x18009acde  lea     r14, [r13+0D218h]
0x18009ace5  lea     rbx, [r13+34F0h]
0x18009acec  mov     edx, 30Dh
0x18009acf1  mov     rcx, rbx
0x18009acf4  call    cs:__imp_RDPServerStackDiagnostics_LogCheckpoint
0x18009acfa  mov     eax, cs:CallbackContext
0x18009ad00  cmp     eax, 4
0x18009ad03  jbe     loc_18009B2E3
0x18009ad09  mov     rdx, 470000000000h
0x18009ad13  lea     rcx, CallbackContext
0x18009ad1a  call    _tlgKeywordOn
0x18009ad1f  test    al, al
0x18009ad21  jz      loc_18009B2E3
0x18009ad27  mov     eax, [r13+0D224h]
0x18009ad2e  lea     rdx, word_18027525A
0x18009ad35  mov     [rbp+40h+var_BC], eax
0x18009ad38  mov     eax, [r13+0D220h]
0x18009ad3f  mov     [rbp+40h+var_C0], eax
0x18009ad42  mov     eax, [r13+0D21Ch]
0x18009ad49  mov     dword ptr [rbp+40h+var_98], eax
0x18009ad4c  mov     eax, [r14]
0x18009ad4f  mov     dword ptr [rbp+40h+var_A8], eax
0x18009ad52  mov     eax, [r13+0D200h]
0x18009ad59  mov     dword ptr [rbp+40h+var_B0], eax
0x18009ad5c  lea     rax, aPipemgr; "PipeMgr"
0x18009ad63  mov     [rbp+40h+var_78], rax
0x18009ad67  lea     rax, aStack; "Stack"
0x18009ad6e  mov     [rbp+40h+var_70], rax
0x18009ad72  lea     rax, aCheckpoint; "Checkpoint"
0x18009ad79  mov     [rbp+40h+var_60], rax
0x18009ad7d  lea     rax, [rbp+40h+var_88]
0x18009ad81  mov     [rsp+140h+var_D0], rax
0x18009ad86  lea     rax, [rbp+40h+var_BC]
0x18009ad8a  mov     [rsp+140h+var_D8], rax
0x18009ad8f  lea     rax, [rbp+40h+var_C0]
0x18009ad93  mov     [rsp+140h+var_E0], rax
0x18009ad98  lea     rax, [rbp+40h+var_98]
0x18009ad9c  mov     [rsp+140h+var_E8], rax
0x18009ada1  lea     rax, [rbp+40h+var_A8]
0x18009ada5  mov     [rsp+140h+var_F0], rax
0x18009adaa  lea     rax, [rbp+40h+var_B0]
0x18009adae  mov     [rsp+140h+var_F8], rax
0x18009adb3  lea     rax, [rbp+40h+var_58]
0x18009adb7  mov     [rsp+140h+var_100], rax
0x18009adbc  lea     rax, [rbp+40h+var_78]
0x18009adc0  mov     [rsp+140h+var_108], rax
0x18009adc5  lea     rax, [rbp+40h+var_70]
0x18009adc9  mov     [rsp+140h+var_110], rax
0x18009adce  lea     rax, [rbp+40h+var_68]
0x18009add2  mov     [rsp+140h+lpcbData], rax
0x18009add7  lea     rax, [rbp+40h+var_60]
0x18009addb  mov     [rsp+140h+lpData], rax
0x18009ade0  mov     [rbp+40h+var_88], rsi
0x18009ade4  mov     [rbp+40h+var_58], rbx
0x18009ade8  mov     [rbp+40h+var_68], 1000000h
0x18009adf0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U4@U4@U4@U4@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@6666AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18009adf5  jmp     loc_18009B2E3
0x18009adfa  cmp     eax, 1
0x18009adfd  jnz     loc_18009B1B5
0x18009ae03  xorps   xmm0, xmm0
0x18009ae06  mov     [rbp+40h+var_90], r12
0x18009ae0a  lea     rcx, [rbp+40h+SystemTime]; lpSystemTime
0x18009ae0e  movups  xmmword ptr [rbp+40h+SystemTime.wYear], xmm0
0x18009ae12  call    cs:__imp_GetSystemTime
0x18009ae18  lea     rcx, aNetapi32Dll; "netapi32.dll"
0x18009ae1f  call    cs:__imp_LoadLibraryW
0x18009ae25  mov     r12, rax
0x18009ae28  test    rax, rax
0x18009ae2b  jnz     loc_18009AEC4
0x18009ae31  call    cs:__imp_GetLastError
0x18009ae37  mov     r15d, eax
0x18009ae3a  test    eax, eax
0x18009ae3c  jle     short loc_18009AE49
0x18009ae3e  movzx   r15d, ax
0x18009ae42  or      r15d, 80070000h
0x18009ae49  mov     eax, cs:CallbackContext
0x18009ae4f  cmp     eax, esi
0x18009ae51  jbe     loc_18009B2F1
0x18009ae57  lea     rax, aLoadlibraryNet; "LoadLibrary(netapi32.dll)"
0x18009ae5e  mov     [rbp+40h+var_A8], rdi
0x18009ae62  mov     [rbp+40h+var_B0], rax
  ... truncated ...
```
