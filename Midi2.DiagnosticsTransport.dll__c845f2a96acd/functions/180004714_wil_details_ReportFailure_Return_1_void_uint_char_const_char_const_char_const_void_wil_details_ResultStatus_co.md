# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004714`
- end: `0x1800049a1`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800041f4`

## callees

- `0x1800033d0`
- `0x180004170`
- `0x180004714`
- `0x180006ab4`
- `0x180007f50`
- `0x18000a010`
- `0x18000a104`
- `0x180011f90`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047c2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800048b6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800048b6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004940`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004940`

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
0x180004714  push    rbp
0x180004716  push    rbx
0x180004717  push    rsi
0x180004718  push    rdi
0x180004719  push    r12
0x18000471b  push    r14
0x18000471d  push    r15
0x18000471f  lea     rbp, [rsp-13D0h]
0x180004727  mov     eax, 14D0h
0x18000472c  call    _alloca_probe
0x180004731  sub     rsp, rax
0x180004734  mov     rax, cs:__security_cookie
0x18000473b  xor     rax, rsp
0x18000473e  mov     [rbp+1400h+var_40], rax
0x180004745  mov     r14, r8
0x180004748  mov     esi, edx
0x18000474a  mov     r15, rcx
0x18000474d  mov     rdi, [rbp+1400h+arg_28]
0x180004754  xor     edx, edx; Val
0x180004756  mov     r8d, 98h; Size
0x18000475c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004761  call    memset_0
0x180004766  nop
0x180004767  xor     r12d, r12d
0x18000476a  mov     [rbp+1400h+OutputString], r12w
0x180004772  mov     [rbp+1400h+var_1440], r12b
0x180004776  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18000477d  mov     ecx, [rdx]; this
0x18000477f  mov     [rsp+1500h+var_14D8], ecx
0x180004783  mov     eax, [rdx+4]
0x180004786  mov     [rsp+1500h+var_14D4], eax
0x18000478a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000478f  mov     ebx, eax
0x180004791  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180004799  mov     ecx, r12d
0x18000479c  lea     eax, [r12+8]
0x1800047a1  cmp     dword ptr [rdx+8], 1
0x1800047a5  cmovz   ecx, eax
0x1800047a8  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800047ac  lea     ecx, [rax-7]
0x1800047af  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800047b7  inc     ecx
0x1800047b9  mov     [rsp+1500h+var_14D0], ecx
0x1800047bd  mov     [rsp+1500h+var_14C8], r12
0x1800047c2  call    cs:__imp_GetCurrentThreadId
0x1800047c8  mov     [rsp+1500h+var_14C0], eax
0x1800047cc  mov     [rsp+1500h+var_14A8], r14
0x1800047d1  mov     [rsp+1500h+var_14A0], esi
0x1800047d5  mov     [rsp+1500h+var_149C], ebx
0x1800047d9  mov     [rsp+1500h+var_14B8], r12
0x1800047de  mov     [rsp+1500h+var_14B0], r12
0x1800047e3  mov     [rbp+1400h+var_1458], rdi
0x1800047e7  mov     [rbp+1400h+var_1450], r15
0x1800047eb  mov     [rsp+1500h+var_1498], r12
0x1800047f0  xorps   xmm0, xmm0
0x1800047f3  xor     eax, eax
0x1800047f5  movups  [rbp+1400h+var_1478], xmm0
0x1800047f9  mov     [rbp+1400h+var_1468], rax
0x1800047fd  xorps   xmm1, xmm1
0x180004800  movups  [rsp+1500h+var_1490], xmm1
0x180004805  mov     [rbp+1400h+var_1480], rax
0x180004809  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004810  test    rax, rax
0x180004813  jz      short loc_180004820
0x180004815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000481a  mov     [rbp+1400h+var_1460], rax
0x18000481e  jmp     short loc_180004824
0x180004820  mov     [rbp+1400h+var_1460], r12
0x180004824  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000482b  test    rax, rax
0x18000482e  jz      short loc_18000483A
0x180004830  lea     rcx, [rsp+1500h+var_14E0]
0x180004835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000483a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004841  test    rax, rax
0x180004844  jz      short loc_18000485A
0x180004846  mov     r8d, 400h
0x18000484c  lea     rdx, [rbp+1400h+var_1440]
0x180004850  lea     rcx, [rsp+1500h+var_14E0]
0x180004855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000485a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004861  test    rax, rax
0x180004864  jz      short loc_180004870
0x180004866  lea     rcx, [rsp+1500h+var_14E0]
0x18000486b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004870  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004877  test    rax, rax
0x18000487a  jz      short loc_18000488D
0x18000487c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004881  jnz     short loc_18000488D
0x180004883  lea     rcx, [rsp+1500h+var_14E0]
0x180004888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000488d  cmp     [rsp+1500h+var_14D8], r12d
0x180004892  jge     loc_18000499B
0x180004898  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000489f  jnz     short loc_1800048C0
0x1800048a1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800048a8  test    rax, rax
0x1800048ab  jz      short loc_1800048B6
0x1800048ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048b2  test    al, al
0x1800048b4  jmp     short loc_1800048BE
0x1800048b6  call    cs:__imp_IsDebuggerPresent
0x1800048bc  test    eax, eax
0x1800048be  jz      short loc_1800048C7
0x1800048c0  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800048c5  jz      short loc_1800048ED
0x1800048c7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800048ce  test    rax, rax
0x1800048d1  jz      short loc_180004946
0x1800048d3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800048da  jnz     short loc_180004946
0x1800048dc  xor     r8d, r8d
0x1800048df  xor     edx, edx
0x1800048e1  lea     rcx, [rsp+1500h+var_14E0]
0x1800048e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048eb  jmp     short loc_180004946
0x1800048ed  mov     ebx, 800h
0x1800048f2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800048f9  test    rax, rax
0x1800048fc  jz      short loc_18000491B
0x1800048fe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004905  jnz     short loc_18000491B
0x180004907  mov     r8d, ebx
0x18000490a  lea     rdx, [rbp+1400h+OutputString]
0x180004911  lea     rcx, [rsp+1500h+var_14E0]
0x180004916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000491b  cmp     [rbp+1400h+OutputString], r12w
0x180004923  jnz     short loc_180004939
0x180004925  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000492a  mov     rdx, rbx; unsigned __int16 *
0x18000492d  lea     rcx, [rbp+1400h+OutputString]; this
0x180004934  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004939  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004940  call    cs:__imp_OutputDebugStringW
0x180004946  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000494b  jnz     short loc_180004956
0x18000494d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004954  jz      short loc_180004968
0x180004956  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000495d  test    rax, rax
0x180004960  jz      short loc_180004968
0x180004962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004967  nop
0x180004968  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000496d  jnz     short loc_180004990
0x18000496f  mov     rcx, [rbp+1400h+var_40]
0x180004976  xor     rcx, rsp; StackCookie
0x180004979  call    __security_check_cookie
0x18000497e  add     rsp, 14D0h
0x180004985  pop     r15
0x180004987  pop     r14
0x180004989  pop     r12
0x18000498b  pop     rdi
0x18000498c  pop     rsi
0x18000498d  pop     rbx
0x18000498e  pop     rbp
0x18000498f  retn
0x180004990  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004995  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000499b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
