# Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(ushort *,ulong &)

- ea: `0x180028804`
- end: `0x1800288fe`
- name: `?ExecuteProcess@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEAGAEAK@Z`
- size: `250`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *this, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180028340`

## callees

- `0x18000262c`
- `0x180015710`
- `0x180028804`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180028880`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180028880`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800288ad`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800288ad`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180028899`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180028899`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800288da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800288e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800288da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800288e5`

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
0x180028804  mov     [rsp+arg_0], rbx
0x180028809  push    rdi
0x18002880a  sub     rsp, 0E0h
0x180028811  mov     rbx, rdx
0x180028814  mov     qword ptr [rsp+0E8h+StartupInfo.cb], 68h ; 'h'
0x18002881d  xor     edx, edx; Val
0x18002881f  lea     rcx, [rsp+0E8h+StartupInfo.lpReserved]; void *
0x180028824  mov     rdi, r8
0x180028827  lea     r8d, [rdx+60h]; Size
0x18002882b  call    memset_0
0x180028830  xor     eax, eax
0x180028832  xorps   xmm0, xmm0
0x180028835  mov     qword ptr [rsp+0E8h+ProcessInformation.dwProcessId], rax
0x18002883a  xor     r9d, r9d; lpThreadAttributes
0x18002883d  lea     rax, [rsp+0E8h+ProcessInformation]
0x180028842  xor     r8d, r8d; lpProcessAttributes
0x180028845  mov     [rsp+0E8h+lpProcessInformation], rax; lpProcessInformation
0x18002884a  mov     rdx, rbx; lpCommandLine
0x18002884d  lea     rax, [rsp+0E8h+StartupInfo]
0x180028852  xor     ecx, ecx; lpApplicationName
0x180028854  mov     [rsp+0E8h+lpStartupInfo], rax; lpStartupInfo
0x180028859  mov     [rsp+0E8h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180028862  mov     [rsp+0E8h+lpEnvironment], 0; lpEnvironment
0x18002886b  mov     [rsp+0E8h+dwCreationFlags], 8000000h; dwCreationFlags
0x180028873  mov     [rsp+0E8h+bInheritHandles], 0; bInheritHandles
0x18002887b  movups  xmmword ptr [rsp+0E8h+ProcessInformation.hProcess], xmm0
0x180028880  call    cs:__imp_CreateProcessW
0x180028886  test    eax, eax
0x180028888  jnz     short loc_180028891
0x18002888a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002888f  jmp     short loc_1800288ED
0x180028891  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hHandle
0x180028896  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180028899  call    cs:__imp_WaitForSingleObject
0x18002889f  test    eax, eax
0x1800288a1  jnz     short loc_1800288B7
0x1800288a3  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hProcess
0x1800288a8  mov     rdx, rdi; lpExitCode
0x1800288ab  mov     [rdi], eax
0x1800288ad  call    cs:__imp_GetExitCodeProcess
0x1800288b3  test    eax, eax
0x1800288b5  jnz     short loc_1800288C9
0x1800288b7  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800288bc  mov     ebx, eax
0x1800288be  test    eax, eax
0x1800288c0  js      short loc_1800288D5
0x1800288c2  mov     ebx, 8000FFFFh
0x1800288c7  jmp     short loc_1800288D5
0x1800288c9  mov     eax, [rdi]
0x1800288cb  neg     eax
0x1800288cd  sbb     ebx, ebx
0x1800288cf  and     ebx, 80004005h
0x1800288d5  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x1800288da  call    cs:__imp_CloseHandle
0x1800288e0  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x1800288e5  call    cs:__imp_CloseHandle
0x1800288eb  mov     eax, ebx
0x1800288ed  mov     rbx, [rsp+0E8h+arg_0]
0x1800288f5  add     rsp, 0E0h
0x1800288fc  pop     rdi
0x1800288fd  retn
```
