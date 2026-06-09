# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140005a64`
- end: `0x140005d0f`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `683`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400059e8`

## callees

- `0x140001e7e`
- `0x140003674`
- `0x140004564`
- `0x140005310`
- `0x140005650`
- `0x14000572c`
- `0x140005a64`
- `0x1400070a0`
- `0x140008010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140005b01`
- `KERNEL32!GetCurrentThreadId` at `0x140005b01`
- `KERNEL32!OutputDebugStringW` at `0x140005ca3`
- `KERNEL32!OutputDebugStringW` at `0x140005ca3`
- `KERNEL32!IsDebuggerPresent` at `0x140005c07`
- `KERNEL32!IsDebuggerPresent` at `0x140005c07`

## string_xrefs

- `0x140005b0b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v8; // r14
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  char v16; // bl
  const struct wil::FailureInfo *v17; // rdx
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  __int64 v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  const char *v27; // [rsp+58h] [rbp-A8h]
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v8 = g_pfnThrowPlatformException != 0;
  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v9 = wil::details::RecordException((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 0;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v19 = v10;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
  v28 = 5331;
  v29 = v9;
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
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && !v8 && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v16 = 1, (v19 & 2) != 0) )
  {
    v16 = 0;
  }
  if ( v8 || v16 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v14);
    if ( v16 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v12);
  if ( v8 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v18, OutputString);
  wil::ThrowResultException((wil *)&v18, v12);
  wil::details::WilFailFast((wil::details *)&v18, v17);
}

