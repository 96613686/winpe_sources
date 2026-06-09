# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002c60`
- end: `0x180002f15`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `693`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002f1c`

## callees

- `0x180002250`
- `0x180002484`
- `0x1800025bc`
- `0x180002bb0`
- `0x180002c60`
- `0x180061960`
- `0x180068e30`
- `0x180068ea0`
- `0x180068f20`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002e22`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002e22`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002eb4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002eb4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        unsigned __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int64 a6,
        unsigned __int64 *a7,
        _WORD *a8,
        int a9,
        int a10)
{
  unsigned int v13; // r15d
  __int64 v14; // rdx
  bool v15; // zf
  const struct wil::FailureInfo *v16; // rdx
  unsigned __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v18; // r9
  unsigned __int64 v19[20]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v20[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset(v19, 0, 0x98u);
  OutputString[0] = 0;
  v20[0] = 0;
  v19[1] = *a7;
  v13 = wil::details::RecordReturn((wil::details *)LODWORD(v19[1]), (int)a7);
  LODWORD(v19[0]) = 1;
  HIDWORD(v19[0]) = a10;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    HIDWORD(v19[0]) = a10 | 8;
  LODWORD(v19[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v15 = *a8 == 0, v19[3] = (unsigned __int64)a8, v15) )
    v19[3] = 0;
  LODWORD(v19[4]) = GetCurrentThreadId();
  v19[7] = a3;
  v19[8] = __PAIR64__(v13, a2);
  v19[5] = 0;
  v19[6] = 0;
  v19[17] = a6;
  v19[18] = a1;
  memset(&v19[9], 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    v19[16] = wil::details::g_pfnGetModuleName(IsDebuggerPresent);
  else
    v19[16] = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v19, v20, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v19);
  if ( wil::details::g_pfnOriginateCallback && (v19[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v19);
  if ( SLODWORD(v19[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)IsDebuggerPresent);
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
         (_DWORD)IsDebuggerPresent))
    && (v19[0] & 0x200000000LL) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v19, OutputString, 2048, v18);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)v19, v18);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(v19, 0, 0, v18);
  }
  if ( ((v19[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  if ( (v19[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v19, v16);
}

```

## disassembly

