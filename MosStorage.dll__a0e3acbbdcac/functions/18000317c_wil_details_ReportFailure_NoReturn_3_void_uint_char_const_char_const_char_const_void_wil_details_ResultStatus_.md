# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000317c`
- end: `0x1800033de`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002f20`

## callees

- `0x180002802`
- `0x18000317c`
- `0x180004514`
- `0x180004cb0`
- `0x180005410`
- `0x180006490`
- `0x18000e780`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000321e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000321e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003321`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003321`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800033ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800033ab`

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
0x18000317c  mov     [rsp-8+arg_18], rbx
0x180003181  push    rbp
0x180003182  push    rsi
0x180003183  push    rdi
0x180003184  push    r12
0x180003186  push    r13
0x180003188  push    r14
0x18000318a  push    r15
0x18000318c  lea     rbp, [rsp-13C0h]
0x180003194  mov     eax, 14C0h
0x180003199  call    _alloca_probe
0x18000319e  sub     rsp, rax
0x1800031a1  mov     r15, r8
0x1800031a4  mov     r14d, edx
0x1800031a7  mov     r12, rcx
0x1800031aa  mov     rsi, [rbp+13F0h+arg_28]
0x1800031b1  xor     edx, edx; Val
0x1800031b3  mov     r8d, 98h; Size
0x1800031b9  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800031be  call    memset_0
0x1800031c3  nop
0x1800031c4  xor     r13d, r13d
0x1800031c7  mov     [rbp+13F0h+OutputString], r13w
0x1800031cf  mov     [rbp+13F0h+var_1430], r13b
0x1800031d3  mov     rbx, [rbp+13F0h+arg_30]
0x1800031da  mov     ecx, [rbx]; this
0x1800031dc  mov     [rsp+14F0h+var_14C8], ecx
0x1800031e0  mov     eax, [rbx+4]
0x1800031e3  mov     [rsp+14F0h+var_14C4], eax
0x1800031e7  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800031ec  mov     edi, eax
0x1800031ee  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800031f6  mov     ecx, r13d
0x1800031f9  lea     eax, [r13+8]
0x1800031fd  cmp     dword ptr [rbx+8], 1
0x180003201  cmovz   ecx, eax
0x180003204  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003208  lea     ecx, [rax-7]
0x18000320b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003213  inc     ecx
0x180003215  mov     [rsp+14F0h+var_14C0], ecx
0x180003219  mov     [rsp+14F0h+var_14B8], r13
0x18000321e  call    cs:__imp_GetCurrentThreadId
0x180003224  mov     [rsp+14F0h+var_14B0], eax
0x180003228  mov     [rsp+14F0h+var_1498], r15
0x18000322d  mov     [rsp+14F0h+var_1490], r14d
0x180003232  mov     [rsp+14F0h+var_148C], edi
0x180003236  mov     [rsp+14F0h+var_14A8], r13
0x18000323b  mov     [rsp+14F0h+var_14A0], r13
0x180003240  mov     [rbp+13F0h+var_1448], rsi
0x180003244  mov     [rbp+13F0h+var_1440], r12
0x180003248  mov     [rsp+14F0h+var_1488], r13
0x18000324d  xorps   xmm0, xmm0
0x180003250  xor     eax, eax
0x180003252  movups  [rbp+13F0h+var_1468], xmm0
0x180003256  mov     [rbp+13F0h+var_1458], rax
0x18000325a  xorps   xmm1, xmm1
0x18000325d  movups  [rsp+14F0h+var_1480], xmm1
0x180003262  mov     [rbp+13F0h+var_1470], rax
0x180003266  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000326d  test    rax, rax
0x180003270  jz      short loc_18000327D
0x180003272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003277  mov     [rbp+13F0h+var_1450], rax
0x18000327b  jmp     short loc_180003281
0x18000327d  mov     [rbp+13F0h+var_1450], r13
0x180003281  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003288  test    rax, rax
0x18000328b  jz      short loc_180003297
0x18000328d  lea     rcx, [rsp+14F0h+var_14D0]
0x180003292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003297  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000329e  test    rax, rax
0x1800032a1  jz      short loc_1800032B7
0x1800032a3  mov     r8d, 400h
0x1800032a9  lea     rdx, [rbp+13F0h+var_1430]
0x1800032ad  lea     rcx, [rsp+14F0h+var_14D0]
0x1800032b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032b7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800032be  test    rax, rax
0x1800032c1  jz      short loc_1800032CD
0x1800032c3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800032c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032cd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800032d4  test    rax, rax
0x1800032d7  jz      short loc_1800032EA
0x1800032d9  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800032de  jnz     short loc_1800032EA
0x1800032e0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800032e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032ea  cmp     [rsp+14F0h+var_14C8], r13d
0x1800032ef  jl      short loc_180003303
0x1800032f1  mov     ecx, 8000FFFFh; this
0x1800032f6  mov     [rsp+14F0h+var_14C8], ecx
0x1800032fa  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800032ff  mov     [rsp+14F0h+var_14C4], eax
0x180003303  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000330a  jnz     short loc_18000332B
0x18000330c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003313  test    rax, rax
0x180003316  jz      short loc_180003321
0x180003318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000331d  test    al, al
0x18000331f  jmp     short loc_180003329
0x180003321  call    cs:__imp_IsDebuggerPresent
0x180003327  test    eax, eax
0x180003329  jz      short loc_180003332
0x18000332b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003330  jz      short loc_180003358
0x180003332  mov     rax, cs:g_pfnResultLoggingCallback
0x180003339  test    rax, rax
0x18000333c  jz      short loc_1800033B1
0x18000333e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003345  jnz     short loc_1800033B1
0x180003347  xor     r8d, r8d
0x18000334a  xor     edx, edx
0x18000334c  lea     rcx, [rsp+14F0h+var_14D0]
0x180003351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003356  jmp     short loc_1800033B1
0x180003358  mov     ebx, 800h
0x18000335d  mov     rax, cs:g_pfnResultLoggingCallback
0x180003364  test    rax, rax
0x180003367  jz      short loc_180003386
0x180003369  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003370  jnz     short loc_180003386
0x180003372  mov     r8d, ebx
0x180003375  lea     rdx, [rbp+13F0h+OutputString]
0x18000337c  lea     rcx, [rsp+14F0h+var_14D0]
0x180003381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003386  cmp     [rbp+13F0h+OutputString], r13w
0x18000338e  jnz     short loc_1800033A4
0x180003390  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003395  mov     rdx, rbx; unsigned __int16 *
0x180003398  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000339f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800033a4  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800033ab  call    cs:__imp_OutputDebugStringW
0x1800033b1  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800033b6  jnz     short loc_1800033C1
0x1800033b8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800033bf  jz      short loc_1800033D3
0x1800033c1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800033c8  test    rax, rax
0x1800033cb  jz      short loc_1800033D3
0x1800033cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033d2  nop
0x1800033d3  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800033d8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
