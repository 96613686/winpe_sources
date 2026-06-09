# VfsDeleteSecurityDescriptors

- ea: `0x14000e850`
- end: `0x14000e8c8`
- name: `VfsDeleteSecurityDescriptors`
- size: `120`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140009368`
- `0x14000e59c`

## callees

- `0x14000e850`

## import_xrefs

- `ntoskrnl!SeDeassignSecurity` at `0x14000e88a`
- `ntoskrnl!SeDeassignSecurity` at `0x14000e8a8`
- `ntoskrnl!SeDeassignSecurity` at `0x14000e88a`
- `ntoskrnl!SeDeassignSecurity` at `0x14000e8a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e86a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e86a`

## pseudocode

```c
void __fastcall VfsDeleteSecurityDescriptors(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0x64534656u);
    *a1 = 0;
  }
  if ( a1[1] )
  {
    SeDeassignSecurity(a1 + 1);
    a1[1] = 0;
  }
  if ( a1[2] )
  {
    SeDeassignSecurity(a1 + 2);
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x14000e850  mov     [rsp+arg_0], rbx
0x14000e855  push    rdi
0x14000e856  sub     rsp, 20h
0x14000e85a  mov     rbx, rcx
0x14000e85d  mov     rcx, [rcx]; P
0x14000e860  test    rcx, rcx
0x14000e863  jz      short loc_14000E87D
0x14000e865  mov     edx, 64534656h; Tag
0x14000e86a  call    cs:__imp_ExFreePoolWithTag
0x14000e871  nop     dword ptr [rax+rax+00h]
0x14000e876  mov     qword ptr [rbx], 0
0x14000e87d  lea     rdi, [rbx+8]
0x14000e881  cmp     qword ptr [rdi], 0
0x14000e885  jz      short loc_14000E89D
0x14000e887  mov     rcx, rdi; SecurityDescriptor
0x14000e88a  call    cs:__imp_SeDeassignSecurity
0x14000e891  nop     dword ptr [rax+rax+00h]
0x14000e896  mov     qword ptr [rdi], 0
0x14000e89d  cmp     qword ptr [rbx+10h], 0
0x14000e8a2  jz      short loc_14000E8BC
0x14000e8a4  lea     rcx, [rbx+10h]; SecurityDescriptor
0x14000e8a8  call    cs:__imp_SeDeassignSecurity
0x14000e8af  nop     dword ptr [rax+rax+00h]
0x14000e8b4  mov     qword ptr [rbx+10h], 0
0x14000e8bc  mov     rbx, [rsp+28h+arg_0]
0x14000e8c1  add     rsp, 20h
0x14000e8c5  pop     rdi
0x14000e8c6  retn
```
