# BasepNotifyTrackingService

- ea: `0x1800cfdf0`
- end: `0x1800d00f5`
- name: `BasepNotifyTrackingService`
- size: `773`
- prototype: `__int64 __fastcall(PHANDLE FileHandle, POBJECT_ATTRIBUTES ObjectAttributes)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800cd450`
- `0x1800f6f80`

## callees

- `0x180048f30`
- `0x1800cfdf0`
- `0x18012daf0`
- `0x180188eb9`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800cfea2`
- `ntdll!RtlInitUnicodeString` at `0x1800cfea2`
- `ntdll!NtQueryInformationFile` at `0x1800cff99`
- `ntdll!NtQueryInformationFile` at `0x1800cff99`
- `ntdll!NtOpenFile` at `0x1800cff6a`
- `ntdll!NtOpenFile` at `0x1800d0034`
- `ntdll!NtOpenFile` at `0x1800cff6a`
- `ntdll!NtOpenFile` at `0x1800d0034`
- `ntdll!NtSetInformationFile` at `0x1800cff2b`
- `ntdll!NtSetInformationFile` at `0x1800cfff5`
- `ntdll!NtSetInformationFile` at `0x1800d0070`
- `ntdll!NtSetInformationFile` at `0x1800d00a2`
- `ntdll!NtSetInformationFile` at `0x1800cff2b`
- `ntdll!NtSetInformationFile` at `0x1800cfff5`
- `ntdll!NtSetInformationFile` at `0x1800d0070`
- `ntdll!NtSetInformationFile` at `0x1800d00a2`
- `ntdll!RtlUnicodeStringToOemString` at `0x1800cfeb5`
- `ntdll!RtlUnicodeStringToOemString` at `0x1800cfeb5`
- `ntdll!NtClose` at `0x1800d0047`
- `ntdll!NtClose` at `0x1800d0047`
- `ext-ms-win-kernel32-file-l1-1-0!BasepGetComputerNameFromNtPath` at `0x1800cfe62`
- `ext-ms-win-kernel32-file-l1-1-0!BasepGetComputerNameFromNtPath` at `0x1800cfe62`

## pseudocode

```c
__int64 __fastcall BasepNotifyTrackingService(
        PHANDLE FileHandle,
        POBJECT_ATTRIBUTES ObjectAttributes,
        __int64 a3,
        __int64 a4)
{
  int ComputerNameFromNtPath; // eax
  NTSTATUS v9; // ebx
  __int64 Length; // rbx
  int v11; // esi
  HANDLE v12; // rcx
  struct _STRING v14; // [rsp+38h] [rbp-200h] BYREF
  int v15; // [rsp+48h] [rbp-1F0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-1E8h] BYREF
  HANDLE FileHandlea; // [rsp+60h] [rbp-1D8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-1D0h] BYREF
  __int128 v19; // [rsp+78h] [rbp-1C0h] BYREF
  __int128 v20; // [rsp+88h] [rbp-1B0h]
  __int64 v21; // [rsp+98h] [rbp-1A0h]
  __int64 FileInformation; // [rsp+A0h] [rbp-198h] BYREF
  int v23; // [rsp+A8h] [rbp-190h]
  _BYTE v24[36]; // [rsp+ACh] [rbp-18Ch] BYREF
  WCHAR SourceString[16]; // [rsp+D0h] [rbp-168h] BYREF
  char v26; // [rsp+F0h] [rbp-148h] BYREF

  v19 = 0;
  v20 = 0;
  v21 = 0;
  IoStatusBlock = 0;
  v15 = 16;
  if ( (unsigned __int8)IsBasepGetComputerNameFromNtPathPresent() )
    ComputerNameFromNtPath = BasepGetComputerNameFromNtPath(a4, a3, SourceString, &v15);
  else
    ComputerNameFromNtPath = 50;
  if ( ComputerNameFromNtPath )
  {
    v23 = 0;
  }
  else
  {
    *(_DWORD *)(&v14.MaximumLength + 1) = 0;
    DestinationString = 0;
    *(_DWORD *)&v14.Length = 17039360;
    v14.Buffer = &v26;
    RtlInitUnicodeString(&DestinationString, SourceString);
    v9 = RtlUnicodeStringToOemString(&v14, &DestinationString, 0);
    if ( v9 < 0 )
      return (unsigned int)v9;
    if ( v14.Length > 0x1Eu )
      return (unsigned int)-2147483643;
    Length = v14.Length;
    memcpy_0(v24, v14.Buffer, v14.Length);
    v24[Length] = 0;
    v23 = v14.Length + 1;
  }
  FileInformation = a3;
  v9 = NtSetInformationFile(*FileHandle, &IoStatusBlock, &FileInformation, 0x30u, FileTrackingInformation);
  if ( v9 == -1073741790 )
  {
    CloseHandle(*FileHandle);
    v9 = NtOpenFile(FileHandle, 0x100180u, ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
    if ( v9 < 0 )
    {
      *FileHandle = (HANDLE)-1LL;
    }
    else
    {
      v9 = NtQueryInformationFile(*FileHandle, &IoStatusBlock, &v19, 0x28u, FileBasicInformation);
      if ( v9 >= 0 )
      {
        v11 = v21;
        v19 = 0;
        v20 = 0;
        v21 = (unsigned int)v21 & 0xFFFFFFFE;
        v9 = NtSetInformationFile(*FileHandle, &IoStatusBlock, &v19, 0x28u, FileBasicInformation);
        if ( v9 >= 0 )
        {
          FileHandlea = 0;
          v9 = NtOpenFile(&FileHandlea, 0x40100000u, ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
          if ( v9 >= 0 )
          {
            NtClose(*FileHandle);
            v12 = FileHandlea;
            *FileHandle = FileHandlea;
            v9 = NtSetInformationFile(v12, &IoStatusBlock, &FileInformation, 0x30u, FileTrackingInformation);
          }
          if ( v9 < 0 )
          {
            LODWORD(v21) = v11;
            NtSetInformationFile(*FileHandle, &IoStatusBlock, &v19, 0x28u, FileBasicInformation);
          }
        }
      }
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800cfdf0  push    rbx
0x1800cfdf2  push    rsi
0x1800cfdf3  push    rdi
0x1800cfdf4  push    r14
0x1800cfdf6  sub     rsp, 218h
0x1800cfdfd  mov     rax, cs:__security_cookie
0x1800cfe04  xor     rax, rsp
0x1800cfe07  mov     [rsp+238h+var_38], rax
0x1800cfe0f  mov     rbx, r9
0x1800cfe12  mov     rsi, r8
0x1800cfe15  mov     r14, rdx
0x1800cfe18  mov     rdi, rcx
0x1800cfe1b  xorps   xmm0, xmm0
0x1800cfe1e  xor     eax, eax
0x1800cfe20  movups  [rsp+238h+var_1C0], xmm0
0x1800cfe25  movups  [rsp+238h+var_1B0], xmm0
0x1800cfe2d  mov     [rsp+238h+var_1A0], rax
0x1800cfe35  movups  xmmword ptr [rsp+238h+IoStatusBlock], xmm0
0x1800cfe3a  mov     [rsp+238h+var_1F0], 10h
0x1800cfe42  call    IsBasepGetComputerNameFromNtPathPresent
0x1800cfe47  test    al, al
0x1800cfe49  jz      loc_1800D00C5
0x1800cfe4f  lea     r9, [rsp+238h+var_1F0]
0x1800cfe54  lea     r8, [rsp+238h+SourceString]
0x1800cfe5c  mov     rdx, rsi
0x1800cfe5f  mov     rcx, rbx
0x1800cfe62  call    cs:__imp_BasepGetComputerNameFromNtPath
0x1800cfe68  test    eax, eax
0x1800cfe6a  jnz     loc_1800D00AA
0x1800cfe70  xorps   xmm0, xmm0
0x1800cfe73  movups  xmmword ptr [rsp+238h+var_200.Length], xmm0
0x1800cfe78  xorps   xmm1, xmm1
0x1800cfe7b  movups  xmmword ptr [rsp+238h+DestinationString.Length], xmm1
0x1800cfe80  mov     dword ptr [rsp+238h+var_200.Length], 1040000h
0x1800cfe88  lea     rax, [rsp+238h+var_148]
0x1800cfe90  mov     [rsp+238h+var_200.Buffer], rax
0x1800cfe95  lea     rdx, [rsp+238h+SourceString]; SourceString
0x1800cfe9d  lea     rcx, [rsp+238h+DestinationString]; DestinationString
0x1800cfea2  call    cs:__imp_RtlInitUnicodeString
0x1800cfea8  xor     r8d, r8d; AllocateDestinationString
0x1800cfeab  lea     rdx, [rsp+238h+DestinationString]; SourceString
0x1800cfeb0  lea     rcx, [rsp+238h+var_200]; DestinationString
0x1800cfeb5  call    cs:__imp_RtlUnicodeStringToOemString
0x1800cfebb  mov     ebx, eax
0x1800cfebd  mov     [rsp+238h+var_208], eax
0x1800cfec1  test    eax, eax
0x1800cfec3  js      loc_1800D00D6
0x1800cfec9  cmp     [rsp+238h+var_200.Length], 1Eh
0x1800cfecf  ja      loc_1800D00BA
0x1800cfed5  movzx   ebx, [rsp+238h+var_200.Length]
0x1800cfeda  mov     r8d, ebx; Size
0x1800cfedd  mov     rdx, [rsp+238h+var_200.Buffer]; Src
0x1800cfee2  lea     rcx, [rsp+238h+var_18C]; void *
0x1800cfeea  call    memcpy_0
0x1800cfeef  mov     [rsp+rbx+238h+var_18C], 0
0x1800cfef7  movzx   eax, [rsp+238h+var_200.Length]
0x1800cfefc  inc     eax
0x1800cfefe  mov     [rsp+238h+var_190], eax
0x1800cff05  mov     [rsp+238h+FileInformation], rsi
0x1800cff0d  mov     [rsp+238h+FileInformationClass], 24h ; '$'; FileInformationClass
0x1800cff15  mov     r9d, 30h ; '0'; Length
0x1800cff1b  lea     r8, [rsp+238h+FileInformation]; FileInformation
0x1800cff23  lea     rdx, [rsp+238h+IoStatusBlock]; IoStatusBlock
0x1800cff28  mov     rcx, [rdi]; FileHandle
0x1800cff2b  call    cs:__imp_NtSetInformationFile
0x1800cff31  mov     ebx, eax
0x1800cff33  mov     [rsp+238h+var_208], eax
0x1800cff37  cmp     eax, 0C0000022h
0x1800cff3c  jnz     loc_1800D00D6
0x1800cff42  mov     rcx, [rdi]; hObject
0x1800cff45  call    CloseHandle
0x1800cff4a  mov     [rsp+238h+OpenOptions], 20h ; ' '; OpenOptions
0x1800cff52  mov     [rsp+238h+FileInformationClass], 7; ShareAccess
0x1800cff5a  lea     r9, [rsp+238h+IoStatusBlock]; IoStatusBlock
0x1800cff5f  mov     r8, r14; ObjectAttributes
0x1800cff62  mov     edx, 100180h; DesiredAccess
0x1800cff67  mov     rcx, rdi; FileHandle
0x1800cff6a  call    cs:__imp_NtOpenFile
0x1800cff70  mov     ebx, eax
0x1800cff72  mov     [rsp+238h+var_208], eax
0x1800cff76  test    eax, eax
0x1800cff78  js      loc_1800D00CF
0x1800cff7e  mov     [rsp+238h+FileInformationClass], 4; FileInformationClass
0x1800cff86  mov     r9d, 28h ; '('; Length
0x1800cff8c  lea     r8, [rsp+238h+var_1C0]; FileInformation
0x1800cff91  lea     rdx, [rsp+238h+IoStatusBlock]; IoStatusBlock
0x1800cff96  mov     rcx, [rdi]; FileHandle
0x1800cff99  call    cs:__imp_NtQueryInformationFile
0x1800cff9f  mov     ebx, eax
0x1800cffa1  mov     [rsp+238h+var_208], eax
0x1800cffa5  test    eax, eax
0x1800cffa7  js      loc_1800D00D6
0x1800cffad  mov     esi, dword ptr [rsp+238h+var_1A0]
0x1800cffb4  xorps   xmm0, xmm0
0x1800cffb7  xor     eax, eax
0x1800cffb9  movups  [rsp+238h+var_1C0], xmm0
0x1800cffbe  movups  [rsp+238h+var_1B0], xmm0
0x1800cffc6  mov     [rsp+238h+var_1A0], rax
0x1800cffce  mov     eax, esi
0x1800cffd0  and     eax, 0FFFFFFFEh
0x1800cffd3  mov     dword ptr [rsp+238h+var_1A0], eax
0x1800cffda  mov     [rsp+238h+FileInformationClass], 4; FileInformationClass
0x1800cffe2  mov     r9d, 28h ; '('; Length
0x1800cffe8  lea     r8, [rsp+238h+var_1C0]; FileInformation
0x1800cffed  lea     rdx, [rsp+238h+IoStatusBlock]; IoStatusBlock
0x1800cfff2  mov     rcx, [rdi]; FileHandle
0x1800cfff5  call    cs:__imp_NtSetInformationFile
0x1800cfffb  mov     ebx, eax
0x1800cfffd  mov     [rsp+238h+var_208], eax
0x1800d0001  test    eax, eax
0x1800d0003  js      loc_1800D00D6
0x1800d0009  mov     [rsp+238h+FileHandle], 0
0x1800d0012  mov     [rsp+238h+OpenOptions], 20h ; ' '; OpenOptions
0x1800d001a  mov     [rsp+238h+FileInformationClass], 7; ShareAccess
0x1800d0022  lea     r9, [rsp+238h+IoStatusBlock]; IoStatusBlock
0x1800d0027  mov     r8, r14; ObjectAttributes
0x1800d002a  mov     edx, 40100000h; DesiredAccess
0x1800d002f  lea     rcx, [rsp+238h+FileHandle]; FileHandle
0x1800d0034  call    cs:__imp_NtOpenFile
0x1800d003a  mov     ebx, eax
0x1800d003c  mov     [rsp+238h+var_208], eax
0x1800d0040  test    eax, eax
0x1800d0042  js      short loc_1800D007C
0x1800d0044  mov     rcx, [rdi]; Handle
0x1800d0047  call    cs:__imp_NtClose
0x1800d004d  mov     rcx, [rsp+238h+FileHandle]; FileHandle
0x1800d0052  mov     [rdi], rcx
0x1800d0055  mov     [rsp+238h+FileInformationClass], 24h ; '$'; FileInformationClass
0x1800d005d  mov     r9d, 30h ; '0'; Length
0x1800d0063  lea     r8, [rsp+238h+FileInformation]; FileInformation
0x1800d006b  lea     rdx, [rsp+238h+IoStatusBlock]; IoStatusBlock
0x1800d0070  call    cs:__imp_NtSetInformationFile
0x1800d0076  mov     ebx, eax
0x1800d0078  mov     [rsp+238h+var_208], eax
0x1800d007c  test    ebx, ebx
0x1800d007e  jns     short loc_1800D00D6
0x1800d0080  mov     dword ptr [rsp+238h+var_1A0], esi
0x1800d0087  mov     [rsp+238h+FileInformationClass], 4; FileInformationClass
0x1800d008f  mov     r9d, 28h ; '('; Length
0x1800d0095  lea     r8, [rsp+238h+var_1C0]; FileInformation
0x1800d009a  lea     rdx, [rsp+238h+IoStatusBlock]; IoStatusBlock
0x1800d009f  mov     rcx, [rdi]; FileHandle
0x1800d00a2  call    cs:__imp_NtSetInformationFile
0x1800d00a8  jmp     short loc_1800D00D6
0x1800d00aa  mov     [rsp+238h+var_190], 0
0x1800d00b5  jmp     loc_1800CFF05
0x1800d00ba  mov     ebx, 80000005h
0x1800d00bf  mov     [rsp+238h+var_208], ebx
0x1800d00c3  jmp     short loc_1800D00D6
0x1800d00c5  mov     eax, 32h ; '2'
0x1800d00ca  jmp     loc_1800CFE68
0x1800d00cf  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1800d00d6  mov     eax, ebx
0x1800d00d8  mov     rcx, [rsp+238h+var_38]
0x1800d00e0  xor     rcx, rsp; StackCookie
0x1800d00e3  call    __security_check_cookie
0x1800d00e8  add     rsp, 218h
0x1800d00ef  pop     r14
0x1800d00f1  pop     rdi
0x1800d00f2  pop     rsi
0x1800d00f3  pop     rbx
0x1800d00f4  retn
0x18018ba6c  push    rbp
0x18018ba6e  sub     rsp, 30h
0x18018ba72  mov     rbp, rdx
0x18018ba75  add     rsp, 30h
0x18018ba79  pop     rbp
0x18018ba7a  retn
```