```asm
0x180002c60  push    rbp
0x180002c62  push    rbx
0x180002c63  push    rsi
0x180002c64  push    rdi
0x180002c65  push    r12
0x180002c67  push    r14
0x180002c69  push    r15
0x180002c6b  lea     rbp, [rsp-13D0h]
0x180002c73  mov     eax, 14D0h
0x180002c78  call    _alloca_probe
0x180002c7d  sub     rsp, rax
0x180002c80  mov     rax, cs:__security_cookie
0x180002c87  xor     rax, rsp
0x180002c8a  mov     [rbp+1400h+var_40], rax
0x180002c91  mov     rsi, r8
0x180002c94  mov     edi, edx
0x180002c96  mov     rbx, rcx
0x180002c99  mov     r14, [rbp+1400h+arg_28]
0x180002ca0  xor     edx, edx; Val
0x180002ca2  mov     r8d, 98h; Size
0x180002ca8  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180002cad  call    memset
0x180002cb2  nop
0x180002cb3  xor     r12d, r12d
0x180002cb6  mov     [rbp+1400h+OutputString], r12w
0x180002cbe  mov     [rbp+1400h+var_1440], r12b
0x180002cc2  mov     rdx, [rbp+1400h+arg_30]; int
0x180002cc9  mov     ecx, [rdx]; this
0x180002ccb  mov     [rsp+1500h+var_14D8], ecx
0x180002ccf  mov     eax, [rdx+4]
0x180002cd2  mov     [rsp+1500h+var_14D4], eax
0x180002cd6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002cdb  mov     r15d, eax
0x180002cde  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180002ce6  mov     ecx, [rbp+1400h+arg_48]
0x180002cec  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180002cf0  cmp     dword ptr [rdx+8], 1
0x180002cf4  jnz     short loc_180002CFD
0x180002cf6  or      ecx, 8
0x180002cf9  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180002cfd  mov     ecx, 1
0x180002d02  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002d0a  inc     ecx
0x180002d0c  mov     [rsp+1500h+var_14D0], ecx
0x180002d10  mov     rax, [rbp+1400h+arg_38]
0x180002d17  test    rax, rax
0x180002d1a  jz      short loc_180002D27
0x180002d1c  cmp     [rax], r12w
0x180002d20  mov     [rsp+1500h+var_14C8], rax
0x180002d25  jnz     short loc_180002D2C
0x180002d27  mov     [rsp+1500h+var_14C8], r12
0x180002d2c  call    cs:__imp_GetCurrentThreadId
0x180002d32  mov     [rsp+1500h+var_14C0], eax
0x180002d36  mov     [rsp+1500h+var_14A8], rsi
0x180002d3b  mov     [rsp+1500h+var_14A0], edi
0x180002d3f  mov     [rsp+1500h+var_149C], r15d
0x180002d44  mov     [rsp+1500h+var_14B8], r12
0x180002d49  mov     [rsp+1500h+var_14B0], r12
0x180002d4e  mov     [rbp+1400h+var_1458], r14
0x180002d52  mov     [rbp+1400h+var_1450], rbx
0x180002d56  mov     [rsp+1500h+var_1498], r12
0x180002d5b  xorps   xmm0, xmm0
0x180002d5e  xor     eax, eax
0x180002d60  movups  [rbp+1400h+var_1478], xmm0
0x180002d64  mov     [rbp+1400h+var_1468], rax
0x180002d68  xorps   xmm1, xmm1
0x180002d6b  movups  [rsp+1500h+var_1490], xmm1
0x180002d70  mov     [rbp+1400h+var_1480], rax
0x180002d74  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002d7b  test    rax, rax
0x180002d7e  jz      short loc_180002D8B
0x180002d80  call    _guard_dispatch_icall
0x180002d85  mov     [rbp+1400h+var_1460], rax
0x180002d89  jmp     short loc_180002D8F
0x180002d8b  mov     [rbp+1400h+var_1460], r12
0x180002d8f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002d96  test    rax, rax
0x180002d99  jz      short loc_180002DA5
0x180002d9b  lea     rcx, [rsp+1500h+var_14E0]
0x180002da0  call    _guard_dispatch_icall
0x180002da5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002dac  test    rax, rax
0x180002daf  jz      short loc_180002DC5
0x180002db1  mov     r8d, 400h
0x180002db7  lea     rdx, [rbp+1400h+var_1440]
0x180002dbb  lea     rcx, [rsp+1500h+var_14E0]
0x180002dc0  call    _guard_dispatch_icall
0x180002dc5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002dcc  test    rax, rax
0x180002dcf  jz      short loc_180002DDB
0x180002dd1  lea     rcx, [rsp+1500h+var_14E0]
0x180002dd6  call    _guard_dispatch_icall
0x180002ddb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002de2  test    rax, rax
0x180002de5  jz      short loc_180002DF8
0x180002de7  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180002dec  jnz     short loc_180002DF8
0x180002dee  lea     rcx, [rsp+1500h+var_14E0]
0x180002df3  call    _guard_dispatch_icall
0x180002df8  cmp     [rsp+1500h+var_14D8], r12d
0x180002dfd  jge     loc_180002F0F
0x180002e03  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002e0a  jnz     short loc_180002E34
0x180002e0c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002e13  test    rax, rax
0x180002e16  jz      short loc_180002E22
0x180002e18  call    _guard_dispatch_icall
0x180002e1d  movzx   ecx, al
0x180002e20  jmp     short loc_180002E30
0x180002e22  call    cs:__imp_IsDebuggerPresent
0x180002e28  mov     ecx, r12d
0x180002e2b  test    eax, eax
0x180002e2d  setnz   cl
0x180002e30  test    ecx, ecx
0x180002e32  jz      short loc_180002E3B
0x180002e34  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180002e39  jz      short loc_180002E61
0x180002e3b  mov     rax, cs:g_pfnResultLoggingCallback
0x180002e42  test    rax, rax
0x180002e45  jz      short loc_180002EBA
0x180002e47  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002e4e  jnz     short loc_180002EBA
0x180002e50  xor     r8d, r8d
0x180002e53  xor     edx, edx
0x180002e55  lea     rcx, [rsp+1500h+var_14E0]
0x180002e5a  call    _guard_dispatch_icall
0x180002e5f  jmp     short loc_180002EBA
0x180002e61  mov     ebx, 800h
0x180002e66  mov     rax, cs:g_pfnResultLoggingCallback
0x180002e6d  test    rax, rax
0x180002e70  jz      short loc_180002E8F
0x180002e72  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002e79  jnz     short loc_180002E8F
0x180002e7b  mov     r8d, ebx
0x180002e7e  lea     rdx, [rbp+1400h+OutputString]
0x180002e85  lea     rcx, [rsp+1500h+var_14E0]
0x180002e8a  call    _guard_dispatch_icall
0x180002e8f  cmp     [rbp+1400h+OutputString], r12w
0x180002e97  jnz     short loc_180002EAD
0x180002e99  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180002e9e  mov     rdx, rbx; wchar_t *
0x180002ea1  lea     rcx, [rbp+1400h+OutputString]; this
0x180002ea8  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180002ead  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180002eb4  call    cs:__imp_OutputDebugStringW
0x180002eba  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180002ebf  jnz     short loc_180002ECA
0x180002ec1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002ec8  jz      short loc_180002EDC
0x180002eca  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002ed1  test    rax, rax
0x180002ed4  jz      short loc_180002EDC
0x180002ed6  call    _guard_dispatch_icall
0x180002edb  nop
0x180002edc  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180002ee1  jnz     short loc_180002F04
0x180002ee3  mov     rcx, [rbp+1400h+var_40]
0x180002eea  xor     rcx, rsp; StackCookie
0x180002eed  call    __security_check_cookie
0x180002ef2  add     rsp, 14D0h
0x180002ef9  pop     r15
0x180002efb  pop     r14
0x180002efd  pop     r12
0x180002eff  pop     rdi
0x180002f00  pop     rsi
0x180002f01  pop     rbx
0x180002f02  pop     rbp
0x180002f03  retn
0x180002f04  lea     rcx, [rsp+1500h+var_14E0]; this
0x180002f09  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002f0f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
