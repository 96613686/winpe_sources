# WcpPrivilegedRemoveFile

- ea: `0x18000de94`
- end: `0x18000e00d`
- name: `WcpPrivilegedRemoveFile`
- size: `377`
- prototype: `__int64 __fastcall(POBJECT_ATTRIBUTES ObjectAttributes, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x18000e014`

## callees

- `0x18000d268`
- `0x18000de94`
- `0x18000edcc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000deed`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000deed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ded5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ded5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000defd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000defd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dff1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dff1`
- `ntdll!NtSetInformationFile` at `0x18000df9c`
- `ntdll!NtSetInformationFile` at `0x18000df9c`
- `ntdll!NtClose` at `0x18000dfd6`
- `ntdll!NtClose` at `0x18000dfd6`
- `ntdll!RtlNtStatusToDosError` at `0x18000dfb2`
- `ntdll!RtlNtStatusToDosError` at `0x18000dfb2`
- `ntdll!NtOpenFile` at `0x18000df53`
- `ntdll!NtOpenFile` at `0x18000df53`

## pseudocode

```c
__int64 __fastcall WcpPrivilegedRemoveFile(POBJECT_ATTRIBUTES ObjectAttributes, __int64 a2, __int64 a3, __int64 a4)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  int v10; // ebx
  int v11; // ebx
  int v12; // eax
  int FileInformation; // [rsp+30h] [rbp-38h] BYREF
  int v15; // [rsp+34h] [rbp-34h] BYREF
  void *FileHandle; // [rsp+38h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-28h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+48h] [rbp-20h] BYREF

  FileInformation = 0;
  IoStatusBlock = 0;
  FileHandle = 0;
  TokenHandle = 0;
  v15 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    v10 = WcpSetPrivilege(TokenHandle, 17, 1, &v15);
    if ( v10 < 0 )
    {
      v11 = v10 | 0x10000000;
      goto LABEL_12;
    }
    v12 = NtOpenFile(&FileHandle, 0x110000u, ObjectAttributes, &IoStatusBlock, 7u, 0x204020u);
    if ( v12 >= 0 )
    {
      v11 = EnsurePathNotRedirected(FileHandle, a2, a3, a4);
      if ( v11 < 0 )
        goto LABEL_12;
      FileInformation = 17;
      v12 = NtSetInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 4u, (FILE_INFORMATION_CLASS)64);
      if ( v12 >= 0 )
      {
        v11 = 0;
        goto LABEL_12;
      }
    }
    LastError = RtlNtStatusToDosError(v12);
  }
  else
  {
    LastError = GetLastError();
  }
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
LABEL_12:
  if ( FileHandle && NtClose(FileHandle) < 0 )
    __int2c();
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000de94  push    rbp
0x18000de96  push    rbx
0x18000de97  push    rsi
0x18000de98  push    rdi
0x18000de99  push    r14
0x18000de9b  push    r15
0x18000de9d  mov     rbp, rsp
0x18000dea0  sub     rsp, 68h
0x18000dea4  xorps   xmm0, xmm0
0x18000dea7  mov     [rbp+FileInformation], 0
0x18000deae  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x18000deb2  mov     rsi, r9
0x18000deb5  mov     [rbp+FileHandle], 0
0x18000debd  mov     r14, r8
0x18000dec0  mov     [rbp+TokenHandle], 0
0x18000dec8  mov     r15, rdx
0x18000decb  mov     [rbp+var_34], 0
0x18000ded2  mov     rdi, rcx
0x18000ded5  call    cs:__imp_GetCurrentProcess
0x18000dedc  nop     dword ptr [rax+rax+00h]
0x18000dee1  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000dee5  mov     edx, 28h ; '('; DesiredAccess
0x18000deea  mov     rcx, rax; ProcessHandle
0x18000deed  call    cs:__imp_OpenProcessToken
0x18000def4  nop     dword ptr [rax+rax+00h]
0x18000def9  test    eax, eax
0x18000defb  jnz     short loc_18000DF0E
0x18000defd  call    cs:__imp_GetLastError
0x18000df04  nop     dword ptr [rax+rax+00h]
0x18000df09  jmp     loc_18000DFBE
0x18000df0e  mov     rcx, [rbp+TokenHandle]
0x18000df12  lea     r9, [rbp+var_34]
0x18000df16  mov     edx, 11h
0x18000df1b  lea     r8d, [rdx-10h]
0x18000df1f  call    WcpSetPrivilege
0x18000df24  mov     ebx, eax
0x18000df26  test    eax, eax
0x18000df28  jns     short loc_18000DF33
0x18000df2a  bts     ebx, 1Ch
0x18000df2e  jmp     loc_18000DFCD
0x18000df33  mov     [rsp+68h+OpenOptions], 204020h; OpenOptions
0x18000df3b  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x18000df3f  mov     r8, rdi; ObjectAttributes
0x18000df42  mov     [rsp+68h+ShareAccess], 7; ShareAccess
0x18000df4a  mov     edx, 110000h; DesiredAccess
0x18000df4f  lea     rcx, [rbp+FileHandle]; FileHandle
0x18000df53  call    cs:__imp_NtOpenFile
0x18000df5a  nop     dword ptr [rax+rax+00h]
0x18000df5f  test    eax, eax
0x18000df61  js      short loc_18000DFB0
0x18000df63  mov     rcx, [rbp+FileHandle]
0x18000df67  mov     r9, rsi
0x18000df6a  mov     r8, r14
0x18000df6d  mov     rdx, r15
0x18000df70  call    EnsurePathNotRedirected
0x18000df75  mov     ebx, eax
0x18000df77  test    eax, eax
0x18000df79  js      short loc_18000DFCD
0x18000df7b  mov     rcx, [rbp+FileHandle]; FileHandle
0x18000df7f  lea     r8, [rbp+FileInformation]; FileInformation
0x18000df83  mov     r9d, 4; Length
0x18000df89  mov     [rbp+FileInformation], 11h
0x18000df90  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x18000df94  mov     [rsp+68h+ShareAccess], 40h ; '@'; FileInformationClass
0x18000df9c  call    cs:__imp_NtSetInformationFile
0x18000dfa3  nop     dword ptr [rax+rax+00h]
0x18000dfa8  test    eax, eax
0x18000dfaa  js      short loc_18000DFB0
0x18000dfac  xor     ebx, ebx
0x18000dfae  jmp     short loc_18000DFCD
0x18000dfb0  mov     ecx, eax; Status
0x18000dfb2  call    cs:__imp_RtlNtStatusToDosError
0x18000dfb9  nop     dword ptr [rax+rax+00h]
0x18000dfbe  mov     ebx, eax
0x18000dfc0  test    eax, eax
0x18000dfc2  jle     short loc_18000DFCD
0x18000dfc4  movzx   ebx, ax
0x18000dfc7  or      ebx, 80070000h
0x18000dfcd  mov     rcx, [rbp+FileHandle]; Handle
0x18000dfd1  test    rcx, rcx
0x18000dfd4  jz      short loc_18000DFE8
0x18000dfd6  call    cs:__imp_NtClose
0x18000dfdd  nop     dword ptr [rax+rax+00h]
0x18000dfe2  test    eax, eax
0x18000dfe4  jns     short loc_18000DFE8
0x18000dfe6  int     2Ch; Windows NT - assertion failure
0x18000dfe8  mov     rcx, [rbp+TokenHandle]; hObject
0x18000dfec  test    rcx, rcx
0x18000dfef  jz      short loc_18000DFFD
0x18000dff1  call    cs:__imp_CloseHandle
0x18000dff8  nop     dword ptr [rax+rax+00h]
0x18000dffd  mov     eax, ebx
0x18000dfff  add     rsp, 68h
0x18000e003  pop     r15
0x18000e005  pop     r14
0x18000e007  pop     rdi
0x18000e008  pop     rsi
0x18000e009  pop     rbx
0x18000e00a  pop     rbp
0x18000e00b  retn
```
