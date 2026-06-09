# CFileStream::Read(void *,ulong,ulong *)

- ea: `0x180022e20`
- end: `0x180022e4b`
- name: `?Read@CFileStream@@UEAAJPEAXKPEAK@Z`
- size: `43`
- prototype: `int(CFileStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcrt!fread` at `0x180022e3b`
- `msvcrt!fread` at `0x180022e3b`

## pseudocode

```c
__int64 __fastcall CFileStream::Read(FILE **this, void *a2, unsigned int a3, unsigned int *a4)
{
  *a4 = fread(a2, 1u, a3, this[3]);
  return 0;
}

```

## disassembly

```asm
0x180022e20  push    rbx
0x180022e22  sub     rsp, 20h
0x180022e26  mov     rax, rdx
0x180022e29  mov     r8d, r8d; ElementCount
0x180022e2c  mov     rbx, r9
0x180022e2f  mov     edx, 1; ElementSize
0x180022e34  mov     r9, [rcx+18h]; Stream
0x180022e38  mov     rcx, rax; Buffer
0x180022e3b  call    cs:__imp_fread
0x180022e41  mov     [rbx], eax
0x180022e43  xor     eax, eax
0x180022e45  add     rsp, 20h
0x180022e49  pop     rbx
0x180022e4a  retn
```
