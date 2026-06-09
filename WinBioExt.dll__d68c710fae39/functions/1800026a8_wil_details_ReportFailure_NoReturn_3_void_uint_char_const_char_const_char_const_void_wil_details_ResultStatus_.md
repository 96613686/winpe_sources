# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800026a8`
- end: `0x180002921`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002430`

## callees

- `0x180002084`
- `0x1800026a8`
- `0x180003b04`
- `0x1800042a0`
- `0x180004a00`
- `0x180005a70`
- `0x180009f50`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002761`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002761`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002864`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002864`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800028ee`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800028ee`

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
0x1800026a8  mov     [rsp-8+arg_18], rbx
0x1800026ad  push    rbp
0x1800026ae  push    rsi
0x1800026af  push    rdi
0x1800026b0  push    r12
0x1800026b2  push    r13
0x1800026b4  push    r14
0x1800026b6  push    r15
0x1800026b8  lea     rbp, [rsp-13C0h]
0x1800026c0  mov     eax, 14C0h
0x1800026c5  call    _alloca_probe
0x1800026ca  sub     rsp, rax
0x1800026cd  mov     r14, r8
0x1800026d0  mov     esi, edx
0x1800026d2  mov     rdi, rcx
0x1800026d5  mov     r15, [rbp+13F0h+arg_28]
0x1800026dc  xor     edx, edx; Val
0x1800026de  mov     r8d, 98h; Size
0x1800026e4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800026e9  call    memset_0
0x1800026ee  nop
0x1800026ef  xor     r13d, r13d
0x1800026f2  mov     [rbp+13F0h+OutputString], r13w
0x1800026fa  mov     [rbp+13F0h+var_1430], r13b
0x1800026fe  mov     rbx, [rbp+13F0h+arg_30]
0x180002705  mov     ecx, [rbx]; this
0x180002707  mov     [rsp+14F0h+var_14C8], ecx
0x18000270b  mov     eax, [rbx+4]
0x18000270e  mov     [rsp+14F0h+var_14C4], eax
0x180002712  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002717  mov     r12d, eax
0x18000271a  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180002722  mov     ecx, r13d
0x180002725  lea     eax, [r13+8]
0x180002729  cmp     dword ptr [rbx+8], 1
0x18000272d  cmovz   ecx, eax
0x180002730  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002734  lea     ecx, [rax-7]
0x180002737  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000273f  inc     ecx
0x180002741  mov     [rsp+14F0h+var_14C0], ecx
0x180002745  mov     rcx, [rbp+13F0h+arg_38]
0x18000274c  test    rcx, rcx
0x18000274f  jz      short loc_18000275C
0x180002751  cmp     [rcx], r13w
0x180002755  mov     [rsp+14F0h+var_14B8], rcx
0x18000275a  jnz     short loc_180002761
0x18000275c  mov     [rsp+14F0h+var_14B8], r13
0x180002761  call    cs:__imp_GetCurrentThreadId
0x180002767  mov     [rsp+14F0h+var_14B0], eax
0x18000276b  mov     [rsp+14F0h+var_1498], r14
0x180002770  mov     [rsp+14F0h+var_1490], esi
0x180002774  mov     [rsp+14F0h+var_148C], r12d
0x180002779  mov     [rsp+14F0h+var_14A8], r13
0x18000277e  mov     [rsp+14F0h+var_14A0], r13
0x180002783  mov     [rbp+13F0h+var_1448], r15
0x180002787  mov     [rbp+13F0h+var_1440], rdi
0x18000278b  mov     [rsp+14F0h+var_1488], r13
0x180002790  xorps   xmm0, xmm0
0x180002793  xor     eax, eax
0x180002795  movups  [rbp+13F0h+var_1468], xmm0
0x180002799  mov     [rbp+13F0h+var_1458], rax
0x18000279d  xorps   xmm1, xmm1
0x1800027a0  movups  [rsp+14F0h+var_1480], xmm1
0x1800027a5  mov     [rbp+13F0h+var_1470], rax
0x1800027a9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800027b0  test    rax, rax
0x1800027b3  jz      short loc_1800027C0
0x1800027b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027ba  mov     [rbp+13F0h+var_1450], rax
0x1800027be  jmp     short loc_1800027C4
0x1800027c0  mov     [rbp+13F0h+var_1450], r13
0x1800027c4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800027cb  test    rax, rax
0x1800027ce  jz      short loc_1800027DA
0x1800027d0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800027d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027da  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800027e1  test    rax, rax
0x1800027e4  jz      short loc_1800027FA
0x1800027e6  mov     r8d, 400h
0x1800027ec  lea     rdx, [rbp+13F0h+var_1430]
0x1800027f0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800027f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027fa  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002801  test    rax, rax
0x180002804  jz      short loc_180002810
0x180002806  lea     rcx, [rsp+14F0h+var_14D0]
0x18000280b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002810  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002817  test    rax, rax
0x18000281a  jz      short loc_18000282D
0x18000281c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002821  jnz     short loc_18000282D
0x180002823  lea     rcx, [rsp+14F0h+var_14D0]
0x180002828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000282d  cmp     [rsp+14F0h+var_14C8], r13d
0x180002832  jl      short loc_180002846
0x180002834  mov     ecx, 8000FFFFh; this
0x180002839  mov     [rsp+14F0h+var_14C8], ecx
0x18000283d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002842  mov     [rsp+14F0h+var_14C4], eax
0x180002846  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000284d  jnz     short loc_18000286E
0x18000284f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002856  test    rax, rax
0x180002859  jz      short loc_180002864
0x18000285b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002860  test    al, al
0x180002862  jmp     short loc_18000286C
0x180002864  call    cs:__imp_IsDebuggerPresent
0x18000286a  test    eax, eax
0x18000286c  jz      short loc_180002875
0x18000286e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002873  jz      short loc_18000289B
0x180002875  mov     rax, cs:g_pfnResultLoggingCallback
0x18000287c  test    rax, rax
0x18000287f  jz      short loc_1800028F4
0x180002881  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002888  jnz     short loc_1800028F4
0x18000288a  xor     r8d, r8d
0x18000288d  xor     edx, edx
0x18000288f  lea     rcx, [rsp+14F0h+var_14D0]
0x180002894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002899  jmp     short loc_1800028F4
0x18000289b  mov     ebx, 800h
0x1800028a0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800028a7  test    rax, rax
0x1800028aa  jz      short loc_1800028C9
0x1800028ac  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800028b3  jnz     short loc_1800028C9
0x1800028b5  mov     r8d, ebx
0x1800028b8  lea     rdx, [rbp+13F0h+OutputString]
0x1800028bf  lea     rcx, [rsp+14F0h+var_14D0]
0x1800028c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028c9  cmp     [rbp+13F0h+OutputString], r13w
0x1800028d1  jnz     short loc_1800028E7
0x1800028d3  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800028d8  mov     rdx, rbx; unsigned __int16 *
0x1800028db  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800028e2  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800028e7  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800028ee  call    cs:__imp_OutputDebugStringW
0x1800028f4  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800028f9  jnz     short loc_180002904
0x1800028fb  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180002902  jz      short loc_180002916
0x180002904  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000290b  test    rax, rax
0x18000290e  jz      short loc_180002916
0x180002910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002915  nop
0x180002916  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000291b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
