# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180003b9c`
- end: `0x180003e0a`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `622`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003918`

## callees

- `0x18000329c`
- `0x180003b9c`
- `0x1800060b4`
- `0x180006870`
- `0x180007870`
- `0x180009d30`
- `0x180016d70`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003c4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003c4a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003dd7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003dd7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003d4d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003d4d`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // edx
  int v11; // edi
  int v12; // ecx
  const struct wil::FailureInfo *v13; // rdx
  __int64 v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  __int64 v37; // [rsp+C0h] [rbp-40h]
  char v38[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2072]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v37 = -2;
  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v19, v10);
  v17 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v18 = v12;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v11;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
  {
    v19 = -2147418113;
    v20 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v13);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( (v18 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v14);
  }
  wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180003b9c  push    rbp
0x180003b9e  push    rsi
0x180003b9f  push    rdi
0x180003ba0  push    r12
0x180003ba2  push    r13
0x180003ba4  push    r14
0x180003ba6  push    r15
0x180003ba8  lea     rbp, [rsp-13D0h]
0x180003bb0  mov     eax, 14D0h
0x180003bb5  call    _alloca_probe
0x180003bba  sub     rsp, rax
0x180003bbd  mov     [rbp+1400h+var_1440], 0FFFFFFFFFFFFFFFEh
0x180003bc5  mov     [rsp+1500h+arg_18], rbx
0x180003bcd  mov     r15, r8
0x180003bd0  mov     r14d, edx
0x180003bd3  mov     r12, rcx
0x180003bd6  mov     rsi, [rbp+1400h+arg_28]
0x180003bdd  xor     edx, edx; Val
0x180003bdf  mov     r8d, 98h; Size
0x180003be5  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003bea  call    memset_0
0x180003bef  nop
0x180003bf0  xor     r13d, r13d
0x180003bf3  mov     [rbp+1400h+OutputString], r13w
0x180003bfb  mov     [rbp+1400h+var_1430], r13b
0x180003bff  mov     rbx, [rbp+1400h+arg_30]
0x180003c06  mov     ecx, [rbx]; this
0x180003c08  mov     [rsp+1500h+var_14D8], ecx
0x180003c0c  mov     eax, [rbx+4]
0x180003c0f  mov     [rsp+1500h+var_14D4], eax
0x180003c13  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003c18  mov     edi, eax
0x180003c1a  mov     dword ptr [rsp+1500h+var_14E0], 3
0x180003c22  mov     ecx, r13d
0x180003c25  lea     eax, [r13+8]
0x180003c29  cmp     dword ptr [rbx+8], 1
0x180003c2d  cmovz   ecx, eax
0x180003c30  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003c34  lea     ecx, [rax-7]
0x180003c37  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003c3f  inc     ecx
0x180003c41  mov     [rsp+1500h+var_14D0], ecx
0x180003c45  mov     [rsp+1500h+var_14C8], r13
0x180003c4a  call    cs:__imp_GetCurrentThreadId
0x180003c50  mov     [rsp+1500h+var_14C0], eax
0x180003c54  mov     [rsp+1500h+var_14A8], r15
0x180003c59  mov     [rsp+1500h+var_14A0], r14d
0x180003c5e  mov     [rsp+1500h+var_149C], edi
0x180003c62  mov     [rsp+1500h+var_14B8], r13
0x180003c67  mov     [rsp+1500h+var_14B0], r13
0x180003c6c  mov     [rbp+1400h+var_1458], rsi
0x180003c70  mov     [rbp+1400h+var_1450], r12
0x180003c74  mov     [rsp+1500h+var_1498], r13
0x180003c79  xorps   xmm0, xmm0
0x180003c7c  xor     eax, eax
0x180003c7e  movups  [rbp+1400h+var_1478], xmm0
0x180003c82  mov     [rbp+1400h+var_1468], rax
0x180003c86  xorps   xmm1, xmm1
0x180003c89  movups  [rsp+1500h+var_1490], xmm1
0x180003c8e  mov     [rbp+1400h+var_1480], rax
0x180003c92  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003c99  test    rax, rax
0x180003c9c  jz      short loc_180003CA9
0x180003c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ca3  mov     [rbp+1400h+var_1460], rax
0x180003ca7  jmp     short loc_180003CAD
0x180003ca9  mov     [rbp+1400h+var_1460], r13
0x180003cad  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003cb4  test    rax, rax
0x180003cb7  jz      short loc_180003CC3
0x180003cb9  lea     rcx, [rsp+1500h+var_14E0]
0x180003cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cc3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003cca  test    rax, rax
0x180003ccd  jz      short loc_180003CE3
0x180003ccf  mov     r8d, 400h
0x180003cd5  lea     rdx, [rbp+1400h+var_1430]
0x180003cd9  lea     rcx, [rsp+1500h+var_14E0]
0x180003cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ce3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003cea  test    rax, rax
0x180003ced  jz      short loc_180003CF9
0x180003cef  lea     rcx, [rsp+1500h+var_14E0]
0x180003cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cf9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003d00  test    rax, rax
0x180003d03  jz      short loc_180003D16
0x180003d05  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003d0a  jnz     short loc_180003D16
0x180003d0c  lea     rcx, [rsp+1500h+var_14E0]
0x180003d11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d16  cmp     [rsp+1500h+var_14D8], r13d
0x180003d1b  jl      short loc_180003D2F
0x180003d1d  mov     ecx, 8000FFFFh; this
0x180003d22  mov     [rsp+1500h+var_14D8], ecx
0x180003d26  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003d2b  mov     [rsp+1500h+var_14D4], eax
0x180003d2f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180003d36  jnz     short loc_180003D57
0x180003d38  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003d3f  test    rax, rax
0x180003d42  jz      short loc_180003D4D
0x180003d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d49  test    al, al
0x180003d4b  jmp     short loc_180003D55
0x180003d4d  call    cs:__imp_IsDebuggerPresent
0x180003d53  test    eax, eax
0x180003d55  jz      short loc_180003D5E
0x180003d57  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003d5c  jz      short loc_180003D84
0x180003d5e  mov     rax, cs:g_pfnResultLoggingCallback
0x180003d65  test    rax, rax
0x180003d68  jz      short loc_180003DDD
0x180003d6a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003d71  jnz     short loc_180003DDD
0x180003d73  xor     r8d, r8d
0x180003d76  xor     edx, edx
0x180003d78  lea     rcx, [rsp+1500h+var_14E0]
0x180003d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d82  jmp     short loc_180003DDD
0x180003d84  mov     ebx, 800h
0x180003d89  mov     rax, cs:g_pfnResultLoggingCallback
0x180003d90  test    rax, rax
0x180003d93  jz      short loc_180003DB2
0x180003d95  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003d9c  jnz     short loc_180003DB2
0x180003d9e  mov     r8d, ebx
0x180003da1  lea     rdx, [rbp+1400h+OutputString]
0x180003da8  lea     rcx, [rsp+1500h+var_14E0]
0x180003dad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003db2  cmp     [rbp+1400h+OutputString], r13w
0x180003dba  jnz     short loc_180003DD0
0x180003dbc  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003dc1  mov     rdx, rbx; wchar_t *
0x180003dc4  lea     rcx, [rbp+1400h+OutputString]; this
0x180003dcb  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180003dd0  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003dd7  call    cs:__imp_OutputDebugStringW
0x180003ddd  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003de2  jnz     short loc_180003DED
0x180003de4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180003deb  jz      short loc_180003DFF
0x180003ded  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003df4  test    rax, rax
0x180003df7  jz      short loc_180003DFF
0x180003df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dfe  nop
0x180003dff  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003e04  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
