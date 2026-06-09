# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180005284`
- end: `0x1800054fd`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180004fec`

## callees

- `0x180003d14`
- `0x180005284`
- `0x1800076e4`
- `0x180008250`
- `0x180008ef0`
- `0x18000a4f0`
- `0x180028fe0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000533d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000533d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005440`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005440`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800054ca`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800054ca`

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
0x180005284  mov     [rsp-8+arg_18], rbx
0x180005289  push    rbp
0x18000528a  push    rsi
0x18000528b  push    rdi
0x18000528c  push    r12
0x18000528e  push    r13
0x180005290  push    r14
0x180005292  push    r15
0x180005294  lea     rbp, [rsp-13C0h]
0x18000529c  mov     eax, 14C0h
0x1800052a1  call    _alloca_probe
0x1800052a6  sub     rsp, rax
0x1800052a9  mov     r14, r8
0x1800052ac  mov     esi, edx
0x1800052ae  mov     rdi, rcx
0x1800052b1  mov     r15, [rbp+13F0h+arg_28]
0x1800052b8  xor     edx, edx; Val
0x1800052ba  mov     r8d, 98h; Size
0x1800052c0  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800052c5  call    memset_0
0x1800052ca  nop
0x1800052cb  xor     r13d, r13d
0x1800052ce  mov     [rbp+13F0h+OutputString], r13w
0x1800052d6  mov     [rbp+13F0h+var_1430], r13b
0x1800052da  mov     rbx, [rbp+13F0h+arg_30]
0x1800052e1  mov     ecx, [rbx]; this
0x1800052e3  mov     [rsp+14F0h+var_14C8], ecx
0x1800052e7  mov     eax, [rbx+4]
0x1800052ea  mov     [rsp+14F0h+var_14C4], eax
0x1800052ee  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800052f3  mov     r12d, eax
0x1800052f6  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800052fe  mov     ecx, r13d
0x180005301  lea     eax, [r13+8]
0x180005305  cmp     dword ptr [rbx+8], 1
0x180005309  cmovz   ecx, eax
0x18000530c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180005310  lea     ecx, [rax-7]
0x180005313  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000531b  inc     ecx
0x18000531d  mov     [rsp+14F0h+var_14C0], ecx
0x180005321  mov     rcx, [rbp+13F0h+arg_38]
0x180005328  test    rcx, rcx
0x18000532b  jz      short loc_180005338
0x18000532d  cmp     [rcx], r13w
0x180005331  mov     [rsp+14F0h+var_14B8], rcx
0x180005336  jnz     short loc_18000533D
0x180005338  mov     [rsp+14F0h+var_14B8], r13
0x18000533d  call    cs:__imp_GetCurrentThreadId
0x180005343  mov     [rsp+14F0h+var_14B0], eax
0x180005347  mov     [rsp+14F0h+var_1498], r14
0x18000534c  mov     [rsp+14F0h+var_1490], esi
0x180005350  mov     [rsp+14F0h+var_148C], r12d
0x180005355  mov     [rsp+14F0h+var_14A8], r13
0x18000535a  mov     [rsp+14F0h+var_14A0], r13
0x18000535f  mov     [rbp+13F0h+var_1448], r15
0x180005363  mov     [rbp+13F0h+var_1440], rdi
0x180005367  mov     [rsp+14F0h+var_1488], r13
0x18000536c  xorps   xmm0, xmm0
0x18000536f  xor     eax, eax
0x180005371  movups  [rbp+13F0h+var_1468], xmm0
0x180005375  mov     [rbp+13F0h+var_1458], rax
0x180005379  xorps   xmm1, xmm1
0x18000537c  movups  [rsp+14F0h+var_1480], xmm1
0x180005381  mov     [rbp+13F0h+var_1470], rax
0x180005385  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000538c  test    rax, rax
0x18000538f  jz      short loc_18000539C
0x180005391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005396  mov     [rbp+13F0h+var_1450], rax
0x18000539a  jmp     short loc_1800053A0
0x18000539c  mov     [rbp+13F0h+var_1450], r13
0x1800053a0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800053a7  test    rax, rax
0x1800053aa  jz      short loc_1800053B6
0x1800053ac  lea     rcx, [rsp+14F0h+var_14D0]
0x1800053b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053b6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800053bd  test    rax, rax
0x1800053c0  jz      short loc_1800053D6
0x1800053c2  mov     r8d, 400h
0x1800053c8  lea     rdx, [rbp+13F0h+var_1430]
0x1800053cc  lea     rcx, [rsp+14F0h+var_14D0]
0x1800053d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053d6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800053dd  test    rax, rax
0x1800053e0  jz      short loc_1800053EC
0x1800053e2  lea     rcx, [rsp+14F0h+var_14D0]
0x1800053e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053ec  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800053f3  test    rax, rax
0x1800053f6  jz      short loc_180005409
0x1800053f8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800053fd  jnz     short loc_180005409
0x1800053ff  lea     rcx, [rsp+14F0h+var_14D0]
0x180005404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005409  cmp     [rsp+14F0h+var_14C8], r13d
0x18000540e  jl      short loc_180005422
0x180005410  mov     ecx, 8000FFFFh; this
0x180005415  mov     [rsp+14F0h+var_14C8], ecx
0x180005419  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000541e  mov     [rsp+14F0h+var_14C4], eax
0x180005422  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180005429  jnz     short loc_18000544A
0x18000542b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005432  test    rax, rax
0x180005435  jz      short loc_180005440
0x180005437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000543c  test    al, al
0x18000543e  jmp     short loc_180005448
0x180005440  call    cs:__imp_IsDebuggerPresent
0x180005446  test    eax, eax
0x180005448  jz      short loc_180005451
0x18000544a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000544f  jz      short loc_180005477
0x180005451  mov     rax, cs:g_pfnResultLoggingCallback
0x180005458  test    rax, rax
0x18000545b  jz      short loc_1800054D0
0x18000545d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005464  jnz     short loc_1800054D0
0x180005466  xor     r8d, r8d
0x180005469  xor     edx, edx
0x18000546b  lea     rcx, [rsp+14F0h+var_14D0]
0x180005470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005475  jmp     short loc_1800054D0
0x180005477  mov     ebx, 800h
0x18000547c  mov     rax, cs:g_pfnResultLoggingCallback
0x180005483  test    rax, rax
0x180005486  jz      short loc_1800054A5
0x180005488  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000548f  jnz     short loc_1800054A5
0x180005491  mov     r8d, ebx
0x180005494  lea     rdx, [rbp+13F0h+OutputString]
0x18000549b  lea     rcx, [rsp+14F0h+var_14D0]
0x1800054a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054a5  cmp     [rbp+13F0h+OutputString], r13w
0x1800054ad  jnz     short loc_1800054C3
0x1800054af  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800054b4  mov     rdx, rbx; unsigned __int16 *
0x1800054b7  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800054be  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800054c3  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800054ca  call    cs:__imp_OutputDebugStringW
0x1800054d0  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800054d5  jnz     short loc_1800054E0
0x1800054d7  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800054de  jz      short loc_1800054F2
0x1800054e0  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800054e7  test    rax, rax
0x1800054ea  jz      short loc_1800054F2
0x1800054ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054f1  nop
0x1800054f2  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800054f7  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
