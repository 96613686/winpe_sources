# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800e58b8`
- end: `0x1800e5b5e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800e534c`

## callees

- `0x180003060`
- `0x180003a40`
- `0x1800e4d20`
- `0x1800e58b8`
- `0x1800e7f74`
- `0x1800e9918`
- `0x1800ec390`
- `0x1800ec608`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e597e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e597e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800e5afd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800e5afd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800e5a73`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800e5a73`

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
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x1800e58b8  push    rbp
0x1800e58ba  push    rbx
0x1800e58bb  push    rsi
0x1800e58bc  push    rdi
0x1800e58bd  push    r12
0x1800e58bf  push    r14
0x1800e58c1  push    r15
0x1800e58c3  lea     rbp, [rsp-13D0h]
0x1800e58cb  mov     eax, 14D0h
0x1800e58d0  call    _alloca_probe
0x1800e58d5  sub     rsp, rax
0x1800e58d8  mov     rax, cs:__security_cookie
0x1800e58df  xor     rax, rsp
0x1800e58e2  mov     [rbp+1400h+var_40], rax
0x1800e58e9  mov     rsi, r8
0x1800e58ec  mov     edi, edx
0x1800e58ee  mov     rbx, rcx
0x1800e58f1  mov     r14, [rbp+1400h+arg_28]
0x1800e58f8  xor     edx, edx; Val
0x1800e58fa  mov     r8d, 98h; Size
0x1800e5900  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800e5905  call    memset_0
0x1800e590a  nop
0x1800e590b  xor     r12d, r12d
0x1800e590e  mov     [rbp+1400h+OutputString], r12w
0x1800e5916  mov     [rbp+1400h+var_1440], r12b
0x1800e591a  mov     rdx, [rbp+1400h+arg_30]; int
0x1800e5921  mov     ecx, [rdx]; this
0x1800e5923  mov     [rsp+1500h+var_14D8], ecx
0x1800e5927  mov     eax, [rdx+4]
0x1800e592a  mov     [rsp+1500h+var_14D4], eax
0x1800e592e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800e5933  mov     r15d, eax
0x1800e5936  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800e593e  mov     ecx, r12d
0x1800e5941  lea     eax, [r12+8]
0x1800e5946  cmp     dword ptr [rdx+8], 1
0x1800e594a  cmovz   ecx, eax
0x1800e594d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800e5951  lea     ecx, [rax-7]
0x1800e5954  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800e595c  inc     ecx
0x1800e595e  mov     [rsp+1500h+var_14D0], ecx
0x1800e5962  mov     rcx, [rbp+1400h+arg_38]
0x1800e5969  test    rcx, rcx
0x1800e596c  jz      short loc_1800E5979
0x1800e596e  cmp     [rcx], r12w
0x1800e5972  mov     [rsp+1500h+var_14C8], rcx
0x1800e5977  jnz     short loc_1800E597E
0x1800e5979  mov     [rsp+1500h+var_14C8], r12
0x1800e597e  call    cs:__imp_GetCurrentThreadId
0x1800e5984  mov     [rsp+1500h+var_14C0], eax
0x1800e5988  mov     [rsp+1500h+var_14A8], rsi
0x1800e598d  mov     [rsp+1500h+var_14A0], edi
0x1800e5991  mov     [rsp+1500h+var_149C], r15d
0x1800e5996  mov     [rsp+1500h+var_14B8], r12
0x1800e599b  mov     [rsp+1500h+var_14B0], r12
0x1800e59a0  mov     [rbp+1400h+var_1458], r14
0x1800e59a4  mov     [rbp+1400h+var_1450], rbx
0x1800e59a8  mov     [rsp+1500h+var_1498], r12
0x1800e59ad  xorps   xmm0, xmm0
0x1800e59b0  xor     eax, eax
0x1800e59b2  movups  [rbp+1400h+var_1478], xmm0
0x1800e59b6  mov     [rbp+1400h+var_1468], rax
0x1800e59ba  xorps   xmm1, xmm1
0x1800e59bd  movups  [rsp+1500h+var_1490], xmm1
0x1800e59c2  mov     [rbp+1400h+var_1480], rax
0x1800e59c6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800e59cd  test    rax, rax
0x1800e59d0  jz      short loc_1800E59DD
0x1800e59d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e59d7  mov     [rbp+1400h+var_1460], rax
0x1800e59db  jmp     short loc_1800E59E1
0x1800e59dd  mov     [rbp+1400h+var_1460], r12
0x1800e59e1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800e59e8  test    rax, rax
0x1800e59eb  jz      short loc_1800E59F7
0x1800e59ed  lea     rcx, [rsp+1500h+var_14E0]
0x1800e59f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e59f7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800e59fe  test    rax, rax
0x1800e5a01  jz      short loc_1800E5A17
0x1800e5a03  mov     r8d, 400h
0x1800e5a09  lea     rdx, [rbp+1400h+var_1440]
0x1800e5a0d  lea     rcx, [rsp+1500h+var_14E0]
0x1800e5a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5a17  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800e5a1e  test    rax, rax
0x1800e5a21  jz      short loc_1800E5A2D
0x1800e5a23  lea     rcx, [rsp+1500h+var_14E0]
0x1800e5a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5a2d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800e5a34  test    rax, rax
0x1800e5a37  jz      short loc_1800E5A4A
0x1800e5a39  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800e5a3e  jnz     short loc_1800E5A4A
0x1800e5a40  lea     rcx, [rsp+1500h+var_14E0]
0x1800e5a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5a4a  cmp     [rsp+1500h+var_14D8], r12d
0x1800e5a4f  jge     loc_1800E5B58
0x1800e5a55  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800e5a5c  jnz     short loc_1800E5A7D
0x1800e5a5e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800e5a65  test    rax, rax
0x1800e5a68  jz      short loc_1800E5A73
0x1800e5a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5a6f  test    al, al
0x1800e5a71  jmp     short loc_1800E5A7B
0x1800e5a73  call    cs:__imp_IsDebuggerPresent
0x1800e5a79  test    eax, eax
0x1800e5a7b  jz      short loc_1800E5A84
0x1800e5a7d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800e5a82  jz      short loc_1800E5AAA
0x1800e5a84  mov     rax, cs:g_pfnResultLoggingCallback
0x1800e5a8b  test    rax, rax
0x1800e5a8e  jz      short loc_1800E5B03
0x1800e5a90  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800e5a97  jnz     short loc_1800E5B03
0x1800e5a99  xor     r8d, r8d
0x1800e5a9c  xor     edx, edx
0x1800e5a9e  lea     rcx, [rsp+1500h+var_14E0]
0x1800e5aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5aa8  jmp     short loc_1800E5B03
0x1800e5aaa  mov     ebx, 800h
0x1800e5aaf  mov     rax, cs:g_pfnResultLoggingCallback
0x1800e5ab6  test    rax, rax
0x1800e5ab9  jz      short loc_1800E5AD8
0x1800e5abb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800e5ac2  jnz     short loc_1800E5AD8
0x1800e5ac4  mov     r8d, ebx
0x1800e5ac7  lea     rdx, [rbp+1400h+OutputString]
0x1800e5ace  lea     rcx, [rsp+1500h+var_14E0]
0x1800e5ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5ad8  cmp     [rbp+1400h+OutputString], r12w
0x1800e5ae0  jnz     short loc_1800E5AF6
0x1800e5ae2  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800e5ae7  mov     rdx, rbx; unsigned __int16 *
0x1800e5aea  lea     rcx, [rbp+1400h+OutputString]; this
0x1800e5af1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800e5af6  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800e5afd  call    cs:__imp_OutputDebugStringW
0x1800e5b03  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800e5b08  jnz     short loc_1800E5B13
0x1800e5b0a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800e5b11  jz      short loc_1800E5B25
0x1800e5b13  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800e5b1a  test    rax, rax
0x1800e5b1d  jz      short loc_1800E5B25
0x1800e5b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5b24  nop
0x1800e5b25  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800e5b2a  jnz     short loc_1800E5B4D
0x1800e5b2c  mov     rcx, [rbp+1400h+var_40]
0x1800e5b33  xor     rcx, rsp; StackCookie
0x1800e5b36  call    __security_check_cookie
0x1800e5b3b  add     rsp, 14D0h
0x1800e5b42  pop     r15
0x1800e5b44  pop     r14
0x1800e5b46  pop     r12
0x1800e5b48  pop     rdi
0x1800e5b49  pop     rsi
0x1800e5b4a  pop     rbx
0x1800e5b4b  pop     rbp
0x1800e5b4c  retn
0x1800e5b4d  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800e5b52  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800e5b58  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
