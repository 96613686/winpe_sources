# unknown_libname_5

- ea: `0x40e91f`
- end: `0x40e94e`
- name: `unknown_libname_5`
- size: `47`
- prototype: `void __cdecl(void **Block)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x40e812`
- `0x40e980`
- `0x40e9a0`
- `0x40e9bb`

## callees

- `0x40e91f`
- `0x41001a`

## pseudocode

```c
// Microsoft VisualC universal runtime
void __cdecl unknown_libname_5(void **Block)
{
  void *v1; // eax
  void **v2; // edi

  if ( Block )
  {
    v1 = *Block;
    v2 = Block;
    while ( v1 )
    {
      _free_base(v1);
      v1 = *++v2;
    }
    _free_base(Block);
  }
}

```

## disassembly

```asm
0x40e91f  mov     edi, edi
0x40e921  push    ebp
0x40e922  mov     ebp, esp
0x40e924  push    esi
0x40e925  mov     esi, [ebp+Block]
0x40e928  test    esi, esi
0x40e92a  jz      short loc_40E94B
0x40e92c  mov     eax, [esi]
0x40e92e  push    edi
0x40e92f  mov     edi, esi
0x40e931  jmp     short loc_40E93F
0x40e933  push    eax; Block
0x40e934  call    __free_base
0x40e939  lea     edi, [edi+4]
0x40e93c  mov     eax, [edi]
0x40e93e  pop     ecx
0x40e93f  test    eax, eax
0x40e941  jnz     short loc_40E933
0x40e943  push    esi; Block
0x40e944  call    __free_base
0x40e949  pop     ecx
0x40e94a  pop     edi
0x40e94b  pop     esi
0x40e94c  pop     ebp
0x40e94d  retn
```
