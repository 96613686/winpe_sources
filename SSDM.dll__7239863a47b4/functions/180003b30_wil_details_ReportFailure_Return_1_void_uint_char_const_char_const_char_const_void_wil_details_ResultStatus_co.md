# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003b30`
- end: `0x180003dd6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002f7c`

## callees

- `0x180003b30`
- `0x180005778`
- `0x180006b70`
- `0x180006f08`
- `0x1800071d4`
- `0x18000e962`
- `0x18000e990`
- `0x18000ea50`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003bf6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003bf6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003ceb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003ceb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003d75`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003d75`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
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
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180003b30  push    rbp
0x180003b32  push    rbx
0x180003b33  push    rsi
0x180003b34  push    rdi
0x180003b35  push    r12
0x180003b37  push    r14
0x180003b39  push    r15
0x180003b3b  lea     rbp, [rsp-13D0h]
0x180003b43  mov     eax, 14D0h
0x180003b48  call    _alloca_probe
0x180003b4d  sub     rsp, rax
0x180003b50  mov     rax, cs:__security_cookie
0x180003b57  xor     rax, rsp
0x180003b5a  mov     [rbp+1400h+var_40], rax
0x180003b61  mov     rsi, r8
0x180003b64  mov     edi, edx
0x180003b66  mov     rbx, rcx
0x180003b69  mov     r14, [rbp+1400h+arg_28]
0x180003b70  xor     edx, edx; Val
0x180003b72  mov     r8d, 98h; Size
0x180003b78  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003b7d  call    memset_0
0x180003b82  nop
0x180003b83  xor     r12d, r12d
0x180003b86  mov     [rbp+1400h+OutputString], r12w
0x180003b8e  mov     [rbp+1400h+var_1440], r12b
0x180003b92  mov     rdx, [rbp+1400h+arg_30]; int
0x180003b99  mov     ecx, [rdx]; this
0x180003b9b  mov     [rsp+1500h+var_14D8], ecx
0x180003b9f  mov     eax, [rdx+4]
0x180003ba2  mov     [rsp+1500h+var_14D4], eax
0x180003ba6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003bab  mov     r15d, eax
0x180003bae  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003bb6  mov     ecx, r12d
0x180003bb9  lea     eax, [r12+8]
0x180003bbe  cmp     dword ptr [rdx+8], 1
0x180003bc2  cmovz   ecx, eax
0x180003bc5  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003bc9  lea     ecx, [rax-7]
0x180003bcc  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003bd4  inc     ecx
0x180003bd6  mov     [rsp+1500h+var_14D0], ecx
0x180003bda  mov     rcx, [rbp+1400h+arg_38]
0x180003be1  test    rcx, rcx
0x180003be4  jz      short loc_180003BF1
0x180003be6  cmp     [rcx], r12w
0x180003bea  mov     [rsp+1500h+var_14C8], rcx
0x180003bef  jnz     short loc_180003BF6
0x180003bf1  mov     [rsp+1500h+var_14C8], r12
0x180003bf6  call    cs:__imp_GetCurrentThreadId
0x180003bfc  mov     [rsp+1500h+var_14C0], eax
0x180003c00  mov     [rsp+1500h+var_14A8], rsi
0x180003c05  mov     [rsp+1500h+var_14A0], edi
0x180003c09  mov     [rsp+1500h+var_149C], r15d
0x180003c0e  mov     [rsp+1500h+var_14B8], r12
0x180003c13  mov     [rsp+1500h+var_14B0], r12
0x180003c18  mov     [rbp+1400h+var_1458], r14
0x180003c1c  mov     [rbp+1400h+var_1450], rbx
0x180003c20  mov     [rsp+1500h+var_1498], r12
0x180003c25  xorps   xmm0, xmm0
0x180003c28  xor     eax, eax
0x180003c2a  movups  [rbp+1400h+var_1478], xmm0
0x180003c2e  mov     [rbp+1400h+var_1468], rax
0x180003c32  xorps   xmm1, xmm1
0x180003c35  movups  [rsp+1500h+var_1490], xmm1
0x180003c3a  mov     [rbp+1400h+var_1480], rax
0x180003c3e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003c45  test    rax, rax
0x180003c48  jz      short loc_180003C55
0x180003c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c4f  mov     [rbp+1400h+var_1460], rax
0x180003c53  jmp     short loc_180003C59
0x180003c55  mov     [rbp+1400h+var_1460], r12
0x180003c59  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003c60  test    rax, rax
0x180003c63  jz      short loc_180003C6F
0x180003c65  lea     rcx, [rsp+1500h+var_14E0]
0x180003c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c6f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003c76  test    rax, rax
0x180003c79  jz      short loc_180003C8F
0x180003c7b  mov     r8d, 400h
0x180003c81  lea     rdx, [rbp+1400h+var_1440]
0x180003c85  lea     rcx, [rsp+1500h+var_14E0]
0x180003c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c8f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003c96  test    rax, rax
0x180003c99  jz      short loc_180003CA5
0x180003c9b  lea     rcx, [rsp+1500h+var_14E0]
0x180003ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ca5  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003cac  test    rax, rax
0x180003caf  jz      short loc_180003CC2
0x180003cb1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003cb6  jnz     short loc_180003CC2
0x180003cb8  lea     rcx, [rsp+1500h+var_14E0]
0x180003cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cc2  cmp     [rsp+1500h+var_14D8], r12d
0x180003cc7  jge     loc_180003DD0
0x180003ccd  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003cd4  jnz     short loc_180003CF5
0x180003cd6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003cdd  test    rax, rax
0x180003ce0  jz      short loc_180003CEB
0x180003ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ce7  test    al, al
0x180003ce9  jmp     short loc_180003CF3
0x180003ceb  call    cs:__imp_IsDebuggerPresent
0x180003cf1  test    eax, eax
0x180003cf3  jz      short loc_180003CFC
0x180003cf5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003cfa  jz      short loc_180003D22
0x180003cfc  mov     rax, cs:g_pfnResultLoggingCallback
0x180003d03  test    rax, rax
0x180003d06  jz      short loc_180003D7B
0x180003d08  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003d0f  jnz     short loc_180003D7B
0x180003d11  xor     r8d, r8d
0x180003d14  xor     edx, edx
0x180003d16  lea     rcx, [rsp+1500h+var_14E0]
0x180003d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d20  jmp     short loc_180003D7B
0x180003d22  mov     ebx, 800h
0x180003d27  mov     rax, cs:g_pfnResultLoggingCallback
0x180003d2e  test    rax, rax
0x180003d31  jz      short loc_180003D50
0x180003d33  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003d3a  jnz     short loc_180003D50
0x180003d3c  mov     r8d, ebx
0x180003d3f  lea     rdx, [rbp+1400h+OutputString]
0x180003d46  lea     rcx, [rsp+1500h+var_14E0]
0x180003d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d50  cmp     [rbp+1400h+OutputString], r12w
0x180003d58  jnz     short loc_180003D6E
0x180003d5a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003d5f  mov     rdx, rbx; wchar_t *
0x180003d62  lea     rcx, [rbp+1400h+OutputString]; this
0x180003d69  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180003d6e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003d75  call    cs:__imp_OutputDebugStringW
0x180003d7b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003d80  jnz     short loc_180003D8B
0x180003d82  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003d89  jz      short loc_180003D9D
0x180003d8b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003d92  test    rax, rax
0x180003d95  jz      short loc_180003D9D
0x180003d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d9c  nop
0x180003d9d  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003da2  jnz     short loc_180003DC5
0x180003da4  mov     rcx, [rbp+1400h+var_40]
0x180003dab  xor     rcx, rsp; StackCookie
0x180003dae  call    __security_check_cookie
0x180003db3  add     rsp, 14D0h
0x180003dba  pop     r15
0x180003dbc  pop     r14
0x180003dbe  pop     r12
0x180003dc0  pop     rdi
0x180003dc1  pop     rsi
0x180003dc2  pop     rbx
0x180003dc3  pop     rbp
0x180003dc4  retn
0x180003dc5  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003dca  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003dd0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
