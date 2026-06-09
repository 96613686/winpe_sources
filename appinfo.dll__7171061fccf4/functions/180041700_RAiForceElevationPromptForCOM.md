# RAiForceElevationPromptForCOM

- ea: `0x180041700`
- end: `0x180041beb`
- name: `RAiForceElevationPromptForCOM`
- size: `1259`
- prototype: `void __fastcall(struct _RPC_ASYNC_STATE *, void *, unsigned __int64, unsigned int, int, int, unsigned __int16 *, struct _GUID *, wchar_t *Source, wchar_t *, wchar_t *, wchar_t *, unsigned int)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000f3e0`
- `0x180011a30`
- `0x18001aee4`
- `0x18001b408`
- `0x18001e7bc`
- `0x18001e7c8`
- `0x180026f40`
- `0x18002ad54`
- `0x18002b0c0`
- `0x18003b3f0`
- `0x18003bb44`
- `0x180040c60`
- `0x180040d64`
- `0x180041700`
- `0x180042a54`
- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180041b86`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180041b86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041ac0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041ace`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041ac0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041ace`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800417dd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800417dd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800417d3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180041adc`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800417d3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180041adc`
- `ntdll!NtClose` at `0x180041ab3`
- `ntdll!NtClose` at `0x180041ab3`

## string_xrefs

- `0x18004188c`: `hwnd = %x dwRunLevel = %x dwClientFlags = %x fAdjustTokenSD = %x dwTimeout = %x\n	lpDesktop = %ws\n	lpFriendlyName = %ws\n	lpServerBinary = %ws\n	lpIconReference = %ws\n	lpRequestorPath = %ws\n	lpCvStr = %s\n`
- `0x180041893`: `RAiForceElevationPromptForCOM`

## pseudocode

```c
void __fastcall RAiForceElevationPromptForCOM(
        struct _RPC_ASYNC_STATE *a1,
        void *a2,
        unsigned __int64 a3,
        unsigned int a4,
        int a5,
        int a6,
        unsigned __int16 *a7,
        struct _GUID *a8,
        wchar_t *Source,
        wchar_t *a10,
        wchar_t *a11,
        wchar_t *a12,
        unsigned int a13)
{
  unsigned int v13; // edi
  wchar_t *v14; // rbx
  struct _CONSENTUI_PARAM_HEADER *v15; // r15
  const unsigned __int16 *v16; // r14
  const wchar_t *v17; // rdx
  wchar_t *v18; // r8
  unsigned __int16 *v19; // r9
  const wchar_t *v20; // rax
  void *v21; // rax
  volatile signed __int64 *v22; // rdi
  const wchar_t *v23; // r8
  wchar_t *v24; // rdi
  const wchar_t *v25; // rax
  unsigned int v26; // edi
  unsigned int v27; // eax
  unsigned __int64 v28; // rax
  int v29; // eax
  unsigned int v30; // r9d
  unsigned __int64 v31; // r8
  void *v32; // rdx
  unsigned int v33; // eax
  int v34; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v35; // [rsp+28h] [rbp-D8h]
  struct _CONSENTUI_PARAM_HEADER *v36; // [rsp+30h] [rbp-D0h]
  unsigned int v37[2]; // [rsp+38h] [rbp-C8h]
  unsigned int v38; // [rsp+38h] [rbp-C8h]
  int Reply; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v40; // [rsp+74h] [rbp-8Ch] BYREF
  int v41; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v42; // [rsp+7Ch] [rbp-84h]
  int v43; // [rsp+80h] [rbp-80h]
  int v44; // [rsp+84h] [rbp-7Ch] BYREF
  int v45; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp-70h] BYREF
  int v47; // [rsp+98h] [rbp-68h] BYREF
  struct _CONSENTUI_PARAM_HEADER *v48; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE Handle; // [rsp+A8h] [rbp-58h] BYREF
  void *v50; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t *v51; // [rsp+B8h] [rbp-48h]
  wchar_t *v52; // [rsp+C0h] [rbp-40h]
  unsigned __int16 *v53; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v54; // [rsp+D0h] [rbp-30h]
  LARGE_INTEGER v55; // [rsp+D8h] [rbp-28h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+E0h] [rbp-20h] BYREF
  LARGE_INTEGER Frequency; // [rsp+E8h] [rbp-18h] BYREF
  const wchar_t *v58; // [rsp+F0h] [rbp-10h]
  wchar_t *v59; // [rsp+F8h] [rbp-8h]
  unsigned __int16 *v60; // [rsp+100h] [rbp+0h]
  struct _GUID *v61; // [rsp+108h] [rbp+8h]
  wchar_t *v62; // [rsp+110h] [rbp+10h] BYREF
  struct _GUID *v63; // [rsp+118h] [rbp+18h] BYREF
  PRPC_ASYNC_STATE pAsync; // [rsp+120h] [rbp+20h]
  char v65[80]; // [rsp+130h] [rbp+30h] BYREF
  char v66[144]; // [rsp+180h] [rbp+80h] BYREF

  v13 = a3;
  v14 = a12;
  v53 = a7;
  v43 = a6;
  v61 = a8;
  v63 = a8;
  v42 = a13;
  v54 = a3;
  v15 = 0;
  v50 = a2;
  pAsync = a1;
  Reply = 0;
  v48 = 0;
  v45 = 0;
  Handle = 0;
  v44 = 0;
  v41 = 0;
  Frequency.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  v55.QuadPart = 0;
  v40 = a4;
  v52 = a10;
  v51 = a11;
  v47 = a5;
  v62 = Source;
  hMem = a12;
  QueryPerformanceCounter(&PerformanceCount);
  QueryPerformanceFrequency(&Frequency);
  memset_0(v66, 0, 0x81u);
  v16 = L"NULL";
  v17 = a11;
  if ( !a11 )
    v17 = L"NULL";
  v58 = v17;
  v18 = v52;
  if ( !v52 )
    v18 = L"NULL";
  v59 = v18;
  v19 = v53;
  v20 = Source;
  if ( !v53 )
    v19 = L"NULL";
  v60 = v19;
  if ( !Source )
    v20 = L"NULL";
  v37[0] = v42;
  LUATelemetry::WatchCurrentThread(
    v65,
    "RAiForceElevationPromptForCOM",
    "hwnd = %x dwRunLevel = %x dwClientFlags = %x fAdjustTokenSD = %x dwTimeout = %x\n"
    "\tlpDesktop = %ws\n"
    "\tlpFriendlyName = %ws\n"
    "\tlpServerBinary = %ws\n"
    "\tlpIconReference = %ws\n"
    "\tlpRequestorPath = %ws\n"
    "\tlpCvStr = %s\n",
    v13,
    v40,
    a5,
    v43,
    *(_QWORD *)v37,
    v19,
    v20,
    v18,
    v17);
  if ( g_pCOMElevationActivityTelemetryRateLimiter
    && (unsigned int)RateLimiter::RequestPermission(g_pCOMElevationActivityTelemetryRateLimiter) )
  {
    v21 = operator new(0x90u);
    v22 = v21 ? (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v21) : 0LL;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v22,
      _InterlockedExchangeAdd64(v22 + 17, 0),
      v66);
    if ( v22 )
      operator delete((void *)v22);
  }
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
    v24 = Source;
  }
  else
  {
    v23 = L"NULL";
    v24 = Source;
    v25 = Source;
    if ( a12 )
      v23 = a12;
    if ( !Source )
      v25 = L"NULL";
    WPP_SF_DDDDDSSSSSs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      (_DWORD)v59,
      v54,
      v40,
      a5,
      v43,
      v42,
      (__int64)v60,
      (__int64)v25,
      (__int64)v59,
      (__int64)v58,
      (__int64)v23,
      (__int64)v66);
  }
  if ( Source )
    v16 = v24;
  v26 = AiLogPerfTrackEventEx(&AppInfo_PerfTrack_Elevation_COM_Start, v16);
  if ( a12 )
  {
    if ( (a5 & 0x20) != 0 )
    {
      v27 = AiConvertWow64Paths(a12, (const unsigned __int16 **)&hMem, 0, 0, 0, 0);
      v14 = (wchar_t *)hMem;
      Reply = v27;
      if ( v27 )
        goto LABEL_35;
    }
    v28 = -1;
    do
      ++v28;
    while ( v14[v28] );
    if ( v28 > 0x7FFF )
    {
      Reply = 87;
      goto LABEL_35;
    }
  }
  v29 = AiBuildCOMParams(Source, v52, v51, v14, v61, &v48);
  v15 = v48;
  Reply = v29;
  if ( !v29 )
  {
    v30 = v40;
    v31 = v54;
    v32 = v50;
    v38 = v42;
    v36 = v48;
    v35 = v53;
    v45 = 0x2000000;
    v34 = v43;
    *((_DWORD *)v48 + 13) = v26;
    Reply = AipGetTokenForService(
              0,
              v32,
              v31,
              v30,
              v34,
              v35,
              v36,
              v38,
              v14,
              (unsigned __int64 *)&Handle,
              0x2000000u,
              v66,
              (enum UACPROMPT_POLICY *)&v41,
              &v44);
  }
