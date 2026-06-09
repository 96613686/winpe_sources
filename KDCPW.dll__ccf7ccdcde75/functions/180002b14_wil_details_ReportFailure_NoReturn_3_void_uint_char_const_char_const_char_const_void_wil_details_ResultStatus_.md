# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002b14`
- end: `0x180002d74`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800028b8`

## callees

- `0x180001f88`
- `0x180002b14`
- `0x180004f34`
- `0x1800056cc`
- `0x180006a30`
- `0x180008ce0`
- `0x18000ca90`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002bb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002bb5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002cb8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002cb8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002d42`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002d42`

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
0x180002b14  mov     [rsp-8+arg_18], rbx
0x180002b19  push    rbp
0x180002b1a  push    rsi
0x180002b1b  push    rdi
0x180002b1c  push    r12
0x180002b1e  push    r13
0x180002b20  push    r14
0x180002b22  push    r15
0x180002b24  lea     rbp, [rsp-13C0h]
0x180002b2c  mov     eax, 14C0h
0x180002b31  call    _alloca_probe
0x180002b36  sub     rsp, rax
0x180002b39  mov     rsi, [rbp+13F0h+arg_28]
0x180002b40  mov     r15, r8
0x180002b43  mov     r14d, edx
0x180002b46  mov     r12, rcx
0x180002b49  xor     edx, edx; Val
0x180002b4b  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002b50  mov     r8d, 98h; Size
0x180002b56  call    memset_0
0x180002b5b  mov     rbx, [rbp+13F0h+arg_30]
0x180002b62  xor     r13d, r13d
0x180002b65  mov     [rbp+13F0h+OutputString], r13w
0x180002b6d  mov     [rbp+13F0h+var_1430], r13b
0x180002b71  mov     ecx, [rbx]; this
0x180002b73  mov     eax, [rbx+4]
0x180002b76  mov     [rsp+14F0h+var_14C8], ecx
0x180002b7a  mov     [rsp+14F0h+var_14C4], eax
0x180002b7e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002b83  cmp     dword ptr [rbx+8], 1
0x180002b87  mov     edi, eax
0x180002b89  lea     eax, [r13+8]
0x180002b8d  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180002b95  mov     ecx, r13d
0x180002b98  cmovz   ecx, eax
0x180002b9b  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002b9f  lea     ecx, [rax-7]
0x180002ba2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002baa  inc     ecx
0x180002bac  mov     [rsp+14F0h+var_14B8], r13
0x180002bb1  mov     [rsp+14F0h+var_14C0], ecx
0x180002bb5  call    cs:__imp_GetCurrentThreadId
0x180002bbb  xorps   xmm0, xmm0
0x180002bbe  mov     [rsp+14F0h+var_1498], r15
0x180002bc3  mov     [rsp+14F0h+var_14B0], eax
0x180002bc7  xorps   xmm1, xmm1
0x180002bca  xor     eax, eax
0x180002bcc  mov     [rsp+14F0h+var_1490], r14d
0x180002bd1  mov     [rbp+13F0h+var_1458], rax
0x180002bd5  mov     [rbp+13F0h+var_1470], rax
0x180002bd9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002be0  mov     [rsp+14F0h+var_148C], edi
0x180002be4  mov     [rsp+14F0h+var_14A8], r13
0x180002be9  mov     [rsp+14F0h+var_14A0], r13
0x180002bee  mov     [rbp+13F0h+var_1448], rsi
0x180002bf2  mov     [rbp+13F0h+var_1440], r12
0x180002bf6  mov     [rsp+14F0h+var_1488], r13
0x180002bfb  movups  [rbp+13F0h+var_1468], xmm0
0x180002bff  movups  [rsp+14F0h+var_1480], xmm1
0x180002c04  test    rax, rax
0x180002c07  jz      short loc_180002C14
0x180002c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c0e  mov     [rbp+13F0h+var_1450], rax
0x180002c12  jmp     short loc_180002C18
0x180002c14  mov     [rbp+13F0h+var_1450], r13
0x180002c18  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002c1f  test    rax, rax
0x180002c22  jz      short loc_180002C2E
0x180002c24  lea     rcx, [rsp+14F0h+var_14D0]
0x180002c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c2e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002c35  test    rax, rax
0x180002c38  jz      short loc_180002C4E
0x180002c3a  mov     r8d, 400h
0x180002c40  lea     rdx, [rbp+13F0h+var_1430]
0x180002c44  lea     rcx, [rsp+14F0h+var_14D0]
0x180002c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c4e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002c55  test    rax, rax
0x180002c58  jz      short loc_180002C64
0x180002c5a  lea     rcx, [rsp+14F0h+var_14D0]
0x180002c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c64  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002c6b  test    rax, rax
0x180002c6e  jz      short loc_180002C81
0x180002c70  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002c75  jnz     short loc_180002C81
0x180002c77  lea     rcx, [rsp+14F0h+var_14D0]
0x180002c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c81  cmp     [rsp+14F0h+var_14C8], r13d
0x180002c86  jl      short loc_180002C9A
0x180002c88  mov     ecx, 8000FFFFh; this
0x180002c8d  mov     [rsp+14F0h+var_14C8], ecx
0x180002c91  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002c96  mov     [rsp+14F0h+var_14C4], eax
0x180002c9a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180002ca1  jnz     short loc_180002CC2
0x180002ca3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002caa  test    rax, rax
0x180002cad  jz      short loc_180002CB8
0x180002caf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cb4  test    al, al
0x180002cb6  jmp     short loc_180002CC0
0x180002cb8  call    cs:__imp_IsDebuggerPresent
0x180002cbe  test    eax, eax
0x180002cc0  jz      short loc_180002CC9
0x180002cc2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002cc7  jz      short loc_180002CEF
0x180002cc9  mov     rax, cs:g_pfnResultLoggingCallback
0x180002cd0  test    rax, rax
0x180002cd3  jz      short loc_180002D48
0x180002cd5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002cdc  jnz     short loc_180002D48
0x180002cde  xor     r8d, r8d
0x180002ce1  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ce6  xor     edx, edx
0x180002ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ced  jmp     short loc_180002D48
0x180002cef  mov     rax, cs:g_pfnResultLoggingCallback
0x180002cf6  mov     ebx, 800h
0x180002cfb  test    rax, rax
0x180002cfe  jz      short loc_180002D1D
0x180002d00  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002d07  jnz     short loc_180002D1D
0x180002d09  mov     r8d, ebx
0x180002d0c  lea     rdx, [rbp+13F0h+OutputString]
0x180002d13  lea     rcx, [rsp+14F0h+var_14D0]
0x180002d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d1d  cmp     [rbp+13F0h+OutputString], r13w
0x180002d25  jnz     short loc_180002D3B
0x180002d27  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002d2c  mov     rdx, rbx; unsigned __int16 *
0x180002d2f  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002d36  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002d3b  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002d42  call    cs:__imp_OutputDebugStringW
0x180002d48  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002d4d  jnz     short loc_180002D58
0x180002d4f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180002d56  jz      short loc_180002D69
0x180002d58  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002d5f  test    rax, rax
0x180002d62  jz      short loc_180002D69
0x180002d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d69  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002d6e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
