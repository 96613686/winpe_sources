# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800082cc`
- end: `0x180008559`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180006f50`

## callees

- `0x1800082cc`
- `0x1800097dc`
- `0x18000ada0`
- `0x18000c388`
- `0x18000c664`
- `0x18000f076`
- `0x18000f0a0`
- `0x18000f160`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000837a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000837a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000846e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000846e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800084f8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800084f8`

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
0x1800082cc  push    rbp
0x1800082ce  push    rbx
0x1800082cf  push    rsi
0x1800082d0  push    rdi
0x1800082d1  push    r12
0x1800082d3  push    r14
0x1800082d5  push    r15
0x1800082d7  lea     rbp, [rsp-13D0h]
0x1800082df  mov     eax, 14D0h
0x1800082e4  call    _alloca_probe
0x1800082e9  sub     rsp, rax
0x1800082ec  mov     rax, cs:__security_cookie
0x1800082f3  xor     rax, rsp
0x1800082f6  mov     [rbp+1400h+var_40], rax
0x1800082fd  mov     r14, r8
0x180008300  mov     esi, edx
0x180008302  mov     r15, rcx
0x180008305  mov     rdi, [rbp+1400h+arg_28]
0x18000830c  xor     edx, edx; Val
0x18000830e  mov     r8d, 98h; Size
0x180008314  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180008319  call    memset_0
0x18000831e  nop
0x18000831f  xor     r12d, r12d
0x180008322  mov     [rbp+1400h+OutputString], r12w
0x18000832a  mov     [rbp+1400h+var_1440], r12b
0x18000832e  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180008335  mov     ecx, [rdx]; this
0x180008337  mov     [rsp+1500h+var_14D8], ecx
0x18000833b  mov     eax, [rdx+4]
0x18000833e  mov     [rsp+1500h+var_14D4], eax
0x180008342  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008347  mov     ebx, eax
0x180008349  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180008351  mov     ecx, r12d
0x180008354  lea     eax, [r12+8]
0x180008359  cmp     dword ptr [rdx+8], 1
0x18000835d  cmovz   ecx, eax
0x180008360  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180008364  lea     ecx, [rax-7]
0x180008367  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000836f  inc     ecx
0x180008371  mov     [rsp+1500h+var_14D0], ecx
0x180008375  mov     [rsp+1500h+var_14C8], r12
0x18000837a  call    cs:__imp_GetCurrentThreadId
0x180008380  mov     [rsp+1500h+var_14C0], eax
0x180008384  mov     [rsp+1500h+var_14A8], r14
0x180008389  mov     [rsp+1500h+var_14A0], esi
0x18000838d  mov     [rsp+1500h+var_149C], ebx
0x180008391  mov     [rsp+1500h+var_14B8], r12
0x180008396  mov     [rsp+1500h+var_14B0], r12
0x18000839b  mov     [rbp+1400h+var_1458], rdi
0x18000839f  mov     [rbp+1400h+var_1450], r15
0x1800083a3  mov     [rsp+1500h+var_1498], r12
0x1800083a8  xorps   xmm0, xmm0
0x1800083ab  xor     eax, eax
0x1800083ad  movups  [rbp+1400h+var_1478], xmm0
0x1800083b1  mov     [rbp+1400h+var_1468], rax
0x1800083b5  xorps   xmm1, xmm1
0x1800083b8  movups  [rsp+1500h+var_1490], xmm1
0x1800083bd  mov     [rbp+1400h+var_1480], rax
0x1800083c1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800083c8  test    rax, rax
0x1800083cb  jz      short loc_1800083D8
0x1800083cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083d2  mov     [rbp+1400h+var_1460], rax
0x1800083d6  jmp     short loc_1800083DC
0x1800083d8  mov     [rbp+1400h+var_1460], r12
0x1800083dc  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800083e3  test    rax, rax
0x1800083e6  jz      short loc_1800083F2
0x1800083e8  lea     rcx, [rsp+1500h+var_14E0]
0x1800083ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083f2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800083f9  test    rax, rax
0x1800083fc  jz      short loc_180008412
0x1800083fe  mov     r8d, 400h
0x180008404  lea     rdx, [rbp+1400h+var_1440]
0x180008408  lea     rcx, [rsp+1500h+var_14E0]
0x18000840d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008412  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008419  test    rax, rax
0x18000841c  jz      short loc_180008428
0x18000841e  lea     rcx, [rsp+1500h+var_14E0]
0x180008423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008428  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000842f  test    rax, rax
0x180008432  jz      short loc_180008445
0x180008434  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180008439  jnz     short loc_180008445
0x18000843b  lea     rcx, [rsp+1500h+var_14E0]
0x180008440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008445  cmp     [rsp+1500h+var_14D8], r12d
0x18000844a  jge     loc_180008553
0x180008450  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180008457  jnz     short loc_180008478
0x180008459  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008460  test    rax, rax
0x180008463  jz      short loc_18000846E
0x180008465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000846a  test    al, al
0x18000846c  jmp     short loc_180008476
0x18000846e  call    cs:__imp_IsDebuggerPresent
0x180008474  test    eax, eax
0x180008476  jz      short loc_18000847F
0x180008478  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000847d  jz      short loc_1800084A5
0x18000847f  mov     rax, cs:g_pfnResultLoggingCallback
0x180008486  test    rax, rax
0x180008489  jz      short loc_1800084FE
0x18000848b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180008492  jnz     short loc_1800084FE
0x180008494  xor     r8d, r8d
0x180008497  xor     edx, edx
0x180008499  lea     rcx, [rsp+1500h+var_14E0]
0x18000849e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084a3  jmp     short loc_1800084FE
0x1800084a5  mov     ebx, 800h
0x1800084aa  mov     rax, cs:g_pfnResultLoggingCallback
0x1800084b1  test    rax, rax
0x1800084b4  jz      short loc_1800084D3
0x1800084b6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800084bd  jnz     short loc_1800084D3
0x1800084bf  mov     r8d, ebx
0x1800084c2  lea     rdx, [rbp+1400h+OutputString]
0x1800084c9  lea     rcx, [rsp+1500h+var_14E0]
0x1800084ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084d3  cmp     [rbp+1400h+OutputString], r12w
0x1800084db  jnz     short loc_1800084F1
0x1800084dd  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800084e2  mov     rdx, rbx; unsigned __int16 *
0x1800084e5  lea     rcx, [rbp+1400h+OutputString]; this
0x1800084ec  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800084f1  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800084f8  call    cs:__imp_OutputDebugStringW
0x1800084fe  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180008503  jnz     short loc_18000850E
0x180008505  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000850c  jz      short loc_180008520
0x18000850e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008515  test    rax, rax
0x180008518  jz      short loc_180008520
0x18000851a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000851f  nop
0x180008520  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180008525  jnz     short loc_180008548
0x180008527  mov     rcx, [rbp+1400h+var_40]
0x18000852e  xor     rcx, rsp; StackCookie
0x180008531  call    __security_check_cookie
0x180008536  add     rsp, 14D0h
0x18000853d  pop     r15
0x18000853f  pop     r14
0x180008541  pop     r12
0x180008543  pop     rdi
0x180008544  pop     rsi
0x180008545  pop     rbx
0x180008546  pop     rbp
0x180008547  retn
0x180008548  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000854d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180008553  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
