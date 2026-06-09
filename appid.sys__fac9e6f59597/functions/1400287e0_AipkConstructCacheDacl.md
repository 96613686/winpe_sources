# AipkConstructCacheDacl

- ea: `0x1400287e0`
- end: `0x1400288c5`
- name: `AipkConstructCacheDacl`
- size: `229`
- prototype: `__int64 __fastcall(struct _ACL **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140028c6c`

## callees

- `0x1400287e0`
- `0x1400328b0`
- `0x140032a50`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x1400287f9`
- `ntoskrnl!RtlLengthSid` at `0x14002880e`
- `ntoskrnl!RtlLengthSid` at `0x1400287f9`
- `ntoskrnl!RtlLengthSid` at `0x14002880e`
- `ntoskrnl!RtlCreateAcl` at `0x140028859`
- `ntoskrnl!RtlCreateAcl` at `0x140028859`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140028880`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400288a7`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140028880`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400288a7`

## pseudocode

```c
__int64 __fastcall AipkConstructCacheDacl(struct _ACL **a1)
{
  ULONG v2; // ebx
  ULONG v3; // ebx
  struct _ACL *v4; // rax
  struct _ACL *v5; // rdi
  NTSTATUS Acl; // ebx

  v2 = RtlLengthSid(qword_14000CA68);
  v3 = RtlLengthSid(qword_14000CA88) + 24 + v2;
  v4 = (struct _ACL *)AiAlloc(v3);
  v5 = v4;
  if ( v4 )
  {
    Acl = RtlCreateAcl(v4, v3, 2u);
    if ( Acl >= 0 )
    {
      Acl = RtlAddAccessAllowedAce(v5, 2u, 0x10000000u, qword_14000CA88);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAccessAllowedAce(v5, 2u, 0x10000000u, qword_14000CA68);
        if ( Acl >= 0 )
        {
          *a1 = v5;
          return (unsigned int)Acl;
        }
      }
    }
  }
  else
  {
    Acl = -1073741801;
  }
  AiFree(v5);
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x1400287e0  mov     [rsp+arg_0], rbx
0x1400287e5  mov     [rsp+arg_8], rsi
0x1400287ea  push    rdi
0x1400287eb  sub     rsp, 20h
0x1400287ef  mov     rsi, rcx
0x1400287f2  lea     rcx, qword_14000CA68; Sid
0x1400287f9  call    cs:__imp_RtlLengthSid
0x140028800  nop     dword ptr [rax+rax+00h]
0x140028805  lea     rcx, qword_14000CA88; Sid
0x14002880c  mov     ebx, eax
0x14002880e  call    cs:__imp_RtlLengthSid
0x140028815  nop     dword ptr [rax+rax+00h]
0x14002881a  add     eax, 18h
0x14002881d  add     ebx, eax
0x14002881f  mov     ecx, ebx
0x140028821  call    AiAlloc
0x140028826  mov     rdi, rax
0x140028829  test    rax, rax
0x14002882c  jnz     short loc_14002884E
0x14002882e  mov     ebx, 0C0000017h
0x140028833  mov     rcx, rdi
0x140028836  call    AiFree
0x14002883b  mov     rsi, [rsp+28h+arg_8]
0x140028840  mov     eax, ebx
0x140028842  mov     rbx, [rsp+28h+arg_0]
0x140028847  add     rsp, 20h
0x14002884b  pop     rdi
0x14002884c  retn
0x14002884e  mov     r8d, 2; AclRevision
0x140028854  mov     edx, ebx; AclLength
0x140028856  mov     rcx, rdi; Acl
0x140028859  call    cs:__imp_RtlCreateAcl
0x140028860  nop     dword ptr [rax+rax+00h]
0x140028865  mov     ebx, eax
0x140028867  test    eax, eax
0x140028869  js      short loc_140028833
0x14002886b  lea     r9, qword_14000CA88; Sid
0x140028872  mov     edx, 2; AceRevision
0x140028877  mov     r8d, 10000000h; AccessMask
0x14002887d  mov     rcx, rdi; Acl
0x140028880  call    cs:__imp_RtlAddAccessAllowedAce
0x140028887  nop     dword ptr [rax+rax+00h]
0x14002888c  mov     ebx, eax
0x14002888e  test    eax, eax
0x140028890  js      short loc_140028833
0x140028892  lea     r9, qword_14000CA68; Sid
0x140028899  mov     edx, 2; AceRevision
0x14002889e  mov     r8d, 10000000h; AccessMask
0x1400288a4  mov     rcx, rdi; Acl
0x1400288a7  call    cs:__imp_RtlAddAccessAllowedAce
0x1400288ae  nop     dword ptr [rax+rax+00h]
0x1400288b3  mov     ebx, eax
0x1400288b5  test    eax, eax
0x1400288b7  js      loc_140028833
0x1400288bd  mov     [rsi], rdi
0x1400288c0  jmp     loc_14002883B
```
