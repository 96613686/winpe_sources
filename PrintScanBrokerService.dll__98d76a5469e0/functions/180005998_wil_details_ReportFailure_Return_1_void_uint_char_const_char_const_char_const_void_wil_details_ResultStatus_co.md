# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180005998`
- end: `0x180005c3e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800052d4`

## callees

- `0x180002d40`
- `0x180003a0c`
- `0x180005998`
- `0x18000a324`
- `0x18000cd10`
- `0x18000f5a8`
- `0x18000f7dc`
- `0x1800442a0`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a5e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005bdd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005bdd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005b53`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005b53`

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
0x180005998  push    rbp
0x18000599a  push    rbx
0x18000599b  push    rsi
0x18000599c  push    rdi
0x18000599d  push    r12
0x18000599f  push    r14
0x1800059a1  push    r15
0x1800059a3  lea     rbp, [rsp-13D0h]
0x1800059ab  mov     eax, 14D0h
0x1800059b0  call    _alloca_probe
0x1800059b5  sub     rsp, rax
0x1800059b8  mov     rax, cs:__security_cookie
0x1800059bf  xor     rax, rsp
0x1800059c2  mov     [rbp+1400h+var_40], rax
0x1800059c9  mov     rsi, r8
0x1800059cc  mov     edi, edx
0x1800059ce  mov     rbx, rcx
0x1800059d1  mov     r14, [rbp+1400h+arg_28]
0x1800059d8  xor     edx, edx; Val
0x1800059da  mov     r8d, 98h; Size
0x1800059e0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800059e5  call    memset_0
0x1800059ea  nop
0x1800059eb  xor     r12d, r12d
0x1800059ee  mov     [rbp+1400h+OutputString], r12w
0x1800059f6  mov     [rbp+1400h+var_1440], r12b
0x1800059fa  mov     rdx, [rbp+1400h+arg_30]; int
0x180005a01  mov     ecx, [rdx]; this
0x180005a03  mov     [rsp+1500h+var_14D8], ecx
0x180005a07  mov     eax, [rdx+4]
0x180005a0a  mov     [rsp+1500h+var_14D4], eax
0x180005a0e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005a13  mov     r15d, eax
0x180005a16  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180005a1e  mov     ecx, r12d
0x180005a21  lea     eax, [r12+8]
0x180005a26  cmp     dword ptr [rdx+8], 1
0x180005a2a  cmovz   ecx, eax
0x180005a2d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180005a31  lea     ecx, [rax-7]
0x180005a34  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005a3c  inc     ecx
0x180005a3e  mov     [rsp+1500h+var_14D0], ecx
0x180005a42  mov     rcx, [rbp+1400h+arg_38]
0x180005a49  test    rcx, rcx
0x180005a4c  jz      short loc_180005A59
0x180005a4e  cmp     [rcx], r12w
0x180005a52  mov     [rsp+1500h+var_14C8], rcx
0x180005a57  jnz     short loc_180005A5E
0x180005a59  mov     [rsp+1500h+var_14C8], r12
0x180005a5e  call    cs:__imp_GetCurrentThreadId
0x180005a64  mov     [rsp+1500h+var_14C0], eax
0x180005a68  mov     [rsp+1500h+var_14A8], rsi
0x180005a6d  mov     [rsp+1500h+var_14A0], edi
0x180005a71  mov     [rsp+1500h+var_149C], r15d
0x180005a76  mov     [rsp+1500h+var_14B8], r12
0x180005a7b  mov     [rsp+1500h+var_14B0], r12
0x180005a80  mov     [rbp+1400h+var_1458], r14
0x180005a84  mov     [rbp+1400h+var_1450], rbx
0x180005a88  mov     [rsp+1500h+var_1498], r12
0x180005a8d  xorps   xmm0, xmm0
0x180005a90  xor     eax, eax
0x180005a92  movups  [rbp+1400h+var_1478], xmm0
0x180005a96  mov     [rbp+1400h+var_1468], rax
0x180005a9a  xorps   xmm1, xmm1
0x180005a9d  movups  [rsp+1500h+var_1490], xmm1
0x180005aa2  mov     [rbp+1400h+var_1480], rax
0x180005aa6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005aad  test    rax, rax
0x180005ab0  jz      short loc_180005ABD
0x180005ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ab7  mov     [rbp+1400h+var_1460], rax
0x180005abb  jmp     short loc_180005AC1
0x180005abd  mov     [rbp+1400h+var_1460], r12
0x180005ac1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005ac8  test    rax, rax
0x180005acb  jz      short loc_180005AD7
0x180005acd  lea     rcx, [rsp+1500h+var_14E0]
0x180005ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ad7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005ade  test    rax, rax
0x180005ae1  jz      short loc_180005AF7
0x180005ae3  mov     r8d, 400h
0x180005ae9  lea     rdx, [rbp+1400h+var_1440]
0x180005aed  lea     rcx, [rsp+1500h+var_14E0]
0x180005af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005af7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005afe  test    rax, rax
0x180005b01  jz      short loc_180005B0D
0x180005b03  lea     rcx, [rsp+1500h+var_14E0]
0x180005b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b0d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005b14  test    rax, rax
0x180005b17  jz      short loc_180005B2A
0x180005b19  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005b1e  jnz     short loc_180005B2A
0x180005b20  lea     rcx, [rsp+1500h+var_14E0]
0x180005b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b2a  cmp     [rsp+1500h+var_14D8], r12d
0x180005b2f  jge     loc_180005C38
0x180005b35  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180005b3c  jnz     short loc_180005B5D
0x180005b3e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005b45  test    rax, rax
0x180005b48  jz      short loc_180005B53
0x180005b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b4f  test    al, al
0x180005b51  jmp     short loc_180005B5B
0x180005b53  call    cs:__imp_IsDebuggerPresent
0x180005b59  test    eax, eax
0x180005b5b  jz      short loc_180005B64
0x180005b5d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005b62  jz      short loc_180005B8A
0x180005b64  mov     rax, cs:g_pfnResultLoggingCallback
0x180005b6b  test    rax, rax
0x180005b6e  jz      short loc_180005BE3
0x180005b70  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005b77  jnz     short loc_180005BE3
0x180005b79  xor     r8d, r8d
0x180005b7c  xor     edx, edx
0x180005b7e  lea     rcx, [rsp+1500h+var_14E0]
0x180005b83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b88  jmp     short loc_180005BE3
0x180005b8a  mov     ebx, 800h
0x180005b8f  mov     rax, cs:g_pfnResultLoggingCallback
0x180005b96  test    rax, rax
0x180005b99  jz      short loc_180005BB8
0x180005b9b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005ba2  jnz     short loc_180005BB8
0x180005ba4  mov     r8d, ebx
0x180005ba7  lea     rdx, [rbp+1400h+OutputString]
0x180005bae  lea     rcx, [rsp+1500h+var_14E0]
0x180005bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bb8  cmp     [rbp+1400h+OutputString], r12w
0x180005bc0  jnz     short loc_180005BD6
0x180005bc2  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180005bc7  mov     rdx, rbx; unsigned __int16 *
0x180005bca  lea     rcx, [rbp+1400h+OutputString]; this
0x180005bd1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005bd6  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180005bdd  call    cs:__imp_OutputDebugStringW
0x180005be3  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180005be8  jnz     short loc_180005BF3
0x180005bea  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180005bf1  jz      short loc_180005C05
0x180005bf3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005bfa  test    rax, rax
0x180005bfd  jz      short loc_180005C05
0x180005bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c04  nop
0x180005c05  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180005c0a  jnz     short loc_180005C2D
0x180005c0c  mov     rcx, [rbp+1400h+var_40]
0x180005c13  xor     rcx, rsp; StackCookie
0x180005c16  call    __security_check_cookie
0x180005c1b  add     rsp, 14D0h
0x180005c22  pop     r15
0x180005c24  pop     r14
0x180005c26  pop     r12
0x180005c28  pop     rdi
0x180005c29  pop     rsi
0x180005c2a  pop     rbx
0x180005c2b  pop     rbp
0x180005c2c  retn
0x180005c2d  lea     rcx, [rsp+1500h+var_14E0]; this
0x180005c32  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005c38  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
