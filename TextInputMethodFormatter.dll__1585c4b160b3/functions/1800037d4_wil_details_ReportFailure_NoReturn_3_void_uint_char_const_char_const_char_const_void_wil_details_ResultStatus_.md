# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800037d4`
- end: `0x180003a4d`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003544`

## callees

- `0x180002db8`
- `0x1800037d4`
- `0x1800054d4`
- `0x180005f24`
- `0x180006770`
- `0x1800078c0`
- `0x180056f80`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000388d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000388d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003a1a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003a1a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003990`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003990`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
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
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x1800037d4  mov     [rsp-8+arg_18], rbx
0x1800037d9  push    rbp
0x1800037da  push    rsi
0x1800037db  push    rdi
0x1800037dc  push    r12
0x1800037de  push    r13
0x1800037e0  push    r14
0x1800037e2  push    r15
0x1800037e4  lea     rbp, [rsp-13C0h]
0x1800037ec  mov     eax, 14C0h
0x1800037f1  call    _alloca_probe
0x1800037f6  sub     rsp, rax
0x1800037f9  mov     r14, r8
0x1800037fc  mov     esi, edx
0x1800037fe  mov     rdi, rcx
0x180003801  mov     r15, [rbp+13F0h+arg_28]
0x180003808  xor     edx, edx; Val
0x18000380a  mov     r8d, 98h; Size
0x180003810  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003815  call    memset_0
0x18000381a  nop
0x18000381b  xor     r13d, r13d
0x18000381e  mov     [rbp+13F0h+OutputString], r13w
0x180003826  mov     [rbp+13F0h+var_1430], r13b
0x18000382a  mov     rbx, [rbp+13F0h+arg_30]
0x180003831  mov     ecx, [rbx]; this
0x180003833  mov     [rsp+14F0h+var_14C8], ecx
0x180003837  mov     eax, [rbx+4]
0x18000383a  mov     [rsp+14F0h+var_14C4], eax
0x18000383e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003843  mov     r12d, eax
0x180003846  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000384e  mov     ecx, r13d
0x180003851  lea     eax, [r13+8]
0x180003855  cmp     dword ptr [rbx+8], 1
0x180003859  cmovz   ecx, eax
0x18000385c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003860  lea     ecx, [rax-7]
0x180003863  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000386b  inc     ecx
0x18000386d  mov     [rsp+14F0h+var_14C0], ecx
0x180003871  mov     rcx, [rbp+13F0h+arg_38]
0x180003878  test    rcx, rcx
0x18000387b  jz      short loc_180003888
0x18000387d  cmp     [rcx], r13w
0x180003881  mov     [rsp+14F0h+var_14B8], rcx
0x180003886  jnz     short loc_18000388D
0x180003888  mov     [rsp+14F0h+var_14B8], r13
0x18000388d  call    cs:__imp_GetCurrentThreadId
0x180003893  mov     [rsp+14F0h+var_14B0], eax
0x180003897  mov     [rsp+14F0h+var_1498], r14
0x18000389c  mov     [rsp+14F0h+var_1490], esi
0x1800038a0  mov     [rsp+14F0h+var_148C], r12d
0x1800038a5  mov     [rsp+14F0h+var_14A8], r13
0x1800038aa  mov     [rsp+14F0h+var_14A0], r13
0x1800038af  mov     [rbp+13F0h+var_1448], r15
0x1800038b3  mov     [rbp+13F0h+var_1440], rdi
0x1800038b7  mov     [rsp+14F0h+var_1488], r13
0x1800038bc  xorps   xmm0, xmm0
0x1800038bf  xor     eax, eax
0x1800038c1  movups  [rbp+13F0h+var_1468], xmm0
0x1800038c5  mov     [rbp+13F0h+var_1458], rax
0x1800038c9  xorps   xmm1, xmm1
0x1800038cc  movups  [rsp+14F0h+var_1480], xmm1
0x1800038d1  mov     [rbp+13F0h+var_1470], rax
0x1800038d5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800038dc  test    rax, rax
0x1800038df  jz      short loc_1800038EC
0x1800038e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038e6  mov     [rbp+13F0h+var_1450], rax
0x1800038ea  jmp     short loc_1800038F0
0x1800038ec  mov     [rbp+13F0h+var_1450], r13
0x1800038f0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800038f7  test    rax, rax
0x1800038fa  jz      short loc_180003906
0x1800038fc  lea     rcx, [rsp+14F0h+var_14D0]
0x180003901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003906  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000390d  test    rax, rax
0x180003910  jz      short loc_180003926
0x180003912  mov     r8d, 400h
0x180003918  lea     rdx, [rbp+13F0h+var_1430]
0x18000391c  lea     rcx, [rsp+14F0h+var_14D0]
0x180003921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003926  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000392d  test    rax, rax
0x180003930  jz      short loc_18000393C
0x180003932  lea     rcx, [rsp+14F0h+var_14D0]
0x180003937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000393c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003943  test    rax, rax
0x180003946  jz      short loc_180003959
0x180003948  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000394d  jnz     short loc_180003959
0x18000394f  lea     rcx, [rsp+14F0h+var_14D0]
0x180003954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003959  cmp     [rsp+14F0h+var_14C8], r13d
0x18000395e  jl      short loc_180003972
0x180003960  mov     ecx, 8000FFFFh; this
0x180003965  mov     [rsp+14F0h+var_14C8], ecx
0x180003969  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000396e  mov     [rsp+14F0h+var_14C4], eax
0x180003972  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180003979  jnz     short loc_18000399A
0x18000397b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003982  test    rax, rax
0x180003985  jz      short loc_180003990
0x180003987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000398c  test    al, al
0x18000398e  jmp     short loc_180003998
0x180003990  call    cs:__imp_IsDebuggerPresent
0x180003996  test    eax, eax
0x180003998  jz      short loc_1800039A1
0x18000399a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000399f  jz      short loc_1800039C7
0x1800039a1  mov     rax, cs:g_pfnResultLoggingCallback
0x1800039a8  test    rax, rax
0x1800039ab  jz      short loc_180003A20
0x1800039ad  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800039b4  jnz     short loc_180003A20
0x1800039b6  xor     r8d, r8d
0x1800039b9  xor     edx, edx
0x1800039bb  lea     rcx, [rsp+14F0h+var_14D0]
0x1800039c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039c5  jmp     short loc_180003A20
0x1800039c7  mov     ebx, 800h
0x1800039cc  mov     rax, cs:g_pfnResultLoggingCallback
0x1800039d3  test    rax, rax
0x1800039d6  jz      short loc_1800039F5
0x1800039d8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800039df  jnz     short loc_1800039F5
0x1800039e1  mov     r8d, ebx
0x1800039e4  lea     rdx, [rbp+13F0h+OutputString]
0x1800039eb  lea     rcx, [rsp+14F0h+var_14D0]
0x1800039f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039f5  cmp     [rbp+13F0h+OutputString], r13w
0x1800039fd  jnz     short loc_180003A13
0x1800039ff  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003a04  mov     rdx, rbx; unsigned __int16 *
0x180003a07  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003a0e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003a13  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003a1a  call    cs:__imp_OutputDebugStringW
0x180003a20  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003a25  jnz     short loc_180003A30
0x180003a27  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180003a2e  jz      short loc_180003A42
0x180003a30  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003a37  test    rax, rax
0x180003a3a  jz      short loc_180003A42
0x180003a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a41  nop
0x180003a42  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003a47  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
