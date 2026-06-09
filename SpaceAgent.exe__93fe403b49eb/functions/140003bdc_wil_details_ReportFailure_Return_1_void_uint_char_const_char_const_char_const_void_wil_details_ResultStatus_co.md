# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140003bdc`
- end: `0x140003e70`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400038a4`

## callees

- `0x140001caf`
- `0x140003bdc`
- `0x140005734`
- `0x140007300`
- `0x1400090d8`
- `0x140009294`
- `0x14001edc0`
- `0x14001ee50`
- `0x140020010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140003d81`
- `KERNEL32!IsDebuggerPresent` at `0x140003d81`
- `KERNEL32!GetCurrentThreadId` at `0x140003c86`
- `KERNEL32!GetCurrentThreadId` at `0x140003c86`
- `KERNEL32!OutputDebugStringW` at `0x140003e0b`
- `KERNEL32!OutputDebugStringW` at `0x140003e0b`

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
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "wil";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x140003bdc  mov     [rsp-8+arg_10], rbx
0x140003be1  push    rbp
0x140003be2  push    rsi
0x140003be3  push    rdi
0x140003be4  push    r14
0x140003be6  push    r15
0x140003be8  lea     rbp, [rsp-13D0h]
0x140003bf0  mov     eax, 14D0h
0x140003bf5  call    _alloca_probe
0x140003bfa  sub     rsp, rax
0x140003bfd  mov     rax, cs:__security_cookie
0x140003c04  xor     rax, rsp
0x140003c07  mov     [rbp+13F0h+var_30], rax
0x140003c0e  mov     rdi, [rbp+13F0h+arg_28]
0x140003c15  mov     esi, edx
0x140003c17  mov     r14, rcx
0x140003c1a  xor     edx, edx; Val
0x140003c1c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140003c21  mov     r8d, 98h; Size
0x140003c27  call    memset_0
0x140003c2c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x140003c33  xor     r15d, r15d
0x140003c36  mov     [rbp+13F0h+OutputString], r15w
0x140003c3e  mov     [rbp+13F0h+var_1430], r15b
0x140003c42  mov     ecx, [rdx]; this
0x140003c44  mov     eax, [rdx+4]
0x140003c47  mov     [rsp+14F0h+var_14C8], ecx
0x140003c4b  mov     [rsp+14F0h+var_14C4], eax
0x140003c4f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140003c54  cmp     dword ptr [rdx+8], 1
0x140003c58  mov     ebx, eax
0x140003c5a  lea     eax, [r15+8]
0x140003c5e  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x140003c66  mov     ecx, r15d
0x140003c69  cmovz   ecx, eax
0x140003c6c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140003c70  lea     ecx, [rax-7]
0x140003c73  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003c7b  inc     ecx
0x140003c7d  mov     [rsp+14F0h+var_14B8], r15
0x140003c82  mov     [rsp+14F0h+var_14C0], ecx
0x140003c86  call    cs:__imp_GetCurrentThreadId
0x140003c8c  xorps   xmm0, xmm0
0x140003c8f  mov     [rsp+14F0h+var_1490], esi
0x140003c93  mov     [rsp+14F0h+var_14B0], eax
0x140003c97  xorps   xmm1, xmm1
0x140003c9a  lea     rax, aWil; "wil"
0x140003ca1  mov     [rsp+14F0h+var_148C], ebx
0x140003ca5  mov     [rsp+14F0h+var_1498], rax
0x140003caa  xor     eax, eax
0x140003cac  mov     [rbp+13F0h+var_1458], rax
0x140003cb0  mov     [rbp+13F0h+var_1470], rax
0x140003cb4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003cbb  mov     [rsp+14F0h+var_14A8], r15
0x140003cc0  mov     [rsp+14F0h+var_14A0], r15
0x140003cc5  mov     [rbp+13F0h+var_1448], rdi
0x140003cc9  mov     [rbp+13F0h+var_1440], r14
0x140003ccd  mov     [rsp+14F0h+var_1488], r15
0x140003cd2  movups  [rbp+13F0h+var_1468], xmm0
0x140003cd6  movups  [rsp+14F0h+var_1480], xmm1
0x140003cdb  test    rax, rax
0x140003cde  jz      short loc_140003CEB
0x140003ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ce5  mov     [rbp+13F0h+var_1450], rax
0x140003ce9  jmp     short loc_140003CEF
0x140003ceb  mov     [rbp+13F0h+var_1450], r15
0x140003cef  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003cf6  test    rax, rax
0x140003cf9  jz      short loc_140003D05
0x140003cfb  lea     rcx, [rsp+14F0h+var_14D0]
0x140003d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d05  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003d0c  test    rax, rax
0x140003d0f  jz      short loc_140003D25
0x140003d11  mov     r8d, 400h
0x140003d17  lea     rdx, [rbp+13F0h+var_1430]
0x140003d1b  lea     rcx, [rsp+14F0h+var_14D0]
0x140003d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d25  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003d2c  test    rax, rax
0x140003d2f  jz      short loc_140003D3B
0x140003d31  lea     rcx, [rsp+14F0h+var_14D0]
0x140003d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d3b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003d42  test    rax, rax
0x140003d45  jz      short loc_140003D58
0x140003d47  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003d4c  jnz     short loc_140003D58
0x140003d4e  lea     rcx, [rsp+14F0h+var_14D0]
0x140003d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d58  cmp     [rsp+14F0h+var_14C8], r15d
0x140003d5d  jge     loc_140003E5F
0x140003d63  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x140003d6a  jnz     short loc_140003D8B
0x140003d6c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003d73  test    rax, rax
0x140003d76  jz      short loc_140003D81
0x140003d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d7d  test    al, al
0x140003d7f  jmp     short loc_140003D89
0x140003d81  call    cs:__imp_IsDebuggerPresent
0x140003d87  test    eax, eax
0x140003d89  jz      short loc_140003D92
0x140003d8b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003d90  jz      short loc_140003DB8
0x140003d92  mov     rax, cs:g_pfnResultLoggingCallback
0x140003d99  test    rax, rax
0x140003d9c  jz      short loc_140003E11
0x140003d9e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140003da5  jnz     short loc_140003E11
0x140003da7  xor     r8d, r8d
0x140003daa  lea     rcx, [rsp+14F0h+var_14D0]
0x140003daf  xor     edx, edx
0x140003db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003db6  jmp     short loc_140003E11
0x140003db8  mov     rax, cs:g_pfnResultLoggingCallback
0x140003dbf  mov     ebx, 800h
0x140003dc4  test    rax, rax
0x140003dc7  jz      short loc_140003DE6
0x140003dc9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140003dd0  jnz     short loc_140003DE6
0x140003dd2  mov     r8d, ebx
0x140003dd5  lea     rdx, [rbp+13F0h+OutputString]
0x140003ddc  lea     rcx, [rsp+14F0h+var_14D0]
0x140003de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003de6  cmp     [rbp+13F0h+OutputString], r15w
0x140003dee  jnz     short loc_140003E04
0x140003df0  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140003df5  mov     rdx, rbx; unsigned __int16 *
0x140003df8  lea     rcx, [rbp+13F0h+OutputString]; this
0x140003dff  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140003e04  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140003e0b  call    cs:__imp_OutputDebugStringW
0x140003e11  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140003e16  jnz     short loc_140003E21
0x140003e18  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x140003e1f  jz      short loc_140003E32
0x140003e21  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003e28  test    rax, rax
0x140003e2b  jz      short loc_140003E32
0x140003e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e32  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140003e37  jnz     short loc_140003E65
0x140003e39  mov     rcx, [rbp+13F0h+var_30]
0x140003e40  xor     rcx, rsp; StackCookie
0x140003e43  call    __security_check_cookie
0x140003e48  mov     rbx, [rsp+14F0h+arg_10]
0x140003e50  add     rsp, 14D0h
0x140003e57  pop     r15
0x140003e59  pop     r14
0x140003e5b  pop     rdi
0x140003e5c  pop     rsi
0x140003e5d  pop     rbp
0x140003e5e  retn
0x140003e5f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003e65  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140003e6a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
