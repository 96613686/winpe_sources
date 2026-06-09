# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180007a5c`
- end: `0x180007d02`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800074ec`

## callees

- `0x180006580`
- `0x180007018`
- `0x180007a5c`
- `0x180009064`
- `0x180009e80`
- `0x18000af90`
- `0x18000b06c`
- `0x180082e30`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007b22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007b22`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007ca1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007ca1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007c17`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007c17`

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
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
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
0x180007a5c  push    rbp
0x180007a5e  push    rbx
0x180007a5f  push    rsi
0x180007a60  push    rdi
0x180007a61  push    r12
0x180007a63  push    r14
0x180007a65  push    r15
0x180007a67  lea     rbp, [rsp-13D0h]
0x180007a6f  mov     eax, 14D0h
0x180007a74  call    _alloca_probe
0x180007a79  sub     rsp, rax
0x180007a7c  mov     rax, cs:__security_cookie
0x180007a83  xor     rax, rsp
0x180007a86  mov     [rbp+1400h+var_40], rax
0x180007a8d  mov     rsi, r8
0x180007a90  mov     edi, edx
0x180007a92  mov     rbx, rcx
0x180007a95  mov     r14, [rbp+1400h+arg_28]
0x180007a9c  xor     edx, edx; Val
0x180007a9e  mov     r8d, 98h; Size
0x180007aa4  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180007aa9  call    memset_0
0x180007aae  nop
0x180007aaf  xor     r12d, r12d
0x180007ab2  mov     [rbp+1400h+OutputString], r12w
0x180007aba  mov     [rbp+1400h+var_1440], r12b
0x180007abe  mov     rdx, [rbp+1400h+arg_30]; int
0x180007ac5  mov     ecx, [rdx]; this
0x180007ac7  mov     [rsp+1500h+var_14D8], ecx
0x180007acb  mov     eax, [rdx+4]
0x180007ace  mov     [rsp+1500h+var_14D4], eax
0x180007ad2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007ad7  mov     r15d, eax
0x180007ada  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180007ae2  mov     ecx, r12d
0x180007ae5  lea     eax, [r12+8]
0x180007aea  cmp     dword ptr [rdx+8], 1
0x180007aee  cmovz   ecx, eax
0x180007af1  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180007af5  lea     ecx, [rax-7]
0x180007af8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007b00  inc     ecx
0x180007b02  mov     [rsp+1500h+var_14D0], ecx
0x180007b06  mov     rcx, [rbp+1400h+arg_38]
0x180007b0d  test    rcx, rcx
0x180007b10  jz      short loc_180007B1D
0x180007b12  cmp     [rcx], r12w
0x180007b16  mov     [rsp+1500h+var_14C8], rcx
0x180007b1b  jnz     short loc_180007B22
0x180007b1d  mov     [rsp+1500h+var_14C8], r12
0x180007b22  call    cs:__imp_GetCurrentThreadId
0x180007b28  mov     [rsp+1500h+var_14C0], eax
0x180007b2c  mov     [rsp+1500h+var_14A8], rsi
0x180007b31  mov     [rsp+1500h+var_14A0], edi
0x180007b35  mov     [rsp+1500h+var_149C], r15d
0x180007b3a  mov     [rsp+1500h+var_14B8], r12
0x180007b3f  mov     [rsp+1500h+var_14B0], r12
0x180007b44  mov     [rbp+1400h+var_1458], r14
0x180007b48  mov     [rbp+1400h+var_1450], rbx
0x180007b4c  mov     [rsp+1500h+var_1498], r12
0x180007b51  xorps   xmm0, xmm0
0x180007b54  xor     eax, eax
0x180007b56  movups  [rbp+1400h+var_1478], xmm0
0x180007b5a  mov     [rbp+1400h+var_1468], rax
0x180007b5e  xorps   xmm1, xmm1
0x180007b61  movups  [rsp+1500h+var_1490], xmm1
0x180007b66  mov     [rbp+1400h+var_1480], rax
0x180007b6a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007b71  test    rax, rax
0x180007b74  jz      short loc_180007B81
0x180007b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b7b  mov     [rbp+1400h+var_1460], rax
0x180007b7f  jmp     short loc_180007B85
0x180007b81  mov     [rbp+1400h+var_1460], r12
0x180007b85  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007b8c  test    rax, rax
0x180007b8f  jz      short loc_180007B9B
0x180007b91  lea     rcx, [rsp+1500h+var_14E0]
0x180007b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b9b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007ba2  test    rax, rax
0x180007ba5  jz      short loc_180007BBB
0x180007ba7  mov     r8d, 400h
0x180007bad  lea     rdx, [rbp+1400h+var_1440]
0x180007bb1  lea     rcx, [rsp+1500h+var_14E0]
0x180007bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bbb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007bc2  test    rax, rax
0x180007bc5  jz      short loc_180007BD1
0x180007bc7  lea     rcx, [rsp+1500h+var_14E0]
0x180007bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bd1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007bd8  test    rax, rax
0x180007bdb  jz      short loc_180007BEE
0x180007bdd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180007be2  jnz     short loc_180007BEE
0x180007be4  lea     rcx, [rsp+1500h+var_14E0]
0x180007be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bee  cmp     [rsp+1500h+var_14D8], r12d
0x180007bf3  jge     loc_180007CFC
0x180007bf9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180007c00  jnz     short loc_180007C21
0x180007c02  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007c09  test    rax, rax
0x180007c0c  jz      short loc_180007C17
0x180007c0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c13  test    al, al
0x180007c15  jmp     short loc_180007C1F
0x180007c17  call    cs:__imp_IsDebuggerPresent
0x180007c1d  test    eax, eax
0x180007c1f  jz      short loc_180007C28
0x180007c21  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180007c26  jz      short loc_180007C4E
0x180007c28  mov     rax, cs:g_pfnResultLoggingCallback
0x180007c2f  test    rax, rax
0x180007c32  jz      short loc_180007CA7
0x180007c34  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180007c3b  jnz     short loc_180007CA7
0x180007c3d  xor     r8d, r8d
0x180007c40  xor     edx, edx
0x180007c42  lea     rcx, [rsp+1500h+var_14E0]
0x180007c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c4c  jmp     short loc_180007CA7
0x180007c4e  mov     ebx, 800h
0x180007c53  mov     rax, cs:g_pfnResultLoggingCallback
0x180007c5a  test    rax, rax
0x180007c5d  jz      short loc_180007C7C
0x180007c5f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180007c66  jnz     short loc_180007C7C
0x180007c68  mov     r8d, ebx
0x180007c6b  lea     rdx, [rbp+1400h+OutputString]
0x180007c72  lea     rcx, [rsp+1500h+var_14E0]
0x180007c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c7c  cmp     [rbp+1400h+OutputString], r12w
0x180007c84  jnz     short loc_180007C9A
0x180007c86  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180007c8b  mov     rdx, rbx; unsigned __int16 *
0x180007c8e  lea     rcx, [rbp+1400h+OutputString]; this
0x180007c95  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007c9a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180007ca1  call    cs:__imp_OutputDebugStringW
0x180007ca7  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180007cac  jnz     short loc_180007CB7
0x180007cae  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180007cb5  jz      short loc_180007CC9
0x180007cb7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007cbe  test    rax, rax
0x180007cc1  jz      short loc_180007CC9
0x180007cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cc8  nop
0x180007cc9  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180007cce  jnz     short loc_180007CF1
0x180007cd0  mov     rcx, [rbp+1400h+var_40]
0x180007cd7  xor     rcx, rsp; StackCookie
0x180007cda  call    __security_check_cookie
0x180007cdf  add     rsp, 14D0h
0x180007ce6  pop     r15
0x180007ce8  pop     r14
0x180007cea  pop     r12
0x180007cec  pop     rdi
0x180007ced  pop     rsi
0x180007cee  pop     rbx
0x180007cef  pop     rbp
0x180007cf0  retn
0x180007cf1  lea     rcx, [rsp+1500h+var_14E0]; this
0x180007cf6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180007cfc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
