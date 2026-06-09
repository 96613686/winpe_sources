# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180003b3c`
- end: `0x180003db5`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800038bc`

## callees

- `0x180002ed4`
- `0x180003b3c`
- `0x180006304`
- `0x180006aa4`
- `0x180007af0`
- `0x18000a2c0`
- `0x1800291b0`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003bf5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003bf5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003cf8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003cf8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003d82`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003d82`

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
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
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
0x180003b3c  mov     [rsp-8+arg_18], rbx
0x180003b41  push    rbp
0x180003b42  push    rsi
0x180003b43  push    rdi
0x180003b44  push    r12
0x180003b46  push    r13
0x180003b48  push    r14
0x180003b4a  push    r15
0x180003b4c  lea     rbp, [rsp-13C0h]
0x180003b54  mov     eax, 14C0h
0x180003b59  call    _alloca_probe
0x180003b5e  sub     rsp, rax
0x180003b61  mov     r14, r8
0x180003b64  mov     esi, edx
0x180003b66  mov     rdi, rcx
0x180003b69  mov     r15, [rbp+13F0h+arg_28]
0x180003b70  xor     edx, edx; Val
0x180003b72  mov     r8d, 98h; Size
0x180003b78  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003b7d  call    memset_0
0x180003b82  nop
0x180003b83  xor     r13d, r13d
0x180003b86  mov     [rbp+13F0h+OutputString], r13w
0x180003b8e  mov     [rbp+13F0h+var_1430], r13b
0x180003b92  mov     rbx, [rbp+13F0h+arg_30]
0x180003b99  mov     ecx, [rbx]; this
0x180003b9b  mov     [rsp+14F0h+var_14C8], ecx
0x180003b9f  mov     eax, [rbx+4]
0x180003ba2  mov     [rsp+14F0h+var_14C4], eax
0x180003ba6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003bab  mov     r12d, eax
0x180003bae  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180003bb6  mov     ecx, r13d
0x180003bb9  lea     eax, [r13+8]
0x180003bbd  cmp     dword ptr [rbx+8], 1
0x180003bc1  cmovz   ecx, eax
0x180003bc4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003bc8  lea     ecx, [rax-7]
0x180003bcb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003bd3  inc     ecx
0x180003bd5  mov     [rsp+14F0h+var_14C0], ecx
0x180003bd9  mov     rcx, [rbp+13F0h+arg_38]
0x180003be0  test    rcx, rcx
0x180003be3  jz      short loc_180003BF0
0x180003be5  cmp     [rcx], r13w
0x180003be9  mov     [rsp+14F0h+var_14B8], rcx
0x180003bee  jnz     short loc_180003BF5
0x180003bf0  mov     [rsp+14F0h+var_14B8], r13
0x180003bf5  call    cs:__imp_GetCurrentThreadId
0x180003bfb  mov     [rsp+14F0h+var_14B0], eax
0x180003bff  mov     [rsp+14F0h+var_1498], r14
0x180003c04  mov     [rsp+14F0h+var_1490], esi
0x180003c08  mov     [rsp+14F0h+var_148C], r12d
0x180003c0d  mov     [rsp+14F0h+var_14A8], r13
0x180003c12  mov     [rsp+14F0h+var_14A0], r13
0x180003c17  mov     [rbp+13F0h+var_1448], r15
0x180003c1b  mov     [rbp+13F0h+var_1440], rdi
0x180003c1f  mov     [rsp+14F0h+var_1488], r13
0x180003c24  xorps   xmm0, xmm0
0x180003c27  xor     eax, eax
0x180003c29  movups  [rbp+13F0h+var_1468], xmm0
0x180003c2d  mov     [rbp+13F0h+var_1458], rax
0x180003c31  xorps   xmm1, xmm1
0x180003c34  movups  [rsp+14F0h+var_1480], xmm1
0x180003c39  mov     [rbp+13F0h+var_1470], rax
0x180003c3d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003c44  test    rax, rax
0x180003c47  jz      short loc_180003C54
0x180003c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c4e  mov     [rbp+13F0h+var_1450], rax
0x180003c52  jmp     short loc_180003C58
0x180003c54  mov     [rbp+13F0h+var_1450], r13
0x180003c58  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003c5f  test    rax, rax
0x180003c62  jz      short loc_180003C6E
0x180003c64  lea     rcx, [rsp+14F0h+var_14D0]
0x180003c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c6e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003c75  test    rax, rax
0x180003c78  jz      short loc_180003C8E
0x180003c7a  mov     r8d, 400h
0x180003c80  lea     rdx, [rbp+13F0h+var_1430]
0x180003c84  lea     rcx, [rsp+14F0h+var_14D0]
0x180003c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c8e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003c95  test    rax, rax
0x180003c98  jz      short loc_180003CA4
0x180003c9a  lea     rcx, [rsp+14F0h+var_14D0]
0x180003c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ca4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003cab  test    rax, rax
0x180003cae  jz      short loc_180003CC1
0x180003cb0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003cb5  jnz     short loc_180003CC1
0x180003cb7  lea     rcx, [rsp+14F0h+var_14D0]
0x180003cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cc1  cmp     [rsp+14F0h+var_14C8], r13d
0x180003cc6  jl      short loc_180003CDA
0x180003cc8  mov     ecx, 8000FFFFh; this
0x180003ccd  mov     [rsp+14F0h+var_14C8], ecx
0x180003cd1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003cd6  mov     [rsp+14F0h+var_14C4], eax
0x180003cda  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180003ce1  jnz     short loc_180003D02
0x180003ce3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003cea  test    rax, rax
0x180003ced  jz      short loc_180003CF8
0x180003cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cf4  test    al, al
0x180003cf6  jmp     short loc_180003D00
0x180003cf8  call    cs:__imp_IsDebuggerPresent
0x180003cfe  test    eax, eax
0x180003d00  jz      short loc_180003D09
0x180003d02  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003d07  jz      short loc_180003D2F
0x180003d09  mov     rax, cs:g_pfnResultLoggingCallback
0x180003d10  test    rax, rax
0x180003d13  jz      short loc_180003D88
0x180003d15  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003d1c  jnz     short loc_180003D88
0x180003d1e  xor     r8d, r8d
0x180003d21  xor     edx, edx
0x180003d23  lea     rcx, [rsp+14F0h+var_14D0]
0x180003d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d2d  jmp     short loc_180003D88
0x180003d2f  mov     ebx, 800h
0x180003d34  mov     rax, cs:g_pfnResultLoggingCallback
0x180003d3b  test    rax, rax
0x180003d3e  jz      short loc_180003D5D
0x180003d40  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003d47  jnz     short loc_180003D5D
0x180003d49  mov     r8d, ebx
0x180003d4c  lea     rdx, [rbp+13F0h+OutputString]
0x180003d53  lea     rcx, [rsp+14F0h+var_14D0]
0x180003d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d5d  cmp     [rbp+13F0h+OutputString], r13w
0x180003d65  jnz     short loc_180003D7B
0x180003d67  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003d6c  mov     rdx, rbx; unsigned __int16 *
0x180003d6f  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003d76  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003d7b  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003d82  call    cs:__imp_OutputDebugStringW
0x180003d88  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003d8d  jnz     short loc_180003D98
0x180003d8f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180003d96  jz      short loc_180003DAA
0x180003d98  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003d9f  test    rax, rax
0x180003da2  jz      short loc_180003DAA
0x180003da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003da9  nop
0x180003daa  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003daf  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
