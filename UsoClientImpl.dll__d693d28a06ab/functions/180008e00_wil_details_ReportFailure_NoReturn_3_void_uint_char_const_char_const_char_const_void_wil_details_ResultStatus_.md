# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180008e00`
- end: `0x180009082`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `642`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800076e0`

## callees

- `0x180006224`
- `0x1800066f0`
- `0x180006930`
- `0x180007630`
- `0x180008e00`
- `0x18005c570`
- `0x18005c5e0`
- `0x18005c660`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008eb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008eb9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000904f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000904f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008fbd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008fbd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      g_pfnResultLoggingCallback(v18, OutputString, 2048, v17);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)v18, v17);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(v18, 0, 0, v17);
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
0x180008e00  mov     [rsp-8+arg_18], rbx
0x180008e05  push    rbp
0x180008e06  push    rsi
0x180008e07  push    rdi
0x180008e08  push    r12
0x180008e0a  push    r13
0x180008e0c  push    r14
0x180008e0e  push    r15
0x180008e10  lea     rbp, [rsp-13C0h]
0x180008e18  mov     eax, 14C0h
0x180008e1d  call    _alloca_probe
0x180008e22  sub     rsp, rax
0x180008e25  mov     r14, r8
0x180008e28  mov     esi, edx
0x180008e2a  mov     rdi, rcx
0x180008e2d  mov     r15, [rbp+13F0h+arg_28]
0x180008e34  xor     edx, edx; Val
0x180008e36  mov     r8d, 98h; Size
0x180008e3c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180008e41  call    memset
0x180008e46  nop
0x180008e47  xor     r13d, r13d
0x180008e4a  mov     [rbp+13F0h+OutputString], r13w
0x180008e52  mov     [rbp+13F0h+var_1430], r13b
0x180008e56  mov     rbx, [rbp+13F0h+arg_30]
0x180008e5d  mov     ecx, [rbx]; this
0x180008e5f  mov     [rsp+14F0h+var_14C8], ecx
0x180008e63  mov     eax, [rbx+4]
0x180008e66  mov     [rsp+14F0h+var_14C4], eax
0x180008e6a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180008e6f  mov     r12d, eax
0x180008e72  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180008e7a  mov     ecx, r13d
0x180008e7d  lea     eax, [r13+8]
0x180008e81  cmp     dword ptr [rbx+8], 1
0x180008e85  cmovz   ecx, eax
0x180008e88  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180008e8c  lea     ecx, [rax-7]
0x180008e8f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008e97  inc     ecx
0x180008e99  mov     [rsp+14F0h+var_14C0], ecx
0x180008e9d  mov     rcx, [rbp+13F0h+arg_38]
0x180008ea4  test    rcx, rcx
0x180008ea7  jz      short loc_180008EB4
0x180008ea9  cmp     [rcx], r13w
0x180008ead  mov     [rsp+14F0h+var_14B8], rcx
0x180008eb2  jnz     short loc_180008EB9
0x180008eb4  mov     [rsp+14F0h+var_14B8], r13
0x180008eb9  call    cs:__imp_GetCurrentThreadId
0x180008ebf  mov     [rsp+14F0h+var_14B0], eax
0x180008ec3  mov     [rsp+14F0h+var_1498], r14
0x180008ec8  mov     [rsp+14F0h+var_1490], esi
0x180008ecc  mov     [rsp+14F0h+var_148C], r12d
0x180008ed1  mov     [rsp+14F0h+var_14A8], r13
0x180008ed6  mov     [rsp+14F0h+var_14A0], r13
0x180008edb  mov     [rbp+13F0h+var_1448], r15
0x180008edf  mov     [rbp+13F0h+var_1440], rdi
0x180008ee3  mov     [rsp+14F0h+var_1488], r13
0x180008ee8  xorps   xmm0, xmm0
0x180008eeb  xor     eax, eax
0x180008eed  movups  [rbp+13F0h+var_1468], xmm0
0x180008ef1  mov     [rbp+13F0h+var_1458], rax
0x180008ef5  xorps   xmm1, xmm1
0x180008ef8  movups  [rsp+14F0h+var_1480], xmm1
0x180008efd  mov     [rbp+13F0h+var_1470], rax
0x180008f01  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008f08  test    rax, rax
0x180008f0b  jz      short loc_180008F18
0x180008f0d  call    _guard_dispatch_icall
0x180008f12  mov     [rbp+13F0h+var_1450], rax
0x180008f16  jmp     short loc_180008F1C
0x180008f18  mov     [rbp+13F0h+var_1450], r13
0x180008f1c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008f23  test    rax, rax
0x180008f26  jz      short loc_180008F32
0x180008f28  lea     rcx, [rsp+14F0h+var_14D0]
0x180008f2d  call    _guard_dispatch_icall
0x180008f32  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008f39  test    rax, rax
0x180008f3c  jz      short loc_180008F52
0x180008f3e  mov     r8d, 400h
0x180008f44  lea     rdx, [rbp+13F0h+var_1430]
0x180008f48  lea     rcx, [rsp+14F0h+var_14D0]
0x180008f4d  call    _guard_dispatch_icall
0x180008f52  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008f59  test    rax, rax
0x180008f5c  jz      short loc_180008F68
0x180008f5e  lea     rcx, [rsp+14F0h+var_14D0]
0x180008f63  call    _guard_dispatch_icall
0x180008f68  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008f6f  test    rax, rax
0x180008f72  jz      short loc_180008F85
0x180008f74  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180008f79  jnz     short loc_180008F85
0x180008f7b  lea     rcx, [rsp+14F0h+var_14D0]
0x180008f80  call    _guard_dispatch_icall
0x180008f85  cmp     [rsp+14F0h+var_14C8], r13d
0x180008f8a  jl      short loc_180008F9E
0x180008f8c  mov     ecx, 8000FFFFh; this
0x180008f91  mov     [rsp+14F0h+var_14C8], ecx
0x180008f95  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008f9a  mov     [rsp+14F0h+var_14C4], eax
0x180008f9e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180008fa5  jnz     short loc_180008FCF
0x180008fa7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008fae  test    rax, rax
0x180008fb1  jz      short loc_180008FBD
0x180008fb3  call    _guard_dispatch_icall
0x180008fb8  movzx   ecx, al
0x180008fbb  jmp     short loc_180008FCB
0x180008fbd  call    cs:__imp_IsDebuggerPresent
0x180008fc3  mov     ecx, r13d
0x180008fc6  test    eax, eax
0x180008fc8  setnz   cl
0x180008fcb  test    ecx, ecx
0x180008fcd  jz      short loc_180008FD6
0x180008fcf  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180008fd4  jz      short loc_180008FFC
0x180008fd6  mov     rax, cs:g_pfnResultLoggingCallback
0x180008fdd  test    rax, rax
0x180008fe0  jz      short loc_180009055
0x180008fe2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180008fe9  jnz     short loc_180009055
0x180008feb  xor     r8d, r8d
0x180008fee  xor     edx, edx
0x180008ff0  lea     rcx, [rsp+14F0h+var_14D0]
0x180008ff5  call    _guard_dispatch_icall
0x180008ffa  jmp     short loc_180009055
0x180008ffc  mov     ebx, 800h
0x180009001  mov     rax, cs:g_pfnResultLoggingCallback
0x180009008  test    rax, rax
0x18000900b  jz      short loc_18000902A
0x18000900d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180009014  jnz     short loc_18000902A
0x180009016  mov     r8d, ebx
0x180009019  lea     rdx, [rbp+13F0h+OutputString]
0x180009020  lea     rcx, [rsp+14F0h+var_14D0]
0x180009025  call    _guard_dispatch_icall
0x18000902a  cmp     [rbp+13F0h+OutputString], r13w
0x180009032  jnz     short loc_180009048
0x180009034  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180009039  mov     rdx, rbx; wchar_t *
0x18000903c  lea     rcx, [rbp+13F0h+OutputString]; this
0x180009043  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180009048  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000904f  call    cs:__imp_OutputDebugStringW
0x180009055  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000905a  jnz     short loc_180009065
0x18000905c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180009063  jz      short loc_180009077
0x180009065  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000906c  test    rax, rax
0x18000906f  jz      short loc_180009077
0x180009071  call    _guard_dispatch_icall
0x180009076  nop
0x180009077  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000907c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
