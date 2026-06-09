# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180001d60`
- end: `0x180001fbd`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `605`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180001c94`

## callees

- `0x180001d60`
- `0x1800024c4`
- `0x1800028ac`
- `0x180002c10`
- `0x1800038f0`
- `0x1800040f6`
- `0x1800041c0`
- `0x180005010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001df4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001df4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180001f8b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180001f8b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180001f01`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180001f01`

## string_xrefs

- `0x180001e0c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7)
{
  int v8; // eax
  int v9; // edx
  int v10; // eax
  int v11; // edi
  int v12; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  __int64 v23; // [rsp+38h] [rbp-C8h]
  DWORD v24; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  const char *v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v8 = a7[1];
  v20 = *a7;
  v21 = v8;
  v10 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v9);
  v17 = a7[2] == 1;
  v11 = v10;
  v18 = 3;
  v12 = 0;
  if ( v17 )
    v12 = 8;
  v19 = v12;
  v23 = 0;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v28 = 3977;
  v24 = CurrentThreadId;
  v29 = v11;
  v27 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
  v34 = 0;
  v32 = 0;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180001d60  push    rbp
0x180001d62  push    rbx
0x180001d63  push    rsi
0x180001d64  push    rdi
0x180001d65  push    r14
0x180001d67  push    r15
0x180001d69  lea     rbp, [rsp-13C8h]
0x180001d71  mov     eax, 14C8h
0x180001d76  call    _alloca_probe
0x180001d7b  sub     rsp, rax
0x180001d7e  mov     rsi, [rbp+13F0h+arg_28]
0x180001d85  mov     r14, rcx
0x180001d88  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180001d8d  xor     edx, edx; Val
0x180001d8f  mov     r8d, 98h; Size
0x180001d95  call    memset_0
0x180001d9a  mov     rbx, [rbp+13F0h+arg_30]
0x180001da1  xor     r15d, r15d
0x180001da4  mov     [rbp+13F0h+OutputString], r15w
0x180001dac  mov     [rbp+13F0h+var_1430], r15b
0x180001db0  mov     ecx, [rbx]; this
0x180001db2  mov     eax, [rbx+4]
0x180001db5  mov     [rsp+14F0h+var_14C8], ecx
0x180001db9  mov     [rsp+14F0h+var_14C4], eax
0x180001dbd  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180001dc2  cmp     dword ptr [rbx+8], 1
0x180001dc6  mov     edi, eax
0x180001dc8  lea     eax, [r15+8]
0x180001dcc  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180001dd4  mov     ecx, r15d
0x180001dd7  cmovz   ecx, eax
0x180001dda  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180001dde  lea     ecx, [rax-7]
0x180001de1  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180001de9  inc     ecx
0x180001deb  mov     [rsp+14F0h+var_14B8], r15
0x180001df0  mov     [rsp+14F0h+var_14C0], ecx
0x180001df4  call    cs:__imp_GetCurrentThreadId
0x180001dfa  xorps   xmm0, xmm0
0x180001dfd  mov     [rsp+14F0h+var_1490], 0F89h
0x180001e05  mov     [rsp+14F0h+var_14B0], eax
0x180001e09  xorps   xmm1, xmm1
0x180001e0c  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180001e13  mov     [rsp+14F0h+var_148C], edi
0x180001e17  mov     [rsp+14F0h+var_1498], rax
0x180001e1c  xor     eax, eax
0x180001e1e  mov     [rbp+13F0h+var_1458], rax
0x180001e22  mov     [rbp+13F0h+var_1470], rax
0x180001e26  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180001e2d  mov     [rsp+14F0h+var_14A8], r15
0x180001e32  mov     [rsp+14F0h+var_14A0], r15
0x180001e37  mov     [rbp+13F0h+var_1448], rsi
0x180001e3b  mov     [rbp+13F0h+var_1440], r14
0x180001e3f  mov     [rsp+14F0h+var_1488], r15
0x180001e44  movups  [rbp+13F0h+var_1468], xmm0
0x180001e48  movups  [rsp+14F0h+var_1480], xmm1
0x180001e4d  test    rax, rax
0x180001e50  jz      short loc_180001E5D
0x180001e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e57  mov     [rbp+13F0h+var_1450], rax
0x180001e5b  jmp     short loc_180001E61
0x180001e5d  mov     [rbp+13F0h+var_1450], r15
0x180001e61  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180001e68  test    rax, rax
0x180001e6b  jz      short loc_180001E77
0x180001e6d  lea     rcx, [rsp+14F0h+var_14D0]
0x180001e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e77  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180001e7e  test    rax, rax
0x180001e81  jz      short loc_180001E97
0x180001e83  mov     r8d, 400h
0x180001e89  lea     rdx, [rbp+13F0h+var_1430]
0x180001e8d  lea     rcx, [rsp+14F0h+var_14D0]
0x180001e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e97  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180001e9e  test    rax, rax
0x180001ea1  jz      short loc_180001EAD
0x180001ea3  lea     rcx, [rsp+14F0h+var_14D0]
0x180001ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ead  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180001eb4  test    rax, rax
0x180001eb7  jz      short loc_180001ECA
0x180001eb9  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180001ebe  jnz     short loc_180001ECA
0x180001ec0  lea     rcx, [rsp+14F0h+var_14D0]
0x180001ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001eca  cmp     [rsp+14F0h+var_14C8], r15d
0x180001ecf  jl      short loc_180001EE3
0x180001ed1  mov     ecx, 8000FFFFh; this
0x180001ed6  mov     [rsp+14F0h+var_14C8], ecx
0x180001eda  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180001edf  mov     [rsp+14F0h+var_14C4], eax
0x180001ee3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180001eea  jnz     short loc_180001F0B
0x180001eec  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180001ef3  test    rax, rax
0x180001ef6  jz      short loc_180001F01
0x180001ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001efd  test    al, al
0x180001eff  jmp     short loc_180001F09
0x180001f01  call    cs:__imp_IsDebuggerPresent
0x180001f07  test    eax, eax
0x180001f09  jz      short loc_180001F12
0x180001f0b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180001f10  jz      short loc_180001F38
0x180001f12  mov     rax, cs:g_pfnResultLoggingCallback
0x180001f19  test    rax, rax
0x180001f1c  jz      short loc_180001F91
0x180001f1e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180001f25  jnz     short loc_180001F91
0x180001f27  xor     r8d, r8d
0x180001f2a  lea     rcx, [rsp+14F0h+var_14D0]
0x180001f2f  xor     edx, edx
0x180001f31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f36  jmp     short loc_180001F91
0x180001f38  mov     rax, cs:g_pfnResultLoggingCallback
0x180001f3f  mov     ebx, 800h
0x180001f44  test    rax, rax
0x180001f47  jz      short loc_180001F66
0x180001f49  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180001f50  jnz     short loc_180001F66
0x180001f52  mov     r8d, ebx
0x180001f55  lea     rdx, [rbp+13F0h+OutputString]
0x180001f5c  lea     rcx, [rsp+14F0h+var_14D0]
0x180001f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f66  cmp     [rbp+13F0h+OutputString], r15w
0x180001f6e  jnz     short loc_180001F84
0x180001f70  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180001f75  mov     rdx, rbx; unsigned __int16 *
0x180001f78  lea     rcx, [rbp+13F0h+OutputString]; this
0x180001f7f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180001f84  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180001f8b  call    cs:__imp_OutputDebugStringW
0x180001f91  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180001f96  jnz     short loc_180001FA1
0x180001f98  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180001f9f  jz      short loc_180001FB2
0x180001fa1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180001fa8  test    rax, rax
0x180001fab  jz      short loc_180001FB2
0x180001fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fb2  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180001fb7  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
