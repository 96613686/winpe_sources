# AfdBuildDeviceAcl

- ea: `0x140049b34`
- end: `0x140049cbb`
- name: `AfdBuildDeviceAcl`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x140049cc4`

## callees

- `0x140003670`
- `0x140049b34`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140049b4e`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140049b4e`
- `ntoskrnl!RtlMapGenericMask` at `0x140049b62`
- `ntoskrnl!RtlMapGenericMask` at `0x140049b62`
- `ntoskrnl!RtlLengthSid` at `0x140049b86`
- `ntoskrnl!RtlLengthSid` at `0x140049b97`
- `ntoskrnl!RtlLengthSid` at `0x140049bb7`
- `ntoskrnl!RtlLengthSid` at `0x140049b86`
- `ntoskrnl!RtlLengthSid` at `0x140049b97`
- `ntoskrnl!RtlLengthSid` at `0x140049bb7`
- `ntoskrnl!SeExports` at `0x140049b6e`
- `ntoskrnl!SeExports` at `0x140049ba6`
- `ntoskrnl!SeExports` at `0x140049c2a`
- `ntoskrnl!SeExports` at `0x140049c51`
- `ntoskrnl!SeExports` at `0x140049c7b`
- `ntoskrnl!RtlCreateAcl` at `0x140049bfd`
- `ntoskrnl!RtlCreateAcl` at `0x140049bfd`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140049c45`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140049c6f`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140049c99`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140049c45`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140049c6f`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140049c99`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049c17`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049c17`

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
0x140049b34  mov     [rsp+arg_0], rbx
0x140049b39  mov     [rsp+arg_10], rsi
0x140049b3e  push    rdi
0x140049b3f  sub     rsp, 20h
0x140049b43  mov     rsi, rcx
0x140049b46  mov     [rsp+28h+AccessMask], 10000000h
0x140049b4e  call    cs:__imp_IoGetFileObjectGenericMapping
0x140049b55  nop     dword ptr [rax+rax+00h]
0x140049b5a  mov     rdx, rax; GenericMapping
0x140049b5d  lea     rcx, [rsp+28h+AccessMask]; AccessMask
0x140049b62  call    cs:__imp_RtlMapGenericMask
0x140049b69  nop     dword ptr [rax+rax+00h]
0x140049b6e  mov     rdx, cs:__imp_SeExports
0x140049b75  mov     rax, [rdx]
0x140049b78  mov     rcx, [rax+110h]; Sid
0x140049b7f  mov     rdi, [rax+188h]
0x140049b86  call    cs:__imp_RtlLengthSid
0x140049b8d  nop     dword ptr [rax+rax+00h]
0x140049b92  mov     rcx, rdi; Sid
0x140049b95  mov     ebx, eax
0x140049b97  call    cs:__imp_RtlLengthSid
0x140049b9e  nop     dword ptr [rax+rax+00h]
0x140049ba3  lea     edi, [rax+rbx]
0x140049ba6  mov     rax, cs:__imp_SeExports
0x140049bad  mov     rcx, [rax]
0x140049bb0  mov     rcx, [rcx+108h]; Sid
0x140049bb7  call    cs:__imp_RtlLengthSid
0x140049bbe  nop     dword ptr [rax+rax+00h]
0x140049bc3  mov     ecx, 100h
0x140049bc8  mov     r9d, 20h ; ' '
0x140049bce  add     eax, 20h ; ' '
0x140049bd1  mov     r8d, 53646641h
0x140049bd7  add     edi, eax
0x140049bd9  mov     edx, edi
0x140049bdb  call    AfdAllocatePoolPriority
0x140049be0  mov     rbx, rax
0x140049be3  test    rax, rax
0x140049be6  jnz     short loc_140049BF2
0x140049be8  mov     eax, 0C000009Ah
0x140049bed  jmp     loc_140049CAA
0x140049bf2  mov     r8d, 2; AclRevision
0x140049bf8  mov     edx, edi; AclLength
0x140049bfa  mov     rcx, rbx; Acl
0x140049bfd  call    cs:__imp_RtlCreateAcl
0x140049c04  nop     dword ptr [rax+rax+00h]
0x140049c09  mov     edi, eax
0x140049c0b  mov     rcx, rbx; Acl
0x140049c0e  test    eax, eax
0x140049c10  jns     short loc_140049C2A
0x140049c12  mov     edx, 53646641h; Tag
0x140049c17  call    cs:__imp_ExFreePoolWithTag
0x140049c1e  nop     dword ptr [rax+rax+00h]
0x140049c23  mov     eax, edi
0x140049c25  jmp     loc_140049CAA
0x140049c2a  mov     rax, cs:__imp_SeExports
0x140049c31  mov     edx, 2; AceRevision
0x140049c36  mov     r8d, [rsp+28h+AccessMask]; AccessMask
0x140049c3b  mov     r9, [rax]
0x140049c3e  mov     r9, [r9+110h]; Sid
0x140049c45  call    cs:__imp_RtlAddAccessAllowedAce
0x140049c4c  nop     dword ptr [rax+rax+00h]
0x140049c51  mov     rax, cs:__imp_SeExports
0x140049c58  mov     edx, 2; AceRevision
0x140049c5d  mov     r8d, [rsp+28h+AccessMask]; AccessMask
0x140049c62  mov     rcx, rbx; Acl
0x140049c65  mov     r9, [rax]
0x140049c68  mov     r9, [r9+108h]; Sid
0x140049c6f  call    cs:__imp_RtlAddAccessAllowedAce
0x140049c76  nop     dword ptr [rax+rax+00h]
0x140049c7b  mov     rax, cs:__imp_SeExports
0x140049c82  mov     edx, 2; AceRevision
0x140049c87  mov     r8d, [rsp+28h+AccessMask]; AccessMask
0x140049c8c  mov     rcx, rbx; Acl
0x140049c8f  mov     r9, [rax]
0x140049c92  mov     r9, [r9+188h]; Sid
0x140049c99  call    cs:__imp_RtlAddAccessAllowedAce
0x140049ca0  nop     dword ptr [rax+rax+00h]
0x140049ca5  xor     eax, eax
0x140049ca7  mov     [rsi], rbx
0x140049caa  mov     rbx, [rsp+28h+arg_0]
0x140049caf  mov     rsi, [rsp+28h+arg_10]
0x140049cb4  add     rsp, 20h
0x140049cb8  pop     rdi
0x140049cb9  retn
```
