# DtcExceptionFilter(_EXCEPTION_POINTERS *,int)

- ea: `0x180070620`
- end: `0x18007073a`
- name: `?DtcExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@H@Z`
- size: `282`
- prototype: `unsigned int __fastcall(struct _EXCEPTION_POINTERS *, int)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800039a0`
- `0x180055010`
- `0x1800552a0`
- `0x180055680`
- `0x180055a40`

## callees

- `0x18000d6f0`
- `0x18000d7ec`
- `0x180058a38`
- `0x180070620`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180070681`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180070681`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180070690`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180070690`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180070718`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180070718`
- `ADVAPI32!DeregisterEventSource` at `0x18007072b`
- `ADVAPI32!DeregisterEventSource` at `0x18007072b`
- `ADVAPI32!RegisterEventSourceW` at `0x1800706cf`
- `ADVAPI32!RegisterEventSourceW` at `0x1800706cf`
- `ADVAPI32!ReportEventW` at `0x18007070d`
- `ADVAPI32!ReportEventW` at `0x18007070d`

## string_xrefs

- `0x18007069b`: `The process '%s' hit an exception in a MSDTC related component.\nThe following exception (0x%08x) was generated at 0x%016p, Pid:%d.\nThe process is being terminated.\nAdditional information useful in a debugger:\nYou can do '.exr 0x%p' to display the exception record.\nYou can do '.cxr 0x%p' to display the context at the time of the exception.\n\n`

## pseudocode

```c
__int64 __fastcall DtcExceptionFilter(struct _EXCEPTION_POINTERS *a1)
{
  PEXCEPTION_RECORD ExceptionRecord; // r15
  PCONTEXT ContextRecord; // rbx
  DWORD CurrentProcessId; // eax
  PVOID ExceptionAddress; // rsi
  DWORD v7; // edi
  DWORD ExceptionCode; // ebp
  LPWSTR CommandLineW; // rax
  HANDLE v10; // rbx
  DWORD lpUserSid; // [rsp+20h] [rbp-688h]
  DWORD dwDataSize; // [rsp+30h] [rbp-678h]
  LPCWSTR Strings; // [rsp+50h] [rbp-658h] BYREF
  WCHAR OutputString[768]; // [rsp+60h] [rbp-648h] BYREF

  ExceptionRecord = a1->ExceptionRecord;
  Strings = OutputString;
  if ( ExceptionRecord->ExceptionCode != -2147483645 )
  {
    ContextRecord = a1->ContextRecord;
    CurrentProcessId = GetCurrentProcessId();
    ExceptionAddress = ExceptionRecord->ExceptionAddress;
    v7 = CurrentProcessId;
    ExceptionCode = ExceptionRecord->ExceptionCode;
    CommandLineW = GetCommandLineW();
    dwDataSize = v7;
    lpUserSid = ExceptionCode;
    StringCbPrintfW(
      OutputString,
      0x600u,
      L"The process '%s' hit an exception in a MSDTC related component.\n"
       "The following exception (0x%08x) was generated at 0x%016p, Pid:%d.\n"
       "The process is being terminated.\n"
       "Additional information useful in a debugger:\n"
       "You can do '.exr 0x%p' to display the exception record.\n"
       "You can do '.cxr 0x%p' to display the context at the time of the exception.\n"
       "\n",
      CommandLineW,
      lpUserSid,
      ExceptionAddress,
      dwDataSize,
      ExceptionRecord,
      ContextRecord);
    v10 = RegisterEventSourceW(0, L"MSDTC");
    if ( v10 )
      ReportEventW(v10, 1u, 1u, 0xC0001103, 0, 1u, 0, &Strings, 0);
    OutputDebugStringW(OutputString);
    DtcDebugBreak();
    if ( v10 )
      DeregisterEventSource(v10);
    DtcRaiseExceptionForWatsonCrashAnalysis(a1);
    JUMPOUT(0x180070739LL);
  }
  return 0;
}

```

## disassembly

