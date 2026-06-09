# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002554`
- end: `0x1800027cd`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800022c4`

## callees

- `0x180002058`
- `0x180002554`
- `0x180003954`
- `0x1800040f4`
- `0x180004860`
- `0x1800058f0`
- `0x180009f20`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000260d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000260d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002710`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002710`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000279a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000279a`

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
0x180002554  mov     [rsp-8+arg_18], rbx
0x180002559  push    rbp
0x18000255a  push    rsi
0x18000255b  push    rdi
0x18000255c  push    r12
0x18000255e  push    r13
0x180002560  push    r14
0x180002562  push    r15
0x180002564  lea     rbp, [rsp-13C0h]
0x18000256c  mov     eax, 14C0h
0x180002571  call    _alloca_probe
0x180002576  sub     rsp, rax
0x180002579  mov     r14, r8
0x18000257c  mov     esi, edx
0x18000257e  mov     rdi, rcx
0x180002581  mov     r15, [rbp+13F0h+arg_28]
0x180002588  xor     edx, edx; Val
0x18000258a  mov     r8d, 98h; Size
0x180002590  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002595  call    memset_0
0x18000259a  nop
0x18000259b  xor     r13d, r13d
0x18000259e  mov     [rbp+13F0h+OutputString], r13w
0x1800025a6  mov     [rbp+13F0h+var_1430], r13b
0x1800025aa  mov     rbx, [rbp+13F0h+arg_30]
0x1800025b1  mov     ecx, [rbx]; this
0x1800025b3  mov     [rsp+14F0h+var_14C8], ecx
0x1800025b7  mov     eax, [rbx+4]
0x1800025ba  mov     [rsp+14F0h+var_14C4], eax
0x1800025be  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800025c3  mov     r12d, eax
0x1800025c6  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800025ce  mov     ecx, r13d
0x1800025d1  lea     eax, [r13+8]
0x1800025d5  cmp     dword ptr [rbx+8], 1
0x1800025d9  cmovz   ecx, eax
0x1800025dc  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800025e0  lea     ecx, [rax-7]
0x1800025e3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800025eb  inc     ecx
0x1800025ed  mov     [rsp+14F0h+var_14C0], ecx
0x1800025f1  mov     rcx, [rbp+13F0h+arg_38]
0x1800025f8  test    rcx, rcx
0x1800025fb  jz      short loc_180002608
0x1800025fd  cmp     [rcx], r13w
0x180002601  mov     [rsp+14F0h+var_14B8], rcx
0x180002606  jnz     short loc_18000260D
0x180002608  mov     [rsp+14F0h+var_14B8], r13
0x18000260d  call    cs:__imp_GetCurrentThreadId
0x180002613  mov     [rsp+14F0h+var_14B0], eax
0x180002617  mov     [rsp+14F0h+var_1498], r14
0x18000261c  mov     [rsp+14F0h+var_1490], esi
0x180002620  mov     [rsp+14F0h+var_148C], r12d
0x180002625  mov     [rsp+14F0h+var_14A8], r13
0x18000262a  mov     [rsp+14F0h+var_14A0], r13
0x18000262f  mov     [rbp+13F0h+var_1448], r15
0x180002633  mov     [rbp+13F0h+var_1440], rdi
0x180002637  mov     [rsp+14F0h+var_1488], r13
0x18000263c  xorps   xmm0, xmm0
0x18000263f  xor     eax, eax
0x180002641  movups  [rbp+13F0h+var_1468], xmm0
0x180002645  mov     [rbp+13F0h+var_1458], rax
0x180002649  xorps   xmm1, xmm1
0x18000264c  movups  [rsp+14F0h+var_1480], xmm1
0x180002651  mov     [rbp+13F0h+var_1470], rax
0x180002655  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000265c  test    rax, rax
0x18000265f  jz      short loc_18000266C
0x180002661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002666  mov     [rbp+13F0h+var_1450], rax
0x18000266a  jmp     short loc_180002670
0x18000266c  mov     [rbp+13F0h+var_1450], r13
0x180002670  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002677  test    rax, rax
0x18000267a  jz      short loc_180002686
0x18000267c  lea     rcx, [rsp+14F0h+var_14D0]
0x180002681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002686  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000268d  test    rax, rax
0x180002690  jz      short loc_1800026A6
0x180002692  mov     r8d, 400h
0x180002698  lea     rdx, [rbp+13F0h+var_1430]
0x18000269c  lea     rcx, [rsp+14F0h+var_14D0]
0x1800026a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026a6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800026ad  test    rax, rax
0x1800026b0  jz      short loc_1800026BC
0x1800026b2  lea     rcx, [rsp+14F0h+var_14D0]
0x1800026b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026bc  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800026c3  test    rax, rax
0x1800026c6  jz      short loc_1800026D9
0x1800026c8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800026cd  jnz     short loc_1800026D9
0x1800026cf  lea     rcx, [rsp+14F0h+var_14D0]
0x1800026d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026d9  cmp     [rsp+14F0h+var_14C8], r13d
0x1800026de  jl      short loc_1800026F2
0x1800026e0  mov     ecx, 8000FFFFh; this
0x1800026e5  mov     [rsp+14F0h+var_14C8], ecx
0x1800026e9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800026ee  mov     [rsp+14F0h+var_14C4], eax
0x1800026f2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800026f9  jnz     short loc_18000271A
0x1800026fb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002702  test    rax, rax
0x180002705  jz      short loc_180002710
0x180002707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000270c  test    al, al
0x18000270e  jmp     short loc_180002718
0x180002710  call    cs:__imp_IsDebuggerPresent
0x180002716  test    eax, eax
0x180002718  jz      short loc_180002721
0x18000271a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000271f  jz      short loc_180002747
0x180002721  mov     rax, cs:g_pfnResultLoggingCallback
0x180002728  test    rax, rax
0x18000272b  jz      short loc_1800027A0
0x18000272d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002734  jnz     short loc_1800027A0
0x180002736  xor     r8d, r8d
0x180002739  xor     edx, edx
0x18000273b  lea     rcx, [rsp+14F0h+var_14D0]
0x180002740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002745  jmp     short loc_1800027A0
0x180002747  mov     ebx, 800h
0x18000274c  mov     rax, cs:g_pfnResultLoggingCallback
0x180002753  test    rax, rax
0x180002756  jz      short loc_180002775
0x180002758  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000275f  jnz     short loc_180002775
0x180002761  mov     r8d, ebx
0x180002764  lea     rdx, [rbp+13F0h+OutputString]
0x18000276b  lea     rcx, [rsp+14F0h+var_14D0]
0x180002770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002775  cmp     [rbp+13F0h+OutputString], r13w
0x18000277d  jnz     short loc_180002793
0x18000277f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002784  mov     rdx, rbx; unsigned __int16 *
0x180002787  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000278e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002793  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000279a  call    cs:__imp_OutputDebugStringW
0x1800027a0  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800027a5  jnz     short loc_1800027B0
0x1800027a7  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800027ae  jz      short loc_1800027C2
0x1800027b0  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800027b7  test    rax, rax
0x1800027ba  jz      short loc_1800027C2
0x1800027bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027c1  nop
0x1800027c2  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800027c7  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
