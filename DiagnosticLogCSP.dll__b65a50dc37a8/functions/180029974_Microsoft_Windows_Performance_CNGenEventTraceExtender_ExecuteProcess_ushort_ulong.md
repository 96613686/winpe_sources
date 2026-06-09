# Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(ushort *,ulong &)

- ea: `0x180029974`
- end: `0x180029a8d`
- name: `?ExecuteProcess@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEAGAEAK@Z`
- size: `281`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *this, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002954c`

## callees

- `0x18000265c`
- `0x180016274`
- `0x180029974`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800299f0`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800299f0`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180029a29`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180029a29`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180029a0f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180029a0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029a5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029a6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029a5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029a6d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180029974  mov     [rsp+arg_0], rbx
0x180029979  push    rdi
0x18002997a  sub     rsp, 0E0h
0x180029981  mov     rbx, rdx
0x180029984  mov     qword ptr [rsp+0E8h+StartupInfo.cb], 68h ; 'h'
0x18002998d  xor     edx, edx; Val
0x18002998f  lea     rcx, [rsp+0E8h+StartupInfo.lpReserved]; void *
0x180029994  mov     rdi, r8
0x180029997  lea     r8d, [rdx+60h]; Size
0x18002999b  call    memset_0
0x1800299a0  xor     eax, eax
0x1800299a2  xorps   xmm0, xmm0
0x1800299a5  mov     qword ptr [rsp+0E8h+ProcessInformation.dwProcessId], rax
0x1800299aa  xor     r9d, r9d; lpThreadAttributes
0x1800299ad  lea     rax, [rsp+0E8h+ProcessInformation]
0x1800299b2  xor     r8d, r8d; lpProcessAttributes
0x1800299b5  mov     [rsp+0E8h+lpProcessInformation], rax; lpProcessInformation
0x1800299ba  mov     rdx, rbx; lpCommandLine
0x1800299bd  lea     rax, [rsp+0E8h+StartupInfo]
0x1800299c2  xor     ecx, ecx; lpApplicationName
0x1800299c4  mov     [rsp+0E8h+lpStartupInfo], rax; lpStartupInfo
0x1800299c9  mov     [rsp+0E8h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1800299d2  mov     [rsp+0E8h+lpEnvironment], 0; lpEnvironment
0x1800299db  mov     [rsp+0E8h+dwCreationFlags], 8000000h; dwCreationFlags
0x1800299e3  mov     [rsp+0E8h+bInheritHandles], 0; bInheritHandles
0x1800299eb  movups  xmmword ptr [rsp+0E8h+ProcessInformation.hProcess], xmm0
0x1800299f0  call    cs:__imp_CreateProcessW
0x1800299f7  nop     dword ptr [rax+rax+00h]
0x1800299fc  test    eax, eax
0x1800299fe  jnz     short loc_180029A07
0x180029a00  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180029a05  jmp     short loc_180029A7B
0x180029a07  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hHandle
0x180029a0c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180029a0f  call    cs:__imp_WaitForSingleObject
0x180029a16  nop     dword ptr [rax+rax+00h]
0x180029a1b  test    eax, eax
0x180029a1d  jnz     short loc_180029A39
0x180029a1f  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hProcess
0x180029a24  mov     rdx, rdi; lpExitCode
0x180029a27  mov     [rdi], eax
0x180029a29  call    cs:__imp_GetExitCodeProcess
0x180029a30  nop     dword ptr [rax+rax+00h]
0x180029a35  test    eax, eax
0x180029a37  jnz     short loc_180029A4B
0x180029a39  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180029a3e  mov     ebx, eax
0x180029a40  test    eax, eax
0x180029a42  js      short loc_180029A57
0x180029a44  mov     ebx, 8000FFFFh
0x180029a49  jmp     short loc_180029A57
0x180029a4b  mov     eax, [rdi]
0x180029a4d  neg     eax
0x180029a4f  sbb     ebx, ebx
0x180029a51  and     ebx, 80004005h
0x180029a57  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x180029a5c  call    cs:__imp_CloseHandle
0x180029a63  nop     dword ptr [rax+rax+00h]
0x180029a68  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x180029a6d  call    cs:__imp_CloseHandle
0x180029a74  nop     dword ptr [rax+rax+00h]
0x180029a79  mov     eax, ebx
0x180029a7b  mov     rbx, [rsp+0E8h+arg_0]
0x180029a83  add     rsp, 0E0h
0x180029a8a  pop     rdi
0x180029a8b  retn
```
