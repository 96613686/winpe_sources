# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800089d8`
- end: `0x180008c7e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180008330`

## callees

- `0x180004ca0`
- `0x180005758`
- `0x1800089d8`
- `0x18000a024`
- `0x18000ad00`
- `0x18000be80`
- `0x18000c008`
- `0x18007f280`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008a9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008a9e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008c1d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008c1d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008b93`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008b93`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
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
0x1800089d8  push    rbp
0x1800089da  push    rbx
0x1800089db  push    rsi
0x1800089dc  push    rdi
0x1800089dd  push    r12
0x1800089df  push    r14
0x1800089e1  push    r15
0x1800089e3  lea     rbp, [rsp-13D0h]
0x1800089eb  mov     eax, 14D0h
0x1800089f0  call    _alloca_probe
0x1800089f5  sub     rsp, rax
0x1800089f8  mov     rax, cs:__security_cookie
0x1800089ff  xor     rax, rsp
0x180008a02  mov     [rbp+1400h+var_40], rax
0x180008a09  mov     rsi, r8
0x180008a0c  mov     edi, edx
0x180008a0e  mov     rbx, rcx
0x180008a11  mov     r14, [rbp+1400h+arg_28]
0x180008a18  xor     edx, edx; Val
0x180008a1a  mov     r8d, 98h; Size
0x180008a20  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180008a25  call    memset_0
0x180008a2a  nop
0x180008a2b  xor     r12d, r12d
0x180008a2e  mov     [rbp+1400h+OutputString], r12w
0x180008a36  mov     [rbp+1400h+var_1440], r12b
0x180008a3a  mov     rdx, [rbp+1400h+arg_30]; int
0x180008a41  mov     ecx, [rdx]; this
0x180008a43  mov     [rsp+1500h+var_14D8], ecx
0x180008a47  mov     eax, [rdx+4]
0x180008a4a  mov     [rsp+1500h+var_14D4], eax
0x180008a4e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008a53  mov     r15d, eax
0x180008a56  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180008a5e  mov     ecx, r12d
0x180008a61  lea     eax, [r12+8]
0x180008a66  cmp     dword ptr [rdx+8], 1
0x180008a6a  cmovz   ecx, eax
0x180008a6d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180008a71  lea     ecx, [rax-7]
0x180008a74  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008a7c  inc     ecx
0x180008a7e  mov     [rsp+1500h+var_14D0], ecx
0x180008a82  mov     rcx, [rbp+1400h+arg_38]
0x180008a89  test    rcx, rcx
0x180008a8c  jz      short loc_180008A99
0x180008a8e  cmp     [rcx], r12w
0x180008a92  mov     [rsp+1500h+var_14C8], rcx
0x180008a97  jnz     short loc_180008A9E
0x180008a99  mov     [rsp+1500h+var_14C8], r12
0x180008a9e  call    cs:__imp_GetCurrentThreadId
0x180008aa4  mov     [rsp+1500h+var_14C0], eax
0x180008aa8  mov     [rsp+1500h+var_14A8], rsi
0x180008aad  mov     [rsp+1500h+var_14A0], edi
0x180008ab1  mov     [rsp+1500h+var_149C], r15d
0x180008ab6  mov     [rsp+1500h+var_14B8], r12
0x180008abb  mov     [rsp+1500h+var_14B0], r12
0x180008ac0  mov     [rbp+1400h+var_1458], r14
0x180008ac4  mov     [rbp+1400h+var_1450], rbx
0x180008ac8  mov     [rsp+1500h+var_1498], r12
0x180008acd  xorps   xmm0, xmm0
0x180008ad0  xor     eax, eax
0x180008ad2  movups  [rbp+1400h+var_1478], xmm0
0x180008ad6  mov     [rbp+1400h+var_1468], rax
0x180008ada  xorps   xmm1, xmm1
0x180008add  movups  [rsp+1500h+var_1490], xmm1
0x180008ae2  mov     [rbp+1400h+var_1480], rax
0x180008ae6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008aed  test    rax, rax
0x180008af0  jz      short loc_180008AFD
0x180008af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008af7  mov     [rbp+1400h+var_1460], rax
0x180008afb  jmp     short loc_180008B01
0x180008afd  mov     [rbp+1400h+var_1460], r12
0x180008b01  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008b08  test    rax, rax
0x180008b0b  jz      short loc_180008B17
0x180008b0d  lea     rcx, [rsp+1500h+var_14E0]
0x180008b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b17  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008b1e  test    rax, rax
0x180008b21  jz      short loc_180008B37
0x180008b23  mov     r8d, 400h
0x180008b29  lea     rdx, [rbp+1400h+var_1440]
0x180008b2d  lea     rcx, [rsp+1500h+var_14E0]
0x180008b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b37  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008b3e  test    rax, rax
0x180008b41  jz      short loc_180008B4D
0x180008b43  lea     rcx, [rsp+1500h+var_14E0]
0x180008b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b4d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008b54  test    rax, rax
0x180008b57  jz      short loc_180008B6A
0x180008b59  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180008b5e  jnz     short loc_180008B6A
0x180008b60  lea     rcx, [rsp+1500h+var_14E0]
0x180008b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b6a  cmp     [rsp+1500h+var_14D8], r12d
0x180008b6f  jge     loc_180008C78
0x180008b75  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180008b7c  jnz     short loc_180008B9D
0x180008b7e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008b85  test    rax, rax
0x180008b88  jz      short loc_180008B93
0x180008b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b8f  test    al, al
0x180008b91  jmp     short loc_180008B9B
0x180008b93  call    cs:__imp_IsDebuggerPresent
0x180008b99  test    eax, eax
0x180008b9b  jz      short loc_180008BA4
0x180008b9d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180008ba2  jz      short loc_180008BCA
0x180008ba4  mov     rax, cs:g_pfnResultLoggingCallback
0x180008bab  test    rax, rax
0x180008bae  jz      short loc_180008C23
0x180008bb0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180008bb7  jnz     short loc_180008C23
0x180008bb9  xor     r8d, r8d
0x180008bbc  xor     edx, edx
0x180008bbe  lea     rcx, [rsp+1500h+var_14E0]
0x180008bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bc8  jmp     short loc_180008C23
0x180008bca  mov     ebx, 800h
0x180008bcf  mov     rax, cs:g_pfnResultLoggingCallback
0x180008bd6  test    rax, rax
0x180008bd9  jz      short loc_180008BF8
0x180008bdb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180008be2  jnz     short loc_180008BF8
0x180008be4  mov     r8d, ebx
0x180008be7  lea     rdx, [rbp+1400h+OutputString]
0x180008bee  lea     rcx, [rsp+1500h+var_14E0]
0x180008bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bf8  cmp     [rbp+1400h+OutputString], r12w
0x180008c00  jnz     short loc_180008C16
0x180008c02  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180008c07  mov     rdx, rbx; wchar_t *
0x180008c0a  lea     rcx, [rbp+1400h+OutputString]; this
0x180008c11  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180008c16  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180008c1d  call    cs:__imp_OutputDebugStringW
0x180008c23  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180008c28  jnz     short loc_180008C33
0x180008c2a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180008c31  jz      short loc_180008C45
0x180008c33  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008c3a  test    rax, rax
0x180008c3d  jz      short loc_180008C45
0x180008c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c44  nop
0x180008c45  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180008c4a  jnz     short loc_180008C6D
0x180008c4c  mov     rcx, [rbp+1400h+var_40]
0x180008c53  xor     rcx, rsp; StackCookie
0x180008c56  call    __security_check_cookie
0x180008c5b  add     rsp, 14D0h
0x180008c62  pop     r15
0x180008c64  pop     r14
0x180008c66  pop     r12
0x180008c68  pop     rdi
0x180008c69  pop     rsi
0x180008c6a  pop     rbx
0x180008c6b  pop     rbp
0x180008c6c  retn
0x180008c6d  lea     rcx, [rsp+1500h+var_14E0]; this
0x180008c72  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180008c78  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
