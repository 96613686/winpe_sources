# RAiForceElevationPromptForCOM

- ea: `0x18003efe0`
- end: `0x18003f4da`
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
- `0x180026eb4`
- `0x1800272f4`
- `0x1800389b0`
- `0x180039720`
- `0x18003e3c4`
- `0x18003e5d4`
- `0x18003efe0`
- `0x1800403d4`
- `0x1800423f4`
- `0x1800449fa`
- `0x180044a20`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003f46e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003f46e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f397`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f3ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f397`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f3ab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003f0b3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003f0b3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003f0a3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003f3bf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003f0a3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003f3bf`
- `ntdll!NtClose` at `0x18003f383`
- `ntdll!NtClose` at `0x18003f383`

## string_xrefs

- `0x18003f149`: `hwnd = %x dwRunLevel = %x dwClientFlags = %x fAdjustTokenSD = %x dwTimeout = %x\n	lpDesktop = %ws\n	lpFriendlyName = %ws\n	lpServerBinary = %ws\n	lpIconReference = %ws\n	lpRequestorPath = %ws\n	lpCvStr = %s\n`
- `0x18003f13d`: `RAiForceElevationPromptForCOM`

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
0x18003efe0  push    rbp
0x18003efe2  push    rbx
0x18003efe3  push    rsi
0x18003efe4  push    rdi
0x18003efe5  push    r12
0x18003efe7  push    r13
0x18003efe9  push    r14
0x18003efeb  push    r15
0x18003efed  lea     rbp, [rsp-108h]
0x18003eff5  sub     rsp, 208h
0x18003effc  mov     rax, cs:__security_cookie
0x18003f003  xor     rax, rsp
0x18003f006  mov     [rbp+140h+var_50], rax
0x18003f00d  mov     rax, [rbp+140h+arg_30]
0x18003f014  mov     r12, r8
0x18003f017  mov     r8, [rbp+140h+arg_50]
0x18003f01e  mov     r13d, r9d
0x18003f021  mov     r15, [rbp+140h+arg_58]
0x18003f028  mov     rdi, [rbp+140h+arg_40]
0x18003f02f  mov     rbx, r15
0x18003f032  mov     r14d, [rbp+140h+arg_20]
0x18003f039  mov     [rbp+140h+var_178], rax
0x18003f03d  mov     eax, [rbp+140h+arg_28]
0x18003f043  mov     [rsp+240h+var_1CC], eax
0x18003f047  mov     rax, [rbp+140h+arg_38]
0x18003f04e  mov     [rbp+140h+var_158], rax
0x18003f052  mov     eax, [rbp+140h+arg_60]
0x18003f058  mov     [rsp+240h+var_1C4], eax
0x18003f05c  xor     eax, eax
0x18003f05e  mov     [rbp+140h+var_190], rdx
0x18003f062  mov     rdx, [rbp+140h+arg_48]
0x18003f069  mov     [rbp+140h+pAsync], rcx
0x18003f06d  lea     rcx, [rbp+140h+PerformanceCount]; lpPerformanceCount
0x18003f071  mov     [rbp+140h+hMem], rax
0x18003f075  mov     [rbp+140h+var_1AC], eax
0x18003f078  mov     [rbp+140h+Handle], rax
0x18003f07c  mov     [rbp+140h+var_1B0], eax
0x18003f07f  mov     [rsp+240h+var_1C8], eax
0x18003f083  mov     qword ptr [rbp+140h+Frequency], rax
0x18003f087  mov     qword ptr [rbp+140h+PerformanceCount], rax
0x18003f08b  mov     qword ptr [rbp+140h+var_170], rax
0x18003f08f  mov     [rbp+140h+var_180], rdx
0x18003f093  mov     [rbp+140h+var_188], r8
0x18003f097  mov     [rbp+140h+var_1C0], r14d
0x18003f09b  mov     [rbp+140h+var_198], rdi
0x18003f09f  mov     [rbp+140h+var_1B8], rbx
0x18003f0a3  call    cs:__imp_QueryPerformanceCounter
0x18003f0aa  nop     dword ptr [rax+rax+00h]
0x18003f0af  lea     rcx, [rbp+140h+Frequency]; lpFrequency
0x18003f0b3  call    cs:__imp_QueryPerformanceFrequency
0x18003f0ba  nop     dword ptr [rax+rax+00h]
0x18003f0bf  xor     edx, edx; Val
0x18003f0c1  lea     rcx, [rbp+140h+var_E0]; void *
0x18003f0c5  mov     r8d, 81h; Size
0x18003f0cb  call    memset_0
0x18003f0d0  mov     rax, [rbp+140h+var_188]
0x18003f0d4  lea     rsi, aNull_0; "NULL"
0x18003f0db  test    rax, rax
0x18003f0de  lea     r10, [rbp+140h+var_E0]
0x18003f0e2  mov     [rsp+240h+var_1D8], r10
0x18003f0e7  mov     rdx, rax
0x18003f0ea  mov     rax, [rbp+140h+var_180]
0x18003f0ee  cmovz   rdx, rsi
0x18003f0f2  test    rax, rax
0x18003f0f5  mov     [rbp+140h+var_150], rdx
0x18003f0f9  mov     r8, rax
0x18003f0fc  mov     rcx, r15
0x18003f0ff  mov     rax, [rbp+140h+var_178]
0x18003f103  cmovz   r8, rsi
0x18003f107  test    rax, rax
0x18003f10a  mov     [rbp+140h+var_148], r8
0x18003f10e  mov     r9, rax
0x18003f111  mov     rax, rdi
0x18003f114  cmovz   r9, rsi
0x18003f118  test    r15, r15
0x18003f11b  mov     [rbp+140h+var_140], r9
0x18003f11f  cmovz   rcx, rsi
0x18003f123  test    rdi, rdi
0x18003f126  mov     [rsp+240h+var_1E0], rcx
0x18003f12b  lea     rcx, [rbp+140h+var_130]
0x18003f12f  mov     [rsp+240h+var_1E8], rdx
0x18003f134  cmovz   rax, rsi
0x18003f138  mov     qword ptr [rsp+240h+var_1F0], r8
0x18003f13d  lea     rdx, aRaiforceelevat; "RAiForceElevationPromptForCOM"
0x18003f144  mov     [rsp+240h+var_1F8], rax
0x18003f149  lea     r8, aHwndXDwrunleve_0; "hwnd = %x dwRunLevel = %x dwClientFlags"...
0x18003f150  mov     eax, [rsp+240h+var_1C4]
0x18003f154  mov     [rsp+240h+var_200], r9
0x18003f159  mov     r9d, r12d
0x18003f15c  mov     [rsp+240h+var_208], eax
0x18003f160  mov     eax, [rsp+240h+var_1CC]
0x18003f164  mov     dword ptr [rsp+240h+var_210], eax
0x18003f168  mov     dword ptr [rsp+240h+var_218], r14d
0x18003f16d  mov     dword ptr [rsp+240h+var_220], r13d
0x18003f172  call    ?WatchCurrentThread@LUATelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; LUATelemetry::WatchCurrentThread(char const *,char const *,...)
0x18003f177  mov     rcx, cs:?g_pCOMElevationActivityTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; this
0x18003f17e  test    rcx, rcx
0x18003f181  jz      short loc_18003F1DA
0x18003f183  call    ?RequestPermission@RateLimiter@@QEAAHXZ; RateLimiter::RequestPermission(void)
0x18003f188  test    eax, eax
0x18003f18a  jz      short loc_18003F1DA
0x18003f18c  mov     ecx, 90h; Size
0x18003f191  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003f196  test    rax, rax
0x18003f199  jz      short loc_18003F1A8
0x18003f19b  mov     rcx, rax
0x18003f19e  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18003f1a3  mov     rbx, rax
0x18003f1a6  jmp     short loc_18003F1AA
0x18003f1a8  xor     ebx, ebx
0x18003f1aa  xor     edx, edx
0x18003f1ac  lock xadd [rbx+88h], rdx; unsigned __int64
0x18003f1b5  lea     r8, [rbp+140h+var_E0]; char *
0x18003f1b9  mov     rcx, rbx; this
0x18003f1bc  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18003f1c1  test    rbx, rbx
0x18003f1c4  jz      short loc_18003F1CE
0x18003f1c6  mov     rcx, rbx; Block
0x18003f1c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003f1ce  mov     rbx, [rbp+140h+var_1B8]
0x18003f1d2  mov     rdi, [rbp+140h+var_198]
0x18003f1d6  mov     r14d, [rbp+140h+var_1C0]
0x18003f1da  mov     r8, cs:WPP_GLOBAL_Control
0x18003f1e1  lea     rax, WPP_GLOBAL_Control
0x18003f1e8  cmp     r8, rax
0x18003f1eb  jz      short loc_18003F261
0x18003f1ed  test    byte ptr [r8+1Ch], 1
0x18003f1f2  jz      short loc_18003F261
0x18003f1f4  test    rbx, rbx
0x18003f1f7  lea     r9, [rbp+140h+var_E0]
0x18003f1fb  mov     [rsp+240h+var_1D8], r9
0x18003f200  mov     rcx, rsi
0x18003f203  cmovnz  rcx, rbx
0x18003f207  mov     rax, rsi
0x18003f20a  mov     [rsp+240h+var_1E0], rcx
0x18003f20f  test    rdi, rdi
0x18003f212  mov     rcx, [rbp+140h+var_150]
0x18003f216  mov     edx, 0Ch
0x18003f21b  mov     [rsp+240h+var_1E8], rcx
0x18003f220  cmovnz  rax, rdi
0x18003f224  mov     rcx, [rbp+140h+var_148]
0x18003f228  mov     r9d, r12d
0x18003f22b  mov     qword ptr [rsp+240h+var_1F0], rcx
0x18003f230  mov     rcx, [r8+10h]
0x18003f234  mov     [rsp+240h+var_1F8], rax
0x18003f239  mov     rax, [rbp+140h+var_140]
0x18003f23d  mov     [rsp+240h+var_200], rax
0x18003f242  mov     eax, [rsp+240h+var_1C4]
0x18003f246  mov     [rsp+240h+var_208], eax
0x18003f24a  mov     eax, [rsp+240h+var_1CC]
0x18003f24e  mov     dword ptr [rsp+240h+var_210], eax
0x18003f252  mov     dword ptr [rsp+240h+var_218], r14d
0x18003f257  mov     dword ptr [rsp+240h+var_220], r13d
0x18003f25c  call    WPP_SF_DDDDDSSSSSs
0x18003f261  test    rdi, rdi
0x18003f264  lea     rcx, AppInfo_PerfTrack_Elevation_COM_Start; struct _EVENT_DESCRIPTOR *
0x18003f26b  cmovnz  rsi, rdi
0x18003f26f  mov     rdx, rsi; unsigned __int16 *
0x18003f272  call    ?AiLogPerfTrackEventEx@@YAKPEBU_EVENT_DESCRIPTOR@@PEBG@Z; AiLogPerfTrackEventEx(_EVENT_DESCRIPTOR const *,ushort const *)
0x18003f277  mov     esi, eax
0x18003f279  test    rbx, rbx
0x18003f27c  jz      short loc_18003F2DA
0x18003f27e  test    r14b, 20h
0x18003f282  jz      short loc_18003F2B4
0x18003f284  xor     r14d, r14d
0x18003f287  lea     rdx, [rbp+140h+var_1B8]; unsigned __int16 **
0x18003f28b  mov     [rsp+240h+var_218], r14; unsigned __int16 **
0x18003f290  xor     r9d, r9d; unsigned __int16 **
0x18003f293  xor     r8d, r8d; unsigned __int16 *
0x18003f296  mov     [rsp+240h+var_220], r14; unsigned __int16 *
0x18003f29b  mov     rcx, r15; unsigned __int16 *
0x18003f29e  call    ?AiConvertWow64Paths@@YAKPEBGPEAPEBGPEAGPEAPEAG01@Z; AiConvertWow64Paths(ushort const *,ushort const * *,ushort *,ushort * *,ushort const *,ushort const * *)
0x18003f2a3  mov     rbx, [rbp+140h+var_1B8]
0x18003f2a7  mov     [rsp+240h+Reply], eax
0x18003f2ab  test    eax, eax
0x18003f2ad  jz      short loc_18003F2B7
0x18003f2af  jmp     loc_18003F37A
0x18003f2b4  xor     r14d, r14d
0x18003f2b7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003f2bb  inc     rax
0x18003f2be  cmp     [rbx+rax*2], r14w
0x18003f2c3  jnz     short loc_18003F2BB
0x18003f2c5  cmp     rax, 7FFFh
0x18003f2cb  jbe     short loc_18003F2DD
0x18003f2cd  mov     [rsp+240h+Reply], 57h ; 'W'
0x18003f2d5  jmp     loc_18003F37A
0x18003f2da  xor     r14d, r14d
0x18003f2dd  mov     r8, [rbp+140h+var_188]; unsigned __int16 *
0x18003f2e1  lea     rax, [rbp+140h+hMem]
0x18003f2e5  mov     rdx, [rbp+140h+var_180]; unsigned __int16 *
0x18003f2e9  mov     r9, rbx; unsigned __int16 *
0x18003f2ec  mov     [rsp+240h+var_218], rax; struct _CONSENTUI_PARAM_HEADER **
0x18003f2f1  mov     rcx, rdi; unsigned __int16 *
0x18003f2f4  mov     rax, [rbp+140h+var_158]
0x18003f2f8  mov     [rsp+240h+var_220], rax; struct _GUID *
0x18003f2fd  call    ?AiBuildCOMParams@@YAKPEBG000PEAU_GUID@@PEAPEAU_CONSENTUI_PARAM_HEADER@@@Z; AiBuildCOMParams(ushort const *,ushort const *,ushort const *,ushort const *,_GUID *,_CONSENTUI_PARAM_HEADER * *)
0x18003f302  mov     [rsp+240h+Reply], eax
0x18003f306  test    eax, eax
0x18003f308  jnz     short loc_18003F37A
0x18003f30a  mov     rax, [rbp+140h+hMem]
0x18003f30e  lea     rcx, [rbp+140h+var_1B0]
0x18003f312  mov     [rsp+240h+var_1D8], rcx; int *
0x18003f317  mov     edx, 2000000h
0x18003f31c  lea     rcx, [rsp+240h+var_1C8]
0x18003f321  mov     [rbp+140h+var_1AC], edx
0x18003f324  mov     [rsp+240h+var_1E0], rcx; enum UACPROMPT_POLICY *
0x18003f329  mov     r9d, r13d; unsigned int
0x18003f32c  mov     [rax+34h], esi
0x18003f32f  lea     rcx, [rbp+140h+var_E0]
0x18003f333  mov     [rsp+240h+var_1E8], rcx; char *
0x18003f338  mov     r8, r12; unsigned __int64
0x18003f33b  mov     [rsp+240h+var_1F0], edx; unsigned int
0x18003f33f  lea     rcx, [rbp+140h+Handle]
0x18003f343  mov     rdx, [rbp+140h+var_190]; void *
0x18003f347  mov     [rsp+240h+var_1F8], rcx; unsigned __int64 *
0x18003f34c  mov     ecx, [rsp+240h+var_1C4]
0x18003f350  mov     [rsp+240h+var_200], rbx; unsigned __int16 *
0x18003f355  mov     [rsp+240h+var_208], ecx; unsigned int
0x18003f359  xor     ecx, ecx; unsigned int
0x18003f35b  mov     [rsp+240h+var_210], rax; struct _CONSENTUI_PARAM_HEADER *
0x18003f360  mov     rax, [rbp+140h+var_178]
0x18003f364  mov     [rsp+240h+var_218], rax; unsigned __int16 *
0x18003f369  mov     eax, [rsp+240h+var_1CC]
0x18003f36d  mov     dword ptr [rsp+240h+var_220], eax; int
0x18003f371  call    ?AipGetTokenForService@@YAKKPEAX_KKHPEBGPEAU_CONSENTUI_PARAM_HEADER@@K2PEA_KKPEBDPEAW4UACPROMPT_POLICY@@PEAH@Z; AipGetTokenForService(ulong,void *,unsigned __int64,ulong,int,ushort const *,_CONSENTUI_PARAM_HEADER *,ulong,ushort const *,unsigned __int64 *,ulong,char const *,UACPROMPT_POLICY *,int *)
0x18003f376  mov     [rsp+240h+Reply], eax
0x18003f37a  mov     rcx, [rbp+140h+Handle]; Handle
0x18003f37e  test    rcx, rcx
0x18003f381  jz      short loc_18003F393
0x18003f383  call    cs:__imp_NtClose
0x18003f38a  nop     dword ptr [rax+rax+00h]
0x18003f38f  mov     [rbp+140h+Handle], r14
0x18003f393  mov     rcx, [rbp+140h+hMem]; hMem
0x18003f397  call    cs:__imp_LocalFree
0x18003f39e  nop     dword ptr [rax+rax+00h]
0x18003f3a3  cmp     rbx, r15
0x18003f3a6  jz      short loc_18003F3BB
0x18003f3a8  mov     rcx, rbx; hMem
0x18003f3ab  call    cs:__imp_LocalFree
0x18003f3b2  nop     dword ptr [rax+rax+00h]
0x18003f3b7  mov     [rbp+140h+var_1B8], r15
0x18003f3bb  lea     rcx, [rbp+140h+var_170]; lpPerformanceCount
0x18003f3bf  call    cs:__imp_QueryPerformanceCounter
0x18003f3c6  nop     dword ptr [rax+rax+00h]
0x18003f3cb  mov     rax, qword ptr [rbp+140h+var_170]
0x18003f3cf  sub     rax, qword ptr [rbp+140h+PerformanceCount]
0x18003f3d3  imul    rax, 3E8h
0x18003f3da  cqo
0x18003f3dc  idiv    qword ptr [rbp+140h+Frequency]
0x18003f3e0  mov     [rbp+140h+var_190], rax
0x18003f3e4  mov     eax, [rsp+240h+var_1C8]
0x18003f3e8  mov     [rsp+240h+var_1C8], eax
0x18003f3ec  mov     eax, [rsp+240h+Reply]
0x18003f3f0  cmp     eax, 4C7h
0x18003f3f5  jnz     short loc_18003F3FE
0x18003f3f7  mov     [rsp+240h+var_1CC], r14d
0x18003f3fc  jmp     short loc_18003F40E
0x18003f3fe  test    eax, eax
0x18003f400  jle     short loc_18003F40A
0x18003f402  movzx   eax, ax
0x18003f405  or      eax, 80070000h
0x18003f40a  mov     [rsp+240h+var_1CC], eax
0x18003f40e  lea     rax, [rbp+140h+var_E0]
0x18003f412  mov     qword ptr [rsp+240h+var_1F0], rax
0x18003f417  lea     r9, [rbp+140h+var_1C0]
0x18003f41b  lea     rax, [rbp+140h+var_190]
0x18003f41f  mov     [rsp+240h+var_1F8], rax
0x18003f424  lea     r8, [rbp+140h+var_1AC]
0x18003f428  lea     rax, [rsp+240h+var_1C8]
0x18003f42d  mov     [rsp+240h+var_200], rax
0x18003f432  lea     rdx, [rsp+240h+Reply]
0x18003f437  lea     rax, [rbp+140h+var_1B0]
0x18003f43b  mov     qword ptr [rsp+240h+var_208], rax
0x18003f440  lea     rcx, [rsp+240h+var_1CC]
0x18003f445  lea     rax, [rbp+140h+var_198]
0x18003f449  mov     [rsp+240h+var_210], rax
0x18003f44e  lea     rax, [rbp+140h+var_1B8]
0x18003f452  mov     [rsp+240h+var_218], rax
0x18003f457  lea     rax, [rbp+140h+var_158]
0x18003f45b  mov     [rsp+240h+var_220], rax
0x18003f460  call    ??$COMElevation@JAEAKAEAKAEAKAEAPEAU_GUID@@AEAPEBGAEAPEBGAEAHKAEA_JAEAY0IB@D@LUATelemetry@@SAX$$QEAJAEAK11AEAPEAU_GUID@@AEAPEBG3AEAH$$QEAKAEA_JAEAY0IB@D@Z; LUATelemetry::COMElevation<long,ulong &,ulong &,ulong &,_GUID * &,ushort const * &,ushort const * &,int &,ulong,__int64 &,char (&)[129]>(long &&,ulong &,ulong &,ulong &,_GUID * &,ushort const * &,ushort const * &,int &,ulong &&,__int64 &,char (&)[129])
0x18003f465  mov     rcx, [rbp+140h+pAsync]; pAsync
0x18003f469  lea     rdx, [rsp+240h+Reply]; Reply
0x18003f46e  call    cs:__imp_RpcAsyncCompleteCall
0x18003f475  nop     dword ptr [rax+rax+00h]
0x18003f47a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f481  lea     rax, WPP_GLOBAL_Control
0x18003f488  cmp     rcx, rax
0x18003f48b  jz      short loc_18003F4AD
0x18003f48d  test    byte ptr [rcx+1Ch], 1
0x18003f491  jz      short loc_18003F4AD
0x18003f493  mov     r9d, [rsp+240h+Reply]
0x18003f498  lea     r8, WPP_aba5399977573c9264c162bacbfc9302_Traceguids
0x18003f49f  mov     rcx, [rcx+10h]
0x18003f4a3  mov     edx, 0Dh
0x18003f4a8  call    WPP_SF_D
0x18003f4ad  lea     rcx, [rbp+140h+var_130]; this
0x18003f4b1  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18003f4b6  mov     rcx, [rbp+140h+var_50]
0x18003f4bd  xor     rcx, rsp; StackCookie
  ... truncated ...
```
