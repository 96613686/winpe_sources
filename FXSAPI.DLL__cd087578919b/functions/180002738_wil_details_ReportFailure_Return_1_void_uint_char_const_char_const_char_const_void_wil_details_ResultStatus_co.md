# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002738`
- end: `0x1800029e1`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800021fc`

## callees

- `0x180002738`
- `0x180005294`
- `0x180006ca8`
- `0x18000931c`
- `0x1800094f0`
- `0x18003d4ca`
- `0x18003d510`
- `0x18003d5a0`
- `0x18003e010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800027e3`
- `KERNEL32!GetCurrentThreadId` at `0x1800027e3`
- `KERNEL32!OutputDebugStringW` at `0x180002974`
- `KERNEL32!OutputDebugStringW` at `0x180002974`
- `KERNEL32!IsDebuggerPresent` at `0x1800028e4`
- `KERNEL32!IsDebuggerPresent` at `0x1800028e4`

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
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
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
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
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
0x180002738  mov     [rsp-8+arg_10], rbx
0x18000273d  push    rbp
0x18000273e  push    rsi
0x18000273f  push    rdi
0x180002740  push    r14
0x180002742  push    r15
0x180002744  lea     rbp, [rsp-13D0h]
0x18000274c  mov     eax, 14D0h
0x180002751  call    _alloca_probe
0x180002756  sub     rsp, rax
0x180002759  mov     rax, cs:__security_cookie
0x180002760  xor     rax, rsp
0x180002763  mov     [rbp+13F0h+var_30], rax
0x18000276a  mov     esi, edx
0x18000276c  mov     r14, rcx
0x18000276f  mov     rdi, [rbp+13F0h+arg_28]
0x180002776  xor     edx, edx; Val
0x180002778  mov     r8d, 98h; Size
0x18000277e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002783  call    memset_0
0x180002788  nop
0x180002789  xor     r15d, r15d
0x18000278c  mov     [rbp+13F0h+OutputString], r15w
0x180002794  mov     [rbp+13F0h+var_1430], r15b
0x180002798  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000279f  mov     ecx, [rdx]; this
0x1800027a1  mov     [rsp+14F0h+var_14C8], ecx
0x1800027a5  mov     eax, [rdx+4]
0x1800027a8  mov     [rsp+14F0h+var_14C4], eax
0x1800027ac  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800027b1  mov     ebx, eax
0x1800027b3  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800027bb  mov     ecx, r15d
0x1800027be  lea     eax, [r15+8]
0x1800027c2  cmp     dword ptr [rdx+8], 1
0x1800027c6  cmovz   ecx, eax
0x1800027c9  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800027cd  lea     ecx, [rax-7]
0x1800027d0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800027d8  inc     ecx
0x1800027da  mov     [rsp+14F0h+var_14C0], ecx
0x1800027de  mov     [rsp+14F0h+var_14B8], r15
0x1800027e3  call    cs:__imp_GetCurrentThreadId
0x1800027ea  nop     dword ptr [rax+rax+00h]
0x1800027ef  mov     [rsp+14F0h+var_14B0], eax
0x1800027f3  lea     rax, aWil; "wil"
0x1800027fa  mov     [rsp+14F0h+var_1498], rax
0x1800027ff  mov     [rsp+14F0h+var_1490], esi
0x180002803  mov     [rsp+14F0h+var_148C], ebx
0x180002807  mov     [rsp+14F0h+var_14A8], r15
0x18000280c  mov     [rsp+14F0h+var_14A0], r15
0x180002811  mov     [rbp+13F0h+var_1448], rdi
0x180002815  mov     [rbp+13F0h+var_1440], r14
0x180002819  mov     [rsp+14F0h+var_1488], r15
0x18000281e  xorps   xmm0, xmm0
0x180002821  xor     eax, eax
0x180002823  movups  [rbp+13F0h+var_1468], xmm0
0x180002827  mov     [rbp+13F0h+var_1458], rax
0x18000282b  xorps   xmm1, xmm1
0x18000282e  movups  [rsp+14F0h+var_1480], xmm1
0x180002833  mov     [rbp+13F0h+var_1470], rax
0x180002837  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000283e  test    rax, rax
0x180002841  jz      short loc_18000284E
0x180002843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002848  mov     [rbp+13F0h+var_1450], rax
0x18000284c  jmp     short loc_180002852
0x18000284e  mov     [rbp+13F0h+var_1450], r15
0x180002852  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002859  test    rax, rax
0x18000285c  jz      short loc_180002868
0x18000285e  lea     rcx, [rsp+14F0h+var_14D0]
0x180002863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002868  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000286f  test    rax, rax
0x180002872  jz      short loc_180002888
0x180002874  mov     r8d, 400h
0x18000287a  lea     rdx, [rbp+13F0h+var_1430]
0x18000287e  lea     rcx, [rsp+14F0h+var_14D0]
0x180002883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002888  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000288f  test    rax, rax
0x180002892  jz      short loc_18000289E
0x180002894  lea     rcx, [rsp+14F0h+var_14D0]
0x180002899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000289e  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800028a5  test    rax, rax
0x1800028a8  jz      short loc_1800028BB
0x1800028aa  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800028af  jnz     short loc_1800028BB
0x1800028b1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800028b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028bb  cmp     [rsp+14F0h+var_14C8], r15d
0x1800028c0  jge     loc_1800029DB
0x1800028c6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800028cd  jnz     short loc_1800028F4
0x1800028cf  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800028d6  test    rax, rax
0x1800028d9  jz      short loc_1800028E4
0x1800028db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028e0  test    al, al
0x1800028e2  jmp     short loc_1800028F2
0x1800028e4  call    cs:__imp_IsDebuggerPresent
0x1800028eb  nop     dword ptr [rax+rax+00h]
0x1800028f0  test    eax, eax
0x1800028f2  jz      short loc_1800028FB
0x1800028f4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800028f9  jz      short loc_180002921
0x1800028fb  mov     rax, cs:g_pfnResultLoggingCallback
0x180002902  test    rax, rax
0x180002905  jz      short loc_180002980
0x180002907  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000290e  jnz     short loc_180002980
0x180002910  xor     r8d, r8d
0x180002913  xor     edx, edx
0x180002915  lea     rcx, [rsp+14F0h+var_14D0]
0x18000291a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000291f  jmp     short loc_180002980
0x180002921  mov     ebx, 800h
0x180002926  mov     rax, cs:g_pfnResultLoggingCallback
0x18000292d  test    rax, rax
0x180002930  jz      short loc_18000294F
0x180002932  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002939  jnz     short loc_18000294F
0x18000293b  mov     r8d, ebx
0x18000293e  lea     rdx, [rbp+13F0h+OutputString]
0x180002945  lea     rcx, [rsp+14F0h+var_14D0]
0x18000294a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000294f  cmp     [rbp+13F0h+OutputString], r15w
0x180002957  jnz     short loc_18000296D
0x180002959  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000295e  mov     rdx, rbx; unsigned __int16 *
0x180002961  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002968  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000296d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002974  call    cs:__imp_OutputDebugStringW
0x18000297b  nop     dword ptr [rax+rax+00h]
0x180002980  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002985  jnz     short loc_180002990
0x180002987  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000298e  jz      short loc_1800029A2
0x180002990  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002997  test    rax, rax
0x18000299a  jz      short loc_1800029A2
0x18000299c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029a1  nop
0x1800029a2  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800029a7  jnz     short loc_1800029D0
0x1800029a9  mov     rcx, [rbp+13F0h+var_30]
0x1800029b0  xor     rcx, rsp; StackCookie
0x1800029b3  call    __security_check_cookie
0x1800029b8  mov     rbx, [rsp+14F0h+arg_10]
0x1800029c0  add     rsp, 14D0h
0x1800029c7  pop     r15
0x1800029c9  pop     r14
0x1800029cb  pop     rdi
0x1800029cc  pop     rsi
0x1800029cd  pop     rbp
0x1800029ce  retn
0x1800029d0  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800029d5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800029db  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
