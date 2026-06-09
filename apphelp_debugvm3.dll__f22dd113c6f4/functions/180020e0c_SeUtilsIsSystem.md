# SeUtilsIsSystem

- ea: `0x180020e0c`
- end: `0x180020ff6`
- name: `SeUtilsIsSystem`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180020a68`

## callees

- `0x180020e0c`
- `0x180021000`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180020ed3`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180020ed3`
- `ntdll!NtClose` at `0x180020e89`
- `ntdll!NtClose` at `0x180020e89`
- `ntdll!NtQuerySecurityObject` at `0x180020f47`
- `ntdll!NtQuerySecurityObject` at `0x180020f97`
- `ntdll!NtQuerySecurityObject` at `0x180020f47`
- `ntdll!NtQuerySecurityObject` at `0x180020f97`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x180020fb2`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x180020fb2`
- `ntdll!RtlEqualSid` at `0x180020fd2`
- `ntdll!RtlEqualSid` at `0x180020fd2`
- `ntdll!NtOpenFile` at `0x180020f20`
- `ntdll!NtOpenFile` at `0x180020f20`
- `ntdll!RtlFreeHeap` at `0x180020ea6`
- `ntdll!RtlFreeHeap` at `0x180020ea6`
- `ntdll!RtlFreeUnicodeString` at `0x180020e7a`
- `ntdll!RtlFreeUnicodeString` at `0x180020e7a`
- `ntdll!RtlAllocateHeap` at `0x180020f70`
- `ntdll!RtlAllocateHeap` at `0x180020f70`

## pseudocode

```c
__int64 __fastcall SeUtilsIsSystem(_DWORD *a1, wchar_t *a2, void *a3)
{
  PVOID Heap; // rdi
  NTSTATUS OwnerSecurityDescriptor; // ebx
  HANDLE Handle; // [rsp+30h] [rbp-19h] BYREF
  PSID Owner; // [rsp+38h] [rbp-11h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+17h] BYREF
  unsigned __int8 OwnerDefaulted; // [rsp+B0h] [rbp+67h] BYREF
  ULONG LengthNeeded; // [rsp+C8h] [rbp+7Fh] BYREF

  *a1 = 0;
  LengthNeeded = 0;
  OwnerDefaulted = 0;
  Owner = 0;
  memset(&ObjectAttributes, 0, 44);
  Handle = 0;
  Heap = 0;
  IoStatusBlock = 0;
  UnicodeString = 0;
  if ( (unsigned int)SeUtilsGetSystemMode(a2) == 4 )
  {
    *a1 = 1;
LABEL_3:
    OwnerSecurityDescriptor = 0;
    goto LABEL_4;
  }
  if ( RtlDosPathNameToNtPathName_U(a2, &UnicodeString, 0, 0) )
  {
    ObjectAttributes.ObjectName = &UnicodeString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    OwnerSecurityDescriptor = NtOpenFile(&Handle, 0x20000u, &ObjectAttributes, &IoStatusBlock, 5u, 0);
    if ( OwnerSecurityDescriptor >= 0 )
    {
      OwnerSecurityDescriptor = NtQuerySecurityObject(Handle, 1u, 0, 0, &LengthNeeded);
      if ( OwnerSecurityDescriptor == -1073741789 )
      {
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, LengthNeeded);
        if ( Heap )
        {
          OwnerSecurityDescriptor = NtQuerySecurityObject(Handle, 1u, Heap, LengthNeeded, &LengthNeeded);
          if ( OwnerSecurityDescriptor >= 0 )
          {
            OwnerSecurityDescriptor = RtlGetOwnerSecurityDescriptor(Heap, &Owner, &OwnerDefaulted);
            if ( OwnerSecurityDescriptor >= 0 )
            {
              if ( !Owner )
                goto LABEL_3;
              *a1 = RtlEqualSid(Owner, a3);
            }
          }
        }
        else
        {
          OwnerSecurityDescriptor = -1073741801;
        }
      }
    }
  }
  else
  {
    OwnerSecurityDescriptor = -1073741773;
  }
LABEL_4:
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( Handle )
    NtClose(Handle);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return (unsigned int)OwnerSecurityDescriptor;
}

