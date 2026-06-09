# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800033e4`
- end: `0x18000367a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002ec4`

## callees

- `0x180001c80`
- `0x180002802`
- `0x1800033e4`
- `0x180004514`
- `0x180005440`
- `0x180006490`
- `0x18000656c`
- `0x18000e780`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000348f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000348f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000358a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000358a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003614`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003614`

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
0x1800033e4  mov     [rsp-8+arg_10], rbx
0x1800033e9  push    rbp
0x1800033ea  push    rsi
0x1800033eb  push    rdi
0x1800033ec  push    r14
0x1800033ee  push    r15
0x1800033f0  lea     rbp, [rsp-13D0h]
0x1800033f8  mov     eax, 14D0h
0x1800033fd  call    _alloca_probe
0x180003402  sub     rsp, rax
0x180003405  mov     rax, cs:__security_cookie
0x18000340c  xor     rax, rsp
0x18000340f  mov     [rbp+13F0h+var_30], rax
0x180003416  mov     esi, edx
0x180003418  mov     r14, rcx
0x18000341b  mov     rdi, [rbp+13F0h+arg_28]
0x180003422  xor     edx, edx; Val
0x180003424  mov     r8d, 98h; Size
0x18000342a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000342f  call    memset_0
0x180003434  nop
0x180003435  xor     r15d, r15d
0x180003438  mov     [rbp+13F0h+OutputString], r15w
0x180003440  mov     [rbp+13F0h+var_1430], r15b
0x180003444  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000344b  mov     ecx, [rdx]; this
0x18000344d  mov     [rsp+14F0h+var_14C8], ecx
0x180003451  mov     eax, [rdx+4]
0x180003454  mov     [rsp+14F0h+var_14C4], eax
0x180003458  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000345d  mov     ebx, eax
0x18000345f  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180003467  mov     ecx, r15d
0x18000346a  lea     eax, [r15+8]
0x18000346e  cmp     dword ptr [rdx+8], 1
0x180003472  cmovz   ecx, eax
0x180003475  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003479  lea     ecx, [rax-7]
0x18000347c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003484  inc     ecx
0x180003486  mov     [rsp+14F0h+var_14C0], ecx
0x18000348a  mov     [rsp+14F0h+var_14B8], r15
0x18000348f  call    cs:__imp_GetCurrentThreadId
0x180003495  mov     [rsp+14F0h+var_14B0], eax
0x180003499  lea     rax, aWil; "wil"
0x1800034a0  mov     [rsp+14F0h+var_1498], rax
0x1800034a5  mov     [rsp+14F0h+var_1490], esi
0x1800034a9  mov     [rsp+14F0h+var_148C], ebx
0x1800034ad  mov     [rsp+14F0h+var_14A8], r15
0x1800034b2  mov     [rsp+14F0h+var_14A0], r15
0x1800034b7  mov     [rbp+13F0h+var_1448], rdi
0x1800034bb  mov     [rbp+13F0h+var_1440], r14
0x1800034bf  mov     [rsp+14F0h+var_1488], r15
0x1800034c4  xorps   xmm0, xmm0
0x1800034c7  xor     eax, eax
0x1800034c9  movups  [rbp+13F0h+var_1468], xmm0
0x1800034cd  mov     [rbp+13F0h+var_1458], rax
0x1800034d1  xorps   xmm1, xmm1
0x1800034d4  movups  [rsp+14F0h+var_1480], xmm1
0x1800034d9  mov     [rbp+13F0h+var_1470], rax
0x1800034dd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800034e4  test    rax, rax
0x1800034e7  jz      short loc_1800034F4
0x1800034e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034ee  mov     [rbp+13F0h+var_1450], rax
0x1800034f2  jmp     short loc_1800034F8
0x1800034f4  mov     [rbp+13F0h+var_1450], r15
0x1800034f8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800034ff  test    rax, rax
0x180003502  jz      short loc_18000350E
0x180003504  lea     rcx, [rsp+14F0h+var_14D0]
0x180003509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000350e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003515  test    rax, rax
0x180003518  jz      short loc_18000352E
0x18000351a  mov     r8d, 400h
0x180003520  lea     rdx, [rbp+13F0h+var_1430]
0x180003524  lea     rcx, [rsp+14F0h+var_14D0]
0x180003529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000352e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003535  test    rax, rax
0x180003538  jz      short loc_180003544
0x18000353a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000353f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003544  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000354b  test    rax, rax
0x18000354e  jz      short loc_180003561
0x180003550  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003555  jnz     short loc_180003561
0x180003557  lea     rcx, [rsp+14F0h+var_14D0]
0x18000355c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003561  cmp     [rsp+14F0h+var_14C8], r15d
0x180003566  jge     loc_180003674
0x18000356c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180003573  jnz     short loc_180003594
0x180003575  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000357c  test    rax, rax
0x18000357f  jz      short loc_18000358A
0x180003581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003586  test    al, al
0x180003588  jmp     short loc_180003592
0x18000358a  call    cs:__imp_IsDebuggerPresent
0x180003590  test    eax, eax
0x180003592  jz      short loc_18000359B
0x180003594  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003599  jz      short loc_1800035C1
0x18000359b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800035a2  test    rax, rax
0x1800035a5  jz      short loc_18000361A
0x1800035a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800035ae  jnz     short loc_18000361A
0x1800035b0  xor     r8d, r8d
0x1800035b3  xor     edx, edx
0x1800035b5  lea     rcx, [rsp+14F0h+var_14D0]
0x1800035ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035bf  jmp     short loc_18000361A
0x1800035c1  mov     ebx, 800h
0x1800035c6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800035cd  test    rax, rax
0x1800035d0  jz      short loc_1800035EF
0x1800035d2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800035d9  jnz     short loc_1800035EF
0x1800035db  mov     r8d, ebx
0x1800035de  lea     rdx, [rbp+13F0h+OutputString]
0x1800035e5  lea     rcx, [rsp+14F0h+var_14D0]
0x1800035ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035ef  cmp     [rbp+13F0h+OutputString], r15w
0x1800035f7  jnz     short loc_18000360D
0x1800035f9  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800035fe  mov     rdx, rbx; unsigned __int16 *
0x180003601  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003608  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000360d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003614  call    cs:__imp_OutputDebugStringW
0x18000361a  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000361f  jnz     short loc_18000362A
0x180003621  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180003628  jz      short loc_18000363C
0x18000362a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003631  test    rax, rax
0x180003634  jz      short loc_18000363C
0x180003636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000363b  nop
0x18000363c  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003641  jnz     short loc_180003669
0x180003643  mov     rcx, [rbp+13F0h+var_30]
0x18000364a  xor     rcx, rsp; StackCookie
0x18000364d  call    __security_check_cookie
0x180003652  mov     rbx, [rsp+14F0h+arg_10]
0x18000365a  add     rsp, 14D0h
0x180003661  pop     r15
0x180003663  pop     r14
0x180003665  pop     rdi
0x180003666  pop     rsi
0x180003667  pop     rbp
0x180003668  retn
0x180003669  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000366e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003674  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