```asm
0x180070620  push    rbx
0x180070622  push    rbp
0x180070623  push    rsi
0x180070624  push    rdi
0x180070625  push    r14
0x180070627  push    r15
0x180070629  sub     rsp, 678h
0x180070630  mov     rax, cs:__security_cookie
0x180070637  xor     rax, rsp
0x18007063a  mov     [rsp+6A8h+var_48], rax
0x180070642  mov     r15, [rcx]
0x180070645  lea     rax, [rsp+6A8h+OutputString]
0x18007064a  mov     [rsp+6A8h+Strings], rax
0x18007064f  mov     r14, rcx
0x180070652  cmp     dword ptr [r15], 80000003h
0x180070659  jnz     short loc_18007067D
0x18007065b  xor     eax, eax
0x18007065d  mov     rcx, [rsp+6A8h+var_48]
0x180070665  xor     rcx, rsp; StackCookie
0x180070668  call    __security_check_cookie
0x18007066d  add     rsp, 678h
0x180070674  pop     r15
0x180070676  pop     r14
0x180070678  pop     rdi
0x180070679  pop     rsi
0x18007067a  pop     rbp
0x18007067b  pop     rbx
0x18007067c  retn
0x18007067d  mov     rbx, [rcx+8]
0x180070681  call    cs:__imp_GetCurrentProcessId
0x180070687  mov     rsi, [r15+10h]
0x18007068b  mov     edi, eax
0x18007068d  mov     ebp, [r15]
0x180070690  call    cs:__imp_GetCommandLineW
0x180070696  mov     [rsp+6A8h+lpRawData], rbx
0x18007069b  lea     r8, aTheProcessSHit; "The process '%s' hit an exception in a "...
0x1800706a2  mov     [rsp+6A8h+lpStrings], r15
0x1800706a7  lea     rcx, [rsp+6A8h+OutputString]; unsigned __int16 *
0x1800706ac  mov     [rsp+6A8h+dwDataSize], edi
0x1800706b0  mov     r9, rax
0x1800706b3  mov     qword ptr [rsp+6A8h+wNumStrings], rsi
0x1800706b8  mov     edx, 600h; unsigned __int64
0x1800706bd  mov     dword ptr [rsp+6A8h+lpUserSid], ebp
0x1800706c1  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800706c6  lea     rdx, aMsdtc; "MSDTC"
0x1800706cd  xor     ecx, ecx; lpUNCServerName
0x1800706cf  call    cs:__imp_RegisterEventSourceW
0x1800706d5  xor     edi, edi
0x1800706d7  mov     rbx, rax
0x1800706da  test    rax, rax
0x1800706dd  jz      short loc_180070713
0x1800706df  mov     [rsp+6A8h+lpRawData], rdi; lpRawData
0x1800706e4  lea     ecx, [rdi+1]
0x1800706e7  lea     rax, [rsp+6A8h+Strings]
0x1800706ec  mov     r8d, ecx; wCategory
0x1800706ef  mov     [rsp+6A8h+lpStrings], rax; lpStrings
0x1800706f4  mov     edx, ecx; wType
0x1800706f6  mov     [rsp+6A8h+dwDataSize], edi; dwDataSize
0x1800706fa  mov     r9d, 0C0001103h; dwEventID
0x180070700  mov     [rsp+6A8h+wNumStrings], cx; wNumStrings
0x180070705  mov     rcx, rbx; hEventLog
0x180070708  mov     [rsp+6A8h+lpUserSid], rdi; lpUserSid
0x18007070d  call    cs:__imp_ReportEventW
0x180070713  lea     rcx, [rsp+6A8h+OutputString]; lpOutputString
0x180070718  call    cs:__imp_OutputDebugStringW
0x18007071e  call    ?DtcDebugBreak@@YAXXZ; DtcDebugBreak(void)
0x180070723  test    rbx, rbx
0x180070726  jz      short loc_180070731
0x180070728  mov     rcx, rbx; hEventLog
0x18007072b  call    cs:__imp_DeregisterEventSource
0x180070731  mov     rcx, r14; struct _EXCEPTION_POINTERS *
0x180070734  call    ?DtcRaiseExceptionForWatsonCrashAnalysis@@YAXPEAU_EXCEPTION_POINTERS@@@Z; DtcRaiseExceptionForWatsonCrashAnalysis(_EXCEPTION_POINTERS *)
```
