# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18003a770`
- end: `0x18003aa27`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `695`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180023430`

## callees

- `0x1800277b0`
- `0x18003a770`
- `0x18003c194`
- `0x18003d260`
- `0x18003e378`
- `0x18003e530`
- `0x18005b620`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a83c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a83c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003a9c1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003a9c1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003a937`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003a937`

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
        unsigned __int64 *a7)
{
  unsigned int v9; // ebx
  int v10; // ecx
  __int64 v11; // r8
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  unsigned __int64 v16[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v17; // [rsp+30h] [rbp-D0h]
  __int128 v18; // [rsp+40h] [rbp-C0h]
  __int128 v19; // [rsp+50h] [rbp-B0h]
  __int128 v20; // [rsp+60h] [rbp-A0h]
  __int128 v21; // [rsp+70h] [rbp-90h]
  _OWORD v22[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v23; // [rsp+A0h] [rbp-60h]
  __int64 v24; // [rsp+B0h] [rbp-50h]
  _BYTE v25[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  *(_OWORD *)v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  memset(v22, 0, sizeof(v22));
  v23 = 0;
  v24 = 0;
  OutputString[0] = 0;
  v25[0] = 0;
  v16[1] = *a7;
  v9 = wil::details::RecordReturn((wil::details *)LODWORD(v16[1]), a2);
  LODWORD(v16[0]) = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  HIDWORD(v16[0]) = v10;
  LODWORD(v17) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  *((_QWORD *)&v17 + 1) = 0;
  LODWORD(v18) = GetCurrentThreadId();
  *((_QWORD *)&v19 + 1) = "wil";
  v20 = __PAIR64__(v9, a2);
  *((_QWORD *)&v18 + 1) = 0;
  *(_QWORD *)&v19 = 0;
  *((_QWORD *)&v23 + 1) = a6;
  v24 = a1;
  v21 = 0;
  memset(v22, 0, sizeof(v22));
  if ( wil::details::g_pfnGetModuleName )
    *(_QWORD *)&v23 = wil::details::g_pfnGetModuleName(v13);
  else
    *(_QWORD *)&v23 = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v16, v25, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v16);
  if ( wil::details::g_pfnOriginateCallback && (v16[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v16);
  if ( SLODWORD(v16[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v16[0] & 0x200000000LL) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v16[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v16[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v16, v12);
}

```

## disassembly

