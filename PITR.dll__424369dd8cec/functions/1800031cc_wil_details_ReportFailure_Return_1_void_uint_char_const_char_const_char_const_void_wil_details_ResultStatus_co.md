# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800031cc`
- end: `0x180003462`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002cac`

## callees

- `0x1800031cc`
- `0x18000e76c`
- `0x180013bac`
- `0x18001daa0`
- `0x18001dd64`
- `0x1800502c2`
- `0x180050300`
- `0x1800503c0`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003277`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003277`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800033fc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800033fc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003372`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003372`

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
0x1800031cc  mov     [rsp-8+arg_10], rbx
0x1800031d1  push    rbp
0x1800031d2  push    rsi
0x1800031d3  push    rdi
0x1800031d4  push    r14
0x1800031d6  push    r15
0x1800031d8  lea     rbp, [rsp-13D0h]
0x1800031e0  mov     eax, 14D0h
0x1800031e5  call    _alloca_probe
0x1800031ea  sub     rsp, rax
0x1800031ed  mov     rax, cs:__security_cookie
0x1800031f4  xor     rax, rsp
0x1800031f7  mov     [rbp+13F0h+var_30], rax
0x1800031fe  mov     esi, edx
0x180003200  mov     r14, rcx
0x180003203  mov     rdi, [rbp+13F0h+arg_28]
0x18000320a  xor     edx, edx; Val
0x18000320c  mov     r8d, 98h; Size
0x180003212  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003217  call    memset_0
0x18000321c  nop
0x18000321d  xor     r15d, r15d
0x180003220  mov     [rbp+13F0h+OutputString], r15w
0x180003228  mov     [rbp+13F0h+var_1430], r15b
0x18000322c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180003233  mov     ecx, [rdx]; this
0x180003235  mov     [rsp+14F0h+var_14C8], ecx
0x180003239  mov     eax, [rdx+4]
0x18000323c  mov     [rsp+14F0h+var_14C4], eax
0x180003240  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003245  mov     ebx, eax
0x180003247  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000324f  mov     ecx, r15d
0x180003252  lea     eax, [r15+8]
0x180003256  cmp     dword ptr [rdx+8], 1
0x18000325a  cmovz   ecx, eax
0x18000325d  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003261  lea     ecx, [rax-7]
0x180003264  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000326c  inc     ecx
0x18000326e  mov     [rsp+14F0h+var_14C0], ecx
0x180003272  mov     [rsp+14F0h+var_14B8], r15
0x180003277  call    cs:__imp_GetCurrentThreadId
0x18000327d  mov     [rsp+14F0h+var_14B0], eax
0x180003281  lea     rax, aWil; "wil"
0x180003288  mov     [rsp+14F0h+var_1498], rax
0x18000328d  mov     [rsp+14F0h+var_1490], esi
0x180003291  mov     [rsp+14F0h+var_148C], ebx
0x180003295  mov     [rsp+14F0h+var_14A8], r15
0x18000329a  mov     [rsp+14F0h+var_14A0], r15
0x18000329f  mov     [rbp+13F0h+var_1448], rdi
0x1800032a3  mov     [rbp+13F0h+var_1440], r14
0x1800032a7  mov     [rsp+14F0h+var_1488], r15
0x1800032ac  xorps   xmm0, xmm0
0x1800032af  xor     eax, eax
0x1800032b1  movups  [rbp+13F0h+var_1468], xmm0
0x1800032b5  mov     [rbp+13F0h+var_1458], rax
0x1800032b9  xorps   xmm1, xmm1
0x1800032bc  movups  [rsp+14F0h+var_1480], xmm1
0x1800032c1  mov     [rbp+13F0h+var_1470], rax
0x1800032c5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800032cc  test    rax, rax
0x1800032cf  jz      short loc_1800032DC
0x1800032d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032d6  mov     [rbp+13F0h+var_1450], rax
0x1800032da  jmp     short loc_1800032E0
0x1800032dc  mov     [rbp+13F0h+var_1450], r15
0x1800032e0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800032e7  test    rax, rax
0x1800032ea  jz      short loc_1800032F6
0x1800032ec  lea     rcx, [rsp+14F0h+var_14D0]
0x1800032f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032f6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800032fd  test    rax, rax
0x180003300  jz      short loc_180003316
0x180003302  mov     r8d, 400h
0x180003308  lea     rdx, [rbp+13F0h+var_1430]
0x18000330c  lea     rcx, [rsp+14F0h+var_14D0]
0x180003311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003316  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000331d  test    rax, rax
0x180003320  jz      short loc_18000332C
0x180003322  lea     rcx, [rsp+14F0h+var_14D0]
0x180003327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000332c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003333  test    rax, rax
0x180003336  jz      short loc_180003349
0x180003338  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000333d  jnz     short loc_180003349
0x18000333f  lea     rcx, [rsp+14F0h+var_14D0]
0x180003344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003349  cmp     [rsp+14F0h+var_14C8], r15d
0x18000334e  jge     loc_18000345C
0x180003354  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000335b  jnz     short loc_18000337C
0x18000335d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003364  test    rax, rax
0x180003367  jz      short loc_180003372
0x180003369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000336e  test    al, al
0x180003370  jmp     short loc_18000337A
0x180003372  call    cs:__imp_IsDebuggerPresent
0x180003378  test    eax, eax
0x18000337a  jz      short loc_180003383
0x18000337c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003381  jz      short loc_1800033A9
0x180003383  mov     rax, cs:g_pfnResultLoggingCallback
0x18000338a  test    rax, rax
0x18000338d  jz      short loc_180003402
0x18000338f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003396  jnz     short loc_180003402
0x180003398  xor     r8d, r8d
0x18000339b  xor     edx, edx
0x18000339d  lea     rcx, [rsp+14F0h+var_14D0]
0x1800033a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033a7  jmp     short loc_180003402
0x1800033a9  mov     ebx, 800h
0x1800033ae  mov     rax, cs:g_pfnResultLoggingCallback
0x1800033b5  test    rax, rax
0x1800033b8  jz      short loc_1800033D7
0x1800033ba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800033c1  jnz     short loc_1800033D7
0x1800033c3  mov     r8d, ebx
0x1800033c6  lea     rdx, [rbp+13F0h+OutputString]
0x1800033cd  lea     rcx, [rsp+14F0h+var_14D0]
0x1800033d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033d7  cmp     [rbp+13F0h+OutputString], r15w
0x1800033df  jnz     short loc_1800033F5
0x1800033e1  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800033e6  mov     rdx, rbx; unsigned __int16 *
0x1800033e9  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800033f0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800033f5  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800033fc  call    cs:__imp_OutputDebugStringW
0x180003402  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003407  jnz     short loc_180003412
0x180003409  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180003410  jz      short loc_180003424
0x180003412  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003419  test    rax, rax
0x18000341c  jz      short loc_180003424
0x18000341e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003423  nop
0x180003424  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003429  jnz     short loc_180003451
0x18000342b  mov     rcx, [rbp+13F0h+var_30]
0x180003432  xor     rcx, rsp; StackCookie
0x180003435  call    __security_check_cookie
0x18000343a  mov     rbx, [rsp+14F0h+arg_10]
0x180003442  add     rsp, 14D0h
0x180003449  pop     r15
0x18000344b  pop     r14
0x18000344d  pop     rdi
0x18000344e  pop     rsi
0x18000344f  pop     rbp
0x180003450  retn
0x180003451  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003456  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000345c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
