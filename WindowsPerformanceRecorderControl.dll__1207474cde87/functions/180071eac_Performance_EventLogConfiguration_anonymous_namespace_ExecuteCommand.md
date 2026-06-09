# Performance::EventLogConfiguration::_anonymous_namespace_::ExecuteCommand

- ea: `0x180071eac`
- end: `0x18007201f`
- name: `Performance::EventLogConfiguration::_anonymous_namespace_::ExecuteCommand`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180071cfc`

## callees

- `0x180008330`
- `0x1800234f0`
- `0x180037634`
- `0x18004aaa4`
- `0x18004b39c`
- `0x18004f964`
- `0x180071eac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180071fa7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180071fa7`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180071f55`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180071f55`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180071fb9`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180071fb9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Performance::EventLogConfiguration::_anonymous_namespace_::ExecuteCommand(char *a1, DWORD *a2)
{
  WCHAR *Buffer; // rax
  unsigned int v5; // ebx
  __int64 result; // rax
  unsigned int Error; // ebx
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v9; // [rsp+68h] [rbp-90h]
  ATL::CAtlException *v10; // [rsp+70h] [rbp-88h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-78h] BYREF
  HANDLE hThread; // [rsp+110h] [rbp+18h] BYREF
  HANDLE hProcess; // [rsp+118h] [rbp+20h] BYREF

  v9 = -2;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  try
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64 *)&hThread,
      a1);
    Buffer = (WCHAR *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&hThread);
    if ( CreateProcessW(0, Buffer, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&hThread);
      hProcess = ProcessInformation.hProcess;
      hThread = ProcessInformation.hThread;
      if ( WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF) != -1
        && GetExitCodeProcess(ProcessInformation.hProcess, a2) )
      {
        ATL::CHandle::~CHandle((ATL::CHandle *)&hThread);
        ATL::CHandle::~CHandle((ATL::CHandle *)&hProcess);
        result = 0;
      }
      else
      {
        Error = ATL::AtlHresultFromLastError();
        ATL::CHandle::~CHandle((ATL::CHandle *)&hThread);
        ATL::CHandle::~CHandle((ATL::CHandle *)&hProcess);
        result = Error;
      }
    }
    else
    {
      v5 = ATL::AtlHresultFromLastError();
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&hThread);
      result = v5;
    }
  }
  catch ( ATL::CAtlException *v10 )
  {
    LODWORD(hThread) = *(_DWORD *)v10;
    return (unsigned int)hThread;
  }
  return result;
}

```

## disassembly

```asm
0x180071eac  mov     r11, rsp
0x180071eaf  push    rdi
0x180071eb0  sub     rsp, 0F0h
0x180071eb7  mov     [rsp+0F8h+var_90], 0FFFFFFFFFFFFFFFEh
0x180071ec0  mov     [r11+8], rbx
0x180071ec4  mov     rdi, rdx
0x180071ec7  mov     rbx, rcx
0x180071eca  xorps   xmm0, xmm0
0x180071ecd  xor     eax, eax
0x180071ecf  movups  xmmword ptr [rsp+0F8h+ProcessInformation.hProcess], xmm0
0x180071ed4  mov     qword ptr [rsp+0F8h+ProcessInformation.dwProcessId], rax
0x180071ed9  xor     edx, edx; Val
0x180071edb  lea     r8d, [rax+64h]; Size
0x180071edf  lea     rcx, [r11-74h]; void *
0x180071ee3  call    memset_0
0x180071ee8  mov     [rsp+0F8h+StartupInfo.cb], 68h ; 'h'
0x180071ef3  mov     rdx, rbx
0x180071ef6  lea     rcx, [rsp+0F8h+arg_10]
0x180071efe  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180071f03  nop
0x180071f04  lea     rcx, [rsp+0F8h+arg_10]
0x180071f0c  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x180071f11  lea     rcx, [rsp+0F8h+ProcessInformation]
0x180071f16  mov     [rsp+0F8h+lpProcessInformation], rcx; lpProcessInformation
0x180071f1b  lea     rcx, [rsp+0F8h+StartupInfo]
0x180071f23  mov     [rsp+0F8h+lpStartupInfo], rcx; lpStartupInfo
0x180071f28  mov     [rsp+0F8h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180071f31  mov     [rsp+0F8h+lpEnvironment], 0; lpEnvironment
0x180071f3a  mov     [rsp+0F8h+dwCreationFlags], 8000000h; dwCreationFlags
0x180071f42  mov     [rsp+0F8h+bInheritHandles], 0; bInheritHandles
0x180071f4a  xor     r9d, r9d; lpThreadAttributes
0x180071f4d  xor     r8d, r8d; lpProcessAttributes
0x180071f50  mov     rdx, rax; lpCommandLine
0x180071f53  xor     ecx, ecx; lpApplicationName
0x180071f55  call    cs:__imp_CreateProcessW
0x180071f5b  test    eax, eax
0x180071f5d  jnz     short loc_180071F7A
0x180071f5f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180071f64  mov     ebx, eax
0x180071f66  lea     rcx, [rsp+0F8h+arg_10]; this
0x180071f6e  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180071f73  mov     eax, ebx
0x180071f75  jmp     loc_18007200D
0x180071f7a  lea     rcx, [rsp+0F8h+arg_10]; this
0x180071f82  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180071f87  nop
0x180071f88  mov     rcx, [rsp+0F8h+ProcessInformation.hProcess]; hHandle
0x180071f8d  mov     [rsp+0F8h+arg_18], rcx
0x180071f95  mov     rax, [rsp+0F8h+ProcessInformation.hThread]
0x180071f9a  mov     [rsp+0F8h+arg_10], rax
0x180071fa2  or      ebx, 0FFFFFFFFh
0x180071fa5  mov     edx, ebx; dwMilliseconds
0x180071fa7  call    cs:__imp_WaitForSingleObject
0x180071fad  cmp     eax, ebx
0x180071faf  jz      short loc_180071FC3
0x180071fb1  mov     rdx, rdi; lpExitCode
0x180071fb4  mov     rcx, [rsp+0F8h+ProcessInformation.hProcess]; hProcess
0x180071fb9  call    cs:__imp_GetExitCodeProcess
0x180071fbf  test    eax, eax
0x180071fc1  jnz     short loc_180071FE8
0x180071fc3  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180071fc8  mov     ebx, eax
0x180071fca  lea     rcx, [rsp+0F8h+arg_10]; this
0x180071fd2  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x180071fd7  lea     rcx, [rsp+0F8h+arg_18]; this
0x180071fdf  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x180071fe4  mov     eax, ebx
0x180071fe6  jmp     short loc_18007200D
0x180071fe8  lea     rcx, [rsp+0F8h+arg_10]; this
0x180071ff0  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x180071ff5  lea     rcx, [rsp+0F8h+arg_18]; this
0x180071ffd  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x180072002  xor     eax, eax
0x180072004  jmp     short loc_18007200D
0x180072006  mov     eax, dword ptr [rsp+0F8h+arg_10]
0x18007200d  mov     rbx, [rsp+0F8h+arg_0]
0x180072015  add     rsp, 0F0h
0x18007201c  pop     rdi
0x18007201d  retn
```
