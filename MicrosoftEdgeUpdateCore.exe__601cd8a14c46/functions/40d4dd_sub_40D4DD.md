# sub_40D4DD

- ea: `0x40d4dd`
- end: `0x40d4eb`
- name: `sub_40D4DD`
- size: `14`
- prototype: `void __cdecl(void *Block)`
- caller_count: `28`
- callee_count: `1`
- tags: ``

## callers

- `0x4015b0`
- `0x401830`
- `0x402340`
- `0x402460`
- `0x403293`
- `0x403590`
- `0x403880`
- `0x403a70`
- `0x403b10`
- `0x403e50`
- `0x403fe0`
- `0x404430`
- `0x404520`
- `0x405ec0`
- `0x405fd0`
- `0x407870`
- `0x4079b0`
- `0x408ec0`
- `0x409370`
- `0x409710`
- `0x409840`
- `0x40a770`
- `0x40a860`
- `0x40a920`
- `0x40cc00`
- `0x40fbc0`
- `0x41d9f0`
- `0x421240`

## callees

- `0x40d088`

## pseudocode

```c
void __cdecl sub_40D4DD(void *Block)
{
  j__free(Block);
}

```

## disassembly

```asm
0x40d4dd  push    ebp
0x40d4de  mov     ebp, esp
0x40d4e0  push    [ebp+Block]; Block
0x40d4e3  call    j__free
0x40d4e8  pop     ecx
0x40d4e9  pop     ebp
0x40d4ea  retn
```
