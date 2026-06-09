# RAiGetTokenForMSI

- ea: `0x18003da80`
- end: `0x18003df85`
- name: `RAiGetTokenForMSI`
- size: `1285`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18001b0c4`
- `0x18001b0d0`
- `0x180024db0`
- `0x180025724`
- `0x180025d50`
- `0x180028424`
- `0x180028864`
- `0x180037fd0`
- `0x180038d40`
- `0x18003c38c`
- `0x18003c4c4`
- `0x18003da80`
- `0x18003df8c`
- `0x1800402e4`
- `0x18004292a`
- `0x180042950`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003df1a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003df1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003de45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003de45`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003db67`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003de55`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003db67`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003de55`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003db77`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18003db77`

## string_xrefs

- `0x18003dc20`: `hwnd = %x dwRunLevel = %x fAdjustTokenSD = %x dwAction = %x dwTimeout = %x\n	lpDesktop = %ws\n	lpProductName = %ws\n	lpVersion = %ws\n	lpLanguage = %ws\n	lpManufacturer = %ws\n	lpPackagePath = %ws\n	lpPackageSource = %ws\n	lpCvStr = %s\n`
- `0x18003dc2c`: `RAiGetTokenForMSI`

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
  unsigned __int16 *v26; // r10
  unsigned __int16 *v27; // r11
  const unsigned __int16 *v28; // rcx
  const unsigned __int16 *v29; // rax
  void *v30; // rax
  volatile signed __int64 *v31; // rbx
  const unsigned __int16 *v32; // rdx
  const unsigned __int16 *v33; // rcx
  const unsigned __int16 *v34; // rax
  unsigned int v35; // edi
  unsigned int v36; // eax
  struct _CONSENTUI_PARAM_HEADER *v37; // rbx
  void *v38; // rdx
  unsigned int v39; // eax
  unsigned int v40[2]; // [rsp+38h] [rbp-C8h]
  int v41; // [rsp+80h] [rbp-80h] BYREF
  int Reply; // [rsp+84h] [rbp-7Ch] BYREF
  int v43; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v44; // [rsp+8Ch] [rbp-74h]
  unsigned int v45; // [rsp+90h] [rbp-70h]
  unsigned int v46; // [rsp+98h] [rbp-68h] BYREF
  int v47; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v48; // [rsp+A4h] [rbp-5Ch] BYREF
  wchar_t *v49; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v50; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v51; // [rsp+B8h] [rbp-48h] BYREF
  wchar_t *v52; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 *v53; // [rsp+C8h] [rbp-38h] BYREF
  void *v54; // [rsp+D0h] [rbp-30h] BYREF
  const unsigned __int16 *v55; // [rsp+D8h] [rbp-28h]
  wchar_t *v56; // [rsp+E0h] [rbp-20h]
  unsigned __int16 *v57; // [rsp+E8h] [rbp-18h]
  HLOCAL hMem; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 *v59; // [rsp+F8h] [rbp-8h]
  LARGE_INTEGER v60; // [rsp+100h] [rbp+0h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+108h] [rbp+8h] BYREF
  LARGE_INTEGER Frequency; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 *v63; // [rsp+118h] [rbp+18h]
  unsigned __int16 *v64; // [rsp+120h] [rbp+20h]
  unsigned __int16 **v65; // [rsp+128h] [rbp+28h]
  unsigned __int16 **v66; // [rsp+130h] [rbp+30h]
  PRPC_ASYNC_STATE pAsync; // [rsp+138h] [rbp+38h]
  char v68[80]; // [rsp+140h] [rbp+40h] BYREF
  char v69[144]; // [rsp+190h] [rbp+90h] BYREF

  v18 = a4;
  v20 = a8;
  v21 = a9;
  v22 = a11;
  v23 = a13;
  v59 = a6;
  v56 = a12;
  v41 = a5;
  v66 = a15;
  v65 = a16;
  v45 = a17;
  pAsync = a1;
  v53 = a18;
  v44 = a7;
  v48 = a7;
  hMem = 0;
  v47 = 0;
  v43 = 0;
  Frequency.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  v60.QuadPart = 0;
  v54 = a2;
  v57 = a10;
  v46 = a4;
  v51 = a8;
  v50 = a9;
  v49 = a11;
  v52 = a13;
  QueryPerformanceCounter(&PerformanceCount);
  QueryPerformanceFrequency(&Frequency);
  memset_0(v69, 0, 0x81u);
  v24 = L"NULL";
  v25 = a12;
  if ( !a12 )
    v25 = L"NULL";
  v26 = v57;
  v55 = v25;
  if ( !v57 )
    v26 = L"NULL";
  v27 = v59;
  v63 = v26;
  if ( !v59 )
    v27 = L"NULL";
  v64 = v27;
  v28 = a9;
  v29 = a8;
  if ( !a9 )
    v28 = L"NULL";
  if ( !a8 )
    v29 = L"NULL";
  v40[0] = v45;
  LUATelemetry::WatchCurrentThread(
    v68,
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
    v41,
    v44,
    *(_QWORD *)v40,
    v27,
    v29,
    v28,
    v26);
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
      v69);
    if ( v31 )
      operator delete((void *)v31);
    v23 = v52;
    v22 = v49;
    v21 = v50;
    v20 = v51;
    v18 = v46;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v32 = L"NULL";
    if ( v23 )
      v32 = v23;
    v33 = L"NULL";
    v34 = L"NULL";
    if ( v22 )
      v33 = v22;
    if ( v21 )
      v34 = v21;
    if ( v20 )
      v24 = v20;
    WPP_SF_DDDDDSSSSSSSs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)v55,
      (_DWORD)WPP_GLOBAL_Control,
      a3,
      v18,
      v41,
      v44,
      v45,
      (__int64)v64,
      (__int64)v24,
      (__int64)v34,
      (__int64)v63,
      (__int64)v33,
      (__int64)v55,
      (__int64)v32,
      (__int64)v69);
  }
  v35 = AiLogPerfTrackEvent(&AppInfo_PerfTrack_Elevation_MSI_Start);
  v36 = AiBuildMSIParams(
          v44,
          v20,
          v21,
          v57,
          v22,
          v56,
          v23,
          a14,
          (const unsigned __int16 **)v66,
          (const unsigned __int16 **)v65,
          (struct _CONSENTUI_PARAM_HEADER **)&hMem);
  v37 = (struct _CONSENTUI_PARAM_HEADER *)hMem;
  Reply = v36;
  if ( !v36 )
  {
    v38 = v54;
    *((_DWORD *)hMem + 13) = v35;
    Reply = AipGetTokenForService(
              1u,
              v38,
              a3,
              v18,
              v41,
              v59,
              v37,
              v45,
              0,
              v53,
              0,
              v69,
              (enum UACPROMPT_POLICY *)&v43,
              &v47);
  }
  LocalFree(v37);
  QueryPerformanceCounter(&v60);
  v53 = (unsigned __int64 *)(1000 * (v60.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart);
  v54 = v69;
  v39 = Reply;
  if ( Reply == 1223 )
  {
    v41 = 0;
  }
  else
  {
    if ( Reply > 0 )
      v39 = (unsigned __int16)Reply | 0x80070000;
    v41 = v39;
  }
  LUATelemetry::MSIElevation<long,unsigned long &,unsigned long &,unsigned short const * &,unsigned short const * &,unsigned short const * &,unsigned short const * &,enum _MSI_ACTION &,unsigned long &,int &,unsigned long,__int64 &,char const *>(
    (unsigned int)&v41,
    (unsigned int)&Reply,
    (unsigned int)&v46,
    (unsigned int)&v52,
    (__int64)&v51,
    (__int64)&v50,
    (__int64)&v49,
    (__int64)&v48,
    (__int64)&a14,
    (__int64)&v47,
    (__int64)&v43,
    (__int64)&v53,
    (__int64)&v54);
  RpcAsyncCompleteCall(pAsync, &Reply);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      &WPP_aba5399977573c9264c162bacbfc9302_Traceguids,
      (unsigned int)Reply);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v68);
}

