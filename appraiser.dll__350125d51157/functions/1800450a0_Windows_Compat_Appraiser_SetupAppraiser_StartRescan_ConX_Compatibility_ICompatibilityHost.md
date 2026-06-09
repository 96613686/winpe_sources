# Windows::Compat::Appraiser::SetupAppraiser::StartRescan(ConX::Compatibility::ICompatibilityHost *)

- ea: `0x1800450a0`
- end: `0x180045892`
- name: `?StartRescan@SetupAppraiser@Appraiser@Compat@Windows@@UEAAXPEAVICompatibilityHost@Compatibility@ConX@@@Z`
- size: `2034`
- prototype: `void __fastcall(Windows::Compat::Appraiser::SetupAppraiser *__hidden this, struct ConX::Compatibility::ICompatibilityHost *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000147c`
- `0x1800018a0`
- `0x180001cc0`
- `0x180008570`
- `0x1800092dc`
- `0x180013c7c`
- `0x180014894`
- `0x1800151f4`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180041020`
- `0x180044094`
- `0x1800450a0`
- `0x1800466a0`
- `0x1800467cc`
- `0x180046908`
- `0x180046cd4`
- `0x1800470f8`
- `0x18021f010`

## import_xrefs

- `KERNEL32!TryEnterCriticalSection` at `0x18004518a`
- `KERNEL32!TryEnterCriticalSection` at `0x18004518a`
- `KERNEL32!GetSystemTime` at `0x180045285`
- `KERNEL32!GetSystemTime` at `0x180045387`
- `KERNEL32!GetSystemTime` at `0x1800455ce`
- `KERNEL32!GetSystemTime` at `0x18004575d`
- `KERNEL32!GetSystemTime` at `0x180045285`
- `KERNEL32!GetSystemTime` at `0x180045387`
- `KERNEL32!GetSystemTime` at `0x1800455ce`
- `KERNEL32!GetSystemTime` at `0x18004575d`
- `KERNEL32!LeaveCriticalSection` at `0x180045842`
- `KERNEL32!LeaveCriticalSection` at `0x180045842`
- `OLEAUT32!__imp_SysFreeString` at `0x180045862`
- `OLEAUT32!__imp_SysFreeString` at `0x180045862`

## string_xrefs

- `0x180045145`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x1800453ed`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18004542e`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180045476`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18004549a`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x1800454f7`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18004563c`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18004567c`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x1800457e0`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x1800454c4`: `Error reading stored data: [0x%x].`
- `0x1800454e0`: `Error reading stored data: [0x%x].`
- `0x180045133`: `Windows::Compat::Appraiser::SetupAppraiser::StartRescan`
- `0x1800453e6`: `Windows::Compat::Appraiser::SetupAppraiser::StartRescan`
- `0x18004543f`: `Windows::Compat::Appraiser::SetupAppraiser::StartRescan`
- `0x18004546a`: `Windows::Compat::Appraiser::SetupAppraiser::StartRescan`
- `0x180045493`: `Windows::Compat::Appraiser::SetupAppraiser::StartRescan`
- `0x1800454eb`: `Windows::Compat::Appraiser::SetupAppraiser::StartRescan`
- `0x18004562d`: `Windows::Compat::Appraiser::SetupAppraiser::StartRescan`
- `0x180045732`: `Windows::Compat::Appraiser::SetupAppraiser::StartRescan`

## pseudocode

