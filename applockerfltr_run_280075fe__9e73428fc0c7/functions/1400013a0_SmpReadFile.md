# SmpReadFile

- ea: `0x1400013a0`
- end: `0x1400013e0`
- name: `SmpReadFile`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `FLTMGR!FltReadFile` at `0x1400013ce`
- `FLTMGR!FltReadFile` at `0x1400013ce`

## pseudocode

```c
NTSTATUS __fastcall SmpReadFile(__int64 a1, union _LARGE_INTEGER *a2, ULONG a3, void *a4)
{
  return FltReadFile(*(PFLT_INSTANCE *)a1, *(PFILE_OBJECT *)(a1 + 8), a2, a3, a4, 4u, 0, 0, 0);
}

```

## disassembly

```asm
0x1400013a0  mov     r11, rsp
0x1400013a3  sub     rsp, 58h
0x1400013a7  xor     eax, eax
0x1400013a9  mov     [r11-18h], rax
0x1400013ad  mov     [r11-20h], rax
0x1400013b1  mov     [r11-28h], rax
0x1400013b5  mov     [rsp+58h+Flags], 4; Flags
0x1400013bd  mov     [r11-38h], r9
0x1400013c1  mov     r9d, r8d; Length
0x1400013c4  mov     r8, rdx; ByteOffset
0x1400013c7  mov     rdx, [rcx+8]; FileObject
0x1400013cb  mov     rcx, [rcx]; InitiatingInstance
0x1400013ce  call    cs:__imp_FltReadFile
0x1400013d5  nop     dword ptr [rax+rax+00h]
0x1400013da  add     rsp, 58h
0x1400013de  retn
```
