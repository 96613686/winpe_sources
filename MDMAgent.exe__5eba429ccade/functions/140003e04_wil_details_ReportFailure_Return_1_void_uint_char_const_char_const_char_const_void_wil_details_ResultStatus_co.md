# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140003e04`
- end: `0x1400040aa`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140003900`

## callees

- `0x140002930`
- `0x14000349c`
- `0x140003e04`
- `0x1400053a4`
- `0x1400066e0`
- `0x1400077a8`
- `0x140007994`
- `0x1400185e0`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003eca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003eca`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003fbf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003fbf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004049`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004049`

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
0x140003e04  push    rbp
0x140003e06  push    rbx
0x140003e07  push    rsi
0x140003e08  push    rdi
0x140003e09  push    r12
0x140003e0b  push    r14
0x140003e0d  push    r15
0x140003e0f  lea     rbp, [rsp-13D0h]
0x140003e17  mov     eax, 14D0h
0x140003e1c  call    _alloca_probe
0x140003e21  sub     rsp, rax
0x140003e24  mov     rax, cs:__security_cookie
0x140003e2b  xor     rax, rsp
0x140003e2e  mov     [rbp+1400h+var_40], rax
0x140003e35  mov     rsi, r8
0x140003e38  mov     edi, edx
0x140003e3a  mov     rbx, rcx
0x140003e3d  mov     r14, [rbp+1400h+arg_28]
0x140003e44  xor     edx, edx; Val
0x140003e46  mov     r8d, 98h; Size
0x140003e4c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140003e51  call    memset_0
0x140003e56  nop
0x140003e57  xor     r12d, r12d
0x140003e5a  mov     [rbp+1400h+OutputString], r12w
0x140003e62  mov     [rbp+1400h+var_1440], r12b
0x140003e66  mov     rdx, [rbp+1400h+arg_30]; int
0x140003e6d  mov     ecx, [rdx]; this
0x140003e6f  mov     [rsp+1500h+var_14D8], ecx
0x140003e73  mov     eax, [rdx+4]
0x140003e76  mov     [rsp+1500h+var_14D4], eax
0x140003e7a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140003e7f  mov     r15d, eax
0x140003e82  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140003e8a  mov     ecx, r12d
0x140003e8d  lea     eax, [r12+8]
0x140003e92  cmp     dword ptr [rdx+8], 1
0x140003e96  cmovz   ecx, eax
0x140003e99  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140003e9d  lea     ecx, [rax-7]
0x140003ea0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003ea8  inc     ecx
0x140003eaa  mov     [rsp+1500h+var_14D0], ecx
0x140003eae  mov     rcx, [rbp+1400h+arg_38]
0x140003eb5  test    rcx, rcx
0x140003eb8  jz      short loc_140003EC5
0x140003eba  cmp     [rcx], r12w
0x140003ebe  mov     [rsp+1500h+var_14C8], rcx
0x140003ec3  jnz     short loc_140003ECA
0x140003ec5  mov     [rsp+1500h+var_14C8], r12
0x140003eca  call    cs:__imp_GetCurrentThreadId
0x140003ed0  mov     [rsp+1500h+var_14C0], eax
0x140003ed4  mov     [rsp+1500h+var_14A8], rsi
0x140003ed9  mov     [rsp+1500h+var_14A0], edi
0x140003edd  mov     [rsp+1500h+var_149C], r15d
0x140003ee2  mov     [rsp+1500h+var_14B8], r12
0x140003ee7  mov     [rsp+1500h+var_14B0], r12
0x140003eec  mov     [rbp+1400h+var_1458], r14
0x140003ef0  mov     [rbp+1400h+var_1450], rbx
0x140003ef4  mov     [rsp+1500h+var_1498], r12
0x140003ef9  xorps   xmm0, xmm0
0x140003efc  xor     eax, eax
0x140003efe  movups  [rbp+1400h+var_1478], xmm0
0x140003f02  mov     [rbp+1400h+var_1468], rax
0x140003f06  xorps   xmm1, xmm1
0x140003f09  movups  [rsp+1500h+var_1490], xmm1
0x140003f0e  mov     [rbp+1400h+var_1480], rax
0x140003f12  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003f19  test    rax, rax
0x140003f1c  jz      short loc_140003F29
0x140003f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f23  mov     [rbp+1400h+var_1460], rax
0x140003f27  jmp     short loc_140003F2D
0x140003f29  mov     [rbp+1400h+var_1460], r12
0x140003f2d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003f34  test    rax, rax
0x140003f37  jz      short loc_140003F43
0x140003f39  lea     rcx, [rsp+1500h+var_14E0]
0x140003f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f43  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003f4a  test    rax, rax
0x140003f4d  jz      short loc_140003F63
0x140003f4f  mov     r8d, 400h
0x140003f55  lea     rdx, [rbp+1400h+var_1440]
0x140003f59  lea     rcx, [rsp+1500h+var_14E0]
0x140003f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f63  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003f6a  test    rax, rax
0x140003f6d  jz      short loc_140003F79
0x140003f6f  lea     rcx, [rsp+1500h+var_14E0]
0x140003f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f79  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003f80  test    rax, rax
0x140003f83  jz      short loc_140003F96
0x140003f85  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140003f8a  jnz     short loc_140003F96
0x140003f8c  lea     rcx, [rsp+1500h+var_14E0]
0x140003f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f96  cmp     [rsp+1500h+var_14D8], r12d
0x140003f9b  jge     loc_1400040A4
0x140003fa1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140003fa8  jnz     short loc_140003FC9
0x140003faa  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003fb1  test    rax, rax
0x140003fb4  jz      short loc_140003FBF
0x140003fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003fbb  test    al, al
0x140003fbd  jmp     short loc_140003FC7
0x140003fbf  call    cs:__imp_IsDebuggerPresent
0x140003fc5  test    eax, eax
0x140003fc7  jz      short loc_140003FD0
0x140003fc9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140003fce  jz      short loc_140003FF6
0x140003fd0  mov     rax, cs:g_pfnResultLoggingCallback
0x140003fd7  test    rax, rax
0x140003fda  jz      short loc_14000404F
0x140003fdc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140003fe3  jnz     short loc_14000404F
0x140003fe5  xor     r8d, r8d
0x140003fe8  xor     edx, edx
0x140003fea  lea     rcx, [rsp+1500h+var_14E0]
0x140003fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ff4  jmp     short loc_14000404F
0x140003ff6  mov     ebx, 800h
0x140003ffb  mov     rax, cs:g_pfnResultLoggingCallback
0x140004002  test    rax, rax
0x140004005  jz      short loc_140004024
0x140004007  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000400e  jnz     short loc_140004024
0x140004010  mov     r8d, ebx
0x140004013  lea     rdx, [rbp+1400h+OutputString]
0x14000401a  lea     rcx, [rsp+1500h+var_14E0]
0x14000401f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004024  cmp     [rbp+1400h+OutputString], r12w
0x14000402c  jnz     short loc_140004042
0x14000402e  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140004033  mov     rdx, rbx; unsigned __int16 *
0x140004036  lea     rcx, [rbp+1400h+OutputString]; this
0x14000403d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004042  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140004049  call    cs:__imp_OutputDebugStringW
0x14000404f  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140004054  jnz     short loc_14000405F
0x140004056  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x14000405d  jz      short loc_140004071
0x14000405f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140004066  test    rax, rax
0x140004069  jz      short loc_140004071
0x14000406b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004070  nop
0x140004071  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140004076  jnz     short loc_140004099
0x140004078  mov     rcx, [rbp+1400h+var_40]
0x14000407f  xor     rcx, rsp; StackCookie
0x140004082  call    __security_check_cookie
0x140004087  add     rsp, 14D0h
0x14000408e  pop     r15
0x140004090  pop     r14
0x140004092  pop     r12
0x140004094  pop     rdi
0x140004095  pop     rsi
0x140004096  pop     rbx
0x140004097  pop     rbp
0x140004098  retn
0x140004099  lea     rcx, [rsp+1500h+var_14E0]; this
0x14000409e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1400040a4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
