# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800067fc`
- end: `0x180006aa8`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180006490`

## callees

- `0x1800022ea`
- `0x180004074`
- `0x180004f44`
- `0x180005ce0`
- `0x180005fe0`
- `0x1800060bc`
- `0x1800067fc`
- `0x180011d10`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800068a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800068a5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800069a0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800069a0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006a3c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006a3c`

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
        int *a7)
{
  bool v9; // r15
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  char v17; // bl
  const struct wil::FailureInfo *v18; // rdx
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  __int64 v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v9 = g_pfnThrowPlatformException != 0;
  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v21 = *a7;
  v22 = a7[1];
  v10 = wil::details::RecordException((wil::details *)(unsigned int)v21, (int)a7);
  v19 = 0;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v20 = v11;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v24 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v28 = a3;
  v29 = a2;
  v30 = v10;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = 0;
  v31 = 0;
  v34 = 0;
  v35 = 0;
  v32 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && !v9 && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v17 = 1, (v20 & 2) != 0) )
  {
    v17 = 0;
  }
  if ( v9 || v17 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048, v15);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v19, v15);
    if ( v17 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v19, 0, 0, v15);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v13);
  if ( v9 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v19, OutputString);
  wil::ThrowResultException((wil *)&v19, v13);
  wil::details::WilFailFast((wil::details *)&v19, v18);
}

