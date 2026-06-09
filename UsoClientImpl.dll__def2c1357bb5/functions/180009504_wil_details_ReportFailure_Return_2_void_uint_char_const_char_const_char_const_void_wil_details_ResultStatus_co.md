# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180009504`
- end: `0x180009804`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `768`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180008dac`

## callees

- `0x180006224`
- `0x1800066c8`
- `0x180006930`
- `0x180007630`
- `0x180007894`
- `0x180008cbc`
- `0x180009504`
- `0x180056500`
- `0x18005c570`
- `0x18005c5e0`
- `0x18005c660`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000961d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000961d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800097a1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800097a1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009711`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009711`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<2>(
        unsigned __int64 a1,
        int a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        unsigned __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8,
        int a9,
        int a10)
{
  int v14; // edx
  int v15; // ebx
  int v16; // edx
  unsigned int v17; // ebx
  bool v18; // zf
  const struct wil::FailureInfo *v19; // rdx
  wil::details::in1diag3 *v20; // rcx
  const struct wil::FailureInfo *v21; // r9
  int IsDebuggerPresent; // ecx
  wil::details *v23; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v24[20]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v25[1024]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR OutputString[2048]; // [rsp+4F0h] [rbp+3F0h] BYREF

  memset(v24, 0, 0x98u);
  OutputString[0] = 0;
  v25[0] = 0;
  v15 = *a7;
  LODWORD(v24[1]) = v15;
  HIDWORD(v24[1]) = a7[1];
  if ( v15 >= 0 )
  {
    v15 = -2147024228;
    LODWORD(v23) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v23);
    LODWORD(v24[1]) = -2147024228;
    HIDWORD(v24[1]) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v16);
  }
  v17 = wil::details::RecordLog((wil::details *)(unsigned int)v15, v14);
  LODWORD(v24[0]) = 2;
  HIDWORD(v24[0]) = a10;
  if ( a7[2] == 1 )
    HIDWORD(v24[0]) = a10 | 8;
  LODWORD(v24[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v18 = *a8 == 0, v24[3] = (unsigned __int64)a8, v18) )
    v24[3] = 0;
  LODWORD(v24[4]) = GetCurrentThreadId();
  v24[7] = a3;
  v24[8] = __PAIR64__(v17, a2);
  v24[5] = a5;
  v24[6] = a4;
  v24[17] = a6;
  v24[18] = a1;
  memset(&v24[9], 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    v24[16] = wil::details::g_pfnGetModuleName();
  else
    v24[16] = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v24);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v24, v25, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v24);
  if ( wil::details::g_pfnOriginateCallback && (v24[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v24);
  if ( SLODWORD(v24[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v20);
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent()),
         IsDebuggerPresent))
    && (v24[0] & 0x200000000LL) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v24, OutputString, 2048, v21);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)v24, v21);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(v24, 0, 0, v21);
  }
  if ( ((v24[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak();
  if ( (v24[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v24, v19);
}

```

## disassembly

