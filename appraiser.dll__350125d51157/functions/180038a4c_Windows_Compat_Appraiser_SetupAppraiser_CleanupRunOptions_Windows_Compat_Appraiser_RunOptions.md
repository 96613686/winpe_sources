# Windows::Compat::Appraiser::SetupAppraiser::CleanupRunOptions(Windows::Compat::Appraiser::RunOptions &)

- ea: `0x180038a4c`
- end: `0x180038f08`
- name: `?CleanupRunOptions@SetupAppraiser@Appraiser@Compat@Windows@@CAXAEAURunOptions@234@@Z`
- size: `1212`
- prototype: `void __fastcall(struct Windows::Compat::Appraiser::RunOptions *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180034754`

## callees

- `0x18000147c`
- `0x180008570`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180038a4c`
- `0x1801b36a4`
- `0x1801fd54c`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x180038be9`
- `KERNEL32!GetSystemTime` at `0x180038d9f`
- `KERNEL32!GetSystemTime` at `0x180038be9`
- `KERNEL32!GetSystemTime` at `0x180038d9f`
- `KERNEL32!GetProcessHeap` at `0x180038e5e`
- `KERNEL32!GetProcessHeap` at `0x180038e83`
- `KERNEL32!GetProcessHeap` at `0x180038ea8`
- `KERNEL32!GetProcessHeap` at `0x180038ecd`
- `KERNEL32!GetProcessHeap` at `0x180038e5e`
- `KERNEL32!GetProcessHeap` at `0x180038e83`
- `KERNEL32!GetProcessHeap` at `0x180038ea8`
- `KERNEL32!GetProcessHeap` at `0x180038ecd`
- `KERNEL32!HeapFree` at `0x180038e6c`
- `KERNEL32!HeapFree` at `0x180038e91`
- `KERNEL32!HeapFree` at `0x180038eb6`
- `KERNEL32!HeapFree` at `0x180038edb`
- `KERNEL32!HeapFree` at `0x180038e6c`
- `KERNEL32!HeapFree` at `0x180038e91`
- `KERNEL32!HeapFree` at `0x180038eb6`
- `KERNEL32!HeapFree` at `0x180038edb`
- `acmigration!AcmEngineDelete` at `0x180038a81`
- `acmigration!AcmEngineDelete` at `0x180038a81`

## string_xrefs

- `0x180038a9d`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180038b17`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180038bbc`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180038c6b`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180038cac`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180038d76`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180038a96`: `Windows::Compat::Appraiser::SetupAppraiser::CleanupRunOptions`
- `0x180038b0b`: `Windows::Compat::Appraiser::SetupAppraiser::CleanupRunOptions`
- `0x180038bb5`: `Windows::Compat::Appraiser::SetupAppraiser::CleanupRunOptions`
- `0x180038c72`: `Windows::Compat::Appraiser::SetupAppraiser::CleanupRunOptions`
- `0x180038c92`: `Windows::Compat::Appraiser::SetupAppraiser::CleanupRunOptions`

## pseudocode

