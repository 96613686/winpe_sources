# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1400059f0`
- end: `0x140005cb5`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400051ec`

## callees

- `0x140002ecc`
- `0x1400059f0`
- `0x1400097c4`
- `0x14000baf4`
- `0x14000d2a8`
- `0x14000d9f0`
- `0x14000e394`
- `0x140021f90`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005ab1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005ab1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005bad`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005bad`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005c49`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005c49`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
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
0x1400059f0  mov     [rsp-8+arg_18], rbx
0x1400059f5  push    rbp
0x1400059f6  push    rsi
0x1400059f7  push    rdi
0x1400059f8  push    r12
0x1400059fa  push    r13
0x1400059fc  push    r14
0x1400059fe  push    r15
0x140005a00  lea     rbp, [rsp-13C0h]
0x140005a08  mov     eax, 14C0h
0x140005a0d  call    _alloca_probe
0x140005a12  sub     rsp, rax
0x140005a15  mov     r14, r8
0x140005a18  mov     esi, edx
0x140005a1a  mov     rbx, rcx
0x140005a1d  mov     r15, [rbp+13F0h+arg_28]
0x140005a24  xor     r13d, r13d
0x140005a27  cmp     cs:g_pfnThrowPlatformException, r13
0x140005a2e  setnz   dil
0x140005a32  xor     edx, edx; Val
0x140005a34  mov     r8d, 98h; Size
0x140005a3a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140005a3f  call    memset_0
0x140005a44  nop
0x140005a45  mov     [rbp+13F0h+OutputString], r13w
0x140005a4d  mov     [rbp+13F0h+var_1430], r13b
0x140005a51  mov     rdx, [rbp+13F0h+arg_30]; int
0x140005a58  mov     ecx, [rdx]; this
0x140005a5a  mov     [rsp+14F0h+var_14C8], ecx
0x140005a5e  mov     eax, [rdx+4]
0x140005a61  mov     [rsp+14F0h+var_14C4], eax
0x140005a65  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140005a6a  mov     r12d, eax
0x140005a6d  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x140005a72  mov     ecx, r13d
0x140005a75  lea     eax, [r13+8]
0x140005a79  cmp     dword ptr [rdx+8], 1
0x140005a7d  cmovz   ecx, eax
0x140005a80  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140005a84  lea     ecx, [rax-7]
0x140005a87  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140005a8f  inc     ecx
0x140005a91  mov     [rsp+14F0h+var_14C0], ecx
0x140005a95  mov     rcx, [rbp+13F0h+arg_38]
0x140005a9c  test    rcx, rcx
0x140005a9f  jz      short loc_140005AAC
0x140005aa1  cmp     [rcx], r13w
0x140005aa5  mov     [rsp+14F0h+var_14B8], rcx
0x140005aaa  jnz     short loc_140005AB1
0x140005aac  mov     [rsp+14F0h+var_14B8], r13
0x140005ab1  call    cs:__imp_GetCurrentThreadId
0x140005ab7  mov     [rsp+14F0h+var_14B0], eax
0x140005abb  mov     [rsp+14F0h+var_1498], r14
0x140005ac0  mov     [rsp+14F0h+var_1490], esi
0x140005ac4  mov     [rsp+14F0h+var_148C], r12d
0x140005ac9  mov     [rsp+14F0h+var_14A8], r13
0x140005ace  mov     [rsp+14F0h+var_14A0], r13
0x140005ad3  mov     [rbp+13F0h+var_1448], r15
0x140005ad7  mov     [rbp+13F0h+var_1440], rbx
0x140005adb  mov     [rsp+14F0h+var_1488], r13
0x140005ae0  xorps   xmm0, xmm0
0x140005ae3  xor     eax, eax
0x140005ae5  movups  [rbp+13F0h+var_1468], xmm0
0x140005ae9  mov     [rbp+13F0h+var_1458], rax
0x140005aed  xorps   xmm1, xmm1
0x140005af0  movups  [rsp+14F0h+var_1480], xmm1
0x140005af5  mov     [rbp+13F0h+var_1470], rax
0x140005af9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140005b00  test    rax, rax
0x140005b03  jz      short loc_140005B10
0x140005b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b0a  mov     [rbp+13F0h+var_1450], rax
0x140005b0e  jmp     short loc_140005B14
0x140005b10  mov     [rbp+13F0h+var_1450], r13
0x140005b14  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140005b1b  test    rax, rax
0x140005b1e  jz      short loc_140005B2A
0x140005b20  lea     rcx, [rsp+14F0h+var_14D0]
0x140005b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b2a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140005b31  test    rax, rax
0x140005b34  jz      short loc_140005B4A
0x140005b36  mov     r8d, 400h
0x140005b3c  lea     rdx, [rbp+13F0h+var_1430]
0x140005b40  lea     rcx, [rsp+14F0h+var_14D0]
0x140005b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b4a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005b51  test    rax, rax
0x140005b54  jz      short loc_140005B60
0x140005b56  lea     rcx, [rsp+14F0h+var_14D0]
0x140005b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b60  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005b67  test    rax, rax
0x140005b6a  jz      short loc_140005B82
0x140005b6c  test    dil, dil
0x140005b6f  jnz     short loc_140005B82
0x140005b71  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140005b76  jnz     short loc_140005B82
0x140005b78  lea     rcx, [rsp+14F0h+var_14D0]
0x140005b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b82  cmp     [rsp+14F0h+var_14C8], r13d
0x140005b87  jl      short loc_140005B8F
0x140005b89  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140005b8f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140005b96  jnz     short loc_140005BB7
0x140005b98  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140005b9f  test    rax, rax
0x140005ba2  jz      short loc_140005BAD
0x140005ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ba9  test    al, al
0x140005bab  jmp     short loc_140005BB5
0x140005bad  call    cs:__imp_IsDebuggerPresent
0x140005bb3  test    eax, eax
0x140005bb5  jz      short loc_140005BC0
0x140005bb7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140005bbc  mov     bl, 1
0x140005bbe  jz      short loc_140005BC3
0x140005bc0  mov     bl, r13b
0x140005bc3  test    dil, dil
0x140005bc6  jnz     short loc_140005BF2
0x140005bc8  test    bl, bl
0x140005bca  jnz     short loc_140005BF2
0x140005bcc  mov     rax, cs:g_pfnResultLoggingCallback
0x140005bd3  test    rax, rax
0x140005bd6  jz      short loc_140005C4F
0x140005bd8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140005bdf  jnz     short loc_140005C4F
0x140005be1  xor     r8d, r8d
0x140005be4  xor     edx, edx
0x140005be6  lea     rcx, [rsp+14F0h+var_14D0]
0x140005beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005bf0  jmp     short loc_140005C4F
0x140005bf2  mov     esi, 800h
0x140005bf7  mov     rax, cs:g_pfnResultLoggingCallback
0x140005bfe  test    rax, rax
0x140005c01  jz      short loc_140005C20
0x140005c03  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140005c0a  jnz     short loc_140005C20
0x140005c0c  mov     r8d, esi
0x140005c0f  lea     rdx, [rbp+13F0h+OutputString]
0x140005c16  lea     rcx, [rsp+14F0h+var_14D0]
0x140005c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c20  cmp     [rbp+13F0h+OutputString], r13w
0x140005c28  jnz     short loc_140005C3E
0x140005c2a  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140005c2f  mov     rdx, rsi; unsigned __int16 *
0x140005c32  lea     rcx, [rbp+13F0h+OutputString]; this
0x140005c39  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140005c3e  test    bl, bl
0x140005c40  jz      short loc_140005C4F
0x140005c42  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140005c49  call    cs:__imp_OutputDebugStringW
0x140005c4f  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140005c54  jnz     short loc_140005C5F
0x140005c56  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140005c5d  jz      short loc_140005C71
0x140005c5f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140005c66  test    rax, rax
0x140005c69  jz      short loc_140005C71
0x140005c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c70  nop
0x140005c71  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140005c76  jz      short loc_140005C83
0x140005c78  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140005c7d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140005c83  test    dil, dil
0x140005c86  jz      short loc_140005CA0
0x140005c88  lea     rdx, [rbp+13F0h+OutputString]
0x140005c8f  lea     rcx, [rsp+14F0h+var_14D0]
0x140005c94  mov     rax, cs:g_pfnThrowPlatformException
0x140005c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ca0  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140005ca5  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x140005caa  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140005caf  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
