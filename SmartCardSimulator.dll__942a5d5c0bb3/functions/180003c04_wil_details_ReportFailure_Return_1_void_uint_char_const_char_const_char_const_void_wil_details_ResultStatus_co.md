# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003c04`
- end: `0x180003e9a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800038a0`

## callees

- `0x180003c04`
- `0x1800049e4`
- `0x180005a90`
- `0x180006648`
- `0x1800067b0`
- `0x1800586c6`
- `0x180058700`
- `0x1800587c0`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003caf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003caf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003daa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003daa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003e34`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003e34`

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
0x180003c04  mov     [rsp-8+arg_10], rbx
0x180003c09  push    rbp
0x180003c0a  push    rsi
0x180003c0b  push    rdi
0x180003c0c  push    r14
0x180003c0e  push    r15
0x180003c10  lea     rbp, [rsp-13D0h]
0x180003c18  mov     eax, 14D0h
0x180003c1d  call    _alloca_probe
0x180003c22  sub     rsp, rax
0x180003c25  mov     rax, cs:__security_cookie
0x180003c2c  xor     rax, rsp
0x180003c2f  mov     [rbp+13F0h+var_30], rax
0x180003c36  mov     esi, edx
0x180003c38  mov     r14, rcx
0x180003c3b  mov     rdi, [rbp+13F0h+arg_28]
0x180003c42  xor     edx, edx; Val
0x180003c44  mov     r8d, 98h; Size
0x180003c4a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003c4f  call    memset_0
0x180003c54  nop
0x180003c55  xor     r15d, r15d
0x180003c58  mov     [rbp+13F0h+OutputString], r15w
0x180003c60  mov     [rbp+13F0h+var_1430], r15b
0x180003c64  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180003c6b  mov     ecx, [rdx]; this
0x180003c6d  mov     [rsp+14F0h+var_14C8], ecx
0x180003c71  mov     eax, [rdx+4]
0x180003c74  mov     [rsp+14F0h+var_14C4], eax
0x180003c78  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003c7d  mov     ebx, eax
0x180003c7f  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180003c87  mov     ecx, r15d
0x180003c8a  lea     eax, [r15+8]
0x180003c8e  cmp     dword ptr [rdx+8], 1
0x180003c92  cmovz   ecx, eax
0x180003c95  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003c99  lea     ecx, [rax-7]
0x180003c9c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003ca4  inc     ecx
0x180003ca6  mov     [rsp+14F0h+var_14C0], ecx
0x180003caa  mov     [rsp+14F0h+var_14B8], r15
0x180003caf  call    cs:__imp_GetCurrentThreadId
0x180003cb5  mov     [rsp+14F0h+var_14B0], eax
0x180003cb9  lea     rax, aWil; "wil"
0x180003cc0  mov     [rsp+14F0h+var_1498], rax
0x180003cc5  mov     [rsp+14F0h+var_1490], esi
0x180003cc9  mov     [rsp+14F0h+var_148C], ebx
0x180003ccd  mov     [rsp+14F0h+var_14A8], r15
0x180003cd2  mov     [rsp+14F0h+var_14A0], r15
0x180003cd7  mov     [rbp+13F0h+var_1448], rdi
0x180003cdb  mov     [rbp+13F0h+var_1440], r14
0x180003cdf  mov     [rsp+14F0h+var_1488], r15
0x180003ce4  xorps   xmm0, xmm0
0x180003ce7  xor     eax, eax
0x180003ce9  movups  [rbp+13F0h+var_1468], xmm0
0x180003ced  mov     [rbp+13F0h+var_1458], rax
0x180003cf1  xorps   xmm1, xmm1
0x180003cf4  movups  [rsp+14F0h+var_1480], xmm1
0x180003cf9  mov     [rbp+13F0h+var_1470], rax
0x180003cfd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003d04  test    rax, rax
0x180003d07  jz      short loc_180003D14
0x180003d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d0e  mov     [rbp+13F0h+var_1450], rax
0x180003d12  jmp     short loc_180003D18
0x180003d14  mov     [rbp+13F0h+var_1450], r15
0x180003d18  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003d1f  test    rax, rax
0x180003d22  jz      short loc_180003D2E
0x180003d24  lea     rcx, [rsp+14F0h+var_14D0]
0x180003d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d2e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003d35  test    rax, rax
0x180003d38  jz      short loc_180003D4E
0x180003d3a  mov     r8d, 400h
0x180003d40  lea     rdx, [rbp+13F0h+var_1430]
0x180003d44  lea     rcx, [rsp+14F0h+var_14D0]
0x180003d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d4e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003d55  test    rax, rax
0x180003d58  jz      short loc_180003D64
0x180003d5a  lea     rcx, [rsp+14F0h+var_14D0]
0x180003d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d64  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003d6b  test    rax, rax
0x180003d6e  jz      short loc_180003D81
0x180003d70  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003d75  jnz     short loc_180003D81
0x180003d77  lea     rcx, [rsp+14F0h+var_14D0]
0x180003d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d81  cmp     [rsp+14F0h+var_14C8], r15d
0x180003d86  jge     loc_180003E94
0x180003d8c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180003d93  jnz     short loc_180003DB4
0x180003d95  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003d9c  test    rax, rax
0x180003d9f  jz      short loc_180003DAA
0x180003da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003da6  test    al, al
0x180003da8  jmp     short loc_180003DB2
0x180003daa  call    cs:__imp_IsDebuggerPresent
0x180003db0  test    eax, eax
0x180003db2  jz      short loc_180003DBB
0x180003db4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003db9  jz      short loc_180003DE1
0x180003dbb  mov     rax, cs:g_pfnResultLoggingCallback
0x180003dc2  test    rax, rax
0x180003dc5  jz      short loc_180003E3A
0x180003dc7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003dce  jnz     short loc_180003E3A
0x180003dd0  xor     r8d, r8d
0x180003dd3  xor     edx, edx
0x180003dd5  lea     rcx, [rsp+14F0h+var_14D0]
0x180003dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ddf  jmp     short loc_180003E3A
0x180003de1  mov     ebx, 800h
0x180003de6  mov     rax, cs:g_pfnResultLoggingCallback
0x180003ded  test    rax, rax
0x180003df0  jz      short loc_180003E0F
0x180003df2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003df9  jnz     short loc_180003E0F
0x180003dfb  mov     r8d, ebx
0x180003dfe  lea     rdx, [rbp+13F0h+OutputString]
0x180003e05  lea     rcx, [rsp+14F0h+var_14D0]
0x180003e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e0f  cmp     [rbp+13F0h+OutputString], r15w
0x180003e17  jnz     short loc_180003E2D
0x180003e19  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003e1e  mov     rdx, rbx; unsigned __int16 *
0x180003e21  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003e28  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003e2d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003e34  call    cs:__imp_OutputDebugStringW
0x180003e3a  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003e3f  jnz     short loc_180003E4A
0x180003e41  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180003e48  jz      short loc_180003E5C
0x180003e4a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003e51  test    rax, rax
0x180003e54  jz      short loc_180003E5C
0x180003e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e5b  nop
0x180003e5c  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003e61  jnz     short loc_180003E89
0x180003e63  mov     rcx, [rbp+13F0h+var_30]
0x180003e6a  xor     rcx, rsp; StackCookie
0x180003e6d  call    __security_check_cookie
0x180003e72  mov     rbx, [rsp+14F0h+arg_10]
0x180003e7a  add     rsp, 14D0h
0x180003e81  pop     r15
0x180003e83  pop     r14
0x180003e85  pop     rdi
0x180003e86  pop     rsi
0x180003e87  pop     rbp
0x180003e88  retn
0x180003e89  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003e8e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003e94  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
