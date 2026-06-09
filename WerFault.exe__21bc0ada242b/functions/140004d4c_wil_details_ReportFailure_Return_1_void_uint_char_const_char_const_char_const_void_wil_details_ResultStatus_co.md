# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140004d4c`
- end: `0x140004ffa`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `686`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400046ec`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x140004d4c`
- `0x140007b34`
- `0x140009668`
- `0x14000c3d0`
- `0x14000c59c`
- `0x14005b770`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004e18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004e18`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004f0d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004f0d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004f97`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004f97`

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
  int v12; // r12d
  int v13; // ecx
  __int64 v14; // rdx
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  _WORD *v24; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  __int64 v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v21 = *a7;
  v22 = a7[1];
  v12 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v19 = 1;
  v13 = 0;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  v20 = v13;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v18 = *a8 == 0, v24 = a8, v18) )
    v24 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v28 = a3;
  v29 = a2;
  v30 = v12;
  v26 = 0;
  v27 = a4;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v35 = 0;
  v32 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x140004d4c  push    rbp
0x140004d4e  push    rbx
0x140004d4f  push    rsi
0x140004d50  push    rdi
0x140004d51  push    r12
0x140004d53  push    r13
0x140004d55  push    r14
0x140004d57  push    r15
0x140004d59  lea     rbp, [rsp-13D8h]
0x140004d61  mov     eax, 14D8h
0x140004d66  call    _alloca_probe
0x140004d6b  sub     rsp, rax
0x140004d6e  mov     rax, cs:__security_cookie
0x140004d75  xor     rax, rsp
0x140004d78  mov     [rbp+1410h+var_50], rax
0x140004d7f  mov     r14, r9
0x140004d82  mov     rsi, r8
0x140004d85  mov     edi, edx
0x140004d87  mov     rbx, rcx
0x140004d8a  mov     r15, [rbp+1410h+arg_28]
0x140004d91  xor     edx, edx; Val
0x140004d93  mov     r8d, 98h; Size
0x140004d99  lea     rcx, [rsp+1510h+var_14F0]; void *
0x140004d9e  call    memset_0
0x140004da3  nop
0x140004da4  xor     r13d, r13d
0x140004da7  mov     [rbp+1410h+OutputString], r13w
0x140004daf  mov     [rbp+1410h+var_1450], r13b
0x140004db3  mov     rdx, [rbp+1410h+arg_30]; int
0x140004dba  mov     ecx, [rdx]; this
0x140004dbc  mov     [rsp+1510h+var_14E8], ecx
0x140004dc0  mov     eax, [rdx+4]
0x140004dc3  mov     [rsp+1510h+var_14E4], eax
0x140004dc7  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140004dcc  mov     r12d, eax
0x140004dcf  lea     r8d, [r13+1]
0x140004dd3  mov     dword ptr [rsp+1510h+var_14F0], r8d
0x140004dd8  mov     ecx, r13d
0x140004ddb  lea     eax, [r13+8]
0x140004ddf  cmp     [rdx+8], r8d
0x140004de3  cmovz   ecx, eax
0x140004de6  mov     dword ptr [rsp+1510h+var_14F0+4], ecx
0x140004dea  mov     ecx, r8d
0x140004ded  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140004df5  add     ecx, r8d
0x140004df8  mov     [rsp+1510h+var_14E0], ecx
0x140004dfc  mov     rcx, [rbp+1410h+arg_38]
0x140004e03  test    rcx, rcx
0x140004e06  jz      short loc_140004E13
0x140004e08  cmp     [rcx], r13w
0x140004e0c  mov     [rsp+1510h+var_14D8], rcx
0x140004e11  jnz     short loc_140004E18
0x140004e13  mov     [rsp+1510h+var_14D8], r13
0x140004e18  call    cs:__imp_GetCurrentThreadId
0x140004e1e  mov     [rsp+1510h+var_14D0], eax
0x140004e22  mov     [rsp+1510h+var_14B8], rsi
0x140004e27  mov     [rsp+1510h+var_14B0], edi
0x140004e2b  mov     [rsp+1510h+var_14AC], r12d
0x140004e30  mov     [rsp+1510h+var_14C8], r13
0x140004e35  mov     [rsp+1510h+var_14C0], r14
0x140004e3a  mov     [rbp+1410h+var_1468], r15
0x140004e3e  mov     [rbp+1410h+var_1460], rbx
0x140004e42  mov     [rsp+1510h+var_14A8], r13
0x140004e47  xorps   xmm0, xmm0
0x140004e4a  xor     eax, eax
0x140004e4c  movups  [rbp+1410h+var_1488], xmm0
0x140004e50  mov     [rbp+1410h+var_1478], rax
0x140004e54  xorps   xmm1, xmm1
0x140004e57  movups  [rsp+1510h+var_14A0], xmm1
0x140004e5c  mov     [rbp+1410h+var_1490], rax
0x140004e60  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140004e67  test    rax, rax
0x140004e6a  jz      short loc_140004E77
0x140004e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e71  mov     [rbp+1410h+var_1470], rax
0x140004e75  jmp     short loc_140004E7B
0x140004e77  mov     [rbp+1410h+var_1470], r13
0x140004e7b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004e82  test    rax, rax
0x140004e85  jz      short loc_140004E91
0x140004e87  lea     rcx, [rsp+1510h+var_14F0]
0x140004e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e91  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004e98  test    rax, rax
0x140004e9b  jz      short loc_140004EB1
0x140004e9d  mov     r8d, 400h
0x140004ea3  lea     rdx, [rbp+1410h+var_1450]
0x140004ea7  lea     rcx, [rsp+1510h+var_14F0]
0x140004eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004eb1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004eb8  test    rax, rax
0x140004ebb  jz      short loc_140004EC7
0x140004ebd  lea     rcx, [rsp+1510h+var_14F0]
0x140004ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ec7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004ece  test    rax, rax
0x140004ed1  jz      short loc_140004EE4
0x140004ed3  test    byte ptr [rsp+1510h+var_14F0+4], 2
0x140004ed8  jnz     short loc_140004EE4
0x140004eda  lea     rcx, [rsp+1510h+var_14F0]
0x140004edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ee4  cmp     [rsp+1510h+var_14E8], r13d
0x140004ee9  jge     loc_140004FF4
0x140004eef  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140004ef6  jnz     short loc_140004F17
0x140004ef8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004eff  test    rax, rax
0x140004f02  jz      short loc_140004F0D
0x140004f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f09  test    al, al
0x140004f0b  jmp     short loc_140004F15
0x140004f0d  call    cs:__imp_IsDebuggerPresent
0x140004f13  test    eax, eax
0x140004f15  jz      short loc_140004F1E
0x140004f17  test    byte ptr [rsp+1510h+var_14F0+4], 2
0x140004f1c  jz      short loc_140004F44
0x140004f1e  mov     rax, cs:g_pfnResultLoggingCallback
0x140004f25  test    rax, rax
0x140004f28  jz      short loc_140004F9D
0x140004f2a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140004f31  jnz     short loc_140004F9D
0x140004f33  xor     r8d, r8d
0x140004f36  xor     edx, edx
0x140004f38  lea     rcx, [rsp+1510h+var_14F0]
0x140004f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f42  jmp     short loc_140004F9D
0x140004f44  mov     ebx, 800h
0x140004f49  mov     rax, cs:g_pfnResultLoggingCallback
0x140004f50  test    rax, rax
0x140004f53  jz      short loc_140004F72
0x140004f55  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140004f5c  jnz     short loc_140004F72
0x140004f5e  mov     r8d, ebx
0x140004f61  lea     rdx, [rbp+1410h+OutputString]
0x140004f68  lea     rcx, [rsp+1510h+var_14F0]
0x140004f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f72  cmp     [rbp+1410h+OutputString], r13w
0x140004f7a  jnz     short loc_140004F90
0x140004f7c  lea     r8, [rsp+1510h+var_14F0]; unsigned __int64
0x140004f81  mov     rdx, rbx; wchar_t *
0x140004f84  lea     rcx, [rbp+1410h+OutputString]; this
0x140004f8b  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140004f90  lea     rcx, [rbp+1410h+OutputString]; lpOutputString
0x140004f97  call    cs:__imp_OutputDebugStringW
0x140004f9d  test    byte ptr [rsp+1510h+var_14F0+4], 4
0x140004fa2  jnz     short loc_140004FAD
0x140004fa4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140004fab  jz      short loc_140004FBF
0x140004fad  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140004fb4  test    rax, rax
0x140004fb7  jz      short loc_140004FBF
0x140004fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004fbe  nop
0x140004fbf  test    byte ptr [rsp+1510h+var_14F0+4], 1
0x140004fc4  jnz     short loc_140004FE9
0x140004fc6  mov     rcx, [rbp+1410h+var_50]
0x140004fcd  xor     rcx, rsp; StackCookie
0x140004fd0  call    __security_check_cookie
0x140004fd5  add     rsp, 14D8h
0x140004fdc  pop     r15
0x140004fde  pop     r14
0x140004fe0  pop     r13
0x140004fe2  pop     r12
0x140004fe4  pop     rdi
0x140004fe5  pop     rsi
0x140004fe6  pop     rbx
0x140004fe7  pop     rbp
0x140004fe8  retn
0x140004fe9  lea     rcx, [rsp+1510h+var_14F0]; this
0x140004fee  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140004ff4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
