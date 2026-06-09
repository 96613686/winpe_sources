# CompatCachepFileOpen

- ea: `0x18002b238`
- end: `0x18002b431`
- name: `CompatCachepFileOpen`
- size: `505`
- prototype: `__int64 __fastcall(PHANDLE FileHandle, PWSTR FileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002ade4`

## callees

- `0x18002b238`
- `0x180039a1e`
- `0x180039a2a`
- `0x180039a36`
- `0x180039a66`

## import_xrefs

- `ntdll!RtlGetFullPathName_UEx` at `0x18002b2d0`
- `ntdll!RtlGetFullPathName_UEx` at `0x18002b2d0`
- `ntdll!RtlInitUnicodeString` at `0x18002b28b`
- `ntdll!RtlInitUnicodeString` at `0x18002b28b`
- `ntdll!NtCreateFile` at `0x18002b37b`
- `ntdll!NtCreateFile` at `0x18002b37b`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18002b3d9`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18002b3d9`

## pseudocode

```c
__int64 __fastcall CompatCachepFileOpen(PHANDLE FileHandle, PWSTR FileName)
{
  char v3; // r14
  RTL_PATH_TYPE v5; // esi
  WCHAR *Heap_0; // rdi
  NTSTATUS FullPathName_UEx; // ebx
  bool v8; // cf
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+7h] BYREF
  RTL_PATH_TYPE InputPathType; // [rsp+E0h] [rbp+67h] BYREF

  *FileHandle = 0;
  InputPathType = RtlPathTypeUnknown;
  v3 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  RtlInitUnicodeString(&DestinationString, FileName);
  v5 = 520;
  while ( 1 )
  {
    Heap_0 = (WCHAR *)RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)v5);
    if ( !Heap_0 )
    {
      FullPathName_UEx = -1073741801;
      goto LABEL_8;
    }
    FullPathName_UEx = RtlGetFullPathName_UEx(FileName, v5, Heap_0, 0, &InputPathType);
    if ( FullPathName_UEx < 0 )
      goto LABEL_8;
    v8 = InputPathType < (unsigned int)v5;
    if ( InputPathType > (unsigned int)v5 )
    {
      if ( v3 )
      {
        FullPathName_UEx = -1073741789;
        goto LABEL_8;
      }
      RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, Heap_0);
      Heap_0 = 0;
      v5 = InputPathType;
      v8 = 0;
    }
    if ( v8 )
      break;
    v3 = 1;
  }
  if ( !wcsnicmp_0(Heap_0, L"\\SystemRoot\\", 0xCu)
    || (FullPathName_UEx = RtlDosPathNameToNtPathName_U_WithStatus(Heap_0, &DestinationString, 0, 0),
        FullPathName_UEx >= 0) )
  {
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    FullPathName_UEx = NtCreateFile(
                         FileHandle,
                         0x80100080,
                         &ObjectAttributes,
                         &IoStatusBlock,
                         0,
                         0x80u,
                         1u,
                         1u,
                         0x60u,
                         0,
                         0);
  }
LABEL_8:
  if ( DestinationString.Buffer != FileName )
    RtlFreeUnicodeString_0(&DestinationString);
  if ( Heap_0 )
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, Heap_0);
  return (unsigned int)FullPathName_UEx;
}

```

## disassembly

