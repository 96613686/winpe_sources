# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x18001b8c8`
- end: `0x18001bb96`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `718`
- prototype: `void __fastcall __noreturn(unsigned __int64, unsigned int, unsigned __int64, __int64, int, unsigned __int64, unsigned __int64 *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001bb9c`

## callees

- `0x180002234`
- `0x180002484`
- `0x1800025bc`
- `0x180002bb0`
- `0x180004988`
- `0x18001b8c8`
- `0x180068e30`
- `0x180068ea0`
- `0x180068f20`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001ba86`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001ba86`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001bb2a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001bb2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b989`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b989`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        unsigned __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int64 a6,
        unsigned __int64 *a7,
        _WORD *a8)
{
  bool v11; // di
  unsigned int v12; // r12d
  int v13; // ecx
  __int64 v14; // rdx
  bool v15; // zf
  const struct wil::FailureInfo *v16; // rdx
  unsigned __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v18; // r9
  char v19; // bl
  const struct wil::FailureInfo *v20; // rdx
  unsigned __int64 v21[20]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v22[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v11 = g_pfnThrowPlatformException != 0;
  memset(v21, 0, 0x98u);
  OutputString[0] = 0;
  v22[0] = 0;
  v21[1] = *a7;
  v12 = wil::details::RecordException((wil::details *)LODWORD(v21[1]), (int)a7);
  LODWORD(v21[0]) = 0;
  v13 = 0;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  HIDWORD(v21[0]) = v13;
  LODWORD(v21[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v15 = *a8 == 0, v21[3] = (unsigned __int64)a8, v15) )
    v21[3] = 0;
  LODWORD(v21[4]) = GetCurrentThreadId();
  v21[7] = a3;
  v21[8] = __PAIR64__(v12, a2);
  v21[5] = 0;
  v21[6] = 0;
  v21[17] = a6;
  v21[18] = a1;
  memset(&v21[9], 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    v21[16] = wil::details::g_pfnGetModuleName(IsDebuggerPresent);
  else
    v21[16] = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v21);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v21, v22, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v21);
  if ( wil::details::g_pfnOriginateCallback && !v11 && (v21[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v21);
  if ( SLODWORD(v21[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)IsDebuggerPresent);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (IsDebuggerPresent = ::IsDebuggerPresent())
      : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
        !(_DWORD)IsDebuggerPresent)
    || (v19 = 1, (v21[0] & 0x200000000LL) != 0) )
  {
    v19 = 0;
  }
  if ( v11 || v19 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v21, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)v21, v18);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(v21, 0, 0);
  }
  if ( ((v21[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  if ( (v21[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v21, v16);
  if ( v11 )
    ((void (__fastcall *)(unsigned __int64 *, WCHAR *))g_pfnThrowPlatformException)(v21, OutputString);
  wil::ThrowResultException((wil *)v21, v16);
  wil::details::WilFailFast((wil::details *)v21, v20);
}

```

## disassembly

```asm
0x18001b8c8  mov     [rsp-8+arg_18], rbx
0x18001b8cd  push    rbp
0x18001b8ce  push    rsi
0x18001b8cf  push    rdi
0x18001b8d0  push    r12
0x18001b8d2  push    r13
0x18001b8d4  push    r14
0x18001b8d6  push    r15
0x18001b8d8  lea     rbp, [rsp-13C0h]
0x18001b8e0  mov     eax, 14C0h
0x18001b8e5  call    _alloca_probe
0x18001b8ea  sub     rsp, rax
0x18001b8ed  mov     r14, r8
0x18001b8f0  mov     esi, edx
0x18001b8f2  mov     rbx, rcx
0x18001b8f5  mov     r15, [rbp+13F0h+arg_28]
0x18001b8fc  xor     r13d, r13d
0x18001b8ff  cmp     cs:g_pfnThrowPlatformException, r13
0x18001b906  setnz   dil
0x18001b90a  xor     edx, edx; Val
0x18001b90c  mov     r8d, 98h; Size
0x18001b912  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18001b917  call    memset
0x18001b91c  nop
0x18001b91d  mov     [rbp+13F0h+OutputString], r13w
0x18001b925  mov     [rbp+13F0h+var_1430], r13b
0x18001b929  mov     rdx, [rbp+13F0h+arg_30]; int
0x18001b930  mov     ecx, [rdx]; this
0x18001b932  mov     [rsp+14F0h+var_14C8], ecx
0x18001b936  mov     eax, [rdx+4]
0x18001b939  mov     [rsp+14F0h+var_14C4], eax
0x18001b93d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001b942  mov     r12d, eax
0x18001b945  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18001b94a  mov     ecx, r13d
0x18001b94d  lea     eax, [r13+8]
0x18001b951  cmp     dword ptr [rdx+8], 1
0x18001b955  cmovz   ecx, eax
0x18001b958  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18001b95c  lea     ecx, [rax-7]
0x18001b95f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001b967  inc     ecx
0x18001b969  mov     [rsp+14F0h+var_14C0], ecx
0x18001b96d  mov     rcx, [rbp+13F0h+arg_38]
0x18001b974  test    rcx, rcx
0x18001b977  jz      short loc_18001B984
0x18001b979  cmp     [rcx], r13w
0x18001b97d  mov     [rsp+14F0h+var_14B8], rcx
0x18001b982  jnz     short loc_18001B989
0x18001b984  mov     [rsp+14F0h+var_14B8], r13
0x18001b989  call    cs:__imp_GetCurrentThreadId
0x18001b98f  mov     [rsp+14F0h+var_14B0], eax
0x18001b993  mov     [rsp+14F0h+var_1498], r14
0x18001b998  mov     [rsp+14F0h+var_1490], esi
0x18001b99c  mov     [rsp+14F0h+var_148C], r12d
0x18001b9a1  mov     [rsp+14F0h+var_14A8], r13
0x18001b9a6  mov     [rsp+14F0h+var_14A0], r13
0x18001b9ab  mov     [rbp+13F0h+var_1448], r15
0x18001b9af  mov     [rbp+13F0h+var_1440], rbx
0x18001b9b3  mov     [rsp+14F0h+var_1488], r13
0x18001b9b8  xorps   xmm0, xmm0
0x18001b9bb  xor     eax, eax
0x18001b9bd  movups  [rbp+13F0h+var_1468], xmm0
0x18001b9c1  mov     [rbp+13F0h+var_1458], rax
0x18001b9c5  xorps   xmm1, xmm1
0x18001b9c8  movups  [rsp+14F0h+var_1480], xmm1
0x18001b9cd  mov     [rbp+13F0h+var_1470], rax
0x18001b9d1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001b9d8  test    rax, rax
0x18001b9db  jz      short loc_18001B9E8
0x18001b9dd  call    _guard_dispatch_icall
0x18001b9e2  mov     [rbp+13F0h+var_1450], rax
0x18001b9e6  jmp     short loc_18001B9EC
0x18001b9e8  mov     [rbp+13F0h+var_1450], r13
0x18001b9ec  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001b9f3  test    rax, rax
0x18001b9f6  jz      short loc_18001BA02
0x18001b9f8  lea     rcx, [rsp+14F0h+var_14D0]
0x18001b9fd  call    _guard_dispatch_icall
0x18001ba02  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001ba09  test    rax, rax
0x18001ba0c  jz      short loc_18001BA22
0x18001ba0e  mov     r8d, 400h
0x18001ba14  lea     rdx, [rbp+13F0h+var_1430]
0x18001ba18  lea     rcx, [rsp+14F0h+var_14D0]
0x18001ba1d  call    _guard_dispatch_icall
0x18001ba22  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001ba29  test    rax, rax
0x18001ba2c  jz      short loc_18001BA38
0x18001ba2e  lea     rcx, [rsp+14F0h+var_14D0]
0x18001ba33  call    _guard_dispatch_icall
0x18001ba38  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001ba3f  test    rax, rax
0x18001ba42  jz      short loc_18001BA5A
0x18001ba44  test    dil, dil
0x18001ba47  jnz     short loc_18001BA5A
0x18001ba49  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001ba4e  jnz     short loc_18001BA5A
0x18001ba50  lea     rcx, [rsp+14F0h+var_14D0]
0x18001ba55  call    _guard_dispatch_icall
0x18001ba5a  cmp     [rsp+14F0h+var_14C8], r13d
0x18001ba5f  jl      short loc_18001BA67
0x18001ba61  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001ba67  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18001ba6e  jnz     short loc_18001BA98
0x18001ba70  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001ba77  test    rax, rax
0x18001ba7a  jz      short loc_18001BA86
0x18001ba7c  call    _guard_dispatch_icall
0x18001ba81  movzx   ecx, al
0x18001ba84  jmp     short loc_18001BA94
0x18001ba86  call    cs:__imp_IsDebuggerPresent
0x18001ba8c  mov     ecx, r13d
0x18001ba8f  test    eax, eax
0x18001ba91  setnz   cl
0x18001ba94  test    ecx, ecx
0x18001ba96  jz      short loc_18001BAA1
0x18001ba98  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001ba9d  mov     bl, 1
0x18001ba9f  jz      short loc_18001BAA4
0x18001baa1  mov     bl, r13b
0x18001baa4  test    dil, dil
0x18001baa7  jnz     short loc_18001BAD3
0x18001baa9  test    bl, bl
0x18001baab  jnz     short loc_18001BAD3
0x18001baad  mov     rax, cs:g_pfnResultLoggingCallback
0x18001bab4  test    rax, rax
0x18001bab7  jz      short loc_18001BB30
0x18001bab9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18001bac0  jnz     short loc_18001BB30
0x18001bac2  xor     r8d, r8d
0x18001bac5  xor     edx, edx
0x18001bac7  lea     rcx, [rsp+14F0h+var_14D0]
0x18001bacc  call    _guard_dispatch_icall
0x18001bad1  jmp     short loc_18001BB30
0x18001bad3  mov     esi, 800h
0x18001bad8  mov     rax, cs:g_pfnResultLoggingCallback
0x18001badf  test    rax, rax
0x18001bae2  jz      short loc_18001BB01
0x18001bae4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18001baeb  jnz     short loc_18001BB01
0x18001baed  mov     r8d, esi
0x18001baf0  lea     rdx, [rbp+13F0h+OutputString]
0x18001baf7  lea     rcx, [rsp+14F0h+var_14D0]
0x18001bafc  call    _guard_dispatch_icall
0x18001bb01  cmp     [rbp+13F0h+OutputString], r13w
0x18001bb09  jnz     short loc_18001BB1F
0x18001bb0b  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18001bb10  mov     rdx, rsi; wchar_t *
0x18001bb13  lea     rcx, [rbp+13F0h+OutputString]; this
0x18001bb1a  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18001bb1f  test    bl, bl
0x18001bb21  jz      short loc_18001BB30
0x18001bb23  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18001bb2a  call    cs:__imp_OutputDebugStringW
0x18001bb30  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18001bb35  jnz     short loc_18001BB40
0x18001bb37  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18001bb3e  jz      short loc_18001BB52
0x18001bb40  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001bb47  test    rax, rax
0x18001bb4a  jz      short loc_18001BB52
0x18001bb4c  call    _guard_dispatch_icall
0x18001bb51  nop
0x18001bb52  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18001bb57  jz      short loc_18001BB64
0x18001bb59  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001bb5e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001bb64  test    dil, dil
0x18001bb67  jz      short loc_18001BB81
0x18001bb69  lea     rdx, [rbp+13F0h+OutputString]
0x18001bb70  lea     rcx, [rsp+14F0h+var_14D0]
0x18001bb75  mov     rax, cs:g_pfnThrowPlatformException
0x18001bb7c  call    _guard_dispatch_icall
0x18001bb81  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001bb86  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18001bb8b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001bb90  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
