# ConsoleSanitizeStandardIoObjects

- ea: `0x1800fdc30`
- end: `0x1800fdf75`
- name: `ConsoleSanitizeStandardIoObjects`
- size: `837`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800b950c`
- `0x1800b960c`
- `0x1800ba128`

## callees

- `0x1800fdc30`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800fdcb3`
- `ntdll!RtlInitUnicodeString` at `0x1800fddb3`
- `ntdll!RtlInitUnicodeString` at `0x1800fde78`
- `ntdll!RtlInitUnicodeString` at `0x1800fdcb3`
- `ntdll!RtlInitUnicodeString` at `0x1800fddb3`
- `ntdll!RtlInitUnicodeString` at `0x1800fde78`
- `ntdll!NtCreateFile` at `0x1800fdd18`
- `ntdll!NtCreateFile` at `0x1800fde18`
- `ntdll!NtCreateFile` at `0x1800fdedd`
- `ntdll!NtCreateFile` at `0x1800fdd18`
- `ntdll!NtCreateFile` at `0x1800fde18`
- `ntdll!NtCreateFile` at `0x1800fdedd`
- `ntdll!NtClose` at `0x1800fde35`
- `ntdll!NtClose` at `0x1800fdf00`
- `ntdll!NtClose` at `0x1800fde35`
- `ntdll!NtClose` at `0x1800fdf00`
- `ntdll!NtDuplicateObject` at `0x1800fdf2c`
- `ntdll!NtDuplicateObject` at `0x1800fdf2c`

## pseudocode

```c
NTSTATUS __fastcall ConsoleSanitizeStandardIoObjects(__int64 a1)
{
  struct _RTL_USER_PROCESS_PARAMETERS *ProcessParameters; // r14
  NTSTATUS v3; // ebx
  int v4; // edi
  void *v5; // rbx
  NTSTATUS result; // eax
  void *v7; // rbx
  HANDLE v8; // rcx
  void *v9; // rbx
  NTSTATUS v10; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-9h] BYREF
  HANDLE FileHandle; // [rsp+F8h] [rbp+6Fh] BYREF
  HANDLE SourceHandle; // [rsp+100h] [rbp+77h] BYREF
  HANDLE TargetHandle; // [rsp+108h] [rbp+7Fh] BYREF

  FileHandle = 0;
  TargetHandle = 0;
  SourceHandle = 0;
  ProcessParameters = NtCurrentPeb()->ProcessParameters;
  if ( ProcessParameters->StandardInput )
  {
    v3 = 0;
    v4 = 0;
    if ( ((__int64)ProcessParameters->StandardInput & 0x10000003) != 3 )
    {
LABEL_5:
      if ( !ProcessParameters->StandardOutput || ((__int64)ProcessParameters->StandardOutput & 0x10000003) == 3 )
      {
        v7 = *(void **)(a1 + 8);
        IoStatusBlock = 0;
        DestinationString = 0;
        memset(&ObjectAttributes, 0, 44);
        RtlInitUnicodeString(&DestinationString, L"\\Output");
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = v7;
        ObjectAttributes.Attributes = 66;
        ObjectAttributes.ObjectName = &DestinationString;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v3 = NtCreateFile(&SourceHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 2u, 0x20u, 0, 0);
        if ( v3 < 0 )
        {
          v8 = FileHandle;
          goto LABEL_19;
        }
        v3 = 0;
        v4 |= 2u;
      }
      if ( ProcessParameters->StandardError && ((__int64)ProcessParameters->StandardError & 0x10000003) != 3 )
        goto LABEL_9;
      if ( SourceHandle )
      {
        v3 = NtDuplicateObject(
               (HANDLE)0xFFFFFFFFFFFFFFFFLL,
               SourceHandle,
               (HANDLE)0xFFFFFFFFFFFFFFFFLL,
               &TargetHandle,
               0,
               0,
               6u);
      }
      else
      {
        v9 = *(void **)(a1 + 8);
        IoStatusBlock = 0;
        DestinationString = 0;
        memset(&ObjectAttributes, 0, 44);
        RtlInitUnicodeString(&DestinationString, L"\\Output");
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = v9;
        ObjectAttributes.Attributes = 66;
        ObjectAttributes.ObjectName = &DestinationString;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v10 = NtCreateFile(&TargetHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 2u, 0x20u, 0, 0);
        v3 = 0;
        if ( v10 < 0 )
          v3 = v10;
      }
      if ( v3 >= 0 )
      {
        v4 |= 4u;
LABEL_9:
        if ( (v4 & 1) != 0 )
          *(_QWORD *)(a1 + 24) = FileHandle;
        if ( (v4 & 2) != 0 )
          *(_QWORD *)(a1 + 32) = SourceHandle;
        if ( (v4 & 4) != 0 )
          *(_QWORD *)(a1 + 40) = TargetHandle;
        *(_DWORD *)a1 = v4;
        return v3;
      }
      if ( FileHandle )
        NtClose(FileHandle);
      v8 = SourceHandle;
LABEL_19:
      if ( v8 )
        NtClose(v8);
      return v3;
    }
  }
  v5 = *(void **)(a1 + 8);
  IoStatusBlock = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, L"\\Input");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = v5;
  ObjectAttributes.Attributes = 66;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = NtCreateFile(&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 2u, 0x20u, 0, 0);
  if ( result >= 0 )
  {
    v3 = 0;
    v4 = 1;
    goto LABEL_5;
  }
  return result;
}

```

