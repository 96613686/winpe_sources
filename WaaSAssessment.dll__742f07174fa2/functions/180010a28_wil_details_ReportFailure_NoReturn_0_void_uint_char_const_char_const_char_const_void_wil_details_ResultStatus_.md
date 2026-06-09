# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180010a28`
- end: `0x180010cd1`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800109ac`

## callees

- `0x18000a684`
- `0x18000ee64`
- `0x18000f34c`
- `0x18000f604`
- `0x18000f6e0`
- `0x180010a28`
- `0x18001972e`
- `0x180019820`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010ac4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010ac4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180010c66`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180010c66`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180010bca`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180010bca`

## string_xrefs

- `0x180010adc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
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
  __int64 v26; // [rsp+38h] [rbp-C8h]
  DWORD v27; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h]
  const char *v30; // [rsp+58h] [rbp-A8h]
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

  v8 = g_pfnThrowPlatformException != 0;
  memset_0(&v21, 0, 0x98u);
  OutputString[0] = 0;
  v41[0] = 0;
  v9 = a7[1];
  v23 = *a7;
  v24 = v9;
  v10 = wil::details::RecordException((wil::details *)(unsigned int)v23, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v21 = 0;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v22 = v13;
  v26 = 0;
  v25 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v31 = 4088;
  v27 = CurrentThreadId;
  v32 = v12;
  v30 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
  v37 = 0;
  v35 = 0;
  v28 = 0;
  v29 = 0;
  v39 = a6;
  v40 = a1;
  v33 = 0;
  v36 = 0;
  v34 = 0;
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
  if ( wil::details::g_pfnOriginateCallback && !v8 && (v22 & 2) == 0 )
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
  if ( v8 || v19 )
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
  if ( v8 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v21, OutputString);
  wil::ThrowResultException((wil *)&v21, v15);
  wil::details::WilFailFast((wil::details *)&v21, v20);
}

