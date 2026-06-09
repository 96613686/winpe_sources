# IsFileOwnedByTrustedInstaller

- ea: `0x1800eda38`
- end: `0x1800edc45`
- name: `IsFileOwnedByTrustedInstaller`
- size: `525`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800a5180`

## callees

- `0x180020880`
- `0x1800220f0`
- `0x1800eda38`
- `0x1800edc4c`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800edaaa`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800edaaa`
- `ntdll!RtlReleaseRelativeName` at `0x1800edb25`
- `ntdll!RtlReleaseRelativeName` at `0x1800edb25`
- `ntdll!NtQueryInformationFile` at `0x1800edb64`
- `ntdll!NtQueryInformationFile` at `0x1800edb64`
- `ntdll!NtQuerySecurityObject` at `0x1800edb88`
- `ntdll!NtQuerySecurityObject` at `0x1800edbc0`
- `ntdll!NtQuerySecurityObject` at `0x1800edb88`
- `ntdll!NtQuerySecurityObject` at `0x1800edbc0`
- `ntdll!NtOpenFile` at `0x1800edb19`
- `ntdll!NtOpenFile` at `0x1800edb19`
- `ntdll!NtClose` at `0x1800edbe1`
- `ntdll!NtClose` at `0x1800edbe1`
- `ntdll!RtlFreeHeap` at `0x1800edb3d`
- `ntdll!RtlFreeHeap` at `0x1800edb3d`

## pseudocode

```c
__int64 __fastcall IsFileOwnedByTrustedInstaller(const WCHAR *a1)
{
  unsigned int v1; // esi
  PWSTR Buffer; // r14
  HLOCAL v3; // rdi
  HANDLE ContainingDirectory; // rax
  NTSTATUS v5; // ebx
  ULONG LengthNeeded; // [rsp+30h] [rbp-79h] BYREF
  HANDLE FileHandle; // [rsp+38h] [rbp-71h] BYREF
  struct _UNICODE_STRING NtName; // [rsp+40h] [rbp-69h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+50h] [rbp-59h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-9h] BYREF
  _OWORD FileInformation[2]; // [rsp+B0h] [rbp+7h] BYREF
  __int64 v14; // [rsp+D0h] [rbp+27h]

  FileHandle = 0;
  v14 = 0;
  memset(&ObjectAttributes, 0, 44);
  LengthNeeded = 0;
  NtName = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  IoStatusBlock = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  if ( !RtlDosPathNameToRelativeNtPathName_U(a1, &NtName, 0, &RelativeName) )
    return 0;
  v1 = 0;
  Buffer = NtName.Buffer;
  v3 = 0;
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
  v5 = NtOpenFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 1u, 0);
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( v5 >= 0
    && NtQueryInformationFile(FileHandle, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation) >= 0
    && (NtQuerySecurityObject(FileHandle, 7u, 0, 0, &LengthNeeded) >= 0
     || LengthNeeded
     && (v3 = LocalAlloc(0, LengthNeeded)) != 0
     && NtQuerySecurityObject(FileHandle, 7u, v3, LengthNeeded, &LengthNeeded) >= 0) )
  {
    if ( (unsigned int)IsTIFileDescriptor(v3) )
      v1 = 1;
  }
  if ( FileHandle )
    NtClose(FileHandle);
  if ( v3 )
    LocalFree(v3);
  return v1;
}

