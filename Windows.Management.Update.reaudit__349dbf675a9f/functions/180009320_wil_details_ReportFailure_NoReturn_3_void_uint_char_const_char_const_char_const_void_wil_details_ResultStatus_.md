# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180009320`
- end: `0x180009594`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `628`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800090ac`

## callees

- `0x1800035cc`
- `0x180009320`
- `0x18000be84`
- `0x18000c694`
- `0x18000d840`
- `0x18001027c`
- `0x180028a60`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800093c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800093c2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800094cb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800094cb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000955b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000955b`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v17, v15);
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
0x180009320  mov     [rsp-8+arg_18], rbx
0x180009325  push    rbp
0x180009326  push    rsi
0x180009327  push    rdi
0x180009328  push    r12
0x18000932a  push    r13
0x18000932c  push    r14
0x18000932e  push    r15
0x180009330  lea     rbp, [rsp-13C0h]
0x180009338  mov     eax, 14C0h
0x18000933d  call    _alloca_probe
0x180009342  sub     rsp, rax
0x180009345  mov     r15, r8
0x180009348  mov     r14d, edx
0x18000934b  mov     r12, rcx
0x18000934e  mov     rsi, [rbp+13F0h+arg_28]
0x180009355  xor     edx, edx; Val
0x180009357  mov     r8d, 98h; Size
0x18000935d  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180009362  call    memset_0
0x180009367  nop
0x180009368  xor     r13d, r13d
0x18000936b  mov     [rbp+13F0h+OutputString], r13w
0x180009373  mov     [rbp+13F0h+var_1430], r13b
0x180009377  mov     rbx, [rbp+13F0h+arg_30]
0x18000937e  mov     ecx, [rbx]; this
0x180009380  mov     [rsp+14F0h+var_14C8], ecx
0x180009384  mov     eax, [rbx+4]
0x180009387  mov     [rsp+14F0h+var_14C4], eax
0x18000938b  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180009390  mov     edi, eax
0x180009392  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000939a  mov     ecx, r13d
0x18000939d  lea     eax, [r13+8]
0x1800093a1  cmp     dword ptr [rbx+8], 1
0x1800093a5  cmovz   ecx, eax
0x1800093a8  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800093ac  lea     ecx, [rax-7]
0x1800093af  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x1800093b7  inc     ecx
0x1800093b9  mov     [rsp+14F0h+var_14C0], ecx
0x1800093bd  mov     [rsp+14F0h+var_14B8], r13
0x1800093c2  call    cs:__imp_GetCurrentThreadId
0x1800093c9  nop     dword ptr [rax+rax+00h]
0x1800093ce  mov     [rsp+14F0h+var_14B0], eax
0x1800093d2  mov     [rsp+14F0h+var_1498], r15
0x1800093d7  mov     [rsp+14F0h+var_1490], r14d
0x1800093dc  mov     [rsp+14F0h+var_148C], edi
0x1800093e0  mov     [rsp+14F0h+var_14A8], r13
0x1800093e5  mov     [rsp+14F0h+var_14A0], r13
0x1800093ea  mov     [rbp+13F0h+var_1448], rsi
0x1800093ee  mov     [rbp+13F0h+var_1440], r12
0x1800093f2  mov     [rsp+14F0h+var_1488], r13
0x1800093f7  xorps   xmm0, xmm0
0x1800093fa  xor     eax, eax
0x1800093fc  movups  [rbp+13F0h+var_1468], xmm0
0x180009400  mov     [rbp+13F0h+var_1458], rax
0x180009404  xorps   xmm1, xmm1
0x180009407  movups  [rsp+14F0h+var_1480], xmm1
0x18000940c  mov     [rbp+13F0h+var_1470], rax
0x180009410  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009417  test    rax, rax
0x18000941a  jz      short loc_180009427
0x18000941c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009421  mov     [rbp+13F0h+var_1450], rax
0x180009425  jmp     short loc_18000942B
0x180009427  mov     [rbp+13F0h+var_1450], r13
0x18000942b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009432  test    rax, rax
0x180009435  jz      short loc_180009441
0x180009437  lea     rcx, [rsp+14F0h+var_14D0]
0x18000943c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009441  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009448  test    rax, rax
0x18000944b  jz      short loc_180009461
0x18000944d  mov     r8d, 400h
0x180009453  lea     rdx, [rbp+13F0h+var_1430]
0x180009457  lea     rcx, [rsp+14F0h+var_14D0]
0x18000945c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009461  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009468  test    rax, rax
0x18000946b  jz      short loc_180009477
0x18000946d  lea     rcx, [rsp+14F0h+var_14D0]
0x180009472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009477  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000947e  test    rax, rax
0x180009481  jz      short loc_180009494
0x180009483  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180009488  jnz     short loc_180009494
0x18000948a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000948f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009494  cmp     [rsp+14F0h+var_14C8], r13d
0x180009499  jl      short loc_1800094AD
0x18000949b  mov     ecx, 8000FFFFh; this
0x1800094a0  mov     [rsp+14F0h+var_14C8], ecx
0x1800094a4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800094a9  mov     [rsp+14F0h+var_14C4], eax
0x1800094ad  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800094b4  jnz     short loc_1800094DB
0x1800094b6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800094bd  test    rax, rax
0x1800094c0  jz      short loc_1800094CB
0x1800094c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094c7  test    al, al
0x1800094c9  jmp     short loc_1800094D9
0x1800094cb  call    cs:__imp_IsDebuggerPresent
0x1800094d2  nop     dword ptr [rax+rax+00h]
0x1800094d7  test    eax, eax
0x1800094d9  jz      short loc_1800094E2
0x1800094db  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800094e0  jz      short loc_180009508
0x1800094e2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800094e9  test    rax, rax
0x1800094ec  jz      short loc_180009567
0x1800094ee  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800094f5  jnz     short loc_180009567
0x1800094f7  xor     r8d, r8d
0x1800094fa  xor     edx, edx
0x1800094fc  lea     rcx, [rsp+14F0h+var_14D0]
0x180009501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009506  jmp     short loc_180009567
0x180009508  mov     ebx, 800h
0x18000950d  mov     rax, cs:g_pfnResultLoggingCallback
0x180009514  test    rax, rax
0x180009517  jz      short loc_180009536
0x180009519  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180009520  jnz     short loc_180009536
0x180009522  mov     r8d, ebx
0x180009525  lea     rdx, [rbp+13F0h+OutputString]
0x18000952c  lea     rcx, [rsp+14F0h+var_14D0]
0x180009531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009536  cmp     [rbp+13F0h+OutputString], r13w
0x18000953e  jnz     short loc_180009554
0x180009540  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180009545  mov     rdx, rbx; unsigned __int16 *
0x180009548  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000954f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180009554  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000955b  call    cs:__imp_OutputDebugStringW
0x180009562  nop     dword ptr [rax+rax+00h]
0x180009567  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000956c  jnz     short loc_180009577
0x18000956e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180009575  jz      short loc_180009589
0x180009577  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000957e  test    rax, rax
0x180009581  jz      short loc_180009589
0x180009583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009588  nop
0x180009589  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000958e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
