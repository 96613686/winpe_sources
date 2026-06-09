# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18001112c`
- end: `0x1800113ea`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `702`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180010f54`

## callees

- `0x180002c48`
- `0x180003df4`
- `0x180004564`
- `0x1800046f4`
- `0x18000478c`
- `0x180004924`
- `0x18001112c`
- `0x180036130`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800111d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800111d5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180011378`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180011378`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800112d6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800112d6`

## pseudocode

```c
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
0x18001112c  mov     [rsp-8+arg_18], rbx
0x180011131  push    rbp
0x180011132  push    rsi
0x180011133  push    rdi
0x180011134  push    r12
0x180011136  push    r13
0x180011138  push    r14
0x18001113a  push    r15
0x18001113c  lea     rbp, [rsp-13C0h]
0x180011144  mov     eax, 14C0h
0x180011149  call    _alloca_probe
0x18001114e  sub     rsp, rax
0x180011151  mov     r14, r8
0x180011154  mov     esi, edx
0x180011156  mov     r15, rcx
0x180011159  mov     rdi, [rbp+13F0h+arg_28]
0x180011160  xor     r13d, r13d
0x180011163  cmp     cs:g_pfnThrowPlatformException, r13
0x18001116a  setnz   r12b
0x18001116e  xor     edx, edx; Val
0x180011170  mov     r8d, 98h; Size
0x180011176  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18001117b  call    memset_0
0x180011180  nop
0x180011181  mov     [rbp+13F0h+OutputString], r13w
0x180011189  mov     [rbp+13F0h+var_1430], r13b
0x18001118d  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180011194  mov     ecx, [rdx]; this
0x180011196  mov     [rsp+14F0h+var_14C8], ecx
0x18001119a  mov     eax, [rdx+4]
0x18001119d  mov     [rsp+14F0h+var_14C4], eax
0x1800111a1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800111a6  mov     ebx, eax
0x1800111a8  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x1800111ad  mov     ecx, r13d
0x1800111b0  lea     eax, [r13+8]
0x1800111b4  cmp     dword ptr [rdx+8], 1
0x1800111b8  cmovz   ecx, eax
0x1800111bb  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800111bf  lea     ecx, [rax-7]
0x1800111c2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800111ca  inc     ecx
0x1800111cc  mov     [rsp+14F0h+var_14C0], ecx
0x1800111d0  mov     [rsp+14F0h+var_14B8], r13
0x1800111d5  call    cs:__imp_GetCurrentThreadId
0x1800111dc  nop     dword ptr [rax+rax+00h]
0x1800111e1  mov     [rsp+14F0h+var_14B0], eax
0x1800111e5  mov     [rsp+14F0h+var_1498], r14
0x1800111ea  mov     [rsp+14F0h+var_1490], esi
0x1800111ee  mov     [rsp+14F0h+var_148C], ebx
0x1800111f2  mov     [rsp+14F0h+var_14A8], r13
0x1800111f7  mov     [rsp+14F0h+var_14A0], r13
0x1800111fc  mov     [rbp+13F0h+var_1448], rdi
0x180011200  mov     [rbp+13F0h+var_1440], r15
0x180011204  mov     [rsp+14F0h+var_1488], r13
0x180011209  xorps   xmm0, xmm0
0x18001120c  xor     eax, eax
0x18001120e  movups  [rbp+13F0h+var_1468], xmm0
0x180011212  mov     [rbp+13F0h+var_1458], rax
0x180011216  xorps   xmm1, xmm1
0x180011219  movups  [rsp+14F0h+var_1480], xmm1
0x18001121e  mov     [rbp+13F0h+var_1470], rax
0x180011222  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180011229  test    rax, rax
0x18001122c  jz      short loc_180011239
0x18001122e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011233  mov     [rbp+13F0h+var_1450], rax
0x180011237  jmp     short loc_18001123D
0x180011239  mov     [rbp+13F0h+var_1450], r13
0x18001123d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180011244  test    rax, rax
0x180011247  jz      short loc_180011253
0x180011249  lea     rcx, [rsp+14F0h+var_14D0]
0x18001124e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011253  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001125a  test    rax, rax
0x18001125d  jz      short loc_180011273
0x18001125f  mov     r8d, 400h
0x180011265  lea     rdx, [rbp+13F0h+var_1430]
0x180011269  lea     rcx, [rsp+14F0h+var_14D0]
0x18001126e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011273  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001127a  test    rax, rax
0x18001127d  jz      short loc_180011289
0x18001127f  lea     rcx, [rsp+14F0h+var_14D0]
0x180011284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011289  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011290  test    rax, rax
0x180011293  jz      short loc_1800112AB
0x180011295  test    r12b, r12b
0x180011298  jnz     short loc_1800112AB
0x18001129a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001129f  jnz     short loc_1800112AB
0x1800112a1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800112a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112ab  cmp     [rsp+14F0h+var_14C8], r13d
0x1800112b0  jl      short loc_1800112B8
0x1800112b2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800112b8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800112bf  jnz     short loc_1800112E6
0x1800112c1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800112c8  test    rax, rax
0x1800112cb  jz      short loc_1800112D6
0x1800112cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112d2  test    al, al
0x1800112d4  jmp     short loc_1800112E4
0x1800112d6  call    cs:__imp_IsDebuggerPresent
0x1800112dd  nop     dword ptr [rax+rax+00h]
0x1800112e2  test    eax, eax
0x1800112e4  jz      short loc_1800112EF
0x1800112e6  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800112eb  mov     bl, 1
0x1800112ed  jz      short loc_1800112F2
0x1800112ef  mov     bl, r13b
0x1800112f2  test    r12b, r12b
0x1800112f5  jnz     short loc_180011321
0x1800112f7  test    bl, bl
0x1800112f9  jnz     short loc_180011321
0x1800112fb  mov     rax, cs:g_pfnResultLoggingCallback
0x180011302  test    rax, rax
0x180011305  jz      short loc_180011384
0x180011307  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18001130e  jnz     short loc_180011384
0x180011310  xor     r8d, r8d
0x180011313  xor     edx, edx
0x180011315  lea     rcx, [rsp+14F0h+var_14D0]
0x18001131a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001131f  jmp     short loc_180011384
0x180011321  mov     edi, 800h
0x180011326  mov     rax, cs:g_pfnResultLoggingCallback
0x18001132d  test    rax, rax
0x180011330  jz      short loc_18001134F
0x180011332  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180011339  jnz     short loc_18001134F
0x18001133b  mov     r8d, edi
0x18001133e  lea     rdx, [rbp+13F0h+OutputString]
0x180011345  lea     rcx, [rsp+14F0h+var_14D0]
0x18001134a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001134f  cmp     [rbp+13F0h+OutputString], r13w
0x180011357  jnz     short loc_18001136D
0x180011359  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18001135e  mov     rdx, rdi; unsigned __int16 *
0x180011361  lea     rcx, [rbp+13F0h+OutputString]; this
0x180011368  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001136d  test    bl, bl
0x18001136f  jz      short loc_180011384
0x180011371  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180011378  call    cs:__imp_OutputDebugStringW
0x18001137f  nop     dword ptr [rax+rax+00h]
0x180011384  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180011389  jnz     short loc_180011394
0x18001138b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180011392  jz      short loc_1800113A6
0x180011394  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001139b  test    rax, rax
0x18001139e  jz      short loc_1800113A6
0x1800113a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113a5  nop
0x1800113a6  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800113ab  jz      short loc_1800113B8
0x1800113ad  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800113b2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800113b8  test    r12b, r12b
0x1800113bb  jz      short loc_1800113D5
0x1800113bd  lea     rdx, [rbp+13F0h+OutputString]
0x1800113c4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800113c9  mov     rax, cs:g_pfnThrowPlatformException
0x1800113d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113d5  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800113da  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x1800113df  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800113e4  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
