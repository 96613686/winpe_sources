# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180006560`
- end: `0x1800067f6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800067fc`

## callees

- `0x180005734`
- `0x180006560`
- `0x180006898`
- `0x180006bec`
- `0x180007200`
- `0x18000ed40`
- `0x1800153c0`
- `0x180015430`
- `0x1800154b0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006703`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006703`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006795`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006795`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000660e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000660e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        unsigned __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int64 a6,
        unsigned __int64 *a7)
{
  unsigned int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  unsigned __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v15; // r9
  unsigned __int64 v16[20]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v17[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset(v16, 0, 0x98u);
  OutputString[0] = 0;
  v17[0] = 0;
  v16[1] = *a7;
  v10 = wil::details::RecordReturn((wil::details *)LODWORD(v16[1]), (int)a7);
  LODWORD(v16[0]) = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  HIDWORD(v16[0]) = v11;
  LODWORD(v16[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v16[3] = 0;
  LODWORD(v16[4]) = GetCurrentThreadId();
  v16[7] = a3;
  v16[8] = __PAIR64__(v10, a2);
  v16[5] = 0;
  v16[6] = 0;
  v16[17] = a6;
  v16[18] = a1;
  memset(&v16[9], 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    v16[16] = wil::details::g_pfnGetModuleName(IsDebuggerPresent);
  else
    v16[16] = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v16, v17, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v16);
  if ( wil::details::g_pfnOriginateCallback && (v16[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v16);
  if ( SLODWORD(v16[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)IsDebuggerPresent);
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
         (_DWORD)IsDebuggerPresent))
    && (v16[0] & 0x200000000LL) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v16, OutputString, 2048, v15);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)v16, v15);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(v16, 0, 0, v15);
  }
  if ( ((v16[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  if ( (v16[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v16, v13);
}

```

## disassembly

