# BfspBsdLogRead

- ea: `0x1400029a8`
- end: `0x1400029f7`
- name: `BfspBsdLogRead`
- size: `79`
- prototype: `NTSTATUS __fastcall(unsigned int, void *, ULONG)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, loader_planting`

## callers

- `0x140003a48`

## import_xrefs

- `ntdll!NtReadFile` at `0x1400029ec`
- `ntdll!NtReadFile` at `0x1400029ec`

## pseudocode

```c
NTSTATUS __fastcall BfspBsdLogRead(unsigned int a1, void *a2, ULONG a3)
{
  struct _IO_STATUS_BLOCK v4; // [rsp+50h] [rbp-18h] BYREF
  union _LARGE_INTEGER v5; // [rsp+88h] [rbp+20h] BYREF

  v5.QuadPart = a1;
  v4 = 0;
  return NtReadFile(BootstatHandle, 0, 0, 0, &v4, a2, a3, &v5, 0);
}

```

## disassembly

```asm
0x1400029a8  mov     r11, rsp
0x1400029ab  sub     rsp, 68h
0x1400029af  mov     qword ptr [r11-28h], 0
0x1400029b7  xorps   xmm0, xmm0
0x1400029ba  mov     eax, ecx
0x1400029bc  xor     r9d, r9d; ApcContext
0x1400029bf  mov     rcx, cs:BootstatHandle; FileHandle
0x1400029c6  mov     [r11+20h], rax
0x1400029ca  lea     rax, [r11+20h]
0x1400029ce  mov     [r11-30h], rax
0x1400029d2  lea     rax, [r11-18h]
0x1400029d6  mov     [r11-38h], r8d
0x1400029da  xor     r8d, r8d; ApcRoutine
0x1400029dd  mov     [r11-40h], rdx
0x1400029e1  xor     edx, edx; Event
0x1400029e3  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x1400029e8  mov     [r11-48h], rax
0x1400029ec  call    cs:__imp_NtReadFile
0x1400029f2  add     rsp, 68h
0x1400029f6  retn
```
