# CARPUninstallStringLauncher::LaunchUninstallStringAndWait(int,ushort const *,ulong,HWND__ *)

- ea: `0x18001bc50`
- end: `0x18001be90`
- name: `?LaunchUninstallStringAndWait@CARPUninstallStringLauncher@@UEAAJHPEBGKPEAUHWND__@@@Z`
- size: `576`
- prototype: `int(CARPUninstallStringLauncher *__hidden this, int, const unsigned __int16 *, unsigned int, HWND)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18001bb50`
- `0x18001bc50`
- `0x18001bebc`
- `0x1800582a2`

## import_xrefs

- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x18001bcff`
- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x18001bcff`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001be1f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001be1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bcbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bcbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be31`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18001bdbe`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18001bdbe`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001bd75`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001bd75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bdc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bdd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001be29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001be5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001be66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bdc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bdd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001be29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001be5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001be66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001be4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001be54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001be70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001be4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001be54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001be70`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x18001be0a`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x18001be0a`
- `KERNEL32!CreateJobObjectW` at `0x18001bca9`
- `KERNEL32!CreateJobObjectW` at `0x18001bca9`
- `KERNEL32!AssignProcessToJobObject` at `0x18001bd8a`
- `KERNEL32!AssignProcessToJobObject` at `0x18001bd8a`
- `pcacli!PcaMonitorProcess` at `0x18001bdb4`
- `pcacli!PcaMonitorProcess` at `0x18001bdb4`

## pseudocode

```c
__int64 __fastcall CARPUninstallStringLauncher::LaunchUninstallStringAndWait(
        CARPUninstallStringLauncher *this,
        int a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  int UninstallStringFromRegistry; // edi
  HANDLE JobObjectW; // rsi
  void *inited; // r14
  BOOL v7; // ebx
  signed int LastError; // eax
  PWSTR ppszApplication; // [rsp+50h] [rbp-71h] BYREF
  PWSTR ppszCommandLine; // [rsp+58h] [rbp-69h] BYREF
  PCWSTR pszCmdTemplate; // [rsp+60h] [rbp-61h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-59h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+80h] [rbp-41h] BYREF
  unsigned __int64 CompletionKey; // [rsp+88h] [rbp-39h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-31h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+128h] [rbp+67h] BYREF

  pszCmdTemplate = 0;
  UninstallStringFromRegistry = ReadUninstallStringFromRegistry(
                                  (HKEY)((a2 != 0) - 0x7FFFFFFFLL),
                                  a3,
                                  a4,
                                  (unsigned __int16 **)&pszCmdTemplate);
  if ( UninstallStringFromRegistry >= 0 )
  {
    UninstallStringFromRegistry = -2147467259;
    JobObjectW = CreateJobObjectW(0, 0);
    if ( JobObjectW )
    {
      if ( GetLastError() != 183 )
      {
        inited = InitJobObject(JobObjectW);
        if ( inited )
        {
          ppszApplication = 0;
          ppszCommandLine = 0;
          UninstallStringFromRegistry = SHEvaluateSystemCommandTemplate(
                                          pszCmdTemplate,
                                          &ppszApplication,
                                          &ppszCommandLine,
                                          0);
          if ( UninstallStringFromRegistry >= 0 )
          {
            *(_QWORD *)&StartupInfo.cb = 104;
            memset(&ProcessInformation, 0, sizeof(ProcessInformation));
            memset_0(&StartupInfo.lpReserved, 0, 0x60u);
            if ( CreateProcessW(
                   ppszApplication,
                   ppszCommandLine,
                   0,
                   0,
                   0,
                   0x804u,
                   0,
                   0,
                   &StartupInfo,
                   &ProcessInformation) )
            {
              v7 = AssignProcessToJobObject(JobObjectW, ProcessInformation.hProcess);
              PcaMonitorProcess(ProcessInformation.hProcess, 3, ppszApplication, ppszCommandLine, 0, 0);
              ResumeThread(ProcessInformation.hThread);
              CloseHandle(ProcessInformation.hThread);
              if ( v7 )
              {
                CloseHandle(ProcessInformation.hProcess);
                NumberOfBytesTransferred = 0;
                CompletionKey = 0;
                Overlapped = 0;
                while ( GetQueuedCompletionStatus(
                          inited,
                          &NumberOfBytesTransferred,
                          &CompletionKey,
                          &Overlapped,
                          0xFFFFFFFF)
                     && NumberOfBytesTransferred != 4 )
                  ;
              }
              else
              {
                WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
                CloseHandle(ProcessInformation.hProcess);
              }
            }
            else
            {
              LastError = GetLastError();
              UninstallStringFromRegistry = LastError;
              if ( LastError > 0 )
                UninstallStringFromRegistry = (unsigned __int16)LastError | 0x80070000;
            }
            CoTaskMemFree(ppszApplication);
            CoTaskMemFree(ppszCommandLine);
          }
          CloseHandle(inited);
        }
      }
      CloseHandle(JobObjectW);
    }
    CoTaskMemFree((LPVOID)pszCmdTemplate);
  }
  return (unsigned int)UninstallStringFromRegistry;
}

