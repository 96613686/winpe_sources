# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180004cd8`
- end: `0x180004f9d`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004700`

## callees

- `0x180002dc4`
- `0x180003324`
- `0x180004cd8`
- `0x180006f10`
- `0x180007130`
- `0x180007170`
- `0x180007298`
- `0x1800173e0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d99`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004e95`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004e95`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004f31`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004f31`

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
0x180004cd8  mov     [rsp-8+arg_18], rbx
0x180004cdd  push    rbp
0x180004cde  push    rsi
0x180004cdf  push    rdi
0x180004ce0  push    r12
0x180004ce2  push    r13
0x180004ce4  push    r14
0x180004ce6  push    r15
0x180004ce8  lea     rbp, [rsp-13C0h]
0x180004cf0  mov     eax, 14C0h
0x180004cf5  call    _alloca_probe
0x180004cfa  sub     rsp, rax
0x180004cfd  mov     r14, r8
0x180004d00  mov     esi, edx
0x180004d02  mov     rbx, rcx
0x180004d05  mov     r15, [rbp+13F0h+arg_28]
0x180004d0c  xor     r13d, r13d
0x180004d0f  cmp     cs:g_pfnThrowPlatformException, r13
0x180004d16  setnz   dil
0x180004d1a  xor     edx, edx; Val
0x180004d1c  mov     r8d, 98h; Size
0x180004d22  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180004d27  call    memset_0
0x180004d2c  nop
0x180004d2d  mov     [rbp+13F0h+OutputString], r13w
0x180004d35  mov     [rbp+13F0h+var_1430], r13b
0x180004d39  mov     rdx, [rbp+13F0h+arg_30]; int
0x180004d40  mov     ecx, [rdx]; this
0x180004d42  mov     [rsp+14F0h+var_14C8], ecx
0x180004d46  mov     eax, [rdx+4]
0x180004d49  mov     [rsp+14F0h+var_14C4], eax
0x180004d4d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004d52  mov     r12d, eax
0x180004d55  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180004d5a  mov     ecx, r13d
0x180004d5d  lea     eax, [r13+8]
0x180004d61  cmp     dword ptr [rdx+8], 1
0x180004d65  cmovz   ecx, eax
0x180004d68  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180004d6c  lea     ecx, [rax-7]
0x180004d6f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004d77  inc     ecx
0x180004d79  mov     [rsp+14F0h+var_14C0], ecx
0x180004d7d  mov     rcx, [rbp+13F0h+arg_38]
0x180004d84  test    rcx, rcx
0x180004d87  jz      short loc_180004D94
0x180004d89  cmp     [rcx], r13w
0x180004d8d  mov     [rsp+14F0h+var_14B8], rcx
0x180004d92  jnz     short loc_180004D99
0x180004d94  mov     [rsp+14F0h+var_14B8], r13
0x180004d99  call    cs:__imp_GetCurrentThreadId
0x180004d9f  mov     [rsp+14F0h+var_14B0], eax
0x180004da3  mov     [rsp+14F0h+var_1498], r14
0x180004da8  mov     [rsp+14F0h+var_1490], esi
0x180004dac  mov     [rsp+14F0h+var_148C], r12d
0x180004db1  mov     [rsp+14F0h+var_14A8], r13
0x180004db6  mov     [rsp+14F0h+var_14A0], r13
0x180004dbb  mov     [rbp+13F0h+var_1448], r15
0x180004dbf  mov     [rbp+13F0h+var_1440], rbx
0x180004dc3  mov     [rsp+14F0h+var_1488], r13
0x180004dc8  xorps   xmm0, xmm0
0x180004dcb  xor     eax, eax
0x180004dcd  movups  [rbp+13F0h+var_1468], xmm0
0x180004dd1  mov     [rbp+13F0h+var_1458], rax
0x180004dd5  xorps   xmm1, xmm1
0x180004dd8  movups  [rsp+14F0h+var_1480], xmm1
0x180004ddd  mov     [rbp+13F0h+var_1470], rax
0x180004de1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004de8  test    rax, rax
0x180004deb  jz      short loc_180004DF8
0x180004ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004df2  mov     [rbp+13F0h+var_1450], rax
0x180004df6  jmp     short loc_180004DFC
0x180004df8  mov     [rbp+13F0h+var_1450], r13
0x180004dfc  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004e03  test    rax, rax
0x180004e06  jz      short loc_180004E12
0x180004e08  lea     rcx, [rsp+14F0h+var_14D0]
0x180004e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e12  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004e19  test    rax, rax
0x180004e1c  jz      short loc_180004E32
0x180004e1e  mov     r8d, 400h
0x180004e24  lea     rdx, [rbp+13F0h+var_1430]
0x180004e28  lea     rcx, [rsp+14F0h+var_14D0]
0x180004e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e32  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004e39  test    rax, rax
0x180004e3c  jz      short loc_180004E48
0x180004e3e  lea     rcx, [rsp+14F0h+var_14D0]
0x180004e43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e48  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004e4f  test    rax, rax
0x180004e52  jz      short loc_180004E6A
0x180004e54  test    dil, dil
0x180004e57  jnz     short loc_180004E6A
0x180004e59  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004e5e  jnz     short loc_180004E6A
0x180004e60  lea     rcx, [rsp+14F0h+var_14D0]
0x180004e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e6a  cmp     [rsp+14F0h+var_14C8], r13d
0x180004e6f  jl      short loc_180004E77
0x180004e71  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004e77  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180004e7e  jnz     short loc_180004E9F
0x180004e80  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004e87  test    rax, rax
0x180004e8a  jz      short loc_180004E95
0x180004e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e91  test    al, al
0x180004e93  jmp     short loc_180004E9D
0x180004e95  call    cs:__imp_IsDebuggerPresent
0x180004e9b  test    eax, eax
0x180004e9d  jz      short loc_180004EA8
0x180004e9f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004ea4  mov     bl, 1
0x180004ea6  jz      short loc_180004EAB
0x180004ea8  mov     bl, r13b
0x180004eab  test    dil, dil
0x180004eae  jnz     short loc_180004EDA
0x180004eb0  test    bl, bl
0x180004eb2  jnz     short loc_180004EDA
0x180004eb4  mov     rax, cs:g_pfnResultLoggingCallback
0x180004ebb  test    rax, rax
0x180004ebe  jz      short loc_180004F37
0x180004ec0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180004ec7  jnz     short loc_180004F37
0x180004ec9  xor     r8d, r8d
0x180004ecc  xor     edx, edx
0x180004ece  lea     rcx, [rsp+14F0h+var_14D0]
0x180004ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ed8  jmp     short loc_180004F37
0x180004eda  mov     esi, 800h
0x180004edf  mov     rax, cs:g_pfnResultLoggingCallback
0x180004ee6  test    rax, rax
0x180004ee9  jz      short loc_180004F08
0x180004eeb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180004ef2  jnz     short loc_180004F08
0x180004ef4  mov     r8d, esi
0x180004ef7  lea     rdx, [rbp+13F0h+OutputString]
0x180004efe  lea     rcx, [rsp+14F0h+var_14D0]
0x180004f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f08  cmp     [rbp+13F0h+OutputString], r13w
0x180004f10  jnz     short loc_180004F26
0x180004f12  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180004f17  mov     rdx, rsi; unsigned __int16 *
0x180004f1a  lea     rcx, [rbp+13F0h+OutputString]; this
0x180004f21  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004f26  test    bl, bl
0x180004f28  jz      short loc_180004F37
0x180004f2a  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180004f31  call    cs:__imp_OutputDebugStringW
0x180004f37  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180004f3c  jnz     short loc_180004F47
0x180004f3e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180004f45  jz      short loc_180004F59
0x180004f47  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004f4e  test    rax, rax
0x180004f51  jz      short loc_180004F59
0x180004f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f58  nop
0x180004f59  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180004f5e  jz      short loc_180004F6B
0x180004f60  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180004f65  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004f6b  test    dil, dil
0x180004f6e  jz      short loc_180004F88
0x180004f70  lea     rdx, [rbp+13F0h+OutputString]
0x180004f77  lea     rcx, [rsp+14F0h+var_14D0]
0x180004f7c  mov     rax, cs:g_pfnThrowPlatformException
0x180004f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f88  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180004f8d  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180004f92  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180004f97  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
