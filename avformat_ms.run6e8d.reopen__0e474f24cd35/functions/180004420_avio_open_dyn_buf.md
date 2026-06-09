# avio_open_dyn_buf

- ea: `0x180004420`
- end: `0x180004427`
- name: `avio_open_dyn_buf`
- size: `7`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010898`

## callees

- `0x180005eb4`

## pseudocode

```c
__int64 __fastcall avio_open_dyn_buf(__int64 a1)
{
  return sub_180005EB4(a1, 0);
}

```

## disassembly

```asm
0x180004420  xor     edx, edx
0x180004422  jmp     sub_180005EB4
```
