# GetFileSecurityW

- ea: `0x1800c08c0`
- end: `0x1800c0b01`
- name: `GetFileSecurityW`
- size: `577`
- prototype: `BOOL __stdcall(LPCWSTR lpFileName, SECURITY_INFORMATION RequestedInformation, PSECURITY_DESCRIPTOR pSecurityDescriptor, DWORD nLength, LPDWORD lpnLengthNeeded)`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800134a0`
- `0x1800c08c0`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800c0965`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800c0965`
- `ntdll!RtlReleaseRelativeName` at `0x1800c09f1`
- `ntdll!RtlReleaseRelativeName` at `0x1800c09f1`
- `ntdll!NtQuerySecurityObject` at `0x1800c0a30`
- `ntdll!NtQuerySecurityObject` at `0x1800c0a30`
- `ntdll!NtOpenFile` at `0x1800c09da`
- `ntdll!NtOpenFile` at `0x1800c0af4`
- `ntdll!NtOpenFile` at `0x1800c09da`
- `ntdll!NtOpenFile` at `0x1800c0af4`
- `ntdll!NtClose` at `0x1800c0a3c`
- `ntdll!NtClose` at `0x1800c0a3c`
- `ntdll!RtlFreeHeap` at `0x1800c0a09`
- `ntdll!RtlFreeHeap` at `0x1800c0a09`

## pseudocode

```c
BOOL __stdcall GetFileSecurityW(
        LPCWSTR lpFileName,
        SECURITY_INFORMATION RequestedInformation,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        DWORD nLength,
        LPDWORD lpnLengthNeeded)
{
  int v6; // ecx
  ACCESS_MASK v10; // esi
  PWSTR Buffer; // r14
  HANDLE ContainingDirectory; // rax
  NTSTATUS SecurityObject; // edi
  HANDLE FileHandle; // [rsp+30h] [rbp-41h] BYREF
  struct _UNICODE_STRING NtName; // [rsp+38h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+48h] [rbp-29h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+58h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp+7h] BYREF

  FileHandle = 0;
  v6 = 0;
  memset(&ObjectAttributes, 0, 44);
  NtName = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  IoStatusBlock = 0;
  if ( (RequestedInformation & 0x10000) != 0 )
    v6 = 16908288;
  if ( (RequestedInformation & 0x17) != 0 )
    v6 |= 0x20000u;
  if ( (RequestedInformation & 0x20) != 0 )
    v6 |= 0x20000u;
  if ( (RequestedInformation & 0x40) != 0 )
    v6 |= 0x20000u;
  if ( (RequestedInformation & 0x80u) != 0 )
    v6 |= 0x20000u;
  if ( (RequestedInformation & 0x100) != 0 )
    v6 |= 0x20000u;
  v10 = v6 | 0x1000000;
  if ( (RequestedInformation & 8) == 0 )
    v10 = v6;
  if ( RtlDosPathNameToRelativeNtPathName_U(lpFileName, &NtName, 0, &RelativeName) )
  {
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
    SecurityObject = NtOpenFile(&FileHandle, v10, &ObjectAttributes, &IoStatusBlock, 7u, 0x200000u);
    if ( SecurityObject == -1073741811 )
      SecurityObject = NtOpenFile(&FileHandle, v10, &ObjectAttributes, &IoStatusBlock, 7u, 0);
    RtlReleaseRelativeName(&RelativeName);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    if ( SecurityObject < 0
      || (SecurityObject = NtQuerySecurityObject(
                             FileHandle,
                             RequestedInformation,
                             pSecurityDescriptor,
                             nLength,
                             lpnLengthNeeded),
          NtClose(FileHandle),
          SecurityObject < 0) )
    {
      BaseSetLastNTError((unsigned int)SecurityObject);
      return 0;
    }
    else
    {
      return 1;
    }
  }
  else
  {
    BaseSetLastNTError(3221225523LL);
    return 0;
  }
}

