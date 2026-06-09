# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800028b4`
- end: `0x180002b1b`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `615`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002660`

## callees

- `0x1800028b4`
- `0x180004334`
- `0x180004b74`
- `0x180005930`
- `0x180007260`
- `0x180007c62`
- `0x180007d20`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002955`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002955`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002a5f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002a5f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002ae9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002ae9`

## string_xrefs

- `0x18000296a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
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
0x1800028b4  mov     [rsp-8+arg_10], rbx
0x1800028b9  mov     [rsp-8+arg_18], rsi
0x1800028be  push    rbp
0x1800028bf  push    rdi
0x1800028c0  push    r12
0x1800028c2  push    r14
0x1800028c4  push    r15
0x1800028c6  lea     rbp, [rsp-13C0h]
0x1800028ce  mov     eax, 14C0h
0x1800028d3  call    _alloca_probe
0x1800028d8  sub     rsp, rax
0x1800028db  mov     rsi, [rbp+13E0h+arg_28]
0x1800028e2  mov     r14d, edx
0x1800028e5  mov     r15, rcx
0x1800028e8  xor     edx, edx; Val
0x1800028ea  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x1800028ef  mov     r8d, 98h; Size
0x1800028f5  call    memset_0
0x1800028fa  mov     rbx, [rbp+13E0h+arg_30]
0x180002901  xor     r12d, r12d
0x180002904  mov     [rbp+13E0h+OutputString], r12w
0x18000290c  mov     [rbp+13E0h+var_1420], r12b
0x180002910  mov     ecx, [rbx]; this
0x180002912  mov     eax, [rbx+4]
0x180002915  mov     [rsp+14E0h+var_14B8], ecx
0x180002919  mov     [rsp+14E0h+var_14B4], eax
0x18000291d  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002922  cmp     dword ptr [rbx+8], 1
0x180002926  mov     edi, eax
0x180002928  lea     eax, [r12+8]
0x18000292d  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180002935  mov     ecx, r12d
0x180002938  cmovz   ecx, eax
0x18000293b  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x18000293f  lea     ecx, [rax-7]
0x180002942  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000294a  inc     ecx
0x18000294c  mov     [rsp+14E0h+var_14A8], r12
0x180002951  mov     [rsp+14E0h+var_14B0], ecx
0x180002955  call    cs:__imp_GetCurrentThreadId
0x18000295b  xorps   xmm0, xmm0
0x18000295e  mov     [rsp+14E0h+var_1480], r14d
0x180002963  mov     [rsp+14E0h+var_14A0], eax
0x180002967  xorps   xmm1, xmm1
0x18000296a  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002971  mov     [rsp+14E0h+var_147C], edi
0x180002975  mov     [rsp+14E0h+var_1488], rax
0x18000297a  xor     eax, eax
0x18000297c  mov     [rbp+13E0h+var_1448], rax
0x180002980  mov     [rbp+13E0h+var_1460], rax
0x180002984  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000298b  mov     [rsp+14E0h+var_1498], r12
0x180002990  mov     [rsp+14E0h+var_1490], r12
0x180002995  mov     [rbp+13E0h+var_1438], rsi
0x180002999  mov     [rbp+13E0h+var_1430], r15
0x18000299d  mov     [rsp+14E0h+var_1478], r12
0x1800029a2  movups  [rbp+13E0h+var_1458], xmm0
0x1800029a6  movups  [rsp+14E0h+var_1470], xmm1
0x1800029ab  test    rax, rax
0x1800029ae  jz      short loc_1800029BB
0x1800029b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029b5  mov     [rbp+13E0h+var_1440], rax
0x1800029b9  jmp     short loc_1800029BF
0x1800029bb  mov     [rbp+13E0h+var_1440], r12
0x1800029bf  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800029c6  test    rax, rax
0x1800029c9  jz      short loc_1800029D5
0x1800029cb  lea     rcx, [rsp+14E0h+var_14C0]
0x1800029d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029d5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800029dc  test    rax, rax
0x1800029df  jz      short loc_1800029F5
0x1800029e1  mov     r8d, 400h
0x1800029e7  lea     rdx, [rbp+13E0h+var_1420]
0x1800029eb  lea     rcx, [rsp+14E0h+var_14C0]
0x1800029f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029f5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800029fc  test    rax, rax
0x1800029ff  jz      short loc_180002A0B
0x180002a01  lea     rcx, [rsp+14E0h+var_14C0]
0x180002a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a0b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002a12  test    rax, rax
0x180002a15  jz      short loc_180002A28
0x180002a17  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002a1c  jnz     short loc_180002A28
0x180002a1e  lea     rcx, [rsp+14E0h+var_14C0]
0x180002a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a28  cmp     [rsp+14E0h+var_14B8], r12d
0x180002a2d  jl      short loc_180002A41
0x180002a2f  mov     ecx, 8000FFFFh; this
0x180002a34  mov     [rsp+14E0h+var_14B8], ecx
0x180002a38  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002a3d  mov     [rsp+14E0h+var_14B4], eax
0x180002a41  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002a48  jnz     short loc_180002A69
0x180002a4a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002a51  test    rax, rax
0x180002a54  jz      short loc_180002A5F
0x180002a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a5b  test    al, al
0x180002a5d  jmp     short loc_180002A67
0x180002a5f  call    cs:__imp_IsDebuggerPresent
0x180002a65  test    eax, eax
0x180002a67  jz      short loc_180002A70
0x180002a69  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002a6e  jz      short loc_180002A96
0x180002a70  mov     rax, cs:g_pfnResultLoggingCallback
0x180002a77  test    rax, rax
0x180002a7a  jz      short loc_180002AEF
0x180002a7c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002a83  jnz     short loc_180002AEF
0x180002a85  xor     r8d, r8d
0x180002a88  lea     rcx, [rsp+14E0h+var_14C0]
0x180002a8d  xor     edx, edx
0x180002a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a94  jmp     short loc_180002AEF
0x180002a96  mov     rax, cs:g_pfnResultLoggingCallback
0x180002a9d  mov     ebx, 800h
0x180002aa2  test    rax, rax
0x180002aa5  jz      short loc_180002AC4
0x180002aa7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002aae  jnz     short loc_180002AC4
0x180002ab0  mov     r8d, ebx
0x180002ab3  lea     rdx, [rbp+13E0h+OutputString]
0x180002aba  lea     rcx, [rsp+14E0h+var_14C0]
0x180002abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ac4  cmp     [rbp+13E0h+OutputString], r12w
0x180002acc  jnz     short loc_180002AE2
0x180002ace  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180002ad3  mov     rdx, rbx; unsigned __int16 *
0x180002ad6  lea     rcx, [rbp+13E0h+OutputString]; this
0x180002add  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002ae2  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180002ae9  call    cs:__imp_OutputDebugStringW
0x180002aef  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180002af4  jnz     short loc_180002AFF
0x180002af6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002afd  jz      short loc_180002B10
0x180002aff  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002b06  test    rax, rax
0x180002b09  jz      short loc_180002B10
0x180002b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b10  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180002b15  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
