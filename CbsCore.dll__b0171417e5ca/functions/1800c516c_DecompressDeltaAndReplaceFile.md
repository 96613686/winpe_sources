# DecompressDeltaAndReplaceFile

- ea: `0x1800c516c`
- end: `0x1800c5959`
- name: `DecompressDeltaAndReplaceFile`
- size: `2029`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18009f8e0`

## callees

- `0x180019bdc`
- `0x18004f454`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800ad504`
- `0x1800c516c`
- `0x1800d0588`
- `0x1800eb920`
- `0x1800fe364`
- `0x1801026fc`
- `0x180265c08`
- `0x180265c64`
- `0x180265e14`
- `0x18028156c`
- `0x18028169c`
- `0x180281858`
- `0x180281a90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c52d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5435`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c56a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5740`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c57cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c58a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c52d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5435`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c56a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5740`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c57cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c58a0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c5730`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c5730`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800c52c5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800c5425`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800c52c5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800c5425`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800c524f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800c5690`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800c524f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800c5690`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800c57bc`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800c57bc`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800c5260`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800c5363`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800c5260`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800c5363`

## string_xrefs

- `0x1800c5454`: `Failed to read base line file.`
- `0x1800c575a`: `Failed to write file.`
- `0x1800c52f4`: `Failed to read delta file.`
- `0x1800c5584`: `Failed to regenerate LZMS compressed buffer.`

## pseudocode

```c
__int64 __fastcall DecompressDeltaAndReplaceFile(Windows::Rtl *a1, void *a2, void *a3)
{
  const void *v3; // r14
  bool *v6; // rdx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  DWORD FileSize; // eax
  DWORD v10; // ebx
  unsigned __int64 v11; // r13
  DWORD v12; // r8d
  LPVOID v13; // rbx
  Windows::Rtl *v14; // rcx
  signed int LastError; // ebx
  unsigned int v16; // eax
  __int64 v17; // rdx
  DWORD v18; // esi
  DWORD v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  int v22; // eax
  __int64 v23; // rdx
  unsigned int v24; // esi
  int v25; // edx
  unsigned __int64 v26; // r9
  __int64 v27; // rdx
  int v28; // eax
  unsigned int v29; // ebx
  int v30; // edx
  int v31; // eax
  unsigned int v32; // ebx
  int v33; // edx
  int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // eax
  unsigned int v39; // eax
  unsigned int lpOverlapped; // [rsp+20h] [rbp-89h]
  struct Windows::Rtl::AutoDeltaBlob *v41; // [rsp+28h] [rbp-81h]
  struct Windows::Rtl::AutoDeltaBlob *v42; // [rsp+30h] [rbp-79h] BYREF
  unsigned int v43[2]; // [rsp+38h] [rbp-71h] BYREF
  LPVOID v44; // [rsp+40h] [rbp-69h] BYREF
  LPVOID lpBuffer; // [rsp+48h] [rbp-61h] BYREF
  unsigned int v46[4]; // [rsp+50h] [rbp-59h] BYREF
  const void *v47; // [rsp+60h] [rbp-49h]
  _QWORD v48[2]; // [rsp+68h] [rbp-41h] BYREF
  const void *v49; // [rsp+78h] [rbp-31h]
  __int128 v50; // [rsp+80h] [rbp-29h] BYREF
  const void *v51; // [rsp+90h] [rbp-19h]
  unsigned __int64 v52[2]; // [rsp+98h] [rbp-11h] BYREF
  LPVOID v53; // [rsp+A8h] [rbp-1h]
  int v54; // [rsp+B0h] [rbp+7h] BYREF
  DWORD NumberOfBytesRead; // [rsp+B4h] [rbp+Bh] BYREF
  DWORD NumberOfBytesWritten; // [rsp+B8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v54 = (int)a1;
  lpBuffer = 0;
  v44 = 0;
  v3 = 0;
  NumberOfBytesRead = 0;
  LOBYTE(v42) = 0;
  *(_QWORD *)&v46[2] = 0;
  v52[1] = 0;
  v48[1] = 0;
  v48[0] = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  NumberOfBytesWritten = 0;
  Windows::Rtl::InitializeDeltaCompressor(a1, a2);
  Windows::Rtl::IsDeltaCompressorAvailable((Windows::Rtl *)&v42, v6);
  if ( !(_BYTE)v42 )
  {
    v7 = -2147467263;
    v54 = -2147467263;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Delta engine not available.");
      *(_QWORD *)v43 = &v54;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v43);
    }
    v8 = 3327;
    goto LABEL_9;
  }
  SetFilePointer(a2, 0, 0, 0);
  FileSize = GetFileSize(a2, 0);
  v10 = FileSize;
  if ( FileSize - 12 > 0xFFFFFFF2 )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid file size");
      if ( LastError > 0 )
        v39 = (unsigned __int16)LastError | 0x80070000;
      else
        v39 = LastError;
      v54 = v39;
      *(_QWORD *)v43 = &v54;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)v43);
    }
    if ( LastError )
    {
      v17 = 3337;
      goto LABEL_87;
    }
    goto LABEL_79;
  }
  v11 = FileSize;
  if ( Windows::AutoNewWithUnsizedArrayPtr<_BACKING_REGION_OUTPUT>::AllocateWithTotalSize(&lpBuffer, FileSize) )
  {
    v12 = v10;
    v13 = lpBuffer;
    if ( !ReadFile(a2, lpBuffer, v12, &NumberOfBytesRead, 0) )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to read delta file.");
        if ( LastError > 0 )
          v16 = (unsigned __int16)LastError | 0x80070000;
        else
          v16 = LastError;
        v54 = v16;
        *(_QWORD *)v43 = &v54;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v43);
      }
      if ( LastError )
      {
        v17 = 3343;
LABEL_87:
        v34 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)v17,
                (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
                (const char *)(unsigned int)LastError,
                lpOverlapped);
