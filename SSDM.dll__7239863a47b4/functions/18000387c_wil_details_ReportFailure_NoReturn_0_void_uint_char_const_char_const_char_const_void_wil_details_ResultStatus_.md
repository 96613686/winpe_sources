# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x18000387c`
- end: `0x180003b28`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003014`

## callees

- `0x18000387c`
- `0x180005778`
- `0x180006b20`
- `0x180006ec4`
- `0x180006f08`
- `0x1800071d4`
- `0x18000e962`
- `0x18000ea50`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003925`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003925`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003a20`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003a20`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003abc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003abc`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v10; // r12
  int v11; // ebx
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  char v18; // bl
  const struct wil::FailureInfo *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v10 = g_pfnThrowPlatformException != 0;
  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v11 = wil::details::RecordException((wil::details *)(unsigned int)v22, (int)a7);
  v20 = 0;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v21 = v12;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v11;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && !v10 && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v18 = 1, (v21 & 2) != 0) )
  {
    v18 = 0;
  }
  if ( v10 || v18 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v14);
  if ( v10 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v20, OutputString);
  wil::ThrowResultException((wil *)&v20, v14);
  wil::details::WilFailFast((wil::details *)&v20, v19);
}

```

## disassembly

```asm
0x18000387c  mov     [rsp-8+arg_18], rbx
0x180003881  push    rbp
0x180003882  push    rsi
0x180003883  push    rdi
0x180003884  push    r12
0x180003886  push    r13
0x180003888  push    r14
0x18000388a  push    r15
0x18000388c  lea     rbp, [rsp-13C0h]
0x180003894  mov     eax, 14C0h
0x180003899  call    _alloca_probe
0x18000389e  sub     rsp, rax
0x1800038a1  mov     r14, r8
0x1800038a4  mov     esi, edx
0x1800038a6  mov     r15, rcx
0x1800038a9  mov     rdi, [rbp+13F0h+arg_28]
0x1800038b0  xor     r13d, r13d
0x1800038b3  cmp     cs:g_pfnThrowPlatformException, r13
0x1800038ba  setnz   r12b
0x1800038be  xor     edx, edx; Val
0x1800038c0  mov     r8d, 98h; Size
0x1800038c6  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800038cb  call    memset_0
0x1800038d0  nop
0x1800038d1  mov     [rbp+13F0h+OutputString], r13w
0x1800038d9  mov     [rbp+13F0h+var_1430], r13b
0x1800038dd  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800038e4  mov     ecx, [rdx]; this
0x1800038e6  mov     [rsp+14F0h+var_14C8], ecx
0x1800038ea  mov     eax, [rdx+4]
0x1800038ed  mov     [rsp+14F0h+var_14C4], eax
0x1800038f1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800038f6  mov     ebx, eax
0x1800038f8  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x1800038fd  mov     ecx, r13d
0x180003900  lea     eax, [r13+8]
0x180003904  cmp     dword ptr [rdx+8], 1
0x180003908  cmovz   ecx, eax
0x18000390b  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000390f  lea     ecx, [rax-7]
0x180003912  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000391a  inc     ecx
0x18000391c  mov     [rsp+14F0h+var_14C0], ecx
0x180003920  mov     [rsp+14F0h+var_14B8], r13
0x180003925  call    cs:__imp_GetCurrentThreadId
0x18000392b  mov     [rsp+14F0h+var_14B0], eax
0x18000392f  mov     [rsp+14F0h+var_1498], r14
0x180003934  mov     [rsp+14F0h+var_1490], esi
0x180003938  mov     [rsp+14F0h+var_148C], ebx
0x18000393c  mov     [rsp+14F0h+var_14A8], r13
0x180003941  mov     [rsp+14F0h+var_14A0], r13
0x180003946  mov     [rbp+13F0h+var_1448], rdi
0x18000394a  mov     [rbp+13F0h+var_1440], r15
0x18000394e  mov     [rsp+14F0h+var_1488], r13
0x180003953  xorps   xmm0, xmm0
0x180003956  xor     eax, eax
0x180003958  movups  [rbp+13F0h+var_1468], xmm0
0x18000395c  mov     [rbp+13F0h+var_1458], rax
0x180003960  xorps   xmm1, xmm1
0x180003963  movups  [rsp+14F0h+var_1480], xmm1
0x180003968  mov     [rbp+13F0h+var_1470], rax
0x18000396c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003973  test    rax, rax
0x180003976  jz      short loc_180003983
0x180003978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000397d  mov     [rbp+13F0h+var_1450], rax
0x180003981  jmp     short loc_180003987
0x180003983  mov     [rbp+13F0h+var_1450], r13
0x180003987  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000398e  test    rax, rax
0x180003991  jz      short loc_18000399D
0x180003993  lea     rcx, [rsp+14F0h+var_14D0]
0x180003998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000399d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800039a4  test    rax, rax
0x1800039a7  jz      short loc_1800039BD
0x1800039a9  mov     r8d, 400h
0x1800039af  lea     rdx, [rbp+13F0h+var_1430]
0x1800039b3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800039b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039bd  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800039c4  test    rax, rax
0x1800039c7  jz      short loc_1800039D3
0x1800039c9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800039ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039d3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800039da  test    rax, rax
0x1800039dd  jz      short loc_1800039F5
0x1800039df  test    r12b, r12b
0x1800039e2  jnz     short loc_1800039F5
0x1800039e4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800039e9  jnz     short loc_1800039F5
0x1800039eb  lea     rcx, [rsp+14F0h+var_14D0]
0x1800039f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039f5  cmp     [rsp+14F0h+var_14C8], r13d
0x1800039fa  jl      short loc_180003A02
0x1800039fc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003a02  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180003a09  jnz     short loc_180003A2A
0x180003a0b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003a12  test    rax, rax
0x180003a15  jz      short loc_180003A20
0x180003a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a1c  test    al, al
0x180003a1e  jmp     short loc_180003A28
0x180003a20  call    cs:__imp_IsDebuggerPresent
0x180003a26  test    eax, eax
0x180003a28  jz      short loc_180003A33
0x180003a2a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003a2f  mov     bl, 1
0x180003a31  jz      short loc_180003A36
0x180003a33  mov     bl, r13b
0x180003a36  test    r12b, r12b
0x180003a39  jnz     short loc_180003A65
0x180003a3b  test    bl, bl
0x180003a3d  jnz     short loc_180003A65
0x180003a3f  mov     rax, cs:g_pfnResultLoggingCallback
0x180003a46  test    rax, rax
0x180003a49  jz      short loc_180003AC2
0x180003a4b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003a52  jnz     short loc_180003AC2
0x180003a54  xor     r8d, r8d
0x180003a57  xor     edx, edx
0x180003a59  lea     rcx, [rsp+14F0h+var_14D0]
0x180003a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a63  jmp     short loc_180003AC2
0x180003a65  mov     edi, 800h
0x180003a6a  mov     rax, cs:g_pfnResultLoggingCallback
0x180003a71  test    rax, rax
0x180003a74  jz      short loc_180003A93
0x180003a76  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003a7d  jnz     short loc_180003A93
0x180003a7f  mov     r8d, edi
0x180003a82  lea     rdx, [rbp+13F0h+OutputString]
0x180003a89  lea     rcx, [rsp+14F0h+var_14D0]
0x180003a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a93  cmp     [rbp+13F0h+OutputString], r13w
0x180003a9b  jnz     short loc_180003AB1
0x180003a9d  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003aa2  mov     rdx, rdi; wchar_t *
0x180003aa5  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003aac  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180003ab1  test    bl, bl
0x180003ab3  jz      short loc_180003AC2
0x180003ab5  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003abc  call    cs:__imp_OutputDebugStringW
0x180003ac2  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003ac7  jnz     short loc_180003AD2
0x180003ac9  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180003ad0  jz      short loc_180003AE4
0x180003ad2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003ad9  test    rax, rax
0x180003adc  jz      short loc_180003AE4
0x180003ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ae3  nop
0x180003ae4  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003ae9  jz      short loc_180003AF6
0x180003aeb  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003af0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003af6  test    r12b, r12b
0x180003af9  jz      short loc_180003B13
0x180003afb  lea     rdx, [rbp+13F0h+OutputString]
0x180003b02  lea     rcx, [rsp+14F0h+var_14D0]
0x180003b07  mov     rax, cs:g_pfnThrowPlatformException
0x180003b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b13  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003b18  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180003b1d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003b22  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
