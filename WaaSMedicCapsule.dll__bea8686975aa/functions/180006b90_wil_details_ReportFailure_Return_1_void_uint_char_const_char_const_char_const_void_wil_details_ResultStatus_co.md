# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180006b90`
- end: `0x180006e36`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180006620`

## callees

- `0x180003bb0`
- `0x180004708`
- `0x180006b90`
- `0x180008254`
- `0x1800097a0`
- `0x18000a9b0`
- `0x18000ab38`
- `0x180060700`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006c56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006c56`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006dd5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006dd5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006d4b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006d4b`

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
0x180006b90  push    rbp
0x180006b92  push    rbx
0x180006b93  push    rsi
0x180006b94  push    rdi
0x180006b95  push    r12
0x180006b97  push    r14
0x180006b99  push    r15
0x180006b9b  lea     rbp, [rsp-13D0h]
0x180006ba3  mov     eax, 14D0h
0x180006ba8  call    _alloca_probe
0x180006bad  sub     rsp, rax
0x180006bb0  mov     rax, cs:__security_cookie
0x180006bb7  xor     rax, rsp
0x180006bba  mov     [rbp+1400h+var_40], rax
0x180006bc1  mov     rsi, r8
0x180006bc4  mov     edi, edx
0x180006bc6  mov     rbx, rcx
0x180006bc9  mov     r14, [rbp+1400h+arg_28]
0x180006bd0  xor     edx, edx; Val
0x180006bd2  mov     r8d, 98h; Size
0x180006bd8  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180006bdd  call    memset_0
0x180006be2  nop
0x180006be3  xor     r12d, r12d
0x180006be6  mov     [rbp+1400h+OutputString], r12w
0x180006bee  mov     [rbp+1400h+var_1440], r12b
0x180006bf2  mov     rdx, [rbp+1400h+arg_30]; int
0x180006bf9  mov     ecx, [rdx]; this
0x180006bfb  mov     [rsp+1500h+var_14D8], ecx
0x180006bff  mov     eax, [rdx+4]
0x180006c02  mov     [rsp+1500h+var_14D4], eax
0x180006c06  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006c0b  mov     r15d, eax
0x180006c0e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180006c16  mov     ecx, r12d
0x180006c19  lea     eax, [r12+8]
0x180006c1e  cmp     dword ptr [rdx+8], 1
0x180006c22  cmovz   ecx, eax
0x180006c25  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180006c29  lea     ecx, [rax-7]
0x180006c2c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006c34  inc     ecx
0x180006c36  mov     [rsp+1500h+var_14D0], ecx
0x180006c3a  mov     rcx, [rbp+1400h+arg_38]
0x180006c41  test    rcx, rcx
0x180006c44  jz      short loc_180006C51
0x180006c46  cmp     [rcx], r12w
0x180006c4a  mov     [rsp+1500h+var_14C8], rcx
0x180006c4f  jnz     short loc_180006C56
0x180006c51  mov     [rsp+1500h+var_14C8], r12
0x180006c56  call    cs:__imp_GetCurrentThreadId
0x180006c5c  mov     [rsp+1500h+var_14C0], eax
0x180006c60  mov     [rsp+1500h+var_14A8], rsi
0x180006c65  mov     [rsp+1500h+var_14A0], edi
0x180006c69  mov     [rsp+1500h+var_149C], r15d
0x180006c6e  mov     [rsp+1500h+var_14B8], r12
0x180006c73  mov     [rsp+1500h+var_14B0], r12
0x180006c78  mov     [rbp+1400h+var_1458], r14
0x180006c7c  mov     [rbp+1400h+var_1450], rbx
0x180006c80  mov     [rsp+1500h+var_1498], r12
0x180006c85  xorps   xmm0, xmm0
0x180006c88  xor     eax, eax
0x180006c8a  movups  [rbp+1400h+var_1478], xmm0
0x180006c8e  mov     [rbp+1400h+var_1468], rax
0x180006c92  xorps   xmm1, xmm1
0x180006c95  movups  [rsp+1500h+var_1490], xmm1
0x180006c9a  mov     [rbp+1400h+var_1480], rax
0x180006c9e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006ca5  test    rax, rax
0x180006ca8  jz      short loc_180006CB5
0x180006caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006caf  mov     [rbp+1400h+var_1460], rax
0x180006cb3  jmp     short loc_180006CB9
0x180006cb5  mov     [rbp+1400h+var_1460], r12
0x180006cb9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006cc0  test    rax, rax
0x180006cc3  jz      short loc_180006CCF
0x180006cc5  lea     rcx, [rsp+1500h+var_14E0]
0x180006cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ccf  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006cd6  test    rax, rax
0x180006cd9  jz      short loc_180006CEF
0x180006cdb  mov     r8d, 400h
0x180006ce1  lea     rdx, [rbp+1400h+var_1440]
0x180006ce5  lea     rcx, [rsp+1500h+var_14E0]
0x180006cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cef  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006cf6  test    rax, rax
0x180006cf9  jz      short loc_180006D05
0x180006cfb  lea     rcx, [rsp+1500h+var_14E0]
0x180006d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d05  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006d0c  test    rax, rax
0x180006d0f  jz      short loc_180006D22
0x180006d11  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180006d16  jnz     short loc_180006D22
0x180006d18  lea     rcx, [rsp+1500h+var_14E0]
0x180006d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d22  cmp     [rsp+1500h+var_14D8], r12d
0x180006d27  jge     loc_180006E30
0x180006d2d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180006d34  jnz     short loc_180006D55
0x180006d36  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006d3d  test    rax, rax
0x180006d40  jz      short loc_180006D4B
0x180006d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d47  test    al, al
0x180006d49  jmp     short loc_180006D53
0x180006d4b  call    cs:__imp_IsDebuggerPresent
0x180006d51  test    eax, eax
0x180006d53  jz      short loc_180006D5C
0x180006d55  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180006d5a  jz      short loc_180006D82
0x180006d5c  mov     rax, cs:g_pfnResultLoggingCallback
0x180006d63  test    rax, rax
0x180006d66  jz      short loc_180006DDB
0x180006d68  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180006d6f  jnz     short loc_180006DDB
0x180006d71  xor     r8d, r8d
0x180006d74  xor     edx, edx
0x180006d76  lea     rcx, [rsp+1500h+var_14E0]
0x180006d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d80  jmp     short loc_180006DDB
0x180006d82  mov     ebx, 800h
0x180006d87  mov     rax, cs:g_pfnResultLoggingCallback
0x180006d8e  test    rax, rax
0x180006d91  jz      short loc_180006DB0
0x180006d93  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180006d9a  jnz     short loc_180006DB0
0x180006d9c  mov     r8d, ebx
0x180006d9f  lea     rdx, [rbp+1400h+OutputString]
0x180006da6  lea     rcx, [rsp+1500h+var_14E0]
0x180006dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006db0  cmp     [rbp+1400h+OutputString], r12w
0x180006db8  jnz     short loc_180006DCE
0x180006dba  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180006dbf  mov     rdx, rbx; unsigned __int16 *
0x180006dc2  lea     rcx, [rbp+1400h+OutputString]; this
0x180006dc9  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006dce  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180006dd5  call    cs:__imp_OutputDebugStringW
0x180006ddb  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180006de0  jnz     short loc_180006DEB
0x180006de2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180006de9  jz      short loc_180006DFD
0x180006deb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006df2  test    rax, rax
0x180006df5  jz      short loc_180006DFD
0x180006df7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dfc  nop
0x180006dfd  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180006e02  jnz     short loc_180006E25
0x180006e04  mov     rcx, [rbp+1400h+var_40]
0x180006e0b  xor     rcx, rsp; StackCookie
0x180006e0e  call    __security_check_cookie
0x180006e13  add     rsp, 14D0h
0x180006e1a  pop     r15
0x180006e1c  pop     r14
0x180006e1e  pop     r12
0x180006e20  pop     rdi
0x180006e21  pop     rsi
0x180006e22  pop     rbx
0x180006e23  pop     rbp
0x180006e24  retn
0x180006e25  lea     rcx, [rsp+1500h+var_14E0]; this
0x180006e2a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180006e30  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
