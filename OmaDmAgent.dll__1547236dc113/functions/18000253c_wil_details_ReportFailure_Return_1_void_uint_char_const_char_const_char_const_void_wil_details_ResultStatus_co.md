# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000253c`
- end: `0x1800027e5`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002204`

## callees

- `0x18000253c`
- `0x180003874`
- `0x1800050e4`
- `0x180005d90`
- `0x1800060cc`
- `0x18001f3da`
- `0x18001f420`
- `0x18001f4e0`
- `0x180021010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180002778`
- `KERNEL32!OutputDebugStringW` at `0x180002778`
- `KERNEL32!IsDebuggerPresent` at `0x1800026e8`
- `KERNEL32!IsDebuggerPresent` at `0x1800026e8`
- `KERNEL32!GetCurrentThreadId` at `0x1800025e7`
- `KERNEL32!GetCurrentThreadId` at `0x1800025e7`

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
0x18000253c  mov     [rsp-8+arg_10], rbx
0x180002541  push    rbp
0x180002542  push    rsi
0x180002543  push    rdi
0x180002544  push    r14
0x180002546  push    r15
0x180002548  lea     rbp, [rsp-13D0h]
0x180002550  mov     eax, 14D0h
0x180002555  call    _alloca_probe
0x18000255a  sub     rsp, rax
0x18000255d  mov     rax, cs:__security_cookie
0x180002564  xor     rax, rsp
0x180002567  mov     [rbp+13F0h+var_30], rax
0x18000256e  mov     esi, edx
0x180002570  mov     r14, rcx
0x180002573  mov     rdi, [rbp+13F0h+arg_28]
0x18000257a  xor     edx, edx; Val
0x18000257c  mov     r8d, 98h; Size
0x180002582  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002587  call    memset_0
0x18000258c  nop
0x18000258d  xor     r15d, r15d
0x180002590  mov     [rbp+13F0h+OutputString], r15w
0x180002598  mov     [rbp+13F0h+var_1430], r15b
0x18000259c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800025a3  mov     ecx, [rdx]; this
0x1800025a5  mov     [rsp+14F0h+var_14C8], ecx
0x1800025a9  mov     eax, [rdx+4]
0x1800025ac  mov     [rsp+14F0h+var_14C4], eax
0x1800025b0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800025b5  mov     ebx, eax
0x1800025b7  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800025bf  mov     ecx, r15d
0x1800025c2  lea     eax, [r15+8]
0x1800025c6  cmp     dword ptr [rdx+8], 1
0x1800025ca  cmovz   ecx, eax
0x1800025cd  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800025d1  lea     ecx, [rax-7]
0x1800025d4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800025dc  inc     ecx
0x1800025de  mov     [rsp+14F0h+var_14C0], ecx
0x1800025e2  mov     [rsp+14F0h+var_14B8], r15
0x1800025e7  call    cs:__imp_GetCurrentThreadId
0x1800025ee  nop     dword ptr [rax+rax+00h]
0x1800025f3  mov     [rsp+14F0h+var_14B0], eax
0x1800025f7  lea     rax, aWil; "wil"
0x1800025fe  mov     [rsp+14F0h+var_1498], rax
0x180002603  mov     [rsp+14F0h+var_1490], esi
0x180002607  mov     [rsp+14F0h+var_148C], ebx
0x18000260b  mov     [rsp+14F0h+var_14A8], r15
0x180002610  mov     [rsp+14F0h+var_14A0], r15
0x180002615  mov     [rbp+13F0h+var_1448], rdi
0x180002619  mov     [rbp+13F0h+var_1440], r14
0x18000261d  mov     [rsp+14F0h+var_1488], r15
0x180002622  xorps   xmm0, xmm0
0x180002625  xor     eax, eax
0x180002627  movups  [rbp+13F0h+var_1468], xmm0
0x18000262b  mov     [rbp+13F0h+var_1458], rax
0x18000262f  xorps   xmm1, xmm1
0x180002632  movups  [rsp+14F0h+var_1480], xmm1
0x180002637  mov     [rbp+13F0h+var_1470], rax
0x18000263b  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002642  test    rax, rax
0x180002645  jz      short loc_180002652
0x180002647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000264c  mov     [rbp+13F0h+var_1450], rax
0x180002650  jmp     short loc_180002656
0x180002652  mov     [rbp+13F0h+var_1450], r15
0x180002656  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000265d  test    rax, rax
0x180002660  jz      short loc_18000266C
0x180002662  lea     rcx, [rsp+14F0h+var_14D0]
0x180002667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000266c  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002673  test    rax, rax
0x180002676  jz      short loc_18000268C
0x180002678  mov     r8d, 400h
0x18000267e  lea     rdx, [rbp+13F0h+var_1430]
0x180002682  lea     rcx, [rsp+14F0h+var_14D0]
0x180002687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000268c  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002693  test    rax, rax
0x180002696  jz      short loc_1800026A2
0x180002698  lea     rcx, [rsp+14F0h+var_14D0]
0x18000269d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026a2  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800026a9  test    rax, rax
0x1800026ac  jz      short loc_1800026BF
0x1800026ae  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800026b3  jnz     short loc_1800026BF
0x1800026b5  lea     rcx, [rsp+14F0h+var_14D0]
0x1800026ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026bf  cmp     [rsp+14F0h+var_14C8], r15d
0x1800026c4  jge     loc_1800027DF
0x1800026ca  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800026d1  jnz     short loc_1800026F8
0x1800026d3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800026da  test    rax, rax
0x1800026dd  jz      short loc_1800026E8
0x1800026df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026e4  test    al, al
0x1800026e6  jmp     short loc_1800026F6
0x1800026e8  call    cs:__imp_IsDebuggerPresent
0x1800026ef  nop     dword ptr [rax+rax+00h]
0x1800026f4  test    eax, eax
0x1800026f6  jz      short loc_1800026FF
0x1800026f8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800026fd  jz      short loc_180002725
0x1800026ff  mov     rax, cs:g_pfnResultLoggingCallback
0x180002706  test    rax, rax
0x180002709  jz      short loc_180002784
0x18000270b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002712  jnz     short loc_180002784
0x180002714  xor     r8d, r8d
0x180002717  xor     edx, edx
0x180002719  lea     rcx, [rsp+14F0h+var_14D0]
0x18000271e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002723  jmp     short loc_180002784
0x180002725  mov     ebx, 800h
0x18000272a  mov     rax, cs:g_pfnResultLoggingCallback
0x180002731  test    rax, rax
0x180002734  jz      short loc_180002753
0x180002736  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000273d  jnz     short loc_180002753
0x18000273f  mov     r8d, ebx
0x180002742  lea     rdx, [rbp+13F0h+OutputString]
0x180002749  lea     rcx, [rsp+14F0h+var_14D0]
0x18000274e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002753  cmp     [rbp+13F0h+OutputString], r15w
0x18000275b  jnz     short loc_180002771
0x18000275d  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002762  mov     rdx, rbx; unsigned __int16 *
0x180002765  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000276c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002771  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002778  call    cs:__imp_OutputDebugStringW
0x18000277f  nop     dword ptr [rax+rax+00h]
0x180002784  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002789  jnz     short loc_180002794
0x18000278b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180002792  jz      short loc_1800027A6
0x180002794  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000279b  test    rax, rax
0x18000279e  jz      short loc_1800027A6
0x1800027a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027a5  nop
0x1800027a6  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800027ab  jnz     short loc_1800027D4
0x1800027ad  mov     rcx, [rbp+13F0h+var_30]
0x1800027b4  xor     rcx, rsp; StackCookie
0x1800027b7  call    __security_check_cookie
0x1800027bc  mov     rbx, [rsp+14F0h+arg_10]
0x1800027c4  add     rsp, 14D0h
0x1800027cb  pop     r15
0x1800027cd  pop     r14
0x1800027cf  pop     rdi
0x1800027d0  pop     rsi
0x1800027d1  pop     rbp
0x1800027d2  retn
0x1800027d4  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800027d9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800027df  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
