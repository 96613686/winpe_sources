# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002adc`
- end: `0x180002d3e`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002874`

## callees

- `0x180002570`
- `0x180002adc`
- `0x180004dc4`
- `0x180005560`
- `0x180006150`
- `0x180008460`
- `0x18000e3e0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002b7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002b7e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002d0b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002d0b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002c81`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002c81`

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
0x180002adc  mov     [rsp-8+arg_18], rbx
0x180002ae1  push    rbp
0x180002ae2  push    rsi
0x180002ae3  push    rdi
0x180002ae4  push    r12
0x180002ae6  push    r13
0x180002ae8  push    r14
0x180002aea  push    r15
0x180002aec  lea     rbp, [rsp-13C0h]
0x180002af4  mov     eax, 14C0h
0x180002af9  call    _alloca_probe
0x180002afe  sub     rsp, rax
0x180002b01  mov     r15, r8
0x180002b04  mov     r14d, edx
0x180002b07  mov     r12, rcx
0x180002b0a  mov     rsi, [rbp+13F0h+arg_28]
0x180002b11  xor     edx, edx; Val
0x180002b13  mov     r8d, 98h; Size
0x180002b19  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002b1e  call    memset_0
0x180002b23  nop
0x180002b24  xor     r13d, r13d
0x180002b27  mov     [rbp+13F0h+OutputString], r13w
0x180002b2f  mov     [rbp+13F0h+var_1430], r13b
0x180002b33  mov     rbx, [rbp+13F0h+arg_30]
0x180002b3a  mov     ecx, [rbx]; this
0x180002b3c  mov     [rsp+14F0h+var_14C8], ecx
0x180002b40  mov     eax, [rbx+4]
0x180002b43  mov     [rsp+14F0h+var_14C4], eax
0x180002b47  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002b4c  mov     edi, eax
0x180002b4e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180002b56  mov     ecx, r13d
0x180002b59  lea     eax, [r13+8]
0x180002b5d  cmp     dword ptr [rbx+8], 1
0x180002b61  cmovz   ecx, eax
0x180002b64  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002b68  lea     ecx, [rax-7]
0x180002b6b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002b73  inc     ecx
0x180002b75  mov     [rsp+14F0h+var_14C0], ecx
0x180002b79  mov     [rsp+14F0h+var_14B8], r13
0x180002b7e  call    cs:__imp_GetCurrentThreadId
0x180002b84  mov     [rsp+14F0h+var_14B0], eax
0x180002b88  mov     [rsp+14F0h+var_1498], r15
0x180002b8d  mov     [rsp+14F0h+var_1490], r14d
0x180002b92  mov     [rsp+14F0h+var_148C], edi
0x180002b96  mov     [rsp+14F0h+var_14A8], r13
0x180002b9b  mov     [rsp+14F0h+var_14A0], r13
0x180002ba0  mov     [rbp+13F0h+var_1448], rsi
0x180002ba4  mov     [rbp+13F0h+var_1440], r12
0x180002ba8  mov     [rsp+14F0h+var_1488], r13
0x180002bad  xorps   xmm0, xmm0
0x180002bb0  xor     eax, eax
0x180002bb2  movups  [rbp+13F0h+var_1468], xmm0
0x180002bb6  mov     [rbp+13F0h+var_1458], rax
0x180002bba  xorps   xmm1, xmm1
0x180002bbd  movups  [rsp+14F0h+var_1480], xmm1
0x180002bc2  mov     [rbp+13F0h+var_1470], rax
0x180002bc6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002bcd  test    rax, rax
0x180002bd0  jz      short loc_180002BDD
0x180002bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bd7  mov     [rbp+13F0h+var_1450], rax
0x180002bdb  jmp     short loc_180002BE1
0x180002bdd  mov     [rbp+13F0h+var_1450], r13
0x180002be1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002be8  test    rax, rax
0x180002beb  jz      short loc_180002BF7
0x180002bed  lea     rcx, [rsp+14F0h+var_14D0]
0x180002bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bf7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002bfe  test    rax, rax
0x180002c01  jz      short loc_180002C17
0x180002c03  mov     r8d, 400h
0x180002c09  lea     rdx, [rbp+13F0h+var_1430]
0x180002c0d  lea     rcx, [rsp+14F0h+var_14D0]
0x180002c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c17  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002c1e  test    rax, rax
0x180002c21  jz      short loc_180002C2D
0x180002c23  lea     rcx, [rsp+14F0h+var_14D0]
0x180002c28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c2d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002c34  test    rax, rax
0x180002c37  jz      short loc_180002C4A
0x180002c39  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002c3e  jnz     short loc_180002C4A
0x180002c40  lea     rcx, [rsp+14F0h+var_14D0]
0x180002c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c4a  cmp     [rsp+14F0h+var_14C8], r13d
0x180002c4f  jl      short loc_180002C63
0x180002c51  mov     ecx, 8000FFFFh; this
0x180002c56  mov     [rsp+14F0h+var_14C8], ecx
0x180002c5a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002c5f  mov     [rsp+14F0h+var_14C4], eax
0x180002c63  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180002c6a  jnz     short loc_180002C8B
0x180002c6c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002c73  test    rax, rax
0x180002c76  jz      short loc_180002C81
0x180002c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c7d  test    al, al
0x180002c7f  jmp     short loc_180002C89
0x180002c81  call    cs:__imp_IsDebuggerPresent
0x180002c87  test    eax, eax
0x180002c89  jz      short loc_180002C92
0x180002c8b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002c90  jz      short loc_180002CB8
0x180002c92  mov     rax, cs:g_pfnResultLoggingCallback
0x180002c99  test    rax, rax
0x180002c9c  jz      short loc_180002D11
0x180002c9e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002ca5  jnz     short loc_180002D11
0x180002ca7  xor     r8d, r8d
0x180002caa  xor     edx, edx
0x180002cac  lea     rcx, [rsp+14F0h+var_14D0]
0x180002cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cb6  jmp     short loc_180002D11
0x180002cb8  mov     ebx, 800h
0x180002cbd  mov     rax, cs:g_pfnResultLoggingCallback
0x180002cc4  test    rax, rax
0x180002cc7  jz      short loc_180002CE6
0x180002cc9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002cd0  jnz     short loc_180002CE6
0x180002cd2  mov     r8d, ebx
0x180002cd5  lea     rdx, [rbp+13F0h+OutputString]
0x180002cdc  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ce6  cmp     [rbp+13F0h+OutputString], r13w
0x180002cee  jnz     short loc_180002D04
0x180002cf0  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002cf5  mov     rdx, rbx; unsigned __int16 *
0x180002cf8  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002cff  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002d04  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002d0b  call    cs:__imp_OutputDebugStringW
0x180002d11  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002d16  jnz     short loc_180002D21
0x180002d18  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180002d1f  jz      short loc_180002D33
0x180002d21  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002d28  test    rax, rax
0x180002d2b  jz      short loc_180002D33
0x180002d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d32  nop
0x180002d33  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002d38  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
