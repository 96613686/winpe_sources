# Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(ushort *,ulong &)

- ea: `0x180015694`
- end: `0x180015786`
- name: `?ExecuteProcess@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEAGAEAK@Z`
- size: `242`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *this, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800150e8`

## callees

- `0x1800067f0`
- `0x180015694`
- `0x180026f6c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180015762`
- `KERNEL32!CloseHandle` at `0x18001576d`
- `KERNEL32!CloseHandle` at `0x180015762`
- `KERNEL32!CloseHandle` at `0x18001576d`
- `KERNEL32!CreateProcessW` at `0x180015708`
- `KERNEL32!CreateProcessW` at `0x180015708`
- `KERNEL32!WaitForSingleObject` at `0x180015721`
- `KERNEL32!WaitForSingleObject` at `0x180015721`
- `KERNEL32!GetExitCodeProcess` at `0x180015735`
- `KERNEL32!GetExitCodeProcess` at `0x180015735`

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

  StartupInfo.cb = 104;
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
0x180015694  mov     [rsp+arg_0], rbx
0x180015699  push    rdi
0x18001569a  sub     rsp, 0E0h
0x1800156a1  mov     rbx, rdx
0x1800156a4  mov     [rsp+0E8h+StartupInfo.cb], 68h ; 'h'
0x1800156ac  xor     edx, edx; Val
0x1800156ae  lea     rcx, [rsp+0E8h+StartupInfo.lpReserved]; void *
0x1800156b3  mov     rdi, r8
0x1800156b6  lea     r8d, [rdx+60h]; Size
0x1800156ba  call    memset_0
0x1800156bf  xor     eax, eax
0x1800156c1  xor     r9d, r9d; lpThreadAttributes
0x1800156c4  mov     [rsp+0E8h+ProcessInformation.hProcess], rax
0x1800156c9  xor     r8d, r8d; lpProcessAttributes
0x1800156cc  mov     [rsp+0E8h+ProcessInformation.hThread], rax
0x1800156d1  mov     rdx, rbx; lpCommandLine
0x1800156d4  mov     qword ptr [rsp+0E8h+ProcessInformation.dwProcessId], rax
0x1800156d9  xor     ecx, ecx; lpApplicationName
0x1800156db  lea     rax, [rsp+0E8h+ProcessInformation]
0x1800156e0  mov     [rsp+0E8h+lpProcessInformation], rax; lpProcessInformation
0x1800156e5  lea     rax, [rsp+0E8h+StartupInfo]
0x1800156ea  mov     [rsp+0E8h+lpStartupInfo], rax; lpStartupInfo
0x1800156ef  and     [rsp+0E8h+var_B0], 0
0x1800156f5  and     [rsp+0E8h+var_B8], 0
0x1800156fb  mov     [rsp+0E8h+dwCreationFlags], 8000000h; dwCreationFlags
0x180015703  and     [rsp+0E8h+var_C8], 0
0x180015708  call    cs:__imp_CreateProcessW
0x18001570e  test    eax, eax
0x180015710  jnz     short loc_180015719
0x180015712  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180015717  jmp     short loc_180015775
0x180015719  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hHandle
0x18001571e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180015721  call    cs:__imp_WaitForSingleObject
0x180015727  test    eax, eax
0x180015729  jnz     short loc_18001573F
0x18001572b  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hProcess
0x180015730  mov     rdx, rdi; lpExitCode
0x180015733  and     [rdi], eax
0x180015735  call    cs:__imp_GetExitCodeProcess
0x18001573b  test    eax, eax
0x18001573d  jnz     short loc_180015751
0x18001573f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180015744  mov     ebx, eax
0x180015746  test    eax, eax
0x180015748  js      short loc_18001575D
0x18001574a  mov     ebx, 8000FFFFh
0x18001574f  jmp     short loc_18001575D
0x180015751  mov     eax, [rdi]
0x180015753  neg     eax
0x180015755  sbb     ebx, ebx
0x180015757  and     ebx, 80004005h
0x18001575d  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x180015762  call    cs:__imp_CloseHandle
0x180015768  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x18001576d  call    cs:__imp_CloseHandle
0x180015773  mov     eax, ebx
0x180015775  mov     rbx, [rsp+0E8h+arg_0]
0x18001577d  add     rsp, 0E0h
0x180015784  pop     rdi
0x180015785  retn
```
