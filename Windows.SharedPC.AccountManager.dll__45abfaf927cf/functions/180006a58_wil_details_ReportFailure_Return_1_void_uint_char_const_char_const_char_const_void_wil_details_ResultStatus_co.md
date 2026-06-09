# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180006a58`
- end: `0x180006cfe`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800066dc`

## callees

- `0x180003530`
- `0x180003fc0`
- `0x180004b74`
- `0x180006a58`
- `0x1800088a4`
- `0x18000942c`
- `0x180009508`
- `0x180023de0`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006b1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006b1e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006c13`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006c13`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006c9d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006c9d`

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
0x180006a58  push    rbp
0x180006a5a  push    rbx
0x180006a5b  push    rsi
0x180006a5c  push    rdi
0x180006a5d  push    r12
0x180006a5f  push    r14
0x180006a61  push    r15
0x180006a63  lea     rbp, [rsp-13D0h]
0x180006a6b  mov     eax, 14D0h
0x180006a70  call    _alloca_probe
0x180006a75  sub     rsp, rax
0x180006a78  mov     rax, cs:__security_cookie
0x180006a7f  xor     rax, rsp
0x180006a82  mov     [rbp+1400h+var_40], rax
0x180006a89  mov     rsi, r8
0x180006a8c  mov     edi, edx
0x180006a8e  mov     rbx, rcx
0x180006a91  mov     r14, [rbp+1400h+arg_28]
0x180006a98  xor     edx, edx; Val
0x180006a9a  mov     r8d, 98h; Size
0x180006aa0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180006aa5  call    memset_0
0x180006aaa  nop
0x180006aab  xor     r12d, r12d
0x180006aae  mov     [rbp+1400h+OutputString], r12w
0x180006ab6  mov     [rbp+1400h+var_1440], r12b
0x180006aba  mov     rdx, [rbp+1400h+arg_30]; int
0x180006ac1  mov     ecx, [rdx]; this
0x180006ac3  mov     [rsp+1500h+var_14D8], ecx
0x180006ac7  mov     eax, [rdx+4]
0x180006aca  mov     [rsp+1500h+var_14D4], eax
0x180006ace  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006ad3  mov     r15d, eax
0x180006ad6  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180006ade  mov     ecx, r12d
0x180006ae1  lea     eax, [r12+8]
0x180006ae6  cmp     dword ptr [rdx+8], 1
0x180006aea  cmovz   ecx, eax
0x180006aed  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180006af1  lea     ecx, [rax-7]
0x180006af4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006afc  inc     ecx
0x180006afe  mov     [rsp+1500h+var_14D0], ecx
0x180006b02  mov     rcx, [rbp+1400h+arg_38]
0x180006b09  test    rcx, rcx
0x180006b0c  jz      short loc_180006B19
0x180006b0e  cmp     [rcx], r12w
0x180006b12  mov     [rsp+1500h+var_14C8], rcx
0x180006b17  jnz     short loc_180006B1E
0x180006b19  mov     [rsp+1500h+var_14C8], r12
0x180006b1e  call    cs:__imp_GetCurrentThreadId
0x180006b24  mov     [rsp+1500h+var_14C0], eax
0x180006b28  mov     [rsp+1500h+var_14A8], rsi
0x180006b2d  mov     [rsp+1500h+var_14A0], edi
0x180006b31  mov     [rsp+1500h+var_149C], r15d
0x180006b36  mov     [rsp+1500h+var_14B8], r12
0x180006b3b  mov     [rsp+1500h+var_14B0], r12
0x180006b40  mov     [rbp+1400h+var_1458], r14
0x180006b44  mov     [rbp+1400h+var_1450], rbx
0x180006b48  mov     [rsp+1500h+var_1498], r12
0x180006b4d  xorps   xmm0, xmm0
0x180006b50  xor     eax, eax
0x180006b52  movups  [rbp+1400h+var_1478], xmm0
0x180006b56  mov     [rbp+1400h+var_1468], rax
0x180006b5a  xorps   xmm1, xmm1
0x180006b5d  movups  [rsp+1500h+var_1490], xmm1
0x180006b62  mov     [rbp+1400h+var_1480], rax
0x180006b66  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006b6d  test    rax, rax
0x180006b70  jz      short loc_180006B7D
0x180006b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b77  mov     [rbp+1400h+var_1460], rax
0x180006b7b  jmp     short loc_180006B81
0x180006b7d  mov     [rbp+1400h+var_1460], r12
0x180006b81  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006b88  test    rax, rax
0x180006b8b  jz      short loc_180006B97
0x180006b8d  lea     rcx, [rsp+1500h+var_14E0]
0x180006b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b97  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006b9e  test    rax, rax
0x180006ba1  jz      short loc_180006BB7
0x180006ba3  mov     r8d, 400h
0x180006ba9  lea     rdx, [rbp+1400h+var_1440]
0x180006bad  lea     rcx, [rsp+1500h+var_14E0]
0x180006bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bb7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006bbe  test    rax, rax
0x180006bc1  jz      short loc_180006BCD
0x180006bc3  lea     rcx, [rsp+1500h+var_14E0]
0x180006bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bcd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006bd4  test    rax, rax
0x180006bd7  jz      short loc_180006BEA
0x180006bd9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180006bde  jnz     short loc_180006BEA
0x180006be0  lea     rcx, [rsp+1500h+var_14E0]
0x180006be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bea  cmp     [rsp+1500h+var_14D8], r12d
0x180006bef  jge     loc_180006CF8
0x180006bf5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180006bfc  jnz     short loc_180006C1D
0x180006bfe  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006c05  test    rax, rax
0x180006c08  jz      short loc_180006C13
0x180006c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c0f  test    al, al
0x180006c11  jmp     short loc_180006C1B
0x180006c13  call    cs:__imp_IsDebuggerPresent
0x180006c19  test    eax, eax
0x180006c1b  jz      short loc_180006C24
0x180006c1d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180006c22  jz      short loc_180006C4A
0x180006c24  mov     rax, cs:g_pfnResultLoggingCallback
0x180006c2b  test    rax, rax
0x180006c2e  jz      short loc_180006CA3
0x180006c30  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180006c37  jnz     short loc_180006CA3
0x180006c39  xor     r8d, r8d
0x180006c3c  xor     edx, edx
0x180006c3e  lea     rcx, [rsp+1500h+var_14E0]
0x180006c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c48  jmp     short loc_180006CA3
0x180006c4a  mov     ebx, 800h
0x180006c4f  mov     rax, cs:g_pfnResultLoggingCallback
0x180006c56  test    rax, rax
0x180006c59  jz      short loc_180006C78
0x180006c5b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180006c62  jnz     short loc_180006C78
0x180006c64  mov     r8d, ebx
0x180006c67  lea     rdx, [rbp+1400h+OutputString]
0x180006c6e  lea     rcx, [rsp+1500h+var_14E0]
0x180006c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c78  cmp     [rbp+1400h+OutputString], r12w
0x180006c80  jnz     short loc_180006C96
0x180006c82  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180006c87  mov     rdx, rbx; unsigned __int16 *
0x180006c8a  lea     rcx, [rbp+1400h+OutputString]; this
0x180006c91  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006c96  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180006c9d  call    cs:__imp_OutputDebugStringW
0x180006ca3  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180006ca8  jnz     short loc_180006CB3
0x180006caa  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180006cb1  jz      short loc_180006CC5
0x180006cb3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006cba  test    rax, rax
0x180006cbd  jz      short loc_180006CC5
0x180006cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cc4  nop
0x180006cc5  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180006cca  jnz     short loc_180006CED
0x180006ccc  mov     rcx, [rbp+1400h+var_40]
0x180006cd3  xor     rcx, rsp; StackCookie
0x180006cd6  call    __security_check_cookie
0x180006cdb  add     rsp, 14D0h
0x180006ce2  pop     r15
0x180006ce4  pop     r14
0x180006ce6  pop     r12
0x180006ce8  pop     rdi
0x180006ce9  pop     rsi
0x180006cea  pop     rbx
0x180006ceb  pop     rbp
0x180006cec  retn
0x180006ced  lea     rcx, [rsp+1500h+var_14E0]; this
0x180006cf2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180006cf8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
