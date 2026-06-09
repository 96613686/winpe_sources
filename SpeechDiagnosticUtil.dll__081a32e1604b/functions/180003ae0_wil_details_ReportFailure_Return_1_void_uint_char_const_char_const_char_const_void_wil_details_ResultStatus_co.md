# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003ae0`
- end: `0x180003d97`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `695`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003598`

## callees

- `0x180002910`
- `0x180003290`
- `0x180003ae0`
- `0x180004624`
- `0x1800058d4`
- `0x1800062cc`
- `0x180006464`
- `0x180010510`
- `0x180011010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180003ca0`
- `KERNEL32!IsDebuggerPresent` at `0x180003ca0`
- `KERNEL32!OutputDebugStringW` at `0x180003d30`
- `KERNEL32!OutputDebugStringW` at `0x180003d30`
- `KERNEL32!GetCurrentThreadId` at `0x180003ba5`
- `KERNEL32!GetCurrentThreadId` at `0x180003ba5`

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
0x180003ae0  push    rbp
0x180003ae2  push    rbx
0x180003ae3  push    rsi
0x180003ae4  push    rdi
0x180003ae5  push    r12
0x180003ae7  push    r14
0x180003ae9  push    r15
0x180003aeb  lea     rbp, [rsp-13D0h]
0x180003af3  mov     eax, 14D0h
0x180003af8  call    _alloca_probe
0x180003afd  sub     rsp, rax
0x180003b00  mov     rax, cs:__security_cookie
0x180003b07  xor     rax, rsp
0x180003b0a  mov     [rbp+1400h+var_40], rax
0x180003b11  mov     r14, [rbp+1400h+arg_28]
0x180003b18  mov     rsi, r8
0x180003b1b  mov     edi, edx
0x180003b1d  mov     rbx, rcx
0x180003b20  xor     edx, edx; Val
0x180003b22  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003b27  mov     r8d, 98h; Size
0x180003b2d  call    memset_0
0x180003b32  mov     rdx, [rbp+1400h+arg_30]; int
0x180003b39  xor     r12d, r12d
0x180003b3c  mov     [rbp+1400h+OutputString], r12w
0x180003b44  mov     [rbp+1400h+var_1440], r12b
0x180003b48  mov     ecx, [rdx]; this
0x180003b4a  mov     eax, [rdx+4]
0x180003b4d  mov     [rsp+1500h+var_14D8], ecx
0x180003b51  mov     [rsp+1500h+var_14D4], eax
0x180003b55  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003b5a  cmp     dword ptr [rdx+8], 1
0x180003b5e  mov     r15d, eax
0x180003b61  lea     eax, [r12+8]
0x180003b66  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003b6e  mov     ecx, r12d
0x180003b71  cmovz   ecx, eax
0x180003b74  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003b78  lea     ecx, [rax-7]
0x180003b7b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003b83  inc     ecx
0x180003b85  mov     [rsp+1500h+var_14D0], ecx
0x180003b89  mov     rcx, [rbp+1400h+arg_38]
0x180003b90  test    rcx, rcx
0x180003b93  jz      short loc_180003BA0
0x180003b95  mov     [rsp+1500h+var_14C8], rcx
0x180003b9a  cmp     [rcx], r12w
0x180003b9e  jnz     short loc_180003BA5
0x180003ba0  mov     [rsp+1500h+var_14C8], r12
0x180003ba5  call    cs:__imp_GetCurrentThreadId
0x180003bac  nop     dword ptr [rax+rax+00h]
0x180003bb1  xorps   xmm0, xmm0
0x180003bb4  mov     [rsp+1500h+var_14A8], rsi
0x180003bb9  mov     [rsp+1500h+var_14C0], eax
0x180003bbd  xorps   xmm1, xmm1
0x180003bc0  xor     eax, eax
0x180003bc2  mov     [rsp+1500h+var_14A0], edi
0x180003bc6  mov     [rbp+1400h+var_1468], rax
0x180003bca  mov     [rbp+1400h+var_1480], rax
0x180003bce  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003bd5  mov     [rsp+1500h+var_149C], r15d
0x180003bda  mov     [rsp+1500h+var_14B8], r12
0x180003bdf  mov     [rsp+1500h+var_14B0], r12
0x180003be4  mov     [rbp+1400h+var_1458], r14
0x180003be8  mov     [rbp+1400h+var_1450], rbx
0x180003bec  mov     [rsp+1500h+var_1498], r12
0x180003bf1  movups  [rbp+1400h+var_1478], xmm0
0x180003bf5  movups  [rsp+1500h+var_1490], xmm1
0x180003bfa  test    rax, rax
0x180003bfd  jz      short loc_180003C0A
0x180003bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c04  mov     [rbp+1400h+var_1460], rax
0x180003c08  jmp     short loc_180003C0E
0x180003c0a  mov     [rbp+1400h+var_1460], r12
0x180003c0e  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003c15  test    rax, rax
0x180003c18  jz      short loc_180003C24
0x180003c1a  lea     rcx, [rsp+1500h+var_14E0]
0x180003c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c24  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003c2b  test    rax, rax
0x180003c2e  jz      short loc_180003C44
0x180003c30  mov     r8d, 400h
0x180003c36  lea     rdx, [rbp+1400h+var_1440]
0x180003c3a  lea     rcx, [rsp+1500h+var_14E0]
0x180003c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c44  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003c4b  test    rax, rax
0x180003c4e  jz      short loc_180003C5A
0x180003c50  lea     rcx, [rsp+1500h+var_14E0]
0x180003c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c5a  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003c61  test    rax, rax
0x180003c64  jz      short loc_180003C77
0x180003c66  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003c6b  jnz     short loc_180003C77
0x180003c6d  lea     rcx, [rsp+1500h+var_14E0]
0x180003c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c77  cmp     [rsp+1500h+var_14D8], r12d
0x180003c7c  jge     loc_180003D86
0x180003c82  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003c89  jnz     short loc_180003CB0
0x180003c8b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003c92  test    rax, rax
0x180003c95  jz      short loc_180003CA0
0x180003c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c9c  test    al, al
0x180003c9e  jmp     short loc_180003CAE
0x180003ca0  call    cs:__imp_IsDebuggerPresent
0x180003ca7  nop     dword ptr [rax+rax+00h]
0x180003cac  test    eax, eax
0x180003cae  jz      short loc_180003CB7
0x180003cb0  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003cb5  jz      short loc_180003CDD
0x180003cb7  mov     rax, cs:g_pfnResultLoggingCallback
0x180003cbe  test    rax, rax
0x180003cc1  jz      short loc_180003D3C
0x180003cc3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003cca  jnz     short loc_180003D3C
0x180003ccc  xor     r8d, r8d
0x180003ccf  lea     rcx, [rsp+1500h+var_14E0]
0x180003cd4  xor     edx, edx
0x180003cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cdb  jmp     short loc_180003D3C
0x180003cdd  mov     rax, cs:g_pfnResultLoggingCallback
0x180003ce4  mov     ebx, 800h
0x180003ce9  test    rax, rax
0x180003cec  jz      short loc_180003D0B
0x180003cee  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003cf5  jnz     short loc_180003D0B
0x180003cf7  mov     r8d, ebx
0x180003cfa  lea     rdx, [rbp+1400h+OutputString]
0x180003d01  lea     rcx, [rsp+1500h+var_14E0]
0x180003d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d0b  cmp     [rbp+1400h+OutputString], r12w
0x180003d13  jnz     short loc_180003D29
0x180003d15  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003d1a  mov     rdx, rbx; unsigned __int16 *
0x180003d1d  lea     rcx, [rbp+1400h+OutputString]; this
0x180003d24  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003d29  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003d30  call    cs:__imp_OutputDebugStringW
0x180003d37  nop     dword ptr [rax+rax+00h]
0x180003d3c  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003d41  jnz     short loc_180003D4C
0x180003d43  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003d4a  jz      short loc_180003D5D
0x180003d4c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003d53  test    rax, rax
0x180003d56  jz      short loc_180003D5D
0x180003d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d5d  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003d62  jnz     short loc_180003D8C
0x180003d64  mov     rcx, [rbp+1400h+var_40]
0x180003d6b  xor     rcx, rsp; StackCookie
0x180003d6e  call    __security_check_cookie
0x180003d73  add     rsp, 14D0h
0x180003d7a  pop     r15
0x180003d7c  pop     r14
0x180003d7e  pop     r12
0x180003d80  pop     rdi
0x180003d81  pop     rsi
0x180003d82  pop     rbx
0x180003d83  pop     rbp
0x180003d84  retn
0x180003d86  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003d8c  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003d91  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