```c
void __fastcall Windows::Compat::Appraiser::SetupAppraiser::CleanupRunOptions(
        struct Windows::Compat::Appraiser::RunOptions *a1)
{
  void *v2; // rcx
  unsigned __int64 v3; // rax
  unsigned __int64 i; // rdi
  void **v5; // rdx
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rcx
  int v8; // eax
  int v9; // r14d
  volatile signed __int64 *v10; // rcx
  void **v11; // rdx
  __int64 v12; // rsi
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // eax
  int v16; // esi
  volatile signed __int64 *v17; // rcx
  void **v18; // rdx
  __int64 v19; // rdi
  __int64 v20; // r8
  __int64 v21; // r9
  void *v22; // rdi
  HANDLE ProcessHeap; // rax
  void *v24; // rdi
  HANDLE v25; // rax
  void *v26; // rdi
  HANDLE v27; // rax
  void *v28; // rdi
  HANDLE v29; // rax
  char *v30; // [rsp+20h] [rbp-E0h]
  char *v31; // [rsp+30h] [rbp-D0h]
  int v32; // [rsp+60h] [rbp-A0h] BYREF
  void *v33; // [rsp+68h] [rbp-98h] BYREF
  char *v34; // [rsp+70h] [rbp-90h] BYREF
  char *v35; // [rsp+78h] [rbp-88h] BYREF
  const char *v36; // [rsp+80h] [rbp-80h] BYREF
  const char *v37; // [rsp+88h] [rbp-78h] BYREF
  const char *v38[2]; // [rsp+90h] [rbp-70h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+A0h] [rbp-60h] BYREF
  struct _SYSTEMTIME v40; // [rsp+B0h] [rbp-50h] BYREF
  char v41[144]; // [rsp+C0h] [rbp-40h] BYREF
  char v42[144]; // [rsp+150h] [rbp+50h] BYREF

  v2 = (void *)*((_QWORD *)a1 + 12);
  if ( v2 )
  {
    AcmEngineDelete(v2);
    *((_QWORD *)a1 + 12) = 0;
  }
  v3 = *((_QWORD *)a1 + 16);
  if ( v3 )
  {
    for ( i = 0; i < v3; ++i )
    {
      v5 = 0;
      if ( i < v3 )
      {
        v34 = 0;
        v6 = *((_QWORD *)a1 + 15) * i;
        if ( !is_mul_ok(*((_QWORD *)a1 + 15), i) || (v7 = *((_QWORD *)a1 + 19), v5 = (void **)(v7 + v6), v7 + v6 < v7) )
          v5 = 0;
      }
      v33 = *v5;
      v8 = Windows::Compat::Appraiser::SdbUtils::SafeReleaseDatabase(&v33);
      v9 = v8;
      if ( v8 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x759u,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::CleanupRunOptions",
            "SetupAppraiser leaked one or more duplicate custom sdb handles [0x%x].",
            v8);
      }
      else
      {
        LODWORD(v31) = v8;
        LODWORD(v30) = v8;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          89,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::CleanupRunOptions",
          v30,
          (int)"SetupAppraiser leaked one or more duplicate custom sdb handles [0x%x].",
          v31);
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v41);
        v10 = (volatile signed __int64 *)v41;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v10 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v10,
          _InterlockedExchangeAdd64(v10 + 17, 0),
          v42);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v11);
        v12 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 > 5u
          && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
        {
          v32 = v9;
          v35 = v42;
          v36 = "Windows::Compat::Appraiser::SetupAppraiser::CleanupRunOptions";
          v37 = "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
          LODWORD(v33) = 1881;
          v38[0] = (const char *)&szValueBuf;
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          v34 = (char *)&v40;
          v40 = SystemTime;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v12,
            (__int64)byte_18029E215,
            v13,
            v14,
            (__int64 *)&v34,
            (const size_t **)v38,
            (__int64)&v33,
            &v37,
            &v36,
            (__int64)&v32,
            (const char **)&v35);
        }
      }
      v3 = *((_QWORD *)a1 + 16);
    }
  }
  v15 = Windows::Compat::Appraiser::SdbUtils::SafeReleaseDatabase((void **)a1 + 13);
  v16 = v15;
  if ( v15 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x75Du,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::CleanupRunOptions",
        "SetupAppraiser leaked one or more duplicate sdb handles [0x%x].",
        v15);
    g_ExpectedAlgorithm = 1;
    g_ExpandCallback = 0;
    g_CompressCallback = 0;
    SdbOfflineRuntimePlatformDataFree();
  }
  else
  {
    LODWORD(v31) = v15;
    LODWORD(v30) = v15;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      93,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CleanupRunOptions",
      v30,
      (int)"SetupAppraiser leaked one or more duplicate sdb handles [0x%x].",
      v31);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v41);
    v17 = (volatile signed __int64 *)v41;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v17 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v17,
      _InterlockedExchangeAdd64(v17 + 17, 0),
      v42);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v18);
    v19 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      LODWORD(v33) = v16;
      v34 = v42;
      v38[0] = "Windows::Compat::Appraiser::SetupAppraiser::CleanupRunOptions";
      v37 = "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
      v32 = 1885;
      v36 = (const char *)&szValueBuf;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v35 = (char *)&v40;
      v40 = SystemTime;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v19,
        (__int64)byte_18029E161,
        v20,
        v21,
        (__int64 *)&v35,
        (const size_t **)&v36,
        (__int64)&v32,
        &v37,
        v38,
        (__int64)&v33,
        (const char **)&v34);
    }
  }
  v22 = (void *)*((_QWORD *)a1 + 6);
  if ( v22 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
    *((_QWORD *)a1 + 6) = 0;
  }
  v24 = (void *)*((_QWORD *)a1 + 5);
  if ( v24 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v24);
    *((_QWORD *)a1 + 5) = 0;
  }
  v26 = (void *)*((_QWORD *)a1 + 7);
  if ( v26 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v26);
    *((_QWORD *)a1 + 7) = 0;
  }
  v28 = (void *)*((_QWORD *)a1 + 9);
  if ( v28 )
  {
    v29 = GetProcessHeap();
    HeapFree(v29, 0, v28);
    *((_QWORD *)a1 + 9) = 0;
  }
}

```

