# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002c80`
- end: `0x180002ee9`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002a2c`

## callees

- `0x180002958`
- `0x180002c80`
- `0x180005294`
- `0x180005a34`
- `0x180006700`
- `0x1800087f0`
- `0x18000e890`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d22`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002e2c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002e2c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002eb6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002eb6`

## string_xrefs

- `0x180002d2c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180002c80  mov     [rsp-8+arg_10], rbx
0x180002c85  mov     [rsp-8+arg_18], rsi
0x180002c8a  push    rbp
0x180002c8b  push    rdi
0x180002c8c  push    r12
0x180002c8e  push    r14
0x180002c90  push    r15
0x180002c92  lea     rbp, [rsp-13C0h]
0x180002c9a  mov     eax, 14C0h
0x180002c9f  call    _alloca_probe
0x180002ca4  sub     rsp, rax
0x180002ca7  mov     r14d, edx
0x180002caa  mov     r15, rcx
0x180002cad  mov     rsi, [rbp+13E0h+arg_28]
0x180002cb4  xor     edx, edx; Val
0x180002cb6  mov     r8d, 98h; Size
0x180002cbc  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180002cc1  call    memset_0
0x180002cc6  nop
0x180002cc7  xor     r12d, r12d
0x180002cca  mov     [rbp+13E0h+OutputString], r12w
0x180002cd2  mov     [rbp+13E0h+var_1420], r12b
0x180002cd6  mov     rbx, [rbp+13E0h+arg_30]
0x180002cdd  mov     ecx, [rbx]; this
0x180002cdf  mov     [rsp+14E0h+var_14B8], ecx
0x180002ce3  mov     eax, [rbx+4]
0x180002ce6  mov     [rsp+14E0h+var_14B4], eax
0x180002cea  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002cef  mov     edi, eax
0x180002cf1  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180002cf9  mov     ecx, r12d
0x180002cfc  lea     eax, [r12+8]
0x180002d01  cmp     dword ptr [rbx+8], 1
0x180002d05  cmovz   ecx, eax
0x180002d08  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180002d0c  lea     ecx, [rax-7]
0x180002d0f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002d17  inc     ecx
0x180002d19  mov     [rsp+14E0h+var_14B0], ecx
0x180002d1d  mov     [rsp+14E0h+var_14A8], r12
0x180002d22  call    cs:__imp_GetCurrentThreadId
0x180002d28  mov     [rsp+14E0h+var_14A0], eax
0x180002d2c  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002d33  mov     [rsp+14E0h+var_1488], rax
0x180002d38  mov     [rsp+14E0h+var_1480], r14d
0x180002d3d  mov     [rsp+14E0h+var_147C], edi
0x180002d41  mov     [rsp+14E0h+var_1498], r12
0x180002d46  mov     [rsp+14E0h+var_1490], r12
0x180002d4b  mov     [rbp+13E0h+var_1438], rsi
0x180002d4f  mov     [rbp+13E0h+var_1430], r15
0x180002d53  mov     [rsp+14E0h+var_1478], r12
0x180002d58  xorps   xmm0, xmm0
0x180002d5b  xor     eax, eax
0x180002d5d  movups  [rbp+13E0h+var_1458], xmm0
0x180002d61  mov     [rbp+13E0h+var_1448], rax
0x180002d65  xorps   xmm1, xmm1
0x180002d68  movups  [rsp+14E0h+var_1470], xmm1
0x180002d6d  mov     [rbp+13E0h+var_1460], rax
0x180002d71  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002d78  test    rax, rax
0x180002d7b  jz      short loc_180002D88
0x180002d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d82  mov     [rbp+13E0h+var_1440], rax
0x180002d86  jmp     short loc_180002D8C
0x180002d88  mov     [rbp+13E0h+var_1440], r12
0x180002d8c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002d93  test    rax, rax
0x180002d96  jz      short loc_180002DA2
0x180002d98  lea     rcx, [rsp+14E0h+var_14C0]
0x180002d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002da2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002da9  test    rax, rax
0x180002dac  jz      short loc_180002DC2
0x180002dae  mov     r8d, 400h
0x180002db4  lea     rdx, [rbp+13E0h+var_1420]
0x180002db8  lea     rcx, [rsp+14E0h+var_14C0]
0x180002dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dc2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002dc9  test    rax, rax
0x180002dcc  jz      short loc_180002DD8
0x180002dce  lea     rcx, [rsp+14E0h+var_14C0]
0x180002dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dd8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002ddf  test    rax, rax
0x180002de2  jz      short loc_180002DF5
0x180002de4  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002de9  jnz     short loc_180002DF5
0x180002deb  lea     rcx, [rsp+14E0h+var_14C0]
0x180002df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002df5  cmp     [rsp+14E0h+var_14B8], r12d
0x180002dfa  jl      short loc_180002E0E
0x180002dfc  mov     ecx, 8000FFFFh; this
0x180002e01  mov     [rsp+14E0h+var_14B8], ecx
0x180002e05  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002e0a  mov     [rsp+14E0h+var_14B4], eax
0x180002e0e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002e15  jnz     short loc_180002E36
0x180002e17  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002e1e  test    rax, rax
0x180002e21  jz      short loc_180002E2C
0x180002e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e28  test    al, al
0x180002e2a  jmp     short loc_180002E34
0x180002e2c  call    cs:__imp_IsDebuggerPresent
0x180002e32  test    eax, eax
0x180002e34  jz      short loc_180002E3D
0x180002e36  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002e3b  jz      short loc_180002E63
0x180002e3d  mov     rax, cs:g_pfnResultLoggingCallback
0x180002e44  test    rax, rax
0x180002e47  jz      short loc_180002EBC
0x180002e49  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002e50  jnz     short loc_180002EBC
0x180002e52  xor     r8d, r8d
0x180002e55  xor     edx, edx
0x180002e57  lea     rcx, [rsp+14E0h+var_14C0]
0x180002e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e61  jmp     short loc_180002EBC
0x180002e63  mov     ebx, 800h
0x180002e68  mov     rax, cs:g_pfnResultLoggingCallback
0x180002e6f  test    rax, rax
0x180002e72  jz      short loc_180002E91
0x180002e74  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002e7b  jnz     short loc_180002E91
0x180002e7d  mov     r8d, ebx
0x180002e80  lea     rdx, [rbp+13E0h+OutputString]
0x180002e87  lea     rcx, [rsp+14E0h+var_14C0]
0x180002e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e91  cmp     [rbp+13E0h+OutputString], r12w
0x180002e99  jnz     short loc_180002EAF
0x180002e9b  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180002ea0  mov     rdx, rbx; unsigned __int16 *
0x180002ea3  lea     rcx, [rbp+13E0h+OutputString]; this
0x180002eaa  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002eaf  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180002eb6  call    cs:__imp_OutputDebugStringW
0x180002ebc  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180002ec1  jnz     short loc_180002ECC
0x180002ec3  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002eca  jz      short loc_180002EDE
0x180002ecc  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002ed3  test    rax, rax
0x180002ed6  jz      short loc_180002EDE
0x180002ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002edd  nop
0x180002ede  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180002ee3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
