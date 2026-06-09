# sub_401FBB

- ea: `0x401fbb`
- end: `0x401ff3`
- name: `sub_401FBB`
- size: `56`
- prototype: `_DWORD *__thiscall(_DWORD *this, int)`
- caller_count: `44`
- callee_count: `3`
- tags: ``

## callers

- `0x401290`
- `0x4012b0`
- `0x401cfa`
- `0x402e3c`
- `0x40353b`
- `0x4035b2`
- `0x4036d1`
- `0x404733`
- `0x404866`
- `0x404ba2`
- `0x4057be`
- `0x405ba1`
- `0x4060c5`
- `0x4061e9`
- `0x406257`
- `0x40654c`
- `0x40672d`
- `0x406b17`
- `0x406c4a`
- `0x407389`
- `0x40775a`
- `0x4078b3`
- `0x408194`
- `0x40885e`
- `0x4099f1`
- `0x409aee`
- `0x409d8e`
- `0x409dbf`
- `0x409ef8`
- `0x409feb`
- `0x40a0cf`
- `0x40a121`
- `0x40a243`
- `0x40a31b`
- `0x40a3a1`
- `0x40a793`
- `0x40a943`
- `0x40aa5c`
- `0x40b050`
- `0x40b905`
- `0x40bb5b`
- `0x40bba1`
- `0x40bca4`
- `0x40cd6a`

## callees

- `0x401aa5`
- `0x401fbb`
- `0x402330`

## pseudocode

```c
_DWORD *__thiscall sub_401FBB(_DWORD *this, int a2)
{
  if ( !a2 )
    sub_401AA5(-2147467259);
  *this = (*(int (__thiscall **)(int))(*(_DWORD *)a2 + 12))(a2) + 16;
  return this;
}

```

## disassembly

```asm
0x401fbb  push    ebp
0x401fbc  mov     ebp, esp
0x401fbe  push    ebx
0x401fbf  push    esi
0x401fc0  push    edi
0x401fc1  mov     edi, [ebp+arg_0]
0x401fc4  mov     ebx, ecx
0x401fc6  test    edi, edi
0x401fc8  jz      short loc_401FE9
0x401fca  mov     eax, [edi]
0x401fcc  mov     esi, [eax+0Ch]
0x401fcf  mov     ecx, esi
0x401fd1  call    ds:___guard_check_icall_fptr
0x401fd7  mov     ecx, edi
0x401fd9  call    esi
0x401fdb  add     eax, 10h
0x401fde  pop     edi
0x401fdf  mov     [ebx], eax
0x401fe1  mov     eax, ebx
0x401fe3  pop     esi
0x401fe4  pop     ebx
0x401fe5  pop     ebp
0x401fe6  retn    4
0x401fe9  push    80004005h
0x401fee  call    sub_401AA5
```
