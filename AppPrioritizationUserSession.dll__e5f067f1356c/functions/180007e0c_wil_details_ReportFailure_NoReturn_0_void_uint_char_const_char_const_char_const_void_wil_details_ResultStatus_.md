# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180007e0c`
- end: `0x1800080b7`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180007ab0`

## callees

- `0x1800032a4`
- `0x180004d84`
- `0x180005d30`
- `0x180006d70`
- `0x180007090`
- `0x18000716c`
- `0x180007e0c`
- `0x18000bec0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007ea9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007ea9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007faf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007faf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000804b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000804b`

## string_xrefs

- `0x180007eb3`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v8; // r14
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  char v16; // bl
  const struct wil::FailureInfo *v17; // rdx
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  __int64 v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  const char *v27; // [rsp+58h] [rbp-A8h]
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

  v8 = g_pfnThrowPlatformException != 0;
  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v9 = wil::details::RecordException((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 0;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v19 = v10;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h";
  v28 = 7368;
  v29 = v9;
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
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && !v8 && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v16 = 1, (v19 & 2) != 0) )
  {
    v16 = 0;
  }
  if ( v8 || v16 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v14);
    if ( v16 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v12);
  if ( v8 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v18, OutputString);
  wil::ThrowResultException((wil *)&v18, v12);
  wil::details::WilFailFast((wil::details *)&v18, v17);
}

```

## disassembly

