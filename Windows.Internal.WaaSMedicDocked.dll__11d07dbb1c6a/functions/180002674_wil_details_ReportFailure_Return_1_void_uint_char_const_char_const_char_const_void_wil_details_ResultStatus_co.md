# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002674`
- end: `0x18000291a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000213c`

## callees

- `0x180001570`
- `0x180001fde`
- `0x180002674`
- `0x180003804`
- `0x180004700`
- `0x180005610`
- `0x1800056ec`
- `0x18000b550`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000273a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000273a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800028b9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800028b9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000282f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000282f`

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
0x180002674  push    rbp
0x180002676  push    rbx
0x180002677  push    rsi
0x180002678  push    rdi
0x180002679  push    r12
0x18000267b  push    r14
0x18000267d  push    r15
0x18000267f  lea     rbp, [rsp-13D0h]
0x180002687  mov     eax, 14D0h
0x18000268c  call    _alloca_probe
0x180002691  sub     rsp, rax
0x180002694  mov     rax, cs:__security_cookie
0x18000269b  xor     rax, rsp
0x18000269e  mov     [rbp+1400h+var_40], rax
0x1800026a5  mov     rsi, r8
0x1800026a8  mov     edi, edx
0x1800026aa  mov     rbx, rcx
0x1800026ad  mov     r14, [rbp+1400h+arg_28]
0x1800026b4  xor     edx, edx; Val
0x1800026b6  mov     r8d, 98h; Size
0x1800026bc  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800026c1  call    memset_0
0x1800026c6  nop
0x1800026c7  xor     r12d, r12d
0x1800026ca  mov     [rbp+1400h+OutputString], r12w
0x1800026d2  mov     [rbp+1400h+var_1440], r12b
0x1800026d6  mov     rdx, [rbp+1400h+arg_30]; int
0x1800026dd  mov     ecx, [rdx]; this
0x1800026df  mov     [rsp+1500h+var_14D8], ecx
0x1800026e3  mov     eax, [rdx+4]
0x1800026e6  mov     [rsp+1500h+var_14D4], eax
0x1800026ea  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800026ef  mov     r15d, eax
0x1800026f2  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800026fa  mov     ecx, r12d
0x1800026fd  lea     eax, [r12+8]
0x180002702  cmp     dword ptr [rdx+8], 1
0x180002706  cmovz   ecx, eax
0x180002709  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000270d  lea     ecx, [rax-7]
0x180002710  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002718  inc     ecx
0x18000271a  mov     [rsp+1500h+var_14D0], ecx
0x18000271e  mov     rcx, [rbp+1400h+arg_38]
0x180002725  test    rcx, rcx
0x180002728  jz      short loc_180002735
0x18000272a  cmp     [rcx], r12w
0x18000272e  mov     [rsp+1500h+var_14C8], rcx
0x180002733  jnz     short loc_18000273A
0x180002735  mov     [rsp+1500h+var_14C8], r12
0x18000273a  call    cs:__imp_GetCurrentThreadId
0x180002740  mov     [rsp+1500h+var_14C0], eax
0x180002744  mov     [rsp+1500h+var_14A8], rsi
0x180002749  mov     [rsp+1500h+var_14A0], edi
0x18000274d  mov     [rsp+1500h+var_149C], r15d
0x180002752  mov     [rsp+1500h+var_14B8], r12
0x180002757  mov     [rsp+1500h+var_14B0], r12
0x18000275c  mov     [rbp+1400h+var_1458], r14
0x180002760  mov     [rbp+1400h+var_1450], rbx
0x180002764  mov     [rsp+1500h+var_1498], r12
0x180002769  xorps   xmm0, xmm0
0x18000276c  xor     eax, eax
0x18000276e  movups  [rbp+1400h+var_1478], xmm0
0x180002772  mov     [rbp+1400h+var_1468], rax
0x180002776  xorps   xmm1, xmm1
0x180002779  movups  [rsp+1500h+var_1490], xmm1
0x18000277e  mov     [rbp+1400h+var_1480], rax
0x180002782  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002789  test    rax, rax
0x18000278c  jz      short loc_180002799
0x18000278e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002793  mov     [rbp+1400h+var_1460], rax
0x180002797  jmp     short loc_18000279D
0x180002799  mov     [rbp+1400h+var_1460], r12
0x18000279d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800027a4  test    rax, rax
0x1800027a7  jz      short loc_1800027B3
0x1800027a9  lea     rcx, [rsp+1500h+var_14E0]
0x1800027ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027b3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800027ba  test    rax, rax
0x1800027bd  jz      short loc_1800027D3
0x1800027bf  mov     r8d, 400h
0x1800027c5  lea     rdx, [rbp+1400h+var_1440]
0x1800027c9  lea     rcx, [rsp+1500h+var_14E0]
0x1800027ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027d3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800027da  test    rax, rax
0x1800027dd  jz      short loc_1800027E9
0x1800027df  lea     rcx, [rsp+1500h+var_14E0]
0x1800027e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027e9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800027f0  test    rax, rax
0x1800027f3  jz      short loc_180002806
0x1800027f5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800027fa  jnz     short loc_180002806
0x1800027fc  lea     rcx, [rsp+1500h+var_14E0]
0x180002801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002806  cmp     [rsp+1500h+var_14D8], r12d
0x18000280b  jge     loc_180002914
0x180002811  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002818  jnz     short loc_180002839
0x18000281a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002821  test    rax, rax
0x180002824  jz      short loc_18000282F
0x180002826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000282b  test    al, al
0x18000282d  jmp     short loc_180002837
0x18000282f  call    cs:__imp_IsDebuggerPresent
0x180002835  test    eax, eax
0x180002837  jz      short loc_180002840
0x180002839  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000283e  jz      short loc_180002866
0x180002840  mov     rax, cs:g_pfnResultLoggingCallback
0x180002847  test    rax, rax
0x18000284a  jz      short loc_1800028BF
0x18000284c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002853  jnz     short loc_1800028BF
0x180002855  xor     r8d, r8d
0x180002858  xor     edx, edx
0x18000285a  lea     rcx, [rsp+1500h+var_14E0]
0x18000285f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002864  jmp     short loc_1800028BF
0x180002866  mov     ebx, 800h
0x18000286b  mov     rax, cs:g_pfnResultLoggingCallback
0x180002872  test    rax, rax
0x180002875  jz      short loc_180002894
0x180002877  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000287e  jnz     short loc_180002894
0x180002880  mov     r8d, ebx
0x180002883  lea     rdx, [rbp+1400h+OutputString]
0x18000288a  lea     rcx, [rsp+1500h+var_14E0]
0x18000288f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002894  cmp     [rbp+1400h+OutputString], r12w
0x18000289c  jnz     short loc_1800028B2
0x18000289e  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800028a3  mov     rdx, rbx; unsigned __int16 *
0x1800028a6  lea     rcx, [rbp+1400h+OutputString]; this
0x1800028ad  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800028b2  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800028b9  call    cs:__imp_OutputDebugStringW
0x1800028bf  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800028c4  jnz     short loc_1800028CF
0x1800028c6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800028cd  jz      short loc_1800028E1
0x1800028cf  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800028d6  test    rax, rax
0x1800028d9  jz      short loc_1800028E1
0x1800028db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028e0  nop
0x1800028e1  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800028e6  jnz     short loc_180002909
0x1800028e8  mov     rcx, [rbp+1400h+var_40]
0x1800028ef  xor     rcx, rsp; StackCookie
0x1800028f2  call    __security_check_cookie
0x1800028f7  add     rsp, 14D0h
0x1800028fe  pop     r15
0x180002900  pop     r14
0x180002902  pop     r12
0x180002904  pop     rdi
0x180002905  pop     rsi
0x180002906  pop     rbx
0x180002907  pop     rbp
0x180002908  retn
0x180002909  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000290e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002914  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
