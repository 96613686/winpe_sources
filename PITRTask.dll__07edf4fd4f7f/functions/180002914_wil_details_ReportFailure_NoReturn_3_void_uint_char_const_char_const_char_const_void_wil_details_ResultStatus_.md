# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002914`
- end: `0x180002b76`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800026b8`

## callees

- `0x180002914`
- `0x180006054`
- `0x18000680c`
- `0x1800077b0`
- `0x18000a410`
- `0x180010792`
- `0x180010880`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800029b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800029b6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002ab9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002ab9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002b43`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002b43`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
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
0x180002914  mov     [rsp-8+arg_18], rbx
0x180002919  push    rbp
0x18000291a  push    rsi
0x18000291b  push    rdi
0x18000291c  push    r12
0x18000291e  push    r13
0x180002920  push    r14
0x180002922  push    r15
0x180002924  lea     rbp, [rsp-13C0h]
0x18000292c  mov     eax, 14C0h
0x180002931  call    _alloca_probe
0x180002936  sub     rsp, rax
0x180002939  mov     r15, r8
0x18000293c  mov     r14d, edx
0x18000293f  mov     r12, rcx
0x180002942  mov     rsi, [rbp+13F0h+arg_28]
0x180002949  xor     edx, edx; Val
0x18000294b  mov     r8d, 98h; Size
0x180002951  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002956  call    memset_0
0x18000295b  nop
0x18000295c  xor     r13d, r13d
0x18000295f  mov     [rbp+13F0h+OutputString], r13w
0x180002967  mov     [rbp+13F0h+var_1430], r13b
0x18000296b  mov     rbx, [rbp+13F0h+arg_30]
0x180002972  mov     ecx, [rbx]; this
0x180002974  mov     [rsp+14F0h+var_14C8], ecx
0x180002978  mov     eax, [rbx+4]
0x18000297b  mov     [rsp+14F0h+var_14C4], eax
0x18000297f  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002984  mov     edi, eax
0x180002986  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000298e  mov     ecx, r13d
0x180002991  lea     eax, [r13+8]
0x180002995  cmp     dword ptr [rbx+8], 1
0x180002999  cmovz   ecx, eax
0x18000299c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800029a0  lea     ecx, [rax-7]
0x1800029a3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800029ab  inc     ecx
0x1800029ad  mov     [rsp+14F0h+var_14C0], ecx
0x1800029b1  mov     [rsp+14F0h+var_14B8], r13
0x1800029b6  call    cs:__imp_GetCurrentThreadId
0x1800029bc  mov     [rsp+14F0h+var_14B0], eax
0x1800029c0  mov     [rsp+14F0h+var_1498], r15
0x1800029c5  mov     [rsp+14F0h+var_1490], r14d
0x1800029ca  mov     [rsp+14F0h+var_148C], edi
0x1800029ce  mov     [rsp+14F0h+var_14A8], r13
0x1800029d3  mov     [rsp+14F0h+var_14A0], r13
0x1800029d8  mov     [rbp+13F0h+var_1448], rsi
0x1800029dc  mov     [rbp+13F0h+var_1440], r12
0x1800029e0  mov     [rsp+14F0h+var_1488], r13
0x1800029e5  xorps   xmm0, xmm0
0x1800029e8  xor     eax, eax
0x1800029ea  movups  [rbp+13F0h+var_1468], xmm0
0x1800029ee  mov     [rbp+13F0h+var_1458], rax
0x1800029f2  xorps   xmm1, xmm1
0x1800029f5  movups  [rsp+14F0h+var_1480], xmm1
0x1800029fa  mov     [rbp+13F0h+var_1470], rax
0x1800029fe  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002a05  test    rax, rax
0x180002a08  jz      short loc_180002A15
0x180002a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a0f  mov     [rbp+13F0h+var_1450], rax
0x180002a13  jmp     short loc_180002A19
0x180002a15  mov     [rbp+13F0h+var_1450], r13
0x180002a19  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002a20  test    rax, rax
0x180002a23  jz      short loc_180002A2F
0x180002a25  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a2f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002a36  test    rax, rax
0x180002a39  jz      short loc_180002A4F
0x180002a3b  mov     r8d, 400h
0x180002a41  lea     rdx, [rbp+13F0h+var_1430]
0x180002a45  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a4f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002a56  test    rax, rax
0x180002a59  jz      short loc_180002A65
0x180002a5b  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a65  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002a6c  test    rax, rax
0x180002a6f  jz      short loc_180002A82
0x180002a71  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002a76  jnz     short loc_180002A82
0x180002a78  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a82  cmp     [rsp+14F0h+var_14C8], r13d
0x180002a87  jl      short loc_180002A9B
0x180002a89  mov     ecx, 8000FFFFh; this
0x180002a8e  mov     [rsp+14F0h+var_14C8], ecx
0x180002a92  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002a97  mov     [rsp+14F0h+var_14C4], eax
0x180002a9b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180002aa2  jnz     short loc_180002AC3
0x180002aa4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002aab  test    rax, rax
0x180002aae  jz      short loc_180002AB9
0x180002ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ab5  test    al, al
0x180002ab7  jmp     short loc_180002AC1
0x180002ab9  call    cs:__imp_IsDebuggerPresent
0x180002abf  test    eax, eax
0x180002ac1  jz      short loc_180002ACA
0x180002ac3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002ac8  jz      short loc_180002AF0
0x180002aca  mov     rax, cs:g_pfnResultLoggingCallback
0x180002ad1  test    rax, rax
0x180002ad4  jz      short loc_180002B49
0x180002ad6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002add  jnz     short loc_180002B49
0x180002adf  xor     r8d, r8d
0x180002ae2  xor     edx, edx
0x180002ae4  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aee  jmp     short loc_180002B49
0x180002af0  mov     ebx, 800h
0x180002af5  mov     rax, cs:g_pfnResultLoggingCallback
0x180002afc  test    rax, rax
0x180002aff  jz      short loc_180002B1E
0x180002b01  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002b08  jnz     short loc_180002B1E
0x180002b0a  mov     r8d, ebx
0x180002b0d  lea     rdx, [rbp+13F0h+OutputString]
0x180002b14  lea     rcx, [rsp+14F0h+var_14D0]
0x180002b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b1e  cmp     [rbp+13F0h+OutputString], r13w
0x180002b26  jnz     short loc_180002B3C
0x180002b28  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002b2d  mov     rdx, rbx; unsigned __int16 *
0x180002b30  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002b37  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002b3c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002b43  call    cs:__imp_OutputDebugStringW
0x180002b49  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002b4e  jnz     short loc_180002B59
0x180002b50  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180002b57  jz      short loc_180002B6B
0x180002b59  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002b60  test    rax, rax
0x180002b63  jz      short loc_180002B6B
0x180002b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b6a  nop
0x180002b6b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002b70  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
