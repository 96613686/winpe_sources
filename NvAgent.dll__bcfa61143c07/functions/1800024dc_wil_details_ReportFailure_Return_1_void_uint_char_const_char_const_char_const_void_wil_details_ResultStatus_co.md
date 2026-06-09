# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800024dc`
- end: `0x180002772`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180001fc4`

## callees

- `0x180001590`
- `0x180001f4a`
- `0x1800024dc`
- `0x180003604`
- `0x1800044f0`
- `0x180005410`
- `0x1800054ec`
- `0x180006170`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002587`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002587`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000270c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000270c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002682`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002682`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x1800024dc  mov     [rsp-8+arg_10], rbx
0x1800024e1  push    rbp
0x1800024e2  push    rsi
0x1800024e3  push    rdi
0x1800024e4  push    r14
0x1800024e6  push    r15
0x1800024e8  lea     rbp, [rsp-13D0h]
0x1800024f0  mov     eax, 14D0h
0x1800024f5  call    _alloca_probe
0x1800024fa  sub     rsp, rax
0x1800024fd  mov     rax, cs:__security_cookie
0x180002504  xor     rax, rsp
0x180002507  mov     [rbp+13F0h+var_30], rax
0x18000250e  mov     esi, edx
0x180002510  mov     r14, rcx
0x180002513  mov     rdi, [rbp+13F0h+arg_28]
0x18000251a  xor     edx, edx; Val
0x18000251c  mov     r8d, 98h; Size
0x180002522  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002527  call    memset_0
0x18000252c  nop
0x18000252d  xor     r15d, r15d
0x180002530  mov     [rbp+13F0h+OutputString], r15w
0x180002538  mov     [rbp+13F0h+var_1430], r15b
0x18000253c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180002543  mov     ecx, [rdx]; this
0x180002545  mov     [rsp+14F0h+var_14C8], ecx
0x180002549  mov     eax, [rdx+4]
0x18000254c  mov     [rsp+14F0h+var_14C4], eax
0x180002550  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002555  mov     ebx, eax
0x180002557  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000255f  mov     ecx, r15d
0x180002562  lea     eax, [r15+8]
0x180002566  cmp     dword ptr [rdx+8], 1
0x18000256a  cmovz   ecx, eax
0x18000256d  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002571  lea     ecx, [rax-7]
0x180002574  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000257c  inc     ecx
0x18000257e  mov     [rsp+14F0h+var_14C0], ecx
0x180002582  mov     [rsp+14F0h+var_14B8], r15
0x180002587  call    cs:__imp_GetCurrentThreadId
0x18000258d  mov     [rsp+14F0h+var_14B0], eax
0x180002591  lea     rax, aWil; "wil"
0x180002598  mov     [rsp+14F0h+var_1498], rax
0x18000259d  mov     [rsp+14F0h+var_1490], esi
0x1800025a1  mov     [rsp+14F0h+var_148C], ebx
0x1800025a5  mov     [rsp+14F0h+var_14A8], r15
0x1800025aa  mov     [rsp+14F0h+var_14A0], r15
0x1800025af  mov     [rbp+13F0h+var_1448], rdi
0x1800025b3  mov     [rbp+13F0h+var_1440], r14
0x1800025b7  mov     [rsp+14F0h+var_1488], r15
0x1800025bc  xorps   xmm0, xmm0
0x1800025bf  xor     eax, eax
0x1800025c1  movups  [rbp+13F0h+var_1468], xmm0
0x1800025c5  mov     [rbp+13F0h+var_1458], rax
0x1800025c9  xorps   xmm1, xmm1
0x1800025cc  movups  [rsp+14F0h+var_1480], xmm1
0x1800025d1  mov     [rbp+13F0h+var_1470], rax
0x1800025d5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800025dc  test    rax, rax
0x1800025df  jz      short loc_1800025EC
0x1800025e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025e6  mov     [rbp+13F0h+var_1450], rax
0x1800025ea  jmp     short loc_1800025F0
0x1800025ec  mov     [rbp+13F0h+var_1450], r15
0x1800025f0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800025f7  test    rax, rax
0x1800025fa  jz      short loc_180002606
0x1800025fc  lea     rcx, [rsp+14F0h+var_14D0]
0x180002601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002606  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000260d  test    rax, rax
0x180002610  jz      short loc_180002626
0x180002612  mov     r8d, 400h
0x180002618  lea     rdx, [rbp+13F0h+var_1430]
0x18000261c  lea     rcx, [rsp+14F0h+var_14D0]
0x180002621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002626  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000262d  test    rax, rax
0x180002630  jz      short loc_18000263C
0x180002632  lea     rcx, [rsp+14F0h+var_14D0]
0x180002637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000263c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002643  test    rax, rax
0x180002646  jz      short loc_180002659
0x180002648  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000264d  jnz     short loc_180002659
0x18000264f  lea     rcx, [rsp+14F0h+var_14D0]
0x180002654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002659  cmp     [rsp+14F0h+var_14C8], r15d
0x18000265e  jge     loc_18000276C
0x180002664  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000266b  jnz     short loc_18000268C
0x18000266d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002674  test    rax, rax
0x180002677  jz      short loc_180002682
0x180002679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000267e  test    al, al
0x180002680  jmp     short loc_18000268A
0x180002682  call    cs:__imp_IsDebuggerPresent
0x180002688  test    eax, eax
0x18000268a  jz      short loc_180002693
0x18000268c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002691  jz      short loc_1800026B9
0x180002693  mov     rax, cs:g_pfnResultLoggingCallback
0x18000269a  test    rax, rax
0x18000269d  jz      short loc_180002712
0x18000269f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800026a6  jnz     short loc_180002712
0x1800026a8  xor     r8d, r8d
0x1800026ab  xor     edx, edx
0x1800026ad  lea     rcx, [rsp+14F0h+var_14D0]
0x1800026b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026b7  jmp     short loc_180002712
0x1800026b9  mov     ebx, 800h
0x1800026be  mov     rax, cs:g_pfnResultLoggingCallback
0x1800026c5  test    rax, rax
0x1800026c8  jz      short loc_1800026E7
0x1800026ca  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800026d1  jnz     short loc_1800026E7
0x1800026d3  mov     r8d, ebx
0x1800026d6  lea     rdx, [rbp+13F0h+OutputString]
0x1800026dd  lea     rcx, [rsp+14F0h+var_14D0]
0x1800026e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026e7  cmp     [rbp+13F0h+OutputString], r15w
0x1800026ef  jnz     short loc_180002705
0x1800026f1  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800026f6  mov     rdx, rbx; unsigned __int16 *
0x1800026f9  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002700  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002705  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000270c  call    cs:__imp_OutputDebugStringW
0x180002712  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002717  jnz     short loc_180002722
0x180002719  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180002720  jz      short loc_180002734
0x180002722  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002729  test    rax, rax
0x18000272c  jz      short loc_180002734
0x18000272e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002733  nop
0x180002734  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180002739  jnz     short loc_180002761
0x18000273b  mov     rcx, [rbp+13F0h+var_30]
0x180002742  xor     rcx, rsp; StackCookie
0x180002745  call    __security_check_cookie
0x18000274a  mov     rbx, [rsp+14F0h+arg_10]
0x180002752  add     rsp, 14D0h
0x180002759  pop     r15
0x18000275b  pop     r14
0x18000275d  pop     rdi
0x18000275e  pop     rsi
0x18000275f  pop     rbp
0x180002760  retn
0x180002761  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002766  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000276c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
