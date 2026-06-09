# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800087fc`
- end: `0x180008a92`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800084c4`

## callees

- `0x180003c20`
- `0x180004a24`
- `0x1800087fc`
- `0x180015884`
- `0x18001825c`
- `0x18001a5f8`
- `0x18001a804`
- `0x1800a34c0`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800088a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800088a7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800089a2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800089a2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008a2c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008a2c`

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
0x1800087fc  mov     [rsp-8+arg_10], rbx
0x180008801  push    rbp
0x180008802  push    rsi
0x180008803  push    rdi
0x180008804  push    r14
0x180008806  push    r15
0x180008808  lea     rbp, [rsp-13D0h]
0x180008810  mov     eax, 14D0h
0x180008815  call    _alloca_probe
0x18000881a  sub     rsp, rax
0x18000881d  mov     rax, cs:__security_cookie
0x180008824  xor     rax, rsp
0x180008827  mov     [rbp+13F0h+var_30], rax
0x18000882e  mov     esi, edx
0x180008830  mov     r14, rcx
0x180008833  mov     rdi, [rbp+13F0h+arg_28]
0x18000883a  xor     edx, edx; Val
0x18000883c  mov     r8d, 98h; Size
0x180008842  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180008847  call    memset_0
0x18000884c  nop
0x18000884d  xor     r15d, r15d
0x180008850  mov     [rbp+13F0h+OutputString], r15w
0x180008858  mov     [rbp+13F0h+var_1430], r15b
0x18000885c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180008863  mov     ecx, [rdx]; this
0x180008865  mov     [rsp+14F0h+var_14C8], ecx
0x180008869  mov     eax, [rdx+4]
0x18000886c  mov     [rsp+14F0h+var_14C4], eax
0x180008870  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008875  mov     ebx, eax
0x180008877  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000887f  mov     ecx, r15d
0x180008882  lea     eax, [r15+8]
0x180008886  cmp     dword ptr [rdx+8], 1
0x18000888a  cmovz   ecx, eax
0x18000888d  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180008891  lea     ecx, [rax-7]
0x180008894  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000889c  inc     ecx
0x18000889e  mov     [rsp+14F0h+var_14C0], ecx
0x1800088a2  mov     [rsp+14F0h+var_14B8], r15
0x1800088a7  call    cs:__imp_GetCurrentThreadId
0x1800088ad  mov     [rsp+14F0h+var_14B0], eax
0x1800088b1  lea     rax, aWil; "wil"
0x1800088b8  mov     [rsp+14F0h+var_1498], rax
0x1800088bd  mov     [rsp+14F0h+var_1490], esi
0x1800088c1  mov     [rsp+14F0h+var_148C], ebx
0x1800088c5  mov     [rsp+14F0h+var_14A8], r15
0x1800088ca  mov     [rsp+14F0h+var_14A0], r15
0x1800088cf  mov     [rbp+13F0h+var_1448], rdi
0x1800088d3  mov     [rbp+13F0h+var_1440], r14
0x1800088d7  mov     [rsp+14F0h+var_1488], r15
0x1800088dc  xorps   xmm0, xmm0
0x1800088df  xor     eax, eax
0x1800088e1  movups  [rbp+13F0h+var_1468], xmm0
0x1800088e5  mov     [rbp+13F0h+var_1458], rax
0x1800088e9  xorps   xmm1, xmm1
0x1800088ec  movups  [rsp+14F0h+var_1480], xmm1
0x1800088f1  mov     [rbp+13F0h+var_1470], rax
0x1800088f5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800088fc  test    rax, rax
0x1800088ff  jz      short loc_18000890C
0x180008901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008906  mov     [rbp+13F0h+var_1450], rax
0x18000890a  jmp     short loc_180008910
0x18000890c  mov     [rbp+13F0h+var_1450], r15
0x180008910  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008917  test    rax, rax
0x18000891a  jz      short loc_180008926
0x18000891c  lea     rcx, [rsp+14F0h+var_14D0]
0x180008921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008926  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000892d  test    rax, rax
0x180008930  jz      short loc_180008946
0x180008932  mov     r8d, 400h
0x180008938  lea     rdx, [rbp+13F0h+var_1430]
0x18000893c  lea     rcx, [rsp+14F0h+var_14D0]
0x180008941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008946  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000894d  test    rax, rax
0x180008950  jz      short loc_18000895C
0x180008952  lea     rcx, [rsp+14F0h+var_14D0]
0x180008957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000895c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008963  test    rax, rax
0x180008966  jz      short loc_180008979
0x180008968  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000896d  jnz     short loc_180008979
0x18000896f  lea     rcx, [rsp+14F0h+var_14D0]
0x180008974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008979  cmp     [rsp+14F0h+var_14C8], r15d
0x18000897e  jge     loc_180008A8C
0x180008984  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000898b  jnz     short loc_1800089AC
0x18000898d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008994  test    rax, rax
0x180008997  jz      short loc_1800089A2
0x180008999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000899e  test    al, al
0x1800089a0  jmp     short loc_1800089AA
0x1800089a2  call    cs:__imp_IsDebuggerPresent
0x1800089a8  test    eax, eax
0x1800089aa  jz      short loc_1800089B3
0x1800089ac  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800089b1  jz      short loc_1800089D9
0x1800089b3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800089ba  test    rax, rax
0x1800089bd  jz      short loc_180008A32
0x1800089bf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800089c6  jnz     short loc_180008A32
0x1800089c8  xor     r8d, r8d
0x1800089cb  xor     edx, edx
0x1800089cd  lea     rcx, [rsp+14F0h+var_14D0]
0x1800089d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089d7  jmp     short loc_180008A32
0x1800089d9  mov     ebx, 800h
0x1800089de  mov     rax, cs:g_pfnResultLoggingCallback
0x1800089e5  test    rax, rax
0x1800089e8  jz      short loc_180008A07
0x1800089ea  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800089f1  jnz     short loc_180008A07
0x1800089f3  mov     r8d, ebx
0x1800089f6  lea     rdx, [rbp+13F0h+OutputString]
0x1800089fd  lea     rcx, [rsp+14F0h+var_14D0]
0x180008a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a07  cmp     [rbp+13F0h+OutputString], r15w
0x180008a0f  jnz     short loc_180008A25
0x180008a11  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180008a16  mov     rdx, rbx; unsigned __int16 *
0x180008a19  lea     rcx, [rbp+13F0h+OutputString]; this
0x180008a20  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008a25  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180008a2c  call    cs:__imp_OutputDebugStringW
0x180008a32  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180008a37  jnz     short loc_180008A42
0x180008a39  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180008a40  jz      short loc_180008A54
0x180008a42  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008a49  test    rax, rax
0x180008a4c  jz      short loc_180008A54
0x180008a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a53  nop
0x180008a54  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180008a59  jnz     short loc_180008A81
0x180008a5b  mov     rcx, [rbp+13F0h+var_30]
0x180008a62  xor     rcx, rsp; StackCookie
0x180008a65  call    __security_check_cookie
0x180008a6a  mov     rbx, [rsp+14F0h+arg_10]
0x180008a72  add     rsp, 14D0h
0x180008a79  pop     r15
0x180008a7b  pop     r14
0x180008a7d  pop     rdi
0x180008a7e  pop     rsi
0x180008a7f  pop     rbp
0x180008a80  retn
0x180008a81  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180008a86  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180008a8c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
