# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002854`
- end: `0x180002ae1`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000232c`

## callees

- `0x180002854`
- `0x1800039d4`
- `0x1800048d0`
- `0x180005600`
- `0x1800057d4`
- `0x18001143a`
- `0x180011460`
- `0x180011520`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002902`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002902`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002a80`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002a80`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800029f6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800029f6`

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
0x180002854  push    rbp
0x180002856  push    rbx
0x180002857  push    rsi
0x180002858  push    rdi
0x180002859  push    r12
0x18000285b  push    r14
0x18000285d  push    r15
0x18000285f  lea     rbp, [rsp-13D0h]
0x180002867  mov     eax, 14D0h
0x18000286c  call    _alloca_probe
0x180002871  sub     rsp, rax
0x180002874  mov     rax, cs:__security_cookie
0x18000287b  xor     rax, rsp
0x18000287e  mov     [rbp+1400h+var_40], rax
0x180002885  mov     r14, r8
0x180002888  mov     esi, edx
0x18000288a  mov     r15, rcx
0x18000288d  mov     rdi, [rbp+1400h+arg_28]
0x180002894  xor     edx, edx; Val
0x180002896  mov     r8d, 98h; Size
0x18000289c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800028a1  call    memset_0
0x1800028a6  nop
0x1800028a7  xor     r12d, r12d
0x1800028aa  mov     [rbp+1400h+OutputString], r12w
0x1800028b2  mov     [rbp+1400h+var_1440], r12b
0x1800028b6  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1800028bd  mov     ecx, [rdx]; this
0x1800028bf  mov     [rsp+1500h+var_14D8], ecx
0x1800028c3  mov     eax, [rdx+4]
0x1800028c6  mov     [rsp+1500h+var_14D4], eax
0x1800028ca  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800028cf  mov     ebx, eax
0x1800028d1  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800028d9  mov     ecx, r12d
0x1800028dc  lea     eax, [r12+8]
0x1800028e1  cmp     dword ptr [rdx+8], 1
0x1800028e5  cmovz   ecx, eax
0x1800028e8  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800028ec  lea     ecx, [rax-7]
0x1800028ef  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800028f7  inc     ecx
0x1800028f9  mov     [rsp+1500h+var_14D0], ecx
0x1800028fd  mov     [rsp+1500h+var_14C8], r12
0x180002902  call    cs:__imp_GetCurrentThreadId
0x180002908  mov     [rsp+1500h+var_14C0], eax
0x18000290c  mov     [rsp+1500h+var_14A8], r14
0x180002911  mov     [rsp+1500h+var_14A0], esi
0x180002915  mov     [rsp+1500h+var_149C], ebx
0x180002919  mov     [rsp+1500h+var_14B8], r12
0x18000291e  mov     [rsp+1500h+var_14B0], r12
0x180002923  mov     [rbp+1400h+var_1458], rdi
0x180002927  mov     [rbp+1400h+var_1450], r15
0x18000292b  mov     [rsp+1500h+var_1498], r12
0x180002930  xorps   xmm0, xmm0
0x180002933  xor     eax, eax
0x180002935  movups  [rbp+1400h+var_1478], xmm0
0x180002939  mov     [rbp+1400h+var_1468], rax
0x18000293d  xorps   xmm1, xmm1
0x180002940  movups  [rsp+1500h+var_1490], xmm1
0x180002945  mov     [rbp+1400h+var_1480], rax
0x180002949  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002950  test    rax, rax
0x180002953  jz      short loc_180002960
0x180002955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000295a  mov     [rbp+1400h+var_1460], rax
0x18000295e  jmp     short loc_180002964
0x180002960  mov     [rbp+1400h+var_1460], r12
0x180002964  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000296b  test    rax, rax
0x18000296e  jz      short loc_18000297A
0x180002970  lea     rcx, [rsp+1500h+var_14E0]
0x180002975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000297a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002981  test    rax, rax
0x180002984  jz      short loc_18000299A
0x180002986  mov     r8d, 400h
0x18000298c  lea     rdx, [rbp+1400h+var_1440]
0x180002990  lea     rcx, [rsp+1500h+var_14E0]
0x180002995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000299a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800029a1  test    rax, rax
0x1800029a4  jz      short loc_1800029B0
0x1800029a6  lea     rcx, [rsp+1500h+var_14E0]
0x1800029ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029b0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800029b7  test    rax, rax
0x1800029ba  jz      short loc_1800029CD
0x1800029bc  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800029c1  jnz     short loc_1800029CD
0x1800029c3  lea     rcx, [rsp+1500h+var_14E0]
0x1800029c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029cd  cmp     [rsp+1500h+var_14D8], r12d
0x1800029d2  jge     loc_180002ADB
0x1800029d8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800029df  jnz     short loc_180002A00
0x1800029e1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800029e8  test    rax, rax
0x1800029eb  jz      short loc_1800029F6
0x1800029ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029f2  test    al, al
0x1800029f4  jmp     short loc_1800029FE
0x1800029f6  call    cs:__imp_IsDebuggerPresent
0x1800029fc  test    eax, eax
0x1800029fe  jz      short loc_180002A07
0x180002a00  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180002a05  jz      short loc_180002A2D
0x180002a07  mov     rax, cs:g_pfnResultLoggingCallback
0x180002a0e  test    rax, rax
0x180002a11  jz      short loc_180002A86
0x180002a13  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002a1a  jnz     short loc_180002A86
0x180002a1c  xor     r8d, r8d
0x180002a1f  xor     edx, edx
0x180002a21  lea     rcx, [rsp+1500h+var_14E0]
0x180002a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a2b  jmp     short loc_180002A86
0x180002a2d  mov     ebx, 800h
0x180002a32  mov     rax, cs:g_pfnResultLoggingCallback
0x180002a39  test    rax, rax
0x180002a3c  jz      short loc_180002A5B
0x180002a3e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002a45  jnz     short loc_180002A5B
0x180002a47  mov     r8d, ebx
0x180002a4a  lea     rdx, [rbp+1400h+OutputString]
0x180002a51  lea     rcx, [rsp+1500h+var_14E0]
0x180002a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a5b  cmp     [rbp+1400h+OutputString], r12w
0x180002a63  jnz     short loc_180002A79
0x180002a65  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180002a6a  mov     rdx, rbx; unsigned __int16 *
0x180002a6d  lea     rcx, [rbp+1400h+OutputString]; this
0x180002a74  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002a79  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180002a80  call    cs:__imp_OutputDebugStringW
0x180002a86  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180002a8b  jnz     short loc_180002A96
0x180002a8d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002a94  jz      short loc_180002AA8
0x180002a96  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002a9d  test    rax, rax
0x180002aa0  jz      short loc_180002AA8
0x180002aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aa7  nop
0x180002aa8  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180002aad  jnz     short loc_180002AD0
0x180002aaf  mov     rcx, [rbp+1400h+var_40]
0x180002ab6  xor     rcx, rsp; StackCookie
0x180002ab9  call    __security_check_cookie
0x180002abe  add     rsp, 14D0h
0x180002ac5  pop     r15
0x180002ac7  pop     r14
0x180002ac9  pop     r12
0x180002acb  pop     rdi
0x180002acc  pop     rsi
0x180002acd  pop     rbx
0x180002ace  pop     rbp
0x180002acf  retn
0x180002ad0  lea     rcx, [rsp+1500h+var_14E0]; this
0x180002ad5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002adb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
