# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002208`
- end: `0x180002493`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180001d94`

## callees

- `0x180002208`
- `0x180005304`
- `0x180005bc4`
- `0x180006d00`
- `0x180007e7c`
- `0x180009c5e`
- `0x180009d50`
- `0x18000b010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x18000245a`
- `KERNEL32!OutputDebugStringW` at `0x18000245a`
- `KERNEL32!IsDebuggerPresent` at `0x1800023ca`
- `KERNEL32!IsDebuggerPresent` at `0x1800023ca`
- `KERNEL32!GetCurrentThreadId` at `0x1800022c1`
- `KERNEL32!GetCurrentThreadId` at `0x1800022c1`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
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
0x180002208  mov     [rsp-8+arg_18], rbx
0x18000220d  push    rbp
0x18000220e  push    rsi
0x18000220f  push    rdi
0x180002210  push    r12
0x180002212  push    r13
0x180002214  push    r14
0x180002216  push    r15
0x180002218  lea     rbp, [rsp-13C0h]
0x180002220  mov     eax, 14C0h
0x180002225  call    _alloca_probe
0x18000222a  sub     rsp, rax
0x18000222d  mov     r14, r8
0x180002230  mov     esi, edx
0x180002232  mov     rdi, rcx
0x180002235  mov     r15, [rbp+13F0h+arg_28]
0x18000223c  xor     edx, edx; Val
0x18000223e  mov     r8d, 98h; Size
0x180002244  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002249  call    memset_0
0x18000224e  nop
0x18000224f  xor     r13d, r13d
0x180002252  mov     [rbp+13F0h+OutputString], r13w
0x18000225a  mov     [rbp+13F0h+var_1430], r13b
0x18000225e  mov     rbx, [rbp+13F0h+arg_30]
0x180002265  mov     ecx, [rbx]; this
0x180002267  mov     [rsp+14F0h+var_14C8], ecx
0x18000226b  mov     eax, [rbx+4]
0x18000226e  mov     [rsp+14F0h+var_14C4], eax
0x180002272  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002277  mov     r12d, eax
0x18000227a  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180002282  mov     ecx, r13d
0x180002285  lea     eax, [r13+8]
0x180002289  cmp     dword ptr [rbx+8], 1
0x18000228d  cmovz   ecx, eax
0x180002290  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002294  lea     ecx, [rax-7]
0x180002297  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000229f  inc     ecx
0x1800022a1  mov     [rsp+14F0h+var_14C0], ecx
0x1800022a5  mov     rcx, [rbp+13F0h+arg_38]
0x1800022ac  test    rcx, rcx
0x1800022af  jz      short loc_1800022BC
0x1800022b1  cmp     [rcx], r13w
0x1800022b5  mov     [rsp+14F0h+var_14B8], rcx
0x1800022ba  jnz     short loc_1800022C1
0x1800022bc  mov     [rsp+14F0h+var_14B8], r13
0x1800022c1  call    cs:__imp_GetCurrentThreadId
0x1800022c8  nop     dword ptr [rax+rax+00h]
0x1800022cd  mov     [rsp+14F0h+var_14B0], eax
0x1800022d1  mov     [rsp+14F0h+var_1498], r14
0x1800022d6  mov     [rsp+14F0h+var_1490], esi
0x1800022da  mov     [rsp+14F0h+var_148C], r12d
0x1800022df  mov     [rsp+14F0h+var_14A8], r13
0x1800022e4  mov     [rsp+14F0h+var_14A0], r13
0x1800022e9  mov     [rbp+13F0h+var_1448], r15
0x1800022ed  mov     [rbp+13F0h+var_1440], rdi
0x1800022f1  mov     [rsp+14F0h+var_1488], r13
0x1800022f6  xorps   xmm0, xmm0
0x1800022f9  xor     eax, eax
0x1800022fb  movups  [rbp+13F0h+var_1468], xmm0
0x1800022ff  mov     [rbp+13F0h+var_1458], rax
0x180002303  xorps   xmm1, xmm1
0x180002306  movups  [rsp+14F0h+var_1480], xmm1
0x18000230b  mov     [rbp+13F0h+var_1470], rax
0x18000230f  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002316  test    rax, rax
0x180002319  jz      short loc_180002326
0x18000231b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002320  mov     [rbp+13F0h+var_1450], rax
0x180002324  jmp     short loc_18000232A
0x180002326  mov     [rbp+13F0h+var_1450], r13
0x18000232a  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002331  test    rax, rax
0x180002334  jz      short loc_180002340
0x180002336  lea     rcx, [rsp+14F0h+var_14D0]
0x18000233b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002340  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002347  test    rax, rax
0x18000234a  jz      short loc_180002360
0x18000234c  mov     r8d, 400h
0x180002352  lea     rdx, [rbp+13F0h+var_1430]
0x180002356  lea     rcx, [rsp+14F0h+var_14D0]
0x18000235b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002360  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002367  test    rax, rax
0x18000236a  jz      short loc_180002376
0x18000236c  lea     rcx, [rsp+14F0h+var_14D0]
0x180002371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002376  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000237d  test    rax, rax
0x180002380  jz      short loc_180002393
0x180002382  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002387  jnz     short loc_180002393
0x180002389  lea     rcx, [rsp+14F0h+var_14D0]
0x18000238e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002393  cmp     [rsp+14F0h+var_14C8], r13d
0x180002398  jl      short loc_1800023AC
0x18000239a  mov     ecx, 8000FFFFh; this
0x18000239f  mov     [rsp+14F0h+var_14C8], ecx
0x1800023a3  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800023a8  mov     [rsp+14F0h+var_14C4], eax
0x1800023ac  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800023b3  jnz     short loc_1800023DA
0x1800023b5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800023bc  test    rax, rax
0x1800023bf  jz      short loc_1800023CA
0x1800023c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023c6  test    al, al
0x1800023c8  jmp     short loc_1800023D8
0x1800023ca  call    cs:__imp_IsDebuggerPresent
0x1800023d1  nop     dword ptr [rax+rax+00h]
0x1800023d6  test    eax, eax
0x1800023d8  jz      short loc_1800023E1
0x1800023da  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800023df  jz      short loc_180002407
0x1800023e1  mov     rax, cs:g_pfnResultLoggingCallback
0x1800023e8  test    rax, rax
0x1800023eb  jz      short loc_180002466
0x1800023ed  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800023f4  jnz     short loc_180002466
0x1800023f6  xor     r8d, r8d
0x1800023f9  xor     edx, edx
0x1800023fb  lea     rcx, [rsp+14F0h+var_14D0]
0x180002400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002405  jmp     short loc_180002466
0x180002407  mov     ebx, 800h
0x18000240c  mov     rax, cs:g_pfnResultLoggingCallback
0x180002413  test    rax, rax
0x180002416  jz      short loc_180002435
0x180002418  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000241f  jnz     short loc_180002435
0x180002421  mov     r8d, ebx
0x180002424  lea     rdx, [rbp+13F0h+OutputString]
0x18000242b  lea     rcx, [rsp+14F0h+var_14D0]
0x180002430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002435  cmp     [rbp+13F0h+OutputString], r13w
0x18000243d  jnz     short loc_180002453
0x18000243f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002444  mov     rdx, rbx; unsigned __int16 *
0x180002447  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000244e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002453  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000245a  call    cs:__imp_OutputDebugStringW
0x180002461  nop     dword ptr [rax+rax+00h]
0x180002466  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000246b  jnz     short loc_180002476
0x18000246d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180002474  jz      short loc_180002488
0x180002476  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000247d  test    rax, rax
0x180002480  jz      short loc_180002488
0x180002482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002487  nop
0x180002488  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000248d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
