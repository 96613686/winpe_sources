# StorageReserveHelper::Internal::GetHandle(ushort const *,void * *)

- ea: `0x18002d1b4`
- end: `0x18002d335`
- name: `?GetHandle@Internal@StorageReserveHelper@@YAJPEBGPEAPEAX@Z`
- size: `385`
- prototype: `__int64 __fastcall(const WCHAR *this, void **, void **)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002980c`
- `0x18002d5a4`
- `0x18002df1c`

## callees

- `0x180003870`
- `0x18000a0f4`
- `0x180023308`
- `0x18002d1b4`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18002d224`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18002d224`
- `ntdll!NtCreateFile` at `0x18002d2ce`
- `ntdll!NtCreateFile` at `0x18002d2ce`
- `ntdll!RtlFreeUnicodeString` at `0x18002d256`
- `ntdll!RtlFreeUnicodeString` at `0x18002d310`
- `ntdll!RtlFreeUnicodeString` at `0x18002d256`
- `ntdll!RtlFreeUnicodeString` at `0x18002d310`

## pseudocode

```c
__int64 __fastcall StorageReserveHelper::Internal::GetHandle(const WCHAR *this, void **a2, void **a3)
{
  unsigned int v4; // ebx
  __int64 v6; // rdx
  NTSTATUS v7; // eax
  unsigned int v8; // r8d
  int AllocationSize; // [rsp+20h] [rbp-49h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-9h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+90h] [rbp+27h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  NtPathName = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
      (const char *)0x80070057LL,
      AllocationSize);
    return v4;
  }
  if ( !RtlDosPathNameToNtPathName_U(this, &NtPathName, 0, 0) )
  {
    v4 = -2147467259;
    v6 = 106;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
      (const char *)v4,
      AllocationSize);
    goto LABEL_7;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtPathName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = NtCreateFile(a2, 0x100180u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x20u, 0, 0);
  if ( v7 < 0 )
  {
    v4 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x7C,
           v8,
           (const char *)(unsigned int)v7,
           AllocationSize);
LABEL_7:
    if ( NtPathName.Buffer )
      RtlFreeUnicodeString(&NtPathName);
    return v4;
  }
  if ( *a2 == (void *)-1LL )
  {
    v4 = -2147024890;
    v6 = 127;
    goto LABEL_6;
  }
  if ( NtPathName.Buffer )
    RtlFreeUnicodeString(&NtPathName);
  return 0;
}

```

## disassembly

```asm
0x18002d1b4  mov     [rsp-8+arg_10], rbx
0x18002d1b9  push    rbp
0x18002d1ba  lea     rbp, [rsp-57h]
0x18002d1bf  sub     rsp, 0C0h
0x18002d1c6  mov     rax, cs:__security_cookie
0x18002d1cd  xor     rax, rsp
0x18002d1d0  mov     [rbp+57h+var_10], rax
0x18002d1d4  xorps   xmm1, xmm1
0x18002d1d7  xorps   xmm0, xmm0
0x18002d1da  mov     rbx, rdx
0x18002d1dd  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x18002d1e1  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x18002d1e5  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18002d1e9  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x18002d1ed  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18002d1f1  test    rdx, rdx
0x18002d1f4  jnz     short loc_18002D21A
0x18002d1f6  mov     rcx, [rbp+5Fh]; this
0x18002d1fa  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18002d201  mov     ebx, 80070057h
0x18002d206  mov     edx, 5Dh ; ']'; void *
0x18002d20b  mov     r9d, ebx; char *
0x18002d20e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d213  mov     eax, ebx
0x18002d215  jmp     loc_18002D318
0x18002d21a  xor     r9d, r9d; DirectoryInfo
0x18002d21d  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x18002d221  xor     r8d, r8d; NtFileNamePart
0x18002d224  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18002d22a  test    al, al
0x18002d22c  jnz     short loc_18002D25E
0x18002d22e  mov     ebx, 80004005h
0x18002d233  mov     edx, 6Ah ; 'j'; void *
0x18002d238  mov     rcx, [rbp+5Fh]; this
0x18002d23c  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18002d243  mov     r9d, ebx; char *
0x18002d246  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d24b  cmp     [rbp+57h+NtPathName.Buffer], 0
0x18002d250  jz      short loc_18002D213
0x18002d252  lea     rcx, [rbp+57h+NtPathName]; UnicodeString
0x18002d256  call    cs:__imp_RtlFreeUnicodeString
0x18002d25c  jmp     short loc_18002D213
0x18002d25e  mov     [rsp+0C0h+EaLength], 0; EaLength
0x18002d266  lea     rax, [rbp+57h+NtPathName]
0x18002d26a  mov     [rsp+0C0h+EaBuffer], 0; EaBuffer
0x18002d273  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18002d277  mov     [rsp+0C0h+CreateOptions], 20h ; ' '; CreateOptions
0x18002d27f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002d283  mov     [rsp+0C0h+CreateDisposition], 1; CreateDisposition
0x18002d28b  xorps   xmm0, xmm0
0x18002d28e  mov     [rsp+0C0h+ShareAccess], 7; ShareAccess
0x18002d296  mov     edx, 100180h; DesiredAccess
0x18002d29b  mov     [rsp+0C0h+FileAttributes], 80h; FileAttributes
0x18002d2a3  mov     rcx, rbx; FileHandle
0x18002d2a6  mov     [rsp+0C0h+AllocationSize], 0; int
0x18002d2af  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18002d2b6  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18002d2be  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18002d2c5  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18002d2c9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002d2ce  call    cs:__imp_NtCreateFile
0x18002d2d4  test    eax, eax
0x18002d2d6  jns     short loc_18002D2F0
0x18002d2d8  mov     rcx, [rbp+5Fh]; this
0x18002d2dc  mov     r9d, eax; char *
0x18002d2df  mov     edx, 7Ch ; '|'; void *
0x18002d2e4  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002d2e9  mov     ebx, eax
0x18002d2eb  jmp     loc_18002D24B
0x18002d2f0  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18002d2f4  jnz     short loc_18002D305
0x18002d2f6  mov     ebx, 80070006h
0x18002d2fb  mov     edx, 7Fh
0x18002d300  jmp     loc_18002D238
0x18002d305  cmp     [rbp+57h+NtPathName.Buffer], 0
0x18002d30a  jz      short loc_18002D316
0x18002d30c  lea     rcx, [rbp+57h+NtPathName]; UnicodeString
0x18002d310  call    cs:__imp_RtlFreeUnicodeString
0x18002d316  xor     eax, eax
0x18002d318  mov     rcx, [rbp+57h+var_10]
0x18002d31c  xor     rcx, rsp; StackCookie
0x18002d31f  call    __security_check_cookie
0x18002d324  mov     rbx, [rsp+0C0h+arg_10]
0x18002d32c  add     rsp, 0C0h
0x18002d333  pop     rbp
0x18002d334  retn
```
