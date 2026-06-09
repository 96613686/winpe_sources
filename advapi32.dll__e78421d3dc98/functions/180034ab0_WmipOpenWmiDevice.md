# WmipOpenWmiDevice

- ea: `0x180034ab0`
- end: `0x180034c2f`
- name: `WmipOpenWmiDevice`
- size: `383`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002b4e0`
- `0x180031730`

## callees

- `0x180034ab0`
- `0x180065090`

## import_xrefs

- `ntdll!NtCreateFile` at `0x180034be2`
- `ntdll!NtCreateFile` at `0x180034be2`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180034b23`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180034b23`
- `ntdll!RtlReleaseRelativeName` at `0x180034bee`
- `ntdll!RtlReleaseRelativeName` at `0x180034bee`
- `ntdll!RtlFreeHeap` at `0x180034c06`
- `ntdll!RtlFreeHeap` at `0x180034c06`
- `ntdll!RtlInitUnicodeString` at `0x180034b0b`
- `ntdll!RtlInitUnicodeString` at `0x180034b0b`

## pseudocode

```c
__int64 WmipOpenWmiDevice()
{
  PWSTR Buffer; // rdi
  HANDLE ContainingDirectory; // rax
  unsigned int v3; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-39h] BYREF
  _RTL_RELATIVE_NAME_U RelativeName; // [rsp+70h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp+27h] BYREF
  __int64 v8; // [rsp+D0h] [rbp+37h] BYREF
  int v9; // [rsp+D8h] [rbp+3Fh]

  v8 = 0;
  v9 = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  RtlInitUnicodeString(&DestinationString, L"\\\\.\\WMIDataDevice");
  if ( !RtlDosPathNameToRelativeNtPathName_U(L"\\\\.\\WMIDataDevice", &DestinationString, 0, &RelativeName) )
    return 3221225530LL;
  Buffer = DestinationString.Buffer;
  if ( RelativeName.RelativeName.Length )
  {
    DestinationString = RelativeName.RelativeName;
    ContainingDirectory = RelativeName.ContainingDirectory;
  }
  else
  {
    ContainingDirectory = 0;
    RelativeName.ContainingDirectory = 0;
  }
  ObjectAttributes.RootDirectory = ContainingDirectory;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.Length = 48;
  LOWORD(v9) = 257;
  v8 = 0x20000000CLL;
  ObjectAttributes.SecurityQualityOfService = &v8;
  v3 = NtCreateFile(&WmipKMHandle, 0xC0100080, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 0, 1u, 0x40u, 0, 0);
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  return v3;
}

```

## disassembly

```asm
0x180034ab0  mov     [rsp-8+arg_0], rbx
0x180034ab5  mov     [rsp-8+arg_8], rdi
0x180034aba  push    rbp
0x180034abb  lea     rbp, [rsp-57h]
0x180034ac0  sub     rsp, 0F0h
0x180034ac7  mov     rax, cs:__security_cookie
0x180034ace  xor     rax, rsp
0x180034ad1  mov     [rbp+57h+var_10], rax
0x180034ad5  xorps   xmm0, xmm0
0x180034ad8  lea     rdx, DosName; "\\\\.\\WMIDataDevice"
0x180034adf  xor     eax, eax
0x180034ae1  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180034ae5  xorps   xmm1, xmm1
0x180034ae8  mov     [rbp+57h+var_20], rax
0x180034aec  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180034af0  mov     [rbp+57h+var_18], eax
0x180034af3  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180034af7  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180034afb  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180034aff  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x180034b03  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm0
0x180034b07  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm0
0x180034b0b  call    cs:__imp_RtlInitUnicodeString
0x180034b11  lea     r9, [rbp+57h+RelativeName]; RelativeName
0x180034b15  xor     r8d, r8d; PartName
0x180034b18  lea     rdx, [rbp+57h+DestinationString]; NtName
0x180034b1c  lea     rcx, DosName; "\\\\.\\WMIDataDevice"
0x180034b23  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x180034b29  xor     edx, edx
0x180034b2b  test    al, al
0x180034b2d  jnz     short loc_180034B39
0x180034b2f  mov     eax, 0C000003Ah
0x180034b34  jmp     loc_180034C0E
0x180034b39  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x180034b3d  mov     rdi, [rbp+57h+DestinationString.Buffer]
0x180034b41  test    ax, ax
0x180034b44  jz      short loc_180034B66
0x180034b46  mov     [rbp+57h+DestinationString.Length], ax
0x180034b4a  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x180034b4d  mov     dword ptr [rbp+57h+DestinationString.MaximumLength], eax
0x180034b50  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x180034b54  mov     word ptr [rbp+57h+DestinationString+6], ax
0x180034b58  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x180034b5c  mov     [rbp+57h+DestinationString.Buffer], rax
0x180034b60  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x180034b64  jmp     short loc_180034B6D
0x180034b66  mov     rax, rdx
0x180034b69  mov     [rbp+57h+RelativeName.ContainingDirectory], rdx
0x180034b6d  mov     [rsp+0F0h+EaLength], edx; EaLength
0x180034b71  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180034b75  mov     [rsp+0F0h+EaBuffer], rdx; EaBuffer
0x180034b7a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180034b7e  mov     ecx, 40h ; '@'
0x180034b83  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180034b87  mov     [rsp+0F0h+CreateOptions], ecx; CreateOptions
0x180034b8b  lea     rax, [rbp+57h+DestinationString]
0x180034b8f  mov     [rsp+0F0h+CreateDisposition], 1; CreateDisposition
0x180034b97  mov     [rsp+0F0h+ShareAccess], edx; ShareAccess
0x180034b9b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180034b9f  lea     rax, [rbp+57h+var_20]
0x180034ba3  mov     [rbp+57h+ObjectAttributes.Attributes], ecx
0x180034ba6  lea     rcx, WmipKMHandle; FileHandle
0x180034bad  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rdx
0x180034bb1  mov     [rsp+0F0h+FileAttributes], 80h; FileAttributes
0x180034bb9  mov     [rsp+0F0h+AllocationSize], rdx; AllocationSize
0x180034bbe  mov     edx, 0C0100080h; DesiredAccess
0x180034bc3  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180034bca  mov     word ptr [rbp+57h+var_18], 101h
0x180034bd0  mov     dword ptr [rbp+57h+var_20+4], 2
0x180034bd7  mov     dword ptr [rbp+57h+var_20], 0Ch
0x180034bde  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x180034be2  call    cs:__imp_NtCreateFile
0x180034be8  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x180034bec  mov     ebx, eax
0x180034bee  call    cs:__imp_RtlReleaseRelativeName
0x180034bf4  mov     rcx, gs:60h
0x180034bfd  mov     r8, rdi; P
0x180034c00  xor     edx, edx; Flags
0x180034c02  mov     rcx, [rcx+30h]; HeapHandle
0x180034c06  call    cs:__imp_RtlFreeHeap
0x180034c0c  mov     eax, ebx
0x180034c0e  mov     rcx, [rbp+57h+var_10]
0x180034c12  xor     rcx, rsp; StackCookie
0x180034c15  call    __security_check_cookie
0x180034c1a  lea     r11, [rsp+0F0h+var_s0]
0x180034c22  mov     rbx, [r11+10h]
0x180034c26  mov     rdi, [r11+18h]
0x180034c2a  mov     rsp, r11
0x180034c2d  pop     rbp
0x180034c2e  retn
```
