# RAiGetTokenForCOM

- ea: `0x18003f6a0`
- end: `0x18003fb81`
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
- `0x180026eb4`
- `0x1800272f4`
- `0x1800389b0`
- `0x180039720`
- `0x18003e3c4`
- `0x18003e5d4`
- `0x18003f6a0`
- `0x1800403d4`
- `0x1800423f4`
- `0x1800449fa`
- `0x180044a20`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003fb15`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003fb15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fa3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fa52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fa3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fa52`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003f77a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003f77a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003f76a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003fa66`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003f76a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003fa66`

## string_xrefs

- `0x18003f810`: `hwnd = %x dwRunLevel = %x dwClientFlags = %x fAdjustTokenSD = %x dwTimeout = %x\n	lpDesktop = %ws\n	lpFriendlyName = %ws\n	lpServerBinary = %ws\n	lpIconReference = %ws\n	lpRequestorPath = %ws\n	lpCvStr = %s\n`
- `0x18003f804`: `RAiGetTokenForCOM`

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
0x18003f6a0  push    rbp
0x18003f6a2  push    rbx
0x18003f6a3  push    rsi
0x18003f6a4  push    rdi
0x18003f6a5  push    r12
0x18003f6a7  push    r13
0x18003f6a9  push    r14
0x18003f6ab  push    r15
0x18003f6ad  lea     rbp, [rsp-108h]
0x18003f6b5  sub     rsp, 208h
0x18003f6bc  mov     rax, cs:__security_cookie
0x18003f6c3  xor     rax, rsp
0x18003f6c6  mov     [rbp+140h+var_50], rax
0x18003f6cd  mov     rax, [rbp+140h+arg_30]
0x18003f6d4  mov     r12, r8
0x18003f6d7  mov     r8, [rbp+140h+arg_50]
0x18003f6de  mov     r13d, r9d
0x18003f6e1  mov     r15, [rbp+140h+arg_58]
0x18003f6e8  mov     rdi, [rbp+140h+arg_40]
0x18003f6ef  mov     rbx, r15
0x18003f6f2  mov     r14d, [rbp+140h+arg_20]
0x18003f6f9  mov     [rbp+140h+var_180], rax
0x18003f6fd  mov     eax, [rbp+140h+arg_28]
0x18003f703  mov     [rsp+240h+var_1CC], eax
0x18003f707  mov     rax, [rbp+140h+arg_38]
0x18003f70e  mov     [rbp+140h+var_160], rax
0x18003f712  mov     eax, [rbp+140h+arg_60]
0x18003f718  mov     [rsp+240h+var_1C4], eax
0x18003f71c  mov     rax, [rbp+140h+arg_68]
0x18003f723  mov     [rbp+140h+var_140], rax
0x18003f727  xor     eax, eax
0x18003f729  mov     [rbp+140h+var_198], rdx
0x18003f72d  mov     rdx, [rbp+140h+arg_48]
0x18003f734  mov     [rbp+140h+pAsync], rcx
0x18003f738  lea     rcx, [rbp+140h+PerformanceCount]; lpPerformanceCount
0x18003f73c  mov     [rbp+140h+hMem], rax
0x18003f740  mov     [rbp+140h+var_1AC], eax
0x18003f743  mov     [rbp+140h+var_1B0], eax
0x18003f746  mov     [rsp+240h+var_1C8], eax
0x18003f74a  mov     qword ptr [rbp+140h+Frequency], rax
0x18003f74e  mov     qword ptr [rbp+140h+PerformanceCount], rax
0x18003f752  mov     qword ptr [rbp+140h+var_178], rax
0x18003f756  mov     [rbp+140h+var_188], rdx
0x18003f75a  mov     [rbp+140h+var_190], r8
0x18003f75e  mov     [rbp+140h+var_1C0], r14d
0x18003f762  mov     [rbp+140h+var_1A0], rdi
0x18003f766  mov     [rbp+140h+var_1B8], rbx
0x18003f76a  call    cs:__imp_QueryPerformanceCounter
0x18003f771  nop     dword ptr [rax+rax+00h]
0x18003f776  lea     rcx, [rbp+140h+Frequency]; lpFrequency
0x18003f77a  call    cs:__imp_QueryPerformanceFrequency
0x18003f781  nop     dword ptr [rax+rax+00h]
0x18003f786  xor     edx, edx; Val
0x18003f788  lea     rcx, [rbp+140h+var_E0]; void *
0x18003f78c  mov     r8d, 81h; Size
0x18003f792  call    memset_0
0x18003f797  mov     rax, [rbp+140h+var_190]
0x18003f79b  lea     rsi, aNull_0; "NULL"
0x18003f7a2  test    rax, rax
0x18003f7a5  lea     r10, [rbp+140h+var_E0]
0x18003f7a9  mov     [rsp+240h+var_1D8], r10
0x18003f7ae  mov     rdx, rax
0x18003f7b1  mov     rax, [rbp+140h+var_188]
0x18003f7b5  cmovz   rdx, rsi
0x18003f7b9  test    rax, rax
0x18003f7bc  mov     [rbp+140h+var_158], rdx
0x18003f7c0  mov     r8, rax
0x18003f7c3  mov     rcx, r15
0x18003f7c6  mov     rax, [rbp+140h+var_180]
0x18003f7ca  cmovz   r8, rsi
0x18003f7ce  test    rax, rax
0x18003f7d1  mov     [rbp+140h+var_150], r8
0x18003f7d5  mov     r9, rax
0x18003f7d8  mov     rax, rdi
0x18003f7db  cmovz   r9, rsi
0x18003f7df  test    r15, r15
0x18003f7e2  mov     [rbp+140h+var_148], r9
0x18003f7e6  cmovz   rcx, rsi
0x18003f7ea  test    rdi, rdi
0x18003f7ed  mov     [rsp+240h+var_1E0], rcx
0x18003f7f2  lea     rcx, [rbp+140h+var_130]
0x18003f7f6  mov     [rsp+240h+var_1E8], rdx
0x18003f7fb  cmovz   rax, rsi
0x18003f7ff  mov     qword ptr [rsp+240h+var_1F0], r8
0x18003f804  lea     rdx, aRaigettokenfor_0; "RAiGetTokenForCOM"
0x18003f80b  mov     [rsp+240h+var_1F8], rax
0x18003f810  lea     r8, aHwndXDwrunleve_0; "hwnd = %x dwRunLevel = %x dwClientFlags"...
0x18003f817  mov     eax, [rsp+240h+var_1C4]
0x18003f81b  mov     [rsp+240h+var_200], r9
0x18003f820  mov     r9d, r12d
0x18003f823  mov     [rsp+240h+var_208], eax
0x18003f827  mov     eax, [rsp+240h+var_1CC]
0x18003f82b  mov     dword ptr [rsp+240h+var_210], eax
0x18003f82f  mov     dword ptr [rsp+240h+var_218], r14d
0x18003f834  mov     dword ptr [rsp+240h+var_220], r13d
0x18003f839  call    ?WatchCurrentThread@LUATelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; LUATelemetry::WatchCurrentThread(char const *,char const *,...)
0x18003f83e  mov     rcx, cs:?g_pCOMElevationActivityTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; this
0x18003f845  test    rcx, rcx
0x18003f848  jz      short loc_18003F8A1
0x18003f84a  call    ?RequestPermission@RateLimiter@@QEAAHXZ; RateLimiter::RequestPermission(void)
0x18003f84f  test    eax, eax
0x18003f851  jz      short loc_18003F8A1
0x18003f853  mov     ecx, 90h; Size
0x18003f858  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003f85d  test    rax, rax
0x18003f860  jz      short loc_18003F86F
0x18003f862  mov     rcx, rax
0x18003f865  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18003f86a  mov     rbx, rax
0x18003f86d  jmp     short loc_18003F871
0x18003f86f  xor     ebx, ebx
0x18003f871  xor     edx, edx
0x18003f873  lock xadd [rbx+88h], rdx; unsigned __int64
0x18003f87c  lea     r8, [rbp+140h+var_E0]; char *
0x18003f880  mov     rcx, rbx; this
0x18003f883  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18003f888  test    rbx, rbx
0x18003f88b  jz      short loc_18003F895
0x18003f88d  mov     rcx, rbx; Block
0x18003f890  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003f895  mov     rbx, [rbp+140h+var_1B8]
0x18003f899  mov     rdi, [rbp+140h+var_1A0]
0x18003f89d  mov     r14d, [rbp+140h+var_1C0]
0x18003f8a1  mov     r8, cs:WPP_GLOBAL_Control
0x18003f8a8  lea     rax, WPP_GLOBAL_Control
0x18003f8af  cmp     r8, rax
0x18003f8b2  jz      short loc_18003F928
0x18003f8b4  test    byte ptr [r8+1Ch], 1
0x18003f8b9  jz      short loc_18003F928
0x18003f8bb  test    rbx, rbx
0x18003f8be  lea     r9, [rbp+140h+var_E0]
0x18003f8c2  mov     [rsp+240h+var_1D8], r9
0x18003f8c7  mov     rcx, rsi
0x18003f8ca  cmovnz  rcx, rbx
0x18003f8ce  mov     rax, rsi
0x18003f8d1  mov     [rsp+240h+var_1E0], rcx
0x18003f8d6  test    rdi, rdi
0x18003f8d9  mov     rcx, [rbp+140h+var_158]
0x18003f8dd  mov     edx, 0Ah
0x18003f8e2  mov     [rsp+240h+var_1E8], rcx
0x18003f8e7  cmovnz  rax, rdi
0x18003f8eb  mov     rcx, [rbp+140h+var_150]
0x18003f8ef  mov     r9d, r12d
0x18003f8f2  mov     qword ptr [rsp+240h+var_1F0], rcx
0x18003f8f7  mov     rcx, [r8+10h]
0x18003f8fb  mov     [rsp+240h+var_1F8], rax
0x18003f900  mov     rax, [rbp+140h+var_148]
0x18003f904  mov     [rsp+240h+var_200], rax
0x18003f909  mov     eax, [rsp+240h+var_1C4]
0x18003f90d  mov     [rsp+240h+var_208], eax
0x18003f911  mov     eax, [rsp+240h+var_1CC]
0x18003f915  mov     dword ptr [rsp+240h+var_210], eax
0x18003f919  mov     dword ptr [rsp+240h+var_218], r14d
0x18003f91e  mov     dword ptr [rsp+240h+var_220], r13d
0x18003f923  call    WPP_SF_DDDDDSSSSSs
0x18003f928  test    rdi, rdi
0x18003f92b  lea     rcx, AppInfo_PerfTrack_Elevation_COM_Start; struct _EVENT_DESCRIPTOR *
0x18003f932  cmovnz  rsi, rdi
0x18003f936  mov     rdx, rsi; unsigned __int16 *
0x18003f939  call    ?AiLogPerfTrackEventEx@@YAKPEBU_EVENT_DESCRIPTOR@@PEBG@Z; AiLogPerfTrackEventEx(_EVENT_DESCRIPTOR const *,ushort const *)
0x18003f93e  mov     esi, eax
0x18003f940  test    rbx, rbx
0x18003f943  jz      short loc_18003F9A1
0x18003f945  test    r14b, 20h
0x18003f949  jz      short loc_18003F97B
0x18003f94b  xor     r14d, r14d
0x18003f94e  lea     rdx, [rbp+140h+var_1B8]; unsigned __int16 **
0x18003f952  mov     [rsp+240h+var_218], r14; unsigned __int16 **
0x18003f957  xor     r9d, r9d; unsigned __int16 **
0x18003f95a  xor     r8d, r8d; unsigned __int16 *
0x18003f95d  mov     [rsp+240h+var_220], r14; unsigned __int16 *
0x18003f962  mov     rcx, r15; unsigned __int16 *
0x18003f965  call    ?AiConvertWow64Paths@@YAKPEBGPEAPEBGPEAGPEAPEAG01@Z; AiConvertWow64Paths(ushort const *,ushort const * *,ushort *,ushort * *,ushort const *,ushort const * *)
0x18003f96a  mov     rbx, [rbp+140h+var_1B8]
0x18003f96e  mov     [rsp+240h+Reply], eax
0x18003f972  test    eax, eax
0x18003f974  jz      short loc_18003F97E
0x18003f976  jmp     loc_18003FA3A
0x18003f97b  xor     r14d, r14d
0x18003f97e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003f982  inc     rax
0x18003f985  cmp     [rbx+rax*2], r14w
0x18003f98a  jnz     short loc_18003F982
0x18003f98c  cmp     rax, 7FFFh
0x18003f992  jbe     short loc_18003F9A4
0x18003f994  mov     [rsp+240h+Reply], 57h ; 'W'
0x18003f99c  jmp     loc_18003FA3A
0x18003f9a1  xor     r14d, r14d
0x18003f9a4  mov     r8, [rbp+140h+var_190]; unsigned __int16 *
0x18003f9a8  lea     rax, [rbp+140h+hMem]
0x18003f9ac  mov     rdx, [rbp+140h+var_188]; unsigned __int16 *
0x18003f9b0  mov     r9, rbx; unsigned __int16 *
0x18003f9b3  mov     [rsp+240h+var_218], rax; struct _CONSENTUI_PARAM_HEADER **
0x18003f9b8  mov     rcx, rdi; unsigned __int16 *
0x18003f9bb  mov     rax, [rbp+140h+var_160]
0x18003f9bf  mov     [rsp+240h+var_220], rax; struct _GUID *
0x18003f9c4  call    ?AiBuildCOMParams@@YAKPEBG000PEAU_GUID@@PEAPEAU_CONSENTUI_PARAM_HEADER@@@Z; AiBuildCOMParams(ushort const *,ushort const *,ushort const *,ushort const *,_GUID *,_CONSENTUI_PARAM_HEADER * *)
0x18003f9c9  mov     [rsp+240h+Reply], eax
0x18003f9cd  test    eax, eax
0x18003f9cf  jnz     short loc_18003FA3A
0x18003f9d1  mov     rax, [rbp+140h+hMem]
0x18003f9d5  lea     rcx, [rbp+140h+var_1B0]
0x18003f9d9  mov     rdx, [rbp+140h+var_198]; void *
0x18003f9dd  mov     r9d, r13d; unsigned int
0x18003f9e0  mov     [rsp+240h+var_1D8], rcx; int *
0x18003f9e5  mov     r8, r12; unsigned __int64
0x18003f9e8  lea     rcx, [rsp+240h+var_1C8]
0x18003f9ed  mov     [rsp+240h+var_1E0], rcx; enum UACPROMPT_POLICY *
0x18003f9f2  lea     rcx, [rbp+140h+var_E0]
0x18003f9f6  mov     [rsp+240h+var_1E8], rcx; char *
0x18003f9fb  mov     rcx, [rbp+140h+var_140]
0x18003f9ff  mov     [rsp+240h+var_1F0], r14d; unsigned int
0x18003fa04  mov     [rsp+240h+var_1F8], rcx; unsigned __int64 *
0x18003fa09  mov     ecx, [rsp+240h+var_1C4]
0x18003fa0d  mov     [rsp+240h+var_200], rbx; unsigned __int16 *
0x18003fa12  mov     [rsp+240h+var_208], ecx; unsigned int
0x18003fa16  xor     ecx, ecx; unsigned int
0x18003fa18  mov     [rsp+240h+var_210], rax; struct _CONSENTUI_PARAM_HEADER *
0x18003fa1d  mov     [rax+34h], esi
0x18003fa20  mov     rax, [rbp+140h+var_180]
0x18003fa24  mov     [rsp+240h+var_218], rax; unsigned __int16 *
0x18003fa29  mov     eax, [rsp+240h+var_1CC]
0x18003fa2d  mov     dword ptr [rsp+240h+var_220], eax; int
0x18003fa31  call    ?AipGetTokenForService@@YAKKPEAX_KKHPEBGPEAU_CONSENTUI_PARAM_HEADER@@K2PEA_KKPEBDPEAW4UACPROMPT_POLICY@@PEAH@Z; AipGetTokenForService(ulong,void *,unsigned __int64,ulong,int,ushort const *,_CONSENTUI_PARAM_HEADER *,ulong,ushort const *,unsigned __int64 *,ulong,char const *,UACPROMPT_POLICY *,int *)
0x18003fa36  mov     [rsp+240h+Reply], eax
0x18003fa3a  mov     rcx, [rbp+140h+hMem]; hMem
0x18003fa3e  call    cs:__imp_LocalFree
0x18003fa45  nop     dword ptr [rax+rax+00h]
0x18003fa4a  cmp     rbx, r15
0x18003fa4d  jz      short loc_18003FA62
0x18003fa4f  mov     rcx, rbx; hMem
0x18003fa52  call    cs:__imp_LocalFree
0x18003fa59  nop     dword ptr [rax+rax+00h]
0x18003fa5e  mov     [rbp+140h+var_1B8], r15
0x18003fa62  lea     rcx, [rbp+140h+var_178]; lpPerformanceCount
0x18003fa66  call    cs:__imp_QueryPerformanceCounter
0x18003fa6d  nop     dword ptr [rax+rax+00h]
0x18003fa72  mov     rax, qword ptr [rbp+140h+var_178]
0x18003fa76  sub     rax, qword ptr [rbp+140h+PerformanceCount]
0x18003fa7a  imul    rax, 3E8h
0x18003fa81  cqo
0x18003fa83  idiv    qword ptr [rbp+140h+Frequency]
0x18003fa87  mov     [rbp+140h+var_198], rax
0x18003fa8b  mov     eax, [rsp+240h+var_1C8]
0x18003fa8f  mov     [rsp+240h+var_1C8], eax
0x18003fa93  mov     eax, [rsp+240h+Reply]
0x18003fa97  cmp     eax, 4C7h
0x18003fa9c  jnz     short loc_18003FAA5
0x18003fa9e  mov     [rsp+240h+var_1CC], r14d
0x18003faa3  jmp     short loc_18003FAB5
0x18003faa5  test    eax, eax
0x18003faa7  jle     short loc_18003FAB1
0x18003faa9  movzx   eax, ax
0x18003faac  or      eax, 80070000h
0x18003fab1  mov     [rsp+240h+var_1CC], eax
0x18003fab5  lea     rax, [rbp+140h+var_E0]
0x18003fab9  mov     qword ptr [rsp+240h+var_1F0], rax
0x18003fabe  lea     r9, [rbp+140h+var_1C0]
0x18003fac2  lea     rax, [rbp+140h+var_198]
0x18003fac6  mov     [rsp+240h+var_1F8], rax
0x18003facb  lea     r8, [rbp+140h+var_1AC]
0x18003facf  lea     rax, [rsp+240h+var_1C8]
0x18003fad4  mov     [rsp+240h+var_200], rax
0x18003fad9  lea     rdx, [rsp+240h+Reply]
0x18003fade  lea     rax, [rbp+140h+var_1B0]
0x18003fae2  mov     qword ptr [rsp+240h+var_208], rax
0x18003fae7  lea     rcx, [rsp+240h+var_1CC]
0x18003faec  lea     rax, [rbp+140h+var_1A0]
0x18003faf0  mov     [rsp+240h+var_210], rax
0x18003faf5  lea     rax, [rbp+140h+var_1B8]
0x18003faf9  mov     [rsp+240h+var_218], rax
0x18003fafe  lea     rax, [rbp+140h+var_160]
0x18003fb02  mov     [rsp+240h+var_220], rax
0x18003fb07  call    ??$COMElevation@JAEAKAEAKAEAKAEAPEAU_GUID@@AEAPEBGAEAPEBGAEAHKAEA_JAEAY0IB@D@LUATelemetry@@SAX$$QEAJAEAK11AEAPEAU_GUID@@AEAPEBG3AEAH$$QEAKAEA_JAEAY0IB@D@Z; LUATelemetry::COMElevation<long,ulong &,ulong &,ulong &,_GUID * &,ushort const * &,ushort const * &,int &,ulong,__int64 &,char (&)[129]>(long &&,ulong &,ulong &,ulong &,_GUID * &,ushort const * &,ushort const * &,int &,ulong &&,__int64 &,char (&)[129])
0x18003fb0c  mov     rcx, [rbp+140h+pAsync]; pAsync
0x18003fb10  lea     rdx, [rsp+240h+Reply]; Reply
0x18003fb15  call    cs:__imp_RpcAsyncCompleteCall
0x18003fb1c  nop     dword ptr [rax+rax+00h]
0x18003fb21  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fb28  lea     rax, WPP_GLOBAL_Control
0x18003fb2f  cmp     rcx, rax
0x18003fb32  jz      short loc_18003FB54
0x18003fb34  test    byte ptr [rcx+1Ch], 1
0x18003fb38  jz      short loc_18003FB54
0x18003fb3a  mov     r9d, [rsp+240h+Reply]
0x18003fb3f  lea     r8, WPP_aba5399977573c9264c162bacbfc9302_Traceguids
0x18003fb46  mov     rcx, [rcx+10h]
0x18003fb4a  mov     edx, 0Bh
0x18003fb4f  call    WPP_SF_D
0x18003fb54  lea     rcx, [rbp+140h+var_130]; this
0x18003fb58  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18003fb5d  mov     rcx, [rbp+140h+var_50]
0x18003fb64  xor     rcx, rsp; StackCookie
0x18003fb67  call    __security_check_cookie
0x18003fb6c  add     rsp, 208h
0x18003fb73  pop     r15
0x18003fb75  pop     r14
0x18003fb77  pop     r13
0x18003fb79  pop     r12
0x18003fb7b  pop     rdi
  ... truncated ...
```