```

## disassembly

```asm
0x18001bc50  mov     [rsp-8+arg_0], rbx
0x18001bc55  mov     [rsp-8+arg_10], rsi
0x18001bc5a  push    rbp
0x18001bc5b  push    rdi
0x18001bc5c  push    r14
0x18001bc5e  lea     rbp, [rsp-3Fh]
0x18001bc63  sub     rsp, 100h
0x18001bc6a  neg     edx
0x18001bc6c  mov     [rbp+4Fh+pszCmdTemplate], 0
0x18001bc74  mov     eax, r9d
0x18001bc77  mov     r10, r8
0x18001bc7a  sbb     rcx, rcx
0x18001bc7d  lea     r9, [rbp+4Fh+pszCmdTemplate]; unsigned __int16 **
0x18001bc81  neg     rcx
0x18001bc84  mov     r8d, eax; unsigned int
0x18001bc87  add     rcx, 0FFFFFFFF80000001h; HKEY
0x18001bc8e  mov     rdx, r10; unsigned __int16 *
0x18001bc91  call    ?ReadUninstallStringFromRegistry@@YAJPEAUHKEY__@@PEBGKPEAPEAG@Z; ReadUninstallStringFromRegistry(HKEY__ *,ushort const *,ulong,ushort * *)
0x18001bc96  mov     edi, eax
0x18001bc98  test    eax, eax
0x18001bc9a  js      loc_18001BE76
0x18001bca0  xor     edx, edx; lpName
0x18001bca2  xor     ecx, ecx; lpJobAttributes
0x18001bca4  mov     edi, 80004005h
0x18001bca9  call    cs:__imp_CreateJobObjectW
0x18001bcaf  mov     rsi, rax
0x18001bcb2  test    rax, rax
0x18001bcb5  jz      loc_18001BE6C
0x18001bcbb  call    cs:__imp_GetLastError
0x18001bcc1  cmp     eax, 0B7h
0x18001bcc6  jz      loc_18001BE63
0x18001bccc  mov     rcx, rsi; hJob
0x18001bccf  call    ?InitJobObject@@YAPEAXPEAX@Z; InitJobObject(void *)
0x18001bcd4  mov     r14, rax
0x18001bcd7  test    rax, rax
0x18001bcda  jz      loc_18001BE63
0x18001bce0  mov     rcx, [rbp+4Fh+pszCmdTemplate]; pszCmdTemplate
0x18001bce4  lea     r8, [rbp+4Fh+ppszCommandLine]; ppszCommandLine
0x18001bce8  xor     r9d, r9d; ppszParameters
0x18001bceb  mov     [rbp+4Fh+ppszApplication], 0
0x18001bcf3  lea     rdx, [rbp+4Fh+ppszApplication]; ppszApplication
0x18001bcf7  mov     [rbp+4Fh+ppszCommandLine], 0
0x18001bcff  call    cs:__imp_SHEvaluateSystemCommandTemplate
0x18001bd05  mov     edi, eax
0x18001bd07  test    eax, eax
0x18001bd09  js      loc_18001BE5A
0x18001bd0f  xor     eax, eax
0x18001bd11  mov     qword ptr [rbp+4Fh+StartupInfo.cb], 68h ; 'h'
0x18001bd19  xorps   xmm0, xmm0
0x18001bd1c  mov     qword ptr [rbp+4Fh+ProcessInformation.dwProcessId], rax
0x18001bd20  xor     edx, edx; Val
0x18001bd22  lea     rcx, [rbp+4Fh+StartupInfo.lpReserved]; void *
0x18001bd26  movups  xmmword ptr [rbp+4Fh+ProcessInformation.hProcess], xmm0
0x18001bd2a  lea     r8d, [rax+60h]; Size
0x18001bd2e  call    memset_0
0x18001bd33  mov     rdx, [rbp+4Fh+ppszCommandLine]; lpCommandLine
0x18001bd37  lea     rax, [rbp+4Fh+ProcessInformation]
0x18001bd3b  mov     rcx, [rbp+4Fh+ppszApplication]; lpApplicationName
0x18001bd3f  xor     r9d, r9d; lpThreadAttributes
0x18001bd42  mov     [rsp+110h+lpProcessInformation], rax; lpProcessInformation
0x18001bd47  xor     r8d, r8d; lpProcessAttributes
0x18001bd4a  lea     rax, [rbp+4Fh+StartupInfo]
0x18001bd4e  mov     [rsp+110h+lpStartupInfo], rax; lpStartupInfo
0x18001bd53  mov     [rsp+110h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18001bd5c  mov     [rsp+110h+lpEnvironment], 0; lpEnvironment
0x18001bd65  mov     [rsp+110h+dwCreationFlags], 804h; dwCreationFlags
0x18001bd6d  mov     [rsp+110h+bInheritHandles], 0; bInheritHandles
0x18001bd75  call    cs:__imp_CreateProcessW
0x18001bd7b  test    eax, eax
0x18001bd7d  jz      loc_18001BE31
0x18001bd83  mov     rdx, [rbp+4Fh+ProcessInformation.hProcess]; hProcess
0x18001bd87  mov     rcx, rsi; hJob
0x18001bd8a  call    cs:__imp_AssignProcessToJobObject
0x18001bd90  mov     r9, [rbp+4Fh+ppszCommandLine]
0x18001bd94  mov     edx, 3
0x18001bd99  mov     r8, [rbp+4Fh+ppszApplication]
0x18001bd9d  mov     ebx, eax
0x18001bd9f  mov     rcx, [rbp+4Fh+ProcessInformation.hProcess]
0x18001bda3  mov     [rsp+110h+dwCreationFlags], 0
0x18001bdab  mov     qword ptr [rsp+110h+bInheritHandles], 0
0x18001bdb4  call    cs:__imp_?PcaMonitorProcess@@YAKPEAXW4PCA_PROCESS_TYPE@@PEBG22I@Z; PcaMonitorProcess(void *,PCA_PROCESS_TYPE,ushort const *,ushort const *,ushort const *,uint)
0x18001bdba  mov     rcx, [rbp+4Fh+ProcessInformation.hThread]; hThread
0x18001bdbe  call    cs:__imp_ResumeThread
0x18001bdc4  mov     rcx, [rbp+4Fh+ProcessInformation.hThread]; hObject
0x18001bdc8  call    cs:__imp_CloseHandle
0x18001bdce  mov     rcx, [rbp+4Fh+ProcessInformation.hProcess]; hHandle
0x18001bdd2  test    ebx, ebx
0x18001bdd4  jz      short loc_18001BE1C
0x18001bdd6  call    cs:__imp_CloseHandle
0x18001bddc  mov     [rbp+4Fh+NumberOfBytesTransferred], 0
0x18001bde3  mov     [rbp+4Fh+CompletionKey], 0
0x18001bdeb  mov     [rbp+4Fh+Overlapped], 0
0x18001bdf3  lea     r9, [rbp+4Fh+Overlapped]; lpOverlapped
0x18001bdf7  mov     [rsp+110h+bInheritHandles], 0FFFFFFFFh; dwMilliseconds
0x18001bdff  lea     r8, [rbp+4Fh+CompletionKey]; lpCompletionKey
0x18001be03  mov     rcx, r14; CompletionPort
0x18001be06  lea     rdx, [rbp+4Fh+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18001be0a  call    cs:__imp_GetQueuedCompletionStatus
0x18001be10  test    eax, eax
0x18001be12  jz      short loc_18001BE46
0x18001be14  cmp     [rbp+4Fh+NumberOfBytesTransferred], 4
0x18001be18  jnz     short loc_18001BDF3
0x18001be1a  jmp     short loc_18001BE46
0x18001be1c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001be1f  call    cs:__imp_WaitForSingleObject
0x18001be25  mov     rcx, [rbp+4Fh+ProcessInformation.hProcess]; hObject
0x18001be29  call    cs:__imp_CloseHandle
0x18001be2f  jmp     short loc_18001BE46
0x18001be31  call    cs:__imp_GetLastError
0x18001be37  mov     edi, eax
0x18001be39  test    eax, eax
0x18001be3b  jle     short loc_18001BE46
0x18001be3d  movzx   edi, ax
0x18001be40  or      edi, 80070000h
0x18001be46  mov     rcx, [rbp+4Fh+ppszApplication]; pv
0x18001be4a  call    cs:__imp_CoTaskMemFree
0x18001be50  mov     rcx, [rbp+4Fh+ppszCommandLine]; pv
0x18001be54  call    cs:__imp_CoTaskMemFree
0x18001be5a  mov     rcx, r14; hObject
0x18001be5d  call    cs:__imp_CloseHandle
0x18001be63  mov     rcx, rsi; hObject
0x18001be66  call    cs:__imp_CloseHandle
0x18001be6c  mov     rcx, [rbp+4Fh+pszCmdTemplate]; pv
0x18001be70  call    cs:__imp_CoTaskMemFree
0x18001be76  lea     r11, [rsp+110h+var_10]
0x18001be7e  mov     eax, edi
0x18001be80  mov     rbx, [r11+20h]
0x18001be84  mov     rsi, [r11+30h]
0x18001be88  mov     rsp, r11
0x18001be8b  pop     r14
0x18001be8d  pop     rdi
0x18001be8e  pop     rbp
0x18001be8f  retn
```
