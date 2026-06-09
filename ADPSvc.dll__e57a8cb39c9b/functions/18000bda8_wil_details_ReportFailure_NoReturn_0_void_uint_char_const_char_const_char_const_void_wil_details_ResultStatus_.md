# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x18000bda8`
- end: `0x18000c054`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000bcb0`

## callees

- `0x180002cf8`
- `0x1800055c4`
- `0x1800064b4`
- `0x1800072c0`
- `0x180007630`
- `0x18000770c`
- `0x18000bda8`
- `0x1800c6e30`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000be51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000be51`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000bf4c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000bf4c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000bfe8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000bfe8`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v10; // r12
  int v11; // ebx
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  char v18; // bl
  const struct wil::FailureInfo *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v10 = g_pfnThrowPlatformException != 0;
  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v11 = wil::details::RecordException((wil::details *)(unsigned int)v22, (int)a7);
  v20 = 0;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v21 = v12;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v11;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && !v10 && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v18 = 1, (v21 & 2) != 0) )
  {
    v18 = 0;
  }
  if ( v10 || v18 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v14);
  if ( v10 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v20, OutputString);
  wil::ThrowResultException((wil *)&v20, v14);
  wil::details::WilFailFast((wil::details *)&v20, v19);
}

```

## disassembly

