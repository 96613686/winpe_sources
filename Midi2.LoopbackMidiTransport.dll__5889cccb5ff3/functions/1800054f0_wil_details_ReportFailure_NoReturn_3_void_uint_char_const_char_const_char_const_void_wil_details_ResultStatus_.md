# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800054f0`
- end: `0x180005759`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000528c`

## callees

- `0x18000500c`
- `0x1800054f0`
- `0x180007b74`
- `0x180008314`
- `0x180008fe0`
- `0x18000b0d0`
- `0x1800300d0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005592`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005592`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000569c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000569c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005726`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005726`

## string_xrefs

- `0x18000559c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800054f0  mov     [rsp-8+arg_10], rbx
0x1800054f5  mov     [rsp-8+arg_18], rsi
0x1800054fa  push    rbp
0x1800054fb  push    rdi
0x1800054fc  push    r12
0x1800054fe  push    r14
0x180005500  push    r15
0x180005502  lea     rbp, [rsp-13C0h]
0x18000550a  mov     eax, 14C0h
0x18000550f  call    _alloca_probe
0x180005514  sub     rsp, rax
0x180005517  mov     r14d, edx
0x18000551a  mov     r15, rcx
0x18000551d  mov     rsi, [rbp+13E0h+arg_28]
0x180005524  xor     edx, edx; Val
0x180005526  mov     r8d, 98h; Size
0x18000552c  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180005531  call    memset_0
0x180005536  nop
0x180005537  xor     r12d, r12d
0x18000553a  mov     [rbp+13E0h+OutputString], r12w
0x180005542  mov     [rbp+13E0h+var_1420], r12b
0x180005546  mov     rbx, [rbp+13E0h+arg_30]
0x18000554d  mov     ecx, [rbx]; this
0x18000554f  mov     [rsp+14E0h+var_14B8], ecx
0x180005553  mov     eax, [rbx+4]
0x180005556  mov     [rsp+14E0h+var_14B4], eax
0x18000555a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000555f  mov     edi, eax
0x180005561  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180005569  mov     ecx, r12d
0x18000556c  lea     eax, [r12+8]
0x180005571  cmp     dword ptr [rbx+8], 1
0x180005575  cmovz   ecx, eax
0x180005578  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x18000557c  lea     ecx, [rax-7]
0x18000557f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005587  inc     ecx
0x180005589  mov     [rsp+14E0h+var_14B0], ecx
0x18000558d  mov     [rsp+14E0h+var_14A8], r12
0x180005592  call    cs:__imp_GetCurrentThreadId
0x180005598  mov     [rsp+14E0h+var_14A0], eax
0x18000559c  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800055a3  mov     [rsp+14E0h+var_1488], rax
0x1800055a8  mov     [rsp+14E0h+var_1480], r14d
0x1800055ad  mov     [rsp+14E0h+var_147C], edi
0x1800055b1  mov     [rsp+14E0h+var_1498], r12
0x1800055b6  mov     [rsp+14E0h+var_1490], r12
0x1800055bb  mov     [rbp+13E0h+var_1438], rsi
0x1800055bf  mov     [rbp+13E0h+var_1430], r15
0x1800055c3  mov     [rsp+14E0h+var_1478], r12
0x1800055c8  xorps   xmm0, xmm0
0x1800055cb  xor     eax, eax
0x1800055cd  movups  [rbp+13E0h+var_1458], xmm0
0x1800055d1  mov     [rbp+13E0h+var_1448], rax
0x1800055d5  xorps   xmm1, xmm1
0x1800055d8  movups  [rsp+14E0h+var_1470], xmm1
0x1800055dd  mov     [rbp+13E0h+var_1460], rax
0x1800055e1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800055e8  test    rax, rax
0x1800055eb  jz      short loc_1800055F8
0x1800055ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055f2  mov     [rbp+13E0h+var_1440], rax
0x1800055f6  jmp     short loc_1800055FC
0x1800055f8  mov     [rbp+13E0h+var_1440], r12
0x1800055fc  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005603  test    rax, rax
0x180005606  jz      short loc_180005612
0x180005608  lea     rcx, [rsp+14E0h+var_14C0]
0x18000560d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005612  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005619  test    rax, rax
0x18000561c  jz      short loc_180005632
0x18000561e  mov     r8d, 400h
0x180005624  lea     rdx, [rbp+13E0h+var_1420]
0x180005628  lea     rcx, [rsp+14E0h+var_14C0]
0x18000562d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005632  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005639  test    rax, rax
0x18000563c  jz      short loc_180005648
0x18000563e  lea     rcx, [rsp+14E0h+var_14C0]
0x180005643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005648  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000564f  test    rax, rax
0x180005652  jz      short loc_180005665
0x180005654  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180005659  jnz     short loc_180005665
0x18000565b  lea     rcx, [rsp+14E0h+var_14C0]
0x180005660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005665  cmp     [rsp+14E0h+var_14B8], r12d
0x18000566a  jl      short loc_18000567E
0x18000566c  mov     ecx, 8000FFFFh; this
0x180005671  mov     [rsp+14E0h+var_14B8], ecx
0x180005675  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000567a  mov     [rsp+14E0h+var_14B4], eax
0x18000567e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180005685  jnz     short loc_1800056A6
0x180005687  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000568e  test    rax, rax
0x180005691  jz      short loc_18000569C
0x180005693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005698  test    al, al
0x18000569a  jmp     short loc_1800056A4
0x18000569c  call    cs:__imp_IsDebuggerPresent
0x1800056a2  test    eax, eax
0x1800056a4  jz      short loc_1800056AD
0x1800056a6  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800056ab  jz      short loc_1800056D3
0x1800056ad  mov     rax, cs:g_pfnResultLoggingCallback
0x1800056b4  test    rax, rax
0x1800056b7  jz      short loc_18000572C
0x1800056b9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800056c0  jnz     short loc_18000572C
0x1800056c2  xor     r8d, r8d
0x1800056c5  xor     edx, edx
0x1800056c7  lea     rcx, [rsp+14E0h+var_14C0]
0x1800056cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056d1  jmp     short loc_18000572C
0x1800056d3  mov     ebx, 800h
0x1800056d8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800056df  test    rax, rax
0x1800056e2  jz      short loc_180005701
0x1800056e4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800056eb  jnz     short loc_180005701
0x1800056ed  mov     r8d, ebx
0x1800056f0  lea     rdx, [rbp+13E0h+OutputString]
0x1800056f7  lea     rcx, [rsp+14E0h+var_14C0]
0x1800056fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005701  cmp     [rbp+13E0h+OutputString], r12w
0x180005709  jnz     short loc_18000571F
0x18000570b  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180005710  mov     rdx, rbx; unsigned __int16 *
0x180005713  lea     rcx, [rbp+13E0h+OutputString]; this
0x18000571a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000571f  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180005726  call    cs:__imp_OutputDebugStringW
0x18000572c  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180005731  jnz     short loc_18000573C
0x180005733  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000573a  jz      short loc_18000574E
0x18000573c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005743  test    rax, rax
0x180005746  jz      short loc_18000574E
0x180005748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000574d  nop
0x18000574e  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180005753  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
