# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800030c8`
- end: `0x18000336e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002b58`

## callees

- `0x1800030c8`
- `0x180004694`
- `0x1800056f0`
- `0x1800069d0`
- `0x180006ba4`
- `0x180021822`
- `0x180021850`
- `0x180021910`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000318e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000318e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003283`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003283`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000330d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000330d`

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
0x1800030c8  push    rbp
0x1800030ca  push    rbx
0x1800030cb  push    rsi
0x1800030cc  push    rdi
0x1800030cd  push    r12
0x1800030cf  push    r14
0x1800030d1  push    r15
0x1800030d3  lea     rbp, [rsp-13D0h]
0x1800030db  mov     eax, 14D0h
0x1800030e0  call    _alloca_probe
0x1800030e5  sub     rsp, rax
0x1800030e8  mov     rax, cs:__security_cookie
0x1800030ef  xor     rax, rsp
0x1800030f2  mov     [rbp+1400h+var_40], rax
0x1800030f9  mov     rsi, r8
0x1800030fc  mov     edi, edx
0x1800030fe  mov     rbx, rcx
0x180003101  mov     r14, [rbp+1400h+arg_28]
0x180003108  xor     edx, edx; Val
0x18000310a  mov     r8d, 98h; Size
0x180003110  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003115  call    memset_0
0x18000311a  nop
0x18000311b  xor     r12d, r12d
0x18000311e  mov     [rbp+1400h+OutputString], r12w
0x180003126  mov     [rbp+1400h+var_1440], r12b
0x18000312a  mov     rdx, [rbp+1400h+arg_30]; int
0x180003131  mov     ecx, [rdx]; this
0x180003133  mov     [rsp+1500h+var_14D8], ecx
0x180003137  mov     eax, [rdx+4]
0x18000313a  mov     [rsp+1500h+var_14D4], eax
0x18000313e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003143  mov     r15d, eax
0x180003146  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000314e  mov     ecx, r12d
0x180003151  lea     eax, [r12+8]
0x180003156  cmp     dword ptr [rdx+8], 1
0x18000315a  cmovz   ecx, eax
0x18000315d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003161  lea     ecx, [rax-7]
0x180003164  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000316c  inc     ecx
0x18000316e  mov     [rsp+1500h+var_14D0], ecx
0x180003172  mov     rcx, [rbp+1400h+arg_38]
0x180003179  test    rcx, rcx
0x18000317c  jz      short loc_180003189
0x18000317e  cmp     [rcx], r12w
0x180003182  mov     [rsp+1500h+var_14C8], rcx
0x180003187  jnz     short loc_18000318E
0x180003189  mov     [rsp+1500h+var_14C8], r12
0x18000318e  call    cs:__imp_GetCurrentThreadId
0x180003194  mov     [rsp+1500h+var_14C0], eax
0x180003198  mov     [rsp+1500h+var_14A8], rsi
0x18000319d  mov     [rsp+1500h+var_14A0], edi
0x1800031a1  mov     [rsp+1500h+var_149C], r15d
0x1800031a6  mov     [rsp+1500h+var_14B8], r12
0x1800031ab  mov     [rsp+1500h+var_14B0], r12
0x1800031b0  mov     [rbp+1400h+var_1458], r14
0x1800031b4  mov     [rbp+1400h+var_1450], rbx
0x1800031b8  mov     [rsp+1500h+var_1498], r12
0x1800031bd  xorps   xmm0, xmm0
0x1800031c0  xor     eax, eax
0x1800031c2  movups  [rbp+1400h+var_1478], xmm0
0x1800031c6  mov     [rbp+1400h+var_1468], rax
0x1800031ca  xorps   xmm1, xmm1
0x1800031cd  movups  [rsp+1500h+var_1490], xmm1
0x1800031d2  mov     [rbp+1400h+var_1480], rax
0x1800031d6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800031dd  test    rax, rax
0x1800031e0  jz      short loc_1800031ED
0x1800031e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031e7  mov     [rbp+1400h+var_1460], rax
0x1800031eb  jmp     short loc_1800031F1
0x1800031ed  mov     [rbp+1400h+var_1460], r12
0x1800031f1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800031f8  test    rax, rax
0x1800031fb  jz      short loc_180003207
0x1800031fd  lea     rcx, [rsp+1500h+var_14E0]
0x180003202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003207  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000320e  test    rax, rax
0x180003211  jz      short loc_180003227
0x180003213  mov     r8d, 400h
0x180003219  lea     rdx, [rbp+1400h+var_1440]
0x18000321d  lea     rcx, [rsp+1500h+var_14E0]
0x180003222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003227  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000322e  test    rax, rax
0x180003231  jz      short loc_18000323D
0x180003233  lea     rcx, [rsp+1500h+var_14E0]
0x180003238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000323d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003244  test    rax, rax
0x180003247  jz      short loc_18000325A
0x180003249  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000324e  jnz     short loc_18000325A
0x180003250  lea     rcx, [rsp+1500h+var_14E0]
0x180003255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000325a  cmp     [rsp+1500h+var_14D8], r12d
0x18000325f  jge     loc_180003368
0x180003265  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000326c  jnz     short loc_18000328D
0x18000326e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003275  test    rax, rax
0x180003278  jz      short loc_180003283
0x18000327a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000327f  test    al, al
0x180003281  jmp     short loc_18000328B
0x180003283  call    cs:__imp_IsDebuggerPresent
0x180003289  test    eax, eax
0x18000328b  jz      short loc_180003294
0x18000328d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003292  jz      short loc_1800032BA
0x180003294  mov     rax, cs:g_pfnResultLoggingCallback
0x18000329b  test    rax, rax
0x18000329e  jz      short loc_180003313
0x1800032a0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800032a7  jnz     short loc_180003313
0x1800032a9  xor     r8d, r8d
0x1800032ac  xor     edx, edx
0x1800032ae  lea     rcx, [rsp+1500h+var_14E0]
0x1800032b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032b8  jmp     short loc_180003313
0x1800032ba  mov     ebx, 800h
0x1800032bf  mov     rax, cs:g_pfnResultLoggingCallback
0x1800032c6  test    rax, rax
0x1800032c9  jz      short loc_1800032E8
0x1800032cb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800032d2  jnz     short loc_1800032E8
0x1800032d4  mov     r8d, ebx
0x1800032d7  lea     rdx, [rbp+1400h+OutputString]
0x1800032de  lea     rcx, [rsp+1500h+var_14E0]
0x1800032e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032e8  cmp     [rbp+1400h+OutputString], r12w
0x1800032f0  jnz     short loc_180003306
0x1800032f2  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800032f7  mov     rdx, rbx; unsigned __int16 *
0x1800032fa  lea     rcx, [rbp+1400h+OutputString]; this
0x180003301  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003306  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000330d  call    cs:__imp_OutputDebugStringW
0x180003313  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003318  jnz     short loc_180003323
0x18000331a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003321  jz      short loc_180003335
0x180003323  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000332a  test    rax, rax
0x18000332d  jz      short loc_180003335
0x18000332f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003334  nop
0x180003335  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000333a  jnz     short loc_18000335D
0x18000333c  mov     rcx, [rbp+1400h+var_40]
0x180003343  xor     rcx, rsp; StackCookie
0x180003346  call    __security_check_cookie
0x18000334b  add     rsp, 14D0h
0x180003352  pop     r15
0x180003354  pop     r14
0x180003356  pop     r12
0x180003358  pop     rdi
0x180003359  pop     rsi
0x18000335a  pop     rbx
0x18000335b  pop     rbp
0x18000335c  retn
0x18000335d  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003362  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003368  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