LABEL_88:
        v7 = v34;
        goto LABEL_89;
      }
      goto LABEL_79;
    }
    v18 = 0;
    if ( a3 )
    {
      v19 = GetFileSize(a3, 0);
      v18 = v19;
      if ( v19 == -1 )
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid baseline file size");
          if ( LastError > 0 )
            v20 = (unsigned __int16)LastError | 0x80070000;
          else
            v20 = LastError;
          v54 = v20;
          *(_QWORD *)v43 = &v54;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {0}",
            (__int64)v43);
        }
        if ( LastError )
        {
          v17 = 3350;
          goto LABEL_87;
        }
LABEL_79:
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v50);
        Windows::Rtl::AutoDeltaBlob::Close((Windows::Rtl::AutoDeltaBlob *)v48);
        Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&v44);
        Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&lpBuffer);
        return 0;
      }
      if ( !Windows::AutoNewWithUnsizedArrayPtr<_BACKING_REGION_OUTPUT>::AllocateWithTotalSize(&v44, v19) )
      {
        v8 = 3353;
        goto LABEL_8;
      }
      v3 = v44;
      if ( !ReadFile(a3, v44, v18, &NumberOfBytesRead, 0) )
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to read base line file.");
          if ( LastError > 0 )
            v21 = (unsigned __int16)LastError | 0x80070000;
          else
            v21 = LastError;
          v54 = v21;
          *(_QWORD *)v43 = &v54;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {0}",
            (__int64)v43);
        }
        if ( LastError )
        {
          v17 = 3356;
          goto LABEL_87;
        }
        goto LABEL_79;
      }
    }
    if ( v54 != 3 )
    {
      if ( v54 == 5 )
      {
        LOBYTE(v47) = 0;
        *(_OWORD *)v46 = 0;
        v22 = Windows::WCP::Rtl::LocalAutoLZMSDecoder::Initialize((Windows::WCP::Rtl::LocalAutoLZMSDecoder *)v46);
        v24 = v22;
        if ( v22 < 0 )
        {
          v54 = v22;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to initialize decoder.");
            *(_QWORD *)v43 = &v54;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v25,
              3,
              (unsigned int)": {}",
              (__int64)v43);
          }
          v26 = v24;
          v27 = 3370;
LABEL_43:
          v7 = wil::details::in1diag3::Return_NtStatus(
                 retaddr,
                 (void *)v27,
                 (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
                 (const char *)v26,
                 lpOverlapped);
          Windows::WCP::Rtl::LocalAutoLZMSDecoder::~LocalAutoLZMSDecoder((Windows::WCP::Rtl::LocalAutoLZMSDecoder *)v46);
          goto LABEL_89;
        }
        v52[0] = v11;
        v53 = v13;
        v28 = Windows::WCP::Rtl::LocalAutoLZMSDecoder::LZMSDecompressBuffer(v46, v23, v52, &v50);
        v29 = v28;
        if ( v28 < 0 )
        {
          v54 = v28;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to regenerate LZMS compressed buffer.");
            *(_QWORD *)v43 = &v54;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v30,
              3,
              (unsigned int)": {}",
              (__int64)v43);
          }
          v26 = v29;
          v27 = 3377;
          goto LABEL_43;
        }
        v3 = v51;
        v18 = v50;
        Windows::WCP::Rtl::LocalAutoLZMSDecoder::~LocalAutoLZMSDecoder((Windows::WCP::Rtl::LocalAutoLZMSDecoder *)v46);
      }
      else
      {
        *(_QWORD *)v46 = v18;
        v47 = v3;
        v52[0] = v11;
        v53 = v13;
        v31 = Windows::Rtl::DeltaDecompressBuffer(
                v14,
                (unsigned int)v46,
                (struct _LBLOB *)(a3 != 0 ? 12LL : 4LL),
                (unsigned __int64)v52,
                (struct _LBLOB *)v48,
                v41,
                v42);
        v32 = v31;
        if ( v31 < 0 )
        {
          v54 = v31;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to regenerate buffer from delta.");
            *(_QWORD *)v43 = &v54;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v33,
              3,
              (unsigned int)": {}",
              (__int64)v43);
          }
          v34 = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0xD4A,
                  (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
                  (const char *)v32,
                  lpOverlapped);
          goto LABEL_88;
        }
        v3 = v49;
        v18 = v48[0];
      }
    }
    if ( SetFilePointer(a2, 0, 0, 0) == -1 )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to rewind file.");
        if ( LastError > 0 )
          v35 = (unsigned __int16)LastError | 0x80070000;
        else
          v35 = LastError;
        v54 = v35;
        *(_QWORD *)v43 = &v54;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v43);
      }
      if ( LastError )
      {
        v17 = 3411;
        goto LABEL_87;
      }
    }
    else if ( WriteFile(a2, v3, v18, &NumberOfBytesWritten, 0) )
    {
      if ( SetEndOfFile(a2) )
      {
        LogAdapter::TraceAtLevel<>(
          1,
          "Successfully regenerated payload from delta and baseline file from remote source");
      }
      else
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to end file.");
          if ( LastError > 0 )
            v37 = (unsigned __int16)LastError | 0x80070000;
          else
            v37 = LastError;
          v54 = v37;
          *(_QWORD *)v43 = &v54;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {0}",
            (__int64)v43);
        }
        if ( LastError )
        {
          v17 = 3413;
          goto LABEL_87;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to write file.");
        if ( LastError > 0 )
          v36 = (unsigned __int16)LastError | 0x80070000;
        else
          v36 = LastError;
        v54 = v36;
        *(_QWORD *)v43 = &v54;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v43);
      }
      if ( LastError )
      {
        v17 = 3412;
        goto LABEL_87;
      }
    }
    goto LABEL_79;
  }
  v8 = 3340;
