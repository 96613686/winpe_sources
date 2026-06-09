# _free

- ea: `0x40c28b`
- end: `0x40c2a6`
- name: `_free`
- size: `27`
- prototype: `void __cdecl(void *Block)`
- caller_count: `22`
- callee_count: `1`
- tags: ``

## callers

- `0x4033ae`
- `0x4040f0`
- `0x405690`
- `0x4056bc`
- `0x405842`
- `0x4058c2`
- `0x4058e9`
- `0x4059b0`
- `0x405d21`
- `0x405df6`
- `0x405ecb`
- `0x405ff0`
- `0x4061ae`
- `0x4061f3`
- `0x406536`
- `0x406551`
- `0x409420`
- `0x40944a`
- `0x40afd4`
- `0x40b037`
- `0x4194ec`
- `0x41bee0`

## callees

- `0x40ed53`

## pseudocode

```c
void __cdecl free(void *Block)
{
  _free_base(Block);
}

```

## disassembly

```asm
0x40c28b  mov     edi, edi
0x40c28d  push    ebp
0x40c28e  mov     ebp, esp
0x40c290  push    ecx
0x40c291  push    [ebp+Block]; Block
0x40c294  mov     [ebp+var_4], 0
0x40c29b  mov     eax, [ebp+var_4]
0x40c29e  call    __free_base
0x40c2a3  pop     ecx
0x40c2a4  leave
0x40c2a5  retn
```
