# AfdBuildDeviceAcl

- ea: `0x140049bd4`
- end: `0x140049d5b`
- name: `AfdBuildDeviceAcl`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x140049d64`

## callees

- `0x140003670`
- `0x140049bd4`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140049bee`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140049bee`
- `ntoskrnl!RtlMapGenericMask` at `0x140049c02`
- `ntoskrnl!RtlMapGenericMask` at `0x140049c02`
- `ntoskrnl!RtlLengthSid` at `0x140049c26`
- `ntoskrnl!RtlLengthSid` at `0x140049c37`
- `ntoskrnl!RtlLengthSid` at `0x140049c57`
- `ntoskrnl!RtlLengthSid` at `0x140049c26`
- `ntoskrnl!RtlLengthSid` at `0x140049c37`
- `ntoskrnl!RtlLengthSid` at `0x140049c57`
- `ntoskrnl!SeExports` at `0x140049c0e`
- `ntoskrnl!SeExports` at `0x140049c46`
- `ntoskrnl!SeExports` at `0x140049cca`
- `ntoskrnl!SeExports` at `0x140049cf1`
- `ntoskrnl!SeExports` at `0x140049d1b`
- `ntoskrnl!RtlCreateAcl` at `0x140049c9d`
- `ntoskrnl!RtlCreateAcl` at `0x140049c9d`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140049ce5`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140049d0f`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140049d39`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140049ce5`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140049d0f`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140049d39`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049cb7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049cb7`

## pseudocode

```c
__int64 __fastcall AfdBuildDeviceAcl(struct _ACL **a1)
{
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  PSID SeNetworkServiceSid; // rdi
  ULONG v4; // ebx
  ULONG v5; // edi
  struct _ACL *PoolPriority; // rax
  struct _ACL *v7; // rbx
  __int64 result; // rax
  NTSTATUS Acl; // edi
  DWORD AccessMask; // [rsp+38h] [rbp+10h] BYREF

  AccessMask = 0x10000000;
  FileObjectGenericMapping = IoGetFileObjectGenericMapping();
  RtlMapGenericMask(&AccessMask, FileObjectGenericMapping);
  SeNetworkServiceSid = SeExports->SeNetworkServiceSid;
  v4 = RtlLengthSid(SeExports->SeAliasAdminsSid);
  LODWORD(SeNetworkServiceSid) = RtlLengthSid(SeNetworkServiceSid) + v4;
  v5 = RtlLengthSid(SeExports->SeLocalSystemSid) + 32 + (_DWORD)SeNetworkServiceSid;
  PoolPriority = (struct _ACL *)AfdAllocatePoolPriority(256, v5, 1399088705, 32);
  v7 = PoolPriority;
  if ( !PoolPriority )
    return 3221225626LL;
  Acl = RtlCreateAcl(PoolPriority, v5, 2u);
  if ( Acl >= 0 )
  {
    RtlAddAccessAllowedAce(v7, 2u, AccessMask, SeExports->SeAliasAdminsSid);
    RtlAddAccessAllowedAce(v7, 2u, AccessMask, SeExports->SeLocalSystemSid);
    RtlAddAccessAllowedAce(v7, 2u, AccessMask, SeExports->SeNetworkServiceSid);
    result = 0;
    *a1 = v7;
  }
  else
  {
    ExFreePoolWithTag(v7, 0x53646641u);
    return (unsigned int)Acl;
  }
  return result;
}

```

## disassembly

