# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800039bc`
- end: `0x180003cc7`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `779`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800032b8`

## callees

- `0x180002140`
- `0x180002c48`
- `0x18000339c`
- `0x1800039bc`
- `0x180003df4`
- `0x1800041f8`
- `0x1800045a4`
- `0x18000478c`
- `0x180004924`
- `0x180036130`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003ad5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003ad5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003c5d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003c5d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003bce`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003bce`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<2>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8,
        int a9,
        int a10)
{
  int v14; // edx
  int v15; // ebx
  int v16; // edx
  int v17; // ebx
  const struct wil::FailureInfo *v18; // rdx
  wil::details::in1diag3 *v19; // rcx
  const struct wil::FailureInfo *v20; // r9
  bool v21; // zf
  wil::details *v22; // [rsp+30h] [rbp-D0h]
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+54h] [rbp-ACh]
  int v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+5Ch] [rbp-A4h]
  signed __int32 v27; // [rsp+60h] [rbp-A0h]
  _WORD *v28; // [rsp+68h] [rbp-98h]
  DWORD CurrentThreadId; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+78h] [rbp-88h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int64 v32; // [rsp+88h] [rbp-78h]
  int v33; // [rsp+90h] [rbp-70h]
  int v34; // [rsp+94h] [rbp-6Ch]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int128 v36; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  __int128 v38; // [rsp+B8h] [rbp-48h]
  __int64 v39; // [rsp+C8h] [rbp-38h]
  __int64 ModuleName; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  __int64 v42; // [rsp+E0h] [rbp-20h]
  char v43[1024]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR OutputString[2048]; // [rsp+4F0h] [rbp+3F0h] BYREF

  memset_0(&v23, 0, 0x98u);
  OutputString[0] = 0;
  v43[0] = 0;
  v15 = *a7;
  v25 = v15;
  v26 = a7[1];
  if ( v15 >= 0 )
  {
    v15 = -2147024228;
    LODWORD(v22) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v22);
    v25 = -2147024228;
    v26 = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v16);
  }
  v17 = wil::details::RecordLog((wil::details *)(unsigned int)v15, v14);
  v23 = 2;
  v24 = a10;
  if ( a7[2] == 1 )
    v24 = a10 | 8;
  v27 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v21 = *a8 == 0, v28 = a8, v21) )
    v28 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v32 = a3;
  v33 = a2;
  v34 = v17;
  v30 = a5;
  v31 = a4;
  v41 = a6;
  v42 = a1;
  v35 = 0;
  v38 = 0;
  v39 = 0;
  v36 = 0;
  v37 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v19);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v23);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v23, v43, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v23);
  if ( wil::details::g_pfnOriginateCallback && (v24 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v23);
  if ( v25 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v21 = !IsDebuggerPresent())
      : (v21 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v19) == 0),
        v21)
    || (v24 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v23, v20);
    OutputDebugStringW(OutputString);
  }
  if ( ((v24 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v19);
  if ( (v24 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v23, v18);
}

```

## disassembly

