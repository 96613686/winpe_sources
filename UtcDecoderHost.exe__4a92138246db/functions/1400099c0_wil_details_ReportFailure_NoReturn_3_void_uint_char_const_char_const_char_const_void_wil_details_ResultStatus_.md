# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1400099c0`
- end: `0x140009c39`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400095ec`

## callees

- `0x1400090ec`
- `0x1400099c0`
- `0x14000b4c4`
- `0x14000bc6c`
- `0x14000c0d0`
- `0x14000d200`
- `0x1400167a0`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009a79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009a79`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140009c06`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140009c06`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140009b7c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140009b7c`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
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
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
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
0x1400099c0  mov     [rsp-8+arg_18], rbx
0x1400099c5  push    rbp
0x1400099c6  push    rsi
0x1400099c7  push    rdi
0x1400099c8  push    r12
0x1400099ca  push    r13
0x1400099cc  push    r14
0x1400099ce  push    r15
0x1400099d0  lea     rbp, [rsp-13C0h]
0x1400099d8  mov     eax, 14C0h
0x1400099dd  call    _alloca_probe
0x1400099e2  sub     rsp, rax
0x1400099e5  mov     r14, r8
0x1400099e8  mov     esi, edx
0x1400099ea  mov     rdi, rcx
0x1400099ed  mov     r15, [rbp+13F0h+arg_28]
0x1400099f4  xor     edx, edx; Val
0x1400099f6  mov     r8d, 98h; Size
0x1400099fc  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140009a01  call    memset_0
0x140009a06  nop
0x140009a07  xor     r13d, r13d
0x140009a0a  mov     [rbp+13F0h+OutputString], r13w
0x140009a12  mov     [rbp+13F0h+var_1430], r13b
0x140009a16  mov     rbx, [rbp+13F0h+arg_30]
0x140009a1d  mov     ecx, [rbx]; this
0x140009a1f  mov     [rsp+14F0h+var_14C8], ecx
0x140009a23  mov     eax, [rbx+4]
0x140009a26  mov     [rsp+14F0h+var_14C4], eax
0x140009a2a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140009a2f  mov     r12d, eax
0x140009a32  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x140009a3a  mov     ecx, r13d
0x140009a3d  lea     eax, [r13+8]
0x140009a41  cmp     dword ptr [rbx+8], 1
0x140009a45  cmovz   ecx, eax
0x140009a48  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140009a4c  lea     ecx, [rax-7]
0x140009a4f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140009a57  inc     ecx
0x140009a59  mov     [rsp+14F0h+var_14C0], ecx
0x140009a5d  mov     rcx, [rbp+13F0h+arg_38]
0x140009a64  test    rcx, rcx
0x140009a67  jz      short loc_140009A74
0x140009a69  cmp     [rcx], r13w
0x140009a6d  mov     [rsp+14F0h+var_14B8], rcx
0x140009a72  jnz     short loc_140009A79
0x140009a74  mov     [rsp+14F0h+var_14B8], r13
0x140009a79  call    cs:__imp_GetCurrentThreadId
0x140009a7f  mov     [rsp+14F0h+var_14B0], eax
0x140009a83  mov     [rsp+14F0h+var_1498], r14
0x140009a88  mov     [rsp+14F0h+var_1490], esi
0x140009a8c  mov     [rsp+14F0h+var_148C], r12d
0x140009a91  mov     [rsp+14F0h+var_14A8], r13
0x140009a96  mov     [rsp+14F0h+var_14A0], r13
0x140009a9b  mov     [rbp+13F0h+var_1448], r15
0x140009a9f  mov     [rbp+13F0h+var_1440], rdi
0x140009aa3  mov     [rsp+14F0h+var_1488], r13
0x140009aa8  xorps   xmm0, xmm0
0x140009aab  xor     eax, eax
0x140009aad  movups  [rbp+13F0h+var_1468], xmm0
0x140009ab1  mov     [rbp+13F0h+var_1458], rax
0x140009ab5  xorps   xmm1, xmm1
0x140009ab8  movups  [rsp+14F0h+var_1480], xmm1
0x140009abd  mov     [rbp+13F0h+var_1470], rax
0x140009ac1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140009ac8  test    rax, rax
0x140009acb  jz      short loc_140009AD8
0x140009acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009ad2  mov     [rbp+13F0h+var_1450], rax
0x140009ad6  jmp     short loc_140009ADC
0x140009ad8  mov     [rbp+13F0h+var_1450], r13
0x140009adc  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140009ae3  test    rax, rax
0x140009ae6  jz      short loc_140009AF2
0x140009ae8  lea     rcx, [rsp+14F0h+var_14D0]
0x140009aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009af2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140009af9  test    rax, rax
0x140009afc  jz      short loc_140009B12
0x140009afe  mov     r8d, 400h
0x140009b04  lea     rdx, [rbp+13F0h+var_1430]
0x140009b08  lea     rcx, [rsp+14F0h+var_14D0]
0x140009b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b12  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140009b19  test    rax, rax
0x140009b1c  jz      short loc_140009B28
0x140009b1e  lea     rcx, [rsp+14F0h+var_14D0]
0x140009b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b28  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140009b2f  test    rax, rax
0x140009b32  jz      short loc_140009B45
0x140009b34  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140009b39  jnz     short loc_140009B45
0x140009b3b  lea     rcx, [rsp+14F0h+var_14D0]
0x140009b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b45  cmp     [rsp+14F0h+var_14C8], r13d
0x140009b4a  jl      short loc_140009B5E
0x140009b4c  mov     ecx, 8000FFFFh; this
0x140009b51  mov     [rsp+14F0h+var_14C8], ecx
0x140009b55  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140009b5a  mov     [rsp+14F0h+var_14C4], eax
0x140009b5e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140009b65  jnz     short loc_140009B86
0x140009b67  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140009b6e  test    rax, rax
0x140009b71  jz      short loc_140009B7C
0x140009b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b78  test    al, al
0x140009b7a  jmp     short loc_140009B84
0x140009b7c  call    cs:__imp_IsDebuggerPresent
0x140009b82  test    eax, eax
0x140009b84  jz      short loc_140009B8D
0x140009b86  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140009b8b  jz      short loc_140009BB3
0x140009b8d  mov     rax, cs:g_pfnResultLoggingCallback
0x140009b94  test    rax, rax
0x140009b97  jz      short loc_140009C0C
0x140009b99  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140009ba0  jnz     short loc_140009C0C
0x140009ba2  xor     r8d, r8d
0x140009ba5  xor     edx, edx
0x140009ba7  lea     rcx, [rsp+14F0h+var_14D0]
0x140009bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009bb1  jmp     short loc_140009C0C
0x140009bb3  mov     ebx, 800h
0x140009bb8  mov     rax, cs:g_pfnResultLoggingCallback
0x140009bbf  test    rax, rax
0x140009bc2  jz      short loc_140009BE1
0x140009bc4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140009bcb  jnz     short loc_140009BE1
0x140009bcd  mov     r8d, ebx
0x140009bd0  lea     rdx, [rbp+13F0h+OutputString]
0x140009bd7  lea     rcx, [rsp+14F0h+var_14D0]
0x140009bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009be1  cmp     [rbp+13F0h+OutputString], r13w
0x140009be9  jnz     short loc_140009BFF
0x140009beb  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140009bf0  mov     rdx, rbx; unsigned __int16 *
0x140009bf3  lea     rcx, [rbp+13F0h+OutputString]; this
0x140009bfa  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140009bff  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140009c06  call    cs:__imp_OutputDebugStringW
0x140009c0c  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140009c11  jnz     short loc_140009C1C
0x140009c13  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140009c1a  jz      short loc_140009C2E
0x140009c1c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140009c23  test    rax, rax
0x140009c26  jz      short loc_140009C2E
0x140009c28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009c2d  nop
0x140009c2e  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140009c33  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
