# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000226c`
- end: `0x1800024d5`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002020`

## callees

- `0x180001f4a`
- `0x18000226c`
- `0x180003604`
- `0x180003da0`
- `0x1800044c0`
- `0x180005410`
- `0x180006170`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000230e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000230e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800024a2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800024a2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002418`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002418`

## string_xrefs

- `0x180002318`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7)
{
  int v9; // edx
  int v10; // edi
  int v11; // ecx
  const struct wil::FailureInfo *v12; // rdx
  __int64 v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v10 = wil::details::RecordFailFast((wil::details *)(unsigned int)v18, v9);
  v16 = 3;
  v11 = 0;
  if ( a7[2] == 1 )
    v11 = 8;
  v17 = v11;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
  v26 = a2;
  v27 = v10;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
  {
    v18 = -2147418113;
    v19 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v12);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( (v17 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v13);
  }
  wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x18000226c  mov     [rsp-8+arg_10], rbx
0x180002271  mov     [rsp-8+arg_18], rsi
0x180002276  push    rbp
0x180002277  push    rdi
0x180002278  push    r12
0x18000227a  push    r14
0x18000227c  push    r15
0x18000227e  lea     rbp, [rsp-13C0h]
0x180002286  mov     eax, 14C0h
0x18000228b  call    _alloca_probe
0x180002290  sub     rsp, rax
0x180002293  mov     r14d, edx
0x180002296  mov     r15, rcx
0x180002299  mov     rsi, [rbp+13E0h+arg_28]
0x1800022a0  xor     edx, edx; Val
0x1800022a2  mov     r8d, 98h; Size
0x1800022a8  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x1800022ad  call    memset_0
0x1800022b2  nop
0x1800022b3  xor     r12d, r12d
0x1800022b6  mov     [rbp+13E0h+OutputString], r12w
0x1800022be  mov     [rbp+13E0h+var_1420], r12b
0x1800022c2  mov     rbx, [rbp+13E0h+arg_30]
0x1800022c9  mov     ecx, [rbx]; this
0x1800022cb  mov     [rsp+14E0h+var_14B8], ecx
0x1800022cf  mov     eax, [rbx+4]
0x1800022d2  mov     [rsp+14E0h+var_14B4], eax
0x1800022d6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800022db  mov     edi, eax
0x1800022dd  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x1800022e5  mov     ecx, r12d
0x1800022e8  lea     eax, [r12+8]
0x1800022ed  cmp     dword ptr [rbx+8], 1
0x1800022f1  cmovz   ecx, eax
0x1800022f4  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x1800022f8  lea     ecx, [rax-7]
0x1800022fb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002303  inc     ecx
0x180002305  mov     [rsp+14E0h+var_14B0], ecx
0x180002309  mov     [rsp+14E0h+var_14A8], r12
0x18000230e  call    cs:__imp_GetCurrentThreadId
0x180002314  mov     [rsp+14E0h+var_14A0], eax
0x180002318  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000231f  mov     [rsp+14E0h+var_1488], rax
0x180002324  mov     [rsp+14E0h+var_1480], r14d
0x180002329  mov     [rsp+14E0h+var_147C], edi
0x18000232d  mov     [rsp+14E0h+var_1498], r12
0x180002332  mov     [rsp+14E0h+var_1490], r12
0x180002337  mov     [rbp+13E0h+var_1438], rsi
0x18000233b  mov     [rbp+13E0h+var_1430], r15
0x18000233f  mov     [rsp+14E0h+var_1478], r12
0x180002344  xorps   xmm0, xmm0
0x180002347  xor     eax, eax
0x180002349  movups  [rbp+13E0h+var_1458], xmm0
0x18000234d  mov     [rbp+13E0h+var_1448], rax
0x180002351  xorps   xmm1, xmm1
0x180002354  movups  [rsp+14E0h+var_1470], xmm1
0x180002359  mov     [rbp+13E0h+var_1460], rax
0x18000235d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002364  test    rax, rax
0x180002367  jz      short loc_180002374
0x180002369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000236e  mov     [rbp+13E0h+var_1440], rax
0x180002372  jmp     short loc_180002378
0x180002374  mov     [rbp+13E0h+var_1440], r12
0x180002378  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000237f  test    rax, rax
0x180002382  jz      short loc_18000238E
0x180002384  lea     rcx, [rsp+14E0h+var_14C0]
0x180002389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000238e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002395  test    rax, rax
0x180002398  jz      short loc_1800023AE
0x18000239a  mov     r8d, 400h
0x1800023a0  lea     rdx, [rbp+13E0h+var_1420]
0x1800023a4  lea     rcx, [rsp+14E0h+var_14C0]
0x1800023a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023ae  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800023b5  test    rax, rax
0x1800023b8  jz      short loc_1800023C4
0x1800023ba  lea     rcx, [rsp+14E0h+var_14C0]
0x1800023bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023c4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800023cb  test    rax, rax
0x1800023ce  jz      short loc_1800023E1
0x1800023d0  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800023d5  jnz     short loc_1800023E1
0x1800023d7  lea     rcx, [rsp+14E0h+var_14C0]
0x1800023dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023e1  cmp     [rsp+14E0h+var_14B8], r12d
0x1800023e6  jl      short loc_1800023FA
0x1800023e8  mov     ecx, 8000FFFFh; this
0x1800023ed  mov     [rsp+14E0h+var_14B8], ecx
0x1800023f1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800023f6  mov     [rsp+14E0h+var_14B4], eax
0x1800023fa  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002401  jnz     short loc_180002422
0x180002403  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000240a  test    rax, rax
0x18000240d  jz      short loc_180002418
0x18000240f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002414  test    al, al
0x180002416  jmp     short loc_180002420
0x180002418  call    cs:__imp_IsDebuggerPresent
0x18000241e  test    eax, eax
0x180002420  jz      short loc_180002429
0x180002422  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002427  jz      short loc_18000244F
0x180002429  mov     rax, cs:g_pfnResultLoggingCallback
0x180002430  test    rax, rax
0x180002433  jz      short loc_1800024A8
0x180002435  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000243c  jnz     short loc_1800024A8
0x18000243e  xor     r8d, r8d
0x180002441  xor     edx, edx
0x180002443  lea     rcx, [rsp+14E0h+var_14C0]
0x180002448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000244d  jmp     short loc_1800024A8
0x18000244f  mov     ebx, 800h
0x180002454  mov     rax, cs:g_pfnResultLoggingCallback
0x18000245b  test    rax, rax
0x18000245e  jz      short loc_18000247D
0x180002460  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002467  jnz     short loc_18000247D
0x180002469  mov     r8d, ebx
0x18000246c  lea     rdx, [rbp+13E0h+OutputString]
0x180002473  lea     rcx, [rsp+14E0h+var_14C0]
0x180002478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000247d  cmp     [rbp+13E0h+OutputString], r12w
0x180002485  jnz     short loc_18000249B
0x180002487  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x18000248c  mov     rdx, rbx; unsigned __int16 *
0x18000248f  lea     rcx, [rbp+13E0h+OutputString]; this
0x180002496  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000249b  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x1800024a2  call    cs:__imp_OutputDebugStringW
0x1800024a8  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x1800024ad  jnz     short loc_1800024B8
0x1800024af  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800024b6  jz      short loc_1800024CA
0x1800024b8  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800024bf  test    rax, rax
0x1800024c2  jz      short loc_1800024CA
0x1800024c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024c9  nop
0x1800024ca  lea     rcx, [rsp+14E0h+var_14C0]; this
0x1800024cf  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
