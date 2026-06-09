# AslDoesDirectoryExistNtPath

- ea: `0x180034420`
- end: `0x180034555`
- name: `AslDoesDirectoryExistNtPath`
- size: `309`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800484c0`
- `0x18004dc10`

## callees

- `0x18000f114`
- `0x180034420`
- `0x180039a66`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800344b4`
- `ntdll!RtlInitUnicodeString` at `0x1800344b4`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18003447c`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18003447c`
- `ntdll!ZwClose` at `0x18003450b`
- `ntdll!ZwClose` at `0x18003450b`
- `ntdll!ZwOpenFile` at `0x1800344fd`
- `ntdll!ZwOpenFile` at `0x1800344fd`
- `ntdll!RtlFreeUnicodeString` at `0x180034538`
- `ntdll!RtlFreeUnicodeString` at `0x180034538`

## string_xrefs

- `0x18003448a`: `RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]`
- `0x18003449c`: `AslDoesDirectoryExistNtPath`

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
  if ( wcsnicmp_0(SourceString, L"\\SystemRoot\\", 0xCu) )
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
0x180034420  mov     [rsp-8+arg_8], rsi
0x180034425  mov     [rsp-8+arg_10], rdi
0x18003442a  push    rbp
0x18003442b  mov     rbp, rsp
0x18003442e  sub     rsp, 80h
0x180034435  xor     eax, eax
0x180034437  lea     rdx, aSystemroot_2; "\\SystemRoot\\"
0x18003443e  xorps   xmm0, xmm0
0x180034441  mov     qword ptr [rbp+DestinationString.Length], rax
0x180034445  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180034449  mov     rdi, rcx
0x18003444c  mov     [rbp+FileHandle], rax
0x180034450  lea     r8d, [rax+0Ch]; MaxCount
0x180034454  mov     [rbp+DestinationString.Buffer], rax
0x180034458  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18003445c  xor     esi, esi
0x18003445e  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180034462  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180034466  call    _wcsnicmp_0
0x18003446b  test    eax, eax
0x18003446d  jz      short loc_1800344AD
0x18003446f  xor     r9d, r9d
0x180034472  lea     rdx, [rbp+DestinationString]
0x180034476  xor     r8d, r8d
0x180034479  mov     rcx, rdi
0x18003447c  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180034482  test    eax, eax
0x180034484  jns     short loc_1800344BA
0x180034486  mov     [rsp+80h+OpenOptions], eax
0x18003448a  lea     r9, aRtldospathname_0; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x180034491  mov     r8d, 22Ah
0x180034497  mov     qword ptr [rsp+80h+ShareAccess], rdi
0x18003449c  lea     rdx, aAsldoesdirecto; "AslDoesDirectoryExistNtPath"
0x1800344a3  lea     ecx, [rsi+1]
0x1800344a6  call    AslLogCallPrintf
0x1800344ab  jmp     short loc_180034526
0x1800344ad  mov     rdx, rdi; SourceString
0x1800344b0  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800344b4  call    cs:__imp_RtlInitUnicodeString
0x1800344ba  lea     rax, [rbp+DestinationString]
0x1800344be  mov     [rsp+80h+OpenOptions], 1; OpenOptions
0x1800344c6  xorps   xmm0, xmm0
0x1800344c9  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800344cd  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x1800344d1  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800344d8  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800344dc  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x1800344e0  mov     edx, 100080h; DesiredAccess
0x1800344e5  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800344ec  lea     rcx, [rbp+FileHandle]; FileHandle
0x1800344f0  mov     [rsp+80h+ShareAccess], 3; ShareAccess
0x1800344f8  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800344fd  call    cs:__imp_ZwOpenFile
0x180034503  test    eax, eax
0x180034505  js      short loc_180034513
0x180034507  mov     rcx, [rbp+FileHandle]; Handle
0x18003450b  call    cs:__imp_ZwClose
0x180034511  jmp     short loc_180034521
0x180034513  cmp     eax, 0C0000022h
0x180034518  jz      short loc_180034521
0x18003451a  cmp     eax, 0C0000043h
0x18003451f  jnz     short loc_180034526
0x180034521  mov     esi, 1
0x180034526  mov     rcx, [rbp+DestinationString.Buffer]
0x18003452a  cmp     rcx, rdi
0x18003452d  jz      short loc_18003453E
0x18003452f  test    rcx, rcx
0x180034532  jz      short loc_18003453E
0x180034534  lea     rcx, [rbp+DestinationString]; UnicodeString
0x180034538  call    cs:__imp_RtlFreeUnicodeString
0x18003453e  lea     r11, [rsp+80h+var_s0]
0x180034546  mov     eax, esi
0x180034548  mov     rsi, [r11+18h]
0x18003454c  mov     rdi, [r11+20h]
0x180034550  mov     rsp, r11
0x180034553  pop     rbp
0x180034554  retn
```
