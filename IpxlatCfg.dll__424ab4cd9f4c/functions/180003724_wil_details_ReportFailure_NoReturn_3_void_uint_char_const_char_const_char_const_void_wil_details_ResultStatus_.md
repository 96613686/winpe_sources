# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180003724`
- end: `0x180003986`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800034c8`

## callees

- `0x180002a28`
- `0x180003724`
- `0x180005c34`
- `0x1800063d0`
- `0x180007350`
- `0x1800099f0`
- `0x180017e10`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003953`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003953`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800038c9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800038c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800037c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800037c6`

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
0x180003724  mov     [rsp-8+arg_18], rbx
0x180003729  push    rbp
0x18000372a  push    rsi
0x18000372b  push    rdi
0x18000372c  push    r12
0x18000372e  push    r13
0x180003730  push    r14
0x180003732  push    r15
0x180003734  lea     rbp, [rsp-13C0h]
0x18000373c  mov     eax, 14C0h
0x180003741  call    _alloca_probe
0x180003746  sub     rsp, rax
0x180003749  mov     r15, r8
0x18000374c  mov     r14d, edx
0x18000374f  mov     r12, rcx
0x180003752  mov     rsi, [rbp+13F0h+arg_28]
0x180003759  xor     edx, edx; Val
0x18000375b  mov     r8d, 98h; Size
0x180003761  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003766  call    memset_0
0x18000376b  nop
0x18000376c  xor     r13d, r13d
0x18000376f  mov     [rbp+13F0h+OutputString], r13w
0x180003777  mov     [rbp+13F0h+var_1430], r13b
0x18000377b  mov     rbx, [rbp+13F0h+arg_30]
0x180003782  mov     ecx, [rbx]; this
0x180003784  mov     [rsp+14F0h+var_14C8], ecx
0x180003788  mov     eax, [rbx+4]
0x18000378b  mov     [rsp+14F0h+var_14C4], eax
0x18000378f  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003794  mov     edi, eax
0x180003796  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000379e  mov     ecx, r13d
0x1800037a1  lea     eax, [r13+8]
0x1800037a5  cmp     dword ptr [rbx+8], 1
0x1800037a9  cmovz   ecx, eax
0x1800037ac  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800037b0  lea     ecx, [rax-7]
0x1800037b3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800037bb  inc     ecx
0x1800037bd  mov     [rsp+14F0h+var_14C0], ecx
0x1800037c1  mov     [rsp+14F0h+var_14B8], r13
0x1800037c6  call    cs:__imp_GetCurrentThreadId
0x1800037cc  mov     [rsp+14F0h+var_14B0], eax
0x1800037d0  mov     [rsp+14F0h+var_1498], r15
0x1800037d5  mov     [rsp+14F0h+var_1490], r14d
0x1800037da  mov     [rsp+14F0h+var_148C], edi
0x1800037de  mov     [rsp+14F0h+var_14A8], r13
0x1800037e3  mov     [rsp+14F0h+var_14A0], r13
0x1800037e8  mov     [rbp+13F0h+var_1448], rsi
0x1800037ec  mov     [rbp+13F0h+var_1440], r12
0x1800037f0  mov     [rsp+14F0h+var_1488], r13
0x1800037f5  xorps   xmm0, xmm0
0x1800037f8  xor     eax, eax
0x1800037fa  movups  [rbp+13F0h+var_1468], xmm0
0x1800037fe  mov     [rbp+13F0h+var_1458], rax
0x180003802  xorps   xmm1, xmm1
0x180003805  movups  [rsp+14F0h+var_1480], xmm1
0x18000380a  mov     [rbp+13F0h+var_1470], rax
0x18000380e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003815  test    rax, rax
0x180003818  jz      short loc_180003825
0x18000381a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000381f  mov     [rbp+13F0h+var_1450], rax
0x180003823  jmp     short loc_180003829
0x180003825  mov     [rbp+13F0h+var_1450], r13
0x180003829  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003830  test    rax, rax
0x180003833  jz      short loc_18000383F
0x180003835  lea     rcx, [rsp+14F0h+var_14D0]
0x18000383a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000383f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003846  test    rax, rax
0x180003849  jz      short loc_18000385F
0x18000384b  mov     r8d, 400h
0x180003851  lea     rdx, [rbp+13F0h+var_1430]
0x180003855  lea     rcx, [rsp+14F0h+var_14D0]
0x18000385a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000385f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003866  test    rax, rax
0x180003869  jz      short loc_180003875
0x18000386b  lea     rcx, [rsp+14F0h+var_14D0]
0x180003870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003875  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000387c  test    rax, rax
0x18000387f  jz      short loc_180003892
0x180003881  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003886  jnz     short loc_180003892
0x180003888  lea     rcx, [rsp+14F0h+var_14D0]
0x18000388d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003892  cmp     [rsp+14F0h+var_14C8], r13d
0x180003897  jl      short loc_1800038AB
0x180003899  mov     ecx, 8000FFFFh; this
0x18000389e  mov     [rsp+14F0h+var_14C8], ecx
0x1800038a2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800038a7  mov     [rsp+14F0h+var_14C4], eax
0x1800038ab  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800038b2  jnz     short loc_1800038D3
0x1800038b4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800038bb  test    rax, rax
0x1800038be  jz      short loc_1800038C9
0x1800038c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038c5  test    al, al
0x1800038c7  jmp     short loc_1800038D1
0x1800038c9  call    cs:__imp_IsDebuggerPresent
0x1800038cf  test    eax, eax
0x1800038d1  jz      short loc_1800038DA
0x1800038d3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800038d8  jz      short loc_180003900
0x1800038da  mov     rax, cs:g_pfnResultLoggingCallback
0x1800038e1  test    rax, rax
0x1800038e4  jz      short loc_180003959
0x1800038e6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800038ed  jnz     short loc_180003959
0x1800038ef  xor     r8d, r8d
0x1800038f2  xor     edx, edx
0x1800038f4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800038f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038fe  jmp     short loc_180003959
0x180003900  mov     ebx, 800h
0x180003905  mov     rax, cs:g_pfnResultLoggingCallback
0x18000390c  test    rax, rax
0x18000390f  jz      short loc_18000392E
0x180003911  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003918  jnz     short loc_18000392E
0x18000391a  mov     r8d, ebx
0x18000391d  lea     rdx, [rbp+13F0h+OutputString]
0x180003924  lea     rcx, [rsp+14F0h+var_14D0]
0x180003929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000392e  cmp     [rbp+13F0h+OutputString], r13w
0x180003936  jnz     short loc_18000394C
0x180003938  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000393d  mov     rdx, rbx; unsigned __int16 *
0x180003940  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003947  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000394c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003953  call    cs:__imp_OutputDebugStringW
0x180003959  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000395e  jnz     short loc_180003969
0x180003960  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180003967  jz      short loc_18000397B
0x180003969  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003970  test    rax, rax
0x180003973  jz      short loc_18000397B
0x180003975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000397a  nop
0x18000397b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003980  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
