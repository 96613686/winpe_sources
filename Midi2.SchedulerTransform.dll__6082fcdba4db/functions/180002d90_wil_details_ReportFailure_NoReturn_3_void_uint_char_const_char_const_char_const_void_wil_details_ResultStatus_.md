# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002d90`
- end: `0x180002ff9`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002b3c`

## callees

- `0x180002a68`
- `0x180002d90`
- `0x1800053a4`
- `0x180005b44`
- `0x180006810`
- `0x180008910`
- `0x18000cc00`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002e32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002e32`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002fc6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002fc6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002f3c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002f3c`

## string_xrefs

- `0x180002e3c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180002d90  mov     [rsp-8+arg_10], rbx
0x180002d95  mov     [rsp-8+arg_18], rsi
0x180002d9a  push    rbp
0x180002d9b  push    rdi
0x180002d9c  push    r12
0x180002d9e  push    r14
0x180002da0  push    r15
0x180002da2  lea     rbp, [rsp-13C0h]
0x180002daa  mov     eax, 14C0h
0x180002daf  call    _alloca_probe
0x180002db4  sub     rsp, rax
0x180002db7  mov     r14d, edx
0x180002dba  mov     r15, rcx
0x180002dbd  mov     rsi, [rbp+13E0h+arg_28]
0x180002dc4  xor     edx, edx; Val
0x180002dc6  mov     r8d, 98h; Size
0x180002dcc  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180002dd1  call    memset_0
0x180002dd6  nop
0x180002dd7  xor     r12d, r12d
0x180002dda  mov     [rbp+13E0h+OutputString], r12w
0x180002de2  mov     [rbp+13E0h+var_1420], r12b
0x180002de6  mov     rbx, [rbp+13E0h+arg_30]
0x180002ded  mov     ecx, [rbx]; this
0x180002def  mov     [rsp+14E0h+var_14B8], ecx
0x180002df3  mov     eax, [rbx+4]
0x180002df6  mov     [rsp+14E0h+var_14B4], eax
0x180002dfa  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002dff  mov     edi, eax
0x180002e01  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180002e09  mov     ecx, r12d
0x180002e0c  lea     eax, [r12+8]
0x180002e11  cmp     dword ptr [rbx+8], 1
0x180002e15  cmovz   ecx, eax
0x180002e18  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180002e1c  lea     ecx, [rax-7]
0x180002e1f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002e27  inc     ecx
0x180002e29  mov     [rsp+14E0h+var_14B0], ecx
0x180002e2d  mov     [rsp+14E0h+var_14A8], r12
0x180002e32  call    cs:__imp_GetCurrentThreadId
0x180002e38  mov     [rsp+14E0h+var_14A0], eax
0x180002e3c  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002e43  mov     [rsp+14E0h+var_1488], rax
0x180002e48  mov     [rsp+14E0h+var_1480], r14d
0x180002e4d  mov     [rsp+14E0h+var_147C], edi
0x180002e51  mov     [rsp+14E0h+var_1498], r12
0x180002e56  mov     [rsp+14E0h+var_1490], r12
0x180002e5b  mov     [rbp+13E0h+var_1438], rsi
0x180002e5f  mov     [rbp+13E0h+var_1430], r15
0x180002e63  mov     [rsp+14E0h+var_1478], r12
0x180002e68  xorps   xmm0, xmm0
0x180002e6b  xor     eax, eax
0x180002e6d  movups  [rbp+13E0h+var_1458], xmm0
0x180002e71  mov     [rbp+13E0h+var_1448], rax
0x180002e75  xorps   xmm1, xmm1
0x180002e78  movups  [rsp+14E0h+var_1470], xmm1
0x180002e7d  mov     [rbp+13E0h+var_1460], rax
0x180002e81  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002e88  test    rax, rax
0x180002e8b  jz      short loc_180002E98
0x180002e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e92  mov     [rbp+13E0h+var_1440], rax
0x180002e96  jmp     short loc_180002E9C
0x180002e98  mov     [rbp+13E0h+var_1440], r12
0x180002e9c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002ea3  test    rax, rax
0x180002ea6  jz      short loc_180002EB2
0x180002ea8  lea     rcx, [rsp+14E0h+var_14C0]
0x180002ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002eb2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002eb9  test    rax, rax
0x180002ebc  jz      short loc_180002ED2
0x180002ebe  mov     r8d, 400h
0x180002ec4  lea     rdx, [rbp+13E0h+var_1420]
0x180002ec8  lea     rcx, [rsp+14E0h+var_14C0]
0x180002ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ed2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002ed9  test    rax, rax
0x180002edc  jz      short loc_180002EE8
0x180002ede  lea     rcx, [rsp+14E0h+var_14C0]
0x180002ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ee8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002eef  test    rax, rax
0x180002ef2  jz      short loc_180002F05
0x180002ef4  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002ef9  jnz     short loc_180002F05
0x180002efb  lea     rcx, [rsp+14E0h+var_14C0]
0x180002f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f05  cmp     [rsp+14E0h+var_14B8], r12d
0x180002f0a  jl      short loc_180002F1E
0x180002f0c  mov     ecx, 8000FFFFh; this
0x180002f11  mov     [rsp+14E0h+var_14B8], ecx
0x180002f15  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002f1a  mov     [rsp+14E0h+var_14B4], eax
0x180002f1e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002f25  jnz     short loc_180002F46
0x180002f27  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002f2e  test    rax, rax
0x180002f31  jz      short loc_180002F3C
0x180002f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f38  test    al, al
0x180002f3a  jmp     short loc_180002F44
0x180002f3c  call    cs:__imp_IsDebuggerPresent
0x180002f42  test    eax, eax
0x180002f44  jz      short loc_180002F4D
0x180002f46  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002f4b  jz      short loc_180002F73
0x180002f4d  mov     rax, cs:g_pfnResultLoggingCallback
0x180002f54  test    rax, rax
0x180002f57  jz      short loc_180002FCC
0x180002f59  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002f60  jnz     short loc_180002FCC
0x180002f62  xor     r8d, r8d
0x180002f65  xor     edx, edx
0x180002f67  lea     rcx, [rsp+14E0h+var_14C0]
0x180002f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f71  jmp     short loc_180002FCC
0x180002f73  mov     ebx, 800h
0x180002f78  mov     rax, cs:g_pfnResultLoggingCallback
0x180002f7f  test    rax, rax
0x180002f82  jz      short loc_180002FA1
0x180002f84  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002f8b  jnz     short loc_180002FA1
0x180002f8d  mov     r8d, ebx
0x180002f90  lea     rdx, [rbp+13E0h+OutputString]
0x180002f97  lea     rcx, [rsp+14E0h+var_14C0]
0x180002f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fa1  cmp     [rbp+13E0h+OutputString], r12w
0x180002fa9  jnz     short loc_180002FBF
0x180002fab  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180002fb0  mov     rdx, rbx; unsigned __int16 *
0x180002fb3  lea     rcx, [rbp+13E0h+OutputString]; this
0x180002fba  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002fbf  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180002fc6  call    cs:__imp_OutputDebugStringW
0x180002fcc  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180002fd1  jnz     short loc_180002FDC
0x180002fd3  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002fda  jz      short loc_180002FEE
0x180002fdc  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002fe3  test    rax, rax
0x180002fe6  jz      short loc_180002FEE
0x180002fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fed  nop
0x180002fee  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180002ff3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
