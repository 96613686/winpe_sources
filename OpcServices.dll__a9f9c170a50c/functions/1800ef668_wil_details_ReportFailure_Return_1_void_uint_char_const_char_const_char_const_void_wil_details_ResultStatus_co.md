# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800ef668`
- end: `0x1800ef90a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800c69c4`

## callees

- `0x1800d5fe4`
- `0x1800ef668`
- `0x1800f0494`
- `0x1800f12d0`
- `0x1800f1c88`
- `0x1800f1de4`
- `0x180117740`
- `0x180117800`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ef71f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ef71f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800ef8a4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800ef8a4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800ef81a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800ef81a`

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
        int *a7)
{
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  __int64 v36; // [rsp+C0h] [rbp-40h]
  char v37[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2048]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v36 = -2;
  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x1800ef668  push    rbp
0x1800ef66a  push    rsi
0x1800ef66b  push    rdi
0x1800ef66c  push    r14
0x1800ef66e  push    r15
0x1800ef670  lea     rbp, [rsp-13E0h]
0x1800ef678  mov     eax, 14E0h
0x1800ef67d  call    _alloca_probe
0x1800ef682  sub     rsp, rax
0x1800ef685  mov     [rbp+1400h+var_1440], 0FFFFFFFFFFFFFFFEh
0x1800ef68d  mov     [rsp+1500h+arg_10], rbx
0x1800ef695  mov     rax, cs:__security_cookie
0x1800ef69c  xor     rax, rsp
0x1800ef69f  mov     [rbp+1400h+var_30], rax
0x1800ef6a6  mov     esi, edx
0x1800ef6a8  mov     r14, rcx
0x1800ef6ab  mov     rdi, [rbp+1400h+arg_28]
0x1800ef6b2  xor     edx, edx; Val
0x1800ef6b4  mov     r8d, 98h; Size
0x1800ef6ba  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800ef6bf  call    memset_0
0x1800ef6c4  nop
0x1800ef6c5  xor     r15d, r15d
0x1800ef6c8  mov     [rbp+1400h+OutputString], r15w
0x1800ef6d0  mov     [rbp+1400h+var_1430], r15b
0x1800ef6d4  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1800ef6db  mov     ecx, [rdx]; this
0x1800ef6dd  mov     [rsp+1500h+var_14D8], ecx
0x1800ef6e1  mov     eax, [rdx+4]
0x1800ef6e4  mov     [rsp+1500h+var_14D4], eax
0x1800ef6e8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800ef6ed  mov     ebx, eax
0x1800ef6ef  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800ef6f7  mov     ecx, r15d
0x1800ef6fa  lea     eax, [r15+8]
0x1800ef6fe  cmp     dword ptr [rdx+8], 1
0x1800ef702  cmovz   ecx, eax
0x1800ef705  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800ef709  lea     ecx, [rax-7]
0x1800ef70c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800ef714  inc     ecx
0x1800ef716  mov     [rsp+1500h+var_14D0], ecx
0x1800ef71a  mov     [rsp+1500h+var_14C8], r15
0x1800ef71f  call    cs:__imp_GetCurrentThreadId
0x1800ef725  mov     [rsp+1500h+var_14C0], eax
0x1800ef729  lea     rax, aWil; "wil"
0x1800ef730  mov     [rsp+1500h+var_14A8], rax
0x1800ef735  mov     [rsp+1500h+var_14A0], esi
0x1800ef739  mov     [rsp+1500h+var_149C], ebx
0x1800ef73d  mov     [rsp+1500h+var_14B8], r15
0x1800ef742  mov     [rsp+1500h+var_14B0], r15
0x1800ef747  mov     [rbp+1400h+var_1458], rdi
0x1800ef74b  mov     [rbp+1400h+var_1450], r14
0x1800ef74f  mov     [rsp+1500h+var_1498], r15
0x1800ef754  xorps   xmm0, xmm0
0x1800ef757  xor     eax, eax
0x1800ef759  movups  [rbp+1400h+var_1478], xmm0
0x1800ef75d  mov     [rbp+1400h+var_1468], rax
0x1800ef761  xorps   xmm1, xmm1
0x1800ef764  movups  [rsp+1500h+var_1490], xmm1
0x1800ef769  mov     [rbp+1400h+var_1480], rax
0x1800ef76d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800ef774  test    rax, rax
0x1800ef777  jz      short loc_1800EF784
0x1800ef779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef77e  mov     [rbp+1400h+var_1460], rax
0x1800ef782  jmp     short loc_1800EF788
0x1800ef784  mov     [rbp+1400h+var_1460], r15
0x1800ef788  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800ef78f  test    rax, rax
0x1800ef792  jz      short loc_1800EF79E
0x1800ef794  lea     rcx, [rsp+1500h+var_14E0]
0x1800ef799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef79e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800ef7a5  test    rax, rax
0x1800ef7a8  jz      short loc_1800EF7BE
0x1800ef7aa  mov     r8d, 400h
0x1800ef7b0  lea     rdx, [rbp+1400h+var_1430]
0x1800ef7b4  lea     rcx, [rsp+1500h+var_14E0]
0x1800ef7b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef7be  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800ef7c5  test    rax, rax
0x1800ef7c8  jz      short loc_1800EF7D4
0x1800ef7ca  lea     rcx, [rsp+1500h+var_14E0]
0x1800ef7cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef7d4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800ef7db  test    rax, rax
0x1800ef7de  jz      short loc_1800EF7F1
0x1800ef7e0  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800ef7e5  jnz     short loc_1800EF7F1
0x1800ef7e7  lea     rcx, [rsp+1500h+var_14E0]
0x1800ef7ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef7f1  cmp     [rsp+1500h+var_14D8], r15d
0x1800ef7f6  jge     loc_1800EF904
0x1800ef7fc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800ef803  jnz     short loc_1800EF824
0x1800ef805  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800ef80c  test    rax, rax
0x1800ef80f  jz      short loc_1800EF81A
0x1800ef811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef816  test    al, al
0x1800ef818  jmp     short loc_1800EF822
0x1800ef81a  call    cs:__imp_IsDebuggerPresent
0x1800ef820  test    eax, eax
0x1800ef822  jz      short loc_1800EF82B
0x1800ef824  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800ef829  jz      short loc_1800EF851
0x1800ef82b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800ef832  test    rax, rax
0x1800ef835  jz      short loc_1800EF8AA
0x1800ef837  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800ef83e  jnz     short loc_1800EF8AA
0x1800ef840  xor     r8d, r8d
0x1800ef843  xor     edx, edx
0x1800ef845  lea     rcx, [rsp+1500h+var_14E0]
0x1800ef84a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef84f  jmp     short loc_1800EF8AA
0x1800ef851  mov     ebx, 800h
0x1800ef856  mov     rax, cs:g_pfnResultLoggingCallback
0x1800ef85d  test    rax, rax
0x1800ef860  jz      short loc_1800EF87F
0x1800ef862  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800ef869  jnz     short loc_1800EF87F
0x1800ef86b  mov     r8d, ebx
0x1800ef86e  lea     rdx, [rbp+1400h+OutputString]
0x1800ef875  lea     rcx, [rsp+1500h+var_14E0]
0x1800ef87a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef87f  cmp     [rbp+1400h+OutputString], r15w
0x1800ef887  jnz     short loc_1800EF89D
0x1800ef889  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800ef88e  mov     rdx, rbx; wchar_t *
0x1800ef891  lea     rcx, [rbp+1400h+OutputString]; this
0x1800ef898  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800ef89d  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800ef8a4  call    cs:__imp_OutputDebugStringW
0x1800ef8aa  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800ef8af  jnz     short loc_1800EF8BA
0x1800ef8b1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800ef8b8  jz      short loc_1800EF8CC
0x1800ef8ba  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800ef8c1  test    rax, rax
0x1800ef8c4  jz      short loc_1800EF8CC
0x1800ef8c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef8cb  nop
0x1800ef8cc  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800ef8d1  jnz     short loc_1800EF8F9
0x1800ef8d3  mov     rcx, [rbp+1400h+var_30]
0x1800ef8da  xor     rcx, rsp; StackCookie
0x1800ef8dd  call    __security_check_cookie
0x1800ef8e2  mov     rbx, [rsp+1500h+arg_10]
0x1800ef8ea  add     rsp, 14E0h
0x1800ef8f1  pop     r15
0x1800ef8f3  pop     r14
0x1800ef8f5  pop     rdi
0x1800ef8f6  pop     rsi
0x1800ef8f7  pop     rbp
0x1800ef8f8  retn
0x1800ef8f9  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800ef8fe  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800ef904  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
