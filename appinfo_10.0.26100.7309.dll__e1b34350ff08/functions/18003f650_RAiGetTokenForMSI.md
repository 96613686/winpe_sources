# RAiGetTokenForMSI

- ea: `0x18003f650`
- end: `0x18003fb55`
- name: `RAiGetTokenForMSI`
- size: `1285`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18001b494`
- `0x18001b4a0`
- `0x1800234a0`
- `0x180023e14`
- `0x180024440`
- `0x180026de4`
- `0x180027224`
- `0x180038670`
- `0x1800393e0`
- `0x18003df54`
- `0x18003e094`
- `0x18003f650`
- `0x18003fb5c`
- `0x180041eb4`
- `0x1800444ba`
- `0x1800444e0`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003faea`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003faea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fa15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fa15`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003f747`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003f747`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003f737`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003fa25`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003f737`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003fa25`

## string_xrefs

- `0x18003f7fc`: `RAiGetTokenForMSI`
- `0x18003f7f0`: `hwnd = %x dwRunLevel = %x fAdjustTokenSD = %x dwAction = %x dwTimeout = %x\n	lpDesktop = %ws\n	lpProductName = %ws\n	lpVersion = %ws\n	lpLanguage = %ws\n	lpManufacturer = %ws\n	lpPackagePath = %ws\n	lpPackageSource = %ws\n	lpCvStr = %s\n`

## pseudocode

```c
void __fastcall RAiGetTokenForMSI(
        struct _RPC_ASYNC_STATE *a1,
        void *a2,
        unsigned __int64 a3,
        unsigned int a4,
        int a5,
        unsigned __int16 *a6,
        unsigned int a7,
        unsigned __int16 *a8,
        unsigned __int16 *a9,
        unsigned __int16 *a10,
        wchar_t *a11,
        wchar_t *a12,
        wchar_t *a13,
        unsigned int a14,
        unsigned __int16 **a15,
        unsigned __int16 **a16,
        unsigned int a17,
        unsigned __int64 *a18)
{
  unsigned int v18; // r12d
  const unsigned __int16 *v20; // rbx
  const unsigned __int16 *v21; // rsi
  wchar_t *v22; // r14
  wchar_t *v23; // r15
  const unsigned __int16 *v24; // rdi
  const unsigned __int16 *v25; // r9
  const unsigned __int16 *v26; // r8
  unsigned __int16 *v27; // r10
  unsigned __int16 *v28; // r11
  const unsigned __int16 *v29; // rdx
  const unsigned __int16 *v30; // rcx
  const unsigned __int16 *v31; // rax
  void *v32; // rax
  volatile signed __int64 *v33; // rbx
  const unsigned __int16 *v34; // rdx
  const unsigned __int16 *v35; // rcx
  const unsigned __int16 *v36; // rax
  unsigned int v37; // edi
  unsigned int v38; // eax
  struct _CONSENTUI_PARAM_HEADER *v39; // rbx
  void *v40; // rdx
  unsigned int v41; // eax
  int v42; // [rsp+80h] [rbp-80h] BYREF
  int Reply; // [rsp+84h] [rbp-7Ch] BYREF
  int v44; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v45; // [rsp+8Ch] [rbp-74h]
  unsigned int v46; // [rsp+90h] [rbp-70h]
  unsigned int v47; // [rsp+98h] [rbp-68h] BYREF
  int v48; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v49; // [rsp+A4h] [rbp-5Ch] BYREF
  wchar_t *v50; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v51; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v52; // [rsp+B8h] [rbp-48h] BYREF
  wchar_t *v53; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 *v54; // [rsp+C8h] [rbp-38h] BYREF
  void *v55; // [rsp+D0h] [rbp-30h] BYREF
  const unsigned __int16 *v56; // [rsp+D8h] [rbp-28h]
  wchar_t *v57; // [rsp+E0h] [rbp-20h]
  unsigned __int16 *v58; // [rsp+E8h] [rbp-18h]
  HLOCAL hMem; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 *v60; // [rsp+F8h] [rbp-8h]
  LARGE_INTEGER v61; // [rsp+100h] [rbp+0h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+108h] [rbp+8h] BYREF
  LARGE_INTEGER Frequency; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 *v64; // [rsp+118h] [rbp+18h]
  unsigned __int16 *v65; // [rsp+120h] [rbp+20h]
  unsigned __int16 **v66; // [rsp+128h] [rbp+28h]
  unsigned __int16 **v67; // [rsp+130h] [rbp+30h]
  PRPC_ASYNC_STATE pAsync; // [rsp+138h] [rbp+38h]
  char v69[80]; // [rsp+140h] [rbp+40h] BYREF
  char v70[144]; // [rsp+190h] [rbp+90h] BYREF

  v18 = a4;
  v20 = a8;
  v21 = a9;
  v22 = a11;
  v23 = a13;
  v60 = a6;
  v57 = a12;
  v42 = a5;
  v67 = a15;
  v66 = a16;
  v46 = a17;
  pAsync = a1;
  v54 = a18;
  v45 = a7;
  v49 = a7;
  hMem = 0;
  v48 = 0;
  v44 = 0;
  Frequency.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  v61.QuadPart = 0;
  v55 = a2;
  v58 = a10;
  v47 = a4;
  v52 = a8;
  v51 = a9;
  v50 = a11;
  v53 = a13;
  QueryPerformanceCounter(&PerformanceCount);
  QueryPerformanceFrequency(&Frequency);
  memset_0(v70, 0, 0x81u);
  v24 = L"NULL";
  v25 = a12;
  v26 = a13;
  if ( !a12 )
    v25 = L"NULL";
  v27 = v58;
  v56 = v25;
  if ( !v58 )
    v27 = L"NULL";
  v28 = v60;
  v64 = v27;
  if ( !v60 )
    v28 = L"NULL";
  v29 = a11;
  v65 = v28;
  v30 = a9;
  v31 = a8;
  if ( !a13 )
    v26 = L"NULL";
  if ( !a11 )
    v29 = L"NULL";
  if ( !a9 )
    v30 = L"NULL";
  if ( !a8 )
    v31 = L"NULL";
  LUATelemetry::WatchCurrentThread(
    v69,
    "RAiGetTokenForMSI",
    "hwnd = %x dwRunLevel = %x fAdjustTokenSD = %x dwAction = %x dwTimeout = %x\n"
    "\tlpDesktop = %ws\n"
    "\tlpProductName = %ws\n"
    "\tlpVersion = %ws\n"
    "\tlpLanguage = %ws\n"
    "\tlpManufacturer = %ws\n"
    "\tlpPackagePath = %ws\n"
    "\tlpPackageSource = %ws\n"
    "\tlpCvStr = %s\n",
    (unsigned int)a3,
    v18,
    v42,
    v45,
    v46,
    v28,
    v31,
    v30,
    v27,
    v29,
    v56,
    v26,
    v70);
  if ( g_pMSIElevationActivityTelemetryRateLimiter
    && (unsigned int)RateLimiter::RequestPermission(g_pMSIElevationActivityTelemetryRateLimiter) )
  {
    v32 = operator new(0x90u);
    if ( v32 )
      v33 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v32);
    else
      v33 = 0;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v33,
      _InterlockedExchangeAdd64(v33 + 17, 0),
      v70);
    if ( v33 )
      operator delete((void *)v33);
    v23 = v53;
    v22 = v50;
    v21 = v51;
    v20 = v52;
    v18 = v47;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v34 = L"NULL";
    if ( v23 )
      v34 = v23;
    v35 = L"NULL";
    v36 = L"NULL";
    if ( v22 )
      v35 = v22;
    if ( v21 )
      v36 = v21;
    if ( v20 )
      v24 = v20;
    WPP_SF_DDDDDSSSSSSSs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)v56,
      (_DWORD)WPP_GLOBAL_Control,
      a3,
      v18,
      v42,
      v45,
      v46,
      (__int64)v65,
      (__int64)v24,
      (__int64)v36,
      (__int64)v64,
      (__int64)v35,
      (__int64)v56,
      (__int64)v34,
      (__int64)v70);
  }
  v37 = AiLogPerfTrackEvent(&AppInfo_PerfTrack_Elevation_MSI_Start);
  v38 = AiBuildMSIParams(
          v45,
          v20,
          v21,
          v58,
          v22,
          v57,
          v23,
          a14,
          (const unsigned __int16 **)v67,
          (const unsigned __int16 **)v66,
          (struct _CONSENTUI_PARAM_HEADER **)&hMem);
  v39 = (struct _CONSENTUI_PARAM_HEADER *)hMem;
  Reply = v38;
  if ( !v38 )
  {
    v40 = v55;
    *((_DWORD *)hMem + 13) = v37;
    Reply = AipGetTokenForService(
              1u,
              v40,
              a3,
              v18,
              v42,
              v60,
              v39,
              v46,
              0,
              v54,
              0,
              v70,
              (enum UACPROMPT_POLICY *)&v44,
              &v48);
  }
  LocalFree(v39);
  QueryPerformanceCounter(&v61);
  v54 = (unsigned __int64 *)(1000 * (v61.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart);
  v55 = v70;
  v41 = Reply;
  if ( Reply == 1223 )
  {
    v42 = 0;
  }
  else
  {
    if ( Reply > 0 )
      v41 = (unsigned __int16)Reply | 0x80070000;
    v42 = v41;
  }
  LUATelemetry::MSIElevation<long,unsigned long &,unsigned long &,unsigned short const * &,unsigned short const * &,unsigned short const * &,unsigned short const * &,enum _MSI_ACTION &,unsigned long &,int &,unsigned long,__int64 &,char const *>(
    (unsigned int)&v42,
    (unsigned int)&Reply,
    (unsigned int)&v47,
    (unsigned int)&v53,
    (__int64)&v52,
    (__int64)&v51,
    (__int64)&v50,
    (__int64)&v49,
    (__int64)&a14,
    (__int64)&v48,
    (__int64)&v44,
    (__int64)&v54,
    (__int64)&v55);
  RpcAsyncCompleteCall(pAsync, &Reply);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      &WPP_aba5399977573c9264c162bacbfc9302_Traceguids,
      (unsigned int)Reply);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v69);
}

