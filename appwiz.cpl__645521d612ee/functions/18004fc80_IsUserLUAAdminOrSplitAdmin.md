# IsUserLUAAdminOrSplitAdmin

- ea: `0x18004fc80`
- end: `0x18004fd68`
- name: `IsUserLUAAdminOrSplitAdmin`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180009d58`

## callees

- `0x18001f6b0`
- `0x18004fc80`
- `0x180057f8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004fcee`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004fcee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004fd39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004fd39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fd31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fd58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fd31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fd58`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004fcc8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004fcc8`
- `USER32!GetWindowThreadProcessId` at `0x18004fcb6`
- `USER32!GetWindowThreadProcessId` at `0x18004fcb6`

## pseudocode

```c
__int64 __fastcall IsUserLUAAdminOrSplitAdmin(HWND a1, _DWORD *a2)
{
  HANDLE CurrentProcess; // rdi
  signed int Error; // ebx
  int v5; // eax
  DWORD dwProcessId; // [rsp+40h] [rbp+8h] BYREF
  int v8; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  dwProcessId = 0;
  TokenHandle = 0;
  v8 = 0;
  *a2 = 0;
  if ( a1 )
  {
    GetWindowThreadProcessId(a1, &dwProcessId);
    CurrentProcess = OpenProcess(0x400u, 0, dwProcessId);
    if ( !CurrentProcess )
    {
      Error = ResultFromLastError();
      if ( Error < 0 )
        return (unsigned int)Error;
    }
  }
  else
  {
    CurrentProcess = GetCurrentProcess();
    if ( !CurrentProcess )
      return (unsigned int)-2147467259;
  }
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    v5 = LUAGetUserType(TokenHandle, &v8);
    Error = v5;
    if ( v5 > 0 )
      Error = (unsigned __int16)v5 | 0x80070000;
    if ( Error >= 0 )
      *a2 = (v8 & 0xFFFFFFEE) == 0;
    CloseHandle(TokenHandle);
  }
  else
  {
    Error = ResultFromLastError();
  }
  CloseHandle(CurrentProcess);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18004fc80  mov     rax, rsp
0x18004fc83  push    rbx
0x18004fc84  push    rsi
0x18004fc85  push    rdi
0x18004fc86  sub     rsp, 20h
0x18004fc8a  mov     dword ptr [rax+8], 0
0x18004fc91  mov     rsi, rdx
0x18004fc94  mov     qword ptr [rax+18h], 0
0x18004fc9c  mov     dword ptr [rax+10h], 0
0x18004fca3  mov     dword ptr [rdx], 0
0x18004fca9  test    rcx, rcx
0x18004fcac  jz      loc_18004FD39
0x18004fcb2  lea     rdx, [rax+8]; lpdwProcessId
0x18004fcb6  call    cs:__imp_GetWindowThreadProcessId
0x18004fcbc  mov     r8d, [rsp+38h+dwProcessId]; dwProcessId
0x18004fcc1  xor     edx, edx; bInheritHandle
0x18004fcc3  mov     ecx, 400h; dwDesiredAccess
0x18004fcc8  call    cs:__imp_OpenProcess
0x18004fcce  mov     rdi, rax
0x18004fcd1  test    rax, rax
0x18004fcd4  jnz     short loc_18004FCE1
0x18004fcd6  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18004fcdb  mov     ebx, eax
0x18004fcdd  test    eax, eax
0x18004fcdf  js      short loc_18004FD5E
0x18004fce1  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18004fce6  mov     edx, 8; DesiredAccess
0x18004fceb  mov     rcx, rdi; ProcessHandle
0x18004fcee  call    cs:__imp_OpenProcessToken
0x18004fcf4  test    eax, eax
0x18004fcf6  jz      short loc_18004FD4E
0x18004fcf8  mov     rcx, [rsp+38h+TokenHandle]
0x18004fcfd  lea     rdx, [rsp+38h+arg_8]
0x18004fd02  call    LUAGetUserType
0x18004fd07  mov     ebx, eax
0x18004fd09  test    eax, eax
0x18004fd0b  jle     short loc_18004FD16
0x18004fd0d  movzx   ebx, ax
0x18004fd10  or      ebx, 80070000h
0x18004fd16  test    ebx, ebx
0x18004fd18  js      short loc_18004FD2C
0x18004fd1a  test    [rsp+38h+arg_8], 0FFFFFFEEh
0x18004fd22  mov     eax, 0
0x18004fd27  setz    al
0x18004fd2a  mov     [rsi], eax
0x18004fd2c  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18004fd31  call    cs:__imp_CloseHandle
0x18004fd37  jmp     short loc_18004FD55
0x18004fd39  call    cs:__imp_GetCurrentProcess
0x18004fd3f  mov     rdi, rax
0x18004fd42  test    rax, rax
0x18004fd45  jnz     short loc_18004FCE1
0x18004fd47  mov     ebx, 80004005h
0x18004fd4c  jmp     short loc_18004FD5E
0x18004fd4e  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18004fd53  mov     ebx, eax
0x18004fd55  mov     rcx, rdi; hObject
0x18004fd58  call    cs:__imp_CloseHandle
0x18004fd5e  mov     eax, ebx
0x18004fd60  add     rsp, 20h
0x18004fd64  pop     rdi
0x18004fd65  pop     rsi
0x18004fd66  pop     rbx
0x18004fd67  retn
```