```

## disassembly

```asm
0x180010a28  push    rbp
0x180010a2a  push    rbx
0x180010a2b  push    rsi
0x180010a2c  push    rdi
0x180010a2d  push    r14
0x180010a2f  push    r15
0x180010a31  lea     rbp, [rsp-13C8h]
0x180010a39  mov     eax, 14C8h
0x180010a3e  call    _alloca_probe
0x180010a43  sub     rsp, rax
0x180010a46  mov     rdi, [rbp+13F0h+arg_28]
0x180010a4d  mov     rsi, rcx
0x180010a50  xor     r15d, r15d
0x180010a53  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180010a58  cmp     cs:g_pfnThrowPlatformException, r15
0x180010a5f  mov     r8d, 98h; Size
0x180010a65  setnz   r14b
0x180010a69  xor     edx, edx; Val
0x180010a6b  call    memset_0
0x180010a70  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180010a77  mov     [rbp+13F0h+OutputString], r15w
0x180010a7f  mov     [rbp+13F0h+var_1430], r15b
0x180010a83  mov     ecx, [rdx]; this
0x180010a85  mov     eax, [rdx+4]
0x180010a88  mov     [rsp+14F0h+var_14C8], ecx
0x180010a8c  mov     [rsp+14F0h+var_14C4], eax
0x180010a90  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180010a95  cmp     dword ptr [rdx+8], 1
0x180010a99  mov     ebx, eax
0x180010a9b  lea     eax, [r15+8]
0x180010a9f  mov     dword ptr [rsp+14F0h+var_14D0], r15d
0x180010aa4  mov     ecx, r15d
0x180010aa7  cmovz   ecx, eax
0x180010aaa  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180010aae  lea     ecx, [rax-7]
0x180010ab1  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180010ab9  inc     ecx
0x180010abb  mov     [rsp+14F0h+var_14B8], r15
0x180010ac0  mov     [rsp+14F0h+var_14C0], ecx
0x180010ac4  call    cs:__imp_GetCurrentThreadId
0x180010aca  xorps   xmm0, xmm0
0x180010acd  mov     [rsp+14F0h+var_1490], 0FF8h
0x180010ad5  mov     [rsp+14F0h+var_14B0], eax
0x180010ad9  xorps   xmm1, xmm1
0x180010adc  lea     rax, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010ae3  mov     [rsp+14F0h+var_148C], ebx
0x180010ae7  mov     [rsp+14F0h+var_1498], rax
0x180010aec  xor     eax, eax
0x180010aee  mov     [rbp+13F0h+var_1458], rax
0x180010af2  mov     [rbp+13F0h+var_1470], rax
0x180010af6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180010afd  mov     [rsp+14F0h+var_14A8], r15
0x180010b02  mov     [rsp+14F0h+var_14A0], r15
0x180010b07  mov     [rbp+13F0h+var_1448], rdi
0x180010b0b  mov     [rbp+13F0h+var_1440], rsi
0x180010b0f  mov     [rsp+14F0h+var_1488], r15
0x180010b14  movups  [rbp+13F0h+var_1468], xmm0
0x180010b18  movups  [rsp+14F0h+var_1480], xmm1
0x180010b1d  test    rax, rax
0x180010b20  jz      short loc_180010B2D
0x180010b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b27  mov     [rbp+13F0h+var_1450], rax
0x180010b2b  jmp     short loc_180010B31
0x180010b2d  mov     [rbp+13F0h+var_1450], r15
0x180010b31  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180010b38  test    rax, rax
0x180010b3b  jz      short loc_180010B47
0x180010b3d  lea     rcx, [rsp+14F0h+var_14D0]
0x180010b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b47  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180010b4e  test    rax, rax
0x180010b51  jz      short loc_180010B67
0x180010b53  mov     r8d, 400h
0x180010b59  lea     rdx, [rbp+13F0h+var_1430]
0x180010b5d  lea     rcx, [rsp+14F0h+var_14D0]
0x180010b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b67  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180010b6e  test    rax, rax
0x180010b71  jz      short loc_180010B7D
0x180010b73  lea     rcx, [rsp+14F0h+var_14D0]
0x180010b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b7d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180010b84  test    rax, rax
0x180010b87  jz      short loc_180010B9F
0x180010b89  test    r14b, r14b
0x180010b8c  jnz     short loc_180010B9F
0x180010b8e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180010b93  jnz     short loc_180010B9F
0x180010b95  lea     rcx, [rsp+14F0h+var_14D0]
0x180010b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b9f  cmp     [rsp+14F0h+var_14C8], r15d
0x180010ba4  jl      short loc_180010BAC
0x180010ba6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180010bac  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180010bb3  jnz     short loc_180010BD4
0x180010bb5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180010bbc  test    rax, rax
0x180010bbf  jz      short loc_180010BCA
0x180010bc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bc6  test    al, al
0x180010bc8  jmp     short loc_180010BD2
0x180010bca  call    cs:__imp_IsDebuggerPresent
0x180010bd0  test    eax, eax
0x180010bd2  jz      short loc_180010BDD
0x180010bd4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180010bd9  mov     bl, 1
0x180010bdb  jz      short loc_180010BE0
0x180010bdd  mov     bl, r15b
0x180010be0  test    r14b, r14b
0x180010be3  jnz     short loc_180010C0F
0x180010be5  test    bl, bl
0x180010be7  jnz     short loc_180010C0F
0x180010be9  mov     rax, cs:g_pfnResultLoggingCallback
0x180010bf0  test    rax, rax
0x180010bf3  jz      short loc_180010C6C
0x180010bf5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180010bfc  jnz     short loc_180010C6C
0x180010bfe  xor     r8d, r8d
0x180010c01  lea     rcx, [rsp+14F0h+var_14D0]
0x180010c06  xor     edx, edx
0x180010c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c0d  jmp     short loc_180010C6C
0x180010c0f  mov     rax, cs:g_pfnResultLoggingCallback
0x180010c16  mov     edi, 800h
0x180010c1b  test    rax, rax
0x180010c1e  jz      short loc_180010C3D
0x180010c20  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180010c27  jnz     short loc_180010C3D
0x180010c29  mov     r8d, edi
0x180010c2c  lea     rdx, [rbp+13F0h+OutputString]
0x180010c33  lea     rcx, [rsp+14F0h+var_14D0]
0x180010c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c3d  cmp     [rbp+13F0h+OutputString], r15w
0x180010c45  jnz     short loc_180010C5B
0x180010c47  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180010c4c  mov     rdx, rdi; unsigned __int16 *
0x180010c4f  lea     rcx, [rbp+13F0h+OutputString]; this
0x180010c56  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180010c5b  test    bl, bl
0x180010c5d  jz      short loc_180010C6C
0x180010c5f  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180010c66  call    cs:__imp_OutputDebugStringW
0x180010c6c  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180010c71  jnz     short loc_180010C7C
0x180010c73  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180010c7a  jz      short loc_180010C8D
0x180010c7c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180010c83  test    rax, rax
0x180010c86  jz      short loc_180010C8D
0x180010c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c8d  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180010c92  jz      short loc_180010C9F
0x180010c94  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180010c99  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180010c9f  test    r14b, r14b
0x180010ca2  jz      short loc_180010CBC
0x180010ca4  mov     rax, cs:g_pfnThrowPlatformException
0x180010cab  lea     rdx, [rbp+13F0h+OutputString]
0x180010cb2  lea     rcx, [rsp+14F0h+var_14D0]
0x180010cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cbc  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180010cc1  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180010cc6  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180010ccb  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
