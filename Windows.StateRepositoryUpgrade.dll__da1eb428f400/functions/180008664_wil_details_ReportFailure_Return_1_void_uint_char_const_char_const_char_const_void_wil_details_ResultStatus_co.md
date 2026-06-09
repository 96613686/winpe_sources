# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180008664`
- end: `0x180008908`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `676`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800082e4`

## callees

- `0x180003980`
- `0x1800042f4`
- `0x180008664`
- `0x1800092e4`
- `0x18000a310`
- `0x18000abb8`
- `0x18000ad74`
- `0x18002dc10`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008729`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008729`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000881e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000881e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800088a8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800088a8`

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
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  int v14; // r15d
  int v15; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v17; // rdx
  wil::details::in1diag3 *v18; // rcx
  const struct wil::FailureInfo *v19; // r9
  bool v20; // zf
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+24h] [rbp-DCh]
  int v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v25; // [rsp+30h] [rbp-D0h]
  _WORD *v26; // [rsp+38h] [rbp-C8h]
  DWORD v27; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+60h] [rbp-A0h]
  int v32; // [rsp+64h] [rbp-9Ch]
  __int64 v33; // [rsp+68h] [rbp-98h]
  __int128 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+80h] [rbp-80h]
  __int128 v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  char v41[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v21, 0, 0x98u);
  OutputString[0] = 0;
  v41[0] = 0;
  v11 = a7[1];
  v23 = *a7;
  v24 = v11;
  v12 = wil::details::RecordReturn((wil::details *)(unsigned int)v23, (int)a7);
  v20 = *(_DWORD *)(v13 + 8) == 1;
  v14 = v12;
  v21 = 1;
  v15 = 0;
  if ( v20 )
    v15 = 8;
  v22 = v15;
  v25 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v26 = a8, !*a8) )
    v26 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v30 = a3;
  v27 = CurrentThreadId;
  v31 = a2;
  v37 = 0;
  v35 = 0;
  v32 = v14;
  v28 = 0;
  v29 = 0;
  v39 = a6;
  v40 = a1;
  v33 = 0;
  v36 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v18);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v21);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v21, v41, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v21);
  if ( wil::details::g_pfnOriginateCallback && (v22 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v21);
  if ( v23 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v18);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v20 = !IsDebuggerPresent())
      : (v20 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v18) == 0),
        v20)
    || (v22 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v21, v19);
    OutputDebugStringW(OutputString);
  }
  if ( ((v22 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v18);
  if ( (v22 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v21, v17);
}

```

## disassembly

```asm
0x180008664  push    rbp
0x180008666  push    rbx
0x180008667  push    rsi
0x180008668  push    rdi
0x180008669  push    r12
0x18000866b  push    r14
0x18000866d  push    r15
0x18000866f  lea     rbp, [rsp-13D0h]
0x180008677  mov     eax, 14D0h
0x18000867c  call    _alloca_probe
0x180008681  sub     rsp, rax
0x180008684  mov     rax, cs:__security_cookie
0x18000868b  xor     rax, rsp
0x18000868e  mov     [rbp+1400h+var_40], rax
0x180008695  mov     r14, [rbp+1400h+arg_28]
0x18000869c  mov     rsi, r8
0x18000869f  mov     edi, edx
0x1800086a1  mov     rbx, rcx
0x1800086a4  xor     edx, edx; Val
0x1800086a6  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800086ab  mov     r8d, 98h; Size
0x1800086b1  call    memset_0
0x1800086b6  mov     rdx, [rbp+1400h+arg_30]; int
0x1800086bd  xor     r12d, r12d
0x1800086c0  mov     [rbp+1400h+OutputString], r12w
0x1800086c8  mov     [rbp+1400h+var_1440], r12b
0x1800086cc  mov     ecx, [rdx]; this
0x1800086ce  mov     eax, [rdx+4]
0x1800086d1  mov     [rsp+1500h+var_14D8], ecx
0x1800086d5  mov     [rsp+1500h+var_14D4], eax
0x1800086d9  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800086de  cmp     dword ptr [rdx+8], 1
0x1800086e2  mov     r15d, eax
0x1800086e5  lea     eax, [r12+8]
0x1800086ea  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800086f2  mov     ecx, r12d
0x1800086f5  cmovz   ecx, eax
0x1800086f8  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800086fc  lea     ecx, [rax-7]
0x1800086ff  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008707  inc     ecx
0x180008709  mov     [rsp+1500h+var_14D0], ecx
0x18000870d  mov     rcx, [rbp+1400h+arg_38]
0x180008714  test    rcx, rcx
0x180008717  jz      short loc_180008724
0x180008719  mov     [rsp+1500h+var_14C8], rcx
0x18000871e  cmp     [rcx], r12w
0x180008722  jnz     short loc_180008729
0x180008724  mov     [rsp+1500h+var_14C8], r12
0x180008729  call    cs:__imp_GetCurrentThreadId
0x18000872f  xorps   xmm0, xmm0
0x180008732  mov     [rsp+1500h+var_14A8], rsi
0x180008737  mov     [rsp+1500h+var_14C0], eax
0x18000873b  xorps   xmm1, xmm1
0x18000873e  xor     eax, eax
0x180008740  mov     [rsp+1500h+var_14A0], edi
0x180008744  mov     [rbp+1400h+var_1468], rax
0x180008748  mov     [rbp+1400h+var_1480], rax
0x18000874c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008753  mov     [rsp+1500h+var_149C], r15d
0x180008758  mov     [rsp+1500h+var_14B8], r12
0x18000875d  mov     [rsp+1500h+var_14B0], r12
0x180008762  mov     [rbp+1400h+var_1458], r14
0x180008766  mov     [rbp+1400h+var_1450], rbx
0x18000876a  mov     [rsp+1500h+var_1498], r12
0x18000876f  movups  [rbp+1400h+var_1478], xmm0
0x180008773  movups  [rsp+1500h+var_1490], xmm1
0x180008778  test    rax, rax
0x18000877b  jz      short loc_180008788
0x18000877d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008782  mov     [rbp+1400h+var_1460], rax
0x180008786  jmp     short loc_18000878C
0x180008788  mov     [rbp+1400h+var_1460], r12
0x18000878c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008793  test    rax, rax
0x180008796  jz      short loc_1800087A2
0x180008798  lea     rcx, [rsp+1500h+var_14E0]
0x18000879d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087a2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800087a9  test    rax, rax
0x1800087ac  jz      short loc_1800087C2
0x1800087ae  mov     r8d, 400h
0x1800087b4  lea     rdx, [rbp+1400h+var_1440]
0x1800087b8  lea     rcx, [rsp+1500h+var_14E0]
0x1800087bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087c2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800087c9  test    rax, rax
0x1800087cc  jz      short loc_1800087D8
0x1800087ce  lea     rcx, [rsp+1500h+var_14E0]
0x1800087d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087d8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800087df  test    rax, rax
0x1800087e2  jz      short loc_1800087F5
0x1800087e4  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800087e9  jnz     short loc_1800087F5
0x1800087eb  lea     rcx, [rsp+1500h+var_14E0]
0x1800087f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087f5  cmp     [rsp+1500h+var_14D8], r12d
0x1800087fa  jge     loc_1800088F7
0x180008800  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180008807  jnz     short loc_180008828
0x180008809  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008810  test    rax, rax
0x180008813  jz      short loc_18000881E
0x180008815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000881a  test    al, al
0x18000881c  jmp     short loc_180008826
0x18000881e  call    cs:__imp_IsDebuggerPresent
0x180008824  test    eax, eax
0x180008826  jz      short loc_18000882F
0x180008828  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000882d  jz      short loc_180008855
0x18000882f  mov     rax, cs:g_pfnResultLoggingCallback
0x180008836  test    rax, rax
0x180008839  jz      short loc_1800088AE
0x18000883b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180008842  jnz     short loc_1800088AE
0x180008844  xor     r8d, r8d
0x180008847  lea     rcx, [rsp+1500h+var_14E0]
0x18000884c  xor     edx, edx
0x18000884e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008853  jmp     short loc_1800088AE
0x180008855  mov     rax, cs:g_pfnResultLoggingCallback
0x18000885c  mov     ebx, 800h
0x180008861  test    rax, rax
0x180008864  jz      short loc_180008883
0x180008866  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000886d  jnz     short loc_180008883
0x18000886f  mov     r8d, ebx
0x180008872  lea     rdx, [rbp+1400h+OutputString]
0x180008879  lea     rcx, [rsp+1500h+var_14E0]
0x18000887e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008883  cmp     [rbp+1400h+OutputString], r12w
0x18000888b  jnz     short loc_1800088A1
0x18000888d  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180008892  mov     rdx, rbx; unsigned __int16 *
0x180008895  lea     rcx, [rbp+1400h+OutputString]; this
0x18000889c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800088a1  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800088a8  call    cs:__imp_OutputDebugStringW
0x1800088ae  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800088b3  jnz     short loc_1800088BE
0x1800088b5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800088bc  jz      short loc_1800088CF
0x1800088be  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800088c5  test    rax, rax
0x1800088c8  jz      short loc_1800088CF
0x1800088ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088cf  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800088d4  jnz     short loc_1800088FD
0x1800088d6  mov     rcx, [rbp+1400h+var_40]
0x1800088dd  xor     rcx, rsp; StackCookie
0x1800088e0  call    __security_check_cookie
0x1800088e5  add     rsp, 14D0h
0x1800088ec  pop     r15
0x1800088ee  pop     r14
0x1800088f0  pop     r12
0x1800088f2  pop     rdi
0x1800088f3  pop     rsi
0x1800088f4  pop     rbx
0x1800088f5  pop     rbp
0x1800088f6  retn
0x1800088f7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800088fd  lea     rcx, [rsp+1500h+var_14E0]; this
0x180008902  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
