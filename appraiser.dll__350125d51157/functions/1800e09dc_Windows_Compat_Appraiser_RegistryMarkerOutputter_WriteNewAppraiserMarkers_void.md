# Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteNewAppraiserMarkers(void)

- ea: `0x1800e09dc`
- end: `0x1800e106c`
- name: `?WriteNewAppraiserMarkers@RegistryMarkerOutputter@Appraiser@Compat@Windows@@AEAAJXZ`
- size: `1680`
- prototype: `__int64 __fastcall(Windows::Compat::Appraiser::RegistryMarkerOutputter *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800da600`

## callees

- `0x18000147c`
- `0x180008570`
- `0x180011d94`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x18008e08c`
- `0x1800e09dc`
- `0x1801dbc18`
- `0x1801dbcd0`
- `0x1801dc634`
- `0x1801dd038`
- `0x1801dd1a4`
- `0x1801dd21c`
- `0x1801dd608`
- `0x1801deb5c`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x1800e0f5a`
- `KERNEL32!GetSystemTime` at `0x1800e0f5a`
- `KERNEL32!GetLastError` at `0x1800e0ab2`
- `KERNEL32!GetLastError` at `0x1800e0ab2`
- `ADVAPI32!RegDeleteTreeW` at `0x1800e0b88`
- `ADVAPI32!RegDeleteTreeW` at `0x1800e0bac`
- `ADVAPI32!RegDeleteTreeW` at `0x1800e0b88`
- `ADVAPI32!RegDeleteTreeW` at `0x1800e0bac`
- `ADVAPI32!RegSetValueExW` at `0x1800e0bfe`
- `ADVAPI32!RegSetValueExW` at `0x1800e0bfe`
- `ktmw32!CreateTransaction` at `0x1800e0a9f`
- `ktmw32!CreateTransaction` at `0x1800e0a9f`

## string_xrefs

