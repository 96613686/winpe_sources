# RAiForceElevationPromptForCOM

- ea: `0x18003ced0`
- end: `0x18003d3ca`
- name: `RAiForceElevationPromptForCOM`
- size: `1274`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

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
- `0x18003ced0`
- `0x18003e2c4`
- `0x1800402e4`
- `0x18004292a`
- `0x180042950`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003d35e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003d35e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d287`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d29b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d287`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d29b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003cf93`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003d2af`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003cf93`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003d2af`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003cfa3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003cfa3`
- `ntdll!NtClose` at `0x18003d273`
- `ntdll!NtClose` at `0x18003d273`

## string_xrefs

- `0x18003d039`: `hwnd = %x dwRunLevel = %x dwClientFlags = %x fAdjustTokenSD = %x dwTimeout = %x\n	lpDesktop = %ws\n	lpFriendlyName = %ws\n	lpServerBinary = %ws\n	lpIconReference = %ws\n	lpRequestorPath = %ws\n	lpCvStr = %s\n`
- `0x18003d02d`: `RAiForceElevationPromptForCOM`

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
        unsigned __int16 *a9,
        unsigned __int16 *a10,
        unsigned __int16 *a11,
        unsigned __int16 *a12,
        unsigned int a13)
{
  const unsigned __int16 *v15; // rdi
  unsigned __int16 *v16; // rbx
  char v17; // r14
  const unsigned __int16 *v18; // rsi
  const unsigned __int16 *v19; // rdx
  unsigned __int16 *v20; // r8
  unsigned __int16 *v21; // r9
  const unsigned __int16 *v22; // rax
  void *v23; // rax
  volatile signed __int64 *v24; // rbx
  const unsigned __int16 *v25; // rcx
  const unsigned __int16 *v26; // rax
  unsigned int v27; // esi
  unsigned int v28; // eax
  unsigned __int64 v29; // rax
  struct _CONSENTUI_PARAM_HEADER *v30; // rax
  unsigned int v31; // eax
  unsigned int v32[2]; // [rsp+38h] [rbp-C8h]
  int Reply; // [rsp+70h] [rbp-90h] BYREF
  int v34; // [rsp+74h] [rbp-8Ch] BYREF
  int v35; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v36; // [rsp+7Ch] [rbp-84h]
  int v37; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL v38; // [rsp+88h] [rbp-78h] BYREF
  int v39; // [rsp+90h] [rbp-70h] BYREF
  int v40; // [rsp+94h] [rbp-6Ch] BYREF
  HANDLE Handle; // [rsp+98h] [rbp-68h] BYREF
  HLOCAL hMem; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v43; // [rsp+A8h] [rbp-58h] BYREF
  void *v44; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v45; // [rsp+B8h] [rbp-48h]
  unsigned __int16 *v46; // [rsp+C0h] [rbp-40h]
  unsigned __int16 *v47; // [rsp+C8h] [rbp-38h]
  LARGE_INTEGER v48; // [rsp+D0h] [rbp-30h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+D8h] [rbp-28h] BYREF
  LARGE_INTEGER Frequency; // [rsp+E0h] [rbp-20h] BYREF
  struct _GUID *v51; // [rsp+E8h] [rbp-18h] BYREF
  const unsigned __int16 *v52; // [rsp+F0h] [rbp-10h]
  unsigned __int16 *v53; // [rsp+F8h] [rbp-8h]
  unsigned __int16 *v54; // [rsp+100h] [rbp+0h]
  PRPC_ASYNC_STATE pAsync; // [rsp+108h] [rbp+8h]
  char v56[80]; // [rsp+110h] [rbp+10h] BYREF
  char v57[144]; // [rsp+160h] [rbp+60h] BYREF

  v15 = a9;
  v16 = a12;
  v17 = a5;
  v47 = a7;
  v34 = a6;
  v51 = a8;
  v36 = a13;
  v44 = a2;
  pAsync = a1;
  hMem = 0;
  v40 = 0;
  Handle = 0;
  v39 = 0;
  v35 = 0;
  Frequency.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  v48.QuadPart = 0;
  v46 = a10;
  v45 = a11;
  v37 = a5;
  v43 = a9;
  v38 = a12;
  QueryPerformanceCounter(&PerformanceCount);
  QueryPerformanceFrequency(&Frequency);
  memset_0(v57, 0, 0x81u);
  v18 = L"NULL";
  v19 = a11;
  if ( !a11 )
    v19 = L"NULL";
  v52 = v19;
  v20 = v46;
  if ( !v46 )
    v20 = L"NULL";
  v53 = v20;
  v21 = v47;
  v22 = a9;
  if ( !v47 )
    v21 = L"NULL";
  v54 = v21;
  if ( !a9 )
    v22 = L"NULL";
  v32[0] = v36;
  LUATelemetry::WatchCurrentThread(
    v56,
    "RAiForceElevationPromptForCOM",
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
    v34,
    *(_QWORD *)v32,
    v21,
    v22,
    v20,
    v19);
  if ( g_pCOMElevationActivityTelemetryRateLimiter
    && (unsigned int)RateLimiter::RequestPermission(g_pCOMElevationActivityTelemetryRateLimiter) )
  {
    v23 = operator new(0x90u);
    if ( v23 )
      v24 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v23);
    else
      v24 = 0;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v24,
      _InterlockedExchangeAdd64(v24 + 17, 0),
      v57);
    if ( v24 )
      operator delete((void *)v24);
    v16 = (unsigned __int16 *)v38;
    v15 = v43;
    v17 = v37;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v25 = L"NULL";
    if ( v16 )
      v25 = v16;
    v26 = L"NULL";
    if ( v15 )
      v26 = v15;
    WPP_SF_DDDDDSSSSSs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      (_DWORD)WPP_GLOBAL_Control,
      a3,
      a4,
      v17,
      v34,
      v36,
      (__int64)v54,
      (__int64)v26,
      (__int64)v53,
      (__int64)v52,
      (__int64)v25,
      (__int64)v57);
  }
  if ( v15 )
    v18 = v15;
  v27 = AiLogPerfTrackEventEx(&AppInfo_PerfTrack_Elevation_COM_Start, v18);
  if ( v16 )
  {
    if ( (v17 & 0x20) != 0 )
    {
      v28 = AiConvertWow64Paths(a12, (const unsigned __int16 **)&v38, 0, 0, 0, 0);
      v16 = (unsigned __int16 *)v38;
      Reply = v28;
      if ( v28 )
        goto LABEL_35;
    }
    v29 = -1;
    do
      ++v29;
    while ( v16[v29] );
    if ( v29 > 0x7FFF )
    {
      Reply = 87;
      goto LABEL_35;
    }
  }
  Reply = AiBuildCOMParams(v15, v46, v45, v16, v51, (struct _CONSENTUI_PARAM_HEADER **)&hMem);
  if ( !Reply )
  {
    v30 = (struct _CONSENTUI_PARAM_HEADER *)hMem;
    v40 = 0x2000000;
    *((_DWORD *)hMem + 13) = v27;
    Reply = AipGetTokenForService(
              0,
              v44,
              a3,
              a4,
              v34,
              v47,
              v30,
              v36,
              v16,
              (unsigned __int64 *)&Handle,
              0x2000000u,
              v57,
              (enum UACPROMPT_POLICY *)&v35,
              &v39);
  }
LABEL_35:
  if ( Handle )
  {
    NtClose(Handle);
    Handle = 0;
  }
  LocalFree(hMem);
  if ( v16 != a12 )
  {
    LocalFree(v16);
    v38 = a12;
  }
  QueryPerformanceCounter(&v48);
  v44 = (void *)(1000 * (v48.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart);
  v31 = Reply;
  if ( Reply == 1223 )
  {
    v34 = 0;
  }
  else
  {
    if ( Reply > 0 )
      v31 = (unsigned __int16)Reply | 0x80070000;
    v34 = v31;
  }
  LUATelemetry::COMElevation<long,unsigned long &,unsigned long &,unsigned long &,_GUID * &,unsigned short const * &,unsigned short const * &,int &,unsigned long,__int64 &,char (&)[129]>(
    (unsigned int)&v34,
    (unsigned int)&Reply,
    (unsigned int)&v40,
    (unsigned int)&v37,
    (__int64)&v51,
    (__int64)&v38,
    (__int64)&v43,
    (__int64)&v39,
    (__int64)&v35,
    (__int64)&v44,
    v57);
  RpcAsyncCompleteCall(pAsync, &Reply);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      &WPP_aba5399977573c9264c162bacbfc9302_Traceguids,
      (unsigned int)Reply);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v56);
}

```

