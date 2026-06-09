# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000a9a4`
- end: `0x18000ac4a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000a634`

## callees

- `0x180009190`
- `0x180009cf0`
- `0x18000a9a4`
- `0x18000c584`
- `0x18000e250`
- `0x18000fdc8`
- `0x180010010`
- `0x180047810`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aa6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aa6a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000ab5f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000ab5f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000abe9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000abe9`

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
0x18000a9a4  push    rbp
0x18000a9a6  push    rbx
0x18000a9a7  push    rsi
0x18000a9a8  push    rdi
0x18000a9a9  push    r12
0x18000a9ab  push    r14
0x18000a9ad  push    r15
0x18000a9af  lea     rbp, [rsp-13D0h]
0x18000a9b7  mov     eax, 14D0h
0x18000a9bc  call    _alloca_probe
0x18000a9c1  sub     rsp, rax
0x18000a9c4  mov     rax, cs:__security_cookie
0x18000a9cb  xor     rax, rsp
0x18000a9ce  mov     [rbp+1400h+var_40], rax
0x18000a9d5  mov     rsi, r8
0x18000a9d8  mov     edi, edx
0x18000a9da  mov     rbx, rcx
0x18000a9dd  mov     r14, [rbp+1400h+arg_28]
0x18000a9e4  xor     edx, edx; Val
0x18000a9e6  mov     r8d, 98h; Size
0x18000a9ec  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000a9f1  call    memset_0
0x18000a9f6  nop
0x18000a9f7  xor     r12d, r12d
0x18000a9fa  mov     [rbp+1400h+OutputString], r12w
0x18000aa02  mov     [rbp+1400h+var_1440], r12b
0x18000aa06  mov     rdx, [rbp+1400h+arg_30]; int
0x18000aa0d  mov     ecx, [rdx]; this
0x18000aa0f  mov     [rsp+1500h+var_14D8], ecx
0x18000aa13  mov     eax, [rdx+4]
0x18000aa16  mov     [rsp+1500h+var_14D4], eax
0x18000aa1a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000aa1f  mov     r15d, eax
0x18000aa22  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000aa2a  mov     ecx, r12d
0x18000aa2d  lea     eax, [r12+8]
0x18000aa32  cmp     dword ptr [rdx+8], 1
0x18000aa36  cmovz   ecx, eax
0x18000aa39  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000aa3d  lea     ecx, [rax-7]
0x18000aa40  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000aa48  inc     ecx
0x18000aa4a  mov     [rsp+1500h+var_14D0], ecx
0x18000aa4e  mov     rcx, [rbp+1400h+arg_38]
0x18000aa55  test    rcx, rcx
0x18000aa58  jz      short loc_18000AA65
0x18000aa5a  cmp     [rcx], r12w
0x18000aa5e  mov     [rsp+1500h+var_14C8], rcx
0x18000aa63  jnz     short loc_18000AA6A
0x18000aa65  mov     [rsp+1500h+var_14C8], r12
0x18000aa6a  call    cs:__imp_GetCurrentThreadId
0x18000aa70  mov     [rsp+1500h+var_14C0], eax
0x18000aa74  mov     [rsp+1500h+var_14A8], rsi
0x18000aa79  mov     [rsp+1500h+var_14A0], edi
0x18000aa7d  mov     [rsp+1500h+var_149C], r15d
0x18000aa82  mov     [rsp+1500h+var_14B8], r12
0x18000aa87  mov     [rsp+1500h+var_14B0], r12
0x18000aa8c  mov     [rbp+1400h+var_1458], r14
0x18000aa90  mov     [rbp+1400h+var_1450], rbx
0x18000aa94  mov     [rsp+1500h+var_1498], r12
0x18000aa99  xorps   xmm0, xmm0
0x18000aa9c  xor     eax, eax
0x18000aa9e  movups  [rbp+1400h+var_1478], xmm0
0x18000aaa2  mov     [rbp+1400h+var_1468], rax
0x18000aaa6  xorps   xmm1, xmm1
0x18000aaa9  movups  [rsp+1500h+var_1490], xmm1
0x18000aaae  mov     [rbp+1400h+var_1480], rax
0x18000aab2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000aab9  test    rax, rax
0x18000aabc  jz      short loc_18000AAC9
0x18000aabe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aac3  mov     [rbp+1400h+var_1460], rax
0x18000aac7  jmp     short loc_18000AACD
0x18000aac9  mov     [rbp+1400h+var_1460], r12
0x18000aacd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000aad4  test    rax, rax
0x18000aad7  jz      short loc_18000AAE3
0x18000aad9  lea     rcx, [rsp+1500h+var_14E0]
0x18000aade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aae3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000aaea  test    rax, rax
0x18000aaed  jz      short loc_18000AB03
0x18000aaef  mov     r8d, 400h
0x18000aaf5  lea     rdx, [rbp+1400h+var_1440]
0x18000aaf9  lea     rcx, [rsp+1500h+var_14E0]
0x18000aafe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab03  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ab0a  test    rax, rax
0x18000ab0d  jz      short loc_18000AB19
0x18000ab0f  lea     rcx, [rsp+1500h+var_14E0]
0x18000ab14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab19  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ab20  test    rax, rax
0x18000ab23  jz      short loc_18000AB36
0x18000ab25  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000ab2a  jnz     short loc_18000AB36
0x18000ab2c  lea     rcx, [rsp+1500h+var_14E0]
0x18000ab31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab36  cmp     [rsp+1500h+var_14D8], r12d
0x18000ab3b  jge     loc_18000AC44
0x18000ab41  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000ab48  jnz     short loc_18000AB69
0x18000ab4a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000ab51  test    rax, rax
0x18000ab54  jz      short loc_18000AB5F
0x18000ab56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab5b  test    al, al
0x18000ab5d  jmp     short loc_18000AB67
0x18000ab5f  call    cs:__imp_IsDebuggerPresent
0x18000ab65  test    eax, eax
0x18000ab67  jz      short loc_18000AB70
0x18000ab69  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000ab6e  jz      short loc_18000AB96
0x18000ab70  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ab77  test    rax, rax
0x18000ab7a  jz      short loc_18000ABEF
0x18000ab7c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000ab83  jnz     short loc_18000ABEF
0x18000ab85  xor     r8d, r8d
0x18000ab88  xor     edx, edx
0x18000ab8a  lea     rcx, [rsp+1500h+var_14E0]
0x18000ab8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab94  jmp     short loc_18000ABEF
0x18000ab96  mov     ebx, 800h
0x18000ab9b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000aba2  test    rax, rax
0x18000aba5  jz      short loc_18000ABC4
0x18000aba7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000abae  jnz     short loc_18000ABC4
0x18000abb0  mov     r8d, ebx
0x18000abb3  lea     rdx, [rbp+1400h+OutputString]
0x18000abba  lea     rcx, [rsp+1500h+var_14E0]
0x18000abbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abc4  cmp     [rbp+1400h+OutputString], r12w
0x18000abcc  jnz     short loc_18000ABE2
0x18000abce  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000abd3  mov     rdx, rbx; unsigned __int16 *
0x18000abd6  lea     rcx, [rbp+1400h+OutputString]; this
0x18000abdd  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000abe2  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000abe9  call    cs:__imp_OutputDebugStringW
0x18000abef  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000abf4  jnz     short loc_18000ABFF
0x18000abf6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000abfd  jz      short loc_18000AC11
0x18000abff  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000ac06  test    rax, rax
0x18000ac09  jz      short loc_18000AC11
0x18000ac0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac10  nop
0x18000ac11  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000ac16  jnz     short loc_18000AC39
0x18000ac18  mov     rcx, [rbp+1400h+var_40]
0x18000ac1f  xor     rcx, rsp; StackCookie
0x18000ac22  call    __security_check_cookie
0x18000ac27  add     rsp, 14D0h
0x18000ac2e  pop     r15
0x18000ac30  pop     r14
0x18000ac32  pop     r12
0x18000ac34  pop     rdi
0x18000ac35  pop     rsi
0x18000ac36  pop     rbx
0x18000ac37  pop     rbp
0x18000ac38  retn
0x18000ac39  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000ac3e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000ac44  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
