# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180005aa8`
- end: `0x180005d4e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180005404`

## callees

- `0x1800033d0`
- `0x180003fb8`
- `0x180005aa8`
- `0x180007fa4`
- `0x1800098b8`
- `0x18000bfe0`
- `0x18000c258`
- `0x180101970`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005b6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005b6e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005c63`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005c63`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005ced`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005ced`

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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)&v18, v16);
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
0x180005aa8  push    rbp
0x180005aaa  push    rbx
0x180005aab  push    rsi
0x180005aac  push    rdi
0x180005aad  push    r12
0x180005aaf  push    r14
0x180005ab1  push    r15
0x180005ab3  lea     rbp, [rsp-13D0h]
0x180005abb  mov     eax, 14D0h
0x180005ac0  call    _alloca_probe
0x180005ac5  sub     rsp, rax
0x180005ac8  mov     rax, cs:__security_cookie
0x180005acf  xor     rax, rsp
0x180005ad2  mov     [rbp+1400h+var_40], rax
0x180005ad9  mov     rsi, r8
0x180005adc  mov     edi, edx
0x180005ade  mov     rbx, rcx
0x180005ae1  mov     r14, [rbp+1400h+arg_28]
0x180005ae8  xor     edx, edx; Val
0x180005aea  mov     r8d, 98h; Size
0x180005af0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180005af5  call    memset_0
0x180005afa  nop
0x180005afb  xor     r12d, r12d
0x180005afe  mov     [rbp+1400h+OutputString], r12w
0x180005b06  mov     [rbp+1400h+var_1440], r12b
0x180005b0a  mov     rdx, [rbp+1400h+arg_30]; int
0x180005b11  mov     ecx, [rdx]; this
0x180005b13  mov     [rsp+1500h+var_14D8], ecx
0x180005b17  mov     eax, [rdx+4]
0x180005b1a  mov     [rsp+1500h+var_14D4], eax
0x180005b1e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005b23  mov     r15d, eax
0x180005b26  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180005b2e  mov     ecx, r12d
0x180005b31  lea     eax, [r12+8]
0x180005b36  cmp     dword ptr [rdx+8], 1
0x180005b3a  cmovz   ecx, eax
0x180005b3d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180005b41  lea     ecx, [rax-7]
0x180005b44  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005b4c  inc     ecx
0x180005b4e  mov     [rsp+1500h+var_14D0], ecx
0x180005b52  mov     rcx, [rbp+1400h+arg_38]
0x180005b59  test    rcx, rcx
0x180005b5c  jz      short loc_180005B69
0x180005b5e  cmp     [rcx], r12w
0x180005b62  mov     [rsp+1500h+var_14C8], rcx
0x180005b67  jnz     short loc_180005B6E
0x180005b69  mov     [rsp+1500h+var_14C8], r12
0x180005b6e  call    cs:__imp_GetCurrentThreadId
0x180005b74  mov     [rsp+1500h+var_14C0], eax
0x180005b78  mov     [rsp+1500h+var_14A8], rsi
0x180005b7d  mov     [rsp+1500h+var_14A0], edi
0x180005b81  mov     [rsp+1500h+var_149C], r15d
0x180005b86  mov     [rsp+1500h+var_14B8], r12
0x180005b8b  mov     [rsp+1500h+var_14B0], r12
0x180005b90  mov     [rbp+1400h+var_1458], r14
0x180005b94  mov     [rbp+1400h+var_1450], rbx
0x180005b98  mov     [rsp+1500h+var_1498], r12
0x180005b9d  xorps   xmm0, xmm0
0x180005ba0  xor     eax, eax
0x180005ba2  movups  [rbp+1400h+var_1478], xmm0
0x180005ba6  mov     [rbp+1400h+var_1468], rax
0x180005baa  xorps   xmm1, xmm1
0x180005bad  movups  [rsp+1500h+var_1490], xmm1
0x180005bb2  mov     [rbp+1400h+var_1480], rax
0x180005bb6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005bbd  test    rax, rax
0x180005bc0  jz      short loc_180005BCD
0x180005bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bc7  mov     [rbp+1400h+var_1460], rax
0x180005bcb  jmp     short loc_180005BD1
0x180005bcd  mov     [rbp+1400h+var_1460], r12
0x180005bd1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005bd8  test    rax, rax
0x180005bdb  jz      short loc_180005BE7
0x180005bdd  lea     rcx, [rsp+1500h+var_14E0]
0x180005be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005be7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005bee  test    rax, rax
0x180005bf1  jz      short loc_180005C07
0x180005bf3  mov     r8d, 400h
0x180005bf9  lea     rdx, [rbp+1400h+var_1440]
0x180005bfd  lea     rcx, [rsp+1500h+var_14E0]
0x180005c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c07  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005c0e  test    rax, rax
0x180005c11  jz      short loc_180005C1D
0x180005c13  lea     rcx, [rsp+1500h+var_14E0]
0x180005c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c1d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005c24  test    rax, rax
0x180005c27  jz      short loc_180005C3A
0x180005c29  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005c2e  jnz     short loc_180005C3A
0x180005c30  lea     rcx, [rsp+1500h+var_14E0]
0x180005c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c3a  cmp     [rsp+1500h+var_14D8], r12d
0x180005c3f  jge     loc_180005D48
0x180005c45  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180005c4c  jnz     short loc_180005C6D
0x180005c4e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005c55  test    rax, rax
0x180005c58  jz      short loc_180005C63
0x180005c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c5f  test    al, al
0x180005c61  jmp     short loc_180005C6B
0x180005c63  call    cs:__imp_IsDebuggerPresent
0x180005c69  test    eax, eax
0x180005c6b  jz      short loc_180005C74
0x180005c6d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005c72  jz      short loc_180005C9A
0x180005c74  mov     rax, cs:g_pfnResultLoggingCallback
0x180005c7b  test    rax, rax
0x180005c7e  jz      short loc_180005CF3
0x180005c80  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005c87  jnz     short loc_180005CF3
0x180005c89  xor     r8d, r8d
0x180005c8c  xor     edx, edx
0x180005c8e  lea     rcx, [rsp+1500h+var_14E0]
0x180005c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c98  jmp     short loc_180005CF3
0x180005c9a  mov     ebx, 800h
0x180005c9f  mov     rax, cs:g_pfnResultLoggingCallback
0x180005ca6  test    rax, rax
0x180005ca9  jz      short loc_180005CC8
0x180005cab  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005cb2  jnz     short loc_180005CC8
0x180005cb4  mov     r8d, ebx
0x180005cb7  lea     rdx, [rbp+1400h+OutputString]
0x180005cbe  lea     rcx, [rsp+1500h+var_14E0]
0x180005cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cc8  cmp     [rbp+1400h+OutputString], r12w
0x180005cd0  jnz     short loc_180005CE6
0x180005cd2  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180005cd7  mov     rdx, rbx; wchar_t *
0x180005cda  lea     rcx, [rbp+1400h+OutputString]; this
0x180005ce1  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180005ce6  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180005ced  call    cs:__imp_OutputDebugStringW
0x180005cf3  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180005cf8  jnz     short loc_180005D03
0x180005cfa  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180005d01  jz      short loc_180005D15
0x180005d03  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005d0a  test    rax, rax
0x180005d0d  jz      short loc_180005D15
0x180005d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d14  nop
0x180005d15  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180005d1a  jnz     short loc_180005D3D
0x180005d1c  mov     rcx, [rbp+1400h+var_40]
0x180005d23  xor     rcx, rsp; StackCookie
0x180005d26  call    __security_check_cookie
0x180005d2b  add     rsp, 14D0h
0x180005d32  pop     r15
0x180005d34  pop     r14
0x180005d36  pop     r12
0x180005d38  pop     rdi
0x180005d39  pop     rsi
0x180005d3a  pop     rbx
0x180005d3b  pop     rbp
0x180005d3c  retn
0x180005d3d  lea     rcx, [rsp+1500h+var_14E0]; this
0x180005d42  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005d48  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
