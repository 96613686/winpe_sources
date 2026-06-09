# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004a30`
- end: `0x180004cbd`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800046fc`

## callees

- `0x180002980`
- `0x180003630`
- `0x180004a30`
- `0x180005f94`
- `0x180007210`
- `0x180008118`
- `0x1800082d4`
- `0x180026630`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ade`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ade`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004c5c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004c5c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004bd2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004bd2`

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
0x180004a30  push    rbp
0x180004a32  push    rbx
0x180004a33  push    rsi
0x180004a34  push    rdi
0x180004a35  push    r12
0x180004a37  push    r14
0x180004a39  push    r15
0x180004a3b  lea     rbp, [rsp-13D0h]
0x180004a43  mov     eax, 14D0h
0x180004a48  call    _alloca_probe
0x180004a4d  sub     rsp, rax
0x180004a50  mov     rax, cs:__security_cookie
0x180004a57  xor     rax, rsp
0x180004a5a  mov     [rbp+1400h+var_40], rax
0x180004a61  mov     r14, r8
0x180004a64  mov     esi, edx
0x180004a66  mov     r15, rcx
0x180004a69  mov     rdi, [rbp+1400h+arg_28]
0x180004a70  xor     edx, edx; Val
0x180004a72  mov     r8d, 98h; Size
0x180004a78  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004a7d  call    memset_0
0x180004a82  nop
0x180004a83  xor     r12d, r12d
0x180004a86  mov     [rbp+1400h+OutputString], r12w
0x180004a8e  mov     [rbp+1400h+var_1440], r12b
0x180004a92  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180004a99  mov     ecx, [rdx]; this
0x180004a9b  mov     [rsp+1500h+var_14D8], ecx
0x180004a9f  mov     eax, [rdx+4]
0x180004aa2  mov     [rsp+1500h+var_14D4], eax
0x180004aa6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004aab  mov     ebx, eax
0x180004aad  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180004ab5  mov     ecx, r12d
0x180004ab8  lea     eax, [r12+8]
0x180004abd  cmp     dword ptr [rdx+8], 1
0x180004ac1  cmovz   ecx, eax
0x180004ac4  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180004ac8  lea     ecx, [rax-7]
0x180004acb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004ad3  inc     ecx
0x180004ad5  mov     [rsp+1500h+var_14D0], ecx
0x180004ad9  mov     [rsp+1500h+var_14C8], r12
0x180004ade  call    cs:__imp_GetCurrentThreadId
0x180004ae4  mov     [rsp+1500h+var_14C0], eax
0x180004ae8  mov     [rsp+1500h+var_14A8], r14
0x180004aed  mov     [rsp+1500h+var_14A0], esi
0x180004af1  mov     [rsp+1500h+var_149C], ebx
0x180004af5  mov     [rsp+1500h+var_14B8], r12
0x180004afa  mov     [rsp+1500h+var_14B0], r12
0x180004aff  mov     [rbp+1400h+var_1458], rdi
0x180004b03  mov     [rbp+1400h+var_1450], r15
0x180004b07  mov     [rsp+1500h+var_1498], r12
0x180004b0c  xorps   xmm0, xmm0
0x180004b0f  xor     eax, eax
0x180004b11  movups  [rbp+1400h+var_1478], xmm0
0x180004b15  mov     [rbp+1400h+var_1468], rax
0x180004b19  xorps   xmm1, xmm1
0x180004b1c  movups  [rsp+1500h+var_1490], xmm1
0x180004b21  mov     [rbp+1400h+var_1480], rax
0x180004b25  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004b2c  test    rax, rax
0x180004b2f  jz      short loc_180004B3C
0x180004b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b36  mov     [rbp+1400h+var_1460], rax
0x180004b3a  jmp     short loc_180004B40
0x180004b3c  mov     [rbp+1400h+var_1460], r12
0x180004b40  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004b47  test    rax, rax
0x180004b4a  jz      short loc_180004B56
0x180004b4c  lea     rcx, [rsp+1500h+var_14E0]
0x180004b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b56  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004b5d  test    rax, rax
0x180004b60  jz      short loc_180004B76
0x180004b62  mov     r8d, 400h
0x180004b68  lea     rdx, [rbp+1400h+var_1440]
0x180004b6c  lea     rcx, [rsp+1500h+var_14E0]
0x180004b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b76  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004b7d  test    rax, rax
0x180004b80  jz      short loc_180004B8C
0x180004b82  lea     rcx, [rsp+1500h+var_14E0]
0x180004b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b8c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004b93  test    rax, rax
0x180004b96  jz      short loc_180004BA9
0x180004b98  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004b9d  jnz     short loc_180004BA9
0x180004b9f  lea     rcx, [rsp+1500h+var_14E0]
0x180004ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ba9  cmp     [rsp+1500h+var_14D8], r12d
0x180004bae  jge     loc_180004CB7
0x180004bb4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180004bbb  jnz     short loc_180004BDC
0x180004bbd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004bc4  test    rax, rax
0x180004bc7  jz      short loc_180004BD2
0x180004bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bce  test    al, al
0x180004bd0  jmp     short loc_180004BDA
0x180004bd2  call    cs:__imp_IsDebuggerPresent
0x180004bd8  test    eax, eax
0x180004bda  jz      short loc_180004BE3
0x180004bdc  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004be1  jz      short loc_180004C09
0x180004be3  mov     rax, cs:g_pfnResultLoggingCallback
0x180004bea  test    rax, rax
0x180004bed  jz      short loc_180004C62
0x180004bef  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004bf6  jnz     short loc_180004C62
0x180004bf8  xor     r8d, r8d
0x180004bfb  xor     edx, edx
0x180004bfd  lea     rcx, [rsp+1500h+var_14E0]
0x180004c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c07  jmp     short loc_180004C62
0x180004c09  mov     ebx, 800h
0x180004c0e  mov     rax, cs:g_pfnResultLoggingCallback
0x180004c15  test    rax, rax
0x180004c18  jz      short loc_180004C37
0x180004c1a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004c21  jnz     short loc_180004C37
0x180004c23  mov     r8d, ebx
0x180004c26  lea     rdx, [rbp+1400h+OutputString]
0x180004c2d  lea     rcx, [rsp+1500h+var_14E0]
0x180004c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c37  cmp     [rbp+1400h+OutputString], r12w
0x180004c3f  jnz     short loc_180004C55
0x180004c41  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180004c46  mov     rdx, rbx; unsigned __int16 *
0x180004c49  lea     rcx, [rbp+1400h+OutputString]; this
0x180004c50  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004c55  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004c5c  call    cs:__imp_OutputDebugStringW
0x180004c62  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004c67  jnz     short loc_180004C72
0x180004c69  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004c70  jz      short loc_180004C84
0x180004c72  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004c79  test    rax, rax
0x180004c7c  jz      short loc_180004C84
0x180004c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c83  nop
0x180004c84  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180004c89  jnz     short loc_180004CAC
0x180004c8b  mov     rcx, [rbp+1400h+var_40]
0x180004c92  xor     rcx, rsp; StackCookie
0x180004c95  call    __security_check_cookie
0x180004c9a  add     rsp, 14D0h
0x180004ca1  pop     r15
0x180004ca3  pop     r14
0x180004ca5  pop     r12
0x180004ca7  pop     rdi
0x180004ca8  pop     rsi
0x180004ca9  pop     rbx
0x180004caa  pop     rbp
0x180004cab  retn
0x180004cac  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004cb1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004cb7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
