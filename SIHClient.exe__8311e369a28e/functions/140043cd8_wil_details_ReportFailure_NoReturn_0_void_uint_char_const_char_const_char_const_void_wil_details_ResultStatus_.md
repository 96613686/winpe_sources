# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x140043cd8`
- end: `0x140043fa6`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `718`
- prototype: `void __fastcall __noreturn(unsigned __int64, unsigned int, unsigned __int64, __int64, int, unsigned __int64, unsigned __int64 *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140043fac`

## callees

- `0x1400078ac`
- `0x140007c74`
- `0x140008958`
- `0x140008c10`
- `0x140008e74`
- `0x140043cd8`
- `0x14004cc90`
- `0x14004cd00`
- `0x14004cd80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140043d99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140043d99`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140043f3a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140043f3a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140043e96`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140043e96`

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
0x140043cd8  mov     [rsp-8+arg_18], rbx
0x140043cdd  push    rbp
0x140043cde  push    rsi
0x140043cdf  push    rdi
0x140043ce0  push    r12
0x140043ce2  push    r13
0x140043ce4  push    r14
0x140043ce6  push    r15
0x140043ce8  lea     rbp, [rsp-13C0h]
0x140043cf0  mov     eax, 14C0h
0x140043cf5  call    _alloca_probe
0x140043cfa  sub     rsp, rax
0x140043cfd  mov     r14, r8
0x140043d00  mov     esi, edx
0x140043d02  mov     rbx, rcx
0x140043d05  mov     r15, [rbp+13F0h+arg_28]
0x140043d0c  xor     r13d, r13d
0x140043d0f  cmp     cs:g_pfnThrowPlatformException, r13
0x140043d16  setnz   dil
0x140043d1a  xor     edx, edx; Val
0x140043d1c  mov     r8d, 98h; Size
0x140043d22  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140043d27  call    memset
0x140043d2c  nop
0x140043d2d  mov     [rbp+13F0h+OutputString], r13w
0x140043d35  mov     [rbp+13F0h+var_1430], r13b
0x140043d39  mov     rdx, [rbp+13F0h+arg_30]; int
0x140043d40  mov     ecx, [rdx]; this
0x140043d42  mov     [rsp+14F0h+var_14C8], ecx
0x140043d46  mov     eax, [rdx+4]
0x140043d49  mov     [rsp+14F0h+var_14C4], eax
0x140043d4d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140043d52  mov     r12d, eax
0x140043d55  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x140043d5a  mov     ecx, r13d
0x140043d5d  lea     eax, [r13+8]
0x140043d61  cmp     dword ptr [rdx+8], 1
0x140043d65  cmovz   ecx, eax
0x140043d68  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140043d6c  lea     ecx, [rax-7]
0x140043d6f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140043d77  inc     ecx
0x140043d79  mov     [rsp+14F0h+var_14C0], ecx
0x140043d7d  mov     rcx, [rbp+13F0h+arg_38]
0x140043d84  test    rcx, rcx
0x140043d87  jz      short loc_140043D94
0x140043d89  cmp     [rcx], r13w
0x140043d8d  mov     [rsp+14F0h+var_14B8], rcx
0x140043d92  jnz     short loc_140043D99
0x140043d94  mov     [rsp+14F0h+var_14B8], r13
0x140043d99  call    cs:__imp_GetCurrentThreadId
0x140043d9f  mov     [rsp+14F0h+var_14B0], eax
0x140043da3  mov     [rsp+14F0h+var_1498], r14
0x140043da8  mov     [rsp+14F0h+var_1490], esi
0x140043dac  mov     [rsp+14F0h+var_148C], r12d
0x140043db1  mov     [rsp+14F0h+var_14A8], r13
0x140043db6  mov     [rsp+14F0h+var_14A0], r13
0x140043dbb  mov     [rbp+13F0h+var_1448], r15
0x140043dbf  mov     [rbp+13F0h+var_1440], rbx
0x140043dc3  mov     [rsp+14F0h+var_1488], r13
0x140043dc8  xorps   xmm0, xmm0
0x140043dcb  xor     eax, eax
0x140043dcd  movups  [rbp+13F0h+var_1468], xmm0
0x140043dd1  mov     [rbp+13F0h+var_1458], rax
0x140043dd5  xorps   xmm1, xmm1
0x140043dd8  movups  [rsp+14F0h+var_1480], xmm1
0x140043ddd  mov     [rbp+13F0h+var_1470], rax
0x140043de1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140043de8  test    rax, rax
0x140043deb  jz      short loc_140043DF8
0x140043ded  call    _guard_dispatch_icall
0x140043df2  mov     [rbp+13F0h+var_1450], rax
0x140043df6  jmp     short loc_140043DFC
0x140043df8  mov     [rbp+13F0h+var_1450], r13
0x140043dfc  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140043e03  test    rax, rax
0x140043e06  jz      short loc_140043E12
0x140043e08  lea     rcx, [rsp+14F0h+var_14D0]
0x140043e0d  call    _guard_dispatch_icall
0x140043e12  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140043e19  test    rax, rax
0x140043e1c  jz      short loc_140043E32
0x140043e1e  mov     r8d, 400h
0x140043e24  lea     rdx, [rbp+13F0h+var_1430]
0x140043e28  lea     rcx, [rsp+14F0h+var_14D0]
0x140043e2d  call    _guard_dispatch_icall
0x140043e32  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140043e39  test    rax, rax
0x140043e3c  jz      short loc_140043E48
0x140043e3e  lea     rcx, [rsp+14F0h+var_14D0]
0x140043e43  call    _guard_dispatch_icall
0x140043e48  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140043e4f  test    rax, rax
0x140043e52  jz      short loc_140043E6A
0x140043e54  test    dil, dil
0x140043e57  jnz     short loc_140043E6A
0x140043e59  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140043e5e  jnz     short loc_140043E6A
0x140043e60  lea     rcx, [rsp+14F0h+var_14D0]
0x140043e65  call    _guard_dispatch_icall
0x140043e6a  cmp     [rsp+14F0h+var_14C8], r13d
0x140043e6f  jl      short loc_140043E77
0x140043e71  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140043e77  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140043e7e  jnz     short loc_140043EA8
0x140043e80  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140043e87  test    rax, rax
0x140043e8a  jz      short loc_140043E96
0x140043e8c  call    _guard_dispatch_icall
0x140043e91  movzx   ecx, al
0x140043e94  jmp     short loc_140043EA4
0x140043e96  call    cs:__imp_IsDebuggerPresent
0x140043e9c  mov     ecx, r13d
0x140043e9f  test    eax, eax
0x140043ea1  setnz   cl
0x140043ea4  test    ecx, ecx
0x140043ea6  jz      short loc_140043EB1
0x140043ea8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140043ead  mov     bl, 1
0x140043eaf  jz      short loc_140043EB4
0x140043eb1  mov     bl, r13b
0x140043eb4  test    dil, dil
0x140043eb7  jnz     short loc_140043EE3
0x140043eb9  test    bl, bl
0x140043ebb  jnz     short loc_140043EE3
0x140043ebd  mov     rax, cs:g_pfnResultLoggingCallback
0x140043ec4  test    rax, rax
0x140043ec7  jz      short loc_140043F40
0x140043ec9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140043ed0  jnz     short loc_140043F40
0x140043ed2  xor     r8d, r8d
0x140043ed5  xor     edx, edx
0x140043ed7  lea     rcx, [rsp+14F0h+var_14D0]
0x140043edc  call    _guard_dispatch_icall
0x140043ee1  jmp     short loc_140043F40
0x140043ee3  mov     esi, 800h
0x140043ee8  mov     rax, cs:g_pfnResultLoggingCallback
0x140043eef  test    rax, rax
0x140043ef2  jz      short loc_140043F11
0x140043ef4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140043efb  jnz     short loc_140043F11
0x140043efd  mov     r8d, esi
0x140043f00  lea     rdx, [rbp+13F0h+OutputString]
0x140043f07  lea     rcx, [rsp+14F0h+var_14D0]
0x140043f0c  call    _guard_dispatch_icall
0x140043f11  cmp     [rbp+13F0h+OutputString], r13w
0x140043f19  jnz     short loc_140043F2F
0x140043f1b  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140043f20  mov     rdx, rsi; wchar_t *
0x140043f23  lea     rcx, [rbp+13F0h+OutputString]; this
0x140043f2a  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140043f2f  test    bl, bl
0x140043f31  jz      short loc_140043F40
0x140043f33  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140043f3a  call    cs:__imp_OutputDebugStringW
0x140043f40  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140043f45  jnz     short loc_140043F50
0x140043f47  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140043f4e  jz      short loc_140043F62
0x140043f50  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140043f57  test    rax, rax
0x140043f5a  jz      short loc_140043F62
0x140043f5c  call    _guard_dispatch_icall
0x140043f61  nop
0x140043f62  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140043f67  jz      short loc_140043F74
0x140043f69  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140043f6e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140043f74  test    dil, dil
0x140043f77  jz      short loc_140043F91
0x140043f79  lea     rdx, [rbp+13F0h+OutputString]
0x140043f80  lea     rcx, [rsp+14F0h+var_14D0]
0x140043f85  mov     rax, cs:g_pfnThrowPlatformException
0x140043f8c  call    _guard_dispatch_icall
0x140043f91  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140043f96  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x140043f9b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140043fa0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
