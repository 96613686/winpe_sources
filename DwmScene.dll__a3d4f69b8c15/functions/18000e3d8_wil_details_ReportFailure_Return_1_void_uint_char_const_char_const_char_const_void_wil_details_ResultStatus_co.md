# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000e3d8`
- end: `0x18000e665`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000e098`

## callees

- `0x18000ca90`
- `0x18000d678`
- `0x18000e3d8`
- `0x18000f4b4`
- `0x180010540`
- `0x1800110f8`
- `0x1800112fc`
- `0x1800d1540`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e486`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e486`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e604`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e604`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e57a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e57a`

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
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString(OutputString, (wchar_t *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x18000e3d8  push    rbp
0x18000e3da  push    rbx
0x18000e3db  push    rsi
0x18000e3dc  push    rdi
0x18000e3dd  push    r12
0x18000e3df  push    r14
0x18000e3e1  push    r15
0x18000e3e3  lea     rbp, [rsp-13D0h]
0x18000e3eb  mov     eax, 14D0h
0x18000e3f0  call    _alloca_probe
0x18000e3f5  sub     rsp, rax
0x18000e3f8  mov     rax, cs:__security_cookie
0x18000e3ff  xor     rax, rsp
0x18000e402  mov     [rbp+1400h+var_40], rax
0x18000e409  mov     r14, r8
0x18000e40c  mov     esi, edx
0x18000e40e  mov     r15, rcx
0x18000e411  mov     rdi, [rbp+1400h+arg_28]
0x18000e418  xor     edx, edx; Val
0x18000e41a  mov     r8d, 98h; Size
0x18000e420  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000e425  call    memset_0
0x18000e42a  nop
0x18000e42b  xor     r12d, r12d
0x18000e42e  mov     [rbp+1400h+OutputString], r12w
0x18000e436  mov     [rbp+1400h+var_1440], r12b
0x18000e43a  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18000e441  mov     ecx, [rdx]; this
0x18000e443  mov     [rsp+1500h+var_14D8], ecx
0x18000e447  mov     eax, [rdx+4]
0x18000e44a  mov     [rsp+1500h+var_14D4], eax
0x18000e44e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000e453  mov     ebx, eax
0x18000e455  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000e45d  mov     ecx, r12d
0x18000e460  lea     eax, [r12+8]
0x18000e465  cmp     dword ptr [rdx+8], 1
0x18000e469  cmovz   ecx, eax
0x18000e46c  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000e470  lea     ecx, [rax-7]
0x18000e473  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000e47b  inc     ecx
0x18000e47d  mov     [rsp+1500h+var_14D0], ecx
0x18000e481  mov     [rsp+1500h+var_14C8], r12
0x18000e486  call    cs:__imp_GetCurrentThreadId
0x18000e48c  mov     [rsp+1500h+var_14C0], eax
0x18000e490  mov     [rsp+1500h+var_14A8], r14
0x18000e495  mov     [rsp+1500h+var_14A0], esi
0x18000e499  mov     [rsp+1500h+var_149C], ebx
0x18000e49d  mov     [rsp+1500h+var_14B8], r12
0x18000e4a2  mov     [rsp+1500h+var_14B0], r12
0x18000e4a7  mov     [rbp+1400h+var_1458], rdi
0x18000e4ab  mov     [rbp+1400h+var_1450], r15
0x18000e4af  mov     [rsp+1500h+var_1498], r12
0x18000e4b4  xorps   xmm0, xmm0
0x18000e4b7  xor     eax, eax
0x18000e4b9  movups  [rbp+1400h+var_1478], xmm0
0x18000e4bd  mov     [rbp+1400h+var_1468], rax
0x18000e4c1  xorps   xmm1, xmm1
0x18000e4c4  movups  [rsp+1500h+var_1490], xmm1
0x18000e4c9  mov     [rbp+1400h+var_1480], rax
0x18000e4cd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000e4d4  test    rax, rax
0x18000e4d7  jz      short loc_18000E4E4
0x18000e4d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4de  mov     [rbp+1400h+var_1460], rax
0x18000e4e2  jmp     short loc_18000E4E8
0x18000e4e4  mov     [rbp+1400h+var_1460], r12
0x18000e4e8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000e4ef  test    rax, rax
0x18000e4f2  jz      short loc_18000E4FE
0x18000e4f4  lea     rcx, [rsp+1500h+var_14E0]
0x18000e4f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4fe  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000e505  test    rax, rax
0x18000e508  jz      short loc_18000E51E
0x18000e50a  mov     r8d, 400h
0x18000e510  lea     rdx, [rbp+1400h+var_1440]
0x18000e514  lea     rcx, [rsp+1500h+var_14E0]
0x18000e519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e51e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e525  test    rax, rax
0x18000e528  jz      short loc_18000E534
0x18000e52a  lea     rcx, [rsp+1500h+var_14E0]
0x18000e52f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e534  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e53b  test    rax, rax
0x18000e53e  jz      short loc_18000E551
0x18000e540  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000e545  jnz     short loc_18000E551
0x18000e547  lea     rcx, [rsp+1500h+var_14E0]
0x18000e54c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e551  cmp     [rsp+1500h+var_14D8], r12d
0x18000e556  jge     loc_18000E65F
0x18000e55c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000e563  jnz     short loc_18000E584
0x18000e565  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000e56c  test    rax, rax
0x18000e56f  jz      short loc_18000E57A
0x18000e571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e576  test    al, al
0x18000e578  jmp     short loc_18000E582
0x18000e57a  call    cs:__imp_IsDebuggerPresent
0x18000e580  test    eax, eax
0x18000e582  jz      short loc_18000E58B
0x18000e584  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000e589  jz      short loc_18000E5B1
0x18000e58b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e592  test    rax, rax
0x18000e595  jz      short loc_18000E60A
0x18000e597  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000e59e  jnz     short loc_18000E60A
0x18000e5a0  xor     r8d, r8d
0x18000e5a3  xor     edx, edx
0x18000e5a5  lea     rcx, [rsp+1500h+var_14E0]
0x18000e5aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5af  jmp     short loc_18000E60A
0x18000e5b1  mov     ebx, 800h
0x18000e5b6  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e5bd  test    rax, rax
0x18000e5c0  jz      short loc_18000E5DF
0x18000e5c2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000e5c9  jnz     short loc_18000E5DF
0x18000e5cb  mov     r8d, ebx
0x18000e5ce  lea     rdx, [rbp+1400h+OutputString]
0x18000e5d5  lea     rcx, [rsp+1500h+var_14E0]
0x18000e5da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5df  cmp     [rbp+1400h+OutputString], r12w
0x18000e5e7  jnz     short loc_18000E5FD
0x18000e5e9  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000e5ee  mov     rdx, rbx; wchar_t *
0x18000e5f1  lea     rcx, [rbp+1400h+OutputString]; pszDest
0x18000e5f8  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000e5fd  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000e604  call    cs:__imp_OutputDebugStringW
0x18000e60a  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000e60f  jnz     short loc_18000E61A
0x18000e611  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000e618  jz      short loc_18000E62C
0x18000e61a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000e621  test    rax, rax
0x18000e624  jz      short loc_18000E62C
0x18000e626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e62b  nop
0x18000e62c  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000e631  jnz     short loc_18000E654
0x18000e633  mov     rcx, [rbp+1400h+var_40]
0x18000e63a  xor     rcx, rsp; StackCookie
0x18000e63d  call    __security_check_cookie
0x18000e642  add     rsp, 14D0h
0x18000e649  pop     r15
0x18000e64b  pop     r14
0x18000e64d  pop     r12
0x18000e64f  pop     rdi
0x18000e650  pop     rsi
0x18000e651  pop     rbx
0x18000e652  pop     rbp
0x18000e653  retn
0x18000e654  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000e659  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000e65f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