```asm
0x18002b238  mov     [rsp-8+arg_8], rbx
0x18002b23d  mov     [rsp-8+arg_10], rsi
0x18002b242  push    rbp
0x18002b243  push    rdi
0x18002b244  push    r12
0x18002b246  push    r14
0x18002b248  push    r15
0x18002b24a  lea     rbp, [rsp-37h]
0x18002b24f  sub     rsp, 0B0h
0x18002b256  xorps   xmm1, xmm1
0x18002b259  mov     qword ptr [rcx], 0
0x18002b260  xorps   xmm0, xmm0
0x18002b263  mov     [rbp+57h+arg_0], 0
0x18002b26a  mov     r12, rcx
0x18002b26d  xor     r14b, r14b
0x18002b270  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18002b274  mov     r15, rdx
0x18002b277  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18002b27b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x18002b27f  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18002b283  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x18002b287  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18002b28b  call    cs:__imp_RtlInitUnicodeString
0x18002b291  mov     esi, 208h
0x18002b296  mov     rcx, gs:60h
0x18002b29f  mov     edx, 8; Flags
0x18002b2a4  mov     r8d, esi; Size
0x18002b2a7  mov     rcx, [rcx+30h]; HeapHandle
0x18002b2ab  call    RtlAllocateHeap_0
0x18002b2b0  mov     rdi, rax
0x18002b2b3  test    rax, rax
0x18002b2b6  jz      loc_18002B427
0x18002b2bc  lea     rax, [rbp+57h+arg_0]
0x18002b2c0  xor     r9d, r9d; FilePart
0x18002b2c3  mov     r8, rdi; Buffer
0x18002b2c6  mov     [rsp+0D0h+InputPathType], rax; InputPathType
0x18002b2cb  mov     edx, esi; BufferLength
0x18002b2cd  mov     rcx, r15; FileName
0x18002b2d0  call    cs:__imp_RtlGetFullPathName_UEx
0x18002b2d6  mov     ebx, eax
0x18002b2d8  test    eax, eax
0x18002b2da  js      loc_18002B383
0x18002b2e0  mov     eax, [rbp+57h+arg_0]
0x18002b2e3  cmp     eax, esi
0x18002b2e5  ja      loc_18002B3F3
0x18002b2eb  jnb     loc_18002B3EB
0x18002b2f1  mov     r8d, 0Ch; MaxCount
0x18002b2f7  lea     rdx, aSystemroot_3; "\\SystemRoot\\"
0x18002b2fe  mov     rcx, rdi; String1
0x18002b301  call    _wcsnicmp_0
0x18002b306  test    eax, eax
0x18002b308  jnz     loc_18002B3CC
0x18002b30e  mov     [rsp+0D0h+EaLength], 0; EaLength
0x18002b316  lea     rax, [rbp+57h+DestinationString]
0x18002b31a  mov     [rsp+0D0h+EaBuffer], 0; EaBuffer
0x18002b323  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18002b327  mov     [rsp+0D0h+CreateOptions], 60h ; '`'; CreateOptions
0x18002b32f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002b333  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18002b337  xorps   xmm0, xmm0
0x18002b33a  mov     eax, 1
0x18002b33f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18002b346  mov     [rsp+0D0h+CreateDisposition], eax; CreateDisposition
0x18002b34a  mov     edx, 80100080h; DesiredAccess
0x18002b34f  mov     [rsp+0D0h+ShareAccess], eax; ShareAccess
0x18002b353  mov     rcx, r12; FileHandle
0x18002b356  mov     [rsp+0D0h+FileAttributes], 80h; FileAttributes
0x18002b35e  mov     [rsp+0D0h+InputPathType], 0; AllocationSize
0x18002b367  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18002b36f  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18002b376  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002b37b  call    cs:__imp_NtCreateFile
0x18002b381  mov     ebx, eax
0x18002b383  cmp     [rbp+57h+DestinationString.Buffer], r15
0x18002b387  jz      short loc_18002B392
0x18002b389  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x18002b38d  call    RtlFreeUnicodeString_0
0x18002b392  test    rdi, rdi
0x18002b395  jz      short loc_18002B3AE
0x18002b397  mov     rcx, gs:60h
0x18002b3a0  mov     r8, rdi; P
0x18002b3a3  xor     edx, edx; Flags
0x18002b3a5  mov     rcx, [rcx+30h]; HeapHandle
0x18002b3a9  call    RtlFreeHeap_0
0x18002b3ae  lea     r11, [rsp+0D0h+var_20]
0x18002b3b6  mov     eax, ebx
0x18002b3b8  mov     rbx, [r11+38h]
0x18002b3bc  mov     rsi, [r11+40h]
0x18002b3c0  mov     rsp, r11
0x18002b3c3  pop     r15
0x18002b3c5  pop     r14
0x18002b3c7  pop     r12
0x18002b3c9  pop     rdi
0x18002b3ca  pop     rbp
0x18002b3cb  retn
0x18002b3cc  xor     r9d, r9d
0x18002b3cf  lea     rdx, [rbp+57h+DestinationString]
0x18002b3d3  xor     r8d, r8d
0x18002b3d6  mov     rcx, rdi
0x18002b3d9  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18002b3df  mov     ebx, eax
0x18002b3e1  test    eax, eax
0x18002b3e3  jns     loc_18002B30E
0x18002b3e9  jmp     short loc_18002B383
0x18002b3eb  mov     r14b, 1
0x18002b3ee  jmp     loc_18002B296
0x18002b3f3  test    r14b, r14b
0x18002b3f6  jnz     short loc_18002B41D
0x18002b3f8  mov     rcx, gs:60h
0x18002b401  mov     r8, rdi; P
0x18002b404  xor     edx, edx; Flags
0x18002b406  mov     rcx, [rcx+30h]; HeapHandle
0x18002b40a  call    RtlFreeHeap_0
0x18002b40f  mov     eax, [rbp+57h+arg_0]
0x18002b412  xor     edi, edi
0x18002b414  mov     esi, eax
0x18002b416  cmp     eax, eax
0x18002b418  jmp     loc_18002B2EB
0x18002b41d  mov     ebx, 0C0000023h
0x18002b422  jmp     loc_18002B383
0x18002b427  mov     ebx, 0C0000017h
0x18002b42c  jmp     loc_18002B383
```
