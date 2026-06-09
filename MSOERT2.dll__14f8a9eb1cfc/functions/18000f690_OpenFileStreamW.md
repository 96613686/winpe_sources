# OpenFileStreamW

- ea: `0x18000f690`
- end: `0x18000f6a9`
- name: `OpenFileStreamW`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000f6b0`

## pseudocode

```c
int __fastcall OpenFileStreamW(const unsigned __int16 *a1, unsigned int a2, unsigned int a3, struct IStream **a4)
{
  return OpenFileStreamWithFlagsW(a1, a2, a3, 0x80u, a4);
}

```

## disassembly

```asm
0x18000f690  sub     rsp, 38h
0x18000f694  mov     [rsp+38h+var_18], r9
0x18000f699  mov     r9d, 80h
0x18000f69f  call    OpenFileStreamWithFlagsW
0x18000f6a4  add     rsp, 38h
0x18000f6a8  retn
```
