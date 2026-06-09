# SymCryptFdefIntCopy

- ea: `0x180017dc0`
- end: `0x180017de7`
- name: `SymCryptFdefIntCopy`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180017fec`

## callees

- `0x180017dc0`
- `0x18001860d`

## pseudocode

```c
void *__fastcall SymCryptFdefIntCopy(__int64 a1, __int64 a2)
{
  void *result; // rax

  if ( a1 != a2 )
    return memcpy_0((void *)(a2 + 32), (const void *)(a1 + 32), (unsigned int)(*(_DWORD *)(a2 + 4) << 6));
  return result;
}

```

## disassembly

```asm
0x180017dc0  sub     rsp, 28h
0x180017dc4  mov     r9, rdx
0x180017dc7  cmp     rcx, rdx
0x180017dca  jz      short loc_180017DE1
0x180017dcc  mov     r8d, [rdx+4]
0x180017dd0  lea     rdx, [rcx+20h]; Src
0x180017dd4  shl     r8d, 6; Size
0x180017dd8  lea     rcx, [r9+20h]; void *
0x180017ddc  call    memcpy_0
0x180017de1  add     rsp, 28h
0x180017de5  retn
```
