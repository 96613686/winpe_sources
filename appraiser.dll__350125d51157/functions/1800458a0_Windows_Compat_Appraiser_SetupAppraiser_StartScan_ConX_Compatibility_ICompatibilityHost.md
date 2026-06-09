# Windows::Compat::Appraiser::SetupAppraiser::StartScan(ConX::Compatibility::ICompatibilityHost *)

- ea: `0x1800458a0`
- end: `0x180046063`
- name: `?StartScan@SetupAppraiser@Appraiser@Compat@Windows@@UEAAXPEAVICompatibilityHost@Compatibility@ConX@@@Z`
- size: `1987`
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
- `0x180013f90`
- `0x180014894`
- `0x1800151f4`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180044094`
- `0x1800458a0`
- `0x1800466a0`
- `0x1800467cc`
- `0x180046908`
- `0x180046cd4`
- `0x1800470f8`
- `0x18021f010`

## import_xrefs

- `KERNEL32!TryEnterCriticalSection` at `0x1800459b6`
- `KERNEL32!TryEnterCriticalSection` at `0x1800459b6`
- `KERNEL32!GetSystemTime` at `0x180045a9f`
- `KERNEL32!GetSystemTime` at `0x180045ba1`
- `KERNEL32!GetSystemTime` at `0x180045d97`
- `KERNEL32!GetSystemTime` at `0x180045f2c`
- `KERNEL32!GetSystemTime` at `0x180045a9f`
- `KERNEL32!GetSystemTime` at `0x180045ba1`
- `KERNEL32!GetSystemTime` at `0x180045d97`
- `KERNEL32!GetSystemTime` at `0x180045f2c`
- `KERNEL32!LeaveCriticalSection` at `0x180046014`
- `KERNEL32!LeaveCriticalSection` at `0x180046014`
- `OLEAUT32!__imp_SysFreeString` at `0x180046033`
- `OLEAUT32!__imp_SysFreeString` at `0x180046033`

## string_xrefs

- `0x180045973`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180045c07`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180045c42`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180045c89`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180045e05`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180045e46`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180045f11`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180045fb0`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180045961`: `Windows::Compat::Appraiser::SetupAppraiser::StartScan`
- `0x180045c00`: `Windows::Compat::Appraiser::SetupAppraiser::StartScan`
- `0x180045c52`: `Windows::Compat::Appraiser::SetupAppraiser::StartScan`
- `0x180045c7d`: `Windows::Compat::Appraiser::SetupAppraiser::StartScan`
- `0x180045df6`: `Windows::Compat::Appraiser::SetupAppraiser::StartScan`
- `0x180045efa`: `Windows::Compat::Appraiser::SetupAppraiser::StartScan`
- `0x180045c36`: `Error reading stored data: [0x%x].`
- `0x180045c72`: `Error reading stored data: [0x%x].`

## pseudocode

```c
void __fastcall Windows::Compat::Appraiser::SetupAppraiser::StartScan(
        Windows::Compat::Appraiser::SetupAppraiser *this,
        struct ConX::Compatibility::ICompatibilityHost *a2)
{
  __int64 v4; // rax
  bool v5; // r12
  unsigned __int16 *v6; // r13
  int v7; // edi
  char v8; // dl
  const char *v9; // rcx
  char v10; // r15
  int v11; // ebx
  volatile signed __int64 *v12; // rcx
  void **v13; // rdx
  int v14; // ebx
  int v15; // r8d
  int v16; // r9d
  volatile signed __int64 *v17; // rcx
  void **v18; // rdx
  int v19; // ebx
  int v20; // r8d
  int v21; // r9d
  int v22; // eax
  int v23; // eax
  volatile signed __int64 *v24; // rcx
  void **v25; // rdx
  int v26; // edi
  int v27; // r8d
  int v28; // r9d
  int v29; // eax
  int v30; // r15d
  volatile signed __int64 *v31; // rcx
  void **v32; // rdx
  int v33; // edi
  int v34; // r8d
  int v35; // r9d
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
  char v47; // [rsp+61h] [rbp-9Fh]
  int v48; // [rsp+64h] [rbp-9Ch] BYREF
  void *v49; // [rsp+68h] [rbp-98h] BYREF
  __int64 v50; // [rsp+70h] [rbp-90h] BYREF
  char v51[8]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v52[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-70h] BYREF
  const size_t *v54; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v55[3]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v56[2]; // [rsp+E0h] [rbp-20h]
  struct _SYSTEMTIME v57; // [rsp+100h] [rbp+0h] BYREF
  struct _SYSTEMTIME v58; // [rsp+110h] [rbp+10h] BYREF
  char v59[144]; // [rsp+120h] [rbp+20h] BYREF
  char v60[144]; // [rsp+1B0h] [rbp+B0h] BYREF

