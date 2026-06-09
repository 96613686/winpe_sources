# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003dd0`
- end: `0x18000405b`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003a90`

## callees

- `0x180003dd0`
- `0x180006ca0`
- `0x18001510c`
- `0x18001b238`
- `0x18001b4c8`
- `0x18002d1ee`
- `0x18002d220`
- `0x18002d2b0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e7d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003f71`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003f71`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003ffb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003ffb`

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
0x180003dd0  push    rbp
0x180003dd2  push    rbx
0x180003dd3  push    rsi
0x180003dd4  push    rdi
0x180003dd5  push    r12
0x180003dd7  push    r14
0x180003dd9  push    r15
0x180003ddb  lea     rbp, [rsp-13D0h]
0x180003de3  mov     eax, 14D0h
0x180003de8  call    _alloca_probe
0x180003ded  sub     rsp, rax
0x180003df0  mov     rax, cs:__security_cookie
0x180003df7  xor     rax, rsp
0x180003dfa  mov     [rbp+1400h+var_40], rax
0x180003e01  mov     rdi, [rbp+1400h+arg_28]
0x180003e08  mov     r14, r8
0x180003e0b  mov     esi, edx
0x180003e0d  mov     r15, rcx
0x180003e10  xor     edx, edx; Val
0x180003e12  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003e17  mov     r8d, 98h; Size
0x180003e1d  call    memset_0
0x180003e22  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180003e29  xor     r12d, r12d
0x180003e2c  mov     [rbp+1400h+OutputString], r12w
0x180003e34  mov     [rbp+1400h+var_1440], r12b
0x180003e38  mov     ecx, [rdx]; this
0x180003e3a  mov     eax, [rdx+4]
0x180003e3d  mov     [rsp+1500h+var_14D8], ecx
0x180003e41  mov     [rsp+1500h+var_14D4], eax
0x180003e45  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003e4a  cmp     dword ptr [rdx+8], 1
0x180003e4e  mov     ebx, eax
0x180003e50  lea     eax, [r12+8]
0x180003e55  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003e5d  mov     ecx, r12d
0x180003e60  cmovz   ecx, eax
0x180003e63  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003e67  lea     ecx, [rax-7]
0x180003e6a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003e72  inc     ecx
0x180003e74  mov     [rsp+1500h+var_14C8], r12
0x180003e79  mov     [rsp+1500h+var_14D0], ecx
0x180003e7d  call    cs:__imp_GetCurrentThreadId
0x180003e83  xorps   xmm0, xmm0
0x180003e86  mov     [rsp+1500h+var_14A8], r14
0x180003e8b  mov     [rsp+1500h+var_14C0], eax
0x180003e8f  xorps   xmm1, xmm1
0x180003e92  xor     eax, eax
0x180003e94  mov     [rsp+1500h+var_14A0], esi
0x180003e98  mov     [rbp+1400h+var_1468], rax
0x180003e9c  mov     [rbp+1400h+var_1480], rax
0x180003ea0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003ea7  mov     [rsp+1500h+var_149C], ebx
0x180003eab  mov     [rsp+1500h+var_14B8], r12
0x180003eb0  mov     [rsp+1500h+var_14B0], r12
0x180003eb5  mov     [rbp+1400h+var_1458], rdi
0x180003eb9  mov     [rbp+1400h+var_1450], r15
0x180003ebd  mov     [rsp+1500h+var_1498], r12
0x180003ec2  movups  [rbp+1400h+var_1478], xmm0
0x180003ec6  movups  [rsp+1500h+var_1490], xmm1
0x180003ecb  test    rax, rax
0x180003ece  jz      short loc_180003EDB
0x180003ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ed5  mov     [rbp+1400h+var_1460], rax
0x180003ed9  jmp     short loc_180003EDF
0x180003edb  mov     [rbp+1400h+var_1460], r12
0x180003edf  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003ee6  test    rax, rax
0x180003ee9  jz      short loc_180003EF5
0x180003eeb  lea     rcx, [rsp+1500h+var_14E0]
0x180003ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ef5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003efc  test    rax, rax
0x180003eff  jz      short loc_180003F15
0x180003f01  mov     r8d, 400h
0x180003f07  lea     rdx, [rbp+1400h+var_1440]
0x180003f0b  lea     rcx, [rsp+1500h+var_14E0]
0x180003f10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f15  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003f1c  test    rax, rax
0x180003f1f  jz      short loc_180003F2B
0x180003f21  lea     rcx, [rsp+1500h+var_14E0]
0x180003f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f2b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003f32  test    rax, rax
0x180003f35  jz      short loc_180003F48
0x180003f37  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003f3c  jnz     short loc_180003F48
0x180003f3e  lea     rcx, [rsp+1500h+var_14E0]
0x180003f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f48  cmp     [rsp+1500h+var_14D8], r12d
0x180003f4d  jge     loc_18000404A
0x180003f53  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003f5a  jnz     short loc_180003F7B
0x180003f5c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003f63  test    rax, rax
0x180003f66  jz      short loc_180003F71
0x180003f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f6d  test    al, al
0x180003f6f  jmp     short loc_180003F79
0x180003f71  call    cs:__imp_IsDebuggerPresent
0x180003f77  test    eax, eax
0x180003f79  jz      short loc_180003F82
0x180003f7b  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003f80  jz      short loc_180003FA8
0x180003f82  mov     rax, cs:g_pfnResultLoggingCallback
0x180003f89  test    rax, rax
0x180003f8c  jz      short loc_180004001
0x180003f8e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003f95  jnz     short loc_180004001
0x180003f97  xor     r8d, r8d
0x180003f9a  lea     rcx, [rsp+1500h+var_14E0]
0x180003f9f  xor     edx, edx
0x180003fa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fa6  jmp     short loc_180004001
0x180003fa8  mov     rax, cs:g_pfnResultLoggingCallback
0x180003faf  mov     ebx, 800h
0x180003fb4  test    rax, rax
0x180003fb7  jz      short loc_180003FD6
0x180003fb9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003fc0  jnz     short loc_180003FD6
0x180003fc2  mov     r8d, ebx
0x180003fc5  lea     rdx, [rbp+1400h+OutputString]
0x180003fcc  lea     rcx, [rsp+1500h+var_14E0]
0x180003fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fd6  cmp     [rbp+1400h+OutputString], r12w
0x180003fde  jnz     short loc_180003FF4
0x180003fe0  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003fe5  mov     rdx, rbx; unsigned __int16 *
0x180003fe8  lea     rcx, [rbp+1400h+OutputString]; this
0x180003fef  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003ff4  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003ffb  call    cs:__imp_OutputDebugStringW
0x180004001  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004006  jnz     short loc_180004011
0x180004008  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000400f  jz      short loc_180004022
0x180004011  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004018  test    rax, rax
0x18000401b  jz      short loc_180004022
0x18000401d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004022  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180004027  jnz     short loc_180004050
0x180004029  mov     rcx, [rbp+1400h+var_40]
0x180004030  xor     rcx, rsp; StackCookie
0x180004033  call    __security_check_cookie
0x180004038  add     rsp, 14D0h
0x18000403f  pop     r15
0x180004041  pop     r14
0x180004043  pop     r12
0x180004045  pop     rdi
0x180004046  pop     rsi
0x180004047  pop     rbx
0x180004048  pop     rbp
0x180004049  retn
0x18000404a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004050  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004055  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
