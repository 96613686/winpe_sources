# BfsWriteBlock

- ea: `0x140012ab0`
- end: `0x140012b0a`
- name: `BfsWriteBlock`
- size: `90`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x14001033c`
- `0x140010b30`
- `0x140010ffc`
- `0x140011458`
- `0x140011d18`
- `0x140012478`

## import_xrefs

- `ntoskrnl!ZwWriteFile` at `0x140012af8`
- `ntoskrnl!ZwWriteFile` at `0x140012af8`

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
0x140012ab0  mov     r11, rsp
0x140012ab3  sub     rsp, 68h
0x140012ab7  mov     rcx, [rcx+8]; FileHandle
0x140012abb  xorps   xmm0, xmm0
0x140012abe  mov     qword ptr [r11-28h], 0
0x140012ac6  xor     r9d, r9d; ApcContext
0x140012ac9  shl     edx, 0Eh
0x140012acc  mov     eax, edx
0x140012ace  xor     edx, edx; Event
0x140012ad0  mov     [r11+8], rax
0x140012ad4  lea     rax, [r11+8]
0x140012ad8  mov     [r11-30h], rax
0x140012adc  lea     rax, [r11-18h]
0x140012ae0  mov     [rsp+68h+Length], 4000h; Length
0x140012ae8  mov     [r11-40h], r8
0x140012aec  xor     r8d, r8d; ApcRoutine
0x140012aef  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x140012af4  mov     [r11-48h], rax
0x140012af8  call    cs:__imp_ZwWriteFile
0x140012aff  nop     dword ptr [rax+rax+00h]
0x140012b04  add     rsp, 68h
0x140012b08  retn
```
