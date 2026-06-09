# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800090bc`
- end: `0x180009335`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180008ecc`

## callees

- `0x180001fd4`
- `0x1800090bc`
- `0x180009868`
- `0x180009dd4`
- `0x18000aa30`
- `0x18000aa9c`
- `0x18001d4b0`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009175`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009175`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009302`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009302`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009278`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009278`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
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
0x1800090bc  mov     [rsp-8+arg_18], rbx
0x1800090c1  push    rbp
0x1800090c2  push    rsi
0x1800090c3  push    rdi
0x1800090c4  push    r12
0x1800090c6  push    r13
0x1800090c8  push    r14
0x1800090ca  push    r15
0x1800090cc  lea     rbp, [rsp-13C0h]
0x1800090d4  mov     eax, 14C0h
0x1800090d9  call    _alloca_probe
0x1800090de  sub     rsp, rax
0x1800090e1  mov     r14, r8
0x1800090e4  mov     esi, edx
0x1800090e6  mov     rdi, rcx
0x1800090e9  mov     r15, [rbp+13F0h+arg_28]
0x1800090f0  xor     edx, edx; Val
0x1800090f2  mov     r8d, 98h; Size
0x1800090f8  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800090fd  call    memset_0
0x180009102  nop
0x180009103  xor     r13d, r13d
0x180009106  mov     [rbp+13F0h+OutputString], r13w
0x18000910e  mov     [rbp+13F0h+var_1430], r13b
0x180009112  mov     rbx, [rbp+13F0h+arg_30]
0x180009119  mov     ecx, [rbx]; this
0x18000911b  mov     [rsp+14F0h+var_14C8], ecx
0x18000911f  mov     eax, [rbx+4]
0x180009122  mov     [rsp+14F0h+var_14C4], eax
0x180009126  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000912b  mov     r12d, eax
0x18000912e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180009136  mov     ecx, r13d
0x180009139  lea     eax, [r13+8]
0x18000913d  cmp     dword ptr [rbx+8], 1
0x180009141  cmovz   ecx, eax
0x180009144  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180009148  lea     ecx, [rax-7]
0x18000914b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180009153  inc     ecx
0x180009155  mov     [rsp+14F0h+var_14C0], ecx
0x180009159  mov     rcx, [rbp+13F0h+arg_38]
0x180009160  test    rcx, rcx
0x180009163  jz      short loc_180009170
0x180009165  cmp     [rcx], r13w
0x180009169  mov     [rsp+14F0h+var_14B8], rcx
0x18000916e  jnz     short loc_180009175
0x180009170  mov     [rsp+14F0h+var_14B8], r13
0x180009175  call    cs:__imp_GetCurrentThreadId
0x18000917b  mov     [rsp+14F0h+var_14B0], eax
0x18000917f  mov     [rsp+14F0h+var_1498], r14
0x180009184  mov     [rsp+14F0h+var_1490], esi
0x180009188  mov     [rsp+14F0h+var_148C], r12d
0x18000918d  mov     [rsp+14F0h+var_14A8], r13
0x180009192  mov     [rsp+14F0h+var_14A0], r13
0x180009197  mov     [rbp+13F0h+var_1448], r15
0x18000919b  mov     [rbp+13F0h+var_1440], rdi
0x18000919f  mov     [rsp+14F0h+var_1488], r13
0x1800091a4  xorps   xmm0, xmm0
0x1800091a7  xor     eax, eax
0x1800091a9  movups  [rbp+13F0h+var_1468], xmm0
0x1800091ad  mov     [rbp+13F0h+var_1458], rax
0x1800091b1  xorps   xmm1, xmm1
0x1800091b4  movups  [rsp+14F0h+var_1480], xmm1
0x1800091b9  mov     [rbp+13F0h+var_1470], rax
0x1800091bd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800091c4  test    rax, rax
0x1800091c7  jz      short loc_1800091D4
0x1800091c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091ce  mov     [rbp+13F0h+var_1450], rax
0x1800091d2  jmp     short loc_1800091D8
0x1800091d4  mov     [rbp+13F0h+var_1450], r13
0x1800091d8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800091df  test    rax, rax
0x1800091e2  jz      short loc_1800091EE
0x1800091e4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800091e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091ee  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800091f5  test    rax, rax
0x1800091f8  jz      short loc_18000920E
0x1800091fa  mov     r8d, 400h
0x180009200  lea     rdx, [rbp+13F0h+var_1430]
0x180009204  lea     rcx, [rsp+14F0h+var_14D0]
0x180009209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000920e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009215  test    rax, rax
0x180009218  jz      short loc_180009224
0x18000921a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000921f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009224  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000922b  test    rax, rax
0x18000922e  jz      short loc_180009241
0x180009230  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180009235  jnz     short loc_180009241
0x180009237  lea     rcx, [rsp+14F0h+var_14D0]
0x18000923c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009241  cmp     [rsp+14F0h+var_14C8], r13d
0x180009246  jl      short loc_18000925A
0x180009248  mov     ecx, 8000FFFFh; this
0x18000924d  mov     [rsp+14F0h+var_14C8], ecx
0x180009251  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009256  mov     [rsp+14F0h+var_14C4], eax
0x18000925a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180009261  jnz     short loc_180009282
0x180009263  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000926a  test    rax, rax
0x18000926d  jz      short loc_180009278
0x18000926f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009274  test    al, al
0x180009276  jmp     short loc_180009280
0x180009278  call    cs:__imp_IsDebuggerPresent
0x18000927e  test    eax, eax
0x180009280  jz      short loc_180009289
0x180009282  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180009287  jz      short loc_1800092AF
0x180009289  mov     rax, cs:g_pfnResultLoggingCallback
0x180009290  test    rax, rax
0x180009293  jz      short loc_180009308
0x180009295  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000929c  jnz     short loc_180009308
0x18000929e  xor     r8d, r8d
0x1800092a1  xor     edx, edx
0x1800092a3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800092a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092ad  jmp     short loc_180009308
0x1800092af  mov     ebx, 800h
0x1800092b4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800092bb  test    rax, rax
0x1800092be  jz      short loc_1800092DD
0x1800092c0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800092c7  jnz     short loc_1800092DD
0x1800092c9  mov     r8d, ebx
0x1800092cc  lea     rdx, [rbp+13F0h+OutputString]
0x1800092d3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800092d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092dd  cmp     [rbp+13F0h+OutputString], r13w
0x1800092e5  jnz     short loc_1800092FB
0x1800092e7  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800092ec  mov     rdx, rbx; unsigned __int16 *
0x1800092ef  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800092f6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800092fb  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180009302  call    cs:__imp_OutputDebugStringW
0x180009308  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000930d  jnz     short loc_180009318
0x18000930f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180009316  jz      short loc_18000932A
0x180009318  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000931f  test    rax, rax
0x180009322  jz      short loc_18000932A
0x180009324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009329  nop
0x18000932a  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000932f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
