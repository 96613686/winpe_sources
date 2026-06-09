# ARPFrame::LaunchClientCommandAndWait(uint,ushort const *,ushort *)

- ea: `0x18000bef0`
- end: `0x18000c02a`
- name: `?LaunchClientCommandAndWait@ARPFrame@@QEAAJIPEBGPEAG@Z`
- size: `314`
- prototype: `__int64 __fastcall(ARPFrame *__hidden this, unsigned int, const unsigned __int16 *, LPWSTR lpCommandLine)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009550`

## callees

- `0x18000bef0`
- `0x18000e500`
- `0x1800582a2`
- `0x180059010`

## import_xrefs

- `SHCORE!__imp_SHWaitForSendMessageThread` at `0x18000bfcd`
- `SHCORE!__imp_SHWaitForSendMessageThread` at `0x18000bfcd`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000bfb9`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000bfb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c000`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c00b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c000`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c00b`

## pseudocode

```c
__int64 __fastcall ARPFrame::LaunchClientCommandAndWait(
        ARPFrame *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        LPWSTR lpCommandLine)
{
  unsigned int v4; // ebx
  __int64 v9; // rcx
  __int64 v10; // rcx
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-C8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-A8h] BYREF

  v4 = 0;
  if ( !*((_BYTE *)this + 373) )
  {
    v9 = *((_QWORD *)this + 47);
    if ( v9 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v9 + 56LL))(v9) )
    {
      v4 = -2147023673;
    }
    else
    {
      ARPFrame::SetProgressDialogText(this, a2, a3);
      memset(&ProcessInformation, 0, sizeof(ProcessInformation));
      memset_0(&StartupInfo, 0, sizeof(StartupInfo));
      StartupInfo.cb = 104;
      StartupInfo.dwFlags = 1;
      StartupInfo.wShowWindow = 1;
      if ( CreateProcessW(0, lpCommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
      {
        while ( (unsigned int)SHWaitForSendMessageThread(ProcessInformation.hProcess, 1000) == 258 )
        {
          v10 = *((_QWORD *)this + 47);
          if ( v10 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v10 + 56LL))(v10) )
          {
            v4 = -2147023673;
            break;
          }
        }
        CloseHandle(ProcessInformation.hProcess);
        CloseHandle(ProcessInformation.hThread);
      }
    }
  }
  ++*((_DWORD *)this + 97);
  return v4;
}

```

## disassembly

```asm
0x18000bef0  push    rbx
0x18000bef2  push    rbp
0x18000bef3  push    rsi
0x18000bef4  push    rdi
0x18000bef5  push    r12
0x18000bef7  push    r14
0x18000bef9  sub     rsp, 0E8h
0x18000bf00  xor     ebx, ebx
0x18000bf02  mov     rsi, r9
0x18000bf05  mov     rbp, r8
0x18000bf08  mov     r14d, edx
0x18000bf0b  mov     rdi, rcx
0x18000bf0e  lea     r12d, [rbx+1]
0x18000bf12  cmp     [rcx+175h], bl
0x18000bf18  jnz     loc_18000C011
0x18000bf1e  mov     rcx, [rcx+178h]
0x18000bf25  test    rcx, rcx
0x18000bf28  jz      short loc_18000BF44
0x18000bf2a  mov     rax, [rcx]
0x18000bf2d  mov     rax, [rax+38h]
0x18000bf31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf36  test    eax, eax
0x18000bf38  jz      short loc_18000BF44
0x18000bf3a  mov     ebx, 800704C7h
0x18000bf3f  jmp     loc_18000C011
0x18000bf44  mov     r8, rbp; unsigned __int16 *
0x18000bf47  mov     edx, r14d; unsigned int
0x18000bf4a  mov     rcx, rdi; this
0x18000bf4d  call    ?SetProgressDialogText@ARPFrame@@QEAAXIPEBG@Z; ARPFrame::SetProgressDialogText(uint,ushort const *)
0x18000bf52  xor     eax, eax
0x18000bf54  lea     rcx, [rsp+118h+StartupInfo]; void *
0x18000bf59  xorps   xmm0, xmm0
0x18000bf5c  mov     qword ptr [rsp+118h+ProcessInformation.dwProcessId], rax
0x18000bf61  xor     edx, edx; Val
0x18000bf63  movups  xmmword ptr [rsp+118h+ProcessInformation.hProcess], xmm0
0x18000bf68  lea     ebp, [rax+68h]
0x18000bf6b  mov     r8d, ebp; Size
0x18000bf6e  call    memset_0
0x18000bf73  lea     rax, [rsp+118h+ProcessInformation]
0x18000bf78  mov     [rsp+118h+StartupInfo.cb], ebp
0x18000bf7c  mov     [rsp+118h+lpProcessInformation], rax; lpProcessInformation
0x18000bf81  xor     r9d, r9d; lpThreadAttributes
0x18000bf84  lea     rax, [rsp+118h+StartupInfo]
0x18000bf89  mov     [rsp+118h+StartupInfo.dwFlags], r12d
0x18000bf91  mov     [rsp+118h+lpStartupInfo], rax; lpStartupInfo
0x18000bf96  xor     r8d, r8d; lpProcessAttributes
0x18000bf99  mov     [rsp+118h+lpCurrentDirectory], rbx; lpCurrentDirectory
0x18000bf9e  mov     rdx, rsi; lpCommandLine
0x18000bfa1  mov     [rsp+118h+lpEnvironment], rbx; lpEnvironment
0x18000bfa6  xor     ecx, ecx; lpApplicationName
0x18000bfa8  mov     [rsp+118h+dwCreationFlags], ebx; dwCreationFlags
0x18000bfac  mov     [rsp+118h+bInheritHandles], ebx; bInheritHandles
0x18000bfb0  mov     [rsp+118h+StartupInfo.wShowWindow], r12w
0x18000bfb9  call    cs:__imp_CreateProcessW
0x18000bfbf  test    eax, eax
0x18000bfc1  jz      short loc_18000C011
0x18000bfc3  mov     rcx, [rsp+118h+ProcessInformation.hProcess]
0x18000bfc8  mov     edx, 3E8h
0x18000bfcd  call    cs:__imp_SHWaitForSendMessageThread
0x18000bfd3  cmp     eax, 102h
0x18000bfd8  jnz     short loc_18000BFFB
0x18000bfda  mov     rcx, [rdi+178h]
0x18000bfe1  test    rcx, rcx
0x18000bfe4  jz      short loc_18000BFC3
0x18000bfe6  mov     rax, [rcx]
0x18000bfe9  mov     rax, [rax+38h]
0x18000bfed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bff2  test    eax, eax
0x18000bff4  jz      short loc_18000BFC3
0x18000bff6  mov     ebx, 800704C7h
0x18000bffb  mov     rcx, [rsp+118h+ProcessInformation.hProcess]; hObject
0x18000c000  call    cs:__imp_CloseHandle
0x18000c006  mov     rcx, [rsp+118h+ProcessInformation.hThread]; hObject
0x18000c00b  call    cs:__imp_CloseHandle
0x18000c011  add     [rdi+184h], r12d
0x18000c018  mov     eax, ebx
0x18000c01a  add     rsp, 0E8h
0x18000c021  pop     r14
0x18000c023  pop     r12
0x18000c025  pop     rdi
0x18000c026  pop     rsi
0x18000c027  pop     rbp
0x18000c028  pop     rbx
0x18000c029  retn
```
