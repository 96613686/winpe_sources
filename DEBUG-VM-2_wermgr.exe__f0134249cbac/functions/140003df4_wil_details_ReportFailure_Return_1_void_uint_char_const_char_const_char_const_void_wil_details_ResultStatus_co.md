# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140003df4`
- end: `0x140004089`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `661`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140003a8c`

## callees

- `0x140002fbc`
- `0x140003200`
- `0x140003df4`
- `0x140007298`
- `0x140009350`
- `0x14000d6ec`
- `0x14000d7c8`
- `0x14001c930`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003ea8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003ea8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003f9c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003f9c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004026`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004026`

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
  int v11; // ebx
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag4 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  __int64 v23; // [rsp+38h] [rbp-C8h]
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
  v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
  v25 = 0;
  v26 = a4;
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
    wil::details::in1diag4::_FailFastImmediate_Unexpected(v15);
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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v18, v16);
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
0x140003df4  push    rbp
0x140003df6  push    rbx
0x140003df7  push    rsi
0x140003df8  push    rdi
0x140003df9  push    r12
0x140003dfb  push    r13
0x140003dfd  push    r14
0x140003dff  push    r15
0x140003e01  lea     rbp, [rsp-13D8h]
0x140003e09  mov     eax, 14D8h
0x140003e0e  call    _alloca_probe
0x140003e13  sub     rsp, rax
0x140003e16  mov     rax, cs:__security_cookie
0x140003e1d  xor     rax, rsp
0x140003e20  mov     [rbp+1410h+var_50], rax
0x140003e27  mov     r12, r9
0x140003e2a  mov     r14, r8
0x140003e2d  mov     esi, edx
0x140003e2f  mov     r15, rcx
0x140003e32  mov     rdi, [rbp+1410h+arg_28]
0x140003e39  xor     edx, edx; Val
0x140003e3b  mov     r8d, 98h; Size
0x140003e41  lea     rcx, [rsp+1510h+var_14F0]; void *
0x140003e46  call    memset_0
0x140003e4b  nop
0x140003e4c  xor     r13d, r13d
0x140003e4f  mov     [rbp+1410h+OutputString], r13w
0x140003e57  mov     [rbp+1410h+var_1450], r13b
0x140003e5b  mov     rdx, qword ptr [rbp+1410h+arg_30]; int
0x140003e62  mov     ecx, [rdx]; this
0x140003e64  mov     [rsp+1510h+var_14E8], ecx
0x140003e68  mov     eax, [rdx+4]
0x140003e6b  mov     [rsp+1510h+var_14E4], eax
0x140003e6f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140003e74  mov     ebx, eax
0x140003e76  lea     r8d, [r13+1]
0x140003e7a  mov     dword ptr [rsp+1510h+var_14F0], r8d
0x140003e7f  mov     ecx, r13d
0x140003e82  lea     eax, [r13+8]
0x140003e86  cmp     [rdx+8], r8d
0x140003e8a  cmovz   ecx, eax
0x140003e8d  mov     dword ptr [rsp+1510h+var_14F0+4], ecx
0x140003e91  mov     ecx, r8d
0x140003e94  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003e9c  add     ecx, r8d
0x140003e9f  mov     [rsp+1510h+var_14E0], ecx
0x140003ea3  mov     [rsp+1510h+var_14D8], r13
0x140003ea8  call    cs:__imp_GetCurrentThreadId
0x140003eae  mov     [rsp+1510h+var_14D0], eax
0x140003eb2  mov     [rsp+1510h+var_14B8], r14
0x140003eb7  mov     [rsp+1510h+var_14B0], esi
0x140003ebb  mov     [rsp+1510h+var_14AC], ebx
0x140003ebf  mov     [rsp+1510h+var_14C8], r13
0x140003ec4  mov     [rsp+1510h+var_14C0], r12
0x140003ec9  mov     [rbp+1410h+var_1468], rdi
0x140003ecd  mov     [rbp+1410h+var_1460], r15
0x140003ed1  mov     [rsp+1510h+var_14A8], r13
0x140003ed6  xorps   xmm0, xmm0
0x140003ed9  xor     eax, eax
0x140003edb  movups  [rbp+1410h+var_1488], xmm0
0x140003edf  mov     [rbp+1410h+var_1478], rax
0x140003ee3  xorps   xmm1, xmm1
0x140003ee6  movups  [rsp+1510h+var_14A0], xmm1
0x140003eeb  mov     [rbp+1410h+var_1490], rax
0x140003eef  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003ef6  test    rax, rax
0x140003ef9  jz      short loc_140003F06
0x140003efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f00  mov     [rbp+1410h+var_1470], rax
0x140003f04  jmp     short loc_140003F0A
0x140003f06  mov     [rbp+1410h+var_1470], r13
0x140003f0a  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003f11  test    rax, rax
0x140003f14  jz      short loc_140003F20
0x140003f16  lea     rcx, [rsp+1510h+var_14F0]
0x140003f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f20  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003f27  test    rax, rax
0x140003f2a  jz      short loc_140003F40
0x140003f2c  mov     r8d, 400h
0x140003f32  lea     rdx, [rbp+1410h+var_1450]
0x140003f36  lea     rcx, [rsp+1510h+var_14F0]
0x140003f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f40  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003f47  test    rax, rax
0x140003f4a  jz      short loc_140003F56
0x140003f4c  lea     rcx, [rsp+1510h+var_14F0]
0x140003f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f56  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003f5d  test    rax, rax
0x140003f60  jz      short loc_140003F73
0x140003f62  test    byte ptr [rsp+1510h+var_14F0+4], 2
0x140003f67  jnz     short loc_140003F73
0x140003f69  lea     rcx, [rsp+1510h+var_14F0]
0x140003f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f73  cmp     [rsp+1510h+var_14E8], r13d
0x140003f78  jge     loc_140004083
0x140003f7e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140003f85  jnz     short loc_140003FA6
0x140003f87  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003f8e  test    rax, rax
0x140003f91  jz      short loc_140003F9C
0x140003f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f98  test    al, al
0x140003f9a  jmp     short loc_140003FA4
0x140003f9c  call    cs:__imp_IsDebuggerPresent
0x140003fa2  test    eax, eax
0x140003fa4  jz      short loc_140003FAD
0x140003fa6  test    byte ptr [rsp+1510h+var_14F0+4], 2
0x140003fab  jz      short loc_140003FD3
0x140003fad  mov     rax, cs:g_pfnResultLoggingCallback
0x140003fb4  test    rax, rax
0x140003fb7  jz      short loc_14000402C
0x140003fb9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140003fc0  jnz     short loc_14000402C
0x140003fc2  xor     r8d, r8d
0x140003fc5  xor     edx, edx
0x140003fc7  lea     rcx, [rsp+1510h+var_14F0]
0x140003fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003fd1  jmp     short loc_14000402C
0x140003fd3  mov     ebx, 800h
0x140003fd8  mov     rax, cs:g_pfnResultLoggingCallback
0x140003fdf  test    rax, rax
0x140003fe2  jz      short loc_140004001
0x140003fe4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140003feb  jnz     short loc_140004001
0x140003fed  mov     r8d, ebx
0x140003ff0  lea     rdx, [rbp+1410h+OutputString]
0x140003ff7  lea     rcx, [rsp+1510h+var_14F0]
0x140003ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004001  cmp     [rbp+1410h+OutputString], r13w
0x140004009  jnz     short loc_14000401F
0x14000400b  lea     r8, [rsp+1510h+var_14F0]; unsigned __int64
0x140004010  mov     rdx, rbx; wchar_t *
0x140004013  lea     rcx, [rbp+1410h+OutputString]; this
0x14000401a  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x14000401f  lea     rcx, [rbp+1410h+OutputString]; lpOutputString
0x140004026  call    cs:__imp_OutputDebugStringW
0x14000402c  test    byte ptr [rsp+1510h+var_14F0+4], 4
0x140004031  jnz     short loc_14000403C
0x140004033  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x14000403a  jz      short loc_14000404E
0x14000403c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140004043  test    rax, rax
0x140004046  jz      short loc_14000404E
0x140004048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000404d  nop
0x14000404e  test    byte ptr [rsp+1510h+var_14F0+4], 1
0x140004053  jnz     short loc_140004078
0x140004055  mov     rcx, [rbp+1410h+var_50]
0x14000405c  xor     rcx, rsp; StackCookie
0x14000405f  call    __security_check_cookie
0x140004064  add     rsp, 14D8h
0x14000406b  pop     r15
0x14000406d  pop     r14
0x14000406f  pop     r13
0x140004071  pop     r12
0x140004073  pop     rdi
0x140004074  pop     rsi
0x140004075  pop     rbx
0x140004076  pop     rbp
0x140004077  retn
0x140004078  lea     rcx, [rsp+1510h+var_14F0]; this
0x14000407d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140004083  call    ?_FailFastImmediate_Unexpected@in1diag4@details@wil@@YAXXZ; wil::details::in1diag4::_FailFastImmediate_Unexpected(void)
```
