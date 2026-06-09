# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004d90`
- end: `0x180005036`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004820`

## callees

- `0x1800038f0`
- `0x1800046a0`
- `0x180004d90`
- `0x180007144`
- `0x180008620`
- `0x18000a830`
- `0x18000a924`
- `0x18001f830`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e56`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004f4b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004f4b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004fd5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004fd5`

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
0x180004d90  push    rbp
0x180004d92  push    rbx
0x180004d93  push    rsi
0x180004d94  push    rdi
0x180004d95  push    r12
0x180004d97  push    r14
0x180004d99  push    r15
0x180004d9b  lea     rbp, [rsp-13D0h]
0x180004da3  mov     eax, 14D0h
0x180004da8  call    _alloca_probe
0x180004dad  sub     rsp, rax
0x180004db0  mov     rax, cs:__security_cookie
0x180004db7  xor     rax, rsp
0x180004dba  mov     [rbp+1400h+var_40], rax
0x180004dc1  mov     rsi, r8
0x180004dc4  mov     edi, edx
0x180004dc6  mov     rbx, rcx
0x180004dc9  mov     r14, [rbp+1400h+arg_28]
0x180004dd0  xor     edx, edx; Val
0x180004dd2  mov     r8d, 98h; Size
0x180004dd8  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004ddd  call    memset_0
0x180004de2  nop
0x180004de3  xor     r12d, r12d
0x180004de6  mov     [rbp+1400h+OutputString], r12w
0x180004dee  mov     [rbp+1400h+var_1440], r12b
0x180004df2  mov     rdx, [rbp+1400h+arg_30]; int
0x180004df9  mov     ecx, [rdx]; this
0x180004dfb  mov     [rsp+1500h+var_14D8], ecx
0x180004dff  mov     eax, [rdx+4]
0x180004e02  mov     [rsp+1500h+var_14D4], eax
0x180004e06  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004e0b  mov     r15d, eax
0x180004e0e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180004e16  mov     ecx, r12d
0x180004e19  lea     eax, [r12+8]
0x180004e1e  cmp     dword ptr [rdx+8], 1
0x180004e22  cmovz   ecx, eax
0x180004e25  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180004e29  lea     ecx, [rax-7]
0x180004e2c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004e34  inc     ecx
0x180004e36  mov     [rsp+1500h+var_14D0], ecx
0x180004e3a  mov     rcx, [rbp+1400h+arg_38]
0x180004e41  test    rcx, rcx
0x180004e44  jz      short loc_180004E51
0x180004e46  cmp     [rcx], r12w
0x180004e4a  mov     [rsp+1500h+var_14C8], rcx
0x180004e4f  jnz     short loc_180004E56
0x180004e51  mov     [rsp+1500h+var_14C8], r12
0x180004e56  call    cs:__imp_GetCurrentThreadId
0x180004e5c  mov     [rsp+1500h+var_14C0], eax
0x180004e60  mov     [rsp+1500h+var_14A8], rsi
0x180004e65  mov     [rsp+1500h+var_14A0], edi
0x180004e69  mov     [rsp+1500h+var_149C], r15d
0x180004e6e  mov     [rsp+1500h+var_14B8], r12
0x180004e73  mov     [rsp+1500h+var_14B0], r12
0x180004e78  mov     [rbp+1400h+var_1458], r14
0x180004e7c  mov     [rbp+1400h+var_1450], rbx
0x180004e80  mov     [rsp+1500h+var_1498], r12
0x180004e85  xorps   xmm0, xmm0
0x180004e88  xor     eax, eax
0x180004e8a  movups  [rbp+1400h+var_1478], xmm0
0x180004e8e  mov     [rbp+1400h+var_1468], rax
0x180004e92  xorps   xmm1, xmm1
0x180004e95  movups  [rsp+1500h+var_1490], xmm1
0x180004e9a  mov     [rbp+1400h+var_1480], rax
0x180004e9e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004ea5  test    rax, rax
0x180004ea8  jz      short loc_180004EB5
0x180004eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eaf  mov     [rbp+1400h+var_1460], rax
0x180004eb3  jmp     short loc_180004EB9
0x180004eb5  mov     [rbp+1400h+var_1460], r12
0x180004eb9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004ec0  test    rax, rax
0x180004ec3  jz      short loc_180004ECF
0x180004ec5  lea     rcx, [rsp+1500h+var_14E0]
0x180004eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ecf  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004ed6  test    rax, rax
0x180004ed9  jz      short loc_180004EEF
0x180004edb  mov     r8d, 400h
0x180004ee1  lea     rdx, [rbp+1400h+var_1440]
0x180004ee5  lea     rcx, [rsp+1500h+var_14E0]
0x180004eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eef  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004ef6  test    rax, rax
0x180004ef9  jz      short loc_180004F05
0x180004efb  lea     rcx, [rsp+1500h+var_14E0]
0x180004f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f05  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004f0c  test    rax, rax
0x180004f0f  jz      short loc_180004F22
0x180004f11  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004f16  jnz     short loc_180004F22
0x180004f18  lea     rcx, [rsp+1500h+var_14E0]
0x180004f1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f22  cmp     [rsp+1500h+var_14D8], r12d
0x180004f27  jge     loc_180005030
0x180004f2d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180004f34  jnz     short loc_180004F55
0x180004f36  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004f3d  test    rax, rax
0x180004f40  jz      short loc_180004F4B
0x180004f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f47  test    al, al
0x180004f49  jmp     short loc_180004F53
0x180004f4b  call    cs:__imp_IsDebuggerPresent
0x180004f51  test    eax, eax
0x180004f53  jz      short loc_180004F5C
0x180004f55  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004f5a  jz      short loc_180004F82
0x180004f5c  mov     rax, cs:g_pfnResultLoggingCallback
0x180004f63  test    rax, rax
0x180004f66  jz      short loc_180004FDB
0x180004f68  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004f6f  jnz     short loc_180004FDB
0x180004f71  xor     r8d, r8d
0x180004f74  xor     edx, edx
0x180004f76  lea     rcx, [rsp+1500h+var_14E0]
0x180004f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f80  jmp     short loc_180004FDB
0x180004f82  mov     ebx, 800h
0x180004f87  mov     rax, cs:g_pfnResultLoggingCallback
0x180004f8e  test    rax, rax
0x180004f91  jz      short loc_180004FB0
0x180004f93  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004f9a  jnz     short loc_180004FB0
0x180004f9c  mov     r8d, ebx
0x180004f9f  lea     rdx, [rbp+1400h+OutputString]
0x180004fa6  lea     rcx, [rsp+1500h+var_14E0]
0x180004fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fb0  cmp     [rbp+1400h+OutputString], r12w
0x180004fb8  jnz     short loc_180004FCE
0x180004fba  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180004fbf  mov     rdx, rbx; unsigned __int16 *
0x180004fc2  lea     rcx, [rbp+1400h+OutputString]; this
0x180004fc9  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004fce  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004fd5  call    cs:__imp_OutputDebugStringW
0x180004fdb  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004fe0  jnz     short loc_180004FEB
0x180004fe2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004fe9  jz      short loc_180004FFD
0x180004feb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004ff2  test    rax, rax
0x180004ff5  jz      short loc_180004FFD
0x180004ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ffc  nop
0x180004ffd  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180005002  jnz     short loc_180005025
0x180005004  mov     rcx, [rbp+1400h+var_40]
0x18000500b  xor     rcx, rsp; StackCookie
0x18000500e  call    __security_check_cookie
0x180005013  add     rsp, 14D0h
0x18000501a  pop     r15
0x18000501c  pop     r14
0x18000501e  pop     r12
0x180005020  pop     rdi
0x180005021  pop     rsi
0x180005022  pop     rbx
0x180005023  pop     rbp
0x180005024  retn
0x180005025  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000502a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005030  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
