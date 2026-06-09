# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x1800346c0`
- end: `0x18003498e`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `718`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180034994`

## callees

- `0x180006224`
- `0x180006690`
- `0x180007378`
- `0x180007630`
- `0x180007894`
- `0x1800346c0`
- `0x18005c570`
- `0x18005c5e0`
- `0x18005c660`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034781`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034781`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180034922`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180034922`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003487e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003487e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      g_pfnResultLoggingCallback(v21, OutputString, 2048, v18);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)v21, v18);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(v21, 0, 0, v18);
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
0x1800346c0  mov     [rsp-8+arg_18], rbx
0x1800346c5  push    rbp
0x1800346c6  push    rsi
0x1800346c7  push    rdi
0x1800346c8  push    r12
0x1800346ca  push    r13
0x1800346cc  push    r14
0x1800346ce  push    r15
0x1800346d0  lea     rbp, [rsp-13C0h]
0x1800346d8  mov     eax, 14C0h
0x1800346dd  call    _alloca_probe
0x1800346e2  sub     rsp, rax
0x1800346e5  mov     r14, r8
0x1800346e8  mov     esi, edx
0x1800346ea  mov     rbx, rcx
0x1800346ed  mov     r15, [rbp+13F0h+arg_28]
0x1800346f4  xor     r13d, r13d
0x1800346f7  cmp     cs:g_pfnThrowPlatformException, r13
0x1800346fe  setnz   dil
0x180034702  xor     edx, edx; Val
0x180034704  mov     r8d, 98h; Size
0x18003470a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18003470f  call    memset
0x180034714  nop
0x180034715  mov     [rbp+13F0h+OutputString], r13w
0x18003471d  mov     [rbp+13F0h+var_1430], r13b
0x180034721  mov     rdx, [rbp+13F0h+arg_30]; int
0x180034728  mov     ecx, [rdx]; this
0x18003472a  mov     [rsp+14F0h+var_14C8], ecx
0x18003472e  mov     eax, [rdx+4]
0x180034731  mov     [rsp+14F0h+var_14C4], eax
0x180034735  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18003473a  mov     r12d, eax
0x18003473d  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180034742  mov     ecx, r13d
0x180034745  lea     eax, [r13+8]
0x180034749  cmp     dword ptr [rdx+8], 1
0x18003474d  cmovz   ecx, eax
0x180034750  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180034754  lea     ecx, [rax-7]
0x180034757  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003475f  inc     ecx
0x180034761  mov     [rsp+14F0h+var_14C0], ecx
0x180034765  mov     rcx, [rbp+13F0h+arg_38]
0x18003476c  test    rcx, rcx
0x18003476f  jz      short loc_18003477C
0x180034771  cmp     [rcx], r13w
0x180034775  mov     [rsp+14F0h+var_14B8], rcx
0x18003477a  jnz     short loc_180034781
0x18003477c  mov     [rsp+14F0h+var_14B8], r13
0x180034781  call    cs:__imp_GetCurrentThreadId
0x180034787  mov     [rsp+14F0h+var_14B0], eax
0x18003478b  mov     [rsp+14F0h+var_1498], r14
0x180034790  mov     [rsp+14F0h+var_1490], esi
0x180034794  mov     [rsp+14F0h+var_148C], r12d
0x180034799  mov     [rsp+14F0h+var_14A8], r13
0x18003479e  mov     [rsp+14F0h+var_14A0], r13
0x1800347a3  mov     [rbp+13F0h+var_1448], r15
0x1800347a7  mov     [rbp+13F0h+var_1440], rbx
0x1800347ab  mov     [rsp+14F0h+var_1488], r13
0x1800347b0  xorps   xmm0, xmm0
0x1800347b3  xor     eax, eax
0x1800347b5  movups  [rbp+13F0h+var_1468], xmm0
0x1800347b9  mov     [rbp+13F0h+var_1458], rax
0x1800347bd  xorps   xmm1, xmm1
0x1800347c0  movups  [rsp+14F0h+var_1480], xmm1
0x1800347c5  mov     [rbp+13F0h+var_1470], rax
0x1800347c9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800347d0  test    rax, rax
0x1800347d3  jz      short loc_1800347E0
0x1800347d5  call    _guard_dispatch_icall
0x1800347da  mov     [rbp+13F0h+var_1450], rax
0x1800347de  jmp     short loc_1800347E4
0x1800347e0  mov     [rbp+13F0h+var_1450], r13
0x1800347e4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800347eb  test    rax, rax
0x1800347ee  jz      short loc_1800347FA
0x1800347f0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800347f5  call    _guard_dispatch_icall
0x1800347fa  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180034801  test    rax, rax
0x180034804  jz      short loc_18003481A
0x180034806  mov     r8d, 400h
0x18003480c  lea     rdx, [rbp+13F0h+var_1430]
0x180034810  lea     rcx, [rsp+14F0h+var_14D0]
0x180034815  call    _guard_dispatch_icall
0x18003481a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180034821  test    rax, rax
0x180034824  jz      short loc_180034830
0x180034826  lea     rcx, [rsp+14F0h+var_14D0]
0x18003482b  call    _guard_dispatch_icall
0x180034830  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180034837  test    rax, rax
0x18003483a  jz      short loc_180034852
0x18003483c  test    dil, dil
0x18003483f  jnz     short loc_180034852
0x180034841  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180034846  jnz     short loc_180034852
0x180034848  lea     rcx, [rsp+14F0h+var_14D0]
0x18003484d  call    _guard_dispatch_icall
0x180034852  cmp     [rsp+14F0h+var_14C8], r13d
0x180034857  jl      short loc_18003485F
0x180034859  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18003485f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180034866  jnz     short loc_180034890
0x180034868  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003486f  test    rax, rax
0x180034872  jz      short loc_18003487E
0x180034874  call    _guard_dispatch_icall
0x180034879  movzx   ecx, al
0x18003487c  jmp     short loc_18003488C
0x18003487e  call    cs:__imp_IsDebuggerPresent
0x180034884  mov     ecx, r13d
0x180034887  test    eax, eax
0x180034889  setnz   cl
0x18003488c  test    ecx, ecx
0x18003488e  jz      short loc_180034899
0x180034890  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180034895  mov     bl, 1
0x180034897  jz      short loc_18003489C
0x180034899  mov     bl, r13b
0x18003489c  test    dil, dil
0x18003489f  jnz     short loc_1800348CB
0x1800348a1  test    bl, bl
0x1800348a3  jnz     short loc_1800348CB
0x1800348a5  mov     rax, cs:g_pfnResultLoggingCallback
0x1800348ac  test    rax, rax
0x1800348af  jz      short loc_180034928
0x1800348b1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800348b8  jnz     short loc_180034928
0x1800348ba  xor     r8d, r8d
0x1800348bd  xor     edx, edx
0x1800348bf  lea     rcx, [rsp+14F0h+var_14D0]
0x1800348c4  call    _guard_dispatch_icall
0x1800348c9  jmp     short loc_180034928
0x1800348cb  mov     esi, 800h
0x1800348d0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800348d7  test    rax, rax
0x1800348da  jz      short loc_1800348F9
0x1800348dc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800348e3  jnz     short loc_1800348F9
0x1800348e5  mov     r8d, esi
0x1800348e8  lea     rdx, [rbp+13F0h+OutputString]
0x1800348ef  lea     rcx, [rsp+14F0h+var_14D0]
0x1800348f4  call    _guard_dispatch_icall
0x1800348f9  cmp     [rbp+13F0h+OutputString], r13w
0x180034901  jnz     short loc_180034917
0x180034903  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180034908  mov     rdx, rsi; wchar_t *
0x18003490b  lea     rcx, [rbp+13F0h+OutputString]; this
0x180034912  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180034917  test    bl, bl
0x180034919  jz      short loc_180034928
0x18003491b  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180034922  call    cs:__imp_OutputDebugStringW
0x180034928  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18003492d  jnz     short loc_180034938
0x18003492f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180034936  jz      short loc_18003494A
0x180034938  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18003493f  test    rax, rax
0x180034942  jz      short loc_18003494A
0x180034944  call    _guard_dispatch_icall
0x180034949  nop
0x18003494a  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18003494f  jz      short loc_18003495C
0x180034951  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180034956  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18003495c  test    dil, dil
0x18003495f  jz      short loc_180034979
0x180034961  lea     rdx, [rbp+13F0h+OutputString]
0x180034968  lea     rcx, [rsp+14F0h+var_14D0]
0x18003496d  mov     rax, cs:g_pfnThrowPlatformException
0x180034974  call    _guard_dispatch_icall
0x180034979  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18003497e  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180034983  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180034988  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
