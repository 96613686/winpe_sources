# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18009b668`
- end: `0x18009b906`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `670`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18006e230`

## callees

- `0x180074160`
- `0x180074a06`
- `0x18009b668`
- `0x18009ed74`
- `0x1800a2d14`
- `0x1800a3570`
- `0x1800a364c`
- `0x1800c8220`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009b715`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009b715`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18009b89f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18009b89f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18009b80f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18009b80f`

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
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // ebx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v22, (int)a7);
  v19 = *(_DWORD *)(v12 + 8) == 1;
  v13 = v11;
  v20 = 1;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x18009b668  push    rbp
0x18009b66a  push    rbx
0x18009b66b  push    rsi
0x18009b66c  push    rdi
0x18009b66d  push    r12
0x18009b66f  push    r14
0x18009b671  push    r15
0x18009b673  lea     rbp, [rsp-13D0h]
0x18009b67b  mov     eax, 14D0h
0x18009b680  call    _alloca_probe
0x18009b685  sub     rsp, rax
0x18009b688  mov     rax, cs:__security_cookie
0x18009b68f  xor     rax, rsp
0x18009b692  mov     [rbp+1400h+var_40], rax
0x18009b699  mov     rdi, [rbp+1400h+arg_28]
0x18009b6a0  mov     r14, r8
0x18009b6a3  mov     esi, edx
0x18009b6a5  mov     r15, rcx
0x18009b6a8  xor     edx, edx; Val
0x18009b6aa  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18009b6af  mov     r8d, 98h; Size
0x18009b6b5  call    memset_0
0x18009b6ba  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18009b6c1  xor     r12d, r12d
0x18009b6c4  mov     [rbp+1400h+OutputString], r12w
0x18009b6cc  mov     [rbp+1400h+var_1440], r12b
0x18009b6d0  mov     ecx, [rdx]; this
0x18009b6d2  mov     eax, [rdx+4]
0x18009b6d5  mov     [rsp+1500h+var_14D8], ecx
0x18009b6d9  mov     [rsp+1500h+var_14D4], eax
0x18009b6dd  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18009b6e2  cmp     dword ptr [rdx+8], 1
0x18009b6e6  mov     ebx, eax
0x18009b6e8  lea     eax, [r12+8]
0x18009b6ed  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18009b6f5  mov     ecx, r12d
0x18009b6f8  cmovz   ecx, eax
0x18009b6fb  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18009b6ff  lea     ecx, [rax-7]
0x18009b702  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18009b70a  inc     ecx
0x18009b70c  mov     [rsp+1500h+var_14C8], r12
0x18009b711  mov     [rsp+1500h+var_14D0], ecx
0x18009b715  call    cs:__imp_GetCurrentThreadId
0x18009b71c  nop     dword ptr [rax+rax+00h]
0x18009b721  xorps   xmm0, xmm0
0x18009b724  mov     [rsp+1500h+var_14A8], r14
0x18009b729  mov     [rsp+1500h+var_14C0], eax
0x18009b72d  xorps   xmm1, xmm1
0x18009b730  xor     eax, eax
0x18009b732  mov     [rsp+1500h+var_14A0], esi
0x18009b736  mov     [rbp+1400h+var_1468], rax
0x18009b73a  mov     [rbp+1400h+var_1480], rax
0x18009b73e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18009b745  mov     [rsp+1500h+var_149C], ebx
0x18009b749  mov     [rsp+1500h+var_14B8], r12
0x18009b74e  mov     [rsp+1500h+var_14B0], r12
0x18009b753  mov     [rbp+1400h+var_1458], rdi
0x18009b757  mov     [rbp+1400h+var_1450], r15
0x18009b75b  mov     [rsp+1500h+var_1498], r12
0x18009b760  movups  [rbp+1400h+var_1478], xmm0
0x18009b764  movups  [rsp+1500h+var_1490], xmm1
0x18009b769  test    rax, rax
0x18009b76c  jz      short loc_18009B779
0x18009b76e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b773  mov     [rbp+1400h+var_1460], rax
0x18009b777  jmp     short loc_18009B77D
0x18009b779  mov     [rbp+1400h+var_1460], r12
0x18009b77d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18009b784  test    rax, rax
0x18009b787  jz      short loc_18009B793
0x18009b789  lea     rcx, [rsp+1500h+var_14E0]
0x18009b78e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b793  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18009b79a  test    rax, rax
0x18009b79d  jz      short loc_18009B7B3
0x18009b79f  mov     r8d, 400h
0x18009b7a5  lea     rdx, [rbp+1400h+var_1440]
0x18009b7a9  lea     rcx, [rsp+1500h+var_14E0]
0x18009b7ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b7b3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18009b7ba  test    rax, rax
0x18009b7bd  jz      short loc_18009B7C9
0x18009b7bf  lea     rcx, [rsp+1500h+var_14E0]
0x18009b7c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b7c9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18009b7d0  test    rax, rax
0x18009b7d3  jz      short loc_18009B7E6
0x18009b7d5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18009b7da  jnz     short loc_18009B7E6
0x18009b7dc  lea     rcx, [rsp+1500h+var_14E0]
0x18009b7e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b7e6  cmp     [rsp+1500h+var_14D8], r12d
0x18009b7eb  jge     loc_18009B8F5
0x18009b7f1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18009b7f8  jnz     short loc_18009B81F
0x18009b7fa  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18009b801  test    rax, rax
0x18009b804  jz      short loc_18009B80F
0x18009b806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b80b  test    al, al
0x18009b80d  jmp     short loc_18009B81D
0x18009b80f  call    cs:__imp_IsDebuggerPresent
0x18009b816  nop     dword ptr [rax+rax+00h]
0x18009b81b  test    eax, eax
0x18009b81d  jz      short loc_18009B826
0x18009b81f  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18009b824  jz      short loc_18009B84C
0x18009b826  mov     rax, cs:g_pfnResultLoggingCallback
0x18009b82d  test    rax, rax
0x18009b830  jz      short loc_18009B8AB
0x18009b832  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18009b839  jnz     short loc_18009B8AB
0x18009b83b  xor     r8d, r8d
0x18009b83e  lea     rcx, [rsp+1500h+var_14E0]
0x18009b843  xor     edx, edx
0x18009b845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b84a  jmp     short loc_18009B8AB
0x18009b84c  mov     rax, cs:g_pfnResultLoggingCallback
0x18009b853  mov     ebx, 800h
0x18009b858  test    rax, rax
0x18009b85b  jz      short loc_18009B87A
0x18009b85d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18009b864  jnz     short loc_18009B87A
0x18009b866  mov     r8d, ebx
0x18009b869  lea     rdx, [rbp+1400h+OutputString]
0x18009b870  lea     rcx, [rsp+1500h+var_14E0]
0x18009b875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b87a  cmp     [rbp+1400h+OutputString], r12w
0x18009b882  jnz     short loc_18009B898
0x18009b884  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18009b889  mov     rdx, rbx; unsigned __int16 *
0x18009b88c  lea     rcx, [rbp+1400h+OutputString]; this
0x18009b893  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18009b898  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18009b89f  call    cs:__imp_OutputDebugStringW
0x18009b8a6  nop     dword ptr [rax+rax+00h]
0x18009b8ab  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18009b8b0  jnz     short loc_18009B8BB
0x18009b8b2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18009b8b9  jz      short loc_18009B8CC
0x18009b8bb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18009b8c2  test    rax, rax
0x18009b8c5  jz      short loc_18009B8CC
0x18009b8c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b8cc  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18009b8d1  jnz     short loc_18009B8FB
0x18009b8d3  mov     rcx, [rbp+1400h+var_40]
0x18009b8da  xor     rcx, rsp; StackCookie
0x18009b8dd  call    __security_check_cookie
0x18009b8e2  add     rsp, 14D0h
0x18009b8e9  pop     r15
0x18009b8eb  pop     r14
0x18009b8ed  pop     r12
0x18009b8ef  pop     rdi
0x18009b8f0  pop     rsi
0x18009b8f1  pop     rbx
0x18009b8f2  pop     rbp
0x18009b8f3  retn
0x18009b8f5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18009b8fb  lea     rcx, [rsp+1500h+var_14E0]; this
0x18009b900  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
