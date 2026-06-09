# BiGetPartitionVhdFilePathFromUnicodeString

- ea: `0x140031550`
- end: `0x1400316ba`
- name: `BiGetPartitionVhdFilePathFromUnicodeString`
- size: `362`
- prototype: `ULONG *__fastcall(struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14002b48c`
- `0x140031520`

## callees

- `0x14000da0d`
- `0x14000da55`
- `0x14000db06`
- `0x14000db18`
- `0x140031550`
- `0x140031f94`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400315da`
- `ntoskrnl!ExAllocatePool2` at `0x1400315da`

## pseudocode

```c
ULONG *__fastcall BiGetPartitionVhdFilePathFromUnicodeString(struct _UNICODE_STRING *a1)
{
  ULONG *v1; // rbx
  ULONG OutputBufferLength; // edi
  int i; // esi
  ULONG *OutputBuffer; // rax
  NTSTATUS v5; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+17h] BYREF
  int InputBuffer; // [rsp+B0h] [rbp+67h] BYREF
  void *FileHandle; // [rsp+B8h] [rbp+6Fh] BYREF
  ULONG *v11; // [rsp+C0h] [rbp+77h]

  ObjectAttributes.ObjectName = a1;
  InputBuffer = 0;
  v11 = 0;
  FileHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  IoStatusBlock = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  v1 = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  if ( ZwOpenFile_0(&FileHandle, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u) >= 0 )
  {
    OutputBufferLength = 520;
    for ( i = 1; ; i = 2 )
    {
      OutputBuffer = (ULONG *)ExAllocatePool2(258, OutputBufferLength, 1262764866);
      v1 = OutputBuffer;
      if ( !OutputBuffer )
        break;
      InputBuffer = 1;
      v5 = ZwDeviceIoControlFile_0(
             FileHandle,
             0,
             0,
             0,
             &IoStatusBlock,
             0x2D5928u,
             &InputBuffer,
             4u,
             OutputBuffer,
             OutputBufferLength);
      if ( v5 != -1073741789 )
      {
        if ( v5 < 0 )
        {
LABEL_11:
          ExFreePoolWithTag_0(v1, 0x4B444342u);
          v1 = 0;
          break;
        }
        if ( (int)BiTranslateSymbolicLinkFile((PCWSTR)v1) >= 0 )
        {
          ExFreePoolWithTag_0(v1, 0x4B444342u);
          v1 = v11;
        }
        break;
      }
      if ( i != 1 )
        goto LABEL_11;
      OutputBufferLength = *v1;
      ExFreePoolWithTag_0(v1, 0x4B444342u);
    }
  }
  if ( FileHandle )
    ZwClose_0(FileHandle);
  return v1;
}

```

## disassembly

```asm
0x140031550  mov     [rsp-8+arg_18], rbx
0x140031555  push    rbp
0x140031556  push    rsi
0x140031557  push    rdi
0x140031558  lea     rbp, [rsp-47h]
0x14003155d  sub     rsp, 90h
0x140031564  xor     eax, eax
0x140031566  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x14003156a  xorps   xmm0, xmm0
0x14003156d  mov     [rsp+0A0h+OpenOptions], 20h ; ' '; OpenOptions
0x140031575  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140031579  mov     [rbp+57h+arg_0], eax
0x14003157c  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140031580  mov     [rbp+57h+arg_10], rax
0x140031584  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140031588  mov     [rbp+57h+FileHandle], rax
0x14003158c  mov     edx, 0C0100000h; DesiredAccess
0x140031591  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140031595  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140031599  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400315a1  xor     ebx, ebx
0x1400315a3  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400315a8  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400315b0  mov     [rsp+0A0h+ShareAccess], 3; ShareAccess
0x1400315b8  call    ZwOpenFile_0
0x1400315bd  test    eax, eax
0x1400315bf  js      loc_140031695
0x1400315c5  mov     edi, 208h
0x1400315ca  lea     esi, [rbx+1]
0x1400315cd  mov     edx, edi
0x1400315cf  mov     ecx, 102h
0x1400315d4  mov     r8d, 4B444342h
0x1400315da  call    cs:__imp_ExAllocatePool2
0x1400315e1  nop     dword ptr [rax+rax+00h]
0x1400315e6  mov     rbx, rax
0x1400315e9  test    rax, rax
0x1400315ec  jz      loc_140031681
0x1400315f2  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400315f6  xor     r9d, r9d; ApcContext
0x1400315f9  mov     [rsp+0A0h+OutputBufferLength], edi; OutputBufferLength
0x1400315fd  xor     r8d, r8d; ApcRoutine
0x140031600  mov     [rsp+0A0h+OutputBuffer], rax; OutputBuffer
0x140031605  xor     edx, edx; Event
0x140031607  mov     [rsp+0A0h+InputBufferLength], 4; InputBufferLength
0x14003160f  lea     rax, [rbp+57h+arg_0]
0x140031613  mov     [rsp+0A0h+InputBuffer], rax; InputBuffer
0x140031618  lea     rax, [rbp+57h+IoStatusBlock]
0x14003161c  mov     [rsp+0A0h+OpenOptions], 2D5928h; IoControlCode
0x140031624  mov     qword ptr [rsp+0A0h+ShareAccess], rax; IoStatusBlock
0x140031629  mov     [rbp+57h+arg_0], 1
0x140031630  call    ZwDeviceIoControlFile_0
0x140031635  cmp     eax, 0C0000023h
0x14003163a  jnz     short loc_14003165A
0x14003163c  cmp     esi, 1
0x14003163f  jnz     short loc_140031686
0x140031641  mov     edi, [rbx]
0x140031643  mov     edx, 4B444342h; Tag
0x140031648  mov     rcx, rbx; P
0x14003164b  call    ExFreePoolWithTag_0
0x140031650  mov     esi, 2
0x140031655  jmp     loc_1400315CD
0x14003165a  test    eax, eax
0x14003165c  js      short loc_140031686
0x14003165e  lea     rdx, [rbp+57h+arg_10]
0x140031662  mov     rcx, rbx; SourceString
0x140031665  call    BiTranslateSymbolicLinkFile
0x14003166a  test    eax, eax
0x14003166c  js      short loc_140031695
0x14003166e  mov     edx, 4B444342h; Tag
0x140031673  mov     rcx, rbx; P
0x140031676  call    ExFreePoolWithTag_0
0x14003167b  mov     rbx, [rbp+57h+arg_10]
0x14003167f  jmp     short loc_140031695
0x140031681  test    rbx, rbx
0x140031684  jz      short loc_140031695
0x140031686  mov     edx, 4B444342h; Tag
0x14003168b  mov     rcx, rbx; P
0x14003168e  call    ExFreePoolWithTag_0
0x140031693  xor     ebx, ebx
0x140031695  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140031699  test    rcx, rcx
0x14003169c  jz      short loc_1400316A3
0x14003169e  call    ZwClose_0
0x1400316a3  mov     rax, rbx
0x1400316a6  mov     rbx, [rsp+0A0h+arg_18]
0x1400316ae  add     rsp, 90h
0x1400316b5  pop     rdi
0x1400316b6  pop     rsi
0x1400316b7  pop     rbp
0x1400316b8  retn
```
