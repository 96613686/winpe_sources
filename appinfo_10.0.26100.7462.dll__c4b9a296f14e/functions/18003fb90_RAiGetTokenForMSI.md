# RAiGetTokenForMSI

- ea: `0x18003fb90`
- end: `0x180040095`
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
- `0x180026eb4`
- `0x1800272f4`
- `0x1800389b0`
- `0x180039720`
- `0x18003e494`
- `0x18003e5d4`
- `0x18003fb90`
- `0x18004009c`
- `0x1800423f4`
- `0x1800449fa`
- `0x180044a20`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18004002a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004002a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ff55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ff55`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003fc87`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003fc87`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003fc77`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003ff65`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003fc77`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003ff65`

## string_xrefs

- `0x18003fd3c`: `RAiGetTokenForMSI`
- `0x18003fd30`: `hwnd = %x dwRunLevel = %x fAdjustTokenSD = %x dwAction = %x dwTimeout = %x\n	lpDesktop = %ws\n	lpProductName = %ws\n	lpVersion = %ws\n	lpLanguage = %ws\n	lpManufacturer = %ws\n	lpPackagePath = %ws\n	lpPackageSource = %ws\n	lpCvStr = %s\n`

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
  int v38; // eax
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
0x18003fb90  push    rbp
0x18003fb92  push    rbx
0x18003fb93  push    rsi
0x18003fb94  push    rdi
0x18003fb95  push    r12
0x18003fb97  push    r13
0x18003fb99  push    r14
0x18003fb9b  push    r15
0x18003fb9d  lea     rbp, [rsp-138h]
0x18003fba5  sub     rsp, 238h
0x18003fbac  mov     rax, cs:__security_cookie
0x18003fbb3  xor     rax, rsp
0x18003fbb6  mov     [rbp+170h+var_50], rax
0x18003fbbd  mov     rax, [rbp+170h+arg_28]
0x18003fbc4  mov     r12d, r9d
0x18003fbc7  mov     r9, [rbp+170h+arg_48]
0x18003fbce  mov     r13, r8
0x18003fbd1  mov     rbx, [rbp+170h+arg_38]
0x18003fbd8  mov     rsi, [rbp+170h+arg_40]
0x18003fbdf  mov     r14, [rbp+170h+arg_50]
0x18003fbe6  mov     r15, [rbp+170h+arg_60]
0x18003fbed  mov     [rbp+170h+var_178], rax
0x18003fbf1  mov     rax, [rbp+170h+arg_58]
0x18003fbf8  mov     [rbp+170h+var_190], rax
0x18003fbfc  mov     eax, [rbp+170h+arg_20]
0x18003fc02  mov     [rbp+170h+var_1F0], eax
0x18003fc05  mov     rax, [rbp+170h+arg_70]
0x18003fc0c  mov     [rbp+170h+var_140], rax
0x18003fc10  mov     rax, [rbp+170h+arg_78]
0x18003fc17  mov     [rbp+170h+var_148], rax
0x18003fc1b  mov     eax, [rbp+170h+arg_80]
0x18003fc21  mov     [rbp+170h+var_1E0], eax
0x18003fc24  mov     rax, [rbp+170h+arg_88]
0x18003fc2b  mov     [rbp+170h+pAsync], rcx
0x18003fc2f  mov     ecx, [rbp+170h+arg_30]
0x18003fc35  mov     [rbp+170h+var_1A8], rax
0x18003fc39  xor     eax, eax
0x18003fc3b  mov     [rbp+170h+var_1E4], ecx
0x18003fc3e  mov     [rbp+170h+var_1CC], ecx
0x18003fc41  lea     rcx, [rbp+170h+PerformanceCount]; lpPerformanceCount
0x18003fc45  mov     [rbp+170h+hMem], rax
0x18003fc49  mov     [rbp+170h+var_1D0], eax
0x18003fc4c  mov     [rbp+170h+var_1E8], eax
0x18003fc4f  mov     qword ptr [rbp+170h+Frequency], rax
0x18003fc53  mov     qword ptr [rbp+170h+PerformanceCount], rax
0x18003fc57  mov     qword ptr [rbp+170h+var_170], rax
0x18003fc5b  mov     [rbp+170h+var_1A0], rdx
0x18003fc5f  mov     [rbp+170h+var_188], r9
0x18003fc63  mov     [rbp+170h+var_1D8], r12d
0x18003fc67  mov     [rbp+170h+var_1B8], rbx
0x18003fc6b  mov     [rbp+170h+var_1C0], rsi
0x18003fc6f  mov     [rbp+170h+var_1C8], r14
0x18003fc73  mov     [rbp+170h+var_1B0], r15
0x18003fc77  call    cs:__imp_QueryPerformanceCounter
0x18003fc7e  nop     dword ptr [rax+rax+00h]
0x18003fc83  lea     rcx, [rbp+170h+Frequency]; lpFrequency
0x18003fc87  call    cs:__imp_QueryPerformanceFrequency
0x18003fc8e  nop     dword ptr [rax+rax+00h]
0x18003fc93  xor     edx, edx; Val
0x18003fc95  lea     rcx, [rbp+170h+var_E0]; void *
0x18003fc9c  mov     r8d, 81h; Size
0x18003fca2  call    memset_0
0x18003fca7  mov     rax, [rbp+170h+var_190]
0x18003fcab  lea     rdi, aNull_0; "NULL"
0x18003fcb2  test    rax, rax
0x18003fcb5  mov     r9, rax
0x18003fcb8  mov     rax, [rbp+170h+var_188]
0x18003fcbc  mov     r8, r15
0x18003fcbf  cmovz   r9, rdi
0x18003fcc3  mov     r10, rax
0x18003fcc6  test    rax, rax
0x18003fcc9  mov     [rbp+170h+var_198], r9
0x18003fccd  mov     rax, [rbp+170h+var_178]
0x18003fcd1  lea     r9, [rbp+170h+var_E0]
0x18003fcd8  cmovz   r10, rdi
0x18003fcdc  mov     [rsp+270h+var_1F8], r9
0x18003fce1  mov     r9, [rbp+170h+var_198]
0x18003fce5  test    rax, rax
0x18003fce8  mov     r11, rax
0x18003fceb  mov     [rbp+170h+var_158], r10
0x18003fcef  cmovz   r11, rdi
0x18003fcf3  mov     rdx, r14
0x18003fcf6  test    r15, r15
0x18003fcf9  mov     [rbp+170h+var_150], r11
0x18003fcfd  mov     rcx, rsi
0x18003fd00  mov     rax, rbx
0x18003fd03  cmovz   r8, rdi
0x18003fd07  test    r14, r14
0x18003fd0a  mov     [rsp+270h+var_200], r8
0x18003fd0f  cmovz   rdx, rdi
0x18003fd13  mov     [rsp+270h+var_208], r9
0x18003fd18  test    rsi, rsi
0x18003fd1b  mov     [rsp+270h+var_210], rdx
0x18003fd20  cmovz   rcx, rdi
0x18003fd24  test    rbx, rbx
0x18003fd27  cmovz   rax, rdi
0x18003fd2b  mov     [rsp+270h+var_218], r10
0x18003fd30  lea     r8, aHwndXDwrunleve; "hwnd = %x dwRunLevel = %x fAdjustTokenS"...
0x18003fd37  mov     [rsp+270h+var_220], rcx
0x18003fd3c  lea     rdx, aRaigettokenfor; "RAiGetTokenForMSI"
0x18003fd43  mov     [rsp+270h+var_228], rax
0x18003fd48  lea     rcx, [rbp+170h+var_130]
0x18003fd4c  mov     eax, [rbp+170h+var_1E0]
0x18003fd4f  mov     r9d, r13d
0x18003fd52  mov     [rsp+270h+var_230], r11
0x18003fd57  mov     [rsp+270h+var_238], eax
0x18003fd5b  mov     eax, [rbp+170h+var_1E4]
0x18003fd5e  mov     dword ptr [rsp+270h+var_240], eax
0x18003fd62  mov     eax, [rbp+170h+var_1F0]
0x18003fd65  mov     dword ptr [rsp+270h+var_248], eax
0x18003fd69  mov     dword ptr [rsp+270h+var_250], r12d
0x18003fd6e  call    ?WatchCurrentThread@LUATelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; LUATelemetry::WatchCurrentThread(char const *,char const *,...)
0x18003fd73  mov     rcx, cs:?g_pMSIElevationActivityTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; this
0x18003fd7a  test    rcx, rcx
0x18003fd7d  jz      short loc_18003FDE1
0x18003fd7f  call    ?RequestPermission@RateLimiter@@QEAAHXZ; RateLimiter::RequestPermission(void)
0x18003fd84  test    eax, eax
0x18003fd86  jz      short loc_18003FDE1
0x18003fd88  mov     ecx, 90h; Size
0x18003fd8d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003fd92  test    rax, rax
0x18003fd95  jz      short loc_18003FDA4
0x18003fd97  mov     rcx, rax
0x18003fd9a  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18003fd9f  mov     rbx, rax
0x18003fda2  jmp     short loc_18003FDA6
0x18003fda4  xor     ebx, ebx
0x18003fda6  xor     edx, edx
0x18003fda8  lock xadd [rbx+88h], rdx; unsigned __int64
0x18003fdb1  lea     r8, [rbp+170h+var_E0]; char *
0x18003fdb8  mov     rcx, rbx; this
0x18003fdbb  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18003fdc0  test    rbx, rbx
0x18003fdc3  jz      short loc_18003FDCD
0x18003fdc5  mov     rcx, rbx; Block
0x18003fdc8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003fdcd  mov     r15, [rbp+170h+var_1B0]
0x18003fdd1  mov     r14, [rbp+170h+var_1C8]
0x18003fdd5  mov     rsi, [rbp+170h+var_1C0]
0x18003fdd9  mov     rbx, [rbp+170h+var_1B8]
0x18003fddd  mov     r12d, [rbp+170h+var_1D8]
0x18003fde1  mov     r8, cs:WPP_GLOBAL_Control
0x18003fde8  lea     rax, WPP_GLOBAL_Control
0x18003fdef  cmp     r8, rax
0x18003fdf2  jz      loc_18003FE89
0x18003fdf8  test    byte ptr [r8+1Ch], 1
0x18003fdfd  jz      loc_18003FE89
0x18003fe03  test    r15, r15
0x18003fe06  lea     r9, [rbp+170h+var_E0]
0x18003fe0d  mov     [rsp+270h+var_1F8], r9
0x18003fe12  mov     rdx, rdi
0x18003fe15  cmovnz  rdx, r15
0x18003fe19  mov     rcx, rdi
0x18003fe1c  mov     [rsp+270h+var_200], rdx
0x18003fe21  test    r14, r14
0x18003fe24  mov     rdx, [rbp+170h+var_198]
0x18003fe28  mov     rax, rdi
0x18003fe2b  mov     [rsp+270h+var_208], rdx
0x18003fe30  cmovnz  rcx, r14
0x18003fe34  mov     [rsp+270h+var_210], rcx
0x18003fe39  test    rsi, rsi
0x18003fe3c  mov     rcx, [rbp+170h+var_158]
0x18003fe40  mov     r9d, r13d
0x18003fe43  mov     [rsp+270h+var_218], rcx
0x18003fe48  cmovnz  rax, rsi
0x18003fe4c  mov     rcx, [r8+10h]
0x18003fe50  test    rbx, rbx
0x18003fe53  mov     [rsp+270h+var_220], rax
0x18003fe58  mov     rax, [rbp+170h+var_150]
0x18003fe5c  cmovnz  rdi, rbx
0x18003fe60  mov     [rsp+270h+var_228], rdi
0x18003fe65  mov     [rsp+270h+var_230], rax
0x18003fe6a  mov     eax, [rbp+170h+var_1E0]
0x18003fe6d  mov     [rsp+270h+var_238], eax
0x18003fe71  mov     eax, [rbp+170h+var_1E4]
0x18003fe74  mov     dword ptr [rsp+270h+var_240], eax
0x18003fe78  mov     eax, [rbp+170h+var_1F0]
0x18003fe7b  mov     dword ptr [rsp+270h+var_248], eax
0x18003fe7f  mov     dword ptr [rsp+270h+var_250], r12d
0x18003fe84  call    WPP_SF_DDDDDSSSSSSSs
0x18003fe89  lea     rcx, AppInfo_PerfTrack_Elevation_MSI_Start; struct _EVENT_DESCRIPTOR *
0x18003fe90  call    ?AiLogPerfTrackEvent@@YAKPEBU_EVENT_DESCRIPTOR@@@Z; AiLogPerfTrackEvent(_EVENT_DESCRIPTOR const *)
0x18003fe95  mov     ecx, [rbp+170h+arg_68]
0x18003fe9b  mov     edi, eax
0x18003fe9d  mov     r9, [rbp+170h+var_188]; unsigned __int16 *
0x18003fea1  lea     rax, [rbp+170h+hMem]
0x18003fea5  mov     [rsp+270h+var_220], rax; struct _CONSENTUI_PARAM_HEADER **
0x18003feaa  mov     r8, rsi; unsigned __int16 *
0x18003fead  mov     rax, [rbp+170h+var_148]
0x18003feb1  mov     rdx, rbx; unsigned __int16 *
0x18003feb4  mov     [rsp+270h+var_228], rax; unsigned __int16 **
0x18003feb9  mov     rax, [rbp+170h+var_140]
0x18003febd  mov     [rsp+270h+var_230], rax; unsigned __int16 **
0x18003fec2  mov     rax, [rbp+170h+var_190]
0x18003fec6  mov     [rsp+270h+var_238], ecx; unsigned int
0x18003feca  mov     ecx, [rbp+170h+var_1E4]; unsigned int
0x18003fecd  mov     [rsp+270h+var_240], r15; wchar_t *
0x18003fed2  mov     [rsp+270h+var_248], rax; wchar_t *
0x18003fed7  mov     [rsp+270h+var_250], r14; wchar_t *
0x18003fedc  call    ?AiBuildMSIParams@@YAKKPEBG00000KPEAPEBG1PEAPEAU_CONSENTUI_PARAM_HEADER@@@Z; AiBuildMSIParams(ulong,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const * *,ushort const * *,_CONSENTUI_PARAM_HEADER * *)
0x18003fee1  mov     rbx, [rbp+170h+hMem]
0x18003fee5  xor     esi, esi
0x18003fee7  mov     [rbp+170h+Reply], eax
0x18003feea  test    eax, eax
0x18003feec  jnz     short loc_18003FF52
0x18003feee  mov     rdx, [rbp+170h+var_1A0]; void *
0x18003fef2  lea     rax, [rbp+170h+var_1D0]
0x18003fef6  mov     [rsp+270h+var_208], rax; int *
0x18003fefb  lea     ecx, [rsi+1]; unsigned int
0x18003fefe  lea     rax, [rbp+170h+var_1E8]
0x18003ff02  mov     [rbx+34h], edi
0x18003ff05  mov     [rsp+270h+var_210], rax; enum UACPROMPT_POLICY *
0x18003ff0a  mov     r9d, r12d; unsigned int
0x18003ff0d  lea     rax, [rbp+170h+var_E0]
0x18003ff14  mov     r8, r13; unsigned __int64
0x18003ff17  mov     [rsp+270h+var_218], rax; char *
0x18003ff1c  mov     rax, [rbp+170h+var_1A8]
0x18003ff20  mov     dword ptr [rsp+270h+var_220], esi; unsigned int
0x18003ff24  mov     [rsp+270h+var_228], rax; unsigned __int64 *
0x18003ff29  mov     eax, [rbp+170h+var_1E0]
0x18003ff2c  mov     [rsp+270h+var_230], rsi; unsigned __int16 *
0x18003ff31  mov     [rsp+270h+var_238], eax; unsigned int
0x18003ff35  mov     rax, [rbp+170h+var_178]
0x18003ff39  mov     [rsp+270h+var_240], rbx; struct _CONSENTUI_PARAM_HEADER *
0x18003ff3e  mov     [rsp+270h+var_248], rax; unsigned __int16 *
0x18003ff43  mov     eax, [rbp+170h+var_1F0]
0x18003ff46  mov     dword ptr [rsp+270h+var_250], eax; int
0x18003ff4a  call    ?AipGetTokenForService@@YAKKPEAX_KKHPEBGPEAU_CONSENTUI_PARAM_HEADER@@K2PEA_KKPEBDPEAW4UACPROMPT_POLICY@@PEAH@Z; AipGetTokenForService(ulong,void *,unsigned __int64,ulong,int,ushort const *,_CONSENTUI_PARAM_HEADER *,ulong,ushort const *,unsigned __int64 *,ulong,char const *,UACPROMPT_POLICY *,int *)
0x18003ff4f  mov     [rbp+170h+Reply], eax
0x18003ff52  mov     rcx, rbx; hMem
0x18003ff55  call    cs:__imp_LocalFree
0x18003ff5c  nop     dword ptr [rax+rax+00h]
0x18003ff61  lea     rcx, [rbp+170h+var_170]; lpPerformanceCount
0x18003ff65  call    cs:__imp_QueryPerformanceCounter
0x18003ff6c  nop     dword ptr [rax+rax+00h]
0x18003ff71  mov     rax, qword ptr [rbp+170h+var_170]
0x18003ff75  sub     rax, qword ptr [rbp+170h+PerformanceCount]
0x18003ff79  imul    rax, 3E8h
0x18003ff80  cqo
0x18003ff82  idiv    qword ptr [rbp+170h+Frequency]
0x18003ff86  mov     [rbp+170h+var_1A8], rax
0x18003ff8a  lea     rax, [rbp+170h+var_E0]
0x18003ff91  mov     [rbp+170h+var_1A0], rax
0x18003ff95  mov     eax, [rbp+170h+var_1E8]
0x18003ff98  mov     [rbp+170h+var_1E8], eax
0x18003ff9b  mov     eax, [rbp+170h+Reply]
0x18003ff9e  cmp     eax, 4C7h
0x18003ffa3  jnz     short loc_18003FFAA
0x18003ffa5  mov     [rbp+170h+var_1F0], esi
0x18003ffa8  jmp     short loc_18003FFB9
0x18003ffaa  test    eax, eax
0x18003ffac  jle     short loc_18003FFB6
0x18003ffae  movzx   eax, ax
0x18003ffb1  or      eax, 80070000h
0x18003ffb6  mov     [rbp+170h+var_1F0], eax
0x18003ffb9  lea     rax, [rbp+170h+var_1A0]
0x18003ffbd  mov     [rsp+270h+var_210], rax
0x18003ffc2  lea     r9, [rbp+170h+var_1B0]
0x18003ffc6  lea     rax, [rbp+170h+var_1A8]
0x18003ffca  mov     [rsp+270h+var_218], rax
0x18003ffcf  lea     r8, [rbp+170h+var_1D8]
0x18003ffd3  lea     rax, [rbp+170h+var_1E8]
0x18003ffd7  mov     [rsp+270h+var_220], rax
0x18003ffdc  lea     rdx, [rbp+170h+Reply]
0x18003ffe0  lea     rax, [rbp+170h+var_1D0]
0x18003ffe4  mov     [rsp+270h+var_228], rax
0x18003ffe9  lea     rcx, [rbp+170h+var_1F0]
0x18003ffed  lea     rax, [rbp+170h+arg_68]
0x18003fff4  mov     [rsp+270h+var_230], rax
0x18003fff9  lea     rax, [rbp+170h+var_1CC]
0x18003fffd  mov     qword ptr [rsp+270h+var_238], rax
0x180040002  lea     rax, [rbp+170h+var_1C8]
0x180040006  mov     [rsp+270h+var_240], rax
0x18004000b  lea     rax, [rbp+170h+var_1C0]
0x18004000f  mov     [rsp+270h+var_248], rax
0x180040014  lea     rax, [rbp+170h+var_1B8]
0x180040018  mov     [rsp+270h+var_250], rax
0x18004001d  call    ??$MSIElevation@JAEAKAEAKAEAPEBGAEAPEBGAEAPEBGAEAPEBGAEAW4_MSI_ACTION@@AEAKAEAHKAEA_JPEBD@LUATelemetry@@SAX$$QEAJAEAK1AEAPEBG222AEAW4_MSI_ACTION@@1AEAH$$QEAKAEA_J$$QEAPEBD@Z; LUATelemetry::MSIElevation<long,ulong &,ulong &,ushort const * &,ushort const * &,ushort const * &,ushort const * &,_MSI_ACTION &,ulong &,int &,ulong,__int64 &,char const *>(long &&,ulong &,ulong &,ushort const * &,ushort const * &,ushort const * &,ushort const * &,_MSI_ACTION &,ulong &,int &,ulong &&,__int64 &,char const * &&)
0x180040022  mov     rcx, [rbp+170h+pAsync]; pAsync
0x180040026  lea     rdx, [rbp+170h+Reply]; Reply
0x18004002a  call    cs:__imp_RpcAsyncCompleteCall
0x180040031  nop     dword ptr [rax+rax+00h]
0x180040036  mov     rcx, cs:WPP_GLOBAL_Control
0x18004003d  lea     rax, WPP_GLOBAL_Control
0x180040044  cmp     rcx, rax
0x180040047  jz      short loc_180040068
0x180040049  test    byte ptr [rcx+1Ch], 1
0x18004004d  jz      short loc_180040068
0x18004004f  mov     r9d, [rbp+170h+Reply]
0x180040053  lea     r8, WPP_aba5399977573c9264c162bacbfc9302_Traceguids
0x18004005a  mov     rcx, [rcx+10h]
0x18004005e  mov     edx, 0Fh
0x180040063  call    WPP_SF_D
0x180040068  lea     rcx, [rbp+170h+var_130]; this
0x18004006c  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180040071  mov     rcx, [rbp+170h+var_50]
0x180040078  xor     rcx, rsp; StackCookie
0x18004007b  call    __security_check_cookie
0x180040080  add     rsp, 238h
0x180040087  pop     r15
  ... truncated ...
```