```asm
0x180007e0c  push    rbp
0x180007e0e  push    rbx
0x180007e0f  push    rsi
0x180007e10  push    rdi
0x180007e11  push    r14
0x180007e13  push    r15
0x180007e15  lea     rbp, [rsp-13C8h]
0x180007e1d  mov     eax, 14C8h
0x180007e22  call    _alloca_probe
0x180007e27  sub     rsp, rax
0x180007e2a  mov     rsi, rcx
0x180007e2d  mov     rdi, [rbp+13F0h+arg_28]
0x180007e34  xor     r15d, r15d
0x180007e37  cmp     cs:g_pfnThrowPlatformException, r15
0x180007e3e  setnz   r14b
0x180007e42  xor     edx, edx; Val
0x180007e44  mov     r8d, 98h; Size
0x180007e4a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180007e4f  call    memset_0
0x180007e54  nop
0x180007e55  mov     [rbp+13F0h+OutputString], r15w
0x180007e5d  mov     [rbp+13F0h+var_1430], r15b
0x180007e61  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180007e68  mov     ecx, [rdx]; this
0x180007e6a  mov     [rsp+14F0h+var_14C8], ecx
0x180007e6e  mov     eax, [rdx+4]
0x180007e71  mov     [rsp+14F0h+var_14C4], eax
0x180007e75  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180007e7a  mov     ebx, eax
0x180007e7c  mov     dword ptr [rsp+14F0h+var_14D0], r15d
0x180007e81  mov     ecx, r15d
0x180007e84  lea     eax, [r15+8]
0x180007e88  cmp     dword ptr [rdx+8], 1
0x180007e8c  cmovz   ecx, eax
0x180007e8f  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180007e93  lea     ecx, [rax-7]
0x180007e96  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007e9e  inc     ecx
0x180007ea0  mov     [rsp+14F0h+var_14C0], ecx
0x180007ea4  mov     [rsp+14F0h+var_14B8], r15
0x180007ea9  call    cs:__imp_GetCurrentThreadId
0x180007eaf  mov     [rsp+14F0h+var_14B0], eax
0x180007eb3  lea     rax, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007eba  mov     [rsp+14F0h+var_1498], rax
0x180007ebf  mov     [rsp+14F0h+var_1490], 1CC8h
0x180007ec7  mov     [rsp+14F0h+var_148C], ebx
0x180007ecb  mov     [rsp+14F0h+var_14A8], r15
0x180007ed0  mov     [rsp+14F0h+var_14A0], r15
0x180007ed5  mov     [rbp+13F0h+var_1448], rdi
0x180007ed9  mov     [rbp+13F0h+var_1440], rsi
0x180007edd  mov     [rsp+14F0h+var_1488], r15
0x180007ee2  xorps   xmm0, xmm0
0x180007ee5  xor     eax, eax
0x180007ee7  movups  [rbp+13F0h+var_1468], xmm0
0x180007eeb  mov     [rbp+13F0h+var_1458], rax
0x180007eef  xorps   xmm1, xmm1
0x180007ef2  movups  [rsp+14F0h+var_1480], xmm1
0x180007ef7  mov     [rbp+13F0h+var_1470], rax
0x180007efb  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007f02  test    rax, rax
0x180007f05  jz      short loc_180007F12
0x180007f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f0c  mov     [rbp+13F0h+var_1450], rax
0x180007f10  jmp     short loc_180007F16
0x180007f12  mov     [rbp+13F0h+var_1450], r15
0x180007f16  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007f1d  test    rax, rax
0x180007f20  jz      short loc_180007F2C
0x180007f22  lea     rcx, [rsp+14F0h+var_14D0]
0x180007f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f2c  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007f33  test    rax, rax
0x180007f36  jz      short loc_180007F4C
0x180007f38  mov     r8d, 400h
0x180007f3e  lea     rdx, [rbp+13F0h+var_1430]
0x180007f42  lea     rcx, [rsp+14F0h+var_14D0]
0x180007f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f4c  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007f53  test    rax, rax
0x180007f56  jz      short loc_180007F62
0x180007f58  lea     rcx, [rsp+14F0h+var_14D0]
0x180007f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f62  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007f69  test    rax, rax
0x180007f6c  jz      short loc_180007F84
0x180007f6e  test    r14b, r14b
0x180007f71  jnz     short loc_180007F84
0x180007f73  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007f78  jnz     short loc_180007F84
0x180007f7a  lea     rcx, [rsp+14F0h+var_14D0]
0x180007f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f84  cmp     [rsp+14F0h+var_14C8], r15d
0x180007f89  jl      short loc_180007F91
0x180007f8b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007f91  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180007f98  jnz     short loc_180007FB9
0x180007f9a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007fa1  test    rax, rax
0x180007fa4  jz      short loc_180007FAF
0x180007fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fab  test    al, al
0x180007fad  jmp     short loc_180007FB7
0x180007faf  call    cs:__imp_IsDebuggerPresent
0x180007fb5  test    eax, eax
0x180007fb7  jz      short loc_180007FC2
0x180007fb9  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007fbe  mov     bl, 1
0x180007fc0  jz      short loc_180007FC5
0x180007fc2  mov     bl, r15b
0x180007fc5  test    r14b, r14b
0x180007fc8  jnz     short loc_180007FF4
0x180007fca  test    bl, bl
0x180007fcc  jnz     short loc_180007FF4
0x180007fce  mov     rax, cs:g_pfnResultLoggingCallback
0x180007fd5  test    rax, rax
0x180007fd8  jz      short loc_180008051
0x180007fda  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007fe1  jnz     short loc_180008051
0x180007fe3  xor     r8d, r8d
0x180007fe6  xor     edx, edx
0x180007fe8  lea     rcx, [rsp+14F0h+var_14D0]
0x180007fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ff2  jmp     short loc_180008051
0x180007ff4  mov     edi, 800h
0x180007ff9  mov     rax, cs:g_pfnResultLoggingCallback
0x180008000  test    rax, rax
0x180008003  jz      short loc_180008022
0x180008005  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000800c  jnz     short loc_180008022
0x18000800e  mov     r8d, edi
0x180008011  lea     rdx, [rbp+13F0h+OutputString]
0x180008018  lea     rcx, [rsp+14F0h+var_14D0]
0x18000801d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008022  cmp     [rbp+13F0h+OutputString], r15w
0x18000802a  jnz     short loc_180008040
0x18000802c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180008031  mov     rdx, rdi; unsigned __int16 *
0x180008034  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000803b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008040  test    bl, bl
0x180008042  jz      short loc_180008051
0x180008044  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000804b  call    cs:__imp_OutputDebugStringW
0x180008051  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180008056  jnz     short loc_180008061
0x180008058  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000805f  jz      short loc_180008073
0x180008061  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008068  test    rax, rax
0x18000806b  jz      short loc_180008073
0x18000806d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008072  nop
0x180008073  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180008078  jz      short loc_180008085
0x18000807a  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000807f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180008085  test    r14b, r14b
0x180008088  jz      short loc_1800080A2
0x18000808a  lea     rdx, [rbp+13F0h+OutputString]
0x180008091  lea     rcx, [rsp+14F0h+var_14D0]
0x180008096  mov     rax, cs:g_pfnThrowPlatformException
0x18000809d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080a2  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800080a7  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x1800080ac  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800080b1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
