# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800026d4`
- end: `0x180002961`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800021b4`

## callees

- `0x180001560`
- `0x180001ef2`
- `0x1800026d4`
- `0x180003844`
- `0x180004740`
- `0x180005650`
- `0x18000572c`
- `0x180007f10`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002782`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002782`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002876`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002876`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002900`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002900`

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
0x1800026d4  push    rbp
0x1800026d6  push    rbx
0x1800026d7  push    rsi
0x1800026d8  push    rdi
0x1800026d9  push    r12
0x1800026db  push    r14
0x1800026dd  push    r15
0x1800026df  lea     rbp, [rsp-13D0h]
0x1800026e7  mov     eax, 14D0h
0x1800026ec  call    _alloca_probe
0x1800026f1  sub     rsp, rax
0x1800026f4  mov     rax, cs:__security_cookie
0x1800026fb  xor     rax, rsp
0x1800026fe  mov     [rbp+1400h+var_40], rax
0x180002705  mov     r14, r8
0x180002708  mov     esi, edx
0x18000270a  mov     r15, rcx
0x18000270d  mov     rdi, [rbp+1400h+arg_28]
0x180002714  xor     edx, edx; Val
0x180002716  mov     r8d, 98h; Size
0x18000271c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180002721  call    memset_0
0x180002726  nop
0x180002727  xor     r12d, r12d
0x18000272a  mov     [rbp+1400h+OutputString], r12w
0x180002732  mov     [rbp+1400h+var_1440], r12b
0x180002736  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18000273d  mov     ecx, [rdx]; this
0x18000273f  mov     [rsp+1500h+var_14D8], ecx
0x180002743  mov     eax, [rdx+4]
0x180002746  mov     [rsp+1500h+var_14D4], eax
0x18000274a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000274f  mov     ebx, eax
0x180002751  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180002759  mov     ecx, r12d
0x18000275c  lea     eax, [r12+8]
0x180002761  cmp     dword ptr [rdx+8], 1
0x180002765  cmovz   ecx, eax
0x180002768  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000276c  lea     ecx, [rax-7]
0x18000276f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002777  inc     ecx
0x180002779  mov     [rsp+1500h+var_14D0], ecx
0x18000277d  mov     [rsp+1500h+var_14C8], r12
0x180002782  call    cs:__imp_GetCurrentThreadId
0x180002788  mov     [rsp+1500h+var_14C0], eax
0x18000278c  mov     [rsp+1500h+var_14A8], r14
0x180002791  mov     [rsp+1500h+var_14A0], esi
0x180002795  mov     [rsp+1500h+var_149C], ebx
0x180002799  mov     [rsp+1500h+var_14B8], r12
0x18000279e  mov     [rsp+1500h+var_14B0], r12
0x1800027a3  mov     [rbp+1400h+var_1458], rdi
0x1800027a7  mov     [rbp+1400h+var_1450], r15
0x1800027ab  mov     [rsp+1500h+var_1498], r12
0x1800027b0  xorps   xmm0, xmm0
0x1800027b3  xor     eax, eax
0x1800027b5  movups  [rbp+1400h+var_1478], xmm0
0x1800027b9  mov     [rbp+1400h+var_1468], rax
0x1800027bd  xorps   xmm1, xmm1
0x1800027c0  movups  [rsp+1500h+var_1490], xmm1
0x1800027c5  mov     [rbp+1400h+var_1480], rax
0x1800027c9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800027d0  test    rax, rax
0x1800027d3  jz      short loc_1800027E0
0x1800027d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027da  mov     [rbp+1400h+var_1460], rax
0x1800027de  jmp     short loc_1800027E4
0x1800027e0  mov     [rbp+1400h+var_1460], r12
0x1800027e4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800027eb  test    rax, rax
0x1800027ee  jz      short loc_1800027FA
0x1800027f0  lea     rcx, [rsp+1500h+var_14E0]
0x1800027f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027fa  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002801  test    rax, rax
0x180002804  jz      short loc_18000281A
0x180002806  mov     r8d, 400h
0x18000280c  lea     rdx, [rbp+1400h+var_1440]
0x180002810  lea     rcx, [rsp+1500h+var_14E0]
0x180002815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000281a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002821  test    rax, rax
0x180002824  jz      short loc_180002830
0x180002826  lea     rcx, [rsp+1500h+var_14E0]
0x18000282b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002830  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002837  test    rax, rax
0x18000283a  jz      short loc_18000284D
0x18000283c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180002841  jnz     short loc_18000284D
0x180002843  lea     rcx, [rsp+1500h+var_14E0]
0x180002848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000284d  cmp     [rsp+1500h+var_14D8], r12d
0x180002852  jge     loc_18000295B
0x180002858  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000285f  jnz     short loc_180002880
0x180002861  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002868  test    rax, rax
0x18000286b  jz      short loc_180002876
0x18000286d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002872  test    al, al
0x180002874  jmp     short loc_18000287E
0x180002876  call    cs:__imp_IsDebuggerPresent
0x18000287c  test    eax, eax
0x18000287e  jz      short loc_180002887
0x180002880  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180002885  jz      short loc_1800028AD
0x180002887  mov     rax, cs:g_pfnResultLoggingCallback
0x18000288e  test    rax, rax
0x180002891  jz      short loc_180002906
0x180002893  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000289a  jnz     short loc_180002906
0x18000289c  xor     r8d, r8d
0x18000289f  xor     edx, edx
0x1800028a1  lea     rcx, [rsp+1500h+var_14E0]
0x1800028a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028ab  jmp     short loc_180002906
0x1800028ad  mov     ebx, 800h
0x1800028b2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800028b9  test    rax, rax
0x1800028bc  jz      short loc_1800028DB
0x1800028be  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800028c5  jnz     short loc_1800028DB
0x1800028c7  mov     r8d, ebx
0x1800028ca  lea     rdx, [rbp+1400h+OutputString]
0x1800028d1  lea     rcx, [rsp+1500h+var_14E0]
0x1800028d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028db  cmp     [rbp+1400h+OutputString], r12w
0x1800028e3  jnz     short loc_1800028F9
0x1800028e5  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800028ea  mov     rdx, rbx; unsigned __int16 *
0x1800028ed  lea     rcx, [rbp+1400h+OutputString]; this
0x1800028f4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800028f9  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180002900  call    cs:__imp_OutputDebugStringW
0x180002906  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000290b  jnz     short loc_180002916
0x18000290d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002914  jz      short loc_180002928
0x180002916  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000291d  test    rax, rax
0x180002920  jz      short loc_180002928
0x180002922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002927  nop
0x180002928  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000292d  jnz     short loc_180002950
0x18000292f  mov     rcx, [rbp+1400h+var_40]
0x180002936  xor     rcx, rsp; StackCookie
0x180002939  call    __security_check_cookie
0x18000293e  add     rsp, 14D0h
0x180002945  pop     r15
0x180002947  pop     r14
0x180002949  pop     r12
0x18000294b  pop     rdi
0x18000294c  pop     rsi
0x18000294d  pop     rbx
0x18000294e  pop     rbp
0x18000294f  retn
0x180002950  lea     rcx, [rsp+1500h+var_14E0]; this
0x180002955  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000295b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
