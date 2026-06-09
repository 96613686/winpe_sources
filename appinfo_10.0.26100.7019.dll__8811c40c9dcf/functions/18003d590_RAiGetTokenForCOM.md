# RAiGetTokenForCOM

- ea: `0x18003d590`
- end: `0x18003da71`
- name: `RAiGetTokenForCOM`
- size: `1249`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x18000f060`
- `0x1800132ac`
- `0x180018f18`
- `0x18001b0c4`
- `0x18001b0d0`
- `0x180024db0`
- `0x180028424`
- `0x180028864`
- `0x180037fd0`
- `0x180038d40`
- `0x18003c2bc`
- `0x18003c4c4`
- `0x18003d590`
- `0x18003e2c4`
- `0x1800402e4`
- `0x18004292a`
- `0x180042950`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003da05`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003da05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d92e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d942`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d92e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d942`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003d65a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003d956`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003d65a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003d956`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003d66a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003d66a`

## string_xrefs

- `0x18003d700`: `hwnd = %x dwRunLevel = %x dwClientFlags = %x fAdjustTokenSD = %x dwTimeout = %x\n	lpDesktop = %ws\n	lpFriendlyName = %ws\n	lpServerBinary = %ws\n	lpIconReference = %ws\n	lpRequestorPath = %ws\n	lpCvStr = %s\n`
- `0x18003d6f4`: `RAiGetTokenForCOM`

## pseudocode

```c
void __fastcall RAiGetTokenForCOM(
        struct _RPC_ASYNC_STATE *a1,
        void *a2,
        unsigned __int64 a3,
        unsigned int a4,
        int a5,
        int a6,
        unsigned __int16 *a7,
        struct _GUID *a8,
        unsigned __int16 *a9,
        unsigned __int16 *a10,
        unsigned __int16 *a11,
        unsigned __int16 *a12,
        unsigned int a13,
        unsigned __int64 *a14)
{
  const unsigned __int16 *v16; // rdi
  unsigned __int16 *v17; // rbx
  char v18; // r14
  const unsigned __int16 *v19; // rsi
  const unsigned __int16 *v20; // rdx
  unsigned __int16 *v21; // r8
  unsigned __int16 *v22; // r9
  const unsigned __int16 *v23; // rax
  void *v24; // rax
  volatile signed __int64 *v25; // rbx
  const unsigned __int16 *v26; // rcx
  const unsigned __int16 *v27; // rax
  unsigned int v28; // esi
  unsigned int v29; // eax
  unsigned __int64 v30; // rax
  void *v31; // rdx
  unsigned int v32; // eax
  struct _CONSENTUI_PARAM_HEADER *v33; // [rsp+30h] [rbp-D0h]
  unsigned int v34[2]; // [rsp+38h] [rbp-C8h]
  unsigned int v35; // [rsp+38h] [rbp-C8h]
  unsigned __int64 *v36; // [rsp+48h] [rbp-B8h]
  int Reply; // [rsp+70h] [rbp-90h] BYREF
  int v38; // [rsp+74h] [rbp-8Ch] BYREF
  int v39; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v40; // [rsp+7Ch] [rbp-84h]
  int v41; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL v42; // [rsp+88h] [rbp-78h] BYREF
  int v43; // [rsp+90h] [rbp-70h] BYREF
  int v44; // [rsp+94h] [rbp-6Ch] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v46; // [rsp+A0h] [rbp-60h] BYREF
  void *v47; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v48; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v49; // [rsp+B8h] [rbp-48h]
  unsigned __int16 *v50; // [rsp+C0h] [rbp-40h]
  LARGE_INTEGER v51; // [rsp+C8h] [rbp-38h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+D0h] [rbp-30h] BYREF
  LARGE_INTEGER Frequency; // [rsp+D8h] [rbp-28h] BYREF
  struct _GUID *v54; // [rsp+E0h] [rbp-20h] BYREF
  const unsigned __int16 *v55; // [rsp+E8h] [rbp-18h]
  unsigned __int16 *v56; // [rsp+F0h] [rbp-10h]
  unsigned __int16 *v57; // [rsp+F8h] [rbp-8h]
  unsigned __int64 *v58; // [rsp+100h] [rbp+0h]
  PRPC_ASYNC_STATE pAsync; // [rsp+108h] [rbp+8h]
  char v60[80]; // [rsp+110h] [rbp+10h] BYREF
  char v61[144]; // [rsp+160h] [rbp+60h] BYREF

  v16 = a9;
  v17 = a12;
  v18 = a5;
  v50 = a7;
  v38 = a6;
  v54 = a8;
  v40 = a13;
  v58 = a14;
  v47 = a2;
  pAsync = a1;
  hMem = 0;
  v44 = 0;
  v43 = 0;
  v39 = 0;
  Frequency.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  v51.QuadPart = 0;
  v49 = a10;
  v48 = a11;
  v41 = a5;
  v46 = a9;
  v42 = a12;
  QueryPerformanceCounter(&PerformanceCount);
  QueryPerformanceFrequency(&Frequency);
  memset_0(v61, 0, 0x81u);
  v19 = L"NULL";
  v20 = a11;
  if ( !a11 )
    v20 = L"NULL";
  v55 = v20;
  v21 = v49;
  if ( !v49 )
    v21 = L"NULL";
  v56 = v21;
  v22 = v50;
  v23 = a9;
  if ( !v50 )
    v22 = L"NULL";
  v57 = v22;
  if ( !a9 )
    v23 = L"NULL";
  v34[0] = v40;
  LUATelemetry::WatchCurrentThread(
    v60,
    "RAiGetTokenForCOM",
    "hwnd = %x dwRunLevel = %x dwClientFlags = %x fAdjustTokenSD = %x dwTimeout = %x\n"
    "\tlpDesktop = %ws\n"
    "\tlpFriendlyName = %ws\n"
    "\tlpServerBinary = %ws\n"
    "\tlpIconReference = %ws\n"
    "\tlpRequestorPath = %ws\n"
    "\tlpCvStr = %s\n",
    (unsigned int)a3,
    a4,
    a5,
    v38,
    *(_QWORD *)v34,
    v22,
    v23,
    v21,
    v20);
  if ( g_pCOMElevationActivityTelemetryRateLimiter
    && (unsigned int)RateLimiter::RequestPermission(g_pCOMElevationActivityTelemetryRateLimiter) )
  {
    v24 = operator new(0x90u);
    if ( v24 )
      v25 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v24);
    else
      v25 = 0;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v25,
      _InterlockedExchangeAdd64(v25 + 17, 0),
      v61);
    if ( v25 )
      operator delete((void *)v25);
    v17 = (unsigned __int16 *)v42;
    v16 = v46;
    v18 = v41;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v26 = L"NULL";
    if ( v17 )
      v26 = v17;
    v27 = L"NULL";
    if ( v16 )
      v27 = v16;
    WPP_SF_DDDDDSSSSSs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (_DWORD)WPP_GLOBAL_Control,
      a3,
      a4,
      v18,
      v38,
      v40,
      (__int64)v57,
      (__int64)v27,
      (__int64)v56,
      (__int64)v55,
      (__int64)v26,
      (__int64)v61);
  }
  if ( v16 )
    v19 = v16;
  v28 = AiLogPerfTrackEventEx(&AppInfo_PerfTrack_Elevation_COM_Start, v19);
  if ( v17 )
  {
    if ( (v18 & 0x20) != 0 )
    {
      v29 = AiConvertWow64Paths(a12, (const unsigned __int16 **)&v42, 0, 0, 0, 0);
      v17 = (unsigned __int16 *)v42;
      Reply = v29;
      if ( v29 )
        goto LABEL_35;
    }
    v30 = -1;
    do
      ++v30;
    while ( v17[v30] );
    if ( v30 > 0x7FFF )
    {
      Reply = 87;
      goto LABEL_35;
    }
  }
  Reply = AiBuildCOMParams(v16, v49, v48, v17, v54, (struct _CONSENTUI_PARAM_HEADER **)&hMem);
  if ( !Reply )
  {
    v31 = v47;
    v36 = v58;
    v35 = v40;
    v33 = (struct _CONSENTUI_PARAM_HEADER *)hMem;
    *((_DWORD *)hMem + 13) = v28;
    Reply = AipGetTokenForService(
              0,
              v31,
              a3,
              a4,
              v38,
              v50,
              v33,
              v35,
              v17,
              v36,
              0,
              v61,
              (enum UACPROMPT_POLICY *)&v39,
              &v43);
  }
