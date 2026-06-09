# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800048ac`
- end: `0x180004bac`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `768`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180003f58`

## callees

- `0x1800021c0`
- `0x180002c04`
- `0x1800042b8`
- `0x1800048ac`
- `0x1800072bc`
- `0x180007ee0`
- `0x180008b84`
- `0x18000a7b0`
- `0x18000a938`
- `0x180029890`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800049cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800049cd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004ac0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004ac0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004b49`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004b49`

## pseudocode

```c
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
0x1800048ac  push    rbp
0x1800048ae  push    rbx
0x1800048af  push    rsi
0x1800048b0  push    rdi
0x1800048b1  push    r12
0x1800048b3  push    r13
0x1800048b5  push    r14
0x1800048b7  push    r15
0x1800048b9  lea     rbp, [rsp-1408h]
0x1800048c1  mov     eax, 1508h
0x1800048c6  call    _alloca_probe
0x1800048cb  sub     rsp, rax
0x1800048ce  mov     rax, cs:__security_cookie
0x1800048d5  xor     rax, rsp
0x1800048d8  mov     [rbp+1440h+var_50], rax
0x1800048df  mov     r12, r9
0x1800048e2  mov     r15, r8
0x1800048e5  mov     r14d, edx
0x1800048e8  mov     rsi, rcx
0x1800048eb  mov     r13, [rbp+1440h+arg_20]
0x1800048f2  mov     rax, [rbp+1440h+arg_28]
0x1800048f9  mov     [rsp+1540h+var_1500], rax
0x1800048fe  xor     edx, edx; Val
0x180004900  mov     r8d, 98h; Size
0x180004906  lea     rcx, [rsp+1540h+var_14F0]; void *
0x18000490b  call    memset_0
0x180004910  nop
0x180004911  xor     eax, eax
0x180004913  mov     [rbp+1440h+OutputString], ax
0x18000491a  mov     [rbp+1440h+var_1450], al
0x18000491d  mov     rdi, [rbp+1440h+arg_30]
0x180004924  mov     ebx, [rdi]
0x180004926  mov     [rsp+1540h+var_14E8], ebx
0x18000492a  mov     eax, [rdi+4]
0x18000492d  mov     [rsp+1540h+var_14E4], eax
0x180004931  test    ebx, ebx
0x180004933  js      short loc_180004975
0x180004935  mov     [rsp+1540h+var_1508], 0
0x18000493d  mov     ebx, 8007029Ch
0x180004942  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x180004946  mov     rax, [rsp+1540h+var_1500]
0x18000494b  mov     [rsp+1540h+var_1518], rax; __int64
0x180004950  mov     [rsp+1540h+var_1520], r13; __int64
0x180004955  mov     r9, r12; int
0x180004958  mov     r8, r15; int
0x18000495b  mov     edx, r14d; int
0x18000495e  mov     rcx, rsi; int
0x180004961  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004966  mov     [rsp+1540h+var_14E8], ebx
0x18000496a  mov     ecx, ebx; this
0x18000496c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004971  mov     [rsp+1540h+var_14E4], eax
0x180004975  mov     ecx, ebx; this
0x180004977  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000497c  mov     ebx, eax
0x18000497e  mov     dword ptr [rsp+1540h+var_14F0], 2
0x180004986  mov     ecx, [rbp+1440h+arg_48]
0x18000498c  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180004990  cmp     dword ptr [rdi+8], 1
0x180004994  jnz     short loc_18000499D
0x180004996  or      ecx, 8
0x180004999  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x18000499d  mov     ecx, 1
0x1800049a2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800049aa  inc     ecx
0x1800049ac  mov     [rsp+1540h+var_14E0], ecx
0x1800049b0  mov     rax, [rbp+1440h+arg_38]
0x1800049b7  xor     edi, edi
0x1800049b9  test    rax, rax
0x1800049bc  jz      short loc_1800049C8
0x1800049be  cmp     [rax], di
0x1800049c1  mov     [rsp+1540h+var_14D8], rax
0x1800049c6  jnz     short loc_1800049CD
0x1800049c8  mov     [rsp+1540h+var_14D8], rdi
0x1800049cd  call    cs:__imp_GetCurrentThreadId
0x1800049d3  mov     [rsp+1540h+var_14D0], eax
0x1800049d7  mov     [rbp+1440h+var_14B8], r15
0x1800049db  mov     [rbp+1440h+var_14B0], r14d
0x1800049df  mov     [rbp+1440h+var_14AC], ebx
0x1800049e2  mov     [rsp+1540h+var_14C8], r13
0x1800049e7  mov     [rbp+1440h+var_14C0], r12
0x1800049eb  mov     rax, [rsp+1540h+var_1500]
0x1800049f0  mov     [rbp+1440h+var_1468], rax
0x1800049f4  mov     [rbp+1440h+var_1460], rsi
0x1800049f8  mov     [rbp+1440h+var_14A8], rdi
0x1800049fc  xorps   xmm0, xmm0
0x1800049ff  xor     eax, eax
0x180004a01  movups  [rbp+1440h+var_1488], xmm0
0x180004a05  mov     [rbp+1440h+var_1478], rax
0x180004a09  xorps   xmm1, xmm1
0x180004a0c  movups  [rbp+1440h+var_14A0], xmm1
0x180004a10  mov     [rbp+1440h+var_1490], rax
0x180004a14  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004a1b  test    rax, rax
0x180004a1e  jz      short loc_180004A2B
0x180004a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a25  mov     [rbp+1440h+var_1470], rax
0x180004a29  jmp     short loc_180004A2F
0x180004a2b  mov     [rbp+1440h+var_1470], rdi
0x180004a2f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004a36  test    rax, rax
0x180004a39  jz      short loc_180004A45
0x180004a3b  lea     rcx, [rsp+1540h+var_14F0]
0x180004a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a45  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004a4c  test    rax, rax
0x180004a4f  jz      short loc_180004A65
0x180004a51  mov     r8d, 400h
0x180004a57  lea     rdx, [rbp+1440h+var_1450]
0x180004a5b  lea     rcx, [rsp+1540h+var_14F0]
0x180004a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a65  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004a6c  test    rax, rax
0x180004a6f  jz      short loc_180004A7B
0x180004a71  lea     rcx, [rsp+1540h+var_14F0]
0x180004a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a7b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004a82  test    rax, rax
0x180004a85  jz      short loc_180004A98
0x180004a87  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180004a8c  jnz     short loc_180004A98
0x180004a8e  lea     rcx, [rsp+1540h+var_14F0]
0x180004a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a98  cmp     [rsp+1540h+var_14E8], edi
0x180004a9c  jge     loc_180004BA6
0x180004aa2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004aa9  jnz     short loc_180004ACA
0x180004aab  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004ab2  test    rax, rax
0x180004ab5  jz      short loc_180004AC0
0x180004ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004abc  test    al, al
0x180004abe  jmp     short loc_180004AC8
0x180004ac0  call    cs:__imp_IsDebuggerPresent
0x180004ac6  test    eax, eax
0x180004ac8  jz      short loc_180004AD1
0x180004aca  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180004acf  jz      short loc_180004AF7
0x180004ad1  mov     rax, cs:g_pfnResultLoggingCallback
0x180004ad8  test    rax, rax
0x180004adb  jz      short loc_180004B4F
0x180004add  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004ae4  jnz     short loc_180004B4F
0x180004ae6  xor     r8d, r8d
0x180004ae9  xor     edx, edx
0x180004aeb  lea     rcx, [rsp+1540h+var_14F0]
0x180004af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004af5  jmp     short loc_180004B4F
0x180004af7  mov     ebx, 800h
0x180004afc  mov     rax, cs:g_pfnResultLoggingCallback
0x180004b03  test    rax, rax
0x180004b06  jz      short loc_180004B25
0x180004b08  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004b0f  jnz     short loc_180004B25
0x180004b11  mov     r8d, ebx
0x180004b14  lea     rdx, [rbp+1440h+OutputString]
0x180004b1b  lea     rcx, [rsp+1540h+var_14F0]
0x180004b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b25  cmp     [rbp+1440h+OutputString], di
0x180004b2c  jnz     short loc_180004B42
0x180004b2e  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x180004b33  mov     rdx, rbx; unsigned __int16 *
0x180004b36  lea     rcx, [rbp+1440h+OutputString]; this
0x180004b3d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004b42  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x180004b49  call    cs:__imp_OutputDebugStringW
0x180004b4f  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x180004b54  jnz     short loc_180004B5F
0x180004b56  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004b5d  jz      short loc_180004B71
0x180004b5f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004b66  test    rax, rax
0x180004b69  jz      short loc_180004B71
0x180004b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b70  nop
0x180004b71  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x180004b76  jnz     short loc_180004B9B
0x180004b78  mov     rcx, [rbp+1440h+var_50]
0x180004b7f  xor     rcx, rsp; StackCookie
0x180004b82  call    __security_check_cookie
0x180004b87  add     rsp, 1508h
0x180004b8e  pop     r15
0x180004b90  pop     r14
0x180004b92  pop     r13
0x180004b94  pop     r12
0x180004b96  pop     rdi
0x180004b97  pop     rsi
0x180004b98  pop     rbx
0x180004b99  pop     rbp
0x180004b9a  retn
0x180004b9b  lea     rcx, [rsp+1540h+var_14F0]; this
0x180004ba0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004ba6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
