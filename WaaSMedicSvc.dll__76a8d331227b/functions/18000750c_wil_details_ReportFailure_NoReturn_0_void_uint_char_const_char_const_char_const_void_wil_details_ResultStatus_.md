# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000750c`
- end: `0x1800077d1`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000703c`

## callees

- `0x180002f7c`
- `0x180004714`
- `0x180005604`
- `0x18000639c`
- `0x1800066f0`
- `0x1800067cc`
- `0x18000750c`
- `0x18000bd40`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800075cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800075cd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007765`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007765`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800076c9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800076c9`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  bool v11; // di
  int v12; // r12d
  int v13; // ecx
  __int64 v14; // rdx
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  char v19; // bl
  const struct wil::FailureInfo *v20; // rdx
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+24h] [rbp-DCh]
  int v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v25; // [rsp+30h] [rbp-D0h]
  _WORD *v26; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+60h] [rbp-A0h]
  int v32; // [rsp+64h] [rbp-9Ch]
  __int64 v33; // [rsp+68h] [rbp-98h]
  __int128 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+80h] [rbp-80h]
  __int128 v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  char v41[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v11 = g_pfnThrowPlatformException != 0;
  memset_0(&v21, 0, 0x98u);
  OutputString[0] = 0;
  v41[0] = 0;
  v23 = *a7;
  v24 = a7[1];
  v12 = wil::details::RecordException((wil::details *)(unsigned int)v23, (int)a7);
  v21 = 0;
  v13 = 0;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  v22 = v13;
  v25 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v18 = *a8 == 0, v26 = a8, v18) )
    v26 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v30 = a3;
  v31 = a2;
  v32 = v12;
  v28 = 0;
  v29 = 0;
  v39 = a6;
  v40 = a1;
  v33 = 0;
  v36 = 0;
  v37 = 0;
  v34 = 0;
  v35 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v21);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v21, v41, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v21);
  if ( wil::details::g_pfnOriginateCallback && !v11 && (v22 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v21);
  if ( v23 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v19 = 1, (v22 & 2) != 0) )
  {
    v19 = 0;
  }
  if ( v11 || v19 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v21, v17);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v21, 0, 0);
  }
  if ( ((v22 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v22 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v21, v15);
  if ( v11 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v21, OutputString);
  wil::ThrowResultException((wil *)&v21, v15);
  wil::details::WilFailFast((wil::details *)&v21, v20);
}

```

## disassembly

```asm
0x18000750c  mov     [rsp-8+arg_18], rbx
0x180007511  push    rbp
0x180007512  push    rsi
0x180007513  push    rdi
0x180007514  push    r12
0x180007516  push    r13
0x180007518  push    r14
0x18000751a  push    r15
0x18000751c  lea     rbp, [rsp-13C0h]
0x180007524  mov     eax, 14C0h
0x180007529  call    _alloca_probe
0x18000752e  sub     rsp, rax
0x180007531  mov     r14, r8
0x180007534  mov     esi, edx
0x180007536  mov     rbx, rcx
0x180007539  mov     r15, [rbp+13F0h+arg_28]
0x180007540  xor     r13d, r13d
0x180007543  cmp     cs:g_pfnThrowPlatformException, r13
0x18000754a  setnz   dil
0x18000754e  xor     edx, edx; Val
0x180007550  mov     r8d, 98h; Size
0x180007556  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000755b  call    memset_0
0x180007560  nop
0x180007561  mov     [rbp+13F0h+OutputString], r13w
0x180007569  mov     [rbp+13F0h+var_1430], r13b
0x18000756d  mov     rdx, [rbp+13F0h+arg_30]; int
0x180007574  mov     ecx, [rdx]; this
0x180007576  mov     [rsp+14F0h+var_14C8], ecx
0x18000757a  mov     eax, [rdx+4]
0x18000757d  mov     [rsp+14F0h+var_14C4], eax
0x180007581  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180007586  mov     r12d, eax
0x180007589  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000758e  mov     ecx, r13d
0x180007591  lea     eax, [r13+8]
0x180007595  cmp     dword ptr [rdx+8], 1
0x180007599  cmovz   ecx, eax
0x18000759c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800075a0  lea     ecx, [rax-7]
0x1800075a3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800075ab  inc     ecx
0x1800075ad  mov     [rsp+14F0h+var_14C0], ecx
0x1800075b1  mov     rcx, [rbp+13F0h+arg_38]
0x1800075b8  test    rcx, rcx
0x1800075bb  jz      short loc_1800075C8
0x1800075bd  cmp     [rcx], r13w
0x1800075c1  mov     [rsp+14F0h+var_14B8], rcx
0x1800075c6  jnz     short loc_1800075CD
0x1800075c8  mov     [rsp+14F0h+var_14B8], r13
0x1800075cd  call    cs:__imp_GetCurrentThreadId
0x1800075d3  mov     [rsp+14F0h+var_14B0], eax
0x1800075d7  mov     [rsp+14F0h+var_1498], r14
0x1800075dc  mov     [rsp+14F0h+var_1490], esi
0x1800075e0  mov     [rsp+14F0h+var_148C], r12d
0x1800075e5  mov     [rsp+14F0h+var_14A8], r13
0x1800075ea  mov     [rsp+14F0h+var_14A0], r13
0x1800075ef  mov     [rbp+13F0h+var_1448], r15
0x1800075f3  mov     [rbp+13F0h+var_1440], rbx
0x1800075f7  mov     [rsp+14F0h+var_1488], r13
0x1800075fc  xorps   xmm0, xmm0
0x1800075ff  xor     eax, eax
0x180007601  movups  [rbp+13F0h+var_1468], xmm0
0x180007605  mov     [rbp+13F0h+var_1458], rax
0x180007609  xorps   xmm1, xmm1
0x18000760c  movups  [rsp+14F0h+var_1480], xmm1
0x180007611  mov     [rbp+13F0h+var_1470], rax
0x180007615  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000761c  test    rax, rax
0x18000761f  jz      short loc_18000762C
0x180007621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007626  mov     [rbp+13F0h+var_1450], rax
0x18000762a  jmp     short loc_180007630
0x18000762c  mov     [rbp+13F0h+var_1450], r13
0x180007630  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007637  test    rax, rax
0x18000763a  jz      short loc_180007646
0x18000763c  lea     rcx, [rsp+14F0h+var_14D0]
0x180007641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007646  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000764d  test    rax, rax
0x180007650  jz      short loc_180007666
0x180007652  mov     r8d, 400h
0x180007658  lea     rdx, [rbp+13F0h+var_1430]
0x18000765c  lea     rcx, [rsp+14F0h+var_14D0]
0x180007661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007666  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000766d  test    rax, rax
0x180007670  jz      short loc_18000767C
0x180007672  lea     rcx, [rsp+14F0h+var_14D0]
0x180007677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000767c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007683  test    rax, rax
0x180007686  jz      short loc_18000769E
0x180007688  test    dil, dil
0x18000768b  jnz     short loc_18000769E
0x18000768d  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007692  jnz     short loc_18000769E
0x180007694  lea     rcx, [rsp+14F0h+var_14D0]
0x180007699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000769e  cmp     [rsp+14F0h+var_14C8], r13d
0x1800076a3  jl      short loc_1800076AB
0x1800076a5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800076ab  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800076b2  jnz     short loc_1800076D3
0x1800076b4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800076bb  test    rax, rax
0x1800076be  jz      short loc_1800076C9
0x1800076c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076c5  test    al, al
0x1800076c7  jmp     short loc_1800076D1
0x1800076c9  call    cs:__imp_IsDebuggerPresent
0x1800076cf  test    eax, eax
0x1800076d1  jz      short loc_1800076DC
0x1800076d3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800076d8  mov     bl, 1
0x1800076da  jz      short loc_1800076DF
0x1800076dc  mov     bl, r13b
0x1800076df  test    dil, dil
0x1800076e2  jnz     short loc_18000770E
0x1800076e4  test    bl, bl
0x1800076e6  jnz     short loc_18000770E
0x1800076e8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800076ef  test    rax, rax
0x1800076f2  jz      short loc_18000776B
0x1800076f4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800076fb  jnz     short loc_18000776B
0x1800076fd  xor     r8d, r8d
0x180007700  xor     edx, edx
0x180007702  lea     rcx, [rsp+14F0h+var_14D0]
0x180007707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000770c  jmp     short loc_18000776B
0x18000770e  mov     esi, 800h
0x180007713  mov     rax, cs:g_pfnResultLoggingCallback
0x18000771a  test    rax, rax
0x18000771d  jz      short loc_18000773C
0x18000771f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180007726  jnz     short loc_18000773C
0x180007728  mov     r8d, esi
0x18000772b  lea     rdx, [rbp+13F0h+OutputString]
0x180007732  lea     rcx, [rsp+14F0h+var_14D0]
0x180007737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000773c  cmp     [rbp+13F0h+OutputString], r13w
0x180007744  jnz     short loc_18000775A
0x180007746  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000774b  mov     rdx, rsi; unsigned __int16 *
0x18000774e  lea     rcx, [rbp+13F0h+OutputString]; this
0x180007755  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000775a  test    bl, bl
0x18000775c  jz      short loc_18000776B
0x18000775e  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180007765  call    cs:__imp_OutputDebugStringW
0x18000776b  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180007770  jnz     short loc_18000777B
0x180007772  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180007779  jz      short loc_18000778D
0x18000777b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007782  test    rax, rax
0x180007785  jz      short loc_18000778D
0x180007787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000778c  nop
0x18000778d  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180007792  jz      short loc_18000779F
0x180007794  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180007799  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000779f  test    dil, dil
0x1800077a2  jz      short loc_1800077BC
0x1800077a4  lea     rdx, [rbp+13F0h+OutputString]
0x1800077ab  lea     rcx, [rsp+14F0h+var_14D0]
0x1800077b0  mov     rax, cs:g_pfnThrowPlatformException
0x1800077b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077bc  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800077c1  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x1800077c6  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800077cb  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
