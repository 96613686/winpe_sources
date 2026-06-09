# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180041580`
- end: `0x18004181e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `670`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001d730`

## callees

- `0x18002d2b0`
- `0x18002dee0`
- `0x180041580`
- `0x180042784`
- `0x1800430e4`
- `0x180043764`
- `0x180043840`
- `0x180097e20`
- `0x18009e020`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x1800417b7`
- `KERNEL32!OutputDebugStringW` at `0x1800417b7`
- `KERNEL32!GetCurrentThreadId` at `0x18004162d`
- `KERNEL32!GetCurrentThreadId` at `0x18004162d`
- `KERNEL32!IsDebuggerPresent` at `0x180041727`
- `KERNEL32!IsDebuggerPresent` at `0x180041727`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        unsigned __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int64 a6,
        _DWORD *a7)
{
  int v10; // eax
  unsigned int v11; // eax
  __int64 v12; // rdx
  unsigned int v13; // ebx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  unsigned __int64 v20[20]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v21[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset(v20, 0, 0x98u);
  OutputString[0] = 0;
  v21[0] = 0;
  v10 = a7[1];
  LODWORD(v20[1]) = *a7;
  HIDWORD(v20[1]) = v10;
  v11 = wil::details::RecordReturn((wil::details *)LODWORD(v20[1]), (int)a7);
  v19 = *(_DWORD *)(v12 + 8) == 1;
  v13 = v11;
  LODWORD(v20[0]) = 1;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  HIDWORD(v20[0]) = v14;
  v20[3] = 0;
  LODWORD(v20[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v20[7] = a3;
  LODWORD(v20[4]) = CurrentThreadId;
  v20[8] = __PAIR64__(v13, a2);
  v20[5] = 0;
  v20[6] = 0;
  v20[17] = a6;
  v20[18] = a1;
  memset(&v20[9], 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    v20[16] = wil::details::g_pfnGetModuleName(v17);
  else
    v20[16] = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v20, v21, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v20);
  if ( wil::details::g_pfnOriginateCallback && (v20[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v20);
  if ( SLODWORD(v20[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v20[0] & 0x200000000LL) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v20[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v20, v16);
}

```

## disassembly