LABEL_35:
  if ( Handle )
  {
    NtClose(Handle);
    Handle = 0;
  }
  LocalFree(v15);
  if ( v14 != a12 )
  {
    LocalFree(v14);
    hMem = a12;
  }
  QueryPerformanceCounter(&v55);
  v50 = (void *)(1000 * (v55.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart);
  v33 = Reply;
  if ( Reply == 1223 )
  {
    v33 = 0;
  }
  else if ( Reply > 0 )
  {
    v33 = (unsigned __int16)Reply | 0x80070000;
  }
  v40 = v33;
  LUATelemetry::COMElevation<long,unsigned long &,unsigned long &,unsigned long &,_GUID * &,unsigned short const * &,unsigned short const * &,int &,unsigned long,__int64 &,char (&)[129]>(
    (unsigned int)&v40,
    (unsigned int)&Reply,
    (unsigned int)&v45,
    (unsigned int)&v47,
    (__int64)&v63,
    (__int64)&hMem,
    (__int64)&v62,
    (__int64)&v44,
    (__int64)&v41,
    (__int64)&v50,
    v66);
  RpcAsyncCompleteCall(pAsync, &Reply);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_aba5399977573c9264c162bacbfc9302_Traceguids,
      (unsigned int)Reply);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v65);
}

