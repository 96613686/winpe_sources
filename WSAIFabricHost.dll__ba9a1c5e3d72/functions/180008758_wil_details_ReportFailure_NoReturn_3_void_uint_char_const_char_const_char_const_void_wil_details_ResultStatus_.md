# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180008758`
- end: `0x1800089d1`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180008390`

## callees

- `0x180005758`
- `0x180008758`
- `0x18000a024`
- `0x18000a870`
- `0x18000acd0`
- `0x18000be80`
- `0x18007f280`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008811`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008811`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000899e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000899e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008914`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008914`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180008758  mov     [rsp-8+arg_18], rbx
0x18000875d  push    rbp
0x18000875e  push    rsi
0x18000875f  push    rdi
0x180008760  push    r12
0x180008762  push    r13
0x180008764  push    r14
0x180008766  push    r15
0x180008768  lea     rbp, [rsp-13C0h]
0x180008770  mov     eax, 14C0h
0x180008775  call    _alloca_probe
0x18000877a  sub     rsp, rax
0x18000877d  mov     r14, r8
0x180008780  mov     esi, edx
0x180008782  mov     rdi, rcx
0x180008785  mov     r15, [rbp+13F0h+arg_28]
0x18000878c  xor     edx, edx; Val
0x18000878e  mov     r8d, 98h; Size
0x180008794  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180008799  call    memset_0
0x18000879e  nop
0x18000879f  xor     r13d, r13d
0x1800087a2  mov     [rbp+13F0h+OutputString], r13w
0x1800087aa  mov     [rbp+13F0h+var_1430], r13b
0x1800087ae  mov     rbx, [rbp+13F0h+arg_30]
0x1800087b5  mov     ecx, [rbx]; this
0x1800087b7  mov     [rsp+14F0h+var_14C8], ecx
0x1800087bb  mov     eax, [rbx+4]
0x1800087be  mov     [rsp+14F0h+var_14C4], eax
0x1800087c2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800087c7  mov     r12d, eax
0x1800087ca  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800087d2  mov     ecx, r13d
0x1800087d5  lea     eax, [r13+8]
0x1800087d9  cmp     dword ptr [rbx+8], 1
0x1800087dd  cmovz   ecx, eax
0x1800087e0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800087e4  lea     ecx, [rax-7]
0x1800087e7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800087ef  inc     ecx
0x1800087f1  mov     [rsp+14F0h+var_14C0], ecx
0x1800087f5  mov     rcx, [rbp+13F0h+arg_38]
0x1800087fc  test    rcx, rcx
0x1800087ff  jz      short loc_18000880C
0x180008801  cmp     [rcx], r13w
0x180008805  mov     [rsp+14F0h+var_14B8], rcx
0x18000880a  jnz     short loc_180008811
0x18000880c  mov     [rsp+14F0h+var_14B8], r13
0x180008811  call    cs:__imp_GetCurrentThreadId
0x180008817  mov     [rsp+14F0h+var_14B0], eax
0x18000881b  mov     [rsp+14F0h+var_1498], r14
0x180008820  mov     [rsp+14F0h+var_1490], esi
0x180008824  mov     [rsp+14F0h+var_148C], r12d
0x180008829  mov     [rsp+14F0h+var_14A8], r13
0x18000882e  mov     [rsp+14F0h+var_14A0], r13
0x180008833  mov     [rbp+13F0h+var_1448], r15
0x180008837  mov     [rbp+13F0h+var_1440], rdi
0x18000883b  mov     [rsp+14F0h+var_1488], r13
0x180008840  xorps   xmm0, xmm0
0x180008843  xor     eax, eax
0x180008845  movups  [rbp+13F0h+var_1468], xmm0
0x180008849  mov     [rbp+13F0h+var_1458], rax
0x18000884d  xorps   xmm1, xmm1
0x180008850  movups  [rsp+14F0h+var_1480], xmm1
0x180008855  mov     [rbp+13F0h+var_1470], rax
0x180008859  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008860  test    rax, rax
0x180008863  jz      short loc_180008870
0x180008865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000886a  mov     [rbp+13F0h+var_1450], rax
0x18000886e  jmp     short loc_180008874
0x180008870  mov     [rbp+13F0h+var_1450], r13
0x180008874  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000887b  test    rax, rax
0x18000887e  jz      short loc_18000888A
0x180008880  lea     rcx, [rsp+14F0h+var_14D0]
0x180008885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000888a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008891  test    rax, rax
0x180008894  jz      short loc_1800088AA
0x180008896  mov     r8d, 400h
0x18000889c  lea     rdx, [rbp+13F0h+var_1430]
0x1800088a0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800088a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088aa  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800088b1  test    rax, rax
0x1800088b4  jz      short loc_1800088C0
0x1800088b6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800088bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088c0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800088c7  test    rax, rax
0x1800088ca  jz      short loc_1800088DD
0x1800088cc  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800088d1  jnz     short loc_1800088DD
0x1800088d3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800088d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088dd  cmp     [rsp+14F0h+var_14C8], r13d
0x1800088e2  jl      short loc_1800088F6
0x1800088e4  mov     ecx, 8000FFFFh; this
0x1800088e9  mov     [rsp+14F0h+var_14C8], ecx
0x1800088ed  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800088f2  mov     [rsp+14F0h+var_14C4], eax
0x1800088f6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800088fd  jnz     short loc_18000891E
0x1800088ff  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008906  test    rax, rax
0x180008909  jz      short loc_180008914
0x18000890b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008910  test    al, al
0x180008912  jmp     short loc_18000891C
0x180008914  call    cs:__imp_IsDebuggerPresent
0x18000891a  test    eax, eax
0x18000891c  jz      short loc_180008925
0x18000891e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180008923  jz      short loc_18000894B
0x180008925  mov     rax, cs:g_pfnResultLoggingCallback
0x18000892c  test    rax, rax
0x18000892f  jz      short loc_1800089A4
0x180008931  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180008938  jnz     short loc_1800089A4
0x18000893a  xor     r8d, r8d
0x18000893d  xor     edx, edx
0x18000893f  lea     rcx, [rsp+14F0h+var_14D0]
0x180008944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008949  jmp     short loc_1800089A4
0x18000894b  mov     ebx, 800h
0x180008950  mov     rax, cs:g_pfnResultLoggingCallback
0x180008957  test    rax, rax
0x18000895a  jz      short loc_180008979
0x18000895c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180008963  jnz     short loc_180008979
0x180008965  mov     r8d, ebx
0x180008968  lea     rdx, [rbp+13F0h+OutputString]
0x18000896f  lea     rcx, [rsp+14F0h+var_14D0]
0x180008974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008979  cmp     [rbp+13F0h+OutputString], r13w
0x180008981  jnz     short loc_180008997
0x180008983  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180008988  mov     rdx, rbx; wchar_t *
0x18000898b  lea     rcx, [rbp+13F0h+OutputString]; this
0x180008992  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180008997  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000899e  call    cs:__imp_OutputDebugStringW
0x1800089a4  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800089a9  jnz     short loc_1800089B4
0x1800089ab  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800089b2  jz      short loc_1800089C6
0x1800089b4  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800089bb  test    rax, rax
0x1800089be  jz      short loc_1800089C6
0x1800089c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089c5  nop
0x1800089c6  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800089cb  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
