# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800074fc`
- end: `0x1800077a7`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `683`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000745c`

## callees

- `0x180002fc4`
- `0x180004c44`
- `0x180005d08`
- `0x180006c90`
- `0x180006fc0`
- `0x180007148`
- `0x1800074fc`
- `0x180011040`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007599`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007599`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000773b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000773b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000769f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000769f`

## string_xrefs

- `0x1800075a3`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v8; // r14
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  char v16; // bl
  const struct wil::FailureInfo *v17; // rdx
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  __int64 v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  const char *v27; // [rsp+58h] [rbp-A8h]
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

  v8 = g_pfnThrowPlatformException != 0;
  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v9 = wil::details::RecordException((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 0;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v19 = v10;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h";
  v28 = 7368;
  v29 = v9;
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
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && !v8 && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v16 = 1, (v19 & 2) != 0) )
  {
    v16 = 0;
  }
  if ( v8 || v16 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v14);
    if ( v16 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v12);
  if ( v8 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v18, OutputString);
  wil::ThrowResultException((wil *)&v18, v12);
  wil::details::WilFailFast((wil::details *)&v18, v17);
}

```

## disassembly

```asm
0x1800074fc  push    rbp
0x1800074fe  push    rbx
0x1800074ff  push    rsi
0x180007500  push    rdi
0x180007501  push    r14
0x180007503  push    r15
0x180007505  lea     rbp, [rsp-13C8h]
0x18000750d  mov     eax, 14C8h
0x180007512  call    _alloca_probe
0x180007517  sub     rsp, rax
0x18000751a  mov     rsi, rcx
0x18000751d  mov     rdi, [rbp+13F0h+arg_28]
0x180007524  xor     r15d, r15d
0x180007527  cmp     cs:g_pfnThrowPlatformException, r15
0x18000752e  setnz   r14b
0x180007532  xor     edx, edx; Val
0x180007534  mov     r8d, 98h; Size
0x18000753a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000753f  call    memset_0
0x180007544  nop
0x180007545  mov     [rbp+13F0h+OutputString], r15w
0x18000754d  mov     [rbp+13F0h+var_1430], r15b
0x180007551  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180007558  mov     ecx, [rdx]; this
0x18000755a  mov     [rsp+14F0h+var_14C8], ecx
0x18000755e  mov     eax, [rdx+4]
0x180007561  mov     [rsp+14F0h+var_14C4], eax
0x180007565  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000756a  mov     ebx, eax
0x18000756c  mov     dword ptr [rsp+14F0h+var_14D0], r15d
0x180007571  mov     ecx, r15d
0x180007574  lea     eax, [r15+8]
0x180007578  cmp     dword ptr [rdx+8], 1
0x18000757c  cmovz   ecx, eax
0x18000757f  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180007583  lea     ecx, [rax-7]
0x180007586  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000758e  inc     ecx
0x180007590  mov     [rsp+14F0h+var_14C0], ecx
0x180007594  mov     [rsp+14F0h+var_14B8], r15
0x180007599  call    cs:__imp_GetCurrentThreadId
0x18000759f  mov     [rsp+14F0h+var_14B0], eax
0x1800075a3  lea     rax, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800075aa  mov     [rsp+14F0h+var_1498], rax
0x1800075af  mov     [rsp+14F0h+var_1490], 1CC8h
0x1800075b7  mov     [rsp+14F0h+var_148C], ebx
0x1800075bb  mov     [rsp+14F0h+var_14A8], r15
0x1800075c0  mov     [rsp+14F0h+var_14A0], r15
0x1800075c5  mov     [rbp+13F0h+var_1448], rdi
0x1800075c9  mov     [rbp+13F0h+var_1440], rsi
0x1800075cd  mov     [rsp+14F0h+var_1488], r15
0x1800075d2  xorps   xmm0, xmm0
0x1800075d5  xor     eax, eax
0x1800075d7  movups  [rbp+13F0h+var_1468], xmm0
0x1800075db  mov     [rbp+13F0h+var_1458], rax
0x1800075df  xorps   xmm1, xmm1
0x1800075e2  movups  [rsp+14F0h+var_1480], xmm1
0x1800075e7  mov     [rbp+13F0h+var_1470], rax
0x1800075eb  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800075f2  test    rax, rax
0x1800075f5  jz      short loc_180007602
0x1800075f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075fc  mov     [rbp+13F0h+var_1450], rax
0x180007600  jmp     short loc_180007606
0x180007602  mov     [rbp+13F0h+var_1450], r15
0x180007606  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000760d  test    rax, rax
0x180007610  jz      short loc_18000761C
0x180007612  lea     rcx, [rsp+14F0h+var_14D0]
0x180007617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000761c  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007623  test    rax, rax
0x180007626  jz      short loc_18000763C
0x180007628  mov     r8d, 400h
0x18000762e  lea     rdx, [rbp+13F0h+var_1430]
0x180007632  lea     rcx, [rsp+14F0h+var_14D0]
0x180007637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000763c  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007643  test    rax, rax
0x180007646  jz      short loc_180007652
0x180007648  lea     rcx, [rsp+14F0h+var_14D0]
0x18000764d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007652  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007659  test    rax, rax
0x18000765c  jz      short loc_180007674
0x18000765e  test    r14b, r14b
0x180007661  jnz     short loc_180007674
0x180007663  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007668  jnz     short loc_180007674
0x18000766a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000766f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007674  cmp     [rsp+14F0h+var_14C8], r15d
0x180007679  jl      short loc_180007681
0x18000767b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007681  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180007688  jnz     short loc_1800076A9
0x18000768a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007691  test    rax, rax
0x180007694  jz      short loc_18000769F
0x180007696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000769b  test    al, al
0x18000769d  jmp     short loc_1800076A7
0x18000769f  call    cs:__imp_IsDebuggerPresent
0x1800076a5  test    eax, eax
0x1800076a7  jz      short loc_1800076B2
0x1800076a9  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800076ae  mov     bl, 1
0x1800076b0  jz      short loc_1800076B5
0x1800076b2  mov     bl, r15b
0x1800076b5  test    r14b, r14b
0x1800076b8  jnz     short loc_1800076E4
0x1800076ba  test    bl, bl
0x1800076bc  jnz     short loc_1800076E4
0x1800076be  mov     rax, cs:g_pfnResultLoggingCallback
0x1800076c5  test    rax, rax
0x1800076c8  jz      short loc_180007741
0x1800076ca  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800076d1  jnz     short loc_180007741
0x1800076d3  xor     r8d, r8d
0x1800076d6  xor     edx, edx
0x1800076d8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800076dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076e2  jmp     short loc_180007741
0x1800076e4  mov     edi, 800h
0x1800076e9  mov     rax, cs:g_pfnResultLoggingCallback
0x1800076f0  test    rax, rax
0x1800076f3  jz      short loc_180007712
0x1800076f5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800076fc  jnz     short loc_180007712
0x1800076fe  mov     r8d, edi
0x180007701  lea     rdx, [rbp+13F0h+OutputString]
0x180007708  lea     rcx, [rsp+14F0h+var_14D0]
0x18000770d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007712  cmp     [rbp+13F0h+OutputString], r15w
0x18000771a  jnz     short loc_180007730
0x18000771c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180007721  mov     rdx, rdi; unsigned __int16 *
0x180007724  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000772b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007730  test    bl, bl
0x180007732  jz      short loc_180007741
0x180007734  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000773b  call    cs:__imp_OutputDebugStringW
0x180007741  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180007746  jnz     short loc_180007751
0x180007748  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000774f  jz      short loc_180007763
0x180007751  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007758  test    rax, rax
0x18000775b  jz      short loc_180007763
0x18000775d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007762  nop
0x180007763  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180007768  jz      short loc_180007775
0x18000776a  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000776f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180007775  test    r14b, r14b
0x180007778  jz      short loc_180007792
0x18000777a  lea     rdx, [rbp+13F0h+OutputString]
0x180007781  lea     rcx, [rsp+14F0h+var_14D0]
0x180007786  mov     rax, cs:g_pfnThrowPlatformException
0x18000778d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007792  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180007797  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000779c  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800077a1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
