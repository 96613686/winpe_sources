# VfsRenameFile

- ea: `0x140011134`
- end: `0x1400111e6`
- name: `VfsRenameFile`
- size: `178`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, __int64, const void **, char)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000b4ec`
- `0x14000c40c`
- `0x14000c574`
- `0x14000c8c4`

## callees

- `0x140011134`
- `0x140013d00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400111ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400111ca`
- `ntoskrnl!ExAllocatePool2` at `0x140011161`
- `ntoskrnl!ExAllocatePool2` at `0x140011161`
- `FLTMGR!FltSetInformationFile` at `0x1400111b4`
- `FLTMGR!FltSetInformationFile` at `0x1400111b4`

## pseudocode

```c
__int64 __fastcall VfsRenameFile(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, __int64 a3, const void **a4, char a5)
{
  ULONG v8; // esi
  __int64 Pool2; // rax
  void *v11; // rdi
  unsigned int v13; // ebx

  v8 = *(unsigned __int16 *)a4 + 20;
  Pool2 = ExAllocatePool2(256, v8, 1850164822);
  v11 = (void *)Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  *(_BYTE *)Pool2 = a5;
  *(_QWORD *)(Pool2 + 8) = a3;
  *(_DWORD *)(Pool2 + 16) = *(unsigned __int16 *)a4;
  memmove((void *)(Pool2 + 20), a4[1], *(unsigned __int16 *)a4);
  v13 = FltSetInformationFile(Instance, FileObject, v11, v8, FileRenameInformation);
  ExFreePoolWithTag(v11, 0x6E474656u);
  return v13;
}

```

## disassembly

```asm
0x140011134  push    rbx
0x140011136  push    rbp
0x140011137  push    rsi
0x140011138  push    rdi
0x140011139  push    r14
0x14001113b  push    r15
0x14001113d  sub     rsp, 38h
0x140011141  movzx   esi, word ptr [r9]
0x140011145  mov     rbp, r8
0x140011148  mov     r14, rdx
0x14001114b  mov     r15, rcx
0x14001114e  add     esi, 14h
0x140011151  mov     ecx, 100h
0x140011156  mov     edx, esi
0x140011158  mov     r8d, 6E474656h
0x14001115e  mov     rbx, r9
0x140011161  call    cs:__imp_ExAllocatePool2
0x140011168  nop     dword ptr [rax+rax+00h]
0x14001116d  mov     rdi, rax
0x140011170  test    rax, rax
0x140011173  jnz     short loc_14001117C
0x140011175  mov     eax, 0C000009Ah
0x14001117a  jmp     short loc_1400111D8
0x14001117c  mov     al, [rsp+68h+arg_20]
0x140011183  lea     rcx, [rdi+14h]; void *
0x140011187  mov     [rdi], al
0x140011189  mov     [rdi+8], rbp
0x14001118d  movzx   eax, word ptr [rbx]
0x140011190  mov     [rdi+10h], eax
0x140011193  movzx   r8d, word ptr [rbx]; Size
0x140011197  mov     rdx, [rbx+8]; Src
0x14001119b  call    memmove
0x1400111a0  mov     r9d, esi; Length
0x1400111a3  mov     [rsp+68h+FileInformationClass], 0Ah; FileInformationClass
0x1400111ab  mov     r8, rdi; FileInformation
0x1400111ae  mov     rdx, r14; FileObject
0x1400111b1  mov     rcx, r15; Instance
0x1400111b4  call    cs:__imp_FltSetInformationFile
0x1400111bb  nop     dword ptr [rax+rax+00h]
0x1400111c0  mov     edx, 6E474656h; Tag
0x1400111c5  mov     rcx, rdi; P
0x1400111c8  mov     ebx, eax
0x1400111ca  call    cs:__imp_ExFreePoolWithTag
0x1400111d1  nop     dword ptr [rax+rax+00h]
0x1400111d6  mov     eax, ebx
0x1400111d8  add     rsp, 38h
0x1400111dc  pop     r15
0x1400111de  pop     r14
0x1400111e0  pop     rdi
0x1400111e1  pop     rsi
0x1400111e2  pop     rbp
0x1400111e3  pop     rbx
0x1400111e4  retn
```
