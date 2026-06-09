# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140003628`
- end: `0x1400038be`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000314c`

## callees

- `0x140002210`
- `0x140002d50`
- `0x140003628`
- `0x1400053b4`
- `0x140006770`
- `0x140007448`
- `0x14000768c`
- `0x140010de0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400036d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400036d3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003858`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003858`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400037ce`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400037ce`

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
0x140003628  mov     [rsp-8+arg_10], rbx
0x14000362d  push    rbp
0x14000362e  push    rsi
0x14000362f  push    rdi
0x140003630  push    r14
0x140003632  push    r15
0x140003634  lea     rbp, [rsp-13D0h]
0x14000363c  mov     eax, 14D0h
0x140003641  call    _alloca_probe
0x140003646  sub     rsp, rax
0x140003649  mov     rax, cs:__security_cookie
0x140003650  xor     rax, rsp
0x140003653  mov     [rbp+13F0h+var_30], rax
0x14000365a  mov     esi, edx
0x14000365c  mov     r14, rcx
0x14000365f  mov     rdi, [rbp+13F0h+arg_28]
0x140003666  xor     edx, edx; Val
0x140003668  mov     r8d, 98h; Size
0x14000366e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140003673  call    memset_0
0x140003678  nop
0x140003679  xor     r15d, r15d
0x14000367c  mov     [rbp+13F0h+OutputString], r15w
0x140003684  mov     [rbp+13F0h+var_1430], r15b
0x140003688  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x14000368f  mov     ecx, [rdx]; this
0x140003691  mov     [rsp+14F0h+var_14C8], ecx
0x140003695  mov     eax, [rdx+4]
0x140003698  mov     [rsp+14F0h+var_14C4], eax
0x14000369c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400036a1  mov     ebx, eax
0x1400036a3  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1400036ab  mov     ecx, r15d
0x1400036ae  lea     eax, [r15+8]
0x1400036b2  cmp     dword ptr [rdx+8], 1
0x1400036b6  cmovz   ecx, eax
0x1400036b9  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1400036bd  lea     ecx, [rax-7]
0x1400036c0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400036c8  inc     ecx
0x1400036ca  mov     [rsp+14F0h+var_14C0], ecx
0x1400036ce  mov     [rsp+14F0h+var_14B8], r15
0x1400036d3  call    cs:__imp_GetCurrentThreadId
0x1400036d9  mov     [rsp+14F0h+var_14B0], eax
0x1400036dd  lea     rax, aWil; "wil"
0x1400036e4  mov     [rsp+14F0h+var_1498], rax
0x1400036e9  mov     [rsp+14F0h+var_1490], esi
0x1400036ed  mov     [rsp+14F0h+var_148C], ebx
0x1400036f1  mov     [rsp+14F0h+var_14A8], r15
0x1400036f6  mov     [rsp+14F0h+var_14A0], r15
0x1400036fb  mov     [rbp+13F0h+var_1448], rdi
0x1400036ff  mov     [rbp+13F0h+var_1440], r14
0x140003703  mov     [rsp+14F0h+var_1488], r15
0x140003708  xorps   xmm0, xmm0
0x14000370b  xor     eax, eax
0x14000370d  movups  [rbp+13F0h+var_1468], xmm0
0x140003711  mov     [rbp+13F0h+var_1458], rax
0x140003715  xorps   xmm1, xmm1
0x140003718  movups  [rsp+14F0h+var_1480], xmm1
0x14000371d  mov     [rbp+13F0h+var_1470], rax
0x140003721  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003728  test    rax, rax
0x14000372b  jz      short loc_140003738
0x14000372d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003732  mov     [rbp+13F0h+var_1450], rax
0x140003736  jmp     short loc_14000373C
0x140003738  mov     [rbp+13F0h+var_1450], r15
0x14000373c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003743  test    rax, rax
0x140003746  jz      short loc_140003752
0x140003748  lea     rcx, [rsp+14F0h+var_14D0]
0x14000374d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003752  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003759  test    rax, rax
0x14000375c  jz      short loc_140003772
0x14000375e  mov     r8d, 400h
0x140003764  lea     rdx, [rbp+13F0h+var_1430]
0x140003768  lea     rcx, [rsp+14F0h+var_14D0]
0x14000376d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003772  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003779  test    rax, rax
0x14000377c  jz      short loc_140003788
0x14000377e  lea     rcx, [rsp+14F0h+var_14D0]
0x140003783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003788  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000378f  test    rax, rax
0x140003792  jz      short loc_1400037A5
0x140003794  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140003799  jnz     short loc_1400037A5
0x14000379b  lea     rcx, [rsp+14F0h+var_14D0]
0x1400037a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037a5  cmp     [rsp+14F0h+var_14C8], r15d
0x1400037aa  jge     loc_1400038B8
0x1400037b0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1400037b7  jnz     short loc_1400037D8
0x1400037b9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400037c0  test    rax, rax
0x1400037c3  jz      short loc_1400037CE
0x1400037c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037ca  test    al, al
0x1400037cc  jmp     short loc_1400037D6
0x1400037ce  call    cs:__imp_IsDebuggerPresent
0x1400037d4  test    eax, eax
0x1400037d6  jz      short loc_1400037DF
0x1400037d8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400037dd  jz      short loc_140003805
0x1400037df  mov     rax, cs:g_pfnResultLoggingCallback
0x1400037e6  test    rax, rax
0x1400037e9  jz      short loc_14000385E
0x1400037eb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400037f2  jnz     short loc_14000385E
0x1400037f4  xor     r8d, r8d
0x1400037f7  xor     edx, edx
0x1400037f9  lea     rcx, [rsp+14F0h+var_14D0]
0x1400037fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003803  jmp     short loc_14000385E
0x140003805  mov     ebx, 800h
0x14000380a  mov     rax, cs:g_pfnResultLoggingCallback
0x140003811  test    rax, rax
0x140003814  jz      short loc_140003833
0x140003816  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000381d  jnz     short loc_140003833
0x14000381f  mov     r8d, ebx
0x140003822  lea     rdx, [rbp+13F0h+OutputString]
0x140003829  lea     rcx, [rsp+14F0h+var_14D0]
0x14000382e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003833  cmp     [rbp+13F0h+OutputString], r15w
0x14000383b  jnz     short loc_140003851
0x14000383d  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140003842  mov     rdx, rbx; unsigned __int16 *
0x140003845  lea     rcx, [rbp+13F0h+OutputString]; this
0x14000384c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140003851  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140003858  call    cs:__imp_OutputDebugStringW
0x14000385e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140003863  jnz     short loc_14000386E
0x140003865  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x14000386c  jz      short loc_140003880
0x14000386e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003875  test    rax, rax
0x140003878  jz      short loc_140003880
0x14000387a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000387f  nop
0x140003880  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140003885  jnz     short loc_1400038AD
0x140003887  mov     rcx, [rbp+13F0h+var_30]
0x14000388e  xor     rcx, rsp; StackCookie
0x140003891  call    __security_check_cookie
0x140003896  mov     rbx, [rsp+14F0h+arg_10]
0x14000389e  add     rsp, 14D0h
0x1400038a5  pop     r15
0x1400038a7  pop     r14
0x1400038a9  pop     rdi
0x1400038aa  pop     rsi
0x1400038ab  pop     rbp
0x1400038ac  retn
0x1400038ad  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1400038b2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1400038b8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
