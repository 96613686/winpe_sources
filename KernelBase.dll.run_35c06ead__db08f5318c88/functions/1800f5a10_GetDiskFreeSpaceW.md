# GetDiskFreeSpaceW

- ea: `0x1800f5a10`
- end: `0x1800f5c54`
- name: `GetDiskFreeSpaceW`
- size: `580`
- prototype: `BOOL __stdcall(LPCWSTR lpRootPathName, LPDWORD lpSectorsPerCluster, LPDWORD lpBytesPerSector, LPDWORD lpNumberOfFreeClusters, LPDWORD lpTotalNumberOfClusters)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800f5990`

## callees

- `0x1800134a0`
- `0x1800f5a10`
- `0x180188f10`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1800f5ae0`
- `ntdll!NtOpenFile` at `0x1800f5ae0`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800f5a87`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800f5a87`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800f5b20`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800f5b20`
- `ntdll!RtlSetLastWin32Error` at `0x1800f5c38`
- `ntdll!RtlSetLastWin32Error` at `0x1800f5c38`
- `ntdll!NtClose` at `0x1800f5b2c`
- `ntdll!NtClose` at `0x1800f5b2c`
- `ntdll!RtlFreeHeap` at `0x1800f5b00`
- `ntdll!RtlFreeHeap` at `0x1800f5c1b`
- `ntdll!RtlFreeHeap` at `0x1800f5b00`
- `ntdll!RtlFreeHeap` at `0x1800f5c1b`

## pseudocode

```c
BOOL __stdcall GetDiskFreeSpaceW(
        LPCWSTR lpRootPathName,
        LPDWORD lpSectorsPerCluster,
        LPDWORD lpBytesPerSector,
        LPDWORD lpNumberOfFreeClusters,
        LPDWORD lpTotalNumberOfClusters)
{
  const WCHAR *v6; // rcx
  PWSTR Buffer; // rdi
  NTSTATUS v11; // eax
  NTSTATUS v12; // edi
  DWORD v13; // r10d
  DWORD v14; // edi
  unsigned __int64 v15; // r9
  ULONGLONG v16; // r11
  unsigned __int64 v17; // r8
  DWORD v18; // eax
  DWORD v19; // eax
  int v21; // [rsp+30h] [rbp-61h] BYREF
  HANDLE FileHandle; // [rsp+38h] [rbp-59h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+40h] [rbp-51h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-41h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-11h] BYREF
  __int128 FsInformation; // [rsp+90h] [rbp-1h] BYREF
  __int64 v27; // [rsp+A0h] [rbp+Fh]

  v21 = 92;
  v6 = (const WCHAR *)&v21;
  FileHandle = 0;
  v27 = 0;
  if ( lpRootPathName )
    v6 = lpRootPathName;
  memset(&ObjectAttributes, 0, 44);
  NtPathName = 0;
  IoStatusBlock = 0;
  FsInformation = 0;
  if ( !RtlDosPathNameToNtPathName_U(v6, &NtPathName, 0, 0) )
  {
    RtlSetLastWin32Error(3u);
    return 0;
  }
  Buffer = NtPathName.Buffer;
  ObjectAttributes.ObjectName = &NtPathName;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v11 = NtOpenFile(&FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 3u, 0x800021u);
  if ( v11 < 0 )
  {
    BaseSetLastNTError((unsigned int)v11);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    if ( lpBytesPerSector )
      *lpBytesPerSector = 0;
    return 0;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  v12 = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &FsInformation, 0x18u, FileFsSizeInformation);
  NtClose(FileHandle);
  if ( v12 < 0 )
  {
    BaseSetLastNTError((unsigned int)v12);
    return 0;
  }
  v13 = FsInformation;
  v14 = DWORD2(FsInformation);
  v15 = (unsigned int)v27;
  v16 = NtCurrentPeb()->AppCompatFlags.QuadPart & 8;
  if ( DWORD1(FsInformation) )
    v13 = -1;
  if ( HIDWORD(FsInformation) )
    v14 = -1;
  if ( lpSectorsPerCluster )
    *lpSectorsPerCluster = v27;
  v17 = HIDWORD(v27);
  if ( lpBytesPerSector )
    *lpBytesPerSector = HIDWORD(v27);
  if ( lpNumberOfFreeClusters )
  {
    if ( v16 && v15 <= 0xFFFFFFFFFFFFFFFFuLL / v17 && (v18 = 0x7FFFFFFFu / ((int)v15 * (int)v17), v18 < v14) )
      *lpNumberOfFreeClusters = v18;
    else
      *lpNumberOfFreeClusters = v14;
  }
  if ( lpTotalNumberOfClusters )
  {
    if ( v16 && v15 <= 0xFFFFFFFFFFFFFFFFuLL / v17 && (v19 = 0x7FFFFFFFu / ((int)v15 * (int)v17), v19 < v13) )
      *lpTotalNumberOfClusters = v19;
    else
      *lpTotalNumberOfClusters = v13;
  }
  return 1;
}

