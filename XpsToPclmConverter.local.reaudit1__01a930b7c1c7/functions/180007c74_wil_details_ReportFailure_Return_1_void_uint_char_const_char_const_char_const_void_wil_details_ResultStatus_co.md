# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180007c74`
- end: `0x180007f1a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800078f0`

## callees

- `0x1800015f0`
- `0x180002148`
- `0x180007c74`
- `0x1800095d4`
- `0x18000afc0`
- `0x18000c8c8`
- `0x18000cad4`
- `0x18001cbf0`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007d3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007d3a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007e2f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007e2f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007eb9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007eb9`

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
0x180007c74  push    rbp
0x180007c76  push    rbx
0x180007c77  push    rsi
0x180007c78  push    rdi
0x180007c79  push    r12
0x180007c7b  push    r14
0x180007c7d  push    r15
0x180007c7f  lea     rbp, [rsp-13D0h]
0x180007c87  mov     eax, 14D0h
0x180007c8c  call    _alloca_probe
0x180007c91  sub     rsp, rax
0x180007c94  mov     rax, cs:__security_cookie
0x180007c9b  xor     rax, rsp
0x180007c9e  mov     [rbp+1400h+var_40], rax
0x180007ca5  mov     rsi, r8
0x180007ca8  mov     edi, edx
0x180007caa  mov     rbx, rcx
0x180007cad  mov     r14, [rbp+1400h+arg_28]
0x180007cb4  xor     edx, edx; Val
0x180007cb6  mov     r8d, 98h; Size
0x180007cbc  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180007cc1  call    memset_0
0x180007cc6  nop
0x180007cc7  xor     r12d, r12d
0x180007cca  mov     [rbp+1400h+OutputString], r12w
0x180007cd2  mov     [rbp+1400h+var_1440], r12b
0x180007cd6  mov     rdx, [rbp+1400h+arg_30]; int
0x180007cdd  mov     ecx, [rdx]; this
0x180007cdf  mov     [rsp+1500h+var_14D8], ecx
0x180007ce3  mov     eax, [rdx+4]
0x180007ce6  mov     [rsp+1500h+var_14D4], eax
0x180007cea  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007cef  mov     r15d, eax
0x180007cf2  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180007cfa  mov     ecx, r12d
0x180007cfd  lea     eax, [r12+8]
0x180007d02  cmp     dword ptr [rdx+8], 1
0x180007d06  cmovz   ecx, eax
0x180007d09  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180007d0d  lea     ecx, [rax-7]
0x180007d10  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007d18  inc     ecx
0x180007d1a  mov     [rsp+1500h+var_14D0], ecx
0x180007d1e  mov     rcx, [rbp+1400h+arg_38]
0x180007d25  test    rcx, rcx
0x180007d28  jz      short loc_180007D35
0x180007d2a  cmp     [rcx], r12w
0x180007d2e  mov     [rsp+1500h+var_14C8], rcx
0x180007d33  jnz     short loc_180007D3A
0x180007d35  mov     [rsp+1500h+var_14C8], r12
0x180007d3a  call    cs:__imp_GetCurrentThreadId
0x180007d40  mov     [rsp+1500h+var_14C0], eax
0x180007d44  mov     [rsp+1500h+var_14A8], rsi
0x180007d49  mov     [rsp+1500h+var_14A0], edi
0x180007d4d  mov     [rsp+1500h+var_149C], r15d
0x180007d52  mov     [rsp+1500h+var_14B8], r12
0x180007d57  mov     [rsp+1500h+var_14B0], r12
0x180007d5c  mov     [rbp+1400h+var_1458], r14
0x180007d60  mov     [rbp+1400h+var_1450], rbx
0x180007d64  mov     [rsp+1500h+var_1498], r12
0x180007d69  xorps   xmm0, xmm0
0x180007d6c  xor     eax, eax
0x180007d6e  movups  [rbp+1400h+var_1478], xmm0
0x180007d72  mov     [rbp+1400h+var_1468], rax
0x180007d76  xorps   xmm1, xmm1
0x180007d79  movups  [rsp+1500h+var_1490], xmm1
0x180007d7e  mov     [rbp+1400h+var_1480], rax
0x180007d82  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007d89  test    rax, rax
0x180007d8c  jz      short loc_180007D99
0x180007d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d93  mov     [rbp+1400h+var_1460], rax
0x180007d97  jmp     short loc_180007D9D
0x180007d99  mov     [rbp+1400h+var_1460], r12
0x180007d9d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007da4  test    rax, rax
0x180007da7  jz      short loc_180007DB3
0x180007da9  lea     rcx, [rsp+1500h+var_14E0]
0x180007dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007db3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007dba  test    rax, rax
0x180007dbd  jz      short loc_180007DD3
0x180007dbf  mov     r8d, 400h
0x180007dc5  lea     rdx, [rbp+1400h+var_1440]
0x180007dc9  lea     rcx, [rsp+1500h+var_14E0]
0x180007dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dd3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007dda  test    rax, rax
0x180007ddd  jz      short loc_180007DE9
0x180007ddf  lea     rcx, [rsp+1500h+var_14E0]
0x180007de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007de9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007df0  test    rax, rax
0x180007df3  jz      short loc_180007E06
0x180007df5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180007dfa  jnz     short loc_180007E06
0x180007dfc  lea     rcx, [rsp+1500h+var_14E0]
0x180007e01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e06  cmp     [rsp+1500h+var_14D8], r12d
0x180007e0b  jge     loc_180007F14
0x180007e11  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180007e18  jnz     short loc_180007E39
0x180007e1a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007e21  test    rax, rax
0x180007e24  jz      short loc_180007E2F
0x180007e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e2b  test    al, al
0x180007e2d  jmp     short loc_180007E37
0x180007e2f  call    cs:__imp_IsDebuggerPresent
0x180007e35  test    eax, eax
0x180007e37  jz      short loc_180007E40
0x180007e39  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180007e3e  jz      short loc_180007E66
0x180007e40  mov     rax, cs:g_pfnResultLoggingCallback
0x180007e47  test    rax, rax
0x180007e4a  jz      short loc_180007EBF
0x180007e4c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180007e53  jnz     short loc_180007EBF
0x180007e55  xor     r8d, r8d
0x180007e58  xor     edx, edx
0x180007e5a  lea     rcx, [rsp+1500h+var_14E0]
0x180007e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e64  jmp     short loc_180007EBF
0x180007e66  mov     ebx, 800h
0x180007e6b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007e72  test    rax, rax
0x180007e75  jz      short loc_180007E94
0x180007e77  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180007e7e  jnz     short loc_180007E94
0x180007e80  mov     r8d, ebx
0x180007e83  lea     rdx, [rbp+1400h+OutputString]
0x180007e8a  lea     rcx, [rsp+1500h+var_14E0]
0x180007e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e94  cmp     [rbp+1400h+OutputString], r12w
0x180007e9c  jnz     short loc_180007EB2
0x180007e9e  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180007ea3  mov     rdx, rbx; unsigned __int16 *
0x180007ea6  lea     rcx, [rbp+1400h+OutputString]; this
0x180007ead  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007eb2  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180007eb9  call    cs:__imp_OutputDebugStringW
0x180007ebf  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180007ec4  jnz     short loc_180007ECF
0x180007ec6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180007ecd  jz      short loc_180007EE1
0x180007ecf  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007ed6  test    rax, rax
0x180007ed9  jz      short loc_180007EE1
0x180007edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ee0  nop
0x180007ee1  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180007ee6  jnz     short loc_180007F09
0x180007ee8  mov     rcx, [rbp+1400h+var_40]
0x180007eef  xor     rcx, rsp; StackCookie
0x180007ef2  call    __security_check_cookie
0x180007ef7  add     rsp, 14D0h
0x180007efe  pop     r15
0x180007f00  pop     r14
0x180007f02  pop     r12
0x180007f04  pop     rdi
0x180007f05  pop     rsi
0x180007f06  pop     rbx
0x180007f07  pop     rbp
0x180007f08  retn
0x180007f09  lea     rcx, [rsp+1500h+var_14E0]; this
0x180007f0e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180007f14  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
