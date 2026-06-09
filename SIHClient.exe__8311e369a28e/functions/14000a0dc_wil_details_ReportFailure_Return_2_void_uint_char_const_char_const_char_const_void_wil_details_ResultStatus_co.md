# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x14000a0dc`
- end: `0x14000a3dc`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `768`
- prototype: `void __fastcall(unsigned __int64, int, unsigned __int64, unsigned __int64, unsigned __int64, __int64, int *, _WORD *, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x140009bc0`

## callees

- `0x1400078ac`
- `0x140007cac`
- `0x140007f10`
- `0x140008c10`
- `0x140008e74`
- `0x140009ad0`
- `0x14000a0dc`
- `0x140045dc0`
- `0x14004cc90`
- `0x14004cd00`
- `0x14004cd80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a1f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a1f5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000a379`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000a379`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000a2e9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000a2e9`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<2>(
        unsigned __int64 a1,
        int a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        unsigned __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8,
        int a9,
        int a10)
{
  int v14; // edx
  int v15; // ebx
  int v16; // edx
  unsigned int v17; // ebx
  bool v18; // zf
  const struct wil::FailureInfo *v19; // rdx
  unsigned __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v21; // r9
  wil::details *v22; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v23[20]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v24[1024]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR OutputString[2048]; // [rsp+4F0h] [rbp+3F0h] BYREF

  memset(v23, 0, 0x98u);
  OutputString[0] = 0;
  v24[0] = 0;
  v15 = *a7;
  LODWORD(v23[1]) = v15;
  HIDWORD(v23[1]) = a7[1];
  if ( v15 >= 0 )
  {
    v15 = -2147024228;
    LODWORD(v22) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v22);
    LODWORD(v23[1]) = -2147024228;
    HIDWORD(v23[1]) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v16);
  }
  v17 = wil::details::RecordLog((wil::details *)(unsigned int)v15, v14);
  LODWORD(v23[0]) = 2;
  HIDWORD(v23[0]) = a10;
  if ( a7[2] == 1 )
    HIDWORD(v23[0]) = a10 | 8;
  LODWORD(v23[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v18 = *a8 == 0, v23[3] = (unsigned __int64)a8, v18) )
    v23[3] = 0;
  LODWORD(v23[4]) = GetCurrentThreadId();
  v23[7] = a3;
  v23[8] = __PAIR64__(v17, a2);
  v23[5] = a5;
  v23[6] = a4;
  v23[17] = a6;
  v23[18] = a1;
  memset(&v23[9], 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    v23[16] = wil::details::g_pfnGetModuleName(IsDebuggerPresent);
  else
    v23[16] = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v23);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v23, v24, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v23);
  if ( wil::details::g_pfnOriginateCallback && (v23[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v23);
  if ( SLODWORD(v23[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)IsDebuggerPresent);
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
         (_DWORD)IsDebuggerPresent))
    && (v23[0] & 0x200000000LL) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v23, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)v23, v21);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(v23, 0, 0);
  }
  if ( ((v23[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  if ( (v23[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v23, v19);
}

```

## disassembly

```asm
0x14000a0dc  push    rbp
0x14000a0de  push    rbx
0x14000a0df  push    rsi
0x14000a0e0  push    rdi
0x14000a0e1  push    r12
0x14000a0e3  push    r13
0x14000a0e5  push    r14
0x14000a0e7  push    r15
0x14000a0e9  lea     rbp, [rsp-1408h]
0x14000a0f1  mov     eax, 1508h
0x14000a0f6  call    _alloca_probe
0x14000a0fb  sub     rsp, rax
0x14000a0fe  mov     rax, cs:__security_cookie
0x14000a105  xor     rax, rsp
0x14000a108  mov     [rbp+1440h+var_50], rax
0x14000a10f  mov     r12, r9
0x14000a112  mov     r15, r8
0x14000a115  mov     r14d, edx
0x14000a118  mov     rsi, rcx
0x14000a11b  mov     r13, [rbp+1440h+arg_20]
0x14000a122  mov     rax, [rbp+1440h+arg_28]
0x14000a129  mov     [rsp+1540h+var_1500], rax
0x14000a12e  xor     edx, edx; Val
0x14000a130  mov     r8d, 98h; Size
0x14000a136  lea     rcx, [rsp+1540h+var_14F0]; void *
0x14000a13b  call    memset
0x14000a140  nop
0x14000a141  xor     ecx, ecx
0x14000a143  mov     [rbp+1440h+OutputString], cx
0x14000a14a  mov     [rbp+1440h+var_1450], cl
0x14000a14d  mov     rdi, [rbp+1440h+arg_30]
0x14000a154  mov     ebx, [rdi]
0x14000a156  mov     [rsp+1540h+var_14E8], ebx
0x14000a15a  mov     eax, [rdi+4]
0x14000a15d  mov     [rsp+1540h+var_14E4], eax
0x14000a161  test    ebx, ebx
0x14000a163  js      short loc_14000A19D
0x14000a165  mov     ebx, 8007029Ch
0x14000a16a  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x14000a16e  mov     rax, [rsp+1540h+var_1500]
0x14000a173  mov     [rsp+1540h+var_1518], rax; __int64
0x14000a178  mov     [rsp+1540h+var_1520], r13; __int64
0x14000a17d  mov     r9, r12; int
0x14000a180  mov     r8, r15; int
0x14000a183  mov     edx, r14d; int
0x14000a186  mov     rcx, rsi; int
0x14000a189  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000a18e  mov     [rsp+1540h+var_14E8], ebx
0x14000a192  mov     ecx, ebx; this
0x14000a194  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000a199  mov     [rsp+1540h+var_14E4], eax
0x14000a19d  mov     ecx, ebx; this
0x14000a19f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14000a1a4  mov     ebx, eax
0x14000a1a6  mov     dword ptr [rsp+1540h+var_14F0], 2
0x14000a1ae  mov     ecx, [rbp+1440h+arg_48]
0x14000a1b4  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x14000a1b8  cmp     dword ptr [rdi+8], 1
0x14000a1bc  jnz     short loc_14000A1C5
0x14000a1be  or      ecx, 8
0x14000a1c1  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x14000a1c5  mov     ecx, 1
0x14000a1ca  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000a1d2  inc     ecx
0x14000a1d4  mov     [rsp+1540h+var_14E0], ecx
0x14000a1d8  mov     rax, [rbp+1440h+arg_38]
0x14000a1df  xor     edi, edi
0x14000a1e1  test    rax, rax
0x14000a1e4  jz      short loc_14000A1F0
0x14000a1e6  cmp     [rax], di
0x14000a1e9  mov     [rsp+1540h+var_14D8], rax
0x14000a1ee  jnz     short loc_14000A1F5
0x14000a1f0  mov     [rsp+1540h+var_14D8], rdi
0x14000a1f5  call    cs:__imp_GetCurrentThreadId
0x14000a1fb  mov     [rsp+1540h+var_14D0], eax
0x14000a1ff  mov     [rbp+1440h+var_14B8], r15
0x14000a203  mov     [rbp+1440h+var_14B0], r14d
0x14000a207  mov     [rbp+1440h+var_14AC], ebx
0x14000a20a  mov     [rsp+1540h+var_14C8], r13
0x14000a20f  mov     [rbp+1440h+var_14C0], r12
0x14000a213  mov     rax, [rsp+1540h+var_1500]
0x14000a218  mov     [rbp+1440h+var_1468], rax
0x14000a21c  mov     [rbp+1440h+var_1460], rsi
0x14000a220  mov     [rbp+1440h+var_14A8], rdi
0x14000a224  xorps   xmm0, xmm0
0x14000a227  xor     eax, eax
0x14000a229  movups  [rbp+1440h+var_1488], xmm0
0x14000a22d  mov     [rbp+1440h+var_1478], rax
0x14000a231  xorps   xmm1, xmm1
0x14000a234  movups  [rbp+1440h+var_14A0], xmm1
0x14000a238  mov     [rbp+1440h+var_1490], rax
0x14000a23c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000a243  test    rax, rax
0x14000a246  jz      short loc_14000A253
0x14000a248  call    _guard_dispatch_icall
0x14000a24d  mov     [rbp+1440h+var_1470], rax
0x14000a251  jmp     short loc_14000A257
0x14000a253  mov     [rbp+1440h+var_1470], rdi
0x14000a257  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000a25e  test    rax, rax
0x14000a261  jz      short loc_14000A26D
0x14000a263  lea     rcx, [rsp+1540h+var_14F0]
0x14000a268  call    _guard_dispatch_icall
0x14000a26d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000a274  test    rax, rax
0x14000a277  jz      short loc_14000A28D
0x14000a279  mov     r8d, 400h
0x14000a27f  lea     rdx, [rbp+1440h+var_1450]
0x14000a283  lea     rcx, [rsp+1540h+var_14F0]
0x14000a288  call    _guard_dispatch_icall
0x14000a28d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000a294  test    rax, rax
0x14000a297  jz      short loc_14000A2A3
0x14000a299  lea     rcx, [rsp+1540h+var_14F0]
0x14000a29e  call    _guard_dispatch_icall
0x14000a2a3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000a2aa  test    rax, rax
0x14000a2ad  jz      short loc_14000A2C0
0x14000a2af  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x14000a2b4  jnz     short loc_14000A2C0
0x14000a2b6  lea     rcx, [rsp+1540h+var_14F0]
0x14000a2bb  call    _guard_dispatch_icall
0x14000a2c0  cmp     [rsp+1540h+var_14E8], edi
0x14000a2c4  jge     loc_14000A3D6
0x14000a2ca  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000a2d1  jnz     short loc_14000A2FA
0x14000a2d3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000a2da  test    rax, rax
0x14000a2dd  jz      short loc_14000A2E9
0x14000a2df  call    _guard_dispatch_icall
0x14000a2e4  movzx   ecx, al
0x14000a2e7  jmp     short loc_14000A2F6
0x14000a2e9  call    cs:__imp_IsDebuggerPresent
0x14000a2ef  mov     ecx, edi
0x14000a2f1  test    eax, eax
0x14000a2f3  setnz   cl
0x14000a2f6  test    ecx, ecx
0x14000a2f8  jz      short loc_14000A301
0x14000a2fa  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x14000a2ff  jz      short loc_14000A327
0x14000a301  mov     rax, cs:g_pfnResultLoggingCallback
0x14000a308  test    rax, rax
0x14000a30b  jz      short loc_14000A37F
0x14000a30d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000a314  jnz     short loc_14000A37F
0x14000a316  xor     r8d, r8d
0x14000a319  xor     edx, edx
0x14000a31b  lea     rcx, [rsp+1540h+var_14F0]
0x14000a320  call    _guard_dispatch_icall
0x14000a325  jmp     short loc_14000A37F
0x14000a327  mov     ebx, 800h
0x14000a32c  mov     rax, cs:g_pfnResultLoggingCallback
0x14000a333  test    rax, rax
0x14000a336  jz      short loc_14000A355
0x14000a338  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000a33f  jnz     short loc_14000A355
0x14000a341  mov     r8d, ebx
0x14000a344  lea     rdx, [rbp+1440h+OutputString]
0x14000a34b  lea     rcx, [rsp+1540h+var_14F0]
0x14000a350  call    _guard_dispatch_icall
0x14000a355  cmp     [rbp+1440h+OutputString], di
0x14000a35c  jnz     short loc_14000A372
0x14000a35e  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x14000a363  mov     rdx, rbx; wchar_t *
0x14000a366  lea     rcx, [rbp+1440h+OutputString]; this
0x14000a36d  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x14000a372  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x14000a379  call    cs:__imp_OutputDebugStringW
0x14000a37f  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x14000a384  jnz     short loc_14000A38F
0x14000a386  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000a38d  jz      short loc_14000A3A1
0x14000a38f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000a396  test    rax, rax
0x14000a399  jz      short loc_14000A3A1
0x14000a39b  call    _guard_dispatch_icall
0x14000a3a0  nop
0x14000a3a1  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x14000a3a6  jnz     short loc_14000A3CB
0x14000a3a8  mov     rcx, [rbp+1440h+var_50]
0x14000a3af  xor     rcx, rsp; StackCookie
0x14000a3b2  call    __security_check_cookie
0x14000a3b7  add     rsp, 1508h
0x14000a3be  pop     r15
0x14000a3c0  pop     r14
0x14000a3c2  pop     r13
0x14000a3c4  pop     r12
0x14000a3c6  pop     rdi
0x14000a3c7  pop     rsi
0x14000a3c8  pop     rbx
0x14000a3c9  pop     rbp
0x14000a3ca  retn
0x14000a3cb  lea     rcx, [rsp+1540h+var_14F0]; this
0x14000a3d0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000a3d6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
