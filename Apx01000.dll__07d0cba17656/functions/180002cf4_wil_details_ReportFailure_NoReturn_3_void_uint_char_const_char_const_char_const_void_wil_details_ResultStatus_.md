# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002cf4`
- end: `0x180002f56`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002a98`

## callees

- `0x1800027c8`
- `0x180002cf4`
- `0x1800051f4`
- `0x180005990`
- `0x1800068d0`
- `0x180008e00`
- `0x180029820`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d96`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002f23`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002f23`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002e99`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002e99`

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
0x180002cf4  mov     [rsp-8+arg_18], rbx
0x180002cf9  push    rbp
0x180002cfa  push    rsi
0x180002cfb  push    rdi
0x180002cfc  push    r12
0x180002cfe  push    r13
0x180002d00  push    r14
0x180002d02  push    r15
0x180002d04  lea     rbp, [rsp-13C0h]
0x180002d0c  mov     eax, 14C0h
0x180002d11  call    _alloca_probe
0x180002d16  sub     rsp, rax
0x180002d19  mov     r15, r8
0x180002d1c  mov     r14d, edx
0x180002d1f  mov     r12, rcx
0x180002d22  mov     rsi, [rbp+13F0h+arg_28]
0x180002d29  xor     edx, edx; Val
0x180002d2b  mov     r8d, 98h; Size
0x180002d31  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002d36  call    memset_0
0x180002d3b  nop
0x180002d3c  xor     r13d, r13d
0x180002d3f  mov     [rbp+13F0h+OutputString], r13w
0x180002d47  mov     [rbp+13F0h+var_1430], r13b
0x180002d4b  mov     rbx, [rbp+13F0h+arg_30]
0x180002d52  mov     ecx, [rbx]; this
0x180002d54  mov     [rsp+14F0h+var_14C8], ecx
0x180002d58  mov     eax, [rbx+4]
0x180002d5b  mov     [rsp+14F0h+var_14C4], eax
0x180002d5f  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002d64  mov     edi, eax
0x180002d66  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180002d6e  mov     ecx, r13d
0x180002d71  lea     eax, [r13+8]
0x180002d75  cmp     dword ptr [rbx+8], 1
0x180002d79  cmovz   ecx, eax
0x180002d7c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002d80  lea     ecx, [rax-7]
0x180002d83  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002d8b  inc     ecx
0x180002d8d  mov     [rsp+14F0h+var_14C0], ecx
0x180002d91  mov     [rsp+14F0h+var_14B8], r13
0x180002d96  call    cs:__imp_GetCurrentThreadId
0x180002d9c  mov     [rsp+14F0h+var_14B0], eax
0x180002da0  mov     [rsp+14F0h+var_1498], r15
0x180002da5  mov     [rsp+14F0h+var_1490], r14d
0x180002daa  mov     [rsp+14F0h+var_148C], edi
0x180002dae  mov     [rsp+14F0h+var_14A8], r13
0x180002db3  mov     [rsp+14F0h+var_14A0], r13
0x180002db8  mov     [rbp+13F0h+var_1448], rsi
0x180002dbc  mov     [rbp+13F0h+var_1440], r12
0x180002dc0  mov     [rsp+14F0h+var_1488], r13
0x180002dc5  xorps   xmm0, xmm0
0x180002dc8  xor     eax, eax
0x180002dca  movups  [rbp+13F0h+var_1468], xmm0
0x180002dce  mov     [rbp+13F0h+var_1458], rax
0x180002dd2  xorps   xmm1, xmm1
0x180002dd5  movups  [rsp+14F0h+var_1480], xmm1
0x180002dda  mov     [rbp+13F0h+var_1470], rax
0x180002dde  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002de5  test    rax, rax
0x180002de8  jz      short loc_180002DF5
0x180002dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002def  mov     [rbp+13F0h+var_1450], rax
0x180002df3  jmp     short loc_180002DF9
0x180002df5  mov     [rbp+13F0h+var_1450], r13
0x180002df9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002e00  test    rax, rax
0x180002e03  jz      short loc_180002E0F
0x180002e05  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e0f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002e16  test    rax, rax
0x180002e19  jz      short loc_180002E2F
0x180002e1b  mov     r8d, 400h
0x180002e21  lea     rdx, [rbp+13F0h+var_1430]
0x180002e25  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e2f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002e36  test    rax, rax
0x180002e39  jz      short loc_180002E45
0x180002e3b  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e45  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002e4c  test    rax, rax
0x180002e4f  jz      short loc_180002E62
0x180002e51  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002e56  jnz     short loc_180002E62
0x180002e58  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e62  cmp     [rsp+14F0h+var_14C8], r13d
0x180002e67  jl      short loc_180002E7B
0x180002e69  mov     ecx, 8000FFFFh; this
0x180002e6e  mov     [rsp+14F0h+var_14C8], ecx
0x180002e72  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002e77  mov     [rsp+14F0h+var_14C4], eax
0x180002e7b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180002e82  jnz     short loc_180002EA3
0x180002e84  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002e8b  test    rax, rax
0x180002e8e  jz      short loc_180002E99
0x180002e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e95  test    al, al
0x180002e97  jmp     short loc_180002EA1
0x180002e99  call    cs:__imp_IsDebuggerPresent
0x180002e9f  test    eax, eax
0x180002ea1  jz      short loc_180002EAA
0x180002ea3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002ea8  jz      short loc_180002ED0
0x180002eaa  mov     rax, cs:g_pfnResultLoggingCallback
0x180002eb1  test    rax, rax
0x180002eb4  jz      short loc_180002F29
0x180002eb6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002ebd  jnz     short loc_180002F29
0x180002ebf  xor     r8d, r8d
0x180002ec2  xor     edx, edx
0x180002ec4  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ece  jmp     short loc_180002F29
0x180002ed0  mov     ebx, 800h
0x180002ed5  mov     rax, cs:g_pfnResultLoggingCallback
0x180002edc  test    rax, rax
0x180002edf  jz      short loc_180002EFE
0x180002ee1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002ee8  jnz     short loc_180002EFE
0x180002eea  mov     r8d, ebx
0x180002eed  lea     rdx, [rbp+13F0h+OutputString]
0x180002ef4  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002efe  cmp     [rbp+13F0h+OutputString], r13w
0x180002f06  jnz     short loc_180002F1C
0x180002f08  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002f0d  mov     rdx, rbx; unsigned __int16 *
0x180002f10  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002f17  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002f1c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002f23  call    cs:__imp_OutputDebugStringW
0x180002f29  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002f2e  jnz     short loc_180002F39
0x180002f30  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180002f37  jz      short loc_180002F4B
0x180002f39  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002f40  test    rax, rax
0x180002f43  jz      short loc_180002F4B
0x180002f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f4a  nop
0x180002f4b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002f50  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
