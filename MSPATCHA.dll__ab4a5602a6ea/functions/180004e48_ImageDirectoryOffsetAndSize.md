# ImageDirectoryOffsetAndSize

- ea: `0x180004e48`
- end: `0x180004e92`
- name: `ImageDirectoryOffsetAndSize`
- size: `74`
- prototype: `__int64 __fastcall(__int64, int, int, __int64, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000541c`
- `0x180005754`
- `0x180005934`
- `0x1800061e4`

## callees

- `0x180004e48`
- `0x180004e98`
- `0x180004ef0`

## pseudocode

```c
__int64 __fastcall ImageDirectoryOffsetAndSize(__int64 a1, int a2, int a3, __int64 a4, unsigned int a5)
{
  unsigned int v7; // eax

  v7 = ImageDirectoryRvaAndSize(a1, a2, a3, a4, a5);
  if ( v7 )
    return ImageRvaToFileOffset(a1, v7, a4, a5);
  else
    return 0;
}

```

## disassembly

```asm
0x180004e48  mov     [rsp+arg_0], rbx
0x180004e4d  mov     [rsp+arg_8], rsi
0x180004e52  push    rdi
0x180004e53  sub     rsp, 30h
0x180004e57  mov     esi, [rsp+38h+arg_20]
0x180004e5b  mov     rbx, r9
0x180004e5e  mov     [rsp+38h+var_18], esi
0x180004e62  mov     rdi, rcx
0x180004e65  call    ImageDirectoryRvaAndSize
0x180004e6a  test    eax, eax
0x180004e6c  jz      short loc_180004E80
0x180004e6e  mov     r9d, esi
0x180004e71  mov     r8, rbx
0x180004e74  mov     edx, eax
0x180004e76  mov     rcx, rdi
0x180004e79  call    ImageRvaToFileOffset
0x180004e7e  jmp     short loc_180004E82
0x180004e80  xor     eax, eax
0x180004e82  mov     rbx, [rsp+38h+arg_0]
0x180004e87  mov     rsi, [rsp+38h+arg_8]
0x180004e8c  add     rsp, 30h
0x180004e90  pop     rdi
0x180004e91  retn
```
