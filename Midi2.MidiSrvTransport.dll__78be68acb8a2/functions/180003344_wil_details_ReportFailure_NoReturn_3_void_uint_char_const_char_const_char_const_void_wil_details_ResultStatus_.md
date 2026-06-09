# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180003344`
- end: `0x1800035ad`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800030f0`

## callees

- `0x180002ff8`
- `0x180003344`
- `0x180005954`
- `0x1800060fc`
- `0x180006dd0`
- `0x180008f10`
- `0x180014020`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800033e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800033e6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000357a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000357a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800034f0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800034f0`

## string_xrefs

- `0x1800033f0`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180003344  mov     [rsp-8+arg_10], rbx
0x180003349  mov     [rsp-8+arg_18], rsi
0x18000334e  push    rbp
0x18000334f  push    rdi
0x180003350  push    r12
0x180003352  push    r14
0x180003354  push    r15
0x180003356  lea     rbp, [rsp-13C0h]
0x18000335e  mov     eax, 14C0h
0x180003363  call    _alloca_probe
0x180003368  sub     rsp, rax
0x18000336b  mov     r14d, edx
0x18000336e  mov     r15, rcx
0x180003371  mov     rsi, [rbp+13E0h+arg_28]
0x180003378  xor     edx, edx; Val
0x18000337a  mov     r8d, 98h; Size
0x180003380  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180003385  call    memset_0
0x18000338a  nop
0x18000338b  xor     r12d, r12d
0x18000338e  mov     [rbp+13E0h+OutputString], r12w
0x180003396  mov     [rbp+13E0h+var_1420], r12b
0x18000339a  mov     rbx, [rbp+13E0h+arg_30]
0x1800033a1  mov     ecx, [rbx]; this
0x1800033a3  mov     [rsp+14E0h+var_14B8], ecx
0x1800033a7  mov     eax, [rbx+4]
0x1800033aa  mov     [rsp+14E0h+var_14B4], eax
0x1800033ae  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800033b3  mov     edi, eax
0x1800033b5  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x1800033bd  mov     ecx, r12d
0x1800033c0  lea     eax, [r12+8]
0x1800033c5  cmp     dword ptr [rbx+8], 1
0x1800033c9  cmovz   ecx, eax
0x1800033cc  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x1800033d0  lea     ecx, [rax-7]
0x1800033d3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800033db  inc     ecx
0x1800033dd  mov     [rsp+14E0h+var_14B0], ecx
0x1800033e1  mov     [rsp+14E0h+var_14A8], r12
0x1800033e6  call    cs:__imp_GetCurrentThreadId
0x1800033ec  mov     [rsp+14E0h+var_14A0], eax
0x1800033f0  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800033f7  mov     [rsp+14E0h+var_1488], rax
0x1800033fc  mov     [rsp+14E0h+var_1480], r14d
0x180003401  mov     [rsp+14E0h+var_147C], edi
0x180003405  mov     [rsp+14E0h+var_1498], r12
0x18000340a  mov     [rsp+14E0h+var_1490], r12
0x18000340f  mov     [rbp+13E0h+var_1438], rsi
0x180003413  mov     [rbp+13E0h+var_1430], r15
0x180003417  mov     [rsp+14E0h+var_1478], r12
0x18000341c  xorps   xmm0, xmm0
0x18000341f  xor     eax, eax
0x180003421  movups  [rbp+13E0h+var_1458], xmm0
0x180003425  mov     [rbp+13E0h+var_1448], rax
0x180003429  xorps   xmm1, xmm1
0x18000342c  movups  [rsp+14E0h+var_1470], xmm1
0x180003431  mov     [rbp+13E0h+var_1460], rax
0x180003435  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000343c  test    rax, rax
0x18000343f  jz      short loc_18000344C
0x180003441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003446  mov     [rbp+13E0h+var_1440], rax
0x18000344a  jmp     short loc_180003450
0x18000344c  mov     [rbp+13E0h+var_1440], r12
0x180003450  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003457  test    rax, rax
0x18000345a  jz      short loc_180003466
0x18000345c  lea     rcx, [rsp+14E0h+var_14C0]
0x180003461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003466  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000346d  test    rax, rax
0x180003470  jz      short loc_180003486
0x180003472  mov     r8d, 400h
0x180003478  lea     rdx, [rbp+13E0h+var_1420]
0x18000347c  lea     rcx, [rsp+14E0h+var_14C0]
0x180003481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003486  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000348d  test    rax, rax
0x180003490  jz      short loc_18000349C
0x180003492  lea     rcx, [rsp+14E0h+var_14C0]
0x180003497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000349c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800034a3  test    rax, rax
0x1800034a6  jz      short loc_1800034B9
0x1800034a8  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800034ad  jnz     short loc_1800034B9
0x1800034af  lea     rcx, [rsp+14E0h+var_14C0]
0x1800034b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034b9  cmp     [rsp+14E0h+var_14B8], r12d
0x1800034be  jl      short loc_1800034D2
0x1800034c0  mov     ecx, 8000FFFFh; this
0x1800034c5  mov     [rsp+14E0h+var_14B8], ecx
0x1800034c9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800034ce  mov     [rsp+14E0h+var_14B4], eax
0x1800034d2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800034d9  jnz     short loc_1800034FA
0x1800034db  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800034e2  test    rax, rax
0x1800034e5  jz      short loc_1800034F0
0x1800034e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034ec  test    al, al
0x1800034ee  jmp     short loc_1800034F8
0x1800034f0  call    cs:__imp_IsDebuggerPresent
0x1800034f6  test    eax, eax
0x1800034f8  jz      short loc_180003501
0x1800034fa  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800034ff  jz      short loc_180003527
0x180003501  mov     rax, cs:g_pfnResultLoggingCallback
0x180003508  test    rax, rax
0x18000350b  jz      short loc_180003580
0x18000350d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003514  jnz     short loc_180003580
0x180003516  xor     r8d, r8d
0x180003519  xor     edx, edx
0x18000351b  lea     rcx, [rsp+14E0h+var_14C0]
0x180003520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003525  jmp     short loc_180003580
0x180003527  mov     ebx, 800h
0x18000352c  mov     rax, cs:g_pfnResultLoggingCallback
0x180003533  test    rax, rax
0x180003536  jz      short loc_180003555
0x180003538  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000353f  jnz     short loc_180003555
0x180003541  mov     r8d, ebx
0x180003544  lea     rdx, [rbp+13E0h+OutputString]
0x18000354b  lea     rcx, [rsp+14E0h+var_14C0]
0x180003550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003555  cmp     [rbp+13E0h+OutputString], r12w
0x18000355d  jnz     short loc_180003573
0x18000355f  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180003564  mov     rdx, rbx; unsigned __int16 *
0x180003567  lea     rcx, [rbp+13E0h+OutputString]; this
0x18000356e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003573  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x18000357a  call    cs:__imp_OutputDebugStringW
0x180003580  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180003585  jnz     short loc_180003590
0x180003587  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000358e  jz      short loc_1800035A2
0x180003590  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003597  test    rax, rax
0x18000359a  jz      short loc_1800035A2
0x18000359c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035a1  nop
0x1800035a2  lea     rcx, [rsp+14E0h+var_14C0]; this
0x1800035a7  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
