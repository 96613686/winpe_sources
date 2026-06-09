# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000980c`
- end: `0x180009abb`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `687`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180009088`

## callees

- `0x180006224`
- `0x1800066ac`
- `0x180007630`
- `0x180007894`
- `0x18000980c`
- `0x180056500`
- `0x18005c570`
- `0x18005c5e0`
- `0x18005c660`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800098d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800098d2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009a5a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009a5a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800099c8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800099c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        unsigned __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int64 a6,
        unsigned __int64 *a7,
        _WORD *a8)
{
  unsigned int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  bool v14; // zf
  const struct wil::FailureInfo *v15; // rdx
  unsigned __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v17; // r9
  unsigned __int64 v18[20]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v19[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset(v18, 0, 0x98u);
  OutputString[0] = 0;
  v19[0] = 0;
  v18[1] = *a7;
  v11 = wil::details::RecordReturn((wil::details *)LODWORD(v18[1]), (int)a7);
  LODWORD(v18[0]) = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  HIDWORD(v18[0]) = v12;
  LODWORD(v18[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v14 = *a8 == 0, v18[3] = (unsigned __int64)a8, v14) )
    v18[3] = 0;
  LODWORD(v18[4]) = GetCurrentThreadId();
  v18[7] = a3;
  v18[8] = __PAIR64__(v11, a2);
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)IsDebuggerPresent);
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
         (_DWORD)IsDebuggerPresent))
    && (v18[0] & 0x200000000LL) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v18, OutputString, 2048, v17);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)v18, v17);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(v18, 0, 0, v17);
  }
  if ( ((v18[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  if ( (v18[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v18, v15);
}

```

## disassembly

