# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180003e68`
- end: `0x1800040d1`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003c14`

## callees

- `0x180003a20`
- `0x180003e68`
- `0x180006474`
- `0x180006c14`
- `0x1800078e0`
- `0x1800099d0`
- `0x180012080`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003f0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003f0a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004014`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004014`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000409e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000409e`

## string_xrefs

- `0x180003f14`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180003e68  mov     [rsp-8+arg_10], rbx
0x180003e6d  mov     [rsp-8+arg_18], rsi
0x180003e72  push    rbp
0x180003e73  push    rdi
0x180003e74  push    r12
0x180003e76  push    r14
0x180003e78  push    r15
0x180003e7a  lea     rbp, [rsp-13C0h]
0x180003e82  mov     eax, 14C0h
0x180003e87  call    _alloca_probe
0x180003e8c  sub     rsp, rax
0x180003e8f  mov     r14d, edx
0x180003e92  mov     r15, rcx
0x180003e95  mov     rsi, [rbp+13E0h+arg_28]
0x180003e9c  xor     edx, edx; Val
0x180003e9e  mov     r8d, 98h; Size
0x180003ea4  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180003ea9  call    memset_0
0x180003eae  nop
0x180003eaf  xor     r12d, r12d
0x180003eb2  mov     [rbp+13E0h+OutputString], r12w
0x180003eba  mov     [rbp+13E0h+var_1420], r12b
0x180003ebe  mov     rbx, [rbp+13E0h+arg_30]
0x180003ec5  mov     ecx, [rbx]; this
0x180003ec7  mov     [rsp+14E0h+var_14B8], ecx
0x180003ecb  mov     eax, [rbx+4]
0x180003ece  mov     [rsp+14E0h+var_14B4], eax
0x180003ed2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003ed7  mov     edi, eax
0x180003ed9  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180003ee1  mov     ecx, r12d
0x180003ee4  lea     eax, [r12+8]
0x180003ee9  cmp     dword ptr [rbx+8], 1
0x180003eed  cmovz   ecx, eax
0x180003ef0  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180003ef4  lea     ecx, [rax-7]
0x180003ef7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003eff  inc     ecx
0x180003f01  mov     [rsp+14E0h+var_14B0], ecx
0x180003f05  mov     [rsp+14E0h+var_14A8], r12
0x180003f0a  call    cs:__imp_GetCurrentThreadId
0x180003f10  mov     [rsp+14E0h+var_14A0], eax
0x180003f14  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003f1b  mov     [rsp+14E0h+var_1488], rax
0x180003f20  mov     [rsp+14E0h+var_1480], r14d
0x180003f25  mov     [rsp+14E0h+var_147C], edi
0x180003f29  mov     [rsp+14E0h+var_1498], r12
0x180003f2e  mov     [rsp+14E0h+var_1490], r12
0x180003f33  mov     [rbp+13E0h+var_1438], rsi
0x180003f37  mov     [rbp+13E0h+var_1430], r15
0x180003f3b  mov     [rsp+14E0h+var_1478], r12
0x180003f40  xorps   xmm0, xmm0
0x180003f43  xor     eax, eax
0x180003f45  movups  [rbp+13E0h+var_1458], xmm0
0x180003f49  mov     [rbp+13E0h+var_1448], rax
0x180003f4d  xorps   xmm1, xmm1
0x180003f50  movups  [rsp+14E0h+var_1470], xmm1
0x180003f55  mov     [rbp+13E0h+var_1460], rax
0x180003f59  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003f60  test    rax, rax
0x180003f63  jz      short loc_180003F70
0x180003f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f6a  mov     [rbp+13E0h+var_1440], rax
0x180003f6e  jmp     short loc_180003F74
0x180003f70  mov     [rbp+13E0h+var_1440], r12
0x180003f74  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003f7b  test    rax, rax
0x180003f7e  jz      short loc_180003F8A
0x180003f80  lea     rcx, [rsp+14E0h+var_14C0]
0x180003f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f8a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003f91  test    rax, rax
0x180003f94  jz      short loc_180003FAA
0x180003f96  mov     r8d, 400h
0x180003f9c  lea     rdx, [rbp+13E0h+var_1420]
0x180003fa0  lea     rcx, [rsp+14E0h+var_14C0]
0x180003fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003faa  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003fb1  test    rax, rax
0x180003fb4  jz      short loc_180003FC0
0x180003fb6  lea     rcx, [rsp+14E0h+var_14C0]
0x180003fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fc0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003fc7  test    rax, rax
0x180003fca  jz      short loc_180003FDD
0x180003fcc  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180003fd1  jnz     short loc_180003FDD
0x180003fd3  lea     rcx, [rsp+14E0h+var_14C0]
0x180003fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fdd  cmp     [rsp+14E0h+var_14B8], r12d
0x180003fe2  jl      short loc_180003FF6
0x180003fe4  mov     ecx, 8000FFFFh; this
0x180003fe9  mov     [rsp+14E0h+var_14B8], ecx
0x180003fed  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003ff2  mov     [rsp+14E0h+var_14B4], eax
0x180003ff6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003ffd  jnz     short loc_18000401E
0x180003fff  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004006  test    rax, rax
0x180004009  jz      short loc_180004014
0x18000400b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004010  test    al, al
0x180004012  jmp     short loc_18000401C
0x180004014  call    cs:__imp_IsDebuggerPresent
0x18000401a  test    eax, eax
0x18000401c  jz      short loc_180004025
0x18000401e  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180004023  jz      short loc_18000404B
0x180004025  mov     rax, cs:g_pfnResultLoggingCallback
0x18000402c  test    rax, rax
0x18000402f  jz      short loc_1800040A4
0x180004031  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004038  jnz     short loc_1800040A4
0x18000403a  xor     r8d, r8d
0x18000403d  xor     edx, edx
0x18000403f  lea     rcx, [rsp+14E0h+var_14C0]
0x180004044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004049  jmp     short loc_1800040A4
0x18000404b  mov     ebx, 800h
0x180004050  mov     rax, cs:g_pfnResultLoggingCallback
0x180004057  test    rax, rax
0x18000405a  jz      short loc_180004079
0x18000405c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004063  jnz     short loc_180004079
0x180004065  mov     r8d, ebx
0x180004068  lea     rdx, [rbp+13E0h+OutputString]
0x18000406f  lea     rcx, [rsp+14E0h+var_14C0]
0x180004074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004079  cmp     [rbp+13E0h+OutputString], r12w
0x180004081  jnz     short loc_180004097
0x180004083  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180004088  mov     rdx, rbx; unsigned __int16 *
0x18000408b  lea     rcx, [rbp+13E0h+OutputString]; this
0x180004092  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004097  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x18000409e  call    cs:__imp_OutputDebugStringW
0x1800040a4  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x1800040a9  jnz     short loc_1800040B4
0x1800040ab  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800040b2  jz      short loc_1800040C6
0x1800040b4  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800040bb  test    rax, rax
0x1800040be  jz      short loc_1800040C6
0x1800040c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040c5  nop
0x1800040c6  lea     rcx, [rsp+14E0h+var_14C0]; this
0x1800040cb  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
