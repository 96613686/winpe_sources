# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18002711c`
- end: `0x1800273c0`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `676`
- prototype: `void __fastcall(void *callerReturnAddress, unsigned int lineNumber, const char *fileName, const char *returnAddress, const char *resultPair, void *message, const wil::details::ResultStatus *callerReturnAddress_0, const wchar_t *lineNumber_0)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800201b0`

## callees

- `0x18001b040`
- `0x18002711c`
- `0x1800276cc`
- `0x18002841c`
- `0x1800284f8`
- `0x1800415ee`
- `0x180041620`
- `0x1800416b0`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800271e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800271e1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180027360`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180027360`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800272d6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800272d6`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        void *callerReturnAddress,
        unsigned int lineNumber,
        const char *fileName,
        const char *returnAddress,
        const char *resultPair,
        void *message,
        const wil::details::ResultStatus *callerReturnAddress_0,
        const wchar_t *lineNumber_0)
{
  int status; // eax
  int v12; // eax
  __int64 v13; // rdx
  int v14; // r15d
  int v15; // ecx
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v17; // rcx
  bool v18; // zf
  wil::FailureInfo failure; // [rsp+20h] [rbp-E0h] BYREF
  char callContextString[1024]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t debugString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&failure, 0, sizeof(failure));
  debugString[0] = 0;
  callContextString[0] = 0;
  status = callerReturnAddress_0->status;
  failure.hr = callerReturnAddress_0->hr;
  failure.status = status;
  v12 = wil::details::RecordReturn(failure.hr);
  v18 = *(_DWORD *)(v13 + 8) == 1;
  v14 = v12;
  failure.type = Return;
  v15 = 0;
  if ( v18 )
    v15 = 8;
  *(_DWORD *)failure.flags = v15;
  failure.failureId = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !lineNumber_0 || (failure.pszMessage = lineNumber_0, !*lineNumber_0) )
    failure.pszMessage = 0;
  CurrentThreadId = GetCurrentThreadId();
  failure.pszFile = fileName;
  failure.threadId = CurrentThreadId;
  failure.uLineNumber = lineNumber;
  failure.cFailureCount = v14;
  failure.pszCode = 0;
  failure.pszFunction = 0;
  failure.returnAddress = message;
  failure.callerReturnAddress = callerReturnAddress;
  memset(&failure.pszCallContext, 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    failure.pszModule = wil::details::g_pfnGetModuleName();
  else
    failure.pszModule = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&failure);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&failure, callContextString, 0x400u);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&failure);
  if ( wil::details::g_pfnOriginateCallback && (failure.flags[0] & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&failure);
  if ( failure.hr >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent ? (v18 = !IsDebuggerPresent()) : (v18 = !wil::g_pfnIsDebuggerPresent()), v18)
    || (failure.flags[0] & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&failure, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&failure, debugString, 0x800u);
    if ( !debugString[0] )
      wil::GetFailureLogString(debugString, 0x800u, &failure);
    OutputDebugStringW(debugString);
  }
  if ( ((failure.flags[0] & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak();
  if ( (failure.flags[0] & 1) != 0 )
    wil::details::WilFailFast(&failure);
}

```

## disassembly

