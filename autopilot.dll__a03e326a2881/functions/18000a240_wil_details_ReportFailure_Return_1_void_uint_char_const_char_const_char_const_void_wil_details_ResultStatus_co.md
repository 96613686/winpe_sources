# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000a240`
- end: `0x18000a4e6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180009ce0`

## callees

- `0x1800045b0`
- `0x180005374`
- `0x18000a240`
- `0x18000d284`
- `0x18000f1d8`
- `0x180011e10`
- `0x180012104`
- `0x1800281e0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a306`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a306`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a3fb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a3fb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a485`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a485`

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
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
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
0x18000a240  push    rbp
0x18000a242  push    rbx
0x18000a243  push    rsi
0x18000a244  push    rdi
0x18000a245  push    r12
0x18000a247  push    r14
0x18000a249  push    r15
0x18000a24b  lea     rbp, [rsp-13D0h]
0x18000a253  mov     eax, 14D0h
0x18000a258  call    _alloca_probe
0x18000a25d  sub     rsp, rax
0x18000a260  mov     rax, cs:__security_cookie
0x18000a267  xor     rax, rsp
0x18000a26a  mov     [rbp+1400h+var_40], rax
0x18000a271  mov     rsi, r8
0x18000a274  mov     edi, edx
0x18000a276  mov     rbx, rcx
0x18000a279  mov     r14, [rbp+1400h+arg_28]
0x18000a280  xor     edx, edx; Val
0x18000a282  mov     r8d, 98h; Size
0x18000a288  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000a28d  call    memset_0
0x18000a292  nop
0x18000a293  xor     r12d, r12d
0x18000a296  mov     [rbp+1400h+OutputString], r12w
0x18000a29e  mov     [rbp+1400h+var_1440], r12b
0x18000a2a2  mov     rdx, [rbp+1400h+arg_30]; int
0x18000a2a9  mov     ecx, [rdx]; this
0x18000a2ab  mov     [rsp+1500h+var_14D8], ecx
0x18000a2af  mov     eax, [rdx+4]
0x18000a2b2  mov     [rsp+1500h+var_14D4], eax
0x18000a2b6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a2bb  mov     r15d, eax
0x18000a2be  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000a2c6  mov     ecx, r12d
0x18000a2c9  lea     eax, [r12+8]
0x18000a2ce  cmp     dword ptr [rdx+8], 1
0x18000a2d2  cmovz   ecx, eax
0x18000a2d5  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000a2d9  lea     ecx, [rax-7]
0x18000a2dc  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a2e4  inc     ecx
0x18000a2e6  mov     [rsp+1500h+var_14D0], ecx
0x18000a2ea  mov     rcx, [rbp+1400h+arg_38]
0x18000a2f1  test    rcx, rcx
0x18000a2f4  jz      short loc_18000A301
0x18000a2f6  cmp     [rcx], r12w
0x18000a2fa  mov     [rsp+1500h+var_14C8], rcx
0x18000a2ff  jnz     short loc_18000A306
0x18000a301  mov     [rsp+1500h+var_14C8], r12
0x18000a306  call    cs:__imp_GetCurrentThreadId
0x18000a30c  mov     [rsp+1500h+var_14C0], eax
0x18000a310  mov     [rsp+1500h+var_14A8], rsi
0x18000a315  mov     [rsp+1500h+var_14A0], edi
0x18000a319  mov     [rsp+1500h+var_149C], r15d
0x18000a31e  mov     [rsp+1500h+var_14B8], r12
0x18000a323  mov     [rsp+1500h+var_14B0], r12
0x18000a328  mov     [rbp+1400h+var_1458], r14
0x18000a32c  mov     [rbp+1400h+var_1450], rbx
0x18000a330  mov     [rsp+1500h+var_1498], r12
0x18000a335  xorps   xmm0, xmm0
0x18000a338  xor     eax, eax
0x18000a33a  movups  [rbp+1400h+var_1478], xmm0
0x18000a33e  mov     [rbp+1400h+var_1468], rax
0x18000a342  xorps   xmm1, xmm1
0x18000a345  movups  [rsp+1500h+var_1490], xmm1
0x18000a34a  mov     [rbp+1400h+var_1480], rax
0x18000a34e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a355  test    rax, rax
0x18000a358  jz      short loc_18000A365
0x18000a35a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a35f  mov     [rbp+1400h+var_1460], rax
0x18000a363  jmp     short loc_18000A369
0x18000a365  mov     [rbp+1400h+var_1460], r12
0x18000a369  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a370  test    rax, rax
0x18000a373  jz      short loc_18000A37F
0x18000a375  lea     rcx, [rsp+1500h+var_14E0]
0x18000a37a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a37f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a386  test    rax, rax
0x18000a389  jz      short loc_18000A39F
0x18000a38b  mov     r8d, 400h
0x18000a391  lea     rdx, [rbp+1400h+var_1440]
0x18000a395  lea     rcx, [rsp+1500h+var_14E0]
0x18000a39a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a39f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a3a6  test    rax, rax
0x18000a3a9  jz      short loc_18000A3B5
0x18000a3ab  lea     rcx, [rsp+1500h+var_14E0]
0x18000a3b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3b5  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a3bc  test    rax, rax
0x18000a3bf  jz      short loc_18000A3D2
0x18000a3c1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000a3c6  jnz     short loc_18000A3D2
0x18000a3c8  lea     rcx, [rsp+1500h+var_14E0]
0x18000a3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3d2  cmp     [rsp+1500h+var_14D8], r12d
0x18000a3d7  jge     loc_18000A4E0
0x18000a3dd  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000a3e4  jnz     short loc_18000A405
0x18000a3e6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a3ed  test    rax, rax
0x18000a3f0  jz      short loc_18000A3FB
0x18000a3f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3f7  test    al, al
0x18000a3f9  jmp     short loc_18000A403
0x18000a3fb  call    cs:__imp_IsDebuggerPresent
0x18000a401  test    eax, eax
0x18000a403  jz      short loc_18000A40C
0x18000a405  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000a40a  jz      short loc_18000A432
0x18000a40c  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a413  test    rax, rax
0x18000a416  jz      short loc_18000A48B
0x18000a418  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000a41f  jnz     short loc_18000A48B
0x18000a421  xor     r8d, r8d
0x18000a424  xor     edx, edx
0x18000a426  lea     rcx, [rsp+1500h+var_14E0]
0x18000a42b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a430  jmp     short loc_18000A48B
0x18000a432  mov     ebx, 800h
0x18000a437  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a43e  test    rax, rax
0x18000a441  jz      short loc_18000A460
0x18000a443  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000a44a  jnz     short loc_18000A460
0x18000a44c  mov     r8d, ebx
0x18000a44f  lea     rdx, [rbp+1400h+OutputString]
0x18000a456  lea     rcx, [rsp+1500h+var_14E0]
0x18000a45b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a460  cmp     [rbp+1400h+OutputString], r12w
0x18000a468  jnz     short loc_18000A47E
0x18000a46a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000a46f  mov     rdx, rbx; unsigned __int16 *
0x18000a472  lea     rcx, [rbp+1400h+OutputString]; this
0x18000a479  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000a47e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000a485  call    cs:__imp_OutputDebugStringW
0x18000a48b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000a490  jnz     short loc_18000A49B
0x18000a492  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000a499  jz      short loc_18000A4AD
0x18000a49b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a4a2  test    rax, rax
0x18000a4a5  jz      short loc_18000A4AD
0x18000a4a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4ac  nop
0x18000a4ad  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000a4b2  jnz     short loc_18000A4D5
0x18000a4b4  mov     rcx, [rbp+1400h+var_40]
0x18000a4bb  xor     rcx, rsp; StackCookie
0x18000a4be  call    __security_check_cookie
0x18000a4c3  add     rsp, 14D0h
0x18000a4ca  pop     r15
0x18000a4cc  pop     r14
0x18000a4ce  pop     r12
0x18000a4d0  pop     rdi
0x18000a4d1  pop     rsi
0x18000a4d2  pop     rbx
0x18000a4d3  pop     rbp
0x18000a4d4  retn
0x18000a4d5  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000a4da  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000a4e0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
