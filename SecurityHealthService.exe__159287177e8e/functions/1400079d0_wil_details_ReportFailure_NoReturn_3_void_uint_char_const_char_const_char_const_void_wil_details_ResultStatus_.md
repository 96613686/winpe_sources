# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1400079d0`
- end: `0x140007c32`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400078c8`

## callees

- `0x14000202c`
- `0x140005b60`
- `0x14000615c`
- `0x140006b80`
- `0x140006d60`
- `0x1400079d0`
- `0x140012180`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140007a72`
- `KERNEL32!GetCurrentThreadId` at `0x140007a72`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140007bff`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140007bff`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140007b75`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140007b75`

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
0x1400079d0  mov     [rsp-8+arg_18], rbx
0x1400079d5  push    rbp
0x1400079d6  push    rsi
0x1400079d7  push    rdi
0x1400079d8  push    r12
0x1400079da  push    r13
0x1400079dc  push    r14
0x1400079de  push    r15
0x1400079e0  lea     rbp, [rsp-13C0h]
0x1400079e8  mov     eax, 14C0h
0x1400079ed  call    _alloca_probe
0x1400079f2  sub     rsp, rax
0x1400079f5  mov     r15, r8
0x1400079f8  mov     r14d, edx
0x1400079fb  mov     r12, rcx
0x1400079fe  mov     rsi, [rbp+13F0h+arg_28]
0x140007a05  xor     edx, edx; Val
0x140007a07  mov     r8d, 98h; Size
0x140007a0d  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140007a12  call    memset_0
0x140007a17  nop
0x140007a18  xor     r13d, r13d
0x140007a1b  mov     [rbp+13F0h+OutputString], r13w
0x140007a23  mov     [rbp+13F0h+var_1430], r13b
0x140007a27  mov     rbx, [rbp+13F0h+arg_30]
0x140007a2e  mov     ecx, [rbx]; this
0x140007a30  mov     [rsp+14F0h+var_14C8], ecx
0x140007a34  mov     eax, [rbx+4]
0x140007a37  mov     [rsp+14F0h+var_14C4], eax
0x140007a3b  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140007a40  mov     edi, eax
0x140007a42  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x140007a4a  mov     ecx, r13d
0x140007a4d  lea     eax, [r13+8]
0x140007a51  cmp     dword ptr [rbx+8], 1
0x140007a55  cmovz   ecx, eax
0x140007a58  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140007a5c  lea     ecx, [rax-7]
0x140007a5f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140007a67  inc     ecx
0x140007a69  mov     [rsp+14F0h+var_14C0], ecx
0x140007a6d  mov     [rsp+14F0h+var_14B8], r13
0x140007a72  call    cs:__imp_GetCurrentThreadId
0x140007a78  mov     [rsp+14F0h+var_14B0], eax
0x140007a7c  mov     [rsp+14F0h+var_1498], r15
0x140007a81  mov     [rsp+14F0h+var_1490], r14d
0x140007a86  mov     [rsp+14F0h+var_148C], edi
0x140007a8a  mov     [rsp+14F0h+var_14A8], r13
0x140007a8f  mov     [rsp+14F0h+var_14A0], r13
0x140007a94  mov     [rbp+13F0h+var_1448], rsi
0x140007a98  mov     [rbp+13F0h+var_1440], r12
0x140007a9c  mov     [rsp+14F0h+var_1488], r13
0x140007aa1  xorps   xmm0, xmm0
0x140007aa4  xor     eax, eax
0x140007aa6  movups  [rbp+13F0h+var_1468], xmm0
0x140007aaa  mov     [rbp+13F0h+var_1458], rax
0x140007aae  xorps   xmm1, xmm1
0x140007ab1  movups  [rsp+14F0h+var_1480], xmm1
0x140007ab6  mov     [rbp+13F0h+var_1470], rax
0x140007aba  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140007ac1  test    rax, rax
0x140007ac4  jz      short loc_140007AD1
0x140007ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007acb  mov     [rbp+13F0h+var_1450], rax
0x140007acf  jmp     short loc_140007AD5
0x140007ad1  mov     [rbp+13F0h+var_1450], r13
0x140007ad5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140007adc  test    rax, rax
0x140007adf  jz      short loc_140007AEB
0x140007ae1  lea     rcx, [rsp+14F0h+var_14D0]
0x140007ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007aeb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140007af2  test    rax, rax
0x140007af5  jz      short loc_140007B0B
0x140007af7  mov     r8d, 400h
0x140007afd  lea     rdx, [rbp+13F0h+var_1430]
0x140007b01  lea     rcx, [rsp+14F0h+var_14D0]
0x140007b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007b0b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140007b12  test    rax, rax
0x140007b15  jz      short loc_140007B21
0x140007b17  lea     rcx, [rsp+14F0h+var_14D0]
0x140007b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007b21  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140007b28  test    rax, rax
0x140007b2b  jz      short loc_140007B3E
0x140007b2d  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140007b32  jnz     short loc_140007B3E
0x140007b34  lea     rcx, [rsp+14F0h+var_14D0]
0x140007b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007b3e  cmp     [rsp+14F0h+var_14C8], r13d
0x140007b43  jl      short loc_140007B57
0x140007b45  mov     ecx, 8000FFFFh; this
0x140007b4a  mov     [rsp+14F0h+var_14C8], ecx
0x140007b4e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140007b53  mov     [rsp+14F0h+var_14C4], eax
0x140007b57  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140007b5e  jnz     short loc_140007B7F
0x140007b60  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140007b67  test    rax, rax
0x140007b6a  jz      short loc_140007B75
0x140007b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007b71  test    al, al
0x140007b73  jmp     short loc_140007B7D
0x140007b75  call    cs:__imp_IsDebuggerPresent
0x140007b7b  test    eax, eax
0x140007b7d  jz      short loc_140007B86
0x140007b7f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140007b84  jz      short loc_140007BAC
0x140007b86  mov     rax, cs:g_pfnResultLoggingCallback
0x140007b8d  test    rax, rax
0x140007b90  jz      short loc_140007C05
0x140007b92  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140007b99  jnz     short loc_140007C05
0x140007b9b  xor     r8d, r8d
0x140007b9e  xor     edx, edx
0x140007ba0  lea     rcx, [rsp+14F0h+var_14D0]
0x140007ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007baa  jmp     short loc_140007C05
0x140007bac  mov     ebx, 800h
0x140007bb1  mov     rax, cs:g_pfnResultLoggingCallback
0x140007bb8  test    rax, rax
0x140007bbb  jz      short loc_140007BDA
0x140007bbd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140007bc4  jnz     short loc_140007BDA
0x140007bc6  mov     r8d, ebx
0x140007bc9  lea     rdx, [rbp+13F0h+OutputString]
0x140007bd0  lea     rcx, [rsp+14F0h+var_14D0]
0x140007bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007bda  cmp     [rbp+13F0h+OutputString], r13w
0x140007be2  jnz     short loc_140007BF8
0x140007be4  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140007be9  mov     rdx, rbx; unsigned __int16 *
0x140007bec  lea     rcx, [rbp+13F0h+OutputString]; this
0x140007bf3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140007bf8  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140007bff  call    cs:__imp_OutputDebugStringW
0x140007c05  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140007c0a  jnz     short loc_140007C15
0x140007c0c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140007c13  jz      short loc_140007C27
0x140007c15  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140007c1c  test    rax, rax
0x140007c1f  jz      short loc_140007C27
0x140007c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007c26  nop
0x140007c27  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140007c2c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