- `0x1800e0ae5`: `CompatMarkers`
- `0x1800e0b10`: `CompatMarkers`
- `0x1800e0b64`: `CompatMarkers`
- `0x1800e0c2a`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800e1020`: `onecore\base\appcompat\appraiser\outputters\registrymarker.cpp`
- `0x1800e0c23`: `Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteNewAppraiserMarkers`
- `0x1800e1019`: `Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteNewAppraiserMarkers`
- `0x1800e0c3e`: `Failed to initialize %ls marker writer: [0x%x].`
- `0x1800e1009`: `Failed to initialize %ls marker writer: [0x%x].`
- `0x1800e0e76`: `Failed to write markers, swallowing: [0x%x].`
- `0x1800e0fdf`: `Failed to write markers, swallowing: [0x%x].`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteNewAppraiserMarkers(
        Windows::Compat::Appraiser::RegistryMarkerOutputter *this)
{
  signed int v2; // ebx
  TraceLoggingCorrelationVector *v3; // rcx
  char v4; // di
  __int64 v5; // rsi
  signed int LastError; // eax
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // r15
  __int64 v12; // r9
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rdx
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rcx
  int v19; // eax
  char v20; // dl
  const char *v21; // rax
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  int v26; // eax
  int v27; // r14d
  volatile signed __int64 *v28; // rcx
  void **v29; // rdx
  __int64 v30; // rbx
  __int64 v31; // r8
  __int64 v32; // r9
  const char *IsolationFlags; // [rsp+20h] [rbp-E0h]
  const char *Timeout; // [rsp+28h] [rbp-D8h]
  const char *Description; // [rsp+30h] [rbp-D0h]
  char v37[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v38; // [rsp+64h] [rbp-9Ch] BYREF
  int v39; // [rsp+68h] [rbp-98h] BYREF
  struct _SYSTEMTIME *v40; // [rsp+70h] [rbp-90h] BYREF
  char *v41; // [rsp+78h] [rbp-88h] BYREF
  const char *v42; // [rsp+80h] [rbp-80h] BYREF
  const char *v43; // [rsp+88h] [rbp-78h] BYREF
  const size_t *v44; // [rsp+90h] [rbp-70h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v46; // [rsp+B0h] [rbp-50h]
  struct _SYSTEMTIME v47; // [rsp+C0h] [rbp-40h] BYREF
  void *Transaction; // [rsp+D0h] [rbp-30h] BYREF
  HKEY phkResult; // [rsp+D8h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+E0h] [rbp-20h] BYREF
  HKEY v51; // [rsp+E8h] [rbp-18h] BYREF
  BYTE v52[528]; // [rsp+F0h] [rbp-10h] BYREF
  _WORD Data[144]; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v54[144]; // [rsp+420h] [rbp+320h] BYREF
  _BYTE v55[144]; // [rsp+4B0h] [rbp+3B0h] BYREF
  unsigned __int16 v56[16]; // [rsp+540h] [rbp+440h] BYREF
  char v57[144]; // [rsp+560h] [rbp+460h] BYREF
  char v58[144]; // [rsp+5F0h] [rbp+4F0h] BYREF

  v46 = -2;
  Windows::Compat::Shared::IndicatorWriter::IndicatorWriter((Windows::Compat::Shared::IndicatorWriter *)&Transaction);
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v54);
  if ( *((_QWORD *)this + 4) )
  {
    v3 = (TraceLoggingCorrelationVector *)v54;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v3 = Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::Increment(v3, v57);
    v37[0] = 0;
    if ( this != (Windows::Compat::Appraiser::RegistryMarkerOutputter *)-376LL )
    {
      v4 = *((_BYTE *)this + 360);
      Data[140] = 0;
      Transaction = CreateTransaction(0, 0, 0, 0, 0, 0, 0);
      v5 = -1;
      if ( Transaction == (void *)-1LL )
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        if ( v2 < 0 )
          goto LABEL_71;
      }
      else
      {
        v2 = Windows::Compat::Shared::IndicatorWriter::OpenRegistryKeys(
               &hKey,
               &v51,
               L"CompatMarkers",
               (const unsigned __int16 *)this + 188,
               &Transaction,
               0);
        if ( v2 < 0 )
          goto LABEL_71;
        Windows::Compat::Shared::IndicatorWriter::OpenRegistryKeys(
          &phkResult,
          0,
          L"CompatMarkers",
          (const unsigned __int16 *)this + 188,
          0,
          0);
        if ( !v4 )
        {
          if ( (int)Windows::Compat::Shared::RegistryChecksum::IsIntact(v37, &hKey, &v51, 3) < 0 || (v4 = 0, !v37[0]) )
            v4 = 1;
        }
        v2 = Windows::Compat::Shared::IndicatorWriter::SetUpTelemetry(
               (struct Windows::Compat::Shared::IndicatorTelemetry *)v52,
               (struct Windows::Compat::Shared::RegistryKey *)&v51,
               (wchar_t *)L"CompatMarkers",
               (const unsigned __int16 *)this + 188,
               v4,
               v57);
        if ( v2 < 0 )
          goto LABEL_71;
        v7 = RegDeleteTreeW(hKey, 0);
        v2 = v7;
        if ( v7 > 0 )
          v2 = (unsigned __int16)v7 | 0x80070000;
        if ( v2 < 0 )
          goto LABEL_71;
        v8 = RegDeleteTreeW(v51, 0);
        v2 = v8;
        if ( v8 > 0 )
          v2 = (unsigned __int16)v8 | 0x80070000;
        if ( v2 < 0 )
          goto LABEL_71;
        do
          ++v5;
        while ( Data[v5] );
        v9 = RegSetValueExW(v51, L"UtcSyncId", 0, 1u, (const BYTE *)Data, 2 * v5 + 2);
        v2 = v9;
        if ( v9 > 0 )
          v2 = (unsigned __int16)v9 | 0x80070000;
        if ( v2 < 0 )
          goto LABEL_71;
        v2 = 0;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x4B6u,
          "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
          "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteNewAppraiserMarkers",
          "Failed to initialize %ls marker writer: [0x%x].",
          (const wchar_t *)this + 188,
          v2);
      v10 = *((_QWORD *)this + 4);
      if ( v10 )
      {
        v11 = 0;
        while ( 1 )
        {
          v12 = 0;
          if ( v11 < v10 )
          {
            v40 = 0;
            v13 = *((_QWORD *)this + 3) * v11;
            if ( !is_mul_ok(*((_QWORD *)this + 3), v11)
              || (v14 = *((_QWORD *)this + 7), v12 = v14 + v13, v14 + v13 < v14) )
            {
              v12 = 0;
            }
          }
          v15 = StringCchPrintfW(v56, 0xBu, L"%d", *(unsigned int *)(v12 + 16));
          v2 = v15;
          if ( v15 < 0 )
            break;
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x4BBu,
              "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
              "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteNewAppraiserMarkers",
              "Failed to print marker match count to buffer: [0x%x].",
              v15);
          v16 = 0;
          if ( v11 < *((_QWORD *)this + 4) )
          {
            v40 = 0;
            v17 = *((_QWORD *)this + 3) * v11;
            if ( !is_mul_ok(*((_QWORD *)this + 3), v11)
              || (v18 = *((_QWORD *)this + 7), v16 = v18 + v17, v18 + v17 < v18) )
            {
              v16 = 0;
            }
          }
          v2 = Windows::Compat::Shared::IndicatorWriter::Add(
                 (Windows::Compat::Shared::IndicatorWriter *)&Transaction,
                 *(const unsigned __int16 **)(v16 + 8),
                 v56,
                 1);
          if ( v2 < 0 )
          {
            v21 = "Failed to add marker to indicator transaction: [0x%x].";
            v20 = -66;
            goto LABEL_51;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x4BEu,
              "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
              "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteNewAppraiserMarkers",
              "Failed to add marker to indicator transaction: [0x%x].",
              v2);
          ++v11;
          v10 = *((_QWORD *)this + 4);
          if ( v11 >= v10 )
            goto LABEL_47;
        }
        v21 = "Failed to print marker match count to buffer: [0x%x].";
        v20 = -69;
LABEL_51:
        LODWORD(Description) = v2;
        LODWORD(Timeout) = (_DWORD)v21;
      }
      else
      {
LABEL_47:
        v19 = StringCchPrintfW(v56, 0xBu, L"%d", *((unsigned int *)this + 86));
        v2 = v19;
        if ( v19 >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x4C6u,
              "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
              "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteNewAppraiserMarkers",
              "Failed to print marker version to buffer: [0x%x].",
              v19);
          v22 = Windows::Compat::Shared::IndicatorWriter::Add(
                  (Windows::Compat::Shared::IndicatorWriter *)&Transaction,
                  L"Version",
                  v56,
                  1);
          v2 = v22;
          if ( v22 >= 0 )
          {
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x4C9u,
                "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
                "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteNewAppraiserMarkers",
                "Failed to add marker to indicator transaction: [0x%x].",
                v22);
            v26 = Windows::Compat::Shared::IndicatorWriter::Write(&Transaction, v23, v24, v25);
            v27 = v26;
            if ( v26 >= 0 )
            {
              if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                  0x4D2u,
                  "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
                  "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteNewAppraiserMarkers",
                  "Failed to write markers, swallowing: [0x%x].",
                  v26);
            }
            else
            {
              LODWORD(Description) = v26;
              LODWORD(IsolationFlags) = v26;
              Windows::Compat::Appraiser::WriteLog(
                (Windows::Compat::Appraiser *)1,
                210,
                (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
                "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteNewAppraiserMarkers",
                IsolationFlags,
                (int)"Failed to write markers, swallowing: [0x%x].",
                Description);
              TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v55);
              v28 = (volatile signed __int64 *)v55;
              if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
                v28 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
              TraceLoggingCorrelationVector::ToStringImpl(
                (TraceLoggingCorrelationVector *)v28,
                _InterlockedExchangeAdd64(v28 + 17, 0),
                v58);
              if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
                UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v29);
              v30 = qword_1802C9628;
              if ( *(_DWORD *)qword_1802C9628 > 5u
                && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
                && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
              {
                v41 = v58;
                v38 = v27;
                v42 = "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteNewAppraiserMarkers";
                v43 = "onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp";
                v39 = 1234;
                v44 = &szValueBuf;
                SystemTime = 0;
                GetSystemTime(&SystemTime);
                v47 = SystemTime;
                v40 = &v47;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                  v30,
                  (__int64)qword_1802A4000,
                  v31,
                  v32,
                  (__int64 *)&v40,
                  &v44,
                  (__int64)&v39,
                  &v43,
                  &v42,
                  (__int64)&v38,
                  (const char **)&v41);
              }
            }
            goto LABEL_2;
          }
          LODWORD(Description) = v22;
          Timeout = "Failed to add marker to indicator transaction: [0x%x].";
          v20 = -55;
        }
        else
        {
          LODWORD(Description) = v19;
          Timeout = "Failed to print marker version to buffer: [0x%x].";
          v20 = -58;
        }
      }
      LODWORD(IsolationFlags) = v2;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v20,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
        "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteNewAppraiserMarkers",
        IsolationFlags,
        (int)Timeout,
        Description);
      goto LABEL_72;
    }
    v2 = -2147024809;
LABEL_71:
    LODWORD(IsolationFlags) = v2;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      182,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\registrymarker.cpp",
      "Windows::Compat::Appraiser::RegistryMarkerOutputter::WriteNewAppraiserMarkers",
      IsolationFlags,
      (int)"Failed to initialize %ls marker writer: [0x%x].",
      (const char *)this + 376,
      v2);
    goto LABEL_72;
  }
LABEL_2:
  v2 = 0;
LABEL_72:
  Windows::Compat::Shared::IndicatorWriter::UnInitialize((Windows::Compat::Shared::IndicatorWriter *)&Transaction);
  Windows::Compat::Shared::IndicatorTelemetry::~IndicatorTelemetry((Windows::Compat::Shared::IndicatorTelemetry *)v52);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800e09dc  push    rbp
0x1800e09de  push    rbx
0x1800e09df  push    rsi
0x1800e09e0  push    rdi
0x1800e09e1  push    r12
0x1800e09e3  push    r13
0x1800e09e5  push    r14
0x1800e09e7  push    r15
0x1800e09e9  lea     rbp, [rsp-598h]
0x1800e09f1  sub     rsp, 698h
0x1800e09f8  mov     [rbp+5D0h+var_620], 0FFFFFFFFFFFFFFFEh
0x1800e0a00  mov     rax, cs:__security_cookie
0x1800e0a07  xor     rax, rsp
0x1800e0a0a  mov     [rbp+5D0h+var_50], rax
0x1800e0a11  mov     r14, rcx
0x1800e0a14  lea     rcx, [rbp+5D0h+var_600]; this
0x1800e0a18  call    ??0IndicatorWriter@Shared@Compat@Windows@@QEAA@XZ; Windows::Compat::Shared::IndicatorWriter::IndicatorWriter(void)
0x1800e0a1d  nop
0x1800e0a1e  lea     rcx, [rbp+5D0h+var_2B0]; this
0x1800e0a25  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800e0a2a  xor     r12d, r12d
0x1800e0a2d  cmp     [r14+20h], r12
0x1800e0a31  jnz     short loc_1800E0A3B
0x1800e0a33  mov     ebx, r12d
0x1800e0a36  jmp     loc_1800E1034
0x1800e0a3b  lea     rcx, [rbp+5D0h+var_2B0]
0x1800e0a42  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1800e0a49  test    rax, rax
0x1800e0a4c  cmovnz  rcx, rax; this
0x1800e0a50  lea     rdx, [rbp+5D0h+var_170]; char *
0x1800e0a57  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x1800e0a5c  lea     r15, [r14+178h]
0x1800e0a63  mov     [rsp+6D0h+var_670], r12b
0x1800e0a68  mov     r13d, 1
0x1800e0a6e  test    r15, r15
0x1800e0a71  jz      loc_1800E0FFB
0x1800e0a77  mov     dil, [r14+168h]
0x1800e0a7e  mov     [rbp+5D0h+var_2B8], r12w
0x1800e0a86  mov     [rsp+6D0h+Description], r12; Description
0x1800e0a8b  mov     [rsp+6D0h+Timeout], r12d; Timeout
0x1800e0a90  mov     [rsp+6D0h+IsolationFlags], r12d; IsolationFlags
0x1800e0a95  xor     r9d, r9d; IsolationLevel
0x1800e0a98  xor     r8d, r8d; CreateOptions
0x1800e0a9b  xor     edx, edx; UOW
0x1800e0a9d  xor     ecx, ecx; lpTransactionAttributes
0x1800e0a9f  call    cs:__imp_CreateTransaction
0x1800e0aa5  mov     [rbp+5D0h+var_600], rax
0x1800e0aa9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800e0aad  cmp     rax, rsi
0x1800e0ab0  jnz     short loc_1800E0AD4
0x1800e0ab2  call    cs:__imp_GetLastError
0x1800e0ab8  mov     ebx, eax
0x1800e0aba  test    eax, eax
0x1800e0abc  jle     short loc_1800E0AC7
0x1800e0abe  movzx   ebx, ax
0x1800e0ac1  or      ebx, 80070000h
0x1800e0ac7  test    ebx, ebx
0x1800e0ac9  jns     loc_1800E0C1A
0x1800e0acf  jmp     loc_1800E1000
0x1800e0ad4  mov     byte ptr [rsp+6D0h+Timeout], r12b; bool
0x1800e0ad9  lea     rax, [rbp+5D0h+var_600]
0x1800e0add  mov     qword ptr [rsp+6D0h+IsolationFlags], rax; void **
0x1800e0ae2  mov     r9, r15; unsigned __int16 *
0x1800e0ae5  lea     r8, aCompatmarkers; "CompatMarkers"
0x1800e0aec  lea     rdx, [rbp+5D0h+var_5E8]; PHKEY
0x1800e0af0  lea     rcx, [rbp+5D0h+hKey]; phkResult
0x1800e0af4  call    ?OpenRegistryKeys@IndicatorWriter@Shared@Compat@Windows@@CAJPEAVRegistryKey@234@0PEBG1PEAPEAX_N@Z; Windows::Compat::Shared::IndicatorWriter::OpenRegistryKeys(Windows::Compat::Shared::RegistryKey *,Windows::Compat::Shared::RegistryKey *,ushort const *,ushort const *,void * *,bool)
0x1800e0af9  mov     ebx, eax
0x1800e0afb  test    eax, eax
0x1800e0afd  js      loc_1800E1000
0x1800e0b03  mov     byte ptr [rsp+6D0h+Timeout], r12b; bool
0x1800e0b08  mov     qword ptr [rsp+6D0h+IsolationFlags], r12; void **
0x1800e0b0d  mov     r9, r15; unsigned __int16 *
0x1800e0b10  lea     r8, aCompatmarkers; "CompatMarkers"
0x1800e0b17  xor     edx, edx; PHKEY
0x1800e0b19  lea     rcx, [rbp+5D0h+phkResult]; phkResult
0x1800e0b1d  call    ?OpenRegistryKeys@IndicatorWriter@Shared@Compat@Windows@@CAJPEAVRegistryKey@234@0PEBG1PEAPEAX_N@Z; Windows::Compat::Shared::IndicatorWriter::OpenRegistryKeys(Windows::Compat::Shared::RegistryKey *,Windows::Compat::Shared::RegistryKey *,ushort const *,ushort const *,void * *,bool)
0x1800e0b22  test    dil, dil
0x1800e0b25  jnz     short loc_1800E0B50
0x1800e0b27  mov     r9d, 3
0x1800e0b2d  lea     r8, [rbp+5D0h+var_5E8]
0x1800e0b31  lea     rdx, [rbp+5D0h+hKey]
0x1800e0b35  lea     rcx, [rsp+6D0h+var_670]
0x1800e0b3a  call    ?IsIntact@RegistryChecksum@Shared@Compat@Windows@@SAJPEA_NPEAVRegistryKey@234@1W4RegistryChecksumType@234@PEBG@Z; Windows::Compat::Shared::RegistryChecksum::IsIntact(bool *,Windows::Compat::Shared::RegistryKey *,Windows::Compat::Shared::RegistryKey *,Windows::Compat::Shared::RegistryChecksumType,ushort const *)
0x1800e0b3f  test    eax, eax
0x1800e0b41  js      short loc_1800E0B4D
0x1800e0b43  cmp     [rsp+6D0h+var_670], r12b
0x1800e0b48  mov     dil, r12b
0x1800e0b4b  jnz     short loc_1800E0B50
0x1800e0b4d  mov     dil, r13b
0x1800e0b50  lea     rax, [rbp+5D0h+var_170]
0x1800e0b57  mov     qword ptr [rsp+6D0h+Timeout], rax; char *
0x1800e0b5c  mov     byte ptr [rsp+6D0h+IsolationFlags], dil; bool
0x1800e0b61  mov     r9, r15; unsigned __int16 *
0x1800e0b64  lea     r8, aCompatmarkers; "CompatMarkers"
0x1800e0b6b  lea     rdx, [rbp+5D0h+var_5E8]; struct Windows::Compat::Shared::RegistryKey *
0x1800e0b6f  lea     rcx, [rbp+5D0h+var_5E0]; this
0x1800e0b73  call    ?SetUpTelemetry@IndicatorWriter@Shared@Compat@Windows@@CAJPEAVIndicatorTelemetry@234@PEAVRegistryKey@234@PEBG2_NPEBD@Z; Windows::Compat::Shared::IndicatorWriter::SetUpTelemetry(Windows::Compat::Shared::IndicatorTelemetry *,Windows::Compat::Shared::RegistryKey *,ushort const *,ushort const *,bool,char const *)
0x1800e0b78  mov     ebx, eax
0x1800e0b7a  test    eax, eax
0x1800e0b7c  js      loc_1800E1000
0x1800e0b82  xor     edx, edx; lpSubKey
0x1800e0b84  mov     rcx, [rbp+5D0h+hKey]; hKey
0x1800e0b88  call    cs:__imp_RegDeleteTreeW
0x1800e0b8e  mov     ebx, eax
0x1800e0b90  mov     edi, 80070000h
0x1800e0b95  test    eax, eax
0x1800e0b97  jle     short loc_1800E0B9E
0x1800e0b99  movzx   ebx, ax
0x1800e0b9c  or      ebx, edi
0x1800e0b9e  test    ebx, ebx
0x1800e0ba0  js      loc_1800E1000
0x1800e0ba6  xor     edx, edx; lpSubKey
0x1800e0ba8  mov     rcx, [rbp+5D0h+var_5E8]; hKey
0x1800e0bac  call    cs:__imp_RegDeleteTreeW
0x1800e0bb2  mov     ebx, eax
0x1800e0bb4  test    eax, eax
0x1800e0bb6  jle     short loc_1800E0BBD
0x1800e0bb8  movzx   ebx, ax
0x1800e0bbb  or      ebx, edi
0x1800e0bbd  test    ebx, ebx
0x1800e0bbf  js      loc_1800E1000
0x1800e0bc5  lea     rax, [rbp+5D0h+Data]
0x1800e0bcc  inc     rsi
0x1800e0bcf  cmp     [rax+rsi*2], r12w
0x1800e0bd4  jnz     short loc_1800E0BCC
0x1800e0bd6  lea     eax, ds:2[rsi*2]
0x1800e0bdd  mov     [rsp+6D0h+Timeout], eax; cbData
0x1800e0be1  lea     rax, [rbp+5D0h+Data]
0x1800e0be8  mov     qword ptr [rsp+6D0h+IsolationFlags], rax; lpData
0x1800e0bed  mov     r9d, r13d; dwType
0x1800e0bf0  xor     r8d, r8d; Reserved
0x1800e0bf3  lea     rdx, aUtcsyncid; "UtcSyncId"
0x1800e0bfa  mov     rcx, [rbp+5D0h+var_5E8]; hKey
0x1800e0bfe  call    cs:__imp_RegSetValueExW
0x1800e0c04  mov     ebx, eax
0x1800e0c06  test    eax, eax
0x1800e0c08  jle     short loc_1800E0C0F
0x1800e0c0a  movzx   ebx, ax
0x1800e0c0d  or      ebx, edi
0x1800e0c0f  test    ebx, ebx
0x1800e0c11  js      loc_1800E1000
0x1800e0c17  mov     ebx, r12d
0x1800e0c1a  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800e0c20  and     eax, r13d
0x1800e0c23  lea     rdi, aWindowsCompatA_618; "Windows::Compat::Appraiser::RegistryMar"...
0x1800e0c2a  lea     rsi, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800e0c31  test    al, al
0x1800e0c33  jz      short loc_1800E0C55
0x1800e0c35  mov     [rsp+6D0h+Timeout], ebx
0x1800e0c39  mov     qword ptr [rsp+6D0h+IsolationFlags], r15
0x1800e0c3e  lea     r9, aFailedToInitia_9; "Failed to initialize %ls marker writer:"...
0x1800e0c45  mov     r8, rdi; char *
0x1800e0c48  mov     rdx, rsi; char *
0x1800e0c4b  mov     ecx, 4B6h; unsigned int
0x1800e0c50  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800e0c55  mov     rax, [r14+20h]
0x1800e0c59  lea     r15, aFailedToAddMar_0; "Failed to add marker to indicator trans"...
0x1800e0c60  test    rax, rax
0x1800e0c63  jz      loc_1800E0D6C
0x1800e0c69  mov     r15, r12
0x1800e0c6c  mov     r9, r12
0x1800e0c6f  cmp     r15, rax
0x1800e0c72  jnb     short loc_1800E0C98
0x1800e0c74  mov     [rsp+6D0h+var_660], r12
0x1800e0c79  mov     rax, r15
0x1800e0c7c  mul     qword ptr [r14+18h]
0x1800e0c80  mov     rcx, rax
0x1800e0c83  test    rdx, rdx
0x1800e0c86  jnz     short loc_1800E0C95
0x1800e0c88  mov     rax, [r14+38h]
0x1800e0c8c  lea     r9, [rax+rcx]
0x1800e0c90  cmp     r9, rax
0x1800e0c93  jnb     short loc_1800E0C98
0x1800e0c95  mov     r9, r12
0x1800e0c98  mov     r9d, [r9+10h]
0x1800e0c9c  lea     r8, aD; "%d"
0x1800e0ca3  mov     edx, 0Bh; unsigned __int64
0x1800e0ca8  lea     rcx, [rbp+5D0h+var_190]; unsigned __int16 *
0x1800e0caf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800e0cb4  mov     ebx, eax
0x1800e0cb6  test    eax, eax
0x1800e0cb8  js      loc_1800E0DB6
0x1800e0cbe  mov     ecx, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800e0cc4  and     ecx, r13d
0x1800e0cc7  test    cl, cl
0x1800e0cc9  jz      short loc_1800E0CE6
0x1800e0ccb  mov     [rsp+6D0h+IsolationFlags], eax
0x1800e0ccf  lea     r9, aFailedToPrintM_0; "Failed to print marker match count to b"...
0x1800e0cd6  mov     r8, rdi; char *
0x1800e0cd9  mov     rdx, rsi; char *
0x1800e0cdc  mov     ecx, 4BBh; unsigned int
0x1800e0ce1  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800e0ce6  mov     rdx, r12
0x1800e0ce9  cmp     r15, [r14+20h]
0x1800e0ced  jnb     short loc_1800E0D10
0x1800e0cef  mov     [rsp+6D0h+var_660], r12
0x1800e0cf4  mov     rax, r15
0x1800e0cf7  mul     qword ptr [r14+18h]
0x1800e0cfb  test    rdx, rdx
0x1800e0cfe  jnz     short loc_1800E0D0D
0x1800e0d00  mov     rcx, [r14+38h]
0x1800e0d04  lea     rdx, [rcx+rax]
0x1800e0d08  cmp     rdx, rcx
0x1800e0d0b  jnb     short loc_1800E0D10
0x1800e0d0d  mov     rdx, r12
0x1800e0d10  mov     r9d, r13d; int
0x1800e0d13  lea     r8, [rbp+5D0h+var_190]; unsigned __int16 *
0x1800e0d1a  mov     rdx, [rdx+8]; unsigned __int16 *
0x1800e0d1e  lea     rcx, [rbp+5D0h+var_600]; this
0x1800e0d22  call    ?Add@IndicatorWriter@Shared@Compat@Windows@@QEAAJPEBG0H@Z; Windows::Compat::Shared::IndicatorWriter::Add(ushort const *,ushort const *,int)
0x1800e0d27  mov     ebx, eax
0x1800e0d29  test    eax, eax
0x1800e0d2b  js      short loc_1800E0DA8
0x1800e0d2d  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800e0d33  and     eax, r13d
0x1800e0d36  test    al, al
0x1800e0d38  jz      short loc_1800E0D55
0x1800e0d3a  mov     [rsp+6D0h+IsolationFlags], ebx
0x1800e0d3e  lea     r9, aFailedToAddMar_0; "Failed to add marker to indicator trans"...
0x1800e0d45  mov     r8, rdi; char *
0x1800e0d48  mov     rdx, rsi; char *
0x1800e0d4b  mov     ecx, 4BEh; unsigned int
0x1800e0d50  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800e0d55  add     r15, r13
0x1800e0d58  mov     rax, [r14+20h]
0x1800e0d5c  cmp     r15, rax
0x1800e0d5f  jb      loc_1800E0C6C
0x1800e0d65  lea     r15, aFailedToAddMar_0; "Failed to add marker to indicator trans"...
0x1800e0d6c  mov     r9d, [r14+158h]
0x1800e0d73  lea     r8, aD; "%d"
0x1800e0d7a  mov     edx, 0Bh; unsigned __int64
0x1800e0d7f  lea     rcx, [rbp+5D0h+var_190]; unsigned __int16 *
0x1800e0d86  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800e0d8b  mov     ebx, eax
0x1800e0d8d  test    eax, eax
0x1800e0d8f  jns     short loc_1800E0DE2
0x1800e0d91  mov     dword ptr [rsp+6D0h+Description], eax
0x1800e0d95  lea     r9, aFailedToPrintM; "Failed to print marker version to buffe"...
0x1800e0d9c  mov     qword ptr [rsp+6D0h+Timeout], r9
0x1800e0da1  mov     edx, 4C6h
0x1800e0da6  jmp     short loc_1800E0DCB
0x1800e0da8  lea     rax, aFailedToAddMar_0; "Failed to add marker to indicator trans"...
0x1800e0daf  mov     edx, 4BEh
0x1800e0db4  jmp     short loc_1800E0DC2
0x1800e0db6  lea     rax, aFailedToPrintM_0; "Failed to print marker match count to b"...
0x1800e0dbd  mov     edx, 4BBh; bool
0x1800e0dc2  mov     dword ptr [rsp+6D0h+Description], ebx; char *
0x1800e0dc6  mov     qword ptr [rsp+6D0h+Timeout], rax; int
0x1800e0dcb  mov     r8, rsi; unsigned int
0x1800e0dce  mov     r9, rdi; char *
0x1800e0dd1  mov     [rsp+6D0h+IsolationFlags], ebx; char *
0x1800e0dd5  mov     ecx, r13d; this
0x1800e0dd8  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800e0ddd  jmp     loc_1800E1034
0x1800e0de2  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800e0de8  and     eax, r13d
0x1800e0deb  test    al, al
0x1800e0ded  jz      short loc_1800E0E0A
0x1800e0def  mov     [rsp+6D0h+IsolationFlags], ebx
0x1800e0df3  lea     r9, aFailedToPrintM; "Failed to print marker version to buffe"...
0x1800e0dfa  mov     r8, rdi; char *
0x1800e0dfd  mov     rdx, rsi; char *
0x1800e0e00  mov     ecx, 4C6h; unsigned int
0x1800e0e05  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800e0e0a  mov     r9d, r13d; int
0x1800e0e0d  lea     r8, [rbp+5D0h+var_190]; unsigned __int16 *
0x1800e0e14  lea     rdx, aVersion; "Version"
0x1800e0e1b  lea     rcx, [rbp+5D0h+var_600]; this
0x1800e0e1f  call    ?Add@IndicatorWriter@Shared@Compat@Windows@@QEAAJPEBG0H@Z; Windows::Compat::Shared::IndicatorWriter::Add(ushort const *,ushort const *,int)
0x1800e0e24  mov     ebx, eax
0x1800e0e26  test    eax, eax
0x1800e0e28  jns     short loc_1800E0E3A
0x1800e0e2a  mov     dword ptr [rsp+6D0h+Description], eax
0x1800e0e2e  mov     qword ptr [rsp+6D0h+Timeout], r15
0x1800e0e33  mov     edx, 4C9h
0x1800e0e38  jmp     short loc_1800E0DCB
0x1800e0e3a  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800e0e40  and     eax, r13d
0x1800e0e43  test    al, al
0x1800e0e45  jz      short loc_1800E0E5E
0x1800e0e47  mov     [rsp+6D0h+IsolationFlags], ebx
0x1800e0e4b  mov     r9, r15; char *
0x1800e0e4e  mov     r8, rdi; char *
0x1800e0e51  mov     rdx, rsi; char *
0x1800e0e54  mov     ecx, 4C9h; unsigned int
0x1800e0e59  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800e0e5e  lea     rcx, [rbp+5D0h+var_600]
0x1800e0e62  call    ?Write@IndicatorWriter@Shared@Compat@Windows@@QEAAJW4RegistryChecksumType@234@@Z; Windows::Compat::Shared::IndicatorWriter::Write(Windows::Compat::Shared::RegistryChecksumType)
0x1800e0e67  mov     r14d, eax
0x1800e0e6a  test    eax, eax
0x1800e0e6c  jns     loc_1800E0FC9
0x1800e0e72  mov     dword ptr [rsp+6D0h+Description], eax; char *
0x1800e0e76  lea     r9, aFailedToWriteM_4; "Failed to write markers, swallowing: [0"...
0x1800e0e7d  mov     qword ptr [rsp+6D0h+Timeout], r9; int
0x1800e0e82  mov     [rsp+6D0h+IsolationFlags], eax; char *
0x1800e0e86  mov     r9, rdi; char *
0x1800e0e89  mov     r8, rsi; unsigned int
0x1800e0e8c  mov     edx, 4D2h; bool
0x1800e0e91  mov     ecx, r13d; this
  ... truncated ...
```
