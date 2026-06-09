# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002970`
- end: `0x180002bd0`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002714`

## callees

- `0x1800024d4`
- `0x180002970`
- `0x1800048c4`
- `0x18000505c`
- `0x180005c50`
- `0x180007960`
- `0x1800265e0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002a11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002a11`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002b14`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002b14`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002b9e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002b9e`

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
0x180002970  mov     [rsp-8+arg_18], rbx
0x180002975  push    rbp
0x180002976  push    rsi
0x180002977  push    rdi
0x180002978  push    r12
0x18000297a  push    r13
0x18000297c  push    r14
0x18000297e  push    r15
0x180002980  lea     rbp, [rsp-13C0h]
0x180002988  mov     eax, 14C0h
0x18000298d  call    _alloca_probe
0x180002992  sub     rsp, rax
0x180002995  mov     rsi, [rbp+13F0h+arg_28]
0x18000299c  mov     r15, r8
0x18000299f  mov     r14d, edx
0x1800029a2  mov     r12, rcx
0x1800029a5  xor     edx, edx; Val
0x1800029a7  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800029ac  mov     r8d, 98h; Size
0x1800029b2  call    memset_0
0x1800029b7  mov     rbx, [rbp+13F0h+arg_30]
0x1800029be  xor     r13d, r13d
0x1800029c1  mov     [rbp+13F0h+OutputString], r13w
0x1800029c9  mov     [rbp+13F0h+var_1430], r13b
0x1800029cd  mov     ecx, [rbx]; this
0x1800029cf  mov     eax, [rbx+4]
0x1800029d2  mov     [rsp+14F0h+var_14C8], ecx
0x1800029d6  mov     [rsp+14F0h+var_14C4], eax
0x1800029da  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800029df  cmp     dword ptr [rbx+8], 1
0x1800029e3  mov     edi, eax
0x1800029e5  lea     eax, [r13+8]
0x1800029e9  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800029f1  mov     ecx, r13d
0x1800029f4  cmovz   ecx, eax
0x1800029f7  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800029fb  lea     ecx, [rax-7]
0x1800029fe  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002a06  inc     ecx
0x180002a08  mov     [rsp+14F0h+var_14B8], r13
0x180002a0d  mov     [rsp+14F0h+var_14C0], ecx
0x180002a11  call    cs:__imp_GetCurrentThreadId
0x180002a17  xorps   xmm0, xmm0
0x180002a1a  mov     [rsp+14F0h+var_1498], r15
0x180002a1f  mov     [rsp+14F0h+var_14B0], eax
0x180002a23  xorps   xmm1, xmm1
0x180002a26  xor     eax, eax
0x180002a28  mov     [rsp+14F0h+var_1490], r14d
0x180002a2d  mov     [rbp+13F0h+var_1458], rax
0x180002a31  mov     [rbp+13F0h+var_1470], rax
0x180002a35  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002a3c  mov     [rsp+14F0h+var_148C], edi
0x180002a40  mov     [rsp+14F0h+var_14A8], r13
0x180002a45  mov     [rsp+14F0h+var_14A0], r13
0x180002a4a  mov     [rbp+13F0h+var_1448], rsi
0x180002a4e  mov     [rbp+13F0h+var_1440], r12
0x180002a52  mov     [rsp+14F0h+var_1488], r13
0x180002a57  movups  [rbp+13F0h+var_1468], xmm0
0x180002a5b  movups  [rsp+14F0h+var_1480], xmm1
0x180002a60  test    rax, rax
0x180002a63  jz      short loc_180002A70
0x180002a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a6a  mov     [rbp+13F0h+var_1450], rax
0x180002a6e  jmp     short loc_180002A74
0x180002a70  mov     [rbp+13F0h+var_1450], r13
0x180002a74  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002a7b  test    rax, rax
0x180002a7e  jz      short loc_180002A8A
0x180002a80  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a8a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002a91  test    rax, rax
0x180002a94  jz      short loc_180002AAA
0x180002a96  mov     r8d, 400h
0x180002a9c  lea     rdx, [rbp+13F0h+var_1430]
0x180002aa0  lea     rcx, [rsp+14F0h+var_14D0]
0x180002aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aaa  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002ab1  test    rax, rax
0x180002ab4  jz      short loc_180002AC0
0x180002ab6  lea     rcx, [rsp+14F0h+var_14D0]
0x180002abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ac0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002ac7  test    rax, rax
0x180002aca  jz      short loc_180002ADD
0x180002acc  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002ad1  jnz     short loc_180002ADD
0x180002ad3  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002add  cmp     [rsp+14F0h+var_14C8], r13d
0x180002ae2  jl      short loc_180002AF6
0x180002ae4  mov     ecx, 8000FFFFh; this
0x180002ae9  mov     [rsp+14F0h+var_14C8], ecx
0x180002aed  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002af2  mov     [rsp+14F0h+var_14C4], eax
0x180002af6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180002afd  jnz     short loc_180002B1E
0x180002aff  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002b06  test    rax, rax
0x180002b09  jz      short loc_180002B14
0x180002b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b10  test    al, al
0x180002b12  jmp     short loc_180002B1C
0x180002b14  call    cs:__imp_IsDebuggerPresent
0x180002b1a  test    eax, eax
0x180002b1c  jz      short loc_180002B25
0x180002b1e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002b23  jz      short loc_180002B4B
0x180002b25  mov     rax, cs:g_pfnResultLoggingCallback
0x180002b2c  test    rax, rax
0x180002b2f  jz      short loc_180002BA4
0x180002b31  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002b38  jnz     short loc_180002BA4
0x180002b3a  xor     r8d, r8d
0x180002b3d  lea     rcx, [rsp+14F0h+var_14D0]
0x180002b42  xor     edx, edx
0x180002b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b49  jmp     short loc_180002BA4
0x180002b4b  mov     rax, cs:g_pfnResultLoggingCallback
0x180002b52  mov     ebx, 800h
0x180002b57  test    rax, rax
0x180002b5a  jz      short loc_180002B79
0x180002b5c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002b63  jnz     short loc_180002B79
0x180002b65  mov     r8d, ebx
0x180002b68  lea     rdx, [rbp+13F0h+OutputString]
0x180002b6f  lea     rcx, [rsp+14F0h+var_14D0]
0x180002b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b79  cmp     [rbp+13F0h+OutputString], r13w
0x180002b81  jnz     short loc_180002B97
0x180002b83  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002b88  mov     rdx, rbx; unsigned __int16 *
0x180002b8b  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002b92  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002b97  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002b9e  call    cs:__imp_OutputDebugStringW
0x180002ba4  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002ba9  jnz     short loc_180002BB4
0x180002bab  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180002bb2  jz      short loc_180002BC5
0x180002bb4  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002bbb  test    rax, rax
0x180002bbe  jz      short loc_180002BC5
0x180002bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bc5  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002bca  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