  memset_0(v55, 0, 0x4Cu);
  v4 = *(_QWORD *)a2;
  v5 = 0;
  v46 = 0;
  if ( ((*(__int64 (__fastcall **)(struct ConX::Compatibility::ICompatibilityHost *))(v4 + 8))(a2) & 0x200) != 0 )
  {
    (*(void (__fastcall **)(Windows::Compat::Appraiser::SetupAppraiser *, struct ConX::Compatibility::ICompatibilityHost *))(*(_QWORD *)this + 8LL))(
      this,
      a2);
  }
  else
  {
    v6 = 0;
    v7 = (*(__int64 (__fastcall **)(struct ConX::Compatibility::ICompatibilityHost *))(*(_QWORD *)a2 + 152LL))(a2);
    Windows::Compat::Shared::Telemetry::TelemetryProvider::InitializeCoreProvider(
      (Windows::Compat::Shared::Telemetry::TelemetryProvider *)&APPRAISER_UTC_PROVIDER,
      v7 != 0);
    Windows::Compat::Appraiser::AppraiserSettings::ForcedOptIn = v7 != 0;
    v8 = 100;
    v9 = "Opted in to telemetry";
    if ( !v7 )
    {
      v9 = "Not opted in to telemetry.";
      v8 = 104;
    }
    Windows::Compat::Appraiser::WriteLog(
      0,
      v8,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::StartScan",
      0,
      (int)v9,
      v42);
    Windows::Compat::Appraiser::WriteLog(
      0,
      107,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::StartScan",
      0,
      (int)"StartScan called.",
      v43);
    v10 = 0;
    if ( TryEnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8)) )
    {
      v47 = 1;
      Windows::Compat::Appraiser::SetupAppraiser::UpdateCorrelationVector(a2);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v59);
      v12 = (volatile signed __int64 *)v59;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v12 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v12,
        _InterlockedExchangeAdd64(v12 + 17, 0),
        v60);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v13);
      v14 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        v50 = 0x1000000;
        v49 = v60;
        LOWORD(v48) = (**(__int64 (__fastcall ***)(struct ConX::Compatibility::ICompatibilityHost *))a2)(a2);
        *(_QWORD *)v51 = &szValueBuf;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v52[0] = &v57;
        v57 = SystemTime;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
          v14,
          (unsigned int)&byte_18029F65F,
          v15,
          v16,
          (__int64)v52,
          (__int64)v51,
          (__int64)&v48,
          (__int64)&v50,
          (__int64)&v49);
      }
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v59);
      v17 = (volatile signed __int64 *)v59;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v17 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v17,
        _InterlockedExchangeAdd64(v17 + 17, 0),
        v60);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v18);
      v19 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000002LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000002LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        *(_QWORD *)v51 = 0x1000000;
        v52[0] = v60;
        v50 = (__int64)&szValueBuf;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v49 = &v57;
        v57 = SystemTime;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
          v19,
          (unsigned int)byte_18029F619,
          v20,
          v21,
          (__int64)&v49,
          (__int64)&v50,
          (__int64)v51,
          (__int64)v52);
      }
      Windows::Compat::Appraiser::WriteLog(
        0,
        119,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::StartScan",
        0,
        (int)"Start Scan Called",
        v44);
      v22 = Windows::Compat::Appraiser::PersistedData::Read(
              (Windows::Compat::Appraiser::SetupAppraiser *)((char *)this + 152),
              a2);
      v11 = v22;
      if ( v22 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x7Au,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::StartScan",
            "Error reading stored data: [0x%x].",
            v22);
        v10 = 1;
        Windows::Compat::Appraiser::SetupAppraiser::UpdateSyncId(this);
        RtlStringArray::Clear((Windows::Compat::Appraiser::SetupAppraiser *)((char *)this + 208));
        RtlStringArray::Clear((Windows::Compat::Appraiser::SetupAppraiser *)((char *)this + 264));
        RtlStringArray::Clear((Windows::Compat::Appraiser::SetupAppraiser *)((char *)this + 152));
        memset_0((char *)this + 64, 0, 0x4Cu);
        *((_QWORD *)this + 18) = 0;
        v23 = Windows::Compat::Appraiser::SetupAppraiser::ScanInternal(this, &v46, a2, 0);
        v5 = v46;
        v11 = v23;
      }
      else
      {
        LODWORD(v44) = v22;
        LODWORD(v40) = v22;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          122,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::StartScan",
          v40,
          (int)"Error reading stored data: [0x%x].",
          v44);
      }
    }
    else
    {
      v47 = 0;
      v11 = -2144337870;
    }
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v59);
    v24 = (volatile signed __int64 *)v59;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v24 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v24,
      _InterlockedExchangeAdd64(v24 + 17, 0),
      v60);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v25);
    v26 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000002LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000002LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      *(_QWORD *)v51 = 0x1000000;
      v52[0] = v60;
      v50 = (__int64)&szValueBuf;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v49 = &v57;
      v57 = SystemTime;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        v26,
        (unsigned int)word_18029F572,
        v27,
        v28,
        (__int64)&v49,
        (__int64)&v50,
        (__int64)v51,
        (__int64)v52);
    }
    Windows::Compat::Appraiser::WriteLog(
      0,
      143,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::StartScan",
      0,
      (int)"Start Scan Done",
      v44);
    if ( v10 )
    {
      v29 = Windows::Compat::Appraiser::PersistedData::Save(
              (Windows::Compat::Appraiser::SetupAppraiser *)((char *)this + 152),
              a2);
      v30 = v29;
      if ( v29 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x94u,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::StartScan",
            "Error storing data: [0x%x].",
            v29);
      }
      else
      {
        LODWORD(v45) = v29;
        LODWORD(v41) = v29;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          148,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::StartScan",
          v41,
          (int)"Error storing data: [0x%x].",
          v45);
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v59);
        v31 = (volatile signed __int64 *)v59;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v31 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v31,
          _InterlockedExchangeAdd64(v31 + 17, 0),
          v60);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v32);
        v33 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 > 5u
          && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
        {
          v48 = v30;
          v52[0] = v60;
          LODWORD(v49) = 148;
          *(_QWORD *)v51 = "Windows::Compat::Appraiser::SetupAppraiser::StartScan";
          v50 = (__int64)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
          v54 = &szValueBuf;
          v57 = 0;
          GetSystemTime(&v57);
          *(_QWORD *)&SystemTime.wYear = &v58;
          v58 = v57;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v33,
            (unsigned int)&word_18029F5B6,
            v34,
            v35,
            (__int64)&SystemTime,
            (__int64)&v54,
            (__int64)&v49,
            (__int64)&v50,
            (__int64)v51,
            (__int64)&v48,
            (__int64)v52);
        }
      }
    }
    if ( v47 )
    {
      v36 = *((_OWORD *)this + 5);
      v55[0] = *((_OWORD *)this + 4);
      v37 = *((_OWORD *)this + 6);
      v55[1] = v36;
      v38 = *((_OWORD *)this + 7);
      v55[2] = v37;
      v39 = *(_OWORD *)((char *)this + 124);
      v56[0] = v38;
      *(_OWORD *)((char *)v56 + 12) = v39;
      memset_0((char *)this + 64, 0, 0x4Cu);
      v6 = (unsigned __int16 *)*((_QWORD *)this + 18);
      *((_QWORD *)this + 18) = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    }
    Windows::Compat::Appraiser::SetupAppraiser::WriteScanStatusToHost(
      v5,
      v11,
      a2,
      (struct ConX::Compatibility::ScanStatus *)v55,
      v6);
    SysFreeString(v6);
  }
}

