# BfspBsdLogWrite

- ea: `0x140002b24`
- end: `0x140002b73`
- name: `BfspBsdLogWrite`
- size: `79`
- prototype: `NTSTATUS __fastcall(unsigned int, void *, ULONG)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, loader_planting`

## callers

- `0x140003a48`

## import_xrefs

- `ntdll!NtWriteFile` at `0x140002b68`
- `ntdll!NtWriteFile` at `0x140002b68`

## pseudocode

```c
NTSTATUS __fastcall BfspBsdLogWrite(unsigned int a1, void *a2, ULONG a3)
{
  struct _IO_STATUS_BLOCK v4; // [rsp+50h] [rbp-18h] BYREF
  union _LARGE_INTEGER v5; // [rsp+88h] [rbp+20h] BYREF

  v5.QuadPart = a1;
  v4 = 0;
  return NtWriteFile(BootstatHandle, 0, 0, 0, &v4, a2, a3, &v5, 0);
}

```

## disassembly

```asm
0x140002b24  mov     r11, rsp
0x140002b27  sub     rsp, 68h
0x140002b2b  mov     qword ptr [r11-28h], 0
0x140002b33  xorps   xmm0, xmm0
0x140002b36  mov     eax, ecx
0x140002b38  xor     r9d, r9d; ApcContext
0x140002b3b  mov     rcx, cs:BootstatHandle; FileHandle
0x140002b42  mov     [r11+20h], rax
0x140002b46  lea     rax, [r11+20h]
0x140002b4a  mov     [r11-30h], rax
0x140002b4e  lea     rax, [r11-18h]
0x140002b52  mov     [r11-38h], r8d
0x140002b56  xor     r8d, r8d; ApcRoutine
0x140002b59  mov     [r11-40h], rdx
0x140002b5d  xor     edx, edx; Event
0x140002b5f  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x140002b64  mov     [r11-48h], rax
0x140002b68  call    cs:__imp_NtWriteFile
0x140002b6e  add     rsp, 68h
0x140002b72  retn
```
