# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003a54`
- end: `0x180003cfa`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800034e4`

## callees

- `0x180002240`
- `0x180002db8`
- `0x180003a54`
- `0x1800054d4`
- `0x1800067a0`
- `0x1800078c0`
- `0x180007a48`
- `0x180056f80`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b1a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003c99`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003c99`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003c0f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003c0f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
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
0x180003a54  push    rbp
0x180003a56  push    rbx
0x180003a57  push    rsi
0x180003a58  push    rdi
0x180003a59  push    r12
0x180003a5b  push    r14
0x180003a5d  push    r15
0x180003a5f  lea     rbp, [rsp-13D0h]
0x180003a67  mov     eax, 14D0h
0x180003a6c  call    _alloca_probe
0x180003a71  sub     rsp, rax
0x180003a74  mov     rax, cs:__security_cookie
0x180003a7b  xor     rax, rsp
0x180003a7e  mov     [rbp+1400h+var_40], rax
0x180003a85  mov     rsi, r8
0x180003a88  mov     edi, edx
0x180003a8a  mov     rbx, rcx
0x180003a8d  mov     r14, [rbp+1400h+arg_28]
0x180003a94  xor     edx, edx; Val
0x180003a96  mov     r8d, 98h; Size
0x180003a9c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003aa1  call    memset_0
0x180003aa6  nop
0x180003aa7  xor     r12d, r12d
0x180003aaa  mov     [rbp+1400h+OutputString], r12w
0x180003ab2  mov     [rbp+1400h+var_1440], r12b
0x180003ab6  mov     rdx, [rbp+1400h+arg_30]; int
0x180003abd  mov     ecx, [rdx]; this
0x180003abf  mov     [rsp+1500h+var_14D8], ecx
0x180003ac3  mov     eax, [rdx+4]
0x180003ac6  mov     [rsp+1500h+var_14D4], eax
0x180003aca  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003acf  mov     r15d, eax
0x180003ad2  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003ada  mov     ecx, r12d
0x180003add  lea     eax, [r12+8]
0x180003ae2  cmp     dword ptr [rdx+8], 1
0x180003ae6  cmovz   ecx, eax
0x180003ae9  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003aed  lea     ecx, [rax-7]
0x180003af0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003af8  inc     ecx
0x180003afa  mov     [rsp+1500h+var_14D0], ecx
0x180003afe  mov     rcx, [rbp+1400h+arg_38]
0x180003b05  test    rcx, rcx
0x180003b08  jz      short loc_180003B15
0x180003b0a  cmp     [rcx], r12w
0x180003b0e  mov     [rsp+1500h+var_14C8], rcx
0x180003b13  jnz     short loc_180003B1A
0x180003b15  mov     [rsp+1500h+var_14C8], r12
0x180003b1a  call    cs:__imp_GetCurrentThreadId
0x180003b20  mov     [rsp+1500h+var_14C0], eax
0x180003b24  mov     [rsp+1500h+var_14A8], rsi
0x180003b29  mov     [rsp+1500h+var_14A0], edi
0x180003b2d  mov     [rsp+1500h+var_149C], r15d
0x180003b32  mov     [rsp+1500h+var_14B8], r12
0x180003b37  mov     [rsp+1500h+var_14B0], r12
0x180003b3c  mov     [rbp+1400h+var_1458], r14
0x180003b40  mov     [rbp+1400h+var_1450], rbx
0x180003b44  mov     [rsp+1500h+var_1498], r12
0x180003b49  xorps   xmm0, xmm0
0x180003b4c  xor     eax, eax
0x180003b4e  movups  [rbp+1400h+var_1478], xmm0
0x180003b52  mov     [rbp+1400h+var_1468], rax
0x180003b56  xorps   xmm1, xmm1
0x180003b59  movups  [rsp+1500h+var_1490], xmm1
0x180003b5e  mov     [rbp+1400h+var_1480], rax
0x180003b62  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003b69  test    rax, rax
0x180003b6c  jz      short loc_180003B79
0x180003b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b73  mov     [rbp+1400h+var_1460], rax
0x180003b77  jmp     short loc_180003B7D
0x180003b79  mov     [rbp+1400h+var_1460], r12
0x180003b7d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003b84  test    rax, rax
0x180003b87  jz      short loc_180003B93
0x180003b89  lea     rcx, [rsp+1500h+var_14E0]
0x180003b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b93  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003b9a  test    rax, rax
0x180003b9d  jz      short loc_180003BB3
0x180003b9f  mov     r8d, 400h
0x180003ba5  lea     rdx, [rbp+1400h+var_1440]
0x180003ba9  lea     rcx, [rsp+1500h+var_14E0]
0x180003bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bb3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003bba  test    rax, rax
0x180003bbd  jz      short loc_180003BC9
0x180003bbf  lea     rcx, [rsp+1500h+var_14E0]
0x180003bc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bc9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003bd0  test    rax, rax
0x180003bd3  jz      short loc_180003BE6
0x180003bd5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003bda  jnz     short loc_180003BE6
0x180003bdc  lea     rcx, [rsp+1500h+var_14E0]
0x180003be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003be6  cmp     [rsp+1500h+var_14D8], r12d
0x180003beb  jge     loc_180003CF4
0x180003bf1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003bf8  jnz     short loc_180003C19
0x180003bfa  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003c01  test    rax, rax
0x180003c04  jz      short loc_180003C0F
0x180003c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c0b  test    al, al
0x180003c0d  jmp     short loc_180003C17
0x180003c0f  call    cs:__imp_IsDebuggerPresent
0x180003c15  test    eax, eax
0x180003c17  jz      short loc_180003C20
0x180003c19  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003c1e  jz      short loc_180003C46
0x180003c20  mov     rax, cs:g_pfnResultLoggingCallback
0x180003c27  test    rax, rax
0x180003c2a  jz      short loc_180003C9F
0x180003c2c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003c33  jnz     short loc_180003C9F
0x180003c35  xor     r8d, r8d
0x180003c38  xor     edx, edx
0x180003c3a  lea     rcx, [rsp+1500h+var_14E0]
0x180003c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c44  jmp     short loc_180003C9F
0x180003c46  mov     ebx, 800h
0x180003c4b  mov     rax, cs:g_pfnResultLoggingCallback
0x180003c52  test    rax, rax
0x180003c55  jz      short loc_180003C74
0x180003c57  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003c5e  jnz     short loc_180003C74
0x180003c60  mov     r8d, ebx
0x180003c63  lea     rdx, [rbp+1400h+OutputString]
0x180003c6a  lea     rcx, [rsp+1500h+var_14E0]
0x180003c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c74  cmp     [rbp+1400h+OutputString], r12w
0x180003c7c  jnz     short loc_180003C92
0x180003c7e  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003c83  mov     rdx, rbx; unsigned __int16 *
0x180003c86  lea     rcx, [rbp+1400h+OutputString]; this
0x180003c8d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003c92  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003c99  call    cs:__imp_OutputDebugStringW
0x180003c9f  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003ca4  jnz     short loc_180003CAF
0x180003ca6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003cad  jz      short loc_180003CC1
0x180003caf  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003cb6  test    rax, rax
0x180003cb9  jz      short loc_180003CC1
0x180003cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cc0  nop
0x180003cc1  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003cc6  jnz     short loc_180003CE9
0x180003cc8  mov     rcx, [rbp+1400h+var_40]
0x180003ccf  xor     rcx, rsp; StackCookie
0x180003cd2  call    __security_check_cookie
0x180003cd7  add     rsp, 14D0h
0x180003cde  pop     r15
0x180003ce0  pop     r14
0x180003ce2  pop     r12
0x180003ce4  pop     rdi
0x180003ce5  pop     rsi
0x180003ce6  pop     rbx
0x180003ce7  pop     rbp
0x180003ce8  retn
0x180003ce9  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003cee  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003cf4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