```

## disassembly

```asm
0x180020e0c  mov     [rsp-8+arg_8], rbx
0x180020e11  mov     [rsp-8+arg_10], rsi
0x180020e16  push    rbp
0x180020e17  push    rdi
0x180020e18  push    r14
0x180020e1a  lea     rbp, [rsp-47h]
0x180020e1f  sub     rsp, 90h
0x180020e26  xor     eax, eax
0x180020e28  xorps   xmm0, xmm0
0x180020e2b  mov     [rcx], eax
0x180020e2d  mov     rsi, rcx
0x180020e30  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180020e34  mov     rcx, rdx; String1
0x180020e37  mov     [rbp+57h+LengthNeeded], eax
0x180020e3a  mov     r14, r8
0x180020e3d  mov     [rbp+57h+OwnerDefaulted], al
0x180020e40  mov     rbx, rdx
0x180020e43  mov     [rbp+57h+Owner], rax
0x180020e47  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180020e4b  mov     [rbp+57h+Handle], rax
0x180020e4f  xor     edi, edi
0x180020e51  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180020e55  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180020e59  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x180020e5d  call    SeUtilsGetSystemMode
0x180020e62  cmp     eax, 4
0x180020e65  jnz     short loc_180020EC6
0x180020e67  mov     dword ptr [rsi], 1
0x180020e6d  xor     ebx, ebx
0x180020e6f  cmp     [rbp+57h+UnicodeString.Buffer], 0
0x180020e74  jz      short loc_180020E80
0x180020e76  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x180020e7a  call    cs:__imp_RtlFreeUnicodeString
0x180020e80  mov     rcx, [rbp+57h+Handle]; Handle
0x180020e84  test    rcx, rcx
0x180020e87  jz      short loc_180020E8F
0x180020e89  call    cs:__imp_NtClose
0x180020e8f  test    rdi, rdi
0x180020e92  jz      short loc_180020EAC
0x180020e94  mov     rcx, gs:60h
0x180020e9d  mov     r8, rdi; P
0x180020ea0  xor     edx, edx; Flags
0x180020ea2  mov     rcx, [rcx+30h]; HeapHandle
0x180020ea6  call    cs:__imp_RtlFreeHeap
0x180020eac  lea     r11, [rsp+0A0h+var_10]
0x180020eb4  mov     eax, ebx
0x180020eb6  mov     rbx, [r11+28h]
0x180020eba  mov     rsi, [r11+30h]
0x180020ebe  mov     rsp, r11
0x180020ec1  pop     r14
0x180020ec3  pop     rdi
0x180020ec4  pop     rbp
0x180020ec5  retn
0x180020ec6  xor     r9d, r9d; DirectoryInfo
0x180020ec9  lea     rdx, [rbp+57h+UnicodeString]; NtPathName
0x180020ecd  xor     r8d, r8d; NtFileNamePart
0x180020ed0  mov     rcx, rbx; DosPathName
0x180020ed3  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180020ed9  test    al, al
0x180020edb  jz      loc_180020FE2
0x180020ee1  lea     rax, [rbp+57h+UnicodeString]
0x180020ee5  mov     [rsp+0A0h+OpenOptions], edi; OpenOptions
0x180020ee9  xorps   xmm0, xmm0
0x180020eec  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180020ef0  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180020ef4  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180020efb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180020eff  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x180020f03  mov     edx, 20000h; DesiredAccess
0x180020f08  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180020f0f  lea     rcx, [rbp+57h+Handle]; FileHandle
0x180020f13  mov     [rsp+0A0h+ShareAccess], 5; ShareAccess
0x180020f1b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180020f20  call    cs:__imp_NtOpenFile
0x180020f26  mov     ebx, eax
0x180020f28  test    eax, eax
0x180020f2a  js      loc_180020E6F
0x180020f30  mov     rcx, [rbp+57h+Handle]; Handle
0x180020f34  lea     rax, [rbp+57h+LengthNeeded]
0x180020f38  xor     r9d, r9d; Length
0x180020f3b  mov     qword ptr [rsp+0A0h+ShareAccess], rax; LengthNeeded
0x180020f40  xor     r8d, r8d; SecurityDescriptor
0x180020f43  lea     edx, [r9+1]; SecurityInformation
0x180020f47  call    cs:__imp_NtQuerySecurityObject
0x180020f4d  mov     ebx, eax
0x180020f4f  cmp     eax, 0C0000023h
0x180020f54  jnz     loc_180020E6F
0x180020f5a  mov     rcx, gs:60h
0x180020f63  mov     edx, 8; Flags
0x180020f68  mov     r8d, [rbp+57h+LengthNeeded]; Size
0x180020f6c  mov     rcx, [rcx+30h]; HeapHandle
0x180020f70  call    cs:__imp_RtlAllocateHeap
0x180020f76  mov     rdi, rax
0x180020f79  test    rax, rax
0x180020f7c  jz      short loc_180020FEC
0x180020f7e  mov     r9d, [rbp+57h+LengthNeeded]; Length
0x180020f82  lea     rax, [rbp+57h+LengthNeeded]
0x180020f86  mov     rcx, [rbp+57h+Handle]; Handle
0x180020f8a  mov     r8, rdi; SecurityDescriptor
0x180020f8d  mov     edx, 1; SecurityInformation
0x180020f92  mov     qword ptr [rsp+0A0h+ShareAccess], rax; LengthNeeded
0x180020f97  call    cs:__imp_NtQuerySecurityObject
0x180020f9d  mov     ebx, eax
0x180020f9f  test    eax, eax
0x180020fa1  js      loc_180020E6F
0x180020fa7  lea     r8, [rbp+57h+OwnerDefaulted]; OwnerDefaulted
0x180020fab  mov     rcx, rdi; SecurityDescriptor
0x180020fae  lea     rdx, [rbp+57h+Owner]; Owner
0x180020fb2  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x180020fb8  mov     ebx, eax
0x180020fba  test    eax, eax
0x180020fbc  js      loc_180020E6F
0x180020fc2  mov     rcx, [rbp+57h+Owner]; Sid1
0x180020fc6  test    rcx, rcx
0x180020fc9  jz      loc_180020E6D
0x180020fcf  mov     rdx, r14; Sid2
0x180020fd2  call    cs:__imp_RtlEqualSid
0x180020fd8  movzx   eax, al
0x180020fdb  mov     [rsi], eax
0x180020fdd  jmp     loc_180020E6F
0x180020fe2  mov     ebx, 0C0000033h
0x180020fe7  jmp     loc_180020E6F
0x180020fec  mov     ebx, 0C0000017h
0x180020ff1  jmp     loc_180020E6F
```
