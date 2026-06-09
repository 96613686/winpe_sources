# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002768`
- end: `0x180002a21`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180001d38`

## callees

- `0x180002768`
- `0x180005304`
- `0x180006d34`
- `0x180007e7c`
- `0x180008058`
- `0x180009c5e`
- `0x180009c90`
- `0x180009d50`
- `0x18000b010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x1800029b9`
- `KERNEL32!OutputDebugStringW` at `0x1800029b9`
- `KERNEL32!IsDebuggerPresent` at `0x180002929`
- `KERNEL32!IsDebuggerPresent` at `0x180002929`
- `KERNEL32!GetCurrentThreadId` at `0x18000282e`
- `KERNEL32!GetCurrentThreadId` at `0x18000282e`

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
0x180002768  push    rbp
0x18000276a  push    rbx
0x18000276b  push    rsi
0x18000276c  push    rdi
0x18000276d  push    r12
0x18000276f  push    r14
0x180002771  push    r15
0x180002773  lea     rbp, [rsp-13D0h]
0x18000277b  mov     eax, 14D0h
0x180002780  call    _alloca_probe
0x180002785  sub     rsp, rax
0x180002788  mov     rax, cs:__security_cookie
0x18000278f  xor     rax, rsp
0x180002792  mov     [rbp+1400h+var_40], rax
0x180002799  mov     rsi, r8
0x18000279c  mov     edi, edx
0x18000279e  mov     rbx, rcx
0x1800027a1  mov     r14, [rbp+1400h+arg_28]
0x1800027a8  xor     edx, edx; Val
0x1800027aa  mov     r8d, 98h; Size
0x1800027b0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800027b5  call    memset_0
0x1800027ba  nop
0x1800027bb  xor     r12d, r12d
0x1800027be  mov     [rbp+1400h+OutputString], r12w
0x1800027c6  mov     [rbp+1400h+var_1440], r12b
0x1800027ca  mov     rdx, [rbp+1400h+arg_30]; int
0x1800027d1  mov     ecx, [rdx]; this
0x1800027d3  mov     [rsp+1500h+var_14D8], ecx
0x1800027d7  mov     eax, [rdx+4]
0x1800027da  mov     [rsp+1500h+var_14D4], eax
0x1800027de  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800027e3  mov     r15d, eax
0x1800027e6  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800027ee  mov     ecx, r12d
0x1800027f1  lea     eax, [r12+8]
0x1800027f6  cmp     dword ptr [rdx+8], 1
0x1800027fa  cmovz   ecx, eax
0x1800027fd  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180002801  lea     ecx, [rax-7]
0x180002804  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000280c  inc     ecx
0x18000280e  mov     [rsp+1500h+var_14D0], ecx
0x180002812  mov     rcx, [rbp+1400h+arg_38]
0x180002819  test    rcx, rcx
0x18000281c  jz      short loc_180002829
0x18000281e  cmp     [rcx], r12w
0x180002822  mov     [rsp+1500h+var_14C8], rcx
0x180002827  jnz     short loc_18000282E
0x180002829  mov     [rsp+1500h+var_14C8], r12
0x18000282e  call    cs:__imp_GetCurrentThreadId
0x180002835  nop     dword ptr [rax+rax+00h]
0x18000283a  mov     [rsp+1500h+var_14C0], eax
0x18000283e  mov     [rsp+1500h+var_14A8], rsi
0x180002843  mov     [rsp+1500h+var_14A0], edi
0x180002847  mov     [rsp+1500h+var_149C], r15d
0x18000284c  mov     [rsp+1500h+var_14B8], r12
0x180002851  mov     [rsp+1500h+var_14B0], r12
0x180002856  mov     [rbp+1400h+var_1458], r14
0x18000285a  mov     [rbp+1400h+var_1450], rbx
0x18000285e  mov     [rsp+1500h+var_1498], r12
0x180002863  xorps   xmm0, xmm0
0x180002866  xor     eax, eax
0x180002868  movups  [rbp+1400h+var_1478], xmm0
0x18000286c  mov     [rbp+1400h+var_1468], rax
0x180002870  xorps   xmm1, xmm1
0x180002873  movups  [rsp+1500h+var_1490], xmm1
0x180002878  mov     [rbp+1400h+var_1480], rax
0x18000287c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002883  test    rax, rax
0x180002886  jz      short loc_180002893
0x180002888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000288d  mov     [rbp+1400h+var_1460], rax
0x180002891  jmp     short loc_180002897
0x180002893  mov     [rbp+1400h+var_1460], r12
0x180002897  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000289e  test    rax, rax
0x1800028a1  jz      short loc_1800028AD
0x1800028a3  lea     rcx, [rsp+1500h+var_14E0]
0x1800028a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028ad  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800028b4  test    rax, rax
0x1800028b7  jz      short loc_1800028CD
0x1800028b9  mov     r8d, 400h
0x1800028bf  lea     rdx, [rbp+1400h+var_1440]
0x1800028c3  lea     rcx, [rsp+1500h+var_14E0]
0x1800028c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028cd  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800028d4  test    rax, rax
0x1800028d7  jz      short loc_1800028E3
0x1800028d9  lea     rcx, [rsp+1500h+var_14E0]
0x1800028de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028e3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800028ea  test    rax, rax
0x1800028ed  jz      short loc_180002900
0x1800028ef  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800028f4  jnz     short loc_180002900
0x1800028f6  lea     rcx, [rsp+1500h+var_14E0]
0x1800028fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002900  cmp     [rsp+1500h+var_14D8], r12d
0x180002905  jge     loc_180002A1B
0x18000290b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002912  jnz     short loc_180002939
0x180002914  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000291b  test    rax, rax
0x18000291e  jz      short loc_180002929
0x180002920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002925  test    al, al
0x180002927  jmp     short loc_180002937
0x180002929  call    cs:__imp_IsDebuggerPresent
0x180002930  nop     dword ptr [rax+rax+00h]
0x180002935  test    eax, eax
0x180002937  jz      short loc_180002940
0x180002939  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000293e  jz      short loc_180002966
0x180002940  mov     rax, cs:g_pfnResultLoggingCallback
0x180002947  test    rax, rax
0x18000294a  jz      short loc_1800029C5
0x18000294c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002953  jnz     short loc_1800029C5
0x180002955  xor     r8d, r8d
0x180002958  xor     edx, edx
0x18000295a  lea     rcx, [rsp+1500h+var_14E0]
0x18000295f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002964  jmp     short loc_1800029C5
0x180002966  mov     ebx, 800h
0x18000296b  mov     rax, cs:g_pfnResultLoggingCallback
0x180002972  test    rax, rax
0x180002975  jz      short loc_180002994
0x180002977  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000297e  jnz     short loc_180002994
0x180002980  mov     r8d, ebx
0x180002983  lea     rdx, [rbp+1400h+OutputString]
0x18000298a  lea     rcx, [rsp+1500h+var_14E0]
0x18000298f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002994  cmp     [rbp+1400h+OutputString], r12w
0x18000299c  jnz     short loc_1800029B2
0x18000299e  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800029a3  mov     rdx, rbx; unsigned __int16 *
0x1800029a6  lea     rcx, [rbp+1400h+OutputString]; this
0x1800029ad  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800029b2  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800029b9  call    cs:__imp_OutputDebugStringW
0x1800029c0  nop     dword ptr [rax+rax+00h]
0x1800029c5  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800029ca  jnz     short loc_1800029D5
0x1800029cc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800029d3  jz      short loc_1800029E7
0x1800029d5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800029dc  test    rax, rax
0x1800029df  jz      short loc_1800029E7
0x1800029e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029e6  nop
0x1800029e7  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800029ec  jnz     short loc_180002A10
0x1800029ee  mov     rcx, [rbp+1400h+var_40]
0x1800029f5  xor     rcx, rsp; StackCookie
0x1800029f8  call    __security_check_cookie
0x1800029fd  add     rsp, 14D0h
0x180002a04  pop     r15
0x180002a06  pop     r14
0x180002a08  pop     r12
0x180002a0a  pop     rdi
0x180002a0b  pop     rsi
0x180002a0c  pop     rbx
0x180002a0d  pop     rbp
0x180002a0e  retn
0x180002a10  lea     rcx, [rsp+1500h+var_14E0]; this
0x180002a15  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002a1b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
