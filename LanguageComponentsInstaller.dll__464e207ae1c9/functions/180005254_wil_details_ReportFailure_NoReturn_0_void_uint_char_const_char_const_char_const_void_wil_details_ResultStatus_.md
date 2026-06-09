# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180005254`
- end: `0x180005500`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800049cc`

## callees

- `0x180004118`
- `0x180005254`
- `0x180007d64`
- `0x180008efc`
- `0x180009d20`
- `0x18000a0b0`
- `0x18000a364`
- `0x180027cb0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800052fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800052fd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800053f8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800053f8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005494`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005494`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v16);
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
0x180005254  mov     [rsp-8+arg_18], rbx
0x180005259  push    rbp
0x18000525a  push    rsi
0x18000525b  push    rdi
0x18000525c  push    r12
0x18000525e  push    r13
0x180005260  push    r14
0x180005262  push    r15
0x180005264  lea     rbp, [rsp-13C0h]
0x18000526c  mov     eax, 14C0h
0x180005271  call    _alloca_probe
0x180005276  sub     rsp, rax
0x180005279  mov     r14, r8
0x18000527c  mov     esi, edx
0x18000527e  mov     r15, rcx
0x180005281  mov     rdi, [rbp+13F0h+arg_28]
0x180005288  xor     r13d, r13d
0x18000528b  cmp     cs:g_pfnThrowPlatformException, r13
0x180005292  setnz   r12b
0x180005296  xor     edx, edx; Val
0x180005298  mov     r8d, 98h; Size
0x18000529e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800052a3  call    memset_0
0x1800052a8  nop
0x1800052a9  mov     [rbp+13F0h+OutputString], r13w
0x1800052b1  mov     [rbp+13F0h+var_1430], r13b
0x1800052b5  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800052bc  mov     ecx, [rdx]; this
0x1800052be  mov     [rsp+14F0h+var_14C8], ecx
0x1800052c2  mov     eax, [rdx+4]
0x1800052c5  mov     [rsp+14F0h+var_14C4], eax
0x1800052c9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800052ce  mov     ebx, eax
0x1800052d0  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x1800052d5  mov     ecx, r13d
0x1800052d8  lea     eax, [r13+8]
0x1800052dc  cmp     dword ptr [rdx+8], 1
0x1800052e0  cmovz   ecx, eax
0x1800052e3  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800052e7  lea     ecx, [rax-7]
0x1800052ea  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800052f2  inc     ecx
0x1800052f4  mov     [rsp+14F0h+var_14C0], ecx
0x1800052f8  mov     [rsp+14F0h+var_14B8], r13
0x1800052fd  call    cs:__imp_GetCurrentThreadId
0x180005303  mov     [rsp+14F0h+var_14B0], eax
0x180005307  mov     [rsp+14F0h+var_1498], r14
0x18000530c  mov     [rsp+14F0h+var_1490], esi
0x180005310  mov     [rsp+14F0h+var_148C], ebx
0x180005314  mov     [rsp+14F0h+var_14A8], r13
0x180005319  mov     [rsp+14F0h+var_14A0], r13
0x18000531e  mov     [rbp+13F0h+var_1448], rdi
0x180005322  mov     [rbp+13F0h+var_1440], r15
0x180005326  mov     [rsp+14F0h+var_1488], r13
0x18000532b  xorps   xmm0, xmm0
0x18000532e  xor     eax, eax
0x180005330  movups  [rbp+13F0h+var_1468], xmm0
0x180005334  mov     [rbp+13F0h+var_1458], rax
0x180005338  xorps   xmm1, xmm1
0x18000533b  movups  [rsp+14F0h+var_1480], xmm1
0x180005340  mov     [rbp+13F0h+var_1470], rax
0x180005344  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000534b  test    rax, rax
0x18000534e  jz      short loc_18000535B
0x180005350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005355  mov     [rbp+13F0h+var_1450], rax
0x180005359  jmp     short loc_18000535F
0x18000535b  mov     [rbp+13F0h+var_1450], r13
0x18000535f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005366  test    rax, rax
0x180005369  jz      short loc_180005375
0x18000536b  lea     rcx, [rsp+14F0h+var_14D0]
0x180005370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005375  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000537c  test    rax, rax
0x18000537f  jz      short loc_180005395
0x180005381  mov     r8d, 400h
0x180005387  lea     rdx, [rbp+13F0h+var_1430]
0x18000538b  lea     rcx, [rsp+14F0h+var_14D0]
0x180005390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005395  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000539c  test    rax, rax
0x18000539f  jz      short loc_1800053AB
0x1800053a1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800053a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053ab  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800053b2  test    rax, rax
0x1800053b5  jz      short loc_1800053CD
0x1800053b7  test    r12b, r12b
0x1800053ba  jnz     short loc_1800053CD
0x1800053bc  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800053c1  jnz     short loc_1800053CD
0x1800053c3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800053c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053cd  cmp     [rsp+14F0h+var_14C8], r13d
0x1800053d2  jl      short loc_1800053DA
0x1800053d4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800053da  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800053e1  jnz     short loc_180005402
0x1800053e3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800053ea  test    rax, rax
0x1800053ed  jz      short loc_1800053F8
0x1800053ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053f4  test    al, al
0x1800053f6  jmp     short loc_180005400
0x1800053f8  call    cs:__imp_IsDebuggerPresent
0x1800053fe  test    eax, eax
0x180005400  jz      short loc_18000540B
0x180005402  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005407  mov     bl, 1
0x180005409  jz      short loc_18000540E
0x18000540b  mov     bl, r13b
0x18000540e  test    r12b, r12b
0x180005411  jnz     short loc_18000543D
0x180005413  test    bl, bl
0x180005415  jnz     short loc_18000543D
0x180005417  mov     rax, cs:g_pfnResultLoggingCallback
0x18000541e  test    rax, rax
0x180005421  jz      short loc_18000549A
0x180005423  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000542a  jnz     short loc_18000549A
0x18000542c  xor     r8d, r8d
0x18000542f  xor     edx, edx
0x180005431  lea     rcx, [rsp+14F0h+var_14D0]
0x180005436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000543b  jmp     short loc_18000549A
0x18000543d  mov     edi, 800h
0x180005442  mov     rax, cs:g_pfnResultLoggingCallback
0x180005449  test    rax, rax
0x18000544c  jz      short loc_18000546B
0x18000544e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005455  jnz     short loc_18000546B
0x180005457  mov     r8d, edi
0x18000545a  lea     rdx, [rbp+13F0h+OutputString]
0x180005461  lea     rcx, [rsp+14F0h+var_14D0]
0x180005466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000546b  cmp     [rbp+13F0h+OutputString], r13w
0x180005473  jnz     short loc_180005489
0x180005475  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000547a  mov     rdx, rdi; unsigned __int16 *
0x18000547d  lea     rcx, [rbp+13F0h+OutputString]; this
0x180005484  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005489  test    bl, bl
0x18000548b  jz      short loc_18000549A
0x18000548d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180005494  call    cs:__imp_OutputDebugStringW
0x18000549a  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000549f  jnz     short loc_1800054AA
0x1800054a1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800054a8  jz      short loc_1800054BC
0x1800054aa  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800054b1  test    rax, rax
0x1800054b4  jz      short loc_1800054BC
0x1800054b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054bb  nop
0x1800054bc  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800054c1  jz      short loc_1800054CE
0x1800054c3  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800054c8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800054ce  test    r12b, r12b
0x1800054d1  jz      short loc_1800054EB
0x1800054d3  lea     rdx, [rbp+13F0h+OutputString]
0x1800054da  lea     rcx, [rsp+14F0h+var_14D0]
0x1800054df  mov     rax, cs:g_pfnThrowPlatformException
0x1800054e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054eb  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800054f0  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x1800054f5  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800054fa  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
