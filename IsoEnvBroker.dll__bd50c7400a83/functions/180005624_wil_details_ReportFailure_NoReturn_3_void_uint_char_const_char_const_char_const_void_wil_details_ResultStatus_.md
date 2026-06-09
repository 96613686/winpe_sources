# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180005624`
- end: `0x18000589d`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800053a4`

## callees

- `0x1800030d0`
- `0x180005624`
- `0x180007be4`
- `0x180008430`
- `0x1800093b0`
- `0x18000bb10`
- `0x180064360`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800056dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800056dd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800057e0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800057e0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000586a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000586a`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
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
0x180005624  mov     [rsp-8+arg_18], rbx
0x180005629  push    rbp
0x18000562a  push    rsi
0x18000562b  push    rdi
0x18000562c  push    r12
0x18000562e  push    r13
0x180005630  push    r14
0x180005632  push    r15
0x180005634  lea     rbp, [rsp-13C0h]
0x18000563c  mov     eax, 14C0h
0x180005641  call    _alloca_probe
0x180005646  sub     rsp, rax
0x180005649  mov     r14, r8
0x18000564c  mov     esi, edx
0x18000564e  mov     rdi, rcx
0x180005651  mov     r15, [rbp+13F0h+arg_28]
0x180005658  xor     edx, edx; Val
0x18000565a  mov     r8d, 98h; Size
0x180005660  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180005665  call    memset_0
0x18000566a  nop
0x18000566b  xor     r13d, r13d
0x18000566e  mov     [rbp+13F0h+OutputString], r13w
0x180005676  mov     [rbp+13F0h+var_1430], r13b
0x18000567a  mov     rbx, [rbp+13F0h+arg_30]
0x180005681  mov     ecx, [rbx]; this
0x180005683  mov     [rsp+14F0h+var_14C8], ecx
0x180005687  mov     eax, [rbx+4]
0x18000568a  mov     [rsp+14F0h+var_14C4], eax
0x18000568e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005693  mov     r12d, eax
0x180005696  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000569e  mov     ecx, r13d
0x1800056a1  lea     eax, [r13+8]
0x1800056a5  cmp     dword ptr [rbx+8], 1
0x1800056a9  cmovz   ecx, eax
0x1800056ac  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800056b0  lea     ecx, [rax-7]
0x1800056b3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800056bb  inc     ecx
0x1800056bd  mov     [rsp+14F0h+var_14C0], ecx
0x1800056c1  mov     rcx, [rbp+13F0h+arg_38]
0x1800056c8  test    rcx, rcx
0x1800056cb  jz      short loc_1800056D8
0x1800056cd  cmp     [rcx], r13w
0x1800056d1  mov     [rsp+14F0h+var_14B8], rcx
0x1800056d6  jnz     short loc_1800056DD
0x1800056d8  mov     [rsp+14F0h+var_14B8], r13
0x1800056dd  call    cs:__imp_GetCurrentThreadId
0x1800056e3  mov     [rsp+14F0h+var_14B0], eax
0x1800056e7  mov     [rsp+14F0h+var_1498], r14
0x1800056ec  mov     [rsp+14F0h+var_1490], esi
0x1800056f0  mov     [rsp+14F0h+var_148C], r12d
0x1800056f5  mov     [rsp+14F0h+var_14A8], r13
0x1800056fa  mov     [rsp+14F0h+var_14A0], r13
0x1800056ff  mov     [rbp+13F0h+var_1448], r15
0x180005703  mov     [rbp+13F0h+var_1440], rdi
0x180005707  mov     [rsp+14F0h+var_1488], r13
0x18000570c  xorps   xmm0, xmm0
0x18000570f  xor     eax, eax
0x180005711  movups  [rbp+13F0h+var_1468], xmm0
0x180005715  mov     [rbp+13F0h+var_1458], rax
0x180005719  xorps   xmm1, xmm1
0x18000571c  movups  [rsp+14F0h+var_1480], xmm1
0x180005721  mov     [rbp+13F0h+var_1470], rax
0x180005725  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000572c  test    rax, rax
0x18000572f  jz      short loc_18000573C
0x180005731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005736  mov     [rbp+13F0h+var_1450], rax
0x18000573a  jmp     short loc_180005740
0x18000573c  mov     [rbp+13F0h+var_1450], r13
0x180005740  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005747  test    rax, rax
0x18000574a  jz      short loc_180005756
0x18000574c  lea     rcx, [rsp+14F0h+var_14D0]
0x180005751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005756  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000575d  test    rax, rax
0x180005760  jz      short loc_180005776
0x180005762  mov     r8d, 400h
0x180005768  lea     rdx, [rbp+13F0h+var_1430]
0x18000576c  lea     rcx, [rsp+14F0h+var_14D0]
0x180005771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005776  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000577d  test    rax, rax
0x180005780  jz      short loc_18000578C
0x180005782  lea     rcx, [rsp+14F0h+var_14D0]
0x180005787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000578c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005793  test    rax, rax
0x180005796  jz      short loc_1800057A9
0x180005798  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000579d  jnz     short loc_1800057A9
0x18000579f  lea     rcx, [rsp+14F0h+var_14D0]
0x1800057a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057a9  cmp     [rsp+14F0h+var_14C8], r13d
0x1800057ae  jl      short loc_1800057C2
0x1800057b0  mov     ecx, 8000FFFFh; this
0x1800057b5  mov     [rsp+14F0h+var_14C8], ecx
0x1800057b9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800057be  mov     [rsp+14F0h+var_14C4], eax
0x1800057c2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800057c9  jnz     short loc_1800057EA
0x1800057cb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800057d2  test    rax, rax
0x1800057d5  jz      short loc_1800057E0
0x1800057d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057dc  test    al, al
0x1800057de  jmp     short loc_1800057E8
0x1800057e0  call    cs:__imp_IsDebuggerPresent
0x1800057e6  test    eax, eax
0x1800057e8  jz      short loc_1800057F1
0x1800057ea  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800057ef  jz      short loc_180005817
0x1800057f1  mov     rax, cs:g_pfnResultLoggingCallback
0x1800057f8  test    rax, rax
0x1800057fb  jz      short loc_180005870
0x1800057fd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005804  jnz     short loc_180005870
0x180005806  xor     r8d, r8d
0x180005809  xor     edx, edx
0x18000580b  lea     rcx, [rsp+14F0h+var_14D0]
0x180005810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005815  jmp     short loc_180005870
0x180005817  mov     ebx, 800h
0x18000581c  mov     rax, cs:g_pfnResultLoggingCallback
0x180005823  test    rax, rax
0x180005826  jz      short loc_180005845
0x180005828  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000582f  jnz     short loc_180005845
0x180005831  mov     r8d, ebx
0x180005834  lea     rdx, [rbp+13F0h+OutputString]
0x18000583b  lea     rcx, [rsp+14F0h+var_14D0]
0x180005840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005845  cmp     [rbp+13F0h+OutputString], r13w
0x18000584d  jnz     short loc_180005863
0x18000584f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180005854  mov     rdx, rbx; wchar_t *
0x180005857  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000585e  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180005863  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000586a  call    cs:__imp_OutputDebugStringW
0x180005870  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180005875  jnz     short loc_180005880
0x180005877  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000587e  jz      short loc_180005892
0x180005880  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005887  test    rax, rax
0x18000588a  jz      short loc_180005892
0x18000588c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005891  nop
0x180005892  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005897  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
