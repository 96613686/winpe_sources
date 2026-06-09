# SdbpWriteBufferToFile

- ea: `0x180049914`
- end: `0x180049ae0`
- name: `SdbpWriteBufferToFile`
- size: `460`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PVOID Buffer, ULONG Length)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180048930`

## callees

- `0x18000f114`
- `0x180049914`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180049973`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180049973`
- `ntdll!NtClose` at `0x180049abb`
- `ntdll!NtClose` at `0x180049abb`
- `ntdll!NtWriteFile` at `0x180049a7b`
- `ntdll!NtWriteFile` at `0x180049a7b`
- `ntdll!RtlInitUnicodeString` at `0x18004995f`
- `ntdll!RtlInitUnicodeString` at `0x18004995f`
- `ntdll!NtCreateFile` at `0x180049a1b`
- `ntdll!NtCreateFile` at `0x180049a1b`
- `ntdll!RtlFreeUnicodeString` at `0x180049a27`
- `ntdll!RtlFreeUnicodeString` at `0x180049a27`

## string_xrefs

- `0x180049982`: `Failed to convert file name "%ws" to NT path`
- `0x18004998f`: `SdbpWriteBufferToFile`
- `0x180049a9d`: `SdbpWriteBufferToFile`
- `0x180049a31`: `Failed to create file "%ws"`
- `0x180049a8b`: `Failed to write file "%ws" to disk [%x]`

## pseudocode

```c
_BOOL8 __fastcall SdbpWriteBufferToFile(PCWSTR SourceString, PVOID Buffer, ULONG Length)
{
  NTSTATUS v6; // ebx
  NTSTATUS v7; // eax
  ULONG FileAttributes[2]; // [rsp+28h] [rbp-41h]
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+17h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+D0h] [rbp+67h] BYREF
  void *FileHandle; // [rsp+E8h] [rbp+7Fh] BYREF

  FileHandle = 0;
  ByteOffset.QuadPart = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  if ( RtlDosPathNameToNtPathName_U(DestinationString.Buffer, &DestinationString, 0, 0) )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v6 = NtCreateFile(&FileHandle, 0xC0100080, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 0, 5u, 0x60u, 0, 0);
    RtlFreeUnicodeString(&DestinationString);
    if ( v6 >= 0 )
    {
      ByteOffset.QuadPart = 0;
      v7 = NtWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, Buffer, Length, &ByteOffset, 0);
      v6 = v7;
      if ( v7 >= 0 )
      {
        v6 = 0;
      }
      else
      {
        FileAttributes[0] = v7;
        AslLogCallPrintf(
          1,
          "SdbpWriteBufferToFile",
          1296,
          "Failed to write file \"%ws\" to disk [%x]",
          SourceString,
          *(_QWORD *)FileAttributes);
      }
    }
    else
    {
      AslLogCallPrintf(1, "SdbpWriteBufferToFile", 1275, "Failed to create file \"%ws\"", SourceString);
    }
  }
  else
  {
    v6 = -1073741823;
    AslLogCallPrintf(1, "SdbpWriteBufferToFile", 1246, "Failed to convert file name \"%ws\" to NT path", SourceString);
  }
  if ( FileHandle )
    NtClose(FileHandle);
  return v6 == 0;
}

