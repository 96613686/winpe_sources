# FindFirstChangeNotificationW

- ea: `0x1800f31b0`
- end: `0x1800f333e`
- name: `FindFirstChangeNotificationW`
- size: `398`
- prototype: `HANDLE __stdcall(LPCWSTR lpPathName, BOOL bWatchSubtree, DWORD dwNotifyFilter)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1801818f0`

## callees

- `0x1800134a0`
- `0x1800f31b0`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800f3201`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800f3201`
- `ntdll!RtlReleaseRelativeName` at `0x1800f3276`
- `ntdll!RtlReleaseRelativeName` at `0x1800f3276`
- `ntdll!NtOpenFile` at `0x1800f326a`
- `ntdll!NtOpenFile` at `0x1800f326a`
- `ntdll!RtlSetLastWin32Error` at `0x1800f32fd`
- `ntdll!RtlSetLastWin32Error` at `0x1800f32fd`
- `ntdll!NtClose` at `0x1800f3333`
- `ntdll!NtClose` at `0x1800f3333`
- `ntdll!RtlFreeHeap` at `0x1800f328e`
- `ntdll!RtlFreeHeap` at `0x1800f328e`
- `ntdll!NtNotifyChangeDirectoryFile` at `0x1800f32e8`
- `ntdll!NtNotifyChangeDirectoryFile` at `0x1800f32e8`

## pseudocode

```c
HANDLE __stdcall FindFirstChangeNotificationW(LPCWSTR lpPathName, BOOL bWatchSubtree, DWORD dwNotifyFilter)
{
  BOOLEAN WatchTree; // r14
  PWSTR Buffer; // rdi
  HANDLE ContainingDirectory; // rax
  NTSTATUS v7; // ebx
  NTSTATUS v9; // eax
  struct _UNICODE_STRING NtName; // [rsp+50h] [rbp-49h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-39h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+70h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-9h] BYREF
  HANDLE FileHandle; // [rsp+118h] [rbp+7Fh] BYREF

  WatchTree = bWatchSubtree;
  FileHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  NtName = 0;
  IoStatusBlock = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  if ( !RtlDosPathNameToRelativeNtPathName_U(lpPathName, &NtName, 0, &RelativeName) )
  {
    RtlSetLastWin32Error(3u);
    return (HANDLE)-1LL;
  }
  Buffer = NtName.Buffer;
  if ( RelativeName.RelativeName.Length )
  {
    NtName = RelativeName.RelativeName;
    ContainingDirectory = RelativeName.ContainingDirectory;
  }
  else
  {
    ContainingDirectory = 0;
    RelativeName.ContainingDirectory = 0;
  }
  ObjectAttributes.RootDirectory = ContainingDirectory;
  ObjectAttributes.ObjectName = &NtName;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = NtOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4001u);
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( v7 < 0 )
  {
    BaseSetLastNTError((unsigned int)v7);
    return (HANDLE)-1LL;
  }
  v9 = NtNotifyChangeDirectoryFile(
         FileHandle,
         0,
         0,
         0,
         &staticIoStatusBlock,
         staticchangebuff,
         0x20u,
         dwNotifyFilter,
         WatchTree);
  if ( v9 < 0 )
  {
    BaseSetLastNTError((unsigned int)v9);
    NtClose(FileHandle);
    return (HANDLE)-1LL;
  }
  return FileHandle;
}

```

## disassembly

