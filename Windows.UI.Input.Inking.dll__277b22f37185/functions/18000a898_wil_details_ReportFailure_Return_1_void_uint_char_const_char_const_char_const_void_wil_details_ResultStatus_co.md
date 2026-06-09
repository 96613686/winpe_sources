# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000a898`
- end: `0x18000ab3e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000a528`

## callees

- `0x1800062a0`
- `0x180006f00`
- `0x18000a898`
- `0x18000e9b4`
- `0x18001229c`
- `0x180014798`
- `0x180014a30`
- `0x1800f8570`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a95e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a95e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000aa53`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000aa53`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000aadd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000aadd`

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
0x18000a898  push    rbp
0x18000a89a  push    rbx
0x18000a89b  push    rsi
0x18000a89c  push    rdi
0x18000a89d  push    r12
0x18000a89f  push    r14
0x18000a8a1  push    r15
0x18000a8a3  lea     rbp, [rsp-13D0h]
0x18000a8ab  mov     eax, 14D0h
0x18000a8b0  call    _alloca_probe
0x18000a8b5  sub     rsp, rax
0x18000a8b8  mov     rax, cs:__security_cookie
0x18000a8bf  xor     rax, rsp
0x18000a8c2  mov     [rbp+1400h+var_40], rax
0x18000a8c9  mov     rsi, r8
0x18000a8cc  mov     edi, edx
0x18000a8ce  mov     rbx, rcx
0x18000a8d1  mov     r14, [rbp+1400h+arg_28]
0x18000a8d8  xor     edx, edx; Val
0x18000a8da  mov     r8d, 98h; Size
0x18000a8e0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000a8e5  call    memset_0
0x18000a8ea  nop
0x18000a8eb  xor     r12d, r12d
0x18000a8ee  mov     [rbp+1400h+OutputString], r12w
0x18000a8f6  mov     [rbp+1400h+var_1440], r12b
0x18000a8fa  mov     rdx, [rbp+1400h+arg_30]; int
0x18000a901  mov     ecx, [rdx]; this
0x18000a903  mov     [rsp+1500h+var_14D8], ecx
0x18000a907  mov     eax, [rdx+4]
0x18000a90a  mov     [rsp+1500h+var_14D4], eax
0x18000a90e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a913  mov     r15d, eax
0x18000a916  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000a91e  mov     ecx, r12d
0x18000a921  lea     eax, [r12+8]
0x18000a926  cmp     dword ptr [rdx+8], 1
0x18000a92a  cmovz   ecx, eax
0x18000a92d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000a931  lea     ecx, [rax-7]
0x18000a934  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a93c  inc     ecx
0x18000a93e  mov     [rsp+1500h+var_14D0], ecx
0x18000a942  mov     rcx, [rbp+1400h+arg_38]
0x18000a949  test    rcx, rcx
0x18000a94c  jz      short loc_18000A959
0x18000a94e  cmp     [rcx], r12w
0x18000a952  mov     [rsp+1500h+var_14C8], rcx
0x18000a957  jnz     short loc_18000A95E
0x18000a959  mov     [rsp+1500h+var_14C8], r12
0x18000a95e  call    cs:__imp_GetCurrentThreadId
0x18000a964  mov     [rsp+1500h+var_14C0], eax
0x18000a968  mov     [rsp+1500h+var_14A8], rsi
0x18000a96d  mov     [rsp+1500h+var_14A0], edi
0x18000a971  mov     [rsp+1500h+var_149C], r15d
0x18000a976  mov     [rsp+1500h+var_14B8], r12
0x18000a97b  mov     [rsp+1500h+var_14B0], r12
0x18000a980  mov     [rbp+1400h+var_1458], r14
0x18000a984  mov     [rbp+1400h+var_1450], rbx
0x18000a988  mov     [rsp+1500h+var_1498], r12
0x18000a98d  xorps   xmm0, xmm0
0x18000a990  xor     eax, eax
0x18000a992  movups  [rbp+1400h+var_1478], xmm0
0x18000a996  mov     [rbp+1400h+var_1468], rax
0x18000a99a  xorps   xmm1, xmm1
0x18000a99d  movups  [rsp+1500h+var_1490], xmm1
0x18000a9a2  mov     [rbp+1400h+var_1480], rax
0x18000a9a6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a9ad  test    rax, rax
0x18000a9b0  jz      short loc_18000A9BD
0x18000a9b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9b7  mov     [rbp+1400h+var_1460], rax
0x18000a9bb  jmp     short loc_18000A9C1
0x18000a9bd  mov     [rbp+1400h+var_1460], r12
0x18000a9c1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a9c8  test    rax, rax
0x18000a9cb  jz      short loc_18000A9D7
0x18000a9cd  lea     rcx, [rsp+1500h+var_14E0]
0x18000a9d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9d7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a9de  test    rax, rax
0x18000a9e1  jz      short loc_18000A9F7
0x18000a9e3  mov     r8d, 400h
0x18000a9e9  lea     rdx, [rbp+1400h+var_1440]
0x18000a9ed  lea     rcx, [rsp+1500h+var_14E0]
0x18000a9f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9f7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a9fe  test    rax, rax
0x18000aa01  jz      short loc_18000AA0D
0x18000aa03  lea     rcx, [rsp+1500h+var_14E0]
0x18000aa08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa0d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000aa14  test    rax, rax
0x18000aa17  jz      short loc_18000AA2A
0x18000aa19  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000aa1e  jnz     short loc_18000AA2A
0x18000aa20  lea     rcx, [rsp+1500h+var_14E0]
0x18000aa25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa2a  cmp     [rsp+1500h+var_14D8], r12d
0x18000aa2f  jge     loc_18000AB38
0x18000aa35  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000aa3c  jnz     short loc_18000AA5D
0x18000aa3e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000aa45  test    rax, rax
0x18000aa48  jz      short loc_18000AA53
0x18000aa4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa4f  test    al, al
0x18000aa51  jmp     short loc_18000AA5B
0x18000aa53  call    cs:__imp_IsDebuggerPresent
0x18000aa59  test    eax, eax
0x18000aa5b  jz      short loc_18000AA64
0x18000aa5d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000aa62  jz      short loc_18000AA8A
0x18000aa64  mov     rax, cs:g_pfnResultLoggingCallback
0x18000aa6b  test    rax, rax
0x18000aa6e  jz      short loc_18000AAE3
0x18000aa70  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000aa77  jnz     short loc_18000AAE3
0x18000aa79  xor     r8d, r8d
0x18000aa7c  xor     edx, edx
0x18000aa7e  lea     rcx, [rsp+1500h+var_14E0]
0x18000aa83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa88  jmp     short loc_18000AAE3
0x18000aa8a  mov     ebx, 800h
0x18000aa8f  mov     rax, cs:g_pfnResultLoggingCallback
0x18000aa96  test    rax, rax
0x18000aa99  jz      short loc_18000AAB8
0x18000aa9b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000aaa2  jnz     short loc_18000AAB8
0x18000aaa4  mov     r8d, ebx
0x18000aaa7  lea     rdx, [rbp+1400h+OutputString]
0x18000aaae  lea     rcx, [rsp+1500h+var_14E0]
0x18000aab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aab8  cmp     [rbp+1400h+OutputString], r12w
0x18000aac0  jnz     short loc_18000AAD6
0x18000aac2  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000aac7  mov     rdx, rbx; unsigned __int16 *
0x18000aaca  lea     rcx, [rbp+1400h+OutputString]; this
0x18000aad1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000aad6  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000aadd  call    cs:__imp_OutputDebugStringW
0x18000aae3  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000aae8  jnz     short loc_18000AAF3
0x18000aaea  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000aaf1  jz      short loc_18000AB05
0x18000aaf3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000aafa  test    rax, rax
0x18000aafd  jz      short loc_18000AB05
0x18000aaff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab04  nop
0x18000ab05  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000ab0a  jnz     short loc_18000AB2D
0x18000ab0c  mov     rcx, [rbp+1400h+var_40]
0x18000ab13  xor     rcx, rsp; StackCookie
0x18000ab16  call    __security_check_cookie
0x18000ab1b  add     rsp, 14D0h
0x18000ab22  pop     r15
0x18000ab24  pop     r14
0x18000ab26  pop     r12
0x18000ab28  pop     rdi
0x18000ab29  pop     rsi
0x18000ab2a  pop     rbx
0x18000ab2b  pop     rbp
0x18000ab2c  retn
0x18000ab2d  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000ab32  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000ab38  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
