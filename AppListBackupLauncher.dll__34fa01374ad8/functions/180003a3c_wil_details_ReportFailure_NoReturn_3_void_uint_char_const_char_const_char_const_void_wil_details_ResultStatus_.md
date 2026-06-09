# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180003a3c`
- end: `0x180003cb5`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003634`

## callees

- `0x180002de0`
- `0x180003a3c`
- `0x18000860c`
- `0x180008f00`
- `0x18000a7b0`
- `0x18000de50`
- `0x180010290`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003af5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003af5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003bf8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003bf8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003c82`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003c82`

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
0x180003a3c  mov     [rsp-8+arg_18], rbx
0x180003a41  push    rbp
0x180003a42  push    rsi
0x180003a43  push    rdi
0x180003a44  push    r12
0x180003a46  push    r13
0x180003a48  push    r14
0x180003a4a  push    r15
0x180003a4c  lea     rbp, [rsp-13C0h]
0x180003a54  mov     eax, 14C0h
0x180003a59  call    _alloca_probe
0x180003a5e  sub     rsp, rax
0x180003a61  mov     r14, r8
0x180003a64  mov     esi, edx
0x180003a66  mov     rdi, rcx
0x180003a69  mov     r15, [rbp+13F0h+arg_28]
0x180003a70  xor     edx, edx; Val
0x180003a72  mov     r8d, 98h; Size
0x180003a78  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003a7d  call    memset_0
0x180003a82  nop
0x180003a83  xor     r13d, r13d
0x180003a86  mov     [rbp+13F0h+OutputString], r13w
0x180003a8e  mov     [rbp+13F0h+var_1430], r13b
0x180003a92  mov     rbx, [rbp+13F0h+arg_30]
0x180003a99  mov     ecx, [rbx]; this
0x180003a9b  mov     [rsp+14F0h+var_14C8], ecx
0x180003a9f  mov     eax, [rbx+4]
0x180003aa2  mov     [rsp+14F0h+var_14C4], eax
0x180003aa6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003aab  mov     r12d, eax
0x180003aae  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180003ab6  mov     ecx, r13d
0x180003ab9  lea     eax, [r13+8]
0x180003abd  cmp     dword ptr [rbx+8], 1
0x180003ac1  cmovz   ecx, eax
0x180003ac4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003ac8  lea     ecx, [rax-7]
0x180003acb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003ad3  inc     ecx
0x180003ad5  mov     [rsp+14F0h+var_14C0], ecx
0x180003ad9  mov     rcx, [rbp+13F0h+arg_38]
0x180003ae0  test    rcx, rcx
0x180003ae3  jz      short loc_180003AF0
0x180003ae5  cmp     [rcx], r13w
0x180003ae9  mov     [rsp+14F0h+var_14B8], rcx
0x180003aee  jnz     short loc_180003AF5
0x180003af0  mov     [rsp+14F0h+var_14B8], r13
0x180003af5  call    cs:__imp_GetCurrentThreadId
0x180003afb  mov     [rsp+14F0h+var_14B0], eax
0x180003aff  mov     [rsp+14F0h+var_1498], r14
0x180003b04  mov     [rsp+14F0h+var_1490], esi
0x180003b08  mov     [rsp+14F0h+var_148C], r12d
0x180003b0d  mov     [rsp+14F0h+var_14A8], r13
0x180003b12  mov     [rsp+14F0h+var_14A0], r13
0x180003b17  mov     [rbp+13F0h+var_1448], r15
0x180003b1b  mov     [rbp+13F0h+var_1440], rdi
0x180003b1f  mov     [rsp+14F0h+var_1488], r13
0x180003b24  xorps   xmm0, xmm0
0x180003b27  xor     eax, eax
0x180003b29  movups  [rbp+13F0h+var_1468], xmm0
0x180003b2d  mov     [rbp+13F0h+var_1458], rax
0x180003b31  xorps   xmm1, xmm1
0x180003b34  movups  [rsp+14F0h+var_1480], xmm1
0x180003b39  mov     [rbp+13F0h+var_1470], rax
0x180003b3d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003b44  test    rax, rax
0x180003b47  jz      short loc_180003B54
0x180003b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b4e  mov     [rbp+13F0h+var_1450], rax
0x180003b52  jmp     short loc_180003B58
0x180003b54  mov     [rbp+13F0h+var_1450], r13
0x180003b58  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003b5f  test    rax, rax
0x180003b62  jz      short loc_180003B6E
0x180003b64  lea     rcx, [rsp+14F0h+var_14D0]
0x180003b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b6e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003b75  test    rax, rax
0x180003b78  jz      short loc_180003B8E
0x180003b7a  mov     r8d, 400h
0x180003b80  lea     rdx, [rbp+13F0h+var_1430]
0x180003b84  lea     rcx, [rsp+14F0h+var_14D0]
0x180003b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b8e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003b95  test    rax, rax
0x180003b98  jz      short loc_180003BA4
0x180003b9a  lea     rcx, [rsp+14F0h+var_14D0]
0x180003b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ba4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003bab  test    rax, rax
0x180003bae  jz      short loc_180003BC1
0x180003bb0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003bb5  jnz     short loc_180003BC1
0x180003bb7  lea     rcx, [rsp+14F0h+var_14D0]
0x180003bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bc1  cmp     [rsp+14F0h+var_14C8], r13d
0x180003bc6  jl      short loc_180003BDA
0x180003bc8  mov     ecx, 8000FFFFh; this
0x180003bcd  mov     [rsp+14F0h+var_14C8], ecx
0x180003bd1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003bd6  mov     [rsp+14F0h+var_14C4], eax
0x180003bda  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180003be1  jnz     short loc_180003C02
0x180003be3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003bea  test    rax, rax
0x180003bed  jz      short loc_180003BF8
0x180003bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bf4  test    al, al
0x180003bf6  jmp     short loc_180003C00
0x180003bf8  call    cs:__imp_IsDebuggerPresent
0x180003bfe  test    eax, eax
0x180003c00  jz      short loc_180003C09
0x180003c02  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003c07  jz      short loc_180003C2F
0x180003c09  mov     rax, cs:g_pfnResultLoggingCallback
0x180003c10  test    rax, rax
0x180003c13  jz      short loc_180003C88
0x180003c15  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003c1c  jnz     short loc_180003C88
0x180003c1e  xor     r8d, r8d
0x180003c21  xor     edx, edx
0x180003c23  lea     rcx, [rsp+14F0h+var_14D0]
0x180003c28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c2d  jmp     short loc_180003C88
0x180003c2f  mov     ebx, 800h
0x180003c34  mov     rax, cs:g_pfnResultLoggingCallback
0x180003c3b  test    rax, rax
0x180003c3e  jz      short loc_180003C5D
0x180003c40  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003c47  jnz     short loc_180003C5D
0x180003c49  mov     r8d, ebx
0x180003c4c  lea     rdx, [rbp+13F0h+OutputString]
0x180003c53  lea     rcx, [rsp+14F0h+var_14D0]
0x180003c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c5d  cmp     [rbp+13F0h+OutputString], r13w
0x180003c65  jnz     short loc_180003C7B
0x180003c67  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003c6c  mov     rdx, rbx; unsigned __int16 *
0x180003c6f  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003c76  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003c7b  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003c82  call    cs:__imp_OutputDebugStringW
0x180003c88  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003c8d  jnz     short loc_180003C98
0x180003c8f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180003c96  jz      short loc_180003CAA
0x180003c98  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003c9f  test    rax, rax
0x180003ca2  jz      short loc_180003CAA
0x180003ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ca9  nop
0x180003caa  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003caf  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
