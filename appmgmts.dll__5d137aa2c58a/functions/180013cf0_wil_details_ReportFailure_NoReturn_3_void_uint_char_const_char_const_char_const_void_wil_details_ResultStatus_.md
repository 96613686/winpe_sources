# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180013cf0`
- end: `0x180013f52`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180013a94`

## callees

- `0x180002024`
- `0x180013cf0`
- `0x180015f74`
- `0x180016710`
- `0x180017300`
- `0x1800194e0`
- `0x18002ad30`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013d92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013d92`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180013f1f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180013f1f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180013e95`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180013e95`

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
0x180013cf0  mov     [rsp-8+arg_18], rbx
0x180013cf5  push    rbp
0x180013cf6  push    rsi
0x180013cf7  push    rdi
0x180013cf8  push    r12
0x180013cfa  push    r13
0x180013cfc  push    r14
0x180013cfe  push    r15
0x180013d00  lea     rbp, [rsp-13C0h]
0x180013d08  mov     eax, 14C0h
0x180013d0d  call    _alloca_probe
0x180013d12  sub     rsp, rax
0x180013d15  mov     r15, r8
0x180013d18  mov     r14d, edx
0x180013d1b  mov     r12, rcx
0x180013d1e  mov     rsi, [rbp+13F0h+arg_28]
0x180013d25  xor     edx, edx; Val
0x180013d27  mov     r8d, 98h; Size
0x180013d2d  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180013d32  call    memset_0
0x180013d37  nop
0x180013d38  xor     r13d, r13d
0x180013d3b  mov     [rbp+13F0h+OutputString], r13w
0x180013d43  mov     [rbp+13F0h+var_1430], r13b
0x180013d47  mov     rbx, [rbp+13F0h+arg_30]
0x180013d4e  mov     ecx, [rbx]; this
0x180013d50  mov     [rsp+14F0h+var_14C8], ecx
0x180013d54  mov     eax, [rbx+4]
0x180013d57  mov     [rsp+14F0h+var_14C4], eax
0x180013d5b  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180013d60  mov     edi, eax
0x180013d62  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180013d6a  mov     ecx, r13d
0x180013d6d  lea     eax, [r13+8]
0x180013d71  cmp     dword ptr [rbx+8], 1
0x180013d75  cmovz   ecx, eax
0x180013d78  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180013d7c  lea     ecx, [rax-7]
0x180013d7f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180013d87  inc     ecx
0x180013d89  mov     [rsp+14F0h+var_14C0], ecx
0x180013d8d  mov     [rsp+14F0h+var_14B8], r13
0x180013d92  call    cs:__imp_GetCurrentThreadId
0x180013d98  mov     [rsp+14F0h+var_14B0], eax
0x180013d9c  mov     [rsp+14F0h+var_1498], r15
0x180013da1  mov     [rsp+14F0h+var_1490], r14d
0x180013da6  mov     [rsp+14F0h+var_148C], edi
0x180013daa  mov     [rsp+14F0h+var_14A8], r13
0x180013daf  mov     [rsp+14F0h+var_14A0], r13
0x180013db4  mov     [rbp+13F0h+var_1448], rsi
0x180013db8  mov     [rbp+13F0h+var_1440], r12
0x180013dbc  mov     [rsp+14F0h+var_1488], r13
0x180013dc1  xorps   xmm0, xmm0
0x180013dc4  xor     eax, eax
0x180013dc6  movups  [rbp+13F0h+var_1468], xmm0
0x180013dca  mov     [rbp+13F0h+var_1458], rax
0x180013dce  xorps   xmm1, xmm1
0x180013dd1  movups  [rsp+14F0h+var_1480], xmm1
0x180013dd6  mov     [rbp+13F0h+var_1470], rax
0x180013dda  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180013de1  test    rax, rax
0x180013de4  jz      short loc_180013DF1
0x180013de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013deb  mov     [rbp+13F0h+var_1450], rax
0x180013def  jmp     short loc_180013DF5
0x180013df1  mov     [rbp+13F0h+var_1450], r13
0x180013df5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180013dfc  test    rax, rax
0x180013dff  jz      short loc_180013E0B
0x180013e01  lea     rcx, [rsp+14F0h+var_14D0]
0x180013e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e0b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180013e12  test    rax, rax
0x180013e15  jz      short loc_180013E2B
0x180013e17  mov     r8d, 400h
0x180013e1d  lea     rdx, [rbp+13F0h+var_1430]
0x180013e21  lea     rcx, [rsp+14F0h+var_14D0]
0x180013e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e2b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180013e32  test    rax, rax
0x180013e35  jz      short loc_180013E41
0x180013e37  lea     rcx, [rsp+14F0h+var_14D0]
0x180013e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e41  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180013e48  test    rax, rax
0x180013e4b  jz      short loc_180013E5E
0x180013e4d  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180013e52  jnz     short loc_180013E5E
0x180013e54  lea     rcx, [rsp+14F0h+var_14D0]
0x180013e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e5e  cmp     [rsp+14F0h+var_14C8], r13d
0x180013e63  jl      short loc_180013E77
0x180013e65  mov     ecx, 8000FFFFh; this
0x180013e6a  mov     [rsp+14F0h+var_14C8], ecx
0x180013e6e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180013e73  mov     [rsp+14F0h+var_14C4], eax
0x180013e77  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180013e7e  jnz     short loc_180013E9F
0x180013e80  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180013e87  test    rax, rax
0x180013e8a  jz      short loc_180013E95
0x180013e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e91  test    al, al
0x180013e93  jmp     short loc_180013E9D
0x180013e95  call    cs:__imp_IsDebuggerPresent
0x180013e9b  test    eax, eax
0x180013e9d  jz      short loc_180013EA6
0x180013e9f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180013ea4  jz      short loc_180013ECC
0x180013ea6  mov     rax, cs:g_pfnResultLoggingCallback
0x180013ead  test    rax, rax
0x180013eb0  jz      short loc_180013F25
0x180013eb2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180013eb9  jnz     short loc_180013F25
0x180013ebb  xor     r8d, r8d
0x180013ebe  xor     edx, edx
0x180013ec0  lea     rcx, [rsp+14F0h+var_14D0]
0x180013ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013eca  jmp     short loc_180013F25
0x180013ecc  mov     ebx, 800h
0x180013ed1  mov     rax, cs:g_pfnResultLoggingCallback
0x180013ed8  test    rax, rax
0x180013edb  jz      short loc_180013EFA
0x180013edd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180013ee4  jnz     short loc_180013EFA
0x180013ee6  mov     r8d, ebx
0x180013ee9  lea     rdx, [rbp+13F0h+OutputString]
0x180013ef0  lea     rcx, [rsp+14F0h+var_14D0]
0x180013ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013efa  cmp     [rbp+13F0h+OutputString], r13w
0x180013f02  jnz     short loc_180013F18
0x180013f04  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180013f09  mov     rdx, rbx; unsigned __int16 *
0x180013f0c  lea     rcx, [rbp+13F0h+OutputString]; this
0x180013f13  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180013f18  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180013f1f  call    cs:__imp_OutputDebugStringW
0x180013f25  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180013f2a  jnz     short loc_180013F35
0x180013f2c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180013f33  jz      short loc_180013F47
0x180013f35  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180013f3c  test    rax, rax
0x180013f3f  jz      short loc_180013F47
0x180013f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f46  nop
0x180013f47  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180013f4c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
