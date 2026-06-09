# BfsReadBlock

- ea: `0x1400125a8`
- end: `0x140012602`
- name: `BfsReadBlock`
- size: `90`
- prototype: `NTSTATUS __fastcall(__int64, int, void *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x14001093c`
- `0x140010cc8`
- `0x1400123fc`

## import_xrefs

- `ntoskrnl!ZwReadFile` at `0x1400125f0`
- `ntoskrnl!ZwReadFile` at `0x1400125f0`

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
0x1400125a8  mov     r11, rsp
0x1400125ab  sub     rsp, 68h
0x1400125af  mov     rcx, [rcx+8]; FileHandle
0x1400125b3  xorps   xmm0, xmm0
0x1400125b6  mov     qword ptr [r11-28h], 0
0x1400125be  xor     r9d, r9d; ApcContext
0x1400125c1  shl     edx, 0Eh
0x1400125c4  mov     eax, edx
0x1400125c6  xor     edx, edx; Event
0x1400125c8  mov     [r11+8], rax
0x1400125cc  lea     rax, [r11+8]
0x1400125d0  mov     [r11-30h], rax
0x1400125d4  lea     rax, [r11-18h]
0x1400125d8  mov     [rsp+68h+Length], 4000h; Length
0x1400125e0  mov     [r11-40h], r8
0x1400125e4  xor     r8d, r8d; ApcRoutine
0x1400125e7  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x1400125ec  mov     [r11-48h], rax
0x1400125f0  call    cs:__imp_ZwReadFile
0x1400125f7  nop     dword ptr [rax+rax+00h]
0x1400125fc  add     rsp, 68h
0x140012600  retn
```
