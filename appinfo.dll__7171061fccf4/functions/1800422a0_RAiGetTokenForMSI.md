# RAiGetTokenForMSI

- ea: `0x1800422a0`
- end: `0x180042747`
- name: `RAiGetTokenForMSI`
- size: `1191`
- prototype: `void __fastcall(struct _RPC_ASYNC_STATE *, void *, unsigned __int64, unsigned int, int, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned __int16 **, unsigned __int16 **, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18001aee4`
- `0x18001b25c`
- `0x18001e7bc`
- `0x18001e7c8`
- `0x180026f40`
- `0x180027668`
- `0x180028a80`
- `0x18002ad54`
- `0x18002b0c0`
- `0x180037250`
- `0x18003b3f0`
- `0x18003bb44`
- `0x180040d64`
- `0x180041418`
- `0x1800422a0`
- `0x180042750`
- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x1800426e3`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800426e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042628`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042628`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180042389`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180042389`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004237f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180042632`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004237f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180042632`

## string_xrefs

- `0x180042444`: `RAiGetTokenForMSI`
- `0x180042438`: `hwnd = %x dwRunLevel = %x fAdjustTokenSD = %x dwAction = %x dwTimeout = %x\n	lpDesktop = %ws\n	lpProductName = %ws\n	lpVersion = %ws\n	lpLanguage = %ws\n	lpManufacturer = %ws\n	lpPackagePath = %ws\n	lpPackageSource = %ws\n	lpCvStr = %s\n`

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
        unsigned __int16 *a11,
        unsigned __int16 *a12,
        unsigned __int16 *a13,
        unsigned int a14,
        unsigned __int16 **a15,
        unsigned __int16 **a16,
        unsigned int a17,
        unsigned __int64 *a18)
{
  char v20; // bl
  const wchar_t *v21; // rcx
  unsigned __int16 *v22; // rdx
  unsigned __int16 *v23; // r8
  unsigned __int16 *v24; // rax
  const wchar_t *v25; // r9
  const wchar_t *v26; // r15
  unsigned __int16 *v27; // rdi
  int v28; // edx
  int v29; // r8d
  void *v30; // rax
  volatile signed __int64 *v31; // rbx
  unsigned int v32; // r15d
  signed int v33; // eax
  struct _CONSENTUI_PARAM_HEADER *v34; // rbx
  void *v35; // rdx
  unsigned __int8 v36; // cl
  unsigned int v37; // ebx
  LONGLONG v38; // r15
  __int64 v39; // rcx
  LUATelemetry *v40; // rcx
  unsigned __int16 *v41; // [rsp+38h] [rbp-C8h]
  signed int Reply; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v43; // [rsp+84h] [rbp-7Ch]
  unsigned int v44; // [rsp+88h] [rbp-78h] BYREF
  int v45; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned __int16 *v46; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v47; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v48; // [rsp+A0h] [rbp-60h]
  unsigned __int16 *v49; // [rsp+A8h] [rbp-58h]
  HLOCAL hMem; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v51; // [rsp+B8h] [rbp-48h]
  LARGE_INTEGER v52; // [rsp+C0h] [rbp-40h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+C8h] [rbp-38h] BYREF
  LARGE_INTEGER Frequency; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v55; // [rsp+D8h] [rbp-28h]
  unsigned __int16 *v56; // [rsp+E0h] [rbp-20h]
  const wchar_t *v57; // [rsp+E8h] [rbp-18h]
  unsigned __int16 *v58; // [rsp+F0h] [rbp-10h]
  unsigned __int16 *v59; // [rsp+F8h] [rbp-8h]
  unsigned __int16 *v60; // [rsp+100h] [rbp+0h]
  const wchar_t *v61; // [rsp+108h] [rbp+8h]
  unsigned __int16 **v62; // [rsp+110h] [rbp+10h]
  unsigned __int16 **v63; // [rsp+118h] [rbp+18h]
  unsigned __int64 *v64; // [rsp+120h] [rbp+20h]
  void *v65; // [rsp+128h] [rbp+28h]
  PRPC_ASYNC_STATE pAsync; // [rsp+130h] [rbp+30h]
  char v67[80]; // [rsp+140h] [rbp+40h] BYREF
  char v68[144]; // [rsp+190h] [rbp+90h] BYREF

  v20 = a17;
  v51 = a6;
  v49 = a10;
  v46 = a11;
  v48 = a12;
  v47 = a13;
  v63 = a15;
  v62 = a16;
  v64 = a18;
  pAsync = a1;
  Reply = 0;
  hMem = 0;
  v45 = 0;
  v44 = 0;
  Frequency.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  v52.QuadPart = 0;
  v65 = a2;
  v56 = a8;
  v55 = a9;
  v43 = a17;
  QueryPerformanceCounter(&PerformanceCount);
  QueryPerformanceFrequency(&Frequency);
  memset_0(v68, 0, 0x81u);
  v21 = a13;
  if ( !a13 )
    v21 = L"NULL";
  v57 = v21;
  v22 = v48;
  if ( !v48 )
    v22 = L"NULL";
  v23 = v46;
  v58 = v22;
  v24 = v49;
  if ( !v46 )
    v23 = L"NULL";
  v25 = a9;
  v59 = v23;
  if ( !v49 )
    v24 = L"NULL";
  v26 = a8;
  v60 = v24;
  if ( !a9 )
    v25 = L"NULL";
  v27 = v51;
  v61 = v25;
  if ( !a8 )
    v26 = L"NULL";
  if ( !v51 )
    v27 = L"NULL";
  LODWORD(v41) = a17;
  LUATelemetry::WatchCurrentThread(
    v67,
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
    a4,
    a5,
    a7,
    v41,
    v27,
    v26,
    v25,
    v24);
  if ( g_pMSIElevationActivityTelemetryRateLimiter
    && (unsigned int)RateLimiter::RequestPermission(g_pMSIElevationActivityTelemetryRateLimiter) )
  {
    v30 = operator new(0x90u);
    if ( v30 )
      v31 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v30);
    else
      v31 = 0;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v31,
      _InterlockedExchangeAdd64(v31 + 17, 0),
      v68);
    if ( v31 )
      operator delete((void *)v31);
    v20 = v43;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_DDDDDSSSSSSSs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v28,
      v29,
      a3,
      a4,
      a5,
      a7,
      v20,
      (__int64)v27,
      (__int64)v26,
      (__int64)v61,
      (__int64)v60,
      (__int64)v59,
      (__int64)v58,
      (__int64)v57,
      (__int64)v68);
  v32 = AiLogPerfTrackEvent(&AppInfo_PerfTrack_Elevation_MSI_Start);
  v33 = AiBuildMSIParams(
          a7,
          v56,
          v55,
          v49,
          v46,
          v48,
          v47,
          a14,
          (const unsigned __int16 **)v63,
          (const unsigned __int16 **)v62,
          (struct _CONSENTUI_PARAM_HEADER **)&hMem);
  v34 = (struct _CONSENTUI_PARAM_HEADER *)hMem;
  Reply = v33;
  if ( !v33 )
  {
    v35 = v65;
    *((_DWORD *)hMem + 13) = v32;
    Reply = AipGetTokenForService(
              1u,
              v35,
              a3,
              a4,
              a5,
              v51,
              v34,
              v43,
              0,
              v64,
              0,
              v68,
              (enum UACPROMPT_POLICY *)&v44,
              &v45);
  }
  LocalFree(v34);
  QueryPerformanceCounter(&v52);
  v37 = Reply;
  v38 = 1000 * (v52.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart;
  if ( Reply == 1223 )
  {
    v37 = 0;
  }
  else if ( Reply > 0 )
  {
    v37 = (unsigned __int16)Reply | 0x80070000;
  }
  if ( LUATelemetry::IsEnabled(v36, 1000 * (v52.QuadPart - PerformanceCount.QuadPart) % Frequency.QuadPart) )
  {
    wil::details::static_lazy<LUATelemetry>::get(v39, _lambda_8fd1dd6eff698f29c42c633fb94303b5_::_lambda_invoker_cdecl_);
    LUATelemetry::MSIElevation_(v40, v37, Reply, a4, v47, v56, v55, v46, a7, a14, v45, v44, v38, v68);
  }
  RpcAsyncCompleteCall(pAsync, &Reply);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      WPP_aba5399977573c9264c162bacbfc9302_Traceguids,
      (unsigned int)Reply);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v67);
}

```

