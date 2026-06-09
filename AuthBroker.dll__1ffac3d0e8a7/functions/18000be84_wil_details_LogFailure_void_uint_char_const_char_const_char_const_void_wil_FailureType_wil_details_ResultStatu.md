# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000be84`
- end: `0x18000c178`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `756`
- prototype: `void __fastcall(void *callerReturnAddress, unsigned int lineNumber, const char *fileName, const char *functionName, const char *code, void *returnAddress, wil::FailureType type, const wil::details::ResultStatus *resultPair, const wchar_t *message, bool debugString, wchar_t *callContextString, unsigned __int64 flags, char *failure, unsigned __int64 callerReturnAddress, wil::FailureFlags lineNumber, wil::FailureInfo *fileName)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180009b2c`
- `0x180009bdc`
- `0x180009ccc`

## callees

- `0x180007730`
- `0x180009a80`
- `0x18000b104`
- `0x18000be84`
- `0x18000cb6c`
- `0x18000cb90`
- `0x18000cc4c`
- `0x18000cc68`
- `0x18000e194`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bfa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bfa7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c0c8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c0c8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c13a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c13a`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        void *callerReturnAddress,
        unsigned int lineNumber,
        const char *fileName,
        const char *functionName,
        char *code,
        void *returnAddress,
        wil::FailureType type,
        const wil::details::ResultStatus *resultPair,
        const wchar_t *message,
        bool debugString,
        wchar_t *callContextString,
        unsigned __int64 flags,
        char *failure,
        unsigned __int64 callerReturnAddress_0,
        int lineNumber_0,
        wil::FailureInfo *fileName_0)
{
  int v16; // ebp
  int hr; // edi
  int v20; // eax
  const wchar_t *v21; // rax
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v23; // rcx
  const char *ModuleName; // rax
  bool v25; // zf
  wil::FailureFlags v26; // [rsp+38h] [rbp-40h]

  v16 = 0;
  *callContextString = 0;
  *failure = 0;
  hr = resultPair->hr;
  fileName_0->hr = resultPair->hr;
  fileName_0->status = resultPair->status;
  if ( type )
  {
    switch ( type )
    {
      case Return:
        v20 = wil::details::RecordReturn(hr);
        break;
      case Log:
        if ( hr >= 0 )
        {
          hr = -2147024228;
          wil::details::ReportFailure_Hr<2>(
            callerReturnAddress,
            lineNumber,
            fileName,
            functionName,
            code,
            returnAddress,
            -2147024228,
            v26);
          fileName_0->hr = -2147024228;
          fileName_0->status = wil::details::HrToNtStatus(-2147024228);
        }
        v20 = wil::details::RecordLog(hr);
        break;
      case FailFast:
        v20 = wil::details::RecordFailFast(hr);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException(hr);
  }
  v16 = v20;
LABEL_12:
  *(_DWORD *)fileName_0->flags = lineNumber_0;
  fileName_0->type = type;
  if ( resultPair->kind == NtStatus )
    *(_DWORD *)fileName_0->flags = lineNumber_0 | 8;
  fileName_0->failureId = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = message;
  if ( !message || !*message )
    v21 = 0;
  fileName_0->pszMessage = v21;
  CurrentThreadId = GetCurrentThreadId();
  fileName_0->pszFile = fileName;
  fileName_0->threadId = CurrentThreadId;
  fileName_0->uLineNumber = lineNumber;
  fileName_0->pszCode = code;
  fileName_0->returnAddress = returnAddress;
  fileName_0->callerReturnAddress = callerReturnAddress;
  fileName_0->cFailureCount = v16;
  fileName_0->pszFunction = functionName;
  fileName_0->pszCallContext = 0;
  *(_OWORD *)&fileName_0->callContextCurrent.contextId = 0;
  fileName_0->callContextCurrent.contextMessage = 0;
  *(_OWORD *)&fileName_0->callContextOriginating.contextId = 0;
  fileName_0->callContextOriginating.contextMessage = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  fileName_0->pszModule = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(fileName_0);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(fileName_0, failure, 0x400u);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(fileName_0);
  if ( wil::details::g_pfnOriginateCallback && (fileName_0->flags[0] & 2) == 0 )
    wil::details::g_pfnOriginateCallback(fileName_0);
  if ( fileName_0->hr >= 0 )
  {
    if ( type != FailFast )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    fileName_0->hr = -2147418113;
    fileName_0->status = wil::details::HrToNtStatus(-2147418113);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent ? (v25 = !IsDebuggerPresent()) : (v25 = !wil::g_pfnIsDebuggerPresent()), v25)
    || (fileName_0->flags[0] & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(fileName_0, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(fileName_0, callContextString, 0x800u);
    if ( !*callContextString )
      wil::GetFailureLogString(callContextString, 0x800u, fileName_0);
    OutputDebugStringW(callContextString);
  }
  if ( (fileName_0->flags[0] & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x18000be84  mov     [rsp+arg_10], rbx
0x18000be89  mov     [rsp+arg_8], lineNumber
0x18000be8d  mov     [rsp+arg_0], callerReturnAddress
0x18000be92  push    rbp
0x18000be93  push    rsi
0x18000be94  push    rdi
0x18000be95  push    r12
0x18000be97  push    r13
0x18000be99  push    r14
0x18000be9b  push    r15
0x18000be9d  sub     rsp, 40h
0x18000bea1  mov     r14, [rsp+78h+arg_38]
0x18000bea9  xor     eax, eax
0x18000beab  mov     rbx, [rsp+78h+fileName_0]
0x18000beb3  xor     ebp, ebp
0x18000beb5  mov     r15d, [rsp+78h+arg_30]
0x18000bebd  mov     r10, callerReturnAddress
0x18000bec0  mov     rsi, [rsp+78h+pszDest]
0x18000bec8  mov     r12, functionName
0x18000becb  mov     r13, fileName
0x18000bece  mov     ecx, r15d
0x18000bed1  mov     [rsi], ax
0x18000bed4  mov     rax, [rsp+78h+arg_60]
0x18000bedc  mov     byte ptr [rax], 0
0x18000bedf  mov     edi, [r14]
0x18000bee2  mov     [rbx+8], edi
0x18000bee5  mov     eax, [r14+4]
0x18000bee9  mov     [rbx+0Ch], eax
0x18000beec  test    r15d, r15d
0x18000beef  jz      short loc_18000BF57
0x18000bef1  sub     ecx, 1
0x18000bef4  jz      short loc_18000BF4E
0x18000bef6  sub     ecx, 1
0x18000bef9  jz      short loc_18000BF09
0x18000befb  cmp     ecx, 1
0x18000befe  jnz     short loc_18000BF60
0x18000bf00  mov     ecx, edi; hr
0x18000bf02  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000bf07  jmp     short loc_18000BF5E
0x18000bf09  test    edi, edi
0x18000bf0b  js      short loc_18000BF45
0x18000bf0d  mov     rax, [rsp+78h+arg_28]
0x18000bf15  mov     edi, 8007029Ch
0x18000bf1a  mov     [rsp+78h+hr], edi; hr
0x18000bf1e  mov     callerReturnAddress, r10; callerReturnAddress
0x18000bf21  mov     [rsp+78h+var_50], rax; returnAddress
0x18000bf26  mov     rax, [rsp+78h+arg_20]
0x18000bf2e  mov     [rsp+78h+var_58], rax; code
0x18000bf33  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000bf38  mov     ecx, edi; hr
0x18000bf3a  mov     [rbx+8], edi
0x18000bf3d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000bf42  mov     [rbx+0Ch], eax
0x18000bf45  mov     ecx, edi; hr
0x18000bf47  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000bf4c  jmp     short loc_18000BF5E
0x18000bf4e  mov     ecx, edi; hr
0x18000bf50  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000bf55  jmp     short loc_18000BF5E
0x18000bf57  mov     ecx, edi; hr
0x18000bf59  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000bf5e  mov     ebp, eax
0x18000bf60  mov     eax, [rsp+78h+lineNumber_0]
0x18000bf67  mov     [rbx+4], eax
0x18000bf6a  mov     [rbx], r15d
0x18000bf6d  cmp     dword ptr [r14+8], 1
0x18000bf72  jnz     short loc_18000BF7A
0x18000bf74  or      eax, 8
0x18000bf77  mov     [rbx+4], eax
0x18000bf7a  mov     eax, 1
0x18000bf7f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000bf87  inc     eax
0x18000bf89  xor     edi, edi
0x18000bf8b  mov     [rbx+10h], eax
0x18000bf8e  mov     rax, [rsp+78h+arg_40]
0x18000bf96  test    rax, rax
0x18000bf99  jz      short loc_18000BFA0
0x18000bf9b  cmp     [rax], di
0x18000bf9e  jnz     short loc_18000BFA3
0x18000bfa0  mov     rax, rdi
0x18000bfa3  mov     [rbx+18h], rax
0x18000bfa7  call    cs:__imp_GetCurrentThreadId
0x18000bfad  mov     [rbx+38h], r13
0x18000bfb1  xorps   xmm0, xmm0
0x18000bfb4  mov     [rbx+20h], eax
0x18000bfb7  mov     eax, [rsp+78h+arg_8]
0x18000bfbe  mov     [rbx+40h], eax
0x18000bfc1  mov     rax, [rsp+78h+arg_20]
0x18000bfc9  mov     [rbx+28h], rax
0x18000bfcd  mov     rax, [rsp+78h+arg_28]
0x18000bfd5  mov     [rbx+88h], rax
0x18000bfdc  mov     rax, [rsp+78h+arg_0]
0x18000bfe4  mov     [rbx+90h], rax
0x18000bfeb  xor     eax, eax
0x18000bfed  mov     [rbx+44h], ebp
0x18000bff0  mov     [rbx+30h], r12
0x18000bff4  mov     [rbx+48h], rdi
0x18000bff8  movups  xmmword ptr [rbx+68h], xmm0
0x18000bffc  mov     [rbx+78h], rax
0x18000c000  movups  xmmword ptr [rbx+50h], xmm0
0x18000c004  mov     [rbx+60h], rax
0x18000c008  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000c00f  test    rax, rax
0x18000c012  jz      short loc_18000C01B
0x18000c014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c019  jmp     short loc_18000C01E
0x18000c01b  mov     rax, rdi
0x18000c01e  mov     [rbx+80h], rax
0x18000c025  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000c02c  test    rax, rax
0x18000c02f  jz      short loc_18000C039
0x18000c031  mov     callerReturnAddress, rbx
0x18000c034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c039  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000c040  test    rax, rax
0x18000c043  jz      short loc_18000C05B
0x18000c045  mov     rdx, [rsp+78h+arg_60]
0x18000c04d  mov     r8d, 400h
0x18000c053  mov     callerReturnAddress, rbx
0x18000c056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c05b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c062  test    rax, rax
0x18000c065  jz      short loc_18000C06F
0x18000c067  mov     callerReturnAddress, rbx
0x18000c06a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c06f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c076  test    rax, rax
0x18000c079  jz      short loc_18000C089
0x18000c07b  test    byte ptr [rbx+4], 2
0x18000c07f  jnz     short loc_18000C089
0x18000c081  mov     callerReturnAddress, rbx
0x18000c084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c089  cmp     [rbx+8], edi
0x18000c08c  jl      short loc_18000C0AA
0x18000c08e  cmp     r15d, 3
0x18000c092  jz      short loc_18000C09A
0x18000c094  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000c09a  mov     ecx, 8000FFFFh; hr
0x18000c09f  mov     [rbx+8], ecx
0x18000c0a2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000c0a7  mov     [rbx+0Ch], eax
0x18000c0aa  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000c0b1  jnz     short loc_18000C0D2
0x18000c0b3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000c0ba  test    rax, rax
0x18000c0bd  jz      short loc_18000C0C8
0x18000c0bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0c4  test    al, al
0x18000c0c6  jmp     short loc_18000C0D0
0x18000c0c8  call    cs:__imp_IsDebuggerPresent
0x18000c0ce  test    eax, eax
0x18000c0d0  jz      short loc_18000C0D8
0x18000c0d2  test    byte ptr [rbx+4], 2
0x18000c0d6  jz      short loc_18000C0FC
0x18000c0d8  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c0df  test    rax, rax
0x18000c0e2  jz      short loc_18000C140
0x18000c0e4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000c0eb  jnz     short loc_18000C140
0x18000c0ed  xor     r8d, r8d
0x18000c0f0  xor     lineNumber, lineNumber
0x18000c0f2  mov     callerReturnAddress, rbx
0x18000c0f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0fa  jmp     short loc_18000C140
0x18000c0fc  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c103  mov     ebp, 800h
0x18000c108  test    rax, rax
0x18000c10b  jz      short loc_18000C124
0x18000c10d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000c114  jnz     short loc_18000C124
0x18000c116  mov     r8d, ebp
0x18000c119  mov     rdx, rsi
0x18000c11c  mov     callerReturnAddress, rbx
0x18000c11f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c124  cmp     [rsi], di
0x18000c127  jnz     short loc_18000C137
0x18000c129  mov     fileName, rbx; failure
0x18000c12c  mov     rdx, rbp; cchDest
0x18000c12f  mov     callerReturnAddress, rsi; pszDest
0x18000c132  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000c137  mov     callerReturnAddress, rsi; lpOutputString
0x18000c13a  call    cs:__imp_OutputDebugStringW
0x18000c140  test    byte ptr [rbx+4], 4
0x18000c144  jnz     short loc_18000C14F
0x18000c146  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000c14d  jz      short loc_18000C160
0x18000c14f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000c156  test    rax, rax
0x18000c159  jz      short loc_18000C160
0x18000c15b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c160  mov     rbx, [rsp+78h+arg_10]
0x18000c168  add     rsp, 40h
0x18000c16c  pop     r15
0x18000c16e  pop     r14
0x18000c170  pop     r13
0x18000c172  pop     r12
0x18000c174  pop     rdi
0x18000c175  pop     rsi
0x18000c176  pop     rbp
0x18000c177  retn
```
