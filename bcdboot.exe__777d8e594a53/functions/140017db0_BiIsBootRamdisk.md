# BiIsBootRamdisk

- ea: `0x140017db0`
- end: `0x140017ede`
- name: `BiIsBootRamdisk`
- size: `302`
- prototype: `char __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x140015160`

## callees

- `0x140017db0`
- `0x1400265fa`

## import_xrefs

- `ntdll!ZwDeviceIoControlFile` at `0x140017e99`
- `ntdll!ZwDeviceIoControlFile` at `0x140017e99`
- `ntdll!ZwClose` at `0x140017ea5`
- `ntdll!ZwClose` at `0x140017ea5`
- `ntdll!RtlInitUnicodeString` at `0x140017e07`
- `ntdll!RtlInitUnicodeString` at `0x140017e07`
- `ntdll!ZwOpenFile` at `0x140017e54`
- `ntdll!ZwOpenFile` at `0x140017e54`

## pseudocode

```c
char __fastcall BiIsBootRamdisk(_QWORD *a1)
{
  char v2; // di
  NTSTATUS v3; // ebx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-59h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-19h] BYREF
  _BYTE OutputBuffer[20]; // [rsp+A0h] [rbp-9h] BYREF
  int v9; // [rsp+B4h] [rbp+Bh]
  __int64 v10; // [rsp+C0h] [rbp+17h]
  __int64 v11; // [rsp+D0h] [rbp+27h]
  void *FileHandle; // [rsp+118h] [rbp+6Fh] BYREF

  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  IoStatusBlock = 0;
  memset_0(OutputBuffer, 0, 0x40u);
  FileHandle = 0;
  v2 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\Ramdisk{d9b257fc-684e-4dcb-ab79-03cfa2f6b750}");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  if ( ZwOpenFile(&FileHandle, 0xC0000000, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u) >= 0 )
  {
    v3 = ZwDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x240008u, 0, 0, OutputBuffer, 0x40u);
    ZwClose(FileHandle);
    if ( v3 >= 0 && (v9 == 3 || *a1 == v11 << 12 && a1[1] == v10) )
      return 1;
  }
  return v2;
}

```

## disassembly

```asm
0x140017db0  push    rbp
0x140017db2  push    rbx
0x140017db3  push    rsi
0x140017db4  push    rdi
0x140017db5  lea     rbp, [rsp-3Fh]
0x140017dba  sub     rsp, 0E8h
0x140017dc1  xorps   xmm0, xmm0
0x140017dc4  xor     eax, eax
0x140017dc6  mov     rsi, rcx
0x140017dc9  xor     edx, edx; Val
0x140017dcb  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140017dcf  lea     rcx, [rbp+57h+var_60]; void *
0x140017dd3  lea     ebx, [rax+40h]
0x140017dd6  mov     r8d, ebx; Size
0x140017dd9  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140017ddd  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140017de1  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140017de5  call    memset_0
0x140017dea  xorps   xmm0, xmm0
0x140017ded  mov     [rbp+57h+FileHandle], 0
0x140017df5  lea     rdx, aDeviceRamdiskD; "\\Device\\Ramdisk{d9b257fc-684e-4dcb-ab"...
0x140017dfc  xor     dil, dil
0x140017dff  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140017e03  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140017e07  call    cs:__imp_RtlInitUnicodeString
0x140017e0d  lea     rax, [rbp+57h+DestinationString]
0x140017e11  mov     [rsp+100h+OpenOptions], 20h ; ' '; OpenOptions
0x140017e19  xorps   xmm0, xmm0
0x140017e1c  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140017e20  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140017e24  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140017e2b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140017e2f  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140017e37  mov     edx, 0C0000000h; DesiredAccess
0x140017e3c  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140017e43  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140017e47  mov     [rsp+100h+ShareAccess], 3; ShareAccess
0x140017e4f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140017e54  call    cs:__imp_ZwOpenFile
0x140017e5a  test    eax, eax
0x140017e5c  js      short loc_140017ECF
0x140017e5e  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140017e62  lea     rax, [rbp+57h+var_60]
0x140017e66  mov     [rsp+100h+OutputBufferLength], ebx; OutputBufferLength
0x140017e6a  xor     r9d, r9d; ApcContext
0x140017e6d  mov     [rsp+100h+OutputBuffer], rax; OutputBuffer
0x140017e72  xor     r8d, r8d; ApcRoutine
0x140017e75  mov     [rsp+100h+InputBufferLength], 0; InputBufferLength
0x140017e7d  lea     rax, [rbp+57h+IoStatusBlock]
0x140017e81  mov     [rsp+100h+InputBuffer], 0; InputBuffer
0x140017e8a  xor     edx, edx; Event
0x140017e8c  mov     [rsp+100h+OpenOptions], 240008h; IoControlCode
0x140017e94  mov     qword ptr [rsp+100h+ShareAccess], rax; IoStatusBlock
0x140017e99  call    cs:__imp_ZwDeviceIoControlFile
0x140017e9f  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140017ea3  mov     ebx, eax
0x140017ea5  call    cs:__imp_ZwClose
0x140017eab  test    ebx, ebx
0x140017ead  js      short loc_140017ECF
0x140017eaf  cmp     [rbp+57h+var_4C], 3
0x140017eb3  jz      short loc_140017ECC
0x140017eb5  mov     rax, [rbp+57h+var_30]
0x140017eb9  shl     rax, 0Ch
0x140017ebd  cmp     [rsi], rax
0x140017ec0  jnz     short loc_140017ECF
0x140017ec2  mov     rax, [rbp+57h+var_40]
0x140017ec6  cmp     [rsi+8], rax
0x140017eca  jnz     short loc_140017ECF
0x140017ecc  mov     dil, 1
0x140017ecf  mov     al, dil
0x140017ed2  add     rsp, 0E8h
0x140017ed9  pop     rdi
0x140017eda  pop     rsi
0x140017edb  pop     rbx
0x140017edc  pop     rbp
0x140017edd  retn
```
