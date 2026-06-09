# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140004d94`
- end: `0x140005033`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `671`
- prototype: `void __fastcall(unsigned __int64, unsigned int, __int64, __int64, int, unsigned __int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400049f0`

## callees

- `0x14000142c`
- `0x1400018b4`
- `0x1400029fc`
- `0x140002c20`
- `0x140004d94`
- `0x14000a390`
- `0x14000f460`
- `0x14000f4d0`
- `0x14000f550`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140004e3f`
- `KERNEL32!GetCurrentThreadId` at `0x140004e3f`
- `KERNEL32!OutputDebugStringW` at `0x140004fcd`
- `KERNEL32!OutputDebugStringW` at `0x140004fcd`
- `KERNEL32!IsDebuggerPresent` at `0x140004f3b`
- `KERNEL32!IsDebuggerPresent` at `0x140004f3b`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        unsigned __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int64 a6,
        unsigned __int64 *a7)
{
  unsigned int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  unsigned __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v14; // r9
  unsigned __int64 v15[20]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v16[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset(v15, 0, 0x98u);
  OutputString[0] = 0;
  v16[0] = 0;
  v15[1] = *a7;
  v9 = wil::details::RecordReturn((wil::details *)LODWORD(v15[1]), (int)a7);
  LODWORD(v15[0]) = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  HIDWORD(v15[0]) = v10;
  LODWORD(v15[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v15[3] = 0;
  LODWORD(v15[4]) = GetCurrentThreadId();
  v15[7] = (unsigned __int64)"wil";
  v15[8] = __PAIR64__(v9, a2);
  v15[5] = 0;
  v15[6] = 0;
  v15[17] = a6;
  v15[18] = a1;
  memset(&v15[9], 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    v15[16] = wil::details::g_pfnGetModuleName(IsDebuggerPresent);
  else
    v15[16] = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v15);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v15, v16, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v15);
  if ( wil::details::g_pfnOriginateCallback && (v15[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v15);
  if ( SLODWORD(v15[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)IsDebuggerPresent);
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
         (_DWORD)IsDebuggerPresent))
    && (v15[0] & 0x200000000LL) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v15, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)v15, v14);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(v15, 0, 0);
  }
  if ( ((v15[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  if ( (v15[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v15, v12);
}

```

## disassembly

