# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1400024e4`
- end: `0x140002771`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140001fbc`

## callees

- `0x140001530`
- `0x140001f50`
- `0x1400024e4`
- `0x140003704`
- `0x140004600`
- `0x140005500`
- `0x1400055dc`
- `0x140008990`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002592`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002592`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002710`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002710`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002686`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002686`

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
0x1400024e4  push    rbp
0x1400024e6  push    rbx
0x1400024e7  push    rsi
0x1400024e8  push    rdi
0x1400024e9  push    r12
0x1400024eb  push    r14
0x1400024ed  push    r15
0x1400024ef  lea     rbp, [rsp-13D0h]
0x1400024f7  mov     eax, 14D0h
0x1400024fc  call    _alloca_probe
0x140002501  sub     rsp, rax
0x140002504  mov     rax, cs:__security_cookie
0x14000250b  xor     rax, rsp
0x14000250e  mov     [rbp+1400h+var_40], rax
0x140002515  mov     r14, r8
0x140002518  mov     esi, edx
0x14000251a  mov     r15, rcx
0x14000251d  mov     rdi, [rbp+1400h+arg_28]
0x140002524  xor     edx, edx; Val
0x140002526  mov     r8d, 98h; Size
0x14000252c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140002531  call    memset_0
0x140002536  nop
0x140002537  xor     r12d, r12d
0x14000253a  mov     [rbp+1400h+OutputString], r12w
0x140002542  mov     [rbp+1400h+var_1440], r12b
0x140002546  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x14000254d  mov     ecx, [rdx]; this
0x14000254f  mov     [rsp+1500h+var_14D8], ecx
0x140002553  mov     eax, [rdx+4]
0x140002556  mov     [rsp+1500h+var_14D4], eax
0x14000255a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000255f  mov     ebx, eax
0x140002561  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140002569  mov     ecx, r12d
0x14000256c  lea     eax, [r12+8]
0x140002571  cmp     dword ptr [rdx+8], 1
0x140002575  cmovz   ecx, eax
0x140002578  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x14000257c  lea     ecx, [rax-7]
0x14000257f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002587  inc     ecx
0x140002589  mov     [rsp+1500h+var_14D0], ecx
0x14000258d  mov     [rsp+1500h+var_14C8], r12
0x140002592  call    cs:__imp_GetCurrentThreadId
0x140002598  mov     [rsp+1500h+var_14C0], eax
0x14000259c  mov     [rsp+1500h+var_14A8], r14
0x1400025a1  mov     [rsp+1500h+var_14A0], esi
0x1400025a5  mov     [rsp+1500h+var_149C], ebx
0x1400025a9  mov     [rsp+1500h+var_14B8], r12
0x1400025ae  mov     [rsp+1500h+var_14B0], r12
0x1400025b3  mov     [rbp+1400h+var_1458], rdi
0x1400025b7  mov     [rbp+1400h+var_1450], r15
0x1400025bb  mov     [rsp+1500h+var_1498], r12
0x1400025c0  xorps   xmm0, xmm0
0x1400025c3  xor     eax, eax
0x1400025c5  movups  [rbp+1400h+var_1478], xmm0
0x1400025c9  mov     [rbp+1400h+var_1468], rax
0x1400025cd  xorps   xmm1, xmm1
0x1400025d0  movups  [rsp+1500h+var_1490], xmm1
0x1400025d5  mov     [rbp+1400h+var_1480], rax
0x1400025d9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400025e0  test    rax, rax
0x1400025e3  jz      short loc_1400025F0
0x1400025e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400025ea  mov     [rbp+1400h+var_1460], rax
0x1400025ee  jmp     short loc_1400025F4
0x1400025f0  mov     [rbp+1400h+var_1460], r12
0x1400025f4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400025fb  test    rax, rax
0x1400025fe  jz      short loc_14000260A
0x140002600  lea     rcx, [rsp+1500h+var_14E0]
0x140002605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000260a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002611  test    rax, rax
0x140002614  jz      short loc_14000262A
0x140002616  mov     r8d, 400h
0x14000261c  lea     rdx, [rbp+1400h+var_1440]
0x140002620  lea     rcx, [rsp+1500h+var_14E0]
0x140002625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000262a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002631  test    rax, rax
0x140002634  jz      short loc_140002640
0x140002636  lea     rcx, [rsp+1500h+var_14E0]
0x14000263b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002640  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002647  test    rax, rax
0x14000264a  jz      short loc_14000265D
0x14000264c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140002651  jnz     short loc_14000265D
0x140002653  lea     rcx, [rsp+1500h+var_14E0]
0x140002658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000265d  cmp     [rsp+1500h+var_14D8], r12d
0x140002662  jge     loc_14000276B
0x140002668  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x14000266f  jnz     short loc_140002690
0x140002671  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002678  test    rax, rax
0x14000267b  jz      short loc_140002686
0x14000267d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002682  test    al, al
0x140002684  jmp     short loc_14000268E
0x140002686  call    cs:__imp_IsDebuggerPresent
0x14000268c  test    eax, eax
0x14000268e  jz      short loc_140002697
0x140002690  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140002695  jz      short loc_1400026BD
0x140002697  mov     rax, cs:g_pfnResultLoggingCallback
0x14000269e  test    rax, rax
0x1400026a1  jz      short loc_140002716
0x1400026a3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400026aa  jnz     short loc_140002716
0x1400026ac  xor     r8d, r8d
0x1400026af  xor     edx, edx
0x1400026b1  lea     rcx, [rsp+1500h+var_14E0]
0x1400026b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400026bb  jmp     short loc_140002716
0x1400026bd  mov     ebx, 800h
0x1400026c2  mov     rax, cs:g_pfnResultLoggingCallback
0x1400026c9  test    rax, rax
0x1400026cc  jz      short loc_1400026EB
0x1400026ce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400026d5  jnz     short loc_1400026EB
0x1400026d7  mov     r8d, ebx
0x1400026da  lea     rdx, [rbp+1400h+OutputString]
0x1400026e1  lea     rcx, [rsp+1500h+var_14E0]
0x1400026e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400026eb  cmp     [rbp+1400h+OutputString], r12w
0x1400026f3  jnz     short loc_140002709
0x1400026f5  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1400026fa  mov     rdx, rbx; unsigned __int16 *
0x1400026fd  lea     rcx, [rbp+1400h+OutputString]; this
0x140002704  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140002709  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140002710  call    cs:__imp_OutputDebugStringW
0x140002716  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x14000271b  jnz     short loc_140002726
0x14000271d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140002724  jz      short loc_140002738
0x140002726  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000272d  test    rax, rax
0x140002730  jz      short loc_140002738
0x140002732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002737  nop
0x140002738  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x14000273d  jnz     short loc_140002760
0x14000273f  mov     rcx, [rbp+1400h+var_40]
0x140002746  xor     rcx, rsp; StackCookie
0x140002749  call    __security_check_cookie
0x14000274e  add     rsp, 14D0h
0x140002755  pop     r15
0x140002757  pop     r14
0x140002759  pop     r12
0x14000275b  pop     rdi
0x14000275c  pop     rsi
0x14000275d  pop     rbx
0x14000275e  pop     rbp
0x14000275f  retn
0x140002760  lea     rcx, [rsp+1500h+var_14E0]; this
0x140002765  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000276b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
