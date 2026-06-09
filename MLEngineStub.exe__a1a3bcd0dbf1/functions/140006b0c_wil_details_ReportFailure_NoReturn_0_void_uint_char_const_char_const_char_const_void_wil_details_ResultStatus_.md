# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140006b0c`
- end: `0x140006dd1`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400068fc`

## callees

- `0x140002c58`
- `0x140004374`
- `0x14000521c`
- `0x140005e6c`
- `0x1400061c0`
- `0x14000629c`
- `0x140006b0c`
- `0x14000acc0`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006bcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006bcd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140006cc9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140006cc9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006d65`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006d65`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  bool v11; // di
  int v12; // r12d
  int v13; // ecx
  __int64 v14; // rdx
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  char v19; // bl
  const struct wil::FailureInfo *v20; // rdx
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+24h] [rbp-DCh]
  int v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v25; // [rsp+30h] [rbp-D0h]
  _WORD *v26; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+60h] [rbp-A0h]
  int v32; // [rsp+64h] [rbp-9Ch]
  __int64 v33; // [rsp+68h] [rbp-98h]
  __int128 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+80h] [rbp-80h]
  __int128 v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  char v41[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v11 = g_pfnThrowPlatformException != 0;
  memset_0(&v21, 0, 0x98u);
  OutputString[0] = 0;
  v41[0] = 0;
  v23 = *a7;
  v24 = a7[1];
  v12 = wil::details::RecordException((wil::details *)(unsigned int)v23, (int)a7);
  v21 = 0;
  v13 = 0;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  v22 = v13;
  v25 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v18 = *a8 == 0, v26 = a8, v18) )
    v26 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v30 = a3;
  v31 = a2;
  v32 = v12;
  v28 = 0;
  v29 = 0;
  v39 = a6;
  v40 = a1;
  v33 = 0;
  v36 = 0;
  v37 = 0;
  v34 = 0;
  v35 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v21);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v21, v41, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v21);
  if ( wil::details::g_pfnOriginateCallback && !v11 && (v22 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v21);
  if ( v23 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v19 = 1, (v22 & 2) != 0) )
  {
    v19 = 0;
  }
  if ( v11 || v19 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v21, v17);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v21, 0, 0);
  }
  if ( ((v22 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v22 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v21, v15);
  if ( v11 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v21, OutputString);
  wil::ThrowResultException((wil *)&v21, v15);
  wil::details::WilFailFast((wil::details *)&v21, v20);
}

```

## disassembly

