# SrpIsSubjectService

- ea: `0x140032d30`
- end: `0x140032db2`
- name: `SrpIsSubjectService`
- size: `130`
- prototype: `__int64 __fastcall(PSECURITY_SUBJECT_CONTEXT SubjectSecurityContext)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14002be08`

## callees

- `0x140032d30`

## import_xrefs

- `ntoskrnl!SeAccessCheck` at `0x140032d84`
- `ntoskrnl!SeAccessCheck` at `0x140032d84`

## pseudocode

```c
__int64 __fastcall SrpIsSubjectService(PSECURITY_SUBJECT_CONTEXT SubjectSecurityContext, BOOLEAN *a2)
{
  BOOLEAN v3; // al
  unsigned int v4; // ecx
  unsigned int v6; // [rsp+70h] [rbp+18h] BYREF
  DWORD v7; // [rsp+78h] [rbp+20h] BYREF

  v6 = 0;
  v7 = 0;
  v3 = SeAccessCheck(
         qword_14000A378,
         SubjectSecurityContext,
         0,
         1u,
         0,
         0,
         (PGENERIC_MAPPING)&GenericMapping,
         1,
         &v7,
         (PNTSTATUS)&v6);
  v4 = v6;
  if ( v3 )
    goto LABEL_4;
  if ( v6 == -1073741790 )
  {
    v4 = 0;
LABEL_4:
    *a2 = v3;
  }
  return v4;
}

```

## disassembly

```asm
0x140032d30  mov     r11, rsp
0x140032d33  mov     [r11+8], rbx
0x140032d37  push    rdi
0x140032d38  sub     rsp, 50h
0x140032d3c  xor     edi, edi
0x140032d3e  lea     rax, [r11+18h]
0x140032d42  mov     [r11-10h], rax
0x140032d46  mov     rbx, rdx
0x140032d49  lea     rax, [r11+20h]
0x140032d4d  mov     [rsp+58h+arg_10], edi
0x140032d51  mov     [r11-18h], rax
0x140032d55  mov     rdx, rcx; SubjectSecurityContext
0x140032d58  mov     [rsp+58h+AccessMode], 1; AccessMode
0x140032d5d  lea     rax, GenericMapping
0x140032d64  mov     [r11-28h], rax
0x140032d68  lea     rcx, qword_14000A378; SecurityDescriptor
0x140032d6f  mov     [r11-30h], rdi
0x140032d73  mov     r9d, 1; DesiredAccess
0x140032d79  xor     r8d, r8d; SubjectContextLocked
0x140032d7c  mov     [rsp+58h+PreviouslyGrantedAccess], edi; PreviouslyGrantedAccess
0x140032d80  mov     [rsp+58h+arg_18], edi
0x140032d84  call    cs:__imp_SeAccessCheck
0x140032d8b  nop     dword ptr [rax+rax+00h]
0x140032d90  mov     ecx, [rsp+58h+arg_10]
0x140032d94  test    al, al
0x140032d96  jnz     short loc_140032DA2
0x140032d98  cmp     ecx, 0C0000022h
0x140032d9e  jnz     short loc_140032DA4
0x140032da0  mov     ecx, edi
0x140032da2  mov     [rbx], al
0x140032da4  mov     eax, ecx
0x140032da6  mov     rbx, [rsp+58h+arg_0]
0x140032dab  add     rsp, 50h
0x140032daf  pop     rdi
0x140032db0  retn
```
