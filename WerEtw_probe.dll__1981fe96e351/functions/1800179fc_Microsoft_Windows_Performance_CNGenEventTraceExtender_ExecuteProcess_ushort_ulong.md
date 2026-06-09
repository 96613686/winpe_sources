# Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(ushort *,ulong &)

- ea: `0x1800179fc`
- end: `0x180017af6`
- name: `?ExecuteProcess@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEAGAEAK@Z`
- size: `250`
- prototype: `int(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001753c`

## callees

- `0x180002420`
- `0x180004670`
- `0x1800179fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017a91`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017a91`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180017a78`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180017a78`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180017aa5`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180017aa5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017ad2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017add`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017ad2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017add`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        unsigned __int16 *a2,
        unsigned int *a3)
{
  HANDLE hProcess; // rcx
  signed int Error; // ebx
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-98h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-78h] BYREF

  *(_QWORD *)&StartupInfo.cb = 104;
  memset_0(&StartupInfo.lpReserved, 0, 0x60u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( !CreateProcessW(0, a2, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
    return ATL::AtlHresultFromLastError();
  if ( !WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF)
    && (hProcess = ProcessInformation.hProcess, *a3 = 0, GetExitCodeProcess(hProcess, a3)) )
  {
    Error = *a3 != 0 ? 0x80004005 : 0;
  }
  else
  {
    Error = ATL::AtlHresultFromLastError();
    if ( Error >= 0 )
      Error = -2147418113;
  }
  CloseHandle(ProcessInformation.hProcess);
  CloseHandle(ProcessInformation.hThread);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800179fc  mov     [rsp+arg_0], rbx
0x180017a01  push    rdi
0x180017a02  sub     rsp, 0E0h
0x180017a09  mov     rbx, rdx
0x180017a0c  mov     qword ptr [rsp+0E8h+StartupInfo.cb], 68h ; 'h'
0x180017a15  xor     edx, edx; Val
0x180017a17  lea     rcx, [rsp+0E8h+StartupInfo.lpReserved]; void *
0x180017a1c  mov     rdi, r8
0x180017a1f  lea     r8d, [rdx+60h]; Size
0x180017a23  call    memset_0
0x180017a28  xor     eax, eax
0x180017a2a  xorps   xmm0, xmm0
0x180017a2d  mov     qword ptr [rsp+0E8h+ProcessInformation.dwProcessId], rax
0x180017a32  xor     r9d, r9d; lpThreadAttributes
0x180017a35  lea     rax, [rsp+0E8h+ProcessInformation]
0x180017a3a  xor     r8d, r8d; lpProcessAttributes
0x180017a3d  mov     [rsp+0E8h+lpProcessInformation], rax; lpProcessInformation
0x180017a42  mov     rdx, rbx; lpCommandLine
0x180017a45  lea     rax, [rsp+0E8h+StartupInfo]
0x180017a4a  xor     ecx, ecx; lpApplicationName
0x180017a4c  mov     [rsp+0E8h+lpStartupInfo], rax; lpStartupInfo
0x180017a51  mov     [rsp+0E8h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180017a5a  mov     [rsp+0E8h+lpEnvironment], 0; lpEnvironment
0x180017a63  mov     [rsp+0E8h+dwCreationFlags], 8000000h; dwCreationFlags
0x180017a6b  mov     [rsp+0E8h+bInheritHandles], 0; bInheritHandles
0x180017a73  movups  xmmword ptr [rsp+0E8h+ProcessInformation.hProcess], xmm0
0x180017a78  call    cs:__imp_CreateProcessW
0x180017a7e  test    eax, eax
0x180017a80  jnz     short loc_180017A89
0x180017a82  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180017a87  jmp     short loc_180017AE5
0x180017a89  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hHandle
0x180017a8e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180017a91  call    cs:__imp_WaitForSingleObject
0x180017a97  test    eax, eax
0x180017a99  jnz     short loc_180017AAF
0x180017a9b  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hProcess
0x180017aa0  mov     rdx, rdi; lpExitCode
0x180017aa3  mov     [rdi], eax
0x180017aa5  call    cs:__imp_GetExitCodeProcess
0x180017aab  test    eax, eax
0x180017aad  jnz     short loc_180017AC1
0x180017aaf  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180017ab4  mov     ebx, eax
0x180017ab6  test    eax, eax
0x180017ab8  js      short loc_180017ACD
0x180017aba  mov     ebx, 8000FFFFh
0x180017abf  jmp     short loc_180017ACD
0x180017ac1  mov     eax, [rdi]
0x180017ac3  neg     eax
0x180017ac5  sbb     ebx, ebx
0x180017ac7  and     ebx, 80004005h
0x180017acd  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x180017ad2  call    cs:__imp_CloseHandle
0x180017ad8  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x180017add  call    cs:__imp_CloseHandle
0x180017ae3  mov     eax, ebx
0x180017ae5  mov     rbx, [rsp+0E8h+arg_0]
0x180017aed  add     rsp, 0E0h
0x180017af4  pop     rdi
0x180017af5  retn
```
