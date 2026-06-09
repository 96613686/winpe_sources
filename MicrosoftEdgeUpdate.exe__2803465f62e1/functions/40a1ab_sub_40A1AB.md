# sub_40A1AB

- ea: `0x40a1ab`
- end: `0x40a1cc`
- name: `sub_40A1AB`
- size: `33`
- prototype: `int __stdcall(unsigned int)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x409f30`
- `0x40a410`
- `0x40a4de`
- `0x40a616`
- `0x40ade6`

## callees

- `0x407f0d`
- `0x40a1ab`
- `0x40a8db`

## pseudocode

```c
int __stdcall sub_40A1AB(unsigned int a1)
{
  size_t v1; // ecx

  if ( a1 > 0x7FFFFFFF )
    sub_407F0D();
  v1 = 2 * a1;
  _mm_lfence();
  return sub_40A8DB(v1);
}

```

## disassembly

```asm
0x40a1ab  push    ebp
0x40a1ac  mov     ebp, esp
0x40a1ae  mov     ecx, [ebp+arg_0]
0x40a1b1  cmp     ecx, 7FFFFFFFh
0x40a1b7  ja      short loc_40A1C7
0x40a1b9  add     ecx, ecx; Size
0x40a1bb  lfence
0x40a1be  call    sub_40A8DB
0x40a1c3  pop     ebp
0x40a1c4  retn    4
0x40a1c7  call    sub_407F0D
```
