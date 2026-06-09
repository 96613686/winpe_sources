# BaseRegSaveKeyExInternal

- ea: `0x180104a28`
- end: `0x180104c16`
- name: `BaseRegSaveKeyExInternal`
- size: `494`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801048b0`
- `0x180140840`

## callees

- `0x180104a28`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180104ab8`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180104ab8`
- `ntdll!RtlReleaseRelativeName` at `0x180104b67`
- `ntdll!RtlReleaseRelativeName` at `0x180104b67`
- `ntdll!NtCreateFile` at `0x180104b5b`
- `ntdll!NtCreateFile` at `0x180104b5b`
- `ntdll!RtlNtStatusToDosError` at `0x180104b8b`
- `ntdll!RtlNtStatusToDosError` at `0x180104b8b`
- `ntdll!NtClose` at `0x180104ba4`
- `ntdll!NtClose` at `0x180104ba4`
- `ntdll!RtlFreeHeap` at `0x180104b7f`
- `ntdll!RtlFreeHeap` at `0x180104b7f`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180104bd3`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180104bd3`
- `ntdll!NtSaveKeyEx` at `0x180104bb6`
- `ntdll!NtSaveKeyEx` at `0x180104bb6`

## pseudocode

```c
ULONG __fastcall BaseRegSaveKeyExInternal(HANDLE KeyHandle, __int16 *a2, __int64 a3, ULONG a4)
{
  __int16 v8; // ax
  PWSTR Buffer; // r14
  HANDLE ContainingDirectory; // rax
  int v12; // ebx
  void *v13; // rcx
  struct _UNICODE_STRING NtName; // [rsp+60h] [rbp-59h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-49h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+80h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-19h] BYREF
  HANDLE FileHandle; // [rsp+120h] [rbp+67h] BYREF

  FileHandle = 0;
  NtName = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( !KeyHandle )
    return 87;
  if ( !a2 )
    return 87;
  if ( !*((_QWORD *)a2 + 1) )
    return 87;
  v8 = *a2;
  if ( (*a2 & 1) != 0 )
    return 87;
  if ( v8 )
    *a2 = v8 - 2;
  if ( a3 )
  {
    v13 = *(void **)(a3 + 8);
    if ( !v13 || !RtlValidRelativeSecurityDescriptor(v13, *(_DWORD *)(a3 + 16), 0) )
      return 87;
  }
  if ( !RtlDosPathNameToRelativeNtPathName_U(*((PCWSTR *)a2 + 1), &NtName, 0, &RelativeName) )
    return 87;
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
  if ( a3 )
    ObjectAttributes.SecurityDescriptor = *(PVOID *)(a3 + 8);
  else
    ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.SecurityQualityOfService = 0;
  v12 = NtCreateFile(&FileHandle, 0x40100000u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 2u, 0x4020u, 0, 0);
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( v12 >= 0 )
  {
    if ( ((unsigned __int8)KeyHandle & 2) != 0 )
      v12 = -1073741811;
    else
      v12 = NtSaveKeyEx(KeyHandle, FileHandle, a4);
    NtClose(FileHandle);
  }
  return RtlNtStatusToDosError(v12);
}

