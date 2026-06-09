# RAiForceElevationPromptForCOM

- ea: `0x18003eaa0`
- end: `0x18003ef9a`
- name: `RAiForceElevationPromptForCOM`
- size: `1274`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

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
- `0x18003eaa0`
- `0x18003fe94`
- `0x180041eb4`
- `0x1800444ba`
- `0x1800444e0`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003ef2e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003ef2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ee57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ee6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ee57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ee6b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003eb73`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003eb73`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003eb63`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003ee7f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003eb63`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003ee7f`
- `ntdll!NtClose` at `0x18003ee43`
- `ntdll!NtClose` at `0x18003ee43`

## string_xrefs

- `0x18003ec09`: `hwnd = %x dwRunLevel = %x dwClientFlags = %x fAdjustTokenSD = %x dwTimeout = %x\n	lpDesktop = %ws\n	lpFriendlyName = %ws\n	lpServerBinary = %ws\n	lpIconReference = %ws\n	lpRequestorPath = %ws\n	lpCvStr = %s\n`
- `0x18003ebfd`: `RAiForceElevationPromptForCOM`

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
  const unsigned __int16 *v21; // rcx
  unsigned __int16 *v22; // r9
  const unsigned __int16 *v23; // rax
  void *v24; // rax
  volatile signed __int64 *v25; // rbx
  const unsigned __int16 *v26; // rcx
  const unsigned __int16 *v27; // rax
  unsigned int v28; // esi
  unsigned int v29; // eax
  unsigned __int64 v30; // rax
  struct _CONSENTUI_PARAM_HEADER *v31; // rax
  unsigned int v32; // eax
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
  v21 = a12;
  if ( !v46 )
    v20 = L"NULL";
  v53 = v20;
  v22 = v47;
  v23 = a9;
  if ( !v47 )
    v22 = L"NULL";
  v54 = v22;
  if ( !a12 )
    v21 = L"NULL";
  if ( !a9 )
    v23 = L"NULL";
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
    v36,
    v22,
    v23,
    v20,
    v19,
    v21,
    v57);
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
      v57);
    if ( v25 )
      operator delete((void *)v25);
    v16 = (unsigned __int16 *)v38;
    v15 = v43;
    v17 = v37;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v26 = L"NULL";
    if ( v16 )
      v26 = v16;
    v27 = L"NULL";
    if ( v15 )
      v27 = v15;
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
      (__int64)v27,
      (__int64)v53,
      (__int64)v52,
      (__int64)v26,
      (__int64)v57);
  }
  if ( v15 )
    v18 = v15;
  v28 = AiLogPerfTrackEventEx(&AppInfo_PerfTrack_Elevation_COM_Start, v18);
  if ( v16 )
  {
    if ( (v17 & 0x20) != 0 )
    {
      v29 = AiConvertWow64Paths(a12, (const unsigned __int16 **)&v38, 0, 0, 0, 0);
      v16 = (unsigned __int16 *)v38;
      Reply = v29;
      if ( v29 )
        goto LABEL_37;
    }
    v30 = -1;
    do
      ++v30;
    while ( v16[v30] );
    if ( v30 > 0x7FFF )
    {
      Reply = 87;
      goto LABEL_37;
    }
  }
  Reply = AiBuildCOMParams(v15, v46, v45, v16, v51, (struct _CONSENTUI_PARAM_HEADER **)&hMem);
  if ( !Reply )
  {
    v31 = (struct _CONSENTUI_PARAM_HEADER *)hMem;
    v40 = 0x2000000;
    *((_DWORD *)hMem + 13) = v28;
    Reply = AipGetTokenForService(
              0,
              v44,
              a3,
              a4,
              v34,
              v47,
              v31,
              v36,
              v16,
              (unsigned __int64 *)&Handle,
              0x2000000u,
              v57,
              (enum UACPROMPT_POLICY *)&v35,
              &v39);
  }
LABEL_37:
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
  v32 = Reply;
  if ( Reply == 1223 )
  {
    v34 = 0;
  }
  else
  {
    if ( Reply > 0 )
      v32 = (unsigned __int16)Reply | 0x80070000;
    v34 = v32;
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
0x18003eaa0  push    rbp
0x18003eaa2  push    rbx
0x18003eaa3  push    rsi
0x18003eaa4  push    rdi
0x18003eaa5  push    r12
0x18003eaa7  push    r13
0x18003eaa9  push    r14
0x18003eaab  push    r15
0x18003eaad  lea     rbp, [rsp-108h]
0x18003eab5  sub     rsp, 208h
0x18003eabc  mov     rax, cs:__security_cookie
0x18003eac3  xor     rax, rsp
0x18003eac6  mov     [rbp+140h+var_50], rax
0x18003eacd  mov     rax, [rbp+140h+arg_30]
0x18003ead4  mov     r12, r8
0x18003ead7  mov     r8, [rbp+140h+arg_50]
0x18003eade  mov     r13d, r9d
0x18003eae1  mov     r15, [rbp+140h+arg_58]
0x18003eae8  mov     rdi, [rbp+140h+arg_40]
0x18003eaef  mov     rbx, r15
0x18003eaf2  mov     r14d, [rbp+140h+arg_20]
0x18003eaf9  mov     [rbp+140h+var_178], rax
0x18003eafd  mov     eax, [rbp+140h+arg_28]
0x18003eb03  mov     [rsp+240h+var_1CC], eax
0x18003eb07  mov     rax, [rbp+140h+arg_38]
0x18003eb0e  mov     [rbp+140h+var_158], rax
0x18003eb12  mov     eax, [rbp+140h+arg_60]
0x18003eb18  mov     [rsp+240h+var_1C4], eax
0x18003eb1c  xor     eax, eax
0x18003eb1e  mov     [rbp+140h+var_190], rdx
0x18003eb22  mov     rdx, [rbp+140h+arg_48]
0x18003eb29  mov     [rbp+140h+pAsync], rcx
0x18003eb2d  lea     rcx, [rbp+140h+PerformanceCount]; lpPerformanceCount
0x18003eb31  mov     [rbp+140h+hMem], rax
0x18003eb35  mov     [rbp+140h+var_1AC], eax
0x18003eb38  mov     [rbp+140h+Handle], rax
0x18003eb3c  mov     [rbp+140h+var_1B0], eax
0x18003eb3f  mov     [rsp+240h+var_1C8], eax
0x18003eb43  mov     qword ptr [rbp+140h+Frequency], rax
0x18003eb47  mov     qword ptr [rbp+140h+PerformanceCount], rax
0x18003eb4b  mov     qword ptr [rbp+140h+var_170], rax
0x18003eb4f  mov     [rbp+140h+var_180], rdx
0x18003eb53  mov     [rbp+140h+var_188], r8
0x18003eb57  mov     [rbp+140h+var_1C0], r14d
0x18003eb5b  mov     [rbp+140h+var_198], rdi
0x18003eb5f  mov     [rbp+140h+var_1B8], rbx
0x18003eb63  call    cs:__imp_QueryPerformanceCounter
0x18003eb6a  nop     dword ptr [rax+rax+00h]
0x18003eb6f  lea     rcx, [rbp+140h+Frequency]; lpFrequency
0x18003eb73  call    cs:__imp_QueryPerformanceFrequency
0x18003eb7a  nop     dword ptr [rax+rax+00h]
0x18003eb7f  xor     edx, edx; Val
0x18003eb81  lea     rcx, [rbp+140h+var_E0]; void *
0x18003eb85  mov     r8d, 81h; Size
0x18003eb8b  call    memset_0
0x18003eb90  mov     rax, [rbp+140h+var_188]
0x18003eb94  lea     rsi, aNull_0; "NULL"
0x18003eb9b  test    rax, rax
0x18003eb9e  lea     r10, [rbp+140h+var_E0]
0x18003eba2  mov     [rsp+240h+var_1D8], r10
0x18003eba7  mov     rdx, rax
0x18003ebaa  mov     rax, [rbp+140h+var_180]
0x18003ebae  cmovz   rdx, rsi
0x18003ebb2  test    rax, rax
0x18003ebb5  mov     [rbp+140h+var_150], rdx
0x18003ebb9  mov     r8, rax
0x18003ebbc  mov     rcx, r15
0x18003ebbf  mov     rax, [rbp+140h+var_178]
0x18003ebc3  cmovz   r8, rsi
0x18003ebc7  test    rax, rax
0x18003ebca  mov     [rbp+140h+var_148], r8
0x18003ebce  mov     r9, rax
0x18003ebd1  mov     rax, rdi
0x18003ebd4  cmovz   r9, rsi
0x18003ebd8  test    r15, r15
0x18003ebdb  mov     [rbp+140h+var_140], r9
0x18003ebdf  cmovz   rcx, rsi
0x18003ebe3  test    rdi, rdi
0x18003ebe6  mov     [rsp+240h+var_1E0], rcx
0x18003ebeb  lea     rcx, [rbp+140h+var_130]
0x18003ebef  mov     [rsp+240h+var_1E8], rdx
0x18003ebf4  cmovz   rax, rsi
0x18003ebf8  mov     qword ptr [rsp+240h+var_1F0], r8
0x18003ebfd  lea     rdx, aRaiforceelevat; "RAiForceElevationPromptForCOM"
0x18003ec04  mov     [rsp+240h+var_1F8], rax
0x18003ec09  lea     r8, aHwndXDwrunleve_0; "hwnd = %x dwRunLevel = %x dwClientFlags"...
0x18003ec10  mov     eax, [rsp+240h+var_1C4]
0x18003ec14  mov     [rsp+240h+var_200], r9
0x18003ec19  mov     r9d, r12d
0x18003ec1c  mov     [rsp+240h+var_208], eax
0x18003ec20  mov     eax, [rsp+240h+var_1CC]
0x18003ec24  mov     dword ptr [rsp+240h+var_210], eax
0x18003ec28  mov     dword ptr [rsp+240h+var_218], r14d
0x18003ec2d  mov     dword ptr [rsp+240h+var_220], r13d
0x18003ec32  call    ?WatchCurrentThread@LUATelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; LUATelemetry::WatchCurrentThread(char const *,char const *,...)
0x18003ec37  mov     rcx, cs:?g_pCOMElevationActivityTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; this
0x18003ec3e  test    rcx, rcx
0x18003ec41  jz      short loc_18003EC9A
0x18003ec43  call    ?RequestPermission@RateLimiter@@QEAAHXZ; RateLimiter::RequestPermission(void)
0x18003ec48  test    eax, eax
0x18003ec4a  jz      short loc_18003EC9A
0x18003ec4c  mov     ecx, 90h; Size
0x18003ec51  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003ec56  test    rax, rax
0x18003ec59  jz      short loc_18003EC68
0x18003ec5b  mov     rcx, rax
0x18003ec5e  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18003ec63  mov     rbx, rax
0x18003ec66  jmp     short loc_18003EC6A
0x18003ec68  xor     ebx, ebx
0x18003ec6a  xor     edx, edx
0x18003ec6c  lock xadd [rbx+88h], rdx; unsigned __int64
0x18003ec75  lea     r8, [rbp+140h+var_E0]; char *
0x18003ec79  mov     rcx, rbx; this
0x18003ec7c  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18003ec81  test    rbx, rbx
0x18003ec84  jz      short loc_18003EC8E
0x18003ec86  mov     rcx, rbx; Block
0x18003ec89  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003ec8e  mov     rbx, [rbp+140h+var_1B8]
0x18003ec92  mov     rdi, [rbp+140h+var_198]
0x18003ec96  mov     r14d, [rbp+140h+var_1C0]
0x18003ec9a  mov     r8, cs:WPP_GLOBAL_Control
0x18003eca1  lea     rax, WPP_GLOBAL_Control
0x18003eca8  cmp     r8, rax
0x18003ecab  jz      short loc_18003ED21
0x18003ecad  test    byte ptr [r8+1Ch], 1
0x18003ecb2  jz      short loc_18003ED21
0x18003ecb4  test    rbx, rbx
0x18003ecb7  lea     r9, [rbp+140h+var_E0]
0x18003ecbb  mov     [rsp+240h+var_1D8], r9
0x18003ecc0  mov     rcx, rsi
0x18003ecc3  cmovnz  rcx, rbx
0x18003ecc7  mov     rax, rsi
0x18003ecca  mov     [rsp+240h+var_1E0], rcx
0x18003eccf  test    rdi, rdi
0x18003ecd2  mov     rcx, [rbp+140h+var_150]
0x18003ecd6  mov     edx, 0Ch
0x18003ecdb  mov     [rsp+240h+var_1E8], rcx
0x18003ece0  cmovnz  rax, rdi
0x18003ece4  mov     rcx, [rbp+140h+var_148]
0x18003ece8  mov     r9d, r12d
0x18003eceb  mov     qword ptr [rsp+240h+var_1F0], rcx
0x18003ecf0  mov     rcx, [r8+10h]
0x18003ecf4  mov     [rsp+240h+var_1F8], rax
0x18003ecf9  mov     rax, [rbp+140h+var_140]
0x18003ecfd  mov     [rsp+240h+var_200], rax
0x18003ed02  mov     eax, [rsp+240h+var_1C4]
0x18003ed06  mov     [rsp+240h+var_208], eax
0x18003ed0a  mov     eax, [rsp+240h+var_1CC]
0x18003ed0e  mov     dword ptr [rsp+240h+var_210], eax
0x18003ed12  mov     dword ptr [rsp+240h+var_218], r14d
0x18003ed17  mov     dword ptr [rsp+240h+var_220], r13d
0x18003ed1c  call    WPP_SF_DDDDDSSSSSs
0x18003ed21  test    rdi, rdi
0x18003ed24  lea     rcx, AppInfo_PerfTrack_Elevation_COM_Start; struct _EVENT_DESCRIPTOR *
0x18003ed2b  cmovnz  rsi, rdi
0x18003ed2f  mov     rdx, rsi; unsigned __int16 *
0x18003ed32  call    ?AiLogPerfTrackEventEx@@YAKPEBU_EVENT_DESCRIPTOR@@PEBG@Z; AiLogPerfTrackEventEx(_EVENT_DESCRIPTOR const *,ushort const *)
0x18003ed37  mov     esi, eax
0x18003ed39  test    rbx, rbx
0x18003ed3c  jz      short loc_18003ED9A
0x18003ed3e  test    r14b, 20h
0x18003ed42  jz      short loc_18003ED74
0x18003ed44  xor     r14d, r14d
0x18003ed47  lea     rdx, [rbp+140h+var_1B8]; unsigned __int16 **
0x18003ed4b  mov     [rsp+240h+var_218], r14; unsigned __int16 **
0x18003ed50  xor     r9d, r9d; unsigned __int16 **
0x18003ed53  xor     r8d, r8d; unsigned __int16 *
0x18003ed56  mov     [rsp+240h+var_220], r14; unsigned __int16 *
0x18003ed5b  mov     rcx, r15; unsigned __int16 *
0x18003ed5e  call    ?AiConvertWow64Paths@@YAKPEBGPEAPEBGPEAGPEAPEAG01@Z; AiConvertWow64Paths(ushort const *,ushort const * *,ushort *,ushort * *,ushort const *,ushort const * *)
0x18003ed63  mov     rbx, [rbp+140h+var_1B8]
0x18003ed67  mov     [rsp+240h+Reply], eax
0x18003ed6b  test    eax, eax
0x18003ed6d  jz      short loc_18003ED77
0x18003ed6f  jmp     loc_18003EE3A
0x18003ed74  xor     r14d, r14d
0x18003ed77  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003ed7b  inc     rax
0x18003ed7e  cmp     [rbx+rax*2], r14w
0x18003ed83  jnz     short loc_18003ED7B
0x18003ed85  cmp     rax, 7FFFh
0x18003ed8b  jbe     short loc_18003ED9D
0x18003ed8d  mov     [rsp+240h+Reply], 57h ; 'W'
0x18003ed95  jmp     loc_18003EE3A
0x18003ed9a  xor     r14d, r14d
0x18003ed9d  mov     r8, [rbp+140h+var_188]; unsigned __int16 *
0x18003eda1  lea     rax, [rbp+140h+hMem]
0x18003eda5  mov     rdx, [rbp+140h+var_180]; unsigned __int16 *
0x18003eda9  mov     r9, rbx; unsigned __int16 *
0x18003edac  mov     [rsp+240h+var_218], rax; struct _CONSENTUI_PARAM_HEADER **
0x18003edb1  mov     rcx, rdi; unsigned __int16 *
0x18003edb4  mov     rax, [rbp+140h+var_158]
0x18003edb8  mov     [rsp+240h+var_220], rax; struct _GUID *
0x18003edbd  call    ?AiBuildCOMParams@@YAKPEBG000PEAU_GUID@@PEAPEAU_CONSENTUI_PARAM_HEADER@@@Z; AiBuildCOMParams(ushort const *,ushort const *,ushort const *,ushort const *,_GUID *,_CONSENTUI_PARAM_HEADER * *)
0x18003edc2  mov     [rsp+240h+Reply], eax
0x18003edc6  test    eax, eax
0x18003edc8  jnz     short loc_18003EE3A
0x18003edca  mov     rax, [rbp+140h+hMem]
0x18003edce  lea     rcx, [rbp+140h+var_1B0]
0x18003edd2  mov     [rsp+240h+var_1D8], rcx; int *
0x18003edd7  mov     edx, 2000000h
0x18003eddc  lea     rcx, [rsp+240h+var_1C8]
0x18003ede1  mov     [rbp+140h+var_1AC], edx
0x18003ede4  mov     [rsp+240h+var_1E0], rcx; enum UACPROMPT_POLICY *
0x18003ede9  mov     r9d, r13d; unsigned int
0x18003edec  mov     [rax+34h], esi
0x18003edef  lea     rcx, [rbp+140h+var_E0]
0x18003edf3  mov     [rsp+240h+var_1E8], rcx; char *
0x18003edf8  mov     r8, r12; unsigned __int64
0x18003edfb  mov     [rsp+240h+var_1F0], edx; unsigned int
0x18003edff  lea     rcx, [rbp+140h+Handle]
0x18003ee03  mov     rdx, [rbp+140h+var_190]; void *
0x18003ee07  mov     [rsp+240h+var_1F8], rcx; unsigned __int64 *
0x18003ee0c  mov     ecx, [rsp+240h+var_1C4]
0x18003ee10  mov     [rsp+240h+var_200], rbx; unsigned __int16 *
0x18003ee15  mov     [rsp+240h+var_208], ecx; unsigned int
0x18003ee19  xor     ecx, ecx; unsigned int
0x18003ee1b  mov     [rsp+240h+var_210], rax; struct _CONSENTUI_PARAM_HEADER *
0x18003ee20  mov     rax, [rbp+140h+var_178]
0x18003ee24  mov     [rsp+240h+var_218], rax; unsigned __int16 *
0x18003ee29  mov     eax, [rsp+240h+var_1CC]
0x18003ee2d  mov     dword ptr [rsp+240h+var_220], eax; int
0x18003ee31  call    ?AipGetTokenForService@@YAKKPEAX_KKHPEBGPEAU_CONSENTUI_PARAM_HEADER@@K2PEA_KKPEBDPEAW4UACPROMPT_POLICY@@PEAH@Z; AipGetTokenForService(ulong,void *,unsigned __int64,ulong,int,ushort const *,_CONSENTUI_PARAM_HEADER *,ulong,ushort const *,unsigned __int64 *,ulong,char const *,UACPROMPT_POLICY *,int *)
0x18003ee36  mov     [rsp+240h+Reply], eax
0x18003ee3a  mov     rcx, [rbp+140h+Handle]; Handle
0x18003ee3e  test    rcx, rcx
0x18003ee41  jz      short loc_18003EE53
0x18003ee43  call    cs:__imp_NtClose
0x18003ee4a  nop     dword ptr [rax+rax+00h]
0x18003ee4f  mov     [rbp+140h+Handle], r14
0x18003ee53  mov     rcx, [rbp+140h+hMem]; hMem
0x18003ee57  call    cs:__imp_LocalFree
0x18003ee5e  nop     dword ptr [rax+rax+00h]
0x18003ee63  cmp     rbx, r15
0x18003ee66  jz      short loc_18003EE7B
0x18003ee68  mov     rcx, rbx; hMem
0x18003ee6b  call    cs:__imp_LocalFree
0x18003ee72  nop     dword ptr [rax+rax+00h]
0x18003ee77  mov     [rbp+140h+var_1B8], r15
0x18003ee7b  lea     rcx, [rbp+140h+var_170]; lpPerformanceCount
0x18003ee7f  call    cs:__imp_QueryPerformanceCounter
0x18003ee86  nop     dword ptr [rax+rax+00h]
0x18003ee8b  mov     rax, qword ptr [rbp+140h+var_170]
0x18003ee8f  sub     rax, qword ptr [rbp+140h+PerformanceCount]
0x18003ee93  imul    rax, 3E8h
0x18003ee9a  cqo
0x18003ee9c  idiv    qword ptr [rbp+140h+Frequency]
0x18003eea0  mov     [rbp+140h+var_190], rax
0x18003eea4  mov     eax, [rsp+240h+var_1C8]
0x18003eea8  mov     [rsp+240h+var_1C8], eax
0x18003eeac  mov     eax, [rsp+240h+Reply]
0x18003eeb0  cmp     eax, 4C7h
0x18003eeb5  jnz     short loc_18003EEBE
0x18003eeb7  mov     [rsp+240h+var_1CC], r14d
0x18003eebc  jmp     short loc_18003EECE
0x18003eebe  test    eax, eax
0x18003eec0  jle     short loc_18003EECA
0x18003eec2  movzx   eax, ax
0x18003eec5  or      eax, 80070000h
0x18003eeca  mov     [rsp+240h+var_1CC], eax
0x18003eece  lea     rax, [rbp+140h+var_E0]
0x18003eed2  mov     qword ptr [rsp+240h+var_1F0], rax
0x18003eed7  lea     r9, [rbp+140h+var_1C0]
0x18003eedb  lea     rax, [rbp+140h+var_190]
0x18003eedf  mov     [rsp+240h+var_1F8], rax
0x18003eee4  lea     r8, [rbp+140h+var_1AC]
0x18003eee8  lea     rax, [rsp+240h+var_1C8]
0x18003eeed  mov     [rsp+240h+var_200], rax
0x18003eef2  lea     rdx, [rsp+240h+Reply]
0x18003eef7  lea     rax, [rbp+140h+var_1B0]
0x18003eefb  mov     qword ptr [rsp+240h+var_208], rax
0x18003ef00  lea     rcx, [rsp+240h+var_1CC]
0x18003ef05  lea     rax, [rbp+140h+var_198]
0x18003ef09  mov     [rsp+240h+var_210], rax
0x18003ef0e  lea     rax, [rbp+140h+var_1B8]
0x18003ef12  mov     [rsp+240h+var_218], rax
0x18003ef17  lea     rax, [rbp+140h+var_158]
0x18003ef1b  mov     [rsp+240h+var_220], rax
0x18003ef20  call    ??$COMElevation@JAEAKAEAKAEAKAEAPEAU_GUID@@AEAPEBGAEAPEBGAEAHKAEA_JAEAY0IB@D@LUATelemetry@@SAX$$QEAJAEAK11AEAPEAU_GUID@@AEAPEBG3AEAH$$QEAKAEA_JAEAY0IB@D@Z; LUATelemetry::COMElevation<long,ulong &,ulong &,ulong &,_GUID * &,ushort const * &,ushort const * &,int &,ulong,__int64 &,char (&)[129]>(long &&,ulong &,ulong &,ulong &,_GUID * &,ushort const * &,ushort const * &,int &,ulong &&,__int64 &,char (&)[129])
0x18003ef25  mov     rcx, [rbp+140h+pAsync]; pAsync
0x18003ef29  lea     rdx, [rsp+240h+Reply]; Reply
0x18003ef2e  call    cs:__imp_RpcAsyncCompleteCall
0x18003ef35  nop     dword ptr [rax+rax+00h]
0x18003ef3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ef41  lea     rax, WPP_GLOBAL_Control
0x18003ef48  cmp     rcx, rax
0x18003ef4b  jz      short loc_18003EF6D
0x18003ef4d  test    byte ptr [rcx+1Ch], 1
0x18003ef51  jz      short loc_18003EF6D
0x18003ef53  mov     r9d, [rsp+240h+Reply]
0x18003ef58  lea     r8, WPP_aba5399977573c9264c162bacbfc9302_Traceguids
0x18003ef5f  mov     rcx, [rcx+10h]
0x18003ef63  mov     edx, 0Dh
0x18003ef68  call    WPP_SF_D
0x18003ef6d  lea     rcx, [rbp+140h+var_130]; this
0x18003ef71  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18003ef76  mov     rcx, [rbp+140h+var_50]
0x18003ef7d  xor     rcx, rsp; StackCookie
  ... truncated ...
```
