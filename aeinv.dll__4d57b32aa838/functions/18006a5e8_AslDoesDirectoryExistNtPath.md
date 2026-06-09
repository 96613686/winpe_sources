# AslDoesDirectoryExistNtPath

- ea: `0x18006a5e8`
- end: `0x18006a71d`
- name: `AslDoesDirectoryExistNtPath`
- size: `309`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1801205f0`

## callees

- `0x1800197d4`
- `0x18005a7d8`
- `0x18006a5e8`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18006a700`
- `ntdll!RtlFreeUnicodeString` at `0x18006a700`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18006a644`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18006a644`
- `ntdll!ZwClose` at `0x18006a6d3`
- `ntdll!ZwClose` at `0x18006a6d3`
- `ntdll!RtlInitUnicodeString` at `0x18006a67c`
- `ntdll!RtlInitUnicodeString` at `0x18006a67c`
- `ntdll!ZwOpenFile` at `0x18006a6c5`
- `ntdll!ZwOpenFile` at `0x18006a6c5`

## string_xrefs

- `0x18006a652`: `RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]`
- `0x18006a664`: `AslDoesDirectoryExistNtPath`

## pseudocode

```c
__int64 __fastcall AslDoesDirectoryExistNtPath(PCWSTR SourceString)
{
  unsigned int v2; // esi
  NTSTATUS v3; // eax
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
  if ( wcsnicmp(SourceString, L"\\SystemRoot\\", 0xCu) )
  {
    if ( (int)RtlDosPathNameToNtPathName_U_WithStatus(SourceString, &DestinationString, 0, 0) < 0 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"AslDoesDirectoryExistNtPath",
        554,
        (unsigned int)"RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]");
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
  v3 = ZwOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 3u, 1u);
  if ( v3 >= 0 )
  {
    ZwClose(FileHandle);
LABEL_9:
    v2 = 1;
    goto LABEL_10;
  }
  if ( v3 == -1073741790 || v3 == -1073741757 )
    goto LABEL_9;
LABEL_10:
  if ( DestinationString.Buffer != SourceString && DestinationString.Buffer )
    RtlFreeUnicodeString(&DestinationString);
  return v2;
}

```

## disassembly

```asm
0x18006a5e8  mov     [rsp-8+arg_8], rsi
0x18006a5ed  mov     [rsp-8+arg_10], rdi
0x18006a5f2  push    rbp
0x18006a5f3  mov     rbp, rsp
0x18006a5f6  sub     rsp, 80h
0x18006a5fd  xor     eax, eax
0x18006a5ff  lea     rdx, aSystemroot_2; "\\SystemRoot\\"
0x18006a606  xorps   xmm0, xmm0
0x18006a609  mov     qword ptr [rbp+DestinationString.Length], rax
0x18006a60d  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18006a611  mov     rdi, rcx
0x18006a614  mov     [rbp+FileHandle], rax
0x18006a618  lea     r8d, [rax+0Ch]; MaxCount
0x18006a61c  mov     [rbp+DestinationString.Buffer], rax
0x18006a620  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18006a624  xor     esi, esi
0x18006a626  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18006a62a  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x18006a62e  call    _wcsnicmp
0x18006a633  test    eax, eax
0x18006a635  jz      short loc_18006A675
0x18006a637  xor     r9d, r9d
0x18006a63a  lea     rdx, [rbp+DestinationString]
0x18006a63e  xor     r8d, r8d
0x18006a641  mov     rcx, rdi
0x18006a644  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18006a64a  test    eax, eax
0x18006a64c  jns     short loc_18006A682
0x18006a64e  mov     [rsp+80h+OpenOptions], eax
0x18006a652  lea     r9, aRtldospathname_0; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x18006a659  mov     r8d, 22Ah
0x18006a65f  mov     qword ptr [rsp+80h+ShareAccess], rdi
0x18006a664  lea     rdx, aAsldoesdirecto; "AslDoesDirectoryExistNtPath"
0x18006a66b  lea     ecx, [rsi+1]
0x18006a66e  call    AslLogCallPrintf
0x18006a673  jmp     short loc_18006A6EE
0x18006a675  mov     rdx, rdi; SourceString
0x18006a678  lea     rcx, [rbp+DestinationString]; DestinationString
0x18006a67c  call    cs:__imp_RtlInitUnicodeString
0x18006a682  lea     rax, [rbp+DestinationString]
0x18006a686  mov     [rsp+80h+OpenOptions], 1; OpenOptions
0x18006a68e  xorps   xmm0, xmm0
0x18006a691  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18006a695  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x18006a699  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18006a6a0  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18006a6a4  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x18006a6a8  mov     edx, 100080h; DesiredAccess
0x18006a6ad  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18006a6b4  lea     rcx, [rbp+FileHandle]; FileHandle
0x18006a6b8  mov     [rsp+80h+ShareAccess], 3; ShareAccess
0x18006a6c0  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18006a6c5  call    cs:__imp_ZwOpenFile
0x18006a6cb  test    eax, eax
0x18006a6cd  js      short loc_18006A6DB
0x18006a6cf  mov     rcx, [rbp+FileHandle]; Handle
0x18006a6d3  call    cs:__imp_ZwClose
0x18006a6d9  jmp     short loc_18006A6E9
0x18006a6db  cmp     eax, 0C0000022h
0x18006a6e0  jz      short loc_18006A6E9
0x18006a6e2  cmp     eax, 0C0000043h
0x18006a6e7  jnz     short loc_18006A6EE
0x18006a6e9  mov     esi, 1
0x18006a6ee  mov     rcx, [rbp+DestinationString.Buffer]
0x18006a6f2  cmp     rcx, rdi
0x18006a6f5  jz      short loc_18006A706
0x18006a6f7  test    rcx, rcx
0x18006a6fa  jz      short loc_18006A706
0x18006a6fc  lea     rcx, [rbp+DestinationString]; UnicodeString
0x18006a700  call    cs:__imp_RtlFreeUnicodeString
0x18006a706  lea     r11, [rsp+80h+var_s0]
0x18006a70e  mov     eax, esi
0x18006a710  mov     rsi, [r11+18h]
0x18006a714  mov     rdi, [r11+20h]
0x18006a718  mov     rsp, r11
0x18006a71b  pop     rbp
0x18006a71c  retn
```
