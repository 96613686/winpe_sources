# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x1800035fc`
- end: `0x180003875`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002fdc`

## callees

- `0x1800035fc`
- `0x180005778`
- `0x1800060f0`
- `0x180006b40`
- `0x180006f08`
- `0x18000e962`
- `0x18000ea50`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800036b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800036b5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800037b8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800037b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003842`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003842`

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
0x1800035fc  mov     [rsp-8+arg_18], rbx
0x180003601  push    rbp
0x180003602  push    rsi
0x180003603  push    rdi
0x180003604  push    r12
0x180003606  push    r13
0x180003608  push    r14
0x18000360a  push    r15
0x18000360c  lea     rbp, [rsp-13C0h]
0x180003614  mov     eax, 14C0h
0x180003619  call    _alloca_probe
0x18000361e  sub     rsp, rax
0x180003621  mov     r14, r8
0x180003624  mov     esi, edx
0x180003626  mov     rdi, rcx
0x180003629  mov     r15, [rbp+13F0h+arg_28]
0x180003630  xor     edx, edx; Val
0x180003632  mov     r8d, 98h; Size
0x180003638  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000363d  call    memset_0
0x180003642  nop
0x180003643  xor     r13d, r13d
0x180003646  mov     [rbp+13F0h+OutputString], r13w
0x18000364e  mov     [rbp+13F0h+var_1430], r13b
0x180003652  mov     rbx, [rbp+13F0h+arg_30]
0x180003659  mov     ecx, [rbx]; this
0x18000365b  mov     [rsp+14F0h+var_14C8], ecx
0x18000365f  mov     eax, [rbx+4]
0x180003662  mov     [rsp+14F0h+var_14C4], eax
0x180003666  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000366b  mov     r12d, eax
0x18000366e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180003676  mov     ecx, r13d
0x180003679  lea     eax, [r13+8]
0x18000367d  cmp     dword ptr [rbx+8], 1
0x180003681  cmovz   ecx, eax
0x180003684  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003688  lea     ecx, [rax-7]
0x18000368b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003693  inc     ecx
0x180003695  mov     [rsp+14F0h+var_14C0], ecx
0x180003699  mov     rcx, [rbp+13F0h+arg_38]
0x1800036a0  test    rcx, rcx
0x1800036a3  jz      short loc_1800036B0
0x1800036a5  cmp     [rcx], r13w
0x1800036a9  mov     [rsp+14F0h+var_14B8], rcx
0x1800036ae  jnz     short loc_1800036B5
0x1800036b0  mov     [rsp+14F0h+var_14B8], r13
0x1800036b5  call    cs:__imp_GetCurrentThreadId
0x1800036bb  mov     [rsp+14F0h+var_14B0], eax
0x1800036bf  mov     [rsp+14F0h+var_1498], r14
0x1800036c4  mov     [rsp+14F0h+var_1490], esi
0x1800036c8  mov     [rsp+14F0h+var_148C], r12d
0x1800036cd  mov     [rsp+14F0h+var_14A8], r13
0x1800036d2  mov     [rsp+14F0h+var_14A0], r13
0x1800036d7  mov     [rbp+13F0h+var_1448], r15
0x1800036db  mov     [rbp+13F0h+var_1440], rdi
0x1800036df  mov     [rsp+14F0h+var_1488], r13
0x1800036e4  xorps   xmm0, xmm0
0x1800036e7  xor     eax, eax
0x1800036e9  movups  [rbp+13F0h+var_1468], xmm0
0x1800036ed  mov     [rbp+13F0h+var_1458], rax
0x1800036f1  xorps   xmm1, xmm1
0x1800036f4  movups  [rsp+14F0h+var_1480], xmm1
0x1800036f9  mov     [rbp+13F0h+var_1470], rax
0x1800036fd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003704  test    rax, rax
0x180003707  jz      short loc_180003714
0x180003709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000370e  mov     [rbp+13F0h+var_1450], rax
0x180003712  jmp     short loc_180003718
0x180003714  mov     [rbp+13F0h+var_1450], r13
0x180003718  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000371f  test    rax, rax
0x180003722  jz      short loc_18000372E
0x180003724  lea     rcx, [rsp+14F0h+var_14D0]
0x180003729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000372e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003735  test    rax, rax
0x180003738  jz      short loc_18000374E
0x18000373a  mov     r8d, 400h
0x180003740  lea     rdx, [rbp+13F0h+var_1430]
0x180003744  lea     rcx, [rsp+14F0h+var_14D0]
0x180003749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000374e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003755  test    rax, rax
0x180003758  jz      short loc_180003764
0x18000375a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000375f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003764  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000376b  test    rax, rax
0x18000376e  jz      short loc_180003781
0x180003770  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003775  jnz     short loc_180003781
0x180003777  lea     rcx, [rsp+14F0h+var_14D0]
0x18000377c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003781  cmp     [rsp+14F0h+var_14C8], r13d
0x180003786  jl      short loc_18000379A
0x180003788  mov     ecx, 8000FFFFh; this
0x18000378d  mov     [rsp+14F0h+var_14C8], ecx
0x180003791  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003796  mov     [rsp+14F0h+var_14C4], eax
0x18000379a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800037a1  jnz     short loc_1800037C2
0x1800037a3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800037aa  test    rax, rax
0x1800037ad  jz      short loc_1800037B8
0x1800037af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037b4  test    al, al
0x1800037b6  jmp     short loc_1800037C0
0x1800037b8  call    cs:__imp_IsDebuggerPresent
0x1800037be  test    eax, eax
0x1800037c0  jz      short loc_1800037C9
0x1800037c2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800037c7  jz      short loc_1800037EF
0x1800037c9  mov     rax, cs:g_pfnResultLoggingCallback
0x1800037d0  test    rax, rax
0x1800037d3  jz      short loc_180003848
0x1800037d5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800037dc  jnz     short loc_180003848
0x1800037de  xor     r8d, r8d
0x1800037e1  xor     edx, edx
0x1800037e3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800037e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037ed  jmp     short loc_180003848
0x1800037ef  mov     ebx, 800h
0x1800037f4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800037fb  test    rax, rax
0x1800037fe  jz      short loc_18000381D
0x180003800  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003807  jnz     short loc_18000381D
0x180003809  mov     r8d, ebx
0x18000380c  lea     rdx, [rbp+13F0h+OutputString]
0x180003813  lea     rcx, [rsp+14F0h+var_14D0]
0x180003818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000381d  cmp     [rbp+13F0h+OutputString], r13w
0x180003825  jnz     short loc_18000383B
0x180003827  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000382c  mov     rdx, rbx; wchar_t *
0x18000382f  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003836  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000383b  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003842  call    cs:__imp_OutputDebugStringW
0x180003848  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000384d  jnz     short loc_180003858
0x18000384f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180003856  jz      short loc_18000386A
0x180003858  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000385f  test    rax, rax
0x180003862  jz      short loc_18000386A
0x180003864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003869  nop
0x18000386a  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000386f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
