# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002f64`
- end: `0x18000320c`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `680`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002a04`

## callees

- `0x180001960`
- `0x1800022ea`
- `0x180002f64`
- `0x180004074`
- `0x180004f90`
- `0x180005fe0`
- `0x1800060bc`
- `0x180011d10`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003027`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003027`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000311c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000311c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800031a6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800031a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  int v10; // r14d
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  _WORD *v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v16 = *a8 == 0, v22 = a8, v16) )
    v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = 0;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0, v15);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048, v15);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180002f64  mov     [rsp-8+arg_0], rbx
0x180002f69  push    rbp
0x180002f6a  push    rsi
0x180002f6b  push    rdi
0x180002f6c  push    r14
0x180002f6e  push    r15
0x180002f70  lea     rbp, [rsp-13D0h]
0x180002f78  mov     eax, 14D0h
0x180002f7d  call    _alloca_probe
0x180002f82  sub     rsp, rax
0x180002f85  mov     rax, cs:__security_cookie
0x180002f8c  xor     rax, rsp
0x180002f8f  mov     [rbp+13F0h+var_30], rax
0x180002f96  mov     rdi, r8
0x180002f99  mov     ebx, edx
0x180002f9b  mov     rsi, [rbp+13F0h+arg_28]
0x180002fa2  xor     edx, edx; Val
0x180002fa4  mov     r8d, 98h; Size
0x180002faa  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002faf  call    memset_0
0x180002fb4  nop
0x180002fb5  xor     r15d, r15d
0x180002fb8  mov     [rbp+13F0h+OutputString], r15w
0x180002fc0  mov     [rbp+13F0h+var_1430], r15b
0x180002fc4  mov     rdx, [rbp+13F0h+arg_30]; int
0x180002fcb  mov     ecx, [rdx]; this
0x180002fcd  mov     [rsp+14F0h+var_14C8], ecx
0x180002fd1  mov     eax, [rdx+4]
0x180002fd4  mov     [rsp+14F0h+var_14C4], eax
0x180002fd8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002fdd  mov     r14d, eax
0x180002fe0  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180002fe8  mov     ecx, r15d
0x180002feb  lea     eax, [r15+8]
0x180002fef  cmp     dword ptr [rdx+8], 1
0x180002ff3  cmovz   ecx, eax
0x180002ff6  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002ffa  lea     ecx, [rax-7]
0x180002ffd  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003005  inc     ecx
0x180003007  mov     [rsp+14F0h+var_14C0], ecx
0x18000300b  mov     rcx, [rbp+13F0h+arg_38]
0x180003012  test    rcx, rcx
0x180003015  jz      short loc_180003022
0x180003017  cmp     [rcx], r15w
0x18000301b  mov     [rsp+14F0h+var_14B8], rcx
0x180003020  jnz     short loc_180003027
0x180003022  mov     [rsp+14F0h+var_14B8], r15
0x180003027  call    cs:__imp_GetCurrentThreadId
0x18000302d  mov     [rsp+14F0h+var_14B0], eax
0x180003031  mov     [rsp+14F0h+var_1498], rdi
0x180003036  mov     [rsp+14F0h+var_1490], ebx
0x18000303a  mov     [rsp+14F0h+var_148C], r14d
0x18000303f  mov     [rsp+14F0h+var_14A8], r15
0x180003044  mov     [rsp+14F0h+var_14A0], r15
0x180003049  mov     [rbp+13F0h+var_1448], rsi
0x18000304d  mov     [rbp+13F0h+var_1440], r15
0x180003051  mov     [rsp+14F0h+var_1488], r15
0x180003056  xorps   xmm0, xmm0
0x180003059  xor     eax, eax
0x18000305b  movups  [rbp+13F0h+var_1468], xmm0
0x18000305f  mov     [rbp+13F0h+var_1458], rax
0x180003063  xorps   xmm1, xmm1
0x180003066  movups  [rsp+14F0h+var_1480], xmm1
0x18000306b  mov     [rbp+13F0h+var_1470], rax
0x18000306f  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003076  test    rax, rax
0x180003079  jz      short loc_180003086
0x18000307b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003080  mov     [rbp+13F0h+var_1450], rax
0x180003084  jmp     short loc_18000308A
0x180003086  mov     [rbp+13F0h+var_1450], r15
0x18000308a  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003091  test    rax, rax
0x180003094  jz      short loc_1800030A0
0x180003096  lea     rcx, [rsp+14F0h+var_14D0]
0x18000309b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030a0  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800030a7  test    rax, rax
0x1800030aa  jz      short loc_1800030C0
0x1800030ac  mov     r8d, 400h
0x1800030b2  lea     rdx, [rbp+13F0h+var_1430]
0x1800030b6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800030bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030c0  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800030c7  test    rax, rax
0x1800030ca  jz      short loc_1800030D6
0x1800030cc  lea     rcx, [rsp+14F0h+var_14D0]
0x1800030d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030d6  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800030dd  test    rax, rax
0x1800030e0  jz      short loc_1800030F3
0x1800030e2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800030e7  jnz     short loc_1800030F3
0x1800030e9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800030ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030f3  cmp     [rsp+14F0h+var_14C8], r15d
0x1800030f8  jge     loc_180003206
0x1800030fe  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180003105  jnz     short loc_180003126
0x180003107  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000310e  test    rax, rax
0x180003111  jz      short loc_18000311C
0x180003113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003118  test    al, al
0x18000311a  jmp     short loc_180003124
0x18000311c  call    cs:__imp_IsDebuggerPresent
0x180003122  test    eax, eax
0x180003124  jz      short loc_18000312D
0x180003126  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000312b  jz      short loc_180003153
0x18000312d  mov     rax, cs:g_pfnResultLoggingCallback
0x180003134  test    rax, rax
0x180003137  jz      short loc_1800031AC
0x180003139  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003140  jnz     short loc_1800031AC
0x180003142  xor     r8d, r8d
0x180003145  xor     edx, edx
0x180003147  lea     rcx, [rsp+14F0h+var_14D0]
0x18000314c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003151  jmp     short loc_1800031AC
0x180003153  mov     ebx, 800h
0x180003158  mov     rax, cs:g_pfnResultLoggingCallback
0x18000315f  test    rax, rax
0x180003162  jz      short loc_180003181
0x180003164  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000316b  jnz     short loc_180003181
0x18000316d  mov     r8d, ebx
0x180003170  lea     rdx, [rbp+13F0h+OutputString]
0x180003177  lea     rcx, [rsp+14F0h+var_14D0]
0x18000317c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003181  cmp     [rbp+13F0h+OutputString], r15w
0x180003189  jnz     short loc_18000319F
0x18000318b  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003190  mov     rdx, rbx; unsigned __int16 *
0x180003193  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000319a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000319f  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800031a6  call    cs:__imp_OutputDebugStringW
0x1800031ac  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800031b1  jnz     short loc_1800031BC
0x1800031b3  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800031ba  jz      short loc_1800031CE
0x1800031bc  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800031c3  test    rax, rax
0x1800031c6  jz      short loc_1800031CE
0x1800031c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031cd  nop
0x1800031ce  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800031d3  jnz     short loc_1800031FB
0x1800031d5  mov     rcx, [rbp+13F0h+var_30]
0x1800031dc  xor     rcx, rsp; StackCookie
0x1800031df  call    __security_check_cookie
0x1800031e4  mov     rbx, [rsp+14F0h+arg_0]
0x1800031ec  add     rsp, 14D0h
0x1800031f3  pop     r15
0x1800031f5  pop     r14
0x1800031f7  pop     rdi
0x1800031f8  pop     rsi
0x1800031f9  pop     rbp
0x1800031fa  retn
0x1800031fb  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003200  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003206  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
