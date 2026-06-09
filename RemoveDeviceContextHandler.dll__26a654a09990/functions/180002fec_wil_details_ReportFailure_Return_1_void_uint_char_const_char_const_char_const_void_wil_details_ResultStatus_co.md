# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002fec`
- end: `0x180003280`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002ad4`

## callees

- `0x180002fec`
- `0x180003f84`
- `0x180004c00`
- `0x1800054f0`
- `0x180005678`
- `0x18000c966`
- `0x18000c990`
- `0x18000ca20`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003096`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003096`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003191`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003191`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000321b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000321b`

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
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "wil";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x180002fec  mov     [rsp-8+arg_10], rbx
0x180002ff1  push    rbp
0x180002ff2  push    rsi
0x180002ff3  push    rdi
0x180002ff4  push    r14
0x180002ff6  push    r15
0x180002ff8  lea     rbp, [rsp-13D0h]
0x180003000  mov     eax, 14D0h
0x180003005  call    _alloca_probe
0x18000300a  sub     rsp, rax
0x18000300d  mov     rax, cs:__security_cookie
0x180003014  xor     rax, rsp
0x180003017  mov     [rbp+13F0h+var_30], rax
0x18000301e  mov     rdi, [rbp+13F0h+arg_28]
0x180003025  mov     esi, edx
0x180003027  mov     r14, rcx
0x18000302a  xor     edx, edx; Val
0x18000302c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003031  mov     r8d, 98h; Size
0x180003037  call    memset_0
0x18000303c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180003043  xor     r15d, r15d
0x180003046  mov     [rbp+13F0h+OutputString], r15w
0x18000304e  mov     [rbp+13F0h+var_1430], r15b
0x180003052  mov     ecx, [rdx]; this
0x180003054  mov     eax, [rdx+4]
0x180003057  mov     [rsp+14F0h+var_14C8], ecx
0x18000305b  mov     [rsp+14F0h+var_14C4], eax
0x18000305f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003064  cmp     dword ptr [rdx+8], 1
0x180003068  mov     ebx, eax
0x18000306a  lea     eax, [r15+8]
0x18000306e  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180003076  mov     ecx, r15d
0x180003079  cmovz   ecx, eax
0x18000307c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003080  lea     ecx, [rax-7]
0x180003083  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000308b  inc     ecx
0x18000308d  mov     [rsp+14F0h+var_14B8], r15
0x180003092  mov     [rsp+14F0h+var_14C0], ecx
0x180003096  call    cs:__imp_GetCurrentThreadId
0x18000309c  xorps   xmm0, xmm0
0x18000309f  mov     [rsp+14F0h+var_1490], esi
0x1800030a3  mov     [rsp+14F0h+var_14B0], eax
0x1800030a7  xorps   xmm1, xmm1
0x1800030aa  lea     rax, aWil; "wil"
0x1800030b1  mov     [rsp+14F0h+var_148C], ebx
0x1800030b5  mov     [rsp+14F0h+var_1498], rax
0x1800030ba  xor     eax, eax
0x1800030bc  mov     [rbp+13F0h+var_1458], rax
0x1800030c0  mov     [rbp+13F0h+var_1470], rax
0x1800030c4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800030cb  mov     [rsp+14F0h+var_14A8], r15
0x1800030d0  mov     [rsp+14F0h+var_14A0], r15
0x1800030d5  mov     [rbp+13F0h+var_1448], rdi
0x1800030d9  mov     [rbp+13F0h+var_1440], r14
0x1800030dd  mov     [rsp+14F0h+var_1488], r15
0x1800030e2  movups  [rbp+13F0h+var_1468], xmm0
0x1800030e6  movups  [rsp+14F0h+var_1480], xmm1
0x1800030eb  test    rax, rax
0x1800030ee  jz      short loc_1800030FB
0x1800030f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030f5  mov     [rbp+13F0h+var_1450], rax
0x1800030f9  jmp     short loc_1800030FF
0x1800030fb  mov     [rbp+13F0h+var_1450], r15
0x1800030ff  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003106  test    rax, rax
0x180003109  jz      short loc_180003115
0x18000310b  lea     rcx, [rsp+14F0h+var_14D0]
0x180003110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003115  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000311c  test    rax, rax
0x18000311f  jz      short loc_180003135
0x180003121  mov     r8d, 400h
0x180003127  lea     rdx, [rbp+13F0h+var_1430]
0x18000312b  lea     rcx, [rsp+14F0h+var_14D0]
0x180003130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003135  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000313c  test    rax, rax
0x18000313f  jz      short loc_18000314B
0x180003141  lea     rcx, [rsp+14F0h+var_14D0]
0x180003146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000314b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003152  test    rax, rax
0x180003155  jz      short loc_180003168
0x180003157  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000315c  jnz     short loc_180003168
0x18000315e  lea     rcx, [rsp+14F0h+var_14D0]
0x180003163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003168  cmp     [rsp+14F0h+var_14C8], r15d
0x18000316d  jge     loc_18000326F
0x180003173  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000317a  jnz     short loc_18000319B
0x18000317c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003183  test    rax, rax
0x180003186  jz      short loc_180003191
0x180003188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000318d  test    al, al
0x18000318f  jmp     short loc_180003199
0x180003191  call    cs:__imp_IsDebuggerPresent
0x180003197  test    eax, eax
0x180003199  jz      short loc_1800031A2
0x18000319b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800031a0  jz      short loc_1800031C8
0x1800031a2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800031a9  test    rax, rax
0x1800031ac  jz      short loc_180003221
0x1800031ae  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800031b5  jnz     short loc_180003221
0x1800031b7  xor     r8d, r8d
0x1800031ba  lea     rcx, [rsp+14F0h+var_14D0]
0x1800031bf  xor     edx, edx
0x1800031c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031c6  jmp     short loc_180003221
0x1800031c8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800031cf  mov     ebx, 800h
0x1800031d4  test    rax, rax
0x1800031d7  jz      short loc_1800031F6
0x1800031d9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800031e0  jnz     short loc_1800031F6
0x1800031e2  mov     r8d, ebx
0x1800031e5  lea     rdx, [rbp+13F0h+OutputString]
0x1800031ec  lea     rcx, [rsp+14F0h+var_14D0]
0x1800031f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031f6  cmp     [rbp+13F0h+OutputString], r15w
0x1800031fe  jnz     short loc_180003214
0x180003200  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003205  mov     rdx, rbx; unsigned __int16 *
0x180003208  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000320f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003214  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000321b  call    cs:__imp_OutputDebugStringW
0x180003221  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003226  jnz     short loc_180003231
0x180003228  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000322f  jz      short loc_180003242
0x180003231  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003238  test    rax, rax
0x18000323b  jz      short loc_180003242
0x18000323d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003242  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003247  jnz     short loc_180003275
0x180003249  mov     rcx, [rbp+13F0h+var_30]
0x180003250  xor     rcx, rsp; StackCookie
0x180003253  call    __security_check_cookie
0x180003258  mov     rbx, [rsp+14F0h+arg_10]
0x180003260  add     rsp, 14D0h
0x180003267  pop     r15
0x180003269  pop     r14
0x18000326b  pop     rdi
0x18000326c  pop     rsi
0x18000326d  pop     rbp
0x18000326e  retn
0x18000326f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003275  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000327a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
