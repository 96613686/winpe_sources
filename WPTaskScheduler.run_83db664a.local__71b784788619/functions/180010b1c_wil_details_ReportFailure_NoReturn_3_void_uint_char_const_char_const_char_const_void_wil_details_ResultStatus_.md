# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180010b1c`
- end: `0x180010d7e`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800108e8`

## callees

- `0x180010b1c`
- `0x180012644`
- `0x180012eb0`
- `0x180013e20`
- `0x180016040`
- `0x180020c02`
- `0x180020cf0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010bbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010bbe`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180010cc1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180010cc1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180010d4b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180010d4b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // edx
  int v11; // edi
  int v12; // ecx
  const struct wil::FailureInfo *v13; // rdx
  __int64 v14; // rcx
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v19, v10);
  v17 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v18 = v12;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v11;
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
  {
    v19 = -2147418113;
    v20 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v13);
  }
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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( (v18 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v14);
  }
  wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180010b1c  mov     [rsp-8+arg_18], rbx
0x180010b21  push    rbp
0x180010b22  push    rsi
0x180010b23  push    rdi
0x180010b24  push    r12
0x180010b26  push    r13
0x180010b28  push    r14
0x180010b2a  push    r15
0x180010b2c  lea     rbp, [rsp-13C0h]
0x180010b34  mov     eax, 14C0h
0x180010b39  call    _alloca_probe
0x180010b3e  sub     rsp, rax
0x180010b41  mov     r15, r8
0x180010b44  mov     r14d, edx
0x180010b47  mov     r12, rcx
0x180010b4a  mov     rsi, [rbp+13F0h+arg_28]
0x180010b51  xor     edx, edx; Val
0x180010b53  mov     r8d, 98h; Size
0x180010b59  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180010b5e  call    memset_0
0x180010b63  nop
0x180010b64  xor     r13d, r13d
0x180010b67  mov     [rbp+13F0h+OutputString], r13w
0x180010b6f  mov     [rbp+13F0h+var_1430], r13b
0x180010b73  mov     rbx, [rbp+13F0h+arg_30]
0x180010b7a  mov     ecx, [rbx]; this
0x180010b7c  mov     [rsp+14F0h+var_14C8], ecx
0x180010b80  mov     eax, [rbx+4]
0x180010b83  mov     [rsp+14F0h+var_14C4], eax
0x180010b87  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180010b8c  mov     edi, eax
0x180010b8e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180010b96  mov     ecx, r13d
0x180010b99  lea     eax, [r13+8]
0x180010b9d  cmp     dword ptr [rbx+8], 1
0x180010ba1  cmovz   ecx, eax
0x180010ba4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180010ba8  lea     ecx, [rax-7]
0x180010bab  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180010bb3  inc     ecx
0x180010bb5  mov     [rsp+14F0h+var_14C0], ecx
0x180010bb9  mov     [rsp+14F0h+var_14B8], r13
0x180010bbe  call    cs:__imp_GetCurrentThreadId
0x180010bc4  mov     [rsp+14F0h+var_14B0], eax
0x180010bc8  mov     [rsp+14F0h+var_1498], r15
0x180010bcd  mov     [rsp+14F0h+var_1490], r14d
0x180010bd2  mov     [rsp+14F0h+var_148C], edi
0x180010bd6  mov     [rsp+14F0h+var_14A8], r13
0x180010bdb  mov     [rsp+14F0h+var_14A0], r13
0x180010be0  mov     [rbp+13F0h+var_1448], rsi
0x180010be4  mov     [rbp+13F0h+var_1440], r12
0x180010be8  mov     [rsp+14F0h+var_1488], r13
0x180010bed  xorps   xmm0, xmm0
0x180010bf0  xor     eax, eax
0x180010bf2  movups  [rbp+13F0h+var_1468], xmm0
0x180010bf6  mov     [rbp+13F0h+var_1458], rax
0x180010bfa  xorps   xmm1, xmm1
0x180010bfd  movups  [rsp+14F0h+var_1480], xmm1
0x180010c02  mov     [rbp+13F0h+var_1470], rax
0x180010c06  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180010c0d  test    rax, rax
0x180010c10  jz      short loc_180010C1D
0x180010c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c17  mov     [rbp+13F0h+var_1450], rax
0x180010c1b  jmp     short loc_180010C21
0x180010c1d  mov     [rbp+13F0h+var_1450], r13
0x180010c21  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180010c28  test    rax, rax
0x180010c2b  jz      short loc_180010C37
0x180010c2d  lea     rcx, [rsp+14F0h+var_14D0]
0x180010c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c37  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180010c3e  test    rax, rax
0x180010c41  jz      short loc_180010C57
0x180010c43  mov     r8d, 400h
0x180010c49  lea     rdx, [rbp+13F0h+var_1430]
0x180010c4d  lea     rcx, [rsp+14F0h+var_14D0]
0x180010c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c57  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180010c5e  test    rax, rax
0x180010c61  jz      short loc_180010C6D
0x180010c63  lea     rcx, [rsp+14F0h+var_14D0]
0x180010c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c6d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180010c74  test    rax, rax
0x180010c77  jz      short loc_180010C8A
0x180010c79  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180010c7e  jnz     short loc_180010C8A
0x180010c80  lea     rcx, [rsp+14F0h+var_14D0]
0x180010c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c8a  cmp     [rsp+14F0h+var_14C8], r13d
0x180010c8f  jl      short loc_180010CA3
0x180010c91  mov     ecx, 8000FFFFh; this
0x180010c96  mov     [rsp+14F0h+var_14C8], ecx
0x180010c9a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180010c9f  mov     [rsp+14F0h+var_14C4], eax
0x180010ca3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180010caa  jnz     short loc_180010CCB
0x180010cac  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180010cb3  test    rax, rax
0x180010cb6  jz      short loc_180010CC1
0x180010cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cbd  test    al, al
0x180010cbf  jmp     short loc_180010CC9
0x180010cc1  call    cs:__imp_IsDebuggerPresent
0x180010cc7  test    eax, eax
0x180010cc9  jz      short loc_180010CD2
0x180010ccb  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180010cd0  jz      short loc_180010CF8
0x180010cd2  mov     rax, cs:g_pfnResultLoggingCallback
0x180010cd9  test    rax, rax
0x180010cdc  jz      short loc_180010D51
0x180010cde  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180010ce5  jnz     short loc_180010D51
0x180010ce7  xor     r8d, r8d
0x180010cea  xor     edx, edx
0x180010cec  lea     rcx, [rsp+14F0h+var_14D0]
0x180010cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cf6  jmp     short loc_180010D51
0x180010cf8  mov     ebx, 800h
0x180010cfd  mov     rax, cs:g_pfnResultLoggingCallback
0x180010d04  test    rax, rax
0x180010d07  jz      short loc_180010D26
0x180010d09  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180010d10  jnz     short loc_180010D26
0x180010d12  mov     r8d, ebx
0x180010d15  lea     rdx, [rbp+13F0h+OutputString]
0x180010d1c  lea     rcx, [rsp+14F0h+var_14D0]
0x180010d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d26  cmp     [rbp+13F0h+OutputString], r13w
0x180010d2e  jnz     short loc_180010D44
0x180010d30  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180010d35  mov     rdx, rbx; unsigned __int16 *
0x180010d38  lea     rcx, [rbp+13F0h+OutputString]; this
0x180010d3f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180010d44  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180010d4b  call    cs:__imp_OutputDebugStringW
0x180010d51  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180010d56  jnz     short loc_180010D61
0x180010d58  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180010d5f  jz      short loc_180010D73
0x180010d61  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180010d68  test    rax, rax
0x180010d6b  jz      short loc_180010D73
0x180010d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d72  nop
0x180010d73  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180010d78  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
