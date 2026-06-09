# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180005824`
- end: `0x180005acf`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `683`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1800057a8`

## callees

- `0x180001f4a`
- `0x180003604`
- `0x18000449c`
- `0x1800050ec`
- `0x180005410`
- `0x1800054ec`
- `0x180005824`
- `0x180006170`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800058c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800058c1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005a63`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005a63`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800059c7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800059c7`

## string_xrefs

- `0x1800058cb`: `onecore\vm\dv\net\nvsp\agent\service\nvagentservice.cpp`

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
  v27 = "onecore\\vm\\dv\\net\\nvsp\\agent\\service\\nvagentservice.cpp";
  v28 = 262;
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
0x180005824  push    rbp
0x180005826  push    rbx
0x180005827  push    rsi
0x180005828  push    rdi
0x180005829  push    r14
0x18000582b  push    r15
0x18000582d  lea     rbp, [rsp-13C8h]
0x180005835  mov     eax, 14C8h
0x18000583a  call    _alloca_probe
0x18000583f  sub     rsp, rax
0x180005842  mov     rsi, rcx
0x180005845  mov     rdi, [rbp+13F0h+arg_28]
0x18000584c  xor     r15d, r15d
0x18000584f  cmp     cs:g_pfnThrowPlatformException, r15
0x180005856  setnz   r14b
0x18000585a  xor     edx, edx; Val
0x18000585c  mov     r8d, 98h; Size
0x180005862  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180005867  call    memset_0
0x18000586c  nop
0x18000586d  mov     [rbp+13F0h+OutputString], r15w
0x180005875  mov     [rbp+13F0h+var_1430], r15b
0x180005879  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180005880  mov     ecx, [rdx]; this
0x180005882  mov     [rsp+14F0h+var_14C8], ecx
0x180005886  mov     eax, [rdx+4]
0x180005889  mov     [rsp+14F0h+var_14C4], eax
0x18000588d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005892  mov     ebx, eax
0x180005894  mov     dword ptr [rsp+14F0h+var_14D0], r15d
0x180005899  mov     ecx, r15d
0x18000589c  lea     eax, [r15+8]
0x1800058a0  cmp     dword ptr [rdx+8], 1
0x1800058a4  cmovz   ecx, eax
0x1800058a7  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800058ab  lea     ecx, [rax-7]
0x1800058ae  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800058b6  inc     ecx
0x1800058b8  mov     [rsp+14F0h+var_14C0], ecx
0x1800058bc  mov     [rsp+14F0h+var_14B8], r15
0x1800058c1  call    cs:__imp_GetCurrentThreadId
0x1800058c7  mov     [rsp+14F0h+var_14B0], eax
0x1800058cb  lea     rax, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\nvsp\\agent\\serv"...
0x1800058d2  mov     [rsp+14F0h+var_1498], rax
0x1800058d7  mov     [rsp+14F0h+var_1490], 106h
0x1800058df  mov     [rsp+14F0h+var_148C], ebx
0x1800058e3  mov     [rsp+14F0h+var_14A8], r15
0x1800058e8  mov     [rsp+14F0h+var_14A0], r15
0x1800058ed  mov     [rbp+13F0h+var_1448], rdi
0x1800058f1  mov     [rbp+13F0h+var_1440], rsi
0x1800058f5  mov     [rsp+14F0h+var_1488], r15
0x1800058fa  xorps   xmm0, xmm0
0x1800058fd  xor     eax, eax
0x1800058ff  movups  [rbp+13F0h+var_1468], xmm0
0x180005903  mov     [rbp+13F0h+var_1458], rax
0x180005907  xorps   xmm1, xmm1
0x18000590a  movups  [rsp+14F0h+var_1480], xmm1
0x18000590f  mov     [rbp+13F0h+var_1470], rax
0x180005913  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000591a  test    rax, rax
0x18000591d  jz      short loc_18000592A
0x18000591f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005924  mov     [rbp+13F0h+var_1450], rax
0x180005928  jmp     short loc_18000592E
0x18000592a  mov     [rbp+13F0h+var_1450], r15
0x18000592e  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005935  test    rax, rax
0x180005938  jz      short loc_180005944
0x18000593a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000593f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005944  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000594b  test    rax, rax
0x18000594e  jz      short loc_180005964
0x180005950  mov     r8d, 400h
0x180005956  lea     rdx, [rbp+13F0h+var_1430]
0x18000595a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000595f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005964  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000596b  test    rax, rax
0x18000596e  jz      short loc_18000597A
0x180005970  lea     rcx, [rsp+14F0h+var_14D0]
0x180005975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000597a  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005981  test    rax, rax
0x180005984  jz      short loc_18000599C
0x180005986  test    r14b, r14b
0x180005989  jnz     short loc_18000599C
0x18000598b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005990  jnz     short loc_18000599C
0x180005992  lea     rcx, [rsp+14F0h+var_14D0]
0x180005997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000599c  cmp     [rsp+14F0h+var_14C8], r15d
0x1800059a1  jl      short loc_1800059A9
0x1800059a3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800059a9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800059b0  jnz     short loc_1800059D1
0x1800059b2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800059b9  test    rax, rax
0x1800059bc  jz      short loc_1800059C7
0x1800059be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059c3  test    al, al
0x1800059c5  jmp     short loc_1800059CF
0x1800059c7  call    cs:__imp_IsDebuggerPresent
0x1800059cd  test    eax, eax
0x1800059cf  jz      short loc_1800059DA
0x1800059d1  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800059d6  mov     bl, 1
0x1800059d8  jz      short loc_1800059DD
0x1800059da  mov     bl, r15b
0x1800059dd  test    r14b, r14b
0x1800059e0  jnz     short loc_180005A0C
0x1800059e2  test    bl, bl
0x1800059e4  jnz     short loc_180005A0C
0x1800059e6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800059ed  test    rax, rax
0x1800059f0  jz      short loc_180005A69
0x1800059f2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800059f9  jnz     short loc_180005A69
0x1800059fb  xor     r8d, r8d
0x1800059fe  xor     edx, edx
0x180005a00  lea     rcx, [rsp+14F0h+var_14D0]
0x180005a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a0a  jmp     short loc_180005A69
0x180005a0c  mov     edi, 800h
0x180005a11  mov     rax, cs:g_pfnResultLoggingCallback
0x180005a18  test    rax, rax
0x180005a1b  jz      short loc_180005A3A
0x180005a1d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005a24  jnz     short loc_180005A3A
0x180005a26  mov     r8d, edi
0x180005a29  lea     rdx, [rbp+13F0h+OutputString]
0x180005a30  lea     rcx, [rsp+14F0h+var_14D0]
0x180005a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a3a  cmp     [rbp+13F0h+OutputString], r15w
0x180005a42  jnz     short loc_180005A58
0x180005a44  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180005a49  mov     rdx, rdi; unsigned __int16 *
0x180005a4c  lea     rcx, [rbp+13F0h+OutputString]; this
0x180005a53  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005a58  test    bl, bl
0x180005a5a  jz      short loc_180005A69
0x180005a5c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180005a63  call    cs:__imp_OutputDebugStringW
0x180005a69  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180005a6e  jnz     short loc_180005A79
0x180005a70  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180005a77  jz      short loc_180005A8B
0x180005a79  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005a80  test    rax, rax
0x180005a83  jz      short loc_180005A8B
0x180005a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a8a  nop
0x180005a8b  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180005a90  jz      short loc_180005A9D
0x180005a92  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005a97  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005a9d  test    r14b, r14b
0x180005aa0  jz      short loc_180005ABA
0x180005aa2  lea     rdx, [rbp+13F0h+OutputString]
0x180005aa9  lea     rcx, [rsp+14F0h+var_14D0]
0x180005aae  mov     rax, cs:g_pfnThrowPlatformException
0x180005ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aba  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005abf  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180005ac4  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005ac9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
