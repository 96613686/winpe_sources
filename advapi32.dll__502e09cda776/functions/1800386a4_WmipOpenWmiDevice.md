# WmipOpenWmiDevice

- ea: `0x1800386a4`
- end: `0x180038842`
- name: `WmipOpenWmiDevice`
- size: `414`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e830`
- `0x180034b14`

## callees

- `0x1800386a4`
- `0x1800720b0`

## import_xrefs

- `ntdll!NtCreateFile` at `0x1800387e2`
- `ntdll!NtCreateFile` at `0x1800387e2`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18003871d`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18003871d`
- `ntdll!RtlReleaseRelativeName` at `0x1800387f4`
- `ntdll!RtlReleaseRelativeName` at `0x1800387f4`
- `ntdll!RtlFreeHeap` at `0x180038812`
- `ntdll!RtlFreeHeap` at `0x180038812`
- `ntdll!RtlInitUnicodeString` at `0x1800386ff`
- `ntdll!RtlInitUnicodeString` at `0x1800386ff`

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
0x1800386a4  mov     [rsp-8+arg_0], rbx
0x1800386a9  mov     [rsp-8+arg_8], rdi
0x1800386ae  push    rbp
0x1800386af  lea     rbp, [rsp-57h]
0x1800386b4  sub     rsp, 0F0h
0x1800386bb  mov     rax, cs:__security_cookie
0x1800386c2  xor     rax, rsp
0x1800386c5  mov     [rbp+57h+var_10], rax
0x1800386c9  xorps   xmm0, xmm0
0x1800386cc  lea     rdx, DosName; "\\\\.\\WMIDataDevice"
0x1800386d3  xor     eax, eax
0x1800386d5  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800386d9  xorps   xmm1, xmm1
0x1800386dc  mov     [rbp+57h+var_20], rax
0x1800386e0  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800386e4  mov     [rbp+57h+var_18], eax
0x1800386e7  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800386eb  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800386ef  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800386f3  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x1800386f7  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm0
0x1800386fb  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm0
0x1800386ff  call    cs:__imp_RtlInitUnicodeString
0x180038706  nop     dword ptr [rax+rax+00h]
0x18003870b  lea     r9, [rbp+57h+RelativeName]; RelativeName
0x18003870f  xor     r8d, r8d; PartName
0x180038712  lea     rdx, [rbp+57h+DestinationString]; NtName
0x180038716  lea     rcx, DosName; "\\\\.\\WMIDataDevice"
0x18003871d  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x180038724  nop     dword ptr [rax+rax+00h]
0x180038729  xor     edx, edx
0x18003872b  test    al, al
0x18003872d  jnz     short loc_180038739
0x18003872f  mov     eax, 0C000003Ah
0x180038734  jmp     loc_180038820
0x180038739  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x18003873d  mov     rdi, [rbp+57h+DestinationString.Buffer]
0x180038741  test    ax, ax
0x180038744  jz      short loc_180038766
0x180038746  mov     [rbp+57h+DestinationString.Length], ax
0x18003874a  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x18003874d  mov     dword ptr [rbp+57h+DestinationString.MaximumLength], eax
0x180038750  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x180038754  mov     word ptr [rbp+57h+DestinationString+6], ax
0x180038758  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x18003875c  mov     [rbp+57h+DestinationString.Buffer], rax
0x180038760  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x180038764  jmp     short loc_18003876D
0x180038766  mov     rax, rdx
0x180038769  mov     [rbp+57h+RelativeName.ContainingDirectory], rdx
0x18003876d  mov     [rsp+0F0h+EaLength], edx; EaLength
0x180038771  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180038775  mov     [rsp+0F0h+EaBuffer], rdx; EaBuffer
0x18003877a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18003877e  mov     ecx, 40h ; '@'
0x180038783  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180038787  mov     [rsp+0F0h+CreateOptions], ecx; CreateOptions
0x18003878b  lea     rax, [rbp+57h+DestinationString]
0x18003878f  mov     [rsp+0F0h+CreateDisposition], 1; CreateDisposition
0x180038797  mov     [rsp+0F0h+ShareAccess], edx; ShareAccess
0x18003879b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18003879f  lea     rax, [rbp+57h+var_20]
0x1800387a3  mov     [rbp+57h+ObjectAttributes.Attributes], ecx
0x1800387a6  lea     rcx, WmipKMHandle; FileHandle
0x1800387ad  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rdx
0x1800387b1  mov     [rsp+0F0h+FileAttributes], 80h; FileAttributes
0x1800387b9  mov     [rsp+0F0h+AllocationSize], rdx; AllocationSize
0x1800387be  mov     edx, 0C0100080h; DesiredAccess
0x1800387c3  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800387ca  mov     word ptr [rbp+57h+var_18], 101h
0x1800387d0  mov     dword ptr [rbp+57h+var_20+4], 2
0x1800387d7  mov     dword ptr [rbp+57h+var_20], 0Ch
0x1800387de  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x1800387e2  call    cs:__imp_NtCreateFile
0x1800387e9  nop     dword ptr [rax+rax+00h]
0x1800387ee  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1800387f2  mov     ebx, eax
0x1800387f4  call    cs:__imp_RtlReleaseRelativeName
0x1800387fb  nop     dword ptr [rax+rax+00h]
0x180038800  mov     rcx, gs:60h
0x180038809  mov     r8, rdi; P
0x18003880c  xor     edx, edx; Flags
0x18003880e  mov     rcx, [rcx+30h]; HeapHandle
0x180038812  call    cs:__imp_RtlFreeHeap
0x180038819  nop     dword ptr [rax+rax+00h]
0x18003881e  mov     eax, ebx
0x180038820  mov     rcx, [rbp+57h+var_10]
0x180038824  xor     rcx, rsp; StackCookie
0x180038827  call    __security_check_cookie
0x18003882c  lea     r11, [rsp+0F0h+var_s0]
0x180038834  mov     rbx, [r11+10h]
0x180038838  mov     rdi, [r11+18h]
0x18003883c  mov     rsp, r11
0x18003883f  pop     rbp
0x180038840  retn
```
