# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800025fc`
- end: `0x180002890`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800020dc`

## callees

- `0x1800025fc`
- `0x1800044b4`
- `0x180005ca4`
- `0x180007a90`
- `0x180007c4c`
- `0x18000c4a4`
- `0x18000c560`
- `0x18000c5f0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800026a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800026a6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800027a1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800027a1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000282b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000282b`

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
0x1800025fc  mov     [rsp-8+arg_10], rbx
0x180002601  push    rbp
0x180002602  push    rsi
0x180002603  push    rdi
0x180002604  push    r14
0x180002606  push    r15
0x180002608  lea     rbp, [rsp-13D0h]
0x180002610  mov     eax, 14D0h
0x180002615  call    _alloca_probe
0x18000261a  sub     rsp, rax
0x18000261d  mov     rax, cs:__security_cookie
0x180002624  xor     rax, rsp
0x180002627  mov     [rbp+13F0h+var_30], rax
0x18000262e  mov     rdi, [rbp+13F0h+arg_28]
0x180002635  mov     esi, edx
0x180002637  mov     r14, rcx
0x18000263a  xor     edx, edx; Val
0x18000263c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002641  mov     r8d, 98h; Size
0x180002647  call    memset_0
0x18000264c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180002653  xor     r15d, r15d
0x180002656  mov     [rbp+13F0h+OutputString], r15w
0x18000265e  mov     [rbp+13F0h+var_1430], r15b
0x180002662  mov     ecx, [rdx]; this
0x180002664  mov     eax, [rdx+4]
0x180002667  mov     [rsp+14F0h+var_14C8], ecx
0x18000266b  mov     [rsp+14F0h+var_14C4], eax
0x18000266f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002674  cmp     dword ptr [rdx+8], 1
0x180002678  mov     ebx, eax
0x18000267a  lea     eax, [r15+8]
0x18000267e  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180002686  mov     ecx, r15d
0x180002689  cmovz   ecx, eax
0x18000268c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002690  lea     ecx, [rax-7]
0x180002693  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000269b  inc     ecx
0x18000269d  mov     [rsp+14F0h+var_14B8], r15
0x1800026a2  mov     [rsp+14F0h+var_14C0], ecx
0x1800026a6  call    cs:__imp_GetCurrentThreadId
0x1800026ac  xorps   xmm0, xmm0
0x1800026af  mov     [rsp+14F0h+var_1490], esi
0x1800026b3  mov     [rsp+14F0h+var_14B0], eax
0x1800026b7  xorps   xmm1, xmm1
0x1800026ba  lea     rax, aWil; "wil"
0x1800026c1  mov     [rsp+14F0h+var_148C], ebx
0x1800026c5  mov     [rsp+14F0h+var_1498], rax
0x1800026ca  xor     eax, eax
0x1800026cc  mov     [rbp+13F0h+var_1458], rax
0x1800026d0  mov     [rbp+13F0h+var_1470], rax
0x1800026d4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800026db  mov     [rsp+14F0h+var_14A8], r15
0x1800026e0  mov     [rsp+14F0h+var_14A0], r15
0x1800026e5  mov     [rbp+13F0h+var_1448], rdi
0x1800026e9  mov     [rbp+13F0h+var_1440], r14
0x1800026ed  mov     [rsp+14F0h+var_1488], r15
0x1800026f2  movups  [rbp+13F0h+var_1468], xmm0
0x1800026f6  movups  [rsp+14F0h+var_1480], xmm1
0x1800026fb  test    rax, rax
0x1800026fe  jz      short loc_18000270B
0x180002700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002705  mov     [rbp+13F0h+var_1450], rax
0x180002709  jmp     short loc_18000270F
0x18000270b  mov     [rbp+13F0h+var_1450], r15
0x18000270f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002716  test    rax, rax
0x180002719  jz      short loc_180002725
0x18000271b  lea     rcx, [rsp+14F0h+var_14D0]
0x180002720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002725  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000272c  test    rax, rax
0x18000272f  jz      short loc_180002745
0x180002731  mov     r8d, 400h
0x180002737  lea     rdx, [rbp+13F0h+var_1430]
0x18000273b  lea     rcx, [rsp+14F0h+var_14D0]
0x180002740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002745  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000274c  test    rax, rax
0x18000274f  jz      short loc_18000275B
0x180002751  lea     rcx, [rsp+14F0h+var_14D0]
0x180002756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000275b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002762  test    rax, rax
0x180002765  jz      short loc_180002778
0x180002767  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000276c  jnz     short loc_180002778
0x18000276e  lea     rcx, [rsp+14F0h+var_14D0]
0x180002773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002778  cmp     [rsp+14F0h+var_14C8], r15d
0x18000277d  jge     loc_18000287F
0x180002783  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000278a  jnz     short loc_1800027AB
0x18000278c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002793  test    rax, rax
0x180002796  jz      short loc_1800027A1
0x180002798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000279d  test    al, al
0x18000279f  jmp     short loc_1800027A9
0x1800027a1  call    cs:__imp_IsDebuggerPresent
0x1800027a7  test    eax, eax
0x1800027a9  jz      short loc_1800027B2
0x1800027ab  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800027b0  jz      short loc_1800027D8
0x1800027b2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800027b9  test    rax, rax
0x1800027bc  jz      short loc_180002831
0x1800027be  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800027c5  jnz     short loc_180002831
0x1800027c7  xor     r8d, r8d
0x1800027ca  lea     rcx, [rsp+14F0h+var_14D0]
0x1800027cf  xor     edx, edx
0x1800027d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027d6  jmp     short loc_180002831
0x1800027d8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800027df  mov     ebx, 800h
0x1800027e4  test    rax, rax
0x1800027e7  jz      short loc_180002806
0x1800027e9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800027f0  jnz     short loc_180002806
0x1800027f2  mov     r8d, ebx
0x1800027f5  lea     rdx, [rbp+13F0h+OutputString]
0x1800027fc  lea     rcx, [rsp+14F0h+var_14D0]
0x180002801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002806  cmp     [rbp+13F0h+OutputString], r15w
0x18000280e  jnz     short loc_180002824
0x180002810  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002815  mov     rdx, rbx; unsigned __int16 *
0x180002818  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000281f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002824  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000282b  call    cs:__imp_OutputDebugStringW
0x180002831  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002836  jnz     short loc_180002841
0x180002838  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000283f  jz      short loc_180002852
0x180002841  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002848  test    rax, rax
0x18000284b  jz      short loc_180002852
0x18000284d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002852  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180002857  jnz     short loc_180002885
0x180002859  mov     rcx, [rbp+13F0h+var_30]
0x180002860  xor     rcx, rsp; StackCookie
0x180002863  call    __security_check_cookie
0x180002868  mov     rbx, [rsp+14F0h+arg_10]
0x180002870  add     rsp, 14D0h
0x180002877  pop     r15
0x180002879  pop     r14
0x18000287b  pop     rdi
0x18000287c  pop     rsi
0x18000287d  pop     rbp
0x18000287e  retn
0x18000287f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180002885  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000288a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
