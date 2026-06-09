# GetDiskSpaceInformationW

- ea: `0x180182030`
- end: `0x1801821b5`
- name: `GetDiskSpaceInformationW`
- size: `389`
- prototype: `HRESULT __stdcall(LPCWSTR rootPath, DISK_SPACE_INFORMATION *diskSpaceInfo)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180181fc0`
- `0x1801821c0`

## callees

- `0x1800134a0`
- `0x180182030`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1801820ee`
- `ntdll!NtOpenFile` at `0x1801820ee`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180182084`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180182084`
- `ntdll!NtQueryVolumeInformationFile` at `0x180182181`
- `ntdll!NtQueryVolumeInformationFile` at `0x180182181`
- `ntdll!RtlSetLastWin32Error` at `0x180182093`
- `ntdll!RtlSetLastWin32Error` at `0x180182113`
- `ntdll!RtlSetLastWin32Error` at `0x18018215b`
- `ntdll!RtlSetLastWin32Error` at `0x180182093`
- `ntdll!RtlSetLastWin32Error` at `0x180182113`
- `ntdll!RtlSetLastWin32Error` at `0x18018215b`
- `ntdll!NtClose` at `0x18018218d`
- `ntdll!NtClose` at `0x18018218d`
- `ntdll!RtlFreeHeap` at `0x18018212b`
- `ntdll!RtlFreeHeap` at `0x18018214b`
- `ntdll!RtlFreeHeap` at `0x18018212b`
- `ntdll!RtlFreeHeap` at `0x18018214b`

## pseudocode

```c
HRESULT __stdcall GetDiskSpaceInformationW(LPCWSTR rootPath, DISK_SPACE_INFORMATION *diskSpaceInfo)
{
  const WCHAR *v3; // rcx
  PWSTR Buffer; // rdi
  NTSTATUS v7; // eax
  NTSTATUS v8; // ebx
  struct _UNICODE_STRING NtPathName; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  int v12; // [rsp+B0h] [rbp+30h] BYREF
  HANDLE FileHandle; // [rsp+B8h] [rbp+38h] BYREF

  v12 = 92;
  v3 = (const WCHAR *)&v12;
  FileHandle = 0;
  if ( rootPath )
    v3 = rootPath;
  memset(&ObjectAttributes, 0, 44);
  NtPathName = 0;
  IoStatusBlock = 0;
  if ( !RtlDosPathNameToNtPathName_U(v3, &NtPathName, 0, 0) )
  {
    RtlSetLastWin32Error(3u);
    return -2147024893;
  }
  Buffer = NtPathName.Buffer;
  ObjectAttributes.ObjectName = &NtPathName;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = NtOpenFile(&FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 0, 0x800021u);
  v8 = v7;
  if ( v7 < 0 )
  {
    BaseSetLastNTError((unsigned int)v7);
    if ( NtCurrentTeb()->LastErrorValue == 2 )
      RtlSetLastWin32Error(3u);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    return v8 | 0x10000000;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( diskSpaceInfo )
  {
    v8 = NtQueryVolumeInformationFile(
           FileHandle,
           &IoStatusBlock,
           diskSpaceInfo,
           0x60u,
           FileFsMaximumInformation|FileFsDeviceInformation);
    NtClose(FileHandle);
    if ( v8 < 0 )
    {
      BaseSetLastNTError((unsigned int)v8);
      return v8 | 0x10000000;
    }
    return 0;
  }
  else
  {
    RtlSetLastWin32Error(0xC000000D);
    return -805306355;
  }
}

```

## disassembly

```asm
0x180182030  mov     [rsp-18h+arg_0], rbx
0x180182035  push    rbp
0x180182036  push    rsi
0x180182037  push    rdi
0x180182038  mov     rbp, rsp
0x18018203b  sub     rsp, 80h
0x180182042  mov     r8, rcx
0x180182045  mov     [rbp+arg_10], 5Ch ; '\'
0x18018204c  xorps   xmm0, xmm0
0x18018204f  lea     rcx, [rbp+arg_10]
0x180182053  xor     eax, eax
0x180182055  mov     rsi, rdx
0x180182058  test    r8, r8
0x18018205b  mov     [rbp+FileHandle], rax
0x18018205f  xorps   xmm1, xmm1
0x180182062  lea     rdx, [rbp+NtPathName]; NtPathName
0x180182066  cmovnz  rcx, r8; DosPathName
0x18018206a  xor     r9d, r9d; DirectoryInfo
0x18018206d  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180182071  xor     r8d, r8d; NtFileNamePart
0x180182074  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180182078  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18018207c  movups  xmmword ptr [rbp+NtPathName.Length], xmm0
0x180182080  movups  xmmword ptr [rbp+IoStatusBlock], xmm1
0x180182084  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18018208a  test    al, al
0x18018208c  jnz     short loc_1801820A3
0x18018208e  mov     ecx, 3; LastError
0x180182093  call    cs:__imp_RtlSetLastWin32Error
0x180182099  mov     eax, 80070003h
0x18018209e  jmp     loc_1801821A2
0x1801820a3  mov     rdi, [rbp+NtPathName.Buffer]
0x1801820a7  lea     rax, [rbp+NtPathName]
0x1801820ab  xorps   xmm0, xmm0
0x1801820ae  mov     [rsp+80h+OpenOptions], 800021h; OpenOptions
0x1801820b6  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x1801820ba  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1801820be  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1801820c2  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1801820c9  mov     edx, 100000h; DesiredAccess
0x1801820ce  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1801820d6  lea     rcx, [rbp+FileHandle]; FileHandle
0x1801820da  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1801820e1  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1801820e6  mov     [rsp+80h+ShareAccess], 0; ShareAccess
0x1801820ee  call    cs:__imp_NtOpenFile
0x1801820f4  mov     ebx, eax
0x1801820f6  test    eax, eax
0x1801820f8  jns     short loc_180182139
0x1801820fa  mov     ecx, eax
0x1801820fc  call    BaseSetLastNTError
0x180182101  mov     ecx, gs:68h
0x180182109  cmp     ecx, 2
0x18018210c  jnz     short loc_180182119
0x18018210e  mov     ecx, 3; LastError
0x180182113  call    cs:__imp_RtlSetLastWin32Error
0x180182119  mov     rcx, gs:60h
0x180182122  mov     r8, rdi; P
0x180182125  xor     edx, edx; Flags
0x180182127  mov     rcx, [rcx+30h]; HeapHandle
0x18018212b  call    cs:__imp_RtlFreeHeap
0x180182131  bts     ebx, 1Ch
0x180182135  mov     eax, ebx
0x180182137  jmp     short loc_1801821A2
0x180182139  mov     rcx, gs:60h
0x180182142  mov     r8, rdi; P
0x180182145  xor     edx, edx; Flags
0x180182147  mov     rcx, [rcx+30h]; HeapHandle
0x18018214b  call    cs:__imp_RtlFreeHeap
0x180182151  test    rsi, rsi
0x180182154  jnz     short loc_180182168
0x180182156  mov     ecx, 0C000000Dh; LastError
0x18018215b  call    cs:__imp_RtlSetLastWin32Error
0x180182161  mov     eax, 0D000000Dh
0x180182166  jmp     short loc_1801821A2
0x180182168  mov     rcx, [rbp+FileHandle]; FileHandle
0x18018216c  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x180182170  mov     r9d, 60h ; '`'; Length
0x180182176  mov     [rsp+80h+ShareAccess], 0Eh; FsInformationClass
0x18018217e  mov     r8, rsi; FsInformation
0x180182181  call    cs:__imp_NtQueryVolumeInformationFile
0x180182187  mov     rcx, [rbp+FileHandle]; Handle
0x18018218b  mov     ebx, eax
0x18018218d  call    cs:__imp_NtClose
0x180182193  test    ebx, ebx
0x180182195  jns     short loc_1801821A0
0x180182197  mov     ecx, ebx
0x180182199  call    BaseSetLastNTError
0x18018219e  jmp     short loc_180182131
0x1801821a0  xor     eax, eax
0x1801821a2  mov     rbx, [rsp+80h+arg_0]
0x1801821aa  add     rsp, 80h
0x1801821b1  pop     rdi
0x1801821b2  pop     rsi
0x1801821b3  pop     rbp
0x1801821b4  retn
```
