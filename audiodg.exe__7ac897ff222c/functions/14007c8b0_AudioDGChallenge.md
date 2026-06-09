# AudioDGChallenge

- ea: `0x14007c8b0`
- end: `0x14007ca2d`
- name: `AudioDGChallenge`
- size: `381`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, HANDLE hSourceHandle)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x14005e168`
- `0x14007c8b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007c933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007c933`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14007c977`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14007c977`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14007c9a3`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14007c9a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007c9ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007ca08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007c9ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007ca08`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14007c91f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14007c91f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14007c9d7`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14007c9d7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14007c9c2`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14007c9c2`
- `ntdll!NtQueryInformationProcess` at `0x14007c960`
- `ntdll!NtQueryInformationProcess` at `0x14007c960`
- `RPCRT4!RpcRevertToSelf` at `0x14007c928`
- `RPCRT4!RpcRevertToSelf` at `0x14007c928`
- `RPCRT4!RpcImpersonateClient` at `0x14007c904`
- `RPCRT4!RpcImpersonateClient` at `0x14007c904`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14007c8f1`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14007c8f1`

## pseudocode

```c
__int64 __fastcall AudioDGChallenge(RPC_BINDING_HANDLE BindingHandle, HANDLE hSourceHandle, __int64 a3)
{
  char *v6; // rdi
  int LastError; // ebx
  HANDLE CurrentProcess; // rax
  _QWORD *v9; // rax
  HANDLE TargetHandle; // [rsp+40h] [rbp-29h] BYREF
  _QWORD ProcessInformation[7]; // [rsp+50h] [rbp-19h] BYREF
  char v13; // [rsp+88h] [rbp+1Fh]
  unsigned int Pid; // [rsp+E8h] [rbp+7Fh] BYREF

  Pid = 0;
  v6 = 0;
  memset_0(ProcessInformation, 0, 0x40u);
  TargetHandle = 0;
  LastError = I_RpcBindingInqLocalClientPID(BindingHandle, &Pid);
  if ( !LastError )
  {
    LastError = RpcImpersonateClient(BindingHandle);
    if ( !LastError )
    {
      v6 = (char *)OpenProcess(0x440u, 0, Pid);
      RpcRevertToSelf();
      if ( !v6 )
      {
LABEL_4:
        LastError = GetLastError();
        goto LABEL_11;
      }
      ProcessInformation[0] = 64;
      if ( NtQueryInformationProcess(v6, ProcessBasicInformation, ProcessInformation, 0x40u, 0) >= 0 && (v13 & 1) != 0 )
      {
        CurrentProcess = GetCurrentProcess();
        if ( !DuplicateHandle(v6, hSourceHandle, CurrentProcess, &TargetHandle, 2u, 0, 0) )
          goto LABEL_4;
        v9 = MapViewOfFile(TargetHandle, 2u, 0, 0, 8u);
        if ( !v9 )
          goto LABEL_4;
        *v9 = a3;
        UnmapViewOfFile(v9);
        LastError = 0;
      }
      else
      {
        LastError = 5;
      }
    }
  }
LABEL_11:
  if ( (char *)TargetHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(TargetHandle);
    TargetHandle = 0;
  }
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x14007c8b0  push    rbp
0x14007c8b2  push    rbx
0x14007c8b3  push    rsi
0x14007c8b4  push    rdi
0x14007c8b5  push    r14
0x14007c8b7  push    r15
0x14007c8b9  lea     rbp, [rsp-2Fh]
0x14007c8be  sub     rsp, 98h
0x14007c8c5  mov     r14, r8
0x14007c8c8  mov     [rbp+57h+Pid], 0
0x14007c8cf  mov     r15, rdx
0x14007c8d2  mov     rsi, rcx
0x14007c8d5  xor     edi, edi
0x14007c8d7  lea     rcx, [rbp+57h+ProcessInformation]; void *
0x14007c8db  xor     edx, edx; Val
0x14007c8dd  lea     r8d, [rdi+40h]; Size
0x14007c8e1  call    memset_0
0x14007c8e6  lea     rdx, [rbp+57h+Pid]; Pid
0x14007c8ea  mov     [rbp+57h+TargetHandle], rdi
0x14007c8ee  mov     rcx, rsi; Binding
0x14007c8f1  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x14007c8f7  mov     ebx, eax
0x14007c8f9  test    eax, eax
0x14007c8fb  jnz     loc_14007C9DF
0x14007c901  mov     rcx, rsi; BindingHandle
0x14007c904  call    cs:__imp_RpcImpersonateClient
0x14007c90a  mov     ebx, eax
0x14007c90c  test    eax, eax
0x14007c90e  jnz     loc_14007C9DF
0x14007c914  mov     r8d, [rbp+57h+Pid]; dwProcessId
0x14007c918  xor     edx, edx; bInheritHandle
0x14007c91a  mov     ecx, 440h; dwDesiredAccess
0x14007c91f  call    cs:__imp_OpenProcess
0x14007c925  mov     rdi, rax
0x14007c928  call    cs:__imp_RpcRevertToSelf
0x14007c92e  test    rdi, rdi
0x14007c931  jnz     short loc_14007C940
0x14007c933  call    cs:__imp_GetLastError
0x14007c939  mov     ebx, eax
0x14007c93b  jmp     loc_14007C9DF
0x14007c940  mov     r9d, 40h ; '@'; ProcessInformationLength
0x14007c946  mov     [rbp+57h+ProcessInformation], 40h ; '@'
0x14007c94e  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x14007c952  mov     [rsp+0C0h+ReturnLength], 0; ReturnLength
0x14007c95b  xor     edx, edx; ProcessInformationClass
0x14007c95d  mov     rcx, rdi; ProcessHandle
0x14007c960  call    cs:__imp_NtQueryInformationProcess
0x14007c966  test    eax, eax
0x14007c968  jns     short loc_14007C971
0x14007c96a  mov     ebx, 5
0x14007c96f  jmp     short loc_14007C9DF
0x14007c971  test    [rbp+57h+var_38], 1
0x14007c975  jz      short loc_14007C96A
0x14007c977  call    cs:__imp_GetCurrentProcess
0x14007c97d  mov     [rsp+0C0h+dwOptions], 0; dwOptions
0x14007c985  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x14007c989  mov     ebx, 2
0x14007c98e  mov     [rsp+0C0h+bInheritHandle], 0; bInheritHandle
0x14007c996  mov     r8, rax; hTargetProcessHandle
0x14007c999  mov     dword ptr [rsp+0C0h+ReturnLength], ebx; dwDesiredAccess
0x14007c99d  mov     rdx, r15; hSourceHandle
0x14007c9a0  mov     rcx, rdi; hSourceProcessHandle
0x14007c9a3  call    cs:__imp_DuplicateHandle
0x14007c9a9  test    eax, eax
0x14007c9ab  jz      short loc_14007C933
0x14007c9ad  mov     rcx, [rbp+57h+TargetHandle]; hFileMappingObject
0x14007c9b1  xor     r9d, r9d; dwFileOffsetLow
0x14007c9b4  xor     r8d, r8d; dwFileOffsetHigh
0x14007c9b7  mov     [rsp+0C0h+ReturnLength], 8; dwNumberOfBytesToMap
0x14007c9c0  mov     edx, ebx; dwDesiredAccess
0x14007c9c2  call    cs:__imp_MapViewOfFile
0x14007c9c8  test    rax, rax
0x14007c9cb  jz      loc_14007C933
0x14007c9d1  mov     rcx, rax; lpBaseAddress
0x14007c9d4  mov     [rax], r14
0x14007c9d7  call    cs:__imp_UnmapViewOfFile
0x14007c9dd  xor     ebx, ebx
0x14007c9df  mov     rcx, [rbp+57h+TargetHandle]; hObject
0x14007c9e3  lea     rax, [rcx-1]
0x14007c9e7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14007c9eb  ja      short loc_14007C9FB
0x14007c9ed  call    cs:__imp_CloseHandle
0x14007c9f3  mov     [rbp+57h+TargetHandle], 0
0x14007c9fb  lea     rax, [rdi-1]
0x14007c9ff  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14007ca03  ja      short loc_14007CA0E
0x14007ca05  mov     rcx, rdi; hObject
0x14007ca08  call    cs:__imp_CloseHandle
0x14007ca0e  test    ebx, ebx
0x14007ca10  jle     short loc_14007CA1B
0x14007ca12  movzx   ebx, bx
0x14007ca15  or      ebx, 80070000h
0x14007ca1b  mov     eax, ebx
0x14007ca1d  add     rsp, 98h
0x14007ca24  pop     r15
0x14007ca26  pop     r14
0x14007ca28  pop     rdi
0x14007ca29  pop     rsi
0x14007ca2a  pop     rbx
0x14007ca2b  pop     rbp
0x14007ca2c  retn
```