```asm
0x18000980c  push    rbp
0x18000980e  push    rbx
0x18000980f  push    rsi
0x180009810  push    rdi
0x180009811  push    r12
0x180009813  push    r14
0x180009815  push    r15
0x180009817  lea     rbp, [rsp-13D0h]
0x18000981f  mov     eax, 14D0h
0x180009824  call    _alloca_probe
0x180009829  sub     rsp, rax
0x18000982c  mov     rax, cs:__security_cookie
0x180009833  xor     rax, rsp
0x180009836  mov     [rbp+1400h+var_40], rax
0x18000983d  mov     rsi, r8
0x180009840  mov     edi, edx
0x180009842  mov     rbx, rcx
0x180009845  mov     r14, [rbp+1400h+arg_28]
0x18000984c  xor     edx, edx; Val
0x18000984e  mov     r8d, 98h; Size
0x180009854  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180009859  call    memset
0x18000985e  nop
0x18000985f  xor     r12d, r12d
0x180009862  mov     [rbp+1400h+OutputString], r12w
0x18000986a  mov     [rbp+1400h+var_1440], r12b
0x18000986e  mov     rdx, [rbp+1400h+arg_30]; int
0x180009875  mov     ecx, [rdx]; this
0x180009877  mov     [rsp+1500h+var_14D8], ecx
0x18000987b  mov     eax, [rdx+4]
0x18000987e  mov     [rsp+1500h+var_14D4], eax
0x180009882  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180009887  mov     r15d, eax
0x18000988a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180009892  mov     ecx, r12d
0x180009895  lea     eax, [r12+8]
0x18000989a  cmp     dword ptr [rdx+8], 1
0x18000989e  cmovz   ecx, eax
0x1800098a1  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800098a5  lea     ecx, [rax-7]
0x1800098a8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800098b0  inc     ecx
0x1800098b2  mov     [rsp+1500h+var_14D0], ecx
0x1800098b6  mov     rcx, [rbp+1400h+arg_38]
0x1800098bd  test    rcx, rcx
0x1800098c0  jz      short loc_1800098CD
0x1800098c2  cmp     [rcx], r12w
0x1800098c6  mov     [rsp+1500h+var_14C8], rcx
0x1800098cb  jnz     short loc_1800098D2
0x1800098cd  mov     [rsp+1500h+var_14C8], r12
0x1800098d2  call    cs:__imp_GetCurrentThreadId
0x1800098d8  mov     [rsp+1500h+var_14C0], eax
0x1800098dc  mov     [rsp+1500h+var_14A8], rsi
0x1800098e1  mov     [rsp+1500h+var_14A0], edi
0x1800098e5  mov     [rsp+1500h+var_149C], r15d
0x1800098ea  mov     [rsp+1500h+var_14B8], r12
0x1800098ef  mov     [rsp+1500h+var_14B0], r12
0x1800098f4  mov     [rbp+1400h+var_1458], r14
0x1800098f8  mov     [rbp+1400h+var_1450], rbx
0x1800098fc  mov     [rsp+1500h+var_1498], r12
0x180009901  xorps   xmm0, xmm0
0x180009904  xor     eax, eax
0x180009906  movups  [rbp+1400h+var_1478], xmm0
0x18000990a  mov     [rbp+1400h+var_1468], rax
0x18000990e  xorps   xmm1, xmm1
0x180009911  movups  [rsp+1500h+var_1490], xmm1
0x180009916  mov     [rbp+1400h+var_1480], rax
0x18000991a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009921  test    rax, rax
0x180009924  jz      short loc_180009931
0x180009926  call    _guard_dispatch_icall
0x18000992b  mov     [rbp+1400h+var_1460], rax
0x18000992f  jmp     short loc_180009935
0x180009931  mov     [rbp+1400h+var_1460], r12
0x180009935  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000993c  test    rax, rax
0x18000993f  jz      short loc_18000994B
0x180009941  lea     rcx, [rsp+1500h+var_14E0]
0x180009946  call    _guard_dispatch_icall
0x18000994b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009952  test    rax, rax
0x180009955  jz      short loc_18000996B
0x180009957  mov     r8d, 400h
0x18000995d  lea     rdx, [rbp+1400h+var_1440]
0x180009961  lea     rcx, [rsp+1500h+var_14E0]
0x180009966  call    _guard_dispatch_icall
0x18000996b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009972  test    rax, rax
0x180009975  jz      short loc_180009981
0x180009977  lea     rcx, [rsp+1500h+var_14E0]
0x18000997c  call    _guard_dispatch_icall
0x180009981  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009988  test    rax, rax
0x18000998b  jz      short loc_18000999E
0x18000998d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180009992  jnz     short loc_18000999E
0x180009994  lea     rcx, [rsp+1500h+var_14E0]
0x180009999  call    _guard_dispatch_icall
0x18000999e  cmp     [rsp+1500h+var_14D8], r12d
0x1800099a3  jge     loc_180009AB5
0x1800099a9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800099b0  jnz     short loc_1800099DA
0x1800099b2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800099b9  test    rax, rax
0x1800099bc  jz      short loc_1800099C8
0x1800099be  call    _guard_dispatch_icall
0x1800099c3  movzx   ecx, al
0x1800099c6  jmp     short loc_1800099D6
0x1800099c8  call    cs:__imp_IsDebuggerPresent
0x1800099ce  mov     ecx, r12d
0x1800099d1  test    eax, eax
0x1800099d3  setnz   cl
0x1800099d6  test    ecx, ecx
0x1800099d8  jz      short loc_1800099E1
0x1800099da  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800099df  jz      short loc_180009A07
0x1800099e1  mov     rax, cs:g_pfnResultLoggingCallback
0x1800099e8  test    rax, rax
0x1800099eb  jz      short loc_180009A60
0x1800099ed  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800099f4  jnz     short loc_180009A60
0x1800099f6  xor     r8d, r8d
0x1800099f9  xor     edx, edx
0x1800099fb  lea     rcx, [rsp+1500h+var_14E0]
0x180009a00  call    _guard_dispatch_icall
0x180009a05  jmp     short loc_180009A60
0x180009a07  mov     ebx, 800h
0x180009a0c  mov     rax, cs:g_pfnResultLoggingCallback
0x180009a13  test    rax, rax
0x180009a16  jz      short loc_180009A35
0x180009a18  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180009a1f  jnz     short loc_180009A35
0x180009a21  mov     r8d, ebx
0x180009a24  lea     rdx, [rbp+1400h+OutputString]
0x180009a2b  lea     rcx, [rsp+1500h+var_14E0]
0x180009a30  call    _guard_dispatch_icall
0x180009a35  cmp     [rbp+1400h+OutputString], r12w
0x180009a3d  jnz     short loc_180009A53
0x180009a3f  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180009a44  mov     rdx, rbx; wchar_t *
0x180009a47  lea     rcx, [rbp+1400h+OutputString]; this
0x180009a4e  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180009a53  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180009a5a  call    cs:__imp_OutputDebugStringW
0x180009a60  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180009a65  jnz     short loc_180009A70
0x180009a67  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180009a6e  jz      short loc_180009A82
0x180009a70  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009a77  test    rax, rax
0x180009a7a  jz      short loc_180009A82
0x180009a7c  call    _guard_dispatch_icall
0x180009a81  nop
0x180009a82  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180009a87  jnz     short loc_180009AAA
0x180009a89  mov     rcx, [rbp+1400h+var_40]
0x180009a90  xor     rcx, rsp; StackCookie
0x180009a93  call    __security_check_cookie
0x180009a98  add     rsp, 14D0h
0x180009a9f  pop     r15
0x180009aa1  pop     r14
0x180009aa3  pop     r12
0x180009aa5  pop     rdi
0x180009aa6  pop     rsi
0x180009aa7  pop     rbx
0x180009aa8  pop     rbp
0x180009aa9  retn
0x180009aaa  lea     rcx, [rsp+1500h+var_14E0]; this
0x180009aaf  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180009ab5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