```

## disassembly

```asm
0x1800458a0  mov     [rsp-8+arg_10], rbx
0x1800458a5  push    rbp
0x1800458a6  push    rsi
0x1800458a7  push    rdi
0x1800458a8  push    r12
0x1800458aa  push    r13
0x1800458ac  push    r14
0x1800458ae  push    r15
0x1800458b0  lea     rbp, [rsp-150h]
0x1800458b8  sub     rsp, 250h
0x1800458bf  mov     rax, cs:__security_cookie
0x1800458c6  xor     rax, rsp
0x1800458c9  mov     [rbp+180h+var_40], rax
0x1800458d0  mov     r14, rdx
0x1800458d3  mov     rsi, rcx
0x1800458d6  xor     edx, edx; Val
0x1800458d8  lea     rcx, [rbp+180h+var_1D0]; void *
0x1800458dc  lea     r8d, [rdx+4Ch]; Size
0x1800458e0  call    memset_0
0x1800458e5  mov     rax, [r14]
0x1800458e8  xor     r12b, r12b
0x1800458eb  mov     rcx, r14
0x1800458ee  mov     [rsp+280h+var_220], r12b
0x1800458f3  mov     rax, [rax+8]
0x1800458f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800458fc  bt      eax, 9
0x180045900  jnb     short loc_180045919
0x180045902  mov     rax, [rsi]
0x180045905  mov     rdx, r14
0x180045908  mov     rcx, rsi
0x18004590b  mov     rax, [rax+8]
0x18004590f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045914  jmp     loc_180046039
0x180045919  mov     rax, [r14]
0x18004591c  mov     rcx, r14
0x18004591f  xor     r13d, r13d
0x180045922  mov     rax, [rax+98h]
0x180045929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004592e  test    eax, eax
0x180045930  lea     rcx, ?APPRAISER_UTC_PROVIDER@@3VTelemetryProvider@Telemetry@Shared@Compat@Windows@@A; this
0x180045937  mov     edi, eax
0x180045939  setnz   bl
0x18004593c  mov     dl, bl; bool
0x18004593e  call    ?InitializeCoreProvider@TelemetryProvider@Telemetry@Shared@Compat@Windows@@IEAAX_N@Z; Windows::Compat::Shared::Telemetry::TelemetryProvider::InitializeCoreProvider(bool)
0x180045943  test    edi, edi
0x180045945  mov     cs:?ForcedOptIn@AppraiserSettings@Appraiser@Compat@Windows@@0_NA, bl; bool Windows::Compat::Appraiser::AppraiserSettings::ForcedOptIn
0x18004594b  lea     rax, aNotOptedInToTe; "Not opted in to telemetry."
0x180045952  lea     edx, [r13+64h]
0x180045956  lea     rcx, aOptedInToTelem; "Opted in to telemetry"
0x18004595d  cmovz   rcx, rax
0x180045961  lea     rbx, aWindowsCompatA_125; "Windows::Compat::Appraiser::SetupApprai"...
0x180045968  mov     qword ptr [rsp+280h+var_258], rcx; int
0x18004596d  lea     eax, [rdx+4]
0x180045970  cmovz   edx, eax; bool
0x180045973  lea     r15, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x18004597a  xor     edi, edi
0x18004597c  mov     r9, rbx; char *
0x18004597f  mov     r8, r15; unsigned int
0x180045982  mov     [rsp+280h+var_260], rdi; char *
0x180045987  xor     ecx, ecx; this
0x180045989  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18004598e  lea     rax, aStartscanCalle; "StartScan called."
0x180045995  mov     r9, rbx; char *
0x180045998  mov     qword ptr [rsp+280h+var_258], rax; int
0x18004599d  lea     edx, [rdi+6Bh]; bool
0x1800459a0  mov     r8, r15; unsigned int
0x1800459a3  mov     [rsp+280h+var_260], rdi; char *
0x1800459a8  xor     ecx, ecx; this
0x1800459aa  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800459af  lea     rcx, [rsi+8]; lpCriticalSection
0x1800459b3  mov     r15b, dil
0x1800459b6  call    cs:__imp_TryEnterCriticalSection
0x1800459bc  test    eax, eax
0x1800459be  jnz     short loc_1800459CF
0x1800459c0  mov     [rsp+280h+var_21F], dil
0x1800459c5  mov     ebx, 80300032h
0x1800459ca  jmp     loc_180045CEC
0x1800459cf  mov     rcx, r14; struct ConX::Compatibility::ICompatibilityHost *
0x1800459d2  mov     [rsp+280h+var_21F], 1
0x1800459d7  call    ?UpdateCorrelationVector@SetupAppraiser@Appraiser@Compat@Windows@@CAXPEAVICompatibilityHost@Compatibility@ConX@@@Z; Windows::Compat::Appraiser::SetupAppraiser::UpdateCorrelationVector(ConX::Compatibility::ICompatibilityHost *)
0x1800459dc  lea     rcx, [rbp+180h+var_160]; this
0x1800459e0  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800459e5  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1800459ec  lea     rcx, [rbp+180h+var_160]
0x1800459f0  test    rax, rax
0x1800459f3  mov     rdx, rdi
0x1800459f6  cmovnz  rcx, rax; this
0x1800459fa  lock xadd [rcx+88h], rdx; unsigned __int64
0x180045a03  lea     r8, [rbp+180h+var_D0]; char *
0x180045a0a  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180045a0f  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, dil; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x180045a16  jz      short loc_180045A24
0x180045a18  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x180045a1f  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x180045a24  mov     rbx, cs:qword_1802C9628
0x180045a2b  mov     eax, [rbx]
0x180045a2d  cmp     eax, 5
0x180045a30  jbe     loc_180045AF6
0x180045a36  mov     rcx, [rbx+18h]
0x180045a3a  mov     rdx, 200000000000h
0x180045a44  mov     rax, [rbx+10h]
0x180045a48  test    rdx, rax
0x180045a4b  jz      loc_180045AF6
0x180045a51  mov     rax, rcx
0x180045a54  and     rax, rdx
0x180045a57  cmp     rax, rcx
0x180045a5a  jnz     loc_180045AF6
0x180045a60  lea     rax, [rbp+180h+var_D0]
0x180045a67  mov     [rsp+280h+var_210], 1000000h
0x180045a70  mov     [rsp+280h+var_218], rax
0x180045a75  mov     rcx, r14
0x180045a78  mov     rax, [r14]
0x180045a7b  mov     rax, [rax]
0x180045a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a83  mov     word ptr [rsp+280h+var_21C], ax
0x180045a88  lea     rcx, [rbp+180h+SystemTime]; lpSystemTime
0x180045a8c  lea     rax, szValueBuf
0x180045a93  xorps   xmm0, xmm0
0x180045a96  mov     qword ptr [rsp+280h+var_208], rax
0x180045a9b  movups  xmmword ptr [rbp+180h+SystemTime.wYear], xmm0
0x180045a9f  call    cs:__imp_GetSystemTime
0x180045aa5  movaps  xmm0, xmmword ptr [rbp+180h+SystemTime.wYear]
0x180045aa9  lea     rax, [rbp+180h+var_180]
0x180045aad  mov     [rbp+180h+var_200], rax
0x180045ab1  lea     rdx, byte_18029F65F
0x180045ab8  lea     rax, [rsp+280h+var_218]
0x180045abd  movdqa  xmmword ptr [rbp+180h+var_180.wYear], xmm0
0x180045ac2  mov     [rsp+280h+var_240], rax
0x180045ac7  mov     rcx, rbx
0x180045aca  lea     rax, [rsp+280h+var_210]
0x180045acf  mov     [rsp+280h+var_248], rax
0x180045ad4  lea     rax, [rsp+280h+var_21C]
0x180045ad9  mov     [rsp+280h+var_250], rax
0x180045ade  lea     rax, [rsp+280h+var_208]
0x180045ae3  mov     qword ptr [rsp+280h+var_258], rax
0x180045ae8  lea     rax, [rbp+180h+var_200]
0x180045aec  mov     [rsp+280h+var_260], rax
0x180045af1  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x180045af6  lea     rcx, [rbp+180h+var_160]; this
0x180045afa  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180045aff  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x180045b06  lea     rcx, [rbp+180h+var_160]
0x180045b0a  test    rax, rax
0x180045b0d  mov     rdx, rdi
0x180045b10  cmovnz  rcx, rax; this
0x180045b14  lock xadd [rcx+88h], rdx; unsigned __int64
0x180045b1d  lea     r8, [rbp+180h+var_D0]; char *
0x180045b24  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180045b29  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, dil; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x180045b30  jz      short loc_180045B3E
0x180045b32  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x180045b39  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x180045b3e  mov     rbx, cs:qword_1802C9628
0x180045b45  mov     eax, [rbx]
0x180045b47  cmp     eax, 5
0x180045b4a  jbe     loc_180045BEF
0x180045b50  mov     rcx, [rbx+18h]
0x180045b54  mov     rdx, 200000000002h
0x180045b5e  mov     rax, [rbx+10h]
0x180045b62  test    rdx, rax
0x180045b65  jz      loc_180045BEF
0x180045b6b  mov     rax, rcx
0x180045b6e  and     rax, rdx
0x180045b71  cmp     rax, rcx
0x180045b74  jnz     short loc_180045BEF
0x180045b76  lea     rax, [rbp+180h+var_D0]
0x180045b7d  mov     qword ptr [rsp+280h+var_208], 1000000h
0x180045b86  mov     [rbp+180h+var_200], rax
0x180045b8a  lea     rcx, [rbp+180h+SystemTime]; lpSystemTime
0x180045b8e  lea     rax, szValueBuf
0x180045b95  xorps   xmm0, xmm0
0x180045b98  mov     [rsp+280h+var_210], rax
0x180045b9d  movups  xmmword ptr [rbp+180h+SystemTime.wYear], xmm0
0x180045ba1  call    cs:__imp_GetSystemTime
0x180045ba7  movaps  xmm0, xmmword ptr [rbp+180h+SystemTime.wYear]
0x180045bab  lea     rax, [rbp+180h+var_180]
0x180045baf  mov     [rsp+280h+var_218], rax
0x180045bb4  lea     rdx, byte_18029F619
0x180045bbb  lea     rax, [rbp+180h+var_200]
0x180045bbf  movdqa  xmmword ptr [rbp+180h+var_180.wYear], xmm0
0x180045bc4  mov     [rsp+280h+var_248], rax
0x180045bc9  mov     rcx, rbx
0x180045bcc  lea     rax, [rsp+280h+var_208]
0x180045bd1  mov     [rsp+280h+var_250], rax; char *
0x180045bd6  lea     rax, [rsp+280h+var_210]
0x180045bdb  mov     qword ptr [rsp+280h+var_258], rax
0x180045be0  lea     rax, [rsp+280h+var_218]
0x180045be5  mov     [rsp+280h+var_260], rax
0x180045bea  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x180045bef  lea     rax, aStartScanCalle; "Start Scan Called"
0x180045bf6  mov     edx, 77h ; 'w'; bool
0x180045bfb  mov     qword ptr [rsp+280h+var_258], rax; int
0x180045c00  lea     r9, aWindowsCompatA_125; "Windows::Compat::Appraiser::SetupApprai"...
0x180045c07  lea     r8, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x180045c0e  mov     [rsp+280h+var_260], rdi; char *
0x180045c13  xor     ecx, ecx; this
0x180045c15  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180045c1a  lea     rdi, [rsi+98h]
0x180045c21  mov     rdx, r14; struct ConX::Compatibility::ICompatibilityHost *
0x180045c24  mov     rcx, rdi; this
0x180045c27  call    ?Read@PersistedData@Appraiser@Compat@Windows@@QEAAJPEAVICompatibilityHost@Compatibility@ConX@@@Z; Windows::Compat::Appraiser::PersistedData::Read(ConX::Compatibility::ICompatibilityHost *)
0x180045c2c  mov     ebx, eax
0x180045c2e  test    eax, eax
0x180045c30  jns     short loc_180045C68
0x180045c32  mov     dword ptr [rsp+280h+var_250], eax; char *
0x180045c36  lea     r9, aErrorReadingSt; "Error reading stored data: [0x%x]."
0x180045c3d  mov     qword ptr [rsp+280h+var_258], r9; int
0x180045c42  lea     r8, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x180045c49  mov     edx, 7Ah ; 'z'; bool
0x180045c4e  mov     dword ptr [rsp+280h+var_260], eax; char *
0x180045c52  lea     r9, aWindowsCompatA_125; "Windows::Compat::Appraiser::SetupApprai"...
0x180045c59  lea     ecx, [rdx-79h]; this
0x180045c5c  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180045c61  xor     edi, edi
0x180045c63  jmp     loc_180045CEC
0x180045c68  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180045c6e  test    al, 1
0x180045c70  jz      short loc_180045C95
0x180045c72  lea     r9, aErrorReadingSt; "Error reading stored data: [0x%x]."
0x180045c79  mov     dword ptr [rsp+280h+var_260], ebx
0x180045c7d  lea     r8, aWindowsCompatA_125; "Windows::Compat::Appraiser::SetupApprai"...
0x180045c84  mov     ecx, 7Ah ; 'z'; unsigned int
0x180045c89  lea     rdx, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x180045c90  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180045c95  mov     rcx, rsi; this
0x180045c98  mov     r15b, 1
0x180045c9b  call    ?UpdateSyncId@SetupAppraiser@Appraiser@Compat@Windows@@AEAAXXZ; Windows::Compat::Appraiser::SetupAppraiser::UpdateSyncId(void)
0x180045ca0  lea     rcx, [rdi+38h]; this
0x180045ca4  call    ?Clear@RtlStringArray@@QEAAXXZ; RtlStringArray::Clear(void)
0x180045ca9  lea     rcx, [rdi+70h]; this
0x180045cad  call    ?Clear@RtlStringArray@@QEAAXXZ; RtlStringArray::Clear(void)
0x180045cb2  mov     rcx, rdi; this
0x180045cb5  call    ?Clear@RtlStringArray@@QEAAXXZ; RtlStringArray::Clear(void)
0x180045cba  xor     edx, edx; Val
0x180045cbc  lea     rcx, [rsi+40h]; void *
0x180045cc0  lea     r8d, [rdx+4Ch]; Size
0x180045cc4  call    memset_0
0x180045cc9  xor     edi, edi
0x180045ccb  lea     rdx, [rsp+280h+var_220]; bool *
0x180045cd0  xor     r9d, r9d; bool
0x180045cd3  mov     [rsi+90h], rdi
0x180045cda  mov     r8, r14; struct ConX::Compatibility::ICompatibilityHost *
0x180045cdd  mov     rcx, rsi; this
0x180045ce0  call    ?ScanInternal@SetupAppraiser@Appraiser@Compat@Windows@@AEAAJAEA_NPEAVICompatibilityHost@Compatibility@ConX@@_N@Z; Windows::Compat::Appraiser::SetupAppraiser::ScanInternal(bool &,ConX::Compatibility::ICompatibilityHost *,bool)
0x180045ce5  mov     r12b, [rsp+280h+var_220]
0x180045cea  mov     ebx, eax
0x180045cec  lea     rcx, [rbp+180h+var_160]; this
0x180045cf0  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180045cf5  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x180045cfc  lea     rcx, [rbp+180h+var_160]
0x180045d00  test    rax, rax
0x180045d03  mov     rdx, rdi
0x180045d06  cmovnz  rcx, rax; this
0x180045d0a  lock xadd [rcx+88h], rdx; unsigned __int64
0x180045d13  lea     r8, [rbp+180h+var_D0]; char *
0x180045d1a  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180045d1f  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, dil; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x180045d26  jz      short loc_180045D34
0x180045d28  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x180045d2f  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x180045d34  mov     rdi, cs:qword_1802C9628
0x180045d3b  mov     eax, [rdi]
0x180045d3d  cmp     eax, 5
0x180045d40  jbe     loc_180045DE5
0x180045d46  mov     rcx, [rdi+18h]
0x180045d4a  mov     rdx, 200000000002h
0x180045d54  mov     rax, [rdi+10h]
0x180045d58  test    rdx, rax
0x180045d5b  jz      loc_180045DE5
0x180045d61  mov     rax, rcx
0x180045d64  and     rax, rdx
0x180045d67  cmp     rax, rcx
0x180045d6a  jnz     short loc_180045DE5
0x180045d6c  lea     rax, [rbp+180h+var_D0]
0x180045d73  mov     qword ptr [rsp+280h+var_208], 1000000h
0x180045d7c  mov     [rbp+180h+var_200], rax
0x180045d80  lea     rcx, [rbp+180h+SystemTime]; lpSystemTime
0x180045d84  lea     rax, szValueBuf
0x180045d8b  xorps   xmm0, xmm0
0x180045d8e  mov     [rsp+280h+var_210], rax
0x180045d93  movups  xmmword ptr [rbp+180h+SystemTime.wYear], xmm0
0x180045d97  call    cs:__imp_GetSystemTime
0x180045d9d  movaps  xmm0, xmmword ptr [rbp+180h+SystemTime.wYear]
0x180045da1  lea     rax, [rbp+180h+var_180]
0x180045da5  mov     [rsp+280h+var_218], rax
0x180045daa  lea     rdx, word_18029F572
0x180045db1  lea     rax, [rbp+180h+var_200]
0x180045db5  movdqa  xmmword ptr [rbp+180h+var_180.wYear], xmm0
0x180045dba  mov     [rsp+280h+var_248], rax
0x180045dbf  mov     rcx, rdi
0x180045dc2  lea     rax, [rsp+280h+var_208]
0x180045dc7  mov     [rsp+280h+var_250], rax; char *
0x180045dcc  lea     rax, [rsp+280h+var_210]
0x180045dd1  mov     qword ptr [rsp+280h+var_258], rax
0x180045dd6  lea     rax, [rsp+280h+var_218]
0x180045ddb  mov     [rsp+280h+var_260], rax
0x180045de0  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x180045de5  lea     rax, aStartScanDone; "Start Scan Done"
0x180045dec  mov     edx, 8Fh; bool
0x180045df1  mov     qword ptr [rsp+280h+var_258], rax; int
  ... truncated ...
```
