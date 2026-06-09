# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800f7d7c`
- end: `0x1800f801b`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `671`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800f76bc`

## callees

- `0x180003060`
- `0x180003a40`
- `0x1800e4d20`
- `0x1800e9918`
- `0x1800ec390`
- `0x1800ec608`
- `0x1800f7d7c`
- `0x1800f95b0`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f7e41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f7e41`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800f7fbb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800f7fbb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800f7f36`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800f7f36`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  int v14; // r15d
  int v15; // ecx
  DWORD CurrentThreadId; // eax
  wchar_t *v17; // rdx
  wil::details::in1diag3 *v18; // rcx
  const struct wil::FailureInfo *v19; // r9
  bool v20; // zf
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+24h] [rbp-DCh]
  int v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v25; // [rsp+30h] [rbp-D0h]
  _WORD *v26; // [rsp+38h] [rbp-C8h]
  DWORD v27; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+60h] [rbp-A0h]
  int v32; // [rsp+64h] [rbp-9Ch]
  __int64 v33; // [rsp+68h] [rbp-98h]
  __int128 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+80h] [rbp-80h]
  __int128 v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  char v41[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v21, 0, 0x98u);
  OutputString[0] = 0;
  v41[0] = 0;
  v11 = a7[1];
  v23 = *a7;
  v24 = v11;
  v12 = wil::details::RecordReturn((wil::details *)(unsigned int)v23, (int)a7);
  v20 = *(_DWORD *)(v13 + 8) == 1;
  v14 = v12;
  v21 = 1;
  v15 = 0;
  if ( v20 )
    v15 = 8;
  v22 = v15;
  v25 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v26 = a8, !*a8) )
    v26 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v30 = a3;
  v27 = CurrentThreadId;
  v31 = a2;
  v37 = 0;
  v35 = 0;
  v32 = v14;
  v28 = 0;
  v29 = 0;
  v39 = a6;
  v40 = a1;
  v33 = 0;
  v36 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v18);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v21);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v21, v41, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v21);
  if ( wil::details::g_pfnOriginateCallback && (v22 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v21);
  if ( v23 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v18);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v20 = !IsDebuggerPresent())
      : (v20 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v18) == 0),
        v20)
    || (v22 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, v17, (unsigned __int64)&v21, v19);
    OutputDebugStringW(OutputString);
  }
  if ( ((v22 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v18);
  if ( (v22 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v21, (const struct wil::FailureInfo *)v17);
}

```

## disassembly

```asm
0x1800f7d7c  push    rbp
0x1800f7d7e  push    rbx
0x1800f7d7f  push    rsi
0x1800f7d80  push    rdi
0x1800f7d81  push    r12
0x1800f7d83  push    r14
0x1800f7d85  push    r15
0x1800f7d87  lea     rbp, [rsp-13D0h]
0x1800f7d8f  mov     eax, 14D0h
0x1800f7d94  call    _alloca_probe
0x1800f7d99  sub     rsp, rax
0x1800f7d9c  mov     rax, cs:__security_cookie
0x1800f7da3  xor     rax, rsp
0x1800f7da6  mov     [rbp+1400h+var_40], rax
0x1800f7dad  mov     r14, [rbp+1400h+arg_28]
0x1800f7db4  mov     rsi, r8
0x1800f7db7  mov     edi, edx
0x1800f7db9  mov     rbx, rcx
0x1800f7dbc  xor     edx, edx; Val
0x1800f7dbe  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800f7dc3  mov     r8d, 98h; Size
0x1800f7dc9  call    memset_0
0x1800f7dce  mov     rdx, [rbp+1400h+arg_30]; int
0x1800f7dd5  xor     r12d, r12d
0x1800f7dd8  mov     [rbp+1400h+OutputString], r12w
0x1800f7de0  mov     [rbp+1400h+var_1440], r12b
0x1800f7de4  mov     ecx, [rdx]; this
0x1800f7de6  mov     eax, [rdx+4]
0x1800f7de9  mov     [rsp+1500h+var_14D8], ecx
0x1800f7ded  mov     [rsp+1500h+var_14D4], eax
0x1800f7df1  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800f7df6  cmp     dword ptr [rdx+8], 1
0x1800f7dfa  mov     r15d, eax
0x1800f7dfd  lea     eax, [r12+8]
0x1800f7e02  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800f7e0a  mov     ecx, r12d
0x1800f7e0d  cmovz   ecx, eax
0x1800f7e10  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800f7e14  lea     ecx, [rax-7]
0x1800f7e17  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800f7e1f  inc     ecx
0x1800f7e21  mov     [rsp+1500h+var_14D0], ecx
0x1800f7e25  mov     rcx, [rbp+1400h+arg_38]
0x1800f7e2c  test    rcx, rcx
0x1800f7e2f  jz      short loc_1800F7E3C
0x1800f7e31  mov     [rsp+1500h+var_14C8], rcx
0x1800f7e36  cmp     [rcx], r12w
0x1800f7e3a  jnz     short loc_1800F7E41
0x1800f7e3c  mov     [rsp+1500h+var_14C8], r12
0x1800f7e41  call    cs:__imp_GetCurrentThreadId
0x1800f7e47  xorps   xmm0, xmm0
0x1800f7e4a  mov     [rsp+1500h+var_14A8], rsi
0x1800f7e4f  mov     [rsp+1500h+var_14C0], eax
0x1800f7e53  xorps   xmm1, xmm1
0x1800f7e56  xor     eax, eax
0x1800f7e58  mov     [rsp+1500h+var_14A0], edi
0x1800f7e5c  mov     [rbp+1400h+var_1468], rax
0x1800f7e60  mov     [rbp+1400h+var_1480], rax
0x1800f7e64  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800f7e6b  mov     [rsp+1500h+var_149C], r15d
0x1800f7e70  mov     [rsp+1500h+var_14B8], r12
0x1800f7e75  mov     [rsp+1500h+var_14B0], r12
0x1800f7e7a  mov     [rbp+1400h+var_1458], r14
0x1800f7e7e  mov     [rbp+1400h+var_1450], rbx
0x1800f7e82  mov     [rsp+1500h+var_1498], r12
0x1800f7e87  movups  [rbp+1400h+var_1478], xmm0
0x1800f7e8b  movups  [rsp+1500h+var_1490], xmm1
0x1800f7e90  test    rax, rax
0x1800f7e93  jz      short loc_1800F7EA0
0x1800f7e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7e9a  mov     [rbp+1400h+var_1460], rax
0x1800f7e9e  jmp     short loc_1800F7EA4
0x1800f7ea0  mov     [rbp+1400h+var_1460], r12
0x1800f7ea4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800f7eab  test    rax, rax
0x1800f7eae  jz      short loc_1800F7EBA
0x1800f7eb0  lea     rcx, [rsp+1500h+var_14E0]
0x1800f7eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7eba  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800f7ec1  test    rax, rax
0x1800f7ec4  jz      short loc_1800F7EDA
0x1800f7ec6  mov     r8d, 400h
0x1800f7ecc  lea     rdx, [rbp+1400h+var_1440]
0x1800f7ed0  lea     rcx, [rsp+1500h+var_14E0]
0x1800f7ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7eda  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800f7ee1  test    rax, rax
0x1800f7ee4  jz      short loc_1800F7EF0
0x1800f7ee6  lea     rcx, [rsp+1500h+var_14E0]
0x1800f7eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7ef0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800f7ef7  test    rax, rax
0x1800f7efa  jz      short loc_1800F7F0D
0x1800f7efc  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800f7f01  jnz     short loc_1800F7F0D
0x1800f7f03  lea     rcx, [rsp+1500h+var_14E0]
0x1800f7f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7f0d  cmp     [rsp+1500h+var_14D8], r12d
0x1800f7f12  jge     loc_1800F8015
0x1800f7f18  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800f7f1f  jnz     short loc_1800F7F40
0x1800f7f21  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800f7f28  test    rax, rax
0x1800f7f2b  jz      short loc_1800F7F36
0x1800f7f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7f32  test    al, al
0x1800f7f34  jmp     short loc_1800F7F3E
0x1800f7f36  call    cs:__imp_IsDebuggerPresent
0x1800f7f3c  test    eax, eax
0x1800f7f3e  jz      short loc_1800F7F47
0x1800f7f40  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800f7f45  jz      short loc_1800F7F6D
0x1800f7f47  mov     rax, cs:g_pfnResultLoggingCallback
0x1800f7f4e  test    rax, rax
0x1800f7f51  jz      short loc_1800F7FC1
0x1800f7f53  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800f7f5a  jnz     short loc_1800F7FC1
0x1800f7f5c  xor     r8d, r8d
0x1800f7f5f  lea     rcx, [rsp+1500h+var_14E0]
0x1800f7f64  xor     edx, edx
0x1800f7f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7f6b  jmp     short loc_1800F7FC1
0x1800f7f6d  mov     rax, cs:g_pfnResultLoggingCallback
0x1800f7f74  test    rax, rax
0x1800f7f77  jz      short loc_1800F7F99
0x1800f7f79  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800f7f80  jnz     short loc_1800F7F99
0x1800f7f82  mov     r8d, 800h
0x1800f7f88  lea     rdx, [rbp+1400h+OutputString]
0x1800f7f8f  lea     rcx, [rsp+1500h+var_14E0]
0x1800f7f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7f99  cmp     [rbp+1400h+OutputString], r12w
0x1800f7fa1  jnz     short loc_1800F7FB4
0x1800f7fa3  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800f7fa8  lea     rcx, [rbp+1400h+OutputString]; this
0x1800f7faf  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800f7fb4  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800f7fbb  call    cs:__imp_OutputDebugStringW
0x1800f7fc1  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800f7fc6  jnz     short loc_1800F7FD1
0x1800f7fc8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800f7fcf  jz      short loc_1800F7FE2
0x1800f7fd1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800f7fd8  test    rax, rax
0x1800f7fdb  jz      short loc_1800F7FE2
0x1800f7fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7fe2  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800f7fe7  jnz     short loc_1800F800A
0x1800f7fe9  mov     rcx, [rbp+1400h+var_40]
0x1800f7ff0  xor     rcx, rsp; StackCookie
0x1800f7ff3  call    __security_check_cookie
0x1800f7ff8  add     rsp, 14D0h
0x1800f7fff  pop     r15
0x1800f8001  pop     r14
0x1800f8003  pop     r12
0x1800f8005  pop     rdi
0x1800f8006  pop     rsi
0x1800f8007  pop     rbx
0x1800f8008  pop     rbp
0x1800f8009  retn
0x1800f800a  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800f800f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800f8015  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
