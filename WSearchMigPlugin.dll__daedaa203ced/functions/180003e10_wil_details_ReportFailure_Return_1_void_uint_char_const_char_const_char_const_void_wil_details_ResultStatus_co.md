# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003e10`
- end: `0x1800040be`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `686`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800038bc`

## callees

- `0x1800026f0`
- `0x18000329c`
- `0x180003e10`
- `0x1800060b4`
- `0x1800079c0`
- `0x180009d30`
- `0x180009efc`
- `0x180016d70`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003ede`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003ede`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000405d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000405d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003fd3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003fd3`

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
  __int64 v38; // [rsp+C0h] [rbp-40h]
  char v39[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2048]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v38 = -2;
  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
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
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v39, 1024);
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
0x180003e10  push    rbp
0x180003e12  push    rbx
0x180003e13  push    rsi
0x180003e14  push    rdi
0x180003e15  push    r12
0x180003e17  push    r14
0x180003e19  push    r15
0x180003e1b  lea     rbp, [rsp-13E0h]
0x180003e23  mov     eax, 14E0h
0x180003e28  call    _alloca_probe
0x180003e2d  sub     rsp, rax
0x180003e30  mov     [rbp+1410h+var_1450], 0FFFFFFFFFFFFFFFEh
0x180003e38  mov     rax, cs:__security_cookie
0x180003e3f  xor     rax, rsp
0x180003e42  mov     [rbp+1410h+var_40], rax
0x180003e49  mov     rsi, r8
0x180003e4c  mov     edi, edx
0x180003e4e  mov     rbx, rcx
0x180003e51  mov     r14, [rbp+1410h+arg_28]
0x180003e58  xor     edx, edx; Val
0x180003e5a  mov     r8d, 98h; Size
0x180003e60  lea     rcx, [rsp+1510h+var_14F0]; void *
0x180003e65  call    memset_0
0x180003e6a  nop
0x180003e6b  xor     r12d, r12d
0x180003e6e  mov     [rbp+1410h+OutputString], r12w
0x180003e76  mov     [rbp+1410h+var_1440], r12b
0x180003e7a  mov     rdx, [rbp+1410h+arg_30]; int
0x180003e81  mov     ecx, [rdx]; this
0x180003e83  mov     [rsp+1510h+var_14E8], ecx
0x180003e87  mov     eax, [rdx+4]
0x180003e8a  mov     [rsp+1510h+var_14E4], eax
0x180003e8e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003e93  mov     r15d, eax
0x180003e96  mov     dword ptr [rsp+1510h+var_14F0], 1
0x180003e9e  mov     ecx, r12d
0x180003ea1  lea     eax, [r12+8]
0x180003ea6  cmp     dword ptr [rdx+8], 1
0x180003eaa  cmovz   ecx, eax
0x180003ead  mov     dword ptr [rsp+1510h+var_14F0+4], ecx
0x180003eb1  lea     ecx, [rax-7]
0x180003eb4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003ebc  inc     ecx
0x180003ebe  mov     [rsp+1510h+var_14E0], ecx
0x180003ec2  mov     rcx, [rbp+1410h+arg_38]
0x180003ec9  test    rcx, rcx
0x180003ecc  jz      short loc_180003ED9
0x180003ece  cmp     [rcx], r12w
0x180003ed2  mov     [rsp+1510h+var_14D8], rcx
0x180003ed7  jnz     short loc_180003EDE
0x180003ed9  mov     [rsp+1510h+var_14D8], r12
0x180003ede  call    cs:__imp_GetCurrentThreadId
0x180003ee4  mov     [rsp+1510h+var_14D0], eax
0x180003ee8  mov     [rsp+1510h+var_14B8], rsi
0x180003eed  mov     [rsp+1510h+var_14B0], edi
0x180003ef1  mov     [rsp+1510h+var_14AC], r15d
0x180003ef6  mov     [rsp+1510h+var_14C8], r12
0x180003efb  mov     [rsp+1510h+var_14C0], r12
0x180003f00  mov     [rbp+1410h+var_1468], r14
0x180003f04  mov     [rbp+1410h+var_1460], rbx
0x180003f08  mov     [rsp+1510h+var_14A8], r12
0x180003f0d  xorps   xmm0, xmm0
0x180003f10  xor     eax, eax
0x180003f12  movups  [rbp+1410h+var_1488], xmm0
0x180003f16  mov     [rbp+1410h+var_1478], rax
0x180003f1a  xorps   xmm1, xmm1
0x180003f1d  movups  [rsp+1510h+var_14A0], xmm1
0x180003f22  mov     [rbp+1410h+var_1490], rax
0x180003f26  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003f2d  test    rax, rax
0x180003f30  jz      short loc_180003F3D
0x180003f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f37  mov     [rbp+1410h+var_1470], rax
0x180003f3b  jmp     short loc_180003F41
0x180003f3d  mov     [rbp+1410h+var_1470], r12
0x180003f41  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003f48  test    rax, rax
0x180003f4b  jz      short loc_180003F57
0x180003f4d  lea     rcx, [rsp+1510h+var_14F0]
0x180003f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f57  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003f5e  test    rax, rax
0x180003f61  jz      short loc_180003F77
0x180003f63  mov     r8d, 400h
0x180003f69  lea     rdx, [rbp+1410h+var_1440]
0x180003f6d  lea     rcx, [rsp+1510h+var_14F0]
0x180003f72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f77  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003f7e  test    rax, rax
0x180003f81  jz      short loc_180003F8D
0x180003f83  lea     rcx, [rsp+1510h+var_14F0]
0x180003f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f8d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003f94  test    rax, rax
0x180003f97  jz      short loc_180003FAA
0x180003f99  test    byte ptr [rsp+1510h+var_14F0+4], 2
0x180003f9e  jnz     short loc_180003FAA
0x180003fa0  lea     rcx, [rsp+1510h+var_14F0]
0x180003fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003faa  cmp     [rsp+1510h+var_14E8], r12d
0x180003faf  jge     loc_1800040B8
0x180003fb5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003fbc  jnz     short loc_180003FDD
0x180003fbe  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003fc5  test    rax, rax
0x180003fc8  jz      short loc_180003FD3
0x180003fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fcf  test    al, al
0x180003fd1  jmp     short loc_180003FDB
0x180003fd3  call    cs:__imp_IsDebuggerPresent
0x180003fd9  test    eax, eax
0x180003fdb  jz      short loc_180003FE4
0x180003fdd  test    byte ptr [rsp+1510h+var_14F0+4], 2
0x180003fe2  jz      short loc_18000400A
0x180003fe4  mov     rax, cs:g_pfnResultLoggingCallback
0x180003feb  test    rax, rax
0x180003fee  jz      short loc_180004063
0x180003ff0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003ff7  jnz     short loc_180004063
0x180003ff9  xor     r8d, r8d
0x180003ffc  xor     edx, edx
0x180003ffe  lea     rcx, [rsp+1510h+var_14F0]
0x180004003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004008  jmp     short loc_180004063
0x18000400a  mov     ebx, 800h
0x18000400f  mov     rax, cs:g_pfnResultLoggingCallback
0x180004016  test    rax, rax
0x180004019  jz      short loc_180004038
0x18000401b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004022  jnz     short loc_180004038
0x180004024  mov     r8d, ebx
0x180004027  lea     rdx, [rbp+1410h+OutputString]
0x18000402e  lea     rcx, [rsp+1510h+var_14F0]
0x180004033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004038  cmp     [rbp+1410h+OutputString], r12w
0x180004040  jnz     short loc_180004056
0x180004042  lea     r8, [rsp+1510h+var_14F0]; unsigned __int64
0x180004047  mov     rdx, rbx; wchar_t *
0x18000404a  lea     rcx, [rbp+1410h+OutputString]; this
0x180004051  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180004056  lea     rcx, [rbp+1410h+OutputString]; lpOutputString
0x18000405d  call    cs:__imp_OutputDebugStringW
0x180004063  test    byte ptr [rsp+1510h+var_14F0+4], 4
0x180004068  jnz     short loc_180004073
0x18000406a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004071  jz      short loc_180004085
0x180004073  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000407a  test    rax, rax
0x18000407d  jz      short loc_180004085
0x18000407f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004084  nop
0x180004085  test    byte ptr [rsp+1510h+var_14F0+4], 1
0x18000408a  jnz     short loc_1800040AD
0x18000408c  mov     rcx, [rbp+1410h+var_40]
0x180004093  xor     rcx, rsp; StackCookie
0x180004096  call    __security_check_cookie
0x18000409b  add     rsp, 14E0h
0x1800040a2  pop     r15
0x1800040a4  pop     r14
0x1800040a6  pop     r12
0x1800040a8  pop     rdi
0x1800040a9  pop     rsi
0x1800040aa  pop     rbx
0x1800040ab  pop     rbp
0x1800040ac  retn
0x1800040ad  lea     rcx, [rsp+1510h+var_14F0]; this
0x1800040b2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800040b8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