```

## disassembly

```asm
0x1800067fc  mov     [rsp-8+arg_0], rbx
0x180006801  mov     [rsp-8+arg_18], rsi
0x180006806  push    rbp
0x180006807  push    rdi
0x180006808  push    r12
0x18000680a  push    r14
0x18000680c  push    r15
0x18000680e  lea     rbp, [rsp-13C0h]
0x180006816  mov     eax, 14C0h
0x18000681b  call    _alloca_probe
0x180006820  sub     rsp, rax
0x180006823  mov     r14, r8
0x180006826  mov     esi, edx
0x180006828  mov     rdi, [rbp+13E0h+arg_28]
0x18000682f  xor     r12d, r12d
0x180006832  cmp     cs:g_pfnThrowPlatformException, r12
0x180006839  setnz   r15b
0x18000683d  xor     edx, edx; Val
0x18000683f  mov     r8d, 98h; Size
0x180006845  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x18000684a  call    memset_0
0x18000684f  nop
0x180006850  mov     [rbp+13E0h+OutputString], r12w
0x180006858  mov     [rbp+13E0h+var_1420], r12b
0x18000685c  mov     rdx, qword ptr [rbp+13E0h+arg_30]; int
0x180006863  mov     ecx, [rdx]; this
0x180006865  mov     [rsp+14E0h+var_14B8], ecx
0x180006869  mov     eax, [rdx+4]
0x18000686c  mov     [rsp+14E0h+var_14B4], eax
0x180006870  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006875  mov     ebx, eax
0x180006877  mov     dword ptr [rsp+14E0h+var_14C0], r12d
0x18000687c  mov     ecx, r12d
0x18000687f  lea     eax, [r12+8]
0x180006884  cmp     dword ptr [rdx+8], 1
0x180006888  cmovz   ecx, eax
0x18000688b  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x18000688f  lea     ecx, [rax-7]
0x180006892  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000689a  inc     ecx
0x18000689c  mov     [rsp+14E0h+var_14B0], ecx
0x1800068a0  mov     [rsp+14E0h+var_14A8], r12
0x1800068a5  call    cs:__imp_GetCurrentThreadId
0x1800068ab  mov     [rsp+14E0h+var_14A0], eax
0x1800068af  mov     [rsp+14E0h+var_1488], r14
0x1800068b4  mov     [rsp+14E0h+var_1480], esi
0x1800068b8  mov     [rsp+14E0h+var_147C], ebx
0x1800068bc  mov     [rsp+14E0h+var_1498], r12
0x1800068c1  mov     [rsp+14E0h+var_1490], r12
0x1800068c6  mov     [rbp+13E0h+var_1438], rdi
0x1800068ca  mov     [rbp+13E0h+var_1430], r12
0x1800068ce  mov     [rsp+14E0h+var_1478], r12
0x1800068d3  xorps   xmm0, xmm0
0x1800068d6  xor     eax, eax
0x1800068d8  movups  [rbp+13E0h+var_1458], xmm0
0x1800068dc  mov     [rbp+13E0h+var_1448], rax
0x1800068e0  xorps   xmm1, xmm1
0x1800068e3  movups  [rsp+14E0h+var_1470], xmm1
0x1800068e8  mov     [rbp+13E0h+var_1460], rax
0x1800068ec  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800068f3  test    rax, rax
0x1800068f6  jz      short loc_180006903
0x1800068f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068fd  mov     [rbp+13E0h+var_1440], rax
0x180006901  jmp     short loc_180006907
0x180006903  mov     [rbp+13E0h+var_1440], r12
0x180006907  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000690e  test    rax, rax
0x180006911  jz      short loc_18000691D
0x180006913  lea     rcx, [rsp+14E0h+var_14C0]
0x180006918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000691d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006924  test    rax, rax
0x180006927  jz      short loc_18000693D
0x180006929  mov     r8d, 400h
0x18000692f  lea     rdx, [rbp+13E0h+var_1420]
0x180006933  lea     rcx, [rsp+14E0h+var_14C0]
0x180006938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000693d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006944  test    rax, rax
0x180006947  jz      short loc_180006953
0x180006949  lea     rcx, [rsp+14E0h+var_14C0]
0x18000694e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006953  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000695a  test    rax, rax
0x18000695d  jz      short loc_180006975
0x18000695f  test    r15b, r15b
0x180006962  jnz     short loc_180006975
0x180006964  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180006969  jnz     short loc_180006975
0x18000696b  lea     rcx, [rsp+14E0h+var_14C0]
0x180006970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006975  cmp     [rsp+14E0h+var_14B8], r12d
0x18000697a  jl      short loc_180006982
0x18000697c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006982  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180006989  jnz     short loc_1800069AA
0x18000698b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006992  test    rax, rax
0x180006995  jz      short loc_1800069A0
0x180006997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000699c  test    al, al
0x18000699e  jmp     short loc_1800069A8
0x1800069a0  call    cs:__imp_IsDebuggerPresent
0x1800069a6  test    eax, eax
0x1800069a8  jz      short loc_1800069B3
0x1800069aa  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800069af  mov     bl, 1
0x1800069b1  jz      short loc_1800069B6
0x1800069b3  mov     bl, r12b
0x1800069b6  test    r15b, r15b
0x1800069b9  jnz     short loc_1800069E5
0x1800069bb  test    bl, bl
0x1800069bd  jnz     short loc_1800069E5
0x1800069bf  mov     rax, cs:g_pfnResultLoggingCallback
0x1800069c6  test    rax, rax
0x1800069c9  jz      short loc_180006A42
0x1800069cb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800069d2  jnz     short loc_180006A42
0x1800069d4  xor     r8d, r8d
0x1800069d7  xor     edx, edx
0x1800069d9  lea     rcx, [rsp+14E0h+var_14C0]
0x1800069de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069e3  jmp     short loc_180006A42
0x1800069e5  mov     edi, 800h
0x1800069ea  mov     rax, cs:g_pfnResultLoggingCallback
0x1800069f1  test    rax, rax
0x1800069f4  jz      short loc_180006A13
0x1800069f6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800069fd  jnz     short loc_180006A13
0x1800069ff  mov     r8d, edi
0x180006a02  lea     rdx, [rbp+13E0h+OutputString]
0x180006a09  lea     rcx, [rsp+14E0h+var_14C0]
0x180006a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a13  cmp     [rbp+13E0h+OutputString], r12w
0x180006a1b  jnz     short loc_180006A31
0x180006a1d  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180006a22  mov     rdx, rdi; unsigned __int16 *
0x180006a25  lea     rcx, [rbp+13E0h+OutputString]; this
0x180006a2c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006a31  test    bl, bl
0x180006a33  jz      short loc_180006A42
0x180006a35  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180006a3c  call    cs:__imp_OutputDebugStringW
0x180006a42  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180006a47  jnz     short loc_180006A52
0x180006a49  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180006a50  jz      short loc_180006A64
0x180006a52  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006a59  test    rax, rax
0x180006a5c  jz      short loc_180006A64
0x180006a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a63  nop
0x180006a64  test    byte ptr [rsp+14E0h+var_14C0+4], 1
0x180006a69  jz      short loc_180006A76
0x180006a6b  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180006a70  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180006a76  test    r15b, r15b
0x180006a79  jz      short loc_180006A93
0x180006a7b  lea     rdx, [rbp+13E0h+OutputString]
0x180006a82  lea     rcx, [rsp+14E0h+var_14C0]
0x180006a87  mov     rax, cs:g_pfnThrowPlatformException
0x180006a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a93  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180006a98  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180006a9d  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180006aa2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
