# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000822c`
- end: `0x1800084e5`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180007d24`

## callees

- `0x180006f60`
- `0x180007b38`
- `0x18000822c`
- `0x180009a74`
- `0x18000ad64`
- `0x18000bbf0`
- `0x18000bda0`
- `0x18003b490`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800082f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800082f2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800083ed`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800083ed`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000847d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000847d`

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
0x18000822c  push    rbp
0x18000822e  push    rbx
0x18000822f  push    rsi
0x180008230  push    rdi
0x180008231  push    r12
0x180008233  push    r14
0x180008235  push    r15
0x180008237  lea     rbp, [rsp-13D0h]
0x18000823f  mov     eax, 14D0h
0x180008244  call    _alloca_probe
0x180008249  sub     rsp, rax
0x18000824c  mov     rax, cs:__security_cookie
0x180008253  xor     rax, rsp
0x180008256  mov     [rbp+1400h+var_40], rax
0x18000825d  mov     rsi, r8
0x180008260  mov     edi, edx
0x180008262  mov     rbx, rcx
0x180008265  mov     r14, [rbp+1400h+arg_28]
0x18000826c  xor     edx, edx; Val
0x18000826e  mov     r8d, 98h; Size
0x180008274  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180008279  call    memset_0
0x18000827e  nop
0x18000827f  xor     r12d, r12d
0x180008282  mov     [rbp+1400h+OutputString], r12w
0x18000828a  mov     [rbp+1400h+var_1440], r12b
0x18000828e  mov     rdx, [rbp+1400h+arg_30]; int
0x180008295  mov     ecx, [rdx]; this
0x180008297  mov     [rsp+1500h+var_14D8], ecx
0x18000829b  mov     eax, [rdx+4]
0x18000829e  mov     [rsp+1500h+var_14D4], eax
0x1800082a2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800082a7  mov     r15d, eax
0x1800082aa  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800082b2  mov     ecx, r12d
0x1800082b5  lea     eax, [r12+8]
0x1800082ba  cmp     dword ptr [rdx+8], 1
0x1800082be  cmovz   ecx, eax
0x1800082c1  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800082c5  lea     ecx, [rax-7]
0x1800082c8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800082d0  inc     ecx
0x1800082d2  mov     [rsp+1500h+var_14D0], ecx
0x1800082d6  mov     rcx, [rbp+1400h+arg_38]
0x1800082dd  test    rcx, rcx
0x1800082e0  jz      short loc_1800082ED
0x1800082e2  cmp     [rcx], r12w
0x1800082e6  mov     [rsp+1500h+var_14C8], rcx
0x1800082eb  jnz     short loc_1800082F2
0x1800082ed  mov     [rsp+1500h+var_14C8], r12
0x1800082f2  call    cs:__imp_GetCurrentThreadId
0x1800082f9  nop     dword ptr [rax+rax+00h]
0x1800082fe  mov     [rsp+1500h+var_14C0], eax
0x180008302  mov     [rsp+1500h+var_14A8], rsi
0x180008307  mov     [rsp+1500h+var_14A0], edi
0x18000830b  mov     [rsp+1500h+var_149C], r15d
0x180008310  mov     [rsp+1500h+var_14B8], r12
0x180008315  mov     [rsp+1500h+var_14B0], r12
0x18000831a  mov     [rbp+1400h+var_1458], r14
0x18000831e  mov     [rbp+1400h+var_1450], rbx
0x180008322  mov     [rsp+1500h+var_1498], r12
0x180008327  xorps   xmm0, xmm0
0x18000832a  xor     eax, eax
0x18000832c  movups  [rbp+1400h+var_1478], xmm0
0x180008330  mov     [rbp+1400h+var_1468], rax
0x180008334  xorps   xmm1, xmm1
0x180008337  movups  [rsp+1500h+var_1490], xmm1
0x18000833c  mov     [rbp+1400h+var_1480], rax
0x180008340  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008347  test    rax, rax
0x18000834a  jz      short loc_180008357
0x18000834c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008351  mov     [rbp+1400h+var_1460], rax
0x180008355  jmp     short loc_18000835B
0x180008357  mov     [rbp+1400h+var_1460], r12
0x18000835b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008362  test    rax, rax
0x180008365  jz      short loc_180008371
0x180008367  lea     rcx, [rsp+1500h+var_14E0]
0x18000836c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008371  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008378  test    rax, rax
0x18000837b  jz      short loc_180008391
0x18000837d  mov     r8d, 400h
0x180008383  lea     rdx, [rbp+1400h+var_1440]
0x180008387  lea     rcx, [rsp+1500h+var_14E0]
0x18000838c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008391  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008398  test    rax, rax
0x18000839b  jz      short loc_1800083A7
0x18000839d  lea     rcx, [rsp+1500h+var_14E0]
0x1800083a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083a7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800083ae  test    rax, rax
0x1800083b1  jz      short loc_1800083C4
0x1800083b3  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800083b8  jnz     short loc_1800083C4
0x1800083ba  lea     rcx, [rsp+1500h+var_14E0]
0x1800083bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083c4  cmp     [rsp+1500h+var_14D8], r12d
0x1800083c9  jge     loc_1800084DF
0x1800083cf  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800083d6  jnz     short loc_1800083FD
0x1800083d8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800083df  test    rax, rax
0x1800083e2  jz      short loc_1800083ED
0x1800083e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083e9  test    al, al
0x1800083eb  jmp     short loc_1800083FB
0x1800083ed  call    cs:__imp_IsDebuggerPresent
0x1800083f4  nop     dword ptr [rax+rax+00h]
0x1800083f9  test    eax, eax
0x1800083fb  jz      short loc_180008404
0x1800083fd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180008402  jz      short loc_18000842A
0x180008404  mov     rax, cs:g_pfnResultLoggingCallback
0x18000840b  test    rax, rax
0x18000840e  jz      short loc_180008489
0x180008410  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180008417  jnz     short loc_180008489
0x180008419  xor     r8d, r8d
0x18000841c  xor     edx, edx
0x18000841e  lea     rcx, [rsp+1500h+var_14E0]
0x180008423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008428  jmp     short loc_180008489
0x18000842a  mov     ebx, 800h
0x18000842f  mov     rax, cs:g_pfnResultLoggingCallback
0x180008436  test    rax, rax
0x180008439  jz      short loc_180008458
0x18000843b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180008442  jnz     short loc_180008458
0x180008444  mov     r8d, ebx
0x180008447  lea     rdx, [rbp+1400h+OutputString]
0x18000844e  lea     rcx, [rsp+1500h+var_14E0]
0x180008453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008458  cmp     [rbp+1400h+OutputString], r12w
0x180008460  jnz     short loc_180008476
0x180008462  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180008467  mov     rdx, rbx; unsigned __int16 *
0x18000846a  lea     rcx, [rbp+1400h+OutputString]; this
0x180008471  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008476  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000847d  call    cs:__imp_OutputDebugStringW
0x180008484  nop     dword ptr [rax+rax+00h]
0x180008489  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000848e  jnz     short loc_180008499
0x180008490  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180008497  jz      short loc_1800084AB
0x180008499  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800084a0  test    rax, rax
0x1800084a3  jz      short loc_1800084AB
0x1800084a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084aa  nop
0x1800084ab  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800084b0  jnz     short loc_1800084D4
0x1800084b2  mov     rcx, [rbp+1400h+var_40]
0x1800084b9  xor     rcx, rsp; StackCookie
0x1800084bc  call    __security_check_cookie
0x1800084c1  add     rsp, 14D0h
0x1800084c8  pop     r15
0x1800084ca  pop     r14
0x1800084cc  pop     r12
0x1800084ce  pop     rdi
0x1800084cf  pop     rsi
0x1800084d0  pop     rbx
0x1800084d1  pop     rbp
0x1800084d2  retn
0x1800084d4  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800084d9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800084df  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
