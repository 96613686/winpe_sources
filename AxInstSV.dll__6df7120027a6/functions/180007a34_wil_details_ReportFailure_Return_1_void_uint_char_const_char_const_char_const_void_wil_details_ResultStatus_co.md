# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180007a34`
- end: `0x180007cca`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800076fc`

## callees

- `0x180001720`
- `0x1800021b8`
- `0x180007a34`
- `0x18000b174`
- `0x18000dd40`
- `0x180010c58`
- `0x180010e28`
- `0x1800142b0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007adf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007adf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007bda`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007bda`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007c64`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007c64`

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
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x180007a34  mov     [rsp-8+arg_10], rbx
0x180007a39  push    rbp
0x180007a3a  push    rsi
0x180007a3b  push    rdi
0x180007a3c  push    r14
0x180007a3e  push    r15
0x180007a40  lea     rbp, [rsp-13D0h]
0x180007a48  mov     eax, 14D0h
0x180007a4d  call    _alloca_probe
0x180007a52  sub     rsp, rax
0x180007a55  mov     rax, cs:__security_cookie
0x180007a5c  xor     rax, rsp
0x180007a5f  mov     [rbp+13F0h+var_30], rax
0x180007a66  mov     esi, edx
0x180007a68  mov     r14, rcx
0x180007a6b  mov     rdi, [rbp+13F0h+arg_28]
0x180007a72  xor     edx, edx; Val
0x180007a74  mov     r8d, 98h; Size
0x180007a7a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180007a7f  call    memset_0
0x180007a84  nop
0x180007a85  xor     r15d, r15d
0x180007a88  mov     [rbp+13F0h+OutputString], r15w
0x180007a90  mov     [rbp+13F0h+var_1430], r15b
0x180007a94  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180007a9b  mov     ecx, [rdx]; this
0x180007a9d  mov     [rsp+14F0h+var_14C8], ecx
0x180007aa1  mov     eax, [rdx+4]
0x180007aa4  mov     [rsp+14F0h+var_14C4], eax
0x180007aa8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007aad  mov     ebx, eax
0x180007aaf  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180007ab7  mov     ecx, r15d
0x180007aba  lea     eax, [r15+8]
0x180007abe  cmp     dword ptr [rdx+8], 1
0x180007ac2  cmovz   ecx, eax
0x180007ac5  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180007ac9  lea     ecx, [rax-7]
0x180007acc  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007ad4  inc     ecx
0x180007ad6  mov     [rsp+14F0h+var_14C0], ecx
0x180007ada  mov     [rsp+14F0h+var_14B8], r15
0x180007adf  call    cs:__imp_GetCurrentThreadId
0x180007ae5  mov     [rsp+14F0h+var_14B0], eax
0x180007ae9  lea     rax, aWil; "wil"
0x180007af0  mov     [rsp+14F0h+var_1498], rax
0x180007af5  mov     [rsp+14F0h+var_1490], esi
0x180007af9  mov     [rsp+14F0h+var_148C], ebx
0x180007afd  mov     [rsp+14F0h+var_14A8], r15
0x180007b02  mov     [rsp+14F0h+var_14A0], r15
0x180007b07  mov     [rbp+13F0h+var_1448], rdi
0x180007b0b  mov     [rbp+13F0h+var_1440], r14
0x180007b0f  mov     [rsp+14F0h+var_1488], r15
0x180007b14  xorps   xmm0, xmm0
0x180007b17  xor     eax, eax
0x180007b19  movups  [rbp+13F0h+var_1468], xmm0
0x180007b1d  mov     [rbp+13F0h+var_1458], rax
0x180007b21  xorps   xmm1, xmm1
0x180007b24  movups  [rsp+14F0h+var_1480], xmm1
0x180007b29  mov     [rbp+13F0h+var_1470], rax
0x180007b2d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007b34  test    rax, rax
0x180007b37  jz      short loc_180007B44
0x180007b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b3e  mov     [rbp+13F0h+var_1450], rax
0x180007b42  jmp     short loc_180007B48
0x180007b44  mov     [rbp+13F0h+var_1450], r15
0x180007b48  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007b4f  test    rax, rax
0x180007b52  jz      short loc_180007B5E
0x180007b54  lea     rcx, [rsp+14F0h+var_14D0]
0x180007b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b5e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007b65  test    rax, rax
0x180007b68  jz      short loc_180007B7E
0x180007b6a  mov     r8d, 400h
0x180007b70  lea     rdx, [rbp+13F0h+var_1430]
0x180007b74  lea     rcx, [rsp+14F0h+var_14D0]
0x180007b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b7e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007b85  test    rax, rax
0x180007b88  jz      short loc_180007B94
0x180007b8a  lea     rcx, [rsp+14F0h+var_14D0]
0x180007b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b94  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007b9b  test    rax, rax
0x180007b9e  jz      short loc_180007BB1
0x180007ba0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007ba5  jnz     short loc_180007BB1
0x180007ba7  lea     rcx, [rsp+14F0h+var_14D0]
0x180007bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bb1  cmp     [rsp+14F0h+var_14C8], r15d
0x180007bb6  jge     loc_180007CC4
0x180007bbc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180007bc3  jnz     short loc_180007BE4
0x180007bc5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007bcc  test    rax, rax
0x180007bcf  jz      short loc_180007BDA
0x180007bd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bd6  test    al, al
0x180007bd8  jmp     short loc_180007BE2
0x180007bda  call    cs:__imp_IsDebuggerPresent
0x180007be0  test    eax, eax
0x180007be2  jz      short loc_180007BEB
0x180007be4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007be9  jz      short loc_180007C11
0x180007beb  mov     rax, cs:g_pfnResultLoggingCallback
0x180007bf2  test    rax, rax
0x180007bf5  jz      short loc_180007C6A
0x180007bf7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007bfe  jnz     short loc_180007C6A
0x180007c00  xor     r8d, r8d
0x180007c03  xor     edx, edx
0x180007c05  lea     rcx, [rsp+14F0h+var_14D0]
0x180007c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c0f  jmp     short loc_180007C6A
0x180007c11  mov     ebx, 800h
0x180007c16  mov     rax, cs:g_pfnResultLoggingCallback
0x180007c1d  test    rax, rax
0x180007c20  jz      short loc_180007C3F
0x180007c22  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007c29  jnz     short loc_180007C3F
0x180007c2b  mov     r8d, ebx
0x180007c2e  lea     rdx, [rbp+13F0h+OutputString]
0x180007c35  lea     rcx, [rsp+14F0h+var_14D0]
0x180007c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c3f  cmp     [rbp+13F0h+OutputString], r15w
0x180007c47  jnz     short loc_180007C5D
0x180007c49  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180007c4e  mov     rdx, rbx; unsigned __int16 *
0x180007c51  lea     rcx, [rbp+13F0h+OutputString]; this
0x180007c58  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007c5d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180007c64  call    cs:__imp_OutputDebugStringW
0x180007c6a  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180007c6f  jnz     short loc_180007C7A
0x180007c71  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180007c78  jz      short loc_180007C8C
0x180007c7a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007c81  test    rax, rax
0x180007c84  jz      short loc_180007C8C
0x180007c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c8b  nop
0x180007c8c  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180007c91  jnz     short loc_180007CB9
0x180007c93  mov     rcx, [rbp+13F0h+var_30]
0x180007c9a  xor     rcx, rsp; StackCookie
0x180007c9d  call    __security_check_cookie
0x180007ca2  mov     rbx, [rsp+14F0h+arg_10]
0x180007caa  add     rsp, 14D0h
0x180007cb1  pop     r15
0x180007cb3  pop     r14
0x180007cb5  pop     rdi
0x180007cb6  pop     rsi
0x180007cb7  pop     rbp
0x180007cb8  retn
0x180007cb9  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180007cbe  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180007cc4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
