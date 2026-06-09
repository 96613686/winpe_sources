# VfsGetChildSecurityDescriptor

- ea: `0x14000e8d0`
- end: `0x14000e93d`
- name: `VfsGetChildSecurityDescriptor`
- size: `109`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR ParentDescriptor)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000e59c`

## import_xrefs

- `ntoskrnl!SeAssignSecurityEx` at `0x14000e920`
- `ntoskrnl!SeAssignSecurityEx` at `0x14000e920`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000e8e7`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000e8e7`

## pseudocode

```c
NTSTATUS __fastcall VfsGetChildSecurityDescriptor(
        PSECURITY_DESCRIPTOR ParentDescriptor,
        BOOLEAN a2,
        PSECURITY_DESCRIPTOR *a3)
{
  struct _GENERIC_MAPPING *GenericMapping; // rax

  GenericMapping = IoGetFileObjectGenericMapping();
  return SeAssignSecurityEx(ParentDescriptor, 0, a3, 0, a2, 0x7Bu, 0, GenericMapping, PagedPool);
}

```

## disassembly

```asm
0x14000e8d0  mov     [rsp+arg_0], rbx
0x14000e8d5  mov     [rsp+arg_8], rsi
0x14000e8da  push    rdi
0x14000e8db  sub     rsp, 50h
0x14000e8df  mov     rdi, r8
0x14000e8e2  mov     bl, dl
0x14000e8e4  mov     rsi, rcx
0x14000e8e7  call    cs:__imp_IoGetFileObjectGenericMapping
0x14000e8ee  nop     dword ptr [rax+rax+00h]
0x14000e8f3  mov     [rsp+58h+PoolType], 1; PoolType
0x14000e8fb  xor     r9d, r9d; ObjectType
0x14000e8fe  mov     [rsp+58h+GenericMapping], rax; GenericMapping
0x14000e903  mov     r8, rdi; NewDescriptor
0x14000e906  mov     [rsp+58h+SubjectContext], 0; SubjectContext
0x14000e90f  xor     edx, edx; ExplicitDescriptor
0x14000e911  mov     [rsp+58h+AutoInheritFlags], 7Bh ; '{'; AutoInheritFlags
0x14000e919  mov     rcx, rsi; ParentDescriptor
0x14000e91c  mov     [rsp+58h+IsDirectoryObject], bl; IsDirectoryObject
0x14000e920  call    cs:__imp_SeAssignSecurityEx
0x14000e927  nop     dword ptr [rax+rax+00h]
0x14000e92c  mov     rbx, [rsp+58h+arg_0]
0x14000e931  mov     rsi, [rsp+58h+arg_8]
0x14000e936  add     rsp, 50h
0x14000e93a  pop     rdi
0x14000e93b  retn
```