```

## disassembly

```asm
0x180049914  mov     [rsp-8+arg_8], rbx
0x180049919  mov     [rsp-8+arg_10], rsi
0x18004991e  push    rbp
0x18004991f  push    rdi
0x180049920  push    r14
0x180049922  lea     rbp, [rsp-47h]
0x180049927  sub     rsp, 0B0h
0x18004992e  xorps   xmm0, xmm0
0x180049931  xor     eax, eax
0x180049933  mov     r14, rdx
0x180049936  mov     [rbp+57h+FileHandle], rax
0x18004993a  mov     rdx, rcx; SourceString
0x18004993d  mov     qword ptr [rbp+57h+ByteOffset], rax
0x180049941  mov     rdi, rcx
0x180049944  mov     esi, r8d
0x180049947  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18004994b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18004994f  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180049953  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180049957  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18004995b  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18004995f  call    cs:__imp_RtlInitUnicodeString
0x180049965  mov     rcx, [rbp+57h+DestinationString.Buffer]; DosPathName
0x180049969  lea     rdx, [rbp+57h+DestinationString]; NtPathName
0x18004996d  xor     r9d, r9d; DirectoryInfo
0x180049970  xor     r8d, r8d; NtFileNamePart
0x180049973  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180049979  test    al, al
0x18004997b  jnz     short loc_1800499AA
0x18004997d  mov     ebx, 0C0000001h
0x180049982  lea     r9, aFailedToConver_16; "Failed to convert file name \"%ws\" to "...
0x180049989  mov     r8d, 4DEh
0x18004998f  lea     rdx, aSdbpwritebuffe_0; "SdbpWriteBufferToFile"
0x180049996  mov     [rsp+0C0h+AllocationSize], rdi
0x18004999b  mov     ecx, 1
0x1800499a0  call    AslLogCallPrintf
0x1800499a5  jmp     loc_180049AB2
0x1800499aa  mov     [rsp+0C0h+EaLength], 0; EaLength
0x1800499b2  lea     rax, [rbp+57h+DestinationString]
0x1800499b6  mov     [rsp+0C0h+EaBuffer], 0; EaBuffer
0x1800499bf  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800499c3  mov     [rsp+0C0h+CreateOptions], 60h ; '`'; CreateOptions
0x1800499cb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800499cf  mov     [rsp+0C0h+CreateDisposition], 5; CreateDisposition
0x1800499d7  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800499db  mov     [rsp+0C0h+ShareAccess], 0; ShareAccess
0x1800499e3  xorps   xmm0, xmm0
0x1800499e6  mov     [rsp+0C0h+FileAttributes], 80h; FileAttributes
0x1800499ee  mov     edx, 0C0100080h; DesiredAccess
0x1800499f3  mov     [rsp+0C0h+AllocationSize], 0; AllocationSize
0x1800499fc  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180049a03  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180049a0b  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180049a12  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180049a16  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180049a1b  call    cs:__imp_NtCreateFile
0x180049a21  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x180049a25  mov     ebx, eax
0x180049a27  call    cs:__imp_RtlFreeUnicodeString
0x180049a2d  test    ebx, ebx
0x180049a2f  jns     short loc_180049A43
0x180049a31  lea     r9, aFailedToCreate_21; "Failed to create file \"%ws\""
0x180049a38  mov     r8d, 4FBh
0x180049a3e  jmp     loc_18004998F
0x180049a43  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180049a47  lea     rax, [rbp+57h+ByteOffset]
0x180049a4b  mov     qword ptr [rsp+0C0h+CreateOptions], 0; Key
0x180049a54  xor     r9d, r9d; ApcContext
0x180049a57  mov     qword ptr [rsp+0C0h+CreateDisposition], rax; ByteOffset
0x180049a5c  xor     r8d, r8d; ApcRoutine
0x180049a5f  mov     [rsp+0C0h+ShareAccess], esi; Length
0x180049a63  lea     rax, [rbp+57h+IoStatusBlock]
0x180049a67  mov     qword ptr [rsp+0C0h+FileAttributes], r14; Buffer
0x180049a6c  xor     edx, edx; Event
0x180049a6e  mov     [rsp+0C0h+AllocationSize], rax; IoStatusBlock
0x180049a73  mov     qword ptr [rbp+57h+ByteOffset], 0
0x180049a7b  call    cs:__imp_NtWriteFile
0x180049a81  mov     ebx, eax
0x180049a83  test    eax, eax
0x180049a85  jns     short loc_180049AB0
0x180049a87  mov     [rsp+0C0h+FileAttributes], eax
0x180049a8b  lea     r9, aFailedToWriteF; "Failed to write file \"%ws\" to disk [%"...
0x180049a92  mov     r8d, 510h
0x180049a98  mov     [rsp+0C0h+AllocationSize], rdi
0x180049a9d  lea     rdx, aSdbpwritebuffe_0; "SdbpWriteBufferToFile"
0x180049aa4  mov     ecx, 1
0x180049aa9  call    AslLogCallPrintf
0x180049aae  jmp     short loc_180049AB2
0x180049ab0  xor     ebx, ebx
0x180049ab2  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180049ab6  test    rcx, rcx
0x180049ab9  jz      short loc_180049AC1
0x180049abb  call    cs:__imp_NtClose
0x180049ac1  xor     eax, eax
0x180049ac3  lea     r11, [rsp+0C0h+var_10]
0x180049acb  mov     rsi, [r11+30h]
0x180049acf  test    ebx, ebx
0x180049ad1  mov     rbx, [r11+28h]
0x180049ad5  setz    al
0x180049ad8  mov     rsp, r11
0x180049adb  pop     r14
0x180049add  pop     rdi
0x180049ade  pop     rbp
0x180049adf  retn
```
