# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x14000d300`
- end: `0x14000d5b9`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000cdf4`

## callees

- `0x140004870`
- `0x1400057f8`
- `0x14000d300`
- `0x14000efd0`
- `0x140010e04`
- `0x140012ac0`
- `0x140012d64`
- `0x1401b0be0`
- `0x1401b9010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000d3c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000d3c6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000d551`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000d551`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000d4c1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000d4c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
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
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x14000d300  push    rbp
0x14000d302  push    rbx
0x14000d303  push    rsi
0x14000d304  push    rdi
0x14000d305  push    r12
0x14000d307  push    r14
0x14000d309  push    r15
0x14000d30b  lea     rbp, [rsp-13D0h]
0x14000d313  mov     eax, 14D0h
0x14000d318  call    _alloca_probe
0x14000d31d  sub     rsp, rax
0x14000d320  mov     rax, cs:__security_cookie
0x14000d327  xor     rax, rsp
0x14000d32a  mov     [rbp+1400h+var_40], rax
0x14000d331  mov     rsi, r8
0x14000d334  mov     edi, edx
0x14000d336  mov     rbx, rcx
0x14000d339  mov     r14, [rbp+1400h+arg_28]
0x14000d340  xor     edx, edx; Val
0x14000d342  mov     r8d, 98h; Size
0x14000d348  lea     rcx, [rsp+1500h+var_14E0]; void *
0x14000d34d  call    memset_0
0x14000d352  nop
0x14000d353  xor     r12d, r12d
0x14000d356  mov     [rbp+1400h+OutputString], r12w
0x14000d35e  mov     [rbp+1400h+var_1440], r12b
0x14000d362  mov     rdx, [rbp+1400h+arg_30]; int
0x14000d369  mov     ecx, [rdx]; this
0x14000d36b  mov     [rsp+1500h+var_14D8], ecx
0x14000d36f  mov     eax, [rdx+4]
0x14000d372  mov     [rsp+1500h+var_14D4], eax
0x14000d376  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000d37b  mov     r15d, eax
0x14000d37e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x14000d386  mov     ecx, r12d
0x14000d389  lea     eax, [r12+8]
0x14000d38e  cmp     dword ptr [rdx+8], 1
0x14000d392  cmovz   ecx, eax
0x14000d395  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x14000d399  lea     ecx, [rax-7]
0x14000d39c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000d3a4  inc     ecx
0x14000d3a6  mov     [rsp+1500h+var_14D0], ecx
0x14000d3aa  mov     rcx, [rbp+1400h+arg_38]
0x14000d3b1  test    rcx, rcx
0x14000d3b4  jz      short loc_14000D3C1
0x14000d3b6  cmp     [rcx], r12w
0x14000d3ba  mov     [rsp+1500h+var_14C8], rcx
0x14000d3bf  jnz     short loc_14000D3C6
0x14000d3c1  mov     [rsp+1500h+var_14C8], r12
0x14000d3c6  call    cs:__imp_GetCurrentThreadId
0x14000d3cd  nop     dword ptr [rax+rax+00h]
0x14000d3d2  mov     [rsp+1500h+var_14C0], eax
0x14000d3d6  mov     [rsp+1500h+var_14A8], rsi
0x14000d3db  mov     [rsp+1500h+var_14A0], edi
0x14000d3df  mov     [rsp+1500h+var_149C], r15d
0x14000d3e4  mov     [rsp+1500h+var_14B8], r12
0x14000d3e9  mov     [rsp+1500h+var_14B0], r12
0x14000d3ee  mov     [rbp+1400h+var_1458], r14
0x14000d3f2  mov     [rbp+1400h+var_1450], rbx
0x14000d3f6  mov     [rsp+1500h+var_1498], r12
0x14000d3fb  xorps   xmm0, xmm0
0x14000d3fe  xor     eax, eax
0x14000d400  movups  [rbp+1400h+var_1478], xmm0
0x14000d404  mov     [rbp+1400h+var_1468], rax
0x14000d408  xorps   xmm1, xmm1
0x14000d40b  movups  [rsp+1500h+var_1490], xmm1
0x14000d410  mov     [rbp+1400h+var_1480], rax
0x14000d414  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000d41b  test    rax, rax
0x14000d41e  jz      short loc_14000D42B
0x14000d420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d425  mov     [rbp+1400h+var_1460], rax
0x14000d429  jmp     short loc_14000D42F
0x14000d42b  mov     [rbp+1400h+var_1460], r12
0x14000d42f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000d436  test    rax, rax
0x14000d439  jz      short loc_14000D445
0x14000d43b  lea     rcx, [rsp+1500h+var_14E0]
0x14000d440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d445  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000d44c  test    rax, rax
0x14000d44f  jz      short loc_14000D465
0x14000d451  mov     r8d, 400h
0x14000d457  lea     rdx, [rbp+1400h+var_1440]
0x14000d45b  lea     rcx, [rsp+1500h+var_14E0]
0x14000d460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d465  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000d46c  test    rax, rax
0x14000d46f  jz      short loc_14000D47B
0x14000d471  lea     rcx, [rsp+1500h+var_14E0]
0x14000d476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d47b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000d482  test    rax, rax
0x14000d485  jz      short loc_14000D498
0x14000d487  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x14000d48c  jnz     short loc_14000D498
0x14000d48e  lea     rcx, [rsp+1500h+var_14E0]
0x14000d493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d498  cmp     [rsp+1500h+var_14D8], r12d
0x14000d49d  jge     loc_14000D5B3
0x14000d4a3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x14000d4aa  jnz     short loc_14000D4D1
0x14000d4ac  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000d4b3  test    rax, rax
0x14000d4b6  jz      short loc_14000D4C1
0x14000d4b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d4bd  test    al, al
0x14000d4bf  jmp     short loc_14000D4CF
0x14000d4c1  call    cs:__imp_IsDebuggerPresent
0x14000d4c8  nop     dword ptr [rax+rax+00h]
0x14000d4cd  test    eax, eax
0x14000d4cf  jz      short loc_14000D4D8
0x14000d4d1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x14000d4d6  jz      short loc_14000D4FE
0x14000d4d8  mov     rax, cs:g_pfnResultLoggingCallback
0x14000d4df  test    rax, rax
0x14000d4e2  jz      short loc_14000D55D
0x14000d4e4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000d4eb  jnz     short loc_14000D55D
0x14000d4ed  xor     r8d, r8d
0x14000d4f0  xor     edx, edx
0x14000d4f2  lea     rcx, [rsp+1500h+var_14E0]
0x14000d4f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d4fc  jmp     short loc_14000D55D
0x14000d4fe  mov     ebx, 800h
0x14000d503  mov     rax, cs:g_pfnResultLoggingCallback
0x14000d50a  test    rax, rax
0x14000d50d  jz      short loc_14000D52C
0x14000d50f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000d516  jnz     short loc_14000D52C
0x14000d518  mov     r8d, ebx
0x14000d51b  lea     rdx, [rbp+1400h+OutputString]
0x14000d522  lea     rcx, [rsp+1500h+var_14E0]
0x14000d527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d52c  cmp     [rbp+1400h+OutputString], r12w
0x14000d534  jnz     short loc_14000D54A
0x14000d536  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x14000d53b  mov     rdx, rbx; unsigned __int16 *
0x14000d53e  lea     rcx, [rbp+1400h+OutputString]; this
0x14000d545  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000d54a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x14000d551  call    cs:__imp_OutputDebugStringW
0x14000d558  nop     dword ptr [rax+rax+00h]
0x14000d55d  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x14000d562  jnz     short loc_14000D56D
0x14000d564  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x14000d56b  jz      short loc_14000D57F
0x14000d56d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000d574  test    rax, rax
0x14000d577  jz      short loc_14000D57F
0x14000d579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d57e  nop
0x14000d57f  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x14000d584  jnz     short loc_14000D5A8
0x14000d586  mov     rcx, [rbp+1400h+var_40]
0x14000d58d  xor     rcx, rsp; StackCookie
0x14000d590  call    __security_check_cookie
0x14000d595  add     rsp, 14D0h
0x14000d59c  pop     r15
0x14000d59e  pop     r14
0x14000d5a0  pop     r12
0x14000d5a2  pop     rdi
0x14000d5a3  pop     rsi
0x14000d5a4  pop     rbx
0x14000d5a5  pop     rbp
0x14000d5a6  retn
0x14000d5a8  lea     rcx, [rsp+1500h+var_14E0]; this
0x14000d5ad  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000d5b3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