```asm
0x140004d94  mov     [rsp-8+arg_10], rbx
0x140004d99  push    rbp
0x140004d9a  push    rsi
0x140004d9b  push    rdi
0x140004d9c  push    r14
0x140004d9e  push    r15
0x140004da0  lea     rbp, [rsp-13D0h]
0x140004da8  mov     eax, 14D0h
0x140004dad  call    _alloca_probe
0x140004db2  sub     rsp, rax
0x140004db5  mov     rax, cs:__security_cookie
0x140004dbc  xor     rax, rsp
0x140004dbf  mov     [rbp+13F0h+var_30], rax
0x140004dc6  mov     esi, edx
0x140004dc8  mov     r14, rcx
0x140004dcb  mov     rdi, [rbp+13F0h+arg_28]
0x140004dd2  xor     edx, edx; Val
0x140004dd4  mov     r8d, 98h; Size
0x140004dda  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140004ddf  call    memset
0x140004de4  nop
0x140004de5  xor     r15d, r15d
0x140004de8  mov     [rbp+13F0h+OutputString], r15w
0x140004df0  mov     [rbp+13F0h+var_1430], r15b
0x140004df4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x140004dfb  mov     ecx, [rdx]; this
0x140004dfd  mov     [rsp+14F0h+var_14C8], ecx
0x140004e01  mov     eax, [rdx+4]
0x140004e04  mov     [rsp+14F0h+var_14C4], eax
0x140004e08  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140004e0d  mov     ebx, eax
0x140004e0f  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x140004e17  mov     ecx, r15d
0x140004e1a  lea     eax, [r15+8]
0x140004e1e  cmp     dword ptr [rdx+8], 1
0x140004e22  cmovz   ecx, eax
0x140004e25  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140004e29  lea     ecx, [rax-7]
0x140004e2c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140004e34  inc     ecx
0x140004e36  mov     [rsp+14F0h+var_14C0], ecx
0x140004e3a  mov     [rsp+14F0h+var_14B8], r15
0x140004e3f  call    cs:__imp_GetCurrentThreadId
0x140004e45  mov     [rsp+14F0h+var_14B0], eax
0x140004e49  lea     rax, aWil; "wil"
0x140004e50  mov     [rsp+14F0h+var_1498], rax
0x140004e55  mov     [rsp+14F0h+var_1490], esi
0x140004e59  mov     [rsp+14F0h+var_148C], ebx
0x140004e5d  mov     [rsp+14F0h+var_14A8], r15
0x140004e62  mov     [rsp+14F0h+var_14A0], r15
0x140004e67  mov     [rbp+13F0h+var_1448], rdi
0x140004e6b  mov     [rbp+13F0h+var_1440], r14
0x140004e6f  mov     [rsp+14F0h+var_1488], r15
0x140004e74  xorps   xmm0, xmm0
0x140004e77  xor     eax, eax
0x140004e79  movups  [rbp+13F0h+var_1468], xmm0
0x140004e7d  mov     [rbp+13F0h+var_1458], rax
0x140004e81  xorps   xmm1, xmm1
0x140004e84  movups  [rsp+14F0h+var_1480], xmm1
0x140004e89  mov     [rbp+13F0h+var_1470], rax
0x140004e8d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140004e94  test    rax, rax
0x140004e97  jz      short loc_140004EA4
0x140004e99  call    _guard_dispatch_icall
0x140004e9e  mov     [rbp+13F0h+var_1450], rax
0x140004ea2  jmp     short loc_140004EA8
0x140004ea4  mov     [rbp+13F0h+var_1450], r15
0x140004ea8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004eaf  test    rax, rax
0x140004eb2  jz      short loc_140004EBE
0x140004eb4  lea     rcx, [rsp+14F0h+var_14D0]
0x140004eb9  call    _guard_dispatch_icall
0x140004ebe  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004ec5  test    rax, rax
0x140004ec8  jz      short loc_140004EDE
0x140004eca  mov     r8d, 400h
0x140004ed0  lea     rdx, [rbp+13F0h+var_1430]
0x140004ed4  lea     rcx, [rsp+14F0h+var_14D0]
0x140004ed9  call    _guard_dispatch_icall
0x140004ede  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004ee5  test    rax, rax
0x140004ee8  jz      short loc_140004EF4
0x140004eea  lea     rcx, [rsp+14F0h+var_14D0]
0x140004eef  call    _guard_dispatch_icall
0x140004ef4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004efb  test    rax, rax
0x140004efe  jz      short loc_140004F11
0x140004f00  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140004f05  jnz     short loc_140004F11
0x140004f07  lea     rcx, [rsp+14F0h+var_14D0]
0x140004f0c  call    _guard_dispatch_icall
0x140004f11  cmp     [rsp+14F0h+var_14C8], r15d
0x140004f16  jge     loc_14000502D
0x140004f1c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x140004f23  jnz     short loc_140004F4D
0x140004f25  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004f2c  test    rax, rax
0x140004f2f  jz      short loc_140004F3B
0x140004f31  call    _guard_dispatch_icall
0x140004f36  movzx   ecx, al
0x140004f39  jmp     short loc_140004F49
0x140004f3b  call    cs:__imp_IsDebuggerPresent
0x140004f41  mov     ecx, r15d
0x140004f44  test    eax, eax
0x140004f46  setnz   cl
0x140004f49  test    ecx, ecx
0x140004f4b  jz      short loc_140004F54
0x140004f4d  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140004f52  jz      short loc_140004F7A
0x140004f54  mov     rax, cs:g_pfnResultLoggingCallback
0x140004f5b  test    rax, rax
0x140004f5e  jz      short loc_140004FD3
0x140004f60  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140004f67  jnz     short loc_140004FD3
0x140004f69  xor     r8d, r8d
0x140004f6c  xor     edx, edx
0x140004f6e  lea     rcx, [rsp+14F0h+var_14D0]
0x140004f73  call    _guard_dispatch_icall
0x140004f78  jmp     short loc_140004FD3
0x140004f7a  mov     ebx, 800h
0x140004f7f  mov     rax, cs:g_pfnResultLoggingCallback
0x140004f86  test    rax, rax
0x140004f89  jz      short loc_140004FA8
0x140004f8b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140004f92  jnz     short loc_140004FA8
0x140004f94  mov     r8d, ebx
0x140004f97  lea     rdx, [rbp+13F0h+OutputString]
0x140004f9e  lea     rcx, [rsp+14F0h+var_14D0]
0x140004fa3  call    _guard_dispatch_icall
0x140004fa8  cmp     [rbp+13F0h+OutputString], r15w
0x140004fb0  jnz     short loc_140004FC6
0x140004fb2  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140004fb7  mov     rdx, rbx; wchar_t *
0x140004fba  lea     rcx, [rbp+13F0h+OutputString]; this
0x140004fc1  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140004fc6  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140004fcd  call    cs:__imp_OutputDebugStringW
0x140004fd3  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140004fd8  jnz     short loc_140004FE3
0x140004fda  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x140004fe1  jz      short loc_140004FF5
0x140004fe3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140004fea  test    rax, rax
0x140004fed  jz      short loc_140004FF5
0x140004fef  call    _guard_dispatch_icall
0x140004ff4  nop
0x140004ff5  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140004ffa  jnz     short loc_140005022
0x140004ffc  mov     rcx, [rbp+13F0h+var_30]
0x140005003  xor     rcx, rsp; StackCookie
0x140005006  call    __security_check_cookie
0x14000500b  mov     rbx, [rsp+14F0h+arg_10]
0x140005013  add     rsp, 14D0h
0x14000501a  pop     r15
0x14000501c  pop     r14
0x14000501e  pop     rdi
0x14000501f  pop     rsi
0x140005020  pop     rbp
0x140005021  retn
0x140005022  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140005027  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000502d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