```asm
0x140006b0c  mov     [rsp-8+arg_18], rbx
0x140006b11  push    rbp
0x140006b12  push    rsi
0x140006b13  push    rdi
0x140006b14  push    r12
0x140006b16  push    r13
0x140006b18  push    r14
0x140006b1a  push    r15
0x140006b1c  lea     rbp, [rsp-13C0h]
0x140006b24  mov     eax, 14C0h
0x140006b29  call    _alloca_probe
0x140006b2e  sub     rsp, rax
0x140006b31  mov     r14, r8
0x140006b34  mov     esi, edx
0x140006b36  mov     rbx, rcx
0x140006b39  mov     r15, [rbp+13F0h+arg_28]
0x140006b40  xor     r13d, r13d
0x140006b43  cmp     cs:g_pfnThrowPlatformException, r13
0x140006b4a  setnz   dil
0x140006b4e  xor     edx, edx; Val
0x140006b50  mov     r8d, 98h; Size
0x140006b56  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140006b5b  call    memset_0
0x140006b60  nop
0x140006b61  mov     [rbp+13F0h+OutputString], r13w
0x140006b69  mov     [rbp+13F0h+var_1430], r13b
0x140006b6d  mov     rdx, [rbp+13F0h+arg_30]; int
0x140006b74  mov     ecx, [rdx]; this
0x140006b76  mov     [rsp+14F0h+var_14C8], ecx
0x140006b7a  mov     eax, [rdx+4]
0x140006b7d  mov     [rsp+14F0h+var_14C4], eax
0x140006b81  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140006b86  mov     r12d, eax
0x140006b89  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x140006b8e  mov     ecx, r13d
0x140006b91  lea     eax, [r13+8]
0x140006b95  cmp     dword ptr [rdx+8], 1
0x140006b99  cmovz   ecx, eax
0x140006b9c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140006ba0  lea     ecx, [rax-7]
0x140006ba3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140006bab  inc     ecx
0x140006bad  mov     [rsp+14F0h+var_14C0], ecx
0x140006bb1  mov     rcx, [rbp+13F0h+arg_38]
0x140006bb8  test    rcx, rcx
0x140006bbb  jz      short loc_140006BC8
0x140006bbd  cmp     [rcx], r13w
0x140006bc1  mov     [rsp+14F0h+var_14B8], rcx
0x140006bc6  jnz     short loc_140006BCD
0x140006bc8  mov     [rsp+14F0h+var_14B8], r13
0x140006bcd  call    cs:__imp_GetCurrentThreadId
0x140006bd3  mov     [rsp+14F0h+var_14B0], eax
0x140006bd7  mov     [rsp+14F0h+var_1498], r14
0x140006bdc  mov     [rsp+14F0h+var_1490], esi
0x140006be0  mov     [rsp+14F0h+var_148C], r12d
0x140006be5  mov     [rsp+14F0h+var_14A8], r13
0x140006bea  mov     [rsp+14F0h+var_14A0], r13
0x140006bef  mov     [rbp+13F0h+var_1448], r15
0x140006bf3  mov     [rbp+13F0h+var_1440], rbx
0x140006bf7  mov     [rsp+14F0h+var_1488], r13
0x140006bfc  xorps   xmm0, xmm0
0x140006bff  xor     eax, eax
0x140006c01  movups  [rbp+13F0h+var_1468], xmm0
0x140006c05  mov     [rbp+13F0h+var_1458], rax
0x140006c09  xorps   xmm1, xmm1
0x140006c0c  movups  [rsp+14F0h+var_1480], xmm1
0x140006c11  mov     [rbp+13F0h+var_1470], rax
0x140006c15  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140006c1c  test    rax, rax
0x140006c1f  jz      short loc_140006C2C
0x140006c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c26  mov     [rbp+13F0h+var_1450], rax
0x140006c2a  jmp     short loc_140006C30
0x140006c2c  mov     [rbp+13F0h+var_1450], r13
0x140006c30  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140006c37  test    rax, rax
0x140006c3a  jz      short loc_140006C46
0x140006c3c  lea     rcx, [rsp+14F0h+var_14D0]
0x140006c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c46  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140006c4d  test    rax, rax
0x140006c50  jz      short loc_140006C66
0x140006c52  mov     r8d, 400h
0x140006c58  lea     rdx, [rbp+13F0h+var_1430]
0x140006c5c  lea     rcx, [rsp+14F0h+var_14D0]
0x140006c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c66  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006c6d  test    rax, rax
0x140006c70  jz      short loc_140006C7C
0x140006c72  lea     rcx, [rsp+14F0h+var_14D0]
0x140006c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c7c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006c83  test    rax, rax
0x140006c86  jz      short loc_140006C9E
0x140006c88  test    dil, dil
0x140006c8b  jnz     short loc_140006C9E
0x140006c8d  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140006c92  jnz     short loc_140006C9E
0x140006c94  lea     rcx, [rsp+14F0h+var_14D0]
0x140006c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c9e  cmp     [rsp+14F0h+var_14C8], r13d
0x140006ca3  jl      short loc_140006CAB
0x140006ca5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140006cab  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140006cb2  jnz     short loc_140006CD3
0x140006cb4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140006cbb  test    rax, rax
0x140006cbe  jz      short loc_140006CC9
0x140006cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006cc5  test    al, al
0x140006cc7  jmp     short loc_140006CD1
0x140006cc9  call    cs:__imp_IsDebuggerPresent
0x140006ccf  test    eax, eax
0x140006cd1  jz      short loc_140006CDC
0x140006cd3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140006cd8  mov     bl, 1
0x140006cda  jz      short loc_140006CDF
0x140006cdc  mov     bl, r13b
0x140006cdf  test    dil, dil
0x140006ce2  jnz     short loc_140006D0E
0x140006ce4  test    bl, bl
0x140006ce6  jnz     short loc_140006D0E
0x140006ce8  mov     rax, cs:g_pfnResultLoggingCallback
0x140006cef  test    rax, rax
0x140006cf2  jz      short loc_140006D6B
0x140006cf4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140006cfb  jnz     short loc_140006D6B
0x140006cfd  xor     r8d, r8d
0x140006d00  xor     edx, edx
0x140006d02  lea     rcx, [rsp+14F0h+var_14D0]
0x140006d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d0c  jmp     short loc_140006D6B
0x140006d0e  mov     esi, 800h
0x140006d13  mov     rax, cs:g_pfnResultLoggingCallback
0x140006d1a  test    rax, rax
0x140006d1d  jz      short loc_140006D3C
0x140006d1f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140006d26  jnz     short loc_140006D3C
0x140006d28  mov     r8d, esi
0x140006d2b  lea     rdx, [rbp+13F0h+OutputString]
0x140006d32  lea     rcx, [rsp+14F0h+var_14D0]
0x140006d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d3c  cmp     [rbp+13F0h+OutputString], r13w
0x140006d44  jnz     short loc_140006D5A
0x140006d46  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140006d4b  mov     rdx, rsi; unsigned __int16 *
0x140006d4e  lea     rcx, [rbp+13F0h+OutputString]; this
0x140006d55  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140006d5a  test    bl, bl
0x140006d5c  jz      short loc_140006D6B
0x140006d5e  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140006d65  call    cs:__imp_OutputDebugStringW
0x140006d6b  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140006d70  jnz     short loc_140006D7B
0x140006d72  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140006d79  jz      short loc_140006D8D
0x140006d7b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140006d82  test    rax, rax
0x140006d85  jz      short loc_140006D8D
0x140006d87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d8c  nop
0x140006d8d  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140006d92  jz      short loc_140006D9F
0x140006d94  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140006d99  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140006d9f  test    dil, dil
0x140006da2  jz      short loc_140006DBC
0x140006da4  lea     rdx, [rbp+13F0h+OutputString]
0x140006dab  lea     rcx, [rsp+14F0h+var_14D0]
0x140006db0  mov     rax, cs:g_pfnThrowPlatformException
0x140006db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006dbc  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140006dc1  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x140006dc6  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140006dcb  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
