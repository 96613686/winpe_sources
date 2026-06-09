# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800139cc`
- end: `0x180013cc4`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800131b8`

## callees

- `0x180007660`
- `0x18000856c`
- `0x1800133d4`
- `0x1800139cc`
- `0x180015e04`
- `0x180016650`
- `0x18001748c`
- `0x180019bc0`
- `0x180019e38`
- `0x180068320`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013ae5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013ae5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180013bd8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180013bd8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180013c61`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180013c61`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<2>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8,
        int a9,
        int a10)
{
  int v14; // edx
  int v15; // ebx
  int v16; // edx
  int v17; // ebx
  const struct wil::FailureInfo *v18; // rdx
  wil::details::in1diag3 *v19; // rcx
  const struct wil::FailureInfo *v20; // r9
  bool v21; // zf
  wil::details *v22; // [rsp+30h] [rbp-D0h]
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+54h] [rbp-ACh]
  int v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+5Ch] [rbp-A4h]
  signed __int32 v27; // [rsp+60h] [rbp-A0h]
  _WORD *v28; // [rsp+68h] [rbp-98h]
  DWORD CurrentThreadId; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+78h] [rbp-88h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int64 v32; // [rsp+88h] [rbp-78h]
  int v33; // [rsp+90h] [rbp-70h]
  int v34; // [rsp+94h] [rbp-6Ch]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int128 v36; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  __int128 v38; // [rsp+B8h] [rbp-48h]
  __int64 v39; // [rsp+C8h] [rbp-38h]
  __int64 ModuleName; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  __int64 v42; // [rsp+E0h] [rbp-20h]
  char v43[1024]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR OutputString[2048]; // [rsp+4F0h] [rbp+3F0h] BYREF

  memset_0(&v23, 0, 0x98u);
  OutputString[0] = 0;
  v43[0] = 0;
  v15 = *a7;
  v25 = v15;
  v26 = a7[1];
  if ( v15 >= 0 )
  {
    v15 = -2147024228;
    LODWORD(v22) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v22);
    v25 = -2147024228;
    v26 = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v16);
  }
  v17 = wil::details::RecordLog((wil::details *)(unsigned int)v15, v14);
  v23 = 2;
  v24 = a10;
  if ( a7[2] == 1 )
    v24 = a10 | 8;
  v27 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v21 = *a8 == 0, v28 = a8, v21) )
    v28 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v32 = a3;
  v33 = a2;
  v34 = v17;
  v30 = a5;
  v31 = a4;
  v41 = a6;
  v42 = a1;
  v35 = 0;
  v38 = 0;
  v39 = 0;
  v36 = 0;
  v37 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v23);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v23, v43, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v23);
  if ( wil::details::g_pfnOriginateCallback && (v24 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v23);
  if ( v25 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v21 = !IsDebuggerPresent())
      : (v21 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v21)
    || (v24 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, 0, 0, v20);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, OutputString, 2048, v20);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v23, v20);
    OutputDebugStringW(OutputString);
  }
  if ( ((v24 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak();
  if ( (v24 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v23, v18);
}

```

## disassembly

