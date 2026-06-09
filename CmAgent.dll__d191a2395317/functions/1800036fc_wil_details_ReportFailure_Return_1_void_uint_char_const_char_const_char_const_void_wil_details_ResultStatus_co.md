# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800036fc`
- end: `0x1800039b5`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800032ac`

## callees

- `0x180002140`
- `0x180002c48`
- `0x1800036fc`
- `0x180003df4`
- `0x1800045c4`
- `0x18000478c`
- `0x180004924`
- `0x180036130`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800037c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800037c2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000394d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000394d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800038bd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800038bd`

## pseudocode

```c
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
0x1800036fc  push    rbp
0x1800036fe  push    rbx
0x1800036ff  push    rsi
0x180003700  push    rdi
0x180003701  push    r12
0x180003703  push    r14
0x180003705  push    r15
0x180003707  lea     rbp, [rsp-13D0h]
0x18000370f  mov     eax, 14D0h
0x180003714  call    _alloca_probe
0x180003719  sub     rsp, rax
0x18000371c  mov     rax, cs:__security_cookie
0x180003723  xor     rax, rsp
0x180003726  mov     [rbp+1400h+var_40], rax
0x18000372d  mov     rsi, r8
0x180003730  mov     edi, edx
0x180003732  mov     rbx, rcx
0x180003735  mov     r14, [rbp+1400h+arg_28]
0x18000373c  xor     edx, edx; Val
0x18000373e  mov     r8d, 98h; Size
0x180003744  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003749  call    memset_0
0x18000374e  nop
0x18000374f  xor     r12d, r12d
0x180003752  mov     [rbp+1400h+OutputString], r12w
0x18000375a  mov     [rbp+1400h+var_1440], r12b
0x18000375e  mov     rdx, [rbp+1400h+arg_30]; int
0x180003765  mov     ecx, [rdx]; this
0x180003767  mov     [rsp+1500h+var_14D8], ecx
0x18000376b  mov     eax, [rdx+4]
0x18000376e  mov     [rsp+1500h+var_14D4], eax
0x180003772  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003777  mov     r15d, eax
0x18000377a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003782  mov     ecx, r12d
0x180003785  lea     eax, [r12+8]
0x18000378a  cmp     dword ptr [rdx+8], 1
0x18000378e  cmovz   ecx, eax
0x180003791  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003795  lea     ecx, [rax-7]
0x180003798  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800037a0  inc     ecx
0x1800037a2  mov     [rsp+1500h+var_14D0], ecx
0x1800037a6  mov     rcx, [rbp+1400h+arg_38]
0x1800037ad  test    rcx, rcx
0x1800037b0  jz      short loc_1800037BD
0x1800037b2  cmp     [rcx], r12w
0x1800037b6  mov     [rsp+1500h+var_14C8], rcx
0x1800037bb  jnz     short loc_1800037C2
0x1800037bd  mov     [rsp+1500h+var_14C8], r12
0x1800037c2  call    cs:__imp_GetCurrentThreadId
0x1800037c9  nop     dword ptr [rax+rax+00h]
0x1800037ce  mov     [rsp+1500h+var_14C0], eax
0x1800037d2  mov     [rsp+1500h+var_14A8], rsi
0x1800037d7  mov     [rsp+1500h+var_14A0], edi
0x1800037db  mov     [rsp+1500h+var_149C], r15d
0x1800037e0  mov     [rsp+1500h+var_14B8], r12
0x1800037e5  mov     [rsp+1500h+var_14B0], r12
0x1800037ea  mov     [rbp+1400h+var_1458], r14
0x1800037ee  mov     [rbp+1400h+var_1450], rbx
0x1800037f2  mov     [rsp+1500h+var_1498], r12
0x1800037f7  xorps   xmm0, xmm0
0x1800037fa  xor     eax, eax
0x1800037fc  movups  [rbp+1400h+var_1478], xmm0
0x180003800  mov     [rbp+1400h+var_1468], rax
0x180003804  xorps   xmm1, xmm1
0x180003807  movups  [rsp+1500h+var_1490], xmm1
0x18000380c  mov     [rbp+1400h+var_1480], rax
0x180003810  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003817  test    rax, rax
0x18000381a  jz      short loc_180003827
0x18000381c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003821  mov     [rbp+1400h+var_1460], rax
0x180003825  jmp     short loc_18000382B
0x180003827  mov     [rbp+1400h+var_1460], r12
0x18000382b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003832  test    rax, rax
0x180003835  jz      short loc_180003841
0x180003837  lea     rcx, [rsp+1500h+var_14E0]
0x18000383c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003841  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003848  test    rax, rax
0x18000384b  jz      short loc_180003861
0x18000384d  mov     r8d, 400h
0x180003853  lea     rdx, [rbp+1400h+var_1440]
0x180003857  lea     rcx, [rsp+1500h+var_14E0]
0x18000385c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003861  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003868  test    rax, rax
0x18000386b  jz      short loc_180003877
0x18000386d  lea     rcx, [rsp+1500h+var_14E0]
0x180003872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003877  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000387e  test    rax, rax
0x180003881  jz      short loc_180003894
0x180003883  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003888  jnz     short loc_180003894
0x18000388a  lea     rcx, [rsp+1500h+var_14E0]
0x18000388f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003894  cmp     [rsp+1500h+var_14D8], r12d
0x180003899  jge     loc_1800039AF
0x18000389f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800038a6  jnz     short loc_1800038CD
0x1800038a8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800038af  test    rax, rax
0x1800038b2  jz      short loc_1800038BD
0x1800038b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038b9  test    al, al
0x1800038bb  jmp     short loc_1800038CB
0x1800038bd  call    cs:__imp_IsDebuggerPresent
0x1800038c4  nop     dword ptr [rax+rax+00h]
0x1800038c9  test    eax, eax
0x1800038cb  jz      short loc_1800038D4
0x1800038cd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800038d2  jz      short loc_1800038FA
0x1800038d4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800038db  test    rax, rax
0x1800038de  jz      short loc_180003959
0x1800038e0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800038e7  jnz     short loc_180003959
0x1800038e9  xor     r8d, r8d
0x1800038ec  xor     edx, edx
0x1800038ee  lea     rcx, [rsp+1500h+var_14E0]
0x1800038f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038f8  jmp     short loc_180003959
0x1800038fa  mov     ebx, 800h
0x1800038ff  mov     rax, cs:g_pfnResultLoggingCallback
0x180003906  test    rax, rax
0x180003909  jz      short loc_180003928
0x18000390b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003912  jnz     short loc_180003928
0x180003914  mov     r8d, ebx
0x180003917  lea     rdx, [rbp+1400h+OutputString]
0x18000391e  lea     rcx, [rsp+1500h+var_14E0]
0x180003923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003928  cmp     [rbp+1400h+OutputString], r12w
0x180003930  jnz     short loc_180003946
0x180003932  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003937  mov     rdx, rbx; unsigned __int16 *
0x18000393a  lea     rcx, [rbp+1400h+OutputString]; this
0x180003941  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003946  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000394d  call    cs:__imp_OutputDebugStringW
0x180003954  nop     dword ptr [rax+rax+00h]
0x180003959  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000395e  jnz     short loc_180003969
0x180003960  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003967  jz      short loc_18000397B
0x180003969  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003970  test    rax, rax
0x180003973  jz      short loc_18000397B
0x180003975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000397a  nop
0x18000397b  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003980  jnz     short loc_1800039A4
0x180003982  mov     rcx, [rbp+1400h+var_40]
0x180003989  xor     rcx, rsp; StackCookie
0x18000398c  call    __security_check_cookie
0x180003991  add     rsp, 14D0h
0x180003998  pop     r15
0x18000399a  pop     r14
0x18000399c  pop     r12
0x18000399e  pop     rdi
0x18000399f  pop     rsi
0x1800039a0  pop     rbx
0x1800039a1  pop     rbp
0x1800039a2  retn
0x1800039a4  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800039a9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800039af  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
