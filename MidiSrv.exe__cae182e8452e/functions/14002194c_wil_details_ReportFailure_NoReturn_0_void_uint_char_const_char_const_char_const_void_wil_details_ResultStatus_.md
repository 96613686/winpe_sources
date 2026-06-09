# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x14002194c`
- end: `0x140021bf8`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140021780`

## callees

- `0x1400060f8`
- `0x140008e14`
- `0x140009dd4`
- `0x14000c0b8`
- `0x14000c470`
- `0x14000c54c`
- `0x14002194c`
- `0x1400562f0`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400219f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400219f5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140021b8c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140021b8c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140021af0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140021af0`

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
0x14002194c  mov     [rsp-8+arg_18], rbx
0x140021951  push    rbp
0x140021952  push    rsi
0x140021953  push    rdi
0x140021954  push    r12
0x140021956  push    r13
0x140021958  push    r14
0x14002195a  push    r15
0x14002195c  lea     rbp, [rsp-13C0h]
0x140021964  mov     eax, 14C0h
0x140021969  call    _alloca_probe
0x14002196e  sub     rsp, rax
0x140021971  mov     r14, r8
0x140021974  mov     esi, edx
0x140021976  mov     r15, rcx
0x140021979  mov     rdi, [rbp+13F0h+arg_28]
0x140021980  xor     r13d, r13d
0x140021983  cmp     cs:g_pfnThrowPlatformException, r13
0x14002198a  setnz   r12b
0x14002198e  xor     edx, edx; Val
0x140021990  mov     r8d, 98h; Size
0x140021996  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x14002199b  call    memset_0
0x1400219a0  nop
0x1400219a1  mov     [rbp+13F0h+OutputString], r13w
0x1400219a9  mov     [rbp+13F0h+var_1430], r13b
0x1400219ad  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1400219b4  mov     ecx, [rdx]; this
0x1400219b6  mov     [rsp+14F0h+var_14C8], ecx
0x1400219ba  mov     eax, [rdx+4]
0x1400219bd  mov     [rsp+14F0h+var_14C4], eax
0x1400219c1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1400219c6  mov     ebx, eax
0x1400219c8  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x1400219cd  mov     ecx, r13d
0x1400219d0  lea     eax, [r13+8]
0x1400219d4  cmp     dword ptr [rdx+8], 1
0x1400219d8  cmovz   ecx, eax
0x1400219db  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1400219df  lea     ecx, [rax-7]
0x1400219e2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400219ea  inc     ecx
0x1400219ec  mov     [rsp+14F0h+var_14C0], ecx
0x1400219f0  mov     [rsp+14F0h+var_14B8], r13
0x1400219f5  call    cs:__imp_GetCurrentThreadId
0x1400219fb  mov     [rsp+14F0h+var_14B0], eax
0x1400219ff  mov     [rsp+14F0h+var_1498], r14
0x140021a04  mov     [rsp+14F0h+var_1490], esi
0x140021a08  mov     [rsp+14F0h+var_148C], ebx
0x140021a0c  mov     [rsp+14F0h+var_14A8], r13
0x140021a11  mov     [rsp+14F0h+var_14A0], r13
0x140021a16  mov     [rbp+13F0h+var_1448], rdi
0x140021a1a  mov     [rbp+13F0h+var_1440], r15
0x140021a1e  mov     [rsp+14F0h+var_1488], r13
0x140021a23  xorps   xmm0, xmm0
0x140021a26  xor     eax, eax
0x140021a28  movups  [rbp+13F0h+var_1468], xmm0
0x140021a2c  mov     [rbp+13F0h+var_1458], rax
0x140021a30  xorps   xmm1, xmm1
0x140021a33  movups  [rsp+14F0h+var_1480], xmm1
0x140021a38  mov     [rbp+13F0h+var_1470], rax
0x140021a3c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140021a43  test    rax, rax
0x140021a46  jz      short loc_140021A53
0x140021a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021a4d  mov     [rbp+13F0h+var_1450], rax
0x140021a51  jmp     short loc_140021A57
0x140021a53  mov     [rbp+13F0h+var_1450], r13
0x140021a57  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140021a5e  test    rax, rax
0x140021a61  jz      short loc_140021A6D
0x140021a63  lea     rcx, [rsp+14F0h+var_14D0]
0x140021a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021a6d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140021a74  test    rax, rax
0x140021a77  jz      short loc_140021A8D
0x140021a79  mov     r8d, 400h
0x140021a7f  lea     rdx, [rbp+13F0h+var_1430]
0x140021a83  lea     rcx, [rsp+14F0h+var_14D0]
0x140021a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021a8d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140021a94  test    rax, rax
0x140021a97  jz      short loc_140021AA3
0x140021a99  lea     rcx, [rsp+14F0h+var_14D0]
0x140021a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021aa3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140021aaa  test    rax, rax
0x140021aad  jz      short loc_140021AC5
0x140021aaf  test    r12b, r12b
0x140021ab2  jnz     short loc_140021AC5
0x140021ab4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140021ab9  jnz     short loc_140021AC5
0x140021abb  lea     rcx, [rsp+14F0h+var_14D0]
0x140021ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021ac5  cmp     [rsp+14F0h+var_14C8], r13d
0x140021aca  jl      short loc_140021AD2
0x140021acc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140021ad2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140021ad9  jnz     short loc_140021AFA
0x140021adb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140021ae2  test    rax, rax
0x140021ae5  jz      short loc_140021AF0
0x140021ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021aec  test    al, al
0x140021aee  jmp     short loc_140021AF8
0x140021af0  call    cs:__imp_IsDebuggerPresent
0x140021af6  test    eax, eax
0x140021af8  jz      short loc_140021B03
0x140021afa  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140021aff  mov     bl, 1
0x140021b01  jz      short loc_140021B06
0x140021b03  mov     bl, r13b
0x140021b06  test    r12b, r12b
0x140021b09  jnz     short loc_140021B35
0x140021b0b  test    bl, bl
0x140021b0d  jnz     short loc_140021B35
0x140021b0f  mov     rax, cs:g_pfnResultLoggingCallback
0x140021b16  test    rax, rax
0x140021b19  jz      short loc_140021B92
0x140021b1b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140021b22  jnz     short loc_140021B92
0x140021b24  xor     r8d, r8d
0x140021b27  xor     edx, edx
0x140021b29  lea     rcx, [rsp+14F0h+var_14D0]
0x140021b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021b33  jmp     short loc_140021B92
0x140021b35  mov     edi, 800h
0x140021b3a  mov     rax, cs:g_pfnResultLoggingCallback
0x140021b41  test    rax, rax
0x140021b44  jz      short loc_140021B63
0x140021b46  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140021b4d  jnz     short loc_140021B63
0x140021b4f  mov     r8d, edi
0x140021b52  lea     rdx, [rbp+13F0h+OutputString]
0x140021b59  lea     rcx, [rsp+14F0h+var_14D0]
0x140021b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021b63  cmp     [rbp+13F0h+OutputString], r13w
0x140021b6b  jnz     short loc_140021B81
0x140021b6d  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140021b72  mov     rdx, rdi; unsigned __int16 *
0x140021b75  lea     rcx, [rbp+13F0h+OutputString]; this
0x140021b7c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140021b81  test    bl, bl
0x140021b83  jz      short loc_140021B92
0x140021b85  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140021b8c  call    cs:__imp_OutputDebugStringW
0x140021b92  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140021b97  jnz     short loc_140021BA2
0x140021b99  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140021ba0  jz      short loc_140021BB4
0x140021ba2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140021ba9  test    rax, rax
0x140021bac  jz      short loc_140021BB4
0x140021bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021bb3  nop
0x140021bb4  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140021bb9  jz      short loc_140021BC6
0x140021bbb  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140021bc0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140021bc6  test    r12b, r12b
0x140021bc9  jz      short loc_140021BE3
0x140021bcb  lea     rdx, [rbp+13F0h+OutputString]
0x140021bd2  lea     rcx, [rsp+14F0h+var_14D0]
0x140021bd7  mov     rax, cs:g_pfnThrowPlatformException
0x140021bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021be3  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140021be8  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x140021bed  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140021bf2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