```asm
0x1800039bc  push    rbp
0x1800039be  push    rbx
0x1800039bf  push    rsi
0x1800039c0  push    rdi
0x1800039c1  push    r12
0x1800039c3  push    r13
0x1800039c5  push    r14
0x1800039c7  push    r15
0x1800039c9  lea     rbp, [rsp-1408h]
0x1800039d1  mov     eax, 1508h
0x1800039d6  call    _alloca_probe
0x1800039db  sub     rsp, rax
0x1800039de  mov     rax, cs:__security_cookie
0x1800039e5  xor     rax, rsp
0x1800039e8  mov     [rbp+1440h+var_50], rax
0x1800039ef  mov     r12, r9
0x1800039f2  mov     r15, r8
0x1800039f5  mov     r14d, edx
0x1800039f8  mov     rsi, rcx
0x1800039fb  mov     r13, [rbp+1440h+arg_20]
0x180003a02  mov     rax, [rbp+1440h+arg_28]
0x180003a09  mov     [rsp+1540h+var_1500], rax
0x180003a0e  xor     edx, edx; Val
0x180003a10  mov     r8d, 98h; Size
0x180003a16  lea     rcx, [rsp+1540h+var_14F0]; void *
0x180003a1b  call    memset_0
0x180003a20  nop
0x180003a21  xor     eax, eax
0x180003a23  mov     [rbp+1440h+OutputString], ax
0x180003a2a  mov     [rbp+1440h+var_1450], al
0x180003a2d  mov     rdi, [rbp+1440h+arg_30]
0x180003a34  mov     ebx, [rdi]
0x180003a36  mov     [rsp+1540h+var_14E8], ebx
0x180003a3a  mov     eax, [rdi+4]
0x180003a3d  mov     [rsp+1540h+var_14E4], eax
0x180003a41  test    ebx, ebx
0x180003a43  js      short loc_180003A7D
0x180003a45  mov     ebx, 8007029Ch
0x180003a4a  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x180003a4e  mov     rax, [rsp+1540h+var_1500]
0x180003a53  mov     [rsp+1540h+var_1518], rax; __int64
0x180003a58  mov     [rsp+1540h+var_1520], r13; __int64
0x180003a5d  mov     r9, r12; int
0x180003a60  mov     r8, r15; int
0x180003a63  mov     edx, r14d; int
0x180003a66  mov     rcx, rsi; int
0x180003a69  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180003a6e  mov     [rsp+1540h+var_14E8], ebx
0x180003a72  mov     ecx, ebx; this
0x180003a74  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003a79  mov     [rsp+1540h+var_14E4], eax
0x180003a7d  mov     ecx, ebx; this
0x180003a7f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180003a84  mov     ebx, eax
0x180003a86  mov     dword ptr [rsp+1540h+var_14F0], 2
0x180003a8e  mov     ecx, [rbp+1440h+arg_48]
0x180003a94  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180003a98  cmp     dword ptr [rdi+8], 1
0x180003a9c  jnz     short loc_180003AA5
0x180003a9e  or      ecx, 8
0x180003aa1  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180003aa5  mov     ecx, 1
0x180003aaa  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003ab2  inc     ecx
0x180003ab4  mov     [rsp+1540h+var_14E0], ecx
0x180003ab8  mov     rax, [rbp+1440h+arg_38]
0x180003abf  xor     edi, edi
0x180003ac1  test    rax, rax
0x180003ac4  jz      short loc_180003AD0
0x180003ac6  cmp     [rax], di
0x180003ac9  mov     [rsp+1540h+var_14D8], rax
0x180003ace  jnz     short loc_180003AD5
0x180003ad0  mov     [rsp+1540h+var_14D8], rdi
0x180003ad5  call    cs:__imp_GetCurrentThreadId
0x180003adc  nop     dword ptr [rax+rax+00h]
0x180003ae1  mov     [rsp+1540h+var_14D0], eax
0x180003ae5  mov     [rbp+1440h+var_14B8], r15
0x180003ae9  mov     [rbp+1440h+var_14B0], r14d
0x180003aed  mov     [rbp+1440h+var_14AC], ebx
0x180003af0  mov     [rsp+1540h+var_14C8], r13
0x180003af5  mov     [rbp+1440h+var_14C0], r12
0x180003af9  mov     rax, [rsp+1540h+var_1500]
0x180003afe  mov     [rbp+1440h+var_1468], rax
0x180003b02  mov     [rbp+1440h+var_1460], rsi
0x180003b06  mov     [rbp+1440h+var_14A8], rdi
0x180003b0a  xorps   xmm0, xmm0
0x180003b0d  xor     eax, eax
0x180003b0f  movups  [rbp+1440h+var_1488], xmm0
0x180003b13  mov     [rbp+1440h+var_1478], rax
0x180003b17  xorps   xmm1, xmm1
0x180003b1a  movups  [rbp+1440h+var_14A0], xmm1
0x180003b1e  mov     [rbp+1440h+var_1490], rax
0x180003b22  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003b29  test    rax, rax
0x180003b2c  jz      short loc_180003B39
0x180003b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b33  mov     [rbp+1440h+var_1470], rax
0x180003b37  jmp     short loc_180003B3D
0x180003b39  mov     [rbp+1440h+var_1470], rdi
0x180003b3d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003b44  test    rax, rax
0x180003b47  jz      short loc_180003B53
0x180003b49  lea     rcx, [rsp+1540h+var_14F0]
0x180003b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b53  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003b5a  test    rax, rax
0x180003b5d  jz      short loc_180003B73
0x180003b5f  mov     r8d, 400h
0x180003b65  lea     rdx, [rbp+1440h+var_1450]
0x180003b69  lea     rcx, [rsp+1540h+var_14F0]
0x180003b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b73  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003b7a  test    rax, rax
0x180003b7d  jz      short loc_180003B89
0x180003b7f  lea     rcx, [rsp+1540h+var_14F0]
0x180003b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b89  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003b90  test    rax, rax
0x180003b93  jz      short loc_180003BA6
0x180003b95  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180003b9a  jnz     short loc_180003BA6
0x180003b9c  lea     rcx, [rsp+1540h+var_14F0]
0x180003ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ba6  cmp     [rsp+1540h+var_14E8], edi
0x180003baa  jge     loc_180003CC1
0x180003bb0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180003bb7  jnz     short loc_180003BDE
0x180003bb9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003bc0  test    rax, rax
0x180003bc3  jz      short loc_180003BCE
0x180003bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bca  test    al, al
0x180003bcc  jmp     short loc_180003BDC
0x180003bce  call    cs:__imp_IsDebuggerPresent
0x180003bd5  nop     dword ptr [rax+rax+00h]
0x180003bda  test    eax, eax
0x180003bdc  jz      short loc_180003BE5
0x180003bde  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180003be3  jz      short loc_180003C0B
0x180003be5  mov     rax, cs:g_pfnResultLoggingCallback
0x180003bec  test    rax, rax
0x180003bef  jz      short loc_180003C69
0x180003bf1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180003bf8  jnz     short loc_180003C69
0x180003bfa  xor     r8d, r8d
0x180003bfd  xor     edx, edx
0x180003bff  lea     rcx, [rsp+1540h+var_14F0]
0x180003c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c09  jmp     short loc_180003C69
0x180003c0b  mov     ebx, 800h
0x180003c10  mov     rax, cs:g_pfnResultLoggingCallback
0x180003c17  test    rax, rax
0x180003c1a  jz      short loc_180003C39
0x180003c1c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180003c23  jnz     short loc_180003C39
0x180003c25  mov     r8d, ebx
0x180003c28  lea     rdx, [rbp+1440h+OutputString]
0x180003c2f  lea     rcx, [rsp+1540h+var_14F0]
0x180003c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c39  cmp     [rbp+1440h+OutputString], di
0x180003c40  jnz     short loc_180003C56
0x180003c42  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x180003c47  mov     rdx, rbx; unsigned __int16 *
0x180003c4a  lea     rcx, [rbp+1440h+OutputString]; this
0x180003c51  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003c56  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x180003c5d  call    cs:__imp_OutputDebugStringW
0x180003c64  nop     dword ptr [rax+rax+00h]
0x180003c69  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x180003c6e  jnz     short loc_180003C79
0x180003c70  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180003c77  jz      short loc_180003C8B
0x180003c79  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003c80  test    rax, rax
0x180003c83  jz      short loc_180003C8B
0x180003c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c8a  nop
0x180003c8b  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x180003c90  jnz     short loc_180003CB6
0x180003c92  mov     rcx, [rbp+1440h+var_50]
0x180003c99  xor     rcx, rsp; StackCookie
0x180003c9c  call    __security_check_cookie
0x180003ca1  add     rsp, 1508h
0x180003ca8  pop     r15
0x180003caa  pop     r14
0x180003cac  pop     r13
0x180003cae  pop     r12
0x180003cb0  pop     rdi
0x180003cb1  pop     rsi
0x180003cb2  pop     rbx
0x180003cb3  pop     rbp
0x180003cb4  retn
0x180003cb6  lea     rcx, [rsp+1540h+var_14F0]; this
0x180003cbb  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003cc1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