```asm
0x18000bda8  mov     [rsp-8+arg_18], rbx
0x18000bdad  push    rbp
0x18000bdae  push    rsi
0x18000bdaf  push    rdi
0x18000bdb0  push    r12
0x18000bdb2  push    r13
0x18000bdb4  push    r14
0x18000bdb6  push    r15
0x18000bdb8  lea     rbp, [rsp-13C0h]
0x18000bdc0  mov     eax, 14C0h
0x18000bdc5  call    _alloca_probe
0x18000bdca  sub     rsp, rax
0x18000bdcd  mov     r14, r8
0x18000bdd0  mov     esi, edx
0x18000bdd2  mov     r15, rcx
0x18000bdd5  mov     rdi, [rbp+13F0h+arg_28]
0x18000bddc  xor     r13d, r13d
0x18000bddf  cmp     cs:g_pfnThrowPlatformException, r13
0x18000bde6  setnz   r12b
0x18000bdea  xor     edx, edx; Val
0x18000bdec  mov     r8d, 98h; Size
0x18000bdf2  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000bdf7  call    memset_0
0x18000bdfc  nop
0x18000bdfd  mov     [rbp+13F0h+OutputString], r13w
0x18000be05  mov     [rbp+13F0h+var_1430], r13b
0x18000be09  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000be10  mov     ecx, [rdx]; this
0x18000be12  mov     [rsp+14F0h+var_14C8], ecx
0x18000be16  mov     eax, [rdx+4]
0x18000be19  mov     [rsp+14F0h+var_14C4], eax
0x18000be1d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000be22  mov     ebx, eax
0x18000be24  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000be29  mov     ecx, r13d
0x18000be2c  lea     eax, [r13+8]
0x18000be30  cmp     dword ptr [rdx+8], 1
0x18000be34  cmovz   ecx, eax
0x18000be37  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000be3b  lea     ecx, [rax-7]
0x18000be3e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000be46  inc     ecx
0x18000be48  mov     [rsp+14F0h+var_14C0], ecx
0x18000be4c  mov     [rsp+14F0h+var_14B8], r13
0x18000be51  call    cs:__imp_GetCurrentThreadId
0x18000be57  mov     [rsp+14F0h+var_14B0], eax
0x18000be5b  mov     [rsp+14F0h+var_1498], r14
0x18000be60  mov     [rsp+14F0h+var_1490], esi
0x18000be64  mov     [rsp+14F0h+var_148C], ebx
0x18000be68  mov     [rsp+14F0h+var_14A8], r13
0x18000be6d  mov     [rsp+14F0h+var_14A0], r13
0x18000be72  mov     [rbp+13F0h+var_1448], rdi
0x18000be76  mov     [rbp+13F0h+var_1440], r15
0x18000be7a  mov     [rsp+14F0h+var_1488], r13
0x18000be7f  xorps   xmm0, xmm0
0x18000be82  xor     eax, eax
0x18000be84  movups  [rbp+13F0h+var_1468], xmm0
0x18000be88  mov     [rbp+13F0h+var_1458], rax
0x18000be8c  xorps   xmm1, xmm1
0x18000be8f  movups  [rsp+14F0h+var_1480], xmm1
0x18000be94  mov     [rbp+13F0h+var_1470], rax
0x18000be98  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000be9f  test    rax, rax
0x18000bea2  jz      short loc_18000BEAF
0x18000bea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bea9  mov     [rbp+13F0h+var_1450], rax
0x18000bead  jmp     short loc_18000BEB3
0x18000beaf  mov     [rbp+13F0h+var_1450], r13
0x18000beb3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000beba  test    rax, rax
0x18000bebd  jz      short loc_18000BEC9
0x18000bebf  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bec9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000bed0  test    rax, rax
0x18000bed3  jz      short loc_18000BEE9
0x18000bed5  mov     r8d, 400h
0x18000bedb  lea     rdx, [rbp+13F0h+var_1430]
0x18000bedf  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bee9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000bef0  test    rax, rax
0x18000bef3  jz      short loc_18000BEFF
0x18000bef5  lea     rcx, [rsp+14F0h+var_14D0]
0x18000befa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000beff  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000bf06  test    rax, rax
0x18000bf09  jz      short loc_18000BF21
0x18000bf0b  test    r12b, r12b
0x18000bf0e  jnz     short loc_18000BF21
0x18000bf10  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000bf15  jnz     short loc_18000BF21
0x18000bf17  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bf1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf21  cmp     [rsp+14F0h+var_14C8], r13d
0x18000bf26  jl      short loc_18000BF2E
0x18000bf28  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000bf2e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000bf35  jnz     short loc_18000BF56
0x18000bf37  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000bf3e  test    rax, rax
0x18000bf41  jz      short loc_18000BF4C
0x18000bf43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf48  test    al, al
0x18000bf4a  jmp     short loc_18000BF54
0x18000bf4c  call    cs:__imp_IsDebuggerPresent
0x18000bf52  test    eax, eax
0x18000bf54  jz      short loc_18000BF5F
0x18000bf56  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000bf5b  mov     bl, 1
0x18000bf5d  jz      short loc_18000BF62
0x18000bf5f  mov     bl, r13b
0x18000bf62  test    r12b, r12b
0x18000bf65  jnz     short loc_18000BF91
0x18000bf67  test    bl, bl
0x18000bf69  jnz     short loc_18000BF91
0x18000bf6b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bf72  test    rax, rax
0x18000bf75  jz      short loc_18000BFEE
0x18000bf77  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000bf7e  jnz     short loc_18000BFEE
0x18000bf80  xor     r8d, r8d
0x18000bf83  xor     edx, edx
0x18000bf85  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bf8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf8f  jmp     short loc_18000BFEE
0x18000bf91  mov     edi, 800h
0x18000bf96  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bf9d  test    rax, rax
0x18000bfa0  jz      short loc_18000BFBF
0x18000bfa2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000bfa9  jnz     short loc_18000BFBF
0x18000bfab  mov     r8d, edi
0x18000bfae  lea     rdx, [rbp+13F0h+OutputString]
0x18000bfb5  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bfba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfbf  cmp     [rbp+13F0h+OutputString], r13w
0x18000bfc7  jnz     short loc_18000BFDD
0x18000bfc9  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000bfce  mov     rdx, rdi; wchar_t *
0x18000bfd1  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000bfd8  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000bfdd  test    bl, bl
0x18000bfdf  jz      short loc_18000BFEE
0x18000bfe1  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000bfe8  call    cs:__imp_OutputDebugStringW
0x18000bfee  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000bff3  jnz     short loc_18000BFFE
0x18000bff5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000bffc  jz      short loc_18000C010
0x18000bffe  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000c005  test    rax, rax
0x18000c008  jz      short loc_18000C010
0x18000c00a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c00f  nop
0x18000c010  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000c015  jz      short loc_18000C022
0x18000c017  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000c01c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000c022  test    r12b, r12b
0x18000c025  jz      short loc_18000C03F
0x18000c027  lea     rdx, [rbp+13F0h+OutputString]
0x18000c02e  lea     rcx, [rsp+14F0h+var_14D0]
0x18000c033  mov     rax, cs:g_pfnThrowPlatformException
0x18000c03a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c03f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000c044  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000c049  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000c04e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
