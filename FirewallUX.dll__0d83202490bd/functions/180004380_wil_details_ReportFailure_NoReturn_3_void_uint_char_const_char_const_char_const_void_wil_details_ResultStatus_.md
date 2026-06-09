# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180004380`
- end: `0x1800045f9`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003fac`

## callees

- `0x180002c04`
- `0x180004380`
- `0x1800072bc`
- `0x180007ee0`
- `0x180008b70`
- `0x18000a7b0`
- `0x180029890`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004439`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004439`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000453c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000453c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800045c6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800045c6`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
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
0x180004380  mov     [rsp-8+arg_18], rbx
0x180004385  push    rbp
0x180004386  push    rsi
0x180004387  push    rdi
0x180004388  push    r12
0x18000438a  push    r13
0x18000438c  push    r14
0x18000438e  push    r15
0x180004390  lea     rbp, [rsp-13C0h]
0x180004398  mov     eax, 14C0h
0x18000439d  call    _alloca_probe
0x1800043a2  sub     rsp, rax
0x1800043a5  mov     r14, r8
0x1800043a8  mov     esi, edx
0x1800043aa  mov     rdi, rcx
0x1800043ad  mov     r15, [rbp+13F0h+arg_28]
0x1800043b4  xor     edx, edx; Val
0x1800043b6  mov     r8d, 98h; Size
0x1800043bc  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800043c1  call    memset_0
0x1800043c6  nop
0x1800043c7  xor     r13d, r13d
0x1800043ca  mov     [rbp+13F0h+OutputString], r13w
0x1800043d2  mov     [rbp+13F0h+var_1430], r13b
0x1800043d6  mov     rbx, [rbp+13F0h+arg_30]
0x1800043dd  mov     ecx, [rbx]; this
0x1800043df  mov     [rsp+14F0h+var_14C8], ecx
0x1800043e3  mov     eax, [rbx+4]
0x1800043e6  mov     [rsp+14F0h+var_14C4], eax
0x1800043ea  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800043ef  mov     r12d, eax
0x1800043f2  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800043fa  mov     ecx, r13d
0x1800043fd  lea     eax, [r13+8]
0x180004401  cmp     dword ptr [rbx+8], 1
0x180004405  cmovz   ecx, eax
0x180004408  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000440c  lea     ecx, [rax-7]
0x18000440f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004417  inc     ecx
0x180004419  mov     [rsp+14F0h+var_14C0], ecx
0x18000441d  mov     rcx, [rbp+13F0h+arg_38]
0x180004424  test    rcx, rcx
0x180004427  jz      short loc_180004434
0x180004429  cmp     [rcx], r13w
0x18000442d  mov     [rsp+14F0h+var_14B8], rcx
0x180004432  jnz     short loc_180004439
0x180004434  mov     [rsp+14F0h+var_14B8], r13
0x180004439  call    cs:__imp_GetCurrentThreadId
0x18000443f  mov     [rsp+14F0h+var_14B0], eax
0x180004443  mov     [rsp+14F0h+var_1498], r14
0x180004448  mov     [rsp+14F0h+var_1490], esi
0x18000444c  mov     [rsp+14F0h+var_148C], r12d
0x180004451  mov     [rsp+14F0h+var_14A8], r13
0x180004456  mov     [rsp+14F0h+var_14A0], r13
0x18000445b  mov     [rbp+13F0h+var_1448], r15
0x18000445f  mov     [rbp+13F0h+var_1440], rdi
0x180004463  mov     [rsp+14F0h+var_1488], r13
0x180004468  xorps   xmm0, xmm0
0x18000446b  xor     eax, eax
0x18000446d  movups  [rbp+13F0h+var_1468], xmm0
0x180004471  mov     [rbp+13F0h+var_1458], rax
0x180004475  xorps   xmm1, xmm1
0x180004478  movups  [rsp+14F0h+var_1480], xmm1
0x18000447d  mov     [rbp+13F0h+var_1470], rax
0x180004481  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004488  test    rax, rax
0x18000448b  jz      short loc_180004498
0x18000448d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004492  mov     [rbp+13F0h+var_1450], rax
0x180004496  jmp     short loc_18000449C
0x180004498  mov     [rbp+13F0h+var_1450], r13
0x18000449c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800044a3  test    rax, rax
0x1800044a6  jz      short loc_1800044B2
0x1800044a8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800044ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044b2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800044b9  test    rax, rax
0x1800044bc  jz      short loc_1800044D2
0x1800044be  mov     r8d, 400h
0x1800044c4  lea     rdx, [rbp+13F0h+var_1430]
0x1800044c8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800044cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044d2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800044d9  test    rax, rax
0x1800044dc  jz      short loc_1800044E8
0x1800044de  lea     rcx, [rsp+14F0h+var_14D0]
0x1800044e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044e8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800044ef  test    rax, rax
0x1800044f2  jz      short loc_180004505
0x1800044f4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800044f9  jnz     short loc_180004505
0x1800044fb  lea     rcx, [rsp+14F0h+var_14D0]
0x180004500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004505  cmp     [rsp+14F0h+var_14C8], r13d
0x18000450a  jl      short loc_18000451E
0x18000450c  mov     ecx, 8000FFFFh; this
0x180004511  mov     [rsp+14F0h+var_14C8], ecx
0x180004515  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000451a  mov     [rsp+14F0h+var_14C4], eax
0x18000451e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180004525  jnz     short loc_180004546
0x180004527  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000452e  test    rax, rax
0x180004531  jz      short loc_18000453C
0x180004533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004538  test    al, al
0x18000453a  jmp     short loc_180004544
0x18000453c  call    cs:__imp_IsDebuggerPresent
0x180004542  test    eax, eax
0x180004544  jz      short loc_18000454D
0x180004546  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000454b  jz      short loc_180004573
0x18000454d  mov     rax, cs:g_pfnResultLoggingCallback
0x180004554  test    rax, rax
0x180004557  jz      short loc_1800045CC
0x180004559  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180004560  jnz     short loc_1800045CC
0x180004562  xor     r8d, r8d
0x180004565  xor     edx, edx
0x180004567  lea     rcx, [rsp+14F0h+var_14D0]
0x18000456c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004571  jmp     short loc_1800045CC
0x180004573  mov     ebx, 800h
0x180004578  mov     rax, cs:g_pfnResultLoggingCallback
0x18000457f  test    rax, rax
0x180004582  jz      short loc_1800045A1
0x180004584  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000458b  jnz     short loc_1800045A1
0x18000458d  mov     r8d, ebx
0x180004590  lea     rdx, [rbp+13F0h+OutputString]
0x180004597  lea     rcx, [rsp+14F0h+var_14D0]
0x18000459c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045a1  cmp     [rbp+13F0h+OutputString], r13w
0x1800045a9  jnz     short loc_1800045BF
0x1800045ab  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800045b0  mov     rdx, rbx; unsigned __int16 *
0x1800045b3  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800045ba  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800045bf  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800045c6  call    cs:__imp_OutputDebugStringW
0x1800045cc  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800045d1  jnz     short loc_1800045DC
0x1800045d3  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800045da  jz      short loc_1800045EE
0x1800045dc  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800045e3  test    rax, rax
0x1800045e6  jz      short loc_1800045EE
0x1800045e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045ed  nop
0x1800045ee  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800045f3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
