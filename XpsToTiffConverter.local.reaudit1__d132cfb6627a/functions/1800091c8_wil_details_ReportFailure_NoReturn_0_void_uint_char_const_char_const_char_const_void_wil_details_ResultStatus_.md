# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800091c8`
- end: `0x18000948d`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180009048`

## callees

- `0x1800020e4`
- `0x180004c84`
- `0x180006034`
- `0x180007ee0`
- `0x180008540`
- `0x18000870c`
- `0x1800091c8`
- `0x18000caf0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009289`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009289`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009421`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009421`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009385`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009385`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v21, v17);
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
0x1800091c8  mov     [rsp-8+arg_18], rbx
0x1800091cd  push    rbp
0x1800091ce  push    rsi
0x1800091cf  push    rdi
0x1800091d0  push    r12
0x1800091d2  push    r13
0x1800091d4  push    r14
0x1800091d6  push    r15
0x1800091d8  lea     rbp, [rsp-13C0h]
0x1800091e0  mov     eax, 14C0h
0x1800091e5  call    _alloca_probe
0x1800091ea  sub     rsp, rax
0x1800091ed  mov     r14, r8
0x1800091f0  mov     esi, edx
0x1800091f2  mov     rbx, rcx
0x1800091f5  mov     r15, [rbp+13F0h+arg_28]
0x1800091fc  xor     r13d, r13d
0x1800091ff  cmp     cs:g_pfnThrowPlatformException, r13
0x180009206  setnz   dil
0x18000920a  xor     edx, edx; Val
0x18000920c  mov     r8d, 98h; Size
0x180009212  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180009217  call    memset_0
0x18000921c  nop
0x18000921d  mov     [rbp+13F0h+OutputString], r13w
0x180009225  mov     [rbp+13F0h+var_1430], r13b
0x180009229  mov     rdx, [rbp+13F0h+arg_30]; int
0x180009230  mov     ecx, [rdx]; this
0x180009232  mov     [rsp+14F0h+var_14C8], ecx
0x180009236  mov     eax, [rdx+4]
0x180009239  mov     [rsp+14F0h+var_14C4], eax
0x18000923d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180009242  mov     r12d, eax
0x180009245  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000924a  mov     ecx, r13d
0x18000924d  lea     eax, [r13+8]
0x180009251  cmp     dword ptr [rdx+8], 1
0x180009255  cmovz   ecx, eax
0x180009258  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000925c  lea     ecx, [rax-7]
0x18000925f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180009267  inc     ecx
0x180009269  mov     [rsp+14F0h+var_14C0], ecx
0x18000926d  mov     rcx, [rbp+13F0h+arg_38]
0x180009274  test    rcx, rcx
0x180009277  jz      short loc_180009284
0x180009279  cmp     [rcx], r13w
0x18000927d  mov     [rsp+14F0h+var_14B8], rcx
0x180009282  jnz     short loc_180009289
0x180009284  mov     [rsp+14F0h+var_14B8], r13
0x180009289  call    cs:__imp_GetCurrentThreadId
0x18000928f  mov     [rsp+14F0h+var_14B0], eax
0x180009293  mov     [rsp+14F0h+var_1498], r14
0x180009298  mov     [rsp+14F0h+var_1490], esi
0x18000929c  mov     [rsp+14F0h+var_148C], r12d
0x1800092a1  mov     [rsp+14F0h+var_14A8], r13
0x1800092a6  mov     [rsp+14F0h+var_14A0], r13
0x1800092ab  mov     [rbp+13F0h+var_1448], r15
0x1800092af  mov     [rbp+13F0h+var_1440], rbx
0x1800092b3  mov     [rsp+14F0h+var_1488], r13
0x1800092b8  xorps   xmm0, xmm0
0x1800092bb  xor     eax, eax
0x1800092bd  movups  [rbp+13F0h+var_1468], xmm0
0x1800092c1  mov     [rbp+13F0h+var_1458], rax
0x1800092c5  xorps   xmm1, xmm1
0x1800092c8  movups  [rsp+14F0h+var_1480], xmm1
0x1800092cd  mov     [rbp+13F0h+var_1470], rax
0x1800092d1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800092d8  test    rax, rax
0x1800092db  jz      short loc_1800092E8
0x1800092dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092e2  mov     [rbp+13F0h+var_1450], rax
0x1800092e6  jmp     short loc_1800092EC
0x1800092e8  mov     [rbp+13F0h+var_1450], r13
0x1800092ec  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800092f3  test    rax, rax
0x1800092f6  jz      short loc_180009302
0x1800092f8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800092fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009302  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009309  test    rax, rax
0x18000930c  jz      short loc_180009322
0x18000930e  mov     r8d, 400h
0x180009314  lea     rdx, [rbp+13F0h+var_1430]
0x180009318  lea     rcx, [rsp+14F0h+var_14D0]
0x18000931d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009322  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009329  test    rax, rax
0x18000932c  jz      short loc_180009338
0x18000932e  lea     rcx, [rsp+14F0h+var_14D0]
0x180009333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009338  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000933f  test    rax, rax
0x180009342  jz      short loc_18000935A
0x180009344  test    dil, dil
0x180009347  jnz     short loc_18000935A
0x180009349  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000934e  jnz     short loc_18000935A
0x180009350  lea     rcx, [rsp+14F0h+var_14D0]
0x180009355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000935a  cmp     [rsp+14F0h+var_14C8], r13d
0x18000935f  jl      short loc_180009367
0x180009361  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180009367  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000936e  jnz     short loc_18000938F
0x180009370  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009377  test    rax, rax
0x18000937a  jz      short loc_180009385
0x18000937c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009381  test    al, al
0x180009383  jmp     short loc_18000938D
0x180009385  call    cs:__imp_IsDebuggerPresent
0x18000938b  test    eax, eax
0x18000938d  jz      short loc_180009398
0x18000938f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180009394  mov     bl, 1
0x180009396  jz      short loc_18000939B
0x180009398  mov     bl, r13b
0x18000939b  test    dil, dil
0x18000939e  jnz     short loc_1800093CA
0x1800093a0  test    bl, bl
0x1800093a2  jnz     short loc_1800093CA
0x1800093a4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800093ab  test    rax, rax
0x1800093ae  jz      short loc_180009427
0x1800093b0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800093b7  jnz     short loc_180009427
0x1800093b9  xor     r8d, r8d
0x1800093bc  xor     edx, edx
0x1800093be  lea     rcx, [rsp+14F0h+var_14D0]
0x1800093c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093c8  jmp     short loc_180009427
0x1800093ca  mov     esi, 800h
0x1800093cf  mov     rax, cs:g_pfnResultLoggingCallback
0x1800093d6  test    rax, rax
0x1800093d9  jz      short loc_1800093F8
0x1800093db  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800093e2  jnz     short loc_1800093F8
0x1800093e4  mov     r8d, esi
0x1800093e7  lea     rdx, [rbp+13F0h+OutputString]
0x1800093ee  lea     rcx, [rsp+14F0h+var_14D0]
0x1800093f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093f8  cmp     [rbp+13F0h+OutputString], r13w
0x180009400  jnz     short loc_180009416
0x180009402  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180009407  mov     rdx, rsi; unsigned __int16 *
0x18000940a  lea     rcx, [rbp+13F0h+OutputString]; this
0x180009411  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180009416  test    bl, bl
0x180009418  jz      short loc_180009427
0x18000941a  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180009421  call    cs:__imp_OutputDebugStringW
0x180009427  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000942c  jnz     short loc_180009437
0x18000942e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180009435  jz      short loc_180009449
0x180009437  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000943e  test    rax, rax
0x180009441  jz      short loc_180009449
0x180009443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009448  nop
0x180009449  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000944e  jz      short loc_18000945B
0x180009450  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180009455  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000945b  test    dil, dil
0x18000945e  jz      short loc_180009478
0x180009460  lea     rdx, [rbp+13F0h+OutputString]
0x180009467  lea     rcx, [rsp+14F0h+var_14D0]
0x18000946c  mov     rax, cs:g_pfnThrowPlatformException
0x180009473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009478  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000947d  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180009482  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180009487  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
