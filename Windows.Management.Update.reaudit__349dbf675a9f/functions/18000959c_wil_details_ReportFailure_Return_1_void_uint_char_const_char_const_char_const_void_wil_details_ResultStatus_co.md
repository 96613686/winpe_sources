# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000959c`
- end: `0x180009845`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000905c`

## callees

- `0x180002880`
- `0x1800035cc`
- `0x18000959c`
- `0x18000be84`
- `0x18000d9c0`
- `0x18001027c`
- `0x180010464`
- `0x180028a60`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009647`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009647`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009748`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009748`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800097d8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800097d8`

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
0x18000959c  mov     [rsp-8+arg_10], rbx
0x1800095a1  push    rbp
0x1800095a2  push    rsi
0x1800095a3  push    rdi
0x1800095a4  push    r14
0x1800095a6  push    r15
0x1800095a8  lea     rbp, [rsp-13D0h]
0x1800095b0  mov     eax, 14D0h
0x1800095b5  call    _alloca_probe
0x1800095ba  sub     rsp, rax
0x1800095bd  mov     rax, cs:__security_cookie
0x1800095c4  xor     rax, rsp
0x1800095c7  mov     [rbp+13F0h+var_30], rax
0x1800095ce  mov     esi, edx
0x1800095d0  mov     r14, rcx
0x1800095d3  mov     rdi, [rbp+13F0h+arg_28]
0x1800095da  xor     edx, edx; Val
0x1800095dc  mov     r8d, 98h; Size
0x1800095e2  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800095e7  call    memset_0
0x1800095ec  nop
0x1800095ed  xor     r15d, r15d
0x1800095f0  mov     [rbp+13F0h+OutputString], r15w
0x1800095f8  mov     [rbp+13F0h+var_1430], r15b
0x1800095fc  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180009603  mov     ecx, [rdx]; this
0x180009605  mov     [rsp+14F0h+var_14C8], ecx
0x180009609  mov     eax, [rdx+4]
0x18000960c  mov     [rsp+14F0h+var_14C4], eax
0x180009610  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180009615  mov     ebx, eax
0x180009617  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000961f  mov     ecx, r15d
0x180009622  lea     eax, [r15+8]
0x180009626  cmp     dword ptr [rdx+8], 1
0x18000962a  cmovz   ecx, eax
0x18000962d  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180009631  lea     ecx, [rax-7]
0x180009634  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x18000963c  inc     ecx
0x18000963e  mov     [rsp+14F0h+var_14C0], ecx
0x180009642  mov     [rsp+14F0h+var_14B8], r15
0x180009647  call    cs:__imp_GetCurrentThreadId
0x18000964e  nop     dword ptr [rax+rax+00h]
0x180009653  mov     [rsp+14F0h+var_14B0], eax
0x180009657  lea     rax, aWil; "wil"
0x18000965e  mov     [rsp+14F0h+var_1498], rax
0x180009663  mov     [rsp+14F0h+var_1490], esi
0x180009667  mov     [rsp+14F0h+var_148C], ebx
0x18000966b  mov     [rsp+14F0h+var_14A8], r15
0x180009670  mov     [rsp+14F0h+var_14A0], r15
0x180009675  mov     [rbp+13F0h+var_1448], rdi
0x180009679  mov     [rbp+13F0h+var_1440], r14
0x18000967d  mov     [rsp+14F0h+var_1488], r15
0x180009682  xorps   xmm0, xmm0
0x180009685  xor     eax, eax
0x180009687  movups  [rbp+13F0h+var_1468], xmm0
0x18000968b  mov     [rbp+13F0h+var_1458], rax
0x18000968f  xorps   xmm1, xmm1
0x180009692  movups  [rsp+14F0h+var_1480], xmm1
0x180009697  mov     [rbp+13F0h+var_1470], rax
0x18000969b  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800096a2  test    rax, rax
0x1800096a5  jz      short loc_1800096B2
0x1800096a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096ac  mov     [rbp+13F0h+var_1450], rax
0x1800096b0  jmp     short loc_1800096B6
0x1800096b2  mov     [rbp+13F0h+var_1450], r15
0x1800096b6  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800096bd  test    rax, rax
0x1800096c0  jz      short loc_1800096CC
0x1800096c2  lea     rcx, [rsp+14F0h+var_14D0]
0x1800096c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096cc  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800096d3  test    rax, rax
0x1800096d6  jz      short loc_1800096EC
0x1800096d8  mov     r8d, 400h
0x1800096de  lea     rdx, [rbp+13F0h+var_1430]
0x1800096e2  lea     rcx, [rsp+14F0h+var_14D0]
0x1800096e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096ec  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800096f3  test    rax, rax
0x1800096f6  jz      short loc_180009702
0x1800096f8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800096fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009702  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009709  test    rax, rax
0x18000970c  jz      short loc_18000971F
0x18000970e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180009713  jnz     short loc_18000971F
0x180009715  lea     rcx, [rsp+14F0h+var_14D0]
0x18000971a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000971f  cmp     [rsp+14F0h+var_14C8], r15d
0x180009724  jge     loc_18000983F
0x18000972a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180009731  jnz     short loc_180009758
0x180009733  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000973a  test    rax, rax
0x18000973d  jz      short loc_180009748
0x18000973f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009744  test    al, al
0x180009746  jmp     short loc_180009756
0x180009748  call    cs:__imp_IsDebuggerPresent
0x18000974f  nop     dword ptr [rax+rax+00h]
0x180009754  test    eax, eax
0x180009756  jz      short loc_18000975F
0x180009758  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000975d  jz      short loc_180009785
0x18000975f  mov     rax, cs:g_pfnResultLoggingCallback
0x180009766  test    rax, rax
0x180009769  jz      short loc_1800097E4
0x18000976b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180009772  jnz     short loc_1800097E4
0x180009774  xor     r8d, r8d
0x180009777  xor     edx, edx
0x180009779  lea     rcx, [rsp+14F0h+var_14D0]
0x18000977e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009783  jmp     short loc_1800097E4
0x180009785  mov     ebx, 800h
0x18000978a  mov     rax, cs:g_pfnResultLoggingCallback
0x180009791  test    rax, rax
0x180009794  jz      short loc_1800097B3
0x180009796  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000979d  jnz     short loc_1800097B3
0x18000979f  mov     r8d, ebx
0x1800097a2  lea     rdx, [rbp+13F0h+OutputString]
0x1800097a9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800097ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097b3  cmp     [rbp+13F0h+OutputString], r15w
0x1800097bb  jnz     short loc_1800097D1
0x1800097bd  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800097c2  mov     rdx, rbx; unsigned __int16 *
0x1800097c5  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800097cc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800097d1  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800097d8  call    cs:__imp_OutputDebugStringW
0x1800097df  nop     dword ptr [rax+rax+00h]
0x1800097e4  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800097e9  jnz     short loc_1800097F4
0x1800097eb  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800097f2  jz      short loc_180009806
0x1800097f4  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800097fb  test    rax, rax
0x1800097fe  jz      short loc_180009806
0x180009800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009805  nop
0x180009806  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000980b  jnz     short loc_180009834
0x18000980d  mov     rcx, [rbp+13F0h+var_30]
0x180009814  xor     rcx, rsp; StackCookie
0x180009817  call    __security_check_cookie
0x18000981c  mov     rbx, [rsp+14F0h+arg_10]
0x180009824  add     rsp, 14D0h
0x18000982b  pop     r15
0x18000982d  pop     r14
0x18000982f  pop     rdi
0x180009830  pop     rsi
0x180009831  pop     rbp
0x180009832  retn
0x180009834  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180009839  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000983f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