```

## disassembly

```asm
0x1800f5a10  push    rbp
0x1800f5a12  push    rbx
0x1800f5a13  push    rsi
0x1800f5a14  push    rdi
0x1800f5a15  push    r14
0x1800f5a17  push    r15
0x1800f5a19  lea     rbp, [rsp-27h]
0x1800f5a1e  sub     rsp, 0B8h
0x1800f5a25  mov     rax, cs:__security_cookie
0x1800f5a2c  xor     rax, rsp
0x1800f5a2f  mov     [rbp+4Fh+var_38], rax
0x1800f5a33  mov     rsi, [rbp+4Fh+lpTotalNumberOfClusters]
0x1800f5a37  xorps   xmm0, xmm0
0x1800f5a3a  mov     r10, rcx
0x1800f5a3d  mov     [rbp+4Fh+var_B0], 5Ch ; '\'
0x1800f5a44  xor     eax, eax
0x1800f5a46  lea     rcx, [rbp+4Fh+var_B0]
0x1800f5a4a  test    r10, r10
0x1800f5a4d  mov     [rbp+4Fh+FileHandle], rax
0x1800f5a51  mov     r14, r9
0x1800f5a54  mov     [rbp+4Fh+var_40], rax
0x1800f5a58  cmovnz  rcx, r10; DosPathName
0x1800f5a5c  mov     rbx, r8
0x1800f5a5f  mov     r15, rdx
0x1800f5a62  xorps   xmm1, xmm1
0x1800f5a65  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x1800f5a69  xor     r9d, r9d; DirectoryInfo
0x1800f5a6c  lea     rdx, [rbp+4Fh+NtPathName]; NtPathName
0x1800f5a70  xor     r8d, r8d; NtFileNamePart
0x1800f5a73  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x1800f5a77  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x1800f5a7b  movups  xmmword ptr [rbp+4Fh+NtPathName.Length], xmm0
0x1800f5a7f  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm1
0x1800f5a83  movups  [rbp+4Fh+FsInformation], xmm0
0x1800f5a87  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800f5a8d  test    al, al
0x1800f5a8f  jz      loc_1800F5C33
0x1800f5a95  mov     rdi, [rbp+4Fh+NtPathName.Buffer]
0x1800f5a99  lea     rax, [rbp+4Fh+NtPathName]
0x1800f5a9d  xorps   xmm0, xmm0
0x1800f5aa0  mov     [rsp+0E0h+OpenOptions], 800021h; OpenOptions
0x1800f5aa8  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x1800f5aac  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x1800f5ab0  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1800f5ab4  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1800f5abb  mov     edx, 100000h; DesiredAccess
0x1800f5ac0  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], 0
0x1800f5ac8  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1800f5acc  mov     [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x1800f5ad3  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1800f5ad8  mov     [rsp+0E0h+ShareAccess], 3; ShareAccess
0x1800f5ae0  call    cs:__imp_NtOpenFile
0x1800f5ae6  test    eax, eax
0x1800f5ae8  js      loc_1800F5C02
0x1800f5aee  mov     rcx, gs:60h
0x1800f5af7  mov     r8, rdi; P
0x1800f5afa  xor     edx, edx; Flags
0x1800f5afc  mov     rcx, [rcx+30h]; HeapHandle
0x1800f5b00  call    cs:__imp_RtlFreeHeap
0x1800f5b06  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1800f5b0a  lea     r8, [rbp+4Fh+FsInformation]; FsInformation
0x1800f5b0e  mov     r9d, 18h; Length
0x1800f5b14  mov     [rsp+0E0h+ShareAccess], 3; FsInformationClass
0x1800f5b1c  lea     rdx, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x1800f5b20  call    cs:__imp_NtQueryVolumeInformationFile
0x1800f5b26  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x1800f5b2a  mov     edi, eax
0x1800f5b2c  call    cs:__imp_NtClose
0x1800f5b32  test    edi, edi
0x1800f5b34  js      loc_1800F5C2A
0x1800f5b3a  mov     rax, gs:60h
0x1800f5b43  mov     r10d, dword ptr [rbp+4Fh+FsInformation]
0x1800f5b47  mov     edi, dword ptr [rbp+4Fh+FsInformation+8]
0x1800f5b4a  mov     r9d, dword ptr [rbp+4Fh+var_40]
0x1800f5b4e  mov     r11, [rax+2C8h]
0x1800f5b55  or      eax, 0FFFFFFFFh
0x1800f5b58  and     r11d, 8
0x1800f5b5c  cmp     dword ptr [rbp+4Fh+FsInformation+4], 0
0x1800f5b60  cmovnz  r10d, eax
0x1800f5b64  cmp     dword ptr [rbp+4Fh+FsInformation+0Ch], 0
0x1800f5b68  cmovnz  edi, eax
0x1800f5b6b  test    r15, r15
0x1800f5b6e  jz      short loc_1800F5B73
0x1800f5b70  mov     [r15], r9d
0x1800f5b73  mov     r8d, dword ptr [rbp+4Fh+var_40+4]
0x1800f5b77  test    rbx, rbx
0x1800f5b7a  jz      short loc_1800F5B7F
0x1800f5b7c  mov     [rbx], r8d
0x1800f5b7f  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800f5b83  mov     ebx, 7FFFFFFFh
0x1800f5b88  test    r14, r14
0x1800f5b8b  jz      short loc_1800F5BB7
0x1800f5b8d  test    r11, r11
0x1800f5b90  jz      short loc_1800F5BB4
0x1800f5b92  xor     edx, edx
0x1800f5b94  mov     rax, r15
0x1800f5b97  div     r8
0x1800f5b9a  cmp     r9, rax
0x1800f5b9d  ja      short loc_1800F5BB4
0x1800f5b9f  xor     edx, edx
0x1800f5ba1  mov     ecx, r8d
0x1800f5ba4  imul    ecx, r9d
0x1800f5ba8  mov     eax, ebx
0x1800f5baa  div     ecx
0x1800f5bac  cmp     eax, edi
0x1800f5bae  jb      loc_1800F5C48
0x1800f5bb4  mov     [r14], edi
0x1800f5bb7  test    rsi, rsi
0x1800f5bba  jz      short loc_1800F5BE1
0x1800f5bbc  test    r11, r11
0x1800f5bbf  jz      short loc_1800F5BDE
0x1800f5bc1  xor     edx, edx
0x1800f5bc3  mov     rax, r15
0x1800f5bc6  div     r8
0x1800f5bc9  cmp     r9, rax
0x1800f5bcc  ja      short loc_1800F5BDE
0x1800f5bce  imul    r8d, r9d
0x1800f5bd2  xor     edx, edx
0x1800f5bd4  mov     eax, ebx
0x1800f5bd6  div     r8d
0x1800f5bd9  cmp     eax, r10d
0x1800f5bdc  jb      short loc_1800F5C50
0x1800f5bde  mov     [rsi], r10d
0x1800f5be1  mov     eax, 1
0x1800f5be6  mov     rcx, [rbp+4Fh+var_38]
0x1800f5bea  xor     rcx, rsp; StackCookie
0x1800f5bed  call    __security_check_cookie
0x1800f5bf2  add     rsp, 0B8h
0x1800f5bf9  pop     r15
0x1800f5bfb  pop     r14
0x1800f5bfd  pop     rdi
0x1800f5bfe  pop     rsi
0x1800f5bff  pop     rbx
0x1800f5c00  pop     rbp
0x1800f5c01  retn
0x1800f5c02  mov     ecx, eax
0x1800f5c04  call    BaseSetLastNTError
0x1800f5c09  mov     rcx, gs:60h
0x1800f5c12  mov     r8, rdi; P
0x1800f5c15  xor     edx, edx; Flags
0x1800f5c17  mov     rcx, [rcx+30h]; HeapHandle
0x1800f5c1b  call    cs:__imp_RtlFreeHeap
0x1800f5c21  test    rbx, rbx
0x1800f5c24  jnz     short loc_1800F5C40
0x1800f5c26  xor     eax, eax
0x1800f5c28  jmp     short loc_1800F5BE6
0x1800f5c2a  mov     ecx, edi
0x1800f5c2c  call    BaseSetLastNTError
0x1800f5c31  jmp     short loc_1800F5C26
0x1800f5c33  mov     ecx, 3; LastError
0x1800f5c38  call    cs:__imp_RtlSetLastWin32Error
0x1800f5c3e  jmp     short loc_1800F5C26
0x1800f5c40  mov     dword ptr [rbx], 0
0x1800f5c46  jmp     short loc_1800F5C26
0x1800f5c48  mov     [r14], eax
0x1800f5c4b  jmp     loc_1800F5BB7
0x1800f5c50  mov     [rsi], eax
0x1800f5c52  jmp     short loc_1800F5BE1
```
