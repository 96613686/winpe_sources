# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x14000a3e4`
- end: `0x14000a693`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `687`
- prototype: `void __fastcall(unsigned __int64, unsigned int, unsigned __int64, __int64, int, unsigned __int64, unsigned __int64 *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140009e9c`

## callees

- `0x1400078ac`
- `0x140007c90`
- `0x140008c10`
- `0x140008e74`
- `0x14000a3e4`
- `0x140045dc0`
- `0x14004cc90`
- `0x14004cd00`
- `0x14004cd80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a4aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a4aa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000a632`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000a632`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000a5a0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000a5a0`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        unsigned __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int64 a6,
        unsigned __int64 *a7,
        _WORD *a8)
{
  unsigned int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  bool v14; // zf
  const struct wil::FailureInfo *v15; // rdx
  unsigned __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v17; // r9
  unsigned __int64 v18[20]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v19[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset(v18, 0, 0x98u);
  OutputString[0] = 0;
  v19[0] = 0;
  v18[1] = *a7;
  v11 = wil::details::RecordReturn((wil::details *)LODWORD(v18[1]), (int)a7);
  LODWORD(v18[0]) = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  HIDWORD(v18[0]) = v12;
  LODWORD(v18[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v14 = *a8 == 0, v18[3] = (unsigned __int64)a8, v14) )
    v18[3] = 0;
  LODWORD(v18[4]) = GetCurrentThreadId();
  v18[7] = a3;
  v18[8] = __PAIR64__(v11, a2);
  v18[5] = 0;
  v18[6] = 0;
  v18[17] = a6;
  v18[18] = a1;
  memset(&v18[9], 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    v18[16] = wil::details::g_pfnGetModuleName(IsDebuggerPresent);
  else
    v18[16] = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v18, v19, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v18);
  if ( wil::details::g_pfnOriginateCallback && (v18[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v18);
  if ( SLODWORD(v18[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)IsDebuggerPresent);
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
         (_DWORD)IsDebuggerPresent))
    && (v18[0] & 0x200000000LL) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)v18, v17);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(v18, 0, 0);
  }
  if ( ((v18[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  if ( (v18[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v18, v15);
}

```

## disassembly

```asm
0x14000a3e4  push    rbp
0x14000a3e6  push    rbx
0x14000a3e7  push    rsi
0x14000a3e8  push    rdi
0x14000a3e9  push    r12
0x14000a3eb  push    r14
0x14000a3ed  push    r15
0x14000a3ef  lea     rbp, [rsp-13D0h]
0x14000a3f7  mov     eax, 14D0h
0x14000a3fc  call    _alloca_probe
0x14000a401  sub     rsp, rax
0x14000a404  mov     rax, cs:__security_cookie
0x14000a40b  xor     rax, rsp
0x14000a40e  mov     [rbp+1400h+var_40], rax
0x14000a415  mov     rsi, r8
0x14000a418  mov     edi, edx
0x14000a41a  mov     rbx, rcx
0x14000a41d  mov     r14, [rbp+1400h+arg_28]
0x14000a424  xor     edx, edx; Val
0x14000a426  mov     r8d, 98h; Size
0x14000a42c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x14000a431  call    memset
0x14000a436  nop
0x14000a437  xor     r12d, r12d
0x14000a43a  mov     [rbp+1400h+OutputString], r12w
0x14000a442  mov     [rbp+1400h+var_1440], r12b
0x14000a446  mov     rdx, [rbp+1400h+arg_30]; int
0x14000a44d  mov     ecx, [rdx]; this
0x14000a44f  mov     [rsp+1500h+var_14D8], ecx
0x14000a453  mov     eax, [rdx+4]
0x14000a456  mov     [rsp+1500h+var_14D4], eax
0x14000a45a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000a45f  mov     r15d, eax
0x14000a462  mov     dword ptr [rsp+1500h+var_14E0], 1
0x14000a46a  mov     ecx, r12d
0x14000a46d  lea     eax, [r12+8]
0x14000a472  cmp     dword ptr [rdx+8], 1
0x14000a476  cmovz   ecx, eax
0x14000a479  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x14000a47d  lea     ecx, [rax-7]
0x14000a480  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000a488  inc     ecx
0x14000a48a  mov     [rsp+1500h+var_14D0], ecx
0x14000a48e  mov     rcx, [rbp+1400h+arg_38]
0x14000a495  test    rcx, rcx
0x14000a498  jz      short loc_14000A4A5
0x14000a49a  cmp     [rcx], r12w
0x14000a49e  mov     [rsp+1500h+var_14C8], rcx
0x14000a4a3  jnz     short loc_14000A4AA
0x14000a4a5  mov     [rsp+1500h+var_14C8], r12
0x14000a4aa  call    cs:__imp_GetCurrentThreadId
0x14000a4b0  mov     [rsp+1500h+var_14C0], eax
0x14000a4b4  mov     [rsp+1500h+var_14A8], rsi
0x14000a4b9  mov     [rsp+1500h+var_14A0], edi
0x14000a4bd  mov     [rsp+1500h+var_149C], r15d
0x14000a4c2  mov     [rsp+1500h+var_14B8], r12
0x14000a4c7  mov     [rsp+1500h+var_14B0], r12
0x14000a4cc  mov     [rbp+1400h+var_1458], r14
0x14000a4d0  mov     [rbp+1400h+var_1450], rbx
0x14000a4d4  mov     [rsp+1500h+var_1498], r12
0x14000a4d9  xorps   xmm0, xmm0
0x14000a4dc  xor     eax, eax
0x14000a4de  movups  [rbp+1400h+var_1478], xmm0
0x14000a4e2  mov     [rbp+1400h+var_1468], rax
0x14000a4e6  xorps   xmm1, xmm1
0x14000a4e9  movups  [rsp+1500h+var_1490], xmm1
0x14000a4ee  mov     [rbp+1400h+var_1480], rax
0x14000a4f2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000a4f9  test    rax, rax
0x14000a4fc  jz      short loc_14000A509
0x14000a4fe  call    _guard_dispatch_icall
0x14000a503  mov     [rbp+1400h+var_1460], rax
0x14000a507  jmp     short loc_14000A50D
0x14000a509  mov     [rbp+1400h+var_1460], r12
0x14000a50d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000a514  test    rax, rax
0x14000a517  jz      short loc_14000A523
0x14000a519  lea     rcx, [rsp+1500h+var_14E0]
0x14000a51e  call    _guard_dispatch_icall
0x14000a523  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000a52a  test    rax, rax
0x14000a52d  jz      short loc_14000A543
0x14000a52f  mov     r8d, 400h
0x14000a535  lea     rdx, [rbp+1400h+var_1440]
0x14000a539  lea     rcx, [rsp+1500h+var_14E0]
0x14000a53e  call    _guard_dispatch_icall
0x14000a543  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000a54a  test    rax, rax
0x14000a54d  jz      short loc_14000A559
0x14000a54f  lea     rcx, [rsp+1500h+var_14E0]
0x14000a554  call    _guard_dispatch_icall
0x14000a559  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000a560  test    rax, rax
0x14000a563  jz      short loc_14000A576
0x14000a565  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x14000a56a  jnz     short loc_14000A576
0x14000a56c  lea     rcx, [rsp+1500h+var_14E0]
0x14000a571  call    _guard_dispatch_icall
0x14000a576  cmp     [rsp+1500h+var_14D8], r12d
0x14000a57b  jge     loc_14000A68D
0x14000a581  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x14000a588  jnz     short loc_14000A5B2
0x14000a58a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000a591  test    rax, rax
0x14000a594  jz      short loc_14000A5A0
0x14000a596  call    _guard_dispatch_icall
0x14000a59b  movzx   ecx, al
0x14000a59e  jmp     short loc_14000A5AE
0x14000a5a0  call    cs:__imp_IsDebuggerPresent
0x14000a5a6  mov     ecx, r12d
0x14000a5a9  test    eax, eax
0x14000a5ab  setnz   cl
0x14000a5ae  test    ecx, ecx
0x14000a5b0  jz      short loc_14000A5B9
0x14000a5b2  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x14000a5b7  jz      short loc_14000A5DF
0x14000a5b9  mov     rax, cs:g_pfnResultLoggingCallback
0x14000a5c0  test    rax, rax
0x14000a5c3  jz      short loc_14000A638
0x14000a5c5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000a5cc  jnz     short loc_14000A638
0x14000a5ce  xor     r8d, r8d
0x14000a5d1  xor     edx, edx
0x14000a5d3  lea     rcx, [rsp+1500h+var_14E0]
0x14000a5d8  call    _guard_dispatch_icall
0x14000a5dd  jmp     short loc_14000A638
0x14000a5df  mov     ebx, 800h
0x14000a5e4  mov     rax, cs:g_pfnResultLoggingCallback
0x14000a5eb  test    rax, rax
0x14000a5ee  jz      short loc_14000A60D
0x14000a5f0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000a5f7  jnz     short loc_14000A60D
0x14000a5f9  mov     r8d, ebx
0x14000a5fc  lea     rdx, [rbp+1400h+OutputString]
0x14000a603  lea     rcx, [rsp+1500h+var_14E0]
0x14000a608  call    _guard_dispatch_icall
0x14000a60d  cmp     [rbp+1400h+OutputString], r12w
0x14000a615  jnz     short loc_14000A62B
0x14000a617  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x14000a61c  mov     rdx, rbx; wchar_t *
0x14000a61f  lea     rcx, [rbp+1400h+OutputString]; this
0x14000a626  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x14000a62b  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x14000a632  call    cs:__imp_OutputDebugStringW
0x14000a638  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x14000a63d  jnz     short loc_14000A648
0x14000a63f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x14000a646  jz      short loc_14000A65A
0x14000a648  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000a64f  test    rax, rax
0x14000a652  jz      short loc_14000A65A
0x14000a654  call    _guard_dispatch_icall
0x14000a659  nop
0x14000a65a  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x14000a65f  jnz     short loc_14000A682
0x14000a661  mov     rcx, [rbp+1400h+var_40]
0x14000a668  xor     rcx, rsp; StackCookie
0x14000a66b  call    __security_check_cookie
0x14000a670  add     rsp, 14D0h
0x14000a677  pop     r15
0x14000a679  pop     r14
0x14000a67b  pop     r12
0x14000a67d  pop     rdi
0x14000a67e  pop     rsi
0x14000a67f  pop     rbx
0x14000a680  pop     rbp
0x14000a681  retn
0x14000a682  lea     rcx, [rsp+1500h+var_14E0]; this
0x14000a687  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000a68d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
