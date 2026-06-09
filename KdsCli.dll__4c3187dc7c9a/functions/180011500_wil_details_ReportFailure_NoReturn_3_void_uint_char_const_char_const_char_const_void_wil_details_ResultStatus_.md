# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180011500`
- end: `0x180011760`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800112a4`

## callees

- `0x180001f7c`
- `0x180011500`
- `0x180013414`
- `0x180013bac`
- `0x1800147c0`
- `0x180016400`
- `0x18001a640`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800115a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800115a1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800116a4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800116a4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001172e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001172e`

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
  int v10; // eax
  int v11; // edx
  int v12; // eax
  int v13; // edi
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  __int64 v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v22, v11);
  v19 = a7[2] == 1;
  v13 = v12;
  v20 = 3;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
  {
    v22 = -2147418113;
    v23 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v16);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( (v21 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v17);
  }
  wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x180011500  mov     [rsp-8+arg_18], rbx
0x180011505  push    rbp
0x180011506  push    rsi
0x180011507  push    rdi
0x180011508  push    r12
0x18001150a  push    r13
0x18001150c  push    r14
0x18001150e  push    r15
0x180011510  lea     rbp, [rsp-13C0h]
0x180011518  mov     eax, 14C0h
0x18001151d  call    _alloca_probe
0x180011522  sub     rsp, rax
0x180011525  mov     rsi, [rbp+13F0h+arg_28]
0x18001152c  mov     r15, r8
0x18001152f  mov     r14d, edx
0x180011532  mov     r12, rcx
0x180011535  xor     edx, edx; Val
0x180011537  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18001153c  mov     r8d, 98h; Size
0x180011542  call    memset_0
0x180011547  mov     rbx, [rbp+13F0h+arg_30]
0x18001154e  xor     r13d, r13d
0x180011551  mov     [rbp+13F0h+OutputString], r13w
0x180011559  mov     [rbp+13F0h+var_1430], r13b
0x18001155d  mov     ecx, [rbx]; this
0x18001155f  mov     eax, [rbx+4]
0x180011562  mov     [rsp+14F0h+var_14C8], ecx
0x180011566  mov     [rsp+14F0h+var_14C4], eax
0x18001156a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001156f  cmp     dword ptr [rbx+8], 1
0x180011573  mov     edi, eax
0x180011575  lea     eax, [r13+8]
0x180011579  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180011581  mov     ecx, r13d
0x180011584  cmovz   ecx, eax
0x180011587  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18001158b  lea     ecx, [rax-7]
0x18001158e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180011596  inc     ecx
0x180011598  mov     [rsp+14F0h+var_14B8], r13
0x18001159d  mov     [rsp+14F0h+var_14C0], ecx
0x1800115a1  call    cs:__imp_GetCurrentThreadId
0x1800115a7  xorps   xmm0, xmm0
0x1800115aa  mov     [rsp+14F0h+var_1498], r15
0x1800115af  mov     [rsp+14F0h+var_14B0], eax
0x1800115b3  xorps   xmm1, xmm1
0x1800115b6  xor     eax, eax
0x1800115b8  mov     [rsp+14F0h+var_1490], r14d
0x1800115bd  mov     [rbp+13F0h+var_1458], rax
0x1800115c1  mov     [rbp+13F0h+var_1470], rax
0x1800115c5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800115cc  mov     [rsp+14F0h+var_148C], edi
0x1800115d0  mov     [rsp+14F0h+var_14A8], r13
0x1800115d5  mov     [rsp+14F0h+var_14A0], r13
0x1800115da  mov     [rbp+13F0h+var_1448], rsi
0x1800115de  mov     [rbp+13F0h+var_1440], r12
0x1800115e2  mov     [rsp+14F0h+var_1488], r13
0x1800115e7  movups  [rbp+13F0h+var_1468], xmm0
0x1800115eb  movups  [rsp+14F0h+var_1480], xmm1
0x1800115f0  test    rax, rax
0x1800115f3  jz      short loc_180011600
0x1800115f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115fa  mov     [rbp+13F0h+var_1450], rax
0x1800115fe  jmp     short loc_180011604
0x180011600  mov     [rbp+13F0h+var_1450], r13
0x180011604  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001160b  test    rax, rax
0x18001160e  jz      short loc_18001161A
0x180011610  lea     rcx, [rsp+14F0h+var_14D0]
0x180011615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001161a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180011621  test    rax, rax
0x180011624  jz      short loc_18001163A
0x180011626  mov     r8d, 400h
0x18001162c  lea     rdx, [rbp+13F0h+var_1430]
0x180011630  lea     rcx, [rsp+14F0h+var_14D0]
0x180011635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001163a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011641  test    rax, rax
0x180011644  jz      short loc_180011650
0x180011646  lea     rcx, [rsp+14F0h+var_14D0]
0x18001164b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011650  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011657  test    rax, rax
0x18001165a  jz      short loc_18001166D
0x18001165c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180011661  jnz     short loc_18001166D
0x180011663  lea     rcx, [rsp+14F0h+var_14D0]
0x180011668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001166d  cmp     [rsp+14F0h+var_14C8], r13d
0x180011672  jl      short loc_180011686
0x180011674  mov     ecx, 8000FFFFh; this
0x180011679  mov     [rsp+14F0h+var_14C8], ecx
0x18001167d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180011682  mov     [rsp+14F0h+var_14C4], eax
0x180011686  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18001168d  jnz     short loc_1800116AE
0x18001168f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180011696  test    rax, rax
0x180011699  jz      short loc_1800116A4
0x18001169b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116a0  test    al, al
0x1800116a2  jmp     short loc_1800116AC
0x1800116a4  call    cs:__imp_IsDebuggerPresent
0x1800116aa  test    eax, eax
0x1800116ac  jz      short loc_1800116B5
0x1800116ae  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800116b3  jz      short loc_1800116DB
0x1800116b5  mov     rax, cs:g_pfnResultLoggingCallback
0x1800116bc  test    rax, rax
0x1800116bf  jz      short loc_180011734
0x1800116c1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800116c8  jnz     short loc_180011734
0x1800116ca  xor     r8d, r8d
0x1800116cd  lea     rcx, [rsp+14F0h+var_14D0]
0x1800116d2  xor     edx, edx
0x1800116d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116d9  jmp     short loc_180011734
0x1800116db  mov     rax, cs:g_pfnResultLoggingCallback
0x1800116e2  mov     ebx, 800h
0x1800116e7  test    rax, rax
0x1800116ea  jz      short loc_180011709
0x1800116ec  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800116f3  jnz     short loc_180011709
0x1800116f5  mov     r8d, ebx
0x1800116f8  lea     rdx, [rbp+13F0h+OutputString]
0x1800116ff  lea     rcx, [rsp+14F0h+var_14D0]
0x180011704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011709  cmp     [rbp+13F0h+OutputString], r13w
0x180011711  jnz     short loc_180011727
0x180011713  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180011718  mov     rdx, rbx; unsigned __int16 *
0x18001171b  lea     rcx, [rbp+13F0h+OutputString]; this
0x180011722  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180011727  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18001172e  call    cs:__imp_OutputDebugStringW
0x180011734  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180011739  jnz     short loc_180011744
0x18001173b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180011742  jz      short loc_180011755
0x180011744  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001174b  test    rax, rax
0x18001174e  jz      short loc_180011755
0x180011750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011755  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001175a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