LABEL_8:
  v7 = -2147024882;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
    (const char *)v7,
    lpOverlapped);
LABEL_89:
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v50);
  Windows::Rtl::AutoDeltaBlob::Close((Windows::Rtl::AutoDeltaBlob *)v48);
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&v44);
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&lpBuffer);
  return v7;
}

```

## disassembly

```asm
0x1800c516c  mov     [rsp-8+arg_0], rbx
0x1800c5171  push    rbp
0x1800c5172  push    rsi
0x1800c5173  push    rdi
0x1800c5174  push    r12
0x1800c5176  push    r13
0x1800c5178  push    r14
0x1800c517a  push    r15
0x1800c517c  lea     rbp, [rsp-27h]
0x1800c5181  sub     rsp, 0D0h
0x1800c5188  mov     rax, cs:__security_cookie
0x1800c518f  xor     rax, rsp
0x1800c5192  mov     [rbp+57h+var_40], rax
0x1800c5196  xor     edi, edi
0x1800c5198  mov     [rbp+57h+var_50], ecx
0x1800c519b  xorps   xmm0, xmm0
0x1800c519e  mov     [rbp+57h+lpBuffer], rdi
0x1800c51a2  xor     eax, eax
0x1800c51a4  mov     [rbp+57h+var_C0], rdi
0x1800c51a8  mov     r14d, edi
0x1800c51ab  mov     [rbp+57h+NumberOfBytesRead], edi
0x1800c51ae  mov     byte ptr [rbp+57h+var_D0], dil
0x1800c51b2  mov     r12, r8
0x1800c51b5  mov     qword ptr [rbp+57h+var_B0+8], rdi
0x1800c51b9  mov     r15, rdx
0x1800c51bc  mov     [rbp+57h+var_60], rdi
0x1800c51c0  mov     [rbp+57h+var_90], rdi
0x1800c51c4  mov     [rbp+57h+var_98], rdi
0x1800c51c8  mov     [rbp+57h+var_88], rdi
0x1800c51cc  movups  [rbp+57h+var_80], xmm0
0x1800c51d0  mov     [rbp+57h+var_70], rax
0x1800c51d4  mov     [rbp+57h+NumberOfBytesWritten], edi
0x1800c51d7  call    ?InitializeDeltaCompressor@Rtl@Windows@@YAJPEAX@Z; Windows::Rtl::InitializeDeltaCompressor(void *)
0x1800c51dc  lea     rcx, [rbp+57h+var_D0]; this
0x1800c51e0  call    ?IsDeltaCompressorAvailable@Rtl@Windows@@YAJPEA_N@Z; Windows::Rtl::IsDeltaCompressorAvailable(bool *)
0x1800c51e5  cmp     byte ptr [rbp+57h+var_D0], dil
0x1800c51e9  jnz     short loc_1800C5244
0x1800c51eb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c51f2  mov     ebx, 80004001h
0x1800c51f7  mov     [rbp+57h+var_50], ebx
0x1800c51fa  test    rcx, rcx
0x1800c51fd  jz      short loc_1800C523D
0x1800c51ff  lea     edi, [r14+3]
0x1800c5203  xor     edx, edx
0x1800c5205  mov     r8d, edi
0x1800c5208  lea     r9, aDeltaEngineNot; "Delta engine not available."
0x1800c520f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c5214  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c521b  lea     rax, [rbp+57h+var_50]
0x1800c521f  mov     qword ptr [rbp+57h+var_C8], rax
0x1800c5223  lea     r9, asc_1802EE7AC; ": {}"
0x1800c522a  lea     rax, [rbp+57h+var_C8]
0x1800c522e  mov     r8d, edi
0x1800c5231  mov     dl, 1
0x1800c5233  mov     [rsp+100h+lpOverlapped], rax
0x1800c5238  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c523d  mov     edx, 0CFFh
0x1800c5242  jmp     short loc_1800C5297
0x1800c5244  xor     r9d, r9d; dwMoveMethod
0x1800c5247  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800c524a  xor     edx, edx; lDistanceToMove
0x1800c524c  mov     rcx, r15; hFile
0x1800c524f  call    cs:__imp_SetFilePointer
0x1800c5256  nop     dword ptr [rax+rax+00h]
0x1800c525b  xor     edx, edx; lpFileSizeHigh
0x1800c525d  mov     rcx, r15; hFile
0x1800c5260  call    cs:__imp_GetFileSize
0x1800c5267  nop     dword ptr [rax+rax+00h]
0x1800c526c  mov     ebx, eax
0x1800c526e  lea     ecx, [rbx-0Ch]
0x1800c5271  cmp     ecx, 0FFFFFFF2h
0x1800c5274  ja      loc_1800C58A0
0x1800c527a  mov     edx, ebx
0x1800c527c  lea     rcx, [rbp+57h+lpBuffer]
0x1800c5280  mov     r13d, ebx
0x1800c5283  call    ?AllocateWithTotalSize@?$AutoNewWithUnsizedArrayPtr@U_BACKING_REGION_OUTPUT@@@Windows@@QEAAPEAU_BACKING_REGION_OUTPUT@@_K@Z; Windows::AutoNewWithUnsizedArrayPtr<_BACKING_REGION_OUTPUT>::AllocateWithTotalSize(unsigned __int64)
0x1800c5288  test    rax, rax
0x1800c528b  jnz     short loc_1800C52AF
0x1800c528d  mov     edx, 0D0Ch; void *
0x1800c5292  mov     ebx, 8007000Eh
0x1800c5297  mov     rcx, [rbp+5Fh]; this
0x1800c529b  lea     r8, aOnecoreBaseCbs_64; "onecore\\base\\cbs\\core\\helper.cpp"
0x1800c52a2  mov     r9d, ebx; char *
0x1800c52a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c52aa  jmp     loc_1800C592E
0x1800c52af  mov     r8d, ebx; nNumberOfBytesToRead
0x1800c52b2  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x1800c52b7  mov     rbx, [rbp+57h+lpBuffer]
0x1800c52bb  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800c52bf  mov     rdx, rbx; lpBuffer
0x1800c52c2  mov     rcx, r15; hFile
0x1800c52c5  call    cs:__imp_ReadFile
0x1800c52cc  nop     dword ptr [rax+rax+00h]
0x1800c52d1  test    eax, eax
0x1800c52d3  jnz     short loc_1800C5353
0x1800c52d5  call    cs:__imp_GetLastError
0x1800c52dc  nop     dword ptr [rax+rax+00h]
0x1800c52e1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c52e8  mov     ebx, eax
0x1800c52ea  test    rcx, rcx
0x1800c52ed  jz      short loc_1800C5341
0x1800c52ef  mov     edi, 3
0x1800c52f4  lea     r9, aFailedToReadDe; "Failed to read delta file."
0x1800c52fb  mov     r8d, edi
0x1800c52fe  xor     edx, edx
0x1800c5300  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c5305  test    ebx, ebx
0x1800c5307  jg      short loc_1800C530D
0x1800c5309  mov     eax, ebx
0x1800c530b  jmp     short loc_1800C5315
0x1800c530d  movzx   eax, bx
0x1800c5310  or      eax, 80070000h
0x1800c5315  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c531c  lea     r9, a0; ": {0}"
0x1800c5323  mov     [rbp+57h+var_50], eax
0x1800c5326  mov     r8d, edi
0x1800c5329  lea     rax, [rbp+57h+var_50]
0x1800c532d  mov     dl, 1
0x1800c532f  mov     qword ptr [rbp+57h+var_C8], rax
0x1800c5333  lea     rax, [rbp+57h+var_C8]
0x1800c5337  mov     [rsp+100h+lpOverlapped], rax
0x1800c533c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c5341  test    ebx, ebx
0x1800c5343  jz      loc_1800C5852
0x1800c5349  mov     edx, 0D0Fh
0x1800c534e  jmp     loc_1800C5919
0x1800c5353  mov     esi, edi
0x1800c5355  test    r12, r12
0x1800c5358  jz      loc_1800C54B3
0x1800c535e  xor     edx, edx; lpFileSizeHigh
0x1800c5360  mov     rcx, r12; hFile
0x1800c5363  call    cs:__imp_GetFileSize
0x1800c536a  nop     dword ptr [rax+rax+00h]
0x1800c536f  mov     esi, eax
0x1800c5371  cmp     eax, 0FFFFFFFFh
0x1800c5374  jnz     short loc_1800C53F4
0x1800c5376  call    cs:__imp_GetLastError
0x1800c537d  nop     dword ptr [rax+rax+00h]
0x1800c5382  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c5389  mov     ebx, eax
0x1800c538b  test    rcx, rcx
0x1800c538e  jz      short loc_1800C53E2
0x1800c5390  mov     edi, 3
0x1800c5395  lea     r9, aInvalidBaselin; "Invalid baseline file size"
0x1800c539c  mov     r8d, edi
0x1800c539f  xor     edx, edx
0x1800c53a1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c53a6  test    ebx, ebx
0x1800c53a8  jg      short loc_1800C53AE
0x1800c53aa  mov     eax, ebx
0x1800c53ac  jmp     short loc_1800C53B6
0x1800c53ae  movzx   eax, bx
0x1800c53b1  or      eax, 80070000h
0x1800c53b6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c53bd  lea     r9, a0; ": {0}"
0x1800c53c4  mov     [rbp+57h+var_50], eax
0x1800c53c7  mov     r8d, edi
0x1800c53ca  lea     rax, [rbp+57h+var_50]
0x1800c53ce  mov     dl, 1
0x1800c53d0  mov     qword ptr [rbp+57h+var_C8], rax
0x1800c53d4  lea     rax, [rbp+57h+var_C8]
0x1800c53d8  mov     [rsp+100h+lpOverlapped], rax
0x1800c53dd  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c53e2  test    ebx, ebx
0x1800c53e4  jz      loc_1800C5852
0x1800c53ea  mov     edx, 0D16h
0x1800c53ef  jmp     loc_1800C5919
0x1800c53f4  mov     rdx, rsi
0x1800c53f7  lea     rcx, [rbp+57h+var_C0]
0x1800c53fb  call    ?AllocateWithTotalSize@?$AutoNewWithUnsizedArrayPtr@U_BACKING_REGION_OUTPUT@@@Windows@@QEAAPEAU_BACKING_REGION_OUTPUT@@_K@Z; Windows::AutoNewWithUnsizedArrayPtr<_BACKING_REGION_OUTPUT>::AllocateWithTotalSize(unsigned __int64)
0x1800c5400  test    rax, rax
0x1800c5403  jnz     short loc_1800C540F
0x1800c5405  mov     edx, 0D19h
0x1800c540a  jmp     loc_1800C5292
0x1800c540f  mov     r14, [rbp+57h+var_C0]
0x1800c5413  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800c5417  mov     rdx, r14; lpBuffer
0x1800c541a  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x1800c541f  mov     r8d, esi; nNumberOfBytesToRead
0x1800c5422  mov     rcx, r12; hFile
0x1800c5425  call    cs:__imp_ReadFile
0x1800c542c  nop     dword ptr [rax+rax+00h]
0x1800c5431  test    eax, eax
0x1800c5433  jnz     short loc_1800C54B3
0x1800c5435  call    cs:__imp_GetLastError
0x1800c543c  nop     dword ptr [rax+rax+00h]
0x1800c5441  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c5448  mov     ebx, eax
0x1800c544a  test    rcx, rcx
0x1800c544d  jz      short loc_1800C54A1
0x1800c544f  mov     edi, 3
0x1800c5454  lea     r9, aFailedToReadBa; "Failed to read base line file."
0x1800c545b  mov     r8d, edi
0x1800c545e  xor     edx, edx
0x1800c5460  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c5465  test    ebx, ebx
0x1800c5467  jg      short loc_1800C546D
0x1800c5469  mov     eax, ebx
0x1800c546b  jmp     short loc_1800C5475
0x1800c546d  movzx   eax, bx
0x1800c5470  or      eax, 80070000h
0x1800c5475  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c547c  lea     r9, a0; ": {0}"
0x1800c5483  mov     [rbp+57h+var_50], eax
0x1800c5486  mov     r8d, edi
0x1800c5489  lea     rax, [rbp+57h+var_50]
0x1800c548d  mov     dl, 1
0x1800c548f  mov     qword ptr [rbp+57h+var_C8], rax
0x1800c5493  lea     rax, [rbp+57h+var_C8]
0x1800c5497  mov     [rsp+100h+lpOverlapped], rax
0x1800c549c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c54a1  test    ebx, ebx
0x1800c54a3  jz      loc_1800C5852
0x1800c54a9  mov     edx, 0D1Ch
0x1800c54ae  jmp     loc_1800C5919
0x1800c54b3  mov     eax, [rbp+57h+var_50]
0x1800c54b6  mov     edi, 3
0x1800c54bb  cmp     eax, edi
0x1800c54bd  jz      loc_1800C5685
0x1800c54c3  cmp     eax, 5
0x1800c54c6  jnz     loc_1800C55DE
0x1800c54cc  xorps   xmm0, xmm0
0x1800c54cf  mov     byte ptr [rbp+57h+var_A0], 0
0x1800c54d3  lea     rcx, [rbp+57h+var_B0]; this
0x1800c54d7  movdqu  xmmword ptr [rbp+57h+var_B0], xmm0
0x1800c54dc  call    ?Initialize@LocalAutoLZMSDecoder@Rtl@WCP@Windows@@QEAAJXZ; Windows::WCP::Rtl::LocalAutoLZMSDecoder::Initialize(void)
0x1800c54e1  mov     esi, eax
0x1800c54e3  test    eax, eax
0x1800c54e5  jns     short loc_1800C5556
0x1800c54e7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c54ee  mov     [rbp+57h+var_50], eax
0x1800c54f1  test    rcx, rcx
0x1800c54f4  jz      short loc_1800C552E
0x1800c54f6  lea     r9, aFailedToInitia_63; "Failed to initialize decoder."
0x1800c54fd  mov     r8d, edi
0x1800c5500  xor     edx, edx
0x1800c5502  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c5507  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c550e  lea     rax, [rbp+57h+var_50]
0x1800c5512  mov     qword ptr [rbp+57h+var_C8], rax
0x1800c5516  lea     r9, asc_1802EE7AC; ": {}"
0x1800c551d  lea     rax, [rbp+57h+var_C8]
0x1800c5521  mov     r8d, edi
0x1800c5524  mov     [rsp+100h+lpOverlapped], rax; int
0x1800c5529  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x1800c552e  mov     r9d, esi; char *
0x1800c5531  mov     edx, 0D2Ah; void *
0x1800c5536  mov     rcx, [rbp+5Fh]; this
0x1800c553a  lea     r8, aOnecoreBaseCbs_64; "onecore\\base\\cbs\\core\\helper.cpp"
0x1800c5541  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800c5546  lea     rcx, [rbp+57h+var_B0]; this
0x1800c554a  mov     ebx, eax
0x1800c554c  call    ??1LocalAutoLZMSDecoder@Rtl@WCP@Windows@@QEAA@XZ; Windows::WCP::Rtl::LocalAutoLZMSDecoder::~LocalAutoLZMSDecoder(void)
0x1800c5551  jmp     loc_1800C592E
0x1800c5556  lea     r9, [rbp+57h+var_80]
0x1800c555a  mov     [rbp+57h+var_68], r13
0x1800c555e  lea     r8, [rbp+57h+var_68]
0x1800c5562  mov     [rbp+57h+var_58], rbx
0x1800c5566  lea     rcx, [rbp+57h+var_B0]
0x1800c556a  call    ?LZMSDecompressBuffer@LocalAutoLZMSDecoder@Rtl@WCP@Windows@@QEAAJ_KPEBU_LBLOB@@AEAV?$Auto@U_LBLOB@@@4@@Z; Windows::WCP::Rtl::LocalAutoLZMSDecoder::LZMSDecompressBuffer(unsigned __int64,_LBLOB const *,Windows::Auto<_LBLOB> &)
0x1800c556f  mov     ebx, eax
0x1800c5571  test    eax, eax
0x1800c5573  jns     short loc_1800C55C9
0x1800c5575  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c557c  mov     [rbp+57h+var_50], eax
0x1800c557f  test    rcx, rcx
0x1800c5582  jz      short loc_1800C55BC
0x1800c5584  lea     r9, aFailedToRegene; "Failed to regenerate LZMS compressed bu"...
0x1800c558b  mov     r8d, edi
0x1800c558e  xor     edx, edx
0x1800c5590  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c5595  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c559c  lea     rax, [rbp+57h+var_50]
0x1800c55a0  mov     qword ptr [rbp+57h+var_C8], rax
0x1800c55a4  lea     r9, asc_1802EE7AC; ": {}"
0x1800c55ab  lea     rax, [rbp+57h+var_C8]
0x1800c55af  mov     r8d, edi
0x1800c55b2  mov     [rsp+100h+lpOverlapped], rax
0x1800c55b7  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x1800c55bc  mov     r9d, ebx
0x1800c55bf  mov     edx, 0D31h
0x1800c55c4  jmp     loc_1800C5536
0x1800c55c9  mov     r14, [rbp+57h+var_70]
0x1800c55cd  lea     rcx, [rbp+57h+var_B0]; this
0x1800c55d1  mov     esi, dword ptr [rbp+57h+var_80]
0x1800c55d4  call    ??1LocalAutoLZMSDecoder@Rtl@WCP@Windows@@QEAA@XZ; Windows::WCP::Rtl::LocalAutoLZMSDecoder::~LocalAutoLZMSDecoder(void)
0x1800c55d9  jmp     loc_1800C5685
0x1800c55de  mov     eax, esi
0x1800c55e0  lea     r9, [rbp+57h+var_68]; unsigned __int64
0x1800c55e4  mov     qword ptr [rbp+57h+var_B0], rax
0x1800c55e8  lea     rdx, [rbp+57h+var_B0]; unsigned int
0x1800c55ec  lea     rax, [rbp+57h+var_98]
0x1800c55f0  mov     [rbp+57h+var_A0], r14
0x1800c55f4  neg     r12
0x1800c55f7  mov     [rbp+57h+var_68], r13
0x1800c55fb  mov     [rbp+57h+var_58], rbx
0x1800c55ff  sbb     r8, r8
0x1800c5602  mov     [rsp+100h+lpOverlapped], rax; struct _LBLOB *
0x1800c5607  and     r8d, 8
0x1800c560b  add     r8, 4; struct _LBLOB *
  ... truncated ...
```
