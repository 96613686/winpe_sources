# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18009f568`
- end: `0x18009f7f5`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180097c18`

## callees

- `0x18009d670`
- `0x18009e054`
- `0x18009f568`
- `0x1800a02e4`
- `0x1800a0f20`
- `0x1800a19a8`
- `0x1800a1ad8`
- `0x1800c8990`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009f616`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009f616`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18009f794`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18009f794`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18009f70a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18009f70a`

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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v17, v15);
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
0x18009f568  push    rbp
0x18009f56a  push    rbx
0x18009f56b  push    rsi
0x18009f56c  push    rdi
0x18009f56d  push    r12
0x18009f56f  push    r14
0x18009f571  push    r15
0x18009f573  lea     rbp, [rsp-13D0h]
0x18009f57b  mov     eax, 14D0h
0x18009f580  call    _alloca_probe
0x18009f585  sub     rsp, rax
0x18009f588  mov     rax, cs:__security_cookie
0x18009f58f  xor     rax, rsp
0x18009f592  mov     [rbp+1400h+var_40], rax
0x18009f599  mov     r14, r8
0x18009f59c  mov     esi, edx
0x18009f59e  mov     r15, rcx
0x18009f5a1  mov     rdi, [rbp+1400h+arg_28]
0x18009f5a8  xor     edx, edx; Val
0x18009f5aa  mov     r8d, 98h; Size
0x18009f5b0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18009f5b5  call    memset_0
0x18009f5ba  nop
0x18009f5bb  xor     r12d, r12d
0x18009f5be  mov     [rbp+1400h+OutputString], r12w
0x18009f5c6  mov     [rbp+1400h+var_1440], r12b
0x18009f5ca  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18009f5d1  mov     ecx, [rdx]; this
0x18009f5d3  mov     [rsp+1500h+var_14D8], ecx
0x18009f5d7  mov     eax, [rdx+4]
0x18009f5da  mov     [rsp+1500h+var_14D4], eax
0x18009f5de  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18009f5e3  mov     ebx, eax
0x18009f5e5  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18009f5ed  mov     ecx, r12d
0x18009f5f0  lea     eax, [r12+8]
0x18009f5f5  cmp     dword ptr [rdx+8], 1
0x18009f5f9  cmovz   ecx, eax
0x18009f5fc  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18009f600  lea     ecx, [rax-7]
0x18009f603  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18009f60b  inc     ecx
0x18009f60d  mov     [rsp+1500h+var_14D0], ecx
0x18009f611  mov     [rsp+1500h+var_14C8], r12
0x18009f616  call    cs:__imp_GetCurrentThreadId
0x18009f61c  mov     [rsp+1500h+var_14C0], eax
0x18009f620  mov     [rsp+1500h+var_14A8], r14
0x18009f625  mov     [rsp+1500h+var_14A0], esi
0x18009f629  mov     [rsp+1500h+var_149C], ebx
0x18009f62d  mov     [rsp+1500h+var_14B8], r12
0x18009f632  mov     [rsp+1500h+var_14B0], r12
0x18009f637  mov     [rbp+1400h+var_1458], rdi
0x18009f63b  mov     [rbp+1400h+var_1450], r15
0x18009f63f  mov     [rsp+1500h+var_1498], r12
0x18009f644  xorps   xmm0, xmm0
0x18009f647  xor     eax, eax
0x18009f649  movups  [rbp+1400h+var_1478], xmm0
0x18009f64d  mov     [rbp+1400h+var_1468], rax
0x18009f651  xorps   xmm1, xmm1
0x18009f654  movups  [rsp+1500h+var_1490], xmm1
0x18009f659  mov     [rbp+1400h+var_1480], rax
0x18009f65d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18009f664  test    rax, rax
0x18009f667  jz      short loc_18009F674
0x18009f669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f66e  mov     [rbp+1400h+var_1460], rax
0x18009f672  jmp     short loc_18009F678
0x18009f674  mov     [rbp+1400h+var_1460], r12
0x18009f678  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18009f67f  test    rax, rax
0x18009f682  jz      short loc_18009F68E
0x18009f684  lea     rcx, [rsp+1500h+var_14E0]
0x18009f689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f68e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18009f695  test    rax, rax
0x18009f698  jz      short loc_18009F6AE
0x18009f69a  mov     r8d, 400h
0x18009f6a0  lea     rdx, [rbp+1400h+var_1440]
0x18009f6a4  lea     rcx, [rsp+1500h+var_14E0]
0x18009f6a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f6ae  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18009f6b5  test    rax, rax
0x18009f6b8  jz      short loc_18009F6C4
0x18009f6ba  lea     rcx, [rsp+1500h+var_14E0]
0x18009f6bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f6c4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18009f6cb  test    rax, rax
0x18009f6ce  jz      short loc_18009F6E1
0x18009f6d0  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18009f6d5  jnz     short loc_18009F6E1
0x18009f6d7  lea     rcx, [rsp+1500h+var_14E0]
0x18009f6dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f6e1  cmp     [rsp+1500h+var_14D8], r12d
0x18009f6e6  jge     loc_18009F7EF
0x18009f6ec  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18009f6f3  jnz     short loc_18009F714
0x18009f6f5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18009f6fc  test    rax, rax
0x18009f6ff  jz      short loc_18009F70A
0x18009f701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f706  test    al, al
0x18009f708  jmp     short loc_18009F712
0x18009f70a  call    cs:__imp_IsDebuggerPresent
0x18009f710  test    eax, eax
0x18009f712  jz      short loc_18009F71B
0x18009f714  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18009f719  jz      short loc_18009F741
0x18009f71b  mov     rax, cs:g_pfnResultLoggingCallback
0x18009f722  test    rax, rax
0x18009f725  jz      short loc_18009F79A
0x18009f727  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18009f72e  jnz     short loc_18009F79A
0x18009f730  xor     r8d, r8d
0x18009f733  xor     edx, edx
0x18009f735  lea     rcx, [rsp+1500h+var_14E0]
0x18009f73a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f73f  jmp     short loc_18009F79A
0x18009f741  mov     ebx, 800h
0x18009f746  mov     rax, cs:g_pfnResultLoggingCallback
0x18009f74d  test    rax, rax
0x18009f750  jz      short loc_18009F76F
0x18009f752  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18009f759  jnz     short loc_18009F76F
0x18009f75b  mov     r8d, ebx
0x18009f75e  lea     rdx, [rbp+1400h+OutputString]
0x18009f765  lea     rcx, [rsp+1500h+var_14E0]
0x18009f76a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f76f  cmp     [rbp+1400h+OutputString], r12w
0x18009f777  jnz     short loc_18009F78D
0x18009f779  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18009f77e  mov     rdx, rbx; wchar_t *
0x18009f781  lea     rcx, [rbp+1400h+OutputString]; this
0x18009f788  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18009f78d  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18009f794  call    cs:__imp_OutputDebugStringW
0x18009f79a  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18009f79f  jnz     short loc_18009F7AA
0x18009f7a1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18009f7a8  jz      short loc_18009F7BC
0x18009f7aa  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18009f7b1  test    rax, rax
0x18009f7b4  jz      short loc_18009F7BC
0x18009f7b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f7bb  nop
0x18009f7bc  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18009f7c1  jnz     short loc_18009F7E4
0x18009f7c3  mov     rcx, [rbp+1400h+var_40]
0x18009f7ca  xor     rcx, rsp; StackCookie
0x18009f7cd  call    __security_check_cookie
0x18009f7d2  add     rsp, 14D0h
0x18009f7d9  pop     r15
0x18009f7db  pop     r14
0x18009f7dd  pop     r12
0x18009f7df  pop     rdi
0x18009f7e0  pop     rsi
0x18009f7e1  pop     rbx
0x18009f7e2  pop     rbp
0x18009f7e3  retn
0x18009f7e4  lea     rcx, [rsp+1500h+var_14E0]; this
0x18009f7e9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18009f7ef  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
