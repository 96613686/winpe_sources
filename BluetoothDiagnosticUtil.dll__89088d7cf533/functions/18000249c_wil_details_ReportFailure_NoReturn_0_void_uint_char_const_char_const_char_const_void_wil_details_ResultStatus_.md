# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000249c`
- end: `0x180002761`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180001dcc`

## callees

- `0x18000249c`
- `0x180005304`
- `0x180006cd4`
- `0x180007ad0`
- `0x180007e7c`
- `0x180008058`
- `0x180009c5e`
- `0x180009d50`
- `0x18000b010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x1800026ef`
- `KERNEL32!OutputDebugStringW` at `0x1800026ef`
- `KERNEL32!IsDebuggerPresent` at `0x18000264d`
- `KERNEL32!IsDebuggerPresent` at `0x18000264d`
- `KERNEL32!GetCurrentThreadId` at `0x180002545`
- `KERNEL32!GetCurrentThreadId` at `0x180002545`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v9; // r15
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  char v17; // bl
  const struct wil::FailureInfo *v18; // rdx
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v9 = g_pfnThrowPlatformException != 0;
  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v21 = *a7;
  v22 = a7[1];
  v10 = wil::details::RecordException((wil::details *)(unsigned int)v21, (int)a7);
  v19 = 0;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v20 = v11;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v24 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v28 = "base\\diagnosis\\pdi\\scripteddiag\\packages\\bluetooth\\bluetoothdiagnosticutil\\bluetoothdiagnosticutil.cpp";
  v29 = a2;
  v30 = v10;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v35 = 0;
  v32 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && !v9 && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v17 = 1, (v20 & 2) != 0) )
  {
    v17 = 0;
  }
  if ( v9 || v17 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048, v15);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v19, v15);
    if ( v17 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v19, 0, 0, v15);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v13);
  if ( v9 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v19, OutputString);
  wil::ThrowResultException((wil *)&v19, v13);
  wil::details::WilFailFast((wil::details *)&v19, v18);
}

```

## disassembly

