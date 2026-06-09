# RAiGetTokenForCOM

- ea: `0x180041dc0`
- end: `0x180042298`
- name: `RAiGetTokenForCOM`
- size: `1240`
- prototype: `void __fastcall(struct _RPC_ASYNC_STATE *, void *, unsigned __int64, unsigned int, int, int, unsigned __int16 *, struct _GUID *, wchar_t *Source, wchar_t *, wchar_t *, wchar_t *, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x18000f3e0`
- `0x180011a30`
- `0x18001aee4`
- `0x18001b408`
- `0x18001e7bc`
- `0x18001e7c8`
- `0x180026f40`
- `0x18002ad54`
- `0x18002b0c0`
- `0x18003b3f0`
- `0x18003bb44`
- `0x180040c60`
- `0x180040d64`
- `0x180041dc0`
- `0x180042a54`
- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180042233`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180042233`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004216d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004217b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004216d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004217b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180041ea4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180041ea4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180041e9a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180042189`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180041e9a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180042189`

## string_xrefs

- `0x180041f53`: `hwnd = %x dwRunLevel = %x dwClientFlags = %x fAdjustTokenSD = %x dwTimeout = %x\n	lpDesktop = %ws\n	lpFriendlyName = %ws\n	lpServerBinary = %ws\n	lpIconReference = %ws\n	lpRequestorPath = %ws\n	lpCvStr = %s\n`
- `0x180041f5a`: `RAiGetTokenForCOM`

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
        wchar_t *Source,
        wchar_t *a10,
        wchar_t *a11,
        wchar_t *a12,
        unsigned int a13,
        unsigned __int64 *a14)
{
  unsigned int v14; // edi
  wchar_t *v15; // rbx
  struct _CONSENTUI_PARAM_HEADER *v16; // r14
  const unsigned __int16 *v17; // r15
  const wchar_t *v18; // rdx
  wchar_t *v19; // r8
  unsigned __int16 *v20; // r9
  const wchar_t *v21; // rax
  void *v22; // rax
  volatile signed __int64 *v23; // rdi
  const wchar_t *v24; // r8
  wchar_t *v25; // rdi
  const wchar_t *v26; // rax
  unsigned int v27; // edi
  unsigned int v28; // eax
  unsigned __int64 v29; // rax
  int v30; // eax
  unsigned int v31; // r9d
  unsigned __int64 v32; // r8
  void *v33; // rdx
  unsigned int v34; // eax
  int v35; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v36; // [rsp+28h] [rbp-D8h]
  struct _CONSENTUI_PARAM_HEADER *v37; // [rsp+30h] [rbp-D0h]
  unsigned int v38[2]; // [rsp+38h] [rbp-C8h]
  unsigned int v39; // [rsp+38h] [rbp-C8h]
  unsigned __int64 *v40; // [rsp+48h] [rbp-B8h]
  int Reply; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v42; // [rsp+74h] [rbp-8Ch] BYREF
  int v43; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v44; // [rsp+7Ch] [rbp-84h]
  int v45; // [rsp+80h] [rbp-80h]
  int v46; // [rsp+84h] [rbp-7Ch] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-78h] BYREF
  int v48; // [rsp+90h] [rbp-70h] BYREF
  int v49; // [rsp+98h] [rbp-68h] BYREF
  struct _CONSENTUI_PARAM_HEADER *v50; // [rsp+A0h] [rbp-60h] BYREF
  void *v51; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t *v52; // [rsp+B0h] [rbp-50h]
  wchar_t *v53; // [rsp+B8h] [rbp-48h]
  unsigned __int16 *v54; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v55; // [rsp+C8h] [rbp-38h]
  LARGE_INTEGER v56; // [rsp+D0h] [rbp-30h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+D8h] [rbp-28h] BYREF
  LARGE_INTEGER Frequency; // [rsp+E0h] [rbp-20h] BYREF
  const wchar_t *v59; // [rsp+E8h] [rbp-18h]
  wchar_t *v60; // [rsp+F0h] [rbp-10h]
  unsigned __int16 *v61; // [rsp+F8h] [rbp-8h]
  struct _GUID *v62; // [rsp+100h] [rbp+0h]
  unsigned __int64 *v63; // [rsp+108h] [rbp+8h]
  wchar_t *v64; // [rsp+110h] [rbp+10h] BYREF
  struct _GUID *v65; // [rsp+118h] [rbp+18h] BYREF
  PRPC_ASYNC_STATE pAsync; // [rsp+120h] [rbp+20h]
  char v67[80]; // [rsp+130h] [rbp+30h] BYREF
  char v68[144]; // [rsp+180h] [rbp+80h] BYREF

  v14 = a3;
  v15 = a12;
  v54 = a7;
  v45 = a6;
  v62 = a8;
  v65 = a8;
  v44 = a13;
  v63 = a14;
  v55 = a3;
  v16 = 0;
  v51 = a2;
  pAsync = a1;
  Reply = 0;
  v50 = 0;
  v49 = 0;
  v46 = 0;
  v43 = 0;
  Frequency.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  v56.QuadPart = 0;
  v42 = a4;
  v53 = a10;
  v52 = a11;
  v48 = a5;
  v64 = Source;
  hMem = a12;
  QueryPerformanceCounter(&PerformanceCount);
  QueryPerformanceFrequency(&Frequency);
  memset_0(v68, 0, 0x81u);
  v17 = L"NULL";
  v18 = a11;
  if ( !a11 )
    v18 = L"NULL";
  v59 = v18;
  v19 = v53;
  if ( !v53 )
    v19 = L"NULL";
  v60 = v19;
  v20 = v54;
  v21 = Source;
  if ( !v54 )
    v20 = L"NULL";
  v61 = v20;
  if ( !Source )
    v21 = L"NULL";
  v38[0] = v44;
  LUATelemetry::WatchCurrentThread(
    v67,
    "RAiGetTokenForCOM",
    "hwnd = %x dwRunLevel = %x dwClientFlags = %x fAdjustTokenSD = %x dwTimeout = %x\n"
    "\tlpDesktop = %ws\n"
    "\tlpFriendlyName = %ws\n"
    "\tlpServerBinary = %ws\n"
    "\tlpIconReference = %ws\n"
    "\tlpRequestorPath = %ws\n"
    "\tlpCvStr = %s\n",
    v14,
    v42,
    a5,
    v45,
    *(_QWORD *)v38,
    v20,
    v21,
    v19,
    v18);
  if ( g_pCOMElevationActivityTelemetryRateLimiter
    && (unsigned int)RateLimiter::RequestPermission(g_pCOMElevationActivityTelemetryRateLimiter) )
  {
    v22 = operator new(0x90u);
    v23 = v22 ? (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v22) : 0LL;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v23,
      _InterlockedExchangeAdd64(v23 + 17, 0),
      v68);
    if ( v23 )
      operator delete((void *)v23);
  }
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
    v25 = Source;
  }
  else
  {
    v24 = L"NULL";
    v25 = Source;
    v26 = Source;
    if ( a12 )
      v24 = a12;
    if ( !Source )
      v26 = L"NULL";
    WPP_SF_DDDDDSSSSSs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (_DWORD)v60,
      v55,
      v42,
      a5,
      v45,
      v44,
      (__int64)v61,
      (__int64)v26,
      (__int64)v60,
      (__int64)v59,
      (__int64)v24,
      (__int64)v68);
  }
  if ( Source )
    v17 = v25;
  v27 = AiLogPerfTrackEventEx(&AppInfo_PerfTrack_Elevation_COM_Start, v17);
  if ( a12 )
  {
    if ( (a5 & 0x20) != 0 )
    {
      v28 = AiConvertWow64Paths(a12, (const unsigned __int16 **)&hMem, 0, 0, 0, 0);
      v15 = (wchar_t *)hMem;
      Reply = v28;
      if ( v28 )
        goto LABEL_35;
    }
    v29 = -1;
    do
      ++v29;
    while ( v15[v29] );
    if ( v29 > 0x7FFF )
    {
      Reply = 87;
      goto LABEL_35;
    }
  }
  v30 = AiBuildCOMParams(Source, v53, v52, v15, v62, &v50);
  v16 = v50;
  Reply = v30;
  if ( !v30 )
  {
    v31 = v42;
    v32 = v55;
    v33 = v51;
    v40 = v63;
    v39 = v44;
    v37 = v50;
    v36 = v54;
    v35 = v45;
    *((_DWORD *)v50 + 13) = v27;
    Reply = AipGetTokenForService(
              0,
              v33,
              v32,
              v31,
              v35,
              v36,
              v37,
              v39,
              v15,
              v40,
              0,
              v68,
              (enum UACPROMPT_POLICY *)&v43,
              &v46);
  }
