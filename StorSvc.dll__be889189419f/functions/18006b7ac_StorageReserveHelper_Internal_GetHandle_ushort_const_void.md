# StorageReserveHelper::Internal::GetHandle(ushort const *,void * *)

- ea: `0x18006b7ac`
- end: `0x18006b928`
- name: `?GetHandle@Internal@StorageReserveHelper@@YAJPEBGPEAPEAX@Z`
- size: `380`
- prototype: `__int64 __fastcall(const WCHAR *this, void **, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006a788`

## callees

- `0x18000d030`
- `0x180012734`
- `0x18006b7ac`
- `0x18006b930`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18006b81c`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18006b81c`
- `ntdll!NtCreateFile` at `0x18006b8c6`
- `ntdll!NtCreateFile` at `0x18006b8c6`
- `ntdll!RtlFreeUnicodeString` at `0x18006b84e`
- `ntdll!RtlFreeUnicodeString` at `0x18006b903`
- `ntdll!RtlFreeUnicodeString` at `0x18006b84e`
- `ntdll!RtlFreeUnicodeString` at `0x18006b903`

## pseudocode

```c
__int64 __fastcall StorageReserveHelper::Internal::GetHandle(const WCHAR *this, void **a2, void **a3)
{
  unsigned int v4; // ebx
  __int64 v6; // rdx
  NTSTATUS v7; // eax
  void *v8; // rdx
  unsigned int v9; // r8d
  int AllocationSize; // [rsp+20h] [rbp-49h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-9h] BYREF
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
    v4 = wil::details::in1diag3::Return_NtStatus(retaddr, v8, v9, (const char *)(unsigned int)v7, AllocationSize);
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
0x18006b7ac  mov     [rsp-8+arg_10], rbx
0x18006b7b1  push    rbp
0x18006b7b2  lea     rbp, [rsp-57h]
0x18006b7b7  sub     rsp, 0C0h
0x18006b7be  mov     rax, cs:__security_cookie
0x18006b7c5  xor     rax, rsp
0x18006b7c8  mov     [rbp+57h+var_10], rax
0x18006b7cc  xorps   xmm1, xmm1
0x18006b7cf  xorps   xmm0, xmm0
0x18006b7d2  mov     rbx, rdx
0x18006b7d5  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x18006b7d9  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x18006b7dd  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18006b7e1  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x18006b7e5  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18006b7e9  test    rdx, rdx
0x18006b7ec  jnz     short loc_18006B812
0x18006b7ee  mov     rcx, [rbp+5Fh]; this
0x18006b7f2  lea     r8, aOnecoreDrivers_3; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18006b7f9  mov     ebx, 80070057h
0x18006b7fe  mov     edx, 5Dh ; ']'; void *
0x18006b803  mov     r9d, ebx; char *
0x18006b806  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b80b  mov     eax, ebx
0x18006b80d  jmp     loc_18006B90B
0x18006b812  xor     r9d, r9d; DirectoryInfo
0x18006b815  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x18006b819  xor     r8d, r8d; NtFileNamePart
0x18006b81c  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18006b822  test    al, al
0x18006b824  jnz     short loc_18006B856
0x18006b826  mov     ebx, 80004005h
0x18006b82b  mov     edx, 6Ah ; 'j'; void *
0x18006b830  mov     rcx, [rbp+5Fh]; this
0x18006b834  lea     r8, aOnecoreDrivers_3; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18006b83b  mov     r9d, ebx; char *
0x18006b83e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b843  cmp     [rbp+57h+NtPathName.Buffer], 0
0x18006b848  jz      short loc_18006B80B
0x18006b84a  lea     rcx, [rbp+57h+NtPathName]; UnicodeString
0x18006b84e  call    cs:__imp_RtlFreeUnicodeString
0x18006b854  jmp     short loc_18006B80B
0x18006b856  mov     [rsp+0C0h+EaLength], 0; EaLength
0x18006b85e  lea     rax, [rbp+57h+NtPathName]
0x18006b862  mov     [rsp+0C0h+EaBuffer], 0; EaBuffer
0x18006b86b  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18006b86f  mov     [rsp+0C0h+CreateOptions], 20h ; ' '; CreateOptions
0x18006b877  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18006b87b  mov     [rsp+0C0h+CreateDisposition], 1; CreateDisposition
0x18006b883  xorps   xmm0, xmm0
0x18006b886  mov     [rsp+0C0h+ShareAccess], 7; ShareAccess
0x18006b88e  mov     edx, 100180h; DesiredAccess
0x18006b893  mov     [rsp+0C0h+FileAttributes], 80h; FileAttributes
0x18006b89b  mov     rcx, rbx; FileHandle
0x18006b89e  mov     [rsp+0C0h+AllocationSize], 0; int
0x18006b8a7  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18006b8ae  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18006b8b6  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18006b8bd  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18006b8c1  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006b8c6  call    cs:__imp_NtCreateFile
0x18006b8cc  test    eax, eax
0x18006b8ce  jns     short loc_18006B8E3
0x18006b8d0  mov     rcx, [rbp+5Fh]; this
0x18006b8d4  mov     r9d, eax; char *
0x18006b8d7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18006b8dc  mov     ebx, eax
0x18006b8de  jmp     loc_18006B843
0x18006b8e3  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18006b8e7  jnz     short loc_18006B8F8
0x18006b8e9  mov     ebx, 80070006h
0x18006b8ee  mov     edx, 7Fh
0x18006b8f3  jmp     loc_18006B830
0x18006b8f8  cmp     [rbp+57h+NtPathName.Buffer], 0
0x18006b8fd  jz      short loc_18006B909
0x18006b8ff  lea     rcx, [rbp+57h+NtPathName]; UnicodeString
0x18006b903  call    cs:__imp_RtlFreeUnicodeString
0x18006b909  xor     eax, eax
0x18006b90b  mov     rcx, [rbp+57h+var_10]
0x18006b90f  xor     rcx, rsp; StackCookie
0x18006b912  call    __security_check_cookie
0x18006b917  mov     rbx, [rsp+0C0h+arg_10]
0x18006b91f  add     rsp, 0C0h
0x18006b926  pop     rbp
0x18006b927  retn
```
