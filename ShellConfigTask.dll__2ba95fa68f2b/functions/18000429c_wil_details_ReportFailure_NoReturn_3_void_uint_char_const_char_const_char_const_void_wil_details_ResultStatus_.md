# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000429c`
- end: `0x180004515`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000401c`

## callees

- `0x180002f98`
- `0x18000429c`
- `0x180007914`
- `0x180008110`
- `0x1800092a0`
- `0x18000c380`
- `0x1800300f0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004355`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004355`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004458`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004458`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800044e2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800044e2`

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
0x18000429c  mov     [rsp-8+arg_18], rbx
0x1800042a1  push    rbp
0x1800042a2  push    rsi
0x1800042a3  push    rdi
0x1800042a4  push    r12
0x1800042a6  push    r13
0x1800042a8  push    r14
0x1800042aa  push    r15
0x1800042ac  lea     rbp, [rsp-13C0h]
0x1800042b4  mov     eax, 14C0h
0x1800042b9  call    _alloca_probe
0x1800042be  sub     rsp, rax
0x1800042c1  mov     r14, r8
0x1800042c4  mov     esi, edx
0x1800042c6  mov     rdi, rcx
0x1800042c9  mov     r15, [rbp+13F0h+arg_28]
0x1800042d0  xor     edx, edx; Val
0x1800042d2  mov     r8d, 98h; Size
0x1800042d8  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800042dd  call    memset_0
0x1800042e2  nop
0x1800042e3  xor     r13d, r13d
0x1800042e6  mov     [rbp+13F0h+OutputString], r13w
0x1800042ee  mov     [rbp+13F0h+var_1430], r13b
0x1800042f2  mov     rbx, [rbp+13F0h+arg_30]
0x1800042f9  mov     ecx, [rbx]; this
0x1800042fb  mov     [rsp+14F0h+var_14C8], ecx
0x1800042ff  mov     eax, [rbx+4]
0x180004302  mov     [rsp+14F0h+var_14C4], eax
0x180004306  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000430b  mov     r12d, eax
0x18000430e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180004316  mov     ecx, r13d
0x180004319  lea     eax, [r13+8]
0x18000431d  cmp     dword ptr [rbx+8], 1
0x180004321  cmovz   ecx, eax
0x180004324  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180004328  lea     ecx, [rax-7]
0x18000432b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004333  inc     ecx
0x180004335  mov     [rsp+14F0h+var_14C0], ecx
0x180004339  mov     rcx, [rbp+13F0h+arg_38]
0x180004340  test    rcx, rcx
0x180004343  jz      short loc_180004350
0x180004345  cmp     [rcx], r13w
0x180004349  mov     [rsp+14F0h+var_14B8], rcx
0x18000434e  jnz     short loc_180004355
0x180004350  mov     [rsp+14F0h+var_14B8], r13
0x180004355  call    cs:__imp_GetCurrentThreadId
0x18000435b  mov     [rsp+14F0h+var_14B0], eax
0x18000435f  mov     [rsp+14F0h+var_1498], r14
0x180004364  mov     [rsp+14F0h+var_1490], esi
0x180004368  mov     [rsp+14F0h+var_148C], r12d
0x18000436d  mov     [rsp+14F0h+var_14A8], r13
0x180004372  mov     [rsp+14F0h+var_14A0], r13
0x180004377  mov     [rbp+13F0h+var_1448], r15
0x18000437b  mov     [rbp+13F0h+var_1440], rdi
0x18000437f  mov     [rsp+14F0h+var_1488], r13
0x180004384  xorps   xmm0, xmm0
0x180004387  xor     eax, eax
0x180004389  movups  [rbp+13F0h+var_1468], xmm0
0x18000438d  mov     [rbp+13F0h+var_1458], rax
0x180004391  xorps   xmm1, xmm1
0x180004394  movups  [rsp+14F0h+var_1480], xmm1
0x180004399  mov     [rbp+13F0h+var_1470], rax
0x18000439d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800043a4  test    rax, rax
0x1800043a7  jz      short loc_1800043B4
0x1800043a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043ae  mov     [rbp+13F0h+var_1450], rax
0x1800043b2  jmp     short loc_1800043B8
0x1800043b4  mov     [rbp+13F0h+var_1450], r13
0x1800043b8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800043bf  test    rax, rax
0x1800043c2  jz      short loc_1800043CE
0x1800043c4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800043c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043ce  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800043d5  test    rax, rax
0x1800043d8  jz      short loc_1800043EE
0x1800043da  mov     r8d, 400h
0x1800043e0  lea     rdx, [rbp+13F0h+var_1430]
0x1800043e4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800043e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043ee  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800043f5  test    rax, rax
0x1800043f8  jz      short loc_180004404
0x1800043fa  lea     rcx, [rsp+14F0h+var_14D0]
0x1800043ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004404  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000440b  test    rax, rax
0x18000440e  jz      short loc_180004421
0x180004410  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004415  jnz     short loc_180004421
0x180004417  lea     rcx, [rsp+14F0h+var_14D0]
0x18000441c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004421  cmp     [rsp+14F0h+var_14C8], r13d
0x180004426  jl      short loc_18000443A
0x180004428  mov     ecx, 8000FFFFh; this
0x18000442d  mov     [rsp+14F0h+var_14C8], ecx
0x180004431  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004436  mov     [rsp+14F0h+var_14C4], eax
0x18000443a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180004441  jnz     short loc_180004462
0x180004443  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000444a  test    rax, rax
0x18000444d  jz      short loc_180004458
0x18000444f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004454  test    al, al
0x180004456  jmp     short loc_180004460
0x180004458  call    cs:__imp_IsDebuggerPresent
0x18000445e  test    eax, eax
0x180004460  jz      short loc_180004469
0x180004462  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004467  jz      short loc_18000448F
0x180004469  mov     rax, cs:g_pfnResultLoggingCallback
0x180004470  test    rax, rax
0x180004473  jz      short loc_1800044E8
0x180004475  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000447c  jnz     short loc_1800044E8
0x18000447e  xor     r8d, r8d
0x180004481  xor     edx, edx
0x180004483  lea     rcx, [rsp+14F0h+var_14D0]
0x180004488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000448d  jmp     short loc_1800044E8
0x18000448f  mov     ebx, 800h
0x180004494  mov     rax, cs:g_pfnResultLoggingCallback
0x18000449b  test    rax, rax
0x18000449e  jz      short loc_1800044BD
0x1800044a0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800044a7  jnz     short loc_1800044BD
0x1800044a9  mov     r8d, ebx
0x1800044ac  lea     rdx, [rbp+13F0h+OutputString]
0x1800044b3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800044b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044bd  cmp     [rbp+13F0h+OutputString], r13w
0x1800044c5  jnz     short loc_1800044DB
0x1800044c7  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800044cc  mov     rdx, rbx; unsigned __int16 *
0x1800044cf  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800044d6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800044db  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800044e2  call    cs:__imp_OutputDebugStringW
0x1800044e8  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800044ed  jnz     short loc_1800044F8
0x1800044ef  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800044f6  jz      short loc_18000450A
0x1800044f8  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800044ff  test    rax, rax
0x180004502  jz      short loc_18000450A
0x180004504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004509  nop
0x18000450a  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000450f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
