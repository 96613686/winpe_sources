# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x1800f7a10`
- end: `0x1800f7c82`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `626`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800f76d4`

## callees

- `0x180003a40`
- `0x1800e4d20`
- `0x1800e8820`
- `0x1800e97d0`
- `0x1800ec390`
- `0x1800f7a10`
- `0x1800f95b0`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f7ac8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f7ac8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800f7c50`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800f7c50`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800f7bcb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800f7bcb`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
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
  int v12; // edx
  int v13; // eax
  int v14; // r12d
  int v15; // ecx
  DWORD CurrentThreadId; // eax
  wchar_t *v17; // rdx
  __int64 v18; // rcx
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v21, 0, 0x98u);
  OutputString[0] = 0;
  v41[0] = 0;
  v11 = a7[1];
  v23 = *a7;
  v24 = v11;
  v13 = wil::details::RecordFailFast((wil::details *)(unsigned int)v23, v12);
  v20 = a7[2] == 1;
  v14 = v13;
  v21 = 3;
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
  {
    v23 = -2147418113;
    v24 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v17);
  }
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
  if ( (v22 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v18);
  }
  wil::details::WilFailFast((wil::details *)&v21, (const struct wil::FailureInfo *)v17);
}

```

## disassembly

```asm
0x1800f7a10  mov     [rsp-8+arg_18], rbx
0x1800f7a15  push    rbp
0x1800f7a16  push    rsi
0x1800f7a17  push    rdi
0x1800f7a18  push    r12
0x1800f7a1a  push    r13
0x1800f7a1c  push    r14
0x1800f7a1e  push    r15
0x1800f7a20  lea     rbp, [rsp-13C0h]
0x1800f7a28  mov     eax, 14C0h
0x1800f7a2d  call    _alloca_probe
0x1800f7a32  sub     rsp, rax
0x1800f7a35  mov     r15, [rbp+13F0h+arg_28]
0x1800f7a3c  mov     r14, r8
0x1800f7a3f  mov     esi, edx
0x1800f7a41  mov     rdi, rcx
0x1800f7a44  xor     edx, edx; Val
0x1800f7a46  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800f7a4b  mov     r8d, 98h; Size
0x1800f7a51  call    memset_0
0x1800f7a56  mov     rbx, [rbp+13F0h+arg_30]
0x1800f7a5d  xor     r13d, r13d
0x1800f7a60  mov     [rbp+13F0h+OutputString], r13w
0x1800f7a68  mov     [rbp+13F0h+var_1430], r13b
0x1800f7a6c  mov     ecx, [rbx]; this
0x1800f7a6e  mov     eax, [rbx+4]
0x1800f7a71  mov     [rsp+14F0h+var_14C8], ecx
0x1800f7a75  mov     [rsp+14F0h+var_14C4], eax
0x1800f7a79  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800f7a7e  cmp     dword ptr [rbx+8], 1
0x1800f7a82  mov     r12d, eax
0x1800f7a85  lea     eax, [r13+8]
0x1800f7a89  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800f7a91  mov     ecx, r13d
0x1800f7a94  cmovz   ecx, eax
0x1800f7a97  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800f7a9b  lea     ecx, [rax-7]
0x1800f7a9e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800f7aa6  inc     ecx
0x1800f7aa8  mov     [rsp+14F0h+var_14C0], ecx
0x1800f7aac  mov     rcx, [rbp+13F0h+arg_38]
0x1800f7ab3  test    rcx, rcx
0x1800f7ab6  jz      short loc_1800F7AC3
0x1800f7ab8  mov     [rsp+14F0h+var_14B8], rcx
0x1800f7abd  cmp     [rcx], r13w
0x1800f7ac1  jnz     short loc_1800F7AC8
0x1800f7ac3  mov     [rsp+14F0h+var_14B8], r13
0x1800f7ac8  call    cs:__imp_GetCurrentThreadId
0x1800f7ace  xorps   xmm0, xmm0
0x1800f7ad1  mov     [rsp+14F0h+var_1498], r14
0x1800f7ad6  mov     [rsp+14F0h+var_14B0], eax
0x1800f7ada  xorps   xmm1, xmm1
0x1800f7add  xor     eax, eax
0x1800f7adf  mov     [rsp+14F0h+var_1490], esi
0x1800f7ae3  mov     [rbp+13F0h+var_1458], rax
0x1800f7ae7  mov     [rbp+13F0h+var_1470], rax
0x1800f7aeb  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800f7af2  mov     [rsp+14F0h+var_148C], r12d
0x1800f7af7  mov     [rsp+14F0h+var_14A8], r13
0x1800f7afc  mov     [rsp+14F0h+var_14A0], r13
0x1800f7b01  mov     [rbp+13F0h+var_1448], r15
0x1800f7b05  mov     [rbp+13F0h+var_1440], rdi
0x1800f7b09  mov     [rsp+14F0h+var_1488], r13
0x1800f7b0e  movups  [rbp+13F0h+var_1468], xmm0
0x1800f7b12  movups  [rsp+14F0h+var_1480], xmm1
0x1800f7b17  test    rax, rax
0x1800f7b1a  jz      short loc_1800F7B27
0x1800f7b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7b21  mov     [rbp+13F0h+var_1450], rax
0x1800f7b25  jmp     short loc_1800F7B2B
0x1800f7b27  mov     [rbp+13F0h+var_1450], r13
0x1800f7b2b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800f7b32  test    rax, rax
0x1800f7b35  jz      short loc_1800F7B41
0x1800f7b37  lea     rcx, [rsp+14F0h+var_14D0]
0x1800f7b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7b41  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800f7b48  test    rax, rax
0x1800f7b4b  jz      short loc_1800F7B61
0x1800f7b4d  mov     r8d, 400h
0x1800f7b53  lea     rdx, [rbp+13F0h+var_1430]
0x1800f7b57  lea     rcx, [rsp+14F0h+var_14D0]
0x1800f7b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7b61  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800f7b68  test    rax, rax
0x1800f7b6b  jz      short loc_1800F7B77
0x1800f7b6d  lea     rcx, [rsp+14F0h+var_14D0]
0x1800f7b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7b77  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800f7b7e  test    rax, rax
0x1800f7b81  jz      short loc_1800F7B94
0x1800f7b83  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800f7b88  jnz     short loc_1800F7B94
0x1800f7b8a  lea     rcx, [rsp+14F0h+var_14D0]
0x1800f7b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7b94  cmp     [rsp+14F0h+var_14C8], r13d
0x1800f7b99  jl      short loc_1800F7BAD
0x1800f7b9b  mov     ecx, 8000FFFFh; this
0x1800f7ba0  mov     [rsp+14F0h+var_14C8], ecx
0x1800f7ba4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800f7ba9  mov     [rsp+14F0h+var_14C4], eax
0x1800f7bad  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800f7bb4  jnz     short loc_1800F7BD5
0x1800f7bb6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800f7bbd  test    rax, rax
0x1800f7bc0  jz      short loc_1800F7BCB
0x1800f7bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7bc7  test    al, al
0x1800f7bc9  jmp     short loc_1800F7BD3
0x1800f7bcb  call    cs:__imp_IsDebuggerPresent
0x1800f7bd1  test    eax, eax
0x1800f7bd3  jz      short loc_1800F7BDC
0x1800f7bd5  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800f7bda  jz      short loc_1800F7C02
0x1800f7bdc  mov     rax, cs:g_pfnResultLoggingCallback
0x1800f7be3  test    rax, rax
0x1800f7be6  jz      short loc_1800F7C56
0x1800f7be8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800f7bef  jnz     short loc_1800F7C56
0x1800f7bf1  xor     r8d, r8d
0x1800f7bf4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800f7bf9  xor     edx, edx
0x1800f7bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7c00  jmp     short loc_1800F7C56
0x1800f7c02  mov     rax, cs:g_pfnResultLoggingCallback
0x1800f7c09  test    rax, rax
0x1800f7c0c  jz      short loc_1800F7C2E
0x1800f7c0e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800f7c15  jnz     short loc_1800F7C2E
0x1800f7c17  mov     r8d, 800h
0x1800f7c1d  lea     rdx, [rbp+13F0h+OutputString]
0x1800f7c24  lea     rcx, [rsp+14F0h+var_14D0]
0x1800f7c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7c2e  cmp     [rbp+13F0h+OutputString], r13w
0x1800f7c36  jnz     short loc_1800F7C49
0x1800f7c38  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800f7c3d  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800f7c44  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800f7c49  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800f7c50  call    cs:__imp_OutputDebugStringW
0x1800f7c56  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800f7c5b  jnz     short loc_1800F7C66
0x1800f7c5d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800f7c64  jz      short loc_1800F7C77
0x1800f7c66  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800f7c6d  test    rax, rax
0x1800f7c70  jz      short loc_1800F7C77
0x1800f7c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7c77  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800f7c7c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