## disassembly

```asm
0x1800422a0  push    rbp
0x1800422a2  push    rbx
0x1800422a3  push    rsi
0x1800422a4  push    rdi
0x1800422a5  push    r12
0x1800422a7  push    r13
0x1800422a9  push    r14
0x1800422ab  push    r15
0x1800422ad  lea     rbp, [rsp-138h]
0x1800422b5  sub     rsp, 238h
0x1800422bc  mov     rax, cs:__security_cookie
0x1800422c3  xor     rax, rsp
0x1800422c6  mov     [rbp+170h+var_50], rax
0x1800422cd  mov     rax, [rbp+170h+arg_28]
0x1800422d4  mov     esi, r9d
0x1800422d7  mov     rdi, [rbp+170h+arg_38]
0x1800422de  mov     r12, r8
0x1800422e1  mov     r15, [rbp+170h+arg_40]
0x1800422e8  mov     ebx, [rbp+170h+arg_80]
0x1800422ee  mov     r13d, [rbp+170h+arg_20]
0x1800422f5  mov     r14d, [rbp+170h+arg_30]
0x1800422fc  mov     [rbp+170h+var_1B8], rax
0x180042300  mov     rax, [rbp+170h+arg_48]
0x180042307  mov     [rbp+170h+var_1C8], rax
0x18004230b  mov     rax, [rbp+170h+arg_50]
0x180042312  mov     [rbp+170h+var_1E0], rax
0x180042316  mov     rax, [rbp+170h+arg_58]
0x18004231d  mov     [rbp+170h+var_1D0], rax
0x180042321  mov     rax, [rbp+170h+arg_60]
0x180042328  mov     [rbp+170h+var_1D8], rax
0x18004232c  mov     rax, [rbp+170h+arg_70]
0x180042333  mov     [rbp+170h+var_158], rax
0x180042337  mov     rax, [rbp+170h+arg_78]
0x18004233e  mov     [rbp+170h+var_160], rax
0x180042342  mov     rax, [rbp+170h+arg_88]
0x180042349  mov     [rbp+170h+var_150], rax
0x18004234d  xor     eax, eax
0x18004234f  mov     [rbp+170h+pAsync], rcx
0x180042353  lea     rcx, [rbp+170h+PerformanceCount]; lpPerformanceCount
0x180042357  mov     [rbp+170h+Reply], eax
0x18004235a  mov     [rbp+170h+hMem], rax
0x18004235e  mov     [rbp+170h+var_1E4], eax
0x180042361  mov     [rbp+170h+var_1E8], eax
0x180042364  mov     qword ptr [rbp+170h+Frequency], rax
0x180042368  mov     qword ptr [rbp+170h+PerformanceCount], rax
0x18004236c  mov     qword ptr [rbp+170h+var_1B0], rax
0x180042370  mov     [rbp+170h+var_148], rdx
0x180042374  mov     [rbp+170h+var_190], rdi
0x180042378  mov     [rbp+170h+var_198], r15
0x18004237c  mov     [rbp+170h+var_1EC], ebx
0x18004237f  call    cs:__imp_QueryPerformanceCounter
0x180042385  lea     rcx, [rbp+170h+Frequency]; lpFrequency
0x180042389  call    cs:__imp_QueryPerformanceFrequency
0x18004238f  xor     edx, edx; Val
0x180042391  lea     rcx, [rbp+170h+var_E0]; void *
0x180042398  mov     r8d, 81h; Size
0x18004239e  call    memset_0
0x1800423a3  mov     rax, [rbp+170h+var_1D8]
0x1800423a7  lea     r11, aNull_0; "NULL"
0x1800423ae  mov     r9, [rbp+170h+var_1C8]
0x1800423b2  test    rax, rax
0x1800423b5  mov     r10, [rbp+170h+var_1B8]
0x1800423b9  mov     rcx, rax
0x1800423bc  mov     rax, [rbp+170h+var_1D0]
0x1800423c0  cmovz   rcx, r11
0x1800423c4  test    rax, rax
0x1800423c7  mov     [rbp+170h+var_188], rcx
0x1800423cb  mov     rdx, rax
0x1800423ce  mov     rax, [rbp+170h+var_1E0]
0x1800423d2  cmovz   rdx, r11
0x1800423d6  mov     r8, rax
0x1800423d9  test    rax, rax
0x1800423dc  mov     [rbp+170h+var_180], rdx
0x1800423e0  mov     rax, r9
0x1800423e3  cmovz   r8, r11
0x1800423e7  test    r9, r9
0x1800423ea  mov     r9, r15
0x1800423ed  mov     [rbp+170h+var_178], r8
0x1800423f1  cmovz   rax, r11
0x1800423f5  test    r15, r15
0x1800423f8  mov     r15, rdi
0x1800423fb  mov     [rbp+170h+var_170], rax
0x1800423ff  cmovz   r9, r11
0x180042403  test    rdi, rdi
0x180042406  mov     rdi, r10
0x180042409  mov     [rbp+170h+var_168], r9
0x18004240d  cmovz   r15, r11
0x180042411  test    r10, r10
0x180042414  lea     r10, [rbp+170h+var_E0]
0x18004241b  mov     [rsp+270h+var_1F8], r10
0x180042420  cmovz   rdi, r11
0x180042424  mov     [rsp+270h+var_200], rcx
0x180042429  mov     [rsp+270h+var_208], rdx
0x18004242e  mov     [rsp+270h+var_210], r8
0x180042433  mov     [rsp+270h+var_218], rax
0x180042438  lea     r8, aHwndXDwrunleve; "hwnd = %x dwRunLevel = %x fAdjustTokenS"...
0x18004243f  mov     [rsp+270h+var_220], r9
0x180042444  lea     rdx, aRaigettokenfor; "RAiGetTokenForMSI"
0x18004244b  mov     [rsp+270h+var_228], r15
0x180042450  lea     rcx, [rbp+170h+var_130]
0x180042454  mov     [rsp+270h+var_230], rdi
0x180042459  mov     r9d, r12d
0x18004245c  mov     dword ptr [rsp+270h+var_238], ebx
0x180042460  mov     dword ptr [rsp+270h+var_240], r14d
0x180042465  mov     dword ptr [rsp+270h+var_248], r13d
0x18004246a  mov     dword ptr [rsp+270h+var_250], esi
0x18004246e  call    ?WatchCurrentThread@LUATelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; LUATelemetry::WatchCurrentThread(char const *,char const *,...)
0x180042473  mov     rcx, cs:?g_pMSIElevationActivityTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; this
0x18004247a  test    rcx, rcx
0x18004247d  jz      short loc_1800424D0
0x18004247f  call    ?RequestPermission@RateLimiter@@QEAAHXZ; RateLimiter::RequestPermission(void)
0x180042484  test    eax, eax
0x180042486  jz      short loc_1800424D0
0x180042488  mov     ecx, 90h; Size
0x18004248d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180042492  test    rax, rax
0x180042495  jz      short loc_1800424A4
0x180042497  mov     rcx, rax
0x18004249a  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18004249f  mov     rbx, rax
0x1800424a2  jmp     short loc_1800424A6
0x1800424a4  xor     ebx, ebx
0x1800424a6  xor     edx, edx
0x1800424a8  lock xadd [rbx+88h], rdx; unsigned __int64
0x1800424b1  lea     r8, [rbp+170h+var_E0]; char *
0x1800424b8  mov     rcx, rbx; this
0x1800424bb  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800424c0  test    rbx, rbx
0x1800424c3  jz      short loc_1800424CD
0x1800424c5  mov     rcx, rbx; Block
0x1800424c8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800424cd  mov     ebx, [rbp+170h+var_1EC]
0x1800424d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800424d7  lea     rax, WPP_GLOBAL_Control
0x1800424de  cmp     rcx, rax
0x1800424e1  jz      short loc_18004254A
0x1800424e3  test    byte ptr [rcx+1Ch], 1
0x1800424e7  jz      short loc_18004254A
0x1800424e9  mov     rcx, [rcx+10h]
0x1800424ed  lea     rax, [rbp+170h+var_E0]
0x1800424f4  mov     [rsp+270h+var_1F8], rax
0x1800424f9  mov     r9d, r12d
0x1800424fc  mov     rax, [rbp+170h+var_188]
0x180042500  mov     [rsp+270h+var_200], rax
0x180042505  mov     rax, [rbp+170h+var_180]
0x180042509  mov     [rsp+270h+var_208], rax
0x18004250e  mov     rax, [rbp+170h+var_178]
0x180042512  mov     [rsp+270h+var_210], rax
0x180042517  mov     rax, [rbp+170h+var_170]
0x18004251b  mov     [rsp+270h+var_218], rax
0x180042520  mov     rax, [rbp+170h+var_168]
0x180042524  mov     [rsp+270h+var_220], rax
0x180042529  mov     [rsp+270h+var_228], r15
0x18004252e  mov     [rsp+270h+var_230], rdi
0x180042533  mov     dword ptr [rsp+270h+var_238], ebx
0x180042537  mov     dword ptr [rsp+270h+var_240], r14d
0x18004253c  mov     dword ptr [rsp+270h+var_248], r13d
0x180042541  mov     dword ptr [rsp+270h+var_250], esi
0x180042545  call    WPP_SF_DDDDDSSSSSSSs
0x18004254a  lea     rcx, AppInfo_PerfTrack_Elevation_MSI_Start; struct _EVENT_DESCRIPTOR *
0x180042551  call    ?AiLogPerfTrackEvent@@YAKPEBU_EVENT_DESCRIPTOR@@@Z; AiLogPerfTrackEvent(_EVENT_DESCRIPTOR const *)
0x180042556  mov     edi, [rbp+170h+arg_68]
0x18004255c  mov     r15d, eax
0x18004255f  mov     r9, [rbp+170h+var_1C8]; unsigned __int16 *
0x180042563  lea     rax, [rbp+170h+hMem]
0x180042567  mov     r8, [rbp+170h+var_198]; unsigned __int16 *
0x18004256b  mov     ecx, r14d; unsigned int
0x18004256e  mov     rdx, [rbp+170h+var_190]; unsigned __int16 *
0x180042572  mov     [rsp+270h+var_220], rax; struct _CONSENTUI_PARAM_HEADER **
0x180042577  mov     rax, [rbp+170h+var_160]
0x18004257b  mov     [rsp+270h+var_228], rax; unsigned __int16 **
0x180042580  mov     rax, [rbp+170h+var_158]
0x180042584  mov     [rsp+270h+var_230], rax; unsigned __int16 **
0x180042589  mov     rax, [rbp+170h+var_1D8]
0x18004258d  mov     dword ptr [rsp+270h+var_238], edi; unsigned int
0x180042591  mov     [rsp+270h+var_240], rax; unsigned __int16 *
0x180042596  mov     rax, [rbp+170h+var_1D0]
0x18004259a  mov     [rsp+270h+var_248], rax; unsigned __int16 *
0x18004259f  mov     rax, [rbp+170h+var_1E0]
0x1800425a3  mov     [rsp+270h+var_250], rax; unsigned __int16 *
0x1800425a8  call    ?AiBuildMSIParams@@YAKKPEBG00000KPEAPEBG1PEAPEAU_CONSENTUI_PARAM_HEADER@@@Z; AiBuildMSIParams(ulong,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const * *,ushort const * *,_CONSENTUI_PARAM_HEADER * *)
0x1800425ad  mov     rbx, [rbp+170h+hMem]
0x1800425b1  mov     [rbp+170h+Reply], eax
0x1800425b4  test    eax, eax
0x1800425b6  jnz     short loc_180042625
0x1800425b8  mov     rdx, [rbp+170h+var_148]; void *
0x1800425bc  lea     rax, [rbp+170h+var_1E4]
0x1800425c0  mov     [rsp+270h+var_208], rax; int *
0x1800425c5  mov     r9d, esi; unsigned int
0x1800425c8  lea     rax, [rbp+170h+var_1E8]
0x1800425cc  mov     [rbx+34h], r15d
0x1800425d0  mov     [rsp+270h+var_210], rax; enum UACPROMPT_POLICY *
0x1800425d5  mov     r8, r12; unsigned __int64
0x1800425d8  lea     rax, [rbp+170h+var_E0]
0x1800425df  mov     ecx, 1; unsigned int
0x1800425e4  mov     [rsp+270h+var_218], rax; char *
0x1800425e9  mov     rax, [rbp+170h+var_150]
0x1800425ed  mov     dword ptr [rsp+270h+var_220], 0; unsigned int
0x1800425f5  mov     [rsp+270h+var_228], rax; unsigned __int64 *
0x1800425fa  mov     eax, [rbp+170h+var_1EC]
0x1800425fd  mov     [rsp+270h+var_230], 0; unsigned __int16 *
0x180042606  mov     dword ptr [rsp+270h+var_238], eax; unsigned int
0x18004260a  mov     rax, [rbp+170h+var_1B8]
0x18004260e  mov     [rsp+270h+var_240], rbx; struct _CONSENTUI_PARAM_HEADER *
0x180042613  mov     [rsp+270h+var_248], rax; unsigned __int16 *
0x180042618  mov     dword ptr [rsp+270h+var_250], r13d; int
0x18004261d  call    ?AipGetTokenForService@@YAKKPEAX_KKHPEBGPEAU_CONSENTUI_PARAM_HEADER@@K2PEA_KKPEBDPEAW4UACPROMPT_POLICY@@PEAH@Z; AipGetTokenForService(ulong,void *,unsigned __int64,ulong,int,ushort const *,_CONSENTUI_PARAM_HEADER *,ulong,ushort const *,unsigned __int64 *,ulong,char const *,UACPROMPT_POLICY *,int *)
0x180042622  mov     [rbp+170h+Reply], eax
0x180042625  mov     rcx, rbx; hMem
0x180042628  call    cs:__imp_LocalFree
0x18004262e  lea     rcx, [rbp+170h+var_1B0]; lpPerformanceCount
0x180042632  call    cs:__imp_QueryPerformanceCounter
0x180042638  mov     rax, qword ptr [rbp+170h+var_1B0]
0x18004263c  sub     rax, qword ptr [rbp+170h+PerformanceCount]
0x180042640  mov     ebx, [rbp+170h+Reply]
0x180042643  imul    rax, 3E8h
0x18004264a  cqo; unsigned __int64
0x18004264c  idiv    qword ptr [rbp+170h+Frequency]
0x180042650  mov     r15, rax
0x180042653  cmp     ebx, 4C7h
0x180042659  jnz     short loc_18004265F
0x18004265b  xor     ebx, ebx
0x18004265d  jmp     short loc_18004266C
0x18004265f  test    ebx, ebx
0x180042661  jle     short loc_18004266C
0x180042663  movzx   ebx, bx
0x180042666  or      ebx, 80070000h
0x18004266c  call    ?IsEnabled@LUATelemetry@@SA_NE_K@Z; LUATelemetry::IsEnabled(uchar,unsigned __int64)
0x180042671  test    al, al
0x180042673  jz      short loc_1800426DB
0x180042675  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_8fd1dd6eff698f29c42c633fb94303b5_@@CA@XZ; _lambda_8fd1dd6eff698f29c42c633fb94303b5_::_lambda_invoker_cdecl_(void)
0x18004267c  call    ?get@?$static_lazy@VLUATelemetry@@@details@wil@@QEAAPEAVLUATelemetry@@P6AXXZ@Z; wil::details::static_lazy<LUATelemetry>::get(void (*)(void))
0x180042681  mov     r8d, [rbp+170h+Reply]; unsigned int
0x180042685  lea     rax, [rbp+170h+var_E0]
0x18004268c  mov     [rsp+270h+var_208], rax; char *
0x180042691  mov     r9d, esi; unsigned int
0x180042694  mov     eax, [rbp+170h+var_1E8]
0x180042697  mov     edx, ebx; int
0x180042699  mov     [rsp+270h+var_210], r15; __int64
0x18004269e  mov     dword ptr [rsp+270h+var_218], eax; unsigned int
0x1800426a2  mov     eax, [rbp+170h+var_1E4]
0x1800426a5  mov     dword ptr [rsp+270h+var_220], eax; int
0x1800426a9  mov     rax, [rbp+170h+var_1E0]
0x1800426ad  mov     dword ptr [rsp+270h+var_228], edi; unsigned int
0x1800426b1  mov     dword ptr [rsp+270h+var_230], r14d; unsigned int
0x1800426b6  mov     [rsp+270h+var_238], rax; unsigned __int16 *
0x1800426bb  mov     rax, [rbp+170h+var_198]
0x1800426bf  mov     [rsp+270h+var_240], rax; unsigned __int16 *
0x1800426c4  mov     rax, [rbp+170h+var_190]
0x1800426c8  mov     [rsp+270h+var_248], rax; unsigned __int16 *
0x1800426cd  mov     rax, [rbp+170h+var_1D8]
0x1800426d1  mov     [rsp+270h+var_250], rax; unsigned __int16 *
0x1800426d6  call    ?MSIElevation_@LUATelemetry@@QEAAXJKKPEBG000KKHK_JPEBD@Z; LUATelemetry::MSIElevation_(long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong,int,ulong,__int64,char const *)
0x1800426db  mov     rcx, [rbp+170h+pAsync]; pAsync
0x1800426df  lea     rdx, [rbp+170h+Reply]; Reply
0x1800426e3  call    cs:__imp_RpcAsyncCompleteCall
0x1800426e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800426f0  lea     rax, WPP_GLOBAL_Control
0x1800426f7  cmp     rcx, rax
0x1800426fa  jz      short loc_18004271B
0x1800426fc  test    byte ptr [rcx+1Ch], 1
0x180042700  jz      short loc_18004271B
0x180042702  mov     r9d, [rbp+170h+Reply]
0x180042706  lea     r8, WPP_aba5399977573c9264c162bacbfc9302_Traceguids
0x18004270d  mov     rcx, [rcx+10h]
0x180042711  mov     edx, 0Fh
0x180042716  call    WPP_SF_D
0x18004271b  lea     rcx, [rbp+170h+var_130]; this
0x18004271f  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180042724  mov     rcx, [rbp+170h+var_50]
0x18004272b  xor     rcx, rsp; StackCookie
0x18004272e  call    __security_check_cookie
0x180042733  add     rsp, 238h
0x18004273a  pop     r15
0x18004273c  pop     r14
0x18004273e  pop     r13
0x180042740  pop     r12
0x180042742  pop     rdi
0x180042743  pop     rsi
0x180042744  pop     rbx
0x180042745  pop     rbp
0x180042746  retn
```