```asm
0x1800f31b0  push    rbp
0x1800f31b2  push    rbx
0x1800f31b3  push    rsi
0x1800f31b4  push    rdi
0x1800f31b5  push    r14
0x1800f31b7  push    r15
0x1800f31b9  lea     rbp, [rsp-2Fh]
0x1800f31be  sub     rsp, 0C8h
0x1800f31c5  xorps   xmm0, xmm0
0x1800f31c8  lea     r9, [rbp+57h+RelativeName]; RelativeName
0x1800f31cc  mov     esi, r8d
0x1800f31cf  mov     r14d, edx
0x1800f31d2  xorps   xmm1, xmm1
0x1800f31d5  lea     rdx, [rbp+57h+NtName]; NtName
0x1800f31d9  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800f31dd  xor     r15d, r15d
0x1800f31e0  xor     eax, eax
0x1800f31e2  xor     r8d, r8d; PartName
0x1800f31e5  mov     [rbp+57h+FileHandle], r15
0x1800f31e9  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800f31ed  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800f31f1  movups  xmmword ptr [rbp+57h+NtName.Length], xmm0
0x1800f31f5  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x1800f31f9  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm0
0x1800f31fd  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm0
0x1800f3201  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x1800f3207  test    al, al
0x1800f3209  jz      loc_1800F32F8
0x1800f320f  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x1800f3213  mov     rdi, [rbp+57h+NtName.Buffer]
0x1800f3217  test    ax, ax
0x1800f321a  jnz     loc_1800F3305
0x1800f3220  mov     eax, r15d
0x1800f3223  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x1800f3227  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800f322b  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800f322f  lea     rax, [rbp+57h+NtName]
0x1800f3233  mov     [rsp+0F0h+OpenOptions], 4001h; OpenOptions
0x1800f323b  xorps   xmm0, xmm0
0x1800f323e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800f3242  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800f3246  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800f324d  mov     edx, 100001h; DesiredAccess
0x1800f3252  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800f3259  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800f325d  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x1800f3265  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800f326a  call    cs:__imp_NtOpenFile
0x1800f3270  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1800f3274  mov     ebx, eax
0x1800f3276  call    cs:__imp_RtlReleaseRelativeName
0x1800f327c  mov     rcx, gs:60h
0x1800f3285  mov     r8, rdi; P
0x1800f3288  xor     edx, edx; Flags
0x1800f328a  mov     rcx, [rcx+30h]; HeapHandle
0x1800f328e  call    cs:__imp_RtlFreeHeap
0x1800f3294  test    ebx, ebx
0x1800f3296  jns     short loc_1800F32B3
0x1800f3298  mov     ecx, ebx
0x1800f329a  call    BaseSetLastNTError
0x1800f329f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f32a3  add     rsp, 0C8h
0x1800f32aa  pop     r15
0x1800f32ac  pop     r14
0x1800f32ae  pop     rdi
0x1800f32af  pop     rsi
0x1800f32b0  pop     rbx
0x1800f32b1  pop     rbp
0x1800f32b2  retn
0x1800f32b3  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800f32b7  lea     rax, staticchangebuff
0x1800f32be  mov     [rsp+0F0h+WatchTree], r14b; WatchTree
0x1800f32c3  xor     r9d, r9d; ApcContext
0x1800f32c6  mov     [rsp+0F0h+CompletionFilter], esi; CompletionFilter
0x1800f32ca  xor     r8d, r8d; ApcRoutine
0x1800f32cd  mov     [rsp+0F0h+BufferSize], 20h ; ' '; BufferSize
0x1800f32d5  xor     edx, edx; Event
0x1800f32d7  mov     qword ptr [rsp+0F0h+OpenOptions], rax; Buffer
0x1800f32dc  lea     rax, staticIoStatusBlock
0x1800f32e3  mov     qword ptr [rsp+0F0h+ShareAccess], rax; IoStatusBlock
0x1800f32e8  call    cs:__imp_NtNotifyChangeDirectoryFile
0x1800f32ee  test    eax, eax
0x1800f32f0  js      short loc_1800F3328
0x1800f32f2  mov     rax, [rbp+57h+FileHandle]
0x1800f32f6  jmp     short loc_1800F32A3
0x1800f32f8  mov     ecx, 3; LastError
0x1800f32fd  call    cs:__imp_RtlSetLastWin32Error
0x1800f3303  jmp     short loc_1800F329F
0x1800f3305  mov     [rbp+57h+NtName.Length], ax
0x1800f3309  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x1800f330c  mov     dword ptr [rbp+57h+NtName.MaximumLength], eax
0x1800f330f  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x1800f3313  mov     word ptr [rbp+57h+NtName+6], ax
0x1800f3317  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x1800f331b  mov     [rbp+57h+NtName.Buffer], rax
0x1800f331f  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x1800f3323  jmp     loc_1800F3227
0x1800f3328  mov     ecx, eax
0x1800f332a  call    BaseSetLastNTError
0x1800f332f  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800f3333  call    cs:__imp_NtClose
0x1800f3339  jmp     loc_1800F329F
```
