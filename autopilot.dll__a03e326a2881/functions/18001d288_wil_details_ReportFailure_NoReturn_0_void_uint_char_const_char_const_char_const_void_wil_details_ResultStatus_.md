# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18001d288`
- end: `0x18001d534`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001d200`

## callees

- `0x180005374`
- `0x18000d284`
- `0x18000f06c`
- `0x180011658`
- `0x180011e10`
- `0x180012104`
- `0x18001d288`
- `0x1800281e0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d331`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d331`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001d42c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001d42c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001d4c8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001d4c8`

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
      g_pfnResultLoggingCallback(&v20, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0, v16);
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
0x18001d288  mov     [rsp-8+arg_18], rbx
0x18001d28d  push    rbp
0x18001d28e  push    rsi
0x18001d28f  push    rdi
0x18001d290  push    r12
0x18001d292  push    r13
0x18001d294  push    r14
0x18001d296  push    r15
0x18001d298  lea     rbp, [rsp-13C0h]
0x18001d2a0  mov     eax, 14C0h
0x18001d2a5  call    _alloca_probe
0x18001d2aa  sub     rsp, rax
0x18001d2ad  mov     r14, r8
0x18001d2b0  mov     esi, edx
0x18001d2b2  mov     r15, rcx
0x18001d2b5  mov     rdi, [rbp+13F0h+arg_28]
0x18001d2bc  xor     r13d, r13d
0x18001d2bf  cmp     cs:g_pfnThrowPlatformException, r13
0x18001d2c6  setnz   r12b
0x18001d2ca  xor     edx, edx; Val
0x18001d2cc  mov     r8d, 98h; Size
0x18001d2d2  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18001d2d7  call    memset_0
0x18001d2dc  nop
0x18001d2dd  mov     [rbp+13F0h+OutputString], r13w
0x18001d2e5  mov     [rbp+13F0h+var_1430], r13b
0x18001d2e9  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18001d2f0  mov     ecx, [rdx]; this
0x18001d2f2  mov     [rsp+14F0h+var_14C8], ecx
0x18001d2f6  mov     eax, [rdx+4]
0x18001d2f9  mov     [rsp+14F0h+var_14C4], eax
0x18001d2fd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001d302  mov     ebx, eax
0x18001d304  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18001d309  mov     ecx, r13d
0x18001d30c  lea     eax, [r13+8]
0x18001d310  cmp     dword ptr [rdx+8], 1
0x18001d314  cmovz   ecx, eax
0x18001d317  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18001d31b  lea     ecx, [rax-7]
0x18001d31e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001d326  inc     ecx
0x18001d328  mov     [rsp+14F0h+var_14C0], ecx
0x18001d32c  mov     [rsp+14F0h+var_14B8], r13
0x18001d331  call    cs:__imp_GetCurrentThreadId
0x18001d337  mov     [rsp+14F0h+var_14B0], eax
0x18001d33b  mov     [rsp+14F0h+var_1498], r14
0x18001d340  mov     [rsp+14F0h+var_1490], esi
0x18001d344  mov     [rsp+14F0h+var_148C], ebx
0x18001d348  mov     [rsp+14F0h+var_14A8], r13
0x18001d34d  mov     [rsp+14F0h+var_14A0], r13
0x18001d352  mov     [rbp+13F0h+var_1448], rdi
0x18001d356  mov     [rbp+13F0h+var_1440], r15
0x18001d35a  mov     [rsp+14F0h+var_1488], r13
0x18001d35f  xorps   xmm0, xmm0
0x18001d362  xor     eax, eax
0x18001d364  movups  [rbp+13F0h+var_1468], xmm0
0x18001d368  mov     [rbp+13F0h+var_1458], rax
0x18001d36c  xorps   xmm1, xmm1
0x18001d36f  movups  [rsp+14F0h+var_1480], xmm1
0x18001d374  mov     [rbp+13F0h+var_1470], rax
0x18001d378  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001d37f  test    rax, rax
0x18001d382  jz      short loc_18001D38F
0x18001d384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d389  mov     [rbp+13F0h+var_1450], rax
0x18001d38d  jmp     short loc_18001D393
0x18001d38f  mov     [rbp+13F0h+var_1450], r13
0x18001d393  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001d39a  test    rax, rax
0x18001d39d  jz      short loc_18001D3A9
0x18001d39f  lea     rcx, [rsp+14F0h+var_14D0]
0x18001d3a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3a9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001d3b0  test    rax, rax
0x18001d3b3  jz      short loc_18001D3C9
0x18001d3b5  mov     r8d, 400h
0x18001d3bb  lea     rdx, [rbp+13F0h+var_1430]
0x18001d3bf  lea     rcx, [rsp+14F0h+var_14D0]
0x18001d3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3c9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001d3d0  test    rax, rax
0x18001d3d3  jz      short loc_18001D3DF
0x18001d3d5  lea     rcx, [rsp+14F0h+var_14D0]
0x18001d3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3df  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001d3e6  test    rax, rax
0x18001d3e9  jz      short loc_18001D401
0x18001d3eb  test    r12b, r12b
0x18001d3ee  jnz     short loc_18001D401
0x18001d3f0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001d3f5  jnz     short loc_18001D401
0x18001d3f7  lea     rcx, [rsp+14F0h+var_14D0]
0x18001d3fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d401  cmp     [rsp+14F0h+var_14C8], r13d
0x18001d406  jl      short loc_18001D40E
0x18001d408  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001d40e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18001d415  jnz     short loc_18001D436
0x18001d417  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001d41e  test    rax, rax
0x18001d421  jz      short loc_18001D42C
0x18001d423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d428  test    al, al
0x18001d42a  jmp     short loc_18001D434
0x18001d42c  call    cs:__imp_IsDebuggerPresent
0x18001d432  test    eax, eax
0x18001d434  jz      short loc_18001D43F
0x18001d436  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001d43b  mov     bl, 1
0x18001d43d  jz      short loc_18001D442
0x18001d43f  mov     bl, r13b
0x18001d442  test    r12b, r12b
0x18001d445  jnz     short loc_18001D471
0x18001d447  test    bl, bl
0x18001d449  jnz     short loc_18001D471
0x18001d44b  mov     rax, cs:g_pfnResultLoggingCallback
0x18001d452  test    rax, rax
0x18001d455  jz      short loc_18001D4CE
0x18001d457  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18001d45e  jnz     short loc_18001D4CE
0x18001d460  xor     r8d, r8d
0x18001d463  xor     edx, edx
0x18001d465  lea     rcx, [rsp+14F0h+var_14D0]
0x18001d46a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d46f  jmp     short loc_18001D4CE
0x18001d471  mov     edi, 800h
0x18001d476  mov     rax, cs:g_pfnResultLoggingCallback
0x18001d47d  test    rax, rax
0x18001d480  jz      short loc_18001D49F
0x18001d482  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18001d489  jnz     short loc_18001D49F
0x18001d48b  mov     r8d, edi
0x18001d48e  lea     rdx, [rbp+13F0h+OutputString]
0x18001d495  lea     rcx, [rsp+14F0h+var_14D0]
0x18001d49a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d49f  cmp     [rbp+13F0h+OutputString], r13w
0x18001d4a7  jnz     short loc_18001D4BD
0x18001d4a9  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18001d4ae  mov     rdx, rdi; unsigned __int16 *
0x18001d4b1  lea     rcx, [rbp+13F0h+OutputString]; this
0x18001d4b8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001d4bd  test    bl, bl
0x18001d4bf  jz      short loc_18001D4CE
0x18001d4c1  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18001d4c8  call    cs:__imp_OutputDebugStringW
0x18001d4ce  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18001d4d3  jnz     short loc_18001D4DE
0x18001d4d5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18001d4dc  jz      short loc_18001D4F0
0x18001d4de  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001d4e5  test    rax, rax
0x18001d4e8  jz      short loc_18001D4F0
0x18001d4ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4ef  nop
0x18001d4f0  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18001d4f5  jz      short loc_18001D502
0x18001d4f7  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001d4fc  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001d502  test    r12b, r12b
0x18001d505  jz      short loc_18001D51F
0x18001d507  lea     rdx, [rbp+13F0h+OutputString]
0x18001d50e  lea     rcx, [rsp+14F0h+var_14D0]
0x18001d513  mov     rax, cs:g_pfnThrowPlatformException
0x18001d51a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d51f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001d524  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18001d529  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001d52e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
