# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140006ac8`
- end: `0x140006d53`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000658c`

## callees

- `0x140003620`
- `0x1400042c4`
- `0x140006ac8`
- `0x14000d4d8`
- `0x14001236c`
- `0x1400178c8`
- `0x140017d60`
- `0x14001e000`
- `0x14001f010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140006b75`
- `KERNEL32!GetCurrentThreadId` at `0x140006b75`
- `KERNEL32!OutputDebugStringW` at `0x140006cf3`
- `KERNEL32!OutputDebugStringW` at `0x140006cf3`
- `KERNEL32!IsDebuggerPresent` at `0x140006c69`
- `KERNEL32!IsDebuggerPresent` at `0x140006c69`

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
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // ebx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v22, (int)a7);
  v19 = *(_DWORD *)(v12 + 8) == 1;
  v13 = v11;
  v20 = 1;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x140006ac8  push    rbp
0x140006aca  push    rbx
0x140006acb  push    rsi
0x140006acc  push    rdi
0x140006acd  push    r12
0x140006acf  push    r14
0x140006ad1  push    r15
0x140006ad3  lea     rbp, [rsp-13D0h]
0x140006adb  mov     eax, 14D0h
0x140006ae0  call    _alloca_probe
0x140006ae5  sub     rsp, rax
0x140006ae8  mov     rax, cs:__security_cookie
0x140006aef  xor     rax, rsp
0x140006af2  mov     [rbp+1400h+var_40], rax
0x140006af9  mov     rdi, [rbp+1400h+arg_28]
0x140006b00  mov     r14, r8
0x140006b03  mov     esi, edx
0x140006b05  mov     r15, rcx
0x140006b08  xor     edx, edx; Val
0x140006b0a  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140006b0f  mov     r8d, 98h; Size
0x140006b15  call    memset_0
0x140006b1a  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x140006b21  xor     r12d, r12d
0x140006b24  mov     [rbp+1400h+OutputString], r12w
0x140006b2c  mov     [rbp+1400h+var_1440], r12b
0x140006b30  mov     ecx, [rdx]; this
0x140006b32  mov     eax, [rdx+4]
0x140006b35  mov     [rsp+1500h+var_14D8], ecx
0x140006b39  mov     [rsp+1500h+var_14D4], eax
0x140006b3d  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140006b42  cmp     dword ptr [rdx+8], 1
0x140006b46  mov     ebx, eax
0x140006b48  lea     eax, [r12+8]
0x140006b4d  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140006b55  mov     ecx, r12d
0x140006b58  cmovz   ecx, eax
0x140006b5b  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140006b5f  lea     ecx, [rax-7]
0x140006b62  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140006b6a  inc     ecx
0x140006b6c  mov     [rsp+1500h+var_14C8], r12
0x140006b71  mov     [rsp+1500h+var_14D0], ecx
0x140006b75  call    cs:__imp_GetCurrentThreadId
0x140006b7b  xorps   xmm0, xmm0
0x140006b7e  mov     [rsp+1500h+var_14A8], r14
0x140006b83  mov     [rsp+1500h+var_14C0], eax
0x140006b87  xorps   xmm1, xmm1
0x140006b8a  xor     eax, eax
0x140006b8c  mov     [rsp+1500h+var_14A0], esi
0x140006b90  mov     [rbp+1400h+var_1468], rax
0x140006b94  mov     [rbp+1400h+var_1480], rax
0x140006b98  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140006b9f  mov     [rsp+1500h+var_149C], ebx
0x140006ba3  mov     [rsp+1500h+var_14B8], r12
0x140006ba8  mov     [rsp+1500h+var_14B0], r12
0x140006bad  mov     [rbp+1400h+var_1458], rdi
0x140006bb1  mov     [rbp+1400h+var_1450], r15
0x140006bb5  mov     [rsp+1500h+var_1498], r12
0x140006bba  movups  [rbp+1400h+var_1478], xmm0
0x140006bbe  movups  [rsp+1500h+var_1490], xmm1
0x140006bc3  test    rax, rax
0x140006bc6  jz      short loc_140006BD3
0x140006bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006bcd  mov     [rbp+1400h+var_1460], rax
0x140006bd1  jmp     short loc_140006BD7
0x140006bd3  mov     [rbp+1400h+var_1460], r12
0x140006bd7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140006bde  test    rax, rax
0x140006be1  jz      short loc_140006BED
0x140006be3  lea     rcx, [rsp+1500h+var_14E0]
0x140006be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006bed  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140006bf4  test    rax, rax
0x140006bf7  jz      short loc_140006C0D
0x140006bf9  mov     r8d, 400h
0x140006bff  lea     rdx, [rbp+1400h+var_1440]
0x140006c03  lea     rcx, [rsp+1500h+var_14E0]
0x140006c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c0d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006c14  test    rax, rax
0x140006c17  jz      short loc_140006C23
0x140006c19  lea     rcx, [rsp+1500h+var_14E0]
0x140006c1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c23  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006c2a  test    rax, rax
0x140006c2d  jz      short loc_140006C40
0x140006c2f  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140006c34  jnz     short loc_140006C40
0x140006c36  lea     rcx, [rsp+1500h+var_14E0]
0x140006c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c40  cmp     [rsp+1500h+var_14D8], r12d
0x140006c45  jge     loc_140006D42
0x140006c4b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140006c52  jnz     short loc_140006C73
0x140006c54  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140006c5b  test    rax, rax
0x140006c5e  jz      short loc_140006C69
0x140006c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c65  test    al, al
0x140006c67  jmp     short loc_140006C71
0x140006c69  call    cs:__imp_IsDebuggerPresent
0x140006c6f  test    eax, eax
0x140006c71  jz      short loc_140006C7A
0x140006c73  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140006c78  jz      short loc_140006CA0
0x140006c7a  mov     rax, cs:g_pfnResultLoggingCallback
0x140006c81  test    rax, rax
0x140006c84  jz      short loc_140006CF9
0x140006c86  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140006c8d  jnz     short loc_140006CF9
0x140006c8f  xor     r8d, r8d
0x140006c92  lea     rcx, [rsp+1500h+var_14E0]
0x140006c97  xor     edx, edx
0x140006c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c9e  jmp     short loc_140006CF9
0x140006ca0  mov     rax, cs:g_pfnResultLoggingCallback
0x140006ca7  mov     ebx, 800h
0x140006cac  test    rax, rax
0x140006caf  jz      short loc_140006CCE
0x140006cb1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140006cb8  jnz     short loc_140006CCE
0x140006cba  mov     r8d, ebx
0x140006cbd  lea     rdx, [rbp+1400h+OutputString]
0x140006cc4  lea     rcx, [rsp+1500h+var_14E0]
0x140006cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006cce  cmp     [rbp+1400h+OutputString], r12w
0x140006cd6  jnz     short loc_140006CEC
0x140006cd8  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140006cdd  mov     rdx, rbx; unsigned __int16 *
0x140006ce0  lea     rcx, [rbp+1400h+OutputString]; this
0x140006ce7  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140006cec  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140006cf3  call    cs:__imp_OutputDebugStringW
0x140006cf9  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140006cfe  jnz     short loc_140006D09
0x140006d00  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140006d07  jz      short loc_140006D1A
0x140006d09  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140006d10  test    rax, rax
0x140006d13  jz      short loc_140006D1A
0x140006d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d1a  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140006d1f  jnz     short loc_140006D48
0x140006d21  mov     rcx, [rbp+1400h+var_40]
0x140006d28  xor     rcx, rsp; StackCookie
0x140006d2b  call    __security_check_cookie
0x140006d30  add     rsp, 14D0h
0x140006d37  pop     r15
0x140006d39  pop     r14
0x140006d3b  pop     r12
0x140006d3d  pop     rdi
0x140006d3e  pop     rsi
0x140006d3f  pop     rbx
0x140006d40  pop     rbp
0x140006d41  retn
0x140006d42  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140006d48  lea     rcx, [rsp+1500h+var_14E0]; this
0x140006d4d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