```

## disassembly

```asm
0x18003da80  push    rbp
0x18003da82  push    rbx
0x18003da83  push    rsi
0x18003da84  push    rdi
0x18003da85  push    r12
0x18003da87  push    r13
0x18003da89  push    r14
0x18003da8b  push    r15
0x18003da8d  lea     rbp, [rsp-138h]
0x18003da95  sub     rsp, 238h
0x18003da9c  mov     rax, cs:__security_cookie
0x18003daa3  xor     rax, rsp
0x18003daa6  mov     [rbp+170h+var_50], rax
0x18003daad  mov     rax, [rbp+170h+arg_28]
0x18003dab4  mov     r12d, r9d
0x18003dab7  mov     r9, [rbp+170h+arg_48]
0x18003dabe  mov     r13, r8
0x18003dac1  mov     rbx, [rbp+170h+arg_38]
0x18003dac8  mov     rsi, [rbp+170h+arg_40]
0x18003dacf  mov     r14, [rbp+170h+arg_50]
0x18003dad6  mov     r15, [rbp+170h+arg_60]
0x18003dadd  mov     [rbp+170h+var_178], rax
0x18003dae1  mov     rax, [rbp+170h+arg_58]
0x18003dae8  mov     [rbp+170h+var_190], rax
0x18003daec  mov     eax, [rbp+170h+arg_20]
0x18003daf2  mov     [rbp+170h+var_1F0], eax
0x18003daf5  mov     rax, [rbp+170h+arg_70]
0x18003dafc  mov     [rbp+170h+var_140], rax
0x18003db00  mov     rax, [rbp+170h+arg_78]
0x18003db07  mov     [rbp+170h+var_148], rax
0x18003db0b  mov     eax, [rbp+170h+arg_80]
0x18003db11  mov     [rbp+170h+var_1E0], eax
0x18003db14  mov     rax, [rbp+170h+arg_88]
0x18003db1b  mov     [rbp+170h+pAsync], rcx
0x18003db1f  mov     ecx, [rbp+170h+arg_30]
0x18003db25  mov     [rbp+170h+var_1A8], rax
0x18003db29  xor     eax, eax
0x18003db2b  mov     [rbp+170h+var_1E4], ecx
0x18003db2e  mov     [rbp+170h+var_1CC], ecx
0x18003db31  lea     rcx, [rbp+170h+PerformanceCount]; lpPerformanceCount
0x18003db35  mov     [rbp+170h+hMem], rax
0x18003db39  mov     [rbp+170h+var_1D0], eax
0x18003db3c  mov     [rbp+170h+var_1E8], eax
0x18003db3f  mov     qword ptr [rbp+170h+Frequency], rax
0x18003db43  mov     qword ptr [rbp+170h+PerformanceCount], rax
0x18003db47  mov     qword ptr [rbp+170h+var_170], rax
0x18003db4b  mov     [rbp+170h+var_1A0], rdx
0x18003db4f  mov     [rbp+170h+var_188], r9
0x18003db53  mov     [rbp+170h+var_1D8], r12d
0x18003db57  mov     [rbp+170h+var_1B8], rbx
0x18003db5b  mov     [rbp+170h+var_1C0], rsi
0x18003db5f  mov     [rbp+170h+var_1C8], r14
0x18003db63  mov     [rbp+170h+var_1B0], r15
0x18003db67  call    cs:__imp_QueryPerformanceCounter
0x18003db6e  nop     dword ptr [rax+rax+00h]
0x18003db73  lea     rcx, [rbp+170h+Frequency]; lpFrequency
0x18003db77  call    cs:__imp_QueryPerformanceFrequency
0x18003db7e  nop     dword ptr [rax+rax+00h]
0x18003db83  xor     edx, edx; Val
0x18003db85  lea     rcx, [rbp+170h+var_E0]; void *
0x18003db8c  mov     r8d, 81h; Size
0x18003db92  call    memset_0
0x18003db97  mov     rax, [rbp+170h+var_190]
0x18003db9b  lea     rdi, aNull_0; "NULL"
0x18003dba2  test    rax, rax
0x18003dba5  mov     r9, rax
0x18003dba8  mov     rax, [rbp+170h+var_188]
0x18003dbac  mov     r8, r15
0x18003dbaf  cmovz   r9, rdi
0x18003dbb3  mov     r10, rax
0x18003dbb6  test    rax, rax
0x18003dbb9  mov     [rbp+170h+var_198], r9
0x18003dbbd  mov     rax, [rbp+170h+var_178]
0x18003dbc1  lea     r9, [rbp+170h+var_E0]
0x18003dbc8  cmovz   r10, rdi
0x18003dbcc  mov     [rsp+270h+var_1F8], r9
0x18003dbd1  mov     r9, [rbp+170h+var_198]
0x18003dbd5  test    rax, rax
0x18003dbd8  mov     r11, rax
0x18003dbdb  mov     [rbp+170h+var_158], r10
0x18003dbdf  cmovz   r11, rdi
0x18003dbe3  mov     rdx, r14
0x18003dbe6  test    r15, r15
0x18003dbe9  mov     [rbp+170h+var_150], r11
0x18003dbed  mov     rcx, rsi
0x18003dbf0  mov     rax, rbx
0x18003dbf3  cmovz   r8, rdi
0x18003dbf7  test    r14, r14
0x18003dbfa  mov     [rsp+270h+var_200], r8
0x18003dbff  cmovz   rdx, rdi
0x18003dc03  mov     [rsp+270h+var_208], r9
0x18003dc08  test    rsi, rsi
0x18003dc0b  mov     [rsp+270h+var_210], rdx
0x18003dc10  cmovz   rcx, rdi
0x18003dc14  test    rbx, rbx
0x18003dc17  cmovz   rax, rdi
0x18003dc1b  mov     [rsp+270h+var_218], r10
0x18003dc20  lea     r8, aHwndXDwrunleve; "hwnd = %x dwRunLevel = %x fAdjustTokenS"...
0x18003dc27  mov     [rsp+270h+var_220], rcx
0x18003dc2c  lea     rdx, aRaigettokenfor; "RAiGetTokenForMSI"
0x18003dc33  mov     [rsp+270h+var_228], rax
0x18003dc38  lea     rcx, [rbp+170h+var_130]
0x18003dc3c  mov     eax, [rbp+170h+var_1E0]
0x18003dc3f  mov     r9d, r13d
0x18003dc42  mov     [rsp+270h+var_230], r11
0x18003dc47  mov     [rsp+270h+var_238], eax
0x18003dc4b  mov     eax, [rbp+170h+var_1E4]
0x18003dc4e  mov     dword ptr [rsp+270h+var_240], eax
0x18003dc52  mov     eax, [rbp+170h+var_1F0]
0x18003dc55  mov     dword ptr [rsp+270h+var_248], eax
0x18003dc59  mov     dword ptr [rsp+270h+var_250], r12d
0x18003dc5e  call    ?WatchCurrentThread@LUATelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; LUATelemetry::WatchCurrentThread(char const *,char const *,...)
0x18003dc63  mov     rcx, cs:?g_pMSIElevationActivityTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; this
0x18003dc6a  test    rcx, rcx
0x18003dc6d  jz      short loc_18003DCD1
0x18003dc6f  call    ?RequestPermission@RateLimiter@@QEAAHXZ; RateLimiter::RequestPermission(void)
0x18003dc74  test    eax, eax
0x18003dc76  jz      short loc_18003DCD1
0x18003dc78  mov     ecx, 90h; Size
0x18003dc7d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003dc82  test    rax, rax
0x18003dc85  jz      short loc_18003DC94
0x18003dc87  mov     rcx, rax
0x18003dc8a  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18003dc8f  mov     rbx, rax
0x18003dc92  jmp     short loc_18003DC96
0x18003dc94  xor     ebx, ebx
0x18003dc96  xor     edx, edx
0x18003dc98  lock xadd [rbx+88h], rdx; unsigned __int64
0x18003dca1  lea     r8, [rbp+170h+var_E0]; char *
0x18003dca8  mov     rcx, rbx; this
0x18003dcab  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18003dcb0  test    rbx, rbx
0x18003dcb3  jz      short loc_18003DCBD
0x18003dcb5  mov     rcx, rbx; Block
0x18003dcb8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003dcbd  mov     r15, [rbp+170h+var_1B0]
0x18003dcc1  mov     r14, [rbp+170h+var_1C8]
0x18003dcc5  mov     rsi, [rbp+170h+var_1C0]
0x18003dcc9  mov     rbx, [rbp+170h+var_1B8]
0x18003dccd  mov     r12d, [rbp+170h+var_1D8]
0x18003dcd1  mov     r8, cs:WPP_GLOBAL_Control
0x18003dcd8  lea     rax, WPP_GLOBAL_Control
0x18003dcdf  cmp     r8, rax
0x18003dce2  jz      loc_18003DD79
0x18003dce8  test    byte ptr [r8+1Ch], 1
0x18003dced  jz      loc_18003DD79
0x18003dcf3  test    r15, r15
0x18003dcf6  lea     r9, [rbp+170h+var_E0]
0x18003dcfd  mov     [rsp+270h+var_1F8], r9
0x18003dd02  mov     rdx, rdi
0x18003dd05  cmovnz  rdx, r15
0x18003dd09  mov     rcx, rdi
0x18003dd0c  mov     [rsp+270h+var_200], rdx
0x18003dd11  test    r14, r14
0x18003dd14  mov     rdx, [rbp+170h+var_198]
0x18003dd18  mov     rax, rdi
0x18003dd1b  mov     [rsp+270h+var_208], rdx
0x18003dd20  cmovnz  rcx, r14
0x18003dd24  mov     [rsp+270h+var_210], rcx
0x18003dd29  test    rsi, rsi
0x18003dd2c  mov     rcx, [rbp+170h+var_158]
0x18003dd30  mov     r9d, r13d
0x18003dd33  mov     [rsp+270h+var_218], rcx
0x18003dd38  cmovnz  rax, rsi
0x18003dd3c  mov     rcx, [r8+10h]
0x18003dd40  test    rbx, rbx
0x18003dd43  mov     [rsp+270h+var_220], rax
0x18003dd48  mov     rax, [rbp+170h+var_150]
0x18003dd4c  cmovnz  rdi, rbx
0x18003dd50  mov     [rsp+270h+var_228], rdi
0x18003dd55  mov     [rsp+270h+var_230], rax
0x18003dd5a  mov     eax, [rbp+170h+var_1E0]
0x18003dd5d  mov     [rsp+270h+var_238], eax
0x18003dd61  mov     eax, [rbp+170h+var_1E4]
0x18003dd64  mov     dword ptr [rsp+270h+var_240], eax
0x18003dd68  mov     eax, [rbp+170h+var_1F0]
0x18003dd6b  mov     dword ptr [rsp+270h+var_248], eax
0x18003dd6f  mov     dword ptr [rsp+270h+var_250], r12d
0x18003dd74  call    WPP_SF_DDDDDSSSSSSSs
0x18003dd79  lea     rcx, AppInfo_PerfTrack_Elevation_MSI_Start; struct _EVENT_DESCRIPTOR *
0x18003dd80  call    ?AiLogPerfTrackEvent@@YAKPEBU_EVENT_DESCRIPTOR@@@Z; AiLogPerfTrackEvent(_EVENT_DESCRIPTOR const *)
0x18003dd85  mov     ecx, [rbp+170h+arg_68]
0x18003dd8b  mov     edi, eax
0x18003dd8d  mov     r9, [rbp+170h+var_188]; unsigned __int16 *
0x18003dd91  lea     rax, [rbp+170h+hMem]
0x18003dd95  mov     [rsp+270h+var_220], rax; struct _CONSENTUI_PARAM_HEADER **
0x18003dd9a  mov     r8, rsi; unsigned __int16 *
0x18003dd9d  mov     rax, [rbp+170h+var_148]
0x18003dda1  mov     rdx, rbx; unsigned __int16 *
0x18003dda4  mov     [rsp+270h+var_228], rax; unsigned __int16 **
0x18003dda9  mov     rax, [rbp+170h+var_140]
0x18003ddad  mov     [rsp+270h+var_230], rax; unsigned __int16 **
0x18003ddb2  mov     rax, [rbp+170h+var_190]
0x18003ddb6  mov     [rsp+270h+var_238], ecx; unsigned int
0x18003ddba  mov     ecx, [rbp+170h+var_1E4]; unsigned int
0x18003ddbd  mov     [rsp+270h+var_240], r15; wchar_t *
0x18003ddc2  mov     [rsp+270h+var_248], rax; wchar_t *
0x18003ddc7  mov     [rsp+270h+var_250], r14; wchar_t *
0x18003ddcc  call    ?AiBuildMSIParams@@YAKKPEBG00000KPEAPEBG1PEAPEAU_CONSENTUI_PARAM_HEADER@@@Z; AiBuildMSIParams(ulong,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const * *,ushort const * *,_CONSENTUI_PARAM_HEADER * *)
0x18003ddd1  mov     rbx, [rbp+170h+hMem]
0x18003ddd5  xor     esi, esi
0x18003ddd7  mov     [rbp+170h+Reply], eax
0x18003ddda  test    eax, eax
0x18003dddc  jnz     short loc_18003DE42
0x18003ddde  mov     rdx, [rbp+170h+var_1A0]; void *
0x18003dde2  lea     rax, [rbp+170h+var_1D0]
0x18003dde6  mov     [rsp+270h+var_208], rax; int *
0x18003ddeb  lea     ecx, [rsi+1]; unsigned int
0x18003ddee  lea     rax, [rbp+170h+var_1E8]
0x18003ddf2  mov     [rbx+34h], edi
0x18003ddf5  mov     [rsp+270h+var_210], rax; enum UACPROMPT_POLICY *
0x18003ddfa  mov     r9d, r12d; unsigned int
0x18003ddfd  lea     rax, [rbp+170h+var_E0]
0x18003de04  mov     r8, r13; unsigned __int64
0x18003de07  mov     [rsp+270h+var_218], rax; char *
0x18003de0c  mov     rax, [rbp+170h+var_1A8]
0x18003de10  mov     dword ptr [rsp+270h+var_220], esi; unsigned int
0x18003de14  mov     [rsp+270h+var_228], rax; unsigned __int64 *
0x18003de19  mov     eax, [rbp+170h+var_1E0]
0x18003de1c  mov     [rsp+270h+var_230], rsi; unsigned __int16 *
0x18003de21  mov     [rsp+270h+var_238], eax; unsigned int
0x18003de25  mov     rax, [rbp+170h+var_178]
0x18003de29  mov     [rsp+270h+var_240], rbx; struct _CONSENTUI_PARAM_HEADER *
0x18003de2e  mov     [rsp+270h+var_248], rax; unsigned __int16 *
0x18003de33  mov     eax, [rbp+170h+var_1F0]
0x18003de36  mov     dword ptr [rsp+270h+var_250], eax; int
0x18003de3a  call    ?AipGetTokenForService@@YAKKPEAX_KKHPEBGPEAU_CONSENTUI_PARAM_HEADER@@K2PEA_KKPEBDPEAW4UACPROMPT_POLICY@@PEAH@Z; AipGetTokenForService(ulong,void *,unsigned __int64,ulong,int,ushort const *,_CONSENTUI_PARAM_HEADER *,ulong,ushort const *,unsigned __int64 *,ulong,char const *,UACPROMPT_POLICY *,int *)
0x18003de3f  mov     [rbp+170h+Reply], eax
0x18003de42  mov     rcx, rbx; hMem
0x18003de45  call    cs:__imp_LocalFree
0x18003de4c  nop     dword ptr [rax+rax+00h]
0x18003de51  lea     rcx, [rbp+170h+var_170]; lpPerformanceCount
0x18003de55  call    cs:__imp_QueryPerformanceCounter
0x18003de5c  nop     dword ptr [rax+rax+00h]
0x18003de61  mov     rax, qword ptr [rbp+170h+var_170]
0x18003de65  sub     rax, qword ptr [rbp+170h+PerformanceCount]
0x18003de69  imul    rax, 3E8h
0x18003de70  cqo
0x18003de72  idiv    qword ptr [rbp+170h+Frequency]
0x18003de76  mov     [rbp+170h+var_1A8], rax
0x18003de7a  lea     rax, [rbp+170h+var_E0]
0x18003de81  mov     [rbp+170h+var_1A0], rax
0x18003de85  mov     eax, [rbp+170h+var_1E8]
0x18003de88  mov     [rbp+170h+var_1E8], eax
0x18003de8b  mov     eax, [rbp+170h+Reply]
0x18003de8e  cmp     eax, 4C7h
0x18003de93  jnz     short loc_18003DE9A
0x18003de95  mov     [rbp+170h+var_1F0], esi
0x18003de98  jmp     short loc_18003DEA9
0x18003de9a  test    eax, eax
0x18003de9c  jle     short loc_18003DEA6
0x18003de9e  movzx   eax, ax
0x18003dea1  or      eax, 80070000h
0x18003dea6  mov     [rbp+170h+var_1F0], eax
0x18003dea9  lea     rax, [rbp+170h+var_1A0]
0x18003dead  mov     [rsp+270h+var_210], rax
0x18003deb2  lea     r9, [rbp+170h+var_1B0]
0x18003deb6  lea     rax, [rbp+170h+var_1A8]
0x18003deba  mov     [rsp+270h+var_218], rax
0x18003debf  lea     r8, [rbp+170h+var_1D8]
0x18003dec3  lea     rax, [rbp+170h+var_1E8]
0x18003dec7  mov     [rsp+270h+var_220], rax
0x18003decc  lea     rdx, [rbp+170h+Reply]
0x18003ded0  lea     rax, [rbp+170h+var_1D0]
0x18003ded4  mov     [rsp+270h+var_228], rax
0x18003ded9  lea     rcx, [rbp+170h+var_1F0]
0x18003dedd  lea     rax, [rbp+170h+arg_68]
0x18003dee4  mov     [rsp+270h+var_230], rax
0x18003dee9  lea     rax, [rbp+170h+var_1CC]
0x18003deed  mov     qword ptr [rsp+270h+var_238], rax
0x18003def2  lea     rax, [rbp+170h+var_1C8]
0x18003def6  mov     [rsp+270h+var_240], rax
0x18003defb  lea     rax, [rbp+170h+var_1C0]
0x18003deff  mov     [rsp+270h+var_248], rax
0x18003df04  lea     rax, [rbp+170h+var_1B8]
0x18003df08  mov     [rsp+270h+var_250], rax
0x18003df0d  call    ??$MSIElevation@JAEAKAEAKAEAPEBGAEAPEBGAEAPEBGAEAPEBGAEAW4_MSI_ACTION@@AEAKAEAHKAEA_JPEBD@LUATelemetry@@SAX$$QEAJAEAK1AEAPEBG222AEAW4_MSI_ACTION@@1AEAH$$QEAKAEA_J$$QEAPEBD@Z; LUATelemetry::MSIElevation<long,ulong &,ulong &,ushort const * &,ushort const * &,ushort const * &,ushort const * &,_MSI_ACTION &,ulong &,int &,ulong,__int64 &,char const *>(long &&,ulong &,ulong &,ushort const * &,ushort const * &,ushort const * &,ushort const * &,_MSI_ACTION &,ulong &,int &,ulong &&,__int64 &,char const * &&)
0x18003df12  mov     rcx, [rbp+170h+pAsync]; pAsync
0x18003df16  lea     rdx, [rbp+170h+Reply]; Reply
0x18003df1a  call    cs:__imp_RpcAsyncCompleteCall
0x18003df21  nop     dword ptr [rax+rax+00h]
0x18003df26  mov     rcx, cs:WPP_GLOBAL_Control
0x18003df2d  lea     rax, WPP_GLOBAL_Control
0x18003df34  cmp     rcx, rax
0x18003df37  jz      short loc_18003DF58
0x18003df39  test    byte ptr [rcx+1Ch], 1
0x18003df3d  jz      short loc_18003DF58
0x18003df3f  mov     r9d, [rbp+170h+Reply]
0x18003df43  lea     r8, WPP_aba5399977573c9264c162bacbfc9302_Traceguids
0x18003df4a  mov     rcx, [rcx+10h]
0x18003df4e  mov     edx, 0Fh
0x18003df53  call    WPP_SF_D
0x18003df58  lea     rcx, [rbp+170h+var_130]; this
0x18003df5c  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18003df61  mov     rcx, [rbp+170h+var_50]
0x18003df68  xor     rcx, rsp; StackCookie
0x18003df6b  call    __security_check_cookie
0x18003df70  add     rsp, 238h
0x18003df77  pop     r15
  ... truncated ...
```
