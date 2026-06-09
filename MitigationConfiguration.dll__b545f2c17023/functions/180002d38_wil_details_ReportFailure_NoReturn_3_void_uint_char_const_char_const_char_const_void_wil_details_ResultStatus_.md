# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002d38`
- end: `0x180002fa1`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002ae4`

## callees

- `0x180002648`
- `0x180002d38`
- `0x180004b54`
- `0x1800052f4`
- `0x180005b30`
- `0x180006c70`
- `0x180013a60`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002dda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002dda`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002ee4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002ee4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002f6e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002f6e`

## string_xrefs

- `0x180002de4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180002d38  mov     [rsp-8+arg_10], rbx
0x180002d3d  mov     [rsp-8+arg_18], rsi
0x180002d42  push    rbp
0x180002d43  push    rdi
0x180002d44  push    r12
0x180002d46  push    r14
0x180002d48  push    r15
0x180002d4a  lea     rbp, [rsp-13C0h]
0x180002d52  mov     eax, 14C0h
0x180002d57  call    _alloca_probe
0x180002d5c  sub     rsp, rax
0x180002d5f  mov     r14d, edx
0x180002d62  mov     r15, rcx
0x180002d65  mov     rsi, [rbp+13E0h+arg_28]
0x180002d6c  xor     edx, edx; Val
0x180002d6e  mov     r8d, 98h; Size
0x180002d74  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180002d79  call    memset_0
0x180002d7e  nop
0x180002d7f  xor     r12d, r12d
0x180002d82  mov     [rbp+13E0h+OutputString], r12w
0x180002d8a  mov     [rbp+13E0h+var_1420], r12b
0x180002d8e  mov     rbx, [rbp+13E0h+arg_30]
0x180002d95  mov     ecx, [rbx]; this
0x180002d97  mov     [rsp+14E0h+var_14B8], ecx
0x180002d9b  mov     eax, [rbx+4]
0x180002d9e  mov     [rsp+14E0h+var_14B4], eax
0x180002da2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002da7  mov     edi, eax
0x180002da9  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180002db1  mov     ecx, r12d
0x180002db4  lea     eax, [r12+8]
0x180002db9  cmp     dword ptr [rbx+8], 1
0x180002dbd  cmovz   ecx, eax
0x180002dc0  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180002dc4  lea     ecx, [rax-7]
0x180002dc7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002dcf  inc     ecx
0x180002dd1  mov     [rsp+14E0h+var_14B0], ecx
0x180002dd5  mov     [rsp+14E0h+var_14A8], r12
0x180002dda  call    cs:__imp_GetCurrentThreadId
0x180002de0  mov     [rsp+14E0h+var_14A0], eax
0x180002de4  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002deb  mov     [rsp+14E0h+var_1488], rax
0x180002df0  mov     [rsp+14E0h+var_1480], r14d
0x180002df5  mov     [rsp+14E0h+var_147C], edi
0x180002df9  mov     [rsp+14E0h+var_1498], r12
0x180002dfe  mov     [rsp+14E0h+var_1490], r12
0x180002e03  mov     [rbp+13E0h+var_1438], rsi
0x180002e07  mov     [rbp+13E0h+var_1430], r15
0x180002e0b  mov     [rsp+14E0h+var_1478], r12
0x180002e10  xorps   xmm0, xmm0
0x180002e13  xor     eax, eax
0x180002e15  movups  [rbp+13E0h+var_1458], xmm0
0x180002e19  mov     [rbp+13E0h+var_1448], rax
0x180002e1d  xorps   xmm1, xmm1
0x180002e20  movups  [rsp+14E0h+var_1470], xmm1
0x180002e25  mov     [rbp+13E0h+var_1460], rax
0x180002e29  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002e30  test    rax, rax
0x180002e33  jz      short loc_180002E40
0x180002e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e3a  mov     [rbp+13E0h+var_1440], rax
0x180002e3e  jmp     short loc_180002E44
0x180002e40  mov     [rbp+13E0h+var_1440], r12
0x180002e44  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002e4b  test    rax, rax
0x180002e4e  jz      short loc_180002E5A
0x180002e50  lea     rcx, [rsp+14E0h+var_14C0]
0x180002e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e5a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002e61  test    rax, rax
0x180002e64  jz      short loc_180002E7A
0x180002e66  mov     r8d, 400h
0x180002e6c  lea     rdx, [rbp+13E0h+var_1420]
0x180002e70  lea     rcx, [rsp+14E0h+var_14C0]
0x180002e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e7a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002e81  test    rax, rax
0x180002e84  jz      short loc_180002E90
0x180002e86  lea     rcx, [rsp+14E0h+var_14C0]
0x180002e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e90  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002e97  test    rax, rax
0x180002e9a  jz      short loc_180002EAD
0x180002e9c  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002ea1  jnz     short loc_180002EAD
0x180002ea3  lea     rcx, [rsp+14E0h+var_14C0]
0x180002ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ead  cmp     [rsp+14E0h+var_14B8], r12d
0x180002eb2  jl      short loc_180002EC6
0x180002eb4  mov     ecx, 8000FFFFh; this
0x180002eb9  mov     [rsp+14E0h+var_14B8], ecx
0x180002ebd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002ec2  mov     [rsp+14E0h+var_14B4], eax
0x180002ec6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002ecd  jnz     short loc_180002EEE
0x180002ecf  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002ed6  test    rax, rax
0x180002ed9  jz      short loc_180002EE4
0x180002edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ee0  test    al, al
0x180002ee2  jmp     short loc_180002EEC
0x180002ee4  call    cs:__imp_IsDebuggerPresent
0x180002eea  test    eax, eax
0x180002eec  jz      short loc_180002EF5
0x180002eee  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002ef3  jz      short loc_180002F1B
0x180002ef5  mov     rax, cs:g_pfnResultLoggingCallback
0x180002efc  test    rax, rax
0x180002eff  jz      short loc_180002F74
0x180002f01  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002f08  jnz     short loc_180002F74
0x180002f0a  xor     r8d, r8d
0x180002f0d  xor     edx, edx
0x180002f0f  lea     rcx, [rsp+14E0h+var_14C0]
0x180002f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f19  jmp     short loc_180002F74
0x180002f1b  mov     ebx, 800h
0x180002f20  mov     rax, cs:g_pfnResultLoggingCallback
0x180002f27  test    rax, rax
0x180002f2a  jz      short loc_180002F49
0x180002f2c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002f33  jnz     short loc_180002F49
0x180002f35  mov     r8d, ebx
0x180002f38  lea     rdx, [rbp+13E0h+OutputString]
0x180002f3f  lea     rcx, [rsp+14E0h+var_14C0]
0x180002f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f49  cmp     [rbp+13E0h+OutputString], r12w
0x180002f51  jnz     short loc_180002F67
0x180002f53  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180002f58  mov     rdx, rbx; unsigned __int16 *
0x180002f5b  lea     rcx, [rbp+13E0h+OutputString]; this
0x180002f62  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002f67  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180002f6e  call    cs:__imp_OutputDebugStringW
0x180002f74  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180002f79  jnz     short loc_180002F84
0x180002f7b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002f82  jz      short loc_180002F96
0x180002f84  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002f8b  test    rax, rax
0x180002f8e  jz      short loc_180002F96
0x180002f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f95  nop
0x180002f96  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180002f9b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
