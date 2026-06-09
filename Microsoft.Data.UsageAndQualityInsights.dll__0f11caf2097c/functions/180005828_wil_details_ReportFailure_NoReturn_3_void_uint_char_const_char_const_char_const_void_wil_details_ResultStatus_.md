# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180005828`
- end: `0x180005aa1`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180005464`

## callees

- `0x180003fb8`
- `0x180005828`
- `0x180007fa4`
- `0x1800087f0`
- `0x180009770`
- `0x18000bfe0`
- `0x180101970`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800058e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800058e1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800059e4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800059e4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005a6e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005a6e`

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
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)&v18, v16);
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
0x180005828  mov     [rsp-8+arg_18], rbx
0x18000582d  push    rbp
0x18000582e  push    rsi
0x18000582f  push    rdi
0x180005830  push    r12
0x180005832  push    r13
0x180005834  push    r14
0x180005836  push    r15
0x180005838  lea     rbp, [rsp-13C0h]
0x180005840  mov     eax, 14C0h
0x180005845  call    _alloca_probe
0x18000584a  sub     rsp, rax
0x18000584d  mov     r14, r8
0x180005850  mov     esi, edx
0x180005852  mov     rdi, rcx
0x180005855  mov     r15, [rbp+13F0h+arg_28]
0x18000585c  xor     edx, edx; Val
0x18000585e  mov     r8d, 98h; Size
0x180005864  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180005869  call    memset_0
0x18000586e  nop
0x18000586f  xor     r13d, r13d
0x180005872  mov     [rbp+13F0h+OutputString], r13w
0x18000587a  mov     [rbp+13F0h+var_1430], r13b
0x18000587e  mov     rbx, [rbp+13F0h+arg_30]
0x180005885  mov     ecx, [rbx]; this
0x180005887  mov     [rsp+14F0h+var_14C8], ecx
0x18000588b  mov     eax, [rbx+4]
0x18000588e  mov     [rsp+14F0h+var_14C4], eax
0x180005892  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005897  mov     r12d, eax
0x18000589a  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800058a2  mov     ecx, r13d
0x1800058a5  lea     eax, [r13+8]
0x1800058a9  cmp     dword ptr [rbx+8], 1
0x1800058ad  cmovz   ecx, eax
0x1800058b0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800058b4  lea     ecx, [rax-7]
0x1800058b7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800058bf  inc     ecx
0x1800058c1  mov     [rsp+14F0h+var_14C0], ecx
0x1800058c5  mov     rcx, [rbp+13F0h+arg_38]
0x1800058cc  test    rcx, rcx
0x1800058cf  jz      short loc_1800058DC
0x1800058d1  cmp     [rcx], r13w
0x1800058d5  mov     [rsp+14F0h+var_14B8], rcx
0x1800058da  jnz     short loc_1800058E1
0x1800058dc  mov     [rsp+14F0h+var_14B8], r13
0x1800058e1  call    cs:__imp_GetCurrentThreadId
0x1800058e7  mov     [rsp+14F0h+var_14B0], eax
0x1800058eb  mov     [rsp+14F0h+var_1498], r14
0x1800058f0  mov     [rsp+14F0h+var_1490], esi
0x1800058f4  mov     [rsp+14F0h+var_148C], r12d
0x1800058f9  mov     [rsp+14F0h+var_14A8], r13
0x1800058fe  mov     [rsp+14F0h+var_14A0], r13
0x180005903  mov     [rbp+13F0h+var_1448], r15
0x180005907  mov     [rbp+13F0h+var_1440], rdi
0x18000590b  mov     [rsp+14F0h+var_1488], r13
0x180005910  xorps   xmm0, xmm0
0x180005913  xor     eax, eax
0x180005915  movups  [rbp+13F0h+var_1468], xmm0
0x180005919  mov     [rbp+13F0h+var_1458], rax
0x18000591d  xorps   xmm1, xmm1
0x180005920  movups  [rsp+14F0h+var_1480], xmm1
0x180005925  mov     [rbp+13F0h+var_1470], rax
0x180005929  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005930  test    rax, rax
0x180005933  jz      short loc_180005940
0x180005935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000593a  mov     [rbp+13F0h+var_1450], rax
0x18000593e  jmp     short loc_180005944
0x180005940  mov     [rbp+13F0h+var_1450], r13
0x180005944  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000594b  test    rax, rax
0x18000594e  jz      short loc_18000595A
0x180005950  lea     rcx, [rsp+14F0h+var_14D0]
0x180005955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000595a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005961  test    rax, rax
0x180005964  jz      short loc_18000597A
0x180005966  mov     r8d, 400h
0x18000596c  lea     rdx, [rbp+13F0h+var_1430]
0x180005970  lea     rcx, [rsp+14F0h+var_14D0]
0x180005975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000597a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005981  test    rax, rax
0x180005984  jz      short loc_180005990
0x180005986  lea     rcx, [rsp+14F0h+var_14D0]
0x18000598b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005990  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005997  test    rax, rax
0x18000599a  jz      short loc_1800059AD
0x18000599c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800059a1  jnz     short loc_1800059AD
0x1800059a3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800059a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059ad  cmp     [rsp+14F0h+var_14C8], r13d
0x1800059b2  jl      short loc_1800059C6
0x1800059b4  mov     ecx, 8000FFFFh; this
0x1800059b9  mov     [rsp+14F0h+var_14C8], ecx
0x1800059bd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800059c2  mov     [rsp+14F0h+var_14C4], eax
0x1800059c6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800059cd  jnz     short loc_1800059EE
0x1800059cf  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800059d6  test    rax, rax
0x1800059d9  jz      short loc_1800059E4
0x1800059db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059e0  test    al, al
0x1800059e2  jmp     short loc_1800059EC
0x1800059e4  call    cs:__imp_IsDebuggerPresent
0x1800059ea  test    eax, eax
0x1800059ec  jz      short loc_1800059F5
0x1800059ee  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800059f3  jz      short loc_180005A1B
0x1800059f5  mov     rax, cs:g_pfnResultLoggingCallback
0x1800059fc  test    rax, rax
0x1800059ff  jz      short loc_180005A74
0x180005a01  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005a08  jnz     short loc_180005A74
0x180005a0a  xor     r8d, r8d
0x180005a0d  xor     edx, edx
0x180005a0f  lea     rcx, [rsp+14F0h+var_14D0]
0x180005a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a19  jmp     short loc_180005A74
0x180005a1b  mov     ebx, 800h
0x180005a20  mov     rax, cs:g_pfnResultLoggingCallback
0x180005a27  test    rax, rax
0x180005a2a  jz      short loc_180005A49
0x180005a2c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005a33  jnz     short loc_180005A49
0x180005a35  mov     r8d, ebx
0x180005a38  lea     rdx, [rbp+13F0h+OutputString]
0x180005a3f  lea     rcx, [rsp+14F0h+var_14D0]
0x180005a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a49  cmp     [rbp+13F0h+OutputString], r13w
0x180005a51  jnz     short loc_180005A67
0x180005a53  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180005a58  mov     rdx, rbx; wchar_t *
0x180005a5b  lea     rcx, [rbp+13F0h+OutputString]; this
0x180005a62  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180005a67  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180005a6e  call    cs:__imp_OutputDebugStringW
0x180005a74  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180005a79  jnz     short loc_180005A84
0x180005a7b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180005a82  jz      short loc_180005A96
0x180005a84  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005a8b  test    rax, rax
0x180005a8e  jz      short loc_180005A96
0x180005a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a95  nop
0x180005a96  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005a9b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
