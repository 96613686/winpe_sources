# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180003070`
- end: `0x180003320`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `688`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003320`

## callees

- `0x180002770`
- `0x180002b50`
- `0x180002c80`
- `0x180002f40`
- `0x180002f90`
- `0x180003070`
- `0x180018ce0`
- `0x18001cdf0`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x1800032b2`
- `KERNEL32!OutputDebugStringW` at `0x1800032b2`
- `KERNEL32!GetCurrentThreadId` at `0x18000310a`
- `KERNEL32!GetCurrentThreadId` at `0x18000310a`
- `KERNEL32!IsDebuggerPresent` at `0x18000320d`
- `KERNEL32!IsDebuggerPresent` at `0x18000320d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v10; // r13
  int IsDebuggerPresent; // r12d
  int v12; // ebx
  int v13; // ecx
  __int64 v14; // rdx
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // bl
  const struct wil::FailureInfo *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v10 = g_pfnThrowPlatformException != 0;
  IsDebuggerPresent = 0;
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v12 = wil::details::RecordException((wil::details *)(unsigned int)v22, (int)a7);
  v20 = 0;
  v13 = 0;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  v21 = v13;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v12;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && !v10 && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  v18 = (wil::g_fIsDebuggerPresent
      || (!wil::g_pfnIsDebuggerPresent
        ? (LOBYTE(IsDebuggerPresent) = ::IsDebuggerPresent())
        : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16)),
          IsDebuggerPresent))
     && (v21 & 2) == 0;
  if ( v10 || v18 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v20, v17);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v15);
  if ( v10 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v20, OutputString);
  wil::ThrowResultException((wil *)&v20, v15);
  wil::details::WilFailFast((wil::details *)&v20, v19);
}

```

## disassembly

