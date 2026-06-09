# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004e94`
- end: `0x18000513a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004b14`

## callees

- `0x1800032b0`
- `0x180004200`
- `0x180004e94`
- `0x180005dc4`
- `0x180006f20`
- `0x180007b58`
- `0x180007d14`
- `0x18004b6e0`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f5a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800050d9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800050d9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000504f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000504f`

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
0x180004e94  push    rbp
0x180004e96  push    rbx
0x180004e97  push    rsi
0x180004e98  push    rdi
0x180004e99  push    r12
0x180004e9b  push    r14
0x180004e9d  push    r15
0x180004e9f  lea     rbp, [rsp-13D0h]
0x180004ea7  mov     eax, 14D0h
0x180004eac  call    _alloca_probe
0x180004eb1  sub     rsp, rax
0x180004eb4  mov     rax, cs:__security_cookie
0x180004ebb  xor     rax, rsp
0x180004ebe  mov     [rbp+1400h+var_40], rax
0x180004ec5  mov     rsi, r8
0x180004ec8  mov     edi, edx
0x180004eca  mov     rbx, rcx
0x180004ecd  mov     r14, [rbp+1400h+arg_28]
0x180004ed4  xor     edx, edx; Val
0x180004ed6  mov     r8d, 98h; Size
0x180004edc  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004ee1  call    memset_0
0x180004ee6  nop
0x180004ee7  xor     r12d, r12d
0x180004eea  mov     [rbp+1400h+OutputString], r12w
0x180004ef2  mov     [rbp+1400h+var_1440], r12b
0x180004ef6  mov     rdx, [rbp+1400h+arg_30]; int
0x180004efd  mov     ecx, [rdx]; this
0x180004eff  mov     [rsp+1500h+var_14D8], ecx
0x180004f03  mov     eax, [rdx+4]
0x180004f06  mov     [rsp+1500h+var_14D4], eax
0x180004f0a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004f0f  mov     r15d, eax
0x180004f12  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180004f1a  mov     ecx, r12d
0x180004f1d  lea     eax, [r12+8]
0x180004f22  cmp     dword ptr [rdx+8], 1
0x180004f26  cmovz   ecx, eax
0x180004f29  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180004f2d  lea     ecx, [rax-7]
0x180004f30  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004f38  inc     ecx
0x180004f3a  mov     [rsp+1500h+var_14D0], ecx
0x180004f3e  mov     rcx, [rbp+1400h+arg_38]
0x180004f45  test    rcx, rcx
0x180004f48  jz      short loc_180004F55
0x180004f4a  cmp     [rcx], r12w
0x180004f4e  mov     [rsp+1500h+var_14C8], rcx
0x180004f53  jnz     short loc_180004F5A
0x180004f55  mov     [rsp+1500h+var_14C8], r12
0x180004f5a  call    cs:__imp_GetCurrentThreadId
0x180004f60  mov     [rsp+1500h+var_14C0], eax
0x180004f64  mov     [rsp+1500h+var_14A8], rsi
0x180004f69  mov     [rsp+1500h+var_14A0], edi
0x180004f6d  mov     [rsp+1500h+var_149C], r15d
0x180004f72  mov     [rsp+1500h+var_14B8], r12
0x180004f77  mov     [rsp+1500h+var_14B0], r12
0x180004f7c  mov     [rbp+1400h+var_1458], r14
0x180004f80  mov     [rbp+1400h+var_1450], rbx
0x180004f84  mov     [rsp+1500h+var_1498], r12
0x180004f89  xorps   xmm0, xmm0
0x180004f8c  xor     eax, eax
0x180004f8e  movups  [rbp+1400h+var_1478], xmm0
0x180004f92  mov     [rbp+1400h+var_1468], rax
0x180004f96  xorps   xmm1, xmm1
0x180004f99  movups  [rsp+1500h+var_1490], xmm1
0x180004f9e  mov     [rbp+1400h+var_1480], rax
0x180004fa2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004fa9  test    rax, rax
0x180004fac  jz      short loc_180004FB9
0x180004fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fb3  mov     [rbp+1400h+var_1460], rax
0x180004fb7  jmp     short loc_180004FBD
0x180004fb9  mov     [rbp+1400h+var_1460], r12
0x180004fbd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004fc4  test    rax, rax
0x180004fc7  jz      short loc_180004FD3
0x180004fc9  lea     rcx, [rsp+1500h+var_14E0]
0x180004fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fd3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004fda  test    rax, rax
0x180004fdd  jz      short loc_180004FF3
0x180004fdf  mov     r8d, 400h
0x180004fe5  lea     rdx, [rbp+1400h+var_1440]
0x180004fe9  lea     rcx, [rsp+1500h+var_14E0]
0x180004fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ff3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004ffa  test    rax, rax
0x180004ffd  jz      short loc_180005009
0x180004fff  lea     rcx, [rsp+1500h+var_14E0]
0x180005004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005009  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005010  test    rax, rax
0x180005013  jz      short loc_180005026
0x180005015  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000501a  jnz     short loc_180005026
0x18000501c  lea     rcx, [rsp+1500h+var_14E0]
0x180005021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005026  cmp     [rsp+1500h+var_14D8], r12d
0x18000502b  jge     loc_180005134
0x180005031  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180005038  jnz     short loc_180005059
0x18000503a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005041  test    rax, rax
0x180005044  jz      short loc_18000504F
0x180005046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000504b  test    al, al
0x18000504d  jmp     short loc_180005057
0x18000504f  call    cs:__imp_IsDebuggerPresent
0x180005055  test    eax, eax
0x180005057  jz      short loc_180005060
0x180005059  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000505e  jz      short loc_180005086
0x180005060  mov     rax, cs:g_pfnResultLoggingCallback
0x180005067  test    rax, rax
0x18000506a  jz      short loc_1800050DF
0x18000506c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005073  jnz     short loc_1800050DF
0x180005075  xor     r8d, r8d
0x180005078  xor     edx, edx
0x18000507a  lea     rcx, [rsp+1500h+var_14E0]
0x18000507f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005084  jmp     short loc_1800050DF
0x180005086  mov     ebx, 800h
0x18000508b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005092  test    rax, rax
0x180005095  jz      short loc_1800050B4
0x180005097  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000509e  jnz     short loc_1800050B4
0x1800050a0  mov     r8d, ebx
0x1800050a3  lea     rdx, [rbp+1400h+OutputString]
0x1800050aa  lea     rcx, [rsp+1500h+var_14E0]
0x1800050af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050b4  cmp     [rbp+1400h+OutputString], r12w
0x1800050bc  jnz     short loc_1800050D2
0x1800050be  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800050c3  mov     rdx, rbx; unsigned __int16 *
0x1800050c6  lea     rcx, [rbp+1400h+OutputString]; this
0x1800050cd  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800050d2  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800050d9  call    cs:__imp_OutputDebugStringW
0x1800050df  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800050e4  jnz     short loc_1800050EF
0x1800050e6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800050ed  jz      short loc_180005101
0x1800050ef  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800050f6  test    rax, rax
0x1800050f9  jz      short loc_180005101
0x1800050fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005100  nop
0x180005101  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180005106  jnz     short loc_180005129
0x180005108  mov     rcx, [rbp+1400h+var_40]
0x18000510f  xor     rcx, rsp; StackCookie
0x180005112  call    __security_check_cookie
0x180005117  add     rsp, 14D0h
0x18000511e  pop     r15
0x180005120  pop     r14
0x180005122  pop     r12
0x180005124  pop     rdi
0x180005125  pop     rsi
0x180005126  pop     rbx
0x180005127  pop     rbp
0x180005128  retn
0x180005129  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000512e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005134  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
