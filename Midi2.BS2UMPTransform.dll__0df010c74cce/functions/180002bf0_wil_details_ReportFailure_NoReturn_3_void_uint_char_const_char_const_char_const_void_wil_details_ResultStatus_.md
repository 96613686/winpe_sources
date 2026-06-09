# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002bf0`
- end: `0x180002e59`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000299c`

## callees

- `0x1800028c8`
- `0x180002bf0`
- `0x180005204`
- `0x1800059a4`
- `0x180006670`
- `0x180008760`
- `0x18000b390`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002c92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002c92`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002e26`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002e26`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002d9c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002d9c`

## string_xrefs

- `0x180002c9c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180002bf0  mov     [rsp-8+arg_10], rbx
0x180002bf5  mov     [rsp-8+arg_18], rsi
0x180002bfa  push    rbp
0x180002bfb  push    rdi
0x180002bfc  push    r12
0x180002bfe  push    r14
0x180002c00  push    r15
0x180002c02  lea     rbp, [rsp-13C0h]
0x180002c0a  mov     eax, 14C0h
0x180002c0f  call    _alloca_probe
0x180002c14  sub     rsp, rax
0x180002c17  mov     r14d, edx
0x180002c1a  mov     r15, rcx
0x180002c1d  mov     rsi, [rbp+13E0h+arg_28]
0x180002c24  xor     edx, edx; Val
0x180002c26  mov     r8d, 98h; Size
0x180002c2c  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180002c31  call    memset_0
0x180002c36  nop
0x180002c37  xor     r12d, r12d
0x180002c3a  mov     [rbp+13E0h+OutputString], r12w
0x180002c42  mov     [rbp+13E0h+var_1420], r12b
0x180002c46  mov     rbx, [rbp+13E0h+arg_30]
0x180002c4d  mov     ecx, [rbx]; this
0x180002c4f  mov     [rsp+14E0h+var_14B8], ecx
0x180002c53  mov     eax, [rbx+4]
0x180002c56  mov     [rsp+14E0h+var_14B4], eax
0x180002c5a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002c5f  mov     edi, eax
0x180002c61  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180002c69  mov     ecx, r12d
0x180002c6c  lea     eax, [r12+8]
0x180002c71  cmp     dword ptr [rbx+8], 1
0x180002c75  cmovz   ecx, eax
0x180002c78  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180002c7c  lea     ecx, [rax-7]
0x180002c7f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002c87  inc     ecx
0x180002c89  mov     [rsp+14E0h+var_14B0], ecx
0x180002c8d  mov     [rsp+14E0h+var_14A8], r12
0x180002c92  call    cs:__imp_GetCurrentThreadId
0x180002c98  mov     [rsp+14E0h+var_14A0], eax
0x180002c9c  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002ca3  mov     [rsp+14E0h+var_1488], rax
0x180002ca8  mov     [rsp+14E0h+var_1480], r14d
0x180002cad  mov     [rsp+14E0h+var_147C], edi
0x180002cb1  mov     [rsp+14E0h+var_1498], r12
0x180002cb6  mov     [rsp+14E0h+var_1490], r12
0x180002cbb  mov     [rbp+13E0h+var_1438], rsi
0x180002cbf  mov     [rbp+13E0h+var_1430], r15
0x180002cc3  mov     [rsp+14E0h+var_1478], r12
0x180002cc8  xorps   xmm0, xmm0
0x180002ccb  xor     eax, eax
0x180002ccd  movups  [rbp+13E0h+var_1458], xmm0
0x180002cd1  mov     [rbp+13E0h+var_1448], rax
0x180002cd5  xorps   xmm1, xmm1
0x180002cd8  movups  [rsp+14E0h+var_1470], xmm1
0x180002cdd  mov     [rbp+13E0h+var_1460], rax
0x180002ce1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002ce8  test    rax, rax
0x180002ceb  jz      short loc_180002CF8
0x180002ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cf2  mov     [rbp+13E0h+var_1440], rax
0x180002cf6  jmp     short loc_180002CFC
0x180002cf8  mov     [rbp+13E0h+var_1440], r12
0x180002cfc  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002d03  test    rax, rax
0x180002d06  jz      short loc_180002D12
0x180002d08  lea     rcx, [rsp+14E0h+var_14C0]
0x180002d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d12  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002d19  test    rax, rax
0x180002d1c  jz      short loc_180002D32
0x180002d1e  mov     r8d, 400h
0x180002d24  lea     rdx, [rbp+13E0h+var_1420]
0x180002d28  lea     rcx, [rsp+14E0h+var_14C0]
0x180002d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d32  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002d39  test    rax, rax
0x180002d3c  jz      short loc_180002D48
0x180002d3e  lea     rcx, [rsp+14E0h+var_14C0]
0x180002d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d48  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002d4f  test    rax, rax
0x180002d52  jz      short loc_180002D65
0x180002d54  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002d59  jnz     short loc_180002D65
0x180002d5b  lea     rcx, [rsp+14E0h+var_14C0]
0x180002d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d65  cmp     [rsp+14E0h+var_14B8], r12d
0x180002d6a  jl      short loc_180002D7E
0x180002d6c  mov     ecx, 8000FFFFh; this
0x180002d71  mov     [rsp+14E0h+var_14B8], ecx
0x180002d75  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002d7a  mov     [rsp+14E0h+var_14B4], eax
0x180002d7e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002d85  jnz     short loc_180002DA6
0x180002d87  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002d8e  test    rax, rax
0x180002d91  jz      short loc_180002D9C
0x180002d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d98  test    al, al
0x180002d9a  jmp     short loc_180002DA4
0x180002d9c  call    cs:__imp_IsDebuggerPresent
0x180002da2  test    eax, eax
0x180002da4  jz      short loc_180002DAD
0x180002da6  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002dab  jz      short loc_180002DD3
0x180002dad  mov     rax, cs:g_pfnResultLoggingCallback
0x180002db4  test    rax, rax
0x180002db7  jz      short loc_180002E2C
0x180002db9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002dc0  jnz     short loc_180002E2C
0x180002dc2  xor     r8d, r8d
0x180002dc5  xor     edx, edx
0x180002dc7  lea     rcx, [rsp+14E0h+var_14C0]
0x180002dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dd1  jmp     short loc_180002E2C
0x180002dd3  mov     ebx, 800h
0x180002dd8  mov     rax, cs:g_pfnResultLoggingCallback
0x180002ddf  test    rax, rax
0x180002de2  jz      short loc_180002E01
0x180002de4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002deb  jnz     short loc_180002E01
0x180002ded  mov     r8d, ebx
0x180002df0  lea     rdx, [rbp+13E0h+OutputString]
0x180002df7  lea     rcx, [rsp+14E0h+var_14C0]
0x180002dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e01  cmp     [rbp+13E0h+OutputString], r12w
0x180002e09  jnz     short loc_180002E1F
0x180002e0b  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180002e10  mov     rdx, rbx; unsigned __int16 *
0x180002e13  lea     rcx, [rbp+13E0h+OutputString]; this
0x180002e1a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002e1f  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180002e26  call    cs:__imp_OutputDebugStringW
0x180002e2c  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180002e31  jnz     short loc_180002E3C
0x180002e33  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002e3a  jz      short loc_180002E4E
0x180002e3c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002e43  test    rax, rax
0x180002e46  jz      short loc_180002E4E
0x180002e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e4d  nop
0x180002e4e  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180002e53  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
