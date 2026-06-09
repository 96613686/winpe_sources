# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002464`
- end: `0x1800026cd`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002210`

## callees

- `0x180001ef2`
- `0x180002464`
- `0x180003844`
- `0x180003fe4`
- `0x180004710`
- `0x180005650`
- `0x180007f10`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002506`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002506`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002610`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002610`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000269a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000269a`

## string_xrefs

- `0x180002510`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180002464  mov     [rsp-8+arg_10], rbx
0x180002469  mov     [rsp-8+arg_18], rsi
0x18000246e  push    rbp
0x18000246f  push    rdi
0x180002470  push    r12
0x180002472  push    r14
0x180002474  push    r15
0x180002476  lea     rbp, [rsp-13C0h]
0x18000247e  mov     eax, 14C0h
0x180002483  call    _alloca_probe
0x180002488  sub     rsp, rax
0x18000248b  mov     r14d, edx
0x18000248e  mov     r15, rcx
0x180002491  mov     rsi, [rbp+13E0h+arg_28]
0x180002498  xor     edx, edx; Val
0x18000249a  mov     r8d, 98h; Size
0x1800024a0  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x1800024a5  call    memset_0
0x1800024aa  nop
0x1800024ab  xor     r12d, r12d
0x1800024ae  mov     [rbp+13E0h+OutputString], r12w
0x1800024b6  mov     [rbp+13E0h+var_1420], r12b
0x1800024ba  mov     rbx, [rbp+13E0h+arg_30]
0x1800024c1  mov     ecx, [rbx]; this
0x1800024c3  mov     [rsp+14E0h+var_14B8], ecx
0x1800024c7  mov     eax, [rbx+4]
0x1800024ca  mov     [rsp+14E0h+var_14B4], eax
0x1800024ce  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800024d3  mov     edi, eax
0x1800024d5  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x1800024dd  mov     ecx, r12d
0x1800024e0  lea     eax, [r12+8]
0x1800024e5  cmp     dword ptr [rbx+8], 1
0x1800024e9  cmovz   ecx, eax
0x1800024ec  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x1800024f0  lea     ecx, [rax-7]
0x1800024f3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800024fb  inc     ecx
0x1800024fd  mov     [rsp+14E0h+var_14B0], ecx
0x180002501  mov     [rsp+14E0h+var_14A8], r12
0x180002506  call    cs:__imp_GetCurrentThreadId
0x18000250c  mov     [rsp+14E0h+var_14A0], eax
0x180002510  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002517  mov     [rsp+14E0h+var_1488], rax
0x18000251c  mov     [rsp+14E0h+var_1480], r14d
0x180002521  mov     [rsp+14E0h+var_147C], edi
0x180002525  mov     [rsp+14E0h+var_1498], r12
0x18000252a  mov     [rsp+14E0h+var_1490], r12
0x18000252f  mov     [rbp+13E0h+var_1438], rsi
0x180002533  mov     [rbp+13E0h+var_1430], r15
0x180002537  mov     [rsp+14E0h+var_1478], r12
0x18000253c  xorps   xmm0, xmm0
0x18000253f  xor     eax, eax
0x180002541  movups  [rbp+13E0h+var_1458], xmm0
0x180002545  mov     [rbp+13E0h+var_1448], rax
0x180002549  xorps   xmm1, xmm1
0x18000254c  movups  [rsp+14E0h+var_1470], xmm1
0x180002551  mov     [rbp+13E0h+var_1460], rax
0x180002555  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000255c  test    rax, rax
0x18000255f  jz      short loc_18000256C
0x180002561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002566  mov     [rbp+13E0h+var_1440], rax
0x18000256a  jmp     short loc_180002570
0x18000256c  mov     [rbp+13E0h+var_1440], r12
0x180002570  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002577  test    rax, rax
0x18000257a  jz      short loc_180002586
0x18000257c  lea     rcx, [rsp+14E0h+var_14C0]
0x180002581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002586  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000258d  test    rax, rax
0x180002590  jz      short loc_1800025A6
0x180002592  mov     r8d, 400h
0x180002598  lea     rdx, [rbp+13E0h+var_1420]
0x18000259c  lea     rcx, [rsp+14E0h+var_14C0]
0x1800025a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025a6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800025ad  test    rax, rax
0x1800025b0  jz      short loc_1800025BC
0x1800025b2  lea     rcx, [rsp+14E0h+var_14C0]
0x1800025b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025bc  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800025c3  test    rax, rax
0x1800025c6  jz      short loc_1800025D9
0x1800025c8  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800025cd  jnz     short loc_1800025D9
0x1800025cf  lea     rcx, [rsp+14E0h+var_14C0]
0x1800025d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025d9  cmp     [rsp+14E0h+var_14B8], r12d
0x1800025de  jl      short loc_1800025F2
0x1800025e0  mov     ecx, 8000FFFFh; this
0x1800025e5  mov     [rsp+14E0h+var_14B8], ecx
0x1800025e9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800025ee  mov     [rsp+14E0h+var_14B4], eax
0x1800025f2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800025f9  jnz     short loc_18000261A
0x1800025fb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002602  test    rax, rax
0x180002605  jz      short loc_180002610
0x180002607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000260c  test    al, al
0x18000260e  jmp     short loc_180002618
0x180002610  call    cs:__imp_IsDebuggerPresent
0x180002616  test    eax, eax
0x180002618  jz      short loc_180002621
0x18000261a  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x18000261f  jz      short loc_180002647
0x180002621  mov     rax, cs:g_pfnResultLoggingCallback
0x180002628  test    rax, rax
0x18000262b  jz      short loc_1800026A0
0x18000262d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002634  jnz     short loc_1800026A0
0x180002636  xor     r8d, r8d
0x180002639  xor     edx, edx
0x18000263b  lea     rcx, [rsp+14E0h+var_14C0]
0x180002640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002645  jmp     short loc_1800026A0
0x180002647  mov     ebx, 800h
0x18000264c  mov     rax, cs:g_pfnResultLoggingCallback
0x180002653  test    rax, rax
0x180002656  jz      short loc_180002675
0x180002658  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000265f  jnz     short loc_180002675
0x180002661  mov     r8d, ebx
0x180002664  lea     rdx, [rbp+13E0h+OutputString]
0x18000266b  lea     rcx, [rsp+14E0h+var_14C0]
0x180002670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002675  cmp     [rbp+13E0h+OutputString], r12w
0x18000267d  jnz     short loc_180002693
0x18000267f  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180002684  mov     rdx, rbx; unsigned __int16 *
0x180002687  lea     rcx, [rbp+13E0h+OutputString]; this
0x18000268e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002693  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x18000269a  call    cs:__imp_OutputDebugStringW
0x1800026a0  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x1800026a5  jnz     short loc_1800026B0
0x1800026a7  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800026ae  jz      short loc_1800026C2
0x1800026b0  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800026b7  test    rax, rax
0x1800026ba  jz      short loc_1800026C2
0x1800026bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026c1  nop
0x1800026c2  lea     rcx, [rsp+14E0h+var_14C0]; this
0x1800026c7  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
