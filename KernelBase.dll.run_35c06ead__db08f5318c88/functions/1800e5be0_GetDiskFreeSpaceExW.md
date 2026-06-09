# GetDiskFreeSpaceExW

- ea: `0x1800e5be0`
- end: `0x1800e5e07`
- name: `GetDiskFreeSpaceExW`
- size: `551`
- prototype: `BOOL __stdcall(LPCWSTR lpDirectoryName, PULARGE_INTEGER lpFreeBytesAvailableToCaller, PULARGE_INTEGER lpTotalNumberOfBytes, PULARGE_INTEGER lpTotalNumberOfFreeBytes)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800e5b60`
- `0x18011328c`

## callees

- `0x1800134a0`
- `0x1800e5be0`
- `0x180188f10`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1800e5caa`
- `ntdll!NtOpenFile` at `0x1800e5caa`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800e5c51`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800e5c51`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800e5cef`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800e5d4d`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800e5cef`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800e5d4d`
- `ntdll!RtlSetLastWin32Error` at `0x1800e5db8`
- `ntdll!RtlSetLastWin32Error` at `0x1800e5dff`
- `ntdll!RtlSetLastWin32Error` at `0x1800e5db8`
- `ntdll!RtlSetLastWin32Error` at `0x1800e5dff`
- `ntdll!NtClose` at `0x1800e5cfd`
- `ntdll!NtClose` at `0x1800e5d5a`
- `ntdll!NtClose` at `0x1800e5cfd`
- `ntdll!NtClose` at `0x1800e5d5a`
- `ntdll!RtlFreeHeap` at `0x1800e5cca`
- `ntdll!RtlFreeHeap` at `0x1800e5de8`
- `ntdll!RtlFreeHeap` at `0x1800e5cca`
- `ntdll!RtlFreeHeap` at `0x1800e5de8`

## pseudocode

```c
BOOL __stdcall GetDiskFreeSpaceExW(
        LPCWSTR lpDirectoryName,
        PULARGE_INTEGER lpFreeBytesAvailableToCaller,
        PULARGE_INTEGER lpTotalNumberOfBytes,
        PULARGE_INTEGER lpTotalNumberOfFreeBytes)
{
  bool v5; // zf
  const WCHAR *v7; // rcx
  PWSTR Buffer; // r14
  NTSTATUS v11; // eax
  __int64 v12; // rcx
  NTSTATUS v13; // r14d
  __int64 v14; // rcx
  ULONGLONG v15; // rax
  int v17; // [rsp+30h] [rbp-59h] BYREF
  HANDLE FileHandle; // [rsp+38h] [rbp-51h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+40h] [rbp-49h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-29h] BYREF
  __int128 FsInformation; // [rsp+90h] [rbp+7h] BYREF
  __int128 v23; // [rsp+A0h] [rbp+17h]

  v17 = 92;
  v5 = lpDirectoryName == 0;
  FileHandle = 0;
  v7 = (const WCHAR *)&v17;
  if ( !v5 )
    v7 = lpDirectoryName;
  memset(&ObjectAttributes, 0, 44);
  NtPathName = 0;
  IoStatusBlock = 0;
  FsInformation = 0;
  v23 = 0;
  if ( RtlDosPathNameToNtPathName_U(v7, &NtPathName, 0, 0) )
  {
    Buffer = NtPathName.Buffer;
    ObjectAttributes.ObjectName = &NtPathName;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v11 = NtOpenFile(&FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 0, 0x800021u);
    if ( v11 < 0 )
    {
      BaseSetLastNTError((unsigned int)v11);
      if ( NtCurrentTeb()->LastErrorValue == 2 )
        RtlSetLastWin32Error(3u);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    }
    else
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
      if ( lpTotalNumberOfFreeBytes
        && NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &FsInformation, 0x20u, FileFsFullSizeInformation) >= 0 )
      {
        NtClose(FileHandle);
        v12 = (unsigned int)(HIDWORD(v23) * DWORD2(v23));
        if ( lpFreeBytesAvailableToCaller )
          lpFreeBytesAvailableToCaller->QuadPart = *((_QWORD *)&FsInformation + 1) * (unsigned int)v12;
        if ( lpTotalNumberOfBytes )
          lpTotalNumberOfBytes->QuadPart = FsInformation * v12;
        lpTotalNumberOfFreeBytes->QuadPart = v23 * v12;
        return 1;
      }
      v13 = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &FsInformation, 0x18u, FileFsSizeInformation);
      NtClose(FileHandle);
      if ( v13 >= 0 )
      {
        v14 = (unsigned int)(DWORD1(v23) * v23);
        v15 = *((_QWORD *)&FsInformation + 1) * v14;
        if ( lpFreeBytesAvailableToCaller )
          lpFreeBytesAvailableToCaller->QuadPart = v15;
        if ( lpTotalNumberOfBytes )
          lpTotalNumberOfBytes->QuadPart = FsInformation * v14;
        if ( lpTotalNumberOfFreeBytes )
          lpTotalNumberOfFreeBytes->QuadPart = v15;
        return 1;
      }
      BaseSetLastNTError((unsigned int)v13);
    }
  }
  else
  {
    RtlSetLastWin32Error(3u);
  }
  return 0;
}

