# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003dbc`
- end: `0x180004062`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000385c`

## callees

- `0x180002350`
- `0x180002ed4`
- `0x180003dbc`
- `0x180006304`
- `0x180007c38`
- `0x18000a2c0`
- `0x18000a48c`
- `0x1800291b0`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e82`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003f77`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003f77`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004001`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004001`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
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
0x180003dbc  push    rbp
0x180003dbe  push    rbx
0x180003dbf  push    rsi
0x180003dc0  push    rdi
0x180003dc1  push    r12
0x180003dc3  push    r14
0x180003dc5  push    r15
0x180003dc7  lea     rbp, [rsp-13D0h]
0x180003dcf  mov     eax, 14D0h
0x180003dd4  call    _alloca_probe
0x180003dd9  sub     rsp, rax
0x180003ddc  mov     rax, cs:__security_cookie
0x180003de3  xor     rax, rsp
0x180003de6  mov     [rbp+1400h+var_40], rax
0x180003ded  mov     rsi, r8
0x180003df0  mov     edi, edx
0x180003df2  mov     rbx, rcx
0x180003df5  mov     r14, [rbp+1400h+arg_28]
0x180003dfc  xor     edx, edx; Val
0x180003dfe  mov     r8d, 98h; Size
0x180003e04  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003e09  call    memset_0
0x180003e0e  nop
0x180003e0f  xor     r12d, r12d
0x180003e12  mov     [rbp+1400h+OutputString], r12w
0x180003e1a  mov     [rbp+1400h+var_1440], r12b
0x180003e1e  mov     rdx, [rbp+1400h+arg_30]; int
0x180003e25  mov     ecx, [rdx]; this
0x180003e27  mov     [rsp+1500h+var_14D8], ecx
0x180003e2b  mov     eax, [rdx+4]
0x180003e2e  mov     [rsp+1500h+var_14D4], eax
0x180003e32  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003e37  mov     r15d, eax
0x180003e3a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003e42  mov     ecx, r12d
0x180003e45  lea     eax, [r12+8]
0x180003e4a  cmp     dword ptr [rdx+8], 1
0x180003e4e  cmovz   ecx, eax
0x180003e51  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003e55  lea     ecx, [rax-7]
0x180003e58  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003e60  inc     ecx
0x180003e62  mov     [rsp+1500h+var_14D0], ecx
0x180003e66  mov     rcx, [rbp+1400h+arg_38]
0x180003e6d  test    rcx, rcx
0x180003e70  jz      short loc_180003E7D
0x180003e72  cmp     [rcx], r12w
0x180003e76  mov     [rsp+1500h+var_14C8], rcx
0x180003e7b  jnz     short loc_180003E82
0x180003e7d  mov     [rsp+1500h+var_14C8], r12
0x180003e82  call    cs:__imp_GetCurrentThreadId
0x180003e88  mov     [rsp+1500h+var_14C0], eax
0x180003e8c  mov     [rsp+1500h+var_14A8], rsi
0x180003e91  mov     [rsp+1500h+var_14A0], edi
0x180003e95  mov     [rsp+1500h+var_149C], r15d
0x180003e9a  mov     [rsp+1500h+var_14B8], r12
0x180003e9f  mov     [rsp+1500h+var_14B0], r12
0x180003ea4  mov     [rbp+1400h+var_1458], r14
0x180003ea8  mov     [rbp+1400h+var_1450], rbx
0x180003eac  mov     [rsp+1500h+var_1498], r12
0x180003eb1  xorps   xmm0, xmm0
0x180003eb4  xor     eax, eax
0x180003eb6  movups  [rbp+1400h+var_1478], xmm0
0x180003eba  mov     [rbp+1400h+var_1468], rax
0x180003ebe  xorps   xmm1, xmm1
0x180003ec1  movups  [rsp+1500h+var_1490], xmm1
0x180003ec6  mov     [rbp+1400h+var_1480], rax
0x180003eca  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003ed1  test    rax, rax
0x180003ed4  jz      short loc_180003EE1
0x180003ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003edb  mov     [rbp+1400h+var_1460], rax
0x180003edf  jmp     short loc_180003EE5
0x180003ee1  mov     [rbp+1400h+var_1460], r12
0x180003ee5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003eec  test    rax, rax
0x180003eef  jz      short loc_180003EFB
0x180003ef1  lea     rcx, [rsp+1500h+var_14E0]
0x180003ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003efb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003f02  test    rax, rax
0x180003f05  jz      short loc_180003F1B
0x180003f07  mov     r8d, 400h
0x180003f0d  lea     rdx, [rbp+1400h+var_1440]
0x180003f11  lea     rcx, [rsp+1500h+var_14E0]
0x180003f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f1b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003f22  test    rax, rax
0x180003f25  jz      short loc_180003F31
0x180003f27  lea     rcx, [rsp+1500h+var_14E0]
0x180003f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f31  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003f38  test    rax, rax
0x180003f3b  jz      short loc_180003F4E
0x180003f3d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003f42  jnz     short loc_180003F4E
0x180003f44  lea     rcx, [rsp+1500h+var_14E0]
0x180003f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f4e  cmp     [rsp+1500h+var_14D8], r12d
0x180003f53  jge     loc_18000405C
0x180003f59  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003f60  jnz     short loc_180003F81
0x180003f62  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003f69  test    rax, rax
0x180003f6c  jz      short loc_180003F77
0x180003f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f73  test    al, al
0x180003f75  jmp     short loc_180003F7F
0x180003f77  call    cs:__imp_IsDebuggerPresent
0x180003f7d  test    eax, eax
0x180003f7f  jz      short loc_180003F88
0x180003f81  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003f86  jz      short loc_180003FAE
0x180003f88  mov     rax, cs:g_pfnResultLoggingCallback
0x180003f8f  test    rax, rax
0x180003f92  jz      short loc_180004007
0x180003f94  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003f9b  jnz     short loc_180004007
0x180003f9d  xor     r8d, r8d
0x180003fa0  xor     edx, edx
0x180003fa2  lea     rcx, [rsp+1500h+var_14E0]
0x180003fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fac  jmp     short loc_180004007
0x180003fae  mov     ebx, 800h
0x180003fb3  mov     rax, cs:g_pfnResultLoggingCallback
0x180003fba  test    rax, rax
0x180003fbd  jz      short loc_180003FDC
0x180003fbf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003fc6  jnz     short loc_180003FDC
0x180003fc8  mov     r8d, ebx
0x180003fcb  lea     rdx, [rbp+1400h+OutputString]
0x180003fd2  lea     rcx, [rsp+1500h+var_14E0]
0x180003fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fdc  cmp     [rbp+1400h+OutputString], r12w
0x180003fe4  jnz     short loc_180003FFA
0x180003fe6  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003feb  mov     rdx, rbx; unsigned __int16 *
0x180003fee  lea     rcx, [rbp+1400h+OutputString]; this
0x180003ff5  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003ffa  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004001  call    cs:__imp_OutputDebugStringW
0x180004007  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000400c  jnz     short loc_180004017
0x18000400e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004015  jz      short loc_180004029
0x180004017  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000401e  test    rax, rax
0x180004021  jz      short loc_180004029
0x180004023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004028  nop
0x180004029  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000402e  jnz     short loc_180004051
0x180004030  mov     rcx, [rbp+1400h+var_40]
0x180004037  xor     rcx, rsp; StackCookie
0x18000403a  call    __security_check_cookie
0x18000403f  add     rsp, 14D0h
0x180004046  pop     r15
0x180004048  pop     r14
0x18000404a  pop     r12
0x18000404c  pop     rdi
0x18000404d  pop     rsi
0x18000404e  pop     rbx
0x18000404f  pop     rbp
0x180004050  retn
0x180004051  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004056  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000405c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
