# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140006cb0`
- end: `0x140006f56`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000640c`

## callees

- `0x1400054c0`
- `0x1400060f8`
- `0x140006cb0`
- `0x140008e14`
- `0x140009e20`
- `0x14000c470`
- `0x14000c54c`
- `0x1400562f0`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006d76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006d76`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006ef5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006ef5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140006e6b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140006e6b`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
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
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x140006cb0  push    rbp
0x140006cb2  push    rbx
0x140006cb3  push    rsi
0x140006cb4  push    rdi
0x140006cb5  push    r12
0x140006cb7  push    r14
0x140006cb9  push    r15
0x140006cbb  lea     rbp, [rsp-13D0h]
0x140006cc3  mov     eax, 14D0h
0x140006cc8  call    _alloca_probe
0x140006ccd  sub     rsp, rax
0x140006cd0  mov     rax, cs:__security_cookie
0x140006cd7  xor     rax, rsp
0x140006cda  mov     [rbp+1400h+var_40], rax
0x140006ce1  mov     rsi, r8
0x140006ce4  mov     edi, edx
0x140006ce6  mov     rbx, rcx
0x140006ce9  mov     r14, [rbp+1400h+arg_28]
0x140006cf0  xor     edx, edx; Val
0x140006cf2  mov     r8d, 98h; Size
0x140006cf8  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140006cfd  call    memset_0
0x140006d02  nop
0x140006d03  xor     r12d, r12d
0x140006d06  mov     [rbp+1400h+OutputString], r12w
0x140006d0e  mov     [rbp+1400h+var_1440], r12b
0x140006d12  mov     rdx, [rbp+1400h+arg_30]; int
0x140006d19  mov     ecx, [rdx]; this
0x140006d1b  mov     [rsp+1500h+var_14D8], ecx
0x140006d1f  mov     eax, [rdx+4]
0x140006d22  mov     [rsp+1500h+var_14D4], eax
0x140006d26  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140006d2b  mov     r15d, eax
0x140006d2e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140006d36  mov     ecx, r12d
0x140006d39  lea     eax, [r12+8]
0x140006d3e  cmp     dword ptr [rdx+8], 1
0x140006d42  cmovz   ecx, eax
0x140006d45  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140006d49  lea     ecx, [rax-7]
0x140006d4c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140006d54  inc     ecx
0x140006d56  mov     [rsp+1500h+var_14D0], ecx
0x140006d5a  mov     rcx, [rbp+1400h+arg_38]
0x140006d61  test    rcx, rcx
0x140006d64  jz      short loc_140006D71
0x140006d66  cmp     [rcx], r12w
0x140006d6a  mov     [rsp+1500h+var_14C8], rcx
0x140006d6f  jnz     short loc_140006D76
0x140006d71  mov     [rsp+1500h+var_14C8], r12
0x140006d76  call    cs:__imp_GetCurrentThreadId
0x140006d7c  mov     [rsp+1500h+var_14C0], eax
0x140006d80  mov     [rsp+1500h+var_14A8], rsi
0x140006d85  mov     [rsp+1500h+var_14A0], edi
0x140006d89  mov     [rsp+1500h+var_149C], r15d
0x140006d8e  mov     [rsp+1500h+var_14B8], r12
0x140006d93  mov     [rsp+1500h+var_14B0], r12
0x140006d98  mov     [rbp+1400h+var_1458], r14
0x140006d9c  mov     [rbp+1400h+var_1450], rbx
0x140006da0  mov     [rsp+1500h+var_1498], r12
0x140006da5  xorps   xmm0, xmm0
0x140006da8  xor     eax, eax
0x140006daa  movups  [rbp+1400h+var_1478], xmm0
0x140006dae  mov     [rbp+1400h+var_1468], rax
0x140006db2  xorps   xmm1, xmm1
0x140006db5  movups  [rsp+1500h+var_1490], xmm1
0x140006dba  mov     [rbp+1400h+var_1480], rax
0x140006dbe  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140006dc5  test    rax, rax
0x140006dc8  jz      short loc_140006DD5
0x140006dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006dcf  mov     [rbp+1400h+var_1460], rax
0x140006dd3  jmp     short loc_140006DD9
0x140006dd5  mov     [rbp+1400h+var_1460], r12
0x140006dd9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140006de0  test    rax, rax
0x140006de3  jz      short loc_140006DEF
0x140006de5  lea     rcx, [rsp+1500h+var_14E0]
0x140006dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006def  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140006df6  test    rax, rax
0x140006df9  jz      short loc_140006E0F
0x140006dfb  mov     r8d, 400h
0x140006e01  lea     rdx, [rbp+1400h+var_1440]
0x140006e05  lea     rcx, [rsp+1500h+var_14E0]
0x140006e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006e0f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006e16  test    rax, rax
0x140006e19  jz      short loc_140006E25
0x140006e1b  lea     rcx, [rsp+1500h+var_14E0]
0x140006e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006e25  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006e2c  test    rax, rax
0x140006e2f  jz      short loc_140006E42
0x140006e31  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140006e36  jnz     short loc_140006E42
0x140006e38  lea     rcx, [rsp+1500h+var_14E0]
0x140006e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006e42  cmp     [rsp+1500h+var_14D8], r12d
0x140006e47  jge     loc_140006F50
0x140006e4d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140006e54  jnz     short loc_140006E75
0x140006e56  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140006e5d  test    rax, rax
0x140006e60  jz      short loc_140006E6B
0x140006e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006e67  test    al, al
0x140006e69  jmp     short loc_140006E73
0x140006e6b  call    cs:__imp_IsDebuggerPresent
0x140006e71  test    eax, eax
0x140006e73  jz      short loc_140006E7C
0x140006e75  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140006e7a  jz      short loc_140006EA2
0x140006e7c  mov     rax, cs:g_pfnResultLoggingCallback
0x140006e83  test    rax, rax
0x140006e86  jz      short loc_140006EFB
0x140006e88  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140006e8f  jnz     short loc_140006EFB
0x140006e91  xor     r8d, r8d
0x140006e94  xor     edx, edx
0x140006e96  lea     rcx, [rsp+1500h+var_14E0]
0x140006e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ea0  jmp     short loc_140006EFB
0x140006ea2  mov     ebx, 800h
0x140006ea7  mov     rax, cs:g_pfnResultLoggingCallback
0x140006eae  test    rax, rax
0x140006eb1  jz      short loc_140006ED0
0x140006eb3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140006eba  jnz     short loc_140006ED0
0x140006ebc  mov     r8d, ebx
0x140006ebf  lea     rdx, [rbp+1400h+OutputString]
0x140006ec6  lea     rcx, [rsp+1500h+var_14E0]
0x140006ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ed0  cmp     [rbp+1400h+OutputString], r12w
0x140006ed8  jnz     short loc_140006EEE
0x140006eda  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140006edf  mov     rdx, rbx; unsigned __int16 *
0x140006ee2  lea     rcx, [rbp+1400h+OutputString]; this
0x140006ee9  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140006eee  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140006ef5  call    cs:__imp_OutputDebugStringW
0x140006efb  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140006f00  jnz     short loc_140006F0B
0x140006f02  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140006f09  jz      short loc_140006F1D
0x140006f0b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140006f12  test    rax, rax
0x140006f15  jz      short loc_140006F1D
0x140006f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f1c  nop
0x140006f1d  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140006f22  jnz     short loc_140006F45
0x140006f24  mov     rcx, [rbp+1400h+var_40]
0x140006f2b  xor     rcx, rsp; StackCookie
0x140006f2e  call    __security_check_cookie
0x140006f33  add     rsp, 14D0h
0x140006f3a  pop     r15
0x140006f3c  pop     r14
0x140006f3e  pop     r12
0x140006f40  pop     rdi
0x140006f41  pop     rsi
0x140006f42  pop     rbx
0x140006f43  pop     rbp
0x140006f44  retn
0x140006f45  lea     rcx, [rsp+1500h+var_14E0]; this
0x140006f4a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140006f50  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
