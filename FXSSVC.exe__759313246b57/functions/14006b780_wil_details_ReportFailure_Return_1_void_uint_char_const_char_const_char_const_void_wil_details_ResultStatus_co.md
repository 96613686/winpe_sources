# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x14006b780`
- end: `0x14006ba29`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `681`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14006b244`

## callees

- `0x140002c73`
- `0x14006b780`
- `0x14006d754`
- `0x14006f008`
- `0x1400712cc`
- `0x1400714a0`
- `0x140086ec0`
- `0x140086f80`
- `0x14008b010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14006b92c`
- `KERNEL32!IsDebuggerPresent` at `0x14006b92c`
- `KERNEL32!OutputDebugStringW` at `0x14006b9bc`
- `KERNEL32!OutputDebugStringW` at `0x14006b9bc`
- `KERNEL32!GetCurrentThreadId` at `0x14006b82b`
- `KERNEL32!GetCurrentThreadId` at `0x14006b82b`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x14006b780  mov     [rsp-8+arg_10], rbx
0x14006b785  push    rbp
0x14006b786  push    rsi
0x14006b787  push    rdi
0x14006b788  push    r14
0x14006b78a  push    r15
0x14006b78c  lea     rbp, [rsp-13D0h]
0x14006b794  mov     eax, 14D0h
0x14006b799  call    _alloca_probe
0x14006b79e  sub     rsp, rax
0x14006b7a1  mov     rax, cs:__security_cookie
0x14006b7a8  xor     rax, rsp
0x14006b7ab  mov     [rbp+13F0h+var_30], rax
0x14006b7b2  mov     esi, edx
0x14006b7b4  mov     r14, rcx
0x14006b7b7  mov     rdi, [rbp+13F0h+arg_28]
0x14006b7be  xor     edx, edx; Val
0x14006b7c0  mov     r8d, 98h; Size
0x14006b7c6  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x14006b7cb  call    memset_0
0x14006b7d0  nop
0x14006b7d1  xor     r15d, r15d
0x14006b7d4  mov     [rbp+13F0h+OutputString], r15w
0x14006b7dc  mov     [rbp+13F0h+var_1430], r15b
0x14006b7e0  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x14006b7e7  mov     ecx, [rdx]; this
0x14006b7e9  mov     [rsp+14F0h+var_14C8], ecx
0x14006b7ed  mov     eax, [rdx+4]
0x14006b7f0  mov     [rsp+14F0h+var_14C4], eax
0x14006b7f4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14006b7f9  mov     ebx, eax
0x14006b7fb  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x14006b803  mov     ecx, r15d
0x14006b806  lea     eax, [r15+8]
0x14006b80a  cmp     dword ptr [rdx+8], 1
0x14006b80e  cmovz   ecx, eax
0x14006b811  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x14006b815  lea     ecx, [rax-7]
0x14006b818  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14006b820  inc     ecx
0x14006b822  mov     [rsp+14F0h+var_14C0], ecx
0x14006b826  mov     [rsp+14F0h+var_14B8], r15
0x14006b82b  call    cs:__imp_GetCurrentThreadId
0x14006b832  nop     dword ptr [rax+rax+00h]
0x14006b837  mov     [rsp+14F0h+var_14B0], eax
0x14006b83b  lea     rax, aWil; "wil"
0x14006b842  mov     [rsp+14F0h+var_1498], rax
0x14006b847  mov     [rsp+14F0h+var_1490], esi
0x14006b84b  mov     [rsp+14F0h+var_148C], ebx
0x14006b84f  mov     [rsp+14F0h+var_14A8], r15
0x14006b854  mov     [rsp+14F0h+var_14A0], r15
0x14006b859  mov     [rbp+13F0h+var_1448], rdi
0x14006b85d  mov     [rbp+13F0h+var_1440], r14
0x14006b861  mov     [rsp+14F0h+var_1488], r15
0x14006b866  xorps   xmm0, xmm0
0x14006b869  xor     eax, eax
0x14006b86b  movups  [rbp+13F0h+var_1468], xmm0
0x14006b86f  mov     [rbp+13F0h+var_1458], rax
0x14006b873  xorps   xmm1, xmm1
0x14006b876  movups  [rsp+14F0h+var_1480], xmm1
0x14006b87b  mov     [rbp+13F0h+var_1470], rax
0x14006b87f  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14006b886  test    rax, rax
0x14006b889  jz      short loc_14006B896
0x14006b88b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b890  mov     [rbp+13F0h+var_1450], rax
0x14006b894  jmp     short loc_14006B89A
0x14006b896  mov     [rbp+13F0h+var_1450], r15
0x14006b89a  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14006b8a1  test    rax, rax
0x14006b8a4  jz      short loc_14006B8B0
0x14006b8a6  lea     rcx, [rsp+14F0h+var_14D0]
0x14006b8ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b8b0  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14006b8b7  test    rax, rax
0x14006b8ba  jz      short loc_14006B8D0
0x14006b8bc  mov     r8d, 400h
0x14006b8c2  lea     rdx, [rbp+13F0h+var_1430]
0x14006b8c6  lea     rcx, [rsp+14F0h+var_14D0]
0x14006b8cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b8d0  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14006b8d7  test    rax, rax
0x14006b8da  jz      short loc_14006B8E6
0x14006b8dc  lea     rcx, [rsp+14F0h+var_14D0]
0x14006b8e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b8e6  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14006b8ed  test    rax, rax
0x14006b8f0  jz      short loc_14006B903
0x14006b8f2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14006b8f7  jnz     short loc_14006B903
0x14006b8f9  lea     rcx, [rsp+14F0h+var_14D0]
0x14006b8fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b903  cmp     [rsp+14F0h+var_14C8], r15d
0x14006b908  jge     loc_14006BA23
0x14006b90e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x14006b915  jnz     short loc_14006B93C
0x14006b917  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14006b91e  test    rax, rax
0x14006b921  jz      short loc_14006B92C
0x14006b923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b928  test    al, al
0x14006b92a  jmp     short loc_14006B93A
0x14006b92c  call    cs:__imp_IsDebuggerPresent
0x14006b933  nop     dword ptr [rax+rax+00h]
0x14006b938  test    eax, eax
0x14006b93a  jz      short loc_14006B943
0x14006b93c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14006b941  jz      short loc_14006B969
0x14006b943  mov     rax, cs:g_pfnResultLoggingCallback
0x14006b94a  test    rax, rax
0x14006b94d  jz      short loc_14006B9C8
0x14006b94f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14006b956  jnz     short loc_14006B9C8
0x14006b958  xor     r8d, r8d
0x14006b95b  xor     edx, edx
0x14006b95d  lea     rcx, [rsp+14F0h+var_14D0]
0x14006b962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b967  jmp     short loc_14006B9C8
0x14006b969  mov     ebx, 800h
0x14006b96e  mov     rax, cs:g_pfnResultLoggingCallback
0x14006b975  test    rax, rax
0x14006b978  jz      short loc_14006B997
0x14006b97a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14006b981  jnz     short loc_14006B997
0x14006b983  mov     r8d, ebx
0x14006b986  lea     rdx, [rbp+13F0h+OutputString]
0x14006b98d  lea     rcx, [rsp+14F0h+var_14D0]
0x14006b992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b997  cmp     [rbp+13F0h+OutputString], r15w
0x14006b99f  jnz     short loc_14006B9B5
0x14006b9a1  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x14006b9a6  mov     rdx, rbx; unsigned __int16 *
0x14006b9a9  lea     rcx, [rbp+13F0h+OutputString]; this
0x14006b9b0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14006b9b5  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x14006b9bc  call    cs:__imp_OutputDebugStringW
0x14006b9c3  nop     dword ptr [rax+rax+00h]
0x14006b9c8  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x14006b9cd  jnz     short loc_14006B9D8
0x14006b9cf  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x14006b9d6  jz      short loc_14006B9EA
0x14006b9d8  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14006b9df  test    rax, rax
0x14006b9e2  jz      short loc_14006B9EA
0x14006b9e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b9e9  nop
0x14006b9ea  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x14006b9ef  jnz     short loc_14006BA18
0x14006b9f1  mov     rcx, [rbp+13F0h+var_30]
0x14006b9f8  xor     rcx, rsp; StackCookie
0x14006b9fb  call    __security_check_cookie
0x14006ba00  mov     rbx, [rsp+14F0h+arg_10]
0x14006ba08  add     rsp, 14D0h
0x14006ba0f  pop     r15
0x14006ba11  pop     r14
0x14006ba13  pop     rdi
0x14006ba14  pop     rsi
0x14006ba15  pop     rbp
0x14006ba16  retn
0x14006ba18  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14006ba1d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14006ba23  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
