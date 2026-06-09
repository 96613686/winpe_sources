# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002364`
- end: `0x1400025f8`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002038`

## callees

- `0x140001600`
- `0x140001fa2`
- `0x140002364`
- `0x140002f54`
- `0x140003f70`
- `0x140004898`
- `0x140004a00`
- `0x140005a30`
- `0x140006010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000240e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000240e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002509`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002509`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002593`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002593`

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
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "wil";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x140002364  mov     [rsp-8+arg_10], rbx
0x140002369  push    rbp
0x14000236a  push    rsi
0x14000236b  push    rdi
0x14000236c  push    r14
0x14000236e  push    r15
0x140002370  lea     rbp, [rsp-13D0h]
0x140002378  mov     eax, 14D0h
0x14000237d  call    _alloca_probe
0x140002382  sub     rsp, rax
0x140002385  mov     rax, cs:__security_cookie
0x14000238c  xor     rax, rsp
0x14000238f  mov     [rbp+13F0h+var_30], rax
0x140002396  mov     rdi, [rbp+13F0h+arg_28]
0x14000239d  mov     esi, edx
0x14000239f  mov     r14, rcx
0x1400023a2  xor     edx, edx; Val
0x1400023a4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1400023a9  mov     r8d, 98h; Size
0x1400023af  call    memset_0
0x1400023b4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1400023bb  xor     r15d, r15d
0x1400023be  mov     [rbp+13F0h+OutputString], r15w
0x1400023c6  mov     [rbp+13F0h+var_1430], r15b
0x1400023ca  mov     ecx, [rdx]; this
0x1400023cc  mov     eax, [rdx+4]
0x1400023cf  mov     [rsp+14F0h+var_14C8], ecx
0x1400023d3  mov     [rsp+14F0h+var_14C4], eax
0x1400023d7  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400023dc  cmp     dword ptr [rdx+8], 1
0x1400023e0  mov     ebx, eax
0x1400023e2  lea     eax, [r15+8]
0x1400023e6  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1400023ee  mov     ecx, r15d
0x1400023f1  cmovz   ecx, eax
0x1400023f4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1400023f8  lea     ecx, [rax-7]
0x1400023fb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002403  inc     ecx
0x140002405  mov     [rsp+14F0h+var_14B8], r15
0x14000240a  mov     [rsp+14F0h+var_14C0], ecx
0x14000240e  call    cs:__imp_GetCurrentThreadId
0x140002414  xorps   xmm0, xmm0
0x140002417  mov     [rsp+14F0h+var_1490], esi
0x14000241b  mov     [rsp+14F0h+var_14B0], eax
0x14000241f  xorps   xmm1, xmm1
0x140002422  lea     rax, aWil; "wil"
0x140002429  mov     [rsp+14F0h+var_148C], ebx
0x14000242d  mov     [rsp+14F0h+var_1498], rax
0x140002432  xor     eax, eax
0x140002434  mov     [rbp+13F0h+var_1458], rax
0x140002438  mov     [rbp+13F0h+var_1470], rax
0x14000243c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002443  mov     [rsp+14F0h+var_14A8], r15
0x140002448  mov     [rsp+14F0h+var_14A0], r15
0x14000244d  mov     [rbp+13F0h+var_1448], rdi
0x140002451  mov     [rbp+13F0h+var_1440], r14
0x140002455  mov     [rsp+14F0h+var_1488], r15
0x14000245a  movups  [rbp+13F0h+var_1468], xmm0
0x14000245e  movups  [rsp+14F0h+var_1480], xmm1
0x140002463  test    rax, rax
0x140002466  jz      short loc_140002473
0x140002468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000246d  mov     [rbp+13F0h+var_1450], rax
0x140002471  jmp     short loc_140002477
0x140002473  mov     [rbp+13F0h+var_1450], r15
0x140002477  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000247e  test    rax, rax
0x140002481  jz      short loc_14000248D
0x140002483  lea     rcx, [rsp+14F0h+var_14D0]
0x140002488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000248d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002494  test    rax, rax
0x140002497  jz      short loc_1400024AD
0x140002499  mov     r8d, 400h
0x14000249f  lea     rdx, [rbp+13F0h+var_1430]
0x1400024a3  lea     rcx, [rsp+14F0h+var_14D0]
0x1400024a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400024ad  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400024b4  test    rax, rax
0x1400024b7  jz      short loc_1400024C3
0x1400024b9  lea     rcx, [rsp+14F0h+var_14D0]
0x1400024be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400024c3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400024ca  test    rax, rax
0x1400024cd  jz      short loc_1400024E0
0x1400024cf  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400024d4  jnz     short loc_1400024E0
0x1400024d6  lea     rcx, [rsp+14F0h+var_14D0]
0x1400024db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400024e0  cmp     [rsp+14F0h+var_14C8], r15d
0x1400024e5  jge     loc_1400025E7
0x1400024eb  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1400024f2  jnz     short loc_140002513
0x1400024f4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400024fb  test    rax, rax
0x1400024fe  jz      short loc_140002509
0x140002500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002505  test    al, al
0x140002507  jmp     short loc_140002511
0x140002509  call    cs:__imp_IsDebuggerPresent
0x14000250f  test    eax, eax
0x140002511  jz      short loc_14000251A
0x140002513  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002518  jz      short loc_140002540
0x14000251a  mov     rax, cs:g_pfnResultLoggingCallback
0x140002521  test    rax, rax
0x140002524  jz      short loc_140002599
0x140002526  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000252d  jnz     short loc_140002599
0x14000252f  xor     r8d, r8d
0x140002532  lea     rcx, [rsp+14F0h+var_14D0]
0x140002537  xor     edx, edx
0x140002539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000253e  jmp     short loc_140002599
0x140002540  mov     rax, cs:g_pfnResultLoggingCallback
0x140002547  mov     ebx, 800h
0x14000254c  test    rax, rax
0x14000254f  jz      short loc_14000256E
0x140002551  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140002558  jnz     short loc_14000256E
0x14000255a  mov     r8d, ebx
0x14000255d  lea     rdx, [rbp+13F0h+OutputString]
0x140002564  lea     rcx, [rsp+14F0h+var_14D0]
0x140002569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000256e  cmp     [rbp+13F0h+OutputString], r15w
0x140002576  jnz     short loc_14000258C
0x140002578  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x14000257d  mov     rdx, rbx; unsigned __int16 *
0x140002580  lea     rcx, [rbp+13F0h+OutputString]; this
0x140002587  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000258c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140002593  call    cs:__imp_OutputDebugStringW
0x140002599  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x14000259e  jnz     short loc_1400025A9
0x1400025a0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1400025a7  jz      short loc_1400025BA
0x1400025a9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400025b0  test    rax, rax
0x1400025b3  jz      short loc_1400025BA
0x1400025b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400025ba  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1400025bf  jnz     short loc_1400025ED
0x1400025c1  mov     rcx, [rbp+13F0h+var_30]
0x1400025c8  xor     rcx, rsp; StackCookie
0x1400025cb  call    __security_check_cookie
0x1400025d0  mov     rbx, [rsp+14F0h+arg_10]
0x1400025d8  add     rsp, 14D0h
0x1400025df  pop     r15
0x1400025e1  pop     r14
0x1400025e3  pop     rdi
0x1400025e4  pop     rsi
0x1400025e5  pop     rbp
0x1400025e6  retn
0x1400025e7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400025ed  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1400025f2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