```asm
0x180009504  push    rbp
0x180009506  push    rbx
0x180009507  push    rsi
0x180009508  push    rdi
0x180009509  push    r12
0x18000950b  push    r13
0x18000950d  push    r14
0x18000950f  push    r15
0x180009511  lea     rbp, [rsp-1408h]
0x180009519  mov     eax, 1508h
0x18000951e  call    _alloca_probe
0x180009523  sub     rsp, rax
0x180009526  mov     rax, cs:__security_cookie
0x18000952d  xor     rax, rsp
0x180009530  mov     [rbp+1440h+var_50], rax
0x180009537  mov     r12, r9
0x18000953a  mov     r15, r8
0x18000953d  mov     r14d, edx
0x180009540  mov     rsi, rcx
0x180009543  mov     r13, [rbp+1440h+arg_20]
0x18000954a  mov     rax, [rbp+1440h+arg_28]
0x180009551  mov     [rsp+1540h+var_1500], rax
0x180009556  xor     edx, edx; Val
0x180009558  mov     r8d, 98h; Size
0x18000955e  lea     rcx, [rsp+1540h+var_14F0]; void *
0x180009563  call    memset
0x180009568  nop
0x180009569  xor     ecx, ecx
0x18000956b  mov     [rbp+1440h+OutputString], cx
0x180009572  mov     [rbp+1440h+var_1450], cl
0x180009575  mov     rdi, [rbp+1440h+arg_30]
0x18000957c  mov     ebx, [rdi]
0x18000957e  mov     [rsp+1540h+var_14E8], ebx
0x180009582  mov     eax, [rdi+4]
0x180009585  mov     [rsp+1540h+var_14E4], eax
0x180009589  test    ebx, ebx
0x18000958b  js      short loc_1800095C5
0x18000958d  mov     ebx, 8007029Ch
0x180009592  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x180009596  mov     rax, [rsp+1540h+var_1500]
0x18000959b  mov     [rsp+1540h+var_1518], rax; __int64
0x1800095a0  mov     [rsp+1540h+var_1520], r13; __int64
0x1800095a5  mov     r9, r12; int
0x1800095a8  mov     r8, r15; int
0x1800095ab  mov     edx, r14d; int
0x1800095ae  mov     rcx, rsi; int
0x1800095b1  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800095b6  mov     [rsp+1540h+var_14E8], ebx
0x1800095ba  mov     ecx, ebx; this
0x1800095bc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800095c1  mov     [rsp+1540h+var_14E4], eax
0x1800095c5  mov     ecx, ebx; this
0x1800095c7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800095cc  mov     ebx, eax
0x1800095ce  mov     dword ptr [rsp+1540h+var_14F0], 2
0x1800095d6  mov     ecx, [rbp+1440h+arg_48]
0x1800095dc  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x1800095e0  cmp     dword ptr [rdi+8], 1
0x1800095e4  jnz     short loc_1800095ED
0x1800095e6  or      ecx, 8
0x1800095e9  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x1800095ed  mov     ecx, 1
0x1800095f2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800095fa  inc     ecx
0x1800095fc  mov     [rsp+1540h+var_14E0], ecx
0x180009600  mov     rax, [rbp+1440h+arg_38]
0x180009607  xor     edi, edi
0x180009609  test    rax, rax
0x18000960c  jz      short loc_180009618
0x18000960e  cmp     [rax], di
0x180009611  mov     [rsp+1540h+var_14D8], rax
0x180009616  jnz     short loc_18000961D
0x180009618  mov     [rsp+1540h+var_14D8], rdi
0x18000961d  call    cs:__imp_GetCurrentThreadId
0x180009623  mov     [rsp+1540h+var_14D0], eax
0x180009627  mov     [rbp+1440h+var_14B8], r15
0x18000962b  mov     [rbp+1440h+var_14B0], r14d
0x18000962f  mov     [rbp+1440h+var_14AC], ebx
0x180009632  mov     [rsp+1540h+var_14C8], r13
0x180009637  mov     [rbp+1440h+var_14C0], r12
0x18000963b  mov     rax, [rsp+1540h+var_1500]
0x180009640  mov     [rbp+1440h+var_1468], rax
0x180009644  mov     [rbp+1440h+var_1460], rsi
0x180009648  mov     [rbp+1440h+var_14A8], rdi
0x18000964c  xorps   xmm0, xmm0
0x18000964f  xor     eax, eax
0x180009651  movups  [rbp+1440h+var_1488], xmm0
0x180009655  mov     [rbp+1440h+var_1478], rax
0x180009659  xorps   xmm1, xmm1
0x18000965c  movups  [rbp+1440h+var_14A0], xmm1
0x180009660  mov     [rbp+1440h+var_1490], rax
0x180009664  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000966b  test    rax, rax
0x18000966e  jz      short loc_18000967B
0x180009670  call    _guard_dispatch_icall
0x180009675  mov     [rbp+1440h+var_1470], rax
0x180009679  jmp     short loc_18000967F
0x18000967b  mov     [rbp+1440h+var_1470], rdi
0x18000967f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009686  test    rax, rax
0x180009689  jz      short loc_180009695
0x18000968b  lea     rcx, [rsp+1540h+var_14F0]
0x180009690  call    _guard_dispatch_icall
0x180009695  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000969c  test    rax, rax
0x18000969f  jz      short loc_1800096B5
0x1800096a1  mov     r8d, 400h
0x1800096a7  lea     rdx, [rbp+1440h+var_1450]
0x1800096ab  lea     rcx, [rsp+1540h+var_14F0]
0x1800096b0  call    _guard_dispatch_icall
0x1800096b5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800096bc  test    rax, rax
0x1800096bf  jz      short loc_1800096CB
0x1800096c1  lea     rcx, [rsp+1540h+var_14F0]
0x1800096c6  call    _guard_dispatch_icall
0x1800096cb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800096d2  test    rax, rax
0x1800096d5  jz      short loc_1800096E8
0x1800096d7  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x1800096dc  jnz     short loc_1800096E8
0x1800096de  lea     rcx, [rsp+1540h+var_14F0]
0x1800096e3  call    _guard_dispatch_icall
0x1800096e8  cmp     [rsp+1540h+var_14E8], edi
0x1800096ec  jge     loc_1800097FE
0x1800096f2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800096f9  jnz     short loc_180009722
0x1800096fb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009702  test    rax, rax
0x180009705  jz      short loc_180009711
0x180009707  call    _guard_dispatch_icall
0x18000970c  movzx   ecx, al
0x18000970f  jmp     short loc_18000971E
0x180009711  call    cs:__imp_IsDebuggerPresent
0x180009717  mov     ecx, edi
0x180009719  test    eax, eax
0x18000971b  setnz   cl
0x18000971e  test    ecx, ecx
0x180009720  jz      short loc_180009729
0x180009722  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180009727  jz      short loc_18000974F
0x180009729  mov     rax, cs:g_pfnResultLoggingCallback
0x180009730  test    rax, rax
0x180009733  jz      short loc_1800097A7
0x180009735  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000973c  jnz     short loc_1800097A7
0x18000973e  xor     r8d, r8d
0x180009741  xor     edx, edx
0x180009743  lea     rcx, [rsp+1540h+var_14F0]
0x180009748  call    _guard_dispatch_icall
0x18000974d  jmp     short loc_1800097A7
0x18000974f  mov     ebx, 800h
0x180009754  mov     rax, cs:g_pfnResultLoggingCallback
0x18000975b  test    rax, rax
0x18000975e  jz      short loc_18000977D
0x180009760  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180009767  jnz     short loc_18000977D
0x180009769  mov     r8d, ebx
0x18000976c  lea     rdx, [rbp+1440h+OutputString]
0x180009773  lea     rcx, [rsp+1540h+var_14F0]
0x180009778  call    _guard_dispatch_icall
0x18000977d  cmp     [rbp+1440h+OutputString], di
0x180009784  jnz     short loc_18000979A
0x180009786  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x18000978b  mov     rdx, rbx; wchar_t *
0x18000978e  lea     rcx, [rbp+1440h+OutputString]; this
0x180009795  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000979a  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x1800097a1  call    cs:__imp_OutputDebugStringW
0x1800097a7  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x1800097ac  jnz     short loc_1800097B7
0x1800097ae  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800097b5  jz      short loc_1800097C9
0x1800097b7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800097be  test    rax, rax
0x1800097c1  jz      short loc_1800097C9
0x1800097c3  call    _guard_dispatch_icall
0x1800097c8  nop
0x1800097c9  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x1800097ce  jnz     short loc_1800097F3
0x1800097d0  mov     rcx, [rbp+1440h+var_50]
0x1800097d7  xor     rcx, rsp; StackCookie
0x1800097da  call    __security_check_cookie
0x1800097df  add     rsp, 1508h
0x1800097e6  pop     r15
0x1800097e8  pop     r14
0x1800097ea  pop     r13
0x1800097ec  pop     r12
0x1800097ee  pop     rdi
0x1800097ef  pop     rsi
0x1800097f0  pop     rbx
0x1800097f1  pop     rbp
0x1800097f2  retn
0x1800097f3  lea     rcx, [rsp+1540h+var_14F0]; this
0x1800097f8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800097fe  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