```asm
0x180006560  push    rbp
0x180006562  push    rbx
0x180006563  push    rsi
0x180006564  push    rdi
0x180006565  push    r12
0x180006567  push    r14
0x180006569  push    r15
0x18000656b  lea     rbp, [rsp-13D0h]
0x180006573  mov     eax, 14D0h
0x180006578  call    _alloca_probe
0x18000657d  sub     rsp, rax
0x180006580  mov     rax, cs:__security_cookie
0x180006587  xor     rax, rsp
0x18000658a  mov     [rbp+1400h+var_40], rax
0x180006591  mov     r14, r8
0x180006594  mov     esi, edx
0x180006596  mov     r15, rcx
0x180006599  mov     rdi, [rbp+1400h+arg_28]
0x1800065a0  xor     edx, edx; Val
0x1800065a2  mov     r8d, 98h; Size
0x1800065a8  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800065ad  call    memset
0x1800065b2  nop
0x1800065b3  xor     r12d, r12d
0x1800065b6  mov     [rbp+1400h+OutputString], r12w
0x1800065be  mov     [rbp+1400h+var_1440], r12b
0x1800065c2  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1800065c9  mov     ecx, [rdx]; this
0x1800065cb  mov     [rsp+1500h+var_14D8], ecx
0x1800065cf  mov     eax, [rdx+4]
0x1800065d2  mov     [rsp+1500h+var_14D4], eax
0x1800065d6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800065db  mov     ebx, eax
0x1800065dd  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800065e5  mov     ecx, r12d
0x1800065e8  lea     eax, [r12+8]
0x1800065ed  cmp     dword ptr [rdx+8], 1
0x1800065f1  cmovz   ecx, eax
0x1800065f4  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800065f8  lea     ecx, [rax-7]
0x1800065fb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006603  inc     ecx
0x180006605  mov     [rsp+1500h+var_14D0], ecx
0x180006609  mov     [rsp+1500h+var_14C8], r12
0x18000660e  call    cs:__imp_GetCurrentThreadId
0x180006614  mov     [rsp+1500h+var_14C0], eax
0x180006618  mov     [rsp+1500h+var_14A8], r14
0x18000661d  mov     [rsp+1500h+var_14A0], esi
0x180006621  mov     [rsp+1500h+var_149C], ebx
0x180006625  mov     [rsp+1500h+var_14B8], r12
0x18000662a  mov     [rsp+1500h+var_14B0], r12
0x18000662f  mov     [rbp+1400h+var_1458], rdi
0x180006633  mov     [rbp+1400h+var_1450], r15
0x180006637  mov     [rsp+1500h+var_1498], r12
0x18000663c  xorps   xmm0, xmm0
0x18000663f  xor     eax, eax
0x180006641  movups  [rbp+1400h+var_1478], xmm0
0x180006645  mov     [rbp+1400h+var_1468], rax
0x180006649  xorps   xmm1, xmm1
0x18000664c  movups  [rsp+1500h+var_1490], xmm1
0x180006651  mov     [rbp+1400h+var_1480], rax
0x180006655  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000665c  test    rax, rax
0x18000665f  jz      short loc_18000666C
0x180006661  call    _guard_dispatch_icall
0x180006666  mov     [rbp+1400h+var_1460], rax
0x18000666a  jmp     short loc_180006670
0x18000666c  mov     [rbp+1400h+var_1460], r12
0x180006670  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006677  test    rax, rax
0x18000667a  jz      short loc_180006686
0x18000667c  lea     rcx, [rsp+1500h+var_14E0]
0x180006681  call    _guard_dispatch_icall
0x180006686  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000668d  test    rax, rax
0x180006690  jz      short loc_1800066A6
0x180006692  mov     r8d, 400h
0x180006698  lea     rdx, [rbp+1400h+var_1440]
0x18000669c  lea     rcx, [rsp+1500h+var_14E0]
0x1800066a1  call    _guard_dispatch_icall
0x1800066a6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800066ad  test    rax, rax
0x1800066b0  jz      short loc_1800066BC
0x1800066b2  lea     rcx, [rsp+1500h+var_14E0]
0x1800066b7  call    _guard_dispatch_icall
0x1800066bc  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800066c3  test    rax, rax
0x1800066c6  jz      short loc_1800066D9
0x1800066c8  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800066cd  jnz     short loc_1800066D9
0x1800066cf  lea     rcx, [rsp+1500h+var_14E0]
0x1800066d4  call    _guard_dispatch_icall
0x1800066d9  cmp     [rsp+1500h+var_14D8], r12d
0x1800066de  jge     loc_1800067F0
0x1800066e4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800066eb  jnz     short loc_180006715
0x1800066ed  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800066f4  test    rax, rax
0x1800066f7  jz      short loc_180006703
0x1800066f9  call    _guard_dispatch_icall
0x1800066fe  movzx   ecx, al
0x180006701  jmp     short loc_180006711
0x180006703  call    cs:__imp_IsDebuggerPresent
0x180006709  mov     ecx, r12d
0x18000670c  test    eax, eax
0x18000670e  setnz   cl
0x180006711  test    ecx, ecx
0x180006713  jz      short loc_18000671C
0x180006715  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000671a  jz      short loc_180006742
0x18000671c  mov     rax, cs:g_pfnResultLoggingCallback
0x180006723  test    rax, rax
0x180006726  jz      short loc_18000679B
0x180006728  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000672f  jnz     short loc_18000679B
0x180006731  xor     r8d, r8d
0x180006734  xor     edx, edx
0x180006736  lea     rcx, [rsp+1500h+var_14E0]
0x18000673b  call    _guard_dispatch_icall
0x180006740  jmp     short loc_18000679B
0x180006742  mov     ebx, 800h
0x180006747  mov     rax, cs:g_pfnResultLoggingCallback
0x18000674e  test    rax, rax
0x180006751  jz      short loc_180006770
0x180006753  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000675a  jnz     short loc_180006770
0x18000675c  mov     r8d, ebx
0x18000675f  lea     rdx, [rbp+1400h+OutputString]
0x180006766  lea     rcx, [rsp+1500h+var_14E0]
0x18000676b  call    _guard_dispatch_icall
0x180006770  cmp     [rbp+1400h+OutputString], r12w
0x180006778  jnz     short loc_18000678E
0x18000677a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000677f  mov     rdx, rbx; wchar_t *
0x180006782  lea     rcx, [rbp+1400h+OutputString]; this
0x180006789  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000678e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180006795  call    cs:__imp_OutputDebugStringW
0x18000679b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800067a0  jnz     short loc_1800067AB
0x1800067a2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800067a9  jz      short loc_1800067BD
0x1800067ab  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800067b2  test    rax, rax
0x1800067b5  jz      short loc_1800067BD
0x1800067b7  call    _guard_dispatch_icall
0x1800067bc  nop
0x1800067bd  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800067c2  jnz     short loc_1800067E5
0x1800067c4  mov     rcx, [rbp+1400h+var_40]
0x1800067cb  xor     rcx, rsp; StackCookie
0x1800067ce  call    __security_check_cookie
0x1800067d3  add     rsp, 14D0h
0x1800067da  pop     r15
0x1800067dc  pop     r14
0x1800067de  pop     r12
0x1800067e0  pop     rdi
0x1800067e1  pop     rsi
0x1800067e2  pop     rbx
0x1800067e3  pop     rbp
0x1800067e4  retn
0x1800067e5  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800067ea  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800067f0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
