# ETWLog::DoLogging(long,ulong,wchar_t const *,wchar_t const *,char * *)

- ea: `0x140014954`
- end: `0x140014aaa`
- name: `?DoLogging@ETWLog@@CAXJKPEB_W0PEAPEAD@Z`
- size: `342`
- prototype: `void __fastcall(int, unsigned int, const wchar_t *, const wchar_t *, char **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14001fbbc`

## callees

- `0x140005240`
- `0x140012738`
- `0x140014954`
- `0x140029a48`
- `0x140029a8c`
- `0x140029bd8`
- `0x140039e10`
- `0x140069b10`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x140014a68`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x140014a68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400149fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400149fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140014a3d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140014a3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400149a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400149a6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400149e4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400149e4`

## pseudocode

```c
void __fastcall ETWLog::DoLogging(__int64 a1, __int64 a2, wchar_t *a3, const wchar_t *a4, char **a5)
{
  DWORD CurrentThreadId; // eax
  __int64 v6; // rcx
  WCHAR OutputString[3504]; // [rsp+40h] [rbp-36D8h] BYREF
  wchar_t pszDest[3504]; // [rsp+1BA0h] [rbp-1B78h] BYREF

  if ( StringVPrintfWorkerW(pszDest, 0xDACu, (size_t *)a3, a4, *a5) >= 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    if ( StringCchPrintfW(OutputString, 0xDACu, L"%4d %s\n", CurrentThreadId, pszDest) >= 0 && g_fETWLoggingEnabled )
      OutputDebugStringW(OutputString);
    if ( dword_1400978F8 )
    {
      EnterCriticalSection(&CriticalSection);
      StringCchCopyW(
        (wchar_t *)(qword_140097900 + ((unsigned __int64)(unsigned int)dword_1400978FC << 11)),
        0x400u,
        OutputString);
      dword_1400978FC = (dword_1400978FC + 1) % (unsigned int)dword_1400978F8;
      LeaveCriticalSection(&CriticalSection);
    }
    if ( !g_fETWLoggingChecked )
    {
      try
      {
        ETWLog::CheckEnabled();
      }
      catch ( ... )
      {
        return;
      }
    }
    if ( (g_fETWLoggingEnabled || EventEnabled(Microsoft_Windows_Search_Core_Context, &MSSearchTraceId_ETWLogging))
      && (byte_140097A02 & 0x20) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(v6, &MSSearchTraceId_ETWLogging, pszDest);
    }
  }
}

```

## disassembly

```asm
0x140014954  mov     eax, 3718h
0x140014959  call    _alloca_probe
0x14001495e  sub     rsp, rax
0x140014961  mov     [rsp+3718h+var_36E8], 0FFFFFFFFFFFFFFFEh
0x14001496a  mov     rax, cs:__security_cookie
0x140014971  xor     rax, rsp
0x140014974  mov     [rsp+3718h+var_18], rax
0x14001497c  mov     rax, [rsp+3718h+arg_20]
0x140014984  mov     rax, [rax]
0x140014987  mov     [rsp+3718h+argList], rax; argList
0x14001498c  mov     edx, 0DACh; cchDest
0x140014991  lea     rcx, [rsp+3718h+pszDest]; pszDest
0x140014999  call    StringVPrintfWorkerW
0x14001499e  test    eax, eax
0x1400149a0  js      loc_140014A90
0x1400149a6  call    cs:__imp_GetCurrentThreadId
0x1400149ac  mov     r9d, eax
0x1400149af  lea     rax, [rsp+3718h+pszDest]
0x1400149b7  mov     [rsp+3718h+argList], rax
0x1400149bc  lea     r8, a4dS; "%4d %s\n"
0x1400149c3  mov     edx, 0DACh; unsigned __int64
0x1400149c8  lea     rcx, [rsp+3718h+OutputString]; unsigned __int16 *
0x1400149cd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400149d2  test    eax, eax
0x1400149d4  js      short loc_1400149EA
0x1400149d6  cmp     cs:?g_fETWLoggingEnabled@@3_NA, 0; bool g_fETWLoggingEnabled
0x1400149dd  jz      short loc_1400149EA
0x1400149df  lea     rcx, [rsp+3718h+OutputString]; lpOutputString
0x1400149e4  call    cs:__imp_OutputDebugStringW
0x1400149ea  cmp     cs:dword_1400978F8, 0
0x1400149f1  jbe     short loc_140014A43
0x1400149f3  lea     rcx, CriticalSection; lpCriticalSection
0x1400149fa  call    cs:__imp_EnterCriticalSection
0x140014a00  mov     ecx, cs:dword_1400978FC
0x140014a06  shl     rcx, 0Bh
0x140014a0a  add     rcx, cs:qword_140097900; wchar_t *
0x140014a11  lea     r8, [rsp+3718h+OutputString]; wchar_t *
0x140014a16  mov     edx, 400h; unsigned __int64
0x140014a1b  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x140014a20  mov     eax, cs:dword_1400978FC
0x140014a26  inc     eax
0x140014a28  xor     edx, edx
0x140014a2a  div     cs:dword_1400978F8
0x140014a30  mov     cs:dword_1400978FC, edx
0x140014a36  lea     rcx, CriticalSection; lpCriticalSection
0x140014a3d  call    cs:__imp_LeaveCriticalSection
0x140014a43  cmp     cs:?g_fETWLoggingChecked@@3_NA, 0; bool g_fETWLoggingChecked
0x140014a4a  jnz     short loc_140014A51
0x140014a4c  call    ?CheckEnabled@ETWLog@@CAXXZ; ETWLog::CheckEnabled(void)
0x140014a51  cmp     cs:?g_fETWLoggingEnabled@@3_NA, 0; bool g_fETWLoggingEnabled
0x140014a58  jnz     short loc_140014A72
0x140014a5a  lea     rdx, MSSearchTraceId_ETWLogging; EventDescriptor
0x140014a61  mov     rcx, cs:Microsoft_Windows_Search_Core_Context; RegHandle
0x140014a68  call    cs:__imp_EventEnabled
0x140014a6e  test    al, al
0x140014a70  jz      short loc_140014A90
0x140014a72  test    cs:byte_140097A02, 20h
0x140014a79  jz      short loc_140014A90
0x140014a7b  lea     r8, [rsp+3718h+pszDest]
0x140014a83  lea     rdx, MSSearchTraceId_ETWLogging
0x140014a8a  call    McTemplateU0z_EventWriteTransfer
0x140014a8f  nop
0x140014a90  jmp     short $+2
0x140014a92  mov     rcx, [rsp+3718h+var_18]
0x140014a9a  xor     rcx, rsp; StackCookie
0x140014a9d  call    __security_check_cookie
0x140014aa2  add     rsp, 3718h
0x140014aa9  retn
```
