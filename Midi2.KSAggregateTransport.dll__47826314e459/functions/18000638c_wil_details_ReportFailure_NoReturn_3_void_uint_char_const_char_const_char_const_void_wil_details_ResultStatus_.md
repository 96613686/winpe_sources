# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000638c`
- end: `0x1800065f5`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180006138`

## callees

- `0x180005e9c`
- `0x18000638c`
- `0x180008c14`
- `0x1800093d0`
- `0x18000a300`
- `0x18000c580`
- `0x1800599b0`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000642e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000642e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800065c2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800065c2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006538`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006538`

## string_xrefs

- `0x180006438`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000638c  mov     [rsp-8+arg_10], rbx
0x180006391  mov     [rsp-8+arg_18], rsi
0x180006396  push    rbp
0x180006397  push    rdi
0x180006398  push    r12
0x18000639a  push    r14
0x18000639c  push    r15
0x18000639e  lea     rbp, [rsp-13C0h]
0x1800063a6  mov     eax, 14C0h
0x1800063ab  call    _alloca_probe
0x1800063b0  sub     rsp, rax
0x1800063b3  mov     r14d, edx
0x1800063b6  mov     r15, rcx
0x1800063b9  mov     rsi, [rbp+13E0h+arg_28]
0x1800063c0  xor     edx, edx; Val
0x1800063c2  mov     r8d, 98h; Size
0x1800063c8  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x1800063cd  call    memset_0
0x1800063d2  nop
0x1800063d3  xor     r12d, r12d
0x1800063d6  mov     [rbp+13E0h+OutputString], r12w
0x1800063de  mov     [rbp+13E0h+var_1420], r12b
0x1800063e2  mov     rbx, [rbp+13E0h+arg_30]
0x1800063e9  mov     ecx, [rbx]; this
0x1800063eb  mov     [rsp+14E0h+var_14B8], ecx
0x1800063ef  mov     eax, [rbx+4]
0x1800063f2  mov     [rsp+14E0h+var_14B4], eax
0x1800063f6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800063fb  mov     edi, eax
0x1800063fd  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180006405  mov     ecx, r12d
0x180006408  lea     eax, [r12+8]
0x18000640d  cmp     dword ptr [rbx+8], 1
0x180006411  cmovz   ecx, eax
0x180006414  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180006418  lea     ecx, [rax-7]
0x18000641b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006423  inc     ecx
0x180006425  mov     [rsp+14E0h+var_14B0], ecx
0x180006429  mov     [rsp+14E0h+var_14A8], r12
0x18000642e  call    cs:__imp_GetCurrentThreadId
0x180006434  mov     [rsp+14E0h+var_14A0], eax
0x180006438  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000643f  mov     [rsp+14E0h+var_1488], rax
0x180006444  mov     [rsp+14E0h+var_1480], r14d
0x180006449  mov     [rsp+14E0h+var_147C], edi
0x18000644d  mov     [rsp+14E0h+var_1498], r12
0x180006452  mov     [rsp+14E0h+var_1490], r12
0x180006457  mov     [rbp+13E0h+var_1438], rsi
0x18000645b  mov     [rbp+13E0h+var_1430], r15
0x18000645f  mov     [rsp+14E0h+var_1478], r12
0x180006464  xorps   xmm0, xmm0
0x180006467  xor     eax, eax
0x180006469  movups  [rbp+13E0h+var_1458], xmm0
0x18000646d  mov     [rbp+13E0h+var_1448], rax
0x180006471  xorps   xmm1, xmm1
0x180006474  movups  [rsp+14E0h+var_1470], xmm1
0x180006479  mov     [rbp+13E0h+var_1460], rax
0x18000647d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006484  test    rax, rax
0x180006487  jz      short loc_180006494
0x180006489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000648e  mov     [rbp+13E0h+var_1440], rax
0x180006492  jmp     short loc_180006498
0x180006494  mov     [rbp+13E0h+var_1440], r12
0x180006498  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000649f  test    rax, rax
0x1800064a2  jz      short loc_1800064AE
0x1800064a4  lea     rcx, [rsp+14E0h+var_14C0]
0x1800064a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064ae  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800064b5  test    rax, rax
0x1800064b8  jz      short loc_1800064CE
0x1800064ba  mov     r8d, 400h
0x1800064c0  lea     rdx, [rbp+13E0h+var_1420]
0x1800064c4  lea     rcx, [rsp+14E0h+var_14C0]
0x1800064c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064ce  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800064d5  test    rax, rax
0x1800064d8  jz      short loc_1800064E4
0x1800064da  lea     rcx, [rsp+14E0h+var_14C0]
0x1800064df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064e4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800064eb  test    rax, rax
0x1800064ee  jz      short loc_180006501
0x1800064f0  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800064f5  jnz     short loc_180006501
0x1800064f7  lea     rcx, [rsp+14E0h+var_14C0]
0x1800064fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006501  cmp     [rsp+14E0h+var_14B8], r12d
0x180006506  jl      short loc_18000651A
0x180006508  mov     ecx, 8000FFFFh; this
0x18000650d  mov     [rsp+14E0h+var_14B8], ecx
0x180006511  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006516  mov     [rsp+14E0h+var_14B4], eax
0x18000651a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180006521  jnz     short loc_180006542
0x180006523  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000652a  test    rax, rax
0x18000652d  jz      short loc_180006538
0x18000652f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006534  test    al, al
0x180006536  jmp     short loc_180006540
0x180006538  call    cs:__imp_IsDebuggerPresent
0x18000653e  test    eax, eax
0x180006540  jz      short loc_180006549
0x180006542  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180006547  jz      short loc_18000656F
0x180006549  mov     rax, cs:g_pfnResultLoggingCallback
0x180006550  test    rax, rax
0x180006553  jz      short loc_1800065C8
0x180006555  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000655c  jnz     short loc_1800065C8
0x18000655e  xor     r8d, r8d
0x180006561  xor     edx, edx
0x180006563  lea     rcx, [rsp+14E0h+var_14C0]
0x180006568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000656d  jmp     short loc_1800065C8
0x18000656f  mov     ebx, 800h
0x180006574  mov     rax, cs:g_pfnResultLoggingCallback
0x18000657b  test    rax, rax
0x18000657e  jz      short loc_18000659D
0x180006580  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180006587  jnz     short loc_18000659D
0x180006589  mov     r8d, ebx
0x18000658c  lea     rdx, [rbp+13E0h+OutputString]
0x180006593  lea     rcx, [rsp+14E0h+var_14C0]
0x180006598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000659d  cmp     [rbp+13E0h+OutputString], r12w
0x1800065a5  jnz     short loc_1800065BB
0x1800065a7  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x1800065ac  mov     rdx, rbx; unsigned __int16 *
0x1800065af  lea     rcx, [rbp+13E0h+OutputString]; this
0x1800065b6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800065bb  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x1800065c2  call    cs:__imp_OutputDebugStringW
0x1800065c8  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x1800065cd  jnz     short loc_1800065D8
0x1800065cf  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800065d6  jz      short loc_1800065EA
0x1800065d8  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800065df  test    rax, rax
0x1800065e2  jz      short loc_1800065EA
0x1800065e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065e9  nop
0x1800065ea  lea     rcx, [rsp+14E0h+var_14C0]; this
0x1800065ef  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
