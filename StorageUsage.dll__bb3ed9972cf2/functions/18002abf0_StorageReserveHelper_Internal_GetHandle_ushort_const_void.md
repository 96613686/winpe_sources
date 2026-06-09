# StorageReserveHelper::Internal::GetHandle(ushort const *,void * *)

- ea: `0x18002abf0`
- end: `0x18002ad78`
- name: `?GetHandle@Internal@StorageReserveHelper@@YAJPEBGPEAPEAX@Z`
- size: `392`
- prototype: `__int64 __fastcall(const WCHAR *this, void **, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002834c`

## callees

- `0x1800050f0`
- `0x1800152d4`
- `0x18001b528`
- `0x18002abf0`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18002ac92`
- `ntdll!RtlFreeUnicodeString` at `0x18002ad53`
- `ntdll!RtlFreeUnicodeString` at `0x18002ac92`
- `ntdll!RtlFreeUnicodeString` at `0x18002ad53`
- `ntdll!NtCreateFile` at `0x18002ad0a`
- `ntdll!NtCreateFile` at `0x18002ad0a`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18002ac60`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18002ac60`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StorageReserveHelper::Internal::GetHandle(const WCHAR *this, void **a2, void **a3)
{
  unsigned int v4; // ebx
  __int64 v6; // rdx
  NTSTATUS v7; // eax
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
           (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
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
0x18002abf0  mov     [rsp-8+arg_10], rbx
0x18002abf5  push    rbp
0x18002abf6  lea     rbp, [rsp-57h]
0x18002abfb  sub     rsp, 0C0h
0x18002ac02  mov     rax, cs:__security_cookie
0x18002ac09  xor     rax, rsp
0x18002ac0c  mov     [rbp+57h+var_10], rax
0x18002ac10  xorps   xmm1, xmm1
0x18002ac13  xorps   xmm0, xmm0
0x18002ac16  mov     rbx, rdx
0x18002ac19  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x18002ac1d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x18002ac21  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18002ac25  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x18002ac29  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18002ac2d  test    rdx, rdx
0x18002ac30  jnz     short loc_18002AC56
0x18002ac32  mov     rcx, [rbp+5Fh]; this
0x18002ac36  lea     r8, aOnecoreDrivers_0; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18002ac3d  mov     ebx, 80070057h
0x18002ac42  mov     edx, 5Dh ; ']'; void *
0x18002ac47  mov     r9d, ebx; char *
0x18002ac4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ac4f  mov     eax, ebx
0x18002ac51  jmp     loc_18002AD5B
0x18002ac56  xor     r9d, r9d; DirectoryInfo
0x18002ac59  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x18002ac5d  xor     r8d, r8d; NtFileNamePart
0x18002ac60  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18002ac66  test    al, al
0x18002ac68  jnz     short loc_18002AC9A
0x18002ac6a  mov     ebx, 80004005h
0x18002ac6f  mov     edx, 6Ah ; 'j'; void *
0x18002ac74  mov     rcx, [rbp+5Fh]; this
0x18002ac78  lea     r8, aOnecoreDrivers_0; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18002ac7f  mov     r9d, ebx; char *
0x18002ac82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ac87  cmp     [rbp+57h+NtPathName.Buffer], 0
0x18002ac8c  jz      short loc_18002AC4F
0x18002ac8e  lea     rcx, [rbp+57h+NtPathName]; UnicodeString
0x18002ac92  call    cs:__imp_RtlFreeUnicodeString
0x18002ac98  jmp     short loc_18002AC4F
0x18002ac9a  mov     [rsp+0C0h+EaLength], 0; EaLength
0x18002aca2  lea     rax, [rbp+57h+NtPathName]
0x18002aca6  mov     [rsp+0C0h+EaBuffer], 0; EaBuffer
0x18002acaf  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18002acb3  mov     [rsp+0C0h+CreateOptions], 20h ; ' '; CreateOptions
0x18002acbb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002acbf  mov     [rsp+0C0h+CreateDisposition], 1; CreateDisposition
0x18002acc7  xorps   xmm0, xmm0
0x18002acca  mov     [rsp+0C0h+ShareAccess], 7; ShareAccess
0x18002acd2  mov     edx, 100180h; DesiredAccess
0x18002acd7  mov     [rsp+0C0h+FileAttributes], 80h; FileAttributes
0x18002acdf  mov     rcx, rbx; FileHandle
0x18002ace2  mov     [rsp+0C0h+AllocationSize], 0; int
0x18002aceb  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18002acf2  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18002acfa  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18002ad01  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18002ad05  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002ad0a  call    cs:__imp_NtCreateFile
0x18002ad10  test    eax, eax
0x18002ad12  jns     short loc_18002AD33
0x18002ad14  mov     rcx, [rbp+5Fh]; this
0x18002ad18  lea     r8, aOnecoreDrivers_0; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18002ad1f  mov     r9d, eax; char *
0x18002ad22  mov     edx, 7Ch ; '|'; void *
0x18002ad27  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002ad2c  mov     ebx, eax
0x18002ad2e  jmp     loc_18002AC87
0x18002ad33  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18002ad37  jnz     short loc_18002AD48
0x18002ad39  mov     ebx, 80070006h
0x18002ad3e  mov     edx, 7Fh
0x18002ad43  jmp     loc_18002AC74
0x18002ad48  cmp     [rbp+57h+NtPathName.Buffer], 0
0x18002ad4d  jz      short loc_18002AD59
0x18002ad4f  lea     rcx, [rbp+57h+NtPathName]; UnicodeString
0x18002ad53  call    cs:__imp_RtlFreeUnicodeString
0x18002ad59  xor     eax, eax
0x18002ad5b  mov     rcx, [rbp+57h+var_10]
0x18002ad5f  xor     rcx, rsp; StackCookie
0x18002ad62  call    __security_check_cookie
0x18002ad67  mov     rbx, [rsp+0C0h+arg_10]
0x18002ad6f  add     rsp, 0C0h
0x18002ad76  pop     rbp
0x18002ad77  retn
```
