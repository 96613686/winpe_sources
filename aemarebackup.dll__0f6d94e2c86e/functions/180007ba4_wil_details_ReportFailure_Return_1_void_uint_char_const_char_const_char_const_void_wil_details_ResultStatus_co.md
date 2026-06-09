# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180007ba4`
- end: `0x180007e31`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000767c`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x180007ba4`
- `0x180009f84`
- `0x18000bbc8`
- `0x18000e370`
- `0x18000e53c`
- `0x1800e67d0`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007c52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007c52`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007d46`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007d46`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007dd0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007dd0`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180007ba4  push    rbp
0x180007ba6  push    rbx
0x180007ba7  push    rsi
0x180007ba8  push    rdi
0x180007ba9  push    r12
0x180007bab  push    r14
0x180007bad  push    r15
0x180007baf  lea     rbp, [rsp-13D0h]
0x180007bb7  mov     eax, 14D0h
0x180007bbc  call    _alloca_probe
0x180007bc1  sub     rsp, rax
0x180007bc4  mov     rax, cs:__security_cookie
0x180007bcb  xor     rax, rsp
0x180007bce  mov     [rbp+1400h+var_40], rax
0x180007bd5  mov     r14, r8
0x180007bd8  mov     esi, edx
0x180007bda  mov     r15, rcx
0x180007bdd  mov     rdi, [rbp+1400h+arg_28]
0x180007be4  xor     edx, edx; Val
0x180007be6  mov     r8d, 98h; Size
0x180007bec  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180007bf1  call    memset_0
0x180007bf6  nop
0x180007bf7  xor     r12d, r12d
0x180007bfa  mov     [rbp+1400h+OutputString], r12w
0x180007c02  mov     [rbp+1400h+var_1440], r12b
0x180007c06  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180007c0d  mov     ecx, [rdx]; this
0x180007c0f  mov     [rsp+1500h+var_14D8], ecx
0x180007c13  mov     eax, [rdx+4]
0x180007c16  mov     [rsp+1500h+var_14D4], eax
0x180007c1a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007c1f  mov     ebx, eax
0x180007c21  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180007c29  mov     ecx, r12d
0x180007c2c  lea     eax, [r12+8]
0x180007c31  cmp     dword ptr [rdx+8], 1
0x180007c35  cmovz   ecx, eax
0x180007c38  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180007c3c  lea     ecx, [rax-7]
0x180007c3f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007c47  inc     ecx
0x180007c49  mov     [rsp+1500h+var_14D0], ecx
0x180007c4d  mov     [rsp+1500h+var_14C8], r12
0x180007c52  call    cs:__imp_GetCurrentThreadId
0x180007c58  mov     [rsp+1500h+var_14C0], eax
0x180007c5c  mov     [rsp+1500h+var_14A8], r14
0x180007c61  mov     [rsp+1500h+var_14A0], esi
0x180007c65  mov     [rsp+1500h+var_149C], ebx
0x180007c69  mov     [rsp+1500h+var_14B8], r12
0x180007c6e  mov     [rsp+1500h+var_14B0], r12
0x180007c73  mov     [rbp+1400h+var_1458], rdi
0x180007c77  mov     [rbp+1400h+var_1450], r15
0x180007c7b  mov     [rsp+1500h+var_1498], r12
0x180007c80  xorps   xmm0, xmm0
0x180007c83  xor     eax, eax
0x180007c85  movups  [rbp+1400h+var_1478], xmm0
0x180007c89  mov     [rbp+1400h+var_1468], rax
0x180007c8d  xorps   xmm1, xmm1
0x180007c90  movups  [rsp+1500h+var_1490], xmm1
0x180007c95  mov     [rbp+1400h+var_1480], rax
0x180007c99  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007ca0  test    rax, rax
0x180007ca3  jz      short loc_180007CB0
0x180007ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007caa  mov     [rbp+1400h+var_1460], rax
0x180007cae  jmp     short loc_180007CB4
0x180007cb0  mov     [rbp+1400h+var_1460], r12
0x180007cb4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007cbb  test    rax, rax
0x180007cbe  jz      short loc_180007CCA
0x180007cc0  lea     rcx, [rsp+1500h+var_14E0]
0x180007cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cca  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007cd1  test    rax, rax
0x180007cd4  jz      short loc_180007CEA
0x180007cd6  mov     r8d, 400h
0x180007cdc  lea     rdx, [rbp+1400h+var_1440]
0x180007ce0  lea     rcx, [rsp+1500h+var_14E0]
0x180007ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cea  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007cf1  test    rax, rax
0x180007cf4  jz      short loc_180007D00
0x180007cf6  lea     rcx, [rsp+1500h+var_14E0]
0x180007cfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d00  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007d07  test    rax, rax
0x180007d0a  jz      short loc_180007D1D
0x180007d0c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180007d11  jnz     short loc_180007D1D
0x180007d13  lea     rcx, [rsp+1500h+var_14E0]
0x180007d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d1d  cmp     [rsp+1500h+var_14D8], r12d
0x180007d22  jge     loc_180007E2B
0x180007d28  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180007d2f  jnz     short loc_180007D50
0x180007d31  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007d38  test    rax, rax
0x180007d3b  jz      short loc_180007D46
0x180007d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d42  test    al, al
0x180007d44  jmp     short loc_180007D4E
0x180007d46  call    cs:__imp_IsDebuggerPresent
0x180007d4c  test    eax, eax
0x180007d4e  jz      short loc_180007D57
0x180007d50  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180007d55  jz      short loc_180007D7D
0x180007d57  mov     rax, cs:g_pfnResultLoggingCallback
0x180007d5e  test    rax, rax
0x180007d61  jz      short loc_180007DD6
0x180007d63  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180007d6a  jnz     short loc_180007DD6
0x180007d6c  xor     r8d, r8d
0x180007d6f  xor     edx, edx
0x180007d71  lea     rcx, [rsp+1500h+var_14E0]
0x180007d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d7b  jmp     short loc_180007DD6
0x180007d7d  mov     ebx, 800h
0x180007d82  mov     rax, cs:g_pfnResultLoggingCallback
0x180007d89  test    rax, rax
0x180007d8c  jz      short loc_180007DAB
0x180007d8e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180007d95  jnz     short loc_180007DAB
0x180007d97  mov     r8d, ebx
0x180007d9a  lea     rdx, [rbp+1400h+OutputString]
0x180007da1  lea     rcx, [rsp+1500h+var_14E0]
0x180007da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dab  cmp     [rbp+1400h+OutputString], r12w
0x180007db3  jnz     short loc_180007DC9
0x180007db5  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180007dba  mov     rdx, rbx; unsigned __int16 *
0x180007dbd  lea     rcx, [rbp+1400h+OutputString]; this
0x180007dc4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007dc9  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180007dd0  call    cs:__imp_OutputDebugStringW
0x180007dd6  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180007ddb  jnz     short loc_180007DE6
0x180007ddd  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180007de4  jz      short loc_180007DF8
0x180007de6  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007ded  test    rax, rax
0x180007df0  jz      short loc_180007DF8
0x180007df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007df7  nop
0x180007df8  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180007dfd  jnz     short loc_180007E20
0x180007dff  mov     rcx, [rbp+1400h+var_40]
0x180007e06  xor     rcx, rsp; StackCookie
0x180007e09  call    __security_check_cookie
0x180007e0e  add     rsp, 14D0h
0x180007e15  pop     r15
0x180007e17  pop     r14
0x180007e19  pop     r12
0x180007e1b  pop     rdi
0x180007e1c  pop     rsi
0x180007e1d  pop     rbx
0x180007e1e  pop     rbp
0x180007e1f  retn
0x180007e20  lea     rcx, [rsp+1500h+var_14E0]; this
0x180007e25  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180007e2b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
