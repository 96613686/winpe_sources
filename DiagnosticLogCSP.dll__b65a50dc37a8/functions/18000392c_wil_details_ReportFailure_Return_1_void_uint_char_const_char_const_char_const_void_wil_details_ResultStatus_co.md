# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000392c`
- end: `0x180003bcc`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `672`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800033f0`

## callees

- `0x180001b90`
- `0x18000265c`
- `0x18000392c`
- `0x1800047a4`
- `0x1800059b4`
- `0x18000689c`
- `0x180006978`
- `0x180036fe0`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800039da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800039da`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003b64`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003b64`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003ad4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003ad4`

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
        int *a7)
{
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x18000392c  push    rbp
0x18000392e  push    rbx
0x18000392f  push    rsi
0x180003930  push    rdi
0x180003931  push    r12
0x180003933  push    r14
0x180003935  push    r15
0x180003937  lea     rbp, [rsp-13D0h]
0x18000393f  mov     eax, 14D0h
0x180003944  call    _alloca_probe
0x180003949  sub     rsp, rax
0x18000394c  mov     rax, cs:__security_cookie
0x180003953  xor     rax, rsp
0x180003956  mov     [rbp+1400h+var_40], rax
0x18000395d  mov     r14, r8
0x180003960  mov     esi, edx
0x180003962  mov     r15, rcx
0x180003965  mov     rdi, [rbp+1400h+arg_28]
0x18000396c  xor     edx, edx; Val
0x18000396e  mov     r8d, 98h; Size
0x180003974  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003979  call    memset_0
0x18000397e  nop
0x18000397f  xor     r12d, r12d
0x180003982  mov     [rbp+1400h+OutputString], r12w
0x18000398a  mov     [rbp+1400h+var_1440], r12b
0x18000398e  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180003995  mov     ecx, [rdx]; this
0x180003997  mov     [rsp+1500h+var_14D8], ecx
0x18000399b  mov     eax, [rdx+4]
0x18000399e  mov     [rsp+1500h+var_14D4], eax
0x1800039a2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800039a7  mov     ebx, eax
0x1800039a9  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800039b1  mov     ecx, r12d
0x1800039b4  lea     eax, [r12+8]
0x1800039b9  cmp     dword ptr [rdx+8], 1
0x1800039bd  cmovz   ecx, eax
0x1800039c0  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800039c4  lea     ecx, [rax-7]
0x1800039c7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800039cf  inc     ecx
0x1800039d1  mov     [rsp+1500h+var_14D0], ecx
0x1800039d5  mov     [rsp+1500h+var_14C8], r12
0x1800039da  call    cs:__imp_GetCurrentThreadId
0x1800039e1  nop     dword ptr [rax+rax+00h]
0x1800039e6  mov     [rsp+1500h+var_14C0], eax
0x1800039ea  mov     [rsp+1500h+var_14A8], r14
0x1800039ef  mov     [rsp+1500h+var_14A0], esi
0x1800039f3  mov     [rsp+1500h+var_149C], ebx
0x1800039f7  mov     [rsp+1500h+var_14B8], r12
0x1800039fc  mov     [rsp+1500h+var_14B0], r12
0x180003a01  mov     [rbp+1400h+var_1458], rdi
0x180003a05  mov     [rbp+1400h+var_1450], r15
0x180003a09  mov     [rsp+1500h+var_1498], r12
0x180003a0e  xorps   xmm0, xmm0
0x180003a11  xor     eax, eax
0x180003a13  movups  [rbp+1400h+var_1478], xmm0
0x180003a17  mov     [rbp+1400h+var_1468], rax
0x180003a1b  xorps   xmm1, xmm1
0x180003a1e  movups  [rsp+1500h+var_1490], xmm1
0x180003a23  mov     [rbp+1400h+var_1480], rax
0x180003a27  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003a2e  test    rax, rax
0x180003a31  jz      short loc_180003A3E
0x180003a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a38  mov     [rbp+1400h+var_1460], rax
0x180003a3c  jmp     short loc_180003A42
0x180003a3e  mov     [rbp+1400h+var_1460], r12
0x180003a42  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003a49  test    rax, rax
0x180003a4c  jz      short loc_180003A58
0x180003a4e  lea     rcx, [rsp+1500h+var_14E0]
0x180003a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a58  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003a5f  test    rax, rax
0x180003a62  jz      short loc_180003A78
0x180003a64  mov     r8d, 400h
0x180003a6a  lea     rdx, [rbp+1400h+var_1440]
0x180003a6e  lea     rcx, [rsp+1500h+var_14E0]
0x180003a73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a78  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003a7f  test    rax, rax
0x180003a82  jz      short loc_180003A8E
0x180003a84  lea     rcx, [rsp+1500h+var_14E0]
0x180003a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a8e  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003a95  test    rax, rax
0x180003a98  jz      short loc_180003AAB
0x180003a9a  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003a9f  jnz     short loc_180003AAB
0x180003aa1  lea     rcx, [rsp+1500h+var_14E0]
0x180003aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aab  cmp     [rsp+1500h+var_14D8], r12d
0x180003ab0  jge     loc_180003BC6
0x180003ab6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003abd  jnz     short loc_180003AE4
0x180003abf  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003ac6  test    rax, rax
0x180003ac9  jz      short loc_180003AD4
0x180003acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ad0  test    al, al
0x180003ad2  jmp     short loc_180003AE2
0x180003ad4  call    cs:__imp_IsDebuggerPresent
0x180003adb  nop     dword ptr [rax+rax+00h]
0x180003ae0  test    eax, eax
0x180003ae2  jz      short loc_180003AEB
0x180003ae4  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003ae9  jz      short loc_180003B11
0x180003aeb  mov     rax, cs:g_pfnResultLoggingCallback
0x180003af2  test    rax, rax
0x180003af5  jz      short loc_180003B70
0x180003af7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003afe  jnz     short loc_180003B70
0x180003b00  xor     r8d, r8d
0x180003b03  xor     edx, edx
0x180003b05  lea     rcx, [rsp+1500h+var_14E0]
0x180003b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b0f  jmp     short loc_180003B70
0x180003b11  mov     ebx, 800h
0x180003b16  mov     rax, cs:g_pfnResultLoggingCallback
0x180003b1d  test    rax, rax
0x180003b20  jz      short loc_180003B3F
0x180003b22  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003b29  jnz     short loc_180003B3F
0x180003b2b  mov     r8d, ebx
0x180003b2e  lea     rdx, [rbp+1400h+OutputString]
0x180003b35  lea     rcx, [rsp+1500h+var_14E0]
0x180003b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b3f  cmp     [rbp+1400h+OutputString], r12w
0x180003b47  jnz     short loc_180003B5D
0x180003b49  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003b4e  mov     rdx, rbx; unsigned __int16 *
0x180003b51  lea     rcx, [rbp+1400h+OutputString]; this
0x180003b58  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003b5d  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003b64  call    cs:__imp_OutputDebugStringW
0x180003b6b  nop     dword ptr [rax+rax+00h]
0x180003b70  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003b75  jnz     short loc_180003B80
0x180003b77  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003b7e  jz      short loc_180003B92
0x180003b80  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003b87  test    rax, rax
0x180003b8a  jz      short loc_180003B92
0x180003b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b91  nop
0x180003b92  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003b97  jnz     short loc_180003BBB
0x180003b99  mov     rcx, [rbp+1400h+var_40]
0x180003ba0  xor     rcx, rsp; StackCookie
0x180003ba3  call    __security_check_cookie
0x180003ba8  add     rsp, 14D0h
0x180003baf  pop     r15
0x180003bb1  pop     r14
0x180003bb3  pop     r12
0x180003bb5  pop     rdi
0x180003bb6  pop     rsi
0x180003bb7  pop     rbx
0x180003bb8  pop     rbp
0x180003bb9  retn
0x180003bbb  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003bc0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003bc6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
