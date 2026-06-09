# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x140006dd8`
- end: `0x14000703a`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140006b7c`

## callees

- `0x1400050e0`
- `0x140006dd8`
- `0x14000c664`
- `0x14000df30`
- `0x140011130`
- `0x140013a20`
- `0x140065be0`
- `0x14006a010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140006f7d`
- `KERNEL32!IsDebuggerPresent` at `0x140006f7d`
- `KERNEL32!OutputDebugStringW` at `0x140007007`
- `KERNEL32!OutputDebugStringW` at `0x140007007`
- `KERNEL32!GetCurrentThreadId` at `0x140006e7a`
- `KERNEL32!GetCurrentThreadId` at `0x140006e7a`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
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
  __int64 v14; // rcx
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v19, v10);
  v17 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v18 = v12;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v11;
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
  {
    v19 = -2147418113;
    v20 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v13);
  }
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
  if ( (v18 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v14);
  }
  wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x140006dd8  mov     [rsp-8+arg_18], rbx
0x140006ddd  push    rbp
0x140006dde  push    rsi
0x140006ddf  push    rdi
0x140006de0  push    r12
0x140006de2  push    r13
0x140006de4  push    r14
0x140006de6  push    r15
0x140006de8  lea     rbp, [rsp-13C0h]
0x140006df0  mov     eax, 14C0h
0x140006df5  call    _alloca_probe
0x140006dfa  sub     rsp, rax
0x140006dfd  mov     r15, r8
0x140006e00  mov     r14d, edx
0x140006e03  mov     r12, rcx
0x140006e06  mov     rsi, [rbp+13F0h+arg_28]
0x140006e0d  xor     edx, edx; Val
0x140006e0f  mov     r8d, 98h; Size
0x140006e15  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140006e1a  call    memset_0
0x140006e1f  nop
0x140006e20  xor     r13d, r13d
0x140006e23  mov     [rbp+13F0h+OutputString], r13w
0x140006e2b  mov     [rbp+13F0h+var_1430], r13b
0x140006e2f  mov     rbx, [rbp+13F0h+arg_30]
0x140006e36  mov     ecx, [rbx]; this
0x140006e38  mov     [rsp+14F0h+var_14C8], ecx
0x140006e3c  mov     eax, [rbx+4]
0x140006e3f  mov     [rsp+14F0h+var_14C4], eax
0x140006e43  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140006e48  mov     edi, eax
0x140006e4a  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x140006e52  mov     ecx, r13d
0x140006e55  lea     eax, [r13+8]
0x140006e59  cmp     dword ptr [rbx+8], 1
0x140006e5d  cmovz   ecx, eax
0x140006e60  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140006e64  lea     ecx, [rax-7]
0x140006e67  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140006e6f  inc     ecx
0x140006e71  mov     [rsp+14F0h+var_14C0], ecx
0x140006e75  mov     [rsp+14F0h+var_14B8], r13
0x140006e7a  call    cs:__imp_GetCurrentThreadId
0x140006e80  mov     [rsp+14F0h+var_14B0], eax
0x140006e84  mov     [rsp+14F0h+var_1498], r15
0x140006e89  mov     [rsp+14F0h+var_1490], r14d
0x140006e8e  mov     [rsp+14F0h+var_148C], edi
0x140006e92  mov     [rsp+14F0h+var_14A8], r13
0x140006e97  mov     [rsp+14F0h+var_14A0], r13
0x140006e9c  mov     [rbp+13F0h+var_1448], rsi
0x140006ea0  mov     [rbp+13F0h+var_1440], r12
0x140006ea4  mov     [rsp+14F0h+var_1488], r13
0x140006ea9  xorps   xmm0, xmm0
0x140006eac  xor     eax, eax
0x140006eae  movups  [rbp+13F0h+var_1468], xmm0
0x140006eb2  mov     [rbp+13F0h+var_1458], rax
0x140006eb6  xorps   xmm1, xmm1
0x140006eb9  movups  [rsp+14F0h+var_1480], xmm1
0x140006ebe  mov     [rbp+13F0h+var_1470], rax
0x140006ec2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140006ec9  test    rax, rax
0x140006ecc  jz      short loc_140006ED9
0x140006ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ed3  mov     [rbp+13F0h+var_1450], rax
0x140006ed7  jmp     short loc_140006EDD
0x140006ed9  mov     [rbp+13F0h+var_1450], r13
0x140006edd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140006ee4  test    rax, rax
0x140006ee7  jz      short loc_140006EF3
0x140006ee9  lea     rcx, [rsp+14F0h+var_14D0]
0x140006eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ef3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140006efa  test    rax, rax
0x140006efd  jz      short loc_140006F13
0x140006eff  mov     r8d, 400h
0x140006f05  lea     rdx, [rbp+13F0h+var_1430]
0x140006f09  lea     rcx, [rsp+14F0h+var_14D0]
0x140006f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f13  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006f1a  test    rax, rax
0x140006f1d  jz      short loc_140006F29
0x140006f1f  lea     rcx, [rsp+14F0h+var_14D0]
0x140006f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f29  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006f30  test    rax, rax
0x140006f33  jz      short loc_140006F46
0x140006f35  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140006f3a  jnz     short loc_140006F46
0x140006f3c  lea     rcx, [rsp+14F0h+var_14D0]
0x140006f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f46  cmp     [rsp+14F0h+var_14C8], r13d
0x140006f4b  jl      short loc_140006F5F
0x140006f4d  mov     ecx, 8000FFFFh; this
0x140006f52  mov     [rsp+14F0h+var_14C8], ecx
0x140006f56  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140006f5b  mov     [rsp+14F0h+var_14C4], eax
0x140006f5f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140006f66  jnz     short loc_140006F87
0x140006f68  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140006f6f  test    rax, rax
0x140006f72  jz      short loc_140006F7D
0x140006f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f79  test    al, al
0x140006f7b  jmp     short loc_140006F85
0x140006f7d  call    cs:__imp_IsDebuggerPresent
0x140006f83  test    eax, eax
0x140006f85  jz      short loc_140006F8E
0x140006f87  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140006f8c  jz      short loc_140006FB4
0x140006f8e  mov     rax, cs:g_pfnResultLoggingCallback
0x140006f95  test    rax, rax
0x140006f98  jz      short loc_14000700D
0x140006f9a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140006fa1  jnz     short loc_14000700D
0x140006fa3  xor     r8d, r8d
0x140006fa6  xor     edx, edx
0x140006fa8  lea     rcx, [rsp+14F0h+var_14D0]
0x140006fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006fb2  jmp     short loc_14000700D
0x140006fb4  mov     ebx, 800h
0x140006fb9  mov     rax, cs:g_pfnResultLoggingCallback
0x140006fc0  test    rax, rax
0x140006fc3  jz      short loc_140006FE2
0x140006fc5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140006fcc  jnz     short loc_140006FE2
0x140006fce  mov     r8d, ebx
0x140006fd1  lea     rdx, [rbp+13F0h+OutputString]
0x140006fd8  lea     rcx, [rsp+14F0h+var_14D0]
0x140006fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006fe2  cmp     [rbp+13F0h+OutputString], r13w
0x140006fea  jnz     short loc_140007000
0x140006fec  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140006ff1  mov     rdx, rbx; wchar_t *
0x140006ff4  lea     rcx, [rbp+13F0h+OutputString]; Buffer
0x140006ffb  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140007000  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140007007  call    cs:__imp_OutputDebugStringW
0x14000700d  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140007012  jnz     short loc_14000701D
0x140007014  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x14000701b  jz      short loc_14000702F
0x14000701d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140007024  test    rax, rax
0x140007027  jz      short loc_14000702F
0x140007029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000702e  nop
0x14000702f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140007034  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