```

## disassembly

```asm
0x1800e5be0  push    rbp
0x1800e5be2  push    rbx
0x1800e5be3  push    rsi
0x1800e5be4  push    rdi
0x1800e5be5  push    r14
0x1800e5be7  lea     rbp, [rsp-37h]
0x1800e5bec  sub     rsp, 0C0h
0x1800e5bf3  mov     rax, cs:__security_cookie
0x1800e5bfa  xor     rax, rsp
0x1800e5bfd  mov     [rbp+57h+var_30], rax
0x1800e5c01  xorps   xmm0, xmm0
0x1800e5c04  mov     [rbp+57h+var_B0], 5Ch ; '\'
0x1800e5c0b  mov     r10, rcx
0x1800e5c0e  xor     eax, eax
0x1800e5c10  test    r10, r10
0x1800e5c13  mov     [rbp+57h+FileHandle], rax
0x1800e5c17  mov     rdi, r9
0x1800e5c1a  lea     rcx, [rbp+57h+var_B0]
0x1800e5c1e  cmovnz  rcx, r10; DosPathName
0x1800e5c22  mov     rbx, r8
0x1800e5c25  mov     rsi, rdx
0x1800e5c28  xorps   xmm1, xmm1
0x1800e5c2b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800e5c2f  xor     r9d, r9d; DirectoryInfo
0x1800e5c32  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x1800e5c36  xor     r8d, r8d; NtFileNamePart
0x1800e5c39  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800e5c3d  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800e5c41  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x1800e5c45  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x1800e5c49  movups  [rbp+57h+FsInformation], xmm0
0x1800e5c4d  movups  [rbp+57h+var_40], xmm0
0x1800e5c51  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800e5c57  test    al, al
0x1800e5c59  jz      loc_1800E5DB3
0x1800e5c5f  mov     r14, [rbp+57h+NtPathName.Buffer]
0x1800e5c63  lea     rax, [rbp+57h+NtPathName]
0x1800e5c67  xorps   xmm0, xmm0
0x1800e5c6a  mov     [rsp+0E0h+OpenOptions], 800021h; OpenOptions
0x1800e5c72  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800e5c76  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800e5c7a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800e5c7e  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800e5c85  mov     edx, 100000h; DesiredAccess
0x1800e5c8a  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800e5c92  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800e5c96  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800e5c9d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800e5ca2  mov     [rsp+0E0h+ShareAccess], 0; ShareAccess
0x1800e5caa  call    cs:__imp_NtOpenFile
0x1800e5cb0  test    eax, eax
0x1800e5cb2  js      loc_1800E5DC2
0x1800e5cb8  mov     rcx, gs:60h
0x1800e5cc1  mov     r8, r14; P
0x1800e5cc4  xor     edx, edx; Flags
0x1800e5cc6  mov     rcx, [rcx+30h]; HeapHandle
0x1800e5cca  call    cs:__imp_RtlFreeHeap
0x1800e5cd0  test    rdi, rdi
0x1800e5cd3  jz      short loc_1800E5D33
0x1800e5cd5  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800e5cd9  lea     r8, [rbp+57h+FsInformation]; FsInformation
0x1800e5cdd  mov     r9d, 20h ; ' '; Length
0x1800e5ce3  mov     [rsp+0E0h+ShareAccess], 7; FsInformationClass
0x1800e5ceb  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800e5cef  call    cs:__imp_NtQueryVolumeInformationFile
0x1800e5cf5  test    eax, eax
0x1800e5cf7  js      short loc_1800E5D33
0x1800e5cf9  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800e5cfd  call    cs:__imp_NtClose
0x1800e5d03  mov     ecx, dword ptr [rbp+57h+var_40+8]
0x1800e5d06  imul    ecx, dword ptr [rbp+57h+var_40+0Ch]
0x1800e5d0a  test    rsi, rsi
0x1800e5d0d  jz      short loc_1800E5D19
0x1800e5d0f  mov     eax, ecx
0x1800e5d11  imul    rax, qword ptr [rbp+57h+FsInformation+8]
0x1800e5d16  mov     [rsi], rax
0x1800e5d19  test    rbx, rbx
0x1800e5d1c  jz      short loc_1800E5D29
0x1800e5d1e  mov     rax, rcx
0x1800e5d21  imul    rax, qword ptr [rbp+57h+FsInformation]
0x1800e5d26  mov     [rbx], rax
0x1800e5d29  imul    rcx, qword ptr [rbp+57h+var_40]
0x1800e5d2e  mov     [rdi], rcx
0x1800e5d31  jmp     short loc_1800E5D94
0x1800e5d33  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800e5d37  lea     r8, [rbp+57h+FsInformation]; FsInformation
0x1800e5d3b  mov     r9d, 18h; Length
0x1800e5d41  mov     [rsp+0E0h+ShareAccess], 3; FsInformationClass
0x1800e5d49  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800e5d4d  call    cs:__imp_NtQueryVolumeInformationFile
0x1800e5d53  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800e5d57  mov     r14d, eax
0x1800e5d5a  call    cs:__imp_NtClose
0x1800e5d60  test    r14d, r14d
0x1800e5d63  js      loc_1800E5DF0
0x1800e5d69  mov     eax, dword ptr [rbp+57h+var_40]
0x1800e5d6c  imul    eax, dword ptr [rbp+57h+var_40+4]
0x1800e5d70  mov     ecx, eax
0x1800e5d72  imul    rax, qword ptr [rbp+57h+FsInformation+8]
0x1800e5d77  test    rsi, rsi
0x1800e5d7a  jz      short loc_1800E5D7F
0x1800e5d7c  mov     [rsi], rax
0x1800e5d7f  test    rbx, rbx
0x1800e5d82  jz      short loc_1800E5D8C
0x1800e5d84  imul    rcx, qword ptr [rbp+57h+FsInformation]
0x1800e5d89  mov     [rbx], rcx
0x1800e5d8c  test    rdi, rdi
0x1800e5d8f  jz      short loc_1800E5D94
0x1800e5d91  mov     [rdi], rax
0x1800e5d94  mov     eax, 1
0x1800e5d99  mov     rcx, [rbp+57h+var_30]
0x1800e5d9d  xor     rcx, rsp; StackCookie
0x1800e5da0  call    __security_check_cookie
0x1800e5da5  add     rsp, 0C0h
0x1800e5dac  pop     r14
0x1800e5dae  pop     rdi
0x1800e5daf  pop     rsi
0x1800e5db0  pop     rbx
0x1800e5db1  pop     rbp
0x1800e5db2  retn
0x1800e5db3  mov     ecx, 3; LastError
0x1800e5db8  call    cs:__imp_RtlSetLastWin32Error
0x1800e5dbe  xor     eax, eax
0x1800e5dc0  jmp     short loc_1800E5D99
0x1800e5dc2  mov     ecx, eax
0x1800e5dc4  call    BaseSetLastNTError
0x1800e5dc9  mov     eax, gs:68h
0x1800e5dd1  cmp     eax, 2
0x1800e5dd4  jz      short loc_1800E5DFA
0x1800e5dd6  mov     rcx, gs:60h
0x1800e5ddf  mov     r8, r14; P
0x1800e5de2  xor     edx, edx; Flags
0x1800e5de4  mov     rcx, [rcx+30h]; HeapHandle
0x1800e5de8  call    cs:__imp_RtlFreeHeap
0x1800e5dee  jmp     short loc_1800E5DBE
0x1800e5df0  mov     ecx, r14d
0x1800e5df3  call    BaseSetLastNTError
0x1800e5df8  jmp     short loc_1800E5DBE
0x1800e5dfa  mov     ecx, 3; LastError
0x1800e5dff  call    cs:__imp_RtlSetLastWin32Error
0x1800e5e05  jmp     short loc_1800E5DD6
```
