# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180006cb8`
- end: `0x180006f23`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `619`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002cd8`

## callees

- `0x180001514`
- `0x1800019c0`
- `0x180001c50`
- `0x180002c28`
- `0x180006cb8`
- `0x18000941c`
- `0x180009830`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006d5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006d5a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006e5e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006e5e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006ef0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006ef0`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // edx
  int v11; // edi
  int v12; // ecx
  const struct wil::FailureInfo *v13; // rdx
  __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v15; // r9
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  __int64 v25; // [rsp+58h] [rbp-A8h]
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v18, v10);
  v16 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v17 = v12;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = a3;
  v26 = a2;
  v27 = v11;
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
    ModuleName = wil::details::g_pfnGetModuleName(IsDebuggerPresent);
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
  {
    v18 = -2147418113;
    v19 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v13);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
         (_DWORD)IsDebuggerPresent))
    && (v17 & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v15);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  if ( (v17 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  }
  wil::details::WilFailFast((wil::details *)&v16, v13);
}

```

## disassembly

```asm
0x180006cb8  mov     [rsp-8+arg_18], rbx
0x180006cbd  push    rbp
0x180006cbe  push    rsi
0x180006cbf  push    rdi
0x180006cc0  push    r12
0x180006cc2  push    r13
0x180006cc4  push    r14
0x180006cc6  push    r15
0x180006cc8  lea     rbp, [rsp-13C0h]
0x180006cd0  mov     eax, 14C0h
0x180006cd5  call    _alloca_probe
0x180006cda  sub     rsp, rax
0x180006cdd  mov     r15, r8
0x180006ce0  mov     r14d, edx
0x180006ce3  mov     r12, rcx
0x180006ce6  mov     rsi, [rbp+13F0h+arg_28]
0x180006ced  xor     edx, edx; Val
0x180006cef  mov     r8d, 98h; Size
0x180006cf5  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180006cfa  call    memset_0
0x180006cff  nop
0x180006d00  xor     r13d, r13d
0x180006d03  mov     [rbp+13F0h+OutputString], r13w
0x180006d0b  mov     [rbp+13F0h+var_1430], r13b
0x180006d0f  mov     rbx, [rbp+13F0h+arg_30]
0x180006d16  mov     ecx, [rbx]; this
0x180006d18  mov     [rsp+14F0h+var_14C8], ecx
0x180006d1c  mov     eax, [rbx+4]
0x180006d1f  mov     [rsp+14F0h+var_14C4], eax
0x180006d23  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006d28  mov     edi, eax
0x180006d2a  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180006d32  mov     ecx, r13d
0x180006d35  lea     eax, [r13+8]
0x180006d39  cmp     dword ptr [rbx+8], 1
0x180006d3d  cmovz   ecx, eax
0x180006d40  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180006d44  lea     ecx, [rax-7]
0x180006d47  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006d4f  inc     ecx
0x180006d51  mov     [rsp+14F0h+var_14C0], ecx
0x180006d55  mov     [rsp+14F0h+var_14B8], r13
0x180006d5a  call    cs:__imp_GetCurrentThreadId
0x180006d60  mov     [rsp+14F0h+var_14B0], eax
0x180006d64  mov     [rsp+14F0h+var_1498], r15
0x180006d69  mov     [rsp+14F0h+var_1490], r14d
0x180006d6e  mov     [rsp+14F0h+var_148C], edi
0x180006d72  mov     [rsp+14F0h+var_14A8], r13
0x180006d77  mov     [rsp+14F0h+var_14A0], r13
0x180006d7c  mov     [rbp+13F0h+var_1448], rsi
0x180006d80  mov     [rbp+13F0h+var_1440], r12
0x180006d84  mov     [rsp+14F0h+var_1488], r13
0x180006d89  xorps   xmm0, xmm0
0x180006d8c  xor     eax, eax
0x180006d8e  movups  [rbp+13F0h+var_1468], xmm0
0x180006d92  mov     [rbp+13F0h+var_1458], rax
0x180006d96  xorps   xmm1, xmm1
0x180006d99  movups  [rsp+14F0h+var_1480], xmm1
0x180006d9e  mov     [rbp+13F0h+var_1470], rax
0x180006da2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006da9  test    rax, rax
0x180006dac  jz      short loc_180006DB9
0x180006dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006db3  mov     [rbp+13F0h+var_1450], rax
0x180006db7  jmp     short loc_180006DBD
0x180006db9  mov     [rbp+13F0h+var_1450], r13
0x180006dbd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006dc4  test    rax, rax
0x180006dc7  jz      short loc_180006DD3
0x180006dc9  lea     rcx, [rsp+14F0h+var_14D0]
0x180006dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dd3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006dda  test    rax, rax
0x180006ddd  jz      short loc_180006DF3
0x180006ddf  mov     r8d, 400h
0x180006de5  lea     rdx, [rbp+13F0h+var_1430]
0x180006de9  lea     rcx, [rsp+14F0h+var_14D0]
0x180006dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006df3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006dfa  test    rax, rax
0x180006dfd  jz      short loc_180006E09
0x180006dff  lea     rcx, [rsp+14F0h+var_14D0]
0x180006e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e09  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006e10  test    rax, rax
0x180006e13  jz      short loc_180006E26
0x180006e15  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006e1a  jnz     short loc_180006E26
0x180006e1c  lea     rcx, [rsp+14F0h+var_14D0]
0x180006e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e26  cmp     [rsp+14F0h+var_14C8], r13d
0x180006e2b  jl      short loc_180006E3F
0x180006e2d  mov     ecx, 8000FFFFh; this
0x180006e32  mov     [rsp+14F0h+var_14C8], ecx
0x180006e36  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006e3b  mov     [rsp+14F0h+var_14C4], eax
0x180006e3f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180006e46  jnz     short loc_180006E70
0x180006e48  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006e4f  test    rax, rax
0x180006e52  jz      short loc_180006E5E
0x180006e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e59  movzx   ecx, al
0x180006e5c  jmp     short loc_180006E6C
0x180006e5e  call    cs:__imp_IsDebuggerPresent
0x180006e64  mov     ecx, r13d
0x180006e67  test    eax, eax
0x180006e69  setnz   cl
0x180006e6c  test    ecx, ecx
0x180006e6e  jz      short loc_180006E77
0x180006e70  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006e75  jz      short loc_180006E9D
0x180006e77  mov     rax, cs:g_pfnResultLoggingCallback
0x180006e7e  test    rax, rax
0x180006e81  jz      short loc_180006EF6
0x180006e83  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180006e8a  jnz     short loc_180006EF6
0x180006e8c  xor     r8d, r8d
0x180006e8f  xor     edx, edx
0x180006e91  lea     rcx, [rsp+14F0h+var_14D0]
0x180006e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e9b  jmp     short loc_180006EF6
0x180006e9d  mov     ebx, 800h
0x180006ea2  mov     rax, cs:g_pfnResultLoggingCallback
0x180006ea9  test    rax, rax
0x180006eac  jz      short loc_180006ECB
0x180006eae  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180006eb5  jnz     short loc_180006ECB
0x180006eb7  mov     r8d, ebx
0x180006eba  lea     rdx, [rbp+13F0h+OutputString]
0x180006ec1  lea     rcx, [rsp+14F0h+var_14D0]
0x180006ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ecb  cmp     [rbp+13F0h+OutputString], r13w
0x180006ed3  jnz     short loc_180006EE9
0x180006ed5  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180006eda  mov     rdx, rbx; unsigned __int16 *
0x180006edd  lea     rcx, [rbp+13F0h+OutputString]; this
0x180006ee4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006ee9  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180006ef0  call    cs:__imp_OutputDebugStringW
0x180006ef6  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180006efb  jnz     short loc_180006F06
0x180006efd  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180006f04  jz      short loc_180006F18
0x180006f06  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006f0d  test    rax, rax
0x180006f10  jz      short loc_180006F18
0x180006f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f17  nop
0x180006f18  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180006f1d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
