# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180047fac`
- end: `0x18004820e`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180047d78`

## callees

- `0x180045374`
- `0x180045d84`
- `0x18004616c`
- `0x180046460`
- `0x180047fac`
- `0x18004ea30`
- `0x1800a6c60`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004804e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004804e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180048151`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180048151`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800481db`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800481db`

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
0x180047fac  mov     [rsp-8+arg_18], rbx
0x180047fb1  push    rbp
0x180047fb2  push    rsi
0x180047fb3  push    rdi
0x180047fb4  push    r12
0x180047fb6  push    r13
0x180047fb8  push    r14
0x180047fba  push    r15
0x180047fbc  lea     rbp, [rsp-13C0h]
0x180047fc4  mov     eax, 14C0h
0x180047fc9  call    _alloca_probe
0x180047fce  sub     rsp, rax
0x180047fd1  mov     r15, r8
0x180047fd4  mov     r14d, edx
0x180047fd7  mov     r12, rcx
0x180047fda  mov     rsi, [rbp+13F0h+arg_28]
0x180047fe1  xor     edx, edx; Val
0x180047fe3  mov     r8d, 98h; Size
0x180047fe9  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180047fee  call    memset_0
0x180047ff3  nop
0x180047ff4  xor     r13d, r13d
0x180047ff7  mov     [rbp+13F0h+OutputString], r13w
0x180047fff  mov     [rbp+13F0h+var_1430], r13b
0x180048003  mov     rbx, [rbp+13F0h+arg_30]
0x18004800a  mov     ecx, [rbx]; this
0x18004800c  mov     [rsp+14F0h+var_14C8], ecx
0x180048010  mov     eax, [rbx+4]
0x180048013  mov     [rsp+14F0h+var_14C4], eax
0x180048017  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18004801c  mov     edi, eax
0x18004801e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180048026  mov     ecx, r13d
0x180048029  lea     eax, [r13+8]
0x18004802d  cmp     dword ptr [rbx+8], 1
0x180048031  cmovz   ecx, eax
0x180048034  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180048038  lea     ecx, [rax-7]
0x18004803b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180048043  inc     ecx
0x180048045  mov     [rsp+14F0h+var_14C0], ecx
0x180048049  mov     [rsp+14F0h+var_14B8], r13
0x18004804e  call    cs:__imp_GetCurrentThreadId
0x180048054  mov     [rsp+14F0h+var_14B0], eax
0x180048058  mov     [rsp+14F0h+var_1498], r15
0x18004805d  mov     [rsp+14F0h+var_1490], r14d
0x180048062  mov     [rsp+14F0h+var_148C], edi
0x180048066  mov     [rsp+14F0h+var_14A8], r13
0x18004806b  mov     [rsp+14F0h+var_14A0], r13
0x180048070  mov     [rbp+13F0h+var_1448], rsi
0x180048074  mov     [rbp+13F0h+var_1440], r12
0x180048078  mov     [rsp+14F0h+var_1488], r13
0x18004807d  xorps   xmm0, xmm0
0x180048080  xor     eax, eax
0x180048082  movups  [rbp+13F0h+var_1468], xmm0
0x180048086  mov     [rbp+13F0h+var_1458], rax
0x18004808a  xorps   xmm1, xmm1
0x18004808d  movups  [rsp+14F0h+var_1480], xmm1
0x180048092  mov     [rbp+13F0h+var_1470], rax
0x180048096  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18004809d  test    rax, rax
0x1800480a0  jz      short loc_1800480AD
0x1800480a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480a7  mov     [rbp+13F0h+var_1450], rax
0x1800480ab  jmp     short loc_1800480B1
0x1800480ad  mov     [rbp+13F0h+var_1450], r13
0x1800480b1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800480b8  test    rax, rax
0x1800480bb  jz      short loc_1800480C7
0x1800480bd  lea     rcx, [rsp+14F0h+var_14D0]
0x1800480c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480c7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800480ce  test    rax, rax
0x1800480d1  jz      short loc_1800480E7
0x1800480d3  mov     r8d, 400h
0x1800480d9  lea     rdx, [rbp+13F0h+var_1430]
0x1800480dd  lea     rcx, [rsp+14F0h+var_14D0]
0x1800480e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480e7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800480ee  test    rax, rax
0x1800480f1  jz      short loc_1800480FD
0x1800480f3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800480f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480fd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180048104  test    rax, rax
0x180048107  jz      short loc_18004811A
0x180048109  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18004810e  jnz     short loc_18004811A
0x180048110  lea     rcx, [rsp+14F0h+var_14D0]
0x180048115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004811a  cmp     [rsp+14F0h+var_14C8], r13d
0x18004811f  jl      short loc_180048133
0x180048121  mov     ecx, 8000FFFFh; this
0x180048126  mov     [rsp+14F0h+var_14C8], ecx
0x18004812a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18004812f  mov     [rsp+14F0h+var_14C4], eax
0x180048133  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18004813a  jnz     short loc_18004815B
0x18004813c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180048143  test    rax, rax
0x180048146  jz      short loc_180048151
0x180048148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004814d  test    al, al
0x18004814f  jmp     short loc_180048159
0x180048151  call    cs:__imp_IsDebuggerPresent
0x180048157  test    eax, eax
0x180048159  jz      short loc_180048162
0x18004815b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180048160  jz      short loc_180048188
0x180048162  mov     rax, cs:g_pfnResultLoggingCallback
0x180048169  test    rax, rax
0x18004816c  jz      short loc_1800481E1
0x18004816e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180048175  jnz     short loc_1800481E1
0x180048177  xor     r8d, r8d
0x18004817a  xor     edx, edx
0x18004817c  lea     rcx, [rsp+14F0h+var_14D0]
0x180048181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048186  jmp     short loc_1800481E1
0x180048188  mov     ebx, 800h
0x18004818d  mov     rax, cs:g_pfnResultLoggingCallback
0x180048194  test    rax, rax
0x180048197  jz      short loc_1800481B6
0x180048199  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800481a0  jnz     short loc_1800481B6
0x1800481a2  mov     r8d, ebx
0x1800481a5  lea     rdx, [rbp+13F0h+OutputString]
0x1800481ac  lea     rcx, [rsp+14F0h+var_14D0]
0x1800481b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800481b6  cmp     [rbp+13F0h+OutputString], r13w
0x1800481be  jnz     short loc_1800481D4
0x1800481c0  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800481c5  mov     rdx, rbx; unsigned __int16 *
0x1800481c8  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800481cf  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800481d4  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800481db  call    cs:__imp_OutputDebugStringW
0x1800481e1  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800481e6  jnz     short loc_1800481F1
0x1800481e8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800481ef  jz      short loc_180048203
0x1800481f1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800481f8  test    rax, rax
0x1800481fb  jz      short loc_180048203
0x1800481fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048202  nop
0x180048203  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180048208  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
