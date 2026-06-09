# LocalOpenCurrentUserLocalSettings

- ea: `0x180101d60`
- end: `0x180101e8a`
- name: `LocalOpenCurrentUserLocalSettings`
- size: `298`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180101d60`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180101e59`
- `ntdll!RtlFreeUnicodeString` at `0x180101e63`
- `ntdll!RtlFreeUnicodeString` at `0x180101e59`
- `ntdll!RtlFreeUnicodeString` at `0x180101e63`
- `ntdll!RtlNtStatusToDosError` at `0x180101e6b`
- `ntdll!RtlNtStatusToDosError` at `0x180101e6b`
- `ntdll!NtCreateKey` at `0x180101e4d`
- `ntdll!NtCreateKey` at `0x180101e4d`
- `ntdll!RtlAppendUnicodeToString` at `0x180101df8`
- `ntdll!RtlAppendUnicodeToString` at `0x180101df8`
- `ntdll!RtlCopyUnicodeString` at `0x180101de7`
- `ntdll!RtlCopyUnicodeString` at `0x180101de7`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180101d98`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180101d98`
- `ntdll!RtlAllocateHeap` at `0x180101dcc`
- `ntdll!RtlAllocateHeap` at `0x180101dcc`

## pseudocode

```c
ULONG __fastcall LocalOpenCurrentUserLocalSettings(__int64 a1, ACCESS_MASK a2, HANDLE *a3)
{
  NTSTATUS v5; // eax
  NTSTATUS appended; // ebx
  NTSTATUS v7; // ecx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING KeyPath; // [rsp+50h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF

  memset(&ObjectAttributes, 0, 44);
  KeyPath = 0;
  DestinationString = 0;
  v5 = RtlFormatCurrentUserKeyPath(&KeyPath);
  if ( v5 < 0 )
  {
    v7 = v5;
  }
  else
  {
    DestinationString.MaximumLength = KeyPath.MaximumLength + 48;
    DestinationString.Buffer = (PWSTR)RtlAllocateHeap(
                                        NtCurrentPeb()->ProcessHeap,
                                        0,
                                        (unsigned __int16)(KeyPath.MaximumLength + 48));
    if ( DestinationString.Buffer )
    {
      RtlCopyUnicodeString(&DestinationString, &KeyPath);
      appended = RtlAppendUnicodeToString(&DestinationString, L"_Classes\\Local Settings");
      if ( appended >= 0 )
      {
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        ObjectAttributes.Attributes = 64;
        appended = NtCreateKey(a3, a2, &ObjectAttributes, 0, 0, 0, 0);
      }
    }
    else
    {
      appended = -1073741670;
    }
    RtlFreeUnicodeString(&KeyPath);
    RtlFreeUnicodeString(&DestinationString);
    v7 = appended;
  }
  return RtlNtStatusToDosError(v7);
}

```

## disassembly

```asm
0x180101d60  push    rbp
0x180101d62  push    rbx
0x180101d63  push    rsi
0x180101d64  push    rdi
0x180101d65  push    r15
0x180101d67  lea     rbp, [rsp-37h]
0x180101d6c  sub     rsp, 90h
0x180101d73  xorps   xmm0, xmm0
0x180101d76  lea     rcx, [rbp+57h+KeyPath]; KeyPath
0x180101d7a  xorps   xmm1, xmm1
0x180101d7d  xor     eax, eax
0x180101d7f  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180101d83  mov     rdi, r8
0x180101d86  mov     esi, edx
0x180101d88  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180101d8c  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180101d90  movups  xmmword ptr [rbp+57h+KeyPath.Length], xmm0
0x180101d94  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x180101d98  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x180101d9e  test    eax, eax
0x180101da0  js      loc_180101E86
0x180101da6  movzx   eax, [rbp+57h+KeyPath.MaximumLength]
0x180101daa  mov     r15d, 30h ; '0'
0x180101db0  add     ax, r15w
0x180101db4  xor     edx, edx; Flags
0x180101db6  movzx   r8d, ax; Size
0x180101dba  mov     [rbp+57h+DestinationString.MaximumLength], r8w
0x180101dbf  mov     rcx, gs:60h
0x180101dc8  mov     rcx, [rcx+30h]; HeapHandle
0x180101dcc  call    cs:__imp_RtlAllocateHeap
0x180101dd2  mov     [rbp+57h+DestinationString.Buffer], rax
0x180101dd6  test    rax, rax
0x180101dd9  jz      loc_180101E7F
0x180101ddf  lea     rdx, [rbp+57h+KeyPath]; SourceString
0x180101de3  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180101de7  call    cs:__imp_RtlCopyUnicodeString
0x180101ded  lea     rdx, aClassesLocalSe; "_Classes\\Local Settings"
0x180101df4  lea     rcx, [rbp+57h+DestinationString]; Destination
0x180101df8  call    cs:__imp_RtlAppendUnicodeToString
0x180101dfe  mov     ebx, eax
0x180101e00  test    eax, eax
0x180101e02  js      short loc_180101E55
0x180101e04  lea     rax, [rbp+57h+DestinationString]
0x180101e08  mov     [rsp+0B0h+Disposition], 0; Disposition
0x180101e11  xorps   xmm0, xmm0
0x180101e14  mov     [rsp+0B0h+CreateOptions], 0; CreateOptions
0x180101e1c  xor     r9d, r9d; TitleIndex
0x180101e1f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180101e23  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180101e27  mov     [rsp+0B0h+Class], 0; Class
0x180101e30  mov     edx, esi; DesiredAccess
0x180101e32  mov     [rbp+57h+ObjectAttributes.Length], r15d
0x180101e36  mov     rcx, rdi; KeyHandle
0x180101e39  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180101e41  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180101e46  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180101e4d  call    cs:__imp_NtCreateKey
0x180101e53  mov     ebx, eax
0x180101e55  lea     rcx, [rbp+57h+KeyPath]; UnicodeString
0x180101e59  call    cs:__imp_RtlFreeUnicodeString
0x180101e5f  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x180101e63  call    cs:__imp_RtlFreeUnicodeString
0x180101e69  mov     ecx, ebx; Status
0x180101e6b  call    cs:__imp_RtlNtStatusToDosError
0x180101e71  add     rsp, 90h
0x180101e78  pop     r15
0x180101e7a  pop     rdi
0x180101e7b  pop     rsi
0x180101e7c  pop     rbx
0x180101e7d  pop     rbp
0x180101e7e  retn
0x180101e7f  mov     ebx, 0C000009Ah
0x180101e84  jmp     short loc_180101E55
0x180101e86  mov     ecx, eax
0x180101e88  jmp     short loc_180101E6B
```
