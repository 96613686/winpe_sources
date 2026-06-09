# OpenFileStreamWithFlagsW

- ea: `0x18000f6b0`
- end: `0x18000f6e7`
- name: `OpenFileStreamWithFlagsW`
- size: `55`
- prototype: `int __fastcall(const unsigned __int16 *, unsigned int, unsigned int, unsigned int, struct IStream **)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000f500`
- `0x18000f690`
- `0x18000f9a0`

## callees

- `0x180001980`

## pseudocode

```c
int __fastcall OpenFileStreamWithFlagsW(
        const unsigned __int16 *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        struct IStream **a5)
{
  return CreateFileStream(a1, a3, 5 - (a3 != 0x80000000), a2, a4, a5);
}

```

## disassembly

```asm
0x18000f6b0  sub     rsp, 38h
0x18000f6b4  mov     r10d, r8d
0x18000f6b7  mov     eax, 80000000h
0x18000f6bc  sub     eax, r8d
0x18000f6bf  neg     eax
0x18000f6c1  mov     rax, [rsp+38h+arg_20]
0x18000f6c6  mov     [rsp+38h+var_10], rax; struct IStream **
0x18000f6cb  sbb     r8d, r8d
0x18000f6ce  mov     [rsp+38h+var_18], r9d; unsigned int
0x18000f6d3  add     r8d, 5; unsigned int
0x18000f6d7  mov     r9d, edx; unsigned int
0x18000f6da  mov     edx, r10d; unsigned int
0x18000f6dd  call    ?CreateFileStream@@YAJPEBGKKKKPEAPEAUIStream@@@Z; CreateFileStream(ushort const *,ulong,ulong,ulong,ulong,IStream * *)
0x18000f6e2  add     rsp, 38h
0x18000f6e6  retn
```
