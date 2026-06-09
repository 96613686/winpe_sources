# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140067978`
- end: `0x140067c0e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140067458`

## callees

- `0x140002c43`
- `0x140067978`
- `0x140069a44`
- `0x14006b1d8`
- `0x14006d180`
- `0x14006d33c`
- `0x1400818b0`
- `0x140081970`
- `0x140085010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140067b1e`
- `KERNEL32!IsDebuggerPresent` at `0x140067b1e`
- `KERNEL32!OutputDebugStringW` at `0x140067ba8`
- `KERNEL32!OutputDebugStringW` at `0x140067ba8`
- `KERNEL32!GetCurrentThreadId` at `0x140067a23`
- `KERNEL32!GetCurrentThreadId` at `0x140067a23`

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
0x140067978  mov     [rsp-8+arg_10], rbx
0x14006797d  push    rbp
0x14006797e  push    rsi
0x14006797f  push    rdi
0x140067980  push    r14
0x140067982  push    r15
0x140067984  lea     rbp, [rsp-13D0h]
0x14006798c  mov     eax, 14D0h
0x140067991  call    _alloca_probe
0x140067996  sub     rsp, rax
0x140067999  mov     rax, cs:__security_cookie
0x1400679a0  xor     rax, rsp
0x1400679a3  mov     [rbp+13F0h+var_30], rax
0x1400679aa  mov     esi, edx
0x1400679ac  mov     r14, rcx
0x1400679af  mov     rdi, [rbp+13F0h+arg_28]
0x1400679b6  xor     edx, edx; Val
0x1400679b8  mov     r8d, 98h; Size
0x1400679be  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1400679c3  call    memset_0
0x1400679c8  nop
0x1400679c9  xor     r15d, r15d
0x1400679cc  mov     [rbp+13F0h+OutputString], r15w
0x1400679d4  mov     [rbp+13F0h+var_1430], r15b
0x1400679d8  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1400679df  mov     ecx, [rdx]; this
0x1400679e1  mov     [rsp+14F0h+var_14C8], ecx
0x1400679e5  mov     eax, [rdx+4]
0x1400679e8  mov     [rsp+14F0h+var_14C4], eax
0x1400679ec  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400679f1  mov     ebx, eax
0x1400679f3  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1400679fb  mov     ecx, r15d
0x1400679fe  lea     eax, [r15+8]
0x140067a02  cmp     dword ptr [rdx+8], 1
0x140067a06  cmovz   ecx, eax
0x140067a09  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140067a0d  lea     ecx, [rax-7]
0x140067a10  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140067a18  inc     ecx
0x140067a1a  mov     [rsp+14F0h+var_14C0], ecx
0x140067a1e  mov     [rsp+14F0h+var_14B8], r15
0x140067a23  call    cs:__imp_GetCurrentThreadId
0x140067a29  mov     [rsp+14F0h+var_14B0], eax
0x140067a2d  lea     rax, aWil; "wil"
0x140067a34  mov     [rsp+14F0h+var_1498], rax
0x140067a39  mov     [rsp+14F0h+var_1490], esi
0x140067a3d  mov     [rsp+14F0h+var_148C], ebx
0x140067a41  mov     [rsp+14F0h+var_14A8], r15
0x140067a46  mov     [rsp+14F0h+var_14A0], r15
0x140067a4b  mov     [rbp+13F0h+var_1448], rdi
0x140067a4f  mov     [rbp+13F0h+var_1440], r14
0x140067a53  mov     [rsp+14F0h+var_1488], r15
0x140067a58  xorps   xmm0, xmm0
0x140067a5b  xor     eax, eax
0x140067a5d  movups  [rbp+13F0h+var_1468], xmm0
0x140067a61  mov     [rbp+13F0h+var_1458], rax
0x140067a65  xorps   xmm1, xmm1
0x140067a68  movups  [rsp+14F0h+var_1480], xmm1
0x140067a6d  mov     [rbp+13F0h+var_1470], rax
0x140067a71  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140067a78  test    rax, rax
0x140067a7b  jz      short loc_140067A88
0x140067a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067a82  mov     [rbp+13F0h+var_1450], rax
0x140067a86  jmp     short loc_140067A8C
0x140067a88  mov     [rbp+13F0h+var_1450], r15
0x140067a8c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140067a93  test    rax, rax
0x140067a96  jz      short loc_140067AA2
0x140067a98  lea     rcx, [rsp+14F0h+var_14D0]
0x140067a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067aa2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140067aa9  test    rax, rax
0x140067aac  jz      short loc_140067AC2
0x140067aae  mov     r8d, 400h
0x140067ab4  lea     rdx, [rbp+13F0h+var_1430]
0x140067ab8  lea     rcx, [rsp+14F0h+var_14D0]
0x140067abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067ac2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140067ac9  test    rax, rax
0x140067acc  jz      short loc_140067AD8
0x140067ace  lea     rcx, [rsp+14F0h+var_14D0]
0x140067ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067ad8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140067adf  test    rax, rax
0x140067ae2  jz      short loc_140067AF5
0x140067ae4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140067ae9  jnz     short loc_140067AF5
0x140067aeb  lea     rcx, [rsp+14F0h+var_14D0]
0x140067af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067af5  cmp     [rsp+14F0h+var_14C8], r15d
0x140067afa  jge     loc_140067C08
0x140067b00  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x140067b07  jnz     short loc_140067B28
0x140067b09  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140067b10  test    rax, rax
0x140067b13  jz      short loc_140067B1E
0x140067b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067b1a  test    al, al
0x140067b1c  jmp     short loc_140067B26
0x140067b1e  call    cs:__imp_IsDebuggerPresent
0x140067b24  test    eax, eax
0x140067b26  jz      short loc_140067B2F
0x140067b28  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140067b2d  jz      short loc_140067B55
0x140067b2f  mov     rax, cs:g_pfnResultLoggingCallback
0x140067b36  test    rax, rax
0x140067b39  jz      short loc_140067BAE
0x140067b3b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140067b42  jnz     short loc_140067BAE
0x140067b44  xor     r8d, r8d
0x140067b47  xor     edx, edx
0x140067b49  lea     rcx, [rsp+14F0h+var_14D0]
0x140067b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067b53  jmp     short loc_140067BAE
0x140067b55  mov     ebx, 800h
0x140067b5a  mov     rax, cs:g_pfnResultLoggingCallback
0x140067b61  test    rax, rax
0x140067b64  jz      short loc_140067B83
0x140067b66  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140067b6d  jnz     short loc_140067B83
0x140067b6f  mov     r8d, ebx
0x140067b72  lea     rdx, [rbp+13F0h+OutputString]
0x140067b79  lea     rcx, [rsp+14F0h+var_14D0]
0x140067b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067b83  cmp     [rbp+13F0h+OutputString], r15w
0x140067b8b  jnz     short loc_140067BA1
0x140067b8d  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140067b92  mov     rdx, rbx; unsigned __int16 *
0x140067b95  lea     rcx, [rbp+13F0h+OutputString]; this
0x140067b9c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140067ba1  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140067ba8  call    cs:__imp_OutputDebugStringW
0x140067bae  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140067bb3  jnz     short loc_140067BBE
0x140067bb5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x140067bbc  jz      short loc_140067BD0
0x140067bbe  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140067bc5  test    rax, rax
0x140067bc8  jz      short loc_140067BD0
0x140067bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067bcf  nop
0x140067bd0  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140067bd5  jnz     short loc_140067BFD
0x140067bd7  mov     rcx, [rbp+13F0h+var_30]
0x140067bde  xor     rcx, rsp; StackCookie
0x140067be1  call    __security_check_cookie
0x140067be6  mov     rbx, [rsp+14F0h+arg_10]
0x140067bee  add     rsp, 14D0h
0x140067bf5  pop     r15
0x140067bf7  pop     r14
0x140067bf9  pop     rdi
0x140067bfa  pop     rsi
0x140067bfb  pop     rbp
0x140067bfc  retn
0x140067bfd  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140067c02  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140067c08  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
