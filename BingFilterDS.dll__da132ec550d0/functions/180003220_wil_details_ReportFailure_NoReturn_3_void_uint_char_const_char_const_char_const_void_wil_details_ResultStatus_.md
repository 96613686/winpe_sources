# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180003220`
- end: `0x180003499`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002f90`

## callees

- `0x180003220`
- `0x180004994`
- `0x180005188`
- `0x180005b60`
- `0x180006f10`
- `0x18000c4f2`
- `0x18000c5f0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800032d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800032d9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800033dc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800033dc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003466`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003466`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
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
0x180003220  mov     [rsp-8+arg_18], rbx
0x180003225  push    rbp
0x180003226  push    rsi
0x180003227  push    rdi
0x180003228  push    r12
0x18000322a  push    r13
0x18000322c  push    r14
0x18000322e  push    r15
0x180003230  lea     rbp, [rsp-13C0h]
0x180003238  mov     eax, 14C0h
0x18000323d  call    _alloca_probe
0x180003242  sub     rsp, rax
0x180003245  mov     r14, r8
0x180003248  mov     esi, edx
0x18000324a  mov     rdi, rcx
0x18000324d  mov     r15, [rbp+13F0h+arg_28]
0x180003254  xor     edx, edx; Val
0x180003256  mov     r8d, 98h; Size
0x18000325c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003261  call    memset_0
0x180003266  nop
0x180003267  xor     r13d, r13d
0x18000326a  mov     [rbp+13F0h+OutputString], r13w
0x180003272  mov     [rbp+13F0h+var_1430], r13b
0x180003276  mov     rbx, [rbp+13F0h+arg_30]
0x18000327d  mov     ecx, [rbx]; this
0x18000327f  mov     [rsp+14F0h+var_14C8], ecx
0x180003283  mov     eax, [rbx+4]
0x180003286  mov     [rsp+14F0h+var_14C4], eax
0x18000328a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000328f  mov     r12d, eax
0x180003292  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000329a  mov     ecx, r13d
0x18000329d  lea     eax, [r13+8]
0x1800032a1  cmp     dword ptr [rbx+8], 1
0x1800032a5  cmovz   ecx, eax
0x1800032a8  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800032ac  lea     ecx, [rax-7]
0x1800032af  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800032b7  inc     ecx
0x1800032b9  mov     [rsp+14F0h+var_14C0], ecx
0x1800032bd  mov     rcx, [rbp+13F0h+arg_38]
0x1800032c4  test    rcx, rcx
0x1800032c7  jz      short loc_1800032D4
0x1800032c9  cmp     [rcx], r13w
0x1800032cd  mov     [rsp+14F0h+var_14B8], rcx
0x1800032d2  jnz     short loc_1800032D9
0x1800032d4  mov     [rsp+14F0h+var_14B8], r13
0x1800032d9  call    cs:__imp_GetCurrentThreadId
0x1800032df  mov     [rsp+14F0h+var_14B0], eax
0x1800032e3  mov     [rsp+14F0h+var_1498], r14
0x1800032e8  mov     [rsp+14F0h+var_1490], esi
0x1800032ec  mov     [rsp+14F0h+var_148C], r12d
0x1800032f1  mov     [rsp+14F0h+var_14A8], r13
0x1800032f6  mov     [rsp+14F0h+var_14A0], r13
0x1800032fb  mov     [rbp+13F0h+var_1448], r15
0x1800032ff  mov     [rbp+13F0h+var_1440], rdi
0x180003303  mov     [rsp+14F0h+var_1488], r13
0x180003308  xorps   xmm0, xmm0
0x18000330b  xor     eax, eax
0x18000330d  movups  [rbp+13F0h+var_1468], xmm0
0x180003311  mov     [rbp+13F0h+var_1458], rax
0x180003315  xorps   xmm1, xmm1
0x180003318  movups  [rsp+14F0h+var_1480], xmm1
0x18000331d  mov     [rbp+13F0h+var_1470], rax
0x180003321  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003328  test    rax, rax
0x18000332b  jz      short loc_180003338
0x18000332d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003332  mov     [rbp+13F0h+var_1450], rax
0x180003336  jmp     short loc_18000333C
0x180003338  mov     [rbp+13F0h+var_1450], r13
0x18000333c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003343  test    rax, rax
0x180003346  jz      short loc_180003352
0x180003348  lea     rcx, [rsp+14F0h+var_14D0]
0x18000334d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003352  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003359  test    rax, rax
0x18000335c  jz      short loc_180003372
0x18000335e  mov     r8d, 400h
0x180003364  lea     rdx, [rbp+13F0h+var_1430]
0x180003368  lea     rcx, [rsp+14F0h+var_14D0]
0x18000336d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003372  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003379  test    rax, rax
0x18000337c  jz      short loc_180003388
0x18000337e  lea     rcx, [rsp+14F0h+var_14D0]
0x180003383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003388  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000338f  test    rax, rax
0x180003392  jz      short loc_1800033A5
0x180003394  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003399  jnz     short loc_1800033A5
0x18000339b  lea     rcx, [rsp+14F0h+var_14D0]
0x1800033a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033a5  cmp     [rsp+14F0h+var_14C8], r13d
0x1800033aa  jl      short loc_1800033BE
0x1800033ac  mov     ecx, 8000FFFFh; this
0x1800033b1  mov     [rsp+14F0h+var_14C8], ecx
0x1800033b5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800033ba  mov     [rsp+14F0h+var_14C4], eax
0x1800033be  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800033c5  jnz     short loc_1800033E6
0x1800033c7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800033ce  test    rax, rax
0x1800033d1  jz      short loc_1800033DC
0x1800033d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033d8  test    al, al
0x1800033da  jmp     short loc_1800033E4
0x1800033dc  call    cs:__imp_IsDebuggerPresent
0x1800033e2  test    eax, eax
0x1800033e4  jz      short loc_1800033ED
0x1800033e6  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800033eb  jz      short loc_180003413
0x1800033ed  mov     rax, cs:g_pfnResultLoggingCallback
0x1800033f4  test    rax, rax
0x1800033f7  jz      short loc_18000346C
0x1800033f9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003400  jnz     short loc_18000346C
0x180003402  xor     r8d, r8d
0x180003405  xor     edx, edx
0x180003407  lea     rcx, [rsp+14F0h+var_14D0]
0x18000340c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003411  jmp     short loc_18000346C
0x180003413  mov     ebx, 800h
0x180003418  mov     rax, cs:g_pfnResultLoggingCallback
0x18000341f  test    rax, rax
0x180003422  jz      short loc_180003441
0x180003424  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000342b  jnz     short loc_180003441
0x18000342d  mov     r8d, ebx
0x180003430  lea     rdx, [rbp+13F0h+OutputString]
0x180003437  lea     rcx, [rsp+14F0h+var_14D0]
0x18000343c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003441  cmp     [rbp+13F0h+OutputString], r13w
0x180003449  jnz     short loc_18000345F
0x18000344b  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003450  mov     rdx, rbx; unsigned __int16 *
0x180003453  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000345a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000345f  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003466  call    cs:__imp_OutputDebugStringW
0x18000346c  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003471  jnz     short loc_18000347C
0x180003473  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000347a  jz      short loc_18000348E
0x18000347c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003483  test    rax, rax
0x180003486  jz      short loc_18000348E
0x180003488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000348d  nop
0x18000348e  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003493  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
