# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002758`
- end: `0x180002a11`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002260`

## callees

- `0x180002758`
- `0x1800038f4`
- `0x180004ad4`
- `0x180005780`
- `0x180005abc`
- `0x180009efe`
- `0x180009f30`
- `0x180009ff0`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000281e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000281e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800029a9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800029a9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002919`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002919`

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
0x180002758  push    rbp
0x18000275a  push    rbx
0x18000275b  push    rsi
0x18000275c  push    rdi
0x18000275d  push    r12
0x18000275f  push    r14
0x180002761  push    r15
0x180002763  lea     rbp, [rsp-13D0h]
0x18000276b  mov     eax, 14D0h
0x180002770  call    _alloca_probe
0x180002775  sub     rsp, rax
0x180002778  mov     rax, cs:__security_cookie
0x18000277f  xor     rax, rsp
0x180002782  mov     [rbp+1400h+var_40], rax
0x180002789  mov     rsi, r8
0x18000278c  mov     edi, edx
0x18000278e  mov     rbx, rcx
0x180002791  mov     r14, [rbp+1400h+arg_28]
0x180002798  xor     edx, edx; Val
0x18000279a  mov     r8d, 98h; Size
0x1800027a0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800027a5  call    memset_0
0x1800027aa  nop
0x1800027ab  xor     r12d, r12d
0x1800027ae  mov     [rbp+1400h+OutputString], r12w
0x1800027b6  mov     [rbp+1400h+var_1440], r12b
0x1800027ba  mov     rdx, [rbp+1400h+arg_30]; int
0x1800027c1  mov     ecx, [rdx]; this
0x1800027c3  mov     [rsp+1500h+var_14D8], ecx
0x1800027c7  mov     eax, [rdx+4]
0x1800027ca  mov     [rsp+1500h+var_14D4], eax
0x1800027ce  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800027d3  mov     r15d, eax
0x1800027d6  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800027de  mov     ecx, r12d
0x1800027e1  lea     eax, [r12+8]
0x1800027e6  cmp     dword ptr [rdx+8], 1
0x1800027ea  cmovz   ecx, eax
0x1800027ed  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800027f1  lea     ecx, [rax-7]
0x1800027f4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800027fc  inc     ecx
0x1800027fe  mov     [rsp+1500h+var_14D0], ecx
0x180002802  mov     rcx, [rbp+1400h+arg_38]
0x180002809  test    rcx, rcx
0x18000280c  jz      short loc_180002819
0x18000280e  cmp     [rcx], r12w
0x180002812  mov     [rsp+1500h+var_14C8], rcx
0x180002817  jnz     short loc_18000281E
0x180002819  mov     [rsp+1500h+var_14C8], r12
0x18000281e  call    cs:__imp_GetCurrentThreadId
0x180002825  nop     dword ptr [rax+rax+00h]
0x18000282a  mov     [rsp+1500h+var_14C0], eax
0x18000282e  mov     [rsp+1500h+var_14A8], rsi
0x180002833  mov     [rsp+1500h+var_14A0], edi
0x180002837  mov     [rsp+1500h+var_149C], r15d
0x18000283c  mov     [rsp+1500h+var_14B8], r12
0x180002841  mov     [rsp+1500h+var_14B0], r12
0x180002846  mov     [rbp+1400h+var_1458], r14
0x18000284a  mov     [rbp+1400h+var_1450], rbx
0x18000284e  mov     [rsp+1500h+var_1498], r12
0x180002853  xorps   xmm0, xmm0
0x180002856  xor     eax, eax
0x180002858  movups  [rbp+1400h+var_1478], xmm0
0x18000285c  mov     [rbp+1400h+var_1468], rax
0x180002860  xorps   xmm1, xmm1
0x180002863  movups  [rsp+1500h+var_1490], xmm1
0x180002868  mov     [rbp+1400h+var_1480], rax
0x18000286c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002873  test    rax, rax
0x180002876  jz      short loc_180002883
0x180002878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000287d  mov     [rbp+1400h+var_1460], rax
0x180002881  jmp     short loc_180002887
0x180002883  mov     [rbp+1400h+var_1460], r12
0x180002887  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000288e  test    rax, rax
0x180002891  jz      short loc_18000289D
0x180002893  lea     rcx, [rsp+1500h+var_14E0]
0x180002898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000289d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800028a4  test    rax, rax
0x1800028a7  jz      short loc_1800028BD
0x1800028a9  mov     r8d, 400h
0x1800028af  lea     rdx, [rbp+1400h+var_1440]
0x1800028b3  lea     rcx, [rsp+1500h+var_14E0]
0x1800028b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028bd  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800028c4  test    rax, rax
0x1800028c7  jz      short loc_1800028D3
0x1800028c9  lea     rcx, [rsp+1500h+var_14E0]
0x1800028ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028d3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800028da  test    rax, rax
0x1800028dd  jz      short loc_1800028F0
0x1800028df  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800028e4  jnz     short loc_1800028F0
0x1800028e6  lea     rcx, [rsp+1500h+var_14E0]
0x1800028eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028f0  cmp     [rsp+1500h+var_14D8], r12d
0x1800028f5  jge     loc_180002A0B
0x1800028fb  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002902  jnz     short loc_180002929
0x180002904  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000290b  test    rax, rax
0x18000290e  jz      short loc_180002919
0x180002910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002915  test    al, al
0x180002917  jmp     short loc_180002927
0x180002919  call    cs:__imp_IsDebuggerPresent
0x180002920  nop     dword ptr [rax+rax+00h]
0x180002925  test    eax, eax
0x180002927  jz      short loc_180002930
0x180002929  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000292e  jz      short loc_180002956
0x180002930  mov     rax, cs:g_pfnResultLoggingCallback
0x180002937  test    rax, rax
0x18000293a  jz      short loc_1800029B5
0x18000293c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002943  jnz     short loc_1800029B5
0x180002945  xor     r8d, r8d
0x180002948  xor     edx, edx
0x18000294a  lea     rcx, [rsp+1500h+var_14E0]
0x18000294f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002954  jmp     short loc_1800029B5
0x180002956  mov     ebx, 800h
0x18000295b  mov     rax, cs:g_pfnResultLoggingCallback
0x180002962  test    rax, rax
0x180002965  jz      short loc_180002984
0x180002967  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000296e  jnz     short loc_180002984
0x180002970  mov     r8d, ebx
0x180002973  lea     rdx, [rbp+1400h+OutputString]
0x18000297a  lea     rcx, [rsp+1500h+var_14E0]
0x18000297f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002984  cmp     [rbp+1400h+OutputString], r12w
0x18000298c  jnz     short loc_1800029A2
0x18000298e  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180002993  mov     rdx, rbx; unsigned __int16 *
0x180002996  lea     rcx, [rbp+1400h+OutputString]; this
0x18000299d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800029a2  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800029a9  call    cs:__imp_OutputDebugStringW
0x1800029b0  nop     dword ptr [rax+rax+00h]
0x1800029b5  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800029ba  jnz     short loc_1800029C5
0x1800029bc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800029c3  jz      short loc_1800029D7
0x1800029c5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800029cc  test    rax, rax
0x1800029cf  jz      short loc_1800029D7
0x1800029d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029d6  nop
0x1800029d7  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800029dc  jnz     short loc_180002A00
0x1800029de  mov     rcx, [rbp+1400h+var_40]
0x1800029e5  xor     rcx, rsp; StackCookie
0x1800029e8  call    __security_check_cookie
0x1800029ed  add     rsp, 14D0h
0x1800029f4  pop     r15
0x1800029f6  pop     r14
0x1800029f8  pop     r12
0x1800029fa  pop     rdi
0x1800029fb  pop     rsi
0x1800029fc  pop     rbx
0x1800029fd  pop     rbp
0x1800029fe  retn
0x180002a00  lea     rcx, [rsp+1500h+var_14E0]; this
0x180002a05  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002a0b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
