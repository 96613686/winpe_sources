# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000383c`
- end: `0x180003ac9`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000331c`

## callees

- `0x180002550`
- `0x180002fc4`
- `0x18000383c`
- `0x180004c44`
- `0x180005d60`
- `0x180006fc0`
- `0x180007148`
- `0x180011040`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800038ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800038ea`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003a68`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003a68`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800039de`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800039de`

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
0x18000383c  push    rbp
0x18000383e  push    rbx
0x18000383f  push    rsi
0x180003840  push    rdi
0x180003841  push    r12
0x180003843  push    r14
0x180003845  push    r15
0x180003847  lea     rbp, [rsp-13D0h]
0x18000384f  mov     eax, 14D0h
0x180003854  call    _alloca_probe
0x180003859  sub     rsp, rax
0x18000385c  mov     rax, cs:__security_cookie
0x180003863  xor     rax, rsp
0x180003866  mov     [rbp+1400h+var_40], rax
0x18000386d  mov     r14, r8
0x180003870  mov     esi, edx
0x180003872  mov     r15, rcx
0x180003875  mov     rdi, [rbp+1400h+arg_28]
0x18000387c  xor     edx, edx; Val
0x18000387e  mov     r8d, 98h; Size
0x180003884  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003889  call    memset_0
0x18000388e  nop
0x18000388f  xor     r12d, r12d
0x180003892  mov     [rbp+1400h+OutputString], r12w
0x18000389a  mov     [rbp+1400h+var_1440], r12b
0x18000389e  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1800038a5  mov     ecx, [rdx]; this
0x1800038a7  mov     [rsp+1500h+var_14D8], ecx
0x1800038ab  mov     eax, [rdx+4]
0x1800038ae  mov     [rsp+1500h+var_14D4], eax
0x1800038b2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800038b7  mov     ebx, eax
0x1800038b9  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800038c1  mov     ecx, r12d
0x1800038c4  lea     eax, [r12+8]
0x1800038c9  cmp     dword ptr [rdx+8], 1
0x1800038cd  cmovz   ecx, eax
0x1800038d0  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800038d4  lea     ecx, [rax-7]
0x1800038d7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800038df  inc     ecx
0x1800038e1  mov     [rsp+1500h+var_14D0], ecx
0x1800038e5  mov     [rsp+1500h+var_14C8], r12
0x1800038ea  call    cs:__imp_GetCurrentThreadId
0x1800038f0  mov     [rsp+1500h+var_14C0], eax
0x1800038f4  mov     [rsp+1500h+var_14A8], r14
0x1800038f9  mov     [rsp+1500h+var_14A0], esi
0x1800038fd  mov     [rsp+1500h+var_149C], ebx
0x180003901  mov     [rsp+1500h+var_14B8], r12
0x180003906  mov     [rsp+1500h+var_14B0], r12
0x18000390b  mov     [rbp+1400h+var_1458], rdi
0x18000390f  mov     [rbp+1400h+var_1450], r15
0x180003913  mov     [rsp+1500h+var_1498], r12
0x180003918  xorps   xmm0, xmm0
0x18000391b  xor     eax, eax
0x18000391d  movups  [rbp+1400h+var_1478], xmm0
0x180003921  mov     [rbp+1400h+var_1468], rax
0x180003925  xorps   xmm1, xmm1
0x180003928  movups  [rsp+1500h+var_1490], xmm1
0x18000392d  mov     [rbp+1400h+var_1480], rax
0x180003931  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003938  test    rax, rax
0x18000393b  jz      short loc_180003948
0x18000393d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003942  mov     [rbp+1400h+var_1460], rax
0x180003946  jmp     short loc_18000394C
0x180003948  mov     [rbp+1400h+var_1460], r12
0x18000394c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003953  test    rax, rax
0x180003956  jz      short loc_180003962
0x180003958  lea     rcx, [rsp+1500h+var_14E0]
0x18000395d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003962  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003969  test    rax, rax
0x18000396c  jz      short loc_180003982
0x18000396e  mov     r8d, 400h
0x180003974  lea     rdx, [rbp+1400h+var_1440]
0x180003978  lea     rcx, [rsp+1500h+var_14E0]
0x18000397d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003982  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003989  test    rax, rax
0x18000398c  jz      short loc_180003998
0x18000398e  lea     rcx, [rsp+1500h+var_14E0]
0x180003993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003998  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000399f  test    rax, rax
0x1800039a2  jz      short loc_1800039B5
0x1800039a4  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800039a9  jnz     short loc_1800039B5
0x1800039ab  lea     rcx, [rsp+1500h+var_14E0]
0x1800039b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039b5  cmp     [rsp+1500h+var_14D8], r12d
0x1800039ba  jge     loc_180003AC3
0x1800039c0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800039c7  jnz     short loc_1800039E8
0x1800039c9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800039d0  test    rax, rax
0x1800039d3  jz      short loc_1800039DE
0x1800039d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039da  test    al, al
0x1800039dc  jmp     short loc_1800039E6
0x1800039de  call    cs:__imp_IsDebuggerPresent
0x1800039e4  test    eax, eax
0x1800039e6  jz      short loc_1800039EF
0x1800039e8  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800039ed  jz      short loc_180003A15
0x1800039ef  mov     rax, cs:g_pfnResultLoggingCallback
0x1800039f6  test    rax, rax
0x1800039f9  jz      short loc_180003A6E
0x1800039fb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003a02  jnz     short loc_180003A6E
0x180003a04  xor     r8d, r8d
0x180003a07  xor     edx, edx
0x180003a09  lea     rcx, [rsp+1500h+var_14E0]
0x180003a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a13  jmp     short loc_180003A6E
0x180003a15  mov     ebx, 800h
0x180003a1a  mov     rax, cs:g_pfnResultLoggingCallback
0x180003a21  test    rax, rax
0x180003a24  jz      short loc_180003A43
0x180003a26  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003a2d  jnz     short loc_180003A43
0x180003a2f  mov     r8d, ebx
0x180003a32  lea     rdx, [rbp+1400h+OutputString]
0x180003a39  lea     rcx, [rsp+1500h+var_14E0]
0x180003a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a43  cmp     [rbp+1400h+OutputString], r12w
0x180003a4b  jnz     short loc_180003A61
0x180003a4d  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003a52  mov     rdx, rbx; unsigned __int16 *
0x180003a55  lea     rcx, [rbp+1400h+OutputString]; this
0x180003a5c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003a61  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003a68  call    cs:__imp_OutputDebugStringW
0x180003a6e  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003a73  jnz     short loc_180003A7E
0x180003a75  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003a7c  jz      short loc_180003A90
0x180003a7e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003a85  test    rax, rax
0x180003a88  jz      short loc_180003A90
0x180003a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a8f  nop
0x180003a90  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003a95  jnz     short loc_180003AB8
0x180003a97  mov     rcx, [rbp+1400h+var_40]
0x180003a9e  xor     rcx, rsp; StackCookie
0x180003aa1  call    __security_check_cookie
0x180003aa6  add     rsp, 14D0h
0x180003aad  pop     r15
0x180003aaf  pop     r14
0x180003ab1  pop     r12
0x180003ab3  pop     rdi
0x180003ab4  pop     rsi
0x180003ab5  pop     rbx
0x180003ab6  pop     rbp
0x180003ab7  retn
0x180003ab8  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003abd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003ac3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
