# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180005a78`
- end: `0x180005cfa`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `642`
- prototype: `void __fastcall __noreturn(unsigned __int64, unsigned int, unsigned __int64, __int64, int, unsigned __int64, __int64, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180004c40`

## callees

- `0x180002470`
- `0x1800025bc`
- `0x180002bb0`
- `0x180002f28`
- `0x180005a78`
- `0x180068e30`
- `0x180068ea0`
- `0x180068f20`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005c35`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005c35`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005cc7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005cc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005b31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005b31`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        unsigned __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int64 a6,
        __int64 a7,
        _WORD *a8)
{
  int v11; // edx
  unsigned int v12; // r12d
  int v13; // ecx
  bool v14; // zf
  const struct wil::FailureInfo *v15; // rdx
  __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v17; // r9
  unsigned __int64 v18[20]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v19[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset(v18, 0, 0x98u);
  OutputString[0] = 0;
  v19[0] = 0;
  v18[1] = *(_QWORD *)a7;
  v12 = wil::details::RecordFailFast((wil::details *)LODWORD(v18[1]), v11);
  LODWORD(v18[0]) = 3;
  v13 = 0;
  if ( *(_DWORD *)(a7 + 8) == 1 )
    v13 = 8;
  HIDWORD(v18[0]) = v13;
  LODWORD(v18[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v14 = *a8 == 0, v18[3] = (unsigned __int64)a8, v14) )
    v18[3] = 0;
  LODWORD(v18[4]) = GetCurrentThreadId();
  v18[7] = a3;
  v18[8] = __PAIR64__(v12, a2);
  v18[5] = 0;
  v18[6] = 0;
  v18[17] = a6;
  v18[18] = a1;
  memset(&v18[9], 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    v18[16] = wil::details::g_pfnGetModuleName(IsDebuggerPresent);
  else
    v18[16] = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v18, v19, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v18);
  if ( wil::details::g_pfnOriginateCallback && (v18[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v18);
  if ( SLODWORD(v18[1]) >= 0 )
  {
    LODWORD(v18[1]) = -2147418113;
    HIDWORD(v18[1]) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v15);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
         (_DWORD)IsDebuggerPresent))
    && (v18[0] & 0x200000000LL) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)v18, v17);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(v18, 0, 0);
  }
  if ( (v18[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  }
  wil::details::WilFailFast((wil::details *)v18, v15);
}

```

## disassembly

