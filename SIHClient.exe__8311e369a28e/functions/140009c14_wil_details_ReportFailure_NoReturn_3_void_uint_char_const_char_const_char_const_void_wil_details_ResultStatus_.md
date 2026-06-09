# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x140009c14`
- end: `0x140009e96`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `642`
- prototype: `void __fastcall __noreturn(unsigned __int64, unsigned int, unsigned __int64, __int64, int, unsigned __int64, __int64, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140008cc0`

## callees

- `0x1400078ac`
- `0x140007cd0`
- `0x140007f10`
- `0x140008c10`
- `0x140009c14`
- `0x14004cc90`
- `0x14004cd00`
- `0x14004cd80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009ccd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009ccd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140009e63`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140009e63`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140009dd1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140009dd1`

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
0x140009c14  mov     [rsp-8+arg_18], rbx
0x140009c19  push    rbp
0x140009c1a  push    rsi
0x140009c1b  push    rdi
0x140009c1c  push    r12
0x140009c1e  push    r13
0x140009c20  push    r14
0x140009c22  push    r15
0x140009c24  lea     rbp, [rsp-13C0h]
0x140009c2c  mov     eax, 14C0h
0x140009c31  call    _alloca_probe
0x140009c36  sub     rsp, rax
0x140009c39  mov     r14, r8
0x140009c3c  mov     esi, edx
0x140009c3e  mov     rdi, rcx
0x140009c41  mov     r15, [rbp+13F0h+arg_28]
0x140009c48  xor     edx, edx; Val
0x140009c4a  mov     r8d, 98h; Size
0x140009c50  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140009c55  call    memset
0x140009c5a  nop
0x140009c5b  xor     r13d, r13d
0x140009c5e  mov     [rbp+13F0h+OutputString], r13w
0x140009c66  mov     [rbp+13F0h+var_1430], r13b
0x140009c6a  mov     rbx, [rbp+13F0h+arg_30]
0x140009c71  mov     ecx, [rbx]; this
0x140009c73  mov     [rsp+14F0h+var_14C8], ecx
0x140009c77  mov     eax, [rbx+4]
0x140009c7a  mov     [rsp+14F0h+var_14C4], eax
0x140009c7e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140009c83  mov     r12d, eax
0x140009c86  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x140009c8e  mov     ecx, r13d
0x140009c91  lea     eax, [r13+8]
0x140009c95  cmp     dword ptr [rbx+8], 1
0x140009c99  cmovz   ecx, eax
0x140009c9c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140009ca0  lea     ecx, [rax-7]
0x140009ca3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140009cab  inc     ecx
0x140009cad  mov     [rsp+14F0h+var_14C0], ecx
0x140009cb1  mov     rcx, [rbp+13F0h+arg_38]
0x140009cb8  test    rcx, rcx
0x140009cbb  jz      short loc_140009CC8
0x140009cbd  cmp     [rcx], r13w
0x140009cc1  mov     [rsp+14F0h+var_14B8], rcx
0x140009cc6  jnz     short loc_140009CCD
0x140009cc8  mov     [rsp+14F0h+var_14B8], r13
0x140009ccd  call    cs:__imp_GetCurrentThreadId
0x140009cd3  mov     [rsp+14F0h+var_14B0], eax
0x140009cd7  mov     [rsp+14F0h+var_1498], r14
0x140009cdc  mov     [rsp+14F0h+var_1490], esi
0x140009ce0  mov     [rsp+14F0h+var_148C], r12d
0x140009ce5  mov     [rsp+14F0h+var_14A8], r13
0x140009cea  mov     [rsp+14F0h+var_14A0], r13
0x140009cef  mov     [rbp+13F0h+var_1448], r15
0x140009cf3  mov     [rbp+13F0h+var_1440], rdi
0x140009cf7  mov     [rsp+14F0h+var_1488], r13
0x140009cfc  xorps   xmm0, xmm0
0x140009cff  xor     eax, eax
0x140009d01  movups  [rbp+13F0h+var_1468], xmm0
0x140009d05  mov     [rbp+13F0h+var_1458], rax
0x140009d09  xorps   xmm1, xmm1
0x140009d0c  movups  [rsp+14F0h+var_1480], xmm1
0x140009d11  mov     [rbp+13F0h+var_1470], rax
0x140009d15  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140009d1c  test    rax, rax
0x140009d1f  jz      short loc_140009D2C
0x140009d21  call    _guard_dispatch_icall
0x140009d26  mov     [rbp+13F0h+var_1450], rax
0x140009d2a  jmp     short loc_140009D30
0x140009d2c  mov     [rbp+13F0h+var_1450], r13
0x140009d30  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140009d37  test    rax, rax
0x140009d3a  jz      short loc_140009D46
0x140009d3c  lea     rcx, [rsp+14F0h+var_14D0]
0x140009d41  call    _guard_dispatch_icall
0x140009d46  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140009d4d  test    rax, rax
0x140009d50  jz      short loc_140009D66
0x140009d52  mov     r8d, 400h
0x140009d58  lea     rdx, [rbp+13F0h+var_1430]
0x140009d5c  lea     rcx, [rsp+14F0h+var_14D0]
0x140009d61  call    _guard_dispatch_icall
0x140009d66  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140009d6d  test    rax, rax
0x140009d70  jz      short loc_140009D7C
0x140009d72  lea     rcx, [rsp+14F0h+var_14D0]
0x140009d77  call    _guard_dispatch_icall
0x140009d7c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140009d83  test    rax, rax
0x140009d86  jz      short loc_140009D99
0x140009d88  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140009d8d  jnz     short loc_140009D99
0x140009d8f  lea     rcx, [rsp+14F0h+var_14D0]
0x140009d94  call    _guard_dispatch_icall
0x140009d99  cmp     [rsp+14F0h+var_14C8], r13d
0x140009d9e  jl      short loc_140009DB2
0x140009da0  mov     ecx, 8000FFFFh; this
0x140009da5  mov     [rsp+14F0h+var_14C8], ecx
0x140009da9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140009dae  mov     [rsp+14F0h+var_14C4], eax
0x140009db2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140009db9  jnz     short loc_140009DE3
0x140009dbb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140009dc2  test    rax, rax
0x140009dc5  jz      short loc_140009DD1
0x140009dc7  call    _guard_dispatch_icall
0x140009dcc  movzx   ecx, al
0x140009dcf  jmp     short loc_140009DDF
0x140009dd1  call    cs:__imp_IsDebuggerPresent
0x140009dd7  mov     ecx, r13d
0x140009dda  test    eax, eax
0x140009ddc  setnz   cl
0x140009ddf  test    ecx, ecx
0x140009de1  jz      short loc_140009DEA
0x140009de3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140009de8  jz      short loc_140009E10
0x140009dea  mov     rax, cs:g_pfnResultLoggingCallback
0x140009df1  test    rax, rax
0x140009df4  jz      short loc_140009E69
0x140009df6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140009dfd  jnz     short loc_140009E69
0x140009dff  xor     r8d, r8d
0x140009e02  xor     edx, edx
0x140009e04  lea     rcx, [rsp+14F0h+var_14D0]
0x140009e09  call    _guard_dispatch_icall
0x140009e0e  jmp     short loc_140009E69
0x140009e10  mov     ebx, 800h
0x140009e15  mov     rax, cs:g_pfnResultLoggingCallback
0x140009e1c  test    rax, rax
0x140009e1f  jz      short loc_140009E3E
0x140009e21  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140009e28  jnz     short loc_140009E3E
0x140009e2a  mov     r8d, ebx
0x140009e2d  lea     rdx, [rbp+13F0h+OutputString]
0x140009e34  lea     rcx, [rsp+14F0h+var_14D0]
0x140009e39  call    _guard_dispatch_icall
0x140009e3e  cmp     [rbp+13F0h+OutputString], r13w
0x140009e46  jnz     short loc_140009E5C
0x140009e48  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140009e4d  mov     rdx, rbx; wchar_t *
0x140009e50  lea     rcx, [rbp+13F0h+OutputString]; this
0x140009e57  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140009e5c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140009e63  call    cs:__imp_OutputDebugStringW
0x140009e69  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140009e6e  jnz     short loc_140009E79
0x140009e70  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140009e77  jz      short loc_140009E8B
0x140009e79  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140009e80  test    rax, rax
0x140009e83  jz      short loc_140009E8B
0x140009e85  call    _guard_dispatch_icall
0x140009e8a  nop
0x140009e8b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140009e90  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
