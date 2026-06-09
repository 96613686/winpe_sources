# SdbpGetFileTimestamp

- ea: `0x140041f78`
- end: `0x140042195`
- name: `SdbpGetFileTimestamp`
- size: `541`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path`

## callers

- `0x14002e934`
- `0x140041638`

## callees

- `0x14000440f`
- `0x140004469`
- `0x1400044e7`
- `0x14000450b`
- `0x1400079f0`
- `0x140007e40`
- `0x14003e364`
- `0x140041f78`

## import_xrefs

- `ntoskrnl!NtQueryInformationFile` at `0x140042138`
- `ntoskrnl!NtQueryInformationFile` at `0x140042138`

## string_xrefs

- `0x1400420f5`: `Failed to open file [%x]`

## pseudocode

```c
__int64 __fastcall SdbpGetFileTimestamp(_QWORD *a1, const WCHAR *a2, int a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v9; // rax
  __int64 v10; // rcx
  NTSTATUS v11; // eax
  NTSTATUS v12; // eax
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-58h] BYREF
  __int128 FileInformation; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v18; // [rsp+C8h] [rbp-38h]
  __int64 v19; // [rsp+D8h] [rbp-28h]
  _QWORD v20[10]; // [rsp+E0h] [rbp-20h] BYREF

  v19 = 0;
  FileHandle = 0;
  DestinationString = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  IoStatusBlock = 0;
  FileInformation = 0;
  v18 = 0;
  memset(v20, 0, 0x48u);
  RtlInitUnicodeString_0(&DestinationString, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  v6 = ZwQueryInformationByName_0(&ObjectAttributes, &IoStatusBlock, v20, 72, 68);
  v7 = v6;
  if ( v6 == -1073741772 )
    goto LABEL_2;
  if ( v6 >= 0 )
  {
    v9 = v20[4];
    v10 = v20[3];
LABEL_7:
    if ( a3 )
      v9 = v10;
    v7 = 0;
    *a1 = v9;
    goto LABEL_2;
  }
  v11 = ZwCreateFile_0(&FileHandle, 0x80100080, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 1u, 0x60u, 0, 0);
  v7 = v11;
  if ( v11 >= 0 )
  {
    v12 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
    v7 = v12;
    if ( v12 < 0 )
    {
      AslLogCallPrintf(1, "SdbpGetFileTimestamp", 1583, "Failed to get timestamp from %S. [%x]", a2, v12);
      goto LABEL_2;
    }
    v9 = *((_QWORD *)&v18 + 1);
    v10 = v18;
    *(_OWORD *)&v20[3] = v18;
    goto LABEL_7;
  }
  if ( v11 != -1073741772 )
    AslLogCallPrintf(1, "SdbpGetFileTimestamp", 1572, "Failed to open file [%x]", v11);
LABEL_2:
  if ( FileHandle )
    ZwClose_0(FileHandle);
  return v7;
}

