# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000793c`
- end: `0x180007b9e`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800076d8`

## callees

- `0x180005914`
- `0x18000793c`
- `0x180009f84`
- `0x18000a72c`
- `0x18000ba80`
- `0x18000e370`
- `0x1800e67d0`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800079de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800079de`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007ae1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007ae1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007b6b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007b6b`

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
0x18000793c  mov     [rsp-8+arg_18], rbx
0x180007941  push    rbp
0x180007942  push    rsi
0x180007943  push    rdi
0x180007944  push    r12
0x180007946  push    r13
0x180007948  push    r14
0x18000794a  push    r15
0x18000794c  lea     rbp, [rsp-13C0h]
0x180007954  mov     eax, 14C0h
0x180007959  call    _alloca_probe
0x18000795e  sub     rsp, rax
0x180007961  mov     r15, r8
0x180007964  mov     r14d, edx
0x180007967  mov     r12, rcx
0x18000796a  mov     rsi, [rbp+13F0h+arg_28]
0x180007971  xor     edx, edx; Val
0x180007973  mov     r8d, 98h; Size
0x180007979  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000797e  call    memset_0
0x180007983  nop
0x180007984  xor     r13d, r13d
0x180007987  mov     [rbp+13F0h+OutputString], r13w
0x18000798f  mov     [rbp+13F0h+var_1430], r13b
0x180007993  mov     rbx, [rbp+13F0h+arg_30]
0x18000799a  mov     ecx, [rbx]; this
0x18000799c  mov     [rsp+14F0h+var_14C8], ecx
0x1800079a0  mov     eax, [rbx+4]
0x1800079a3  mov     [rsp+14F0h+var_14C4], eax
0x1800079a7  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800079ac  mov     edi, eax
0x1800079ae  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800079b6  mov     ecx, r13d
0x1800079b9  lea     eax, [r13+8]
0x1800079bd  cmp     dword ptr [rbx+8], 1
0x1800079c1  cmovz   ecx, eax
0x1800079c4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800079c8  lea     ecx, [rax-7]
0x1800079cb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800079d3  inc     ecx
0x1800079d5  mov     [rsp+14F0h+var_14C0], ecx
0x1800079d9  mov     [rsp+14F0h+var_14B8], r13
0x1800079de  call    cs:__imp_GetCurrentThreadId
0x1800079e4  mov     [rsp+14F0h+var_14B0], eax
0x1800079e8  mov     [rsp+14F0h+var_1498], r15
0x1800079ed  mov     [rsp+14F0h+var_1490], r14d
0x1800079f2  mov     [rsp+14F0h+var_148C], edi
0x1800079f6  mov     [rsp+14F0h+var_14A8], r13
0x1800079fb  mov     [rsp+14F0h+var_14A0], r13
0x180007a00  mov     [rbp+13F0h+var_1448], rsi
0x180007a04  mov     [rbp+13F0h+var_1440], r12
0x180007a08  mov     [rsp+14F0h+var_1488], r13
0x180007a0d  xorps   xmm0, xmm0
0x180007a10  xor     eax, eax
0x180007a12  movups  [rbp+13F0h+var_1468], xmm0
0x180007a16  mov     [rbp+13F0h+var_1458], rax
0x180007a1a  xorps   xmm1, xmm1
0x180007a1d  movups  [rsp+14F0h+var_1480], xmm1
0x180007a22  mov     [rbp+13F0h+var_1470], rax
0x180007a26  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007a2d  test    rax, rax
0x180007a30  jz      short loc_180007A3D
0x180007a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a37  mov     [rbp+13F0h+var_1450], rax
0x180007a3b  jmp     short loc_180007A41
0x180007a3d  mov     [rbp+13F0h+var_1450], r13
0x180007a41  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007a48  test    rax, rax
0x180007a4b  jz      short loc_180007A57
0x180007a4d  lea     rcx, [rsp+14F0h+var_14D0]
0x180007a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a57  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007a5e  test    rax, rax
0x180007a61  jz      short loc_180007A77
0x180007a63  mov     r8d, 400h
0x180007a69  lea     rdx, [rbp+13F0h+var_1430]
0x180007a6d  lea     rcx, [rsp+14F0h+var_14D0]
0x180007a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a77  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007a7e  test    rax, rax
0x180007a81  jz      short loc_180007A8D
0x180007a83  lea     rcx, [rsp+14F0h+var_14D0]
0x180007a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a8d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007a94  test    rax, rax
0x180007a97  jz      short loc_180007AAA
0x180007a99  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007a9e  jnz     short loc_180007AAA
0x180007aa0  lea     rcx, [rsp+14F0h+var_14D0]
0x180007aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aaa  cmp     [rsp+14F0h+var_14C8], r13d
0x180007aaf  jl      short loc_180007AC3
0x180007ab1  mov     ecx, 8000FFFFh; this
0x180007ab6  mov     [rsp+14F0h+var_14C8], ecx
0x180007aba  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007abf  mov     [rsp+14F0h+var_14C4], eax
0x180007ac3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180007aca  jnz     short loc_180007AEB
0x180007acc  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007ad3  test    rax, rax
0x180007ad6  jz      short loc_180007AE1
0x180007ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007add  test    al, al
0x180007adf  jmp     short loc_180007AE9
0x180007ae1  call    cs:__imp_IsDebuggerPresent
0x180007ae7  test    eax, eax
0x180007ae9  jz      short loc_180007AF2
0x180007aeb  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007af0  jz      short loc_180007B18
0x180007af2  mov     rax, cs:g_pfnResultLoggingCallback
0x180007af9  test    rax, rax
0x180007afc  jz      short loc_180007B71
0x180007afe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180007b05  jnz     short loc_180007B71
0x180007b07  xor     r8d, r8d
0x180007b0a  xor     edx, edx
0x180007b0c  lea     rcx, [rsp+14F0h+var_14D0]
0x180007b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b16  jmp     short loc_180007B71
0x180007b18  mov     ebx, 800h
0x180007b1d  mov     rax, cs:g_pfnResultLoggingCallback
0x180007b24  test    rax, rax
0x180007b27  jz      short loc_180007B46
0x180007b29  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180007b30  jnz     short loc_180007B46
0x180007b32  mov     r8d, ebx
0x180007b35  lea     rdx, [rbp+13F0h+OutputString]
0x180007b3c  lea     rcx, [rsp+14F0h+var_14D0]
0x180007b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b46  cmp     [rbp+13F0h+OutputString], r13w
0x180007b4e  jnz     short loc_180007B64
0x180007b50  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180007b55  mov     rdx, rbx; unsigned __int16 *
0x180007b58  lea     rcx, [rbp+13F0h+OutputString]; this
0x180007b5f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007b64  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180007b6b  call    cs:__imp_OutputDebugStringW
0x180007b71  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180007b76  jnz     short loc_180007B81
0x180007b78  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180007b7f  jz      short loc_180007B93
0x180007b81  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007b88  test    rax, rax
0x180007b8b  jz      short loc_180007B93
0x180007b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b92  nop
0x180007b93  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180007b98  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
