# CfpCreateFile

- ea: `0x18000446c`
- end: `0x180004589`
- name: `CfpCreateFile`
- size: `285`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003be0`
- `0x180004ac0`
- `0x180006060`
- `0x1800073b0`
- `0x1800079c0`
- `0x18000d7b0`
- `0x18000f7c4`
- `0x1800106c0`

## callees

- `0x18000446c`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18000454b`
- `ntdll!NtCreateFile` at `0x18000454b`
- `ntdll!RtlFreeUnicodeString` at `0x180004566`
- `ntdll!RtlFreeUnicodeString` at `0x180004566`
- `ntdll!RtlDosLongPathNameToNtPathName_U_WithStatus` at `0x1800044c0`
- `ntdll!RtlDosLongPathNameToNtPathName_U_WithStatus` at `0x1800044c0`
- `ntdll!RtlNtStatusToDosError` at `0x1800044ca`
- `ntdll!RtlNtStatusToDosError` at `0x180004555`
- `ntdll!RtlNtStatusToDosError` at `0x1800044ca`
- `ntdll!RtlNtStatusToDosError` at `0x180004555`

## pseudocode

```c
__int64 __fastcall CfpCreateFile(
        __int64 a1,
        __int64 a2,
        ACCESS_MASK a3,
        ULONG a4,
        __int64 a5,
        ULONG CreateOptions,
        __int64 a7,
        void **FileHandle)
{
  ACCESS_MASK v9; // edi
  int v10; // ebx
  signed int v11; // eax
  struct _UNICODE_STRING UnicodeString; // [rsp+60h] [rbp-51h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-41h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-31h] BYREF

  v9 = a3;
  IoStatusBlock = 0;
  UnicodeString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( !a3 || (CreateOptions & 0x30) != 0 )
    v9 = a3 | 0x100000;
  v10 = RtlDosLongPathNameToNtPathName_U_WithStatus(a1, &UnicodeString, 0, 0);
  v11 = RtlNtStatusToDosError(v10);
  if ( v11 > 0 )
    v11 = (unsigned __int16)v11 | 0x80070000;
  if ( v11 >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &UnicodeString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v10 = NtCreateFile(FileHandle, v9, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, a4, 1u, CreateOptions, 0, 0);
    RtlNtStatusToDosError(v10);
  }
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( v10 < 0 )
    *FileHandle = (void *)-1LL;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000446c  push    rbp
0x18000446e  push    rbx
0x18000446f  push    rsi
0x180004470  push    rdi
0x180004471  push    r14
0x180004473  push    r15
0x180004475  lea     rbp, [rsp-7]
0x18000447a  sub     rsp, 0B8h
0x180004481  mov     r14d, [rbp+2Fh+arg_28]
0x180004485  xorps   xmm0, xmm0
0x180004488  xor     eax, eax
0x18000448a  xorps   xmm1, xmm1
0x18000448d  mov     r15d, r9d
0x180004490  mov     edi, r8d
0x180004493  movups  xmmword ptr [rbp+2Fh+ObjectAttributes.ObjectName], xmm0
0x180004497  movups  xmmword ptr [rbp+2Fh+ObjectAttributes+1Ch], xmm0
0x18000449b  movups  xmmword ptr [rbp+2Fh+IoStatusBlock], xmm0
0x18000449f  movups  xmmword ptr [rbp+2Fh+UnicodeString.Length], xmm1
0x1800044a3  movups  xmmword ptr [rbp+2Fh+ObjectAttributes.Length], xmm0
0x1800044a7  test    r8d, r8d
0x1800044aa  jz      short loc_1800044B2
0x1800044ac  test    r14b, 30h
0x1800044b0  jz      short loc_1800044B6
0x1800044b2  bts     edi, 14h
0x1800044b6  xor     r9d, r9d
0x1800044b9  lea     rdx, [rbp+2Fh+UnicodeString]
0x1800044bd  xor     r8d, r8d
0x1800044c0  call    cs:__imp_RtlDosLongPathNameToNtPathName_U_WithStatus
0x1800044c6  mov     ecx, eax; Status
0x1800044c8  mov     ebx, eax
0x1800044ca  call    cs:__imp_RtlNtStatusToDosError
0x1800044d0  test    eax, eax
0x1800044d2  jle     short loc_1800044DC
0x1800044d4  movzx   eax, ax
0x1800044d7  or      eax, 80070000h
0x1800044dc  mov     rsi, [rbp+2Fh+FileHandle]
0x1800044e0  test    eax, eax
0x1800044e2  js      short loc_18000455B
0x1800044e4  mov     [rsp+0E0h+EaLength], 0; EaLength
0x1800044ec  lea     rax, [rbp+2Fh+UnicodeString]
0x1800044f0  mov     [rsp+0E0h+EaBuffer], 0; EaBuffer
0x1800044f9  lea     r9, [rbp+2Fh+IoStatusBlock]; IoStatusBlock
0x1800044fd  mov     [rsp+0E0h+CreateOptions], r14d; CreateOptions
0x180004502  lea     r8, [rbp+2Fh+ObjectAttributes]; ObjectAttributes
0x180004506  mov     [rsp+0E0h+CreateDisposition], 1; CreateDisposition
0x18000450e  xorps   xmm0, xmm0
0x180004511  mov     [rsp+0E0h+ShareAccess], r15d; ShareAccess
0x180004516  mov     edx, edi; DesiredAccess
0x180004518  mov     [rsp+0E0h+FileAttributes], 80h; FileAttributes
0x180004520  mov     rcx, rsi; FileHandle
0x180004523  mov     [rsp+0E0h+AllocationSize], 0; AllocationSize
0x18000452c  mov     [rbp+2Fh+ObjectAttributes.Length], 30h ; '0'
0x180004533  mov     [rbp+2Fh+ObjectAttributes.RootDirectory], 0
0x18000453b  mov     [rbp+2Fh+ObjectAttributes.Attributes], 40h ; '@'
0x180004542  mov     [rbp+2Fh+ObjectAttributes.ObjectName], rax
0x180004546  movdqu  xmmword ptr [rbp+2Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18000454b  call    cs:__imp_NtCreateFile
0x180004551  mov     ecx, eax; Status
0x180004553  mov     ebx, eax
0x180004555  call    cs:__imp_RtlNtStatusToDosError
0x18000455b  cmp     [rbp+2Fh+UnicodeString.Buffer], 0
0x180004560  jz      short loc_18000456C
0x180004562  lea     rcx, [rbp+2Fh+UnicodeString]; UnicodeString
0x180004566  call    cs:__imp_RtlFreeUnicodeString
0x18000456c  test    ebx, ebx
0x18000456e  jns     short loc_180004577
0x180004570  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180004577  mov     eax, ebx
0x180004579  add     rsp, 0B8h
0x180004580  pop     r15
0x180004582  pop     r14
0x180004584  pop     rdi
0x180004585  pop     rsi
0x180004586  pop     rbx
0x180004587  pop     rbp
0x180004588  retn
```
