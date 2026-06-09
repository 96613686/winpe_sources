# MakeCopyofClassEntry(_class_entry *)

- ea: `0x180017c28`
- end: `0x180017ca6`
- name: `?MakeCopyofClassEntry@@YAPEAU_class_entry@@PEAU1@@Z`
- size: `126`
- prototype: `struct _class_entry *__fastcall(wchar_t *Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800170ac`

## callees

- `0x180017c28`
- `0x180017cac`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180017c86`
- `msvcrt!wcscpy_s` at `0x180017c86`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180017c6d`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180017c6d`

## pseudocode

```c
wchar_t *__fastcall MakeCopyofClassEntry(wchar_t *Source)
{
  __int64 v1; // rbx
  struct _extension_entry *v3; // rdi
  struct _extension_entry *CopyofExtensionEntry; // rax
  wchar_t *v5; // rax
  wchar_t *v6; // rbx

  v1 = *((_QWORD *)Source + 65);
  v3 = 0;
  while ( v1 )
  {
    CopyofExtensionEntry = MakeCopyofExtensionEntry((wchar_t *)v1);
    if ( CopyofExtensionEntry )
    {
      *((_QWORD *)CopyofExtensionEntry + 73) = v3;
      v3 = CopyofExtensionEntry;
    }
    v1 = *(_QWORD *)(v1 + 584);
  }
  v5 = (wchar_t *)AllocADsMem(0x218u);
  v6 = v5;
  if ( v5 )
  {
    wcscpy_s(v5, 0x104u, Source);
    *((_QWORD *)v6 + 65) = v3;
  }
  return v6;
}

```

## disassembly

```asm
0x180017c28  mov     [rsp+arg_0], rbx
0x180017c2d  mov     [rsp+arg_8], rsi
0x180017c32  push    rdi
0x180017c33  sub     rsp, 20h
0x180017c37  mov     rbx, [rcx+208h]
0x180017c3e  mov     rsi, rcx
0x180017c41  xor     edi, edi
0x180017c43  jmp     short loc_180017C63
0x180017c45  mov     rcx, rbx; Source
0x180017c48  call    ?MakeCopyofExtensionEntry@@YAPEAU_extension_entry@@PEAU1@@Z; MakeCopyofExtensionEntry(_extension_entry *)
0x180017c4d  test    rax, rax
0x180017c50  jz      short loc_180017C5C
0x180017c52  mov     [rax+248h], rdi
0x180017c59  mov     rdi, rax
0x180017c5c  mov     rbx, [rbx+248h]
0x180017c63  test    rbx, rbx
0x180017c66  jnz     short loc_180017C45
0x180017c68  mov     ecx, 218h; cb
0x180017c6d  call    cs:__imp_AllocADsMem
0x180017c73  mov     rbx, rax
0x180017c76  test    rax, rax
0x180017c79  jz      short loc_180017C93
0x180017c7b  mov     r8, rsi; Source
0x180017c7e  mov     edx, 104h; SizeInWords
0x180017c83  mov     rcx, rax; Destination
0x180017c86  call    cs:__imp_wcscpy_s
0x180017c8c  mov     [rbx+208h], rdi
0x180017c93  mov     rsi, [rsp+28h+arg_8]
0x180017c98  mov     rax, rbx
0x180017c9b  mov     rbx, [rsp+28h+arg_0]
0x180017ca0  add     rsp, 20h
0x180017ca4  pop     rdi
0x180017ca5  retn
```
