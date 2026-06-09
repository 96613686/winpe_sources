# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180013bbc`
- end: `0x180013e6a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `686`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800108d4`

## callees

- `0x18000caac`
- `0x180013bbc`
- `0x180014984`
- `0x1800154d0`
- `0x180016098`
- `0x180022792`
- `0x1800227c0`
- `0x180022880`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013c8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013c8a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180013d7f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180013d7f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180013e09`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180013e09`

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
0x180013bbc  push    rbp
0x180013bbe  push    rbx
0x180013bbf  push    rsi
0x180013bc0  push    rdi
0x180013bc1  push    r12
0x180013bc3  push    r14
0x180013bc5  push    r15
0x180013bc7  lea     rbp, [rsp-13E0h]
0x180013bcf  mov     eax, 14E0h
0x180013bd4  call    _alloca_probe
0x180013bd9  sub     rsp, rax
0x180013bdc  mov     [rbp+1410h+var_1450], 0FFFFFFFFFFFFFFFEh
0x180013be4  mov     rax, cs:__security_cookie
0x180013beb  xor     rax, rsp
0x180013bee  mov     [rbp+1410h+var_40], rax
0x180013bf5  mov     rsi, r8
0x180013bf8  mov     edi, edx
0x180013bfa  mov     rbx, rcx
0x180013bfd  mov     r14, [rbp+1410h+arg_28]
0x180013c04  xor     edx, edx; Val
0x180013c06  mov     r8d, 98h; Size
0x180013c0c  lea     rcx, [rsp+1510h+var_14F0]; void *
0x180013c11  call    memset_0
0x180013c16  nop
0x180013c17  xor     r12d, r12d
0x180013c1a  mov     [rbp+1410h+OutputString], r12w
0x180013c22  mov     [rbp+1410h+var_1440], r12b
0x180013c26  mov     rdx, [rbp+1410h+arg_30]; int
0x180013c2d  mov     ecx, [rdx]; this
0x180013c2f  mov     [rsp+1510h+var_14E8], ecx
0x180013c33  mov     eax, [rdx+4]
0x180013c36  mov     [rsp+1510h+var_14E4], eax
0x180013c3a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180013c3f  mov     r15d, eax
0x180013c42  mov     dword ptr [rsp+1510h+var_14F0], 1
0x180013c4a  mov     ecx, r12d
0x180013c4d  lea     eax, [r12+8]
0x180013c52  cmp     dword ptr [rdx+8], 1
0x180013c56  cmovz   ecx, eax
0x180013c59  mov     dword ptr [rsp+1510h+var_14F0+4], ecx
0x180013c5d  lea     ecx, [rax-7]
0x180013c60  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180013c68  inc     ecx
0x180013c6a  mov     [rsp+1510h+var_14E0], ecx
0x180013c6e  mov     rcx, [rbp+1410h+arg_38]
0x180013c75  test    rcx, rcx
0x180013c78  jz      short loc_180013C85
0x180013c7a  cmp     [rcx], r12w
0x180013c7e  mov     [rsp+1510h+var_14D8], rcx
0x180013c83  jnz     short loc_180013C8A
0x180013c85  mov     [rsp+1510h+var_14D8], r12
0x180013c8a  call    cs:__imp_GetCurrentThreadId
0x180013c90  mov     [rsp+1510h+var_14D0], eax
0x180013c94  mov     [rsp+1510h+var_14B8], rsi
0x180013c99  mov     [rsp+1510h+var_14B0], edi
0x180013c9d  mov     [rsp+1510h+var_14AC], r15d
0x180013ca2  mov     [rsp+1510h+var_14C8], r12
0x180013ca7  mov     [rsp+1510h+var_14C0], r12
0x180013cac  mov     [rbp+1410h+var_1468], r14
0x180013cb0  mov     [rbp+1410h+var_1460], rbx
0x180013cb4  mov     [rsp+1510h+var_14A8], r12
0x180013cb9  xorps   xmm0, xmm0
0x180013cbc  xor     eax, eax
0x180013cbe  movups  [rbp+1410h+var_1488], xmm0
0x180013cc2  mov     [rbp+1410h+var_1478], rax
0x180013cc6  xorps   xmm1, xmm1
0x180013cc9  movups  [rsp+1510h+var_14A0], xmm1
0x180013cce  mov     [rbp+1410h+var_1490], rax
0x180013cd2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180013cd9  test    rax, rax
0x180013cdc  jz      short loc_180013CE9
0x180013cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ce3  mov     [rbp+1410h+var_1470], rax
0x180013ce7  jmp     short loc_180013CED
0x180013ce9  mov     [rbp+1410h+var_1470], r12
0x180013ced  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180013cf4  test    rax, rax
0x180013cf7  jz      short loc_180013D03
0x180013cf9  lea     rcx, [rsp+1510h+var_14F0]
0x180013cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d03  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180013d0a  test    rax, rax
0x180013d0d  jz      short loc_180013D23
0x180013d0f  mov     r8d, 400h
0x180013d15  lea     rdx, [rbp+1410h+var_1440]
0x180013d19  lea     rcx, [rsp+1510h+var_14F0]
0x180013d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d23  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180013d2a  test    rax, rax
0x180013d2d  jz      short loc_180013D39
0x180013d2f  lea     rcx, [rsp+1510h+var_14F0]
0x180013d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d39  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180013d40  test    rax, rax
0x180013d43  jz      short loc_180013D56
0x180013d45  test    byte ptr [rsp+1510h+var_14F0+4], 2
0x180013d4a  jnz     short loc_180013D56
0x180013d4c  lea     rcx, [rsp+1510h+var_14F0]
0x180013d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d56  cmp     [rsp+1510h+var_14E8], r12d
0x180013d5b  jge     loc_180013E64
0x180013d61  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180013d68  jnz     short loc_180013D89
0x180013d6a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180013d71  test    rax, rax
0x180013d74  jz      short loc_180013D7F
0x180013d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d7b  test    al, al
0x180013d7d  jmp     short loc_180013D87
0x180013d7f  call    cs:__imp_IsDebuggerPresent
0x180013d85  test    eax, eax
0x180013d87  jz      short loc_180013D90
0x180013d89  test    byte ptr [rsp+1510h+var_14F0+4], 2
0x180013d8e  jz      short loc_180013DB6
0x180013d90  mov     rax, cs:g_pfnResultLoggingCallback
0x180013d97  test    rax, rax
0x180013d9a  jz      short loc_180013E0F
0x180013d9c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180013da3  jnz     short loc_180013E0F
0x180013da5  xor     r8d, r8d
0x180013da8  xor     edx, edx
0x180013daa  lea     rcx, [rsp+1510h+var_14F0]
0x180013daf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013db4  jmp     short loc_180013E0F
0x180013db6  mov     ebx, 800h
0x180013dbb  mov     rax, cs:g_pfnResultLoggingCallback
0x180013dc2  test    rax, rax
0x180013dc5  jz      short loc_180013DE4
0x180013dc7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180013dce  jnz     short loc_180013DE4
0x180013dd0  mov     r8d, ebx
0x180013dd3  lea     rdx, [rbp+1410h+OutputString]
0x180013dda  lea     rcx, [rsp+1510h+var_14F0]
0x180013ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013de4  cmp     [rbp+1410h+OutputString], r12w
0x180013dec  jnz     short loc_180013E02
0x180013dee  lea     r8, [rsp+1510h+var_14F0]; unsigned __int64
0x180013df3  mov     rdx, rbx; unsigned __int16 *
0x180013df6  lea     rcx, [rbp+1410h+OutputString]; this
0x180013dfd  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180013e02  lea     rcx, [rbp+1410h+OutputString]; lpOutputString
0x180013e09  call    cs:__imp_OutputDebugStringW
0x180013e0f  test    byte ptr [rsp+1510h+var_14F0+4], 4
0x180013e14  jnz     short loc_180013E1F
0x180013e16  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180013e1d  jz      short loc_180013E31
0x180013e1f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180013e26  test    rax, rax
0x180013e29  jz      short loc_180013E31
0x180013e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e30  nop
0x180013e31  test    byte ptr [rsp+1510h+var_14F0+4], 1
0x180013e36  jnz     short loc_180013E59
0x180013e38  mov     rcx, [rbp+1410h+var_40]
0x180013e3f  xor     rcx, rsp; StackCookie
0x180013e42  call    __security_check_cookie
0x180013e47  add     rsp, 14E0h
0x180013e4e  pop     r15
0x180013e50  pop     r14
0x180013e52  pop     r12
0x180013e54  pop     rdi
0x180013e55  pop     rsi
0x180013e56  pop     rbx
0x180013e57  pop     rbp
0x180013e58  retn
0x180013e59  lea     rcx, [rsp+1510h+var_14F0]; this
0x180013e5e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180013e64  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
