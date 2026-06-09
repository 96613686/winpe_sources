# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004314`
- end: `0x1800045ba`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003f94`

## callees

- `0x1800020c0`
- `0x180002b28`
- `0x180004314`
- `0x180005f94`
- `0x180007c70`
- `0x180009a68`
- `0x180009c20`
- `0x1800164c0`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800043da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800043da`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004559`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004559`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800044cf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800044cf`

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
0x180004314  push    rbp
0x180004316  push    rbx
0x180004317  push    rsi
0x180004318  push    rdi
0x180004319  push    r12
0x18000431b  push    r14
0x18000431d  push    r15
0x18000431f  lea     rbp, [rsp-13D0h]
0x180004327  mov     eax, 14D0h
0x18000432c  call    _alloca_probe
0x180004331  sub     rsp, rax
0x180004334  mov     rax, cs:__security_cookie
0x18000433b  xor     rax, rsp
0x18000433e  mov     [rbp+1400h+var_40], rax
0x180004345  mov     rsi, r8
0x180004348  mov     edi, edx
0x18000434a  mov     rbx, rcx
0x18000434d  mov     r14, [rbp+1400h+arg_28]
0x180004354  xor     edx, edx; Val
0x180004356  mov     r8d, 98h; Size
0x18000435c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004361  call    memset_0
0x180004366  nop
0x180004367  xor     r12d, r12d
0x18000436a  mov     [rbp+1400h+OutputString], r12w
0x180004372  mov     [rbp+1400h+var_1440], r12b
0x180004376  mov     rdx, [rbp+1400h+arg_30]; int
0x18000437d  mov     ecx, [rdx]; this
0x18000437f  mov     [rsp+1500h+var_14D8], ecx
0x180004383  mov     eax, [rdx+4]
0x180004386  mov     [rsp+1500h+var_14D4], eax
0x18000438a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000438f  mov     r15d, eax
0x180004392  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000439a  mov     ecx, r12d
0x18000439d  lea     eax, [r12+8]
0x1800043a2  cmp     dword ptr [rdx+8], 1
0x1800043a6  cmovz   ecx, eax
0x1800043a9  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800043ad  lea     ecx, [rax-7]
0x1800043b0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800043b8  inc     ecx
0x1800043ba  mov     [rsp+1500h+var_14D0], ecx
0x1800043be  mov     rcx, [rbp+1400h+arg_38]
0x1800043c5  test    rcx, rcx
0x1800043c8  jz      short loc_1800043D5
0x1800043ca  cmp     [rcx], r12w
0x1800043ce  mov     [rsp+1500h+var_14C8], rcx
0x1800043d3  jnz     short loc_1800043DA
0x1800043d5  mov     [rsp+1500h+var_14C8], r12
0x1800043da  call    cs:__imp_GetCurrentThreadId
0x1800043e0  mov     [rsp+1500h+var_14C0], eax
0x1800043e4  mov     [rsp+1500h+var_14A8], rsi
0x1800043e9  mov     [rsp+1500h+var_14A0], edi
0x1800043ed  mov     [rsp+1500h+var_149C], r15d
0x1800043f2  mov     [rsp+1500h+var_14B8], r12
0x1800043f7  mov     [rsp+1500h+var_14B0], r12
0x1800043fc  mov     [rbp+1400h+var_1458], r14
0x180004400  mov     [rbp+1400h+var_1450], rbx
0x180004404  mov     [rsp+1500h+var_1498], r12
0x180004409  xorps   xmm0, xmm0
0x18000440c  xor     eax, eax
0x18000440e  movups  [rbp+1400h+var_1478], xmm0
0x180004412  mov     [rbp+1400h+var_1468], rax
0x180004416  xorps   xmm1, xmm1
0x180004419  movups  [rsp+1500h+var_1490], xmm1
0x18000441e  mov     [rbp+1400h+var_1480], rax
0x180004422  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004429  test    rax, rax
0x18000442c  jz      short loc_180004439
0x18000442e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004433  mov     [rbp+1400h+var_1460], rax
0x180004437  jmp     short loc_18000443D
0x180004439  mov     [rbp+1400h+var_1460], r12
0x18000443d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004444  test    rax, rax
0x180004447  jz      short loc_180004453
0x180004449  lea     rcx, [rsp+1500h+var_14E0]
0x18000444e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004453  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000445a  test    rax, rax
0x18000445d  jz      short loc_180004473
0x18000445f  mov     r8d, 400h
0x180004465  lea     rdx, [rbp+1400h+var_1440]
0x180004469  lea     rcx, [rsp+1500h+var_14E0]
0x18000446e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004473  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000447a  test    rax, rax
0x18000447d  jz      short loc_180004489
0x18000447f  lea     rcx, [rsp+1500h+var_14E0]
0x180004484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004489  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004490  test    rax, rax
0x180004493  jz      short loc_1800044A6
0x180004495  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000449a  jnz     short loc_1800044A6
0x18000449c  lea     rcx, [rsp+1500h+var_14E0]
0x1800044a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044a6  cmp     [rsp+1500h+var_14D8], r12d
0x1800044ab  jge     loc_1800045B4
0x1800044b1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800044b8  jnz     short loc_1800044D9
0x1800044ba  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800044c1  test    rax, rax
0x1800044c4  jz      short loc_1800044CF
0x1800044c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044cb  test    al, al
0x1800044cd  jmp     short loc_1800044D7
0x1800044cf  call    cs:__imp_IsDebuggerPresent
0x1800044d5  test    eax, eax
0x1800044d7  jz      short loc_1800044E0
0x1800044d9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800044de  jz      short loc_180004506
0x1800044e0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800044e7  test    rax, rax
0x1800044ea  jz      short loc_18000455F
0x1800044ec  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800044f3  jnz     short loc_18000455F
0x1800044f5  xor     r8d, r8d
0x1800044f8  xor     edx, edx
0x1800044fa  lea     rcx, [rsp+1500h+var_14E0]
0x1800044ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004504  jmp     short loc_18000455F
0x180004506  mov     ebx, 800h
0x18000450b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004512  test    rax, rax
0x180004515  jz      short loc_180004534
0x180004517  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000451e  jnz     short loc_180004534
0x180004520  mov     r8d, ebx
0x180004523  lea     rdx, [rbp+1400h+OutputString]
0x18000452a  lea     rcx, [rsp+1500h+var_14E0]
0x18000452f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004534  cmp     [rbp+1400h+OutputString], r12w
0x18000453c  jnz     short loc_180004552
0x18000453e  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180004543  mov     rdx, rbx; unsigned __int16 *
0x180004546  lea     rcx, [rbp+1400h+OutputString]; this
0x18000454d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004552  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004559  call    cs:__imp_OutputDebugStringW
0x18000455f  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004564  jnz     short loc_18000456F
0x180004566  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000456d  jz      short loc_180004581
0x18000456f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004576  test    rax, rax
0x180004579  jz      short loc_180004581
0x18000457b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004580  nop
0x180004581  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180004586  jnz     short loc_1800045A9
0x180004588  mov     rcx, [rbp+1400h+var_40]
0x18000458f  xor     rcx, rsp; StackCookie
0x180004592  call    __security_check_cookie
0x180004597  add     rsp, 14D0h
0x18000459e  pop     r15
0x1800045a0  pop     r14
0x1800045a2  pop     r12
0x1800045a4  pop     rdi
0x1800045a5  pop     rsi
0x1800045a6  pop     rbx
0x1800045a7  pop     rbp
0x1800045a8  retn
0x1800045a9  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800045ae  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800045b4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
