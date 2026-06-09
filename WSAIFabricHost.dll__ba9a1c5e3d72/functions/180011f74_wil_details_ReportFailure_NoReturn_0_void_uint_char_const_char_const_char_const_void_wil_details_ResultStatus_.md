# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180011f74`
- end: `0x18001225a`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `742`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *, char)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180011d78`

## callees

- `0x180005758`
- `0x18000a024`
- `0x18000acb4`
- `0x18000b024`
- `0x18000baf4`
- `0x18000be80`
- `0x18000c008`
- `0x180011f74`
- `0x18007f280`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012048`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012048`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800121e5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800121e5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180012148`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180012148`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8,
        char a9)
{
  bool v12; // di
  _WORD *v13; // r8
  int v14; // r13d
  int v15; // ecx
  __int64 v16; // rdx
  const struct wil::FailureInfo *v17; // rdx
  wil::details::in1diag3 *v18; // rcx
  const struct wil::FailureInfo *v19; // r9
  bool v20; // zf
  char v21; // bl
  const struct wil::FailureInfo *v22; // rdx
  int v23; // [rsp+20h] [rbp-E0h] BYREF
  int v24; // [rsp+24h] [rbp-DCh]
  int v25; // [rsp+28h] [rbp-D8h]
  int v26; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v27; // [rsp+30h] [rbp-D0h]
  _WORD *v28; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v30; // [rsp+48h] [rbp-B8h]
  __int64 v31; // [rsp+50h] [rbp-B0h]
  __int64 v32; // [rsp+58h] [rbp-A8h]
  int v33; // [rsp+60h] [rbp-A0h]
  int v34; // [rsp+64h] [rbp-9Ch]
  __int64 v35; // [rsp+68h] [rbp-98h]
  __int128 v36; // [rsp+70h] [rbp-90h]
  __int64 v37; // [rsp+80h] [rbp-80h]
  __int128 v38; // [rsp+88h] [rbp-78h]
  __int64 v39; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v41; // [rsp+A8h] [rbp-58h]
  __int64 v42; // [rsp+B0h] [rbp-50h]
  char v43[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v12 = (a9 & 2) == 0 && g_pfnThrowPlatformException;
  memset_0(&v23, 0, 0x98u);
  OutputString[0] = 0;
  v43[0] = 0;
  v25 = *a7;
  v26 = a7[1];
  v14 = wil::details::RecordException((wil::details *)(unsigned int)v25, (int)a7);
  v23 = (int)v13;
  v15 = (int)v13;
  if ( *(_DWORD *)(v16 + 8) == 1 )
    v15 = (_DWORD)v13 + 8;
  v24 = v15;
  v27 = _InterlockedExchangeAdd(&`wil::details::LogFailure'::`2'::s_failureId, (_DWORD)v13 + 1) + 1;
  if ( !a8 || (v20 = *a8 == (unsigned __int16)v13, v28 = a8, v20) )
    v28 = v13;
  CurrentThreadId = GetCurrentThreadId();
  v32 = a3;
  v33 = a2;
  v34 = v14;
  v30 = 0;
  v31 = 0;
  v41 = a6;
  v42 = a1;
  v35 = 0;
  v38 = 0;
  v39 = 0;
  v36 = 0;
  v37 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v18);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v23);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v23, v43, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v23);
  if ( wil::details::g_pfnOriginateCallback && !v12 && (v24 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v23);
  if ( v25 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v18);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v20 = !IsDebuggerPresent())
      : (v20 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v18) == 0),
        v20)
    || (v21 = 1, (v24 & 2) != 0) )
  {
    v21 = 0;
  }
  if ( v12 || v21 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v23, v19);
    if ( v21 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v23, 0, 0);
  }
  if ( ((v24 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v18);
  if ( (v24 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v23, v17);
  if ( v12 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v23, OutputString);
  if ( (a9 & 2) != 0 )
    wil::RethrowCaughtException(v18);
  wil::ThrowResultException((wil *)&v23, v17);
  wil::details::WilFailFast((wil::details *)&v23, v22);
}

```

## disassembly

```asm
0x180011f74  mov     [rsp-8+arg_18], rbx
0x180011f79  push    rbp
0x180011f7a  push    rsi
0x180011f7b  push    rdi
0x180011f7c  push    r12
0x180011f7e  push    r13
0x180011f80  push    r14
0x180011f82  push    r15
0x180011f84  lea     rbp, [rsp-13C0h]
0x180011f8c  mov     eax, 14C0h
0x180011f91  call    _alloca_probe
0x180011f96  sub     rsp, rax
0x180011f99  mov     r15, r8
0x180011f9c  mov     r14d, edx
0x180011f9f  mov     rbx, rcx
0x180011fa2  mov     r12, [rbp+13F0h+arg_28]
0x180011fa9  mov     esi, [rbp+13F0h+arg_40]
0x180011faf  and     esi, 2
0x180011fb2  jnz     short loc_180011FC3
0x180011fb4  cmp     cs:g_pfnThrowPlatformException, 0
0x180011fbc  jz      short loc_180011FC3
0x180011fbe  mov     dil, 1
0x180011fc1  jmp     short loc_180011FC6
0x180011fc3  xor     dil, dil
0x180011fc6  xor     edx, edx; Val
0x180011fc8  mov     r8d, 98h; Size
0x180011fce  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180011fd3  call    memset_0
0x180011fd8  nop
0x180011fd9  xor     r8d, r8d
0x180011fdc  mov     [rbp+13F0h+OutputString], r8w
0x180011fe4  mov     [rbp+13F0h+var_1430], r8b
0x180011fe8  mov     rdx, [rbp+13F0h+arg_30]; int
0x180011fef  mov     ecx, [rdx]; this
0x180011ff1  mov     [rsp+14F0h+var_14C8], ecx
0x180011ff5  mov     eax, [rdx+4]
0x180011ff8  mov     [rsp+14F0h+var_14C4], eax
0x180011ffc  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180012001  mov     r13d, eax
0x180012004  mov     dword ptr [rsp+14F0h+var_14D0], r8d
0x180012009  mov     ecx, r8d
0x18001200c  lea     eax, [r8+8]
0x180012010  cmp     dword ptr [rdx+8], 1
0x180012014  cmovz   ecx, eax
0x180012017  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18001201b  lea     ecx, [rax-7]
0x18001201e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180012026  inc     ecx
0x180012028  mov     [rsp+14F0h+var_14C0], ecx
0x18001202c  mov     rcx, [rbp+13F0h+arg_38]
0x180012033  test    rcx, rcx
0x180012036  jz      short loc_180012043
0x180012038  cmp     [rcx], r8w
0x18001203c  mov     [rsp+14F0h+var_14B8], rcx
0x180012041  jnz     short loc_180012048
0x180012043  mov     [rsp+14F0h+var_14B8], r8
0x180012048  call    cs:__imp_GetCurrentThreadId
0x18001204e  mov     [rsp+14F0h+var_14B0], eax
0x180012052  mov     [rsp+14F0h+var_1498], r15
0x180012057  mov     [rsp+14F0h+var_1490], r14d
0x18001205c  mov     [rsp+14F0h+var_148C], r13d
0x180012061  xor     r14d, r14d
0x180012064  mov     [rsp+14F0h+var_14A8], r14
0x180012069  mov     [rsp+14F0h+var_14A0], r14
0x18001206e  mov     [rbp+13F0h+var_1448], r12
0x180012072  mov     [rbp+13F0h+var_1440], rbx
0x180012076  mov     [rsp+14F0h+var_1488], r14
0x18001207b  xorps   xmm0, xmm0
0x18001207e  xor     eax, eax
0x180012080  movups  [rbp+13F0h+var_1468], xmm0
0x180012084  mov     [rbp+13F0h+var_1458], rax
0x180012088  xorps   xmm1, xmm1
0x18001208b  movups  [rsp+14F0h+var_1480], xmm1
0x180012090  mov     [rbp+13F0h+var_1470], rax
0x180012094  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001209b  test    rax, rax
0x18001209e  jz      short loc_1800120AB
0x1800120a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120a5  mov     [rbp+13F0h+var_1450], rax
0x1800120a9  jmp     short loc_1800120AF
0x1800120ab  mov     [rbp+13F0h+var_1450], r14
0x1800120af  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800120b6  test    rax, rax
0x1800120b9  jz      short loc_1800120C5
0x1800120bb  lea     rcx, [rsp+14F0h+var_14D0]
0x1800120c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120c5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800120cc  test    rax, rax
0x1800120cf  jz      short loc_1800120E5
0x1800120d1  mov     r8d, 400h
0x1800120d7  lea     rdx, [rbp+13F0h+var_1430]
0x1800120db  lea     rcx, [rsp+14F0h+var_14D0]
0x1800120e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120e5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800120ec  test    rax, rax
0x1800120ef  jz      short loc_1800120FB
0x1800120f1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800120f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120fb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180012102  test    rax, rax
0x180012105  jz      short loc_18001211D
0x180012107  test    dil, dil
0x18001210a  jnz     short loc_18001211D
0x18001210c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180012111  jnz     short loc_18001211D
0x180012113  lea     rcx, [rsp+14F0h+var_14D0]
0x180012118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001211d  cmp     [rsp+14F0h+var_14C8], r14d
0x180012122  jl      short loc_18001212A
0x180012124  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001212a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r14b; bool wil::g_fIsDebuggerPresent
0x180012131  jnz     short loc_180012152
0x180012133  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001213a  test    rax, rax
0x18001213d  jz      short loc_180012148
0x18001213f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012144  test    al, al
0x180012146  jmp     short loc_180012150
0x180012148  call    cs:__imp_IsDebuggerPresent
0x18001214e  test    eax, eax
0x180012150  jz      short loc_18001215B
0x180012152  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180012157  mov     bl, 1
0x180012159  jz      short loc_18001215E
0x18001215b  mov     bl, r14b
0x18001215e  test    dil, dil
0x180012161  jnz     short loc_18001218D
0x180012163  test    bl, bl
0x180012165  jnz     short loc_18001218D
0x180012167  mov     rax, cs:g_pfnResultLoggingCallback
0x18001216e  test    rax, rax
0x180012171  jz      short loc_1800121EB
0x180012173  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r14b; bool wil::details::g_resultMessageCallbackSet
0x18001217a  jnz     short loc_1800121EB
0x18001217c  xor     r8d, r8d
0x18001217f  xor     edx, edx
0x180012181  lea     rcx, [rsp+14F0h+var_14D0]
0x180012186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001218b  jmp     short loc_1800121EB
0x18001218d  mov     r15d, 800h
0x180012193  mov     rax, cs:g_pfnResultLoggingCallback
0x18001219a  test    rax, rax
0x18001219d  jz      short loc_1800121BC
0x18001219f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r14b; bool wil::details::g_resultMessageCallbackSet
0x1800121a6  jnz     short loc_1800121BC
0x1800121a8  mov     r8d, r15d
0x1800121ab  lea     rdx, [rbp+13F0h+OutputString]
0x1800121b2  lea     rcx, [rsp+14F0h+var_14D0]
0x1800121b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121bc  cmp     [rbp+13F0h+OutputString], r14w
0x1800121c4  jnz     short loc_1800121DA
0x1800121c6  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800121cb  mov     rdx, r15; wchar_t *
0x1800121ce  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800121d5  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800121da  test    bl, bl
0x1800121dc  jz      short loc_1800121EB
0x1800121de  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800121e5  call    cs:__imp_OutputDebugStringW
0x1800121eb  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800121f0  jnz     short loc_1800121FB
0x1800121f2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r14b; bool wil::g_fBreakOnFailure
0x1800121f9  jz      short loc_18001220D
0x1800121fb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180012202  test    rax, rax
0x180012205  jz      short loc_18001220D
0x180012207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001220c  nop
0x18001220d  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180012212  jz      short loc_18001221F
0x180012214  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180012219  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001221f  test    dil, dil
0x180012222  jz      short loc_18001223C
0x180012224  lea     rdx, [rbp+13F0h+OutputString]
0x18001222b  lea     rcx, [rsp+14F0h+var_14D0]
0x180012230  mov     rax, cs:g_pfnThrowPlatformException
0x180012237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001223c  test    esi, esi
0x18001223e  jz      short loc_180012245
0x180012240  call    ?RethrowCaughtException@wil@@YAXXZ; wil::RethrowCaughtException(void)
0x180012245  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001224a  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18001224f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180012254  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