```asm
0x18002711c  push    rbp
0x18002711e  push    rbx
0x18002711f  push    rsi
0x180027120  push    rdi
0x180027121  push    r12
0x180027123  push    r14
0x180027125  push    r15
0x180027127  lea     rbp, [rsp-13D0h]
0x18002712f  mov     eax, 14D0h
0x180027134  call    _alloca_probe
0x180027139  sub     rsp, rax
0x18002713c  mov     rax, cs:__security_cookie
0x180027143  xor     rax, rsp
0x180027146  mov     [rbp+1400h+var_40], rax
0x18002714d  mov     r14, [rbp+1400h+arg_28]
0x180027154  mov     rsi, fileName
0x180027157  mov     edi, lineNumber
0x180027159  mov     rbx, callerReturnAddress
0x18002715c  xor     lineNumber, lineNumber; Val
0x18002715e  lea     callerReturnAddress, [rsp+1500h+failure]; void *
0x180027163  mov     r8d, 98h; Size
0x180027169  call    memset_0
0x18002716e  mov     rdx, [rbp+1400h+callerReturnAddress_0]
0x180027175  xor     r12d, r12d
0x180027178  mov     [rbp+1400h+debugString], r12w
0x180027180  mov     [rbp+1400h+callContextString], r12b
0x180027184  mov     ecx, [rdx]; hr
0x180027186  mov     eax, [rdx+4]
0x180027189  mov     [rsp+1500h+failure.hr], ecx
0x18002718d  mov     [rsp+1500h+failure.status], eax
0x180027191  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180027196  cmp     dword ptr [rdx+8], 1
0x18002719a  mov     r15d, eax
0x18002719d  lea     eax, [r12+8]
0x1800271a2  mov     [rsp+1500h+failure.type], 1
0x1800271aa  mov     ecx, r12d
0x1800271ad  cmovz   ecx, eax
0x1800271b0  mov     dword ptr [rsp+1500h+failure.flags], ecx
0x1800271b4  lea     ecx, [rax-7]
0x1800271b7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800271bf  inc     ecx
0x1800271c1  mov     [rsp+1500h+failure.failureId], ecx
0x1800271c5  mov     callerReturnAddress, [rbp+1400h+lineNumber_0]
0x1800271cc  test    callerReturnAddress, callerReturnAddress
0x1800271cf  jz      short loc_1800271DC
0x1800271d1  mov     [rsp+1500h+failure.pszMessage], callerReturnAddress
0x1800271d6  cmp     [callerReturnAddress], r12w
0x1800271da  jnz     short loc_1800271E1
0x1800271dc  mov     [rsp+1500h+failure.pszMessage], r12
0x1800271e1  call    cs:__imp_GetCurrentThreadId
0x1800271e7  xorps   xmm0, xmm0
0x1800271ea  mov     [rsp+1500h+failure.pszFile], rsi
0x1800271ef  mov     [rsp+1500h+failure.threadId], eax
0x1800271f3  xorps   xmm1, xmm1
0x1800271f6  xor     eax, eax
0x1800271f8  mov     [rsp+1500h+failure.uLineNumber], edi
0x1800271fc  mov     [rbp+1400h+failure.callContextCurrent.contextMessage], rax
0x180027200  mov     [rbp+1400h+failure.callContextOriginating.contextMessage], rax
0x180027204  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002720b  mov     [rsp+1500h+failure.cFailureCount], r15d
0x180027210  mov     [rsp+1500h+failure.pszCode], r12
0x180027215  mov     [rsp+1500h+failure.pszFunction], r12
0x18002721a  mov     [rbp+1400h+failure.returnAddress], r14
0x18002721e  mov     [rbp+1400h+failure.callerReturnAddress], rbx
0x180027222  mov     [rsp+1500h+failure.pszCallContext], r12
0x180027227  movups  xmmword ptr [rbp+1400h+failure.callContextCurrent.contextId], xmm0
0x18002722b  movups  xmmword ptr [rsp+1500h+failure.callContextOriginating.contextId], xmm1
0x180027230  test    rax, rax
0x180027233  jz      short loc_180027240
0x180027235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002723a  mov     [rbp+1400h+failure.pszModule], rax
0x18002723e  jmp     short loc_180027244
0x180027240  mov     [rbp+1400h+failure.pszModule], r12
0x180027244  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002724b  test    rax, rax
0x18002724e  jz      short loc_18002725A
0x180027250  lea     callerReturnAddress, [rsp+1500h+failure]
0x180027255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002725a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180027261  test    rax, rax
0x180027264  jz      short loc_18002727A
0x180027266  mov     r8d, 400h
0x18002726c  lea     rdx, [rbp+1400h+callContextString]
0x180027270  lea     callerReturnAddress, [rsp+1500h+failure]
0x180027275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002727a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180027281  test    rax, rax
0x180027284  jz      short loc_180027290
0x180027286  lea     callerReturnAddress, [rsp+1500h+failure]
0x18002728b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027290  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180027297  test    rax, rax
0x18002729a  jz      short loc_1800272AD
0x18002729c  test    [rsp+1500h+failure.flags], 2
0x1800272a1  jnz     short loc_1800272AD
0x1800272a3  lea     callerReturnAddress, [rsp+1500h+failure]
0x1800272a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272ad  cmp     [rsp+1500h+failure.hr], r12d
0x1800272b2  jge     loc_1800273AF
0x1800272b8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800272bf  jnz     short loc_1800272E0
0x1800272c1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800272c8  test    rax, rax
0x1800272cb  jz      short loc_1800272D6
0x1800272cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272d2  test    al, al
0x1800272d4  jmp     short loc_1800272DE
0x1800272d6  call    cs:__imp_IsDebuggerPresent
0x1800272dc  test    eax, eax
0x1800272de  jz      short loc_1800272E7
0x1800272e0  test    [rsp+1500h+failure.flags], 2
0x1800272e5  jz      short loc_18002730D
0x1800272e7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800272ee  test    rax, rax
0x1800272f1  jz      short loc_180027366
0x1800272f3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800272fa  jnz     short loc_180027366
0x1800272fc  xor     r8d, r8d
0x1800272ff  lea     callerReturnAddress, [rsp+1500h+failure]
0x180027304  xor     lineNumber, lineNumber
0x180027306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002730b  jmp     short loc_180027366
0x18002730d  mov     rax, cs:g_pfnResultLoggingCallback
0x180027314  mov     ebx, 800h
0x180027319  test    rax, rax
0x18002731c  jz      short loc_18002733B
0x18002731e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180027325  jnz     short loc_18002733B
0x180027327  mov     r8d, ebx
0x18002732a  lea     rdx, [rbp+1400h+debugString]
0x180027331  lea     callerReturnAddress, [rsp+1500h+failure]
0x180027336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002733b  cmp     [rbp+1400h+debugString], r12w
0x180027343  jnz     short loc_180027359
0x180027345  lea     fileName, [rsp+1500h+failure]; failure
0x18002734a  mov     rdx, rbx; cchDest
0x18002734d  lea     callerReturnAddress, [rbp+1400h+debugString]; pszDest
0x180027354  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180027359  lea     callerReturnAddress, [rbp+1400h+debugString]; lpOutputString
0x180027360  call    cs:__imp_OutputDebugStringW
0x180027366  test    [rsp+1500h+failure.flags], 4
0x18002736b  jnz     short loc_180027376
0x18002736d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180027374  jz      short loc_180027387
0x180027376  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002737d  test    rax, rax
0x180027380  jz      short loc_180027387
0x180027382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027387  test    [rsp+1500h+failure.flags], 1
0x18002738c  jnz     short loc_1800273B5
0x18002738e  mov     callerReturnAddress, [rbp+1400h+var_40]
0x180027395  xor     callerReturnAddress, rsp; StackCookie
0x180027398  call    __security_check_cookie
0x18002739d  add     rsp, 14D0h
0x1800273a4  pop     r15
0x1800273a6  pop     r14
0x1800273a8  pop     r12
0x1800273aa  pop     rdi
0x1800273ab  pop     rsi
0x1800273ac  pop     rbx
0x1800273ad  pop     rbp
0x1800273ae  retn
0x1800273af  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800273b5  lea     callerReturnAddress, [rsp+1500h+failure]; failure
0x1800273ba  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
