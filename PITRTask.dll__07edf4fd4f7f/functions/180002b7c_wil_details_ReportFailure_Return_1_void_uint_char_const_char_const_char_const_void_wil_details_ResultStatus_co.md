# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002b7c`
- end: `0x180002e12`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000265c`

## callees

- `0x180002b7c`
- `0x180006054`
- `0x1800078fc`
- `0x18000a410`
- `0x18000b848`
- `0x180010792`
- `0x1800107c0`
- `0x180010880`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002c27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002c27`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002d22`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002d22`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002dac`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002dac`

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
0x180002b7c  mov     [rsp-8+arg_10], rbx
0x180002b81  push    rbp
0x180002b82  push    rsi
0x180002b83  push    rdi
0x180002b84  push    r14
0x180002b86  push    r15
0x180002b88  lea     rbp, [rsp-13D0h]
0x180002b90  mov     eax, 14D0h
0x180002b95  call    _alloca_probe
0x180002b9a  sub     rsp, rax
0x180002b9d  mov     rax, cs:__security_cookie
0x180002ba4  xor     rax, rsp
0x180002ba7  mov     [rbp+13F0h+var_30], rax
0x180002bae  mov     esi, edx
0x180002bb0  mov     r14, rcx
0x180002bb3  mov     rdi, [rbp+13F0h+arg_28]
0x180002bba  xor     edx, edx; Val
0x180002bbc  mov     r8d, 98h; Size
0x180002bc2  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002bc7  call    memset_0
0x180002bcc  nop
0x180002bcd  xor     r15d, r15d
0x180002bd0  mov     [rbp+13F0h+OutputString], r15w
0x180002bd8  mov     [rbp+13F0h+var_1430], r15b
0x180002bdc  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180002be3  mov     ecx, [rdx]; this
0x180002be5  mov     [rsp+14F0h+var_14C8], ecx
0x180002be9  mov     eax, [rdx+4]
0x180002bec  mov     [rsp+14F0h+var_14C4], eax
0x180002bf0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002bf5  mov     ebx, eax
0x180002bf7  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180002bff  mov     ecx, r15d
0x180002c02  lea     eax, [r15+8]
0x180002c06  cmp     dword ptr [rdx+8], 1
0x180002c0a  cmovz   ecx, eax
0x180002c0d  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002c11  lea     ecx, [rax-7]
0x180002c14  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002c1c  inc     ecx
0x180002c1e  mov     [rsp+14F0h+var_14C0], ecx
0x180002c22  mov     [rsp+14F0h+var_14B8], r15
0x180002c27  call    cs:__imp_GetCurrentThreadId
0x180002c2d  mov     [rsp+14F0h+var_14B0], eax
0x180002c31  lea     rax, aWil; "wil"
0x180002c38  mov     [rsp+14F0h+var_1498], rax
0x180002c3d  mov     [rsp+14F0h+var_1490], esi
0x180002c41  mov     [rsp+14F0h+var_148C], ebx
0x180002c45  mov     [rsp+14F0h+var_14A8], r15
0x180002c4a  mov     [rsp+14F0h+var_14A0], r15
0x180002c4f  mov     [rbp+13F0h+var_1448], rdi
0x180002c53  mov     [rbp+13F0h+var_1440], r14
0x180002c57  mov     [rsp+14F0h+var_1488], r15
0x180002c5c  xorps   xmm0, xmm0
0x180002c5f  xor     eax, eax
0x180002c61  movups  [rbp+13F0h+var_1468], xmm0
0x180002c65  mov     [rbp+13F0h+var_1458], rax
0x180002c69  xorps   xmm1, xmm1
0x180002c6c  movups  [rsp+14F0h+var_1480], xmm1
0x180002c71  mov     [rbp+13F0h+var_1470], rax
0x180002c75  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002c7c  test    rax, rax
0x180002c7f  jz      short loc_180002C8C
0x180002c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c86  mov     [rbp+13F0h+var_1450], rax
0x180002c8a  jmp     short loc_180002C90
0x180002c8c  mov     [rbp+13F0h+var_1450], r15
0x180002c90  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002c97  test    rax, rax
0x180002c9a  jz      short loc_180002CA6
0x180002c9c  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ca6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002cad  test    rax, rax
0x180002cb0  jz      short loc_180002CC6
0x180002cb2  mov     r8d, 400h
0x180002cb8  lea     rdx, [rbp+13F0h+var_1430]
0x180002cbc  lea     rcx, [rsp+14F0h+var_14D0]
0x180002cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cc6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002ccd  test    rax, rax
0x180002cd0  jz      short loc_180002CDC
0x180002cd2  lea     rcx, [rsp+14F0h+var_14D0]
0x180002cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cdc  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002ce3  test    rax, rax
0x180002ce6  jz      short loc_180002CF9
0x180002ce8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002ced  jnz     short loc_180002CF9
0x180002cef  lea     rcx, [rsp+14F0h+var_14D0]
0x180002cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cf9  cmp     [rsp+14F0h+var_14C8], r15d
0x180002cfe  jge     loc_180002E0C
0x180002d04  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180002d0b  jnz     short loc_180002D2C
0x180002d0d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002d14  test    rax, rax
0x180002d17  jz      short loc_180002D22
0x180002d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d1e  test    al, al
0x180002d20  jmp     short loc_180002D2A
0x180002d22  call    cs:__imp_IsDebuggerPresent
0x180002d28  test    eax, eax
0x180002d2a  jz      short loc_180002D33
0x180002d2c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002d31  jz      short loc_180002D59
0x180002d33  mov     rax, cs:g_pfnResultLoggingCallback
0x180002d3a  test    rax, rax
0x180002d3d  jz      short loc_180002DB2
0x180002d3f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002d46  jnz     short loc_180002DB2
0x180002d48  xor     r8d, r8d
0x180002d4b  xor     edx, edx
0x180002d4d  lea     rcx, [rsp+14F0h+var_14D0]
0x180002d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d57  jmp     short loc_180002DB2
0x180002d59  mov     ebx, 800h
0x180002d5e  mov     rax, cs:g_pfnResultLoggingCallback
0x180002d65  test    rax, rax
0x180002d68  jz      short loc_180002D87
0x180002d6a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002d71  jnz     short loc_180002D87
0x180002d73  mov     r8d, ebx
0x180002d76  lea     rdx, [rbp+13F0h+OutputString]
0x180002d7d  lea     rcx, [rsp+14F0h+var_14D0]
0x180002d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d87  cmp     [rbp+13F0h+OutputString], r15w
0x180002d8f  jnz     short loc_180002DA5
0x180002d91  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002d96  mov     rdx, rbx; unsigned __int16 *
0x180002d99  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002da0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002da5  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002dac  call    cs:__imp_OutputDebugStringW
0x180002db2  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002db7  jnz     short loc_180002DC2
0x180002db9  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180002dc0  jz      short loc_180002DD4
0x180002dc2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002dc9  test    rax, rax
0x180002dcc  jz      short loc_180002DD4
0x180002dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dd3  nop
0x180002dd4  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180002dd9  jnz     short loc_180002E01
0x180002ddb  mov     rcx, [rbp+13F0h+var_30]
0x180002de2  xor     rcx, rsp; StackCookie
0x180002de5  call    __security_check_cookie
0x180002dea  mov     rbx, [rsp+14F0h+arg_10]
0x180002df2  add     rsp, 14D0h
0x180002df9  pop     r15
0x180002dfb  pop     r14
0x180002dfd  pop     rdi
0x180002dfe  pop     rsi
0x180002dff  pop     rbp
0x180002e00  retn
0x180002e01  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002e06  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002e0c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
