# StorageReserveHelper::Internal::GetHandle(ushort const *,void * *)

- ea: `0x1800db6fc`
- end: `0x1800db87d`
- name: `?GetHandle@Internal@StorageReserveHelper@@YAJPEBGPEAPEAX@Z`
- size: `385`
- prototype: `int(StorageReserveHelper::Internal *__hidden this, const unsigned __int16 *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800dab04`
- `0x1800db884`

## callees

- `0x180006e50`
- `0x18000e6cc`
- `0x1800db6fc`
- `0x1800db964`

## import_xrefs

- `ntdll!NtCreateFile` at `0x1800db816`
- `ntdll!NtCreateFile` at `0x1800db816`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800db76c`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800db76c`
- `ntdll!RtlFreeUnicodeString` at `0x1800db79e`
- `ntdll!RtlFreeUnicodeString` at `0x1800db858`
- `ntdll!RtlFreeUnicodeString` at `0x1800db79e`
- `ntdll!RtlFreeUnicodeString` at `0x1800db858`

## pseudocode

```c
__int64 __fastcall StorageReserveHelper::Internal::GetHandle(const WCHAR *this, void **a2, void **a3)
{
  unsigned int v4; // ebx
  __int64 v6; // rdx
  NTSTATUS v7; // eax
  unsigned int v8; // r8d
  int AllocationSize; // [rsp+20h] [rbp-49h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-9h] BYREF
  _UNICODE_STRING NtPathName; // [rsp+90h] [rbp+27h] BYREF
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
0x1800db6fc  mov     [rsp-8+arg_10], rbx
0x1800db701  push    rbp
0x1800db702  lea     rbp, [rsp-57h]
0x1800db707  sub     rsp, 0C0h
0x1800db70e  mov     rax, cs:__security_cookie
0x1800db715  xor     rax, rsp
0x1800db718  mov     [rbp+57h+var_10], rax
0x1800db71c  xorps   xmm1, xmm1
0x1800db71f  xorps   xmm0, xmm0
0x1800db722  mov     rbx, rdx
0x1800db725  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x1800db729  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x1800db72d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x1800db731  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800db735  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800db739  test    rdx, rdx
0x1800db73c  jnz     short loc_1800DB762
0x1800db73e  mov     rcx, [rbp+5Fh]; this
0x1800db742  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800db749  mov     ebx, 80070057h
0x1800db74e  mov     edx, 5Dh ; ']'; void *
0x1800db753  mov     r9d, ebx; char *
0x1800db756  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800db75b  mov     eax, ebx
0x1800db75d  jmp     loc_1800DB860
0x1800db762  xor     r9d, r9d; DirectoryInfo
0x1800db765  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x1800db769  xor     r8d, r8d; NtFileNamePart
0x1800db76c  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800db772  test    al, al
0x1800db774  jnz     short loc_1800DB7A6
0x1800db776  mov     ebx, 80004005h
0x1800db77b  mov     edx, 6Ah ; 'j'; void *
0x1800db780  mov     rcx, [rbp+5Fh]; this
0x1800db784  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800db78b  mov     r9d, ebx; char *
0x1800db78e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800db793  cmp     [rbp+57h+NtPathName.Buffer], 0
0x1800db798  jz      short loc_1800DB75B
0x1800db79a  lea     rcx, [rbp+57h+NtPathName]; UnicodeString
0x1800db79e  call    cs:__imp_RtlFreeUnicodeString
0x1800db7a4  jmp     short loc_1800DB75B
0x1800db7a6  mov     [rsp+0C0h+EaLength], 0; EaLength
0x1800db7ae  lea     rax, [rbp+57h+NtPathName]
0x1800db7b2  mov     [rsp+0C0h+EaBuffer], 0; EaBuffer
0x1800db7bb  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800db7bf  mov     [rsp+0C0h+CreateOptions], 20h ; ' '; CreateOptions
0x1800db7c7  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800db7cb  mov     [rsp+0C0h+CreateDisposition], 1; CreateDisposition
0x1800db7d3  xorps   xmm0, xmm0
0x1800db7d6  mov     [rsp+0C0h+ShareAccess], 7; ShareAccess
0x1800db7de  mov     edx, 100180h; DesiredAccess
0x1800db7e3  mov     [rsp+0C0h+FileAttributes], 80h; FileAttributes
0x1800db7eb  mov     rcx, rbx; FileHandle
0x1800db7ee  mov     [rsp+0C0h+AllocationSize], 0; int
0x1800db7f7  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800db7fe  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800db806  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800db80d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800db811  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800db816  call    cs:__imp_NtCreateFile
0x1800db81c  test    eax, eax
0x1800db81e  jns     short loc_1800DB838
0x1800db820  mov     rcx, [rbp+5Fh]; this
0x1800db824  mov     r9d, eax; char *
0x1800db827  mov     edx, 7Ch ; '|'; void *
0x1800db82c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800db831  mov     ebx, eax
0x1800db833  jmp     loc_1800DB793
0x1800db838  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1800db83c  jnz     short loc_1800DB84D
0x1800db83e  mov     ebx, 80070006h
0x1800db843  mov     edx, 7Fh
0x1800db848  jmp     loc_1800DB780
0x1800db84d  cmp     [rbp+57h+NtPathName.Buffer], 0
0x1800db852  jz      short loc_1800DB85E
0x1800db854  lea     rcx, [rbp+57h+NtPathName]; UnicodeString
0x1800db858  call    cs:__imp_RtlFreeUnicodeString
0x1800db85e  xor     eax, eax
0x1800db860  mov     rcx, [rbp+57h+var_10]
0x1800db864  xor     rcx, rsp; StackCookie
0x1800db867  call    __security_check_cookie
0x1800db86c  mov     rbx, [rsp+0C0h+arg_10]
0x1800db874  add     rsp, 0C0h
0x1800db87b  pop     rbp
0x1800db87c  retn
```
