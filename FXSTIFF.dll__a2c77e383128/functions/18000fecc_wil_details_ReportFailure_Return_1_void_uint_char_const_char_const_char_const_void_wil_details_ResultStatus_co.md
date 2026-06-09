# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000fecc`
- end: `0x180010162`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000f9ac`

## callees

- `0x18000fecc`
- `0x180012174`
- `0x180013938`
- `0x1800159a0`
- `0x180015b5c`
- `0x180017bce`
- `0x180017c00`
- `0x180017c90`
- `0x180019010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180010072`
- `KERNEL32!IsDebuggerPresent` at `0x180010072`
- `KERNEL32!OutputDebugStringW` at `0x1800100fc`
- `KERNEL32!OutputDebugStringW` at `0x1800100fc`
- `KERNEL32!GetCurrentThreadId` at `0x18000ff77`
- `KERNEL32!GetCurrentThreadId` at `0x18000ff77`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x18000fecc  mov     [rsp-8+arg_10], rbx
0x18000fed1  push    rbp
0x18000fed2  push    rsi
0x18000fed3  push    rdi
0x18000fed4  push    r14
0x18000fed6  push    r15
0x18000fed8  lea     rbp, [rsp-13D0h]
0x18000fee0  mov     eax, 14D0h
0x18000fee5  call    _alloca_probe
0x18000feea  sub     rsp, rax
0x18000feed  mov     rax, cs:__security_cookie
0x18000fef4  xor     rax, rsp
0x18000fef7  mov     [rbp+13F0h+var_30], rax
0x18000fefe  mov     esi, edx
0x18000ff00  mov     r14, rcx
0x18000ff03  mov     rdi, [rbp+13F0h+arg_28]
0x18000ff0a  xor     edx, edx; Val
0x18000ff0c  mov     r8d, 98h; Size
0x18000ff12  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000ff17  call    memset_0
0x18000ff1c  nop
0x18000ff1d  xor     r15d, r15d
0x18000ff20  mov     [rbp+13F0h+OutputString], r15w
0x18000ff28  mov     [rbp+13F0h+var_1430], r15b
0x18000ff2c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000ff33  mov     ecx, [rdx]; this
0x18000ff35  mov     [rsp+14F0h+var_14C8], ecx
0x18000ff39  mov     eax, [rdx+4]
0x18000ff3c  mov     [rsp+14F0h+var_14C4], eax
0x18000ff40  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000ff45  mov     ebx, eax
0x18000ff47  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000ff4f  mov     ecx, r15d
0x18000ff52  lea     eax, [r15+8]
0x18000ff56  cmp     dword ptr [rdx+8], 1
0x18000ff5a  cmovz   ecx, eax
0x18000ff5d  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000ff61  lea     ecx, [rax-7]
0x18000ff64  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000ff6c  inc     ecx
0x18000ff6e  mov     [rsp+14F0h+var_14C0], ecx
0x18000ff72  mov     [rsp+14F0h+var_14B8], r15
0x18000ff77  call    cs:__imp_GetCurrentThreadId
0x18000ff7d  mov     [rsp+14F0h+var_14B0], eax
0x18000ff81  lea     rax, aWil; "wil"
0x18000ff88  mov     [rsp+14F0h+var_1498], rax
0x18000ff8d  mov     [rsp+14F0h+var_1490], esi
0x18000ff91  mov     [rsp+14F0h+var_148C], ebx
0x18000ff95  mov     [rsp+14F0h+var_14A8], r15
0x18000ff9a  mov     [rsp+14F0h+var_14A0], r15
0x18000ff9f  mov     [rbp+13F0h+var_1448], rdi
0x18000ffa3  mov     [rbp+13F0h+var_1440], r14
0x18000ffa7  mov     [rsp+14F0h+var_1488], r15
0x18000ffac  xorps   xmm0, xmm0
0x18000ffaf  xor     eax, eax
0x18000ffb1  movups  [rbp+13F0h+var_1468], xmm0
0x18000ffb5  mov     [rbp+13F0h+var_1458], rax
0x18000ffb9  xorps   xmm1, xmm1
0x18000ffbc  movups  [rsp+14F0h+var_1480], xmm1
0x18000ffc1  mov     [rbp+13F0h+var_1470], rax
0x18000ffc5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000ffcc  test    rax, rax
0x18000ffcf  jz      short loc_18000FFDC
0x18000ffd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffd6  mov     [rbp+13F0h+var_1450], rax
0x18000ffda  jmp     short loc_18000FFE0
0x18000ffdc  mov     [rbp+13F0h+var_1450], r15
0x18000ffe0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000ffe7  test    rax, rax
0x18000ffea  jz      short loc_18000FFF6
0x18000ffec  lea     rcx, [rsp+14F0h+var_14D0]
0x18000fff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fff6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000fffd  test    rax, rax
0x180010000  jz      short loc_180010016
0x180010002  mov     r8d, 400h
0x180010008  lea     rdx, [rbp+13F0h+var_1430]
0x18001000c  lea     rcx, [rsp+14F0h+var_14D0]
0x180010011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010016  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001001d  test    rax, rax
0x180010020  jz      short loc_18001002C
0x180010022  lea     rcx, [rsp+14F0h+var_14D0]
0x180010027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001002c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180010033  test    rax, rax
0x180010036  jz      short loc_180010049
0x180010038  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001003d  jnz     short loc_180010049
0x18001003f  lea     rcx, [rsp+14F0h+var_14D0]
0x180010044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010049  cmp     [rsp+14F0h+var_14C8], r15d
0x18001004e  jge     loc_18001015C
0x180010054  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18001005b  jnz     short loc_18001007C
0x18001005d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180010064  test    rax, rax
0x180010067  jz      short loc_180010072
0x180010069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001006e  test    al, al
0x180010070  jmp     short loc_18001007A
0x180010072  call    cs:__imp_IsDebuggerPresent
0x180010078  test    eax, eax
0x18001007a  jz      short loc_180010083
0x18001007c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180010081  jz      short loc_1800100A9
0x180010083  mov     rax, cs:g_pfnResultLoggingCallback
0x18001008a  test    rax, rax
0x18001008d  jz      short loc_180010102
0x18001008f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180010096  jnz     short loc_180010102
0x180010098  xor     r8d, r8d
0x18001009b  xor     edx, edx
0x18001009d  lea     rcx, [rsp+14F0h+var_14D0]
0x1800100a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100a7  jmp     short loc_180010102
0x1800100a9  mov     ebx, 800h
0x1800100ae  mov     rax, cs:g_pfnResultLoggingCallback
0x1800100b5  test    rax, rax
0x1800100b8  jz      short loc_1800100D7
0x1800100ba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800100c1  jnz     short loc_1800100D7
0x1800100c3  mov     r8d, ebx
0x1800100c6  lea     rdx, [rbp+13F0h+OutputString]
0x1800100cd  lea     rcx, [rsp+14F0h+var_14D0]
0x1800100d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100d7  cmp     [rbp+13F0h+OutputString], r15w
0x1800100df  jnz     short loc_1800100F5
0x1800100e1  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800100e6  mov     rdx, rbx; unsigned __int16 *
0x1800100e9  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800100f0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800100f5  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800100fc  call    cs:__imp_OutputDebugStringW
0x180010102  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180010107  jnz     short loc_180010112
0x180010109  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180010110  jz      short loc_180010124
0x180010112  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180010119  test    rax, rax
0x18001011c  jz      short loc_180010124
0x18001011e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010123  nop
0x180010124  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180010129  jnz     short loc_180010151
0x18001012b  mov     rcx, [rbp+13F0h+var_30]
0x180010132  xor     rcx, rsp; StackCookie
0x180010135  call    __security_check_cookie
0x18001013a  mov     rbx, [rsp+14F0h+arg_10]
0x180010142  add     rsp, 14D0h
0x180010149  pop     r15
0x18001014b  pop     r14
0x18001014d  pop     rdi
0x18001014e  pop     rsi
0x18001014f  pop     rbp
0x180010150  retn
0x180010151  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180010156  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001015c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
