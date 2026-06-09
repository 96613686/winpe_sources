# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140004828`
- end: `0x140004ace`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400041a0`

## callees

- `0x140002f40`
- `0x140003ab8`
- `0x140004828`
- `0x140007224`
- `0x1400098fc`
- `0x14000d6a8`
- `0x14000dbf8`
- `0x140018460`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400048ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400048ee`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400049e3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400049e3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004a6d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004a6d`

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
0x140004828  push    rbp
0x14000482a  push    rbx
0x14000482b  push    rsi
0x14000482c  push    rdi
0x14000482d  push    r12
0x14000482f  push    r14
0x140004831  push    r15
0x140004833  lea     rbp, [rsp-13D0h]
0x14000483b  mov     eax, 14D0h
0x140004840  call    _alloca_probe
0x140004845  sub     rsp, rax
0x140004848  mov     rax, cs:__security_cookie
0x14000484f  xor     rax, rsp
0x140004852  mov     [rbp+1400h+var_40], rax
0x140004859  mov     rsi, r8
0x14000485c  mov     edi, edx
0x14000485e  mov     rbx, rcx
0x140004861  mov     r14, [rbp+1400h+arg_28]
0x140004868  xor     edx, edx; Val
0x14000486a  mov     r8d, 98h; Size
0x140004870  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140004875  call    memset_0
0x14000487a  nop
0x14000487b  xor     r12d, r12d
0x14000487e  mov     [rbp+1400h+OutputString], r12w
0x140004886  mov     [rbp+1400h+var_1440], r12b
0x14000488a  mov     rdx, [rbp+1400h+arg_30]; int
0x140004891  mov     ecx, [rdx]; this
0x140004893  mov     [rsp+1500h+var_14D8], ecx
0x140004897  mov     eax, [rdx+4]
0x14000489a  mov     [rsp+1500h+var_14D4], eax
0x14000489e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400048a3  mov     r15d, eax
0x1400048a6  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1400048ae  mov     ecx, r12d
0x1400048b1  lea     eax, [r12+8]
0x1400048b6  cmp     dword ptr [rdx+8], 1
0x1400048ba  cmovz   ecx, eax
0x1400048bd  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1400048c1  lea     ecx, [rax-7]
0x1400048c4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400048cc  inc     ecx
0x1400048ce  mov     [rsp+1500h+var_14D0], ecx
0x1400048d2  mov     rcx, [rbp+1400h+arg_38]
0x1400048d9  test    rcx, rcx
0x1400048dc  jz      short loc_1400048E9
0x1400048de  cmp     [rcx], r12w
0x1400048e2  mov     [rsp+1500h+var_14C8], rcx
0x1400048e7  jnz     short loc_1400048EE
0x1400048e9  mov     [rsp+1500h+var_14C8], r12
0x1400048ee  call    cs:__imp_GetCurrentThreadId
0x1400048f4  mov     [rsp+1500h+var_14C0], eax
0x1400048f8  mov     [rsp+1500h+var_14A8], rsi
0x1400048fd  mov     [rsp+1500h+var_14A0], edi
0x140004901  mov     [rsp+1500h+var_149C], r15d
0x140004906  mov     [rsp+1500h+var_14B8], r12
0x14000490b  mov     [rsp+1500h+var_14B0], r12
0x140004910  mov     [rbp+1400h+var_1458], r14
0x140004914  mov     [rbp+1400h+var_1450], rbx
0x140004918  mov     [rsp+1500h+var_1498], r12
0x14000491d  xorps   xmm0, xmm0
0x140004920  xor     eax, eax
0x140004922  movups  [rbp+1400h+var_1478], xmm0
0x140004926  mov     [rbp+1400h+var_1468], rax
0x14000492a  xorps   xmm1, xmm1
0x14000492d  movups  [rsp+1500h+var_1490], xmm1
0x140004932  mov     [rbp+1400h+var_1480], rax
0x140004936  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000493d  test    rax, rax
0x140004940  jz      short loc_14000494D
0x140004942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004947  mov     [rbp+1400h+var_1460], rax
0x14000494b  jmp     short loc_140004951
0x14000494d  mov     [rbp+1400h+var_1460], r12
0x140004951  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004958  test    rax, rax
0x14000495b  jz      short loc_140004967
0x14000495d  lea     rcx, [rsp+1500h+var_14E0]
0x140004962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004967  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000496e  test    rax, rax
0x140004971  jz      short loc_140004987
0x140004973  mov     r8d, 400h
0x140004979  lea     rdx, [rbp+1400h+var_1440]
0x14000497d  lea     rcx, [rsp+1500h+var_14E0]
0x140004982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004987  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000498e  test    rax, rax
0x140004991  jz      short loc_14000499D
0x140004993  lea     rcx, [rsp+1500h+var_14E0]
0x140004998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000499d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400049a4  test    rax, rax
0x1400049a7  jz      short loc_1400049BA
0x1400049a9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1400049ae  jnz     short loc_1400049BA
0x1400049b0  lea     rcx, [rsp+1500h+var_14E0]
0x1400049b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400049ba  cmp     [rsp+1500h+var_14D8], r12d
0x1400049bf  jge     loc_140004AC8
0x1400049c5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1400049cc  jnz     short loc_1400049ED
0x1400049ce  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400049d5  test    rax, rax
0x1400049d8  jz      short loc_1400049E3
0x1400049da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400049df  test    al, al
0x1400049e1  jmp     short loc_1400049EB
0x1400049e3  call    cs:__imp_IsDebuggerPresent
0x1400049e9  test    eax, eax
0x1400049eb  jz      short loc_1400049F4
0x1400049ed  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1400049f2  jz      short loc_140004A1A
0x1400049f4  mov     rax, cs:g_pfnResultLoggingCallback
0x1400049fb  test    rax, rax
0x1400049fe  jz      short loc_140004A73
0x140004a00  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140004a07  jnz     short loc_140004A73
0x140004a09  xor     r8d, r8d
0x140004a0c  xor     edx, edx
0x140004a0e  lea     rcx, [rsp+1500h+var_14E0]
0x140004a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004a18  jmp     short loc_140004A73
0x140004a1a  mov     ebx, 800h
0x140004a1f  mov     rax, cs:g_pfnResultLoggingCallback
0x140004a26  test    rax, rax
0x140004a29  jz      short loc_140004A48
0x140004a2b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140004a32  jnz     short loc_140004A48
0x140004a34  mov     r8d, ebx
0x140004a37  lea     rdx, [rbp+1400h+OutputString]
0x140004a3e  lea     rcx, [rsp+1500h+var_14E0]
0x140004a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004a48  cmp     [rbp+1400h+OutputString], r12w
0x140004a50  jnz     short loc_140004A66
0x140004a52  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140004a57  mov     rdx, rbx; unsigned __int16 *
0x140004a5a  lea     rcx, [rbp+1400h+OutputString]; this
0x140004a61  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004a66  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140004a6d  call    cs:__imp_OutputDebugStringW
0x140004a73  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140004a78  jnz     short loc_140004A83
0x140004a7a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140004a81  jz      short loc_140004A95
0x140004a83  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140004a8a  test    rax, rax
0x140004a8d  jz      short loc_140004A95
0x140004a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004a94  nop
0x140004a95  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140004a9a  jnz     short loc_140004ABD
0x140004a9c  mov     rcx, [rbp+1400h+var_40]
0x140004aa3  xor     rcx, rsp; StackCookie
0x140004aa6  call    __security_check_cookie
0x140004aab  add     rsp, 14D0h
0x140004ab2  pop     r15
0x140004ab4  pop     r14
0x140004ab6  pop     r12
0x140004ab8  pop     rdi
0x140004ab9  pop     rsi
0x140004aba  pop     rbx
0x140004abb  pop     rbp
0x140004abc  retn
0x140004abd  lea     rcx, [rsp+1500h+var_14E0]; this
0x140004ac2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140004ac8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
