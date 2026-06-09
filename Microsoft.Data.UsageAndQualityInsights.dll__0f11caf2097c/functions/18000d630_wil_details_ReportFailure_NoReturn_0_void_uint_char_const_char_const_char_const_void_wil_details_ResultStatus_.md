# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x18000d630`
- end: `0x18000d8f5`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000d580`

## callees

- `0x180003fb8`
- `0x180007fa4`
- `0x180009750`
- `0x18000b7c8`
- `0x18000bfe0`
- `0x18000c258`
- `0x18000d630`
- `0x180101970`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d6f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d6f1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d7ed`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d7ed`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d889`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d889`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  bool v11; // di
  int v12; // r12d
  int v13; // ecx
  __int64 v14; // rdx
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  char v19; // bl
  const struct wil::FailureInfo *v20; // rdx
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+24h] [rbp-DCh]
  int v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v25; // [rsp+30h] [rbp-D0h]
  _WORD *v26; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+60h] [rbp-A0h]
  int v32; // [rsp+64h] [rbp-9Ch]
  __int64 v33; // [rsp+68h] [rbp-98h]
  __int128 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+80h] [rbp-80h]
  __int128 v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  char v41[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v11 = g_pfnThrowPlatformException != 0;
  memset_0(&v21, 0, 0x98u);
  OutputString[0] = 0;
  v41[0] = 0;
  v23 = *a7;
  v24 = a7[1];
  v12 = wil::details::RecordException((wil::details *)(unsigned int)v23, (int)a7);
  v21 = 0;
  v13 = 0;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  v22 = v13;
  v25 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v18 = *a8 == 0, v26 = a8, v18) )
    v26 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v30 = a3;
  v31 = a2;
  v32 = v12;
  v28 = 0;
  v29 = 0;
  v39 = a6;
  v40 = a1;
  v33 = 0;
  v36 = 0;
  v37 = 0;
  v34 = 0;
  v35 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v21);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v21, v41, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v21);
  if ( wil::details::g_pfnOriginateCallback && !v11 && (v22 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v21);
  if ( v23 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v19 = 1, (v22 & 2) != 0) )
  {
    v19 = 0;
  }
  if ( v11 || v19 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, OutputString, 2048, v17);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)&v21, v17);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v21, 0, 0, v17);
  }
  if ( ((v22 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v22 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v21, v15);
  if ( v11 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v21, OutputString);
  wil::ThrowResultException((wil *)&v21, v15);
  wil::details::WilFailFast((wil::details *)&v21, v20);
}

```

## disassembly

