# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000f350`
- end: `0x18000f5dd`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000aab4`

## callees

- `0x18000ab5c`
- `0x18000d2a0`
- `0x18000df4c`
- `0x18000e694`
- `0x18000f350`
- `0x180010398`
- `0x180010728`
- `0x1800250f0`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f3fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f3fe`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000f4f2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000f4f2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000f57c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000f57c`

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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v17, v15);
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
0x18000f350  push    rbp
0x18000f352  push    rbx
0x18000f353  push    rsi
0x18000f354  push    rdi
0x18000f355  push    r12
0x18000f357  push    r14
0x18000f359  push    r15
0x18000f35b  lea     rbp, [rsp-13D0h]
0x18000f363  mov     eax, 14D0h
0x18000f368  call    _alloca_probe
0x18000f36d  sub     rsp, rax
0x18000f370  mov     rax, cs:__security_cookie
0x18000f377  xor     rax, rsp
0x18000f37a  mov     [rbp+1400h+var_40], rax
0x18000f381  mov     r14, r8
0x18000f384  mov     esi, edx
0x18000f386  mov     r15, rcx
0x18000f389  mov     rdi, [rbp+1400h+arg_28]
0x18000f390  xor     edx, edx; Val
0x18000f392  mov     r8d, 98h; Size
0x18000f398  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000f39d  call    memset_0
0x18000f3a2  nop
0x18000f3a3  xor     r12d, r12d
0x18000f3a6  mov     [rbp+1400h+OutputString], r12w
0x18000f3ae  mov     [rbp+1400h+var_1440], r12b
0x18000f3b2  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18000f3b9  mov     ecx, [rdx]; this
0x18000f3bb  mov     [rsp+1500h+var_14D8], ecx
0x18000f3bf  mov     eax, [rdx+4]
0x18000f3c2  mov     [rsp+1500h+var_14D4], eax
0x18000f3c6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000f3cb  mov     ebx, eax
0x18000f3cd  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000f3d5  mov     ecx, r12d
0x18000f3d8  lea     eax, [r12+8]
0x18000f3dd  cmp     dword ptr [rdx+8], 1
0x18000f3e1  cmovz   ecx, eax
0x18000f3e4  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000f3e8  lea     ecx, [rax-7]
0x18000f3eb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000f3f3  inc     ecx
0x18000f3f5  mov     [rsp+1500h+var_14D0], ecx
0x18000f3f9  mov     [rsp+1500h+var_14C8], r12
0x18000f3fe  call    cs:__imp_GetCurrentThreadId
0x18000f404  mov     [rsp+1500h+var_14C0], eax
0x18000f408  mov     [rsp+1500h+var_14A8], r14
0x18000f40d  mov     [rsp+1500h+var_14A0], esi
0x18000f411  mov     [rsp+1500h+var_149C], ebx
0x18000f415  mov     [rsp+1500h+var_14B8], r12
0x18000f41a  mov     [rsp+1500h+var_14B0], r12
0x18000f41f  mov     [rbp+1400h+var_1458], rdi
0x18000f423  mov     [rbp+1400h+var_1450], r15
0x18000f427  mov     [rsp+1500h+var_1498], r12
0x18000f42c  xorps   xmm0, xmm0
0x18000f42f  xor     eax, eax
0x18000f431  movups  [rbp+1400h+var_1478], xmm0
0x18000f435  mov     [rbp+1400h+var_1468], rax
0x18000f439  xorps   xmm1, xmm1
0x18000f43c  movups  [rsp+1500h+var_1490], xmm1
0x18000f441  mov     [rbp+1400h+var_1480], rax
0x18000f445  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000f44c  test    rax, rax
0x18000f44f  jz      short loc_18000F45C
0x18000f451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f456  mov     [rbp+1400h+var_1460], rax
0x18000f45a  jmp     short loc_18000F460
0x18000f45c  mov     [rbp+1400h+var_1460], r12
0x18000f460  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000f467  test    rax, rax
0x18000f46a  jz      short loc_18000F476
0x18000f46c  lea     rcx, [rsp+1500h+var_14E0]
0x18000f471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f476  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000f47d  test    rax, rax
0x18000f480  jz      short loc_18000F496
0x18000f482  mov     r8d, 400h
0x18000f488  lea     rdx, [rbp+1400h+var_1440]
0x18000f48c  lea     rcx, [rsp+1500h+var_14E0]
0x18000f491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f496  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000f49d  test    rax, rax
0x18000f4a0  jz      short loc_18000F4AC
0x18000f4a2  lea     rcx, [rsp+1500h+var_14E0]
0x18000f4a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4ac  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000f4b3  test    rax, rax
0x18000f4b6  jz      short loc_18000F4C9
0x18000f4b8  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000f4bd  jnz     short loc_18000F4C9
0x18000f4bf  lea     rcx, [rsp+1500h+var_14E0]
0x18000f4c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4c9  cmp     [rsp+1500h+var_14D8], r12d
0x18000f4ce  jge     loc_18000F5D7
0x18000f4d4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000f4db  jnz     short loc_18000F4FC
0x18000f4dd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000f4e4  test    rax, rax
0x18000f4e7  jz      short loc_18000F4F2
0x18000f4e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4ee  test    al, al
0x18000f4f0  jmp     short loc_18000F4FA
0x18000f4f2  call    cs:__imp_IsDebuggerPresent
0x18000f4f8  test    eax, eax
0x18000f4fa  jz      short loc_18000F503
0x18000f4fc  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000f501  jz      short loc_18000F529
0x18000f503  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f50a  test    rax, rax
0x18000f50d  jz      short loc_18000F582
0x18000f50f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000f516  jnz     short loc_18000F582
0x18000f518  xor     r8d, r8d
0x18000f51b  xor     edx, edx
0x18000f51d  lea     rcx, [rsp+1500h+var_14E0]
0x18000f522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f527  jmp     short loc_18000F582
0x18000f529  mov     ebx, 800h
0x18000f52e  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f535  test    rax, rax
0x18000f538  jz      short loc_18000F557
0x18000f53a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000f541  jnz     short loc_18000F557
0x18000f543  mov     r8d, ebx
0x18000f546  lea     rdx, [rbp+1400h+OutputString]
0x18000f54d  lea     rcx, [rsp+1500h+var_14E0]
0x18000f552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f557  cmp     [rbp+1400h+OutputString], r12w
0x18000f55f  jnz     short loc_18000F575
0x18000f561  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000f566  mov     rdx, rbx; wchar_t *
0x18000f569  lea     rcx, [rbp+1400h+OutputString]; this
0x18000f570  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000f575  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000f57c  call    cs:__imp_OutputDebugStringW
0x18000f582  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000f587  jnz     short loc_18000F592
0x18000f589  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000f590  jz      short loc_18000F5A4
0x18000f592  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000f599  test    rax, rax
0x18000f59c  jz      short loc_18000F5A4
0x18000f59e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5a3  nop
0x18000f5a4  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000f5a9  jnz     short loc_18000F5CC
0x18000f5ab  mov     rcx, [rbp+1400h+var_40]
0x18000f5b2  xor     rcx, rsp; StackCookie
0x18000f5b5  call    __security_check_cookie
0x18000f5ba  add     rsp, 14D0h
0x18000f5c1  pop     r15
0x18000f5c3  pop     r14
0x18000f5c5  pop     r12
0x18000f5c7  pop     rdi
0x18000f5c8  pop     rsi
0x18000f5c9  pop     rbx
0x18000f5ca  pop     rbp
0x18000f5cb  retn
0x18000f5cc  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000f5d1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000f5d7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
