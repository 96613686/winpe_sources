# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180094b5c`
- end: `0x180094df2`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180094a1c`

## callees

- `0x1800049e0`
- `0x180005e44`
- `0x18003b7e8`
- `0x18003cdc0`
- `0x18003e2f4`
- `0x18003e508`
- `0x180094b5c`
- `0x1800efc00`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180094d8c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180094d8c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180094d02`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180094d02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180094c07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180094c07`

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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v16, v14);
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
0x180094b5c  mov     [rsp-8+arg_10], rbx
0x180094b61  push    rbp
0x180094b62  push    rsi
0x180094b63  push    rdi
0x180094b64  push    r14
0x180094b66  push    r15
0x180094b68  lea     rbp, [rsp-13D0h]
0x180094b70  mov     eax, 14D0h
0x180094b75  call    _alloca_probe
0x180094b7a  sub     rsp, rax
0x180094b7d  mov     rax, cs:__security_cookie
0x180094b84  xor     rax, rsp
0x180094b87  mov     [rbp+13F0h+var_30], rax
0x180094b8e  mov     esi, edx
0x180094b90  mov     r14, rcx
0x180094b93  mov     rdi, [rbp+13F0h+arg_28]
0x180094b9a  xor     edx, edx; Val
0x180094b9c  mov     r8d, 98h; Size
0x180094ba2  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180094ba7  call    memset_0
0x180094bac  nop
0x180094bad  xor     r15d, r15d
0x180094bb0  mov     [rbp+13F0h+OutputString], r15w
0x180094bb8  mov     [rbp+13F0h+var_1430], r15b
0x180094bbc  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180094bc3  mov     ecx, [rdx]; this
0x180094bc5  mov     [rsp+14F0h+var_14C8], ecx
0x180094bc9  mov     eax, [rdx+4]
0x180094bcc  mov     [rsp+14F0h+var_14C4], eax
0x180094bd0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180094bd5  mov     ebx, eax
0x180094bd7  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180094bdf  mov     ecx, r15d
0x180094be2  lea     eax, [r15+8]
0x180094be6  cmp     dword ptr [rdx+8], 1
0x180094bea  cmovz   ecx, eax
0x180094bed  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180094bf1  lea     ecx, [rax-7]
0x180094bf4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180094bfc  inc     ecx
0x180094bfe  mov     [rsp+14F0h+var_14C0], ecx
0x180094c02  mov     [rsp+14F0h+var_14B8], r15
0x180094c07  call    cs:__imp_GetCurrentThreadId
0x180094c0d  mov     [rsp+14F0h+var_14B0], eax
0x180094c11  lea     rax, aWil; "wil"
0x180094c18  mov     [rsp+14F0h+var_1498], rax
0x180094c1d  mov     [rsp+14F0h+var_1490], esi
0x180094c21  mov     [rsp+14F0h+var_148C], ebx
0x180094c25  mov     [rsp+14F0h+var_14A8], r15
0x180094c2a  mov     [rsp+14F0h+var_14A0], r15
0x180094c2f  mov     [rbp+13F0h+var_1448], rdi
0x180094c33  mov     [rbp+13F0h+var_1440], r14
0x180094c37  mov     [rsp+14F0h+var_1488], r15
0x180094c3c  xorps   xmm0, xmm0
0x180094c3f  xor     eax, eax
0x180094c41  movups  [rbp+13F0h+var_1468], xmm0
0x180094c45  mov     [rbp+13F0h+var_1458], rax
0x180094c49  xorps   xmm1, xmm1
0x180094c4c  movups  [rsp+14F0h+var_1480], xmm1
0x180094c51  mov     [rbp+13F0h+var_1470], rax
0x180094c55  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180094c5c  test    rax, rax
0x180094c5f  jz      short loc_180094C6C
0x180094c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094c66  mov     [rbp+13F0h+var_1450], rax
0x180094c6a  jmp     short loc_180094C70
0x180094c6c  mov     [rbp+13F0h+var_1450], r15
0x180094c70  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180094c77  test    rax, rax
0x180094c7a  jz      short loc_180094C86
0x180094c7c  lea     rcx, [rsp+14F0h+var_14D0]
0x180094c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094c86  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180094c8d  test    rax, rax
0x180094c90  jz      short loc_180094CA6
0x180094c92  mov     r8d, 400h
0x180094c98  lea     rdx, [rbp+13F0h+var_1430]
0x180094c9c  lea     rcx, [rsp+14F0h+var_14D0]
0x180094ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094ca6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180094cad  test    rax, rax
0x180094cb0  jz      short loc_180094CBC
0x180094cb2  lea     rcx, [rsp+14F0h+var_14D0]
0x180094cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094cbc  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180094cc3  test    rax, rax
0x180094cc6  jz      short loc_180094CD9
0x180094cc8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180094ccd  jnz     short loc_180094CD9
0x180094ccf  lea     rcx, [rsp+14F0h+var_14D0]
0x180094cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094cd9  cmp     [rsp+14F0h+var_14C8], r15d
0x180094cde  jge     loc_180094DEC
0x180094ce4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180094ceb  jnz     short loc_180094D0C
0x180094ced  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180094cf4  test    rax, rax
0x180094cf7  jz      short loc_180094D02
0x180094cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094cfe  test    al, al
0x180094d00  jmp     short loc_180094D0A
0x180094d02  call    cs:__imp_IsDebuggerPresent
0x180094d08  test    eax, eax
0x180094d0a  jz      short loc_180094D13
0x180094d0c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180094d11  jz      short loc_180094D39
0x180094d13  mov     rax, cs:g_pfnResultLoggingCallback
0x180094d1a  test    rax, rax
0x180094d1d  jz      short loc_180094D92
0x180094d1f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180094d26  jnz     short loc_180094D92
0x180094d28  xor     r8d, r8d
0x180094d2b  xor     edx, edx
0x180094d2d  lea     rcx, [rsp+14F0h+var_14D0]
0x180094d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094d37  jmp     short loc_180094D92
0x180094d39  mov     ebx, 800h
0x180094d3e  mov     rax, cs:g_pfnResultLoggingCallback
0x180094d45  test    rax, rax
0x180094d48  jz      short loc_180094D67
0x180094d4a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180094d51  jnz     short loc_180094D67
0x180094d53  mov     r8d, ebx
0x180094d56  lea     rdx, [rbp+13F0h+OutputString]
0x180094d5d  lea     rcx, [rsp+14F0h+var_14D0]
0x180094d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094d67  cmp     [rbp+13F0h+OutputString], r15w
0x180094d6f  jnz     short loc_180094D85
0x180094d71  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180094d76  mov     rdx, rbx; wchar_t *
0x180094d79  lea     rcx, [rbp+13F0h+OutputString]; this
0x180094d80  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180094d85  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180094d8c  call    cs:__imp_OutputDebugStringW
0x180094d92  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180094d97  jnz     short loc_180094DA2
0x180094d99  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180094da0  jz      short loc_180094DB4
0x180094da2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180094da9  test    rax, rax
0x180094dac  jz      short loc_180094DB4
0x180094dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094db3  nop
0x180094db4  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180094db9  jnz     short loc_180094DE1
0x180094dbb  mov     rcx, [rbp+13F0h+var_30]
0x180094dc2  xor     rcx, rsp; StackCookie
0x180094dc5  call    __security_check_cookie
0x180094dca  mov     rbx, [rsp+14F0h+arg_10]
0x180094dd2  add     rsp, 14D0h
0x180094dd9  pop     r15
0x180094ddb  pop     r14
0x180094ddd  pop     rdi
0x180094dde  pop     rsi
0x180094ddf  pop     rbp
0x180094de0  retn
0x180094de1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180094de6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180094dec  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
