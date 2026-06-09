# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000b688`
- end: `0x18000b94d`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000b348`

## callees

- `0x180007018`
- `0x180009064`
- `0x180009e30`
- `0x18000ac44`
- `0x18000af90`
- `0x18000b06c`
- `0x18000b688`
- `0x180082e30`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b749`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b749`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000b8e1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000b8e1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b845`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b845`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      g_pfnResultLoggingCallback(&v21, OutputString, 2048, v17);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v21, v17);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v21, 0, 0, v17);
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
0x18000b688  mov     [rsp-8+arg_18], rbx
0x18000b68d  push    rbp
0x18000b68e  push    rsi
0x18000b68f  push    rdi
0x18000b690  push    r12
0x18000b692  push    r13
0x18000b694  push    r14
0x18000b696  push    r15
0x18000b698  lea     rbp, [rsp-13C0h]
0x18000b6a0  mov     eax, 14C0h
0x18000b6a5  call    _alloca_probe
0x18000b6aa  sub     rsp, rax
0x18000b6ad  mov     r14, r8
0x18000b6b0  mov     esi, edx
0x18000b6b2  mov     rbx, rcx
0x18000b6b5  mov     r15, [rbp+13F0h+arg_28]
0x18000b6bc  xor     r13d, r13d
0x18000b6bf  cmp     cs:g_pfnThrowPlatformException, r13
0x18000b6c6  setnz   dil
0x18000b6ca  xor     edx, edx; Val
0x18000b6cc  mov     r8d, 98h; Size
0x18000b6d2  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000b6d7  call    memset_0
0x18000b6dc  nop
0x18000b6dd  mov     [rbp+13F0h+OutputString], r13w
0x18000b6e5  mov     [rbp+13F0h+var_1430], r13b
0x18000b6e9  mov     rdx, [rbp+13F0h+arg_30]; int
0x18000b6f0  mov     ecx, [rdx]; this
0x18000b6f2  mov     [rsp+14F0h+var_14C8], ecx
0x18000b6f6  mov     eax, [rdx+4]
0x18000b6f9  mov     [rsp+14F0h+var_14C4], eax
0x18000b6fd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000b702  mov     r12d, eax
0x18000b705  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000b70a  mov     ecx, r13d
0x18000b70d  lea     eax, [r13+8]
0x18000b711  cmp     dword ptr [rdx+8], 1
0x18000b715  cmovz   ecx, eax
0x18000b718  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000b71c  lea     ecx, [rax-7]
0x18000b71f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000b727  inc     ecx
0x18000b729  mov     [rsp+14F0h+var_14C0], ecx
0x18000b72d  mov     rcx, [rbp+13F0h+arg_38]
0x18000b734  test    rcx, rcx
0x18000b737  jz      short loc_18000B744
0x18000b739  cmp     [rcx], r13w
0x18000b73d  mov     [rsp+14F0h+var_14B8], rcx
0x18000b742  jnz     short loc_18000B749
0x18000b744  mov     [rsp+14F0h+var_14B8], r13
0x18000b749  call    cs:__imp_GetCurrentThreadId
0x18000b74f  mov     [rsp+14F0h+var_14B0], eax
0x18000b753  mov     [rsp+14F0h+var_1498], r14
0x18000b758  mov     [rsp+14F0h+var_1490], esi
0x18000b75c  mov     [rsp+14F0h+var_148C], r12d
0x18000b761  mov     [rsp+14F0h+var_14A8], r13
0x18000b766  mov     [rsp+14F0h+var_14A0], r13
0x18000b76b  mov     [rbp+13F0h+var_1448], r15
0x18000b76f  mov     [rbp+13F0h+var_1440], rbx
0x18000b773  mov     [rsp+14F0h+var_1488], r13
0x18000b778  xorps   xmm0, xmm0
0x18000b77b  xor     eax, eax
0x18000b77d  movups  [rbp+13F0h+var_1468], xmm0
0x18000b781  mov     [rbp+13F0h+var_1458], rax
0x18000b785  xorps   xmm1, xmm1
0x18000b788  movups  [rsp+14F0h+var_1480], xmm1
0x18000b78d  mov     [rbp+13F0h+var_1470], rax
0x18000b791  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000b798  test    rax, rax
0x18000b79b  jz      short loc_18000B7A8
0x18000b79d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7a2  mov     [rbp+13F0h+var_1450], rax
0x18000b7a6  jmp     short loc_18000B7AC
0x18000b7a8  mov     [rbp+13F0h+var_1450], r13
0x18000b7ac  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000b7b3  test    rax, rax
0x18000b7b6  jz      short loc_18000B7C2
0x18000b7b8  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b7bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7c2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000b7c9  test    rax, rax
0x18000b7cc  jz      short loc_18000B7E2
0x18000b7ce  mov     r8d, 400h
0x18000b7d4  lea     rdx, [rbp+13F0h+var_1430]
0x18000b7d8  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b7dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7e2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b7e9  test    rax, rax
0x18000b7ec  jz      short loc_18000B7F8
0x18000b7ee  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b7f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7f8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b7ff  test    rax, rax
0x18000b802  jz      short loc_18000B81A
0x18000b804  test    dil, dil
0x18000b807  jnz     short loc_18000B81A
0x18000b809  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000b80e  jnz     short loc_18000B81A
0x18000b810  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b81a  cmp     [rsp+14F0h+var_14C8], r13d
0x18000b81f  jl      short loc_18000B827
0x18000b821  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000b827  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000b82e  jnz     short loc_18000B84F
0x18000b830  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000b837  test    rax, rax
0x18000b83a  jz      short loc_18000B845
0x18000b83c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b841  test    al, al
0x18000b843  jmp     short loc_18000B84D
0x18000b845  call    cs:__imp_IsDebuggerPresent
0x18000b84b  test    eax, eax
0x18000b84d  jz      short loc_18000B858
0x18000b84f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000b854  mov     bl, 1
0x18000b856  jz      short loc_18000B85B
0x18000b858  mov     bl, r13b
0x18000b85b  test    dil, dil
0x18000b85e  jnz     short loc_18000B88A
0x18000b860  test    bl, bl
0x18000b862  jnz     short loc_18000B88A
0x18000b864  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b86b  test    rax, rax
0x18000b86e  jz      short loc_18000B8E7
0x18000b870  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000b877  jnz     short loc_18000B8E7
0x18000b879  xor     r8d, r8d
0x18000b87c  xor     edx, edx
0x18000b87e  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b888  jmp     short loc_18000B8E7
0x18000b88a  mov     esi, 800h
0x18000b88f  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b896  test    rax, rax
0x18000b899  jz      short loc_18000B8B8
0x18000b89b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000b8a2  jnz     short loc_18000B8B8
0x18000b8a4  mov     r8d, esi
0x18000b8a7  lea     rdx, [rbp+13F0h+OutputString]
0x18000b8ae  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b8b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8b8  cmp     [rbp+13F0h+OutputString], r13w
0x18000b8c0  jnz     short loc_18000B8D6
0x18000b8c2  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000b8c7  mov     rdx, rsi; unsigned __int16 *
0x18000b8ca  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000b8d1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000b8d6  test    bl, bl
0x18000b8d8  jz      short loc_18000B8E7
0x18000b8da  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000b8e1  call    cs:__imp_OutputDebugStringW
0x18000b8e7  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000b8ec  jnz     short loc_18000B8F7
0x18000b8ee  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000b8f5  jz      short loc_18000B909
0x18000b8f7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000b8fe  test    rax, rax
0x18000b901  jz      short loc_18000B909
0x18000b903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b908  nop
0x18000b909  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000b90e  jz      short loc_18000B91B
0x18000b910  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000b915  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000b91b  test    dil, dil
0x18000b91e  jz      short loc_18000B938
0x18000b920  lea     rdx, [rbp+13F0h+OutputString]
0x18000b927  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b92c  mov     rax, cs:g_pfnThrowPlatformException
0x18000b933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b938  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000b93d  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000b942  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000b947  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
