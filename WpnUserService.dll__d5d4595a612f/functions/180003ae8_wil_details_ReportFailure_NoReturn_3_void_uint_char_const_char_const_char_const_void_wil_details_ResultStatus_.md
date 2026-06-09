# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180003ae8`
- end: `0x180003d61`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003858`

## callees

- `0x18000354c`
- `0x180003ae8`
- `0x180004fb4`
- `0x180005800`
- `0x180005f60`
- `0x180007010`
- `0x180010ba0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003ba1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003ba1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003d2e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003d2e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003ca4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003ca4`

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
0x180003ae8  mov     [rsp-8+arg_18], rbx
0x180003aed  push    rbp
0x180003aee  push    rsi
0x180003aef  push    rdi
0x180003af0  push    r12
0x180003af2  push    r13
0x180003af4  push    r14
0x180003af6  push    r15
0x180003af8  lea     rbp, [rsp-13C0h]
0x180003b00  mov     eax, 14C0h
0x180003b05  call    _alloca_probe
0x180003b0a  sub     rsp, rax
0x180003b0d  mov     r14, r8
0x180003b10  mov     esi, edx
0x180003b12  mov     rdi, rcx
0x180003b15  mov     r15, [rbp+13F0h+arg_28]
0x180003b1c  xor     edx, edx; Val
0x180003b1e  mov     r8d, 98h; Size
0x180003b24  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003b29  call    memset_0
0x180003b2e  nop
0x180003b2f  xor     r13d, r13d
0x180003b32  mov     [rbp+13F0h+OutputString], r13w
0x180003b3a  mov     [rbp+13F0h+var_1430], r13b
0x180003b3e  mov     rbx, [rbp+13F0h+arg_30]
0x180003b45  mov     ecx, [rbx]; this
0x180003b47  mov     [rsp+14F0h+var_14C8], ecx
0x180003b4b  mov     eax, [rbx+4]
0x180003b4e  mov     [rsp+14F0h+var_14C4], eax
0x180003b52  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003b57  mov     r12d, eax
0x180003b5a  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180003b62  mov     ecx, r13d
0x180003b65  lea     eax, [r13+8]
0x180003b69  cmp     dword ptr [rbx+8], 1
0x180003b6d  cmovz   ecx, eax
0x180003b70  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003b74  lea     ecx, [rax-7]
0x180003b77  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003b7f  inc     ecx
0x180003b81  mov     [rsp+14F0h+var_14C0], ecx
0x180003b85  mov     rcx, [rbp+13F0h+arg_38]
0x180003b8c  test    rcx, rcx
0x180003b8f  jz      short loc_180003B9C
0x180003b91  cmp     [rcx], r13w
0x180003b95  mov     [rsp+14F0h+var_14B8], rcx
0x180003b9a  jnz     short loc_180003BA1
0x180003b9c  mov     [rsp+14F0h+var_14B8], r13
0x180003ba1  call    cs:__imp_GetCurrentThreadId
0x180003ba7  mov     [rsp+14F0h+var_14B0], eax
0x180003bab  mov     [rsp+14F0h+var_1498], r14
0x180003bb0  mov     [rsp+14F0h+var_1490], esi
0x180003bb4  mov     [rsp+14F0h+var_148C], r12d
0x180003bb9  mov     [rsp+14F0h+var_14A8], r13
0x180003bbe  mov     [rsp+14F0h+var_14A0], r13
0x180003bc3  mov     [rbp+13F0h+var_1448], r15
0x180003bc7  mov     [rbp+13F0h+var_1440], rdi
0x180003bcb  mov     [rsp+14F0h+var_1488], r13
0x180003bd0  xorps   xmm0, xmm0
0x180003bd3  xor     eax, eax
0x180003bd5  movups  [rbp+13F0h+var_1468], xmm0
0x180003bd9  mov     [rbp+13F0h+var_1458], rax
0x180003bdd  xorps   xmm1, xmm1
0x180003be0  movups  [rsp+14F0h+var_1480], xmm1
0x180003be5  mov     [rbp+13F0h+var_1470], rax
0x180003be9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003bf0  test    rax, rax
0x180003bf3  jz      short loc_180003C00
0x180003bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bfa  mov     [rbp+13F0h+var_1450], rax
0x180003bfe  jmp     short loc_180003C04
0x180003c00  mov     [rbp+13F0h+var_1450], r13
0x180003c04  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003c0b  test    rax, rax
0x180003c0e  jz      short loc_180003C1A
0x180003c10  lea     rcx, [rsp+14F0h+var_14D0]
0x180003c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c1a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003c21  test    rax, rax
0x180003c24  jz      short loc_180003C3A
0x180003c26  mov     r8d, 400h
0x180003c2c  lea     rdx, [rbp+13F0h+var_1430]
0x180003c30  lea     rcx, [rsp+14F0h+var_14D0]
0x180003c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c3a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003c41  test    rax, rax
0x180003c44  jz      short loc_180003C50
0x180003c46  lea     rcx, [rsp+14F0h+var_14D0]
0x180003c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c50  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003c57  test    rax, rax
0x180003c5a  jz      short loc_180003C6D
0x180003c5c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003c61  jnz     short loc_180003C6D
0x180003c63  lea     rcx, [rsp+14F0h+var_14D0]
0x180003c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c6d  cmp     [rsp+14F0h+var_14C8], r13d
0x180003c72  jl      short loc_180003C86
0x180003c74  mov     ecx, 8000FFFFh; this
0x180003c79  mov     [rsp+14F0h+var_14C8], ecx
0x180003c7d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003c82  mov     [rsp+14F0h+var_14C4], eax
0x180003c86  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180003c8d  jnz     short loc_180003CAE
0x180003c8f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003c96  test    rax, rax
0x180003c99  jz      short loc_180003CA4
0x180003c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ca0  test    al, al
0x180003ca2  jmp     short loc_180003CAC
0x180003ca4  call    cs:__imp_IsDebuggerPresent
0x180003caa  test    eax, eax
0x180003cac  jz      short loc_180003CB5
0x180003cae  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003cb3  jz      short loc_180003CDB
0x180003cb5  mov     rax, cs:g_pfnResultLoggingCallback
0x180003cbc  test    rax, rax
0x180003cbf  jz      short loc_180003D34
0x180003cc1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003cc8  jnz     short loc_180003D34
0x180003cca  xor     r8d, r8d
0x180003ccd  xor     edx, edx
0x180003ccf  lea     rcx, [rsp+14F0h+var_14D0]
0x180003cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cd9  jmp     short loc_180003D34
0x180003cdb  mov     ebx, 800h
0x180003ce0  mov     rax, cs:g_pfnResultLoggingCallback
0x180003ce7  test    rax, rax
0x180003cea  jz      short loc_180003D09
0x180003cec  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003cf3  jnz     short loc_180003D09
0x180003cf5  mov     r8d, ebx
0x180003cf8  lea     rdx, [rbp+13F0h+OutputString]
0x180003cff  lea     rcx, [rsp+14F0h+var_14D0]
0x180003d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d09  cmp     [rbp+13F0h+OutputString], r13w
0x180003d11  jnz     short loc_180003D27
0x180003d13  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003d18  mov     rdx, rbx; unsigned __int16 *
0x180003d1b  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003d22  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003d27  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003d2e  call    cs:__imp_OutputDebugStringW
0x180003d34  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003d39  jnz     short loc_180003D44
0x180003d3b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180003d42  jz      short loc_180003D56
0x180003d44  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003d4b  test    rax, rax
0x180003d4e  jz      short loc_180003D56
0x180003d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d55  nop
0x180003d56  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003d5b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