```

## disassembly

```asm
0x1800c08c0  mov     [rsp-8+arg_10], rbx
0x1800c08c5  mov     [rsp-8+arg_18], rsi
0x1800c08ca  push    rbp
0x1800c08cb  push    r12
0x1800c08cd  push    r15
0x1800c08cf  lea     rbp, [rsp-3Fh]
0x1800c08d4  sub     rsp, 0B0h
0x1800c08db  xorps   xmm0, xmm0
0x1800c08de  mov     [rbp+4Fh+FileHandle], 0
0x1800c08e6  xorps   xmm1, xmm1
0x1800c08e9  mov     r10, rcx
0x1800c08ec  xor     ecx, ecx
0x1800c08ee  xor     eax, eax
0x1800c08f0  mov     r15d, r9d
0x1800c08f3  mov     r12, r8
0x1800c08f6  mov     ebx, edx
0x1800c08f8  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x1800c08fc  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x1800c0900  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x1800c0904  movups  xmmword ptr [rbp+4Fh+NtName.Length], xmm0
0x1800c0908  movups  xmmword ptr [rbp+4Fh+RelativeName.RelativeName.Length], xmm1
0x1800c090c  movups  xmmword ptr [rbp+4Fh+RelativeName.ContainingDirectory], xmm1
0x1800c0910  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x1800c0914  bt      edx, 10h
0x1800c0918  jb      loc_1800C0A85
0x1800c091e  test    bl, 17h
0x1800c0921  jz      short loc_1800C0927
0x1800c0923  bts     ecx, 11h
0x1800c0927  test    bl, 20h
0x1800c092a  jnz     loc_1800C0A8F
0x1800c0930  test    bl, 40h
0x1800c0933  jnz     loc_1800C0A98
0x1800c0939  test    bl, bl
0x1800c093b  js      loc_1800C0AA1
0x1800c0941  bt      ebx, 8
0x1800c0945  jb      loc_1800C0AAA
0x1800c094b  mov     esi, ecx
0x1800c094d  lea     r9, [rbp+4Fh+RelativeName]; RelativeName
0x1800c0951  bts     esi, 18h
0x1800c0955  lea     rdx, [rbp+4Fh+NtName]; NtName
0x1800c0959  test    bl, 8
0x1800c095c  cmovz   esi, ecx
0x1800c095f  xor     r8d, r8d; PartName
0x1800c0962  mov     rcx, r10; DosName
0x1800c0965  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x1800c096b  test    al, al
0x1800c096d  jz      loc_1800C0A77
0x1800c0973  movzx   eax, [rbp+4Fh+RelativeName.RelativeName.Length]
0x1800c0977  mov     [rsp+0C0h+arg_0], rdi
0x1800c097f  mov     [rsp+0C0h+arg_8], r14
0x1800c0987  mov     r14, [rbp+4Fh+NtName.Buffer]
0x1800c098b  test    ax, ax
0x1800c098e  jnz     loc_1800C0AB3
0x1800c0994  xor     eax, eax
0x1800c0996  mov     [rbp+4Fh+RelativeName.ContainingDirectory], rax
0x1800c099a  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rax
0x1800c099e  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x1800c09a2  lea     rax, [rbp+4Fh+NtName]
0x1800c09a6  mov     [rsp+0C0h+OpenOptions], 200000h; OpenOptions
0x1800c09ae  xorps   xmm0, xmm0
0x1800c09b1  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x1800c09b5  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1800c09b9  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1800c09c0  mov     edx, esi; DesiredAccess
0x1800c09c2  mov     [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x1800c09c9  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1800c09cd  mov     [rsp+0C0h+ShareAccess], 7; ShareAccess
0x1800c09d5  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1800c09da  call    cs:__imp_NtOpenFile
0x1800c09e0  mov     edi, eax
0x1800c09e2  cmp     eax, 0C000000Dh
0x1800c09e7  jz      loc_1800C0AD6
0x1800c09ed  lea     rcx, [rbp+4Fh+RelativeName]; RelativeName
0x1800c09f1  call    cs:__imp_RtlReleaseRelativeName
0x1800c09f7  mov     rcx, gs:60h
0x1800c0a00  mov     r8, r14; P
0x1800c0a03  xor     edx, edx; Flags
0x1800c0a05  mov     rcx, [rcx+30h]; HeapHandle
0x1800c0a09  call    cs:__imp_RtlFreeHeap
0x1800c0a0f  mov     r14, [rsp+0C0h+arg_8]
0x1800c0a17  test    edi, edi
0x1800c0a19  js      short loc_1800C0A6C
0x1800c0a1b  mov     rax, [rbp+4Fh+lpnLengthNeeded]
0x1800c0a1f  mov     r9d, r15d; Length
0x1800c0a22  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x1800c0a26  mov     r8, r12; SecurityDescriptor
0x1800c0a29  mov     edx, ebx; SecurityInformation
0x1800c0a2b  mov     qword ptr [rsp+0C0h+ShareAccess], rax; LengthNeeded
0x1800c0a30  call    cs:__imp_NtQuerySecurityObject
0x1800c0a36  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x1800c0a3a  mov     edi, eax
0x1800c0a3c  call    cs:__imp_NtClose
0x1800c0a42  test    edi, edi
0x1800c0a44  js      short loc_1800C0A6C
0x1800c0a46  mov     eax, 1
0x1800c0a4b  mov     rdi, [rsp+0C0h+arg_0]
0x1800c0a53  lea     r11, [rsp+0C0h+var_10]
0x1800c0a5b  mov     rbx, [r11+30h]
0x1800c0a5f  mov     rsi, [r11+38h]
0x1800c0a63  mov     rsp, r11
0x1800c0a66  pop     r15
0x1800c0a68  pop     r12
0x1800c0a6a  pop     rbp
0x1800c0a6b  retn
0x1800c0a6c  mov     ecx, edi
0x1800c0a6e  call    BaseSetLastNTError
0x1800c0a73  xor     eax, eax
0x1800c0a75  jmp     short loc_1800C0A4B
0x1800c0a77  mov     ecx, 0C0000033h
0x1800c0a7c  call    BaseSetLastNTError
0x1800c0a81  xor     eax, eax
0x1800c0a83  jmp     short loc_1800C0A53
0x1800c0a85  mov     ecx, 1020000h
0x1800c0a8a  jmp     loc_1800C091E
0x1800c0a8f  bts     ecx, 11h
0x1800c0a93  jmp     loc_1800C0930
0x1800c0a98  bts     ecx, 11h
0x1800c0a9c  jmp     loc_1800C0939
0x1800c0aa1  bts     ecx, 11h
0x1800c0aa5  jmp     loc_1800C0941
0x1800c0aaa  bts     ecx, 11h
0x1800c0aae  jmp     loc_1800C094B
0x1800c0ab3  mov     [rbp+4Fh+NtName.Length], ax
0x1800c0ab7  mov     eax, dword ptr [rbp+4Fh+RelativeName.RelativeName.MaximumLength]
0x1800c0aba  mov     dword ptr [rbp+4Fh+NtName.MaximumLength], eax
0x1800c0abd  movzx   eax, word ptr [rbp+4Fh+RelativeName.RelativeName+6]
0x1800c0ac1  mov     word ptr [rbp+4Fh+NtName+6], ax
0x1800c0ac5  mov     rax, [rbp+4Fh+RelativeName.RelativeName.Buffer]
0x1800c0ac9  mov     [rbp+4Fh+NtName.Buffer], rax
0x1800c0acd  mov     rax, [rbp+4Fh+RelativeName.ContainingDirectory]
0x1800c0ad1  jmp     loc_1800C099A
0x1800c0ad6  mov     [rsp+0C0h+OpenOptions], 0; OpenOptions
0x1800c0ade  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x1800c0ae2  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1800c0ae6  mov     [rsp+0C0h+ShareAccess], 7; ShareAccess
0x1800c0aee  mov     edx, esi; DesiredAccess
0x1800c0af0  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1800c0af4  call    cs:__imp_NtOpenFile
0x1800c0afa  mov     edi, eax
0x1800c0afc  jmp     loc_1800C09ED
```
