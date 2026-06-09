# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003664`
- end: `0x18000390a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800030f8`

## callees

- `0x180003664`
- `0x1800049a4`
- `0x180005ae0`
- `0x180006c80`
- `0x180006f00`
- `0x18002bc62`
- `0x18002bca0`
- `0x18002bd60`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000372a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000372a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000381f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000381f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800038a9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800038a9`

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
0x180003664  push    rbp
0x180003666  push    rbx
0x180003667  push    rsi
0x180003668  push    rdi
0x180003669  push    r12
0x18000366b  push    r14
0x18000366d  push    r15
0x18000366f  lea     rbp, [rsp-13D0h]
0x180003677  mov     eax, 14D0h
0x18000367c  call    _alloca_probe
0x180003681  sub     rsp, rax
0x180003684  mov     rax, cs:__security_cookie
0x18000368b  xor     rax, rsp
0x18000368e  mov     [rbp+1400h+var_40], rax
0x180003695  mov     rsi, r8
0x180003698  mov     edi, edx
0x18000369a  mov     rbx, rcx
0x18000369d  mov     r14, [rbp+1400h+arg_28]
0x1800036a4  xor     edx, edx; Val
0x1800036a6  mov     r8d, 98h; Size
0x1800036ac  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800036b1  call    memset_0
0x1800036b6  nop
0x1800036b7  xor     r12d, r12d
0x1800036ba  mov     [rbp+1400h+OutputString], r12w
0x1800036c2  mov     [rbp+1400h+var_1440], r12b
0x1800036c6  mov     rdx, [rbp+1400h+arg_30]; int
0x1800036cd  mov     ecx, [rdx]; this
0x1800036cf  mov     [rsp+1500h+var_14D8], ecx
0x1800036d3  mov     eax, [rdx+4]
0x1800036d6  mov     [rsp+1500h+var_14D4], eax
0x1800036da  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800036df  mov     r15d, eax
0x1800036e2  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800036ea  mov     ecx, r12d
0x1800036ed  lea     eax, [r12+8]
0x1800036f2  cmp     dword ptr [rdx+8], 1
0x1800036f6  cmovz   ecx, eax
0x1800036f9  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800036fd  lea     ecx, [rax-7]
0x180003700  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003708  inc     ecx
0x18000370a  mov     [rsp+1500h+var_14D0], ecx
0x18000370e  mov     rcx, [rbp+1400h+arg_38]
0x180003715  test    rcx, rcx
0x180003718  jz      short loc_180003725
0x18000371a  cmp     [rcx], r12w
0x18000371e  mov     [rsp+1500h+var_14C8], rcx
0x180003723  jnz     short loc_18000372A
0x180003725  mov     [rsp+1500h+var_14C8], r12
0x18000372a  call    cs:__imp_GetCurrentThreadId
0x180003730  mov     [rsp+1500h+var_14C0], eax
0x180003734  mov     [rsp+1500h+var_14A8], rsi
0x180003739  mov     [rsp+1500h+var_14A0], edi
0x18000373d  mov     [rsp+1500h+var_149C], r15d
0x180003742  mov     [rsp+1500h+var_14B8], r12
0x180003747  mov     [rsp+1500h+var_14B0], r12
0x18000374c  mov     [rbp+1400h+var_1458], r14
0x180003750  mov     [rbp+1400h+var_1450], rbx
0x180003754  mov     [rsp+1500h+var_1498], r12
0x180003759  xorps   xmm0, xmm0
0x18000375c  xor     eax, eax
0x18000375e  movups  [rbp+1400h+var_1478], xmm0
0x180003762  mov     [rbp+1400h+var_1468], rax
0x180003766  xorps   xmm1, xmm1
0x180003769  movups  [rsp+1500h+var_1490], xmm1
0x18000376e  mov     [rbp+1400h+var_1480], rax
0x180003772  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003779  test    rax, rax
0x18000377c  jz      short loc_180003789
0x18000377e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003783  mov     [rbp+1400h+var_1460], rax
0x180003787  jmp     short loc_18000378D
0x180003789  mov     [rbp+1400h+var_1460], r12
0x18000378d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003794  test    rax, rax
0x180003797  jz      short loc_1800037A3
0x180003799  lea     rcx, [rsp+1500h+var_14E0]
0x18000379e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037a3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800037aa  test    rax, rax
0x1800037ad  jz      short loc_1800037C3
0x1800037af  mov     r8d, 400h
0x1800037b5  lea     rdx, [rbp+1400h+var_1440]
0x1800037b9  lea     rcx, [rsp+1500h+var_14E0]
0x1800037be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037c3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800037ca  test    rax, rax
0x1800037cd  jz      short loc_1800037D9
0x1800037cf  lea     rcx, [rsp+1500h+var_14E0]
0x1800037d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037d9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800037e0  test    rax, rax
0x1800037e3  jz      short loc_1800037F6
0x1800037e5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800037ea  jnz     short loc_1800037F6
0x1800037ec  lea     rcx, [rsp+1500h+var_14E0]
0x1800037f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037f6  cmp     [rsp+1500h+var_14D8], r12d
0x1800037fb  jge     loc_180003904
0x180003801  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003808  jnz     short loc_180003829
0x18000380a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003811  test    rax, rax
0x180003814  jz      short loc_18000381F
0x180003816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000381b  test    al, al
0x18000381d  jmp     short loc_180003827
0x18000381f  call    cs:__imp_IsDebuggerPresent
0x180003825  test    eax, eax
0x180003827  jz      short loc_180003830
0x180003829  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000382e  jz      short loc_180003856
0x180003830  mov     rax, cs:g_pfnResultLoggingCallback
0x180003837  test    rax, rax
0x18000383a  jz      short loc_1800038AF
0x18000383c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003843  jnz     short loc_1800038AF
0x180003845  xor     r8d, r8d
0x180003848  xor     edx, edx
0x18000384a  lea     rcx, [rsp+1500h+var_14E0]
0x18000384f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003854  jmp     short loc_1800038AF
0x180003856  mov     ebx, 800h
0x18000385b  mov     rax, cs:g_pfnResultLoggingCallback
0x180003862  test    rax, rax
0x180003865  jz      short loc_180003884
0x180003867  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000386e  jnz     short loc_180003884
0x180003870  mov     r8d, ebx
0x180003873  lea     rdx, [rbp+1400h+OutputString]
0x18000387a  lea     rcx, [rsp+1500h+var_14E0]
0x18000387f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003884  cmp     [rbp+1400h+OutputString], r12w
0x18000388c  jnz     short loc_1800038A2
0x18000388e  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003893  mov     rdx, rbx; unsigned __int16 *
0x180003896  lea     rcx, [rbp+1400h+OutputString]; this
0x18000389d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800038a2  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800038a9  call    cs:__imp_OutputDebugStringW
0x1800038af  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800038b4  jnz     short loc_1800038BF
0x1800038b6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800038bd  jz      short loc_1800038D1
0x1800038bf  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800038c6  test    rax, rax
0x1800038c9  jz      short loc_1800038D1
0x1800038cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038d0  nop
0x1800038d1  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800038d6  jnz     short loc_1800038F9
0x1800038d8  mov     rcx, [rbp+1400h+var_40]
0x1800038df  xor     rcx, rsp; StackCookie
0x1800038e2  call    __security_check_cookie
0x1800038e7  add     rsp, 14D0h
0x1800038ee  pop     r15
0x1800038f0  pop     r14
0x1800038f2  pop     r12
0x1800038f4  pop     rdi
0x1800038f5  pop     rsi
0x1800038f6  pop     rbx
0x1800038f7  pop     rbp
0x1800038f8  retn
0x1800038f9  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800038fe  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003904  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
