# Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(ushort *,ulong &)

- ea: `0x18007afc0`
- end: `0x18007b0ba`
- name: `?ExecuteProcess@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEAGAEAK@Z`
- size: `250`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *this, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007acb0`

## callees

- `0x18004b39c`
- `0x18004f964`
- `0x18007afc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007b055`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007b055`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18007b03c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18007b03c`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18007b069`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18007b069`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b096`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b0a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b096`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b0a1`

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
0x18007afc0  mov     [rsp+arg_0], rbx
0x18007afc5  push    rdi
0x18007afc6  sub     rsp, 0E0h
0x18007afcd  mov     rbx, rdx
0x18007afd0  mov     qword ptr [rsp+0E8h+StartupInfo.cb], 68h ; 'h'
0x18007afd9  xor     edx, edx; Val
0x18007afdb  lea     rcx, [rsp+0E8h+StartupInfo.lpReserved]; void *
0x18007afe0  mov     rdi, r8
0x18007afe3  lea     r8d, [rdx+60h]; Size
0x18007afe7  call    memset_0
0x18007afec  xor     eax, eax
0x18007afee  xorps   xmm0, xmm0
0x18007aff1  mov     qword ptr [rsp+0E8h+ProcessInformation.dwProcessId], rax
0x18007aff6  xor     r9d, r9d; lpThreadAttributes
0x18007aff9  lea     rax, [rsp+0E8h+ProcessInformation]
0x18007affe  xor     r8d, r8d; lpProcessAttributes
0x18007b001  mov     [rsp+0E8h+lpProcessInformation], rax; lpProcessInformation
0x18007b006  mov     rdx, rbx; lpCommandLine
0x18007b009  lea     rax, [rsp+0E8h+StartupInfo]
0x18007b00e  xor     ecx, ecx; lpApplicationName
0x18007b010  mov     [rsp+0E8h+lpStartupInfo], rax; lpStartupInfo
0x18007b015  mov     [rsp+0E8h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18007b01e  mov     [rsp+0E8h+lpEnvironment], 0; lpEnvironment
0x18007b027  mov     [rsp+0E8h+dwCreationFlags], 8000000h; dwCreationFlags
0x18007b02f  mov     [rsp+0E8h+bInheritHandles], 0; bInheritHandles
0x18007b037  movups  xmmword ptr [rsp+0E8h+ProcessInformation.hProcess], xmm0
0x18007b03c  call    cs:__imp_CreateProcessW
0x18007b042  test    eax, eax
0x18007b044  jnz     short loc_18007B04D
0x18007b046  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18007b04b  jmp     short loc_18007B0A9
0x18007b04d  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hHandle
0x18007b052  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18007b055  call    cs:__imp_WaitForSingleObject
0x18007b05b  test    eax, eax
0x18007b05d  jnz     short loc_18007B073
0x18007b05f  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hProcess
0x18007b064  mov     rdx, rdi; lpExitCode
0x18007b067  mov     [rdi], eax
0x18007b069  call    cs:__imp_GetExitCodeProcess
0x18007b06f  test    eax, eax
0x18007b071  jnz     short loc_18007B085
0x18007b073  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18007b078  mov     ebx, eax
0x18007b07a  test    eax, eax
0x18007b07c  js      short loc_18007B091
0x18007b07e  mov     ebx, 8000FFFFh
0x18007b083  jmp     short loc_18007B091
0x18007b085  mov     eax, [rdi]
0x18007b087  neg     eax
0x18007b089  sbb     ebx, ebx
0x18007b08b  and     ebx, 80004005h
0x18007b091  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x18007b096  call    cs:__imp_CloseHandle
0x18007b09c  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x18007b0a1  call    cs:__imp_CloseHandle
0x18007b0a7  mov     eax, ebx
0x18007b0a9  mov     rbx, [rsp+0E8h+arg_0]
0x18007b0b1  add     rsp, 0E0h
0x18007b0b8  pop     rdi
0x18007b0b9  retn
```
