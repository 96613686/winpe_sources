# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000cdac`
- end: `0x18000d057`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000cd30`

## callees

- `0x180002ff8`
- `0x180005954`
- `0x180006da8`
- `0x1800088f0`
- `0x180008f10`
- `0x180009004`
- `0x18000cdac`
- `0x180014020`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ce49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ce49`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000cfeb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000cfeb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000cf4f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000cf4f`

## string_xrefs

- `0x18000ce53`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  v27 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
  v28 = 5331;
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
0x18000cdac  push    rbp
0x18000cdae  push    rbx
0x18000cdaf  push    rsi
0x18000cdb0  push    rdi
0x18000cdb1  push    r14
0x18000cdb3  push    r15
0x18000cdb5  lea     rbp, [rsp-13C8h]
0x18000cdbd  mov     eax, 14C8h
0x18000cdc2  call    _alloca_probe
0x18000cdc7  sub     rsp, rax
0x18000cdca  mov     rsi, rcx
0x18000cdcd  mov     rdi, [rbp+13F0h+arg_28]
0x18000cdd4  xor     r15d, r15d
0x18000cdd7  cmp     cs:g_pfnThrowPlatformException, r15
0x18000cdde  setnz   r14b
0x18000cde2  xor     edx, edx; Val
0x18000cde4  mov     r8d, 98h; Size
0x18000cdea  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000cdef  call    memset_0
0x18000cdf4  nop
0x18000cdf5  mov     [rbp+13F0h+OutputString], r15w
0x18000cdfd  mov     [rbp+13F0h+var_1430], r15b
0x18000ce01  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000ce08  mov     ecx, [rdx]; this
0x18000ce0a  mov     [rsp+14F0h+var_14C8], ecx
0x18000ce0e  mov     eax, [rdx+4]
0x18000ce11  mov     [rsp+14F0h+var_14C4], eax
0x18000ce15  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000ce1a  mov     ebx, eax
0x18000ce1c  mov     dword ptr [rsp+14F0h+var_14D0], r15d
0x18000ce21  mov     ecx, r15d
0x18000ce24  lea     eax, [r15+8]
0x18000ce28  cmp     dword ptr [rdx+8], 1
0x18000ce2c  cmovz   ecx, eax
0x18000ce2f  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000ce33  lea     ecx, [rax-7]
0x18000ce36  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000ce3e  inc     ecx
0x18000ce40  mov     [rsp+14F0h+var_14C0], ecx
0x18000ce44  mov     [rsp+14F0h+var_14B8], r15
0x18000ce49  call    cs:__imp_GetCurrentThreadId
0x18000ce4f  mov     [rsp+14F0h+var_14B0], eax
0x18000ce53  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ce5a  mov     [rsp+14F0h+var_1498], rax
0x18000ce5f  mov     [rsp+14F0h+var_1490], 14D3h
0x18000ce67  mov     [rsp+14F0h+var_148C], ebx
0x18000ce6b  mov     [rsp+14F0h+var_14A8], r15
0x18000ce70  mov     [rsp+14F0h+var_14A0], r15
0x18000ce75  mov     [rbp+13F0h+var_1448], rdi
0x18000ce79  mov     [rbp+13F0h+var_1440], rsi
0x18000ce7d  mov     [rsp+14F0h+var_1488], r15
0x18000ce82  xorps   xmm0, xmm0
0x18000ce85  xor     eax, eax
0x18000ce87  movups  [rbp+13F0h+var_1468], xmm0
0x18000ce8b  mov     [rbp+13F0h+var_1458], rax
0x18000ce8f  xorps   xmm1, xmm1
0x18000ce92  movups  [rsp+14F0h+var_1480], xmm1
0x18000ce97  mov     [rbp+13F0h+var_1470], rax
0x18000ce9b  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000cea2  test    rax, rax
0x18000cea5  jz      short loc_18000CEB2
0x18000cea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ceac  mov     [rbp+13F0h+var_1450], rax
0x18000ceb0  jmp     short loc_18000CEB6
0x18000ceb2  mov     [rbp+13F0h+var_1450], r15
0x18000ceb6  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000cebd  test    rax, rax
0x18000cec0  jz      short loc_18000CECC
0x18000cec2  lea     rcx, [rsp+14F0h+var_14D0]
0x18000cec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cecc  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000ced3  test    rax, rax
0x18000ced6  jz      short loc_18000CEEC
0x18000ced8  mov     r8d, 400h
0x18000cede  lea     rdx, [rbp+13F0h+var_1430]
0x18000cee2  lea     rcx, [rsp+14F0h+var_14D0]
0x18000cee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ceec  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000cef3  test    rax, rax
0x18000cef6  jz      short loc_18000CF02
0x18000cef8  lea     rcx, [rsp+14F0h+var_14D0]
0x18000cefd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf02  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000cf09  test    rax, rax
0x18000cf0c  jz      short loc_18000CF24
0x18000cf0e  test    r14b, r14b
0x18000cf11  jnz     short loc_18000CF24
0x18000cf13  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000cf18  jnz     short loc_18000CF24
0x18000cf1a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000cf1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf24  cmp     [rsp+14F0h+var_14C8], r15d
0x18000cf29  jl      short loc_18000CF31
0x18000cf2b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000cf31  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000cf38  jnz     short loc_18000CF59
0x18000cf3a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000cf41  test    rax, rax
0x18000cf44  jz      short loc_18000CF4F
0x18000cf46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf4b  test    al, al
0x18000cf4d  jmp     short loc_18000CF57
0x18000cf4f  call    cs:__imp_IsDebuggerPresent
0x18000cf55  test    eax, eax
0x18000cf57  jz      short loc_18000CF62
0x18000cf59  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000cf5e  mov     bl, 1
0x18000cf60  jz      short loc_18000CF65
0x18000cf62  mov     bl, r15b
0x18000cf65  test    r14b, r14b
0x18000cf68  jnz     short loc_18000CF94
0x18000cf6a  test    bl, bl
0x18000cf6c  jnz     short loc_18000CF94
0x18000cf6e  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cf75  test    rax, rax
0x18000cf78  jz      short loc_18000CFF1
0x18000cf7a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000cf81  jnz     short loc_18000CFF1
0x18000cf83  xor     r8d, r8d
0x18000cf86  xor     edx, edx
0x18000cf88  lea     rcx, [rsp+14F0h+var_14D0]
0x18000cf8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf92  jmp     short loc_18000CFF1
0x18000cf94  mov     edi, 800h
0x18000cf99  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cfa0  test    rax, rax
0x18000cfa3  jz      short loc_18000CFC2
0x18000cfa5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000cfac  jnz     short loc_18000CFC2
0x18000cfae  mov     r8d, edi
0x18000cfb1  lea     rdx, [rbp+13F0h+OutputString]
0x18000cfb8  lea     rcx, [rsp+14F0h+var_14D0]
0x18000cfbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfc2  cmp     [rbp+13F0h+OutputString], r15w
0x18000cfca  jnz     short loc_18000CFE0
0x18000cfcc  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000cfd1  mov     rdx, rdi; unsigned __int16 *
0x18000cfd4  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000cfdb  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000cfe0  test    bl, bl
0x18000cfe2  jz      short loc_18000CFF1
0x18000cfe4  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000cfeb  call    cs:__imp_OutputDebugStringW
0x18000cff1  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000cff6  jnz     short loc_18000D001
0x18000cff8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000cfff  jz      short loc_18000D013
0x18000d001  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000d008  test    rax, rax
0x18000d00b  jz      short loc_18000D013
0x18000d00d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d012  nop
0x18000d013  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000d018  jz      short loc_18000D025
0x18000d01a  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000d01f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000d025  test    r14b, r14b
0x18000d028  jz      short loc_18000D042
0x18000d02a  lea     rdx, [rbp+13F0h+OutputString]
0x18000d031  lea     rcx, [rsp+14F0h+var_14D0]
0x18000d036  mov     rax, cs:g_pfnThrowPlatformException
0x18000d03d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d042  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000d047  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000d04c  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000d051  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
