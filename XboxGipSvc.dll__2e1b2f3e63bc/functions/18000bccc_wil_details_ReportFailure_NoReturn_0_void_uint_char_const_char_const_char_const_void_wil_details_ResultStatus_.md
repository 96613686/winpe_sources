# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000bccc`
- end: `0x18000bf77`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `683`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000bc2c`

## callees

- `0x180002158`
- `0x180005088`
- `0x180005fb0`
- `0x18000687c`
- `0x180006958`
- `0x180008eec`
- `0x18000bccc`
- `0x180011440`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bd69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bd69`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000bf0b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000bf0b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000be6f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000be6f`

## string_xrefs

- `0x18000bd73`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
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
0x18000bccc  push    rbp
0x18000bcce  push    rbx
0x18000bccf  push    rsi
0x18000bcd0  push    rdi
0x18000bcd1  push    r14
0x18000bcd3  push    r15
0x18000bcd5  lea     rbp, [rsp-13C8h]
0x18000bcdd  mov     eax, 14C8h
0x18000bce2  call    _alloca_probe
0x18000bce7  sub     rsp, rax
0x18000bcea  mov     rsi, rcx
0x18000bced  mov     rdi, [rbp+13F0h+arg_28]
0x18000bcf4  xor     r15d, r15d
0x18000bcf7  cmp     cs:g_pfnThrowPlatformException, r15
0x18000bcfe  setnz   r14b
0x18000bd02  xor     edx, edx; Val
0x18000bd04  mov     r8d, 98h; Size
0x18000bd0a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000bd0f  call    memset_0
0x18000bd14  nop
0x18000bd15  mov     [rbp+13F0h+OutputString], r15w
0x18000bd1d  mov     [rbp+13F0h+var_1430], r15b
0x18000bd21  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000bd28  mov     ecx, [rdx]; this
0x18000bd2a  mov     [rsp+14F0h+var_14C8], ecx
0x18000bd2e  mov     eax, [rdx+4]
0x18000bd31  mov     [rsp+14F0h+var_14C4], eax
0x18000bd35  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000bd3a  mov     ebx, eax
0x18000bd3c  mov     dword ptr [rsp+14F0h+var_14D0], r15d
0x18000bd41  mov     ecx, r15d
0x18000bd44  lea     eax, [r15+8]
0x18000bd48  cmp     dword ptr [rdx+8], 1
0x18000bd4c  cmovz   ecx, eax
0x18000bd4f  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000bd53  lea     ecx, [rax-7]
0x18000bd56  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000bd5e  inc     ecx
0x18000bd60  mov     [rsp+14F0h+var_14C0], ecx
0x18000bd64  mov     [rsp+14F0h+var_14B8], r15
0x18000bd69  call    cs:__imp_GetCurrentThreadId
0x18000bd6f  mov     [rsp+14F0h+var_14B0], eax
0x18000bd73  lea     rax, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bd7a  mov     [rsp+14F0h+var_1498], rax
0x18000bd7f  mov     [rsp+14F0h+var_1490], 1CC8h
0x18000bd87  mov     [rsp+14F0h+var_148C], ebx
0x18000bd8b  mov     [rsp+14F0h+var_14A8], r15
0x18000bd90  mov     [rsp+14F0h+var_14A0], r15
0x18000bd95  mov     [rbp+13F0h+var_1448], rdi
0x18000bd99  mov     [rbp+13F0h+var_1440], rsi
0x18000bd9d  mov     [rsp+14F0h+var_1488], r15
0x18000bda2  xorps   xmm0, xmm0
0x18000bda5  xor     eax, eax
0x18000bda7  movups  [rbp+13F0h+var_1468], xmm0
0x18000bdab  mov     [rbp+13F0h+var_1458], rax
0x18000bdaf  xorps   xmm1, xmm1
0x18000bdb2  movups  [rsp+14F0h+var_1480], xmm1
0x18000bdb7  mov     [rbp+13F0h+var_1470], rax
0x18000bdbb  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000bdc2  test    rax, rax
0x18000bdc5  jz      short loc_18000BDD2
0x18000bdc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdcc  mov     [rbp+13F0h+var_1450], rax
0x18000bdd0  jmp     short loc_18000BDD6
0x18000bdd2  mov     [rbp+13F0h+var_1450], r15
0x18000bdd6  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000bddd  test    rax, rax
0x18000bde0  jz      short loc_18000BDEC
0x18000bde2  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bde7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdec  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000bdf3  test    rax, rax
0x18000bdf6  jz      short loc_18000BE0C
0x18000bdf8  mov     r8d, 400h
0x18000bdfe  lea     rdx, [rbp+13F0h+var_1430]
0x18000be02  lea     rcx, [rsp+14F0h+var_14D0]
0x18000be07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be0c  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000be13  test    rax, rax
0x18000be16  jz      short loc_18000BE22
0x18000be18  lea     rcx, [rsp+14F0h+var_14D0]
0x18000be1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be22  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000be29  test    rax, rax
0x18000be2c  jz      short loc_18000BE44
0x18000be2e  test    r14b, r14b
0x18000be31  jnz     short loc_18000BE44
0x18000be33  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000be38  jnz     short loc_18000BE44
0x18000be3a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000be3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be44  cmp     [rsp+14F0h+var_14C8], r15d
0x18000be49  jl      short loc_18000BE51
0x18000be4b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000be51  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000be58  jnz     short loc_18000BE79
0x18000be5a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000be61  test    rax, rax
0x18000be64  jz      short loc_18000BE6F
0x18000be66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be6b  test    al, al
0x18000be6d  jmp     short loc_18000BE77
0x18000be6f  call    cs:__imp_IsDebuggerPresent
0x18000be75  test    eax, eax
0x18000be77  jz      short loc_18000BE82
0x18000be79  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000be7e  mov     bl, 1
0x18000be80  jz      short loc_18000BE85
0x18000be82  mov     bl, r15b
0x18000be85  test    r14b, r14b
0x18000be88  jnz     short loc_18000BEB4
0x18000be8a  test    bl, bl
0x18000be8c  jnz     short loc_18000BEB4
0x18000be8e  mov     rax, cs:g_pfnResultLoggingCallback
0x18000be95  test    rax, rax
0x18000be98  jz      short loc_18000BF11
0x18000be9a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000bea1  jnz     short loc_18000BF11
0x18000bea3  xor     r8d, r8d
0x18000bea6  xor     edx, edx
0x18000bea8  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000beb2  jmp     short loc_18000BF11
0x18000beb4  mov     edi, 800h
0x18000beb9  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bec0  test    rax, rax
0x18000bec3  jz      short loc_18000BEE2
0x18000bec5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000becc  jnz     short loc_18000BEE2
0x18000bece  mov     r8d, edi
0x18000bed1  lea     rdx, [rbp+13F0h+OutputString]
0x18000bed8  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bedd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bee2  cmp     [rbp+13F0h+OutputString], r15w
0x18000beea  jnz     short loc_18000BF00
0x18000beec  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000bef1  mov     rdx, rdi; unsigned __int16 *
0x18000bef4  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000befb  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000bf00  test    bl, bl
0x18000bf02  jz      short loc_18000BF11
0x18000bf04  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000bf0b  call    cs:__imp_OutputDebugStringW
0x18000bf11  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000bf16  jnz     short loc_18000BF21
0x18000bf18  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000bf1f  jz      short loc_18000BF33
0x18000bf21  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000bf28  test    rax, rax
0x18000bf2b  jz      short loc_18000BF33
0x18000bf2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf32  nop
0x18000bf33  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000bf38  jz      short loc_18000BF45
0x18000bf3a  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000bf3f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000bf45  test    r14b, r14b
0x18000bf48  jz      short loc_18000BF62
0x18000bf4a  lea     rdx, [rbp+13F0h+OutputString]
0x18000bf51  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bf56  mov     rax, cs:g_pfnThrowPlatformException
0x18000bf5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf62  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000bf67  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000bf6c  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000bf71  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
