# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800036a8`
- end: `0x180003923`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `635`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000344c`

## callees

- `0x18000265c`
- `0x1800036a8`
- `0x1800047a4`
- `0x180004fb0`
- `0x180005980`
- `0x18000689c`
- `0x180036fe0`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000374a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000374a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800038ea`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800038ea`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000385a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000385a`

## string_xrefs

- `0x18000375a`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
  v25 = "onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h";
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
0x1800036a8  mov     [rsp-8+arg_10], rbx
0x1800036ad  mov     [rsp-8+arg_18], rsi
0x1800036b2  push    rbp
0x1800036b3  push    rdi
0x1800036b4  push    r12
0x1800036b6  push    r14
0x1800036b8  push    r15
0x1800036ba  lea     rbp, [rsp-13C0h]
0x1800036c2  mov     eax, 14C0h
0x1800036c7  call    _alloca_probe
0x1800036cc  sub     rsp, rax
0x1800036cf  mov     r14d, edx
0x1800036d2  mov     r15, rcx
0x1800036d5  mov     rsi, [rbp+13E0h+arg_28]
0x1800036dc  xor     edx, edx; Val
0x1800036de  mov     r8d, 98h; Size
0x1800036e4  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x1800036e9  call    memset_0
0x1800036ee  nop
0x1800036ef  xor     r12d, r12d
0x1800036f2  mov     [rbp+13E0h+OutputString], r12w
0x1800036fa  mov     [rbp+13E0h+var_1420], r12b
0x1800036fe  mov     rbx, [rbp+13E0h+arg_30]
0x180003705  mov     ecx, [rbx]; this
0x180003707  mov     [rsp+14E0h+var_14B8], ecx
0x18000370b  mov     eax, [rbx+4]
0x18000370e  mov     [rsp+14E0h+var_14B4], eax
0x180003712  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003717  mov     edi, eax
0x180003719  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180003721  mov     ecx, r12d
0x180003724  lea     eax, [r12+8]
0x180003729  cmp     dword ptr [rbx+8], 1
0x18000372d  cmovz   ecx, eax
0x180003730  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180003734  lea     ecx, [rax-7]
0x180003737  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000373f  inc     ecx
0x180003741  mov     [rsp+14E0h+var_14B0], ecx
0x180003745  mov     [rsp+14E0h+var_14A8], r12
0x18000374a  call    cs:__imp_GetCurrentThreadId
0x180003751  nop     dword ptr [rax+rax+00h]
0x180003756  mov     [rsp+14E0h+var_14A0], eax
0x18000375a  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003761  mov     [rsp+14E0h+var_1488], rax
0x180003766  mov     [rsp+14E0h+var_1480], r14d
0x18000376b  mov     [rsp+14E0h+var_147C], edi
0x18000376f  mov     [rsp+14E0h+var_1498], r12
0x180003774  mov     [rsp+14E0h+var_1490], r12
0x180003779  mov     [rbp+13E0h+var_1438], rsi
0x18000377d  mov     [rbp+13E0h+var_1430], r15
0x180003781  mov     [rsp+14E0h+var_1478], r12
0x180003786  xorps   xmm0, xmm0
0x180003789  xor     eax, eax
0x18000378b  movups  [rbp+13E0h+var_1458], xmm0
0x18000378f  mov     [rbp+13E0h+var_1448], rax
0x180003793  xorps   xmm1, xmm1
0x180003796  movups  [rsp+14E0h+var_1470], xmm1
0x18000379b  mov     [rbp+13E0h+var_1460], rax
0x18000379f  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800037a6  test    rax, rax
0x1800037a9  jz      short loc_1800037B6
0x1800037ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037b0  mov     [rbp+13E0h+var_1440], rax
0x1800037b4  jmp     short loc_1800037BA
0x1800037b6  mov     [rbp+13E0h+var_1440], r12
0x1800037ba  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800037c1  test    rax, rax
0x1800037c4  jz      short loc_1800037D0
0x1800037c6  lea     rcx, [rsp+14E0h+var_14C0]
0x1800037cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037d0  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800037d7  test    rax, rax
0x1800037da  jz      short loc_1800037F0
0x1800037dc  mov     r8d, 400h
0x1800037e2  lea     rdx, [rbp+13E0h+var_1420]
0x1800037e6  lea     rcx, [rsp+14E0h+var_14C0]
0x1800037eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037f0  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800037f7  test    rax, rax
0x1800037fa  jz      short loc_180003806
0x1800037fc  lea     rcx, [rsp+14E0h+var_14C0]
0x180003801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003806  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000380d  test    rax, rax
0x180003810  jz      short loc_180003823
0x180003812  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180003817  jnz     short loc_180003823
0x180003819  lea     rcx, [rsp+14E0h+var_14C0]
0x18000381e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003823  cmp     [rsp+14E0h+var_14B8], r12d
0x180003828  jl      short loc_18000383C
0x18000382a  mov     ecx, 8000FFFFh; this
0x18000382f  mov     [rsp+14E0h+var_14B8], ecx
0x180003833  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003838  mov     [rsp+14E0h+var_14B4], eax
0x18000383c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003843  jnz     short loc_18000386A
0x180003845  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000384c  test    rax, rax
0x18000384f  jz      short loc_18000385A
0x180003851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003856  test    al, al
0x180003858  jmp     short loc_180003868
0x18000385a  call    cs:__imp_IsDebuggerPresent
0x180003861  nop     dword ptr [rax+rax+00h]
0x180003866  test    eax, eax
0x180003868  jz      short loc_180003871
0x18000386a  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x18000386f  jz      short loc_180003897
0x180003871  mov     rax, cs:g_pfnResultLoggingCallback
0x180003878  test    rax, rax
0x18000387b  jz      short loc_1800038F6
0x18000387d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003884  jnz     short loc_1800038F6
0x180003886  xor     r8d, r8d
0x180003889  xor     edx, edx
0x18000388b  lea     rcx, [rsp+14E0h+var_14C0]
0x180003890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003895  jmp     short loc_1800038F6
0x180003897  mov     ebx, 800h
0x18000389c  mov     rax, cs:g_pfnResultLoggingCallback
0x1800038a3  test    rax, rax
0x1800038a6  jz      short loc_1800038C5
0x1800038a8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800038af  jnz     short loc_1800038C5
0x1800038b1  mov     r8d, ebx
0x1800038b4  lea     rdx, [rbp+13E0h+OutputString]
0x1800038bb  lea     rcx, [rsp+14E0h+var_14C0]
0x1800038c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038c5  cmp     [rbp+13E0h+OutputString], r12w
0x1800038cd  jnz     short loc_1800038E3
0x1800038cf  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x1800038d4  mov     rdx, rbx; unsigned __int16 *
0x1800038d7  lea     rcx, [rbp+13E0h+OutputString]; this
0x1800038de  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800038e3  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x1800038ea  call    cs:__imp_OutputDebugStringW
0x1800038f1  nop     dword ptr [rax+rax+00h]
0x1800038f6  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x1800038fb  jnz     short loc_180003906
0x1800038fd  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003904  jz      short loc_180003918
0x180003906  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000390d  test    rax, rax
0x180003910  jz      short loc_180003918
0x180003912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003917  nop
0x180003918  lea     rcx, [rsp+14E0h+var_14C0]; this
0x18000391d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