```

## disassembly

```asm
0x180041700  push    rbp
0x180041702  push    rbx
0x180041703  push    rsi
0x180041704  push    rdi
0x180041705  push    r12
0x180041707  push    r13
0x180041709  push    r14
0x18004170b  push    r15
0x18004170d  lea     rbp, [rsp-128h]
0x180041715  sub     rsp, 228h
0x18004171c  mov     rax, cs:__security_cookie
0x180041723  xor     rax, rsp
0x180041726  mov     [rbp+160h+var_50], rax
0x18004172d  mov     rax, [rbp+160h+arg_30]
0x180041734  mov     rdi, r8
0x180041737  mov     r12, [rbp+160h+arg_58]
0x18004173e  mov     rsi, [rbp+160h+Source]
0x180041745  mov     rbx, r12
0x180041748  mov     r13d, [rbp+160h+arg_20]
0x18004174f  mov     [rbp+160h+var_198], rax
0x180041753  mov     eax, [rbp+160h+arg_28]
0x180041759  mov     [rbp+160h+var_1E0], eax
0x18004175c  mov     rax, [rbp+160h+arg_38]
0x180041763  mov     [rbp+160h+var_158], rax
0x180041767  mov     [rbp+160h+var_148], rax
0x18004176b  mov     eax, [rbp+160h+arg_60]
0x180041771  mov     [rsp+260h+var_1E4], eax
0x180041775  xor     eax, eax
0x180041777  mov     [rbp+160h+var_190], r8
0x18004177b  mov     r15d, eax
0x18004177e  mov     r8, [rbp+160h+arg_50]
0x180041785  mov     [rbp+160h+var_1B0], rdx
0x180041789  mov     rdx, [rbp+160h+arg_48]
0x180041790  mov     [rbp+160h+pAsync], rcx
0x180041794  lea     rcx, [rbp+160h+PerformanceCount]; lpPerformanceCount
0x180041798  mov     [rsp+260h+Reply], eax
0x18004179c  mov     [rbp+160h+var_1C0], rax
0x1800417a0  mov     [rbp+160h+var_1D8], eax
0x1800417a3  mov     [rbp+160h+Handle], rax
0x1800417a7  mov     [rbp+160h+var_1DC], eax
0x1800417aa  mov     [rsp+260h+var_1E8], eax
0x1800417ae  mov     qword ptr [rbp+160h+Frequency], rax
0x1800417b2  mov     qword ptr [rbp+160h+PerformanceCount], rax
0x1800417b6  mov     qword ptr [rbp+160h+var_188], rax
0x1800417ba  mov     [rsp+260h+var_1EC], r9d
0x1800417bf  mov     [rbp+160h+var_1A0], rdx
0x1800417c3  mov     [rbp+160h+var_1A8], r8
0x1800417c7  mov     [rbp+160h+var_1C8], r13d
0x1800417cb  mov     [rbp+160h+var_150], rsi
0x1800417cf  mov     [rbp+160h+hMem], rbx
0x1800417d3  call    cs:__imp_QueryPerformanceCounter
0x1800417d9  lea     rcx, [rbp+160h+Frequency]; lpFrequency
0x1800417dd  call    cs:__imp_QueryPerformanceFrequency
0x1800417e3  xor     edx, edx; Val
0x1800417e5  lea     rcx, [rbp+160h+var_E0]; void *
0x1800417ec  mov     r8d, 81h; Size
0x1800417f2  call    memset_0
0x1800417f7  mov     rax, [rbp+160h+var_1A8]
0x1800417fb  lea     r14, aNull_0; "NULL"
0x180041802  test    rax, rax
0x180041805  lea     r10, [rbp+160h+var_E0]
0x18004180c  mov     [rsp+260h+var_1F8], r10
0x180041811  mov     rdx, rax
0x180041814  mov     rax, [rbp+160h+var_1A0]
0x180041818  cmovz   rdx, r14
0x18004181c  test    rax, rax
0x18004181f  mov     [rbp+160h+var_170], rdx
0x180041823  mov     r8, rax
0x180041826  mov     rcx, r12
0x180041829  mov     rax, [rbp+160h+var_198]
0x18004182d  cmovz   r8, r14
0x180041831  test    rax, rax
0x180041834  mov     [rbp+160h+var_168], r8
0x180041838  mov     r9, rax
0x18004183b  mov     rax, rsi
0x18004183e  cmovz   r9, r14
0x180041842  test    r12, r12
0x180041845  mov     [rbp+160h+var_160], r9
0x180041849  cmovz   rcx, r14
0x18004184d  test    rsi, rsi
0x180041850  mov     [rsp+260h+var_200], rcx
0x180041855  mov     [rsp+260h+var_208], rdx
0x18004185a  cmovz   rax, r14
0x18004185e  mov     qword ptr [rsp+260h+var_210], r8
0x180041863  mov     [rsp+260h+var_218], rax
0x180041868  mov     eax, [rsp+260h+var_1E4]
0x18004186c  mov     [rsp+260h+var_220], r9
0x180041871  mov     r9d, edi
0x180041874  mov     [rsp+260h+var_228], eax
0x180041878  mov     eax, [rbp+160h+var_1E0]
0x18004187b  mov     dword ptr [rsp+260h+var_230], eax
0x18004187f  mov     eax, [rsp+260h+var_1EC]
0x180041883  mov     dword ptr [rsp+260h+var_238], r13d
0x180041888  mov     dword ptr [rsp+260h+var_240], eax
0x18004188c  lea     r8, aHwndXDwrunleve_0; "hwnd = %x dwRunLevel = %x dwClientFlags"...
0x180041893  lea     rdx, aRaiforceelevat; "RAiForceElevationPromptForCOM"
0x18004189a  lea     rcx, [rbp+160h+var_130]
0x18004189e  call    ?WatchCurrentThread@LUATelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; LUATelemetry::WatchCurrentThread(char const *,char const *,...)
0x1800418a3  mov     rcx, cs:?g_pCOMElevationActivityTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; this
0x1800418aa  test    rcx, rcx
0x1800418ad  jz      short loc_1800418FD
0x1800418af  call    ?RequestPermission@RateLimiter@@QEAAHXZ; RateLimiter::RequestPermission(void)
0x1800418b4  test    eax, eax
0x1800418b6  jz      short loc_1800418FD
0x1800418b8  mov     ecx, 90h; Size
0x1800418bd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800418c2  test    rax, rax
0x1800418c5  jz      short loc_1800418D4
0x1800418c7  mov     rcx, rax
0x1800418ca  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x1800418cf  mov     rdi, rax
0x1800418d2  jmp     short loc_1800418D6
0x1800418d4  xor     edi, edi
0x1800418d6  xor     edx, edx
0x1800418d8  lock xadd [rdi+88h], rdx; unsigned __int64
0x1800418e1  lea     r8, [rbp+160h+var_E0]; char *
0x1800418e8  mov     rcx, rdi; this
0x1800418eb  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800418f0  test    rdi, rdi
0x1800418f3  jz      short loc_1800418FD
0x1800418f5  mov     rcx, rdi; Block
0x1800418f8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800418fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180041904  lea     rax, WPP_GLOBAL_Control
0x18004190b  cmp     rcx, rax
0x18004190e  jz      short loc_18004198F
0x180041910  test    byte ptr [rcx+1Ch], 1
0x180041914  jz      short loc_18004198F
0x180041916  test    rbx, rbx
0x180041919  mov     r8, r14
0x18004191c  mov     rdi, rsi
0x18004191f  mov     rax, rsi
0x180041922  cmovnz  r8, r12
0x180041926  test    rsi, rsi
0x180041929  jnz     short loc_18004192E
0x18004192b  mov     rax, r14
0x18004192e  mov     rcx, [rcx+10h]
0x180041932  lea     r9, [rbp+160h+var_E0]
0x180041939  mov     [rsp+260h+var_1F8], r9
0x18004193e  mov     edx, 0Ch
0x180041943  mov     r9d, dword ptr [rbp+160h+var_190]
0x180041947  mov     [rsp+260h+var_200], r8
0x18004194c  mov     r8, [rbp+160h+var_170]
0x180041950  mov     [rsp+260h+var_208], r8
0x180041955  mov     r8, [rbp+160h+var_168]
0x180041959  mov     qword ptr [rsp+260h+var_210], r8
0x18004195e  mov     [rsp+260h+var_218], rax
0x180041963  mov     rax, [rbp+160h+var_160]
0x180041967  mov     [rsp+260h+var_220], rax
0x18004196c  mov     eax, [rsp+260h+var_1E4]
0x180041970  mov     [rsp+260h+var_228], eax
0x180041974  mov     eax, [rbp+160h+var_1E0]
0x180041977  mov     dword ptr [rsp+260h+var_230], eax
0x18004197b  mov     eax, [rsp+260h+var_1EC]
0x18004197f  mov     dword ptr [rsp+260h+var_238], r13d
0x180041984  mov     dword ptr [rsp+260h+var_240], eax
0x180041988  call    WPP_SF_DDDDDSSSSSs
0x18004198d  jmp     short loc_180041992
0x18004198f  mov     rdi, rsi
0x180041992  test    rsi, rsi
0x180041995  lea     rcx, AppInfo_PerfTrack_Elevation_COM_Start; struct _EVENT_DESCRIPTOR *
0x18004199c  cmovnz  r14, rdi
0x1800419a0  mov     rdx, r14; unsigned __int16 *
0x1800419a3  call    ?AiLogPerfTrackEventEx@@YAKPEBU_EVENT_DESCRIPTOR@@PEBG@Z; AiLogPerfTrackEventEx(_EVENT_DESCRIPTOR const *,ushort const *)
0x1800419a8  xor     r14d, r14d
0x1800419ab  mov     edi, eax
0x1800419ad  test    rbx, rbx
0x1800419b0  jz      short loc_180041A07
0x1800419b2  test    r13b, 20h
0x1800419b6  jz      short loc_1800419E4
0x1800419b8  mov     [rsp+260h+var_238], r14; unsigned __int16 **
0x1800419bd  lea     rdx, [rbp+160h+hMem]; unsigned __int16 **
0x1800419c1  xor     r9d, r9d; unsigned __int16 **
0x1800419c4  mov     [rsp+260h+var_240], r14; unsigned __int16 *
0x1800419c9  xor     r8d, r8d; unsigned __int16 *
0x1800419cc  mov     rcx, r12; unsigned __int16 *
0x1800419cf  call    ?AiConvertWow64Paths@@YAKPEBGPEAPEBGPEAGPEAPEAG01@Z; AiConvertWow64Paths(ushort const *,ushort const * *,ushort *,ushort * *,ushort const *,ushort const * *)
0x1800419d4  mov     rbx, [rbp+160h+hMem]
0x1800419d8  mov     [rsp+260h+Reply], eax
0x1800419dc  test    eax, eax
0x1800419de  jnz     loc_180041AAA
0x1800419e4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800419e8  inc     rax
0x1800419eb  cmp     [rbx+rax*2], r14w
0x1800419f0  jnz     short loc_1800419E8
0x1800419f2  cmp     rax, 7FFFh
0x1800419f8  jbe     short loc_180041A07
0x1800419fa  mov     [rsp+260h+Reply], 57h ; 'W'
0x180041a02  jmp     loc_180041AAA
0x180041a07  mov     r8, [rbp+160h+var_1A8]; wchar_t *
0x180041a0b  lea     rax, [rbp+160h+var_1C0]
0x180041a0f  mov     rdx, [rbp+160h+var_1A0]; wchar_t *
0x180041a13  mov     r9, rbx; wchar_t *
0x180041a16  mov     [rsp+260h+var_238], rax; struct _CONSENTUI_PARAM_HEADER **
0x180041a1b  mov     rcx, rsi; Source
0x180041a1e  mov     rax, [rbp+160h+var_158]
0x180041a22  mov     [rsp+260h+var_240], rax; struct _GUID *
0x180041a27  call    ?AiBuildCOMParams@@YAKPEBG000PEAU_GUID@@PEAPEAU_CONSENTUI_PARAM_HEADER@@@Z; AiBuildCOMParams(ushort const *,ushort const *,ushort const *,ushort const *,_GUID *,_CONSENTUI_PARAM_HEADER * *)
0x180041a2c  mov     r15, [rbp+160h+var_1C0]
0x180041a30  mov     [rsp+260h+Reply], eax
0x180041a34  test    eax, eax
0x180041a36  jnz     short loc_180041AAA
0x180041a38  mov     r9d, [rsp+260h+var_1EC]; unsigned int
0x180041a3d  lea     rax, [rbp+160h+var_1DC]
0x180041a41  mov     r8, [rbp+160h+var_190]; unsigned __int64
0x180041a45  mov     ecx, 2000000h
0x180041a4a  mov     rdx, [rbp+160h+var_1B0]; void *
0x180041a4e  mov     [rsp+260h+var_1F8], rax; int *
0x180041a53  lea     rax, [rsp+260h+var_1E8]
0x180041a58  mov     [rsp+260h+var_200], rax; enum UACPROMPT_POLICY *
0x180041a5d  lea     rax, [rbp+160h+var_E0]
0x180041a64  mov     [rsp+260h+var_208], rax; char *
0x180041a69  lea     rax, [rbp+160h+Handle]
0x180041a6d  mov     [rsp+260h+var_210], ecx; unsigned int
0x180041a71  mov     [rsp+260h+var_218], rax; unsigned __int64 *
0x180041a76  mov     eax, [rsp+260h+var_1E4]
0x180041a7a  mov     [rsp+260h+var_220], rbx; unsigned __int16 *
0x180041a7f  mov     [rsp+260h+var_228], eax; unsigned int
0x180041a83  mov     rax, [rbp+160h+var_198]
0x180041a87  mov     [rsp+260h+var_230], r15; struct _CONSENTUI_PARAM_HEADER *
0x180041a8c  mov     [rsp+260h+var_238], rax; unsigned __int16 *
0x180041a91  mov     eax, [rbp+160h+var_1E0]
0x180041a94  mov     [rbp+160h+var_1D8], ecx
0x180041a97  xor     ecx, ecx; unsigned int
0x180041a99  mov     dword ptr [rsp+260h+var_240], eax; int
0x180041a9d  mov     [r15+34h], edi
0x180041aa1  call    ?AipGetTokenForService@@YAKKPEAX_KKHPEBGPEAU_CONSENTUI_PARAM_HEADER@@K2PEA_KKPEBDPEAW4UACPROMPT_POLICY@@PEAH@Z; AipGetTokenForService(ulong,void *,unsigned __int64,ulong,int,ushort const *,_CONSENTUI_PARAM_HEADER *,ulong,ushort const *,unsigned __int64 *,ulong,char const *,UACPROMPT_POLICY *,int *)
0x180041aa6  mov     [rsp+260h+Reply], eax
0x180041aaa  mov     rcx, [rbp+160h+Handle]; Handle
0x180041aae  test    rcx, rcx
0x180041ab1  jz      short loc_180041ABD
0x180041ab3  call    cs:__imp_NtClose
0x180041ab9  mov     [rbp+160h+Handle], r14
0x180041abd  mov     rcx, r15; hMem
0x180041ac0  call    cs:__imp_LocalFree
0x180041ac6  cmp     rbx, r12
0x180041ac9  jz      short loc_180041AD8
0x180041acb  mov     rcx, rbx; hMem
0x180041ace  call    cs:__imp_LocalFree
0x180041ad4  mov     [rbp+160h+hMem], r12
0x180041ad8  lea     rcx, [rbp+160h+var_188]; lpPerformanceCount
0x180041adc  call    cs:__imp_QueryPerformanceCounter
0x180041ae2  mov     rax, qword ptr [rbp+160h+var_188]
0x180041ae6  sub     rax, qword ptr [rbp+160h+PerformanceCount]
0x180041aea  imul    rax, 3E8h
0x180041af1  cqo
0x180041af3  idiv    qword ptr [rbp+160h+Frequency]
0x180041af7  mov     [rbp+160h+var_1B0], rax
0x180041afb  mov     eax, [rsp+260h+var_1E8]
0x180041aff  mov     [rsp+260h+var_1E8], eax
0x180041b03  mov     eax, [rsp+260h+Reply]
0x180041b07  cmp     eax, 4C7h
0x180041b0c  jnz     short loc_180041B13
0x180041b0e  mov     eax, r14d
0x180041b11  jmp     short loc_180041B1F
0x180041b13  test    eax, eax
0x180041b15  jle     short loc_180041B1F
0x180041b17  movzx   eax, ax
0x180041b1a  or      eax, 80070000h
0x180041b1f  mov     [rsp+260h+var_1EC], eax
0x180041b23  lea     r9, [rbp+160h+var_1C8]
0x180041b27  lea     rax, [rbp+160h+var_E0]
0x180041b2e  mov     qword ptr [rsp+260h+var_210], rax
0x180041b33  lea     r8, [rbp+160h+var_1D8]
0x180041b37  lea     rax, [rbp+160h+var_1B0]
0x180041b3b  mov     [rsp+260h+var_218], rax
0x180041b40  lea     rdx, [rsp+260h+Reply]
0x180041b45  lea     rax, [rsp+260h+var_1E8]
0x180041b4a  mov     [rsp+260h+var_220], rax
0x180041b4f  lea     rcx, [rsp+260h+var_1EC]
0x180041b54  lea     rax, [rbp+160h+var_1DC]
0x180041b58  mov     qword ptr [rsp+260h+var_228], rax
0x180041b5d  lea     rax, [rbp+160h+var_150]
0x180041b61  mov     [rsp+260h+var_230], rax
0x180041b66  lea     rax, [rbp+160h+hMem]
0x180041b6a  mov     [rsp+260h+var_238], rax
0x180041b6f  lea     rax, [rbp+160h+var_148]
0x180041b73  mov     [rsp+260h+var_240], rax
0x180041b78  call    ??$COMElevation@JAEAKAEAKAEAKAEAPEAU_GUID@@AEAPEBGAEAPEBGAEAHKAEA_JAEAY0IB@D@LUATelemetry@@SAX$$QEAJAEAK11AEAPEAU_GUID@@AEAPEBG3AEAH$$QEAKAEA_JAEAY0IB@D@Z; LUATelemetry::COMElevation<long,ulong &,ulong &,ulong &,_GUID * &,ushort const * &,ushort const * &,int &,ulong,__int64 &,char (&)[129]>(long &&,ulong &,ulong &,ulong &,_GUID * &,ushort const * &,ushort const * &,int &,ulong &&,__int64 &,char (&)[129])
0x180041b7d  mov     rcx, [rbp+160h+pAsync]; pAsync
0x180041b81  lea     rdx, [rsp+260h+Reply]; Reply
0x180041b86  call    cs:__imp_RpcAsyncCompleteCall
0x180041b8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180041b93  lea     rax, WPP_GLOBAL_Control
0x180041b9a  cmp     rcx, rax
0x180041b9d  jz      short loc_180041BBF
0x180041b9f  test    byte ptr [rcx+1Ch], 1
0x180041ba3  jz      short loc_180041BBF
0x180041ba5  mov     r9d, [rsp+260h+Reply]
0x180041baa  lea     r8, WPP_aba5399977573c9264c162bacbfc9302_Traceguids
0x180041bb1  mov     rcx, [rcx+10h]
0x180041bb5  mov     edx, 0Dh
0x180041bba  call    WPP_SF_D
0x180041bbf  lea     rcx, [rbp+160h+var_130]; this
0x180041bc3  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180041bc8  mov     rcx, [rbp+160h+var_50]
0x180041bcf  xor     rcx, rsp; StackCookie
0x180041bd2  call    __security_check_cookie
0x180041bd7  add     rsp, 228h
0x180041bde  pop     r15
  ... truncated ...
```
