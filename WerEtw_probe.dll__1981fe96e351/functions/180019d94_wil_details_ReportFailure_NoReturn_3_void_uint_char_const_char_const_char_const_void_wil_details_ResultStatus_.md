# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180019d94`
- end: `0x180019ffd`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180019b48`

## callees

- `0x180002420`
- `0x180019d94`
- `0x18001cc84`
- `0x18001d420`
- `0x18001e530`
- `0x18001f810`
- `0x180027b80`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019e36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019e36`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180019f40`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180019f40`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180019fca`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180019fca`

## string_xrefs

- `0x180019e40`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // edx
  int v10; // edi
  int v11; // ecx
  const struct wil::FailureInfo *v12; // rdx
  __int64 v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
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
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v10 = wil::details::RecordFailFast((wil::details *)(unsigned int)v18, v9);
  v16 = 3;
  v11 = 0;
  if ( a7[2] == 1 )
    v11 = 8;
  v17 = v11;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
  v26 = a2;
  v27 = v10;
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
    ModuleName = wil::details::g_pfnGetModuleName(v13);
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
    v19 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v12);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( (v17 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v13);
  }
  wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x180019d94  mov     [rsp-8+arg_10], rbx
0x180019d99  mov     [rsp-8+arg_18], rsi
0x180019d9e  push    rbp
0x180019d9f  push    rdi
0x180019da0  push    r12
0x180019da2  push    r14
0x180019da4  push    r15
0x180019da6  lea     rbp, [rsp-13C0h]
0x180019dae  mov     eax, 14C0h
0x180019db3  call    _alloca_probe
0x180019db8  sub     rsp, rax
0x180019dbb  mov     r14d, edx
0x180019dbe  mov     r15, rcx
0x180019dc1  mov     rsi, [rbp+13E0h+arg_28]
0x180019dc8  xor     edx, edx; Val
0x180019dca  mov     r8d, 98h; Size
0x180019dd0  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180019dd5  call    memset_0
0x180019dda  nop
0x180019ddb  xor     r12d, r12d
0x180019dde  mov     [rbp+13E0h+OutputString], r12w
0x180019de6  mov     [rbp+13E0h+var_1420], r12b
0x180019dea  mov     rbx, [rbp+13E0h+arg_30]
0x180019df1  mov     ecx, [rbx]; this
0x180019df3  mov     [rsp+14E0h+var_14B8], ecx
0x180019df7  mov     eax, [rbx+4]
0x180019dfa  mov     [rsp+14E0h+var_14B4], eax
0x180019dfe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180019e03  mov     edi, eax
0x180019e05  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180019e0d  mov     ecx, r12d
0x180019e10  lea     eax, [r12+8]
0x180019e15  cmp     dword ptr [rbx+8], 1
0x180019e19  cmovz   ecx, eax
0x180019e1c  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180019e20  lea     ecx, [rax-7]
0x180019e23  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180019e2b  inc     ecx
0x180019e2d  mov     [rsp+14E0h+var_14B0], ecx
0x180019e31  mov     [rsp+14E0h+var_14A8], r12
0x180019e36  call    cs:__imp_GetCurrentThreadId
0x180019e3c  mov     [rsp+14E0h+var_14A0], eax
0x180019e40  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180019e47  mov     [rsp+14E0h+var_1488], rax
0x180019e4c  mov     [rsp+14E0h+var_1480], r14d
0x180019e51  mov     [rsp+14E0h+var_147C], edi
0x180019e55  mov     [rsp+14E0h+var_1498], r12
0x180019e5a  mov     [rsp+14E0h+var_1490], r12
0x180019e5f  mov     [rbp+13E0h+var_1438], rsi
0x180019e63  mov     [rbp+13E0h+var_1430], r15
0x180019e67  mov     [rsp+14E0h+var_1478], r12
0x180019e6c  xorps   xmm0, xmm0
0x180019e6f  xor     eax, eax
0x180019e71  movups  [rbp+13E0h+var_1458], xmm0
0x180019e75  mov     [rbp+13E0h+var_1448], rax
0x180019e79  xorps   xmm1, xmm1
0x180019e7c  movups  [rsp+14E0h+var_1470], xmm1
0x180019e81  mov     [rbp+13E0h+var_1460], rax
0x180019e85  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180019e8c  test    rax, rax
0x180019e8f  jz      short loc_180019E9C
0x180019e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e96  mov     [rbp+13E0h+var_1440], rax
0x180019e9a  jmp     short loc_180019EA0
0x180019e9c  mov     [rbp+13E0h+var_1440], r12
0x180019ea0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180019ea7  test    rax, rax
0x180019eaa  jz      short loc_180019EB6
0x180019eac  lea     rcx, [rsp+14E0h+var_14C0]
0x180019eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019eb6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180019ebd  test    rax, rax
0x180019ec0  jz      short loc_180019ED6
0x180019ec2  mov     r8d, 400h
0x180019ec8  lea     rdx, [rbp+13E0h+var_1420]
0x180019ecc  lea     rcx, [rsp+14E0h+var_14C0]
0x180019ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ed6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180019edd  test    rax, rax
0x180019ee0  jz      short loc_180019EEC
0x180019ee2  lea     rcx, [rsp+14E0h+var_14C0]
0x180019ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019eec  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180019ef3  test    rax, rax
0x180019ef6  jz      short loc_180019F09
0x180019ef8  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180019efd  jnz     short loc_180019F09
0x180019eff  lea     rcx, [rsp+14E0h+var_14C0]
0x180019f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f09  cmp     [rsp+14E0h+var_14B8], r12d
0x180019f0e  jl      short loc_180019F22
0x180019f10  mov     ecx, 8000FFFFh; this
0x180019f15  mov     [rsp+14E0h+var_14B8], ecx
0x180019f19  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180019f1e  mov     [rsp+14E0h+var_14B4], eax
0x180019f22  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180019f29  jnz     short loc_180019F4A
0x180019f2b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180019f32  test    rax, rax
0x180019f35  jz      short loc_180019F40
0x180019f37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f3c  test    al, al
0x180019f3e  jmp     short loc_180019F48
0x180019f40  call    cs:__imp_IsDebuggerPresent
0x180019f46  test    eax, eax
0x180019f48  jz      short loc_180019F51
0x180019f4a  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180019f4f  jz      short loc_180019F77
0x180019f51  mov     rax, cs:g_pfnResultLoggingCallback
0x180019f58  test    rax, rax
0x180019f5b  jz      short loc_180019FD0
0x180019f5d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180019f64  jnz     short loc_180019FD0
0x180019f66  xor     r8d, r8d
0x180019f69  xor     edx, edx
0x180019f6b  lea     rcx, [rsp+14E0h+var_14C0]
0x180019f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f75  jmp     short loc_180019FD0
0x180019f77  mov     ebx, 800h
0x180019f7c  mov     rax, cs:g_pfnResultLoggingCallback
0x180019f83  test    rax, rax
0x180019f86  jz      short loc_180019FA5
0x180019f88  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180019f8f  jnz     short loc_180019FA5
0x180019f91  mov     r8d, ebx
0x180019f94  lea     rdx, [rbp+13E0h+OutputString]
0x180019f9b  lea     rcx, [rsp+14E0h+var_14C0]
0x180019fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fa5  cmp     [rbp+13E0h+OutputString], r12w
0x180019fad  jnz     short loc_180019FC3
0x180019faf  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180019fb4  mov     rdx, rbx; unsigned __int16 *
0x180019fb7  lea     rcx, [rbp+13E0h+OutputString]; this
0x180019fbe  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180019fc3  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180019fca  call    cs:__imp_OutputDebugStringW
0x180019fd0  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180019fd5  jnz     short loc_180019FE0
0x180019fd7  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180019fde  jz      short loc_180019FF2
0x180019fe0  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180019fe7  test    rax, rax
0x180019fea  jz      short loc_180019FF2
0x180019fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ff1  nop
0x180019ff2  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180019ff7  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
