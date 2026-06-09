# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000580c`
- end: `0x180005a75`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800055b8`

## callees

- `0x18000526c`
- `0x18000580c`
- `0x180008094`
- `0x180008850`
- `0x180009780`
- `0x18000ba00`
- `0x18003e3f0`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800058ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800058ae`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005a42`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005a42`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800059b8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800059b8`

## string_xrefs

- `0x1800058b8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000580c  mov     [rsp-8+arg_10], rbx
0x180005811  mov     [rsp-8+arg_18], rsi
0x180005816  push    rbp
0x180005817  push    rdi
0x180005818  push    r12
0x18000581a  push    r14
0x18000581c  push    r15
0x18000581e  lea     rbp, [rsp-13C0h]
0x180005826  mov     eax, 14C0h
0x18000582b  call    _alloca_probe
0x180005830  sub     rsp, rax
0x180005833  mov     r14d, edx
0x180005836  mov     r15, rcx
0x180005839  mov     rsi, [rbp+13E0h+arg_28]
0x180005840  xor     edx, edx; Val
0x180005842  mov     r8d, 98h; Size
0x180005848  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x18000584d  call    memset_0
0x180005852  nop
0x180005853  xor     r12d, r12d
0x180005856  mov     [rbp+13E0h+OutputString], r12w
0x18000585e  mov     [rbp+13E0h+var_1420], r12b
0x180005862  mov     rbx, [rbp+13E0h+arg_30]
0x180005869  mov     ecx, [rbx]; this
0x18000586b  mov     [rsp+14E0h+var_14B8], ecx
0x18000586f  mov     eax, [rbx+4]
0x180005872  mov     [rsp+14E0h+var_14B4], eax
0x180005876  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000587b  mov     edi, eax
0x18000587d  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180005885  mov     ecx, r12d
0x180005888  lea     eax, [r12+8]
0x18000588d  cmp     dword ptr [rbx+8], 1
0x180005891  cmovz   ecx, eax
0x180005894  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180005898  lea     ecx, [rax-7]
0x18000589b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800058a3  inc     ecx
0x1800058a5  mov     [rsp+14E0h+var_14B0], ecx
0x1800058a9  mov     [rsp+14E0h+var_14A8], r12
0x1800058ae  call    cs:__imp_GetCurrentThreadId
0x1800058b4  mov     [rsp+14E0h+var_14A0], eax
0x1800058b8  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800058bf  mov     [rsp+14E0h+var_1488], rax
0x1800058c4  mov     [rsp+14E0h+var_1480], r14d
0x1800058c9  mov     [rsp+14E0h+var_147C], edi
0x1800058cd  mov     [rsp+14E0h+var_1498], r12
0x1800058d2  mov     [rsp+14E0h+var_1490], r12
0x1800058d7  mov     [rbp+13E0h+var_1438], rsi
0x1800058db  mov     [rbp+13E0h+var_1430], r15
0x1800058df  mov     [rsp+14E0h+var_1478], r12
0x1800058e4  xorps   xmm0, xmm0
0x1800058e7  xor     eax, eax
0x1800058e9  movups  [rbp+13E0h+var_1458], xmm0
0x1800058ed  mov     [rbp+13E0h+var_1448], rax
0x1800058f1  xorps   xmm1, xmm1
0x1800058f4  movups  [rsp+14E0h+var_1470], xmm1
0x1800058f9  mov     [rbp+13E0h+var_1460], rax
0x1800058fd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005904  test    rax, rax
0x180005907  jz      short loc_180005914
0x180005909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000590e  mov     [rbp+13E0h+var_1440], rax
0x180005912  jmp     short loc_180005918
0x180005914  mov     [rbp+13E0h+var_1440], r12
0x180005918  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000591f  test    rax, rax
0x180005922  jz      short loc_18000592E
0x180005924  lea     rcx, [rsp+14E0h+var_14C0]
0x180005929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000592e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005935  test    rax, rax
0x180005938  jz      short loc_18000594E
0x18000593a  mov     r8d, 400h
0x180005940  lea     rdx, [rbp+13E0h+var_1420]
0x180005944  lea     rcx, [rsp+14E0h+var_14C0]
0x180005949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000594e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005955  test    rax, rax
0x180005958  jz      short loc_180005964
0x18000595a  lea     rcx, [rsp+14E0h+var_14C0]
0x18000595f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005964  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000596b  test    rax, rax
0x18000596e  jz      short loc_180005981
0x180005970  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180005975  jnz     short loc_180005981
0x180005977  lea     rcx, [rsp+14E0h+var_14C0]
0x18000597c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005981  cmp     [rsp+14E0h+var_14B8], r12d
0x180005986  jl      short loc_18000599A
0x180005988  mov     ecx, 8000FFFFh; this
0x18000598d  mov     [rsp+14E0h+var_14B8], ecx
0x180005991  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005996  mov     [rsp+14E0h+var_14B4], eax
0x18000599a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800059a1  jnz     short loc_1800059C2
0x1800059a3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800059aa  test    rax, rax
0x1800059ad  jz      short loc_1800059B8
0x1800059af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059b4  test    al, al
0x1800059b6  jmp     short loc_1800059C0
0x1800059b8  call    cs:__imp_IsDebuggerPresent
0x1800059be  test    eax, eax
0x1800059c0  jz      short loc_1800059C9
0x1800059c2  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800059c7  jz      short loc_1800059EF
0x1800059c9  mov     rax, cs:g_pfnResultLoggingCallback
0x1800059d0  test    rax, rax
0x1800059d3  jz      short loc_180005A48
0x1800059d5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800059dc  jnz     short loc_180005A48
0x1800059de  xor     r8d, r8d
0x1800059e1  xor     edx, edx
0x1800059e3  lea     rcx, [rsp+14E0h+var_14C0]
0x1800059e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059ed  jmp     short loc_180005A48
0x1800059ef  mov     ebx, 800h
0x1800059f4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800059fb  test    rax, rax
0x1800059fe  jz      short loc_180005A1D
0x180005a00  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005a07  jnz     short loc_180005A1D
0x180005a09  mov     r8d, ebx
0x180005a0c  lea     rdx, [rbp+13E0h+OutputString]
0x180005a13  lea     rcx, [rsp+14E0h+var_14C0]
0x180005a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a1d  cmp     [rbp+13E0h+OutputString], r12w
0x180005a25  jnz     short loc_180005A3B
0x180005a27  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180005a2c  mov     rdx, rbx; unsigned __int16 *
0x180005a2f  lea     rcx, [rbp+13E0h+OutputString]; this
0x180005a36  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005a3b  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180005a42  call    cs:__imp_OutputDebugStringW
0x180005a48  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180005a4d  jnz     short loc_180005A58
0x180005a4f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180005a56  jz      short loc_180005A6A
0x180005a58  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005a5f  test    rax, rax
0x180005a62  jz      short loc_180005A6A
0x180005a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a69  nop
0x180005a6a  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180005a6f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