LABEL_35:
  LocalFree(hMem);
  if ( v17 != a12 )
  {
    LocalFree(v17);
    v42 = a12;
  }
  QueryPerformanceCounter(&v51);
  v47 = (void *)(1000 * (v51.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart);
  v32 = Reply;
  if ( Reply == 1223 )
  {
    v38 = 0;
  }
  else
  {
    if ( Reply > 0 )
      v32 = (unsigned __int16)Reply | 0x80070000;
    v38 = v32;
  }
  LUATelemetry::COMElevation<long,unsigned long &,unsigned long &,unsigned long &,_GUID * &,unsigned short const * &,unsigned short const * &,int &,unsigned long,__int64 &,char (&)[129]>(
    (unsigned int)&v38,
    (unsigned int)&Reply,
    (unsigned int)&v44,
    (unsigned int)&v41,
    (__int64)&v54,
    (__int64)&v42,
    (__int64)&v46,
    (__int64)&v43,
    (__int64)&v39,
    (__int64)&v47,
    v61);
  RpcAsyncCompleteCall(pAsync, &Reply);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      &WPP_aba5399977573c9264c162bacbfc9302_Traceguids,
      (unsigned int)Reply);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v60);
}

```

## disassembly

```asm
0x18003d590  push    rbp
0x18003d592  push    rbx
0x18003d593  push    rsi
0x18003d594  push    rdi
0x18003d595  push    r12
0x18003d597  push    r13
0x18003d599  push    r14
0x18003d59b  push    r15
0x18003d59d  lea     rbp, [rsp-108h]
0x18003d5a5  sub     rsp, 208h
0x18003d5ac  mov     rax, cs:__security_cookie
0x18003d5b3  xor     rax, rsp
0x18003d5b6  mov     [rbp+140h+var_50], rax
0x18003d5bd  mov     rax, [rbp+140h+arg_30]
0x18003d5c4  mov     r12, r8
0x18003d5c7  mov     r8, [rbp+140h+arg_50]
0x18003d5ce  mov     r13d, r9d
0x18003d5d1  mov     r15, [rbp+140h+arg_58]
0x18003d5d8  mov     rdi, [rbp+140h+arg_40]
0x18003d5df  mov     rbx, r15
0x18003d5e2  mov     r14d, [rbp+140h+arg_20]
0x18003d5e9  mov     [rbp+140h+var_180], rax
0x18003d5ed  mov     eax, [rbp+140h+arg_28]
0x18003d5f3  mov     [rsp+240h+var_1CC], eax
0x18003d5f7  mov     rax, [rbp+140h+arg_38]
0x18003d5fe  mov     [rbp+140h+var_160], rax
0x18003d602  mov     eax, [rbp+140h+arg_60]
0x18003d608  mov     [rsp+240h+var_1C4], eax
0x18003d60c  mov     rax, [rbp+140h+arg_68]
0x18003d613  mov     [rbp+140h+var_140], rax
0x18003d617  xor     eax, eax
0x18003d619  mov     [rbp+140h+var_198], rdx
0x18003d61d  mov     rdx, [rbp+140h+arg_48]
0x18003d624  mov     [rbp+140h+pAsync], rcx
0x18003d628  lea     rcx, [rbp+140h+PerformanceCount]; lpPerformanceCount
0x18003d62c  mov     [rbp+140h+hMem], rax
0x18003d630  mov     [rbp+140h+var_1AC], eax
0x18003d633  mov     [rbp+140h+var_1B0], eax
0x18003d636  mov     [rsp+240h+var_1C8], eax
0x18003d63a  mov     qword ptr [rbp+140h+Frequency], rax
0x18003d63e  mov     qword ptr [rbp+140h+PerformanceCount], rax
0x18003d642  mov     qword ptr [rbp+140h+var_178], rax
0x18003d646  mov     [rbp+140h+var_188], rdx
0x18003d64a  mov     [rbp+140h+var_190], r8
0x18003d64e  mov     [rbp+140h+var_1C0], r14d
0x18003d652  mov     [rbp+140h+var_1A0], rdi
0x18003d656  mov     [rbp+140h+var_1B8], rbx
0x18003d65a  call    cs:__imp_QueryPerformanceCounter
0x18003d661  nop     dword ptr [rax+rax+00h]
0x18003d666  lea     rcx, [rbp+140h+Frequency]; lpFrequency
0x18003d66a  call    cs:__imp_QueryPerformanceFrequency
0x18003d671  nop     dword ptr [rax+rax+00h]
0x18003d676  xor     edx, edx; Val
0x18003d678  lea     rcx, [rbp+140h+var_E0]; void *
0x18003d67c  mov     r8d, 81h; Size
0x18003d682  call    memset_0
0x18003d687  mov     rax, [rbp+140h+var_190]
0x18003d68b  lea     rsi, aNull_0; "NULL"
0x18003d692  test    rax, rax
0x18003d695  lea     r10, [rbp+140h+var_E0]
0x18003d699  mov     [rsp+240h+var_1D8], r10
0x18003d69e  mov     rdx, rax
0x18003d6a1  mov     rax, [rbp+140h+var_188]
0x18003d6a5  cmovz   rdx, rsi
0x18003d6a9  test    rax, rax
0x18003d6ac  mov     [rbp+140h+var_158], rdx
0x18003d6b0  mov     r8, rax
0x18003d6b3  mov     rcx, r15
0x18003d6b6  mov     rax, [rbp+140h+var_180]
0x18003d6ba  cmovz   r8, rsi
0x18003d6be  test    rax, rax
0x18003d6c1  mov     [rbp+140h+var_150], r8
0x18003d6c5  mov     r9, rax
0x18003d6c8  mov     rax, rdi
0x18003d6cb  cmovz   r9, rsi
0x18003d6cf  test    r15, r15
0x18003d6d2  mov     [rbp+140h+var_148], r9
0x18003d6d6  cmovz   rcx, rsi
0x18003d6da  test    rdi, rdi
0x18003d6dd  mov     [rsp+240h+var_1E0], rcx
0x18003d6e2  lea     rcx, [rbp+140h+var_130]
0x18003d6e6  mov     [rsp+240h+var_1E8], rdx
0x18003d6eb  cmovz   rax, rsi
0x18003d6ef  mov     qword ptr [rsp+240h+var_1F0], r8
0x18003d6f4  lea     rdx, aRaigettokenfor_0; "RAiGetTokenForCOM"
0x18003d6fb  mov     [rsp+240h+var_1F8], rax
0x18003d700  lea     r8, aHwndXDwrunleve_0; "hwnd = %x dwRunLevel = %x dwClientFlags"...
0x18003d707  mov     eax, [rsp+240h+var_1C4]
0x18003d70b  mov     [rsp+240h+var_200], r9
0x18003d710  mov     r9d, r12d
0x18003d713  mov     [rsp+240h+var_208], eax
0x18003d717  mov     eax, [rsp+240h+var_1CC]
0x18003d71b  mov     dword ptr [rsp+240h+var_210], eax
0x18003d71f  mov     dword ptr [rsp+240h+var_218], r14d
0x18003d724  mov     dword ptr [rsp+240h+var_220], r13d
0x18003d729  call    ?WatchCurrentThread@LUATelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; LUATelemetry::WatchCurrentThread(char const *,char const *,...)
0x18003d72e  mov     rcx, cs:?g_pCOMElevationActivityTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; this
0x18003d735  test    rcx, rcx
0x18003d738  jz      short loc_18003D791
0x18003d73a  call    ?RequestPermission@RateLimiter@@QEAAHXZ; RateLimiter::RequestPermission(void)
0x18003d73f  test    eax, eax
0x18003d741  jz      short loc_18003D791
0x18003d743  mov     ecx, 90h; Size
0x18003d748  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003d74d  test    rax, rax
0x18003d750  jz      short loc_18003D75F
0x18003d752  mov     rcx, rax
0x18003d755  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18003d75a  mov     rbx, rax
0x18003d75d  jmp     short loc_18003D761
0x18003d75f  xor     ebx, ebx
0x18003d761  xor     edx, edx
0x18003d763  lock xadd [rbx+88h], rdx; unsigned __int64
0x18003d76c  lea     r8, [rbp+140h+var_E0]; char *
0x18003d770  mov     rcx, rbx; this
0x18003d773  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18003d778  test    rbx, rbx
0x18003d77b  jz      short loc_18003D785
0x18003d77d  mov     rcx, rbx; Block
0x18003d780  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003d785  mov     rbx, [rbp+140h+var_1B8]
0x18003d789  mov     rdi, [rbp+140h+var_1A0]
0x18003d78d  mov     r14d, [rbp+140h+var_1C0]
0x18003d791  mov     r8, cs:WPP_GLOBAL_Control
0x18003d798  lea     rax, WPP_GLOBAL_Control
0x18003d79f  cmp     r8, rax
0x18003d7a2  jz      short loc_18003D818
0x18003d7a4  test    byte ptr [r8+1Ch], 1
0x18003d7a9  jz      short loc_18003D818
0x18003d7ab  test    rbx, rbx
0x18003d7ae  lea     r9, [rbp+140h+var_E0]
0x18003d7b2  mov     [rsp+240h+var_1D8], r9
0x18003d7b7  mov     rcx, rsi
0x18003d7ba  cmovnz  rcx, rbx
0x18003d7be  mov     rax, rsi
0x18003d7c1  mov     [rsp+240h+var_1E0], rcx
0x18003d7c6  test    rdi, rdi
0x18003d7c9  mov     rcx, [rbp+140h+var_158]
0x18003d7cd  mov     edx, 0Ah
0x18003d7d2  mov     [rsp+240h+var_1E8], rcx
0x18003d7d7  cmovnz  rax, rdi
0x18003d7db  mov     rcx, [rbp+140h+var_150]
0x18003d7df  mov     r9d, r12d
0x18003d7e2  mov     qword ptr [rsp+240h+var_1F0], rcx
0x18003d7e7  mov     rcx, [r8+10h]
0x18003d7eb  mov     [rsp+240h+var_1F8], rax
0x18003d7f0  mov     rax, [rbp+140h+var_148]
0x18003d7f4  mov     [rsp+240h+var_200], rax
0x18003d7f9  mov     eax, [rsp+240h+var_1C4]
0x18003d7fd  mov     [rsp+240h+var_208], eax
0x18003d801  mov     eax, [rsp+240h+var_1CC]
0x18003d805  mov     dword ptr [rsp+240h+var_210], eax
0x18003d809  mov     dword ptr [rsp+240h+var_218], r14d
0x18003d80e  mov     dword ptr [rsp+240h+var_220], r13d
0x18003d813  call    WPP_SF_DDDDDSSSSSs
0x18003d818  test    rdi, rdi
0x18003d81b  lea     rcx, AppInfo_PerfTrack_Elevation_COM_Start; struct _EVENT_DESCRIPTOR *
0x18003d822  cmovnz  rsi, rdi
0x18003d826  mov     rdx, rsi; unsigned __int16 *
0x18003d829  call    ?AiLogPerfTrackEventEx@@YAKPEBU_EVENT_DESCRIPTOR@@PEBG@Z; AiLogPerfTrackEventEx(_EVENT_DESCRIPTOR const *,ushort const *)
0x18003d82e  mov     esi, eax
0x18003d830  test    rbx, rbx
0x18003d833  jz      short loc_18003D891
0x18003d835  test    r14b, 20h
0x18003d839  jz      short loc_18003D86B
0x18003d83b  xor     r14d, r14d
0x18003d83e  lea     rdx, [rbp+140h+var_1B8]; unsigned __int16 **
0x18003d842  mov     [rsp+240h+var_218], r14; unsigned __int16 **
0x18003d847  xor     r9d, r9d; unsigned __int16 **
0x18003d84a  xor     r8d, r8d; unsigned __int16 *
0x18003d84d  mov     [rsp+240h+var_220], r14; unsigned __int16 *
0x18003d852  mov     rcx, r15; unsigned __int16 *
0x18003d855  call    ?AiConvertWow64Paths@@YAKPEBGPEAPEBGPEAGPEAPEAG01@Z; AiConvertWow64Paths(ushort const *,ushort const * *,ushort *,ushort * *,ushort const *,ushort const * *)
0x18003d85a  mov     rbx, [rbp+140h+var_1B8]
0x18003d85e  mov     [rsp+240h+Reply], eax
0x18003d862  test    eax, eax
0x18003d864  jz      short loc_18003D86E
0x18003d866  jmp     loc_18003D92A
0x18003d86b  xor     r14d, r14d
0x18003d86e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003d872  inc     rax
0x18003d875  cmp     [rbx+rax*2], r14w
0x18003d87a  jnz     short loc_18003D872
0x18003d87c  cmp     rax, 7FFFh
0x18003d882  jbe     short loc_18003D894
0x18003d884  mov     [rsp+240h+Reply], 57h ; 'W'
0x18003d88c  jmp     loc_18003D92A
0x18003d891  xor     r14d, r14d
0x18003d894  mov     r8, [rbp+140h+var_190]; unsigned __int16 *
0x18003d898  lea     rax, [rbp+140h+hMem]
0x18003d89c  mov     rdx, [rbp+140h+var_188]; unsigned __int16 *
0x18003d8a0  mov     r9, rbx; unsigned __int16 *
0x18003d8a3  mov     [rsp+240h+var_218], rax; struct _CONSENTUI_PARAM_HEADER **
0x18003d8a8  mov     rcx, rdi; unsigned __int16 *
0x18003d8ab  mov     rax, [rbp+140h+var_160]
0x18003d8af  mov     [rsp+240h+var_220], rax; struct _GUID *
0x18003d8b4  call    ?AiBuildCOMParams@@YAKPEBG000PEAU_GUID@@PEAPEAU_CONSENTUI_PARAM_HEADER@@@Z; AiBuildCOMParams(ushort const *,ushort const *,ushort const *,ushort const *,_GUID *,_CONSENTUI_PARAM_HEADER * *)
0x18003d8b9  mov     [rsp+240h+Reply], eax
0x18003d8bd  test    eax, eax
0x18003d8bf  jnz     short loc_18003D92A
0x18003d8c1  mov     rax, [rbp+140h+hMem]
0x18003d8c5  lea     rcx, [rbp+140h+var_1B0]
0x18003d8c9  mov     rdx, [rbp+140h+var_198]; void *
0x18003d8cd  mov     r9d, r13d; unsigned int
0x18003d8d0  mov     [rsp+240h+var_1D8], rcx; int *
0x18003d8d5  mov     r8, r12; unsigned __int64
0x18003d8d8  lea     rcx, [rsp+240h+var_1C8]
0x18003d8dd  mov     [rsp+240h+var_1E0], rcx; enum UACPROMPT_POLICY *
0x18003d8e2  lea     rcx, [rbp+140h+var_E0]
0x18003d8e6  mov     [rsp+240h+var_1E8], rcx; char *
0x18003d8eb  mov     rcx, [rbp+140h+var_140]
0x18003d8ef  mov     [rsp+240h+var_1F0], r14d; unsigned int
0x18003d8f4  mov     [rsp+240h+var_1F8], rcx; unsigned __int64 *
0x18003d8f9  mov     ecx, [rsp+240h+var_1C4]
0x18003d8fd  mov     [rsp+240h+var_200], rbx; unsigned __int16 *
0x18003d902  mov     [rsp+240h+var_208], ecx; unsigned int
0x18003d906  xor     ecx, ecx; unsigned int
0x18003d908  mov     [rsp+240h+var_210], rax; struct _CONSENTUI_PARAM_HEADER *
0x18003d90d  mov     [rax+34h], esi
0x18003d910  mov     rax, [rbp+140h+var_180]
0x18003d914  mov     [rsp+240h+var_218], rax; unsigned __int16 *
0x18003d919  mov     eax, [rsp+240h+var_1CC]
0x18003d91d  mov     dword ptr [rsp+240h+var_220], eax; int
0x18003d921  call    ?AipGetTokenForService@@YAKKPEAX_KKHPEBGPEAU_CONSENTUI_PARAM_HEADER@@K2PEA_KKPEBDPEAW4UACPROMPT_POLICY@@PEAH@Z; AipGetTokenForService(ulong,void *,unsigned __int64,ulong,int,ushort const *,_CONSENTUI_PARAM_HEADER *,ulong,ushort const *,unsigned __int64 *,ulong,char const *,UACPROMPT_POLICY *,int *)
0x18003d926  mov     [rsp+240h+Reply], eax
0x18003d92a  mov     rcx, [rbp+140h+hMem]; hMem
0x18003d92e  call    cs:__imp_LocalFree
0x18003d935  nop     dword ptr [rax+rax+00h]
0x18003d93a  cmp     rbx, r15
0x18003d93d  jz      short loc_18003D952
0x18003d93f  mov     rcx, rbx; hMem
0x18003d942  call    cs:__imp_LocalFree
0x18003d949  nop     dword ptr [rax+rax+00h]
0x18003d94e  mov     [rbp+140h+var_1B8], r15
0x18003d952  lea     rcx, [rbp+140h+var_178]; lpPerformanceCount
0x18003d956  call    cs:__imp_QueryPerformanceCounter
0x18003d95d  nop     dword ptr [rax+rax+00h]
0x18003d962  mov     rax, qword ptr [rbp+140h+var_178]
0x18003d966  sub     rax, qword ptr [rbp+140h+PerformanceCount]
0x18003d96a  imul    rax, 3E8h
0x18003d971  cqo
0x18003d973  idiv    qword ptr [rbp+140h+Frequency]
0x18003d977  mov     [rbp+140h+var_198], rax
0x18003d97b  mov     eax, [rsp+240h+var_1C8]
0x18003d97f  mov     [rsp+240h+var_1C8], eax
0x18003d983  mov     eax, [rsp+240h+Reply]
0x18003d987  cmp     eax, 4C7h
0x18003d98c  jnz     short loc_18003D995
0x18003d98e  mov     [rsp+240h+var_1CC], r14d
0x18003d993  jmp     short loc_18003D9A5
0x18003d995  test    eax, eax
0x18003d997  jle     short loc_18003D9A1
0x18003d999  movzx   eax, ax
0x18003d99c  or      eax, 80070000h
0x18003d9a1  mov     [rsp+240h+var_1CC], eax
0x18003d9a5  lea     rax, [rbp+140h+var_E0]
0x18003d9a9  mov     qword ptr [rsp+240h+var_1F0], rax
0x18003d9ae  lea     r9, [rbp+140h+var_1C0]
0x18003d9b2  lea     rax, [rbp+140h+var_198]
0x18003d9b6  mov     [rsp+240h+var_1F8], rax
0x18003d9bb  lea     r8, [rbp+140h+var_1AC]
0x18003d9bf  lea     rax, [rsp+240h+var_1C8]
0x18003d9c4  mov     [rsp+240h+var_200], rax
0x18003d9c9  lea     rdx, [rsp+240h+Reply]
0x18003d9ce  lea     rax, [rbp+140h+var_1B0]
0x18003d9d2  mov     qword ptr [rsp+240h+var_208], rax
0x18003d9d7  lea     rcx, [rsp+240h+var_1CC]
0x18003d9dc  lea     rax, [rbp+140h+var_1A0]
0x18003d9e0  mov     [rsp+240h+var_210], rax
0x18003d9e5  lea     rax, [rbp+140h+var_1B8]
0x18003d9e9  mov     [rsp+240h+var_218], rax
0x18003d9ee  lea     rax, [rbp+140h+var_160]
0x18003d9f2  mov     [rsp+240h+var_220], rax
0x18003d9f7  call    ??$COMElevation@JAEAKAEAKAEAKAEAPEAU_GUID@@AEAPEBGAEAPEBGAEAHKAEA_JAEAY0IB@D@LUATelemetry@@SAX$$QEAJAEAK11AEAPEAU_GUID@@AEAPEBG3AEAH$$QEAKAEA_JAEAY0IB@D@Z; LUATelemetry::COMElevation<long,ulong &,ulong &,ulong &,_GUID * &,ushort const * &,ushort const * &,int &,ulong,__int64 &,char (&)[129]>(long &&,ulong &,ulong &,ulong &,_GUID * &,ushort const * &,ushort const * &,int &,ulong &&,__int64 &,char (&)[129])
0x18003d9fc  mov     rcx, [rbp+140h+pAsync]; pAsync
0x18003da00  lea     rdx, [rsp+240h+Reply]; Reply
0x18003da05  call    cs:__imp_RpcAsyncCompleteCall
0x18003da0c  nop     dword ptr [rax+rax+00h]
0x18003da11  mov     rcx, cs:WPP_GLOBAL_Control
0x18003da18  lea     rax, WPP_GLOBAL_Control
0x18003da1f  cmp     rcx, rax
0x18003da22  jz      short loc_18003DA44
0x18003da24  test    byte ptr [rcx+1Ch], 1
0x18003da28  jz      short loc_18003DA44
0x18003da2a  mov     r9d, [rsp+240h+Reply]
0x18003da2f  lea     r8, WPP_aba5399977573c9264c162bacbfc9302_Traceguids
0x18003da36  mov     rcx, [rcx+10h]
0x18003da3a  mov     edx, 0Bh
0x18003da3f  call    WPP_SF_D
0x18003da44  lea     rcx, [rbp+140h+var_130]; this
0x18003da48  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18003da4d  mov     rcx, [rbp+140h+var_50]
0x18003da54  xor     rcx, rsp; StackCookie
0x18003da57  call    __security_check_cookie
0x18003da5c  add     rsp, 208h
0x18003da63  pop     r15
0x18003da65  pop     r14
0x18003da67  pop     r13
0x18003da69  pop     r12
0x18003da6b  pop     rdi
  ... truncated ...
```
