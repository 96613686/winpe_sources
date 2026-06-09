# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800085c0`
- end: `0x18000886c`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000847c`

## callees

- `0x180002db8`
- `0x1800054d4`
- `0x180006750`
- `0x180007558`
- `0x1800078c0`
- `0x180007a48`
- `0x1800085c0`
- `0x180056f80`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008669`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008669`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008800`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008800`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008764`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008764`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v10; // r12
  int v11; // ebx
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  char v18; // bl
  const struct wil::FailureInfo *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
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

  v10 = g_pfnThrowPlatformException != 0;
  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v11 = wil::details::RecordException((wil::details *)(unsigned int)v22, (int)a7);
  v20 = 0;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v21 = v12;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v11;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && !v10 && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v18 = 1, (v21 & 2) != 0) )
  {
    v18 = 0;
  }
  if ( v10 || v18 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v14);
  if ( v10 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v20, OutputString);
  wil::ThrowResultException((wil *)&v20, v14);
  wil::details::WilFailFast((wil::details *)&v20, v19);
}

```

## disassembly

```asm
0x1800085c0  mov     [rsp-8+arg_18], rbx
0x1800085c5  push    rbp
0x1800085c6  push    rsi
0x1800085c7  push    rdi
0x1800085c8  push    r12
0x1800085ca  push    r13
0x1800085cc  push    r14
0x1800085ce  push    r15
0x1800085d0  lea     rbp, [rsp-13C0h]
0x1800085d8  mov     eax, 14C0h
0x1800085dd  call    _alloca_probe
0x1800085e2  sub     rsp, rax
0x1800085e5  mov     r14, r8
0x1800085e8  mov     esi, edx
0x1800085ea  mov     r15, rcx
0x1800085ed  mov     rdi, [rbp+13F0h+arg_28]
0x1800085f4  xor     r13d, r13d
0x1800085f7  cmp     cs:g_pfnThrowPlatformException, r13
0x1800085fe  setnz   r12b
0x180008602  xor     edx, edx; Val
0x180008604  mov     r8d, 98h; Size
0x18000860a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000860f  call    memset_0
0x180008614  nop
0x180008615  mov     [rbp+13F0h+OutputString], r13w
0x18000861d  mov     [rbp+13F0h+var_1430], r13b
0x180008621  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180008628  mov     ecx, [rdx]; this
0x18000862a  mov     [rsp+14F0h+var_14C8], ecx
0x18000862e  mov     eax, [rdx+4]
0x180008631  mov     [rsp+14F0h+var_14C4], eax
0x180008635  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000863a  mov     ebx, eax
0x18000863c  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180008641  mov     ecx, r13d
0x180008644  lea     eax, [r13+8]
0x180008648  cmp     dword ptr [rdx+8], 1
0x18000864c  cmovz   ecx, eax
0x18000864f  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180008653  lea     ecx, [rax-7]
0x180008656  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000865e  inc     ecx
0x180008660  mov     [rsp+14F0h+var_14C0], ecx
0x180008664  mov     [rsp+14F0h+var_14B8], r13
0x180008669  call    cs:__imp_GetCurrentThreadId
0x18000866f  mov     [rsp+14F0h+var_14B0], eax
0x180008673  mov     [rsp+14F0h+var_1498], r14
0x180008678  mov     [rsp+14F0h+var_1490], esi
0x18000867c  mov     [rsp+14F0h+var_148C], ebx
0x180008680  mov     [rsp+14F0h+var_14A8], r13
0x180008685  mov     [rsp+14F0h+var_14A0], r13
0x18000868a  mov     [rbp+13F0h+var_1448], rdi
0x18000868e  mov     [rbp+13F0h+var_1440], r15
0x180008692  mov     [rsp+14F0h+var_1488], r13
0x180008697  xorps   xmm0, xmm0
0x18000869a  xor     eax, eax
0x18000869c  movups  [rbp+13F0h+var_1468], xmm0
0x1800086a0  mov     [rbp+13F0h+var_1458], rax
0x1800086a4  xorps   xmm1, xmm1
0x1800086a7  movups  [rsp+14F0h+var_1480], xmm1
0x1800086ac  mov     [rbp+13F0h+var_1470], rax
0x1800086b0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800086b7  test    rax, rax
0x1800086ba  jz      short loc_1800086C7
0x1800086bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086c1  mov     [rbp+13F0h+var_1450], rax
0x1800086c5  jmp     short loc_1800086CB
0x1800086c7  mov     [rbp+13F0h+var_1450], r13
0x1800086cb  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800086d2  test    rax, rax
0x1800086d5  jz      short loc_1800086E1
0x1800086d7  lea     rcx, [rsp+14F0h+var_14D0]
0x1800086dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086e1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800086e8  test    rax, rax
0x1800086eb  jz      short loc_180008701
0x1800086ed  mov     r8d, 400h
0x1800086f3  lea     rdx, [rbp+13F0h+var_1430]
0x1800086f7  lea     rcx, [rsp+14F0h+var_14D0]
0x1800086fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008701  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008708  test    rax, rax
0x18000870b  jz      short loc_180008717
0x18000870d  lea     rcx, [rsp+14F0h+var_14D0]
0x180008712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008717  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000871e  test    rax, rax
0x180008721  jz      short loc_180008739
0x180008723  test    r12b, r12b
0x180008726  jnz     short loc_180008739
0x180008728  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000872d  jnz     short loc_180008739
0x18000872f  lea     rcx, [rsp+14F0h+var_14D0]
0x180008734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008739  cmp     [rsp+14F0h+var_14C8], r13d
0x18000873e  jl      short loc_180008746
0x180008740  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008746  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000874d  jnz     short loc_18000876E
0x18000874f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008756  test    rax, rax
0x180008759  jz      short loc_180008764
0x18000875b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008760  test    al, al
0x180008762  jmp     short loc_18000876C
0x180008764  call    cs:__imp_IsDebuggerPresent
0x18000876a  test    eax, eax
0x18000876c  jz      short loc_180008777
0x18000876e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180008773  mov     bl, 1
0x180008775  jz      short loc_18000877A
0x180008777  mov     bl, r13b
0x18000877a  test    r12b, r12b
0x18000877d  jnz     short loc_1800087A9
0x18000877f  test    bl, bl
0x180008781  jnz     short loc_1800087A9
0x180008783  mov     rax, cs:g_pfnResultLoggingCallback
0x18000878a  test    rax, rax
0x18000878d  jz      short loc_180008806
0x18000878f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180008796  jnz     short loc_180008806
0x180008798  xor     r8d, r8d
0x18000879b  xor     edx, edx
0x18000879d  lea     rcx, [rsp+14F0h+var_14D0]
0x1800087a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087a7  jmp     short loc_180008806
0x1800087a9  mov     edi, 800h
0x1800087ae  mov     rax, cs:g_pfnResultLoggingCallback
0x1800087b5  test    rax, rax
0x1800087b8  jz      short loc_1800087D7
0x1800087ba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800087c1  jnz     short loc_1800087D7
0x1800087c3  mov     r8d, edi
0x1800087c6  lea     rdx, [rbp+13F0h+OutputString]
0x1800087cd  lea     rcx, [rsp+14F0h+var_14D0]
0x1800087d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087d7  cmp     [rbp+13F0h+OutputString], r13w
0x1800087df  jnz     short loc_1800087F5
0x1800087e1  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800087e6  mov     rdx, rdi; unsigned __int16 *
0x1800087e9  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800087f0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800087f5  test    bl, bl
0x1800087f7  jz      short loc_180008806
0x1800087f9  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180008800  call    cs:__imp_OutputDebugStringW
0x180008806  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000880b  jnz     short loc_180008816
0x18000880d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180008814  jz      short loc_180008828
0x180008816  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000881d  test    rax, rax
0x180008820  jz      short loc_180008828
0x180008822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008827  nop
0x180008828  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000882d  jz      short loc_18000883A
0x18000882f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180008834  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000883a  test    r12b, r12b
0x18000883d  jz      short loc_180008857
0x18000883f  lea     rdx, [rbp+13F0h+OutputString]
0x180008846  lea     rcx, [rsp+14F0h+var_14D0]
0x18000884b  mov     rax, cs:g_pfnThrowPlatformException
0x180008852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008857  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000885c  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180008861  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180008866  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