```

## disassembly

```asm
0x1800eda38  mov     [rsp-8+arg_8], rbx
0x1800eda3d  mov     [rsp-8+arg_10], rsi
0x1800eda42  push    rbp
0x1800eda43  push    rdi
0x1800eda44  push    r12
0x1800eda46  push    r14
0x1800eda48  push    r15
0x1800eda4a  lea     rbp, [rsp-37h]
0x1800eda4f  sub     rsp, 0E0h
0x1800eda56  mov     rax, cs:__security_cookie
0x1800eda5d  xor     rax, rsp
0x1800eda60  mov     [rbp+57h+var_28], rax
0x1800eda64  xorps   xmm0, xmm0
0x1800eda67  lea     r9, [rbp+57h+RelativeName]; RelativeName
0x1800eda6b  xorps   xmm1, xmm1
0x1800eda6e  lea     rdx, [rbp+57h+NtName]; NtName
0x1800eda72  xor     r15d, r15d
0x1800eda75  xor     eax, eax
0x1800eda77  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800eda7b  xor     r8d, r8d; PartName
0x1800eda7e  mov     [rbp+57h+FileHandle], r15
0x1800eda82  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800eda86  mov     [rbp+57h+var_30], rax
0x1800eda8a  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800eda8e  mov     [rbp+57h+LengthNeeded], r15d
0x1800eda92  movups  xmmword ptr [rbp+57h+NtName.Length], xmm0
0x1800eda96  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm1
0x1800eda9a  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm1
0x1800eda9e  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800edaa2  movups  [rbp+57h+FileInformation], xmm1
0x1800edaa6  movups  [rbp+57h+var_40], xmm1
0x1800edaaa  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x1800edab0  test    al, al
0x1800edab2  jz      loc_1800EDC41
0x1800edab8  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x1800edabc  mov     esi, r15d
0x1800edabf  mov     r14, [rbp+57h+NtName.Buffer]
0x1800edac3  mov     edi, r15d
0x1800edac6  test    ax, ax
0x1800edac9  jnz     loc_1800EDC1E
0x1800edacf  mov     eax, r15d
0x1800edad2  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x1800edad6  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800edada  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800edade  lea     rax, [rbp+57h+NtName]
0x1800edae2  mov     [rsp+100h+OpenOptions], r15d; OpenOptions
0x1800edae7  xorps   xmm0, xmm0
0x1800edaea  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800edaee  mov     r12d, 1
0x1800edaf4  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800edafb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800edaff  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800edb06  mov     edx, 120089h; DesiredAccess
0x1800edb0b  mov     [rsp+100h+ShareAccess], r12d; ShareAccess
0x1800edb10  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800edb14  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800edb19  call    cs:__imp_NtOpenFile
0x1800edb1f  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1800edb23  mov     ebx, eax
0x1800edb25  call    cs:__imp_RtlReleaseRelativeName
0x1800edb2b  mov     rcx, gs:60h
0x1800edb34  mov     r8, r14; P
0x1800edb37  xor     edx, edx; Flags
0x1800edb39  mov     rcx, [rcx+30h]; HeapHandle
0x1800edb3d  call    cs:__imp_RtlFreeHeap
0x1800edb43  test    ebx, ebx
0x1800edb45  js      loc_1800EDBD8
0x1800edb4b  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800edb4f  lea     r9d, [r12+27h]; Length
0x1800edb54  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x1800edb58  mov     [rsp+100h+ShareAccess], 4; FileInformationClass
0x1800edb60  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800edb64  call    cs:__imp_NtQueryInformationFile
0x1800edb6a  test    eax, eax
0x1800edb6c  js      short loc_1800EDBD8
0x1800edb6e  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800edb72  lea     rax, [rbp+57h+LengthNeeded]
0x1800edb76  lea     ebx, [r12+6]
0x1800edb7b  mov     qword ptr [rsp+100h+ShareAccess], rax; LengthNeeded
0x1800edb80  mov     edx, ebx; SecurityInformation
0x1800edb82  xor     r9d, r9d; Length
0x1800edb85  xor     r8d, r8d; SecurityDescriptor
0x1800edb88  call    cs:__imp_NtQuerySecurityObject
0x1800edb8e  test    eax, eax
0x1800edb90  jns     short loc_1800EDBCA
0x1800edb92  mov     eax, [rbp+57h+LengthNeeded]
0x1800edb95  test    eax, eax
0x1800edb97  jz      short loc_1800EDBD8
0x1800edb99  mov     edx, eax; uBytes
0x1800edb9b  xor     ecx, ecx; uFlags
0x1800edb9d  call    LocalAlloc
0x1800edba2  mov     rdi, rax
0x1800edba5  test    rax, rax
0x1800edba8  jz      short loc_1800EDBD8
0x1800edbaa  mov     r9d, [rbp+57h+LengthNeeded]; Length
0x1800edbae  lea     rax, [rbp+57h+LengthNeeded]
0x1800edbb2  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800edbb6  mov     r8, rdi; SecurityDescriptor
0x1800edbb9  mov     edx, ebx; SecurityInformation
0x1800edbbb  mov     qword ptr [rsp+100h+ShareAccess], rax; LengthNeeded
0x1800edbc0  call    cs:__imp_NtQuerySecurityObject
0x1800edbc6  test    eax, eax
0x1800edbc8  js      short loc_1800EDBD8
0x1800edbca  mov     rcx, rdi; SecurityDescriptor
0x1800edbcd  call    IsTIFileDescriptor
0x1800edbd2  test    eax, eax
0x1800edbd4  cmovnz  esi, r12d
0x1800edbd8  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800edbdc  test    rcx, rcx
0x1800edbdf  jz      short loc_1800EDBE7
0x1800edbe1  call    cs:__imp_NtClose
0x1800edbe7  test    rdi, rdi
0x1800edbea  jz      short loc_1800EDBF4
0x1800edbec  mov     rcx, rdi; hMem
0x1800edbef  call    LocalFree
0x1800edbf4  mov     eax, esi
0x1800edbf6  mov     rcx, [rbp+57h+var_28]
0x1800edbfa  xor     rcx, rsp; StackCookie
0x1800edbfd  call    __security_check_cookie
0x1800edc02  lea     r11, [rsp+100h+var_20]
0x1800edc0a  mov     rbx, [r11+38h]
0x1800edc0e  mov     rsi, [r11+40h]
0x1800edc12  mov     rsp, r11
0x1800edc15  pop     r15
0x1800edc17  pop     r14
0x1800edc19  pop     r12
0x1800edc1b  pop     rdi
0x1800edc1c  pop     rbp
0x1800edc1d  retn
0x1800edc1e  mov     [rbp+57h+NtName.Length], ax
0x1800edc22  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x1800edc25  mov     dword ptr [rbp+57h+NtName.MaximumLength], eax
0x1800edc28  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x1800edc2c  mov     word ptr [rbp+57h+NtName+6], ax
0x1800edc30  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x1800edc34  mov     [rbp+57h+NtName.Buffer], rax
0x1800edc38  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x1800edc3c  jmp     loc_1800EDAD6
0x1800edc41  xor     eax, eax
0x1800edc43  jmp     short loc_1800EDBF6
```