```asm
0x18003a770  mov     [rsp-8+arg_10], rbx
0x18003a775  push    rbp
0x18003a776  push    rsi
0x18003a777  push    rdi
0x18003a778  push    r14
0x18003a77a  push    r15
0x18003a77c  lea     rbp, [rsp-13D0h]
0x18003a784  mov     eax, 14D0h
0x18003a789  call    _alloca_probe
0x18003a78e  sub     rsp, rax
0x18003a791  mov     rax, cs:__security_cookie
0x18003a798  xor     rax, rsp
0x18003a79b  mov     [rbp+13F0h+var_30], rax
0x18003a7a2  mov     esi, edx
0x18003a7a4  mov     r14, rcx
0x18003a7a7  mov     rdi, [rbp+13F0h+arg_28]
0x18003a7ae  xorps   xmm0, xmm0
0x18003a7b1  xor     eax, eax
0x18003a7b3  movups  xmmword ptr [rsp+14F0h+var_14D0], xmm0
0x18003a7b8  movups  [rsp+14F0h+var_14C0], xmm0
0x18003a7bd  movups  [rsp+14F0h+var_14B0], xmm0
0x18003a7c2  movups  [rsp+14F0h+var_14A0], xmm0
0x18003a7c7  movups  [rsp+14F0h+var_1490], xmm0
0x18003a7cc  movups  [rsp+14F0h+var_1480], xmm0
0x18003a7d1  movups  [rbp+13F0h+var_1470], xmm0
0x18003a7d5  movups  [rbp+13F0h+var_1460], xmm0
0x18003a7d9  movups  [rbp+13F0h+var_1450], xmm0
0x18003a7dd  mov     [rbp+13F0h+var_1440], rax
0x18003a7e1  xor     r15d, r15d
0x18003a7e4  mov     [rbp+13F0h+OutputString], r15w
0x18003a7ec  mov     [rbp+13F0h+var_1430], r15b
0x18003a7f0  mov     r8, [rbp+13F0h+arg_30]
0x18003a7f7  mov     ecx, [r8]; this
0x18003a7fa  mov     dword ptr [rsp+14F0h+var_14D0+8], ecx
0x18003a7fe  mov     eax, [r8+4]
0x18003a802  mov     dword ptr [rsp+14F0h+var_14D0+0Ch], eax
0x18003a806  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003a80b  mov     ebx, eax
0x18003a80d  mov     edx, 1
0x18003a812  mov     dword ptr [rsp+14F0h+var_14D0], edx
0x18003a816  mov     ecx, r15d
0x18003a819  mov     eax, 8
0x18003a81e  cmp     [r8+8], edx
0x18003a822  cmovz   ecx, eax
0x18003a825  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18003a829  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, edx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003a831  inc     edx
0x18003a833  mov     dword ptr [rsp+14F0h+var_14C0], edx
0x18003a837  mov     qword ptr [rsp+14F0h+var_14C0+8], r15
0x18003a83c  call    cs:__imp_GetCurrentThreadId
0x18003a842  mov     dword ptr [rsp+14F0h+var_14B0], eax
0x18003a846  lea     rax, aWil; "wil"
0x18003a84d  mov     qword ptr [rsp+14F0h+var_14A0+8], rax
0x18003a852  mov     dword ptr [rsp+14F0h+var_1490], esi
0x18003a856  mov     dword ptr [rsp+14F0h+var_1490+4], ebx
0x18003a85a  mov     qword ptr [rsp+14F0h+var_14B0+8], r15
0x18003a85f  mov     qword ptr [rsp+14F0h+var_14A0], r15
0x18003a864  mov     qword ptr [rbp+13F0h+var_1450+8], rdi
0x18003a868  mov     [rbp+13F0h+var_1440], r14
0x18003a86c  mov     qword ptr [rsp+14F0h+var_1490+8], r15
0x18003a871  xorps   xmm0, xmm0
0x18003a874  xor     eax, eax
0x18003a876  movups  [rbp+13F0h+var_1470+8], xmm0
0x18003a87a  mov     qword ptr [rbp+13F0h+var_1460+8], rax
0x18003a87e  xorps   xmm1, xmm1
0x18003a881  movups  [rsp+14F0h+var_1480], xmm1
0x18003a886  mov     qword ptr [rbp+13F0h+var_1470], rax
0x18003a88a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003a891  test    rax, rax
0x18003a894  jz      short loc_18003A8A1
0x18003a896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a89b  mov     qword ptr [rbp+13F0h+var_1450], rax
0x18003a89f  jmp     short loc_18003A8A5
0x18003a8a1  mov     qword ptr [rbp+13F0h+var_1450], r15
0x18003a8a5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003a8ac  test    rax, rax
0x18003a8af  jz      short loc_18003A8BB
0x18003a8b1  lea     rcx, [rsp+14F0h+var_14D0]
0x18003a8b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a8bb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003a8c2  test    rax, rax
0x18003a8c5  jz      short loc_18003A8DB
0x18003a8c7  mov     r8d, 400h
0x18003a8cd  lea     rdx, [rbp+13F0h+var_1430]
0x18003a8d1  lea     rcx, [rsp+14F0h+var_14D0]
0x18003a8d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a8db  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003a8e2  test    rax, rax
0x18003a8e5  jz      short loc_18003A8F1
0x18003a8e7  lea     rcx, [rsp+14F0h+var_14D0]
0x18003a8ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a8f1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003a8f8  test    rax, rax
0x18003a8fb  jz      short loc_18003A90E
0x18003a8fd  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18003a902  jnz     short loc_18003A90E
0x18003a904  lea     rcx, [rsp+14F0h+var_14D0]
0x18003a909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a90e  cmp     dword ptr [rsp+14F0h+var_14D0+8], r15d
0x18003a913  jge     loc_18003AA21
0x18003a919  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18003a920  jnz     short loc_18003A941
0x18003a922  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003a929  test    rax, rax
0x18003a92c  jz      short loc_18003A937
0x18003a92e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a933  test    al, al
0x18003a935  jmp     short loc_18003A93F
0x18003a937  call    cs:__imp_IsDebuggerPresent
0x18003a93d  test    eax, eax
0x18003a93f  jz      short loc_18003A948
0x18003a941  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18003a946  jz      short loc_18003A96E
0x18003a948  mov     rax, cs:g_pfnResultLoggingCallback
0x18003a94f  test    rax, rax
0x18003a952  jz      short loc_18003A9C7
0x18003a954  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003a95b  jnz     short loc_18003A9C7
0x18003a95d  xor     r8d, r8d
0x18003a960  xor     edx, edx
0x18003a962  lea     rcx, [rsp+14F0h+var_14D0]
0x18003a967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a96c  jmp     short loc_18003A9C7
0x18003a96e  mov     rax, cs:g_pfnResultLoggingCallback
0x18003a975  test    rax, rax
0x18003a978  jz      short loc_18003A99A
0x18003a97a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003a981  jnz     short loc_18003A99A
0x18003a983  mov     r8d, 800h
0x18003a989  lea     rdx, [rbp+13F0h+OutputString]
0x18003a990  lea     rcx, [rsp+14F0h+var_14D0]
0x18003a995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a99a  cmp     [rbp+13F0h+OutputString], r15w
0x18003a9a2  jnz     short loc_18003A9BA
0x18003a9a4  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18003a9a9  mov     edx, 800h; unsigned __int16 *
0x18003a9ae  lea     rcx, [rbp+13F0h+OutputString]; this
0x18003a9b5  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18003a9ba  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18003a9c1  call    cs:__imp_OutputDebugStringW
0x18003a9c7  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18003a9cc  jnz     short loc_18003A9D7
0x18003a9ce  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18003a9d5  jz      short loc_18003A9E9
0x18003a9d7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18003a9de  test    rax, rax
0x18003a9e1  jz      short loc_18003A9E9
0x18003a9e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a9e8  nop
0x18003a9e9  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18003a9ee  jnz     short loc_18003AA16
0x18003a9f0  mov     rcx, [rbp+13F0h+var_30]
0x18003a9f7  xor     rcx, rsp; StackCookie
0x18003a9fa  call    __security_check_cookie
0x18003a9ff  mov     rbx, [rsp+14F0h+arg_10]
0x18003aa07  add     rsp, 14D0h
0x18003aa0e  pop     r15
0x18003aa10  pop     r14
0x18003aa12  pop     rdi
0x18003aa13  pop     rsi
0x18003aa14  pop     rbp
0x18003aa15  retn
0x18003aa16  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18003aa1b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18003aa21  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
