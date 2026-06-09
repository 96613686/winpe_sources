# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140006a30`
- end: `0x140006ca9`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14000646c`

## callees

- `0x1400060f8`
- `0x140006a30`
- `0x140008e14`
- `0x140009674`
- `0x140009df0`
- `0x14000c470`
- `0x1400562f0`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006ae9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006ae9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006c76`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006c76`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140006bec`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140006bec`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
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
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
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
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x140006a30  mov     [rsp-8+arg_18], rbx
0x140006a35  push    rbp
0x140006a36  push    rsi
0x140006a37  push    rdi
0x140006a38  push    r12
0x140006a3a  push    r13
0x140006a3c  push    r14
0x140006a3e  push    r15
0x140006a40  lea     rbp, [rsp-13C0h]
0x140006a48  mov     eax, 14C0h
0x140006a4d  call    _alloca_probe
0x140006a52  sub     rsp, rax
0x140006a55  mov     r14, r8
0x140006a58  mov     esi, edx
0x140006a5a  mov     rdi, rcx
0x140006a5d  mov     r15, [rbp+13F0h+arg_28]
0x140006a64  xor     edx, edx; Val
0x140006a66  mov     r8d, 98h; Size
0x140006a6c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140006a71  call    memset_0
0x140006a76  nop
0x140006a77  xor     r13d, r13d
0x140006a7a  mov     [rbp+13F0h+OutputString], r13w
0x140006a82  mov     [rbp+13F0h+var_1430], r13b
0x140006a86  mov     rbx, [rbp+13F0h+arg_30]
0x140006a8d  mov     ecx, [rbx]; this
0x140006a8f  mov     [rsp+14F0h+var_14C8], ecx
0x140006a93  mov     eax, [rbx+4]
0x140006a96  mov     [rsp+14F0h+var_14C4], eax
0x140006a9a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140006a9f  mov     r12d, eax
0x140006aa2  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x140006aaa  mov     ecx, r13d
0x140006aad  lea     eax, [r13+8]
0x140006ab1  cmp     dword ptr [rbx+8], 1
0x140006ab5  cmovz   ecx, eax
0x140006ab8  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140006abc  lea     ecx, [rax-7]
0x140006abf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140006ac7  inc     ecx
0x140006ac9  mov     [rsp+14F0h+var_14C0], ecx
0x140006acd  mov     rcx, [rbp+13F0h+arg_38]
0x140006ad4  test    rcx, rcx
0x140006ad7  jz      short loc_140006AE4
0x140006ad9  cmp     [rcx], r13w
0x140006add  mov     [rsp+14F0h+var_14B8], rcx
0x140006ae2  jnz     short loc_140006AE9
0x140006ae4  mov     [rsp+14F0h+var_14B8], r13
0x140006ae9  call    cs:__imp_GetCurrentThreadId
0x140006aef  mov     [rsp+14F0h+var_14B0], eax
0x140006af3  mov     [rsp+14F0h+var_1498], r14
0x140006af8  mov     [rsp+14F0h+var_1490], esi
0x140006afc  mov     [rsp+14F0h+var_148C], r12d
0x140006b01  mov     [rsp+14F0h+var_14A8], r13
0x140006b06  mov     [rsp+14F0h+var_14A0], r13
0x140006b0b  mov     [rbp+13F0h+var_1448], r15
0x140006b0f  mov     [rbp+13F0h+var_1440], rdi
0x140006b13  mov     [rsp+14F0h+var_1488], r13
0x140006b18  xorps   xmm0, xmm0
0x140006b1b  xor     eax, eax
0x140006b1d  movups  [rbp+13F0h+var_1468], xmm0
0x140006b21  mov     [rbp+13F0h+var_1458], rax
0x140006b25  xorps   xmm1, xmm1
0x140006b28  movups  [rsp+14F0h+var_1480], xmm1
0x140006b2d  mov     [rbp+13F0h+var_1470], rax
0x140006b31  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140006b38  test    rax, rax
0x140006b3b  jz      short loc_140006B48
0x140006b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b42  mov     [rbp+13F0h+var_1450], rax
0x140006b46  jmp     short loc_140006B4C
0x140006b48  mov     [rbp+13F0h+var_1450], r13
0x140006b4c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140006b53  test    rax, rax
0x140006b56  jz      short loc_140006B62
0x140006b58  lea     rcx, [rsp+14F0h+var_14D0]
0x140006b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b62  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140006b69  test    rax, rax
0x140006b6c  jz      short loc_140006B82
0x140006b6e  mov     r8d, 400h
0x140006b74  lea     rdx, [rbp+13F0h+var_1430]
0x140006b78  lea     rcx, [rsp+14F0h+var_14D0]
0x140006b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b82  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006b89  test    rax, rax
0x140006b8c  jz      short loc_140006B98
0x140006b8e  lea     rcx, [rsp+14F0h+var_14D0]
0x140006b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b98  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006b9f  test    rax, rax
0x140006ba2  jz      short loc_140006BB5
0x140006ba4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140006ba9  jnz     short loc_140006BB5
0x140006bab  lea     rcx, [rsp+14F0h+var_14D0]
0x140006bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006bb5  cmp     [rsp+14F0h+var_14C8], r13d
0x140006bba  jl      short loc_140006BCE
0x140006bbc  mov     ecx, 8000FFFFh; this
0x140006bc1  mov     [rsp+14F0h+var_14C8], ecx
0x140006bc5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140006bca  mov     [rsp+14F0h+var_14C4], eax
0x140006bce  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140006bd5  jnz     short loc_140006BF6
0x140006bd7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140006bde  test    rax, rax
0x140006be1  jz      short loc_140006BEC
0x140006be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006be8  test    al, al
0x140006bea  jmp     short loc_140006BF4
0x140006bec  call    cs:__imp_IsDebuggerPresent
0x140006bf2  test    eax, eax
0x140006bf4  jz      short loc_140006BFD
0x140006bf6  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140006bfb  jz      short loc_140006C23
0x140006bfd  mov     rax, cs:g_pfnResultLoggingCallback
0x140006c04  test    rax, rax
0x140006c07  jz      short loc_140006C7C
0x140006c09  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140006c10  jnz     short loc_140006C7C
0x140006c12  xor     r8d, r8d
0x140006c15  xor     edx, edx
0x140006c17  lea     rcx, [rsp+14F0h+var_14D0]
0x140006c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c21  jmp     short loc_140006C7C
0x140006c23  mov     ebx, 800h
0x140006c28  mov     rax, cs:g_pfnResultLoggingCallback
0x140006c2f  test    rax, rax
0x140006c32  jz      short loc_140006C51
0x140006c34  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140006c3b  jnz     short loc_140006C51
0x140006c3d  mov     r8d, ebx
0x140006c40  lea     rdx, [rbp+13F0h+OutputString]
0x140006c47  lea     rcx, [rsp+14F0h+var_14D0]
0x140006c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c51  cmp     [rbp+13F0h+OutputString], r13w
0x140006c59  jnz     short loc_140006C6F
0x140006c5b  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140006c60  mov     rdx, rbx; unsigned __int16 *
0x140006c63  lea     rcx, [rbp+13F0h+OutputString]; this
0x140006c6a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140006c6f  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140006c76  call    cs:__imp_OutputDebugStringW
0x140006c7c  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140006c81  jnz     short loc_140006C8C
0x140006c83  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140006c8a  jz      short loc_140006C9E
0x140006c8c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140006c93  test    rax, rax
0x140006c96  jz      short loc_140006C9E
0x140006c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c9d  nop
0x140006c9e  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140006ca3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