```asm
0x180041580  push    rbp
0x180041582  push    rbx
0x180041583  push    rsi
0x180041584  push    rdi
0x180041585  push    r12
0x180041587  push    r14
0x180041589  push    r15
0x18004158b  lea     rbp, [rsp-13D0h]
0x180041593  mov     eax, 14D0h
0x180041598  call    _alloca_probe
0x18004159d  sub     rsp, rax
0x1800415a0  mov     rax, cs:__security_cookie
0x1800415a7  xor     rax, rsp
0x1800415aa  mov     [rbp+1400h+var_40], rax
0x1800415b1  mov     rdi, [rbp+1400h+arg_28]
0x1800415b8  mov     r14, r8
0x1800415bb  mov     esi, edx
0x1800415bd  mov     r15, rcx
0x1800415c0  xor     edx, edx; Val
0x1800415c2  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800415c7  mov     r8d, 98h; Size
0x1800415cd  call    memset
0x1800415d2  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1800415d9  xor     r12d, r12d
0x1800415dc  mov     [rbp+1400h+OutputString], r12w
0x1800415e4  mov     [rbp+1400h+var_1440], r12b
0x1800415e8  mov     ecx, [rdx]; this
0x1800415ea  mov     eax, [rdx+4]
0x1800415ed  mov     [rsp+1500h+var_14D8], ecx
0x1800415f1  mov     [rsp+1500h+var_14D4], eax
0x1800415f5  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800415fa  cmp     dword ptr [rdx+8], 1
0x1800415fe  mov     ebx, eax
0x180041600  lea     eax, [r12+8]
0x180041605  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18004160d  mov     ecx, r12d
0x180041610  cmovz   ecx, eax
0x180041613  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180041617  lea     ecx, [rax-7]
0x18004161a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180041622  inc     ecx
0x180041624  mov     [rsp+1500h+var_14C8], r12
0x180041629  mov     [rsp+1500h+var_14D0], ecx
0x18004162d  call    cs:__imp_GetCurrentThreadId
0x180041634  nop     dword ptr [rax+rax+00h]
0x180041639  xorps   xmm0, xmm0
0x18004163c  mov     [rsp+1500h+var_14A8], r14
0x180041641  mov     [rsp+1500h+var_14C0], eax
0x180041645  xorps   xmm1, xmm1
0x180041648  xor     eax, eax
0x18004164a  mov     [rsp+1500h+var_14A0], esi
0x18004164e  mov     [rbp+1400h+var_1468], rax
0x180041652  mov     [rbp+1400h+var_1480], rax
0x180041656  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18004165d  mov     [rsp+1500h+var_149C], ebx
0x180041661  mov     [rsp+1500h+var_14B8], r12
0x180041666  mov     [rsp+1500h+var_14B0], r12
0x18004166b  mov     [rbp+1400h+var_1458], rdi
0x18004166f  mov     [rbp+1400h+var_1450], r15
0x180041673  mov     [rsp+1500h+var_1498], r12
0x180041678  movups  [rbp+1400h+var_1478], xmm0
0x18004167c  movups  [rsp+1500h+var_1490], xmm1
0x180041681  test    rax, rax
0x180041684  jz      short loc_180041691
0x180041686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004168b  mov     [rbp+1400h+var_1460], rax
0x18004168f  jmp     short loc_180041695
0x180041691  mov     [rbp+1400h+var_1460], r12
0x180041695  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18004169c  test    rax, rax
0x18004169f  jz      short loc_1800416AB
0x1800416a1  lea     rcx, [rsp+1500h+var_14E0]
0x1800416a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416ab  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800416b2  test    rax, rax
0x1800416b5  jz      short loc_1800416CB
0x1800416b7  mov     r8d, 400h
0x1800416bd  lea     rdx, [rbp+1400h+var_1440]
0x1800416c1  lea     rcx, [rsp+1500h+var_14E0]
0x1800416c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416cb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800416d2  test    rax, rax
0x1800416d5  jz      short loc_1800416E1
0x1800416d7  lea     rcx, [rsp+1500h+var_14E0]
0x1800416dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416e1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800416e8  test    rax, rax
0x1800416eb  jz      short loc_1800416FE
0x1800416ed  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800416f2  jnz     short loc_1800416FE
0x1800416f4  lea     rcx, [rsp+1500h+var_14E0]
0x1800416f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416fe  cmp     [rsp+1500h+var_14D8], r12d
0x180041703  jge     loc_18004180D
0x180041709  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180041710  jnz     short loc_180041737
0x180041712  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180041719  test    rax, rax
0x18004171c  jz      short loc_180041727
0x18004171e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041723  test    al, al
0x180041725  jmp     short loc_180041735
0x180041727  call    cs:__imp_IsDebuggerPresent
0x18004172e  nop     dword ptr [rax+rax+00h]
0x180041733  test    eax, eax
0x180041735  jz      short loc_18004173E
0x180041737  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18004173c  jz      short loc_180041764
0x18004173e  mov     rax, cs:g_pfnResultLoggingCallback
0x180041745  test    rax, rax
0x180041748  jz      short loc_1800417C3
0x18004174a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180041751  jnz     short loc_1800417C3
0x180041753  xor     r8d, r8d
0x180041756  lea     rcx, [rsp+1500h+var_14E0]
0x18004175b  xor     edx, edx
0x18004175d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041762  jmp     short loc_1800417C3
0x180041764  mov     rax, cs:g_pfnResultLoggingCallback
0x18004176b  mov     ebx, 800h
0x180041770  test    rax, rax
0x180041773  jz      short loc_180041792
0x180041775  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18004177c  jnz     short loc_180041792
0x18004177e  mov     r8d, ebx
0x180041781  lea     rdx, [rbp+1400h+OutputString]
0x180041788  lea     rcx, [rsp+1500h+var_14E0]
0x18004178d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041792  cmp     [rbp+1400h+OutputString], r12w
0x18004179a  jnz     short loc_1800417B0
0x18004179c  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800417a1  mov     rdx, rbx; wchar_t *
0x1800417a4  lea     rcx, [rbp+1400h+OutputString]; this
0x1800417ab  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800417b0  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800417b7  call    cs:__imp_OutputDebugStringW
0x1800417be  nop     dword ptr [rax+rax+00h]
0x1800417c3  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800417c8  jnz     short loc_1800417D3
0x1800417ca  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800417d1  jz      short loc_1800417E4
0x1800417d3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800417da  test    rax, rax
0x1800417dd  jz      short loc_1800417E4
0x1800417df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800417e4  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800417e9  jnz     short loc_180041813
0x1800417eb  mov     rcx, [rbp+1400h+var_40]
0x1800417f2  xor     rcx, rsp; StackCookie
0x1800417f5  call    __security_check_cookie
0x1800417fa  add     rsp, 14D0h
0x180041801  pop     r15
0x180041803  pop     r14
0x180041805  pop     r12
0x180041807  pop     rdi
0x180041808  pop     rsi
0x180041809  pop     rbx
0x18004180a  pop     rbp
0x18004180b  retn
0x18004180d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180041813  lea     rcx, [rsp+1500h+var_14E0]; this
0x180041818  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
