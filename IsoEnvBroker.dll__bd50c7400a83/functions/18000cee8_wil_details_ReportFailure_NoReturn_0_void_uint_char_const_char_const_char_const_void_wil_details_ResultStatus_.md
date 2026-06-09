# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x18000cee8`
- end: `0x18000d194`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000ce60`

## callees

- `0x1800030d0`
- `0x180007be4`
- `0x180009390`
- `0x18000b398`
- `0x18000bb10`
- `0x18000bd88`
- `0x18000cee8`
- `0x180064360`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cf91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cf91`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d08c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d08c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d128`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d128`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v10; // r12
  int v11; // ebx
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  char v18; // bl
  const struct wil::FailureInfo *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v10 = g_pfnThrowPlatformException != 0;
  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v11 = wil::details::RecordException((wil::details *)(unsigned int)v22, (int)a7);
  v20 = 0;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v21 = v12;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v11;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && !v10 && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v18 = 1, (v21 & 2) != 0) )
  {
    v18 = 0;
  }
  if ( v10 || v18 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v14);
  if ( v10 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v20, OutputString);
  wil::ThrowResultException((wil *)&v20, v14);
  wil::details::WilFailFast((wil::details *)&v20, v19);
}

```

## disassembly

```asm
0x18000cee8  mov     [rsp-8+arg_18], rbx
0x18000ceed  push    rbp
0x18000ceee  push    rsi
0x18000ceef  push    rdi
0x18000cef0  push    r12
0x18000cef2  push    r13
0x18000cef4  push    r14
0x18000cef6  push    r15
0x18000cef8  lea     rbp, [rsp-13C0h]
0x18000cf00  mov     eax, 14C0h
0x18000cf05  call    _alloca_probe
0x18000cf0a  sub     rsp, rax
0x18000cf0d  mov     r14, r8
0x18000cf10  mov     esi, edx
0x18000cf12  mov     r15, rcx
0x18000cf15  mov     rdi, [rbp+13F0h+arg_28]
0x18000cf1c  xor     r13d, r13d
0x18000cf1f  cmp     cs:g_pfnThrowPlatformException, r13
0x18000cf26  setnz   r12b
0x18000cf2a  xor     edx, edx; Val
0x18000cf2c  mov     r8d, 98h; Size
0x18000cf32  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000cf37  call    memset_0
0x18000cf3c  nop
0x18000cf3d  mov     [rbp+13F0h+OutputString], r13w
0x18000cf45  mov     [rbp+13F0h+var_1430], r13b
0x18000cf49  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000cf50  mov     ecx, [rdx]; this
0x18000cf52  mov     [rsp+14F0h+var_14C8], ecx
0x18000cf56  mov     eax, [rdx+4]
0x18000cf59  mov     [rsp+14F0h+var_14C4], eax
0x18000cf5d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000cf62  mov     ebx, eax
0x18000cf64  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000cf69  mov     ecx, r13d
0x18000cf6c  lea     eax, [r13+8]
0x18000cf70  cmp     dword ptr [rdx+8], 1
0x18000cf74  cmovz   ecx, eax
0x18000cf77  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000cf7b  lea     ecx, [rax-7]
0x18000cf7e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000cf86  inc     ecx
0x18000cf88  mov     [rsp+14F0h+var_14C0], ecx
0x18000cf8c  mov     [rsp+14F0h+var_14B8], r13
0x18000cf91  call    cs:__imp_GetCurrentThreadId
0x18000cf97  mov     [rsp+14F0h+var_14B0], eax
0x18000cf9b  mov     [rsp+14F0h+var_1498], r14
0x18000cfa0  mov     [rsp+14F0h+var_1490], esi
0x18000cfa4  mov     [rsp+14F0h+var_148C], ebx
0x18000cfa8  mov     [rsp+14F0h+var_14A8], r13
0x18000cfad  mov     [rsp+14F0h+var_14A0], r13
0x18000cfb2  mov     [rbp+13F0h+var_1448], rdi
0x18000cfb6  mov     [rbp+13F0h+var_1440], r15
0x18000cfba  mov     [rsp+14F0h+var_1488], r13
0x18000cfbf  xorps   xmm0, xmm0
0x18000cfc2  xor     eax, eax
0x18000cfc4  movups  [rbp+13F0h+var_1468], xmm0
0x18000cfc8  mov     [rbp+13F0h+var_1458], rax
0x18000cfcc  xorps   xmm1, xmm1
0x18000cfcf  movups  [rsp+14F0h+var_1480], xmm1
0x18000cfd4  mov     [rbp+13F0h+var_1470], rax
0x18000cfd8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000cfdf  test    rax, rax
0x18000cfe2  jz      short loc_18000CFEF
0x18000cfe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfe9  mov     [rbp+13F0h+var_1450], rax
0x18000cfed  jmp     short loc_18000CFF3
0x18000cfef  mov     [rbp+13F0h+var_1450], r13
0x18000cff3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000cffa  test    rax, rax
0x18000cffd  jz      short loc_18000D009
0x18000cfff  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d009  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000d010  test    rax, rax
0x18000d013  jz      short loc_18000D029
0x18000d015  mov     r8d, 400h
0x18000d01b  lea     rdx, [rbp+13F0h+var_1430]
0x18000d01f  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d029  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d030  test    rax, rax
0x18000d033  jz      short loc_18000D03F
0x18000d035  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d03a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d03f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d046  test    rax, rax
0x18000d049  jz      short loc_18000D061
0x18000d04b  test    r12b, r12b
0x18000d04e  jnz     short loc_18000D061
0x18000d050  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000d055  jnz     short loc_18000D061
0x18000d057  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d05c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d061  cmp     [rsp+14F0h+var_14C8], r13d
0x18000d066  jl      short loc_18000D06E
0x18000d068  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000d06e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000d075  jnz     short loc_18000D096
0x18000d077  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000d07e  test    rax, rax
0x18000d081  jz      short loc_18000D08C
0x18000d083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d088  test    al, al
0x18000d08a  jmp     short loc_18000D094
0x18000d08c  call    cs:__imp_IsDebuggerPresent
0x18000d092  test    eax, eax
0x18000d094  jz      short loc_18000D09F
0x18000d096  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000d09b  mov     bl, 1
0x18000d09d  jz      short loc_18000D0A2
0x18000d09f  mov     bl, r13b
0x18000d0a2  test    r12b, r12b
0x18000d0a5  jnz     short loc_18000D0D1
0x18000d0a7  test    bl, bl
0x18000d0a9  jnz     short loc_18000D0D1
0x18000d0ab  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d0b2  test    rax, rax
0x18000d0b5  jz      short loc_18000D12E
0x18000d0b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000d0be  jnz     short loc_18000D12E
0x18000d0c0  xor     r8d, r8d
0x18000d0c3  xor     edx, edx
0x18000d0c5  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d0ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0cf  jmp     short loc_18000D12E
0x18000d0d1  mov     edi, 800h
0x18000d0d6  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d0dd  test    rax, rax
0x18000d0e0  jz      short loc_18000D0FF
0x18000d0e2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000d0e9  jnz     short loc_18000D0FF
0x18000d0eb  mov     r8d, edi
0x18000d0ee  lea     rdx, [rbp+13F0h+OutputString]
0x18000d0f5  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d0fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0ff  cmp     [rbp+13F0h+OutputString], r13w
0x18000d107  jnz     short loc_18000D11D
0x18000d109  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000d10e  mov     rdx, rdi; wchar_t *
0x18000d111  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000d118  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000d11d  test    bl, bl
0x18000d11f  jz      short loc_18000D12E
0x18000d121  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000d128  call    cs:__imp_OutputDebugStringW
0x18000d12e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000d133  jnz     short loc_18000D13E
0x18000d135  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000d13c  jz      short loc_18000D150
0x18000d13e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000d145  test    rax, rax
0x18000d148  jz      short loc_18000D150
0x18000d14a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d14f  nop
0x18000d150  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000d155  jz      short loc_18000D162
0x18000d157  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000d15c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000d162  test    r12b, r12b
0x18000d165  jz      short loc_18000D17F
0x18000d167  lea     rdx, [rbp+13F0h+OutputString]
0x18000d16e  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d173  mov     rax, cs:g_pfnThrowPlatformException
0x18000d17a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d17f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000d184  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000d189  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000d18e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
