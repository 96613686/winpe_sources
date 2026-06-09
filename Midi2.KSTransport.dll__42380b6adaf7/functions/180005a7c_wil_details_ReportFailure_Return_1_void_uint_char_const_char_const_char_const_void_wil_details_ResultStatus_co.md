# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180005a7c`
- end: `0x180005d09`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000555c`

## callees

- `0x180004410`
- `0x18000526c`
- `0x180005a7c`
- `0x180008094`
- `0x1800097b0`
- `0x18000ba00`
- `0x18000baf4`
- `0x18003e3f0`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005b2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005b2a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005ca8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005ca8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005c1e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005c1e`

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
0x180005a7c  push    rbp
0x180005a7e  push    rbx
0x180005a7f  push    rsi
0x180005a80  push    rdi
0x180005a81  push    r12
0x180005a83  push    r14
0x180005a85  push    r15
0x180005a87  lea     rbp, [rsp-13D0h]
0x180005a8f  mov     eax, 14D0h
0x180005a94  call    _alloca_probe
0x180005a99  sub     rsp, rax
0x180005a9c  mov     rax, cs:__security_cookie
0x180005aa3  xor     rax, rsp
0x180005aa6  mov     [rbp+1400h+var_40], rax
0x180005aad  mov     r14, r8
0x180005ab0  mov     esi, edx
0x180005ab2  mov     r15, rcx
0x180005ab5  mov     rdi, [rbp+1400h+arg_28]
0x180005abc  xor     edx, edx; Val
0x180005abe  mov     r8d, 98h; Size
0x180005ac4  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180005ac9  call    memset_0
0x180005ace  nop
0x180005acf  xor     r12d, r12d
0x180005ad2  mov     [rbp+1400h+OutputString], r12w
0x180005ada  mov     [rbp+1400h+var_1440], r12b
0x180005ade  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180005ae5  mov     ecx, [rdx]; this
0x180005ae7  mov     [rsp+1500h+var_14D8], ecx
0x180005aeb  mov     eax, [rdx+4]
0x180005aee  mov     [rsp+1500h+var_14D4], eax
0x180005af2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005af7  mov     ebx, eax
0x180005af9  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180005b01  mov     ecx, r12d
0x180005b04  lea     eax, [r12+8]
0x180005b09  cmp     dword ptr [rdx+8], 1
0x180005b0d  cmovz   ecx, eax
0x180005b10  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180005b14  lea     ecx, [rax-7]
0x180005b17  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005b1f  inc     ecx
0x180005b21  mov     [rsp+1500h+var_14D0], ecx
0x180005b25  mov     [rsp+1500h+var_14C8], r12
0x180005b2a  call    cs:__imp_GetCurrentThreadId
0x180005b30  mov     [rsp+1500h+var_14C0], eax
0x180005b34  mov     [rsp+1500h+var_14A8], r14
0x180005b39  mov     [rsp+1500h+var_14A0], esi
0x180005b3d  mov     [rsp+1500h+var_149C], ebx
0x180005b41  mov     [rsp+1500h+var_14B8], r12
0x180005b46  mov     [rsp+1500h+var_14B0], r12
0x180005b4b  mov     [rbp+1400h+var_1458], rdi
0x180005b4f  mov     [rbp+1400h+var_1450], r15
0x180005b53  mov     [rsp+1500h+var_1498], r12
0x180005b58  xorps   xmm0, xmm0
0x180005b5b  xor     eax, eax
0x180005b5d  movups  [rbp+1400h+var_1478], xmm0
0x180005b61  mov     [rbp+1400h+var_1468], rax
0x180005b65  xorps   xmm1, xmm1
0x180005b68  movups  [rsp+1500h+var_1490], xmm1
0x180005b6d  mov     [rbp+1400h+var_1480], rax
0x180005b71  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005b78  test    rax, rax
0x180005b7b  jz      short loc_180005B88
0x180005b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b82  mov     [rbp+1400h+var_1460], rax
0x180005b86  jmp     short loc_180005B8C
0x180005b88  mov     [rbp+1400h+var_1460], r12
0x180005b8c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005b93  test    rax, rax
0x180005b96  jz      short loc_180005BA2
0x180005b98  lea     rcx, [rsp+1500h+var_14E0]
0x180005b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ba2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005ba9  test    rax, rax
0x180005bac  jz      short loc_180005BC2
0x180005bae  mov     r8d, 400h
0x180005bb4  lea     rdx, [rbp+1400h+var_1440]
0x180005bb8  lea     rcx, [rsp+1500h+var_14E0]
0x180005bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bc2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005bc9  test    rax, rax
0x180005bcc  jz      short loc_180005BD8
0x180005bce  lea     rcx, [rsp+1500h+var_14E0]
0x180005bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bd8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005bdf  test    rax, rax
0x180005be2  jz      short loc_180005BF5
0x180005be4  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005be9  jnz     short loc_180005BF5
0x180005beb  lea     rcx, [rsp+1500h+var_14E0]
0x180005bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bf5  cmp     [rsp+1500h+var_14D8], r12d
0x180005bfa  jge     loc_180005D03
0x180005c00  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180005c07  jnz     short loc_180005C28
0x180005c09  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005c10  test    rax, rax
0x180005c13  jz      short loc_180005C1E
0x180005c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c1a  test    al, al
0x180005c1c  jmp     short loc_180005C26
0x180005c1e  call    cs:__imp_IsDebuggerPresent
0x180005c24  test    eax, eax
0x180005c26  jz      short loc_180005C2F
0x180005c28  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005c2d  jz      short loc_180005C55
0x180005c2f  mov     rax, cs:g_pfnResultLoggingCallback
0x180005c36  test    rax, rax
0x180005c39  jz      short loc_180005CAE
0x180005c3b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005c42  jnz     short loc_180005CAE
0x180005c44  xor     r8d, r8d
0x180005c47  xor     edx, edx
0x180005c49  lea     rcx, [rsp+1500h+var_14E0]
0x180005c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c53  jmp     short loc_180005CAE
0x180005c55  mov     ebx, 800h
0x180005c5a  mov     rax, cs:g_pfnResultLoggingCallback
0x180005c61  test    rax, rax
0x180005c64  jz      short loc_180005C83
0x180005c66  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005c6d  jnz     short loc_180005C83
0x180005c6f  mov     r8d, ebx
0x180005c72  lea     rdx, [rbp+1400h+OutputString]
0x180005c79  lea     rcx, [rsp+1500h+var_14E0]
0x180005c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c83  cmp     [rbp+1400h+OutputString], r12w
0x180005c8b  jnz     short loc_180005CA1
0x180005c8d  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180005c92  mov     rdx, rbx; unsigned __int16 *
0x180005c95  lea     rcx, [rbp+1400h+OutputString]; this
0x180005c9c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005ca1  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180005ca8  call    cs:__imp_OutputDebugStringW
0x180005cae  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180005cb3  jnz     short loc_180005CBE
0x180005cb5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180005cbc  jz      short loc_180005CD0
0x180005cbe  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005cc5  test    rax, rax
0x180005cc8  jz      short loc_180005CD0
0x180005cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ccf  nop
0x180005cd0  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180005cd5  jnz     short loc_180005CF8
0x180005cd7  mov     rcx, [rbp+1400h+var_40]
0x180005cde  xor     rcx, rsp; StackCookie
0x180005ce1  call    __security_check_cookie
0x180005ce6  add     rsp, 14D0h
0x180005ced  pop     r15
0x180005cef  pop     r14
0x180005cf1  pop     r12
0x180005cf3  pop     rdi
0x180005cf4  pop     rsi
0x180005cf5  pop     rbx
0x180005cf6  pop     rbp
0x180005cf7  retn
0x180005cf8  lea     rcx, [rsp+1500h+var_14E0]; this
0x180005cfd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005d03  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
