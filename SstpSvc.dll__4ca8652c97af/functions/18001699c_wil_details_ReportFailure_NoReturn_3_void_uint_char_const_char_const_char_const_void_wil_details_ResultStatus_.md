# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18001699c`
- end: `0x180016bfc`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180016768`

## callees

- `0x18001699c`
- `0x180018224`
- `0x180018a90`
- `0x1800199e0`
- `0x18001b030`
- `0x18001bcba`
- `0x18001bd80`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016a3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016a3d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180016bca`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180016bca`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180016b40`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180016b40`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // eax
  int v11; // edx
  int v12; // eax
  int v13; // edi
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  __int64 v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v22, v11);
  v19 = a7[2] == 1;
  v13 = v12;
  v20 = 3;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
  {
    v22 = -2147418113;
    v23 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v16);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( (v21 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v17);
  }
  wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x18001699c  mov     [rsp-8+arg_18], rbx
0x1800169a1  push    rbp
0x1800169a2  push    rsi
0x1800169a3  push    rdi
0x1800169a4  push    r12
0x1800169a6  push    r13
0x1800169a8  push    r14
0x1800169aa  push    r15
0x1800169ac  lea     rbp, [rsp-13C0h]
0x1800169b4  mov     eax, 14C0h
0x1800169b9  call    _alloca_probe
0x1800169be  sub     rsp, rax
0x1800169c1  mov     rsi, [rbp+13F0h+arg_28]
0x1800169c8  mov     r15, r8
0x1800169cb  mov     r14d, edx
0x1800169ce  mov     r12, rcx
0x1800169d1  xor     edx, edx; Val
0x1800169d3  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800169d8  mov     r8d, 98h; Size
0x1800169de  call    memset_0
0x1800169e3  mov     rbx, [rbp+13F0h+arg_30]
0x1800169ea  xor     r13d, r13d
0x1800169ed  mov     [rbp+13F0h+OutputString], r13w
0x1800169f5  mov     [rbp+13F0h+var_1430], r13b
0x1800169f9  mov     ecx, [rbx]; this
0x1800169fb  mov     eax, [rbx+4]
0x1800169fe  mov     [rsp+14F0h+var_14C8], ecx
0x180016a02  mov     [rsp+14F0h+var_14C4], eax
0x180016a06  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180016a0b  cmp     dword ptr [rbx+8], 1
0x180016a0f  mov     edi, eax
0x180016a11  lea     eax, [r13+8]
0x180016a15  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180016a1d  mov     ecx, r13d
0x180016a20  cmovz   ecx, eax
0x180016a23  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180016a27  lea     ecx, [rax-7]
0x180016a2a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180016a32  inc     ecx
0x180016a34  mov     [rsp+14F0h+var_14B8], r13
0x180016a39  mov     [rsp+14F0h+var_14C0], ecx
0x180016a3d  call    cs:__imp_GetCurrentThreadId
0x180016a43  xorps   xmm0, xmm0
0x180016a46  mov     [rsp+14F0h+var_1498], r15
0x180016a4b  mov     [rsp+14F0h+var_14B0], eax
0x180016a4f  xorps   xmm1, xmm1
0x180016a52  xor     eax, eax
0x180016a54  mov     [rsp+14F0h+var_1490], r14d
0x180016a59  mov     [rbp+13F0h+var_1458], rax
0x180016a5d  mov     [rbp+13F0h+var_1470], rax
0x180016a61  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180016a68  mov     [rsp+14F0h+var_148C], edi
0x180016a6c  mov     [rsp+14F0h+var_14A8], r13
0x180016a71  mov     [rsp+14F0h+var_14A0], r13
0x180016a76  mov     [rbp+13F0h+var_1448], rsi
0x180016a7a  mov     [rbp+13F0h+var_1440], r12
0x180016a7e  mov     [rsp+14F0h+var_1488], r13
0x180016a83  movups  [rbp+13F0h+var_1468], xmm0
0x180016a87  movups  [rsp+14F0h+var_1480], xmm1
0x180016a8c  test    rax, rax
0x180016a8f  jz      short loc_180016A9C
0x180016a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a96  mov     [rbp+13F0h+var_1450], rax
0x180016a9a  jmp     short loc_180016AA0
0x180016a9c  mov     [rbp+13F0h+var_1450], r13
0x180016aa0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180016aa7  test    rax, rax
0x180016aaa  jz      short loc_180016AB6
0x180016aac  lea     rcx, [rsp+14F0h+var_14D0]
0x180016ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ab6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180016abd  test    rax, rax
0x180016ac0  jz      short loc_180016AD6
0x180016ac2  mov     r8d, 400h
0x180016ac8  lea     rdx, [rbp+13F0h+var_1430]
0x180016acc  lea     rcx, [rsp+14F0h+var_14D0]
0x180016ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ad6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180016add  test    rax, rax
0x180016ae0  jz      short loc_180016AEC
0x180016ae2  lea     rcx, [rsp+14F0h+var_14D0]
0x180016ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016aec  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180016af3  test    rax, rax
0x180016af6  jz      short loc_180016B09
0x180016af8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180016afd  jnz     short loc_180016B09
0x180016aff  lea     rcx, [rsp+14F0h+var_14D0]
0x180016b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b09  cmp     [rsp+14F0h+var_14C8], r13d
0x180016b0e  jl      short loc_180016B22
0x180016b10  mov     ecx, 8000FFFFh; this
0x180016b15  mov     [rsp+14F0h+var_14C8], ecx
0x180016b19  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180016b1e  mov     [rsp+14F0h+var_14C4], eax
0x180016b22  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180016b29  jnz     short loc_180016B4A
0x180016b2b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180016b32  test    rax, rax
0x180016b35  jz      short loc_180016B40
0x180016b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b3c  test    al, al
0x180016b3e  jmp     short loc_180016B48
0x180016b40  call    cs:__imp_IsDebuggerPresent
0x180016b46  test    eax, eax
0x180016b48  jz      short loc_180016B51
0x180016b4a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180016b4f  jz      short loc_180016B77
0x180016b51  mov     rax, cs:g_pfnResultLoggingCallback
0x180016b58  test    rax, rax
0x180016b5b  jz      short loc_180016BD0
0x180016b5d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180016b64  jnz     short loc_180016BD0
0x180016b66  xor     r8d, r8d
0x180016b69  lea     rcx, [rsp+14F0h+var_14D0]
0x180016b6e  xor     edx, edx
0x180016b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b75  jmp     short loc_180016BD0
0x180016b77  mov     rax, cs:g_pfnResultLoggingCallback
0x180016b7e  mov     ebx, 800h
0x180016b83  test    rax, rax
0x180016b86  jz      short loc_180016BA5
0x180016b88  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180016b8f  jnz     short loc_180016BA5
0x180016b91  mov     r8d, ebx
0x180016b94  lea     rdx, [rbp+13F0h+OutputString]
0x180016b9b  lea     rcx, [rsp+14F0h+var_14D0]
0x180016ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ba5  cmp     [rbp+13F0h+OutputString], r13w
0x180016bad  jnz     short loc_180016BC3
0x180016baf  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180016bb4  mov     rdx, rbx; unsigned __int16 *
0x180016bb7  lea     rcx, [rbp+13F0h+OutputString]; this
0x180016bbe  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180016bc3  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180016bca  call    cs:__imp_OutputDebugStringW
0x180016bd0  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180016bd5  jnz     short loc_180016BE0
0x180016bd7  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180016bde  jz      short loc_180016BF1
0x180016be0  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180016be7  test    rax, rax
0x180016bea  jz      short loc_180016BF1
0x180016bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016bf1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180016bf6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
