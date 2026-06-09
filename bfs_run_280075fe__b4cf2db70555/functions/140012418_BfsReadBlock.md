# BfsReadBlock

- ea: `0x140012418`
- end: `0x140012472`
- name: `BfsReadBlock`
- size: `90`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x14001079c`
- `0x140010b30`
- `0x14001226c`

## import_xrefs

- `ntoskrnl!ZwReadFile` at `0x140012460`
- `ntoskrnl!ZwReadFile` at `0x140012460`

## pseudocode

```c
NTSTATUS __fastcall BfsReadBlock(__int64 a1, int a2, void *a3)
{
  void *v3; // rcx
  struct _IO_STATUS_BLOCK v5; // [rsp+50h] [rbp-18h] BYREF
  union _LARGE_INTEGER v6; // [rsp+70h] [rbp+8h] BYREF

  v3 = *(void **)(a1 + 8);
  v6.QuadPart = (unsigned int)(a2 << 14);
  v5 = 0;
  return ZwReadFile(v3, 0, 0, 0, &v5, a3, 0x4000u, &v6, 0);
}

```

## disassembly

```asm
0x140012418  mov     r11, rsp
0x14001241b  sub     rsp, 68h
0x14001241f  mov     rcx, [rcx+8]; FileHandle
0x140012423  xorps   xmm0, xmm0
0x140012426  mov     qword ptr [r11-28h], 0
0x14001242e  xor     r9d, r9d; ApcContext
0x140012431  shl     edx, 0Eh
0x140012434  mov     eax, edx
0x140012436  xor     edx, edx; Event
0x140012438  mov     [r11+8], rax
0x14001243c  lea     rax, [r11+8]
0x140012440  mov     [r11-30h], rax
0x140012444  lea     rax, [r11-18h]
0x140012448  mov     [rsp+68h+Length], 4000h; Length
0x140012450  mov     [r11-40h], r8
0x140012454  xor     r8d, r8d; ApcRoutine
0x140012457  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x14001245c  mov     [r11-48h], rax
0x140012460  call    cs:__imp_ZwReadFile
0x140012467  nop     dword ptr [rax+rax+00h]
0x14001246c  add     rsp, 68h
0x140012470  retn
```
