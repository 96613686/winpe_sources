# BiCreateSystemStorePath

- ea: `0x1400200a0`
- end: `0x1400201e3`
- name: `BiCreateSystemStorePath`
- size: `323`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001a964`

## callees

- `0x14001c3a8`
- `0x14001c508`
- `0x14001ff78`
- `0x1400200a0`

## import_xrefs

- `ntdll!ZwClose` at `0x1400201ca`
- `ntdll!ZwClose` at `0x1400201ca`
- `ntdll!RtlFreeHeap` at `0x14002019b`
- `ntdll!RtlFreeHeap` at `0x1400201bb`
- `ntdll!RtlFreeHeap` at `0x14002019b`
- `ntdll!RtlFreeHeap` at `0x1400201bb`
- `ntdll!RtlInitUnicodeString` at `0x1400200f4`
- `ntdll!RtlInitUnicodeString` at `0x1400200f4`
- `ntdll!ZwOpenFile` at `0x140020141`
- `ntdll!ZwOpenFile` at `0x140020141`

## pseudocode

```c
__int64 BiCreateSystemStorePath()
{
  int SystemStorePathComponents; // ebx
  BOOL v1; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  PCWSTR SourceString; // [rsp+90h] [rbp+10h] BYREF
  PVOID P; // [rsp+98h] [rbp+18h] BYREF
  void *FileHandle; // [rsp+A0h] [rbp+20h] BYREF

  P = 0;
  SourceString = 0;
  IoStatusBlock = 0;
  FileHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  SystemStorePathComponents = BiGetSystemStorePathComponents(&SourceString, &P);
  if ( SystemStorePathComponents >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    SystemStorePathComponents = ZwOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 3u, 0x11u);
    if ( SystemStorePathComponents >= 0 )
    {
      v1 = BiGetFirmwareType(0) == 1;
      SystemStorePathComponents = BiCreateDirectoryPath(FileHandle, (const wchar_t *)P, v1 ? 6 : 128);
    }
  }
  if ( SourceString )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)SourceString);
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)SystemStorePathComponents;
}

```

## disassembly

```asm
0x1400200a0  mov     [rsp-8+arg_18], rbx
0x1400200a5  push    rbp
0x1400200a6  mov     rbp, rsp
0x1400200a9  sub     rsp, 80h
0x1400200b0  xorps   xmm0, xmm0
0x1400200b3  lea     rdx, [rbp+P]
0x1400200b7  xor     eax, eax
0x1400200b9  lea     rcx, [rbp+SourceString]
0x1400200bd  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1400200c1  mov     [rbp+P], rax
0x1400200c5  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1400200c9  mov     [rbp+SourceString], rax
0x1400200cd  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x1400200d1  mov     [rbp+FileHandle], rax
0x1400200d5  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400200d9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400200dd  call    BiGetSystemStorePathComponents
0x1400200e2  mov     ebx, eax
0x1400200e4  test    eax, eax
0x1400200e6  js      loc_140020181
0x1400200ec  mov     rdx, [rbp+SourceString]; SourceString
0x1400200f0  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400200f4  call    cs:__imp_RtlInitUnicodeString
0x1400200fa  lea     rax, [rbp+DestinationString]
0x1400200fe  mov     [rsp+80h+OpenOptions], 11h; OpenOptions
0x140020106  xorps   xmm0, xmm0
0x140020109  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14002010d  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x140020111  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140020118  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14002011c  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140020124  mov     edx, 100001h; DesiredAccess
0x140020129  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x140020130  lea     rcx, [rbp+FileHandle]; FileHandle
0x140020134  mov     [rsp+80h+ShareAccess], 3; ShareAccess
0x14002013c  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140020141  call    cs:__imp_ZwOpenFile
0x140020147  mov     ebx, eax
0x140020149  test    eax, eax
0x14002014b  js      short loc_140020181
0x14002014d  xor     ecx, ecx
0x14002014f  call    BiGetFirmwareType
0x140020154  sub     eax, 1
0x140020157  jz      short loc_140020160
0x140020159  sub     eax, 1
0x14002015c  xor     eax, eax
0x14002015e  jmp     short loc_140020165
0x140020160  mov     eax, 1
0x140020165  mov     rdx, [rbp+P]
0x140020169  neg     eax
0x14002016b  mov     rcx, [rbp+FileHandle]
0x14002016f  sbb     r8d, r8d
0x140020172  and     r8d, 0FFFFFF86h
0x140020176  sub     r8d, 0FFFFFF80h
0x14002017a  call    BiCreateDirectoryPath
0x14002017f  mov     ebx, eax
0x140020181  cmp     [rbp+SourceString], 0
0x140020186  jz      short loc_1400201A1
0x140020188  mov     rcx, gs:60h
0x140020191  xor     edx, edx; Flags
0x140020193  mov     r8, [rbp+SourceString]; P
0x140020197  mov     rcx, [rcx+30h]; HeapHandle
0x14002019b  call    cs:__imp_RtlFreeHeap
0x1400201a1  cmp     [rbp+P], 0
0x1400201a6  jz      short loc_1400201C1
0x1400201a8  mov     rcx, gs:60h
0x1400201b1  xor     edx, edx; Flags
0x1400201b3  mov     r8, [rbp+P]; P
0x1400201b7  mov     rcx, [rcx+30h]; HeapHandle
0x1400201bb  call    cs:__imp_RtlFreeHeap
0x1400201c1  mov     rcx, [rbp+FileHandle]; Handle
0x1400201c5  test    rcx, rcx
0x1400201c8  jz      short loc_1400201D0
0x1400201ca  call    cs:__imp_ZwClose
0x1400201d0  mov     eax, ebx
0x1400201d2  mov     rbx, [rsp+80h+arg_18]
0x1400201da  add     rsp, 80h
0x1400201e1  pop     rbp
0x1400201e2  retn
```
