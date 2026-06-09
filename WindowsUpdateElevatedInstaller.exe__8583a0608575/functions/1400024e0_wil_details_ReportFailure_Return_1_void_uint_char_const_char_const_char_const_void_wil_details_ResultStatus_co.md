# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1400024e0`
- end: `0x140002786`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140001fa8`

## callees

- `0x140001480`
- `0x140001e7e`
- `0x1400024e0`
- `0x140003674`
- `0x1400045b0`
- `0x140005650`
- `0x14000572c`
- `0x1400070a0`
- `0x140008010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400025a6`
- `KERNEL32!GetCurrentThreadId` at `0x1400025a6`
- `KERNEL32!OutputDebugStringW` at `0x140002725`
- `KERNEL32!OutputDebugStringW` at `0x140002725`
- `KERNEL32!IsDebuggerPresent` at `0x14000269b`
- `KERNEL32!IsDebuggerPresent` at `0x14000269b`

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
0x1400024e0  push    rbp
0x1400024e2  push    rbx
0x1400024e3  push    rsi
0x1400024e4  push    rdi
0x1400024e5  push    r12
0x1400024e7  push    r14
0x1400024e9  push    r15
0x1400024eb  lea     rbp, [rsp-13D0h]
0x1400024f3  mov     eax, 14D0h
0x1400024f8  call    _alloca_probe
0x1400024fd  sub     rsp, rax
0x140002500  mov     rax, cs:__security_cookie
0x140002507  xor     rax, rsp
0x14000250a  mov     [rbp+1400h+var_40], rax
0x140002511  mov     rsi, r8
0x140002514  mov     edi, edx
0x140002516  mov     rbx, rcx
0x140002519  mov     r14, [rbp+1400h+arg_28]
0x140002520  xor     edx, edx; Val
0x140002522  mov     r8d, 98h; Size
0x140002528  lea     rcx, [rsp+1500h+var_14E0]; void *
0x14000252d  call    memset_0
0x140002532  nop
0x140002533  xor     r12d, r12d
0x140002536  mov     [rbp+1400h+OutputString], r12w
0x14000253e  mov     [rbp+1400h+var_1440], r12b
0x140002542  mov     rdx, [rbp+1400h+arg_30]; int
0x140002549  mov     ecx, [rdx]; this
0x14000254b  mov     [rsp+1500h+var_14D8], ecx
0x14000254f  mov     eax, [rdx+4]
0x140002552  mov     [rsp+1500h+var_14D4], eax
0x140002556  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000255b  mov     r15d, eax
0x14000255e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140002566  mov     ecx, r12d
0x140002569  lea     eax, [r12+8]
0x14000256e  cmp     dword ptr [rdx+8], 1
0x140002572  cmovz   ecx, eax
0x140002575  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140002579  lea     ecx, [rax-7]
0x14000257c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002584  inc     ecx
0x140002586  mov     [rsp+1500h+var_14D0], ecx
0x14000258a  mov     rcx, [rbp+1400h+arg_38]
0x140002591  test    rcx, rcx
0x140002594  jz      short loc_1400025A1
0x140002596  cmp     [rcx], r12w
0x14000259a  mov     [rsp+1500h+var_14C8], rcx
0x14000259f  jnz     short loc_1400025A6
0x1400025a1  mov     [rsp+1500h+var_14C8], r12
0x1400025a6  call    cs:__imp_GetCurrentThreadId
0x1400025ac  mov     [rsp+1500h+var_14C0], eax
0x1400025b0  mov     [rsp+1500h+var_14A8], rsi
0x1400025b5  mov     [rsp+1500h+var_14A0], edi
0x1400025b9  mov     [rsp+1500h+var_149C], r15d
0x1400025be  mov     [rsp+1500h+var_14B8], r12
0x1400025c3  mov     [rsp+1500h+var_14B0], r12
0x1400025c8  mov     [rbp+1400h+var_1458], r14
0x1400025cc  mov     [rbp+1400h+var_1450], rbx
0x1400025d0  mov     [rsp+1500h+var_1498], r12
0x1400025d5  xorps   xmm0, xmm0
0x1400025d8  xor     eax, eax
0x1400025da  movups  [rbp+1400h+var_1478], xmm0
0x1400025de  mov     [rbp+1400h+var_1468], rax
0x1400025e2  xorps   xmm1, xmm1
0x1400025e5  movups  [rsp+1500h+var_1490], xmm1
0x1400025ea  mov     [rbp+1400h+var_1480], rax
0x1400025ee  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400025f5  test    rax, rax
0x1400025f8  jz      short loc_140002605
0x1400025fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400025ff  mov     [rbp+1400h+var_1460], rax
0x140002603  jmp     short loc_140002609
0x140002605  mov     [rbp+1400h+var_1460], r12
0x140002609  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002610  test    rax, rax
0x140002613  jz      short loc_14000261F
0x140002615  lea     rcx, [rsp+1500h+var_14E0]
0x14000261a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000261f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002626  test    rax, rax
0x140002629  jz      short loc_14000263F
0x14000262b  mov     r8d, 400h
0x140002631  lea     rdx, [rbp+1400h+var_1440]
0x140002635  lea     rcx, [rsp+1500h+var_14E0]
0x14000263a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000263f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002646  test    rax, rax
0x140002649  jz      short loc_140002655
0x14000264b  lea     rcx, [rsp+1500h+var_14E0]
0x140002650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002655  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000265c  test    rax, rax
0x14000265f  jz      short loc_140002672
0x140002661  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140002666  jnz     short loc_140002672
0x140002668  lea     rcx, [rsp+1500h+var_14E0]
0x14000266d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002672  cmp     [rsp+1500h+var_14D8], r12d
0x140002677  jge     loc_140002780
0x14000267d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140002684  jnz     short loc_1400026A5
0x140002686  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000268d  test    rax, rax
0x140002690  jz      short loc_14000269B
0x140002692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002697  test    al, al
0x140002699  jmp     short loc_1400026A3
0x14000269b  call    cs:__imp_IsDebuggerPresent
0x1400026a1  test    eax, eax
0x1400026a3  jz      short loc_1400026AC
0x1400026a5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1400026aa  jz      short loc_1400026D2
0x1400026ac  mov     rax, cs:g_pfnResultLoggingCallback
0x1400026b3  test    rax, rax
0x1400026b6  jz      short loc_14000272B
0x1400026b8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400026bf  jnz     short loc_14000272B
0x1400026c1  xor     r8d, r8d
0x1400026c4  xor     edx, edx
0x1400026c6  lea     rcx, [rsp+1500h+var_14E0]
0x1400026cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400026d0  jmp     short loc_14000272B
0x1400026d2  mov     ebx, 800h
0x1400026d7  mov     rax, cs:g_pfnResultLoggingCallback
0x1400026de  test    rax, rax
0x1400026e1  jz      short loc_140002700
0x1400026e3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400026ea  jnz     short loc_140002700
0x1400026ec  mov     r8d, ebx
0x1400026ef  lea     rdx, [rbp+1400h+OutputString]
0x1400026f6  lea     rcx, [rsp+1500h+var_14E0]
0x1400026fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002700  cmp     [rbp+1400h+OutputString], r12w
0x140002708  jnz     short loc_14000271E
0x14000270a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x14000270f  mov     rdx, rbx; unsigned __int16 *
0x140002712  lea     rcx, [rbp+1400h+OutputString]; this
0x140002719  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000271e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140002725  call    cs:__imp_OutputDebugStringW
0x14000272b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140002730  jnz     short loc_14000273B
0x140002732  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140002739  jz      short loc_14000274D
0x14000273b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002742  test    rax, rax
0x140002745  jz      short loc_14000274D
0x140002747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000274c  nop
0x14000274d  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140002752  jnz     short loc_140002775
0x140002754  mov     rcx, [rbp+1400h+var_40]
0x14000275b  xor     rcx, rsp; StackCookie
0x14000275e  call    __security_check_cookie
0x140002763  add     rsp, 14D0h
0x14000276a  pop     r15
0x14000276c  pop     r14
0x14000276e  pop     r12
0x140002770  pop     rdi
0x140002771  pop     rsi
0x140002772  pop     rbx
0x140002773  pop     rbp
0x140002774  retn
0x140002775  lea     rcx, [rsp+1500h+var_14E0]; this
0x14000277a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140002780  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
