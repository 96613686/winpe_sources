# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800166e4`
- end: `0x180016990`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180016380`

## callees

- `0x18000316c`
- `0x18000f984`
- `0x180010874`
- `0x180011688`
- `0x180011a10`
- `0x180011aec`
- `0x1800166e4`
- `0x18004bab0`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001678d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001678d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180016924`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180016924`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180016888`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180016888`

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
0x1800166e4  mov     [rsp-8+arg_18], rbx
0x1800166e9  push    rbp
0x1800166ea  push    rsi
0x1800166eb  push    rdi
0x1800166ec  push    r12
0x1800166ee  push    r13
0x1800166f0  push    r14
0x1800166f2  push    r15
0x1800166f4  lea     rbp, [rsp-13C0h]
0x1800166fc  mov     eax, 14C0h
0x180016701  call    _alloca_probe
0x180016706  sub     rsp, rax
0x180016709  mov     r14, r8
0x18001670c  mov     esi, edx
0x18001670e  mov     r15, rcx
0x180016711  mov     rdi, [rbp+13F0h+arg_28]
0x180016718  xor     r13d, r13d
0x18001671b  cmp     cs:g_pfnThrowPlatformException, r13
0x180016722  setnz   r12b
0x180016726  xor     edx, edx; Val
0x180016728  mov     r8d, 98h; Size
0x18001672e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180016733  call    memset_0
0x180016738  nop
0x180016739  mov     [rbp+13F0h+OutputString], r13w
0x180016741  mov     [rbp+13F0h+var_1430], r13b
0x180016745  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18001674c  mov     ecx, [rdx]; this
0x18001674e  mov     [rsp+14F0h+var_14C8], ecx
0x180016752  mov     eax, [rdx+4]
0x180016755  mov     [rsp+14F0h+var_14C4], eax
0x180016759  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001675e  mov     ebx, eax
0x180016760  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180016765  mov     ecx, r13d
0x180016768  lea     eax, [r13+8]
0x18001676c  cmp     dword ptr [rdx+8], 1
0x180016770  cmovz   ecx, eax
0x180016773  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180016777  lea     ecx, [rax-7]
0x18001677a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180016782  inc     ecx
0x180016784  mov     [rsp+14F0h+var_14C0], ecx
0x180016788  mov     [rsp+14F0h+var_14B8], r13
0x18001678d  call    cs:__imp_GetCurrentThreadId
0x180016793  mov     [rsp+14F0h+var_14B0], eax
0x180016797  mov     [rsp+14F0h+var_1498], r14
0x18001679c  mov     [rsp+14F0h+var_1490], esi
0x1800167a0  mov     [rsp+14F0h+var_148C], ebx
0x1800167a4  mov     [rsp+14F0h+var_14A8], r13
0x1800167a9  mov     [rsp+14F0h+var_14A0], r13
0x1800167ae  mov     [rbp+13F0h+var_1448], rdi
0x1800167b2  mov     [rbp+13F0h+var_1440], r15
0x1800167b6  mov     [rsp+14F0h+var_1488], r13
0x1800167bb  xorps   xmm0, xmm0
0x1800167be  xor     eax, eax
0x1800167c0  movups  [rbp+13F0h+var_1468], xmm0
0x1800167c4  mov     [rbp+13F0h+var_1458], rax
0x1800167c8  xorps   xmm1, xmm1
0x1800167cb  movups  [rsp+14F0h+var_1480], xmm1
0x1800167d0  mov     [rbp+13F0h+var_1470], rax
0x1800167d4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800167db  test    rax, rax
0x1800167de  jz      short loc_1800167EB
0x1800167e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167e5  mov     [rbp+13F0h+var_1450], rax
0x1800167e9  jmp     short loc_1800167EF
0x1800167eb  mov     [rbp+13F0h+var_1450], r13
0x1800167ef  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800167f6  test    rax, rax
0x1800167f9  jz      short loc_180016805
0x1800167fb  lea     rcx, [rsp+14F0h+var_14D0]
0x180016800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016805  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001680c  test    rax, rax
0x18001680f  jz      short loc_180016825
0x180016811  mov     r8d, 400h
0x180016817  lea     rdx, [rbp+13F0h+var_1430]
0x18001681b  lea     rcx, [rsp+14F0h+var_14D0]
0x180016820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016825  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001682c  test    rax, rax
0x18001682f  jz      short loc_18001683B
0x180016831  lea     rcx, [rsp+14F0h+var_14D0]
0x180016836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001683b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180016842  test    rax, rax
0x180016845  jz      short loc_18001685D
0x180016847  test    r12b, r12b
0x18001684a  jnz     short loc_18001685D
0x18001684c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180016851  jnz     short loc_18001685D
0x180016853  lea     rcx, [rsp+14F0h+var_14D0]
0x180016858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001685d  cmp     [rsp+14F0h+var_14C8], r13d
0x180016862  jl      short loc_18001686A
0x180016864  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001686a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180016871  jnz     short loc_180016892
0x180016873  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001687a  test    rax, rax
0x18001687d  jz      short loc_180016888
0x18001687f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016884  test    al, al
0x180016886  jmp     short loc_180016890
0x180016888  call    cs:__imp_IsDebuggerPresent
0x18001688e  test    eax, eax
0x180016890  jz      short loc_18001689B
0x180016892  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180016897  mov     bl, 1
0x180016899  jz      short loc_18001689E
0x18001689b  mov     bl, r13b
0x18001689e  test    r12b, r12b
0x1800168a1  jnz     short loc_1800168CD
0x1800168a3  test    bl, bl
0x1800168a5  jnz     short loc_1800168CD
0x1800168a7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800168ae  test    rax, rax
0x1800168b1  jz      short loc_18001692A
0x1800168b3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800168ba  jnz     short loc_18001692A
0x1800168bc  xor     r8d, r8d
0x1800168bf  xor     edx, edx
0x1800168c1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800168c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168cb  jmp     short loc_18001692A
0x1800168cd  mov     edi, 800h
0x1800168d2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800168d9  test    rax, rax
0x1800168dc  jz      short loc_1800168FB
0x1800168de  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800168e5  jnz     short loc_1800168FB
0x1800168e7  mov     r8d, edi
0x1800168ea  lea     rdx, [rbp+13F0h+OutputString]
0x1800168f1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800168f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168fb  cmp     [rbp+13F0h+OutputString], r13w
0x180016903  jnz     short loc_180016919
0x180016905  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18001690a  mov     rdx, rdi; unsigned __int16 *
0x18001690d  lea     rcx, [rbp+13F0h+OutputString]; this
0x180016914  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180016919  test    bl, bl
0x18001691b  jz      short loc_18001692A
0x18001691d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180016924  call    cs:__imp_OutputDebugStringW
0x18001692a  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18001692f  jnz     short loc_18001693A
0x180016931  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180016938  jz      short loc_18001694C
0x18001693a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180016941  test    rax, rax
0x180016944  jz      short loc_18001694C
0x180016946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001694b  nop
0x18001694c  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180016951  jz      short loc_18001695E
0x180016953  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180016958  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001695e  test    r12b, r12b
0x180016961  jz      short loc_18001697B
0x180016963  lea     rdx, [rbp+13F0h+OutputString]
0x18001696a  lea     rcx, [rsp+14F0h+var_14D0]
0x18001696f  mov     rax, cs:g_pfnThrowPlatformException
0x180016976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001697b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180016980  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180016985  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001698a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