## disassembly

```asm
0x18003ced0  push    rbp
0x18003ced2  push    rbx
0x18003ced3  push    rsi
0x18003ced4  push    rdi
0x18003ced5  push    r12
0x18003ced7  push    r13
0x18003ced9  push    r14
0x18003cedb  push    r15
0x18003cedd  lea     rbp, [rsp-108h]
0x18003cee5  sub     rsp, 208h
0x18003ceec  mov     rax, cs:__security_cookie
0x18003cef3  xor     rax, rsp
0x18003cef6  mov     [rbp+140h+var_50], rax
0x18003cefd  mov     rax, [rbp+140h+arg_30]
0x18003cf04  mov     r12, r8
0x18003cf07  mov     r8, [rbp+140h+arg_50]
0x18003cf0e  mov     r13d, r9d
0x18003cf11  mov     r15, [rbp+140h+arg_58]
0x18003cf18  mov     rdi, [rbp+140h+arg_40]
0x18003cf1f  mov     rbx, r15
0x18003cf22  mov     r14d, [rbp+140h+arg_20]
0x18003cf29  mov     [rbp+140h+var_178], rax
0x18003cf2d  mov     eax, [rbp+140h+arg_28]
0x18003cf33  mov     [rsp+240h+var_1CC], eax
0x18003cf37  mov     rax, [rbp+140h+arg_38]
0x18003cf3e  mov     [rbp+140h+var_158], rax
0x18003cf42  mov     eax, [rbp+140h+arg_60]
0x18003cf48  mov     [rsp+240h+var_1C4], eax
0x18003cf4c  xor     eax, eax
0x18003cf4e  mov     [rbp+140h+var_190], rdx
0x18003cf52  mov     rdx, [rbp+140h+arg_48]
0x18003cf59  mov     [rbp+140h+pAsync], rcx
0x18003cf5d  lea     rcx, [rbp+140h+PerformanceCount]; lpPerformanceCount
0x18003cf61  mov     [rbp+140h+hMem], rax
0x18003cf65  mov     [rbp+140h+var_1AC], eax
0x18003cf68  mov     [rbp+140h+Handle], rax
0x18003cf6c  mov     [rbp+140h+var_1B0], eax
0x18003cf6f  mov     [rsp+240h+var_1C8], eax
0x18003cf73  mov     qword ptr [rbp+140h+Frequency], rax
0x18003cf77  mov     qword ptr [rbp+140h+PerformanceCount], rax
0x18003cf7b  mov     qword ptr [rbp+140h+var_170], rax
0x18003cf7f  mov     [rbp+140h+var_180], rdx
0x18003cf83  mov     [rbp+140h+var_188], r8
0x18003cf87  mov     [rbp+140h+var_1C0], r14d
0x18003cf8b  mov     [rbp+140h+var_198], rdi
0x18003cf8f  mov     [rbp+140h+var_1B8], rbx
0x18003cf93  call    cs:__imp_QueryPerformanceCounter
0x18003cf9a  nop     dword ptr [rax+rax+00h]
0x18003cf9f  lea     rcx, [rbp+140h+Frequency]; lpFrequency
0x18003cfa3  call    cs:__imp_QueryPerformanceFrequency
0x18003cfaa  nop     dword ptr [rax+rax+00h]
0x18003cfaf  xor     edx, edx; Val
0x18003cfb1  lea     rcx, [rbp+140h+var_E0]; void *
0x18003cfb5  mov     r8d, 81h; Size
0x18003cfbb  call    memset_0
0x18003cfc0  mov     rax, [rbp+140h+var_188]
0x18003cfc4  lea     rsi, aNull_0; "NULL"
0x18003cfcb  test    rax, rax
0x18003cfce  lea     r10, [rbp+140h+var_E0]
0x18003cfd2  mov     [rsp+240h+var_1D8], r10
0x18003cfd7  mov     rdx, rax
0x18003cfda  mov     rax, [rbp+140h+var_180]
0x18003cfde  cmovz   rdx, rsi
0x18003cfe2  test    rax, rax
0x18003cfe5  mov     [rbp+140h+var_150], rdx
0x18003cfe9  mov     r8, rax
0x18003cfec  mov     rcx, r15
0x18003cfef  mov     rax, [rbp+140h+var_178]
0x18003cff3  cmovz   r8, rsi
0x18003cff7  test    rax, rax
0x18003cffa  mov     [rbp+140h+var_148], r8
0x18003cffe  mov     r9, rax
0x18003d001  mov     rax, rdi
0x18003d004  cmovz   r9, rsi
0x18003d008  test    r15, r15
0x18003d00b  mov     [rbp+140h+var_140], r9
0x18003d00f  cmovz   rcx, rsi
0x18003d013  test    rdi, rdi
0x18003d016  mov     [rsp+240h+var_1E0], rcx
0x18003d01b  lea     rcx, [rbp+140h+var_130]
0x18003d01f  mov     [rsp+240h+var_1E8], rdx
0x18003d024  cmovz   rax, rsi
0x18003d028  mov     qword ptr [rsp+240h+var_1F0], r8
0x18003d02d  lea     rdx, aRaiforceelevat; "RAiForceElevationPromptForCOM"
0x18003d034  mov     [rsp+240h+var_1F8], rax
0x18003d039  lea     r8, aHwndXDwrunleve_0; "hwnd = %x dwRunLevel = %x dwClientFlags"...
0x18003d040  mov     eax, [rsp+240h+var_1C4]
0x18003d044  mov     [rsp+240h+var_200], r9
0x18003d049  mov     r9d, r12d
0x18003d04c  mov     [rsp+240h+var_208], eax
0x18003d050  mov     eax, [rsp+240h+var_1CC]
0x18003d054  mov     dword ptr [rsp+240h+var_210], eax
0x18003d058  mov     dword ptr [rsp+240h+var_218], r14d
0x18003d05d  mov     dword ptr [rsp+240h+var_220], r13d
0x18003d062  call    ?WatchCurrentThread@LUATelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; LUATelemetry::WatchCurrentThread(char const *,char const *,...)
0x18003d067  mov     rcx, cs:?g_pCOMElevationActivityTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; this
0x18003d06e  test    rcx, rcx
0x18003d071  jz      short loc_18003D0CA
0x18003d073  call    ?RequestPermission@RateLimiter@@QEAAHXZ; RateLimiter::RequestPermission(void)
0x18003d078  test    eax, eax
0x18003d07a  jz      short loc_18003D0CA
0x18003d07c  mov     ecx, 90h; Size
0x18003d081  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003d086  test    rax, rax
0x18003d089  jz      short loc_18003D098
0x18003d08b  mov     rcx, rax
0x18003d08e  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18003d093  mov     rbx, rax
0x18003d096  jmp     short loc_18003D09A
0x18003d098  xor     ebx, ebx
0x18003d09a  xor     edx, edx
0x18003d09c  lock xadd [rbx+88h], rdx; unsigned __int64
0x18003d0a5  lea     r8, [rbp+140h+var_E0]; char *
0x18003d0a9  mov     rcx, rbx; this
0x18003d0ac  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18003d0b1  test    rbx, rbx
0x18003d0b4  jz      short loc_18003D0BE
0x18003d0b6  mov     rcx, rbx; Block
0x18003d0b9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003d0be  mov     rbx, [rbp+140h+var_1B8]
0x18003d0c2  mov     rdi, [rbp+140h+var_198]
0x18003d0c6  mov     r14d, [rbp+140h+var_1C0]
0x18003d0ca  mov     r8, cs:WPP_GLOBAL_Control
0x18003d0d1  lea     rax, WPP_GLOBAL_Control
0x18003d0d8  cmp     r8, rax
0x18003d0db  jz      short loc_18003D151
0x18003d0dd  test    byte ptr [r8+1Ch], 1
0x18003d0e2  jz      short loc_18003D151
0x18003d0e4  test    rbx, rbx
0x18003d0e7  lea     r9, [rbp+140h+var_E0]
0x18003d0eb  mov     [rsp+240h+var_1D8], r9
0x18003d0f0  mov     rcx, rsi
0x18003d0f3  cmovnz  rcx, rbx
0x18003d0f7  mov     rax, rsi
0x18003d0fa  mov     [rsp+240h+var_1E0], rcx
0x18003d0ff  test    rdi, rdi
0x18003d102  mov     rcx, [rbp+140h+var_150]
0x18003d106  mov     edx, 0Ch
0x18003d10b  mov     [rsp+240h+var_1E8], rcx
0x18003d110  cmovnz  rax, rdi
0x18003d114  mov     rcx, [rbp+140h+var_148]
0x18003d118  mov     r9d, r12d
0x18003d11b  mov     qword ptr [rsp+240h+var_1F0], rcx
0x18003d120  mov     rcx, [r8+10h]
0x18003d124  mov     [rsp+240h+var_1F8], rax
0x18003d129  mov     rax, [rbp+140h+var_140]
0x18003d12d  mov     [rsp+240h+var_200], rax
0x18003d132  mov     eax, [rsp+240h+var_1C4]
0x18003d136  mov     [rsp+240h+var_208], eax
0x18003d13a  mov     eax, [rsp+240h+var_1CC]
0x18003d13e  mov     dword ptr [rsp+240h+var_210], eax
0x18003d142  mov     dword ptr [rsp+240h+var_218], r14d
0x18003d147  mov     dword ptr [rsp+240h+var_220], r13d
0x18003d14c  call    WPP_SF_DDDDDSSSSSs
0x18003d151  test    rdi, rdi
0x18003d154  lea     rcx, AppInfo_PerfTrack_Elevation_COM_Start; struct _EVENT_DESCRIPTOR *
0x18003d15b  cmovnz  rsi, rdi
0x18003d15f  mov     rdx, rsi; unsigned __int16 *
0x18003d162  call    ?AiLogPerfTrackEventEx@@YAKPEBU_EVENT_DESCRIPTOR@@PEBG@Z; AiLogPerfTrackEventEx(_EVENT_DESCRIPTOR const *,ushort const *)
0x18003d167  mov     esi, eax
0x18003d169  test    rbx, rbx
0x18003d16c  jz      short loc_18003D1CA
0x18003d16e  test    r14b, 20h
0x18003d172  jz      short loc_18003D1A4
0x18003d174  xor     r14d, r14d
0x18003d177  lea     rdx, [rbp+140h+var_1B8]; unsigned __int16 **
0x18003d17b  mov     [rsp+240h+var_218], r14; unsigned __int16 **
0x18003d180  xor     r9d, r9d; unsigned __int16 **
0x18003d183  xor     r8d, r8d; unsigned __int16 *
0x18003d186  mov     [rsp+240h+var_220], r14; unsigned __int16 *
0x18003d18b  mov     rcx, r15; unsigned __int16 *
0x18003d18e  call    ?AiConvertWow64Paths@@YAKPEBGPEAPEBGPEAGPEAPEAG01@Z; AiConvertWow64Paths(ushort const *,ushort const * *,ushort *,ushort * *,ushort const *,ushort const * *)
0x18003d193  mov     rbx, [rbp+140h+var_1B8]
0x18003d197  mov     [rsp+240h+Reply], eax
0x18003d19b  test    eax, eax
0x18003d19d  jz      short loc_18003D1A7
0x18003d19f  jmp     loc_18003D26A
0x18003d1a4  xor     r14d, r14d
0x18003d1a7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003d1ab  inc     rax
0x18003d1ae  cmp     [rbx+rax*2], r14w
0x18003d1b3  jnz     short loc_18003D1AB
0x18003d1b5  cmp     rax, 7FFFh
0x18003d1bb  jbe     short loc_18003D1CD
0x18003d1bd  mov     [rsp+240h+Reply], 57h ; 'W'
0x18003d1c5  jmp     loc_18003D26A
0x18003d1ca  xor     r14d, r14d
0x18003d1cd  mov     r8, [rbp+140h+var_188]; unsigned __int16 *
0x18003d1d1  lea     rax, [rbp+140h+hMem]
0x18003d1d5  mov     rdx, [rbp+140h+var_180]; unsigned __int16 *
0x18003d1d9  mov     r9, rbx; unsigned __int16 *
0x18003d1dc  mov     [rsp+240h+var_218], rax; struct _CONSENTUI_PARAM_HEADER **
0x18003d1e1  mov     rcx, rdi; unsigned __int16 *
0x18003d1e4  mov     rax, [rbp+140h+var_158]
0x18003d1e8  mov     [rsp+240h+var_220], rax; struct _GUID *
0x18003d1ed  call    ?AiBuildCOMParams@@YAKPEBG000PEAU_GUID@@PEAPEAU_CONSENTUI_PARAM_HEADER@@@Z; AiBuildCOMParams(ushort const *,ushort const *,ushort const *,ushort const *,_GUID *,_CONSENTUI_PARAM_HEADER * *)
0x18003d1f2  mov     [rsp+240h+Reply], eax
0x18003d1f6  test    eax, eax
0x18003d1f8  jnz     short loc_18003D26A
0x18003d1fa  mov     rax, [rbp+140h+hMem]
0x18003d1fe  lea     rcx, [rbp+140h+var_1B0]
0x18003d202  mov     [rsp+240h+var_1D8], rcx; int *
0x18003d207  mov     edx, 2000000h
0x18003d20c  lea     rcx, [rsp+240h+var_1C8]
0x18003d211  mov     [rbp+140h+var_1AC], edx
0x18003d214  mov     [rsp+240h+var_1E0], rcx; enum UACPROMPT_POLICY *
0x18003d219  mov     r9d, r13d; unsigned int
0x18003d21c  mov     [rax+34h], esi
0x18003d21f  lea     rcx, [rbp+140h+var_E0]
0x18003d223  mov     [rsp+240h+var_1E8], rcx; char *
0x18003d228  mov     r8, r12; unsigned __int64
0x18003d22b  mov     [rsp+240h+var_1F0], edx; unsigned int
0x18003d22f  lea     rcx, [rbp+140h+Handle]
0x18003d233  mov     rdx, [rbp+140h+var_190]; void *
0x18003d237  mov     [rsp+240h+var_1F8], rcx; unsigned __int64 *
0x18003d23c  mov     ecx, [rsp+240h+var_1C4]
0x18003d240  mov     [rsp+240h+var_200], rbx; unsigned __int16 *
0x18003d245  mov     [rsp+240h+var_208], ecx; unsigned int
0x18003d249  xor     ecx, ecx; unsigned int
0x18003d24b  mov     [rsp+240h+var_210], rax; struct _CONSENTUI_PARAM_HEADER *
0x18003d250  mov     rax, [rbp+140h+var_178]
0x18003d254  mov     [rsp+240h+var_218], rax; unsigned __int16 *
0x18003d259  mov     eax, [rsp+240h+var_1CC]
0x18003d25d  mov     dword ptr [rsp+240h+var_220], eax; int
0x18003d261  call    ?AipGetTokenForService@@YAKKPEAX_KKHPEBGPEAU_CONSENTUI_PARAM_HEADER@@K2PEA_KKPEBDPEAW4UACPROMPT_POLICY@@PEAH@Z; AipGetTokenForService(ulong,void *,unsigned __int64,ulong,int,ushort const *,_CONSENTUI_PARAM_HEADER *,ulong,ushort const *,unsigned __int64 *,ulong,char const *,UACPROMPT_POLICY *,int *)
0x18003d266  mov     [rsp+240h+Reply], eax
0x18003d26a  mov     rcx, [rbp+140h+Handle]; Handle
0x18003d26e  test    rcx, rcx
0x18003d271  jz      short loc_18003D283
0x18003d273  call    cs:__imp_NtClose
0x18003d27a  nop     dword ptr [rax+rax+00h]
0x18003d27f  mov     [rbp+140h+Handle], r14
0x18003d283  mov     rcx, [rbp+140h+hMem]; hMem
0x18003d287  call    cs:__imp_LocalFree
0x18003d28e  nop     dword ptr [rax+rax+00h]
0x18003d293  cmp     rbx, r15
0x18003d296  jz      short loc_18003D2AB
0x18003d298  mov     rcx, rbx; hMem
0x18003d29b  call    cs:__imp_LocalFree
0x18003d2a2  nop     dword ptr [rax+rax+00h]
0x18003d2a7  mov     [rbp+140h+var_1B8], r15
0x18003d2ab  lea     rcx, [rbp+140h+var_170]; lpPerformanceCount
0x18003d2af  call    cs:__imp_QueryPerformanceCounter
0x18003d2b6  nop     dword ptr [rax+rax+00h]
0x18003d2bb  mov     rax, qword ptr [rbp+140h+var_170]
0x18003d2bf  sub     rax, qword ptr [rbp+140h+PerformanceCount]
0x18003d2c3  imul    rax, 3E8h
0x18003d2ca  cqo
0x18003d2cc  idiv    qword ptr [rbp+140h+Frequency]
0x18003d2d0  mov     [rbp+140h+var_190], rax
0x18003d2d4  mov     eax, [rsp+240h+var_1C8]
0x18003d2d8  mov     [rsp+240h+var_1C8], eax
0x18003d2dc  mov     eax, [rsp+240h+Reply]
0x18003d2e0  cmp     eax, 4C7h
0x18003d2e5  jnz     short loc_18003D2EE
0x18003d2e7  mov     [rsp+240h+var_1CC], r14d
0x18003d2ec  jmp     short loc_18003D2FE
0x18003d2ee  test    eax, eax
0x18003d2f0  jle     short loc_18003D2FA
0x18003d2f2  movzx   eax, ax
0x18003d2f5  or      eax, 80070000h
0x18003d2fa  mov     [rsp+240h+var_1CC], eax
0x18003d2fe  lea     rax, [rbp+140h+var_E0]
0x18003d302  mov     qword ptr [rsp+240h+var_1F0], rax
0x18003d307  lea     r9, [rbp+140h+var_1C0]
0x18003d30b  lea     rax, [rbp+140h+var_190]
0x18003d30f  mov     [rsp+240h+var_1F8], rax
0x18003d314  lea     r8, [rbp+140h+var_1AC]
0x18003d318  lea     rax, [rsp+240h+var_1C8]
0x18003d31d  mov     [rsp+240h+var_200], rax
0x18003d322  lea     rdx, [rsp+240h+Reply]
0x18003d327  lea     rax, [rbp+140h+var_1B0]
0x18003d32b  mov     qword ptr [rsp+240h+var_208], rax
0x18003d330  lea     rcx, [rsp+240h+var_1CC]
0x18003d335  lea     rax, [rbp+140h+var_198]
0x18003d339  mov     [rsp+240h+var_210], rax
0x18003d33e  lea     rax, [rbp+140h+var_1B8]
0x18003d342  mov     [rsp+240h+var_218], rax
0x18003d347  lea     rax, [rbp+140h+var_158]
0x18003d34b  mov     [rsp+240h+var_220], rax
0x18003d350  call    ??$COMElevation@JAEAKAEAKAEAKAEAPEAU_GUID@@AEAPEBGAEAPEBGAEAHKAEA_JAEAY0IB@D@LUATelemetry@@SAX$$QEAJAEAK11AEAPEAU_GUID@@AEAPEBG3AEAH$$QEAKAEA_JAEAY0IB@D@Z; LUATelemetry::COMElevation<long,ulong &,ulong &,ulong &,_GUID * &,ushort const * &,ushort const * &,int &,ulong,__int64 &,char (&)[129]>(long &&,ulong &,ulong &,ulong &,_GUID * &,ushort const * &,ushort const * &,int &,ulong &&,__int64 &,char (&)[129])
0x18003d355  mov     rcx, [rbp+140h+pAsync]; pAsync
0x18003d359  lea     rdx, [rsp+240h+Reply]; Reply
0x18003d35e  call    cs:__imp_RpcAsyncCompleteCall
0x18003d365  nop     dword ptr [rax+rax+00h]
0x18003d36a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d371  lea     rax, WPP_GLOBAL_Control
0x18003d378  cmp     rcx, rax
0x18003d37b  jz      short loc_18003D39D
0x18003d37d  test    byte ptr [rcx+1Ch], 1
0x18003d381  jz      short loc_18003D39D
0x18003d383  mov     r9d, [rsp+240h+Reply]
0x18003d388  lea     r8, WPP_aba5399977573c9264c162bacbfc9302_Traceguids
0x18003d38f  mov     rcx, [rcx+10h]
0x18003d393  mov     edx, 0Dh
0x18003d398  call    WPP_SF_D
0x18003d39d  lea     rcx, [rbp+140h+var_130]; this
0x18003d3a1  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18003d3a6  mov     rcx, [rbp+140h+var_50]
0x18003d3ad  xor     rcx, rsp; StackCookie
  ... truncated ...
```