```asm
0x180003070  mov     [rsp-8+arg_18], rbx
0x180003075  push    rbp
0x180003076  push    rsi
0x180003077  push    rdi
0x180003078  push    r12
0x18000307a  push    r13
0x18000307c  push    r14
0x18000307e  push    r15
0x180003080  lea     rbp, [rsp-13C0h]
0x180003088  mov     eax, 14C0h
0x18000308d  call    _alloca_probe
0x180003092  sub     rsp, rax
0x180003095  mov     r14, r8
0x180003098  mov     esi, edx
0x18000309a  mov     r15, rcx
0x18000309d  mov     rdi, [rbp+13F0h+arg_28]
0x1800030a4  cmp     cs:g_pfnThrowPlatformException, 0
0x1800030ac  setnz   r13b
0x1800030b0  xor     r12d, r12d
0x1800030b3  mov     [rbp+13F0h+OutputString], r12w
0x1800030bb  mov     [rbp+13F0h+var_1430], r12b
0x1800030bf  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800030c6  mov     ecx, [rdx]; this
0x1800030c8  mov     [rsp+14F0h+var_14C8], ecx
0x1800030cc  mov     eax, [rdx+4]
0x1800030cf  mov     [rsp+14F0h+var_14C4], eax
0x1800030d3  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800030d8  mov     ebx, eax
0x1800030da  mov     dword ptr [rsp+14F0h+var_14D0], r12d
0x1800030df  mov     ecx, r12d
0x1800030e2  mov     eax, 8
0x1800030e7  cmp     dword ptr [rdx+8], 1
0x1800030eb  cmovz   ecx, eax
0x1800030ee  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800030f2  mov     ecx, 1
0x1800030f7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x1800030ff  inc     ecx
0x180003101  mov     [rsp+14F0h+var_14C0], ecx
0x180003105  mov     [rsp+14F0h+var_14B8], r12
0x18000310a  call    cs:__imp_GetCurrentThreadId
0x180003110  mov     [rsp+14F0h+var_14B0], eax
0x180003114  mov     [rsp+14F0h+var_1498], r14
0x180003119  mov     [rsp+14F0h+var_1490], esi
0x18000311d  mov     [rsp+14F0h+var_148C], ebx
0x180003121  mov     [rsp+14F0h+var_14A8], r12
0x180003126  mov     [rsp+14F0h+var_14A0], r12
0x18000312b  mov     [rbp+13F0h+var_1448], rdi
0x18000312f  mov     [rbp+13F0h+var_1440], r15
0x180003133  mov     [rsp+14F0h+var_1488], r12
0x180003138  xorps   xmm0, xmm0
0x18000313b  xor     eax, eax
0x18000313d  movups  [rbp+13F0h+var_1468], xmm0
0x180003141  mov     [rbp+13F0h+var_1458], rax
0x180003145  xorps   xmm1, xmm1
0x180003148  movups  [rsp+14F0h+var_1480], xmm1
0x18000314d  mov     [rbp+13F0h+var_1470], rax
0x180003151  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003158  test    rax, rax
0x18000315b  jz      short loc_180003169
0x18000315d  call    cs:__guard_dispatch_icall_fptr
0x180003163  mov     [rbp+13F0h+var_1450], rax
0x180003167  jmp     short loc_18000316D
0x180003169  mov     [rbp+13F0h+var_1450], r12
0x18000316d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003174  test    rax, rax
0x180003177  jz      short loc_180003184
0x180003179  lea     rcx, [rsp+14F0h+var_14D0]
0x18000317e  call    cs:__guard_dispatch_icall_fptr
0x180003184  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000318b  test    rax, rax
0x18000318e  jz      short loc_1800031A5
0x180003190  mov     r8d, 400h
0x180003196  lea     rdx, [rbp+13F0h+var_1430]
0x18000319a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000319f  call    cs:__guard_dispatch_icall_fptr
0x1800031a5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800031ac  test    rax, rax
0x1800031af  jz      short loc_1800031BC
0x1800031b1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800031b6  call    cs:__guard_dispatch_icall_fptr
0x1800031bc  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800031c3  test    rax, rax
0x1800031c6  jz      short loc_1800031DF
0x1800031c8  test    r13b, r13b
0x1800031cb  jnz     short loc_1800031DF
0x1800031cd  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800031d2  jnz     short loc_1800031DF
0x1800031d4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800031d9  call    cs:__guard_dispatch_icall_fptr
0x1800031df  cmp     [rsp+14F0h+var_14C8], r12d
0x1800031e4  jl      short loc_1800031EC
0x1800031e6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800031ec  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800031f3  jnz     short loc_18000321E
0x1800031f5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800031fc  test    rax, rax
0x1800031ff  jz      short loc_18000320D
0x180003201  call    cs:__guard_dispatch_icall_fptr
0x180003207  movzx   r12d, al
0x18000320b  jmp     short loc_180003219
0x18000320d  call    cs:__imp_IsDebuggerPresent
0x180003213  test    eax, eax
0x180003215  setnz   r12b
0x180003219  test    r12d, r12d
0x18000321c  jz      short loc_180003229
0x18000321e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003223  jnz     short loc_180003229
0x180003225  mov     bl, 1
0x180003227  jmp     short loc_18000322B
0x180003229  xor     bl, bl
0x18000322b  test    r13b, r13b
0x18000322e  jnz     short loc_18000325A
0x180003230  test    bl, bl
0x180003232  jnz     short loc_18000325A
0x180003234  mov     rax, cs:g_pfnResultLoggingCallback
0x18000323b  test    rax, rax
0x18000323e  jz      short loc_1800032B8
0x180003240  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, bl; bool wil::details::g_resultMessageCallbackSet
0x180003246  jnz     short loc_1800032B8
0x180003248  xor     r8d, r8d
0x18000324b  xor     edx, edx
0x18000324d  lea     rcx, [rsp+14F0h+var_14D0]
0x180003252  call    cs:__guard_dispatch_icall_fptr
0x180003258  jmp     short loc_1800032B8
0x18000325a  mov     rax, cs:g_pfnResultLoggingCallback
0x180003261  test    rax, rax
0x180003264  jz      short loc_180003287
0x180003266  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x18000326d  jnz     short loc_180003287
0x18000326f  mov     r8d, 800h
0x180003275  lea     rdx, [rbp+13F0h+OutputString]
0x18000327c  lea     rcx, [rsp+14F0h+var_14D0]
0x180003281  call    cs:__guard_dispatch_icall_fptr
0x180003287  cmp     [rbp+13F0h+OutputString], 0
0x18000328f  jnz     short loc_1800032A7
0x180003291  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003296  mov     edx, 800h; wchar_t *
0x18000329b  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800032a2  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800032a7  test    bl, bl
0x1800032a9  jz      short loc_1800032B8
0x1800032ab  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800032b2  call    cs:__imp_OutputDebugStringW
0x1800032b8  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800032bd  jnz     short loc_1800032C8
0x1800032bf  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x1800032c6  jz      short loc_1800032DB
0x1800032c8  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800032cf  test    rax, rax
0x1800032d2  jz      short loc_1800032DB
0x1800032d4  call    cs:__guard_dispatch_icall_fptr
0x1800032da  nop
0x1800032db  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800032e0  jz      short loc_1800032ED
0x1800032e2  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800032e7  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800032ed  test    r13b, r13b
0x1800032f0  jz      short loc_18000330B
0x1800032f2  lea     rdx, [rbp+13F0h+OutputString]
0x1800032f9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800032fe  mov     rax, cs:g_pfnThrowPlatformException
0x180003305  call    cs:__guard_dispatch_icall_fptr
0x18000330b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003310  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180003315  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000331a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