```asm
0x180005a78  mov     [rsp-8+arg_18], rbx
0x180005a7d  push    rbp
0x180005a7e  push    rsi
0x180005a7f  push    rdi
0x180005a80  push    r12
0x180005a82  push    r13
0x180005a84  push    r14
0x180005a86  push    r15
0x180005a88  lea     rbp, [rsp-13C0h]
0x180005a90  mov     eax, 14C0h
0x180005a95  call    _alloca_probe
0x180005a9a  sub     rsp, rax
0x180005a9d  mov     r14, r8
0x180005aa0  mov     esi, edx
0x180005aa2  mov     rdi, rcx
0x180005aa5  mov     r15, [rbp+13F0h+arg_28]
0x180005aac  xor     edx, edx; Val
0x180005aae  mov     r8d, 98h; Size
0x180005ab4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180005ab9  call    memset
0x180005abe  nop
0x180005abf  xor     r13d, r13d
0x180005ac2  mov     [rbp+13F0h+OutputString], r13w
0x180005aca  mov     [rbp+13F0h+var_1430], r13b
0x180005ace  mov     rbx, [rbp+13F0h+arg_30]
0x180005ad5  mov     ecx, [rbx]; this
0x180005ad7  mov     [rsp+14F0h+var_14C8], ecx
0x180005adb  mov     eax, [rbx+4]
0x180005ade  mov     [rsp+14F0h+var_14C4], eax
0x180005ae2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005ae7  mov     r12d, eax
0x180005aea  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180005af2  mov     ecx, r13d
0x180005af5  lea     eax, [r13+8]
0x180005af9  cmp     dword ptr [rbx+8], 1
0x180005afd  cmovz   ecx, eax
0x180005b00  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180005b04  lea     ecx, [rax-7]
0x180005b07  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005b0f  inc     ecx
0x180005b11  mov     [rsp+14F0h+var_14C0], ecx
0x180005b15  mov     rcx, [rbp+13F0h+arg_38]
0x180005b1c  test    rcx, rcx
0x180005b1f  jz      short loc_180005B2C
0x180005b21  cmp     [rcx], r13w
0x180005b25  mov     [rsp+14F0h+var_14B8], rcx
0x180005b2a  jnz     short loc_180005B31
0x180005b2c  mov     [rsp+14F0h+var_14B8], r13
0x180005b31  call    cs:__imp_GetCurrentThreadId
0x180005b37  mov     [rsp+14F0h+var_14B0], eax
0x180005b3b  mov     [rsp+14F0h+var_1498], r14
0x180005b40  mov     [rsp+14F0h+var_1490], esi
0x180005b44  mov     [rsp+14F0h+var_148C], r12d
0x180005b49  mov     [rsp+14F0h+var_14A8], r13
0x180005b4e  mov     [rsp+14F0h+var_14A0], r13
0x180005b53  mov     [rbp+13F0h+var_1448], r15
0x180005b57  mov     [rbp+13F0h+var_1440], rdi
0x180005b5b  mov     [rsp+14F0h+var_1488], r13
0x180005b60  xorps   xmm0, xmm0
0x180005b63  xor     eax, eax
0x180005b65  movups  [rbp+13F0h+var_1468], xmm0
0x180005b69  mov     [rbp+13F0h+var_1458], rax
0x180005b6d  xorps   xmm1, xmm1
0x180005b70  movups  [rsp+14F0h+var_1480], xmm1
0x180005b75  mov     [rbp+13F0h+var_1470], rax
0x180005b79  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005b80  test    rax, rax
0x180005b83  jz      short loc_180005B90
0x180005b85  call    _guard_dispatch_icall
0x180005b8a  mov     [rbp+13F0h+var_1450], rax
0x180005b8e  jmp     short loc_180005B94
0x180005b90  mov     [rbp+13F0h+var_1450], r13
0x180005b94  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005b9b  test    rax, rax
0x180005b9e  jz      short loc_180005BAA
0x180005ba0  lea     rcx, [rsp+14F0h+var_14D0]
0x180005ba5  call    _guard_dispatch_icall
0x180005baa  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005bb1  test    rax, rax
0x180005bb4  jz      short loc_180005BCA
0x180005bb6  mov     r8d, 400h
0x180005bbc  lea     rdx, [rbp+13F0h+var_1430]
0x180005bc0  lea     rcx, [rsp+14F0h+var_14D0]
0x180005bc5  call    _guard_dispatch_icall
0x180005bca  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005bd1  test    rax, rax
0x180005bd4  jz      short loc_180005BE0
0x180005bd6  lea     rcx, [rsp+14F0h+var_14D0]
0x180005bdb  call    _guard_dispatch_icall
0x180005be0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005be7  test    rax, rax
0x180005bea  jz      short loc_180005BFD
0x180005bec  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005bf1  jnz     short loc_180005BFD
0x180005bf3  lea     rcx, [rsp+14F0h+var_14D0]
0x180005bf8  call    _guard_dispatch_icall
0x180005bfd  cmp     [rsp+14F0h+var_14C8], r13d
0x180005c02  jl      short loc_180005C16
0x180005c04  mov     ecx, 8000FFFFh; this
0x180005c09  mov     [rsp+14F0h+var_14C8], ecx
0x180005c0d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005c12  mov     [rsp+14F0h+var_14C4], eax
0x180005c16  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180005c1d  jnz     short loc_180005C47
0x180005c1f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005c26  test    rax, rax
0x180005c29  jz      short loc_180005C35
0x180005c2b  call    _guard_dispatch_icall
0x180005c30  movzx   ecx, al
0x180005c33  jmp     short loc_180005C43
0x180005c35  call    cs:__imp_IsDebuggerPresent
0x180005c3b  mov     ecx, r13d
0x180005c3e  test    eax, eax
0x180005c40  setnz   cl
0x180005c43  test    ecx, ecx
0x180005c45  jz      short loc_180005C4E
0x180005c47  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005c4c  jz      short loc_180005C74
0x180005c4e  mov     rax, cs:g_pfnResultLoggingCallback
0x180005c55  test    rax, rax
0x180005c58  jz      short loc_180005CCD
0x180005c5a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005c61  jnz     short loc_180005CCD
0x180005c63  xor     r8d, r8d
0x180005c66  xor     edx, edx
0x180005c68  lea     rcx, [rsp+14F0h+var_14D0]
0x180005c6d  call    _guard_dispatch_icall
0x180005c72  jmp     short loc_180005CCD
0x180005c74  mov     ebx, 800h
0x180005c79  mov     rax, cs:g_pfnResultLoggingCallback
0x180005c80  test    rax, rax
0x180005c83  jz      short loc_180005CA2
0x180005c85  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005c8c  jnz     short loc_180005CA2
0x180005c8e  mov     r8d, ebx
0x180005c91  lea     rdx, [rbp+13F0h+OutputString]
0x180005c98  lea     rcx, [rsp+14F0h+var_14D0]
0x180005c9d  call    _guard_dispatch_icall
0x180005ca2  cmp     [rbp+13F0h+OutputString], r13w
0x180005caa  jnz     short loc_180005CC0
0x180005cac  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180005cb1  mov     rdx, rbx; wchar_t *
0x180005cb4  lea     rcx, [rbp+13F0h+OutputString]; this
0x180005cbb  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180005cc0  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180005cc7  call    cs:__imp_OutputDebugStringW
0x180005ccd  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180005cd2  jnz     short loc_180005CDD
0x180005cd4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180005cdb  jz      short loc_180005CEF
0x180005cdd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005ce4  test    rax, rax
0x180005ce7  jz      short loc_180005CEF
0x180005ce9  call    _guard_dispatch_icall
0x180005cee  nop
0x180005cef  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005cf4  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
