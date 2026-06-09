# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000398c`
- end: `0x180003c22`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000346c`

## callees

- `0x180001d40`
- `0x180002a28`
- `0x18000398c`
- `0x180005c34`
- `0x180007498`
- `0x1800099f0`
- `0x180009bbc`
- `0x180017e10`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003bbc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003bbc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003b32`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003b32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003a37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003a37`

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
0x18000398c  mov     [rsp-8+arg_10], rbx
0x180003991  push    rbp
0x180003992  push    rsi
0x180003993  push    rdi
0x180003994  push    r14
0x180003996  push    r15
0x180003998  lea     rbp, [rsp-13D0h]
0x1800039a0  mov     eax, 14D0h
0x1800039a5  call    _alloca_probe
0x1800039aa  sub     rsp, rax
0x1800039ad  mov     rax, cs:__security_cookie
0x1800039b4  xor     rax, rsp
0x1800039b7  mov     [rbp+13F0h+var_30], rax
0x1800039be  mov     esi, edx
0x1800039c0  mov     r14, rcx
0x1800039c3  mov     rdi, [rbp+13F0h+arg_28]
0x1800039ca  xor     edx, edx; Val
0x1800039cc  mov     r8d, 98h; Size
0x1800039d2  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800039d7  call    memset_0
0x1800039dc  nop
0x1800039dd  xor     r15d, r15d
0x1800039e0  mov     [rbp+13F0h+OutputString], r15w
0x1800039e8  mov     [rbp+13F0h+var_1430], r15b
0x1800039ec  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800039f3  mov     ecx, [rdx]; this
0x1800039f5  mov     [rsp+14F0h+var_14C8], ecx
0x1800039f9  mov     eax, [rdx+4]
0x1800039fc  mov     [rsp+14F0h+var_14C4], eax
0x180003a00  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003a05  mov     ebx, eax
0x180003a07  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180003a0f  mov     ecx, r15d
0x180003a12  lea     eax, [r15+8]
0x180003a16  cmp     dword ptr [rdx+8], 1
0x180003a1a  cmovz   ecx, eax
0x180003a1d  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003a21  lea     ecx, [rax-7]
0x180003a24  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003a2c  inc     ecx
0x180003a2e  mov     [rsp+14F0h+var_14C0], ecx
0x180003a32  mov     [rsp+14F0h+var_14B8], r15
0x180003a37  call    cs:__imp_GetCurrentThreadId
0x180003a3d  mov     [rsp+14F0h+var_14B0], eax
0x180003a41  lea     rax, aWil; "wil"
0x180003a48  mov     [rsp+14F0h+var_1498], rax
0x180003a4d  mov     [rsp+14F0h+var_1490], esi
0x180003a51  mov     [rsp+14F0h+var_148C], ebx
0x180003a55  mov     [rsp+14F0h+var_14A8], r15
0x180003a5a  mov     [rsp+14F0h+var_14A0], r15
0x180003a5f  mov     [rbp+13F0h+var_1448], rdi
0x180003a63  mov     [rbp+13F0h+var_1440], r14
0x180003a67  mov     [rsp+14F0h+var_1488], r15
0x180003a6c  xorps   xmm0, xmm0
0x180003a6f  xor     eax, eax
0x180003a71  movups  [rbp+13F0h+var_1468], xmm0
0x180003a75  mov     [rbp+13F0h+var_1458], rax
0x180003a79  xorps   xmm1, xmm1
0x180003a7c  movups  [rsp+14F0h+var_1480], xmm1
0x180003a81  mov     [rbp+13F0h+var_1470], rax
0x180003a85  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003a8c  test    rax, rax
0x180003a8f  jz      short loc_180003A9C
0x180003a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a96  mov     [rbp+13F0h+var_1450], rax
0x180003a9a  jmp     short loc_180003AA0
0x180003a9c  mov     [rbp+13F0h+var_1450], r15
0x180003aa0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003aa7  test    rax, rax
0x180003aaa  jz      short loc_180003AB6
0x180003aac  lea     rcx, [rsp+14F0h+var_14D0]
0x180003ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ab6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003abd  test    rax, rax
0x180003ac0  jz      short loc_180003AD6
0x180003ac2  mov     r8d, 400h
0x180003ac8  lea     rdx, [rbp+13F0h+var_1430]
0x180003acc  lea     rcx, [rsp+14F0h+var_14D0]
0x180003ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ad6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003add  test    rax, rax
0x180003ae0  jz      short loc_180003AEC
0x180003ae2  lea     rcx, [rsp+14F0h+var_14D0]
0x180003ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aec  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003af3  test    rax, rax
0x180003af6  jz      short loc_180003B09
0x180003af8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003afd  jnz     short loc_180003B09
0x180003aff  lea     rcx, [rsp+14F0h+var_14D0]
0x180003b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b09  cmp     [rsp+14F0h+var_14C8], r15d
0x180003b0e  jge     loc_180003C1C
0x180003b14  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180003b1b  jnz     short loc_180003B3C
0x180003b1d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003b24  test    rax, rax
0x180003b27  jz      short loc_180003B32
0x180003b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b2e  test    al, al
0x180003b30  jmp     short loc_180003B3A
0x180003b32  call    cs:__imp_IsDebuggerPresent
0x180003b38  test    eax, eax
0x180003b3a  jz      short loc_180003B43
0x180003b3c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003b41  jz      short loc_180003B69
0x180003b43  mov     rax, cs:g_pfnResultLoggingCallback
0x180003b4a  test    rax, rax
0x180003b4d  jz      short loc_180003BC2
0x180003b4f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003b56  jnz     short loc_180003BC2
0x180003b58  xor     r8d, r8d
0x180003b5b  xor     edx, edx
0x180003b5d  lea     rcx, [rsp+14F0h+var_14D0]
0x180003b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b67  jmp     short loc_180003BC2
0x180003b69  mov     ebx, 800h
0x180003b6e  mov     rax, cs:g_pfnResultLoggingCallback
0x180003b75  test    rax, rax
0x180003b78  jz      short loc_180003B97
0x180003b7a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003b81  jnz     short loc_180003B97
0x180003b83  mov     r8d, ebx
0x180003b86  lea     rdx, [rbp+13F0h+OutputString]
0x180003b8d  lea     rcx, [rsp+14F0h+var_14D0]
0x180003b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b97  cmp     [rbp+13F0h+OutputString], r15w
0x180003b9f  jnz     short loc_180003BB5
0x180003ba1  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003ba6  mov     rdx, rbx; unsigned __int16 *
0x180003ba9  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003bb0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003bb5  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003bbc  call    cs:__imp_OutputDebugStringW
0x180003bc2  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003bc7  jnz     short loc_180003BD2
0x180003bc9  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180003bd0  jz      short loc_180003BE4
0x180003bd2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003bd9  test    rax, rax
0x180003bdc  jz      short loc_180003BE4
0x180003bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003be3  nop
0x180003be4  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003be9  jnz     short loc_180003C11
0x180003beb  mov     rcx, [rbp+13F0h+var_30]
0x180003bf2  xor     rcx, rsp; StackCookie
0x180003bf5  call    __security_check_cookie
0x180003bfa  mov     rbx, [rsp+14F0h+arg_10]
0x180003c02  add     rsp, 14D0h
0x180003c09  pop     r15
0x180003c0b  pop     r14
0x180003c0d  pop     rdi
0x180003c0e  pop     rsi
0x180003c0f  pop     rbp
0x180003c10  retn
0x180003c11  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003c16  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003c1c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
