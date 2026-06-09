# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180018640`
- end: `0x1800188a0`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800183e4`

## callees

- `0x180018640`
- `0x18001bb28`
- `0x18001cad8`
- `0x180020e30`
- `0x180024360`
- `0x1800322d2`
- `0x1800323d0`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800186e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800186e1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800187e4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800187e4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001886e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001886e`

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
0x180018640  mov     [rsp-8+arg_18], rbx
0x180018645  push    rbp
0x180018646  push    rsi
0x180018647  push    rdi
0x180018648  push    r12
0x18001864a  push    r13
0x18001864c  push    r14
0x18001864e  push    r15
0x180018650  lea     rbp, [rsp-13C0h]
0x180018658  mov     eax, 14C0h
0x18001865d  call    _alloca_probe
0x180018662  sub     rsp, rax
0x180018665  mov     rsi, [rbp+13F0h+arg_28]
0x18001866c  mov     r15, r8
0x18001866f  mov     r14d, edx
0x180018672  mov     r12, rcx
0x180018675  xor     edx, edx; Val
0x180018677  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18001867c  mov     r8d, 98h; Size
0x180018682  call    memset_0
0x180018687  mov     rbx, [rbp+13F0h+arg_30]
0x18001868e  xor     r13d, r13d
0x180018691  mov     [rbp+13F0h+OutputString], r13w
0x180018699  mov     [rbp+13F0h+var_1430], r13b
0x18001869d  mov     ecx, [rbx]; this
0x18001869f  mov     eax, [rbx+4]
0x1800186a2  mov     [rsp+14F0h+var_14C8], ecx
0x1800186a6  mov     [rsp+14F0h+var_14C4], eax
0x1800186aa  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800186af  cmp     dword ptr [rbx+8], 1
0x1800186b3  mov     edi, eax
0x1800186b5  lea     eax, [r13+8]
0x1800186b9  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800186c1  mov     ecx, r13d
0x1800186c4  cmovz   ecx, eax
0x1800186c7  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800186cb  lea     ecx, [rax-7]
0x1800186ce  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800186d6  inc     ecx
0x1800186d8  mov     [rsp+14F0h+var_14B8], r13
0x1800186dd  mov     [rsp+14F0h+var_14C0], ecx
0x1800186e1  call    cs:__imp_GetCurrentThreadId
0x1800186e7  xorps   xmm0, xmm0
0x1800186ea  mov     [rsp+14F0h+var_1498], r15
0x1800186ef  mov     [rsp+14F0h+var_14B0], eax
0x1800186f3  xorps   xmm1, xmm1
0x1800186f6  xor     eax, eax
0x1800186f8  mov     [rsp+14F0h+var_1490], r14d
0x1800186fd  mov     [rbp+13F0h+var_1458], rax
0x180018701  mov     [rbp+13F0h+var_1470], rax
0x180018705  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001870c  mov     [rsp+14F0h+var_148C], edi
0x180018710  mov     [rsp+14F0h+var_14A8], r13
0x180018715  mov     [rsp+14F0h+var_14A0], r13
0x18001871a  mov     [rbp+13F0h+var_1448], rsi
0x18001871e  mov     [rbp+13F0h+var_1440], r12
0x180018722  mov     [rsp+14F0h+var_1488], r13
0x180018727  movups  [rbp+13F0h+var_1468], xmm0
0x18001872b  movups  [rsp+14F0h+var_1480], xmm1
0x180018730  test    rax, rax
0x180018733  jz      short loc_180018740
0x180018735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001873a  mov     [rbp+13F0h+var_1450], rax
0x18001873e  jmp     short loc_180018744
0x180018740  mov     [rbp+13F0h+var_1450], r13
0x180018744  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001874b  test    rax, rax
0x18001874e  jz      short loc_18001875A
0x180018750  lea     rcx, [rsp+14F0h+var_14D0]
0x180018755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001875a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180018761  test    rax, rax
0x180018764  jz      short loc_18001877A
0x180018766  mov     r8d, 400h
0x18001876c  lea     rdx, [rbp+13F0h+var_1430]
0x180018770  lea     rcx, [rsp+14F0h+var_14D0]
0x180018775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001877a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180018781  test    rax, rax
0x180018784  jz      short loc_180018790
0x180018786  lea     rcx, [rsp+14F0h+var_14D0]
0x18001878b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018790  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180018797  test    rax, rax
0x18001879a  jz      short loc_1800187AD
0x18001879c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800187a1  jnz     short loc_1800187AD
0x1800187a3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800187a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187ad  cmp     [rsp+14F0h+var_14C8], r13d
0x1800187b2  jl      short loc_1800187C6
0x1800187b4  mov     ecx, 8000FFFFh; this
0x1800187b9  mov     [rsp+14F0h+var_14C8], ecx
0x1800187bd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800187c2  mov     [rsp+14F0h+var_14C4], eax
0x1800187c6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800187cd  jnz     short loc_1800187EE
0x1800187cf  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800187d6  test    rax, rax
0x1800187d9  jz      short loc_1800187E4
0x1800187db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187e0  test    al, al
0x1800187e2  jmp     short loc_1800187EC
0x1800187e4  call    cs:__imp_IsDebuggerPresent
0x1800187ea  test    eax, eax
0x1800187ec  jz      short loc_1800187F5
0x1800187ee  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800187f3  jz      short loc_18001881B
0x1800187f5  mov     rax, cs:g_pfnResultLoggingCallback
0x1800187fc  test    rax, rax
0x1800187ff  jz      short loc_180018874
0x180018801  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180018808  jnz     short loc_180018874
0x18001880a  xor     r8d, r8d
0x18001880d  lea     rcx, [rsp+14F0h+var_14D0]
0x180018812  xor     edx, edx
0x180018814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018819  jmp     short loc_180018874
0x18001881b  mov     rax, cs:g_pfnResultLoggingCallback
0x180018822  mov     ebx, 800h
0x180018827  test    rax, rax
0x18001882a  jz      short loc_180018849
0x18001882c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180018833  jnz     short loc_180018849
0x180018835  mov     r8d, ebx
0x180018838  lea     rdx, [rbp+13F0h+OutputString]
0x18001883f  lea     rcx, [rsp+14F0h+var_14D0]
0x180018844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018849  cmp     [rbp+13F0h+OutputString], r13w
0x180018851  jnz     short loc_180018867
0x180018853  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180018858  mov     rdx, rbx; unsigned __int16 *
0x18001885b  lea     rcx, [rbp+13F0h+OutputString]; this
0x180018862  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180018867  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18001886e  call    cs:__imp_OutputDebugStringW
0x180018874  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180018879  jnz     short loc_180018884
0x18001887b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180018882  jz      short loc_180018895
0x180018884  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001888b  test    rax, rax
0x18001888e  jz      short loc_180018895
0x180018890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018895  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001889a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
