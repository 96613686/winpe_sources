# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140004d58`
- end: `0x140005019`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `705`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400046dc`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x140004d58`
- `0x140007a24`
- `0x140009698`
- `0x14000c53c`
- `0x14000c710`
- `0x14005f510`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004e24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004e24`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004f1f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004f1f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004faf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004faf`

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
0x140004d58  push    rbp
0x140004d5a  push    rbx
0x140004d5b  push    rsi
0x140004d5c  push    rdi
0x140004d5d  push    r12
0x140004d5f  push    r13
0x140004d61  push    r14
0x140004d63  push    r15
0x140004d65  lea     rbp, [rsp-13D8h]
0x140004d6d  mov     eax, 14D8h
0x140004d72  call    _alloca_probe
0x140004d77  sub     rsp, rax
0x140004d7a  mov     rax, cs:__security_cookie
0x140004d81  xor     rax, rsp
0x140004d84  mov     [rbp+1410h+var_50], rax
0x140004d8b  mov     r14, r9
0x140004d8e  mov     rsi, r8
0x140004d91  mov     edi, edx
0x140004d93  mov     rbx, rcx
0x140004d96  mov     r15, [rbp+1410h+arg_28]
0x140004d9d  xor     edx, edx; Val
0x140004d9f  mov     r8d, 98h; Size
0x140004da5  lea     rcx, [rsp+1510h+var_14F0]; void *
0x140004daa  call    memset_0
0x140004daf  nop
0x140004db0  xor     r13d, r13d
0x140004db3  mov     [rbp+1410h+OutputString], r13w
0x140004dbb  mov     [rbp+1410h+var_1450], r13b
0x140004dbf  mov     rdx, [rbp+1410h+arg_30]; int
0x140004dc6  mov     ecx, [rdx]; this
0x140004dc8  mov     [rsp+1510h+var_14E8], ecx
0x140004dcc  mov     eax, [rdx+4]
0x140004dcf  mov     [rsp+1510h+var_14E4], eax
0x140004dd3  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140004dd8  mov     r12d, eax
0x140004ddb  lea     r8d, [r13+1]
0x140004ddf  mov     dword ptr [rsp+1510h+var_14F0], r8d
0x140004de4  mov     ecx, r13d
0x140004de7  lea     eax, [r13+8]
0x140004deb  cmp     [rdx+8], r8d
0x140004def  cmovz   ecx, eax
0x140004df2  mov     dword ptr [rsp+1510h+var_14F0+4], ecx
0x140004df6  mov     ecx, r8d
0x140004df9  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140004e01  add     ecx, r8d
0x140004e04  mov     [rsp+1510h+var_14E0], ecx
0x140004e08  mov     rcx, [rbp+1410h+arg_38]
0x140004e0f  test    rcx, rcx
0x140004e12  jz      short loc_140004E1F
0x140004e14  cmp     [rcx], r13w
0x140004e18  mov     [rsp+1510h+var_14D8], rcx
0x140004e1d  jnz     short loc_140004E24
0x140004e1f  mov     [rsp+1510h+var_14D8], r13
0x140004e24  call    cs:__imp_GetCurrentThreadId
0x140004e2b  nop     dword ptr [rax+rax+00h]
0x140004e30  mov     [rsp+1510h+var_14D0], eax
0x140004e34  mov     [rsp+1510h+var_14B8], rsi
0x140004e39  mov     [rsp+1510h+var_14B0], edi
0x140004e3d  mov     [rsp+1510h+var_14AC], r12d
0x140004e42  mov     [rsp+1510h+var_14C8], r13
0x140004e47  mov     [rsp+1510h+var_14C0], r14
0x140004e4c  mov     [rbp+1410h+var_1468], r15
0x140004e50  mov     [rbp+1410h+var_1460], rbx
0x140004e54  mov     [rsp+1510h+var_14A8], r13
0x140004e59  xorps   xmm0, xmm0
0x140004e5c  xor     eax, eax
0x140004e5e  movups  [rbp+1410h+var_1488], xmm0
0x140004e62  mov     [rbp+1410h+var_1478], rax
0x140004e66  xorps   xmm1, xmm1
0x140004e69  movups  [rsp+1510h+var_14A0], xmm1
0x140004e6e  mov     [rbp+1410h+var_1490], rax
0x140004e72  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140004e79  test    rax, rax
0x140004e7c  jz      short loc_140004E89
0x140004e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e83  mov     [rbp+1410h+var_1470], rax
0x140004e87  jmp     short loc_140004E8D
0x140004e89  mov     [rbp+1410h+var_1470], r13
0x140004e8d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004e94  test    rax, rax
0x140004e97  jz      short loc_140004EA3
0x140004e99  lea     rcx, [rsp+1510h+var_14F0]
0x140004e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ea3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004eaa  test    rax, rax
0x140004ead  jz      short loc_140004EC3
0x140004eaf  mov     r8d, 400h
0x140004eb5  lea     rdx, [rbp+1410h+var_1450]
0x140004eb9  lea     rcx, [rsp+1510h+var_14F0]
0x140004ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ec3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004eca  test    rax, rax
0x140004ecd  jz      short loc_140004ED9
0x140004ecf  lea     rcx, [rsp+1510h+var_14F0]
0x140004ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ed9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004ee0  test    rax, rax
0x140004ee3  jz      short loc_140004EF6
0x140004ee5  test    byte ptr [rsp+1510h+var_14F0+4], 2
0x140004eea  jnz     short loc_140004EF6
0x140004eec  lea     rcx, [rsp+1510h+var_14F0]
0x140004ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ef6  cmp     [rsp+1510h+var_14E8], r13d
0x140004efb  jge     loc_140005013
0x140004f01  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140004f08  jnz     short loc_140004F2F
0x140004f0a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004f11  test    rax, rax
0x140004f14  jz      short loc_140004F1F
0x140004f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f1b  test    al, al
0x140004f1d  jmp     short loc_140004F2D
0x140004f1f  call    cs:__imp_IsDebuggerPresent
0x140004f26  nop     dword ptr [rax+rax+00h]
0x140004f2b  test    eax, eax
0x140004f2d  jz      short loc_140004F36
0x140004f2f  test    byte ptr [rsp+1510h+var_14F0+4], 2
0x140004f34  jz      short loc_140004F5C
0x140004f36  mov     rax, cs:g_pfnResultLoggingCallback
0x140004f3d  test    rax, rax
0x140004f40  jz      short loc_140004FBB
0x140004f42  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140004f49  jnz     short loc_140004FBB
0x140004f4b  xor     r8d, r8d
0x140004f4e  xor     edx, edx
0x140004f50  lea     rcx, [rsp+1510h+var_14F0]
0x140004f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f5a  jmp     short loc_140004FBB
0x140004f5c  mov     ebx, 800h
0x140004f61  mov     rax, cs:g_pfnResultLoggingCallback
0x140004f68  test    rax, rax
0x140004f6b  jz      short loc_140004F8A
0x140004f6d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140004f74  jnz     short loc_140004F8A
0x140004f76  mov     r8d, ebx
0x140004f79  lea     rdx, [rbp+1410h+OutputString]
0x140004f80  lea     rcx, [rsp+1510h+var_14F0]
0x140004f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f8a  cmp     [rbp+1410h+OutputString], r13w
0x140004f92  jnz     short loc_140004FA8
0x140004f94  lea     r8, [rsp+1510h+var_14F0]; unsigned __int64
0x140004f99  mov     rdx, rbx; wchar_t *
0x140004f9c  lea     rcx, [rbp+1410h+OutputString]; this
0x140004fa3  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140004fa8  lea     rcx, [rbp+1410h+OutputString]; lpOutputString
0x140004faf  call    cs:__imp_OutputDebugStringW
0x140004fb6  nop     dword ptr [rax+rax+00h]
0x140004fbb  test    byte ptr [rsp+1510h+var_14F0+4], 4
0x140004fc0  jnz     short loc_140004FCB
0x140004fc2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140004fc9  jz      short loc_140004FDD
0x140004fcb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140004fd2  test    rax, rax
0x140004fd5  jz      short loc_140004FDD
0x140004fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004fdc  nop
0x140004fdd  test    byte ptr [rsp+1510h+var_14F0+4], 1
0x140004fe2  jnz     short loc_140005008
0x140004fe4  mov     rcx, [rbp+1410h+var_50]
0x140004feb  xor     rcx, rsp; StackCookie
0x140004fee  call    __security_check_cookie
0x140004ff3  add     rsp, 14D8h
0x140004ffa  pop     r15
0x140004ffc  pop     r14
0x140004ffe  pop     r13
0x140005000  pop     r12
0x140005002  pop     rdi
0x140005003  pop     rsi
0x140005004  pop     rbx
0x140005005  pop     rbp
0x140005006  retn
0x140005008  lea     rcx, [rsp+1510h+var_14F0]; this
0x14000500d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140005013  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
