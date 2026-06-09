# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180009224`
- end: `0x18000949d`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180008f94`

## callees

- `0x180005bbc`
- `0x180009224`
- `0x18000a944`
- `0x18000b190`
- `0x18000b8f0`
- `0x18000ca20`
- `0x18006b240`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800092dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800092dd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000946a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000946a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800093e0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800093e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
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
0x180009224  mov     [rsp-8+arg_18], rbx
0x180009229  push    rbp
0x18000922a  push    rsi
0x18000922b  push    rdi
0x18000922c  push    r12
0x18000922e  push    r13
0x180009230  push    r14
0x180009232  push    r15
0x180009234  lea     rbp, [rsp-13C0h]
0x18000923c  mov     eax, 14C0h
0x180009241  call    _alloca_probe
0x180009246  sub     rsp, rax
0x180009249  mov     r14, r8
0x18000924c  mov     esi, edx
0x18000924e  mov     rdi, rcx
0x180009251  mov     r15, [rbp+13F0h+arg_28]
0x180009258  xor     edx, edx; Val
0x18000925a  mov     r8d, 98h; Size
0x180009260  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180009265  call    memset_0
0x18000926a  nop
0x18000926b  xor     r13d, r13d
0x18000926e  mov     [rbp+13F0h+OutputString], r13w
0x180009276  mov     [rbp+13F0h+var_1430], r13b
0x18000927a  mov     rbx, [rbp+13F0h+arg_30]
0x180009281  mov     ecx, [rbx]; this
0x180009283  mov     [rsp+14F0h+var_14C8], ecx
0x180009287  mov     eax, [rbx+4]
0x18000928a  mov     [rsp+14F0h+var_14C4], eax
0x18000928e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180009293  mov     r12d, eax
0x180009296  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000929e  mov     ecx, r13d
0x1800092a1  lea     eax, [r13+8]
0x1800092a5  cmp     dword ptr [rbx+8], 1
0x1800092a9  cmovz   ecx, eax
0x1800092ac  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800092b0  lea     ecx, [rax-7]
0x1800092b3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800092bb  inc     ecx
0x1800092bd  mov     [rsp+14F0h+var_14C0], ecx
0x1800092c1  mov     rcx, [rbp+13F0h+arg_38]
0x1800092c8  test    rcx, rcx
0x1800092cb  jz      short loc_1800092D8
0x1800092cd  cmp     [rcx], r13w
0x1800092d1  mov     [rsp+14F0h+var_14B8], rcx
0x1800092d6  jnz     short loc_1800092DD
0x1800092d8  mov     [rsp+14F0h+var_14B8], r13
0x1800092dd  call    cs:__imp_GetCurrentThreadId
0x1800092e3  mov     [rsp+14F0h+var_14B0], eax
0x1800092e7  mov     [rsp+14F0h+var_1498], r14
0x1800092ec  mov     [rsp+14F0h+var_1490], esi
0x1800092f0  mov     [rsp+14F0h+var_148C], r12d
0x1800092f5  mov     [rsp+14F0h+var_14A8], r13
0x1800092fa  mov     [rsp+14F0h+var_14A0], r13
0x1800092ff  mov     [rbp+13F0h+var_1448], r15
0x180009303  mov     [rbp+13F0h+var_1440], rdi
0x180009307  mov     [rsp+14F0h+var_1488], r13
0x18000930c  xorps   xmm0, xmm0
0x18000930f  xor     eax, eax
0x180009311  movups  [rbp+13F0h+var_1468], xmm0
0x180009315  mov     [rbp+13F0h+var_1458], rax
0x180009319  xorps   xmm1, xmm1
0x18000931c  movups  [rsp+14F0h+var_1480], xmm1
0x180009321  mov     [rbp+13F0h+var_1470], rax
0x180009325  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000932c  test    rax, rax
0x18000932f  jz      short loc_18000933C
0x180009331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009336  mov     [rbp+13F0h+var_1450], rax
0x18000933a  jmp     short loc_180009340
0x18000933c  mov     [rbp+13F0h+var_1450], r13
0x180009340  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009347  test    rax, rax
0x18000934a  jz      short loc_180009356
0x18000934c  lea     rcx, [rsp+14F0h+var_14D0]
0x180009351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009356  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000935d  test    rax, rax
0x180009360  jz      short loc_180009376
0x180009362  mov     r8d, 400h
0x180009368  lea     rdx, [rbp+13F0h+var_1430]
0x18000936c  lea     rcx, [rsp+14F0h+var_14D0]
0x180009371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009376  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000937d  test    rax, rax
0x180009380  jz      short loc_18000938C
0x180009382  lea     rcx, [rsp+14F0h+var_14D0]
0x180009387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000938c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009393  test    rax, rax
0x180009396  jz      short loc_1800093A9
0x180009398  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000939d  jnz     short loc_1800093A9
0x18000939f  lea     rcx, [rsp+14F0h+var_14D0]
0x1800093a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093a9  cmp     [rsp+14F0h+var_14C8], r13d
0x1800093ae  jl      short loc_1800093C2
0x1800093b0  mov     ecx, 8000FFFFh; this
0x1800093b5  mov     [rsp+14F0h+var_14C8], ecx
0x1800093b9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800093be  mov     [rsp+14F0h+var_14C4], eax
0x1800093c2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800093c9  jnz     short loc_1800093EA
0x1800093cb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800093d2  test    rax, rax
0x1800093d5  jz      short loc_1800093E0
0x1800093d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093dc  test    al, al
0x1800093de  jmp     short loc_1800093E8
0x1800093e0  call    cs:__imp_IsDebuggerPresent
0x1800093e6  test    eax, eax
0x1800093e8  jz      short loc_1800093F1
0x1800093ea  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800093ef  jz      short loc_180009417
0x1800093f1  mov     rax, cs:g_pfnResultLoggingCallback
0x1800093f8  test    rax, rax
0x1800093fb  jz      short loc_180009470
0x1800093fd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180009404  jnz     short loc_180009470
0x180009406  xor     r8d, r8d
0x180009409  xor     edx, edx
0x18000940b  lea     rcx, [rsp+14F0h+var_14D0]
0x180009410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009415  jmp     short loc_180009470
0x180009417  mov     ebx, 800h
0x18000941c  mov     rax, cs:g_pfnResultLoggingCallback
0x180009423  test    rax, rax
0x180009426  jz      short loc_180009445
0x180009428  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000942f  jnz     short loc_180009445
0x180009431  mov     r8d, ebx
0x180009434  lea     rdx, [rbp+13F0h+OutputString]
0x18000943b  lea     rcx, [rsp+14F0h+var_14D0]
0x180009440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009445  cmp     [rbp+13F0h+OutputString], r13w
0x18000944d  jnz     short loc_180009463
0x18000944f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180009454  mov     rdx, rbx; unsigned __int16 *
0x180009457  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000945e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180009463  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000946a  call    cs:__imp_OutputDebugStringW
0x180009470  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180009475  jnz     short loc_180009480
0x180009477  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000947e  jz      short loc_180009492
0x180009480  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009487  test    rax, rax
0x18000948a  jz      short loc_180009492
0x18000948c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009491  nop
0x180009492  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180009497  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
