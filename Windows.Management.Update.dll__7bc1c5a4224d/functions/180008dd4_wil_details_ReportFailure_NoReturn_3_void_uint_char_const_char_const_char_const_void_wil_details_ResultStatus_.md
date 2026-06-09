# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180008dd4`
- end: `0x180009036`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180008b78`

## callees

- `0x1800033e8`
- `0x180008dd4`
- `0x18000b974`
- `0x18000c110`
- `0x18000d190`
- `0x18000f9b0`
- `0x180027600`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008e76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008e76`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009003`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009003`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008f79`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008f79`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
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
0x180008dd4  mov     [rsp-8+arg_18], rbx
0x180008dd9  push    rbp
0x180008dda  push    rsi
0x180008ddb  push    rdi
0x180008ddc  push    r12
0x180008dde  push    r13
0x180008de0  push    r14
0x180008de2  push    r15
0x180008de4  lea     rbp, [rsp-13C0h]
0x180008dec  mov     eax, 14C0h
0x180008df1  call    _alloca_probe
0x180008df6  sub     rsp, rax
0x180008df9  mov     r15, r8
0x180008dfc  mov     r14d, edx
0x180008dff  mov     r12, rcx
0x180008e02  mov     rsi, [rbp+13F0h+arg_28]
0x180008e09  xor     edx, edx; Val
0x180008e0b  mov     r8d, 98h; Size
0x180008e11  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180008e16  call    memset_0
0x180008e1b  nop
0x180008e1c  xor     r13d, r13d
0x180008e1f  mov     [rbp+13F0h+OutputString], r13w
0x180008e27  mov     [rbp+13F0h+var_1430], r13b
0x180008e2b  mov     rbx, [rbp+13F0h+arg_30]
0x180008e32  mov     ecx, [rbx]; this
0x180008e34  mov     [rsp+14F0h+var_14C8], ecx
0x180008e38  mov     eax, [rbx+4]
0x180008e3b  mov     [rsp+14F0h+var_14C4], eax
0x180008e3f  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180008e44  mov     edi, eax
0x180008e46  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180008e4e  mov     ecx, r13d
0x180008e51  lea     eax, [r13+8]
0x180008e55  cmp     dword ptr [rbx+8], 1
0x180008e59  cmovz   ecx, eax
0x180008e5c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180008e60  lea     ecx, [rax-7]
0x180008e63  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008e6b  inc     ecx
0x180008e6d  mov     [rsp+14F0h+var_14C0], ecx
0x180008e71  mov     [rsp+14F0h+var_14B8], r13
0x180008e76  call    cs:__imp_GetCurrentThreadId
0x180008e7c  mov     [rsp+14F0h+var_14B0], eax
0x180008e80  mov     [rsp+14F0h+var_1498], r15
0x180008e85  mov     [rsp+14F0h+var_1490], r14d
0x180008e8a  mov     [rsp+14F0h+var_148C], edi
0x180008e8e  mov     [rsp+14F0h+var_14A8], r13
0x180008e93  mov     [rsp+14F0h+var_14A0], r13
0x180008e98  mov     [rbp+13F0h+var_1448], rsi
0x180008e9c  mov     [rbp+13F0h+var_1440], r12
0x180008ea0  mov     [rsp+14F0h+var_1488], r13
0x180008ea5  xorps   xmm0, xmm0
0x180008ea8  xor     eax, eax
0x180008eaa  movups  [rbp+13F0h+var_1468], xmm0
0x180008eae  mov     [rbp+13F0h+var_1458], rax
0x180008eb2  xorps   xmm1, xmm1
0x180008eb5  movups  [rsp+14F0h+var_1480], xmm1
0x180008eba  mov     [rbp+13F0h+var_1470], rax
0x180008ebe  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008ec5  test    rax, rax
0x180008ec8  jz      short loc_180008ED5
0x180008eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ecf  mov     [rbp+13F0h+var_1450], rax
0x180008ed3  jmp     short loc_180008ED9
0x180008ed5  mov     [rbp+13F0h+var_1450], r13
0x180008ed9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008ee0  test    rax, rax
0x180008ee3  jz      short loc_180008EEF
0x180008ee5  lea     rcx, [rsp+14F0h+var_14D0]
0x180008eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eef  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008ef6  test    rax, rax
0x180008ef9  jz      short loc_180008F0F
0x180008efb  mov     r8d, 400h
0x180008f01  lea     rdx, [rbp+13F0h+var_1430]
0x180008f05  lea     rcx, [rsp+14F0h+var_14D0]
0x180008f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f0f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008f16  test    rax, rax
0x180008f19  jz      short loc_180008F25
0x180008f1b  lea     rcx, [rsp+14F0h+var_14D0]
0x180008f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f25  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008f2c  test    rax, rax
0x180008f2f  jz      short loc_180008F42
0x180008f31  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180008f36  jnz     short loc_180008F42
0x180008f38  lea     rcx, [rsp+14F0h+var_14D0]
0x180008f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f42  cmp     [rsp+14F0h+var_14C8], r13d
0x180008f47  jl      short loc_180008F5B
0x180008f49  mov     ecx, 8000FFFFh; this
0x180008f4e  mov     [rsp+14F0h+var_14C8], ecx
0x180008f52  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008f57  mov     [rsp+14F0h+var_14C4], eax
0x180008f5b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180008f62  jnz     short loc_180008F83
0x180008f64  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008f6b  test    rax, rax
0x180008f6e  jz      short loc_180008F79
0x180008f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f75  test    al, al
0x180008f77  jmp     short loc_180008F81
0x180008f79  call    cs:__imp_IsDebuggerPresent
0x180008f7f  test    eax, eax
0x180008f81  jz      short loc_180008F8A
0x180008f83  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180008f88  jz      short loc_180008FB0
0x180008f8a  mov     rax, cs:g_pfnResultLoggingCallback
0x180008f91  test    rax, rax
0x180008f94  jz      short loc_180009009
0x180008f96  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180008f9d  jnz     short loc_180009009
0x180008f9f  xor     r8d, r8d
0x180008fa2  xor     edx, edx
0x180008fa4  lea     rcx, [rsp+14F0h+var_14D0]
0x180008fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fae  jmp     short loc_180009009
0x180008fb0  mov     ebx, 800h
0x180008fb5  mov     rax, cs:g_pfnResultLoggingCallback
0x180008fbc  test    rax, rax
0x180008fbf  jz      short loc_180008FDE
0x180008fc1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180008fc8  jnz     short loc_180008FDE
0x180008fca  mov     r8d, ebx
0x180008fcd  lea     rdx, [rbp+13F0h+OutputString]
0x180008fd4  lea     rcx, [rsp+14F0h+var_14D0]
0x180008fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fde  cmp     [rbp+13F0h+OutputString], r13w
0x180008fe6  jnz     short loc_180008FFC
0x180008fe8  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180008fed  mov     rdx, rbx; unsigned __int16 *
0x180008ff0  lea     rcx, [rbp+13F0h+OutputString]; this
0x180008ff7  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008ffc  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180009003  call    cs:__imp_OutputDebugStringW
0x180009009  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000900e  jnz     short loc_180009019
0x180009010  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180009017  jz      short loc_18000902B
0x180009019  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009020  test    rax, rax
0x180009023  jz      short loc_18000902B
0x180009025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000902a  nop
0x18000902b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180009030  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
