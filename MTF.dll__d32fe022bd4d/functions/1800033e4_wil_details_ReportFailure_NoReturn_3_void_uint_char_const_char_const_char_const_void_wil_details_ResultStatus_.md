# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800033e4`
- end: `0x18000365d`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003154`

## callees

- `0x1800033e4`
- `0x1800049a4`
- `0x1800051f0`
- `0x180005ab0`
- `0x180006c80`
- `0x18002bc62`
- `0x18002bd60`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000349d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000349d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800035a0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800035a0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000362a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000362a`

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
0x1800033e4  mov     [rsp-8+arg_18], rbx
0x1800033e9  push    rbp
0x1800033ea  push    rsi
0x1800033eb  push    rdi
0x1800033ec  push    r12
0x1800033ee  push    r13
0x1800033f0  push    r14
0x1800033f2  push    r15
0x1800033f4  lea     rbp, [rsp-13C0h]
0x1800033fc  mov     eax, 14C0h
0x180003401  call    _alloca_probe
0x180003406  sub     rsp, rax
0x180003409  mov     r14, r8
0x18000340c  mov     esi, edx
0x18000340e  mov     rdi, rcx
0x180003411  mov     r15, [rbp+13F0h+arg_28]
0x180003418  xor     edx, edx; Val
0x18000341a  mov     r8d, 98h; Size
0x180003420  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003425  call    memset_0
0x18000342a  nop
0x18000342b  xor     r13d, r13d
0x18000342e  mov     [rbp+13F0h+OutputString], r13w
0x180003436  mov     [rbp+13F0h+var_1430], r13b
0x18000343a  mov     rbx, [rbp+13F0h+arg_30]
0x180003441  mov     ecx, [rbx]; this
0x180003443  mov     [rsp+14F0h+var_14C8], ecx
0x180003447  mov     eax, [rbx+4]
0x18000344a  mov     [rsp+14F0h+var_14C4], eax
0x18000344e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003453  mov     r12d, eax
0x180003456  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000345e  mov     ecx, r13d
0x180003461  lea     eax, [r13+8]
0x180003465  cmp     dword ptr [rbx+8], 1
0x180003469  cmovz   ecx, eax
0x18000346c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003470  lea     ecx, [rax-7]
0x180003473  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000347b  inc     ecx
0x18000347d  mov     [rsp+14F0h+var_14C0], ecx
0x180003481  mov     rcx, [rbp+13F0h+arg_38]
0x180003488  test    rcx, rcx
0x18000348b  jz      short loc_180003498
0x18000348d  cmp     [rcx], r13w
0x180003491  mov     [rsp+14F0h+var_14B8], rcx
0x180003496  jnz     short loc_18000349D
0x180003498  mov     [rsp+14F0h+var_14B8], r13
0x18000349d  call    cs:__imp_GetCurrentThreadId
0x1800034a3  mov     [rsp+14F0h+var_14B0], eax
0x1800034a7  mov     [rsp+14F0h+var_1498], r14
0x1800034ac  mov     [rsp+14F0h+var_1490], esi
0x1800034b0  mov     [rsp+14F0h+var_148C], r12d
0x1800034b5  mov     [rsp+14F0h+var_14A8], r13
0x1800034ba  mov     [rsp+14F0h+var_14A0], r13
0x1800034bf  mov     [rbp+13F0h+var_1448], r15
0x1800034c3  mov     [rbp+13F0h+var_1440], rdi
0x1800034c7  mov     [rsp+14F0h+var_1488], r13
0x1800034cc  xorps   xmm0, xmm0
0x1800034cf  xor     eax, eax
0x1800034d1  movups  [rbp+13F0h+var_1468], xmm0
0x1800034d5  mov     [rbp+13F0h+var_1458], rax
0x1800034d9  xorps   xmm1, xmm1
0x1800034dc  movups  [rsp+14F0h+var_1480], xmm1
0x1800034e1  mov     [rbp+13F0h+var_1470], rax
0x1800034e5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800034ec  test    rax, rax
0x1800034ef  jz      short loc_1800034FC
0x1800034f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034f6  mov     [rbp+13F0h+var_1450], rax
0x1800034fa  jmp     short loc_180003500
0x1800034fc  mov     [rbp+13F0h+var_1450], r13
0x180003500  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003507  test    rax, rax
0x18000350a  jz      short loc_180003516
0x18000350c  lea     rcx, [rsp+14F0h+var_14D0]
0x180003511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003516  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000351d  test    rax, rax
0x180003520  jz      short loc_180003536
0x180003522  mov     r8d, 400h
0x180003528  lea     rdx, [rbp+13F0h+var_1430]
0x18000352c  lea     rcx, [rsp+14F0h+var_14D0]
0x180003531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003536  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000353d  test    rax, rax
0x180003540  jz      short loc_18000354C
0x180003542  lea     rcx, [rsp+14F0h+var_14D0]
0x180003547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000354c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003553  test    rax, rax
0x180003556  jz      short loc_180003569
0x180003558  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000355d  jnz     short loc_180003569
0x18000355f  lea     rcx, [rsp+14F0h+var_14D0]
0x180003564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003569  cmp     [rsp+14F0h+var_14C8], r13d
0x18000356e  jl      short loc_180003582
0x180003570  mov     ecx, 8000FFFFh; this
0x180003575  mov     [rsp+14F0h+var_14C8], ecx
0x180003579  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000357e  mov     [rsp+14F0h+var_14C4], eax
0x180003582  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180003589  jnz     short loc_1800035AA
0x18000358b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003592  test    rax, rax
0x180003595  jz      short loc_1800035A0
0x180003597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000359c  test    al, al
0x18000359e  jmp     short loc_1800035A8
0x1800035a0  call    cs:__imp_IsDebuggerPresent
0x1800035a6  test    eax, eax
0x1800035a8  jz      short loc_1800035B1
0x1800035aa  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800035af  jz      short loc_1800035D7
0x1800035b1  mov     rax, cs:g_pfnResultLoggingCallback
0x1800035b8  test    rax, rax
0x1800035bb  jz      short loc_180003630
0x1800035bd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800035c4  jnz     short loc_180003630
0x1800035c6  xor     r8d, r8d
0x1800035c9  xor     edx, edx
0x1800035cb  lea     rcx, [rsp+14F0h+var_14D0]
0x1800035d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035d5  jmp     short loc_180003630
0x1800035d7  mov     ebx, 800h
0x1800035dc  mov     rax, cs:g_pfnResultLoggingCallback
0x1800035e3  test    rax, rax
0x1800035e6  jz      short loc_180003605
0x1800035e8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800035ef  jnz     short loc_180003605
0x1800035f1  mov     r8d, ebx
0x1800035f4  lea     rdx, [rbp+13F0h+OutputString]
0x1800035fb  lea     rcx, [rsp+14F0h+var_14D0]
0x180003600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003605  cmp     [rbp+13F0h+OutputString], r13w
0x18000360d  jnz     short loc_180003623
0x18000360f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003614  mov     rdx, rbx; unsigned __int16 *
0x180003617  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000361e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003623  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000362a  call    cs:__imp_OutputDebugStringW
0x180003630  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003635  jnz     short loc_180003640
0x180003637  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000363e  jz      short loc_180003652
0x180003640  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003647  test    rax, rax
0x18000364a  jz      short loc_180003652
0x18000364c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003651  nop
0x180003652  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003657  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
