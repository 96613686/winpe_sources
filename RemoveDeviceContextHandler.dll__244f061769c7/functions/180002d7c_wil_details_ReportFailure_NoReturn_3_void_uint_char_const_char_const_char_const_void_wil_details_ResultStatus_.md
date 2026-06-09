# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002d7c`
- end: `0x180002fe3`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `615`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002b30`

## callees

- `0x180002d7c`
- `0x180003f84`
- `0x1800047c0`
- `0x180004bd0`
- `0x1800054f0`
- `0x18000c966`
- `0x18000ca20`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002e1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002e1d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002f27`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002f27`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002fb1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002fb1`

## string_xrefs

- `0x180002e32`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v9; // eax
  int v10; // edx
  int v11; // eax
  int v12; // edi
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  __int64 v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v21, v10);
  v18 = a7[2] == 1;
  v12 = v11;
  v19 = 3;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
  {
    v21 = -2147418113;
    v22 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v15);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( (v20 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v16);
  }
  wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x180002d7c  mov     [rsp-8+arg_10], rbx
0x180002d81  mov     [rsp-8+arg_18], rsi
0x180002d86  push    rbp
0x180002d87  push    rdi
0x180002d88  push    r12
0x180002d8a  push    r14
0x180002d8c  push    r15
0x180002d8e  lea     rbp, [rsp-13C0h]
0x180002d96  mov     eax, 14C0h
0x180002d9b  call    _alloca_probe
0x180002da0  sub     rsp, rax
0x180002da3  mov     rsi, [rbp+13E0h+arg_28]
0x180002daa  mov     r14d, edx
0x180002dad  mov     r15, rcx
0x180002db0  xor     edx, edx; Val
0x180002db2  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180002db7  mov     r8d, 98h; Size
0x180002dbd  call    memset_0
0x180002dc2  mov     rbx, [rbp+13E0h+arg_30]
0x180002dc9  xor     r12d, r12d
0x180002dcc  mov     [rbp+13E0h+OutputString], r12w
0x180002dd4  mov     [rbp+13E0h+var_1420], r12b
0x180002dd8  mov     ecx, [rbx]; this
0x180002dda  mov     eax, [rbx+4]
0x180002ddd  mov     [rsp+14E0h+var_14B8], ecx
0x180002de1  mov     [rsp+14E0h+var_14B4], eax
0x180002de5  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002dea  cmp     dword ptr [rbx+8], 1
0x180002dee  mov     edi, eax
0x180002df0  lea     eax, [r12+8]
0x180002df5  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180002dfd  mov     ecx, r12d
0x180002e00  cmovz   ecx, eax
0x180002e03  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180002e07  lea     ecx, [rax-7]
0x180002e0a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002e12  inc     ecx
0x180002e14  mov     [rsp+14E0h+var_14A8], r12
0x180002e19  mov     [rsp+14E0h+var_14B0], ecx
0x180002e1d  call    cs:__imp_GetCurrentThreadId
0x180002e23  xorps   xmm0, xmm0
0x180002e26  mov     [rsp+14E0h+var_1480], r14d
0x180002e2b  mov     [rsp+14E0h+var_14A0], eax
0x180002e2f  xorps   xmm1, xmm1
0x180002e32  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002e39  mov     [rsp+14E0h+var_147C], edi
0x180002e3d  mov     [rsp+14E0h+var_1488], rax
0x180002e42  xor     eax, eax
0x180002e44  mov     [rbp+13E0h+var_1448], rax
0x180002e48  mov     [rbp+13E0h+var_1460], rax
0x180002e4c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002e53  mov     [rsp+14E0h+var_1498], r12
0x180002e58  mov     [rsp+14E0h+var_1490], r12
0x180002e5d  mov     [rbp+13E0h+var_1438], rsi
0x180002e61  mov     [rbp+13E0h+var_1430], r15
0x180002e65  mov     [rsp+14E0h+var_1478], r12
0x180002e6a  movups  [rbp+13E0h+var_1458], xmm0
0x180002e6e  movups  [rsp+14E0h+var_1470], xmm1
0x180002e73  test    rax, rax
0x180002e76  jz      short loc_180002E83
0x180002e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e7d  mov     [rbp+13E0h+var_1440], rax
0x180002e81  jmp     short loc_180002E87
0x180002e83  mov     [rbp+13E0h+var_1440], r12
0x180002e87  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002e8e  test    rax, rax
0x180002e91  jz      short loc_180002E9D
0x180002e93  lea     rcx, [rsp+14E0h+var_14C0]
0x180002e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e9d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002ea4  test    rax, rax
0x180002ea7  jz      short loc_180002EBD
0x180002ea9  mov     r8d, 400h
0x180002eaf  lea     rdx, [rbp+13E0h+var_1420]
0x180002eb3  lea     rcx, [rsp+14E0h+var_14C0]
0x180002eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ebd  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002ec4  test    rax, rax
0x180002ec7  jz      short loc_180002ED3
0x180002ec9  lea     rcx, [rsp+14E0h+var_14C0]
0x180002ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ed3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002eda  test    rax, rax
0x180002edd  jz      short loc_180002EF0
0x180002edf  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002ee4  jnz     short loc_180002EF0
0x180002ee6  lea     rcx, [rsp+14E0h+var_14C0]
0x180002eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ef0  cmp     [rsp+14E0h+var_14B8], r12d
0x180002ef5  jl      short loc_180002F09
0x180002ef7  mov     ecx, 8000FFFFh; this
0x180002efc  mov     [rsp+14E0h+var_14B8], ecx
0x180002f00  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002f05  mov     [rsp+14E0h+var_14B4], eax
0x180002f09  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002f10  jnz     short loc_180002F31
0x180002f12  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002f19  test    rax, rax
0x180002f1c  jz      short loc_180002F27
0x180002f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f23  test    al, al
0x180002f25  jmp     short loc_180002F2F
0x180002f27  call    cs:__imp_IsDebuggerPresent
0x180002f2d  test    eax, eax
0x180002f2f  jz      short loc_180002F38
0x180002f31  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002f36  jz      short loc_180002F5E
0x180002f38  mov     rax, cs:g_pfnResultLoggingCallback
0x180002f3f  test    rax, rax
0x180002f42  jz      short loc_180002FB7
0x180002f44  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002f4b  jnz     short loc_180002FB7
0x180002f4d  xor     r8d, r8d
0x180002f50  lea     rcx, [rsp+14E0h+var_14C0]
0x180002f55  xor     edx, edx
0x180002f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f5c  jmp     short loc_180002FB7
0x180002f5e  mov     rax, cs:g_pfnResultLoggingCallback
0x180002f65  mov     ebx, 800h
0x180002f6a  test    rax, rax
0x180002f6d  jz      short loc_180002F8C
0x180002f6f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002f76  jnz     short loc_180002F8C
0x180002f78  mov     r8d, ebx
0x180002f7b  lea     rdx, [rbp+13E0h+OutputString]
0x180002f82  lea     rcx, [rsp+14E0h+var_14C0]
0x180002f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f8c  cmp     [rbp+13E0h+OutputString], r12w
0x180002f94  jnz     short loc_180002FAA
0x180002f96  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180002f9b  mov     rdx, rbx; unsigned __int16 *
0x180002f9e  lea     rcx, [rbp+13E0h+OutputString]; this
0x180002fa5  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002faa  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180002fb1  call    cs:__imp_OutputDebugStringW
0x180002fb7  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180002fbc  jnz     short loc_180002FC7
0x180002fbe  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002fc5  jz      short loc_180002FD8
0x180002fc7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002fce  test    rax, rax
0x180002fd1  jz      short loc_180002FD8
0x180002fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fd8  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180002fdd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
