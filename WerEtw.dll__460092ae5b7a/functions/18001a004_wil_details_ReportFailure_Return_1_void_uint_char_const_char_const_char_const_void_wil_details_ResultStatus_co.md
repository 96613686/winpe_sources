# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18001a004`
- end: `0x18001a29a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180019aec`

## callees

- `0x180001870`
- `0x180002420`
- `0x18001a004`
- `0x18001cc84`
- `0x18001e560`
- `0x18001f810`
- `0x18001f8ec`
- `0x180027b80`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a0af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a0af`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001a1aa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001a1aa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001a234`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001a234`

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
0x18001a004  mov     [rsp-8+arg_10], rbx
0x18001a009  push    rbp
0x18001a00a  push    rsi
0x18001a00b  push    rdi
0x18001a00c  push    r14
0x18001a00e  push    r15
0x18001a010  lea     rbp, [rsp-13D0h]
0x18001a018  mov     eax, 14D0h
0x18001a01d  call    _alloca_probe
0x18001a022  sub     rsp, rax
0x18001a025  mov     rax, cs:__security_cookie
0x18001a02c  xor     rax, rsp
0x18001a02f  mov     [rbp+13F0h+var_30], rax
0x18001a036  mov     esi, edx
0x18001a038  mov     r14, rcx
0x18001a03b  mov     rdi, [rbp+13F0h+arg_28]
0x18001a042  xor     edx, edx; Val
0x18001a044  mov     r8d, 98h; Size
0x18001a04a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18001a04f  call    memset_0
0x18001a054  nop
0x18001a055  xor     r15d, r15d
0x18001a058  mov     [rbp+13F0h+OutputString], r15w
0x18001a060  mov     [rbp+13F0h+var_1430], r15b
0x18001a064  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18001a06b  mov     ecx, [rdx]; this
0x18001a06d  mov     [rsp+14F0h+var_14C8], ecx
0x18001a071  mov     eax, [rdx+4]
0x18001a074  mov     [rsp+14F0h+var_14C4], eax
0x18001a078  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001a07d  mov     ebx, eax
0x18001a07f  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18001a087  mov     ecx, r15d
0x18001a08a  lea     eax, [r15+8]
0x18001a08e  cmp     dword ptr [rdx+8], 1
0x18001a092  cmovz   ecx, eax
0x18001a095  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18001a099  lea     ecx, [rax-7]
0x18001a09c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001a0a4  inc     ecx
0x18001a0a6  mov     [rsp+14F0h+var_14C0], ecx
0x18001a0aa  mov     [rsp+14F0h+var_14B8], r15
0x18001a0af  call    cs:__imp_GetCurrentThreadId
0x18001a0b5  mov     [rsp+14F0h+var_14B0], eax
0x18001a0b9  lea     rax, aWil; "wil"
0x18001a0c0  mov     [rsp+14F0h+var_1498], rax
0x18001a0c5  mov     [rsp+14F0h+var_1490], esi
0x18001a0c9  mov     [rsp+14F0h+var_148C], ebx
0x18001a0cd  mov     [rsp+14F0h+var_14A8], r15
0x18001a0d2  mov     [rsp+14F0h+var_14A0], r15
0x18001a0d7  mov     [rbp+13F0h+var_1448], rdi
0x18001a0db  mov     [rbp+13F0h+var_1440], r14
0x18001a0df  mov     [rsp+14F0h+var_1488], r15
0x18001a0e4  xorps   xmm0, xmm0
0x18001a0e7  xor     eax, eax
0x18001a0e9  movups  [rbp+13F0h+var_1468], xmm0
0x18001a0ed  mov     [rbp+13F0h+var_1458], rax
0x18001a0f1  xorps   xmm1, xmm1
0x18001a0f4  movups  [rsp+14F0h+var_1480], xmm1
0x18001a0f9  mov     [rbp+13F0h+var_1470], rax
0x18001a0fd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001a104  test    rax, rax
0x18001a107  jz      short loc_18001A114
0x18001a109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a10e  mov     [rbp+13F0h+var_1450], rax
0x18001a112  jmp     short loc_18001A118
0x18001a114  mov     [rbp+13F0h+var_1450], r15
0x18001a118  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001a11f  test    rax, rax
0x18001a122  jz      short loc_18001A12E
0x18001a124  lea     rcx, [rsp+14F0h+var_14D0]
0x18001a129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a12e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001a135  test    rax, rax
0x18001a138  jz      short loc_18001A14E
0x18001a13a  mov     r8d, 400h
0x18001a140  lea     rdx, [rbp+13F0h+var_1430]
0x18001a144  lea     rcx, [rsp+14F0h+var_14D0]
0x18001a149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a14e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001a155  test    rax, rax
0x18001a158  jz      short loc_18001A164
0x18001a15a  lea     rcx, [rsp+14F0h+var_14D0]
0x18001a15f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a164  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001a16b  test    rax, rax
0x18001a16e  jz      short loc_18001A181
0x18001a170  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001a175  jnz     short loc_18001A181
0x18001a177  lea     rcx, [rsp+14F0h+var_14D0]
0x18001a17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a181  cmp     [rsp+14F0h+var_14C8], r15d
0x18001a186  jge     loc_18001A294
0x18001a18c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18001a193  jnz     short loc_18001A1B4
0x18001a195  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001a19c  test    rax, rax
0x18001a19f  jz      short loc_18001A1AA
0x18001a1a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1a6  test    al, al
0x18001a1a8  jmp     short loc_18001A1B2
0x18001a1aa  call    cs:__imp_IsDebuggerPresent
0x18001a1b0  test    eax, eax
0x18001a1b2  jz      short loc_18001A1BB
0x18001a1b4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001a1b9  jz      short loc_18001A1E1
0x18001a1bb  mov     rax, cs:g_pfnResultLoggingCallback
0x18001a1c2  test    rax, rax
0x18001a1c5  jz      short loc_18001A23A
0x18001a1c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001a1ce  jnz     short loc_18001A23A
0x18001a1d0  xor     r8d, r8d
0x18001a1d3  xor     edx, edx
0x18001a1d5  lea     rcx, [rsp+14F0h+var_14D0]
0x18001a1da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1df  jmp     short loc_18001A23A
0x18001a1e1  mov     ebx, 800h
0x18001a1e6  mov     rax, cs:g_pfnResultLoggingCallback
0x18001a1ed  test    rax, rax
0x18001a1f0  jz      short loc_18001A20F
0x18001a1f2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001a1f9  jnz     short loc_18001A20F
0x18001a1fb  mov     r8d, ebx
0x18001a1fe  lea     rdx, [rbp+13F0h+OutputString]
0x18001a205  lea     rcx, [rsp+14F0h+var_14D0]
0x18001a20a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a20f  cmp     [rbp+13F0h+OutputString], r15w
0x18001a217  jnz     short loc_18001A22D
0x18001a219  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18001a21e  mov     rdx, rbx; unsigned __int16 *
0x18001a221  lea     rcx, [rbp+13F0h+OutputString]; this
0x18001a228  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001a22d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18001a234  call    cs:__imp_OutputDebugStringW
0x18001a23a  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18001a23f  jnz     short loc_18001A24A
0x18001a241  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18001a248  jz      short loc_18001A25C
0x18001a24a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001a251  test    rax, rax
0x18001a254  jz      short loc_18001A25C
0x18001a256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a25b  nop
0x18001a25c  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18001a261  jnz     short loc_18001A289
0x18001a263  mov     rcx, [rbp+13F0h+var_30]
0x18001a26a  xor     rcx, rsp; StackCookie
0x18001a26d  call    __security_check_cookie
0x18001a272  mov     rbx, [rsp+14F0h+arg_10]
0x18001a27a  add     rsp, 14D0h
0x18001a281  pop     r15
0x18001a283  pop     r14
0x18001a285  pop     rdi
0x18001a286  pop     rsi
0x18001a287  pop     rbp
0x18001a288  retn
0x18001a289  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001a28e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001a294  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
