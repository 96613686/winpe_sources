# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002838`
- end: `0x180002a9a`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800025dc`

## callees

- `0x180002034`
- `0x180002838`
- `0x180004f64`
- `0x180005700`
- `0x1800067f0`
- `0x180008fa0`
- `0x1800136a0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800028da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800028da`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002a67`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002a67`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800029dd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800029dd`

## pseudocode

```c
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
0x180002838  mov     [rsp-8+arg_18], rbx
0x18000283d  push    rbp
0x18000283e  push    rsi
0x18000283f  push    rdi
0x180002840  push    r12
0x180002842  push    r13
0x180002844  push    r14
0x180002846  push    r15
0x180002848  lea     rbp, [rsp-13C0h]
0x180002850  mov     eax, 14C0h
0x180002855  call    _alloca_probe
0x18000285a  sub     rsp, rax
0x18000285d  mov     r15, r8
0x180002860  mov     r14d, edx
0x180002863  mov     r12, rcx
0x180002866  mov     rsi, [rbp+13F0h+arg_28]
0x18000286d  xor     edx, edx; Val
0x18000286f  mov     r8d, 98h; Size
0x180002875  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000287a  call    memset_0
0x18000287f  nop
0x180002880  xor     r13d, r13d
0x180002883  mov     [rbp+13F0h+OutputString], r13w
0x18000288b  mov     [rbp+13F0h+var_1430], r13b
0x18000288f  mov     rbx, [rbp+13F0h+arg_30]
0x180002896  mov     ecx, [rbx]; this
0x180002898  mov     [rsp+14F0h+var_14C8], ecx
0x18000289c  mov     eax, [rbx+4]
0x18000289f  mov     [rsp+14F0h+var_14C4], eax
0x1800028a3  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800028a8  mov     edi, eax
0x1800028aa  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800028b2  mov     ecx, r13d
0x1800028b5  lea     eax, [r13+8]
0x1800028b9  cmp     dword ptr [rbx+8], 1
0x1800028bd  cmovz   ecx, eax
0x1800028c0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800028c4  lea     ecx, [rax-7]
0x1800028c7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800028cf  inc     ecx
0x1800028d1  mov     [rsp+14F0h+var_14C0], ecx
0x1800028d5  mov     [rsp+14F0h+var_14B8], r13
0x1800028da  call    cs:__imp_GetCurrentThreadId
0x1800028e0  mov     [rsp+14F0h+var_14B0], eax
0x1800028e4  mov     [rsp+14F0h+var_1498], r15
0x1800028e9  mov     [rsp+14F0h+var_1490], r14d
0x1800028ee  mov     [rsp+14F0h+var_148C], edi
0x1800028f2  mov     [rsp+14F0h+var_14A8], r13
0x1800028f7  mov     [rsp+14F0h+var_14A0], r13
0x1800028fc  mov     [rbp+13F0h+var_1448], rsi
0x180002900  mov     [rbp+13F0h+var_1440], r12
0x180002904  mov     [rsp+14F0h+var_1488], r13
0x180002909  xorps   xmm0, xmm0
0x18000290c  xor     eax, eax
0x18000290e  movups  [rbp+13F0h+var_1468], xmm0
0x180002912  mov     [rbp+13F0h+var_1458], rax
0x180002916  xorps   xmm1, xmm1
0x180002919  movups  [rsp+14F0h+var_1480], xmm1
0x18000291e  mov     [rbp+13F0h+var_1470], rax
0x180002922  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002929  test    rax, rax
0x18000292c  jz      short loc_180002939
0x18000292e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002933  mov     [rbp+13F0h+var_1450], rax
0x180002937  jmp     short loc_18000293D
0x180002939  mov     [rbp+13F0h+var_1450], r13
0x18000293d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002944  test    rax, rax
0x180002947  jz      short loc_180002953
0x180002949  lea     rcx, [rsp+14F0h+var_14D0]
0x18000294e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002953  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000295a  test    rax, rax
0x18000295d  jz      short loc_180002973
0x18000295f  mov     r8d, 400h
0x180002965  lea     rdx, [rbp+13F0h+var_1430]
0x180002969  lea     rcx, [rsp+14F0h+var_14D0]
0x18000296e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002973  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000297a  test    rax, rax
0x18000297d  jz      short loc_180002989
0x18000297f  lea     rcx, [rsp+14F0h+var_14D0]
0x180002984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002989  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002990  test    rax, rax
0x180002993  jz      short loc_1800029A6
0x180002995  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000299a  jnz     short loc_1800029A6
0x18000299c  lea     rcx, [rsp+14F0h+var_14D0]
0x1800029a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029a6  cmp     [rsp+14F0h+var_14C8], r13d
0x1800029ab  jl      short loc_1800029BF
0x1800029ad  mov     ecx, 8000FFFFh; this
0x1800029b2  mov     [rsp+14F0h+var_14C8], ecx
0x1800029b6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800029bb  mov     [rsp+14F0h+var_14C4], eax
0x1800029bf  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800029c6  jnz     short loc_1800029E7
0x1800029c8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800029cf  test    rax, rax
0x1800029d2  jz      short loc_1800029DD
0x1800029d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029d9  test    al, al
0x1800029db  jmp     short loc_1800029E5
0x1800029dd  call    cs:__imp_IsDebuggerPresent
0x1800029e3  test    eax, eax
0x1800029e5  jz      short loc_1800029EE
0x1800029e7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800029ec  jz      short loc_180002A14
0x1800029ee  mov     rax, cs:g_pfnResultLoggingCallback
0x1800029f5  test    rax, rax
0x1800029f8  jz      short loc_180002A6D
0x1800029fa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002a01  jnz     short loc_180002A6D
0x180002a03  xor     r8d, r8d
0x180002a06  xor     edx, edx
0x180002a08  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a12  jmp     short loc_180002A6D
0x180002a14  mov     ebx, 800h
0x180002a19  mov     rax, cs:g_pfnResultLoggingCallback
0x180002a20  test    rax, rax
0x180002a23  jz      short loc_180002A42
0x180002a25  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002a2c  jnz     short loc_180002A42
0x180002a2e  mov     r8d, ebx
0x180002a31  lea     rdx, [rbp+13F0h+OutputString]
0x180002a38  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a42  cmp     [rbp+13F0h+OutputString], r13w
0x180002a4a  jnz     short loc_180002A60
0x180002a4c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002a51  mov     rdx, rbx; unsigned __int16 *
0x180002a54  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002a5b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002a60  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002a67  call    cs:__imp_OutputDebugStringW
0x180002a6d  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002a72  jnz     short loc_180002A7D
0x180002a74  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180002a7b  jz      short loc_180002A8F
0x180002a7d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002a84  test    rax, rax
0x180002a87  jz      short loc_180002A8F
0x180002a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a8e  nop
0x180002a8f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002a94  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