```c
void __fastcall Windows::Compat::Appraiser::SetupAppraiser::StartRescan(
        Windows::Compat::Appraiser::SetupAppraiser *this,
        struct ConX::Compatibility::ICompatibilityHost *a2)
{
  __int64 v4; // rax
  unsigned __int16 *v5; // r15
  int v6; // edi
  char v7; // dl
  const char *v8; // rcx
  char v9; // r13
  char v10; // r12
  int v11; // ebx
  volatile signed __int64 *v12; // rcx
  void **v13; // rdx
  __int64 v14; // rbx
  __int64 v15; // r8
  __int64 v16; // r9
  volatile signed __int64 *v17; // rcx
  void **v18; // rdx
  __int64 v19; // rbx
  __int64 v20; // r8
  __int64 v21; // r9
  int v22; // eax
  const char *v23; // r9
  char v24; // dl
  volatile signed __int64 *v25; // rcx
  void **v26; // rdx
  __int64 v27; // rdi
  __int64 v28; // r8
  __int64 v29; // r9
  int v30; // eax
  volatile signed __int64 *v31; // rcx
  void **v32; // rdx
  __int64 v33; // rdi
  __int64 v34; // r8
  __int64 v35; // r9
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  char *v40; // [rsp+20h] [rbp-E0h]
  char *v41; // [rsp+20h] [rbp-E0h]
  char *v42; // [rsp+30h] [rbp-D0h]
  char *v43; // [rsp+30h] [rbp-D0h]
  char *v44; // [rsp+30h] [rbp-D0h]
  char *v45; // [rsp+30h] [rbp-D0h]
  bool v46; // [rsp+60h] [rbp-A0h] BYREF
  int v47; // [rsp+64h] [rbp-9Ch] BYREF
  const char *v48; // [rsp+68h] [rbp-98h] BYREF
  __int64 v49; // [rsp+70h] [rbp-90h] BYREF
  char v50[8]; // [rsp+78h] [rbp-88h] BYREF
  const char *v51[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-70h] BYREF
  const size_t *v53; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v54[3]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v55[2]; // [rsp+E0h] [rbp-20h]
  struct _SYSTEMTIME v56; // [rsp+100h] [rbp+0h] BYREF
  struct _SYSTEMTIME v57; // [rsp+110h] [rbp+10h] BYREF
  char v58[144]; // [rsp+120h] [rbp+20h] BYREF
  char v59[144]; // [rsp+1B0h] [rbp+B0h] BYREF

  memset_0(v54, 0, 0x4Cu);
  v4 = *(_QWORD *)a2;
  v5 = 0;
  v46 = 0;
  v6 = (*(__int64 (__fastcall **)(struct ConX::Compatibility::ICompatibilityHost *))(v4 + 152))(a2);
  Windows::Compat::Shared::Telemetry::TelemetryProvider::InitializeCoreProvider(
    (Windows::Compat::Shared::Telemetry::TelemetryProvider *)&APPRAISER_UTC_PROVIDER,
    v6 != 0);
  v7 = 1;
  Windows::Compat::Appraiser::AppraiserSettings::ForcedOptIn = v6 != 0;
  v8 = "Opted in to telemetry";
  if ( !v6 )
  {
    v8 = "Not opted in to telemetry.";
    v7 = 5;
  }
  Windows::Compat::Appraiser::WriteLog(
    0,
    v7,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
    "Windows::Compat::Appraiser::SetupAppraiser::StartRescan",
    0,
    (int)v8,
    v42);
  Windows::Compat::Appraiser::WriteLog(
    0,
    8,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
    "Windows::Compat::Appraiser::SetupAppraiser::StartRescan",
    0,
    (int)"StartRescan called.",
    v43);
  v9 = 0;
  if ( !TryEnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8)) )
  {
    v10 = 0;
    v11 = -2144337864;
    goto LABEL_33;
  }
  v10 = 1;
  Windows::Compat::Appraiser::SetupAppraiser::UpdateCorrelationVector(a2);
  memset_0((char *)this + 64, 0, 0x4Cu);
  *((_QWORD *)this + 18) = 0;
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v58);
  v12 = (volatile signed __int64 *)v58;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v12 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v12,
    _InterlockedExchangeAdd64(v12 + 17, 0),
    v59);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v13);
  v14 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    v49 = 0x1000000;
    v48 = v59;
    LOWORD(v47) = (**(__int64 (__fastcall ***)(struct ConX::Compatibility::ICompatibilityHost *))a2)(a2);
    *(_QWORD *)v50 = &szValueBuf;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v51[0] = (const char *)&v56;
    v56 = SystemTime;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v14,
      (__int64)word_18029DDFA,
      v15,
      v16,
      (__int64 *)v51,
      (const size_t **)v50,
      (__int64)&v47,
      (__int64)&v49,
      &v48);
  }
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v58);
  v17 = (volatile signed __int64 *)v58;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v17 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v17,
    _InterlockedExchangeAdd64(v17 + 17, 0),
    v59);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v18);
  v19 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000002LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000002LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    *(_QWORD *)v50 = 0x1000000;
    v51[0] = v59;
    v49 = (__int64)&szValueBuf;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v48 = (const char *)&v56;
    v56 = SystemTime;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v19,
      (__int64)byte_18029DD09,
      v20,
      v21,
      (__int64 *)&v48,
      (const size_t **)&v49,
      (__int64)v50,
      v51);
  }
  Windows::Compat::Appraiser::WriteLog(
    0,
    23,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
    "Windows::Compat::Appraiser::SetupAppraiser::StartRescan",
    0,
    (int)"Start Rescan Called",
    v44);
  v22 = Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions(this, 0, a2, 1);
  v11 = v22;
  if ( v22 )
  {
    if ( v22 < 0 )
    {
      v23 = "Error retrieving run options: [0x%x].";
      v24 = 33;
LABEL_24:
      LODWORD(v44) = v11;
      LODWORD(v40) = v11;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v24,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::StartRescan",
        v40,
        (int)v23,
        v44);
      goto LABEL_33;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xE21u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::StartRescan",
        "Error retrieving run options: [0x%x].",
        v22);
    Windows::Compat::Appraiser::WriteLog(
      0,
      34,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::StartRescan",
      0,
      (int)"Rescan categories not applicable to appraiser.",
      v44);
  }
  else
  {
    v11 = Windows::Compat::Appraiser::PersistedData::Read(
            (Windows::Compat::Appraiser::SetupAppraiser *)((char *)this + 152),
            a2);
    if ( v11 < 0 )
    {
      v23 = "Error reading stored data: [0x%x].";
      v24 = 39;
      goto LABEL_24;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xE27u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::StartRescan",
        "Error reading stored data: [0x%x].",
        v11);
    v9 = 1;
    Windows::Compat::Appraiser::SetupAppraiser::UpdateSyncId(this);
    v11 = Windows::Compat::Appraiser::SetupAppraiser::ScanInternal(this, &v46, a2, 1);
  }
LABEL_33:
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v58);
  v25 = (volatile signed __int64 *)v58;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v25 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v25,
    _InterlockedExchangeAdd64(v25 + 17, 0),
    v59);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v26);
  v27 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000002LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000002LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    *(_QWORD *)v50 = 0x1000000;
    v51[0] = v59;
    v49 = (__int64)&szValueBuf;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v48 = (const char *)&v56;
    v56 = SystemTime;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v27,
      (__int64)byte_18029DD51,
      v28,
      v29,
      (__int64 *)&v48,
      (const size_t **)&v49,
      (__int64)v50,
      v51);
  }
  Windows::Compat::Appraiser::WriteLog(
    0,
    48,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
    "Windows::Compat::Appraiser::SetupAppraiser::StartRescan",
    0,
    (int)"Start Rescan Done",
    v44);
  if ( v9 )
  {
    v30 = Windows::Compat::Appraiser::PersistedData::Save(
            (Windows::Compat::Appraiser::SetupAppraiser *)((char *)this + 152),
            a2);
    v11 = v30;
    if ( v30 >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xE35u,
          "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::StartRescan",
          "Error storing data: [0x%x].",
          v30);
    }
    else
    {
      LODWORD(v45) = v30;
      LODWORD(v41) = v30;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        53,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::StartRescan",
        v41,
        (int)"Error storing data: [0x%x].",
        v45);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v58);
      v31 = (volatile signed __int64 *)v58;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v31 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v31,
        _InterlockedExchangeAdd64(v31 + 17, 0),
        v59);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v32);
      v33 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        v47 = v11;
        v51[0] = v59;
        v49 = (__int64)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
        *(_QWORD *)v50 = "Windows::Compat::Appraiser::SetupAppraiser::StartRescan";
        LODWORD(v48) = 3637;
        v53 = &szValueBuf;
        v56 = 0;
        GetSystemTime(&v56);
        *(_QWORD *)&SystemTime.wYear = &v57;
        v57 = v56;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v33,
          (__int64)&byte_18029DC57,
          v34,
          v35,
          (__int64 *)&SystemTime,
          &v53,
          (__int64)&v48,
          (const char **)&v49,
          (const char **)v50,
          (__int64)&v47,
          v51);
      }
    }
  }
  if ( v10 )
  {
    v36 = *((_OWORD *)this + 5);
    v54[0] = *((_OWORD *)this + 4);
    v37 = *((_OWORD *)this + 6);
    v54[1] = v36;
    v38 = *((_OWORD *)this + 7);
    v54[2] = v37;
    v39 = *(_OWORD *)((char *)this + 124);
    v55[0] = v38;
    *(_OWORD *)((char *)v55 + 12) = v39;
    memset_0((char *)this + 64, 0, 0x4Cu);
    v5 = (unsigned __int16 *)*((_QWORD *)this + 18);
    *((_QWORD *)this + 18) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  }
  Windows::Compat::Appraiser::SetupAppraiser::WriteScanStatusToHost(
    v46,
    v11,
    a2,
    (struct ConX::Compatibility::ScanStatus *)v54,
    v5);
  SysFreeString(v5);
}

```