```asm
0x1800139cc  push    rbp
0x1800139ce  push    rbx
0x1800139cf  push    rsi
0x1800139d0  push    rdi
0x1800139d1  push    r12
0x1800139d3  push    r13
0x1800139d5  push    r14
0x1800139d7  push    r15
0x1800139d9  lea     rbp, [rsp-1408h]
0x1800139e1  mov     eax, 1508h
0x1800139e6  call    _alloca_probe
0x1800139eb  sub     rsp, rax
0x1800139ee  mov     rax, cs:__security_cookie
0x1800139f5  xor     rax, rsp
0x1800139f8  mov     [rbp+1440h+var_50], rax
0x1800139ff  mov     r12, r9
0x180013a02  mov     r15, r8
0x180013a05  mov     r14d, edx
0x180013a08  mov     rsi, rcx
0x180013a0b  mov     r13, [rbp+1440h+arg_20]
0x180013a12  mov     rax, [rbp+1440h+arg_28]
0x180013a19  mov     [rsp+1540h+var_1500], rax
0x180013a1e  xor     edx, edx; Val
0x180013a20  mov     r8d, 98h; Size
0x180013a26  lea     rcx, [rsp+1540h+var_14F0]; void *
0x180013a2b  call    memset_0
0x180013a30  nop
0x180013a31  xor     eax, eax
0x180013a33  mov     [rbp+1440h+OutputString], ax
0x180013a3a  mov     [rbp+1440h+var_1450], al
0x180013a3d  mov     rdi, [rbp+1440h+arg_30]
0x180013a44  mov     ebx, [rdi]
0x180013a46  mov     [rsp+1540h+var_14E8], ebx
0x180013a4a  mov     eax, [rdi+4]
0x180013a4d  mov     [rsp+1540h+var_14E4], eax
0x180013a51  test    ebx, ebx
0x180013a53  js      short loc_180013A8D
0x180013a55  mov     ebx, 8007029Ch
0x180013a5a  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x180013a5e  mov     rax, [rsp+1540h+var_1500]
0x180013a63  mov     [rsp+1540h+var_1518], rax; __int64
0x180013a68  mov     [rsp+1540h+var_1520], r13; __int64
0x180013a6d  mov     r9, r12; int
0x180013a70  mov     r8, r15; int
0x180013a73  mov     edx, r14d; int
0x180013a76  mov     rcx, rsi; int
0x180013a79  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180013a7e  mov     [rsp+1540h+var_14E8], ebx
0x180013a82  mov     ecx, ebx; this
0x180013a84  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180013a89  mov     [rsp+1540h+var_14E4], eax
0x180013a8d  mov     ecx, ebx; this
0x180013a8f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180013a94  mov     ebx, eax
0x180013a96  mov     dword ptr [rsp+1540h+var_14F0], 2
0x180013a9e  mov     ecx, [rbp+1440h+arg_48]
0x180013aa4  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180013aa8  cmp     dword ptr [rdi+8], 1
0x180013aac  jnz     short loc_180013AB5
0x180013aae  or      ecx, 8
0x180013ab1  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180013ab5  mov     ecx, 1
0x180013aba  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180013ac2  inc     ecx
0x180013ac4  mov     [rsp+1540h+var_14E0], ecx
0x180013ac8  mov     rax, [rbp+1440h+arg_38]
0x180013acf  xor     edi, edi
0x180013ad1  test    rax, rax
0x180013ad4  jz      short loc_180013AE0
0x180013ad6  cmp     [rax], di
0x180013ad9  mov     [rsp+1540h+var_14D8], rax
0x180013ade  jnz     short loc_180013AE5
0x180013ae0  mov     [rsp+1540h+var_14D8], rdi
0x180013ae5  call    cs:__imp_GetCurrentThreadId
0x180013aeb  mov     [rsp+1540h+var_14D0], eax
0x180013aef  mov     [rbp+1440h+var_14B8], r15
0x180013af3  mov     [rbp+1440h+var_14B0], r14d
0x180013af7  mov     [rbp+1440h+var_14AC], ebx
0x180013afa  mov     [rsp+1540h+var_14C8], r13
0x180013aff  mov     [rbp+1440h+var_14C0], r12
0x180013b03  mov     rax, [rsp+1540h+var_1500]
0x180013b08  mov     [rbp+1440h+var_1468], rax
0x180013b0c  mov     [rbp+1440h+var_1460], rsi
0x180013b10  mov     [rbp+1440h+var_14A8], rdi
0x180013b14  xorps   xmm0, xmm0
0x180013b17  xor     eax, eax
0x180013b19  movups  [rbp+1440h+var_1488], xmm0
0x180013b1d  mov     [rbp+1440h+var_1478], rax
0x180013b21  xorps   xmm1, xmm1
0x180013b24  movups  [rbp+1440h+var_14A0], xmm1
0x180013b28  mov     [rbp+1440h+var_1490], rax
0x180013b2c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180013b33  test    rax, rax
0x180013b36  jz      short loc_180013B43
0x180013b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b3d  mov     [rbp+1440h+var_1470], rax
0x180013b41  jmp     short loc_180013B47
0x180013b43  mov     [rbp+1440h+var_1470], rdi
0x180013b47  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180013b4e  test    rax, rax
0x180013b51  jz      short loc_180013B5D
0x180013b53  lea     rcx, [rsp+1540h+var_14F0]
0x180013b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b5d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180013b64  test    rax, rax
0x180013b67  jz      short loc_180013B7D
0x180013b69  mov     r8d, 400h
0x180013b6f  lea     rdx, [rbp+1440h+var_1450]
0x180013b73  lea     rcx, [rsp+1540h+var_14F0]
0x180013b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b7d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180013b84  test    rax, rax
0x180013b87  jz      short loc_180013B93
0x180013b89  lea     rcx, [rsp+1540h+var_14F0]
0x180013b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b93  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180013b9a  test    rax, rax
0x180013b9d  jz      short loc_180013BB0
0x180013b9f  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180013ba4  jnz     short loc_180013BB0
0x180013ba6  lea     rcx, [rsp+1540h+var_14F0]
0x180013bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bb0  cmp     [rsp+1540h+var_14E8], edi
0x180013bb4  jge     loc_180013CBE
0x180013bba  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180013bc1  jnz     short loc_180013BE2
0x180013bc3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180013bca  test    rax, rax
0x180013bcd  jz      short loc_180013BD8
0x180013bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bd4  test    al, al
0x180013bd6  jmp     short loc_180013BE0
0x180013bd8  call    cs:__imp_IsDebuggerPresent
0x180013bde  test    eax, eax
0x180013be0  jz      short loc_180013BE9
0x180013be2  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180013be7  jz      short loc_180013C0F
0x180013be9  mov     rax, cs:g_pfnResultLoggingCallback
0x180013bf0  test    rax, rax
0x180013bf3  jz      short loc_180013C67
0x180013bf5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180013bfc  jnz     short loc_180013C67
0x180013bfe  xor     r8d, r8d
0x180013c01  xor     edx, edx
0x180013c03  lea     rcx, [rsp+1540h+var_14F0]
0x180013c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c0d  jmp     short loc_180013C67
0x180013c0f  mov     ebx, 800h
0x180013c14  mov     rax, cs:g_pfnResultLoggingCallback
0x180013c1b  test    rax, rax
0x180013c1e  jz      short loc_180013C3D
0x180013c20  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180013c27  jnz     short loc_180013C3D
0x180013c29  mov     r8d, ebx
0x180013c2c  lea     rdx, [rbp+1440h+OutputString]
0x180013c33  lea     rcx, [rsp+1540h+var_14F0]
0x180013c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c3d  cmp     [rbp+1440h+OutputString], di
0x180013c44  jnz     short loc_180013C5A
0x180013c46  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x180013c4b  mov     rdx, rbx; unsigned __int16 *
0x180013c4e  lea     rcx, [rbp+1440h+OutputString]; this
0x180013c55  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180013c5a  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x180013c61  call    cs:__imp_OutputDebugStringW
0x180013c67  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x180013c6c  jnz     short loc_180013C77
0x180013c6e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180013c75  jz      short loc_180013C89
0x180013c77  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180013c7e  test    rax, rax
0x180013c81  jz      short loc_180013C89
0x180013c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c88  nop
0x180013c89  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x180013c8e  jnz     short loc_180013CB3
0x180013c90  mov     rcx, [rbp+1440h+var_50]
0x180013c97  xor     rcx, rsp; StackCookie
0x180013c9a  call    __security_check_cookie
0x180013c9f  add     rsp, 1508h
0x180013ca6  pop     r15
0x180013ca8  pop     r14
0x180013caa  pop     r13
0x180013cac  pop     r12
0x180013cae  pop     rdi
0x180013caf  pop     rsi
0x180013cb0  pop     rbx
0x180013cb1  pop     rbp
0x180013cb2  retn
0x180013cb3  lea     rcx, [rsp+1540h+var_14F0]; this
0x180013cb8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180013cbe  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