LABEL_35:
  LocalFree(v16);
  if ( v15 != a12 )
  {
    LocalFree(v15);
    hMem = a12;
  }
  QueryPerformanceCounter(&v56);
  v51 = (void *)(1000 * (v56.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart);
  v34 = Reply;
  if ( Reply == 1223 )
  {
    v34 = 0;
  }
  else if ( Reply > 0 )
  {
    v34 = (unsigned __int16)Reply | 0x80070000;
  }
  v42 = v34;
  LUATelemetry::COMElevation<long,unsigned long &,unsigned long &,unsigned long &,_GUID * &,unsigned short const * &,unsigned short const * &,int &,unsigned long,__int64 &,char (&)[129]>(
    (unsigned int)&v42,
    (unsigned int)&Reply,
    (unsigned int)&v49,
    (unsigned int)&v48,
    (__int64)&v65,
    (__int64)&hMem,
    (__int64)&v64,
    (__int64)&v46,
    (__int64)&v43,
    (__int64)&v51,
    v68);
  RpcAsyncCompleteCall(pAsync, &Reply);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_aba5399977573c9264c162bacbfc9302_Traceguids,
      (unsigned int)Reply);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v67);
}

```

## disassembly

```asm
0x180041dc0  push    rbp
0x180041dc2  push    rbx
0x180041dc3  push    rsi
0x180041dc4  push    rdi
0x180041dc5  push    r12
0x180041dc7  push    r13
0x180041dc9  push    r14
0x180041dcb  push    r15
0x180041dcd  lea     rbp, [rsp-128h]
0x180041dd5  sub     rsp, 228h
0x180041ddc  mov     rax, cs:__security_cookie
0x180041de3  xor     rax, rsp
0x180041de6  mov     [rbp+160h+var_50], rax
0x180041ded  mov     rax, [rbp+160h+arg_30]
0x180041df4  mov     rdi, r8
0x180041df7  mov     r12, [rbp+160h+arg_58]
0x180041dfe  mov     rsi, [rbp+160h+Source]
0x180041e05  mov     rbx, r12
0x180041e08  mov     r13d, [rbp+160h+arg_20]
0x180041e0f  mov     [rbp+160h+var_1A0], rax
0x180041e13  mov     eax, [rbp+160h+arg_28]
0x180041e19  mov     [rbp+160h+var_1E0], eax
0x180041e1c  mov     rax, [rbp+160h+arg_38]
0x180041e23  mov     [rbp+160h+var_160], rax
0x180041e27  mov     [rbp+160h+var_148], rax
0x180041e2b  mov     eax, [rbp+160h+arg_60]
0x180041e31  mov     [rsp+260h+var_1E4], eax
0x180041e35  mov     rax, [rbp+160h+arg_68]
0x180041e3c  mov     [rbp+160h+var_158], rax
0x180041e40  xor     eax, eax
0x180041e42  mov     [rbp+160h+var_198], r8
0x180041e46  mov     r14d, eax
0x180041e49  mov     r8, [rbp+160h+arg_50]
0x180041e50  mov     [rbp+160h+var_1B8], rdx
0x180041e54  mov     rdx, [rbp+160h+arg_48]
0x180041e5b  mov     [rbp+160h+pAsync], rcx
0x180041e5f  lea     rcx, [rbp+160h+PerformanceCount]; lpPerformanceCount
0x180041e63  mov     [rsp+260h+Reply], eax
0x180041e67  mov     [rbp+160h+var_1C0], rax
0x180041e6b  mov     [rbp+160h+var_1C8], eax
0x180041e6e  mov     [rbp+160h+var_1DC], eax
0x180041e71  mov     [rsp+260h+var_1E8], eax
0x180041e75  mov     qword ptr [rbp+160h+Frequency], rax
0x180041e79  mov     qword ptr [rbp+160h+PerformanceCount], rax
0x180041e7d  mov     qword ptr [rbp+160h+var_190], rax
0x180041e81  mov     [rsp+260h+var_1EC], r9d
0x180041e86  mov     [rbp+160h+var_1A8], rdx
0x180041e8a  mov     [rbp+160h+var_1B0], r8
0x180041e8e  mov     [rbp+160h+var_1D0], r13d
0x180041e92  mov     [rbp+160h+var_150], rsi
0x180041e96  mov     [rbp+160h+hMem], rbx
0x180041e9a  call    cs:__imp_QueryPerformanceCounter
0x180041ea0  lea     rcx, [rbp+160h+Frequency]; lpFrequency
0x180041ea4  call    cs:__imp_QueryPerformanceFrequency
0x180041eaa  xor     edx, edx; Val
0x180041eac  lea     rcx, [rbp+160h+var_E0]; void *
0x180041eb3  mov     r8d, 81h; Size
0x180041eb9  call    memset_0
0x180041ebe  mov     rax, [rbp+160h+var_1B0]
0x180041ec2  lea     r15, aNull_0; "NULL"
0x180041ec9  test    rax, rax
0x180041ecc  lea     r10, [rbp+160h+var_E0]
0x180041ed3  mov     [rsp+260h+var_1F8], r10
0x180041ed8  mov     rdx, rax
0x180041edb  mov     rax, [rbp+160h+var_1A8]
0x180041edf  cmovz   rdx, r15
0x180041ee3  test    rax, rax
0x180041ee6  mov     [rbp+160h+var_178], rdx
0x180041eea  mov     r8, rax
0x180041eed  mov     rcx, r12
0x180041ef0  mov     rax, [rbp+160h+var_1A0]
0x180041ef4  cmovz   r8, r15
0x180041ef8  test    rax, rax
0x180041efb  mov     [rbp+160h+var_170], r8
0x180041eff  mov     r9, rax
0x180041f02  mov     rax, rsi
0x180041f05  cmovz   r9, r15
0x180041f09  test    r12, r12
0x180041f0c  mov     [rbp+160h+var_168], r9
0x180041f10  cmovz   rcx, r15
0x180041f14  test    rsi, rsi
0x180041f17  mov     [rsp+260h+var_200], rcx
0x180041f1c  mov     [rsp+260h+var_208], rdx
0x180041f21  cmovz   rax, r15
0x180041f25  mov     qword ptr [rsp+260h+var_210], r8
0x180041f2a  mov     [rsp+260h+var_218], rax
0x180041f2f  mov     eax, [rsp+260h+var_1E4]
0x180041f33  mov     [rsp+260h+var_220], r9
0x180041f38  mov     [rsp+260h+var_228], eax
0x180041f3c  mov     eax, [rbp+160h+var_1E0]
0x180041f3f  mov     dword ptr [rsp+260h+var_230], eax
0x180041f43  mov     eax, [rsp+260h+var_1EC]
0x180041f47  mov     dword ptr [rsp+260h+var_238], r13d
0x180041f4c  mov     dword ptr [rsp+260h+var_240], eax
0x180041f50  mov     r9d, edi
0x180041f53  lea     r8, aHwndXDwrunleve_0; "hwnd = %x dwRunLevel = %x dwClientFlags"...
0x180041f5a  lea     rdx, aRaigettokenfor_0; "RAiGetTokenForCOM"
0x180041f61  lea     rcx, [rbp+160h+var_130]
0x180041f65  call    ?WatchCurrentThread@LUATelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; LUATelemetry::WatchCurrentThread(char const *,char const *,...)
0x180041f6a  mov     rcx, cs:?g_pCOMElevationActivityTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; this
0x180041f71  test    rcx, rcx
0x180041f74  jz      short loc_180041FC4
0x180041f76  call    ?RequestPermission@RateLimiter@@QEAAHXZ; RateLimiter::RequestPermission(void)
0x180041f7b  test    eax, eax
0x180041f7d  jz      short loc_180041FC4
0x180041f7f  mov     ecx, 90h; Size
0x180041f84  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180041f89  test    rax, rax
0x180041f8c  jz      short loc_180041F9B
0x180041f8e  mov     rcx, rax
0x180041f91  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x180041f96  mov     rdi, rax
0x180041f99  jmp     short loc_180041F9D
0x180041f9b  xor     edi, edi
0x180041f9d  xor     edx, edx
0x180041f9f  lock xadd [rdi+88h], rdx; unsigned __int64
0x180041fa8  lea     r8, [rbp+160h+var_E0]; char *
0x180041faf  mov     rcx, rdi; this
0x180041fb2  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180041fb7  test    rdi, rdi
0x180041fba  jz      short loc_180041FC4
0x180041fbc  mov     rcx, rdi; Block
0x180041fbf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180041fc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180041fcb  lea     rax, WPP_GLOBAL_Control
0x180041fd2  cmp     rcx, rax
0x180041fd5  jz      short loc_180042056
0x180041fd7  test    byte ptr [rcx+1Ch], 1
0x180041fdb  jz      short loc_180042056
0x180041fdd  test    rbx, rbx
0x180041fe0  mov     r8, r15
0x180041fe3  mov     rdi, rsi
0x180041fe6  mov     rax, rsi
0x180041fe9  cmovnz  r8, r12
0x180041fed  test    rsi, rsi
0x180041ff0  jnz     short loc_180041FF5
0x180041ff2  mov     rax, r15
0x180041ff5  mov     rcx, [rcx+10h]
0x180041ff9  lea     r9, [rbp+160h+var_E0]
0x180042000  mov     [rsp+260h+var_1F8], r9
0x180042005  mov     edx, 0Ah
0x18004200a  mov     r9d, dword ptr [rbp+160h+var_198]
0x18004200e  mov     [rsp+260h+var_200], r8
0x180042013  mov     r8, [rbp+160h+var_178]
0x180042017  mov     [rsp+260h+var_208], r8
0x18004201c  mov     r8, [rbp+160h+var_170]
0x180042020  mov     qword ptr [rsp+260h+var_210], r8
0x180042025  mov     [rsp+260h+var_218], rax
0x18004202a  mov     rax, [rbp+160h+var_168]
0x18004202e  mov     [rsp+260h+var_220], rax
0x180042033  mov     eax, [rsp+260h+var_1E4]
0x180042037  mov     [rsp+260h+var_228], eax
0x18004203b  mov     eax, [rbp+160h+var_1E0]
0x18004203e  mov     dword ptr [rsp+260h+var_230], eax
0x180042042  mov     eax, [rsp+260h+var_1EC]
0x180042046  mov     dword ptr [rsp+260h+var_238], r13d
0x18004204b  mov     dword ptr [rsp+260h+var_240], eax
0x18004204f  call    WPP_SF_DDDDDSSSSSs
0x180042054  jmp     short loc_180042059
0x180042056  mov     rdi, rsi
0x180042059  test    rsi, rsi
0x18004205c  lea     rcx, AppInfo_PerfTrack_Elevation_COM_Start; struct _EVENT_DESCRIPTOR *
0x180042063  cmovnz  r15, rdi
0x180042067  mov     rdx, r15; unsigned __int16 *
0x18004206a  call    ?AiLogPerfTrackEventEx@@YAKPEBU_EVENT_DESCRIPTOR@@PEBG@Z; AiLogPerfTrackEventEx(_EVENT_DESCRIPTOR const *,ushort const *)
0x18004206f  xor     r15d, r15d
0x180042072  mov     edi, eax
0x180042074  test    rbx, rbx
0x180042077  jz      short loc_1800420CE
0x180042079  test    r13b, 20h
0x18004207d  jz      short loc_1800420AB
0x18004207f  mov     [rsp+260h+var_238], r15; unsigned __int16 **
0x180042084  lea     rdx, [rbp+160h+hMem]; unsigned __int16 **
0x180042088  xor     r9d, r9d; unsigned __int16 **
0x18004208b  mov     [rsp+260h+var_240], r15; unsigned __int16 *
0x180042090  xor     r8d, r8d; unsigned __int16 *
0x180042093  mov     rcx, r12; unsigned __int16 *
0x180042096  call    ?AiConvertWow64Paths@@YAKPEBGPEAPEBGPEAGPEAPEAG01@Z; AiConvertWow64Paths(ushort const *,ushort const * *,ushort *,ushort * *,ushort const *,ushort const * *)
0x18004209b  mov     rbx, [rbp+160h+hMem]
0x18004209f  mov     [rsp+260h+Reply], eax
0x1800420a3  test    eax, eax
0x1800420a5  jnz     loc_18004216A
0x1800420ab  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800420af  inc     rax
0x1800420b2  cmp     [rbx+rax*2], r15w
0x1800420b7  jnz     short loc_1800420AF
0x1800420b9  cmp     rax, 7FFFh
0x1800420bf  jbe     short loc_1800420CE
0x1800420c1  mov     [rsp+260h+Reply], 57h ; 'W'
0x1800420c9  jmp     loc_18004216A
0x1800420ce  mov     r8, [rbp+160h+var_1B0]; wchar_t *
0x1800420d2  lea     rax, [rbp+160h+var_1C0]
0x1800420d6  mov     rdx, [rbp+160h+var_1A8]; wchar_t *
0x1800420da  mov     r9, rbx; wchar_t *
0x1800420dd  mov     [rsp+260h+var_238], rax; struct _CONSENTUI_PARAM_HEADER **
0x1800420e2  mov     rcx, rsi; Source
0x1800420e5  mov     rax, [rbp+160h+var_160]
0x1800420e9  mov     [rsp+260h+var_240], rax; struct _GUID *
0x1800420ee  call    ?AiBuildCOMParams@@YAKPEBG000PEAU_GUID@@PEAPEAU_CONSENTUI_PARAM_HEADER@@@Z; AiBuildCOMParams(ushort const *,ushort const *,ushort const *,ushort const *,_GUID *,_CONSENTUI_PARAM_HEADER * *)
0x1800420f3  mov     r14, [rbp+160h+var_1C0]
0x1800420f7  mov     [rsp+260h+Reply], eax
0x1800420fb  test    eax, eax
0x1800420fd  jnz     short loc_18004216A
0x1800420ff  mov     r9d, [rsp+260h+var_1EC]; unsigned int
0x180042104  lea     rax, [rbp+160h+var_1DC]
0x180042108  mov     r8, [rbp+160h+var_198]; unsigned __int64
0x18004210c  xor     ecx, ecx; unsigned int
0x18004210e  mov     rdx, [rbp+160h+var_1B8]; void *
0x180042112  mov     [rsp+260h+var_1F8], rax; int *
0x180042117  lea     rax, [rsp+260h+var_1E8]
0x18004211c  mov     [rsp+260h+var_200], rax; enum UACPROMPT_POLICY *
0x180042121  lea     rax, [rbp+160h+var_E0]
0x180042128  mov     [rsp+260h+var_208], rax; char *
0x18004212d  mov     rax, [rbp+160h+var_158]
0x180042131  mov     [rsp+260h+var_210], r15d; unsigned int
0x180042136  mov     [rsp+260h+var_218], rax; unsigned __int64 *
0x18004213b  mov     eax, [rsp+260h+var_1E4]
0x18004213f  mov     [rsp+260h+var_220], rbx; unsigned __int16 *
0x180042144  mov     [rsp+260h+var_228], eax; unsigned int
0x180042148  mov     rax, [rbp+160h+var_1A0]
0x18004214c  mov     [rsp+260h+var_230], r14; struct _CONSENTUI_PARAM_HEADER *
0x180042151  mov     [rsp+260h+var_238], rax; unsigned __int16 *
0x180042156  mov     eax, [rbp+160h+var_1E0]
0x180042159  mov     dword ptr [rsp+260h+var_240], eax; int
0x18004215d  mov     [r14+34h], edi
0x180042161  call    ?AipGetTokenForService@@YAKKPEAX_KKHPEBGPEAU_CONSENTUI_PARAM_HEADER@@K2PEA_KKPEBDPEAW4UACPROMPT_POLICY@@PEAH@Z; AipGetTokenForService(ulong,void *,unsigned __int64,ulong,int,ushort const *,_CONSENTUI_PARAM_HEADER *,ulong,ushort const *,unsigned __int64 *,ulong,char const *,UACPROMPT_POLICY *,int *)
0x180042166  mov     [rsp+260h+Reply], eax
0x18004216a  mov     rcx, r14; hMem
0x18004216d  call    cs:__imp_LocalFree
0x180042173  cmp     rbx, r12
0x180042176  jz      short loc_180042185
0x180042178  mov     rcx, rbx; hMem
0x18004217b  call    cs:__imp_LocalFree
0x180042181  mov     [rbp+160h+hMem], r12
0x180042185  lea     rcx, [rbp+160h+var_190]; lpPerformanceCount
0x180042189  call    cs:__imp_QueryPerformanceCounter
0x18004218f  mov     rax, qword ptr [rbp+160h+var_190]
0x180042193  sub     rax, qword ptr [rbp+160h+PerformanceCount]
0x180042197  imul    rax, 3E8h
0x18004219e  cqo
0x1800421a0  idiv    qword ptr [rbp+160h+Frequency]
0x1800421a4  mov     [rbp+160h+var_1B8], rax
0x1800421a8  mov     eax, [rsp+260h+var_1E8]
0x1800421ac  mov     [rsp+260h+var_1E8], eax
0x1800421b0  mov     eax, [rsp+260h+Reply]
0x1800421b4  cmp     eax, 4C7h
0x1800421b9  jnz     short loc_1800421C0
0x1800421bb  mov     eax, r15d
0x1800421be  jmp     short loc_1800421CC
0x1800421c0  test    eax, eax
0x1800421c2  jle     short loc_1800421CC
0x1800421c4  movzx   eax, ax
0x1800421c7  or      eax, 80070000h
0x1800421cc  mov     [rsp+260h+var_1EC], eax
0x1800421d0  lea     r9, [rbp+160h+var_1D0]
0x1800421d4  lea     rax, [rbp+160h+var_E0]
0x1800421db  mov     qword ptr [rsp+260h+var_210], rax
0x1800421e0  lea     r8, [rbp+160h+var_1C8]
0x1800421e4  lea     rax, [rbp+160h+var_1B8]
0x1800421e8  mov     [rsp+260h+var_218], rax
0x1800421ed  lea     rdx, [rsp+260h+Reply]
0x1800421f2  lea     rax, [rsp+260h+var_1E8]
0x1800421f7  mov     [rsp+260h+var_220], rax
0x1800421fc  lea     rcx, [rsp+260h+var_1EC]
0x180042201  lea     rax, [rbp+160h+var_1DC]
0x180042205  mov     qword ptr [rsp+260h+var_228], rax
0x18004220a  lea     rax, [rbp+160h+var_150]
0x18004220e  mov     [rsp+260h+var_230], rax
0x180042213  lea     rax, [rbp+160h+hMem]
0x180042217  mov     [rsp+260h+var_238], rax
0x18004221c  lea     rax, [rbp+160h+var_148]
0x180042220  mov     [rsp+260h+var_240], rax
0x180042225  call    ??$COMElevation@JAEAKAEAKAEAKAEAPEAU_GUID@@AEAPEBGAEAPEBGAEAHKAEA_JAEAY0IB@D@LUATelemetry@@SAX$$QEAJAEAK11AEAPEAU_GUID@@AEAPEBG3AEAH$$QEAKAEA_JAEAY0IB@D@Z; LUATelemetry::COMElevation<long,ulong &,ulong &,ulong &,_GUID * &,ushort const * &,ushort const * &,int &,ulong,__int64 &,char (&)[129]>(long &&,ulong &,ulong &,ulong &,_GUID * &,ushort const * &,ushort const * &,int &,ulong &&,__int64 &,char (&)[129])
0x18004222a  mov     rcx, [rbp+160h+pAsync]; pAsync
0x18004222e  lea     rdx, [rsp+260h+Reply]; Reply
0x180042233  call    cs:__imp_RpcAsyncCompleteCall
0x180042239  mov     rcx, cs:WPP_GLOBAL_Control
0x180042240  lea     rax, WPP_GLOBAL_Control
0x180042247  cmp     rcx, rax
0x18004224a  jz      short loc_18004226C
0x18004224c  test    byte ptr [rcx+1Ch], 1
0x180042250  jz      short loc_18004226C
0x180042252  mov     r9d, [rsp+260h+Reply]
0x180042257  lea     r8, WPP_aba5399977573c9264c162bacbfc9302_Traceguids
0x18004225e  mov     rcx, [rcx+10h]
0x180042262  mov     edx, 0Bh
0x180042267  call    WPP_SF_D
0x18004226c  lea     rcx, [rbp+160h+var_130]; this
0x180042270  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180042275  mov     rcx, [rbp+160h+var_50]
0x18004227c  xor     rcx, rsp; StackCookie
0x18004227f  call    __security_check_cookie
0x180042284  add     rsp, 228h
0x18004228b  pop     r15
0x18004228d  pop     r14
0x18004228f  pop     r13
0x180042291  pop     r12
0x180042293  pop     rdi
0x180042294  pop     rsi
0x180042295  pop     rbx
  ... truncated ...
```
