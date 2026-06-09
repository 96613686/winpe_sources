# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180005ea0`
- end: `0x180006102`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180005c3c`

## callees

- `0x180004998`
- `0x180005ea0`
- `0x1800077f4`
- `0x180007f9c`
- `0x180008700`
- `0x180009790`
- `0x18006b600`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f42`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800060cf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800060cf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006045`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006045`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180005ea0  mov     [rsp-8+arg_18], rbx
0x180005ea5  push    rbp
0x180005ea6  push    rsi
0x180005ea7  push    rdi
0x180005ea8  push    r12
0x180005eaa  push    r13
0x180005eac  push    r14
0x180005eae  push    r15
0x180005eb0  lea     rbp, [rsp-13C0h]
0x180005eb8  mov     eax, 14C0h
0x180005ebd  call    _alloca_probe
0x180005ec2  sub     rsp, rax
0x180005ec5  mov     r15, r8
0x180005ec8  mov     r14d, edx
0x180005ecb  mov     r12, rcx
0x180005ece  mov     rsi, [rbp+13F0h+arg_28]
0x180005ed5  xor     edx, edx; Val
0x180005ed7  mov     r8d, 98h; Size
0x180005edd  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180005ee2  call    memset_0
0x180005ee7  nop
0x180005ee8  xor     r13d, r13d
0x180005eeb  mov     [rbp+13F0h+OutputString], r13w
0x180005ef3  mov     [rbp+13F0h+var_1430], r13b
0x180005ef7  mov     rbx, [rbp+13F0h+arg_30]
0x180005efe  mov     ecx, [rbx]; this
0x180005f00  mov     [rsp+14F0h+var_14C8], ecx
0x180005f04  mov     eax, [rbx+4]
0x180005f07  mov     [rsp+14F0h+var_14C4], eax
0x180005f0b  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005f10  mov     edi, eax
0x180005f12  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180005f1a  mov     ecx, r13d
0x180005f1d  lea     eax, [r13+8]
0x180005f21  cmp     dword ptr [rbx+8], 1
0x180005f25  cmovz   ecx, eax
0x180005f28  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180005f2c  lea     ecx, [rax-7]
0x180005f2f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005f37  inc     ecx
0x180005f39  mov     [rsp+14F0h+var_14C0], ecx
0x180005f3d  mov     [rsp+14F0h+var_14B8], r13
0x180005f42  call    cs:__imp_GetCurrentThreadId
0x180005f48  mov     [rsp+14F0h+var_14B0], eax
0x180005f4c  mov     [rsp+14F0h+var_1498], r15
0x180005f51  mov     [rsp+14F0h+var_1490], r14d
0x180005f56  mov     [rsp+14F0h+var_148C], edi
0x180005f5a  mov     [rsp+14F0h+var_14A8], r13
0x180005f5f  mov     [rsp+14F0h+var_14A0], r13
0x180005f64  mov     [rbp+13F0h+var_1448], rsi
0x180005f68  mov     [rbp+13F0h+var_1440], r12
0x180005f6c  mov     [rsp+14F0h+var_1488], r13
0x180005f71  xorps   xmm0, xmm0
0x180005f74  xor     eax, eax
0x180005f76  movups  [rbp+13F0h+var_1468], xmm0
0x180005f7a  mov     [rbp+13F0h+var_1458], rax
0x180005f7e  xorps   xmm1, xmm1
0x180005f81  movups  [rsp+14F0h+var_1480], xmm1
0x180005f86  mov     [rbp+13F0h+var_1470], rax
0x180005f8a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005f91  test    rax, rax
0x180005f94  jz      short loc_180005FA1
0x180005f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f9b  mov     [rbp+13F0h+var_1450], rax
0x180005f9f  jmp     short loc_180005FA5
0x180005fa1  mov     [rbp+13F0h+var_1450], r13
0x180005fa5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005fac  test    rax, rax
0x180005faf  jz      short loc_180005FBB
0x180005fb1  lea     rcx, [rsp+14F0h+var_14D0]
0x180005fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fbb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005fc2  test    rax, rax
0x180005fc5  jz      short loc_180005FDB
0x180005fc7  mov     r8d, 400h
0x180005fcd  lea     rdx, [rbp+13F0h+var_1430]
0x180005fd1  lea     rcx, [rsp+14F0h+var_14D0]
0x180005fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fdb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005fe2  test    rax, rax
0x180005fe5  jz      short loc_180005FF1
0x180005fe7  lea     rcx, [rsp+14F0h+var_14D0]
0x180005fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ff1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005ff8  test    rax, rax
0x180005ffb  jz      short loc_18000600E
0x180005ffd  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006002  jnz     short loc_18000600E
0x180006004  lea     rcx, [rsp+14F0h+var_14D0]
0x180006009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000600e  cmp     [rsp+14F0h+var_14C8], r13d
0x180006013  jl      short loc_180006027
0x180006015  mov     ecx, 8000FFFFh; this
0x18000601a  mov     [rsp+14F0h+var_14C8], ecx
0x18000601e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006023  mov     [rsp+14F0h+var_14C4], eax
0x180006027  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000602e  jnz     short loc_18000604F
0x180006030  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006037  test    rax, rax
0x18000603a  jz      short loc_180006045
0x18000603c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006041  test    al, al
0x180006043  jmp     short loc_18000604D
0x180006045  call    cs:__imp_IsDebuggerPresent
0x18000604b  test    eax, eax
0x18000604d  jz      short loc_180006056
0x18000604f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006054  jz      short loc_18000607C
0x180006056  mov     rax, cs:g_pfnResultLoggingCallback
0x18000605d  test    rax, rax
0x180006060  jz      short loc_1800060D5
0x180006062  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180006069  jnz     short loc_1800060D5
0x18000606b  xor     r8d, r8d
0x18000606e  xor     edx, edx
0x180006070  lea     rcx, [rsp+14F0h+var_14D0]
0x180006075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000607a  jmp     short loc_1800060D5
0x18000607c  mov     ebx, 800h
0x180006081  mov     rax, cs:g_pfnResultLoggingCallback
0x180006088  test    rax, rax
0x18000608b  jz      short loc_1800060AA
0x18000608d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180006094  jnz     short loc_1800060AA
0x180006096  mov     r8d, ebx
0x180006099  lea     rdx, [rbp+13F0h+OutputString]
0x1800060a0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800060a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060aa  cmp     [rbp+13F0h+OutputString], r13w
0x1800060b2  jnz     short loc_1800060C8
0x1800060b4  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800060b9  mov     rdx, rbx; unsigned __int16 *
0x1800060bc  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800060c3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800060c8  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800060cf  call    cs:__imp_OutputDebugStringW
0x1800060d5  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800060da  jnz     short loc_1800060E5
0x1800060dc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800060e3  jz      short loc_1800060F7
0x1800060e5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800060ec  test    rax, rax
0x1800060ef  jz      short loc_1800060F7
0x1800060f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060f6  nop
0x1800060f7  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800060fc  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
