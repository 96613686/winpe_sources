# _free

- ea: `0x40ef25`
- end: `0x40ef40`
- name: `_free`
- size: `27`
- prototype: `void __cdecl(void *Block)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x40b9dd`
- `0x40d3c1`
- `0x40d424`
- `0x40d7b0`
- `0x40d7da`

## callees

- `0x41001a`

## pseudocode

```c
void __cdecl free(void *Block)
{
  _free_base(Block);
}

```

## disassembly

```asm
0x40ef25  mov     edi, edi
0x40ef27  push    ebp
0x40ef28  mov     ebp, esp
0x40ef2a  push    ecx
0x40ef2b  push    [ebp+Block]; Block
0x40ef2e  mov     [ebp+var_4], 0
0x40ef35  mov     eax, [ebp+var_4]
0x40ef38  call    __free_base
0x40ef3d  pop     ecx
0x40ef3e  leave
0x40ef3f  retn
```