## disassembly

```asm
0x1800fdc30  push    rbp
0x1800fdc32  push    rbx
0x1800fdc33  push    rsi
0x1800fdc34  push    rdi
0x1800fdc35  push    r13
0x1800fdc37  push    r14
0x1800fdc39  push    r15
0x1800fdc3b  lea     rbp, [rsp-27h]
0x1800fdc40  sub     rsp, 0B0h
0x1800fdc47  xor     r15d, r15d
0x1800fdc4a  mov     rsi, rcx
0x1800fdc4d  mov     [rbp+57h+FileHandle], r15
0x1800fdc51  mov     r13d, 10000003h
0x1800fdc57  mov     [rbp+57h+TargetHandle], r15
0x1800fdc5b  mov     [rbp+57h+SourceHandle], r15
0x1800fdc5f  mov     rax, gs:60h
0x1800fdc68  mov     r14, [rax+20h]
0x1800fdc6c  mov     rax, [r14+20h]
0x1800fdc70  test    rax, rax
0x1800fdc73  jz      short loc_1800FDC88
0x1800fdc75  and     rax, r13
0x1800fdc78  mov     ebx, r15d
0x1800fdc7b  mov     edi, r15d
0x1800fdc7e  cmp     rax, 3
0x1800fdc82  jnz     loc_1800FDD38
0x1800fdc88  mov     rbx, [rcx+8]
0x1800fdc8c  lea     rdx, aInput; "\\Input"
0x1800fdc93  xorps   xmm0, xmm0
0x1800fdc96  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800fdc9a  xorps   xmm1, xmm1
0x1800fdc9d  xor     eax, eax
0x1800fdc9f  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800fdca3  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800fdca7  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800fdcab  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x1800fdcaf  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800fdcb3  call    cs:__imp_RtlInitUnicodeString
0x1800fdcb9  mov     [rsp+0E0h+EaLength], r15d; EaLength
0x1800fdcbe  lea     rax, [rbp+57h+DestinationString]
0x1800fdcc2  mov     [rsp+0E0h+EaBuffer], r15; EaBuffer
0x1800fdcc7  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800fdccb  mov     [rsp+0E0h+CreateOptions], 20h ; ' '; CreateOptions
0x1800fdcd3  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800fdcd7  mov     [rsp+0E0h+CreateDisposition], 2; CreateDisposition
0x1800fdcdf  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800fdce3  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x1800fdceb  xorps   xmm0, xmm0
0x1800fdcee  mov     [rsp+0E0h+FileAttributes], r15d; FileAttributes
0x1800fdcf3  mov     edx, 12019Fh; DesiredAccess
0x1800fdcf8  mov     [rsp+0E0h+AllocationSize], r15; AllocationSize
0x1800fdcfd  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800fdd04  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x1800fdd08  mov     [rbp+57h+ObjectAttributes.Attributes], 42h ; 'B'
0x1800fdd0f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800fdd13  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800fdd18  call    cs:__imp_NtCreateFile
0x1800fdd1e  test    eax, eax
0x1800fdd20  jns     loc_1800FDF36
0x1800fdd26  add     rsp, 0B0h
0x1800fdd2d  pop     r15
0x1800fdd2f  pop     r14
0x1800fdd31  pop     r13
0x1800fdd33  pop     rdi
0x1800fdd34  pop     rsi
0x1800fdd35  pop     rbx
0x1800fdd36  pop     rbp
0x1800fdd37  retn
0x1800fdd38  mov     rax, [r14+28h]
0x1800fdd3c  test    rax, rax
0x1800fdd3f  jz      short loc_1800FDD88
0x1800fdd41  and     rax, r13
0x1800fdd44  cmp     rax, 3
0x1800fdd48  jz      short loc_1800FDD88
0x1800fdd4a  mov     rax, [r14+30h]
0x1800fdd4e  test    rax, rax
0x1800fdd51  jz      loc_1800FDE40
0x1800fdd57  and     rax, r13
0x1800fdd5a  cmp     rax, 3
0x1800fdd5e  jz      loc_1800FDE40
0x1800fdd64  test    dil, 1
0x1800fdd68  jnz     loc_1800FDF4E
0x1800fdd6e  test    dil, 2
0x1800fdd72  jnz     loc_1800FDF5B
0x1800fdd78  test    dil, 4
0x1800fdd7c  jnz     loc_1800FDF68
0x1800fdd82  mov     [rsi], edi
0x1800fdd84  mov     eax, ebx
0x1800fdd86  jmp     short loc_1800FDD26
0x1800fdd88  mov     rbx, [rsi+8]
0x1800fdd8c  lea     rdx, aOutput; "\\Output"
0x1800fdd93  xorps   xmm0, xmm0
0x1800fdd96  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800fdd9a  xorps   xmm1, xmm1
0x1800fdd9d  xor     eax, eax
0x1800fdd9f  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800fdda3  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800fdda7  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800fddab  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x1800fddaf  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800fddb3  call    cs:__imp_RtlInitUnicodeString
0x1800fddb9  mov     [rsp+0E0h+EaLength], r15d; EaLength
0x1800fddbe  lea     rax, [rbp+57h+DestinationString]
0x1800fddc2  mov     [rsp+0E0h+EaBuffer], r15; EaBuffer
0x1800fddc7  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800fddcb  mov     [rsp+0E0h+CreateOptions], 20h ; ' '; CreateOptions
0x1800fddd3  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800fddd7  mov     [rsp+0E0h+CreateDisposition], 2; CreateDisposition
0x1800fdddf  lea     rcx, [rbp+57h+SourceHandle]; FileHandle
0x1800fdde3  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x1800fddeb  xorps   xmm0, xmm0
0x1800fddee  mov     [rsp+0E0h+FileAttributes], r15d; FileAttributes
0x1800fddf3  mov     edx, 12019Fh; DesiredAccess
0x1800fddf8  mov     [rsp+0E0h+AllocationSize], r15; AllocationSize
0x1800fddfd  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800fde04  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x1800fde08  mov     [rbp+57h+ObjectAttributes.Attributes], 42h ; 'B'
0x1800fde0f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800fde13  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800fde18  call    cs:__imp_NtCreateFile
0x1800fde1e  mov     ebx, eax
0x1800fde20  test    eax, eax
0x1800fde22  jns     loc_1800FDF43
0x1800fde28  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800fde2c  test    rcx, rcx
0x1800fde2f  jz      loc_1800FDD84
0x1800fde35  call    cs:__imp_NtClose
0x1800fde3b  jmp     loc_1800FDD84
0x1800fde40  mov     rdx, [rbp+57h+SourceHandle]; SourceHandle
0x1800fde44  test    rdx, rdx
0x1800fde47  jnz     loc_1800FDF0F
0x1800fde4d  mov     rbx, [rsi+8]
0x1800fde51  lea     rdx, aOutput; "\\Output"
0x1800fde58  xorps   xmm0, xmm0
0x1800fde5b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800fde5f  xorps   xmm1, xmm1
0x1800fde62  xor     eax, eax
0x1800fde64  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800fde68  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800fde6c  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800fde70  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x1800fde74  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800fde78  call    cs:__imp_RtlInitUnicodeString
0x1800fde7e  mov     [rsp+0E0h+EaLength], r15d; EaLength
0x1800fde83  lea     rax, [rbp+57h+DestinationString]
0x1800fde87  mov     [rsp+0E0h+EaBuffer], r15; EaBuffer
0x1800fde8c  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800fde90  mov     [rsp+0E0h+CreateOptions], 20h ; ' '; CreateOptions
0x1800fde98  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800fde9c  mov     [rsp+0E0h+CreateDisposition], 2; CreateDisposition
0x1800fdea4  lea     rcx, [rbp+57h+TargetHandle]; FileHandle
0x1800fdea8  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x1800fdeb0  xorps   xmm0, xmm0
0x1800fdeb3  mov     [rsp+0E0h+FileAttributes], r15d; FileAttributes
0x1800fdeb8  mov     edx, 12019Fh; DesiredAccess
0x1800fdebd  mov     [rsp+0E0h+AllocationSize], r15; AllocationSize
0x1800fdec2  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800fdec9  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x1800fdecd  mov     [rbp+57h+ObjectAttributes.Attributes], 42h ; 'B'
0x1800fded4  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800fded8  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800fdedd  call    cs:__imp_NtCreateFile
0x1800fdee3  test    eax, eax
0x1800fdee5  mov     ebx, r15d
0x1800fdee8  cmovs   ebx, eax
0x1800fdeeb  test    ebx, ebx
0x1800fdeed  js      short loc_1800FDEF7
0x1800fdeef  or      edi, 4
0x1800fdef2  jmp     loc_1800FDD64
0x1800fdef7  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800fdefb  test    rcx, rcx
0x1800fdefe  jz      short loc_1800FDF06
0x1800fdf00  call    cs:__imp_NtClose
0x1800fdf06  mov     rcx, [rbp+57h+SourceHandle]
0x1800fdf0a  jmp     loc_1800FDE2C
0x1800fdf0f  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x1800fdf13  mov     [rsp+0E0h+ShareAccess], 6; Options
0x1800fdf1b  mov     r8, rcx; TargetProcessHandle
0x1800fdf1e  mov     [rsp+0E0h+FileAttributes], r15d; HandleAttributes
0x1800fdf23  lea     r9, [rbp+57h+TargetHandle]; TargetHandle
0x1800fdf27  mov     dword ptr [rsp+0E0h+AllocationSize], r15d; DesiredAccess
0x1800fdf2c  call    cs:__imp_NtDuplicateObject
0x1800fdf32  mov     ebx, eax
0x1800fdf34  jmp     short loc_1800FDEEB
0x1800fdf36  mov     ebx, r15d
0x1800fdf39  mov     edi, 1
0x1800fdf3e  jmp     loc_1800FDD38
0x1800fdf43  mov     ebx, r15d
0x1800fdf46  or      edi, 2
0x1800fdf49  jmp     loc_1800FDD4A
0x1800fdf4e  mov     rax, [rbp+57h+FileHandle]
0x1800fdf52  mov     [rsi+18h], rax
0x1800fdf56  jmp     loc_1800FDD6E
0x1800fdf5b  mov     rax, [rbp+57h+SourceHandle]
0x1800fdf5f  mov     [rsi+20h], rax
0x1800fdf63  jmp     loc_1800FDD78
0x1800fdf68  mov     rax, [rbp+57h+TargetHandle]
0x1800fdf6c  mov     [rsi+28h], rax
0x1800fdf70  jmp     loc_1800FDD82
```