```

## disassembly

```asm
0x140005a64  push    rbp
0x140005a66  push    rbx
0x140005a67  push    rsi
0x140005a68  push    rdi
0x140005a69  push    r14
0x140005a6b  push    r15
0x140005a6d  lea     rbp, [rsp-13C8h]
0x140005a75  mov     eax, 14C8h
0x140005a7a  call    _alloca_probe
0x140005a7f  sub     rsp, rax
0x140005a82  mov     rsi, rcx
0x140005a85  mov     rdi, [rbp+13F0h+arg_28]
0x140005a8c  xor     r15d, r15d
0x140005a8f  cmp     cs:g_pfnThrowPlatformException, r15
0x140005a96  setnz   r14b
0x140005a9a  xor     edx, edx; Val
0x140005a9c  mov     r8d, 98h; Size
0x140005aa2  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140005aa7  call    memset_0
0x140005aac  nop
0x140005aad  mov     [rbp+13F0h+OutputString], r15w
0x140005ab5  mov     [rbp+13F0h+var_1430], r15b
0x140005ab9  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x140005ac0  mov     ecx, [rdx]; this
0x140005ac2  mov     [rsp+14F0h+var_14C8], ecx
0x140005ac6  mov     eax, [rdx+4]
0x140005ac9  mov     [rsp+14F0h+var_14C4], eax
0x140005acd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140005ad2  mov     ebx, eax
0x140005ad4  mov     dword ptr [rsp+14F0h+var_14D0], r15d
0x140005ad9  mov     ecx, r15d
0x140005adc  lea     eax, [r15+8]
0x140005ae0  cmp     dword ptr [rdx+8], 1
0x140005ae4  cmovz   ecx, eax
0x140005ae7  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140005aeb  lea     ecx, [rax-7]
0x140005aee  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140005af6  inc     ecx
0x140005af8  mov     [rsp+14F0h+var_14C0], ecx
0x140005afc  mov     [rsp+14F0h+var_14B8], r15
0x140005b01  call    cs:__imp_GetCurrentThreadId
0x140005b07  mov     [rsp+14F0h+var_14B0], eax
0x140005b0b  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140005b12  mov     [rsp+14F0h+var_1498], rax
0x140005b17  mov     [rsp+14F0h+var_1490], 14D3h
0x140005b1f  mov     [rsp+14F0h+var_148C], ebx
0x140005b23  mov     [rsp+14F0h+var_14A8], r15
0x140005b28  mov     [rsp+14F0h+var_14A0], r15
0x140005b2d  mov     [rbp+13F0h+var_1448], rdi
0x140005b31  mov     [rbp+13F0h+var_1440], rsi
0x140005b35  mov     [rsp+14F0h+var_1488], r15
0x140005b3a  xorps   xmm0, xmm0
0x140005b3d  xor     eax, eax
0x140005b3f  movups  [rbp+13F0h+var_1468], xmm0
0x140005b43  mov     [rbp+13F0h+var_1458], rax
0x140005b47  xorps   xmm1, xmm1
0x140005b4a  movups  [rsp+14F0h+var_1480], xmm1
0x140005b4f  mov     [rbp+13F0h+var_1470], rax
0x140005b53  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140005b5a  test    rax, rax
0x140005b5d  jz      short loc_140005B6A
0x140005b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b64  mov     [rbp+13F0h+var_1450], rax
0x140005b68  jmp     short loc_140005B6E
0x140005b6a  mov     [rbp+13F0h+var_1450], r15
0x140005b6e  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140005b75  test    rax, rax
0x140005b78  jz      short loc_140005B84
0x140005b7a  lea     rcx, [rsp+14F0h+var_14D0]
0x140005b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b84  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140005b8b  test    rax, rax
0x140005b8e  jz      short loc_140005BA4
0x140005b90  mov     r8d, 400h
0x140005b96  lea     rdx, [rbp+13F0h+var_1430]
0x140005b9a  lea     rcx, [rsp+14F0h+var_14D0]
0x140005b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ba4  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005bab  test    rax, rax
0x140005bae  jz      short loc_140005BBA
0x140005bb0  lea     rcx, [rsp+14F0h+var_14D0]
0x140005bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005bba  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005bc1  test    rax, rax
0x140005bc4  jz      short loc_140005BDC
0x140005bc6  test    r14b, r14b
0x140005bc9  jnz     short loc_140005BDC
0x140005bcb  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140005bd0  jnz     short loc_140005BDC
0x140005bd2  lea     rcx, [rsp+14F0h+var_14D0]
0x140005bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005bdc  cmp     [rsp+14F0h+var_14C8], r15d
0x140005be1  jl      short loc_140005BE9
0x140005be3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140005be9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x140005bf0  jnz     short loc_140005C11
0x140005bf2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140005bf9  test    rax, rax
0x140005bfc  jz      short loc_140005C07
0x140005bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c03  test    al, al
0x140005c05  jmp     short loc_140005C0F
0x140005c07  call    cs:__imp_IsDebuggerPresent
0x140005c0d  test    eax, eax
0x140005c0f  jz      short loc_140005C1A
0x140005c11  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140005c16  mov     bl, 1
0x140005c18  jz      short loc_140005C1D
0x140005c1a  mov     bl, r15b
0x140005c1d  test    r14b, r14b
0x140005c20  jnz     short loc_140005C4C
0x140005c22  test    bl, bl
0x140005c24  jnz     short loc_140005C4C
0x140005c26  mov     rax, cs:g_pfnResultLoggingCallback
0x140005c2d  test    rax, rax
0x140005c30  jz      short loc_140005CA9
0x140005c32  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140005c39  jnz     short loc_140005CA9
0x140005c3b  xor     r8d, r8d
0x140005c3e  xor     edx, edx
0x140005c40  lea     rcx, [rsp+14F0h+var_14D0]
0x140005c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c4a  jmp     short loc_140005CA9
0x140005c4c  mov     edi, 800h
0x140005c51  mov     rax, cs:g_pfnResultLoggingCallback
0x140005c58  test    rax, rax
0x140005c5b  jz      short loc_140005C7A
0x140005c5d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140005c64  jnz     short loc_140005C7A
0x140005c66  mov     r8d, edi
0x140005c69  lea     rdx, [rbp+13F0h+OutputString]
0x140005c70  lea     rcx, [rsp+14F0h+var_14D0]
0x140005c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c7a  cmp     [rbp+13F0h+OutputString], r15w
0x140005c82  jnz     short loc_140005C98
0x140005c84  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140005c89  mov     rdx, rdi; unsigned __int16 *
0x140005c8c  lea     rcx, [rbp+13F0h+OutputString]; this
0x140005c93  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140005c98  test    bl, bl
0x140005c9a  jz      short loc_140005CA9
0x140005c9c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140005ca3  call    cs:__imp_OutputDebugStringW
0x140005ca9  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140005cae  jnz     short loc_140005CB9
0x140005cb0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x140005cb7  jz      short loc_140005CCB
0x140005cb9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140005cc0  test    rax, rax
0x140005cc3  jz      short loc_140005CCB
0x140005cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cca  nop
0x140005ccb  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140005cd0  jz      short loc_140005CDD
0x140005cd2  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140005cd7  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140005cdd  test    r14b, r14b
0x140005ce0  jz      short loc_140005CFA
0x140005ce2  lea     rdx, [rbp+13F0h+OutputString]
0x140005ce9  lea     rcx, [rsp+14F0h+var_14D0]
0x140005cee  mov     rax, cs:g_pfnThrowPlatformException
0x140005cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cfa  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140005cff  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x140005d04  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140005d09  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
