# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004750`
- end: `0x1800049e6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004418`

## callees

- `0x180003410`
- `0x180003f7c`
- `0x180004750`
- `0x1800055c4`
- `0x180006670`
- `0x180007258`
- `0x1800073c0`
- `0x180022ee0`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047fb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004980`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004980`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800048f6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800048f6`

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
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x180004750  mov     [rsp-8+arg_10], rbx
0x180004755  push    rbp
0x180004756  push    rsi
0x180004757  push    rdi
0x180004758  push    r14
0x18000475a  push    r15
0x18000475c  lea     rbp, [rsp-13D0h]
0x180004764  mov     eax, 14D0h
0x180004769  call    _alloca_probe
0x18000476e  sub     rsp, rax
0x180004771  mov     rax, cs:__security_cookie
0x180004778  xor     rax, rsp
0x18000477b  mov     [rbp+13F0h+var_30], rax
0x180004782  mov     esi, edx
0x180004784  mov     r14, rcx
0x180004787  mov     rdi, [rbp+13F0h+arg_28]
0x18000478e  xor     edx, edx; Val
0x180004790  mov     r8d, 98h; Size
0x180004796  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000479b  call    memset_0
0x1800047a0  nop
0x1800047a1  xor     r15d, r15d
0x1800047a4  mov     [rbp+13F0h+OutputString], r15w
0x1800047ac  mov     [rbp+13F0h+var_1430], r15b
0x1800047b0  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800047b7  mov     ecx, [rdx]; this
0x1800047b9  mov     [rsp+14F0h+var_14C8], ecx
0x1800047bd  mov     eax, [rdx+4]
0x1800047c0  mov     [rsp+14F0h+var_14C4], eax
0x1800047c4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800047c9  mov     ebx, eax
0x1800047cb  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800047d3  mov     ecx, r15d
0x1800047d6  lea     eax, [r15+8]
0x1800047da  cmp     dword ptr [rdx+8], 1
0x1800047de  cmovz   ecx, eax
0x1800047e1  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800047e5  lea     ecx, [rax-7]
0x1800047e8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800047f0  inc     ecx
0x1800047f2  mov     [rsp+14F0h+var_14C0], ecx
0x1800047f6  mov     [rsp+14F0h+var_14B8], r15
0x1800047fb  call    cs:__imp_GetCurrentThreadId
0x180004801  mov     [rsp+14F0h+var_14B0], eax
0x180004805  lea     rax, aWil; "wil"
0x18000480c  mov     [rsp+14F0h+var_1498], rax
0x180004811  mov     [rsp+14F0h+var_1490], esi
0x180004815  mov     [rsp+14F0h+var_148C], ebx
0x180004819  mov     [rsp+14F0h+var_14A8], r15
0x18000481e  mov     [rsp+14F0h+var_14A0], r15
0x180004823  mov     [rbp+13F0h+var_1448], rdi
0x180004827  mov     [rbp+13F0h+var_1440], r14
0x18000482b  mov     [rsp+14F0h+var_1488], r15
0x180004830  xorps   xmm0, xmm0
0x180004833  xor     eax, eax
0x180004835  movups  [rbp+13F0h+var_1468], xmm0
0x180004839  mov     [rbp+13F0h+var_1458], rax
0x18000483d  xorps   xmm1, xmm1
0x180004840  movups  [rsp+14F0h+var_1480], xmm1
0x180004845  mov     [rbp+13F0h+var_1470], rax
0x180004849  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004850  test    rax, rax
0x180004853  jz      short loc_180004860
0x180004855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000485a  mov     [rbp+13F0h+var_1450], rax
0x18000485e  jmp     short loc_180004864
0x180004860  mov     [rbp+13F0h+var_1450], r15
0x180004864  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000486b  test    rax, rax
0x18000486e  jz      short loc_18000487A
0x180004870  lea     rcx, [rsp+14F0h+var_14D0]
0x180004875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000487a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004881  test    rax, rax
0x180004884  jz      short loc_18000489A
0x180004886  mov     r8d, 400h
0x18000488c  lea     rdx, [rbp+13F0h+var_1430]
0x180004890  lea     rcx, [rsp+14F0h+var_14D0]
0x180004895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000489a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800048a1  test    rax, rax
0x1800048a4  jz      short loc_1800048B0
0x1800048a6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800048ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048b0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800048b7  test    rax, rax
0x1800048ba  jz      short loc_1800048CD
0x1800048bc  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800048c1  jnz     short loc_1800048CD
0x1800048c3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800048c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048cd  cmp     [rsp+14F0h+var_14C8], r15d
0x1800048d2  jge     loc_1800049E0
0x1800048d8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800048df  jnz     short loc_180004900
0x1800048e1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800048e8  test    rax, rax
0x1800048eb  jz      short loc_1800048F6
0x1800048ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048f2  test    al, al
0x1800048f4  jmp     short loc_1800048FE
0x1800048f6  call    cs:__imp_IsDebuggerPresent
0x1800048fc  test    eax, eax
0x1800048fe  jz      short loc_180004907
0x180004900  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004905  jz      short loc_18000492D
0x180004907  mov     rax, cs:g_pfnResultLoggingCallback
0x18000490e  test    rax, rax
0x180004911  jz      short loc_180004986
0x180004913  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000491a  jnz     short loc_180004986
0x18000491c  xor     r8d, r8d
0x18000491f  xor     edx, edx
0x180004921  lea     rcx, [rsp+14F0h+var_14D0]
0x180004926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000492b  jmp     short loc_180004986
0x18000492d  mov     ebx, 800h
0x180004932  mov     rax, cs:g_pfnResultLoggingCallback
0x180004939  test    rax, rax
0x18000493c  jz      short loc_18000495B
0x18000493e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004945  jnz     short loc_18000495B
0x180004947  mov     r8d, ebx
0x18000494a  lea     rdx, [rbp+13F0h+OutputString]
0x180004951  lea     rcx, [rsp+14F0h+var_14D0]
0x180004956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000495b  cmp     [rbp+13F0h+OutputString], r15w
0x180004963  jnz     short loc_180004979
0x180004965  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000496a  mov     rdx, rbx; unsigned __int16 *
0x18000496d  lea     rcx, [rbp+13F0h+OutputString]; this
0x180004974  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004979  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180004980  call    cs:__imp_OutputDebugStringW
0x180004986  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000498b  jnz     short loc_180004996
0x18000498d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180004994  jz      short loc_1800049A8
0x180004996  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000499d  test    rax, rax
0x1800049a0  jz      short loc_1800049A8
0x1800049a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049a7  nop
0x1800049a8  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800049ad  jnz     short loc_1800049D5
0x1800049af  mov     rcx, [rbp+13F0h+var_30]
0x1800049b6  xor     rcx, rsp; StackCookie
0x1800049b9  call    __security_check_cookie
0x1800049be  mov     rbx, [rsp+14F0h+arg_10]
0x1800049c6  add     rsp, 14D0h
0x1800049cd  pop     r15
0x1800049cf  pop     r14
0x1800049d1  pop     rdi
0x1800049d2  pop     rsi
0x1800049d3  pop     rbp
0x1800049d4  retn
0x1800049d5  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800049da  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800049e0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
