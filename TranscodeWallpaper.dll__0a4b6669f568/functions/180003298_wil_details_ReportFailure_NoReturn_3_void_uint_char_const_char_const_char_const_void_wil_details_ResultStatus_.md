# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180003298`
- end: `0x180003511`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002ec4`

## callees

- `0x180002cb4`
- `0x180003298`
- `0x180004874`
- `0x18000501c`
- `0x180005780`
- `0x1800068a0`
- `0x18000dd00`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003351`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003351`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003454`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003454`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800034de`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800034de`

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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v18, v16);
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
0x180003298  mov     [rsp-8+arg_18], rbx
0x18000329d  push    rbp
0x18000329e  push    rsi
0x18000329f  push    rdi
0x1800032a0  push    r12
0x1800032a2  push    r13
0x1800032a4  push    r14
0x1800032a6  push    r15
0x1800032a8  lea     rbp, [rsp-13C0h]
0x1800032b0  mov     eax, 14C0h
0x1800032b5  call    _alloca_probe
0x1800032ba  sub     rsp, rax
0x1800032bd  mov     r14, r8
0x1800032c0  mov     esi, edx
0x1800032c2  mov     rdi, rcx
0x1800032c5  mov     r15, [rbp+13F0h+arg_28]
0x1800032cc  xor     edx, edx; Val
0x1800032ce  mov     r8d, 98h; Size
0x1800032d4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800032d9  call    memset_0
0x1800032de  nop
0x1800032df  xor     r13d, r13d
0x1800032e2  mov     [rbp+13F0h+OutputString], r13w
0x1800032ea  mov     [rbp+13F0h+var_1430], r13b
0x1800032ee  mov     rbx, [rbp+13F0h+arg_30]
0x1800032f5  mov     ecx, [rbx]; this
0x1800032f7  mov     [rsp+14F0h+var_14C8], ecx
0x1800032fb  mov     eax, [rbx+4]
0x1800032fe  mov     [rsp+14F0h+var_14C4], eax
0x180003302  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003307  mov     r12d, eax
0x18000330a  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180003312  mov     ecx, r13d
0x180003315  lea     eax, [r13+8]
0x180003319  cmp     dword ptr [rbx+8], 1
0x18000331d  cmovz   ecx, eax
0x180003320  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003324  lea     ecx, [rax-7]
0x180003327  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000332f  inc     ecx
0x180003331  mov     [rsp+14F0h+var_14C0], ecx
0x180003335  mov     rcx, [rbp+13F0h+arg_38]
0x18000333c  test    rcx, rcx
0x18000333f  jz      short loc_18000334C
0x180003341  cmp     [rcx], r13w
0x180003345  mov     [rsp+14F0h+var_14B8], rcx
0x18000334a  jnz     short loc_180003351
0x18000334c  mov     [rsp+14F0h+var_14B8], r13
0x180003351  call    cs:__imp_GetCurrentThreadId
0x180003357  mov     [rsp+14F0h+var_14B0], eax
0x18000335b  mov     [rsp+14F0h+var_1498], r14
0x180003360  mov     [rsp+14F0h+var_1490], esi
0x180003364  mov     [rsp+14F0h+var_148C], r12d
0x180003369  mov     [rsp+14F0h+var_14A8], r13
0x18000336e  mov     [rsp+14F0h+var_14A0], r13
0x180003373  mov     [rbp+13F0h+var_1448], r15
0x180003377  mov     [rbp+13F0h+var_1440], rdi
0x18000337b  mov     [rsp+14F0h+var_1488], r13
0x180003380  xorps   xmm0, xmm0
0x180003383  xor     eax, eax
0x180003385  movups  [rbp+13F0h+var_1468], xmm0
0x180003389  mov     [rbp+13F0h+var_1458], rax
0x18000338d  xorps   xmm1, xmm1
0x180003390  movups  [rsp+14F0h+var_1480], xmm1
0x180003395  mov     [rbp+13F0h+var_1470], rax
0x180003399  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800033a0  test    rax, rax
0x1800033a3  jz      short loc_1800033B0
0x1800033a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033aa  mov     [rbp+13F0h+var_1450], rax
0x1800033ae  jmp     short loc_1800033B4
0x1800033b0  mov     [rbp+13F0h+var_1450], r13
0x1800033b4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800033bb  test    rax, rax
0x1800033be  jz      short loc_1800033CA
0x1800033c0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800033c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033ca  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800033d1  test    rax, rax
0x1800033d4  jz      short loc_1800033EA
0x1800033d6  mov     r8d, 400h
0x1800033dc  lea     rdx, [rbp+13F0h+var_1430]
0x1800033e0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800033e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033ea  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800033f1  test    rax, rax
0x1800033f4  jz      short loc_180003400
0x1800033f6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800033fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003400  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003407  test    rax, rax
0x18000340a  jz      short loc_18000341D
0x18000340c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003411  jnz     short loc_18000341D
0x180003413  lea     rcx, [rsp+14F0h+var_14D0]
0x180003418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000341d  cmp     [rsp+14F0h+var_14C8], r13d
0x180003422  jl      short loc_180003436
0x180003424  mov     ecx, 8000FFFFh; this
0x180003429  mov     [rsp+14F0h+var_14C8], ecx
0x18000342d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003432  mov     [rsp+14F0h+var_14C4], eax
0x180003436  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000343d  jnz     short loc_18000345E
0x18000343f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003446  test    rax, rax
0x180003449  jz      short loc_180003454
0x18000344b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003450  test    al, al
0x180003452  jmp     short loc_18000345C
0x180003454  call    cs:__imp_IsDebuggerPresent
0x18000345a  test    eax, eax
0x18000345c  jz      short loc_180003465
0x18000345e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003463  jz      short loc_18000348B
0x180003465  mov     rax, cs:g_pfnResultLoggingCallback
0x18000346c  test    rax, rax
0x18000346f  jz      short loc_1800034E4
0x180003471  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003478  jnz     short loc_1800034E4
0x18000347a  xor     r8d, r8d
0x18000347d  xor     edx, edx
0x18000347f  lea     rcx, [rsp+14F0h+var_14D0]
0x180003484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003489  jmp     short loc_1800034E4
0x18000348b  mov     ebx, 800h
0x180003490  mov     rax, cs:g_pfnResultLoggingCallback
0x180003497  test    rax, rax
0x18000349a  jz      short loc_1800034B9
0x18000349c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800034a3  jnz     short loc_1800034B9
0x1800034a5  mov     r8d, ebx
0x1800034a8  lea     rdx, [rbp+13F0h+OutputString]
0x1800034af  lea     rcx, [rsp+14F0h+var_14D0]
0x1800034b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034b9  cmp     [rbp+13F0h+OutputString], r13w
0x1800034c1  jnz     short loc_1800034D7
0x1800034c3  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800034c8  mov     rdx, rbx; wchar_t *
0x1800034cb  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800034d2  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800034d7  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800034de  call    cs:__imp_OutputDebugStringW
0x1800034e4  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800034e9  jnz     short loc_1800034F4
0x1800034eb  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800034f2  jz      short loc_180003506
0x1800034f4  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800034fb  test    rax, rax
0x1800034fe  jz      short loc_180003506
0x180003500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003505  nop
0x180003506  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000350b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
