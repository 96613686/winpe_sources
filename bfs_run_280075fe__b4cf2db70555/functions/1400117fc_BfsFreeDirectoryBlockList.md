# BfsFreeDirectoryBlockList

- ea: `0x1400117fc`
- end: `0x14001185f`
- name: `BfsFreeDirectoryBlockList`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14001079c`
- `0x14001126c`
- `0x14001226c`

## callees

- `0x1400117fc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001182d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001183e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001182d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001183e`

## pseudocode

```c
void __fastcall BfsFreeDirectoryBlockList(void **a1)
{
  void *v2; // rbx
  void **v3; // rax

  while ( 1 )
  {
    v2 = *a1;
    if ( *a1 == a1 )
      break;
    if ( *((void ***)v2 + 1) != a1 || (v3 = *(void ***)v2, *(void **)(*(_QWORD *)v2 + 8LL) != v2) )
      __fastfail(3u);
    *a1 = v3;
    v3[1] = a1;
    ExFreePoolWithTag(*((PVOID *)v2 + 2), 0);
    ExFreePoolWithTag(v2, 0);
  }
}

```

## disassembly

```asm
0x1400117fc  mov     [rsp+arg_0], rbx
0x140011801  push    rdi
0x140011802  sub     rsp, 20h
0x140011806  mov     rdi, rcx
0x140011809  mov     rbx, [rdi]
0x14001180c  cmp     rbx, rdi
0x14001180f  jz      short loc_140011853
0x140011811  cmp     [rbx+8], rdi
0x140011815  jnz     short loc_14001184C
0x140011817  mov     rax, [rbx]
0x14001181a  cmp     [rax+8], rbx
0x14001181e  jnz     short loc_14001184C
0x140011820  mov     [rdi], rax
0x140011823  xor     edx, edx; Tag
0x140011825  mov     [rax+8], rdi
0x140011829  mov     rcx, [rbx+10h]; P
0x14001182d  call    cs:__imp_ExFreePoolWithTag
0x140011834  nop     dword ptr [rax+rax+00h]
0x140011839  xor     edx, edx; Tag
0x14001183b  mov     rcx, rbx; P
0x14001183e  call    cs:__imp_ExFreePoolWithTag
0x140011845  nop     dword ptr [rax+rax+00h]
0x14001184a  jmp     short loc_140011809
0x14001184c  mov     ecx, 3
0x140011851  int     29h; Win8: RtlFailFast(ecx)
0x140011853  mov     rbx, [rsp+28h+arg_0]
0x140011858  add     rsp, 20h
0x14001185c  pop     rdi
0x14001185d  retn
```