```asm
0x140049bd4  mov     [rsp+arg_0], rbx
0x140049bd9  mov     [rsp+arg_10], rsi
0x140049bde  push    rdi
0x140049bdf  sub     rsp, 20h
0x140049be3  mov     rsi, rcx
0x140049be6  mov     [rsp+28h+AccessMask], 10000000h
0x140049bee  call    cs:__imp_IoGetFileObjectGenericMapping
0x140049bf5  nop     dword ptr [rax+rax+00h]
0x140049bfa  mov     rdx, rax; GenericMapping
0x140049bfd  lea     rcx, [rsp+28h+AccessMask]; AccessMask
0x140049c02  call    cs:__imp_RtlMapGenericMask
0x140049c09  nop     dword ptr [rax+rax+00h]
0x140049c0e  mov     rdx, cs:__imp_SeExports
0x140049c15  mov     rax, [rdx]
0x140049c18  mov     rcx, [rax+110h]; Sid
0x140049c1f  mov     rdi, [rax+188h]
0x140049c26  call    cs:__imp_RtlLengthSid
0x140049c2d  nop     dword ptr [rax+rax+00h]
0x140049c32  mov     rcx, rdi; Sid
0x140049c35  mov     ebx, eax
0x140049c37  call    cs:__imp_RtlLengthSid
0x140049c3e  nop     dword ptr [rax+rax+00h]
0x140049c43  lea     edi, [rax+rbx]
0x140049c46  mov     rax, cs:__imp_SeExports
0x140049c4d  mov     rcx, [rax]
0x140049c50  mov     rcx, [rcx+108h]; Sid
0x140049c57  call    cs:__imp_RtlLengthSid
0x140049c5e  nop     dword ptr [rax+rax+00h]
0x140049c63  mov     ecx, 100h
0x140049c68  mov     r9d, 20h ; ' '
0x140049c6e  add     eax, 20h ; ' '
0x140049c71  mov     r8d, 53646641h
0x140049c77  add     edi, eax
0x140049c79  mov     edx, edi
0x140049c7b  call    AfdAllocatePoolPriority
0x140049c80  mov     rbx, rax
0x140049c83  test    rax, rax
0x140049c86  jnz     short loc_140049C92
0x140049c88  mov     eax, 0C000009Ah
0x140049c8d  jmp     loc_140049D4A
0x140049c92  mov     r8d, 2; AclRevision
0x140049c98  mov     edx, edi; AclLength
0x140049c9a  mov     rcx, rbx; Acl
0x140049c9d  call    cs:__imp_RtlCreateAcl
0x140049ca4  nop     dword ptr [rax+rax+00h]
0x140049ca9  mov     edi, eax
0x140049cab  mov     rcx, rbx; Acl
0x140049cae  test    eax, eax
0x140049cb0  jns     short loc_140049CCA
0x140049cb2  mov     edx, 53646641h; Tag
0x140049cb7  call    cs:__imp_ExFreePoolWithTag
0x140049cbe  nop     dword ptr [rax+rax+00h]
0x140049cc3  mov     eax, edi
0x140049cc5  jmp     loc_140049D4A
0x140049cca  mov     rax, cs:__imp_SeExports
0x140049cd1  mov     edx, 2; AceRevision
0x140049cd6  mov     r8d, [rsp+28h+AccessMask]; AccessMask
0x140049cdb  mov     r9, [rax]
0x140049cde  mov     r9, [r9+110h]; Sid
0x140049ce5  call    cs:__imp_RtlAddAccessAllowedAce
0x140049cec  nop     dword ptr [rax+rax+00h]
0x140049cf1  mov     rax, cs:__imp_SeExports
0x140049cf8  mov     edx, 2; AceRevision
0x140049cfd  mov     r8d, [rsp+28h+AccessMask]; AccessMask
0x140049d02  mov     rcx, rbx; Acl
0x140049d05  mov     r9, [rax]
0x140049d08  mov     r9, [r9+108h]; Sid
0x140049d0f  call    cs:__imp_RtlAddAccessAllowedAce
0x140049d16  nop     dword ptr [rax+rax+00h]
0x140049d1b  mov     rax, cs:__imp_SeExports
0x140049d22  mov     edx, 2; AceRevision
0x140049d27  mov     r8d, [rsp+28h+AccessMask]; AccessMask
0x140049d2c  mov     rcx, rbx; Acl
0x140049d2f  mov     r9, [rax]
0x140049d32  mov     r9, [r9+188h]; Sid
0x140049d39  call    cs:__imp_RtlAddAccessAllowedAce
0x140049d40  nop     dword ptr [rax+rax+00h]
0x140049d45  xor     eax, eax
0x140049d47  mov     [rsi], rbx
0x140049d4a  mov     rbx, [rsp+28h+arg_0]
0x140049d4f  mov     rsi, [rsp+28h+arg_10]
0x140049d54  add     rsp, 20h
0x140049d58  pop     rdi
0x140049d59  retn
```