## disassembly

```asm
0x1800450a0  mov     [rsp-8+arg_10], rbx
0x1800450a5  push    rbp
0x1800450a6  push    rsi
0x1800450a7  push    rdi
0x1800450a8  push    r12
0x1800450aa  push    r13
0x1800450ac  push    r14
0x1800450ae  push    r15
0x1800450b0  lea     rbp, [rsp-150h]
0x1800450b8  sub     rsp, 250h
0x1800450bf  mov     rax, cs:__security_cookie
0x1800450c6  xor     rax, rsp
0x1800450c9  mov     [rbp+180h+var_40], rax
0x1800450d0  mov     r14, rdx
0x1800450d3  mov     rsi, rcx
0x1800450d6  xor     edx, edx; Val
0x1800450d8  lea     rcx, [rbp+180h+var_1D0]; void *
0x1800450dc  lea     r8d, [rdx+4Ch]; Size
0x1800450e0  call    memset_0
0x1800450e5  mov     rax, [r14]
0x1800450e8  xor     r15d, r15d
0x1800450eb  mov     rcx, r14
0x1800450ee  mov     [rsp+280h+var_220], r15b
0x1800450f3  mov     rax, [rax+98h]
0x1800450fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800450ff  test    eax, eax
0x180045101  lea     rcx, ?APPRAISER_UTC_PROVIDER@@3VTelemetryProvider@Telemetry@Shared@Compat@Windows@@A; this
0x180045108  mov     edi, eax
0x18004510a  setnz   bl
0x18004510d  mov     dl, bl; bool
0x18004510f  call    ?InitializeCoreProvider@TelemetryProvider@Telemetry@Shared@Compat@Windows@@IEAAX_N@Z; Windows::Compat::Shared::Telemetry::TelemetryProvider::InitializeCoreProvider(bool)
0x180045114  mov     edx, 0E01h
0x180045119  mov     cs:?ForcedOptIn@AppraiserSettings@Appraiser@Compat@Windows@@0_NA, bl; bool Windows::Compat::Appraiser::AppraiserSettings::ForcedOptIn
0x18004511f  test    edi, edi
0x180045121  lea     rax, aNotOptedInToTe; "Not opted in to telemetry."
0x180045128  lea     rcx, aOptedInToTelem; "Opted in to telemetry"
0x18004512f  cmovz   rcx, rax
0x180045133  lea     rbx, aWindowsCompatA_584; "Windows::Compat::Appraiser::SetupApprai"...
0x18004513a  mov     qword ptr [rsp+280h+var_258], rcx; int
0x18004513f  lea     eax, [rdx+4]
0x180045142  cmovz   edx, eax; bool
0x180045145  lea     r12, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x18004514c  xor     edi, edi
0x18004514e  mov     r9, rbx; char *
0x180045151  mov     r8, r12; unsigned int
0x180045154  mov     [rsp+280h+var_260], rdi; char *
0x180045159  xor     ecx, ecx; this
0x18004515b  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180045160  lea     rax, aStartrescanCal; "StartRescan called."
0x180045167  mov     r9, rbx; char *
0x18004516a  mov     qword ptr [rsp+280h+var_258], rax; int
0x18004516f  mov     r8, r12; unsigned int
0x180045172  mov     edx, 0E08h; bool
0x180045177  mov     [rsp+280h+var_260], rdi; char *
0x18004517c  xor     ecx, ecx; this
0x18004517e  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180045183  lea     rcx, [rsi+8]; lpCriticalSection
0x180045187  mov     r13b, dil
0x18004518a  call    cs:__imp_TryEnterCriticalSection
0x180045190  test    eax, eax
0x180045192  jnz     short loc_1800451A1
0x180045194  mov     r12b, dil
0x180045197  mov     ebx, 80300038h
0x18004519c  jmp     loc_180045523
0x1800451a1  mov     rcx, r14; struct ConX::Compatibility::ICompatibilityHost *
0x1800451a4  mov     r12b, 1
0x1800451a7  call    ?UpdateCorrelationVector@SetupAppraiser@Appraiser@Compat@Windows@@CAXPEAVICompatibilityHost@Compatibility@ConX@@@Z; Windows::Compat::Appraiser::SetupAppraiser::UpdateCorrelationVector(ConX::Compatibility::ICompatibilityHost *)
0x1800451ac  xor     edx, edx; Val
0x1800451ae  lea     rcx, [rsi+40h]; void *
0x1800451b2  lea     r8d, [rdx+4Ch]; Size
0x1800451b6  call    memset_0
0x1800451bb  lea     rcx, [rbp+180h+var_160]; this
0x1800451bf  mov     [rsi+90h], rdi
0x1800451c6  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800451cb  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1800451d2  lea     rcx, [rbp+180h+var_160]
0x1800451d6  test    rax, rax
0x1800451d9  mov     rdx, rdi
0x1800451dc  cmovnz  rcx, rax; this
0x1800451e0  lock xadd [rcx+88h], rdx; unsigned __int64
0x1800451e9  lea     r8, [rbp+180h+var_D0]; char *
0x1800451f0  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800451f5  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, dil; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1800451fc  jz      short loc_18004520A
0x1800451fe  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x180045205  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x18004520a  mov     rbx, cs:qword_1802C9628
0x180045211  mov     eax, [rbx]
0x180045213  cmp     eax, 5
0x180045216  jbe     loc_1800452DC
0x18004521c  mov     rcx, [rbx+18h]
0x180045220  mov     rdx, 200000000000h
0x18004522a  mov     rax, [rbx+10h]
0x18004522e  test    rdx, rax
0x180045231  jz      loc_1800452DC
0x180045237  mov     rax, rcx
0x18004523a  and     rax, rdx
0x18004523d  cmp     rax, rcx
0x180045240  jnz     loc_1800452DC
0x180045246  lea     rax, [rbp+180h+var_D0]
0x18004524d  mov     [rsp+280h+var_210], 1000000h
0x180045256  mov     [rsp+280h+var_218], rax
0x18004525b  mov     rcx, r14
0x18004525e  mov     rax, [r14]
0x180045261  mov     rax, [rax]
0x180045264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045269  mov     word ptr [rsp+280h+var_21C], ax
0x18004526e  lea     rcx, [rbp+180h+SystemTime]; lpSystemTime
0x180045272  lea     rax, szValueBuf
0x180045279  xorps   xmm0, xmm0
0x18004527c  mov     qword ptr [rsp+280h+var_208], rax
0x180045281  movups  xmmword ptr [rbp+180h+SystemTime.wYear], xmm0
0x180045285  call    cs:__imp_GetSystemTime
0x18004528b  movaps  xmm0, xmmword ptr [rbp+180h+SystemTime.wYear]
0x18004528f  lea     rax, [rbp+180h+var_180]
0x180045293  mov     [rbp+180h+var_200], rax
0x180045297  lea     rdx, word_18029DDFA
0x18004529e  lea     rax, [rsp+280h+var_218]
0x1800452a3  movdqa  xmmword ptr [rbp+180h+var_180.wYear], xmm0
0x1800452a8  mov     [rsp+280h+var_240], rax
0x1800452ad  mov     rcx, rbx
0x1800452b0  lea     rax, [rsp+280h+var_210]
0x1800452b5  mov     [rsp+280h+var_248], rax
0x1800452ba  lea     rax, [rsp+280h+var_21C]
0x1800452bf  mov     [rsp+280h+var_250], rax
0x1800452c4  lea     rax, [rsp+280h+var_208]
0x1800452c9  mov     qword ptr [rsp+280h+var_258], rax
0x1800452ce  lea     rax, [rbp+180h+var_200]
0x1800452d2  mov     [rsp+280h+var_260], rax
0x1800452d7  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x1800452dc  lea     rcx, [rbp+180h+var_160]; this
0x1800452e0  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800452e5  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1800452ec  lea     rcx, [rbp+180h+var_160]
0x1800452f0  test    rax, rax
0x1800452f3  mov     rdx, rdi
0x1800452f6  cmovnz  rcx, rax; this
0x1800452fa  lock xadd [rcx+88h], rdx; unsigned __int64
0x180045303  lea     r8, [rbp+180h+var_D0]; char *
0x18004530a  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18004530f  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, dil; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x180045316  jz      short loc_180045324
0x180045318  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x18004531f  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x180045324  mov     rbx, cs:qword_1802C9628
0x18004532b  mov     eax, [rbx]
0x18004532d  cmp     eax, 5
0x180045330  jbe     loc_1800453D5
0x180045336  mov     rcx, [rbx+18h]
0x18004533a  mov     rdx, 200000000002h
0x180045344  mov     rax, [rbx+10h]
0x180045348  test    rdx, rax
0x18004534b  jz      loc_1800453D5
0x180045351  mov     rax, rcx
0x180045354  and     rax, rdx
0x180045357  cmp     rax, rcx
0x18004535a  jnz     short loc_1800453D5
0x18004535c  lea     rax, [rbp+180h+var_D0]
0x180045363  mov     qword ptr [rsp+280h+var_208], 1000000h
0x18004536c  mov     [rbp+180h+var_200], rax
0x180045370  lea     rcx, [rbp+180h+SystemTime]; lpSystemTime
0x180045374  lea     rax, szValueBuf
0x18004537b  xorps   xmm0, xmm0
0x18004537e  mov     [rsp+280h+var_210], rax
0x180045383  movups  xmmword ptr [rbp+180h+SystemTime.wYear], xmm0
0x180045387  call    cs:__imp_GetSystemTime
0x18004538d  movaps  xmm0, xmmword ptr [rbp+180h+SystemTime.wYear]
0x180045391  lea     rax, [rbp+180h+var_180]
0x180045395  mov     [rsp+280h+var_218], rax
0x18004539a  lea     rdx, byte_18029DD09
0x1800453a1  lea     rax, [rbp+180h+var_200]
0x1800453a5  movdqa  xmmword ptr [rbp+180h+var_180.wYear], xmm0
0x1800453aa  mov     [rsp+280h+var_248], rax
0x1800453af  mov     rcx, rbx
0x1800453b2  lea     rax, [rsp+280h+var_208]
0x1800453b7  mov     [rsp+280h+var_250], rax; char *
0x1800453bc  lea     rax, [rsp+280h+var_210]
0x1800453c1  mov     qword ptr [rsp+280h+var_258], rax
0x1800453c6  lea     rax, [rsp+280h+var_218]
0x1800453cb  mov     [rsp+280h+var_260], rax
0x1800453d0  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x1800453d5  lea     rax, aStartRescanCal; "Start Rescan Called"
0x1800453dc  mov     edx, 0E17h; bool
0x1800453e1  mov     qword ptr [rsp+280h+var_258], rax; int
0x1800453e6  lea     r9, aWindowsCompatA_584; "Windows::Compat::Appraiser::SetupApprai"...
0x1800453ed  lea     r8, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800453f4  mov     [rsp+280h+var_260], rdi; char *
0x1800453f9  xor     ecx, ecx; this
0x1800453fb  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180045400  mov     r9b, r12b; bool
0x180045403  mov     r8, r14; struct ConX::Compatibility::ICompatibilityHost *
0x180045406  xor     edx, edx; struct Windows::Compat::Appraiser::RunOptions *
0x180045408  mov     rcx, rsi; this
0x18004540b  call    ?InitializeRunOptions@SetupAppraiser@Appraiser@Compat@Windows@@AEAAJPEAURunOptions@234@PEAVICompatibilityHost@Compatibility@ConX@@_N@Z; Windows::Compat::Appraiser::SetupAppraiser::InitializeRunOptions(Windows::Compat::Appraiser::RunOptions *,ConX::Compatibility::ICompatibilityHost *,bool)
0x180045410  mov     ebx, eax
0x180045412  test    eax, eax
0x180045414  jz      loc_1800454AF
0x18004541a  test    eax, eax
0x18004541c  jns     short loc_180045454
0x18004541e  lea     r9, aErrorRetrievin; "Error retrieving run options: [0x%x]."
0x180045425  mov     edx, 0E21h; bool
0x18004542a  mov     dword ptr [rsp+280h+var_250], ebx; char *
0x18004542e  lea     r8, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x180045435  mov     qword ptr [rsp+280h+var_258], r9; int
0x18004543a  mov     ecx, 1; this
0x18004543f  lea     r9, aWindowsCompatA_584; "Windows::Compat::Appraiser::SetupApprai"...
0x180045446  mov     dword ptr [rsp+280h+var_260], ebx; char *
0x18004544a  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18004544f  jmp     loc_180045523
0x180045454  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18004545a  test    r12b, al
0x18004545d  jz      short loc_180045482
0x18004545f  lea     r9, aErrorRetrievin; "Error retrieving run options: [0x%x]."
0x180045466  mov     dword ptr [rsp+280h+var_260], ebx
0x18004546a  lea     r8, aWindowsCompatA_584; "Windows::Compat::Appraiser::SetupApprai"...
0x180045471  mov     ecx, 0E21h; unsigned int
0x180045476  lea     rdx, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x18004547d  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180045482  lea     rax, aRescanCategori; "Rescan categories not applicable to app"...
0x180045489  mov     edx, 0E22h; bool
0x18004548e  mov     qword ptr [rsp+280h+var_258], rax; int
0x180045493  lea     r9, aWindowsCompatA_584; "Windows::Compat::Appraiser::SetupApprai"...
0x18004549a  lea     r8, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800454a1  mov     [rsp+280h+var_260], rdi; char *
0x1800454a6  xor     ecx, ecx; this
0x1800454a8  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800454ad  jmp     short loc_180045523
0x1800454af  lea     rcx, [rsi+98h]; this
0x1800454b6  mov     rdx, r14; struct ConX::Compatibility::ICompatibilityHost *
0x1800454b9  call    ?Read@PersistedData@Appraiser@Compat@Windows@@QEAAJPEAVICompatibilityHost@Compatibility@ConX@@@Z; Windows::Compat::Appraiser::PersistedData::Read(ConX::Compatibility::ICompatibilityHost *)
0x1800454be  mov     ebx, eax
0x1800454c0  test    eax, eax
0x1800454c2  jns     short loc_1800454D5
0x1800454c4  lea     r9, aErrorReadingSt; "Error reading stored data: [0x%x]."
0x1800454cb  mov     edx, 0E27h
0x1800454d0  jmp     loc_18004542A
0x1800454d5  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800454db  test    r12b, al
0x1800454de  jz      short loc_180045503
0x1800454e0  lea     r9, aErrorReadingSt; "Error reading stored data: [0x%x]."
0x1800454e7  mov     dword ptr [rsp+280h+var_260], ebx
0x1800454eb  lea     r8, aWindowsCompatA_584; "Windows::Compat::Appraiser::SetupApprai"...
0x1800454f2  mov     ecx, 0E27h; unsigned int
0x1800454f7  lea     rdx, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800454fe  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180045503  mov     rcx, rsi; this
0x180045506  mov     r13b, r12b
0x180045509  call    ?UpdateSyncId@SetupAppraiser@Appraiser@Compat@Windows@@AEAAXXZ; Windows::Compat::Appraiser::SetupAppraiser::UpdateSyncId(void)
0x18004550e  mov     r9b, r12b; bool
0x180045511  lea     rdx, [rsp+280h+var_220]; bool *
0x180045516  mov     r8, r14; struct ConX::Compatibility::ICompatibilityHost *
0x180045519  mov     rcx, rsi; this
0x18004551c  call    ?ScanInternal@SetupAppraiser@Appraiser@Compat@Windows@@AEAAJAEA_NPEAVICompatibilityHost@Compatibility@ConX@@_N@Z; Windows::Compat::Appraiser::SetupAppraiser::ScanInternal(bool &,ConX::Compatibility::ICompatibilityHost *,bool)
0x180045521  mov     ebx, eax
0x180045523  lea     rcx, [rbp+180h+var_160]; this
0x180045527  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x18004552c  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x180045533  lea     rcx, [rbp+180h+var_160]
0x180045537  test    rax, rax
0x18004553a  mov     rdx, rdi
0x18004553d  cmovnz  rcx, rax; this
0x180045541  lock xadd [rcx+88h], rdx; unsigned __int64
0x18004554a  lea     r8, [rbp+180h+var_D0]; char *
0x180045551  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180045556  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, dil; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x18004555d  jz      short loc_18004556B
0x18004555f  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x180045566  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x18004556b  mov     rdi, cs:qword_1802C9628
0x180045572  mov     eax, [rdi]
0x180045574  cmp     eax, 5
0x180045577  jbe     loc_18004561C
0x18004557d  mov     rcx, [rdi+18h]
0x180045581  mov     rdx, 200000000002h
0x18004558b  mov     rax, [rdi+10h]
0x18004558f  test    rdx, rax
0x180045592  jz      loc_18004561C
0x180045598  mov     rax, rcx
0x18004559b  and     rax, rdx
0x18004559e  cmp     rax, rcx
0x1800455a1  jnz     short loc_18004561C
0x1800455a3  lea     rax, [rbp+180h+var_D0]
0x1800455aa  mov     qword ptr [rsp+280h+var_208], 1000000h
0x1800455b3  mov     [rbp+180h+var_200], rax
0x1800455b7  lea     rcx, [rbp+180h+SystemTime]; lpSystemTime
0x1800455bb  lea     rax, szValueBuf
0x1800455c2  xorps   xmm0, xmm0
0x1800455c5  mov     [rsp+280h+var_210], rax
0x1800455ca  movups  xmmword ptr [rbp+180h+SystemTime.wYear], xmm0
0x1800455ce  call    cs:__imp_GetSystemTime
0x1800455d4  movaps  xmm0, xmmword ptr [rbp+180h+SystemTime.wYear]
0x1800455d8  lea     rax, [rbp+180h+var_180]
0x1800455dc  mov     [rsp+280h+var_218], rax
0x1800455e1  lea     rdx, byte_18029DD51
0x1800455e8  lea     rax, [rbp+180h+var_200]
0x1800455ec  movdqa  xmmword ptr [rbp+180h+var_180.wYear], xmm0
0x1800455f1  mov     [rsp+280h+var_248], rax
0x1800455f6  mov     rcx, rdi
0x1800455f9  lea     rax, [rsp+280h+var_208]
0x1800455fe  mov     [rsp+280h+var_250], rax; char *
  ... truncated ...
```
