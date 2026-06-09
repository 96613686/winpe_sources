# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1400045e4`
- end: `0x140004871`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002ae8`

## callees

- `0x1400031b0`
- `0x140003de8`
- `0x1400045e4`
- `0x1400060a4`
- `0x14000789c`
- `0x140009348`
- `0x140009554`
- `0x14000a3b0`
- `0x14000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004692`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004692`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004810`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004810`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004786`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004786`

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
0x1400045e4  push    rbp
0x1400045e6  push    rbx
0x1400045e7  push    rsi
0x1400045e8  push    rdi
0x1400045e9  push    r12
0x1400045eb  push    r14
0x1400045ed  push    r15
0x1400045ef  lea     rbp, [rsp-13D0h]
0x1400045f7  mov     eax, 14D0h
0x1400045fc  call    _alloca_probe
0x140004601  sub     rsp, rax
0x140004604  mov     rax, cs:__security_cookie
0x14000460b  xor     rax, rsp
0x14000460e  mov     [rbp+1400h+var_40], rax
0x140004615  mov     r14, r8
0x140004618  mov     esi, edx
0x14000461a  mov     r15, rcx
0x14000461d  mov     rdi, [rbp+1400h+arg_28]
0x140004624  xor     edx, edx; Val
0x140004626  mov     r8d, 98h; Size
0x14000462c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140004631  call    memset_0
0x140004636  nop
0x140004637  xor     r12d, r12d
0x14000463a  mov     [rbp+1400h+OutputString], r12w
0x140004642  mov     [rbp+1400h+var_1440], r12b
0x140004646  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x14000464d  mov     ecx, [rdx]; this
0x14000464f  mov     [rsp+1500h+var_14D8], ecx
0x140004653  mov     eax, [rdx+4]
0x140004656  mov     [rsp+1500h+var_14D4], eax
0x14000465a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000465f  mov     ebx, eax
0x140004661  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140004669  mov     ecx, r12d
0x14000466c  lea     eax, [r12+8]
0x140004671  cmp     dword ptr [rdx+8], 1
0x140004675  cmovz   ecx, eax
0x140004678  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x14000467c  lea     ecx, [rax-7]
0x14000467f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140004687  inc     ecx
0x140004689  mov     [rsp+1500h+var_14D0], ecx
0x14000468d  mov     [rsp+1500h+var_14C8], r12
0x140004692  call    cs:__imp_GetCurrentThreadId
0x140004698  mov     [rsp+1500h+var_14C0], eax
0x14000469c  mov     [rsp+1500h+var_14A8], r14
0x1400046a1  mov     [rsp+1500h+var_14A0], esi
0x1400046a5  mov     [rsp+1500h+var_149C], ebx
0x1400046a9  mov     [rsp+1500h+var_14B8], r12
0x1400046ae  mov     [rsp+1500h+var_14B0], r12
0x1400046b3  mov     [rbp+1400h+var_1458], rdi
0x1400046b7  mov     [rbp+1400h+var_1450], r15
0x1400046bb  mov     [rsp+1500h+var_1498], r12
0x1400046c0  xorps   xmm0, xmm0
0x1400046c3  xor     eax, eax
0x1400046c5  movups  [rbp+1400h+var_1478], xmm0
0x1400046c9  mov     [rbp+1400h+var_1468], rax
0x1400046cd  xorps   xmm1, xmm1
0x1400046d0  movups  [rsp+1500h+var_1490], xmm1
0x1400046d5  mov     [rbp+1400h+var_1480], rax
0x1400046d9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400046e0  test    rax, rax
0x1400046e3  jz      short loc_1400046F0
0x1400046e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400046ea  mov     [rbp+1400h+var_1460], rax
0x1400046ee  jmp     short loc_1400046F4
0x1400046f0  mov     [rbp+1400h+var_1460], r12
0x1400046f4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400046fb  test    rax, rax
0x1400046fe  jz      short loc_14000470A
0x140004700  lea     rcx, [rsp+1500h+var_14E0]
0x140004705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000470a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004711  test    rax, rax
0x140004714  jz      short loc_14000472A
0x140004716  mov     r8d, 400h
0x14000471c  lea     rdx, [rbp+1400h+var_1440]
0x140004720  lea     rcx, [rsp+1500h+var_14E0]
0x140004725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000472a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004731  test    rax, rax
0x140004734  jz      short loc_140004740
0x140004736  lea     rcx, [rsp+1500h+var_14E0]
0x14000473b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004740  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004747  test    rax, rax
0x14000474a  jz      short loc_14000475D
0x14000474c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140004751  jnz     short loc_14000475D
0x140004753  lea     rcx, [rsp+1500h+var_14E0]
0x140004758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000475d  cmp     [rsp+1500h+var_14D8], r12d
0x140004762  jge     loc_14000486B
0x140004768  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x14000476f  jnz     short loc_140004790
0x140004771  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004778  test    rax, rax
0x14000477b  jz      short loc_140004786
0x14000477d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004782  test    al, al
0x140004784  jmp     short loc_14000478E
0x140004786  call    cs:__imp_IsDebuggerPresent
0x14000478c  test    eax, eax
0x14000478e  jz      short loc_140004797
0x140004790  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140004795  jz      short loc_1400047BD
0x140004797  mov     rax, cs:g_pfnResultLoggingCallback
0x14000479e  test    rax, rax
0x1400047a1  jz      short loc_140004816
0x1400047a3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400047aa  jnz     short loc_140004816
0x1400047ac  xor     r8d, r8d
0x1400047af  xor     edx, edx
0x1400047b1  lea     rcx, [rsp+1500h+var_14E0]
0x1400047b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400047bb  jmp     short loc_140004816
0x1400047bd  mov     ebx, 800h
0x1400047c2  mov     rax, cs:g_pfnResultLoggingCallback
0x1400047c9  test    rax, rax
0x1400047cc  jz      short loc_1400047EB
0x1400047ce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400047d5  jnz     short loc_1400047EB
0x1400047d7  mov     r8d, ebx
0x1400047da  lea     rdx, [rbp+1400h+OutputString]
0x1400047e1  lea     rcx, [rsp+1500h+var_14E0]
0x1400047e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400047eb  cmp     [rbp+1400h+OutputString], r12w
0x1400047f3  jnz     short loc_140004809
0x1400047f5  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1400047fa  mov     rdx, rbx; unsigned __int16 *
0x1400047fd  lea     rcx, [rbp+1400h+OutputString]; this
0x140004804  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004809  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140004810  call    cs:__imp_OutputDebugStringW
0x140004816  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x14000481b  jnz     short loc_140004826
0x14000481d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140004824  jz      short loc_140004838
0x140004826  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000482d  test    rax, rax
0x140004830  jz      short loc_140004838
0x140004832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004837  nop
0x140004838  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x14000483d  jnz     short loc_140004860
0x14000483f  mov     rcx, [rbp+1400h+var_40]
0x140004846  xor     rcx, rsp; StackCookie
0x140004849  call    __security_check_cookie
0x14000484e  add     rsp, 14D0h
0x140004855  pop     r15
0x140004857  pop     r14
0x140004859  pop     r12
0x14000485b  pop     rdi
0x14000485c  pop     rsi
0x14000485d  pop     rbx
0x14000485e  pop     rbp
0x14000485f  retn
0x140004860  lea     rcx, [rsp+1500h+var_14E0]; this
0x140004865  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000486b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