```asm
0x18000d630  mov     [rsp-8+arg_18], rbx
0x18000d635  push    rbp
0x18000d636  push    rsi
0x18000d637  push    rdi
0x18000d638  push    r12
0x18000d63a  push    r13
0x18000d63c  push    r14
0x18000d63e  push    r15
0x18000d640  lea     rbp, [rsp-13C0h]
0x18000d648  mov     eax, 14C0h
0x18000d64d  call    _alloca_probe
0x18000d652  sub     rsp, rax
0x18000d655  mov     r14, r8
0x18000d658  mov     esi, edx
0x18000d65a  mov     rbx, rcx
0x18000d65d  mov     r15, [rbp+13F0h+arg_28]
0x18000d664  xor     r13d, r13d
0x18000d667  cmp     cs:g_pfnThrowPlatformException, r13
0x18000d66e  setnz   dil
0x18000d672  xor     edx, edx; Val
0x18000d674  mov     r8d, 98h; Size
0x18000d67a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000d67f  call    memset_0
0x18000d684  nop
0x18000d685  mov     [rbp+13F0h+OutputString], r13w
0x18000d68d  mov     [rbp+13F0h+var_1430], r13b
0x18000d691  mov     rdx, [rbp+13F0h+arg_30]; int
0x18000d698  mov     ecx, [rdx]; this
0x18000d69a  mov     [rsp+14F0h+var_14C8], ecx
0x18000d69e  mov     eax, [rdx+4]
0x18000d6a1  mov     [rsp+14F0h+var_14C4], eax
0x18000d6a5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000d6aa  mov     r12d, eax
0x18000d6ad  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000d6b2  mov     ecx, r13d
0x18000d6b5  lea     eax, [r13+8]
0x18000d6b9  cmp     dword ptr [rdx+8], 1
0x18000d6bd  cmovz   ecx, eax
0x18000d6c0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000d6c4  lea     ecx, [rax-7]
0x18000d6c7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000d6cf  inc     ecx
0x18000d6d1  mov     [rsp+14F0h+var_14C0], ecx
0x18000d6d5  mov     rcx, [rbp+13F0h+arg_38]
0x18000d6dc  test    rcx, rcx
0x18000d6df  jz      short loc_18000D6EC
0x18000d6e1  cmp     [rcx], r13w
0x18000d6e5  mov     [rsp+14F0h+var_14B8], rcx
0x18000d6ea  jnz     short loc_18000D6F1
0x18000d6ec  mov     [rsp+14F0h+var_14B8], r13
0x18000d6f1  call    cs:__imp_GetCurrentThreadId
0x18000d6f7  mov     [rsp+14F0h+var_14B0], eax
0x18000d6fb  mov     [rsp+14F0h+var_1498], r14
0x18000d700  mov     [rsp+14F0h+var_1490], esi
0x18000d704  mov     [rsp+14F0h+var_148C], r12d
0x18000d709  mov     [rsp+14F0h+var_14A8], r13
0x18000d70e  mov     [rsp+14F0h+var_14A0], r13
0x18000d713  mov     [rbp+13F0h+var_1448], r15
0x18000d717  mov     [rbp+13F0h+var_1440], rbx
0x18000d71b  mov     [rsp+14F0h+var_1488], r13
0x18000d720  xorps   xmm0, xmm0
0x18000d723  xor     eax, eax
0x18000d725  movups  [rbp+13F0h+var_1468], xmm0
0x18000d729  mov     [rbp+13F0h+var_1458], rax
0x18000d72d  xorps   xmm1, xmm1
0x18000d730  movups  [rsp+14F0h+var_1480], xmm1
0x18000d735  mov     [rbp+13F0h+var_1470], rax
0x18000d739  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000d740  test    rax, rax
0x18000d743  jz      short loc_18000D750
0x18000d745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d74a  mov     [rbp+13F0h+var_1450], rax
0x18000d74e  jmp     short loc_18000D754
0x18000d750  mov     [rbp+13F0h+var_1450], r13
0x18000d754  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000d75b  test    rax, rax
0x18000d75e  jz      short loc_18000D76A
0x18000d760  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d76a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000d771  test    rax, rax
0x18000d774  jz      short loc_18000D78A
0x18000d776  mov     r8d, 400h
0x18000d77c  lea     rdx, [rbp+13F0h+var_1430]
0x18000d780  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d78a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d791  test    rax, rax
0x18000d794  jz      short loc_18000D7A0
0x18000d796  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d79b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7a0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d7a7  test    rax, rax
0x18000d7aa  jz      short loc_18000D7C2
0x18000d7ac  test    dil, dil
0x18000d7af  jnz     short loc_18000D7C2
0x18000d7b1  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000d7b6  jnz     short loc_18000D7C2
0x18000d7b8  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d7bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7c2  cmp     [rsp+14F0h+var_14C8], r13d
0x18000d7c7  jl      short loc_18000D7CF
0x18000d7c9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000d7cf  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000d7d6  jnz     short loc_18000D7F7
0x18000d7d8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000d7df  test    rax, rax
0x18000d7e2  jz      short loc_18000D7ED
0x18000d7e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7e9  test    al, al
0x18000d7eb  jmp     short loc_18000D7F5
0x18000d7ed  call    cs:__imp_IsDebuggerPresent
0x18000d7f3  test    eax, eax
0x18000d7f5  jz      short loc_18000D800
0x18000d7f7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000d7fc  mov     bl, 1
0x18000d7fe  jz      short loc_18000D803
0x18000d800  mov     bl, r13b
0x18000d803  test    dil, dil
0x18000d806  jnz     short loc_18000D832
0x18000d808  test    bl, bl
0x18000d80a  jnz     short loc_18000D832
0x18000d80c  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d813  test    rax, rax
0x18000d816  jz      short loc_18000D88F
0x18000d818  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000d81f  jnz     short loc_18000D88F
0x18000d821  xor     r8d, r8d
0x18000d824  xor     edx, edx
0x18000d826  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d82b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d830  jmp     short loc_18000D88F
0x18000d832  mov     esi, 800h
0x18000d837  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d83e  test    rax, rax
0x18000d841  jz      short loc_18000D860
0x18000d843  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000d84a  jnz     short loc_18000D860
0x18000d84c  mov     r8d, esi
0x18000d84f  lea     rdx, [rbp+13F0h+OutputString]
0x18000d856  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d85b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d860  cmp     [rbp+13F0h+OutputString], r13w
0x18000d868  jnz     short loc_18000D87E
0x18000d86a  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000d86f  mov     rdx, rsi; wchar_t *
0x18000d872  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000d879  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000d87e  test    bl, bl
0x18000d880  jz      short loc_18000D88F
0x18000d882  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000d889  call    cs:__imp_OutputDebugStringW
0x18000d88f  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000d894  jnz     short loc_18000D89F
0x18000d896  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000d89d  jz      short loc_18000D8B1
0x18000d89f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000d8a6  test    rax, rax
0x18000d8a9  jz      short loc_18000D8B1
0x18000d8ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8b0  nop
0x18000d8b1  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000d8b6  jz      short loc_18000D8C3
0x18000d8b8  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000d8bd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000d8c3  test    dil, dil
0x18000d8c6  jz      short loc_18000D8E0
0x18000d8c8  lea     rdx, [rbp+13F0h+OutputString]
0x18000d8cf  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d8d4  mov     rax, cs:g_pfnThrowPlatformException
0x18000d8db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8e0  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000d8e5  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000d8ea  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000d8ef  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
