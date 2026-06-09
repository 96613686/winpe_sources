# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1400073ac`
- end: `0x140007642`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140006e8c`

## callees

- `0x1400023f3`
- `0x1400073ac`
- `0x14000a4a4`
- `0x14000c498`
- `0x14000e790`
- `0x14000ecd4`
- `0x140011e10`
- `0x140011ed0`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007457`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007457`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140007552`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140007552`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400075dc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400075dc`

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
0x1400073ac  mov     [rsp-8+arg_10], rbx
0x1400073b1  push    rbp
0x1400073b2  push    rsi
0x1400073b3  push    rdi
0x1400073b4  push    r14
0x1400073b6  push    r15
0x1400073b8  lea     rbp, [rsp-13D0h]
0x1400073c0  mov     eax, 14D0h
0x1400073c5  call    _alloca_probe
0x1400073ca  sub     rsp, rax
0x1400073cd  mov     rax, cs:__security_cookie
0x1400073d4  xor     rax, rsp
0x1400073d7  mov     [rbp+13F0h+var_30], rax
0x1400073de  mov     esi, edx
0x1400073e0  mov     r14, rcx
0x1400073e3  mov     rdi, [rbp+13F0h+arg_28]
0x1400073ea  xor     edx, edx; Val
0x1400073ec  mov     r8d, 98h; Size
0x1400073f2  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1400073f7  call    memset_0
0x1400073fc  nop
0x1400073fd  xor     r15d, r15d
0x140007400  mov     [rbp+13F0h+OutputString], r15w
0x140007408  mov     [rbp+13F0h+var_1430], r15b
0x14000740c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x140007413  mov     ecx, [rdx]; this
0x140007415  mov     [rsp+14F0h+var_14C8], ecx
0x140007419  mov     eax, [rdx+4]
0x14000741c  mov     [rsp+14F0h+var_14C4], eax
0x140007420  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140007425  mov     ebx, eax
0x140007427  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x14000742f  mov     ecx, r15d
0x140007432  lea     eax, [r15+8]
0x140007436  cmp     dword ptr [rdx+8], 1
0x14000743a  cmovz   ecx, eax
0x14000743d  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140007441  lea     ecx, [rax-7]
0x140007444  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000744c  inc     ecx
0x14000744e  mov     [rsp+14F0h+var_14C0], ecx
0x140007452  mov     [rsp+14F0h+var_14B8], r15
0x140007457  call    cs:__imp_GetCurrentThreadId
0x14000745d  mov     [rsp+14F0h+var_14B0], eax
0x140007461  lea     rax, aWil; "wil"
0x140007468  mov     [rsp+14F0h+var_1498], rax
0x14000746d  mov     [rsp+14F0h+var_1490], esi
0x140007471  mov     [rsp+14F0h+var_148C], ebx
0x140007475  mov     [rsp+14F0h+var_14A8], r15
0x14000747a  mov     [rsp+14F0h+var_14A0], r15
0x14000747f  mov     [rbp+13F0h+var_1448], rdi
0x140007483  mov     [rbp+13F0h+var_1440], r14
0x140007487  mov     [rsp+14F0h+var_1488], r15
0x14000748c  xorps   xmm0, xmm0
0x14000748f  xor     eax, eax
0x140007491  movups  [rbp+13F0h+var_1468], xmm0
0x140007495  mov     [rbp+13F0h+var_1458], rax
0x140007499  xorps   xmm1, xmm1
0x14000749c  movups  [rsp+14F0h+var_1480], xmm1
0x1400074a1  mov     [rbp+13F0h+var_1470], rax
0x1400074a5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400074ac  test    rax, rax
0x1400074af  jz      short loc_1400074BC
0x1400074b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400074b6  mov     [rbp+13F0h+var_1450], rax
0x1400074ba  jmp     short loc_1400074C0
0x1400074bc  mov     [rbp+13F0h+var_1450], r15
0x1400074c0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400074c7  test    rax, rax
0x1400074ca  jz      short loc_1400074D6
0x1400074cc  lea     rcx, [rsp+14F0h+var_14D0]
0x1400074d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400074d6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400074dd  test    rax, rax
0x1400074e0  jz      short loc_1400074F6
0x1400074e2  mov     r8d, 400h
0x1400074e8  lea     rdx, [rbp+13F0h+var_1430]
0x1400074ec  lea     rcx, [rsp+14F0h+var_14D0]
0x1400074f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400074f6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400074fd  test    rax, rax
0x140007500  jz      short loc_14000750C
0x140007502  lea     rcx, [rsp+14F0h+var_14D0]
0x140007507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000750c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140007513  test    rax, rax
0x140007516  jz      short loc_140007529
0x140007518  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000751d  jnz     short loc_140007529
0x14000751f  lea     rcx, [rsp+14F0h+var_14D0]
0x140007524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007529  cmp     [rsp+14F0h+var_14C8], r15d
0x14000752e  jge     loc_14000763C
0x140007534  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x14000753b  jnz     short loc_14000755C
0x14000753d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140007544  test    rax, rax
0x140007547  jz      short loc_140007552
0x140007549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000754e  test    al, al
0x140007550  jmp     short loc_14000755A
0x140007552  call    cs:__imp_IsDebuggerPresent
0x140007558  test    eax, eax
0x14000755a  jz      short loc_140007563
0x14000755c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140007561  jz      short loc_140007589
0x140007563  mov     rax, cs:g_pfnResultLoggingCallback
0x14000756a  test    rax, rax
0x14000756d  jz      short loc_1400075E2
0x14000756f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140007576  jnz     short loc_1400075E2
0x140007578  xor     r8d, r8d
0x14000757b  xor     edx, edx
0x14000757d  lea     rcx, [rsp+14F0h+var_14D0]
0x140007582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007587  jmp     short loc_1400075E2
0x140007589  mov     ebx, 800h
0x14000758e  mov     rax, cs:g_pfnResultLoggingCallback
0x140007595  test    rax, rax
0x140007598  jz      short loc_1400075B7
0x14000759a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400075a1  jnz     short loc_1400075B7
0x1400075a3  mov     r8d, ebx
0x1400075a6  lea     rdx, [rbp+13F0h+OutputString]
0x1400075ad  lea     rcx, [rsp+14F0h+var_14D0]
0x1400075b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400075b7  cmp     [rbp+13F0h+OutputString], r15w
0x1400075bf  jnz     short loc_1400075D5
0x1400075c1  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1400075c6  mov     rdx, rbx; unsigned __int16 *
0x1400075c9  lea     rcx, [rbp+13F0h+OutputString]; this
0x1400075d0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400075d5  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1400075dc  call    cs:__imp_OutputDebugStringW
0x1400075e2  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1400075e7  jnz     short loc_1400075F2
0x1400075e9  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1400075f0  jz      short loc_140007604
0x1400075f2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400075f9  test    rax, rax
0x1400075fc  jz      short loc_140007604
0x1400075fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007603  nop
0x140007604  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140007609  jnz     short loc_140007631
0x14000760b  mov     rcx, [rbp+13F0h+var_30]
0x140007612  xor     rcx, rsp; StackCookie
0x140007615  call    __security_check_cookie
0x14000761a  mov     rbx, [rsp+14F0h+arg_10]
0x140007622  add     rsp, 14D0h
0x140007629  pop     r15
0x14000762b  pop     r14
0x14000762d  pop     rdi
0x14000762e  pop     rsi
0x14000762f  pop     rbp
0x140007630  retn
0x140007631  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140007636  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000763c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
