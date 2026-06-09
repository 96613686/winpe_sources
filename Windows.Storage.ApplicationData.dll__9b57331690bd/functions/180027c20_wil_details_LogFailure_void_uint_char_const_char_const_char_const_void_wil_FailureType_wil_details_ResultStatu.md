# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180027c20`
- end: `0x180027f18`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(void *callerReturnAddress, unsigned int lineNumber, const char *fileName, const char *functionName, const char *code, void *returnAddress, wil::FailureType type, const wil::details::ResultStatus *resultPair, const wchar_t *message, bool debugString, wchar_t *callContextString, unsigned __int64 flags, char *failure, unsigned __int64 callerReturnAddress, wil::FailureFlags lineNumber, wil::FailureInfo *fileName)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800273c8`
- `0x180028aa8`

## callees

- `0x180002430`
- `0x18001b040`
- `0x18001c094`
- `0x1800270b4`
- `0x1800276cc`
- `0x180027c20`
- `0x1800281ac`
- `0x1800281d0`
- `0x1800284f8`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027d43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027d43`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180027ed4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180027ed4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180027e62`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180027e62`

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
0x180027c20  mov     [rsp+arg_10], rbx
0x180027c25  mov     [rsp+arg_8], lineNumber
0x180027c29  mov     [rsp+arg_0], callerReturnAddress
0x180027c2e  push    rbp
0x180027c2f  push    rsi
0x180027c30  push    rdi
0x180027c31  push    r12
0x180027c33  push    r13
0x180027c35  push    r14
0x180027c37  push    r15
0x180027c39  sub     rsp, 40h
0x180027c3d  mov     r14, [rsp+78h+arg_38]
0x180027c45  xor     eax, eax
0x180027c47  mov     rbx, [rsp+78h+fileName_0]
0x180027c4f  xor     ebp, ebp
0x180027c51  mov     r15d, [rsp+78h+arg_30]
0x180027c59  mov     r10, callerReturnAddress
0x180027c5c  mov     rsi, [rsp+78h+pszDest]
0x180027c64  mov     r12, functionName
0x180027c67  mov     r13, fileName
0x180027c6a  mov     ecx, r15d
0x180027c6d  mov     [rsi], ax
0x180027c70  mov     rax, [rsp+78h+arg_60]
0x180027c78  mov     byte ptr [rax], 0
0x180027c7b  mov     edi, [r14]
0x180027c7e  mov     [rbx+8], edi
0x180027c81  mov     eax, [r14+4]
0x180027c85  mov     [rbx+0Ch], eax
0x180027c88  test    r15d, r15d
0x180027c8b  jz      short loc_180027CF3
0x180027c8d  sub     ecx, 1
0x180027c90  jz      short loc_180027CEA
0x180027c92  sub     ecx, 1
0x180027c95  jz      short loc_180027CA5
0x180027c97  cmp     ecx, 1
0x180027c9a  jnz     short loc_180027CFC
0x180027c9c  mov     ecx, edi; hr
0x180027c9e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180027ca3  jmp     short loc_180027CFA
0x180027ca5  test    edi, edi
0x180027ca7  js      short loc_180027CE1
0x180027ca9  mov     rax, [rsp+78h+arg_28]
0x180027cb1  mov     edi, 8007029Ch
0x180027cb6  mov     [rsp+78h+hr], edi; hr
0x180027cba  mov     callerReturnAddress, r10; callerReturnAddress
0x180027cbd  mov     [rsp+78h+var_50], rax; returnAddress
0x180027cc2  mov     rax, [rsp+78h+arg_20]
0x180027cca  mov     [rsp+78h+var_58], rax; code
0x180027ccf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180027cd4  mov     ecx, edi; hr
0x180027cd6  mov     [rbx+8], edi
0x180027cd9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180027cde  mov     [rbx+0Ch], eax
0x180027ce1  mov     ecx, edi; hr
0x180027ce3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180027ce8  jmp     short loc_180027CFA
0x180027cea  mov     ecx, edi; hr
0x180027cec  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180027cf1  jmp     short loc_180027CFA
0x180027cf3  mov     ecx, edi; hr
0x180027cf5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180027cfa  mov     ebp, eax
0x180027cfc  mov     eax, [rsp+78h+lineNumber_0]
0x180027d03  mov     [rbx+4], eax
0x180027d06  mov     [rbx], r15d
0x180027d09  cmp     dword ptr [r14+8], 1
0x180027d0e  jnz     short loc_180027D16
0x180027d10  or      eax, 8
0x180027d13  mov     [rbx+4], eax
0x180027d16  mov     eax, 1
0x180027d1b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180027d23  inc     eax
0x180027d25  xor     edi, edi
0x180027d27  mov     [rbx+10h], eax
0x180027d2a  mov     rax, [rsp+78h+arg_40]
0x180027d32  test    rax, rax
0x180027d35  jz      short loc_180027D3C
0x180027d37  cmp     [rax], di
0x180027d3a  jnz     short loc_180027D3F
0x180027d3c  mov     rax, rdi
0x180027d3f  mov     [rbx+18h], rax
0x180027d43  call    cs:__imp_GetCurrentThreadId
0x180027d49  mov     [rbx+38h], r13
0x180027d4d  xorps   xmm0, xmm0
0x180027d50  mov     [rbx+20h], eax
0x180027d53  mov     eax, [rsp+78h+arg_8]
0x180027d5a  mov     [rbx+40h], eax
0x180027d5d  mov     rax, [rsp+78h+arg_20]
0x180027d65  mov     [rbx+28h], rax
0x180027d69  mov     rax, [rsp+78h+arg_28]
0x180027d71  mov     [rbx+88h], rax
0x180027d78  mov     rax, [rsp+78h+arg_0]
0x180027d80  mov     [rbx+90h], rax
0x180027d87  xor     eax, eax
0x180027d89  mov     [rbx+44h], ebp
0x180027d8c  mov     [rbx+30h], r12
0x180027d90  mov     [rbx+48h], rdi
0x180027d94  movups  xmmword ptr [rbx+68h], xmm0
0x180027d98  mov     [rbx+78h], rax
0x180027d9c  movups  xmmword ptr [rbx+50h], xmm0
0x180027da0  mov     [rbx+60h], rax
0x180027da4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180027dab  test    rax, rax
0x180027dae  jz      short loc_180027DB7
0x180027db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027db5  jmp     short loc_180027DBA
0x180027db7  mov     rax, rdi
0x180027dba  mov     [rbx+80h], rax
0x180027dc1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180027dc8  test    rax, rax
0x180027dcb  jz      short loc_180027DD5
0x180027dcd  mov     callerReturnAddress, rbx
0x180027dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027dd5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180027ddc  test    rax, rax
0x180027ddf  jz      short loc_180027DF7
0x180027de1  mov     rdx, [rsp+78h+arg_60]
0x180027de9  mov     r8d, 400h
0x180027def  mov     callerReturnAddress, rbx
0x180027df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027df7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180027dfe  test    rax, rax
0x180027e01  jz      short loc_180027E0B
0x180027e03  mov     callerReturnAddress, rbx
0x180027e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e0b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180027e12  test    rax, rax
0x180027e15  jz      short loc_180027E25
0x180027e17  test    byte ptr [rbx+4], 2
0x180027e1b  jnz     short loc_180027E25
0x180027e1d  mov     callerReturnAddress, rbx
0x180027e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e25  cmp     [rbx+8], edi
0x180027e28  jl      short loc_180027E44
0x180027e2a  cmp     r15d, 3
0x180027e2e  jnz     loc_180027F12
0x180027e34  mov     ecx, 8000FFFFh; hr
0x180027e39  mov     [rbx+8], ecx
0x180027e3c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180027e41  mov     [rbx+0Ch], eax
0x180027e44  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180027e4b  jnz     short loc_180027E6C
0x180027e4d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180027e54  test    rax, rax
0x180027e57  jz      short loc_180027E62
0x180027e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e5e  test    al, al
0x180027e60  jmp     short loc_180027E6A
0x180027e62  call    cs:__imp_IsDebuggerPresent
0x180027e68  test    eax, eax
0x180027e6a  jz      short loc_180027E72
0x180027e6c  test    byte ptr [rbx+4], 2
0x180027e70  jz      short loc_180027E96
0x180027e72  mov     rax, cs:g_pfnResultLoggingCallback
0x180027e79  test    rax, rax
0x180027e7c  jz      short loc_180027EDA
0x180027e7e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180027e85  jnz     short loc_180027EDA
0x180027e87  xor     r8d, r8d
0x180027e8a  xor     lineNumber, lineNumber
0x180027e8c  mov     callerReturnAddress, rbx
0x180027e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e94  jmp     short loc_180027EDA
0x180027e96  mov     rax, cs:g_pfnResultLoggingCallback
0x180027e9d  mov     ebp, 800h
0x180027ea2  test    rax, rax
0x180027ea5  jz      short loc_180027EBE
0x180027ea7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180027eae  jnz     short loc_180027EBE
0x180027eb0  mov     r8d, ebp
0x180027eb3  mov     rdx, rsi
0x180027eb6  mov     callerReturnAddress, rbx
0x180027eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ebe  cmp     [rsi], di
0x180027ec1  jnz     short loc_180027ED1
0x180027ec3  mov     fileName, rbx; failure
0x180027ec6  mov     rdx, rbp; cchDest
0x180027ec9  mov     callerReturnAddress, rsi; pszDest
0x180027ecc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180027ed1  mov     callerReturnAddress, rsi; lpOutputString
0x180027ed4  call    cs:__imp_OutputDebugStringW
0x180027eda  test    byte ptr [rbx+4], 4
0x180027ede  jnz     short loc_180027EE9
0x180027ee0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180027ee7  jz      short loc_180027EFA
0x180027ee9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180027ef0  test    rax, rax
0x180027ef3  jz      short loc_180027EFA
0x180027ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027efa  mov     rbx, [rsp+78h+arg_10]
0x180027f02  add     rsp, 40h
0x180027f06  pop     r15
0x180027f08  pop     r14
0x180027f0a  pop     r13
0x180027f0c  pop     r12
0x180027f0e  pop     rdi
0x180027f0f  pop     rsi
0x180027f10  pop     rbp
0x180027f11  retn
0x180027f12  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
