# RAiGetTokenForCOM

- ea: `0x18003f160`
- end: `0x18003f641`
- name: `RAiGetTokenForCOM`
- size: `1249`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x18000f190`
- `0x1800133ec`
- `0x1800192e8`
- `0x18001b494`
- `0x18001b4a0`
- `0x1800234a0`
- `0x180026de4`
- `0x180027224`
- `0x180038670`
- `0x1800393e0`
- `0x18003de84`
- `0x18003e094`
- `0x18003f160`
- `0x18003fe94`
- `0x180041eb4`
- `0x1800444ba`
- `0x1800444e0`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003f5d5`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003f5d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f4fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f512`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f4fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f512`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003f23a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003f23a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003f22a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003f526`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003f22a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003f526`

## string_xrefs

- `0x18003f2d0`: `hwnd = %x dwRunLevel = %x dwClientFlags = %x fAdjustTokenSD = %x dwTimeout = %x\n	lpDesktop = %ws\n	lpFriendlyName = %ws\n	lpServerBinary = %ws\n	lpIconReference = %ws\n	lpRequestorPath = %ws\n	lpCvStr = %s\n`
- `0x18003f2c4`: `RAiGetTokenForCOM`

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
  const unsigned __int16 *v22; // rcx
  unsigned __int16 *v23; // r9
  const unsigned __int16 *v24; // rax
  void *v25; // rax
  volatile signed __int64 *v26; // rbx
  const unsigned __int16 *v27; // rcx
  const unsigned __int16 *v28; // rax
  unsigned int v29; // esi
  unsigned int v30; // eax
  unsigned __int64 v31; // rax
  void *v32; // rdx
  unsigned int v33; // eax
  struct _CONSENTUI_PARAM_HEADER *v34; // [rsp+30h] [rbp-D0h]
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
  v22 = a12;
  if ( !v49 )
    v21 = L"NULL";
  v56 = v21;
  v23 = v50;
  v24 = a9;
  if ( !v50 )
    v23 = L"NULL";
  v57 = v23;
  if ( !a12 )
    v22 = L"NULL";
  if ( !a9 )
    v24 = L"NULL";
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
    v40,
    v23,
    v24,
    v21,
    v20,
    v22,
    v61);
  if ( g_pCOMElevationActivityTelemetryRateLimiter
    && (unsigned int)RateLimiter::RequestPermission(g_pCOMElevationActivityTelemetryRateLimiter) )
  {
    v25 = operator new(0x90u);
    if ( v25 )
      v26 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v25);
    else
      v26 = 0;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v26,
      _InterlockedExchangeAdd64(v26 + 17, 0),
      v61);
    if ( v26 )
      operator delete((void *)v26);
    v17 = (unsigned __int16 *)v42;
    v16 = v46;
    v18 = v41;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v27 = L"NULL";
    if ( v17 )
      v27 = v17;
    v28 = L"NULL";
    if ( v16 )
      v28 = v16;
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
      (__int64)v28,
      (__int64)v56,
      (__int64)v55,
      (__int64)v27,
      (__int64)v61);
  }
  if ( v16 )
    v19 = v16;
  v29 = AiLogPerfTrackEventEx(&AppInfo_PerfTrack_Elevation_COM_Start, v19);
  if ( v17 )
  {
    if ( (v18 & 0x20) != 0 )
    {
      v30 = AiConvertWow64Paths(a12, (const unsigned __int16 **)&v42, 0, 0, 0, 0);
      v17 = (unsigned __int16 *)v42;
      Reply = v30;
      if ( v30 )
        goto LABEL_37;
    }
    v31 = -1;
    do
      ++v31;
    while ( v17[v31] );
    if ( v31 > 0x7FFF )
    {
      Reply = 87;
      goto LABEL_37;
    }
  }
  Reply = AiBuildCOMParams(v16, v49, v48, v17, v54, (struct _CONSENTUI_PARAM_HEADER **)&hMem);
  if ( !Reply )
  {
    v32 = v47;
    v36 = v58;
    v35 = v40;
    v34 = (struct _CONSENTUI_PARAM_HEADER *)hMem;
    *((_DWORD *)hMem + 13) = v29;
    Reply = AipGetTokenForService(
              0,
              v32,
              a3,
              a4,
              v38,
              v50,
              v34,
              v35,
              v17,
              v36,
              0,
              v61,
              (enum UACPROMPT_POLICY *)&v39,
              &v43);
  }
