# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003d68`
- end: `0x18000400e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800037f8`

## callees

- `0x180002bc0`
- `0x18000354c`
- `0x180003d68`
- `0x180004fb4`
- `0x180005f90`
- `0x180007010`
- `0x180007198`
- `0x180010ba0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e2e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003fad`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003fad`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003f23`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003f23`

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
0x180003d68  push    rbp
0x180003d6a  push    rbx
0x180003d6b  push    rsi
0x180003d6c  push    rdi
0x180003d6d  push    r12
0x180003d6f  push    r14
0x180003d71  push    r15
0x180003d73  lea     rbp, [rsp-13D0h]
0x180003d7b  mov     eax, 14D0h
0x180003d80  call    _alloca_probe
0x180003d85  sub     rsp, rax
0x180003d88  mov     rax, cs:__security_cookie
0x180003d8f  xor     rax, rsp
0x180003d92  mov     [rbp+1400h+var_40], rax
0x180003d99  mov     rsi, r8
0x180003d9c  mov     edi, edx
0x180003d9e  mov     rbx, rcx
0x180003da1  mov     r14, [rbp+1400h+arg_28]
0x180003da8  xor     edx, edx; Val
0x180003daa  mov     r8d, 98h; Size
0x180003db0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003db5  call    memset_0
0x180003dba  nop
0x180003dbb  xor     r12d, r12d
0x180003dbe  mov     [rbp+1400h+OutputString], r12w
0x180003dc6  mov     [rbp+1400h+var_1440], r12b
0x180003dca  mov     rdx, [rbp+1400h+arg_30]; int
0x180003dd1  mov     ecx, [rdx]; this
0x180003dd3  mov     [rsp+1500h+var_14D8], ecx
0x180003dd7  mov     eax, [rdx+4]
0x180003dda  mov     [rsp+1500h+var_14D4], eax
0x180003dde  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003de3  mov     r15d, eax
0x180003de6  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003dee  mov     ecx, r12d
0x180003df1  lea     eax, [r12+8]
0x180003df6  cmp     dword ptr [rdx+8], 1
0x180003dfa  cmovz   ecx, eax
0x180003dfd  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003e01  lea     ecx, [rax-7]
0x180003e04  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003e0c  inc     ecx
0x180003e0e  mov     [rsp+1500h+var_14D0], ecx
0x180003e12  mov     rcx, [rbp+1400h+arg_38]
0x180003e19  test    rcx, rcx
0x180003e1c  jz      short loc_180003E29
0x180003e1e  cmp     [rcx], r12w
0x180003e22  mov     [rsp+1500h+var_14C8], rcx
0x180003e27  jnz     short loc_180003E2E
0x180003e29  mov     [rsp+1500h+var_14C8], r12
0x180003e2e  call    cs:__imp_GetCurrentThreadId
0x180003e34  mov     [rsp+1500h+var_14C0], eax
0x180003e38  mov     [rsp+1500h+var_14A8], rsi
0x180003e3d  mov     [rsp+1500h+var_14A0], edi
0x180003e41  mov     [rsp+1500h+var_149C], r15d
0x180003e46  mov     [rsp+1500h+var_14B8], r12
0x180003e4b  mov     [rsp+1500h+var_14B0], r12
0x180003e50  mov     [rbp+1400h+var_1458], r14
0x180003e54  mov     [rbp+1400h+var_1450], rbx
0x180003e58  mov     [rsp+1500h+var_1498], r12
0x180003e5d  xorps   xmm0, xmm0
0x180003e60  xor     eax, eax
0x180003e62  movups  [rbp+1400h+var_1478], xmm0
0x180003e66  mov     [rbp+1400h+var_1468], rax
0x180003e6a  xorps   xmm1, xmm1
0x180003e6d  movups  [rsp+1500h+var_1490], xmm1
0x180003e72  mov     [rbp+1400h+var_1480], rax
0x180003e76  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003e7d  test    rax, rax
0x180003e80  jz      short loc_180003E8D
0x180003e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e87  mov     [rbp+1400h+var_1460], rax
0x180003e8b  jmp     short loc_180003E91
0x180003e8d  mov     [rbp+1400h+var_1460], r12
0x180003e91  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003e98  test    rax, rax
0x180003e9b  jz      short loc_180003EA7
0x180003e9d  lea     rcx, [rsp+1500h+var_14E0]
0x180003ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ea7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003eae  test    rax, rax
0x180003eb1  jz      short loc_180003EC7
0x180003eb3  mov     r8d, 400h
0x180003eb9  lea     rdx, [rbp+1400h+var_1440]
0x180003ebd  lea     rcx, [rsp+1500h+var_14E0]
0x180003ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ec7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003ece  test    rax, rax
0x180003ed1  jz      short loc_180003EDD
0x180003ed3  lea     rcx, [rsp+1500h+var_14E0]
0x180003ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003edd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003ee4  test    rax, rax
0x180003ee7  jz      short loc_180003EFA
0x180003ee9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003eee  jnz     short loc_180003EFA
0x180003ef0  lea     rcx, [rsp+1500h+var_14E0]
0x180003ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003efa  cmp     [rsp+1500h+var_14D8], r12d
0x180003eff  jge     loc_180004008
0x180003f05  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003f0c  jnz     short loc_180003F2D
0x180003f0e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003f15  test    rax, rax
0x180003f18  jz      short loc_180003F23
0x180003f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f1f  test    al, al
0x180003f21  jmp     short loc_180003F2B
0x180003f23  call    cs:__imp_IsDebuggerPresent
0x180003f29  test    eax, eax
0x180003f2b  jz      short loc_180003F34
0x180003f2d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003f32  jz      short loc_180003F5A
0x180003f34  mov     rax, cs:g_pfnResultLoggingCallback
0x180003f3b  test    rax, rax
0x180003f3e  jz      short loc_180003FB3
0x180003f40  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003f47  jnz     short loc_180003FB3
0x180003f49  xor     r8d, r8d
0x180003f4c  xor     edx, edx
0x180003f4e  lea     rcx, [rsp+1500h+var_14E0]
0x180003f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f58  jmp     short loc_180003FB3
0x180003f5a  mov     ebx, 800h
0x180003f5f  mov     rax, cs:g_pfnResultLoggingCallback
0x180003f66  test    rax, rax
0x180003f69  jz      short loc_180003F88
0x180003f6b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003f72  jnz     short loc_180003F88
0x180003f74  mov     r8d, ebx
0x180003f77  lea     rdx, [rbp+1400h+OutputString]
0x180003f7e  lea     rcx, [rsp+1500h+var_14E0]
0x180003f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f88  cmp     [rbp+1400h+OutputString], r12w
0x180003f90  jnz     short loc_180003FA6
0x180003f92  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003f97  mov     rdx, rbx; unsigned __int16 *
0x180003f9a  lea     rcx, [rbp+1400h+OutputString]; this
0x180003fa1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003fa6  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003fad  call    cs:__imp_OutputDebugStringW
0x180003fb3  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003fb8  jnz     short loc_180003FC3
0x180003fba  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003fc1  jz      short loc_180003FD5
0x180003fc3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003fca  test    rax, rax
0x180003fcd  jz      short loc_180003FD5
0x180003fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fd4  nop
0x180003fd5  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003fda  jnz     short loc_180003FFD
0x180003fdc  mov     rcx, [rbp+1400h+var_40]
0x180003fe3  xor     rcx, rsp; StackCookie
0x180003fe6  call    __security_check_cookie
0x180003feb  add     rsp, 14D0h
0x180003ff2  pop     r15
0x180003ff4  pop     r14
0x180003ff6  pop     r12
0x180003ff8  pop     rdi
0x180003ff9  pop     rsi
0x180003ffa  pop     rbx
0x180003ffb  pop     rbp
0x180003ffc  retn
0x180003ffd  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004002  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004008  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
