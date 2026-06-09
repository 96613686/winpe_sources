# AslDoesDirectoryExistNtPath

- ea: `0x14003bf8c`
- end: `0x14003c0c2`
- name: `AslDoesDirectoryExistNtPath`
- size: `310`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140030dc0`

## callees

- `0x14003bf18`
- `0x14003bf8c`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x14003bfd2`
- `msvcrt!_wcsnicmp` at `0x14003bfd2`
- `ntdll!RtlInitUnicodeString` at `0x14003c021`
- `ntdll!RtlInitUnicodeString` at `0x14003c021`
- `ntdll!RtlFreeUnicodeString` at `0x14003c0a5`
- `ntdll!RtlFreeUnicodeString` at `0x14003c0a5`
- `ntdll!ZwClose` at `0x14003c078`
- `ntdll!ZwClose` at `0x14003c078`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14003bfe9`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14003bfe9`
- `ntdll!ZwOpenFile` at `0x14003c06a`
- `ntdll!ZwOpenFile` at `0x14003c06a`

## string_xrefs

- `0x14003bff7`: `RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]`
- `0x14003c009`: `AslDoesDirectoryExistNtPath`

## pseudocode

```c
__int64 __fastcall AslDoesDirectoryExistNtPath(PCWSTR SourceString)
{
  unsigned int v2; // esi
  int v3; // eax
  NTSTATUS v4; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+90h] [rbp+10h] BYREF

  *(_QWORD *)&DestinationString.Length = 0;
  FileHandle = 0;
  DestinationString.Buffer = 0;
  memset(&ObjectAttributes, 0, 44);
  v2 = 0;
  IoStatusBlock = 0;
  if ( _wcsnicmp(SourceString, L"\\SystemRoot\\", 0xCu) )
  {
    v3 = RtlDosPathNameToNtPathName_U_WithStatus(SourceString, &DestinationString, 0, 0);
    if ( v3 < 0 )
    {
      AslLogCallPrintf(
        1,
        "AslDoesDirectoryExistNtPath",
        554,
        "RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]",
        SourceString,
        v3);
      goto LABEL_10;
    }
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
  }
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = ZwOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 3u, 1u);
  if ( v4 >= 0 )
  {
    ZwClose(FileHandle);
LABEL_9:
    v2 = 1;
    goto LABEL_10;
  }
  if ( v4 == -1073741790 || v4 == -1073741757 )
    goto LABEL_9;
LABEL_10:
  if ( DestinationString.Buffer != SourceString && DestinationString.Buffer )
    RtlFreeUnicodeString(&DestinationString);
  return v2;
}

```

## disassembly

```asm
0x14003bf8c  mov     [rsp-8+arg_8], rsi
0x14003bf91  mov     [rsp-8+arg_10], rdi
0x14003bf96  push    rbp
0x14003bf97  mov     rbp, rsp
0x14003bf9a  sub     rsp, 80h
0x14003bfa1  xor     eax, eax
0x14003bfa3  lea     rdx, aSystemroot_3; "\\SystemRoot\\"
0x14003bfaa  xorps   xmm0, xmm0
0x14003bfad  mov     qword ptr [rbp+DestinationString.Length], rax
0x14003bfb1  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14003bfb5  mov     rdi, rcx
0x14003bfb8  mov     [rbp+FileHandle], rax
0x14003bfbc  lea     r8d, [rax+0Ch]; MaxCount
0x14003bfc0  mov     [rbp+DestinationString.Buffer], rax
0x14003bfc4  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14003bfc8  xor     esi, esi
0x14003bfca  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14003bfce  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x14003bfd2  call    cs:__imp__wcsnicmp
0x14003bfd8  test    eax, eax
0x14003bfda  jz      short loc_14003C01A
0x14003bfdc  xor     r9d, r9d
0x14003bfdf  lea     rdx, [rbp+DestinationString]
0x14003bfe3  xor     r8d, r8d
0x14003bfe6  mov     rcx, rdi
0x14003bfe9  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x14003bfef  test    eax, eax
0x14003bff1  jns     short loc_14003C027
0x14003bff3  mov     [rsp+80h+OpenOptions], eax
0x14003bff7  lea     r9, aRtldospathname_0; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x14003bffe  mov     r8d, 22Ah
0x14003c004  mov     qword ptr [rsp+80h+ShareAccess], rdi
0x14003c009  lea     rdx, aAsldoesdirecto; "AslDoesDirectoryExistNtPath"
0x14003c010  lea     ecx, [rsi+1]
0x14003c013  call    AslLogCallPrintf
0x14003c018  jmp     short loc_14003C093
0x14003c01a  mov     rdx, rdi; SourceString
0x14003c01d  lea     rcx, [rbp+DestinationString]; DestinationString
0x14003c021  call    cs:__imp_RtlInitUnicodeString
0x14003c027  lea     rax, [rbp+DestinationString]
0x14003c02b  mov     [rsp+80h+OpenOptions], 1; OpenOptions
0x14003c033  xorps   xmm0, xmm0
0x14003c036  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14003c03a  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x14003c03e  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14003c045  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14003c049  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x14003c04d  mov     edx, 100080h; DesiredAccess
0x14003c052  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x14003c059  lea     rcx, [rbp+FileHandle]; FileHandle
0x14003c05d  mov     [rsp+80h+ShareAccess], 3; ShareAccess
0x14003c065  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14003c06a  call    cs:__imp_ZwOpenFile
0x14003c070  test    eax, eax
0x14003c072  js      short loc_14003C080
0x14003c074  mov     rcx, [rbp+FileHandle]; Handle
0x14003c078  call    cs:__imp_ZwClose
0x14003c07e  jmp     short loc_14003C08E
0x14003c080  cmp     eax, 0C0000022h
0x14003c085  jz      short loc_14003C08E
0x14003c087  cmp     eax, 0C0000043h
0x14003c08c  jnz     short loc_14003C093
0x14003c08e  mov     esi, 1
0x14003c093  mov     rcx, [rbp+DestinationString.Buffer]
0x14003c097  cmp     rcx, rdi
0x14003c09a  jz      short loc_14003C0AB
0x14003c09c  test    rcx, rcx
0x14003c09f  jz      short loc_14003C0AB
0x14003c0a1  lea     rcx, [rbp+DestinationString]; UnicodeString
0x14003c0a5  call    cs:__imp_RtlFreeUnicodeString
0x14003c0ab  lea     r11, [rsp+80h+var_s0]
0x14003c0b3  mov     eax, esi
0x14003c0b5  mov     rsi, [r11+18h]
0x14003c0b9  mov     rdi, [r11+20h]
0x14003c0bd  mov     rsp, r11
0x14003c0c0  pop     rbp
0x14003c0c1  retn
```
