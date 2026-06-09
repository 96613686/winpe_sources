# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x14000227c`
- end: `0x1400024de`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140002018`

## callees

- `0x140001f50`
- `0x14000227c`
- `0x140003704`
- `0x140003ea4`
- `0x1400045d0`
- `0x140005500`
- `0x140008990`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000231e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000231e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400024ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400024ab`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002421`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002421`

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
0x14000227c  mov     [rsp-8+arg_18], rbx
0x140002281  push    rbp
0x140002282  push    rsi
0x140002283  push    rdi
0x140002284  push    r12
0x140002286  push    r13
0x140002288  push    r14
0x14000228a  push    r15
0x14000228c  lea     rbp, [rsp-13C0h]
0x140002294  mov     eax, 14C0h
0x140002299  call    _alloca_probe
0x14000229e  sub     rsp, rax
0x1400022a1  mov     r15, r8
0x1400022a4  mov     r14d, edx
0x1400022a7  mov     r12, rcx
0x1400022aa  mov     rsi, [rbp+13F0h+arg_28]
0x1400022b1  xor     edx, edx; Val
0x1400022b3  mov     r8d, 98h; Size
0x1400022b9  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1400022be  call    memset_0
0x1400022c3  nop
0x1400022c4  xor     r13d, r13d
0x1400022c7  mov     [rbp+13F0h+OutputString], r13w
0x1400022cf  mov     [rbp+13F0h+var_1430], r13b
0x1400022d3  mov     rbx, [rbp+13F0h+arg_30]
0x1400022da  mov     ecx, [rbx]; this
0x1400022dc  mov     [rsp+14F0h+var_14C8], ecx
0x1400022e0  mov     eax, [rbx+4]
0x1400022e3  mov     [rsp+14F0h+var_14C4], eax
0x1400022e7  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400022ec  mov     edi, eax
0x1400022ee  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1400022f6  mov     ecx, r13d
0x1400022f9  lea     eax, [r13+8]
0x1400022fd  cmp     dword ptr [rbx+8], 1
0x140002301  cmovz   ecx, eax
0x140002304  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140002308  lea     ecx, [rax-7]
0x14000230b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002313  inc     ecx
0x140002315  mov     [rsp+14F0h+var_14C0], ecx
0x140002319  mov     [rsp+14F0h+var_14B8], r13
0x14000231e  call    cs:__imp_GetCurrentThreadId
0x140002324  mov     [rsp+14F0h+var_14B0], eax
0x140002328  mov     [rsp+14F0h+var_1498], r15
0x14000232d  mov     [rsp+14F0h+var_1490], r14d
0x140002332  mov     [rsp+14F0h+var_148C], edi
0x140002336  mov     [rsp+14F0h+var_14A8], r13
0x14000233b  mov     [rsp+14F0h+var_14A0], r13
0x140002340  mov     [rbp+13F0h+var_1448], rsi
0x140002344  mov     [rbp+13F0h+var_1440], r12
0x140002348  mov     [rsp+14F0h+var_1488], r13
0x14000234d  xorps   xmm0, xmm0
0x140002350  xor     eax, eax
0x140002352  movups  [rbp+13F0h+var_1468], xmm0
0x140002356  mov     [rbp+13F0h+var_1458], rax
0x14000235a  xorps   xmm1, xmm1
0x14000235d  movups  [rsp+14F0h+var_1480], xmm1
0x140002362  mov     [rbp+13F0h+var_1470], rax
0x140002366  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000236d  test    rax, rax
0x140002370  jz      short loc_14000237D
0x140002372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002377  mov     [rbp+13F0h+var_1450], rax
0x14000237b  jmp     short loc_140002381
0x14000237d  mov     [rbp+13F0h+var_1450], r13
0x140002381  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002388  test    rax, rax
0x14000238b  jz      short loc_140002397
0x14000238d  lea     rcx, [rsp+14F0h+var_14D0]
0x140002392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002397  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000239e  test    rax, rax
0x1400023a1  jz      short loc_1400023B7
0x1400023a3  mov     r8d, 400h
0x1400023a9  lea     rdx, [rbp+13F0h+var_1430]
0x1400023ad  lea     rcx, [rsp+14F0h+var_14D0]
0x1400023b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400023b7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400023be  test    rax, rax
0x1400023c1  jz      short loc_1400023CD
0x1400023c3  lea     rcx, [rsp+14F0h+var_14D0]
0x1400023c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400023cd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400023d4  test    rax, rax
0x1400023d7  jz      short loc_1400023EA
0x1400023d9  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400023de  jnz     short loc_1400023EA
0x1400023e0  lea     rcx, [rsp+14F0h+var_14D0]
0x1400023e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400023ea  cmp     [rsp+14F0h+var_14C8], r13d
0x1400023ef  jl      short loc_140002403
0x1400023f1  mov     ecx, 8000FFFFh; this
0x1400023f6  mov     [rsp+14F0h+var_14C8], ecx
0x1400023fa  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400023ff  mov     [rsp+14F0h+var_14C4], eax
0x140002403  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x14000240a  jnz     short loc_14000242B
0x14000240c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002413  test    rax, rax
0x140002416  jz      short loc_140002421
0x140002418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000241d  test    al, al
0x14000241f  jmp     short loc_140002429
0x140002421  call    cs:__imp_IsDebuggerPresent
0x140002427  test    eax, eax
0x140002429  jz      short loc_140002432
0x14000242b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002430  jz      short loc_140002458
0x140002432  mov     rax, cs:g_pfnResultLoggingCallback
0x140002439  test    rax, rax
0x14000243c  jz      short loc_1400024B1
0x14000243e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140002445  jnz     short loc_1400024B1
0x140002447  xor     r8d, r8d
0x14000244a  xor     edx, edx
0x14000244c  lea     rcx, [rsp+14F0h+var_14D0]
0x140002451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002456  jmp     short loc_1400024B1
0x140002458  mov     ebx, 800h
0x14000245d  mov     rax, cs:g_pfnResultLoggingCallback
0x140002464  test    rax, rax
0x140002467  jz      short loc_140002486
0x140002469  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140002470  jnz     short loc_140002486
0x140002472  mov     r8d, ebx
0x140002475  lea     rdx, [rbp+13F0h+OutputString]
0x14000247c  lea     rcx, [rsp+14F0h+var_14D0]
0x140002481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002486  cmp     [rbp+13F0h+OutputString], r13w
0x14000248e  jnz     short loc_1400024A4
0x140002490  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140002495  mov     rdx, rbx; unsigned __int16 *
0x140002498  lea     rcx, [rbp+13F0h+OutputString]; this
0x14000249f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400024a4  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1400024ab  call    cs:__imp_OutputDebugStringW
0x1400024b1  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1400024b6  jnz     short loc_1400024C1
0x1400024b8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1400024bf  jz      short loc_1400024D3
0x1400024c1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400024c8  test    rax, rax
0x1400024cb  jz      short loc_1400024D3
0x1400024cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400024d2  nop
0x1400024d3  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1400024d8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
