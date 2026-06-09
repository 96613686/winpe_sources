# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18002737c`
- end: `0x1800275de`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180027118`

## callees

- `0x1800268ef`
- `0x18002737c`
- `0x18002a784`
- `0x18002afc8`
- `0x18002c7a0`
- `0x18002f900`
- `0x1800351a0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002741e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002741e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180027521`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180027521`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800275ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800275ab`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
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
0x18002737c  mov     [rsp-8+arg_18], rbx
0x180027381  push    rbp
0x180027382  push    rsi
0x180027383  push    rdi
0x180027384  push    r12
0x180027386  push    r13
0x180027388  push    r14
0x18002738a  push    r15
0x18002738c  lea     rbp, [rsp-13C0h]
0x180027394  mov     eax, 14C0h
0x180027399  call    _alloca_probe
0x18002739e  sub     rsp, rax
0x1800273a1  mov     r15, r8
0x1800273a4  mov     r14d, edx
0x1800273a7  mov     r12, rcx
0x1800273aa  mov     rsi, [rbp+13F0h+arg_28]
0x1800273b1  xor     edx, edx; Val
0x1800273b3  mov     r8d, 98h; Size
0x1800273b9  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800273be  call    memset_0
0x1800273c3  nop
0x1800273c4  xor     r13d, r13d
0x1800273c7  mov     [rbp+13F0h+OutputString], r13w
0x1800273cf  mov     [rbp+13F0h+var_1430], r13b
0x1800273d3  mov     rbx, [rbp+13F0h+arg_30]
0x1800273da  mov     ecx, [rbx]; this
0x1800273dc  mov     [rsp+14F0h+var_14C8], ecx
0x1800273e0  mov     eax, [rbx+4]
0x1800273e3  mov     [rsp+14F0h+var_14C4], eax
0x1800273e7  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800273ec  mov     edi, eax
0x1800273ee  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800273f6  mov     ecx, r13d
0x1800273f9  lea     eax, [r13+8]
0x1800273fd  cmp     dword ptr [rbx+8], 1
0x180027401  cmovz   ecx, eax
0x180027404  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180027408  lea     ecx, [rax-7]
0x18002740b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180027413  inc     ecx
0x180027415  mov     [rsp+14F0h+var_14C0], ecx
0x180027419  mov     [rsp+14F0h+var_14B8], r13
0x18002741e  call    cs:__imp_GetCurrentThreadId
0x180027424  mov     [rsp+14F0h+var_14B0], eax
0x180027428  mov     [rsp+14F0h+var_1498], r15
0x18002742d  mov     [rsp+14F0h+var_1490], r14d
0x180027432  mov     [rsp+14F0h+var_148C], edi
0x180027436  mov     [rsp+14F0h+var_14A8], r13
0x18002743b  mov     [rsp+14F0h+var_14A0], r13
0x180027440  mov     [rbp+13F0h+var_1448], rsi
0x180027444  mov     [rbp+13F0h+var_1440], r12
0x180027448  mov     [rsp+14F0h+var_1488], r13
0x18002744d  xorps   xmm0, xmm0
0x180027450  xor     eax, eax
0x180027452  movups  [rbp+13F0h+var_1468], xmm0
0x180027456  mov     [rbp+13F0h+var_1458], rax
0x18002745a  xorps   xmm1, xmm1
0x18002745d  movups  [rsp+14F0h+var_1480], xmm1
0x180027462  mov     [rbp+13F0h+var_1470], rax
0x180027466  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002746d  test    rax, rax
0x180027470  jz      short loc_18002747D
0x180027472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027477  mov     [rbp+13F0h+var_1450], rax
0x18002747b  jmp     short loc_180027481
0x18002747d  mov     [rbp+13F0h+var_1450], r13
0x180027481  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180027488  test    rax, rax
0x18002748b  jz      short loc_180027497
0x18002748d  lea     rcx, [rsp+14F0h+var_14D0]
0x180027492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027497  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002749e  test    rax, rax
0x1800274a1  jz      short loc_1800274B7
0x1800274a3  mov     r8d, 400h
0x1800274a9  lea     rdx, [rbp+13F0h+var_1430]
0x1800274ad  lea     rcx, [rsp+14F0h+var_14D0]
0x1800274b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274b7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800274be  test    rax, rax
0x1800274c1  jz      short loc_1800274CD
0x1800274c3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800274c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274cd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800274d4  test    rax, rax
0x1800274d7  jz      short loc_1800274EA
0x1800274d9  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800274de  jnz     short loc_1800274EA
0x1800274e0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800274e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274ea  cmp     [rsp+14F0h+var_14C8], r13d
0x1800274ef  jl      short loc_180027503
0x1800274f1  mov     ecx, 8000FFFFh; this
0x1800274f6  mov     [rsp+14F0h+var_14C8], ecx
0x1800274fa  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800274ff  mov     [rsp+14F0h+var_14C4], eax
0x180027503  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18002750a  jnz     short loc_18002752B
0x18002750c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180027513  test    rax, rax
0x180027516  jz      short loc_180027521
0x180027518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002751d  test    al, al
0x18002751f  jmp     short loc_180027529
0x180027521  call    cs:__imp_IsDebuggerPresent
0x180027527  test    eax, eax
0x180027529  jz      short loc_180027532
0x18002752b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180027530  jz      short loc_180027558
0x180027532  mov     rax, cs:g_pfnResultLoggingCallback
0x180027539  test    rax, rax
0x18002753c  jz      short loc_1800275B1
0x18002753e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180027545  jnz     short loc_1800275B1
0x180027547  xor     r8d, r8d
0x18002754a  xor     edx, edx
0x18002754c  lea     rcx, [rsp+14F0h+var_14D0]
0x180027551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027556  jmp     short loc_1800275B1
0x180027558  mov     ebx, 800h
0x18002755d  mov     rax, cs:g_pfnResultLoggingCallback
0x180027564  test    rax, rax
0x180027567  jz      short loc_180027586
0x180027569  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180027570  jnz     short loc_180027586
0x180027572  mov     r8d, ebx
0x180027575  lea     rdx, [rbp+13F0h+OutputString]
0x18002757c  lea     rcx, [rsp+14F0h+var_14D0]
0x180027581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027586  cmp     [rbp+13F0h+OutputString], r13w
0x18002758e  jnz     short loc_1800275A4
0x180027590  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180027595  mov     rdx, rbx; unsigned __int16 *
0x180027598  lea     rcx, [rbp+13F0h+OutputString]; this
0x18002759f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800275a4  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800275ab  call    cs:__imp_OutputDebugStringW
0x1800275b1  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800275b6  jnz     short loc_1800275C1
0x1800275b8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800275bf  jz      short loc_1800275D3
0x1800275c1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800275c8  test    rax, rax
0x1800275cb  jz      short loc_1800275D3
0x1800275cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275d2  nop
0x1800275d3  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800275d8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
