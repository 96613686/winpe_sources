# BfsWriteBlock

- ea: `0x140012c40`
- end: `0x140012c9a`
- name: `BfsWriteBlock`
- size: `90`
- prototype: `NTSTATUS __fastcall(__int64, int, void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1400104ec`
- `0x140010cc8`
- `0x140011194`
- `0x1400115f0`
- `0x140011ea8`
- `0x140012608`

## import_xrefs

- `ntoskrnl!ZwWriteFile` at `0x140012c88`
- `ntoskrnl!ZwWriteFile` at `0x140012c88`

## pseudocode

```c
NTSTATUS __fastcall BfsWriteBlock(__int64 a1, int a2, void *a3)
{
  void *v3; // rcx
  struct _IO_STATUS_BLOCK v5; // [rsp+50h] [rbp-18h] BYREF
  union _LARGE_INTEGER v6; // [rsp+70h] [rbp+8h] BYREF

  v3 = *(void **)(a1 + 8);
  v6.QuadPart = (unsigned int)(a2 << 14);
  v5 = 0;
  return ZwWriteFile(v3, 0, 0, 0, &v5, a3, 0x4000u, &v6, 0);
}

```

## disassembly

```asm
0x140012c40  mov     r11, rsp
0x140012c43  sub     rsp, 68h
0x140012c47  mov     rcx, [rcx+8]; FileHandle
0x140012c4b  xorps   xmm0, xmm0
0x140012c4e  mov     qword ptr [r11-28h], 0
0x140012c56  xor     r9d, r9d; ApcContext
0x140012c59  shl     edx, 0Eh
0x140012c5c  mov     eax, edx
0x140012c5e  xor     edx, edx; Event
0x140012c60  mov     [r11+8], rax
0x140012c64  lea     rax, [r11+8]
0x140012c68  mov     [r11-30h], rax
0x140012c6c  lea     rax, [r11-18h]
0x140012c70  mov     [rsp+68h+Length], 4000h; Length
0x140012c78  mov     [r11-40h], r8
0x140012c7c  xor     r8d, r8d; ApcRoutine
0x140012c7f  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x140012c84  mov     [r11-48h], rax
0x140012c88  call    cs:__imp_ZwWriteFile
0x140012c8f  nop     dword ptr [rax+rax+00h]
0x140012c94  add     rsp, 68h
0x140012c98  retn
```
