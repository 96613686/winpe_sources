# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180022d30`
- end: `0x180022fd4`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `676`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180022688`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x180022d30`
- `0x180024be8`
- `0x180026134`
- `0x180027be0`
- `0x180027dac`
- `0x18005c3b0`
- `0x18005d010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180022eea`
- `KERNEL32!IsDebuggerPresent` at `0x180022eea`
- `KERNEL32!OutputDebugStringW` at `0x180022f74`
- `KERNEL32!OutputDebugStringW` at `0x180022f74`
- `KERNEL32!GetCurrentThreadId` at `0x180022df5`
- `KERNEL32!GetCurrentThreadId` at `0x180022df5`

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
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  int v14; // r15d
  int v15; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v17; // rdx
  wil::details::in1diag3 *v18; // rcx
  const struct wil::FailureInfo *v19; // r9
  bool v20; // zf
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+24h] [rbp-DCh]
  int v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v25; // [rsp+30h] [rbp-D0h]
  _WORD *v26; // [rsp+38h] [rbp-C8h]
  DWORD v27; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+60h] [rbp-A0h]
  int v32; // [rsp+64h] [rbp-9Ch]
  __int64 v33; // [rsp+68h] [rbp-98h]
  __int128 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+80h] [rbp-80h]
  __int128 v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  char v41[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v21, 0, 0x98u);
  OutputString[0] = 0;
  v41[0] = 0;
  v11 = a7[1];
  v23 = *a7;
  v24 = v11;
  v12 = wil::details::RecordReturn((wil::details *)(unsigned int)v23, (int)a7);
  v20 = *(_DWORD *)(v13 + 8) == 1;
  v14 = v12;
  v21 = 1;
  v15 = 0;
  if ( v20 )
    v15 = 8;
  v22 = v15;
  v25 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v26 = a8, !*a8) )
    v26 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v30 = a3;
  v27 = CurrentThreadId;
  v31 = a2;
  v37 = 0;
  v35 = 0;
  v32 = v14;
  v28 = 0;
  v29 = 0;
  v39 = a6;
  v40 = a1;
  v33 = 0;
  v36 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v18);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v21);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v21, v41, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v21);
  if ( wil::details::g_pfnOriginateCallback && (v22 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v21);
  if ( v23 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v18);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v20 = !IsDebuggerPresent())
      : (v20 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v18) == 0),
        v20)
    || (v22 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v21, v19);
    OutputDebugStringW(OutputString);
  }
  if ( ((v22 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v18);
  if ( (v22 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v21, v17);
}

```

## disassembly

```asm
0x180022d30  push    rbp
0x180022d32  push    rbx
0x180022d33  push    rsi
0x180022d34  push    rdi
0x180022d35  push    r12
0x180022d37  push    r14
0x180022d39  push    r15
0x180022d3b  lea     rbp, [rsp-13D0h]
0x180022d43  mov     eax, 14D0h
0x180022d48  call    _alloca_probe
0x180022d4d  sub     rsp, rax
0x180022d50  mov     rax, cs:__security_cookie
0x180022d57  xor     rax, rsp
0x180022d5a  mov     [rbp+1400h+var_40], rax
0x180022d61  mov     r14, [rbp+1400h+arg_28]
0x180022d68  mov     rsi, r8
0x180022d6b  mov     edi, edx
0x180022d6d  mov     rbx, rcx
0x180022d70  xor     edx, edx; Val
0x180022d72  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180022d77  mov     r8d, 98h; Size
0x180022d7d  call    memset_0
0x180022d82  mov     rdx, [rbp+1400h+arg_30]; int
0x180022d89  xor     r12d, r12d
0x180022d8c  mov     [rbp+1400h+OutputString], r12w
0x180022d94  mov     [rbp+1400h+var_1440], r12b
0x180022d98  mov     ecx, [rdx]; this
0x180022d9a  mov     eax, [rdx+4]
0x180022d9d  mov     [rsp+1500h+var_14D8], ecx
0x180022da1  mov     [rsp+1500h+var_14D4], eax
0x180022da5  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180022daa  cmp     dword ptr [rdx+8], 1
0x180022dae  mov     r15d, eax
0x180022db1  lea     eax, [r12+8]
0x180022db6  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180022dbe  mov     ecx, r12d
0x180022dc1  cmovz   ecx, eax
0x180022dc4  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180022dc8  lea     ecx, [rax-7]
0x180022dcb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180022dd3  inc     ecx
0x180022dd5  mov     [rsp+1500h+var_14D0], ecx
0x180022dd9  mov     rcx, [rbp+1400h+arg_38]
0x180022de0  test    rcx, rcx
0x180022de3  jz      short loc_180022DF0
0x180022de5  mov     [rsp+1500h+var_14C8], rcx
0x180022dea  cmp     [rcx], r12w
0x180022dee  jnz     short loc_180022DF5
0x180022df0  mov     [rsp+1500h+var_14C8], r12
0x180022df5  call    cs:__imp_GetCurrentThreadId
0x180022dfb  xorps   xmm0, xmm0
0x180022dfe  mov     [rsp+1500h+var_14A8], rsi
0x180022e03  mov     [rsp+1500h+var_14C0], eax
0x180022e07  xorps   xmm1, xmm1
0x180022e0a  xor     eax, eax
0x180022e0c  mov     [rsp+1500h+var_14A0], edi
0x180022e10  mov     [rbp+1400h+var_1468], rax
0x180022e14  mov     [rbp+1400h+var_1480], rax
0x180022e18  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180022e1f  mov     [rsp+1500h+var_149C], r15d
0x180022e24  mov     [rsp+1500h+var_14B8], r12
0x180022e29  mov     [rsp+1500h+var_14B0], r12
0x180022e2e  mov     [rbp+1400h+var_1458], r14
0x180022e32  mov     [rbp+1400h+var_1450], rbx
0x180022e36  mov     [rsp+1500h+var_1498], r12
0x180022e3b  movups  [rbp+1400h+var_1478], xmm0
0x180022e3f  movups  [rsp+1500h+var_1490], xmm1
0x180022e44  test    rax, rax
0x180022e47  jz      short loc_180022E54
0x180022e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e4e  mov     [rbp+1400h+var_1460], rax
0x180022e52  jmp     short loc_180022E58
0x180022e54  mov     [rbp+1400h+var_1460], r12
0x180022e58  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180022e5f  test    rax, rax
0x180022e62  jz      short loc_180022E6E
0x180022e64  lea     rcx, [rsp+1500h+var_14E0]
0x180022e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e6e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180022e75  test    rax, rax
0x180022e78  jz      short loc_180022E8E
0x180022e7a  mov     r8d, 400h
0x180022e80  lea     rdx, [rbp+1400h+var_1440]
0x180022e84  lea     rcx, [rsp+1500h+var_14E0]
0x180022e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e8e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180022e95  test    rax, rax
0x180022e98  jz      short loc_180022EA4
0x180022e9a  lea     rcx, [rsp+1500h+var_14E0]
0x180022e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ea4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180022eab  test    rax, rax
0x180022eae  jz      short loc_180022EC1
0x180022eb0  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180022eb5  jnz     short loc_180022EC1
0x180022eb7  lea     rcx, [rsp+1500h+var_14E0]
0x180022ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ec1  cmp     [rsp+1500h+var_14D8], r12d
0x180022ec6  jge     loc_180022FC3
0x180022ecc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180022ed3  jnz     short loc_180022EF4
0x180022ed5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180022edc  test    rax, rax
0x180022edf  jz      short loc_180022EEA
0x180022ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ee6  test    al, al
0x180022ee8  jmp     short loc_180022EF2
0x180022eea  call    cs:__imp_IsDebuggerPresent
0x180022ef0  test    eax, eax
0x180022ef2  jz      short loc_180022EFB
0x180022ef4  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180022ef9  jz      short loc_180022F21
0x180022efb  mov     rax, cs:g_pfnResultLoggingCallback
0x180022f02  test    rax, rax
0x180022f05  jz      short loc_180022F7A
0x180022f07  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180022f0e  jnz     short loc_180022F7A
0x180022f10  xor     r8d, r8d
0x180022f13  lea     rcx, [rsp+1500h+var_14E0]
0x180022f18  xor     edx, edx
0x180022f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f1f  jmp     short loc_180022F7A
0x180022f21  mov     rax, cs:g_pfnResultLoggingCallback
0x180022f28  mov     ebx, 800h
0x180022f2d  test    rax, rax
0x180022f30  jz      short loc_180022F4F
0x180022f32  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180022f39  jnz     short loc_180022F4F
0x180022f3b  mov     r8d, ebx
0x180022f3e  lea     rdx, [rbp+1400h+OutputString]
0x180022f45  lea     rcx, [rsp+1500h+var_14E0]
0x180022f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f4f  cmp     [rbp+1400h+OutputString], r12w
0x180022f57  jnz     short loc_180022F6D
0x180022f59  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180022f5e  mov     rdx, rbx; unsigned __int16 *
0x180022f61  lea     rcx, [rbp+1400h+OutputString]; this
0x180022f68  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180022f6d  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180022f74  call    cs:__imp_OutputDebugStringW
0x180022f7a  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180022f7f  jnz     short loc_180022F8A
0x180022f81  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180022f88  jz      short loc_180022F9B
0x180022f8a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180022f91  test    rax, rax
0x180022f94  jz      short loc_180022F9B
0x180022f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f9b  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180022fa0  jnz     short loc_180022FC9
0x180022fa2  mov     rcx, [rbp+1400h+var_40]
0x180022fa9  xor     rcx, rsp; StackCookie
0x180022fac  call    __security_check_cookie
0x180022fb1  add     rsp, 14D0h
0x180022fb8  pop     r15
0x180022fba  pop     r14
0x180022fbc  pop     r12
0x180022fbe  pop     rdi
0x180022fbf  pop     rsi
0x180022fc0  pop     rbx
0x180022fc1  pop     rbp
0x180022fc2  retn
0x180022fc3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180022fc9  lea     rcx, [rsp+1500h+var_14E0]; this
0x180022fce  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