## disassembly

```asm
0x180038a4c  push    rbp
0x180038a4e  push    rbx
0x180038a4f  push    rsi
0x180038a50  push    rdi
0x180038a51  push    r13
0x180038a53  push    r14
0x180038a55  lea     rbp, [rsp-0F8h]
0x180038a5d  sub     rsp, 1F8h
0x180038a64  mov     rax, cs:__security_cookie
0x180038a6b  xor     rax, rsp
0x180038a6e  mov     [rbp+120h+var_40], rax
0x180038a75  mov     rbx, rcx
0x180038a78  mov     rcx, [rcx+60h]
0x180038a7c  test    rcx, rcx
0x180038a7f  jz      short loc_180038A8F
0x180038a81  call    cs:__imp_?AcmEngineDelete@@YAXPEAX@Z; AcmEngineDelete(void *)
0x180038a87  mov     qword ptr [rbx+60h], 0
0x180038a8f  mov     rax, [rbx+80h]
0x180038a96  lea     r14, aWindowsCompatA_661; "Windows::Compat::Appraiser::SetupApprai"...
0x180038a9d  lea     rdi, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x180038aa4  mov     r13, 200000000000h
0x180038aae  test    rax, rax
0x180038ab1  jz      loc_180038CB3
0x180038ab7  xor     edi, edi
0x180038ab9  lea     rsi, aSetupappraiser_1; "SetupAppraiser leaked one or more dupli"...
0x180038ac0  xor     edx, edx
0x180038ac2  cmp     rdi, rax
0x180038ac5  jnb     short loc_180038AEA
0x180038ac7  mov     rax, rdi
0x180038aca  mov     [rsp+220h+var_1B0], rdx
0x180038acf  mul     qword ptr [rbx+78h]
0x180038ad3  test    rdx, rdx
0x180038ad6  jnz     short loc_180038AE8
0x180038ad8  mov     rcx, [rbx+98h]
0x180038adf  lea     rdx, [rcx+rax]
0x180038ae3  cmp     rdx, rcx
0x180038ae6  jnb     short loc_180038AEA
0x180038ae8  xor     edx, edx
0x180038aea  mov     rax, [rdx]
0x180038aed  lea     rcx, [rsp+220h+var_1B8]; void **
0x180038af2  mov     [rsp+220h+var_1B8], rax
0x180038af7  call    ?SafeReleaseDatabase@SdbUtils@Appraiser@Compat@Windows@@SAJAEAPEAX@Z; Windows::Compat::Appraiser::SdbUtils::SafeReleaseDatabase(void * &)
0x180038afc  mov     r14d, eax
0x180038aff  test    eax, eax
0x180038b01  jns     loc_180038C5C
0x180038b07  mov     dword ptr [rsp+220h+var_1F0], eax; char *
0x180038b0b  lea     r9, aWindowsCompatA_661; "Windows::Compat::Appraiser::SetupApprai"...
0x180038b12  mov     qword ptr [rsp+220h+var_1F8], rsi; int
0x180038b17  lea     r8, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x180038b1e  mov     edx, 759h; bool
0x180038b23  mov     dword ptr [rsp+220h+var_200], eax; char *
0x180038b27  mov     ecx, 1; this
0x180038b2c  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180038b31  lea     rcx, [rbp+120h+var_160]; this
0x180038b35  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180038b3a  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x180038b41  lea     rcx, [rbp+120h+var_160]
0x180038b45  test    rax, rax
0x180038b48  cmovnz  rcx, rax; this
0x180038b4c  xor     edx, edx
0x180038b4e  lock xadd [rcx+88h], rdx; unsigned __int64
0x180038b57  lea     r8, [rbp+120h+var_D0]; char *
0x180038b5b  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180038b60  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, 0; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x180038b67  jz      short loc_180038B75
0x180038b69  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x180038b70  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x180038b75  mov     rsi, cs:qword_1802C9628
0x180038b7c  mov     eax, [rsi]
0x180038b7e  cmp     eax, 5
0x180038b81  jbe     loc_180038C8B
0x180038b87  mov     rcx, [rsi+18h]
0x180038b8b  mov     rax, [rsi+10h]
0x180038b8f  test    r13, rax
0x180038b92  jz      loc_180038C8B
0x180038b98  mov     rax, rcx
0x180038b9b  and     rax, r13
0x180038b9e  cmp     rax, rcx
0x180038ba1  jnz     loc_180038C8B
0x180038ba7  lea     rax, [rbp+120h+var_D0]
0x180038bab  mov     [rsp+220h+var_1C0], r14d
0x180038bb0  mov     [rsp+220h+var_1A8], rax
0x180038bb5  lea     r14, aWindowsCompatA_661; "Windows::Compat::Appraiser::SetupApprai"...
0x180038bbc  lea     rax, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x180038bc3  mov     [rbp+120h+var_1A0], r14
0x180038bc7  mov     [rbp+120h+var_198], rax
0x180038bcb  lea     rcx, [rbp+120h+SystemTime]; lpSystemTime
0x180038bcf  lea     rax, szValueBuf
0x180038bd6  mov     dword ptr [rsp+220h+var_1B8], 759h
0x180038bde  xorps   xmm0, xmm0
0x180038be1  mov     [rbp+120h+var_190], rax
0x180038be5  movups  xmmword ptr [rbp+120h+SystemTime.wYear], xmm0
0x180038be9  call    cs:__imp_GetSystemTime
0x180038bef  movaps  xmm0, xmmword ptr [rbp+120h+SystemTime.wYear]
0x180038bf3  lea     rax, [rbp+120h+var_170]
0x180038bf7  mov     [rsp+220h+var_1B0], rax
0x180038bfc  lea     rdx, byte_18029E215
0x180038c03  lea     rax, [rsp+220h+var_1A8]
0x180038c08  movdqa  [rbp+120h+var_170], xmm0
0x180038c0d  mov     [rsp+220h+var_1D0], rax
0x180038c12  mov     rcx, rsi
0x180038c15  lea     rax, [rsp+220h+var_1C0]
0x180038c1a  mov     [rsp+220h+var_1D8], rax
0x180038c1f  lea     rax, [rbp+120h+var_1A0]
0x180038c23  mov     [rsp+220h+var_1E0], rax
0x180038c28  lea     rax, [rbp+120h+var_198]
0x180038c2c  mov     [rsp+220h+var_1E8], rax
0x180038c31  lea     rax, [rsp+220h+var_1B8]
0x180038c36  mov     [rsp+220h+var_1F0], rax
0x180038c3b  lea     rax, [rbp+120h+var_190]
0x180038c3f  mov     qword ptr [rsp+220h+var_1F8], rax
0x180038c44  lea     rax, [rsp+220h+var_1B0]
0x180038c49  mov     [rsp+220h+var_200], rax
0x180038c4e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180038c53  lea     rsi, aSetupappraiser_1; "SetupAppraiser leaked one or more dupli"...
0x180038c5a  jmp     short loc_180038C99
0x180038c5c  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180038c62  test    al, 1
0x180038c64  jz      short loc_180038C92
0x180038c66  mov     dword ptr [rsp+220h+var_200], r14d
0x180038c6b  lea     rdx, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x180038c72  lea     r14, aWindowsCompatA_661; "Windows::Compat::Appraiser::SetupApprai"...
0x180038c79  mov     r9, rsi; char *
0x180038c7c  mov     r8, r14; char *
0x180038c7f  mov     ecx, 759h; unsigned int
0x180038c84  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180038c89  jmp     short loc_180038C99
0x180038c8b  lea     rsi, aSetupappraiser_1; "SetupAppraiser leaked one or more dupli"...
0x180038c92  lea     r14, aWindowsCompatA_661; "Windows::Compat::Appraiser::SetupApprai"...
0x180038c99  mov     rax, [rbx+80h]
0x180038ca0  inc     rdi
0x180038ca3  cmp     rdi, rax
0x180038ca6  jb      loc_180038AC0
0x180038cac  lea     rdi, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x180038cb3  lea     rcx, [rbx+68h]; void **
0x180038cb7  call    ?SafeReleaseDatabase@SdbUtils@Appraiser@Compat@Windows@@SAJAEAPEAX@Z; Windows::Compat::Appraiser::SdbUtils::SafeReleaseDatabase(void * &)
0x180038cbc  mov     esi, eax
0x180038cbe  test    eax, eax
0x180038cc0  jns     loc_180038E0B
0x180038cc6  mov     dword ptr [rsp+220h+var_1F0], eax; char *
0x180038cca  lea     r9, aSetupappraiser_0; "SetupAppraiser leaked one or more dupli"...
0x180038cd1  mov     qword ptr [rsp+220h+var_1F8], r9; int
0x180038cd6  mov     r8, rdi; unsigned int
0x180038cd9  mov     r9, r14; char *
0x180038cdc  mov     dword ptr [rsp+220h+var_200], eax; char *
0x180038ce0  mov     edx, 75Dh; bool
0x180038ce5  mov     ecx, 1; this
0x180038cea  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180038cef  lea     rcx, [rbp+120h+var_160]; this
0x180038cf3  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180038cf8  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x180038cff  lea     rcx, [rbp+120h+var_160]
0x180038d03  test    rax, rax
0x180038d06  cmovnz  rcx, rax; this
0x180038d0a  xor     edx, edx
0x180038d0c  lock xadd [rcx+88h], rdx; unsigned __int64
0x180038d15  lea     r8, [rbp+120h+var_D0]; char *
0x180038d19  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180038d1e  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, 0; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x180038d25  jz      short loc_180038D33
0x180038d27  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x180038d2e  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x180038d33  mov     rdi, cs:qword_1802C9628
0x180038d3a  mov     eax, [rdi]
0x180038d3c  cmp     eax, 5
0x180038d3f  jbe     loc_180038E55
0x180038d45  mov     rcx, [rdi+18h]
0x180038d49  mov     rax, [rdi+10h]
0x180038d4d  test    r13, rax
0x180038d50  jz      loc_180038E55
0x180038d56  mov     rax, rcx
0x180038d59  and     rax, r13
0x180038d5c  cmp     rax, rcx
0x180038d5f  jnz     loc_180038E55
0x180038d65  lea     rax, [rbp+120h+var_D0]
0x180038d69  mov     dword ptr [rsp+220h+var_1B8], esi
0x180038d6d  mov     [rsp+220h+var_1B0], rax
0x180038d72  lea     rcx, [rbp+120h+SystemTime]; lpSystemTime
0x180038d76  lea     rax, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x180038d7d  mov     [rbp+120h+var_190], r14
0x180038d81  mov     [rbp+120h+var_198], rax
0x180038d85  xorps   xmm0, xmm0
0x180038d88  lea     rax, szValueBuf
0x180038d8f  mov     [rsp+220h+var_1C0], 75Dh
0x180038d97  mov     [rbp+120h+var_1A0], rax
0x180038d9b  movups  xmmword ptr [rbp+120h+SystemTime.wYear], xmm0
0x180038d9f  call    cs:__imp_GetSystemTime
0x180038da5  movaps  xmm0, xmmword ptr [rbp+120h+SystemTime.wYear]
0x180038da9  lea     rax, [rbp+120h+var_170]
0x180038dad  mov     [rsp+220h+var_1A8], rax
0x180038db2  lea     rdx, byte_18029E161
0x180038db9  lea     rax, [rsp+220h+var_1B0]
0x180038dbe  movdqa  [rbp+120h+var_170], xmm0
0x180038dc3  mov     [rsp+220h+var_1D0], rax
0x180038dc8  mov     rcx, rdi
0x180038dcb  lea     rax, [rsp+220h+var_1B8]
0x180038dd0  mov     [rsp+220h+var_1D8], rax
0x180038dd5  lea     rax, [rbp+120h+var_190]
0x180038dd9  mov     [rsp+220h+var_1E0], rax
0x180038dde  lea     rax, [rbp+120h+var_198]
0x180038de2  mov     [rsp+220h+var_1E8], rax
0x180038de7  lea     rax, [rsp+220h+var_1C0]
0x180038dec  mov     [rsp+220h+var_1F0], rax
0x180038df1  lea     rax, [rbp+120h+var_1A0]
0x180038df5  mov     qword ptr [rsp+220h+var_1F8], rax
0x180038dfa  lea     rax, [rsp+220h+var_1A8]
0x180038dff  mov     [rsp+220h+var_200], rax
0x180038e04  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180038e09  jmp     short loc_180038E55
0x180038e0b  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180038e11  test    al, 1
0x180038e13  jz      short loc_180038E30
0x180038e15  lea     r9, aSetupappraiser_0; "SetupAppraiser leaked one or more dupli"...
0x180038e1c  mov     dword ptr [rsp+220h+var_200], esi
0x180038e20  mov     r8, r14; char *
0x180038e23  mov     rdx, rdi; char *
0x180038e26  mov     ecx, 75Dh; unsigned int
0x180038e2b  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180038e30  mov     cs:g_ExpectedAlgorithm, 1
0x180038e3a  mov     cs:g_ExpandCallback, 0
0x180038e45  mov     cs:g_CompressCallback, 0
0x180038e50  call    SdbOfflineRuntimePlatformDataFree
0x180038e55  mov     rdi, [rbx+30h]
0x180038e59  test    rdi, rdi
0x180038e5c  jz      short loc_180038E7A
0x180038e5e  call    cs:__imp_GetProcessHeap
0x180038e64  mov     r8, rdi; lpMem
0x180038e67  xor     edx, edx; dwFlags
0x180038e69  mov     rcx, rax; hHeap
0x180038e6c  call    cs:__imp_HeapFree
0x180038e72  mov     qword ptr [rbx+30h], 0
0x180038e7a  mov     rdi, [rbx+28h]
0x180038e7e  test    rdi, rdi
0x180038e81  jz      short loc_180038E9F
0x180038e83  call    cs:__imp_GetProcessHeap
0x180038e89  mov     r8, rdi; lpMem
0x180038e8c  xor     edx, edx; dwFlags
0x180038e8e  mov     rcx, rax; hHeap
0x180038e91  call    cs:__imp_HeapFree
0x180038e97  mov     qword ptr [rbx+28h], 0
0x180038e9f  mov     rdi, [rbx+38h]
0x180038ea3  test    rdi, rdi
0x180038ea6  jz      short loc_180038EC4
0x180038ea8  call    cs:__imp_GetProcessHeap
0x180038eae  mov     r8, rdi; lpMem
0x180038eb1  xor     edx, edx; dwFlags
0x180038eb3  mov     rcx, rax; hHeap
0x180038eb6  call    cs:__imp_HeapFree
0x180038ebc  mov     qword ptr [rbx+38h], 0
0x180038ec4  mov     rdi, [rbx+48h]
0x180038ec8  test    rdi, rdi
0x180038ecb  jz      short loc_180038EE9
0x180038ecd  call    cs:__imp_GetProcessHeap
0x180038ed3  mov     r8, rdi; lpMem
0x180038ed6  xor     edx, edx; dwFlags
0x180038ed8  mov     rcx, rax; hHeap
0x180038edb  call    cs:__imp_HeapFree
0x180038ee1  mov     qword ptr [rbx+48h], 0
0x180038ee9  mov     rcx, [rbp+120h+var_40]
0x180038ef0  xor     rcx, rsp; StackCookie
0x180038ef3  call    __security_check_cookie
0x180038ef8  add     rsp, 1F8h
0x180038eff  pop     r14
0x180038f01  pop     r13
0x180038f03  pop     rdi
0x180038f04  pop     rsi
0x180038f05  pop     rbx
0x180038f06  pop     rbp
0x180038f07  retn
```