```

## disassembly

```asm
0x18003f650  push    rbp
0x18003f652  push    rbx
0x18003f653  push    rsi
0x18003f654  push    rdi
0x18003f655  push    r12
0x18003f657  push    r13
0x18003f659  push    r14
0x18003f65b  push    r15
0x18003f65d  lea     rbp, [rsp-138h]
0x18003f665  sub     rsp, 238h
0x18003f66c  mov     rax, cs:__security_cookie
0x18003f673  xor     rax, rsp
0x18003f676  mov     [rbp+170h+var_50], rax
0x18003f67d  mov     rax, [rbp+170h+arg_28]
0x18003f684  mov     r12d, r9d
0x18003f687  mov     r9, [rbp+170h+arg_48]
0x18003f68e  mov     r13, r8
0x18003f691  mov     rbx, [rbp+170h+arg_38]
0x18003f698  mov     rsi, [rbp+170h+arg_40]
0x18003f69f  mov     r14, [rbp+170h+arg_50]
0x18003f6a6  mov     r15, [rbp+170h+arg_60]
0x18003f6ad  mov     [rbp+170h+var_178], rax
0x18003f6b1  mov     rax, [rbp+170h+arg_58]
0x18003f6b8  mov     [rbp+170h+var_190], rax
0x18003f6bc  mov     eax, [rbp+170h+arg_20]
0x18003f6c2  mov     [rbp+170h+var_1F0], eax
0x18003f6c5  mov     rax, [rbp+170h+arg_70]
0x18003f6cc  mov     [rbp+170h+var_140], rax
0x18003f6d0  mov     rax, [rbp+170h+arg_78]
0x18003f6d7  mov     [rbp+170h+var_148], rax
0x18003f6db  mov     eax, [rbp+170h+arg_80]
0x18003f6e1  mov     [rbp+170h+var_1E0], eax
0x18003f6e4  mov     rax, [rbp+170h+arg_88]
0x18003f6eb  mov     [rbp+170h+pAsync], rcx
0x18003f6ef  mov     ecx, [rbp+170h+arg_30]
0x18003f6f5  mov     [rbp+170h+var_1A8], rax
0x18003f6f9  xor     eax, eax
0x18003f6fb  mov     [rbp+170h+var_1E4], ecx
0x18003f6fe  mov     [rbp+170h+var_1CC], ecx
0x18003f701  lea     rcx, [rbp+170h+PerformanceCount]; lpPerformanceCount
0x18003f705  mov     [rbp+170h+hMem], rax
0x18003f709  mov     [rbp+170h+var_1D0], eax
0x18003f70c  mov     [rbp+170h+var_1E8], eax
0x18003f70f  mov     qword ptr [rbp+170h+Frequency], rax
0x18003f713  mov     qword ptr [rbp+170h+PerformanceCount], rax
0x18003f717  mov     qword ptr [rbp+170h+var_170], rax
0x18003f71b  mov     [rbp+170h+var_1A0], rdx
0x18003f71f  mov     [rbp+170h+var_188], r9
0x18003f723  mov     [rbp+170h+var_1D8], r12d
0x18003f727  mov     [rbp+170h+var_1B8], rbx
0x18003f72b  mov     [rbp+170h+var_1C0], rsi
0x18003f72f  mov     [rbp+170h+var_1C8], r14
0x18003f733  mov     [rbp+170h+var_1B0], r15
0x18003f737  call    cs:__imp_QueryPerformanceCounter
0x18003f73e  nop     dword ptr [rax+rax+00h]
0x18003f743  lea     rcx, [rbp+170h+Frequency]; lpFrequency
0x18003f747  call    cs:__imp_QueryPerformanceFrequency
0x18003f74e  nop     dword ptr [rax+rax+00h]
0x18003f753  xor     edx, edx; Val
0x18003f755  lea     rcx, [rbp+170h+var_E0]; void *
0x18003f75c  mov     r8d, 81h; Size
0x18003f762  call    memset_0
0x18003f767  mov     rax, [rbp+170h+var_190]
0x18003f76b  lea     rdi, aNull_0; "NULL"
0x18003f772  test    rax, rax
0x18003f775  mov     r9, rax
0x18003f778  mov     rax, [rbp+170h+var_188]
0x18003f77c  mov     r8, r15
0x18003f77f  cmovz   r9, rdi
0x18003f783  mov     r10, rax
0x18003f786  test    rax, rax
0x18003f789  mov     [rbp+170h+var_198], r9
0x18003f78d  mov     rax, [rbp+170h+var_178]
0x18003f791  lea     r9, [rbp+170h+var_E0]
0x18003f798  cmovz   r10, rdi
0x18003f79c  mov     [rsp+270h+var_1F8], r9
0x18003f7a1  mov     r9, [rbp+170h+var_198]
0x18003f7a5  test    rax, rax
0x18003f7a8  mov     r11, rax
0x18003f7ab  mov     [rbp+170h+var_158], r10
0x18003f7af  cmovz   r11, rdi
0x18003f7b3  mov     rdx, r14
0x18003f7b6  test    r15, r15
0x18003f7b9  mov     [rbp+170h+var_150], r11
0x18003f7bd  mov     rcx, rsi
0x18003f7c0  mov     rax, rbx
0x18003f7c3  cmovz   r8, rdi
0x18003f7c7  test    r14, r14
0x18003f7ca  mov     [rsp+270h+var_200], r8
0x18003f7cf  cmovz   rdx, rdi
0x18003f7d3  mov     [rsp+270h+var_208], r9
0x18003f7d8  test    rsi, rsi
0x18003f7db  mov     [rsp+270h+var_210], rdx
0x18003f7e0  cmovz   rcx, rdi
0x18003f7e4  test    rbx, rbx
0x18003f7e7  cmovz   rax, rdi
0x18003f7eb  mov     [rsp+270h+var_218], r10
0x18003f7f0  lea     r8, aHwndXDwrunleve; "hwnd = %x dwRunLevel = %x fAdjustTokenS"...
0x18003f7f7  mov     [rsp+270h+var_220], rcx
0x18003f7fc  lea     rdx, aRaigettokenfor; "RAiGetTokenForMSI"
0x18003f803  mov     [rsp+270h+var_228], rax
0x18003f808  lea     rcx, [rbp+170h+var_130]
0x18003f80c  mov     eax, [rbp+170h+var_1E0]
0x18003f80f  mov     r9d, r13d
0x18003f812  mov     [rsp+270h+var_230], r11
0x18003f817  mov     [rsp+270h+var_238], eax
0x18003f81b  mov     eax, [rbp+170h+var_1E4]
0x18003f81e  mov     dword ptr [rsp+270h+var_240], eax
0x18003f822  mov     eax, [rbp+170h+var_1F0]
0x18003f825  mov     dword ptr [rsp+270h+var_248], eax
0x18003f829  mov     dword ptr [rsp+270h+var_250], r12d
0x18003f82e  call    ?WatchCurrentThread@LUATelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; LUATelemetry::WatchCurrentThread(char const *,char const *,...)
0x18003f833  mov     rcx, cs:?g_pMSIElevationActivityTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; this
0x18003f83a  test    rcx, rcx
0x18003f83d  jz      short loc_18003F8A1
0x18003f83f  call    ?RequestPermission@RateLimiter@@QEAAHXZ; RateLimiter::RequestPermission(void)
0x18003f844  test    eax, eax
0x18003f846  jz      short loc_18003F8A1
0x18003f848  mov     ecx, 90h; Size
0x18003f84d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003f852  test    rax, rax
0x18003f855  jz      short loc_18003F864
0x18003f857  mov     rcx, rax
0x18003f85a  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18003f85f  mov     rbx, rax
0x18003f862  jmp     short loc_18003F866
0x18003f864  xor     ebx, ebx
0x18003f866  xor     edx, edx
0x18003f868  lock xadd [rbx+88h], rdx; unsigned __int64
0x18003f871  lea     r8, [rbp+170h+var_E0]; char *
0x18003f878  mov     rcx, rbx; this
0x18003f87b  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18003f880  test    rbx, rbx
0x18003f883  jz      short loc_18003F88D
0x18003f885  mov     rcx, rbx; Block
0x18003f888  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003f88d  mov     r15, [rbp+170h+var_1B0]
0x18003f891  mov     r14, [rbp+170h+var_1C8]
0x18003f895  mov     rsi, [rbp+170h+var_1C0]
0x18003f899  mov     rbx, [rbp+170h+var_1B8]
0x18003f89d  mov     r12d, [rbp+170h+var_1D8]
0x18003f8a1  mov     r8, cs:WPP_GLOBAL_Control
0x18003f8a8  lea     rax, WPP_GLOBAL_Control
0x18003f8af  cmp     r8, rax
0x18003f8b2  jz      loc_18003F949
0x18003f8b8  test    byte ptr [r8+1Ch], 1
0x18003f8bd  jz      loc_18003F949
0x18003f8c3  test    r15, r15
0x18003f8c6  lea     r9, [rbp+170h+var_E0]
0x18003f8cd  mov     [rsp+270h+var_1F8], r9
0x18003f8d2  mov     rdx, rdi
0x18003f8d5  cmovnz  rdx, r15
0x18003f8d9  mov     rcx, rdi
0x18003f8dc  mov     [rsp+270h+var_200], rdx
0x18003f8e1  test    r14, r14
0x18003f8e4  mov     rdx, [rbp+170h+var_198]
0x18003f8e8  mov     rax, rdi
0x18003f8eb  mov     [rsp+270h+var_208], rdx
0x18003f8f0  cmovnz  rcx, r14
0x18003f8f4  mov     [rsp+270h+var_210], rcx
0x18003f8f9  test    rsi, rsi
0x18003f8fc  mov     rcx, [rbp+170h+var_158]
0x18003f900  mov     r9d, r13d
0x18003f903  mov     [rsp+270h+var_218], rcx
0x18003f908  cmovnz  rax, rsi
0x18003f90c  mov     rcx, [r8+10h]
0x18003f910  test    rbx, rbx
0x18003f913  mov     [rsp+270h+var_220], rax
0x18003f918  mov     rax, [rbp+170h+var_150]
0x18003f91c  cmovnz  rdi, rbx
0x18003f920  mov     [rsp+270h+var_228], rdi
0x18003f925  mov     [rsp+270h+var_230], rax
0x18003f92a  mov     eax, [rbp+170h+var_1E0]
0x18003f92d  mov     [rsp+270h+var_238], eax
0x18003f931  mov     eax, [rbp+170h+var_1E4]
0x18003f934  mov     dword ptr [rsp+270h+var_240], eax
0x18003f938  mov     eax, [rbp+170h+var_1F0]
0x18003f93b  mov     dword ptr [rsp+270h+var_248], eax
0x18003f93f  mov     dword ptr [rsp+270h+var_250], r12d
0x18003f944  call    WPP_SF_DDDDDSSSSSSSs
0x18003f949  lea     rcx, AppInfo_PerfTrack_Elevation_MSI_Start; struct _EVENT_DESCRIPTOR *
0x18003f950  call    ?AiLogPerfTrackEvent@@YAKPEBU_EVENT_DESCRIPTOR@@@Z; AiLogPerfTrackEvent(_EVENT_DESCRIPTOR const *)
0x18003f955  mov     ecx, [rbp+170h+arg_68]
0x18003f95b  mov     edi, eax
0x18003f95d  mov     r9, [rbp+170h+var_188]; unsigned __int16 *
0x18003f961  lea     rax, [rbp+170h+hMem]
0x18003f965  mov     [rsp+270h+var_220], rax; struct _CONSENTUI_PARAM_HEADER **
0x18003f96a  mov     r8, rsi; unsigned __int16 *
0x18003f96d  mov     rax, [rbp+170h+var_148]
0x18003f971  mov     rdx, rbx; unsigned __int16 *
0x18003f974  mov     [rsp+270h+var_228], rax; unsigned __int16 **
0x18003f979  mov     rax, [rbp+170h+var_140]
0x18003f97d  mov     [rsp+270h+var_230], rax; unsigned __int16 **
0x18003f982  mov     rax, [rbp+170h+var_190]
0x18003f986  mov     [rsp+270h+var_238], ecx; unsigned int
0x18003f98a  mov     ecx, [rbp+170h+var_1E4]; unsigned int
0x18003f98d  mov     [rsp+270h+var_240], r15; wchar_t *
0x18003f992  mov     [rsp+270h+var_248], rax; wchar_t *
0x18003f997  mov     [rsp+270h+var_250], r14; wchar_t *
0x18003f99c  call    ?AiBuildMSIParams@@YAKKPEBG00000KPEAPEBG1PEAPEAU_CONSENTUI_PARAM_HEADER@@@Z; AiBuildMSIParams(ulong,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const * *,ushort const * *,_CONSENTUI_PARAM_HEADER * *)
0x18003f9a1  mov     rbx, [rbp+170h+hMem]
0x18003f9a5  xor     esi, esi
0x18003f9a7  mov     [rbp+170h+Reply], eax
0x18003f9aa  test    eax, eax
0x18003f9ac  jnz     short loc_18003FA12
0x18003f9ae  mov     rdx, [rbp+170h+var_1A0]; void *
0x18003f9b2  lea     rax, [rbp+170h+var_1D0]
0x18003f9b6  mov     [rsp+270h+var_208], rax; int *
0x18003f9bb  lea     ecx, [rsi+1]; unsigned int
0x18003f9be  lea     rax, [rbp+170h+var_1E8]
0x18003f9c2  mov     [rbx+34h], edi
0x18003f9c5  mov     [rsp+270h+var_210], rax; enum UACPROMPT_POLICY *
0x18003f9ca  mov     r9d, r12d; unsigned int
0x18003f9cd  lea     rax, [rbp+170h+var_E0]
0x18003f9d4  mov     r8, r13; unsigned __int64
0x18003f9d7  mov     [rsp+270h+var_218], rax; char *
0x18003f9dc  mov     rax, [rbp+170h+var_1A8]
0x18003f9e0  mov     dword ptr [rsp+270h+var_220], esi; unsigned int
0x18003f9e4  mov     [rsp+270h+var_228], rax; unsigned __int64 *
0x18003f9e9  mov     eax, [rbp+170h+var_1E0]
0x18003f9ec  mov     [rsp+270h+var_230], rsi; unsigned __int16 *
0x18003f9f1  mov     [rsp+270h+var_238], eax; unsigned int
0x18003f9f5  mov     rax, [rbp+170h+var_178]
0x18003f9f9  mov     [rsp+270h+var_240], rbx; struct _CONSENTUI_PARAM_HEADER *
0x18003f9fe  mov     [rsp+270h+var_248], rax; unsigned __int16 *
0x18003fa03  mov     eax, [rbp+170h+var_1F0]
0x18003fa06  mov     dword ptr [rsp+270h+var_250], eax; int
0x18003fa0a  call    ?AipGetTokenForService@@YAKKPEAX_KKHPEBGPEAU_CONSENTUI_PARAM_HEADER@@K2PEA_KKPEBDPEAW4UACPROMPT_POLICY@@PEAH@Z; AipGetTokenForService(ulong,void *,unsigned __int64,ulong,int,ushort const *,_CONSENTUI_PARAM_HEADER *,ulong,ushort const *,unsigned __int64 *,ulong,char const *,UACPROMPT_POLICY *,int *)
0x18003fa0f  mov     [rbp+170h+Reply], eax
0x18003fa12  mov     rcx, rbx; hMem
0x18003fa15  call    cs:__imp_LocalFree
0x18003fa1c  nop     dword ptr [rax+rax+00h]
0x18003fa21  lea     rcx, [rbp+170h+var_170]; lpPerformanceCount
0x18003fa25  call    cs:__imp_QueryPerformanceCounter
0x18003fa2c  nop     dword ptr [rax+rax+00h]
0x18003fa31  mov     rax, qword ptr [rbp+170h+var_170]
0x18003fa35  sub     rax, qword ptr [rbp+170h+PerformanceCount]
0x18003fa39  imul    rax, 3E8h
0x18003fa40  cqo
0x18003fa42  idiv    qword ptr [rbp+170h+Frequency]
0x18003fa46  mov     [rbp+170h+var_1A8], rax
0x18003fa4a  lea     rax, [rbp+170h+var_E0]
0x18003fa51  mov     [rbp+170h+var_1A0], rax
0x18003fa55  mov     eax, [rbp+170h+var_1E8]
0x18003fa58  mov     [rbp+170h+var_1E8], eax
0x18003fa5b  mov     eax, [rbp+170h+Reply]
0x18003fa5e  cmp     eax, 4C7h
0x18003fa63  jnz     short loc_18003FA6A
0x18003fa65  mov     [rbp+170h+var_1F0], esi
0x18003fa68  jmp     short loc_18003FA79
0x18003fa6a  test    eax, eax
0x18003fa6c  jle     short loc_18003FA76
0x18003fa6e  movzx   eax, ax
0x18003fa71  or      eax, 80070000h
0x18003fa76  mov     [rbp+170h+var_1F0], eax
0x18003fa79  lea     rax, [rbp+170h+var_1A0]
0x18003fa7d  mov     [rsp+270h+var_210], rax
0x18003fa82  lea     r9, [rbp+170h+var_1B0]
0x18003fa86  lea     rax, [rbp+170h+var_1A8]
0x18003fa8a  mov     [rsp+270h+var_218], rax
0x18003fa8f  lea     r8, [rbp+170h+var_1D8]
0x18003fa93  lea     rax, [rbp+170h+var_1E8]
0x18003fa97  mov     [rsp+270h+var_220], rax
0x18003fa9c  lea     rdx, [rbp+170h+Reply]
0x18003faa0  lea     rax, [rbp+170h+var_1D0]
0x18003faa4  mov     [rsp+270h+var_228], rax
0x18003faa9  lea     rcx, [rbp+170h+var_1F0]
0x18003faad  lea     rax, [rbp+170h+arg_68]
0x18003fab4  mov     [rsp+270h+var_230], rax
0x18003fab9  lea     rax, [rbp+170h+var_1CC]
0x18003fabd  mov     qword ptr [rsp+270h+var_238], rax
0x18003fac2  lea     rax, [rbp+170h+var_1C8]
0x18003fac6  mov     [rsp+270h+var_240], rax
0x18003facb  lea     rax, [rbp+170h+var_1C0]
0x18003facf  mov     [rsp+270h+var_248], rax
0x18003fad4  lea     rax, [rbp+170h+var_1B8]
0x18003fad8  mov     [rsp+270h+var_250], rax
0x18003fadd  call    ??$MSIElevation@JAEAKAEAKAEAPEBGAEAPEBGAEAPEBGAEAPEBGAEAW4_MSI_ACTION@@AEAKAEAHKAEA_JPEBD@LUATelemetry@@SAX$$QEAJAEAK1AEAPEBG222AEAW4_MSI_ACTION@@1AEAH$$QEAKAEA_J$$QEAPEBD@Z; LUATelemetry::MSIElevation<long,ulong &,ulong &,ushort const * &,ushort const * &,ushort const * &,ushort const * &,_MSI_ACTION &,ulong &,int &,ulong,__int64 &,char const *>(long &&,ulong &,ulong &,ushort const * &,ushort const * &,ushort const * &,ushort const * &,_MSI_ACTION &,ulong &,int &,ulong &&,__int64 &,char const * &&)
0x18003fae2  mov     rcx, [rbp+170h+pAsync]; pAsync
0x18003fae6  lea     rdx, [rbp+170h+Reply]; Reply
0x18003faea  call    cs:__imp_RpcAsyncCompleteCall
0x18003faf1  nop     dword ptr [rax+rax+00h]
0x18003faf6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fafd  lea     rax, WPP_GLOBAL_Control
0x18003fb04  cmp     rcx, rax
0x18003fb07  jz      short loc_18003FB28
0x18003fb09  test    byte ptr [rcx+1Ch], 1
0x18003fb0d  jz      short loc_18003FB28
0x18003fb0f  mov     r9d, [rbp+170h+Reply]
0x18003fb13  lea     r8, WPP_aba5399977573c9264c162bacbfc9302_Traceguids
0x18003fb1a  mov     rcx, [rcx+10h]
0x18003fb1e  mov     edx, 0Fh
0x18003fb23  call    WPP_SF_D
0x18003fb28  lea     rcx, [rbp+170h+var_130]; this
0x18003fb2c  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18003fb31  mov     rcx, [rbp+170h+var_50]
0x18003fb38  xor     rcx, rsp; StackCookie
0x18003fb3b  call    __security_check_cookie
0x18003fb40  add     rsp, 238h
0x18003fb47  pop     r15
  ... truncated ...
```
