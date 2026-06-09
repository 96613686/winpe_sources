# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180003218`
- end: `0x18000347a`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002fc0`

## callees

- `0x180002158`
- `0x180003218`
- `0x180004bd4`
- `0x18000537c`
- `0x180006350`
- `0x180006e90`
- `0x18000eda0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800032ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800032ba`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003447`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003447`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800033bd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800033bd`

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
        int *a7)
{
  int v10; // edx
  int v11; // edi
  int v12; // ecx
  const struct wil::FailureInfo *v13; // rdx
  __int64 v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v19, v10);
  v17 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v18 = v12;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v11;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
  {
    v19 = -2147418113;
    v20 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v13);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( (v18 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v14);
  }
  wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180003218  mov     [rsp-8+arg_18], rbx
0x18000321d  push    rbp
0x18000321e  push    rsi
0x18000321f  push    rdi
0x180003220  push    r12
0x180003222  push    r13
0x180003224  push    r14
0x180003226  push    r15
0x180003228  lea     rbp, [rsp-13C0h]
0x180003230  mov     eax, 14C0h
0x180003235  call    _alloca_probe
0x18000323a  sub     rsp, rax
0x18000323d  mov     r15, r8
0x180003240  mov     r14d, edx
0x180003243  mov     r12, rcx
0x180003246  mov     rsi, [rbp+13F0h+arg_28]
0x18000324d  xor     edx, edx; Val
0x18000324f  mov     r8d, 98h; Size
0x180003255  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000325a  call    memset_0
0x18000325f  nop
0x180003260  xor     r13d, r13d
0x180003263  mov     [rbp+13F0h+OutputString], r13w
0x18000326b  mov     [rbp+13F0h+var_1430], r13b
0x18000326f  mov     rbx, [rbp+13F0h+arg_30]
0x180003276  mov     ecx, [rbx]; this
0x180003278  mov     [rsp+14F0h+var_14C8], ecx
0x18000327c  mov     eax, [rbx+4]
0x18000327f  mov     [rsp+14F0h+var_14C4], eax
0x180003283  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003288  mov     edi, eax
0x18000328a  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180003292  mov     ecx, r13d
0x180003295  lea     eax, [r13+8]
0x180003299  cmp     dword ptr [rbx+8], 1
0x18000329d  cmovz   ecx, eax
0x1800032a0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800032a4  lea     ecx, [rax-7]
0x1800032a7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800032af  inc     ecx
0x1800032b1  mov     [rsp+14F0h+var_14C0], ecx
0x1800032b5  mov     [rsp+14F0h+var_14B8], r13
0x1800032ba  call    cs:__imp_GetCurrentThreadId
0x1800032c0  mov     [rsp+14F0h+var_14B0], eax
0x1800032c4  mov     [rsp+14F0h+var_1498], r15
0x1800032c9  mov     [rsp+14F0h+var_1490], r14d
0x1800032ce  mov     [rsp+14F0h+var_148C], edi
0x1800032d2  mov     [rsp+14F0h+var_14A8], r13
0x1800032d7  mov     [rsp+14F0h+var_14A0], r13
0x1800032dc  mov     [rbp+13F0h+var_1448], rsi
0x1800032e0  mov     [rbp+13F0h+var_1440], r12
0x1800032e4  mov     [rsp+14F0h+var_1488], r13
0x1800032e9  xorps   xmm0, xmm0
0x1800032ec  xor     eax, eax
0x1800032ee  movups  [rbp+13F0h+var_1468], xmm0
0x1800032f2  mov     [rbp+13F0h+var_1458], rax
0x1800032f6  xorps   xmm1, xmm1
0x1800032f9  movups  [rsp+14F0h+var_1480], xmm1
0x1800032fe  mov     [rbp+13F0h+var_1470], rax
0x180003302  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003309  test    rax, rax
0x18000330c  jz      short loc_180003319
0x18000330e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003313  mov     [rbp+13F0h+var_1450], rax
0x180003317  jmp     short loc_18000331D
0x180003319  mov     [rbp+13F0h+var_1450], r13
0x18000331d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003324  test    rax, rax
0x180003327  jz      short loc_180003333
0x180003329  lea     rcx, [rsp+14F0h+var_14D0]
0x18000332e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003333  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000333a  test    rax, rax
0x18000333d  jz      short loc_180003353
0x18000333f  mov     r8d, 400h
0x180003345  lea     rdx, [rbp+13F0h+var_1430]
0x180003349  lea     rcx, [rsp+14F0h+var_14D0]
0x18000334e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003353  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000335a  test    rax, rax
0x18000335d  jz      short loc_180003369
0x18000335f  lea     rcx, [rsp+14F0h+var_14D0]
0x180003364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003369  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003370  test    rax, rax
0x180003373  jz      short loc_180003386
0x180003375  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000337a  jnz     short loc_180003386
0x18000337c  lea     rcx, [rsp+14F0h+var_14D0]
0x180003381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003386  cmp     [rsp+14F0h+var_14C8], r13d
0x18000338b  jl      short loc_18000339F
0x18000338d  mov     ecx, 8000FFFFh; this
0x180003392  mov     [rsp+14F0h+var_14C8], ecx
0x180003396  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000339b  mov     [rsp+14F0h+var_14C4], eax
0x18000339f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800033a6  jnz     short loc_1800033C7
0x1800033a8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800033af  test    rax, rax
0x1800033b2  jz      short loc_1800033BD
0x1800033b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033b9  test    al, al
0x1800033bb  jmp     short loc_1800033C5
0x1800033bd  call    cs:__imp_IsDebuggerPresent
0x1800033c3  test    eax, eax
0x1800033c5  jz      short loc_1800033CE
0x1800033c7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800033cc  jz      short loc_1800033F4
0x1800033ce  mov     rax, cs:g_pfnResultLoggingCallback
0x1800033d5  test    rax, rax
0x1800033d8  jz      short loc_18000344D
0x1800033da  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800033e1  jnz     short loc_18000344D
0x1800033e3  xor     r8d, r8d
0x1800033e6  xor     edx, edx
0x1800033e8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800033ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033f2  jmp     short loc_18000344D
0x1800033f4  mov     ebx, 800h
0x1800033f9  mov     rax, cs:g_pfnResultLoggingCallback
0x180003400  test    rax, rax
0x180003403  jz      short loc_180003422
0x180003405  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000340c  jnz     short loc_180003422
0x18000340e  mov     r8d, ebx
0x180003411  lea     rdx, [rbp+13F0h+OutputString]
0x180003418  lea     rcx, [rsp+14F0h+var_14D0]
0x18000341d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003422  cmp     [rbp+13F0h+OutputString], r13w
0x18000342a  jnz     short loc_180003440
0x18000342c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003431  mov     rdx, rbx; unsigned __int16 *
0x180003434  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000343b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003440  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003447  call    cs:__imp_OutputDebugStringW
0x18000344d  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003452  jnz     short loc_18000345D
0x180003454  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000345b  jz      short loc_18000346F
0x18000345d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003464  test    rax, rax
0x180003467  jz      short loc_18000346F
0x180003469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000346e  nop
0x18000346f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003474  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
