# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004d4c`
- end: `0x180004fe2`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000482c`

## callees

- `0x180004d4c`
- `0x180009a20`
- `0x18000cf08`
- `0x1800111d0`
- `0x18001138c`
- `0x1800142d2`
- `0x180014310`
- `0x1800143d0`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180004df7`
- `KERNEL32!GetCurrentThreadId` at `0x180004df7`
- `KERNEL32!IsDebuggerPresent` at `0x180004ef2`
- `KERNEL32!IsDebuggerPresent` at `0x180004ef2`
- `KERNEL32!OutputDebugStringW` at `0x180004f7c`
- `KERNEL32!OutputDebugStringW` at `0x180004f7c`

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
0x180004d4c  mov     [rsp-8+arg_10], rbx
0x180004d51  push    rbp
0x180004d52  push    rsi
0x180004d53  push    rdi
0x180004d54  push    r14
0x180004d56  push    r15
0x180004d58  lea     rbp, [rsp-13D0h]
0x180004d60  mov     eax, 14D0h
0x180004d65  call    _alloca_probe
0x180004d6a  sub     rsp, rax
0x180004d6d  mov     rax, cs:__security_cookie
0x180004d74  xor     rax, rsp
0x180004d77  mov     [rbp+13F0h+var_30], rax
0x180004d7e  mov     esi, edx
0x180004d80  mov     r14, rcx
0x180004d83  mov     rdi, [rbp+13F0h+arg_28]
0x180004d8a  xor     edx, edx; Val
0x180004d8c  mov     r8d, 98h; Size
0x180004d92  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180004d97  call    memset_0
0x180004d9c  nop
0x180004d9d  xor     r15d, r15d
0x180004da0  mov     [rbp+13F0h+OutputString], r15w
0x180004da8  mov     [rbp+13F0h+var_1430], r15b
0x180004dac  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180004db3  mov     ecx, [rdx]; this
0x180004db5  mov     [rsp+14F0h+var_14C8], ecx
0x180004db9  mov     eax, [rdx+4]
0x180004dbc  mov     [rsp+14F0h+var_14C4], eax
0x180004dc0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004dc5  mov     ebx, eax
0x180004dc7  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180004dcf  mov     ecx, r15d
0x180004dd2  lea     eax, [r15+8]
0x180004dd6  cmp     dword ptr [rdx+8], 1
0x180004dda  cmovz   ecx, eax
0x180004ddd  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180004de1  lea     ecx, [rax-7]
0x180004de4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004dec  inc     ecx
0x180004dee  mov     [rsp+14F0h+var_14C0], ecx
0x180004df2  mov     [rsp+14F0h+var_14B8], r15
0x180004df7  call    cs:__imp_GetCurrentThreadId
0x180004dfd  mov     [rsp+14F0h+var_14B0], eax
0x180004e01  lea     rax, aWil; "wil"
0x180004e08  mov     [rsp+14F0h+var_1498], rax
0x180004e0d  mov     [rsp+14F0h+var_1490], esi
0x180004e11  mov     [rsp+14F0h+var_148C], ebx
0x180004e15  mov     [rsp+14F0h+var_14A8], r15
0x180004e1a  mov     [rsp+14F0h+var_14A0], r15
0x180004e1f  mov     [rbp+13F0h+var_1448], rdi
0x180004e23  mov     [rbp+13F0h+var_1440], r14
0x180004e27  mov     [rsp+14F0h+var_1488], r15
0x180004e2c  xorps   xmm0, xmm0
0x180004e2f  xor     eax, eax
0x180004e31  movups  [rbp+13F0h+var_1468], xmm0
0x180004e35  mov     [rbp+13F0h+var_1458], rax
0x180004e39  xorps   xmm1, xmm1
0x180004e3c  movups  [rsp+14F0h+var_1480], xmm1
0x180004e41  mov     [rbp+13F0h+var_1470], rax
0x180004e45  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004e4c  test    rax, rax
0x180004e4f  jz      short loc_180004E5C
0x180004e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e56  mov     [rbp+13F0h+var_1450], rax
0x180004e5a  jmp     short loc_180004E60
0x180004e5c  mov     [rbp+13F0h+var_1450], r15
0x180004e60  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004e67  test    rax, rax
0x180004e6a  jz      short loc_180004E76
0x180004e6c  lea     rcx, [rsp+14F0h+var_14D0]
0x180004e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e76  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004e7d  test    rax, rax
0x180004e80  jz      short loc_180004E96
0x180004e82  mov     r8d, 400h
0x180004e88  lea     rdx, [rbp+13F0h+var_1430]
0x180004e8c  lea     rcx, [rsp+14F0h+var_14D0]
0x180004e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e96  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004e9d  test    rax, rax
0x180004ea0  jz      short loc_180004EAC
0x180004ea2  lea     rcx, [rsp+14F0h+var_14D0]
0x180004ea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eac  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004eb3  test    rax, rax
0x180004eb6  jz      short loc_180004EC9
0x180004eb8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004ebd  jnz     short loc_180004EC9
0x180004ebf  lea     rcx, [rsp+14F0h+var_14D0]
0x180004ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ec9  cmp     [rsp+14F0h+var_14C8], r15d
0x180004ece  jge     loc_180004FDC
0x180004ed4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180004edb  jnz     short loc_180004EFC
0x180004edd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004ee4  test    rax, rax
0x180004ee7  jz      short loc_180004EF2
0x180004ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eee  test    al, al
0x180004ef0  jmp     short loc_180004EFA
0x180004ef2  call    cs:__imp_IsDebuggerPresent
0x180004ef8  test    eax, eax
0x180004efa  jz      short loc_180004F03
0x180004efc  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004f01  jz      short loc_180004F29
0x180004f03  mov     rax, cs:g_pfnResultLoggingCallback
0x180004f0a  test    rax, rax
0x180004f0d  jz      short loc_180004F82
0x180004f0f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004f16  jnz     short loc_180004F82
0x180004f18  xor     r8d, r8d
0x180004f1b  xor     edx, edx
0x180004f1d  lea     rcx, [rsp+14F0h+var_14D0]
0x180004f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f27  jmp     short loc_180004F82
0x180004f29  mov     ebx, 800h
0x180004f2e  mov     rax, cs:g_pfnResultLoggingCallback
0x180004f35  test    rax, rax
0x180004f38  jz      short loc_180004F57
0x180004f3a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004f41  jnz     short loc_180004F57
0x180004f43  mov     r8d, ebx
0x180004f46  lea     rdx, [rbp+13F0h+OutputString]
0x180004f4d  lea     rcx, [rsp+14F0h+var_14D0]
0x180004f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f57  cmp     [rbp+13F0h+OutputString], r15w
0x180004f5f  jnz     short loc_180004F75
0x180004f61  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180004f66  mov     rdx, rbx; unsigned __int16 *
0x180004f69  lea     rcx, [rbp+13F0h+OutputString]; this
0x180004f70  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004f75  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180004f7c  call    cs:__imp_OutputDebugStringW
0x180004f82  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180004f87  jnz     short loc_180004F92
0x180004f89  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180004f90  jz      short loc_180004FA4
0x180004f92  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004f99  test    rax, rax
0x180004f9c  jz      short loc_180004FA4
0x180004f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fa3  nop
0x180004fa4  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180004fa9  jnz     short loc_180004FD1
0x180004fab  mov     rcx, [rbp+13F0h+var_30]
0x180004fb2  xor     rcx, rsp; StackCookie
0x180004fb5  call    __security_check_cookie
0x180004fba  mov     rbx, [rsp+14F0h+arg_10]
0x180004fc2  add     rsp, 14D0h
0x180004fc9  pop     r15
0x180004fcb  pop     r14
0x180004fcd  pop     rdi
0x180004fce  pop     rsi
0x180004fcf  pop     rbp
0x180004fd0  retn
0x180004fd1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180004fd6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004fdc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