```

## disassembly

```asm
0x140041f78  mov     [rsp-8+arg_10], rbx
0x140041f7d  mov     [rsp-8+arg_18], rsi
0x140041f82  push    rbp
0x140041f83  push    rdi
0x140041f84  push    r14
0x140041f86  lea     rbp, [rsp-40h]
0x140041f8b  sub     rsp, 140h
0x140041f92  mov     rax, cs:__security_cookie
0x140041f99  xor     rax, rsp
0x140041f9c  mov     [rbp+50h+var_20], rax
0x140041fa0  xorps   xmm0, xmm0
0x140041fa3  xor     eax, eax
0x140041fa5  xorps   xmm1, xmm1
0x140041fa8  mov     [rbp+50h+var_78], rax
0x140041fac  mov     esi, r8d
0x140041faf  mov     [rsp+150h+FileHandle], rax
0x140041fb4  mov     rdi, rdx
0x140041fb7  mov     r14, rcx
0x140041fba  lea     ebx, [rax+48h]
0x140041fbd  xor     edx, edx; Val
0x140041fbf  movups  xmmword ptr [rbp+50h+ObjectAttributes.ObjectName], xmm0
0x140041fc3  mov     r8d, ebx; Size
0x140041fc6  lea     rcx, [rbp+50h+var_70]; void *
0x140041fca  movups  xmmword ptr [rbp+50h+DestinationString.Length], xmm0
0x140041fce  movups  xmmword ptr [rsp+150h+ObjectAttributes.Length], xmm0
0x140041fd3  movups  xmmword ptr [rbp+50h+ObjectAttributes+1Ch], xmm0
0x140041fd7  movups  xmmword ptr [rsp+150h+IoStatusBlock], xmm0
0x140041fdc  movups  [rbp+50h+FileInformation], xmm1
0x140041fe0  movups  [rbp+50h+var_88], xmm1
0x140041fe4  call    memset
0x140041fe9  mov     rdx, rdi; SourceString
0x140041fec  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x140041ff0  call    RtlInitUnicodeString_0
0x140041ff5  lea     rax, [rbp+50h+DestinationString]
0x140041ff9  mov     [rsp+150h+ObjectAttributes.Length], 30h ; '0'
0x140042001  xorps   xmm0, xmm0
0x140042004  mov     [rbp+50h+ObjectAttributes.ObjectName], rax
0x140042008  mov     r9d, ebx
0x14004200b  mov     [rbp+50h+ObjectAttributes.RootDirectory], 0
0x140042013  lea     r8, [rbp+50h+var_70]
0x140042017  mov     [rbp+50h+ObjectAttributes.Attributes], 240h
0x14004201e  lea     rdx, [rsp+150h+IoStatusBlock]
0x140042023  mov     dword ptr [rsp+150h+AllocationSize], 44h ; 'D'
0x14004202b  lea     rcx, [rsp+150h+ObjectAttributes]
0x140042030  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x140042035  call    ZwQueryInformationByName_0
0x14004203a  mov     ebx, eax
0x14004203c  cmp     eax, 0C0000034h
0x140042041  jnz     short loc_140042078
0x140042043  mov     rcx, [rsp+150h+FileHandle]; Handle
0x140042048  test    rcx, rcx
0x14004204b  jnz     loc_14004218B
0x140042051  mov     eax, ebx
0x140042053  mov     rcx, [rbp+50h+var_20]
0x140042057  xor     rcx, rsp; StackCookie
0x14004205a  call    __security_check_cookie
0x14004205f  lea     r11, [rsp+150h+var_10]
0x140042067  mov     rbx, [r11+30h]
0x14004206b  mov     rsi, [r11+38h]
0x14004206f  mov     rsp, r11
0x140042072  pop     r14
0x140042074  pop     rdi
0x140042075  pop     rbp
0x140042076  retn
0x140042078  test    eax, eax
0x14004207a  js      short loc_140042091
0x14004207c  mov     rax, qword ptr [rbp+50h+var_58+8]
0x140042080  mov     rcx, qword ptr [rbp+50h+var_58]
0x140042084  test    esi, esi
0x140042086  cmovnz  rax, rcx
0x14004208a  xor     ebx, ebx
0x14004208c  mov     [r14], rax
0x14004208f  jmp     short loc_140042043
0x140042091  mov     [rsp+150h+EaLength], 0; EaLength
0x140042099  lea     r9, [rsp+150h+IoStatusBlock]; IoStatusBlock
0x14004209e  mov     [rsp+150h+EaBuffer], 0; EaBuffer
0x1400420a7  lea     r8, [rsp+150h+ObjectAttributes]; ObjectAttributes
0x1400420ac  mov     [rsp+150h+CreateOptions], 60h ; '`'; CreateOptions
0x1400420b4  lea     rcx, [rsp+150h+FileHandle]; FileHandle
0x1400420b9  mov     [rsp+150h+CreateDisposition], 1; CreateDisposition
0x1400420c1  mov     edx, 80100080h; DesiredAccess
0x1400420c6  mov     [rsp+150h+ShareAccess], 1; ShareAccess
0x1400420ce  mov     [rsp+150h+FileAttributes], 80h; FileAttributes
0x1400420d6  mov     [rsp+150h+AllocationSize], 0; AllocationSize
0x1400420df  call    ZwCreateFile_0
0x1400420e4  mov     ebx, eax
0x1400420e6  test    eax, eax
0x1400420e8  jns     short loc_14004211C
0x1400420ea  cmp     eax, 0C0000034h
0x1400420ef  jz      loc_140042043
0x1400420f5  lea     r9, aFailedToOpenFi; "Failed to open file [%x]"
0x1400420fc  mov     dword ptr [rsp+150h+AllocationSize], eax
0x140042100  mov     r8d, 624h
0x140042106  lea     rdx, aSdbpgetfiletim; "SdbpGetFileTimestamp"
0x14004210d  mov     ecx, 1
0x140042112  call    AslLogCallPrintf
0x140042117  jmp     loc_140042043
0x14004211c  mov     rcx, [rsp+150h+FileHandle]; FileHandle
0x140042121  lea     r8, [rbp+50h+FileInformation]; FileInformation
0x140042125  mov     r9d, 28h ; '('; Length
0x14004212b  mov     dword ptr [rsp+150h+AllocationSize], 4; FileInformationClass
0x140042133  lea     rdx, [rsp+150h+IoStatusBlock]; IoStatusBlock
0x140042138  call    cs:__imp_NtQueryInformationFile
0x14004213f  nop     dword ptr [rax+rax+00h]
0x140042144  mov     ebx, eax
0x140042146  test    eax, eax
0x140042148  jns     short loc_140042176
0x14004214a  mov     [rsp+150h+FileAttributes], eax
0x14004214e  lea     r9, aFailedToGetTim; "Failed to get timestamp from %S. [%x]"
0x140042155  mov     r8d, 62Fh
0x14004215b  mov     [rsp+150h+AllocationSize], rdi
0x140042160  lea     rdx, aSdbpgetfiletim; "SdbpGetFileTimestamp"
0x140042167  mov     ecx, 1
0x14004216c  call    AslLogCallPrintf
0x140042171  jmp     loc_140042043
0x140042176  mov     rcx, qword ptr [rbp+50h+var_88]
0x14004217a  mov     rax, qword ptr [rbp+50h+var_88+8]
0x14004217e  mov     qword ptr [rbp+50h+var_58], rcx
0x140042182  mov     qword ptr [rbp+50h+var_58+8], rax
0x140042186  jmp     loc_140042084
0x14004218b  call    ZwClose_0
0x140042190  jmp     loc_140042051
```
