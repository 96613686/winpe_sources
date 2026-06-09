# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800026a4`
- end: `0x180002906`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002448`

## callees

- `0x1800026a4`
- `0x1800055e4`
- `0x180005d9c`
- `0x1800076c0`
- `0x18000a130`
- `0x18000c5e2`
- `0x18000c6d0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002746`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002746`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002849`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002849`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800028d3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800028d3`

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
0x1800026a4  mov     [rsp-8+arg_18], rbx
0x1800026a9  push    rbp
0x1800026aa  push    rsi
0x1800026ab  push    rdi
0x1800026ac  push    r12
0x1800026ae  push    r13
0x1800026b0  push    r14
0x1800026b2  push    r15
0x1800026b4  lea     rbp, [rsp-13C0h]
0x1800026bc  mov     eax, 14C0h
0x1800026c1  call    _alloca_probe
0x1800026c6  sub     rsp, rax
0x1800026c9  mov     r15, r8
0x1800026cc  mov     r14d, edx
0x1800026cf  mov     r12, rcx
0x1800026d2  mov     rsi, [rbp+13F0h+arg_28]
0x1800026d9  xor     edx, edx; Val
0x1800026db  mov     r8d, 98h; Size
0x1800026e1  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800026e6  call    memset_0
0x1800026eb  nop
0x1800026ec  xor     r13d, r13d
0x1800026ef  mov     [rbp+13F0h+OutputString], r13w
0x1800026f7  mov     [rbp+13F0h+var_1430], r13b
0x1800026fb  mov     rbx, [rbp+13F0h+arg_30]
0x180002702  mov     ecx, [rbx]; this
0x180002704  mov     [rsp+14F0h+var_14C8], ecx
0x180002708  mov     eax, [rbx+4]
0x18000270b  mov     [rsp+14F0h+var_14C4], eax
0x18000270f  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002714  mov     edi, eax
0x180002716  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000271e  mov     ecx, r13d
0x180002721  lea     eax, [r13+8]
0x180002725  cmp     dword ptr [rbx+8], 1
0x180002729  cmovz   ecx, eax
0x18000272c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002730  lea     ecx, [rax-7]
0x180002733  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000273b  inc     ecx
0x18000273d  mov     [rsp+14F0h+var_14C0], ecx
0x180002741  mov     [rsp+14F0h+var_14B8], r13
0x180002746  call    cs:__imp_GetCurrentThreadId
0x18000274c  mov     [rsp+14F0h+var_14B0], eax
0x180002750  mov     [rsp+14F0h+var_1498], r15
0x180002755  mov     [rsp+14F0h+var_1490], r14d
0x18000275a  mov     [rsp+14F0h+var_148C], edi
0x18000275e  mov     [rsp+14F0h+var_14A8], r13
0x180002763  mov     [rsp+14F0h+var_14A0], r13
0x180002768  mov     [rbp+13F0h+var_1448], rsi
0x18000276c  mov     [rbp+13F0h+var_1440], r12
0x180002770  mov     [rsp+14F0h+var_1488], r13
0x180002775  xorps   xmm0, xmm0
0x180002778  xor     eax, eax
0x18000277a  movups  [rbp+13F0h+var_1468], xmm0
0x18000277e  mov     [rbp+13F0h+var_1458], rax
0x180002782  xorps   xmm1, xmm1
0x180002785  movups  [rsp+14F0h+var_1480], xmm1
0x18000278a  mov     [rbp+13F0h+var_1470], rax
0x18000278e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002795  test    rax, rax
0x180002798  jz      short loc_1800027A5
0x18000279a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000279f  mov     [rbp+13F0h+var_1450], rax
0x1800027a3  jmp     short loc_1800027A9
0x1800027a5  mov     [rbp+13F0h+var_1450], r13
0x1800027a9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800027b0  test    rax, rax
0x1800027b3  jz      short loc_1800027BF
0x1800027b5  lea     rcx, [rsp+14F0h+var_14D0]
0x1800027ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027bf  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800027c6  test    rax, rax
0x1800027c9  jz      short loc_1800027DF
0x1800027cb  mov     r8d, 400h
0x1800027d1  lea     rdx, [rbp+13F0h+var_1430]
0x1800027d5  lea     rcx, [rsp+14F0h+var_14D0]
0x1800027da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027df  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800027e6  test    rax, rax
0x1800027e9  jz      short loc_1800027F5
0x1800027eb  lea     rcx, [rsp+14F0h+var_14D0]
0x1800027f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027f5  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800027fc  test    rax, rax
0x1800027ff  jz      short loc_180002812
0x180002801  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002806  jnz     short loc_180002812
0x180002808  lea     rcx, [rsp+14F0h+var_14D0]
0x18000280d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002812  cmp     [rsp+14F0h+var_14C8], r13d
0x180002817  jl      short loc_18000282B
0x180002819  mov     ecx, 8000FFFFh; this
0x18000281e  mov     [rsp+14F0h+var_14C8], ecx
0x180002822  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002827  mov     [rsp+14F0h+var_14C4], eax
0x18000282b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180002832  jnz     short loc_180002853
0x180002834  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000283b  test    rax, rax
0x18000283e  jz      short loc_180002849
0x180002840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002845  test    al, al
0x180002847  jmp     short loc_180002851
0x180002849  call    cs:__imp_IsDebuggerPresent
0x18000284f  test    eax, eax
0x180002851  jz      short loc_18000285A
0x180002853  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002858  jz      short loc_180002880
0x18000285a  mov     rax, cs:g_pfnResultLoggingCallback
0x180002861  test    rax, rax
0x180002864  jz      short loc_1800028D9
0x180002866  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000286d  jnz     short loc_1800028D9
0x18000286f  xor     r8d, r8d
0x180002872  xor     edx, edx
0x180002874  lea     rcx, [rsp+14F0h+var_14D0]
0x180002879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000287e  jmp     short loc_1800028D9
0x180002880  mov     ebx, 800h
0x180002885  mov     rax, cs:g_pfnResultLoggingCallback
0x18000288c  test    rax, rax
0x18000288f  jz      short loc_1800028AE
0x180002891  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002898  jnz     short loc_1800028AE
0x18000289a  mov     r8d, ebx
0x18000289d  lea     rdx, [rbp+13F0h+OutputString]
0x1800028a4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800028a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028ae  cmp     [rbp+13F0h+OutputString], r13w
0x1800028b6  jnz     short loc_1800028CC
0x1800028b8  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800028bd  mov     rdx, rbx; unsigned __int16 *
0x1800028c0  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800028c7  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800028cc  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800028d3  call    cs:__imp_OutputDebugStringW
0x1800028d9  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800028de  jnz     short loc_1800028E9
0x1800028e0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800028e7  jz      short loc_1800028FB
0x1800028e9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800028f0  test    rax, rax
0x1800028f3  jz      short loc_1800028FB
0x1800028f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028fa  nop
0x1800028fb  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002900  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