LABEL_37:
  LocalFree(hMem);
  if ( v17 != a12 )
  {
    LocalFree(v17);
    v42 = a12;
  }
  QueryPerformanceCounter(&v51);
  v47 = (void *)(1000 * (v51.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart);
  v33 = Reply;
  if ( Reply == 1223 )
  {
    v38 = 0;
  }
  else
  {
    if ( Reply > 0 )
      v33 = (unsigned __int16)Reply | 0x80070000;
    v38 = v33;
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
0x18003f160  push    rbp
0x18003f162  push    rbx
0x18003f163  push    rsi
0x18003f164  push    rdi
0x18003f165  push    r12
0x18003f167  push    r13
0x18003f169  push    r14
0x18003f16b  push    r15
0x18003f16d  lea     rbp, [rsp-108h]
0x18003f175  sub     rsp, 208h
0x18003f17c  mov     rax, cs:__security_cookie
0x18003f183  xor     rax, rsp
0x18003f186  mov     [rbp+140h+var_50], rax
0x18003f18d  mov     rax, [rbp+140h+arg_30]
0x18003f194  mov     r12, r8
0x18003f197  mov     r8, [rbp+140h+arg_50]
0x18003f19e  mov     r13d, r9d
0x18003f1a1  mov     r15, [rbp+140h+arg_58]
0x18003f1a8  mov     rdi, [rbp+140h+arg_40]
0x18003f1af  mov     rbx, r15
0x18003f1b2  mov     r14d, [rbp+140h+arg_20]
0x18003f1b9  mov     [rbp+140h+var_180], rax
0x18003f1bd  mov     eax, [rbp+140h+arg_28]
0x18003f1c3  mov     [rsp+240h+var_1CC], eax
0x18003f1c7  mov     rax, [rbp+140h+arg_38]
0x18003f1ce  mov     [rbp+140h+var_160], rax
0x18003f1d2  mov     eax, [rbp+140h+arg_60]
0x18003f1d8  mov     [rsp+240h+var_1C4], eax
0x18003f1dc  mov     rax, [rbp+140h+arg_68]
0x18003f1e3  mov     [rbp+140h+var_140], rax
0x18003f1e7  xor     eax, eax
0x18003f1e9  mov     [rbp+140h+var_198], rdx
0x18003f1ed  mov     rdx, [rbp+140h+arg_48]
0x18003f1f4  mov     [rbp+140h+pAsync], rcx
0x18003f1f8  lea     rcx, [rbp+140h+PerformanceCount]; lpPerformanceCount
0x18003f1fc  mov     [rbp+140h+hMem], rax
0x18003f200  mov     [rbp+140h+var_1AC], eax
0x18003f203  mov     [rbp+140h+var_1B0], eax
0x18003f206  mov     [rsp+240h+var_1C8], eax
0x18003f20a  mov     qword ptr [rbp+140h+Frequency], rax
0x18003f20e  mov     qword ptr [rbp+140h+PerformanceCount], rax
0x18003f212  mov     qword ptr [rbp+140h+var_178], rax
0x18003f216  mov     [rbp+140h+var_188], rdx
0x18003f21a  mov     [rbp+140h+var_190], r8
0x18003f21e  mov     [rbp+140h+var_1C0], r14d
0x18003f222  mov     [rbp+140h+var_1A0], rdi
0x18003f226  mov     [rbp+140h+var_1B8], rbx
0x18003f22a  call    cs:__imp_QueryPerformanceCounter
0x18003f231  nop     dword ptr [rax+rax+00h]
0x18003f236  lea     rcx, [rbp+140h+Frequency]; lpFrequency
0x18003f23a  call    cs:__imp_QueryPerformanceFrequency
0x18003f241  nop     dword ptr [rax+rax+00h]
0x18003f246  xor     edx, edx; Val
0x18003f248  lea     rcx, [rbp+140h+var_E0]; void *
0x18003f24c  mov     r8d, 81h; Size
0x18003f252  call    memset_0
0x18003f257  mov     rax, [rbp+140h+var_190]
0x18003f25b  lea     rsi, aNull_0; "NULL"
0x18003f262  test    rax, rax
0x18003f265  lea     r10, [rbp+140h+var_E0]
0x18003f269  mov     [rsp+240h+var_1D8], r10
0x18003f26e  mov     rdx, rax
0x18003f271  mov     rax, [rbp+140h+var_188]
0x18003f275  cmovz   rdx, rsi
0x18003f279  test    rax, rax
0x18003f27c  mov     [rbp+140h+var_158], rdx
0x18003f280  mov     r8, rax
0x18003f283  mov     rcx, r15
0x18003f286  mov     rax, [rbp+140h+var_180]
0x18003f28a  cmovz   r8, rsi
0x18003f28e  test    rax, rax
0x18003f291  mov     [rbp+140h+var_150], r8
0x18003f295  mov     r9, rax
0x18003f298  mov     rax, rdi
0x18003f29b  cmovz   r9, rsi
0x18003f29f  test    r15, r15
0x18003f2a2  mov     [rbp+140h+var_148], r9
0x18003f2a6  cmovz   rcx, rsi
0x18003f2aa  test    rdi, rdi
0x18003f2ad  mov     [rsp+240h+var_1E0], rcx
0x18003f2b2  lea     rcx, [rbp+140h+var_130]
0x18003f2b6  mov     [rsp+240h+var_1E8], rdx
0x18003f2bb  cmovz   rax, rsi
0x18003f2bf  mov     qword ptr [rsp+240h+var_1F0], r8
0x18003f2c4  lea     rdx, aRaigettokenfor_0; "RAiGetTokenForCOM"
0x18003f2cb  mov     [rsp+240h+var_1F8], rax
0x18003f2d0  lea     r8, aHwndXDwrunleve_0; "hwnd = %x dwRunLevel = %x dwClientFlags"...
0x18003f2d7  mov     eax, [rsp+240h+var_1C4]
0x18003f2db  mov     [rsp+240h+var_200], r9
0x18003f2e0  mov     r9d, r12d
0x18003f2e3  mov     [rsp+240h+var_208], eax
0x18003f2e7  mov     eax, [rsp+240h+var_1CC]
0x18003f2eb  mov     dword ptr [rsp+240h+var_210], eax
0x18003f2ef  mov     dword ptr [rsp+240h+var_218], r14d
0x18003f2f4  mov     dword ptr [rsp+240h+var_220], r13d
0x18003f2f9  call    ?WatchCurrentThread@LUATelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; LUATelemetry::WatchCurrentThread(char const *,char const *,...)
0x18003f2fe  mov     rcx, cs:?g_pCOMElevationActivityTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; this
0x18003f305  test    rcx, rcx
0x18003f308  jz      short loc_18003F361
0x18003f30a  call    ?RequestPermission@RateLimiter@@QEAAHXZ; RateLimiter::RequestPermission(void)
0x18003f30f  test    eax, eax
0x18003f311  jz      short loc_18003F361
0x18003f313  mov     ecx, 90h; Size
0x18003f318  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003f31d  test    rax, rax
0x18003f320  jz      short loc_18003F32F
0x18003f322  mov     rcx, rax
0x18003f325  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18003f32a  mov     rbx, rax
0x18003f32d  jmp     short loc_18003F331
0x18003f32f  xor     ebx, ebx
0x18003f331  xor     edx, edx
0x18003f333  lock xadd [rbx+88h], rdx; unsigned __int64
0x18003f33c  lea     r8, [rbp+140h+var_E0]; char *
0x18003f340  mov     rcx, rbx; this
0x18003f343  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18003f348  test    rbx, rbx
0x18003f34b  jz      short loc_18003F355
0x18003f34d  mov     rcx, rbx; Block
0x18003f350  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003f355  mov     rbx, [rbp+140h+var_1B8]
0x18003f359  mov     rdi, [rbp+140h+var_1A0]
0x18003f35d  mov     r14d, [rbp+140h+var_1C0]
0x18003f361  mov     r8, cs:WPP_GLOBAL_Control
0x18003f368  lea     rax, WPP_GLOBAL_Control
0x18003f36f  cmp     r8, rax
0x18003f372  jz      short loc_18003F3E8
0x18003f374  test    byte ptr [r8+1Ch], 1
0x18003f379  jz      short loc_18003F3E8
0x18003f37b  test    rbx, rbx
0x18003f37e  lea     r9, [rbp+140h+var_E0]
0x18003f382  mov     [rsp+240h+var_1D8], r9
0x18003f387  mov     rcx, rsi
0x18003f38a  cmovnz  rcx, rbx
0x18003f38e  mov     rax, rsi
0x18003f391  mov     [rsp+240h+var_1E0], rcx
0x18003f396  test    rdi, rdi
0x18003f399  mov     rcx, [rbp+140h+var_158]
0x18003f39d  mov     edx, 0Ah
0x18003f3a2  mov     [rsp+240h+var_1E8], rcx
0x18003f3a7  cmovnz  rax, rdi
0x18003f3ab  mov     rcx, [rbp+140h+var_150]
0x18003f3af  mov     r9d, r12d
0x18003f3b2  mov     qword ptr [rsp+240h+var_1F0], rcx
0x18003f3b7  mov     rcx, [r8+10h]
0x18003f3bb  mov     [rsp+240h+var_1F8], rax
0x18003f3c0  mov     rax, [rbp+140h+var_148]
0x18003f3c4  mov     [rsp+240h+var_200], rax
0x18003f3c9  mov     eax, [rsp+240h+var_1C4]
0x18003f3cd  mov     [rsp+240h+var_208], eax
0x18003f3d1  mov     eax, [rsp+240h+var_1CC]
0x18003f3d5  mov     dword ptr [rsp+240h+var_210], eax
0x18003f3d9  mov     dword ptr [rsp+240h+var_218], r14d
0x18003f3de  mov     dword ptr [rsp+240h+var_220], r13d
0x18003f3e3  call    WPP_SF_DDDDDSSSSSs
0x18003f3e8  test    rdi, rdi
0x18003f3eb  lea     rcx, AppInfo_PerfTrack_Elevation_COM_Start; struct _EVENT_DESCRIPTOR *
0x18003f3f2  cmovnz  rsi, rdi
0x18003f3f6  mov     rdx, rsi; unsigned __int16 *
0x18003f3f9  call    ?AiLogPerfTrackEventEx@@YAKPEBU_EVENT_DESCRIPTOR@@PEBG@Z; AiLogPerfTrackEventEx(_EVENT_DESCRIPTOR const *,ushort const *)
0x18003f3fe  mov     esi, eax
0x18003f400  test    rbx, rbx
0x18003f403  jz      short loc_18003F461
0x18003f405  test    r14b, 20h
0x18003f409  jz      short loc_18003F43B
0x18003f40b  xor     r14d, r14d
0x18003f40e  lea     rdx, [rbp+140h+var_1B8]; unsigned __int16 **
0x18003f412  mov     [rsp+240h+var_218], r14; unsigned __int16 **
0x18003f417  xor     r9d, r9d; unsigned __int16 **
0x18003f41a  xor     r8d, r8d; unsigned __int16 *
0x18003f41d  mov     [rsp+240h+var_220], r14; unsigned __int16 *
0x18003f422  mov     rcx, r15; unsigned __int16 *
0x18003f425  call    ?AiConvertWow64Paths@@YAKPEBGPEAPEBGPEAGPEAPEAG01@Z; AiConvertWow64Paths(ushort const *,ushort const * *,ushort *,ushort * *,ushort const *,ushort const * *)
0x18003f42a  mov     rbx, [rbp+140h+var_1B8]
0x18003f42e  mov     [rsp+240h+Reply], eax
0x18003f432  test    eax, eax
0x18003f434  jz      short loc_18003F43E
0x18003f436  jmp     loc_18003F4FA
0x18003f43b  xor     r14d, r14d
0x18003f43e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003f442  inc     rax
0x18003f445  cmp     [rbx+rax*2], r14w
0x18003f44a  jnz     short loc_18003F442
0x18003f44c  cmp     rax, 7FFFh
0x18003f452  jbe     short loc_18003F464
0x18003f454  mov     [rsp+240h+Reply], 57h ; 'W'
0x18003f45c  jmp     loc_18003F4FA
0x18003f461  xor     r14d, r14d
0x18003f464  mov     r8, [rbp+140h+var_190]; unsigned __int16 *
0x18003f468  lea     rax, [rbp+140h+hMem]
0x18003f46c  mov     rdx, [rbp+140h+var_188]; unsigned __int16 *
0x18003f470  mov     r9, rbx; unsigned __int16 *
0x18003f473  mov     [rsp+240h+var_218], rax; struct _CONSENTUI_PARAM_HEADER **
0x18003f478  mov     rcx, rdi; unsigned __int16 *
0x18003f47b  mov     rax, [rbp+140h+var_160]
0x18003f47f  mov     [rsp+240h+var_220], rax; struct _GUID *
0x18003f484  call    ?AiBuildCOMParams@@YAKPEBG000PEAU_GUID@@PEAPEAU_CONSENTUI_PARAM_HEADER@@@Z; AiBuildCOMParams(ushort const *,ushort const *,ushort const *,ushort const *,_GUID *,_CONSENTUI_PARAM_HEADER * *)
0x18003f489  mov     [rsp+240h+Reply], eax
0x18003f48d  test    eax, eax
0x18003f48f  jnz     short loc_18003F4FA
0x18003f491  mov     rax, [rbp+140h+hMem]
0x18003f495  lea     rcx, [rbp+140h+var_1B0]
0x18003f499  mov     rdx, [rbp+140h+var_198]; void *
0x18003f49d  mov     r9d, r13d; unsigned int
0x18003f4a0  mov     [rsp+240h+var_1D8], rcx; int *
0x18003f4a5  mov     r8, r12; unsigned __int64
0x18003f4a8  lea     rcx, [rsp+240h+var_1C8]
0x18003f4ad  mov     [rsp+240h+var_1E0], rcx; enum UACPROMPT_POLICY *
0x18003f4b2  lea     rcx, [rbp+140h+var_E0]
0x18003f4b6  mov     [rsp+240h+var_1E8], rcx; char *
0x18003f4bb  mov     rcx, [rbp+140h+var_140]
0x18003f4bf  mov     [rsp+240h+var_1F0], r14d; unsigned int
0x18003f4c4  mov     [rsp+240h+var_1F8], rcx; unsigned __int64 *
0x18003f4c9  mov     ecx, [rsp+240h+var_1C4]
0x18003f4cd  mov     [rsp+240h+var_200], rbx; unsigned __int16 *
0x18003f4d2  mov     [rsp+240h+var_208], ecx; unsigned int
0x18003f4d6  xor     ecx, ecx; unsigned int
0x18003f4d8  mov     [rsp+240h+var_210], rax; struct _CONSENTUI_PARAM_HEADER *
0x18003f4dd  mov     [rax+34h], esi
0x18003f4e0  mov     rax, [rbp+140h+var_180]
0x18003f4e4  mov     [rsp+240h+var_218], rax; unsigned __int16 *
0x18003f4e9  mov     eax, [rsp+240h+var_1CC]
0x18003f4ed  mov     dword ptr [rsp+240h+var_220], eax; int
0x18003f4f1  call    ?AipGetTokenForService@@YAKKPEAX_KKHPEBGPEAU_CONSENTUI_PARAM_HEADER@@K2PEA_KKPEBDPEAW4UACPROMPT_POLICY@@PEAH@Z; AipGetTokenForService(ulong,void *,unsigned __int64,ulong,int,ushort const *,_CONSENTUI_PARAM_HEADER *,ulong,ushort const *,unsigned __int64 *,ulong,char const *,UACPROMPT_POLICY *,int *)
0x18003f4f6  mov     [rsp+240h+Reply], eax
0x18003f4fa  mov     rcx, [rbp+140h+hMem]; hMem
0x18003f4fe  call    cs:__imp_LocalFree
0x18003f505  nop     dword ptr [rax+rax+00h]
0x18003f50a  cmp     rbx, r15
0x18003f50d  jz      short loc_18003F522
0x18003f50f  mov     rcx, rbx; hMem
0x18003f512  call    cs:__imp_LocalFree
0x18003f519  nop     dword ptr [rax+rax+00h]
0x18003f51e  mov     [rbp+140h+var_1B8], r15
0x18003f522  lea     rcx, [rbp+140h+var_178]; lpPerformanceCount
0x18003f526  call    cs:__imp_QueryPerformanceCounter
0x18003f52d  nop     dword ptr [rax+rax+00h]
0x18003f532  mov     rax, qword ptr [rbp+140h+var_178]
0x18003f536  sub     rax, qword ptr [rbp+140h+PerformanceCount]
0x18003f53a  imul    rax, 3E8h
0x18003f541  cqo
0x18003f543  idiv    qword ptr [rbp+140h+Frequency]
0x18003f547  mov     [rbp+140h+var_198], rax
0x18003f54b  mov     eax, [rsp+240h+var_1C8]
0x18003f54f  mov     [rsp+240h+var_1C8], eax
0x18003f553  mov     eax, [rsp+240h+Reply]
0x18003f557  cmp     eax, 4C7h
0x18003f55c  jnz     short loc_18003F565
0x18003f55e  mov     [rsp+240h+var_1CC], r14d
0x18003f563  jmp     short loc_18003F575
0x18003f565  test    eax, eax
0x18003f567  jle     short loc_18003F571
0x18003f569  movzx   eax, ax
0x18003f56c  or      eax, 80070000h
0x18003f571  mov     [rsp+240h+var_1CC], eax
0x18003f575  lea     rax, [rbp+140h+var_E0]
0x18003f579  mov     qword ptr [rsp+240h+var_1F0], rax
0x18003f57e  lea     r9, [rbp+140h+var_1C0]
0x18003f582  lea     rax, [rbp+140h+var_198]
0x18003f586  mov     [rsp+240h+var_1F8], rax
0x18003f58b  lea     r8, [rbp+140h+var_1AC]
0x18003f58f  lea     rax, [rsp+240h+var_1C8]
0x18003f594  mov     [rsp+240h+var_200], rax
0x18003f599  lea     rdx, [rsp+240h+Reply]
0x18003f59e  lea     rax, [rbp+140h+var_1B0]
0x18003f5a2  mov     qword ptr [rsp+240h+var_208], rax
0x18003f5a7  lea     rcx, [rsp+240h+var_1CC]
0x18003f5ac  lea     rax, [rbp+140h+var_1A0]
0x18003f5b0  mov     [rsp+240h+var_210], rax
0x18003f5b5  lea     rax, [rbp+140h+var_1B8]
0x18003f5b9  mov     [rsp+240h+var_218], rax
0x18003f5be  lea     rax, [rbp+140h+var_160]
0x18003f5c2  mov     [rsp+240h+var_220], rax
0x18003f5c7  call    ??$COMElevation@JAEAKAEAKAEAKAEAPEAU_GUID@@AEAPEBGAEAPEBGAEAHKAEA_JAEAY0IB@D@LUATelemetry@@SAX$$QEAJAEAK11AEAPEAU_GUID@@AEAPEBG3AEAH$$QEAKAEA_JAEAY0IB@D@Z; LUATelemetry::COMElevation<long,ulong &,ulong &,ulong &,_GUID * &,ushort const * &,ushort const * &,int &,ulong,__int64 &,char (&)[129]>(long &&,ulong &,ulong &,ulong &,_GUID * &,ushort const * &,ushort const * &,int &,ulong &&,__int64 &,char (&)[129])
0x18003f5cc  mov     rcx, [rbp+140h+pAsync]; pAsync
0x18003f5d0  lea     rdx, [rsp+240h+Reply]; Reply
0x18003f5d5  call    cs:__imp_RpcAsyncCompleteCall
0x18003f5dc  nop     dword ptr [rax+rax+00h]
0x18003f5e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f5e8  lea     rax, WPP_GLOBAL_Control
0x18003f5ef  cmp     rcx, rax
0x18003f5f2  jz      short loc_18003F614
0x18003f5f4  test    byte ptr [rcx+1Ch], 1
0x18003f5f8  jz      short loc_18003F614
0x18003f5fa  mov     r9d, [rsp+240h+Reply]
0x18003f5ff  lea     r8, WPP_aba5399977573c9264c162bacbfc9302_Traceguids
0x18003f606  mov     rcx, [rcx+10h]
0x18003f60a  mov     edx, 0Bh
0x18003f60f  call    WPP_SF_D
0x18003f614  lea     rcx, [rbp+140h+var_130]; this
0x18003f618  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18003f61d  mov     rcx, [rbp+140h+var_50]
0x18003f624  xor     rcx, rsp; StackCookie
0x18003f627  call    __security_check_cookie
0x18003f62c  add     rsp, 208h
0x18003f633  pop     r15
0x18003f635  pop     r14
0x18003f637  pop     r13
0x18003f639  pop     r12
0x18003f63b  pop     rdi
  ... truncated ...
```
