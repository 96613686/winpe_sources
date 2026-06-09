# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000688c`
- end: `0x180006b84`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180006088`

## callees

- `0x180003a00`
- `0x1800044b8`
- `0x180006294`
- `0x18000688c`
- `0x180007bb4`
- `0x180008400`
- `0x1800089e4`
- `0x180009e70`
- `0x180009ff8`
- `0x1800633f0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800069a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800069a5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006a98`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006a98`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006b21`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006b21`

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
    ModuleName = wil::details::g_pfnGetModuleName(v19);
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
      : (v21 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v19) == 0),
        v21)
    || (v24 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v23, v20);
    OutputDebugStringW(OutputString);
  }
  if ( ((v24 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v19);
  if ( (v24 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v23, v18);
}

```

## disassembly

```asm
0x18000688c  push    rbp
0x18000688e  push    rbx
0x18000688f  push    rsi
0x180006890  push    rdi
0x180006891  push    r12
0x180006893  push    r13
0x180006895  push    r14
0x180006897  push    r15
0x180006899  lea     rbp, [rsp-1408h]
0x1800068a1  mov     eax, 1508h
0x1800068a6  call    _alloca_probe
0x1800068ab  sub     rsp, rax
0x1800068ae  mov     rax, cs:__security_cookie
0x1800068b5  xor     rax, rsp
0x1800068b8  mov     [rbp+1440h+var_50], rax
0x1800068bf  mov     r12, r9
0x1800068c2  mov     r15, r8
0x1800068c5  mov     r14d, edx
0x1800068c8  mov     rsi, rcx
0x1800068cb  mov     r13, [rbp+1440h+arg_20]
0x1800068d2  mov     rax, [rbp+1440h+arg_28]
0x1800068d9  mov     [rsp+1540h+var_1500], rax
0x1800068de  xor     edx, edx; Val
0x1800068e0  mov     r8d, 98h; Size
0x1800068e6  lea     rcx, [rsp+1540h+var_14F0]; void *
0x1800068eb  call    memset_0
0x1800068f0  nop
0x1800068f1  xor     eax, eax
0x1800068f3  mov     [rbp+1440h+OutputString], ax
0x1800068fa  mov     [rbp+1440h+var_1450], al
0x1800068fd  mov     rdi, [rbp+1440h+arg_30]
0x180006904  mov     ebx, [rdi]
0x180006906  mov     [rsp+1540h+var_14E8], ebx
0x18000690a  mov     eax, [rdi+4]
0x18000690d  mov     [rsp+1540h+var_14E4], eax
0x180006911  test    ebx, ebx
0x180006913  js      short loc_18000694D
0x180006915  mov     ebx, 8007029Ch
0x18000691a  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x18000691e  mov     rax, [rsp+1540h+var_1500]
0x180006923  mov     [rsp+1540h+var_1518], rax; __int64
0x180006928  mov     [rsp+1540h+var_1520], r13; __int64
0x18000692d  mov     r9, r12; int
0x180006930  mov     r8, r15; int
0x180006933  mov     edx, r14d; int
0x180006936  mov     rcx, rsi; int
0x180006939  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000693e  mov     [rsp+1540h+var_14E8], ebx
0x180006942  mov     ecx, ebx; this
0x180006944  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006949  mov     [rsp+1540h+var_14E4], eax
0x18000694d  mov     ecx, ebx; this
0x18000694f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006954  mov     ebx, eax
0x180006956  mov     dword ptr [rsp+1540h+var_14F0], 2
0x18000695e  mov     ecx, [rbp+1440h+arg_48]
0x180006964  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180006968  cmp     dword ptr [rdi+8], 1
0x18000696c  jnz     short loc_180006975
0x18000696e  or      ecx, 8
0x180006971  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180006975  mov     ecx, 1
0x18000697a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006982  inc     ecx
0x180006984  mov     [rsp+1540h+var_14E0], ecx
0x180006988  mov     rax, [rbp+1440h+arg_38]
0x18000698f  xor     edi, edi
0x180006991  test    rax, rax
0x180006994  jz      short loc_1800069A0
0x180006996  cmp     [rax], di
0x180006999  mov     [rsp+1540h+var_14D8], rax
0x18000699e  jnz     short loc_1800069A5
0x1800069a0  mov     [rsp+1540h+var_14D8], rdi
0x1800069a5  call    cs:__imp_GetCurrentThreadId
0x1800069ab  mov     [rsp+1540h+var_14D0], eax
0x1800069af  mov     [rbp+1440h+var_14B8], r15
0x1800069b3  mov     [rbp+1440h+var_14B0], r14d
0x1800069b7  mov     [rbp+1440h+var_14AC], ebx
0x1800069ba  mov     [rsp+1540h+var_14C8], r13
0x1800069bf  mov     [rbp+1440h+var_14C0], r12
0x1800069c3  mov     rax, [rsp+1540h+var_1500]
0x1800069c8  mov     [rbp+1440h+var_1468], rax
0x1800069cc  mov     [rbp+1440h+var_1460], rsi
0x1800069d0  mov     [rbp+1440h+var_14A8], rdi
0x1800069d4  xorps   xmm0, xmm0
0x1800069d7  xor     eax, eax
0x1800069d9  movups  [rbp+1440h+var_1488], xmm0
0x1800069dd  mov     [rbp+1440h+var_1478], rax
0x1800069e1  xorps   xmm1, xmm1
0x1800069e4  movups  [rbp+1440h+var_14A0], xmm1
0x1800069e8  mov     [rbp+1440h+var_1490], rax
0x1800069ec  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800069f3  test    rax, rax
0x1800069f6  jz      short loc_180006A03
0x1800069f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069fd  mov     [rbp+1440h+var_1470], rax
0x180006a01  jmp     short loc_180006A07
0x180006a03  mov     [rbp+1440h+var_1470], rdi
0x180006a07  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006a0e  test    rax, rax
0x180006a11  jz      short loc_180006A1D
0x180006a13  lea     rcx, [rsp+1540h+var_14F0]
0x180006a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a1d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006a24  test    rax, rax
0x180006a27  jz      short loc_180006A3D
0x180006a29  mov     r8d, 400h
0x180006a2f  lea     rdx, [rbp+1440h+var_1450]
0x180006a33  lea     rcx, [rsp+1540h+var_14F0]
0x180006a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a3d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006a44  test    rax, rax
0x180006a47  jz      short loc_180006A53
0x180006a49  lea     rcx, [rsp+1540h+var_14F0]
0x180006a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a53  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006a5a  test    rax, rax
0x180006a5d  jz      short loc_180006A70
0x180006a5f  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180006a64  jnz     short loc_180006A70
0x180006a66  lea     rcx, [rsp+1540h+var_14F0]
0x180006a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a70  cmp     [rsp+1540h+var_14E8], edi
0x180006a74  jge     loc_180006B7E
0x180006a7a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006a81  jnz     short loc_180006AA2
0x180006a83  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006a8a  test    rax, rax
0x180006a8d  jz      short loc_180006A98
0x180006a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a94  test    al, al
0x180006a96  jmp     short loc_180006AA0
0x180006a98  call    cs:__imp_IsDebuggerPresent
0x180006a9e  test    eax, eax
0x180006aa0  jz      short loc_180006AA9
0x180006aa2  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180006aa7  jz      short loc_180006ACF
0x180006aa9  mov     rax, cs:g_pfnResultLoggingCallback
0x180006ab0  test    rax, rax
0x180006ab3  jz      short loc_180006B27
0x180006ab5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006abc  jnz     short loc_180006B27
0x180006abe  xor     r8d, r8d
0x180006ac1  xor     edx, edx
0x180006ac3  lea     rcx, [rsp+1540h+var_14F0]
0x180006ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006acd  jmp     short loc_180006B27
0x180006acf  mov     ebx, 800h
0x180006ad4  mov     rax, cs:g_pfnResultLoggingCallback
0x180006adb  test    rax, rax
0x180006ade  jz      short loc_180006AFD
0x180006ae0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006ae7  jnz     short loc_180006AFD
0x180006ae9  mov     r8d, ebx
0x180006aec  lea     rdx, [rbp+1440h+OutputString]
0x180006af3  lea     rcx, [rsp+1540h+var_14F0]
0x180006af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006afd  cmp     [rbp+1440h+OutputString], di
0x180006b04  jnz     short loc_180006B1A
0x180006b06  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x180006b0b  mov     rdx, rbx; unsigned __int16 *
0x180006b0e  lea     rcx, [rbp+1440h+OutputString]; this
0x180006b15  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006b1a  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x180006b21  call    cs:__imp_OutputDebugStringW
0x180006b27  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x180006b2c  jnz     short loc_180006B37
0x180006b2e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006b35  jz      short loc_180006B49
0x180006b37  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006b3e  test    rax, rax
0x180006b41  jz      short loc_180006B49
0x180006b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b48  nop
0x180006b49  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x180006b4e  jnz     short loc_180006B73
0x180006b50  mov     rcx, [rbp+1440h+var_50]
0x180006b57  xor     rcx, rsp; StackCookie
0x180006b5a  call    __security_check_cookie
0x180006b5f  add     rsp, 1508h
0x180006b66  pop     r15
0x180006b68  pop     r14
0x180006b6a  pop     r13
0x180006b6c  pop     r12
0x180006b6e  pop     rdi
0x180006b6f  pop     rsi
0x180006b70  pop     rbx
0x180006b71  pop     rbp
0x180006b72  retn
0x180006b73  lea     rcx, [rsp+1540h+var_14F0]; this
0x180006b78  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180006b7e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