```

## disassembly

```asm
0x180104a28  push    rbp
0x180104a2a  push    rbx
0x180104a2b  push    rsi
0x180104a2c  push    rdi
0x180104a2d  push    r12
0x180104a2f  push    r13
0x180104a31  push    r14
0x180104a33  push    r15
0x180104a35  lea     rbp, [rsp-1Fh]
0x180104a3a  sub     rsp, 0D8h
0x180104a41  xorps   xmm0, xmm0
0x180104a44  xor     r12d, r12d
0x180104a47  xorps   xmm1, xmm1
0x180104a4a  mov     [rbp+57h+FileHandle], r12
0x180104a4e  xor     eax, eax
0x180104a50  mov     r15d, r9d
0x180104a53  mov     rdi, r8
0x180104a56  mov     rbx, rdx
0x180104a59  mov     rsi, rcx
0x180104a5c  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180104a60  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180104a64  movups  xmmword ptr [rbp+57h+NtName.Length], xmm0
0x180104a68  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm1
0x180104a6c  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm1
0x180104a70  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180104a74  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180104a78  test    rcx, rcx
0x180104a7b  jz      short loc_180104AC2
0x180104a7d  test    rdx, rdx
0x180104a80  jz      short loc_180104AC2
0x180104a82  cmp     [rdx+8], r12
0x180104a86  jz      short loc_180104AC2
0x180104a88  movzx   eax, word ptr [rdx]
0x180104a8b  test    al, 1
0x180104a8d  jnz     short loc_180104AC2
0x180104a8f  lea     r13d, [r12+2]
0x180104a94  test    ax, ax
0x180104a97  jz      short loc_180104AA0
0x180104a99  sub     ax, r13w
0x180104a9d  mov     [rdx], ax
0x180104aa0  test    rdi, rdi
0x180104aa3  jnz     loc_180104BC0
0x180104aa9  mov     rcx, [rbx+8]; DosName
0x180104aad  lea     r9, [rbp+57h+RelativeName]; RelativeName
0x180104ab1  xor     r8d, r8d; PartName
0x180104ab4  lea     rdx, [rbp+57h+NtName]; NtName
0x180104ab8  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x180104abe  test    al, al
0x180104ac0  jnz     short loc_180104ADB
0x180104ac2  mov     eax, 57h ; 'W'
0x180104ac7  add     rsp, 0D8h
0x180104ace  pop     r15
0x180104ad0  pop     r14
0x180104ad2  pop     r13
0x180104ad4  pop     r12
0x180104ad6  pop     rdi
0x180104ad7  pop     rsi
0x180104ad8  pop     rbx
0x180104ad9  pop     rbp
0x180104ada  retn
0x180104adb  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x180104adf  mov     r14, [rbp+57h+NtName.Buffer]
0x180104ae3  test    ax, ax
0x180104ae6  jnz     loc_180104BE6
0x180104aec  mov     rax, r12
0x180104aef  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x180104af3  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180104af7  lea     rax, [rbp+57h+NtName]
0x180104afb  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180104aff  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180104b06  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180104b0d  test    rdi, rdi
0x180104b10  jnz     loc_180104C09
0x180104b16  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], r12
0x180104b1a  mov     [rsp+110h+EaLength], r12d; EaLength
0x180104b1f  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180104b23  mov     [rsp+110h+EaBuffer], r12; EaBuffer
0x180104b28  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180104b2c  mov     [rsp+110h+CreateOptions], 4020h; CreateOptions
0x180104b34  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180104b38  mov     [rsp+110h+CreateDisposition], r13d; CreateDisposition
0x180104b3d  mov     edx, 40100000h; DesiredAccess
0x180104b42  mov     [rsp+110h+ShareAccess], 1; ShareAccess
0x180104b4a  mov     [rsp+110h+FileAttributes], 80h; FileAttributes
0x180104b52  mov     [rsp+110h+AllocationSize], r12; AllocationSize
0x180104b57  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], r12
0x180104b5b  call    cs:__imp_NtCreateFile
0x180104b61  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x180104b65  mov     ebx, eax
0x180104b67  call    cs:__imp_RtlReleaseRelativeName
0x180104b6d  mov     rcx, gs:60h
0x180104b76  mov     r8, r14; P
0x180104b79  xor     edx, edx; Flags
0x180104b7b  mov     rcx, [rcx+30h]; HeapHandle
0x180104b7f  call    cs:__imp_RtlFreeHeap
0x180104b85  test    ebx, ebx
0x180104b87  jns     short loc_180104B96
0x180104b89  mov     ecx, ebx; Status
0x180104b8b  call    cs:__imp_RtlNtStatusToDosError
0x180104b91  jmp     loc_180104AC7
0x180104b96  test    r13b, sil
0x180104b99  jz      short loc_180104BAC
0x180104b9b  mov     ebx, 0C000000Dh
0x180104ba0  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180104ba4  call    cs:__imp_NtClose
0x180104baa  jmp     short loc_180104B89
0x180104bac  mov     rdx, [rbp+57h+FileHandle]; FileHandle
0x180104bb0  mov     r8d, r15d; Flags
0x180104bb3  mov     rcx, rsi; KeyHandle
0x180104bb6  call    cs:__imp_NtSaveKeyEx
0x180104bbc  mov     ebx, eax
0x180104bbe  jmp     short loc_180104BA0
0x180104bc0  mov     rcx, [r8+8]; SecurityDescriptorInput
0x180104bc4  test    rcx, rcx
0x180104bc7  jz      loc_180104AC2
0x180104bcd  mov     edx, [rdi+10h]; SecurityDescriptorLength
0x180104bd0  xor     r8d, r8d; RequiredInformation
0x180104bd3  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x180104bd9  test    al, al
0x180104bdb  jz      loc_180104AC2
0x180104be1  jmp     loc_180104AA9
0x180104be6  mov     [rbp+57h+NtName.Length], ax
0x180104bea  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x180104bed  mov     dword ptr [rbp+57h+NtName.MaximumLength], eax
0x180104bf0  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x180104bf4  mov     word ptr [rbp+57h+NtName+6], ax
0x180104bf8  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x180104bfc  mov     [rbp+57h+NtName.Buffer], rax
0x180104c00  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x180104c04  jmp     loc_180104AF3
0x180104c09  mov     rax, [rdi+8]
0x180104c0d  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x180104c11  jmp     loc_180104B1A
```
