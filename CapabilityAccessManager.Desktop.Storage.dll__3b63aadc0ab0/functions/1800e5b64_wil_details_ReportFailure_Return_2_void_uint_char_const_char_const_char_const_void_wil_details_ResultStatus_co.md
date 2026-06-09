# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800e5b64`
- end: `0x1800e5e64`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `768`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800e5358`

## callees

- `0x180003060`
- `0x180003a40`
- `0x1800e4d20`
- `0x1800e5570`
- `0x1800e5b64`
- `0x1800e7f74`
- `0x1800e8820`
- `0x1800e98fc`
- `0x1800ec390`
- `0x1800ec608`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e5c85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e5c85`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800e5e01`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800e5e01`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800e5d78`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800e5d78`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<2>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8,
        int a9,
        int a10)
{
  int v14; // edx
  int v15; // ebx
  int v16; // edx
  int v17; // ebx
  const struct wil::FailureInfo *v18; // rdx
  wil::details::in1diag3 *v19; // rcx
  const struct wil::FailureInfo *v20; // r9
  bool v21; // zf
  wil::details *v22; // [rsp+30h] [rbp-D0h]
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+54h] [rbp-ACh]
  int v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+5Ch] [rbp-A4h]
  signed __int32 v27; // [rsp+60h] [rbp-A0h]
  _WORD *v28; // [rsp+68h] [rbp-98h]
  DWORD CurrentThreadId; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+78h] [rbp-88h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int64 v32; // [rsp+88h] [rbp-78h]
  int v33; // [rsp+90h] [rbp-70h]
  int v34; // [rsp+94h] [rbp-6Ch]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int128 v36; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  __int128 v38; // [rsp+B8h] [rbp-48h]
  __int64 v39; // [rsp+C8h] [rbp-38h]
  __int64 ModuleName; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  __int64 v42; // [rsp+E0h] [rbp-20h]
  char v43[1024]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR OutputString[2048]; // [rsp+4F0h] [rbp+3F0h] BYREF

  memset_0(&v23, 0, 0x98u);
  OutputString[0] = 0;
  v43[0] = 0;
  v15 = *a7;
  v25 = v15;
  v26 = a7[1];
  if ( v15 >= 0 )
  {
    v15 = -2147024228;
    LODWORD(v22) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v22);
    v25 = -2147024228;
    v26 = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v16);
  }
  v17 = wil::details::RecordLog((wil::details *)(unsigned int)v15, v14);
  v23 = 2;
  v24 = a10;
  if ( a7[2] == 1 )
    v24 = a10 | 8;
  v27 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v21 = *a8 == 0, v28 = a8, v21) )
    v28 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v32 = a3;
  v33 = a2;
  v34 = v17;
  v30 = a5;
  v31 = a4;
  v41 = a6;
  v42 = a1;
  v35 = 0;
  v38 = 0;
  v39 = 0;
  v36 = 0;
  v37 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v19);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v23);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v23, v43, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v23);
  if ( wil::details::g_pfnOriginateCallback && (v24 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v23);
  if ( v25 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v21 = !IsDebuggerPresent())
      : (v21 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v19) == 0),
        v21)
    || (v24 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v23, v20);
    OutputDebugStringW(OutputString);
  }
  if ( ((v24 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v19);
  if ( (v24 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v23, v18);
}

```

## disassembly

```asm
0x1800e5b64  push    rbp
0x1800e5b66  push    rbx
0x1800e5b67  push    rsi
0x1800e5b68  push    rdi
0x1800e5b69  push    r12
0x1800e5b6b  push    r13
0x1800e5b6d  push    r14
0x1800e5b6f  push    r15
0x1800e5b71  lea     rbp, [rsp-1408h]
0x1800e5b79  mov     eax, 1508h
0x1800e5b7e  call    _alloca_probe
0x1800e5b83  sub     rsp, rax
0x1800e5b86  mov     rax, cs:__security_cookie
0x1800e5b8d  xor     rax, rsp
0x1800e5b90  mov     [rbp+1440h+var_50], rax
0x1800e5b97  mov     r12, r9
0x1800e5b9a  mov     r15, r8
0x1800e5b9d  mov     r14d, edx
0x1800e5ba0  mov     rsi, rcx
0x1800e5ba3  mov     r13, [rbp+1440h+arg_20]
0x1800e5baa  mov     rax, [rbp+1440h+arg_28]
0x1800e5bb1  mov     [rsp+1540h+var_1500], rax
0x1800e5bb6  xor     edx, edx; Val
0x1800e5bb8  mov     r8d, 98h; Size
0x1800e5bbe  lea     rcx, [rsp+1540h+var_14F0]; void *
0x1800e5bc3  call    memset_0
0x1800e5bc8  nop
0x1800e5bc9  xor     eax, eax
0x1800e5bcb  mov     [rbp+1440h+OutputString], ax
0x1800e5bd2  mov     [rbp+1440h+var_1450], al
0x1800e5bd5  mov     rdi, [rbp+1440h+arg_30]
0x1800e5bdc  mov     ebx, [rdi]
0x1800e5bde  mov     [rsp+1540h+var_14E8], ebx
0x1800e5be2  mov     eax, [rdi+4]
0x1800e5be5  mov     [rsp+1540h+var_14E4], eax
0x1800e5be9  test    ebx, ebx
0x1800e5beb  js      short loc_1800E5C2D
0x1800e5bed  mov     [rsp+1540h+var_1508], 0
0x1800e5bf5  mov     ebx, 8007029Ch
0x1800e5bfa  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x1800e5bfe  mov     rax, [rsp+1540h+var_1500]
0x1800e5c03  mov     [rsp+1540h+var_1518], rax; __int64
0x1800e5c08  mov     [rsp+1540h+var_1520], r13; __int64
0x1800e5c0d  mov     r9, r12; int
0x1800e5c10  mov     r8, r15; int
0x1800e5c13  mov     edx, r14d; int
0x1800e5c16  mov     rcx, rsi; int
0x1800e5c19  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800e5c1e  mov     [rsp+1540h+var_14E8], ebx
0x1800e5c22  mov     ecx, ebx; this
0x1800e5c24  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800e5c29  mov     [rsp+1540h+var_14E4], eax
0x1800e5c2d  mov     ecx, ebx; this
0x1800e5c2f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800e5c34  mov     ebx, eax
0x1800e5c36  mov     dword ptr [rsp+1540h+var_14F0], 2
0x1800e5c3e  mov     ecx, [rbp+1440h+arg_48]
0x1800e5c44  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x1800e5c48  cmp     dword ptr [rdi+8], 1
0x1800e5c4c  jnz     short loc_1800E5C55
0x1800e5c4e  or      ecx, 8
0x1800e5c51  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x1800e5c55  mov     ecx, 1
0x1800e5c5a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800e5c62  inc     ecx
0x1800e5c64  mov     [rsp+1540h+var_14E0], ecx
0x1800e5c68  mov     rax, [rbp+1440h+arg_38]
0x1800e5c6f  xor     edi, edi
0x1800e5c71  test    rax, rax
0x1800e5c74  jz      short loc_1800E5C80
0x1800e5c76  cmp     [rax], di
0x1800e5c79  mov     [rsp+1540h+var_14D8], rax
0x1800e5c7e  jnz     short loc_1800E5C85
0x1800e5c80  mov     [rsp+1540h+var_14D8], rdi
0x1800e5c85  call    cs:__imp_GetCurrentThreadId
0x1800e5c8b  mov     [rsp+1540h+var_14D0], eax
0x1800e5c8f  mov     [rbp+1440h+var_14B8], r15
0x1800e5c93  mov     [rbp+1440h+var_14B0], r14d
0x1800e5c97  mov     [rbp+1440h+var_14AC], ebx
0x1800e5c9a  mov     [rsp+1540h+var_14C8], r13
0x1800e5c9f  mov     [rbp+1440h+var_14C0], r12
0x1800e5ca3  mov     rax, [rsp+1540h+var_1500]
0x1800e5ca8  mov     [rbp+1440h+var_1468], rax
0x1800e5cac  mov     [rbp+1440h+var_1460], rsi
0x1800e5cb0  mov     [rbp+1440h+var_14A8], rdi
0x1800e5cb4  xorps   xmm0, xmm0
0x1800e5cb7  xor     eax, eax
0x1800e5cb9  movups  [rbp+1440h+var_1488], xmm0
0x1800e5cbd  mov     [rbp+1440h+var_1478], rax
0x1800e5cc1  xorps   xmm1, xmm1
0x1800e5cc4  movups  [rbp+1440h+var_14A0], xmm1
0x1800e5cc8  mov     [rbp+1440h+var_1490], rax
0x1800e5ccc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800e5cd3  test    rax, rax
0x1800e5cd6  jz      short loc_1800E5CE3
0x1800e5cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5cdd  mov     [rbp+1440h+var_1470], rax
0x1800e5ce1  jmp     short loc_1800E5CE7
0x1800e5ce3  mov     [rbp+1440h+var_1470], rdi
0x1800e5ce7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800e5cee  test    rax, rax
0x1800e5cf1  jz      short loc_1800E5CFD
0x1800e5cf3  lea     rcx, [rsp+1540h+var_14F0]
0x1800e5cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5cfd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800e5d04  test    rax, rax
0x1800e5d07  jz      short loc_1800E5D1D
0x1800e5d09  mov     r8d, 400h
0x1800e5d0f  lea     rdx, [rbp+1440h+var_1450]
0x1800e5d13  lea     rcx, [rsp+1540h+var_14F0]
0x1800e5d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5d1d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800e5d24  test    rax, rax
0x1800e5d27  jz      short loc_1800E5D33
0x1800e5d29  lea     rcx, [rsp+1540h+var_14F0]
0x1800e5d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5d33  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800e5d3a  test    rax, rax
0x1800e5d3d  jz      short loc_1800E5D50
0x1800e5d3f  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x1800e5d44  jnz     short loc_1800E5D50
0x1800e5d46  lea     rcx, [rsp+1540h+var_14F0]
0x1800e5d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5d50  cmp     [rsp+1540h+var_14E8], edi
0x1800e5d54  jge     loc_1800E5E5E
0x1800e5d5a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800e5d61  jnz     short loc_1800E5D82
0x1800e5d63  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800e5d6a  test    rax, rax
0x1800e5d6d  jz      short loc_1800E5D78
0x1800e5d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5d74  test    al, al
0x1800e5d76  jmp     short loc_1800E5D80
0x1800e5d78  call    cs:__imp_IsDebuggerPresent
0x1800e5d7e  test    eax, eax
0x1800e5d80  jz      short loc_1800E5D89
0x1800e5d82  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x1800e5d87  jz      short loc_1800E5DAF
0x1800e5d89  mov     rax, cs:g_pfnResultLoggingCallback
0x1800e5d90  test    rax, rax
0x1800e5d93  jz      short loc_1800E5E07
0x1800e5d95  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800e5d9c  jnz     short loc_1800E5E07
0x1800e5d9e  xor     r8d, r8d
0x1800e5da1  xor     edx, edx
0x1800e5da3  lea     rcx, [rsp+1540h+var_14F0]
0x1800e5da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5dad  jmp     short loc_1800E5E07
0x1800e5daf  mov     ebx, 800h
0x1800e5db4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800e5dbb  test    rax, rax
0x1800e5dbe  jz      short loc_1800E5DDD
0x1800e5dc0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800e5dc7  jnz     short loc_1800E5DDD
0x1800e5dc9  mov     r8d, ebx
0x1800e5dcc  lea     rdx, [rbp+1440h+OutputString]
0x1800e5dd3  lea     rcx, [rsp+1540h+var_14F0]
0x1800e5dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5ddd  cmp     [rbp+1440h+OutputString], di
0x1800e5de4  jnz     short loc_1800E5DFA
0x1800e5de6  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x1800e5deb  mov     rdx, rbx; unsigned __int16 *
0x1800e5dee  lea     rcx, [rbp+1440h+OutputString]; this
0x1800e5df5  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800e5dfa  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x1800e5e01  call    cs:__imp_OutputDebugStringW
0x1800e5e07  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x1800e5e0c  jnz     short loc_1800E5E17
0x1800e5e0e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800e5e15  jz      short loc_1800E5E29
0x1800e5e17  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800e5e1e  test    rax, rax
0x1800e5e21  jz      short loc_1800E5E29
0x1800e5e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5e28  nop
0x1800e5e29  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x1800e5e2e  jnz     short loc_1800E5E53
0x1800e5e30  mov     rcx, [rbp+1440h+var_50]
0x1800e5e37  xor     rcx, rsp; StackCookie
0x1800e5e3a  call    __security_check_cookie
0x1800e5e3f  add     rsp, 1508h
0x1800e5e46  pop     r15
0x1800e5e48  pop     r14
0x1800e5e4a  pop     r13
0x1800e5e4c  pop     r12
0x1800e5e4e  pop     rdi
0x1800e5e4f  pop     rsi
0x1800e5e50  pop     rbx
0x1800e5e51  pop     rbp
0x1800e5e52  retn
0x1800e5e53  lea     rcx, [rsp+1540h+var_14F0]; this
0x1800e5e58  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800e5e5e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