```asm
0x18000249c  mov     [rsp-8+arg_10], rbx
0x1800024a1  mov     [rsp-8+arg_18], rsi
0x1800024a6  push    rbp
0x1800024a7  push    rdi
0x1800024a8  push    r12
0x1800024aa  push    r14
0x1800024ac  push    r15
0x1800024ae  lea     rbp, [rsp-13C0h]
0x1800024b6  mov     eax, 14C0h
0x1800024bb  call    _alloca_probe
0x1800024c0  sub     rsp, rax
0x1800024c3  mov     esi, edx
0x1800024c5  mov     r14, rcx
0x1800024c8  mov     rdi, [rbp+13E0h+arg_28]
0x1800024cf  xor     r12d, r12d
0x1800024d2  cmp     cs:g_pfnThrowPlatformException, r12
0x1800024d9  setnz   r15b
0x1800024dd  xor     edx, edx; Val
0x1800024df  mov     r8d, 98h; Size
0x1800024e5  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x1800024ea  call    memset_0
0x1800024ef  nop
0x1800024f0  mov     [rbp+13E0h+OutputString], r12w
0x1800024f8  mov     [rbp+13E0h+var_1420], r12b
0x1800024fc  mov     rdx, qword ptr [rbp+13E0h+arg_30]; int
0x180002503  mov     ecx, [rdx]; this
0x180002505  mov     [rsp+14E0h+var_14B8], ecx
0x180002509  mov     eax, [rdx+4]
0x18000250c  mov     [rsp+14E0h+var_14B4], eax
0x180002510  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180002515  mov     ebx, eax
0x180002517  mov     dword ptr [rsp+14E0h+var_14C0], r12d
0x18000251c  mov     ecx, r12d
0x18000251f  lea     eax, [r12+8]
0x180002524  cmp     dword ptr [rdx+8], 1
0x180002528  cmovz   ecx, eax
0x18000252b  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x18000252f  lea     ecx, [rax-7]
0x180002532  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000253a  inc     ecx
0x18000253c  mov     [rsp+14E0h+var_14B0], ecx
0x180002540  mov     [rsp+14E0h+var_14A8], r12
0x180002545  call    cs:__imp_GetCurrentThreadId
0x18000254c  nop     dword ptr [rax+rax+00h]
0x180002551  mov     [rsp+14E0h+var_14A0], eax
0x180002555  lea     rax, aBaseDiagnosisP; "base\\diagnosis\\pdi\\scripteddiag\\pac"...
0x18000255c  mov     [rsp+14E0h+var_1488], rax
0x180002561  mov     [rsp+14E0h+var_1480], esi
0x180002565  mov     [rsp+14E0h+var_147C], ebx
0x180002569  mov     [rsp+14E0h+var_1498], r12
0x18000256e  mov     [rsp+14E0h+var_1490], r12
0x180002573  mov     [rbp+13E0h+var_1438], rdi
0x180002577  mov     [rbp+13E0h+var_1430], r14
0x18000257b  mov     [rsp+14E0h+var_1478], r12
0x180002580  xorps   xmm0, xmm0
0x180002583  xor     eax, eax
0x180002585  movups  [rbp+13E0h+var_1458], xmm0
0x180002589  mov     [rbp+13E0h+var_1448], rax
0x18000258d  xorps   xmm1, xmm1
0x180002590  movups  [rsp+14E0h+var_1470], xmm1
0x180002595  mov     [rbp+13E0h+var_1460], rax
0x180002599  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800025a0  test    rax, rax
0x1800025a3  jz      short loc_1800025B0
0x1800025a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025aa  mov     [rbp+13E0h+var_1440], rax
0x1800025ae  jmp     short loc_1800025B4
0x1800025b0  mov     [rbp+13E0h+var_1440], r12
0x1800025b4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800025bb  test    rax, rax
0x1800025be  jz      short loc_1800025CA
0x1800025c0  lea     rcx, [rsp+14E0h+var_14C0]
0x1800025c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025ca  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800025d1  test    rax, rax
0x1800025d4  jz      short loc_1800025EA
0x1800025d6  mov     r8d, 400h
0x1800025dc  lea     rdx, [rbp+13E0h+var_1420]
0x1800025e0  lea     rcx, [rsp+14E0h+var_14C0]
0x1800025e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025ea  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800025f1  test    rax, rax
0x1800025f4  jz      short loc_180002600
0x1800025f6  lea     rcx, [rsp+14E0h+var_14C0]
0x1800025fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002600  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002607  test    rax, rax
0x18000260a  jz      short loc_180002622
0x18000260c  test    r15b, r15b
0x18000260f  jnz     short loc_180002622
0x180002611  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002616  jnz     short loc_180002622
0x180002618  lea     rcx, [rsp+14E0h+var_14C0]
0x18000261d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002622  cmp     [rsp+14E0h+var_14B8], r12d
0x180002627  jl      short loc_18000262F
0x180002629  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000262f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002636  jnz     short loc_18000265D
0x180002638  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000263f  test    rax, rax
0x180002642  jz      short loc_18000264D
0x180002644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002649  test    al, al
0x18000264b  jmp     short loc_18000265B
0x18000264d  call    cs:__imp_IsDebuggerPresent
0x180002654  nop     dword ptr [rax+rax+00h]
0x180002659  test    eax, eax
0x18000265b  jz      short loc_180002666
0x18000265d  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002662  mov     bl, 1
0x180002664  jz      short loc_180002669
0x180002666  mov     bl, r12b
0x180002669  test    r15b, r15b
0x18000266c  jnz     short loc_180002698
0x18000266e  test    bl, bl
0x180002670  jnz     short loc_180002698
0x180002672  mov     rax, cs:g_pfnResultLoggingCallback
0x180002679  test    rax, rax
0x18000267c  jz      short loc_1800026FB
0x18000267e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002685  jnz     short loc_1800026FB
0x180002687  xor     r8d, r8d
0x18000268a  xor     edx, edx
0x18000268c  lea     rcx, [rsp+14E0h+var_14C0]
0x180002691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002696  jmp     short loc_1800026FB
0x180002698  mov     edi, 800h
0x18000269d  mov     rax, cs:g_pfnResultLoggingCallback
0x1800026a4  test    rax, rax
0x1800026a7  jz      short loc_1800026C6
0x1800026a9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800026b0  jnz     short loc_1800026C6
0x1800026b2  mov     r8d, edi
0x1800026b5  lea     rdx, [rbp+13E0h+OutputString]
0x1800026bc  lea     rcx, [rsp+14E0h+var_14C0]
0x1800026c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026c6  cmp     [rbp+13E0h+OutputString], r12w
0x1800026ce  jnz     short loc_1800026E4
0x1800026d0  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x1800026d5  mov     rdx, rdi; unsigned __int16 *
0x1800026d8  lea     rcx, [rbp+13E0h+OutputString]; this
0x1800026df  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800026e4  test    bl, bl
0x1800026e6  jz      short loc_1800026FB
0x1800026e8  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x1800026ef  call    cs:__imp_OutputDebugStringW
0x1800026f6  nop     dword ptr [rax+rax+00h]
0x1800026fb  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180002700  jnz     short loc_18000270B
0x180002702  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002709  jz      short loc_18000271D
0x18000270b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002712  test    rax, rax
0x180002715  jz      short loc_18000271D
0x180002717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000271c  nop
0x18000271d  test    byte ptr [rsp+14E0h+var_14C0+4], 1
0x180002722  jz      short loc_18000272F
0x180002724  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180002729  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000272f  test    r15b, r15b
0x180002732  jz      short loc_18000274C
0x180002734  lea     rdx, [rbp+13E0h+OutputString]
0x18000273b  lea     rcx, [rsp+14E0h+var_14C0]
0x180002740  mov     rax, cs:g_pfnThrowPlatformException
0x180002747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000274c  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180002751  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180002756  lea     rcx, [rsp+14E0h+var_14C0]; this
0x18000275b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
