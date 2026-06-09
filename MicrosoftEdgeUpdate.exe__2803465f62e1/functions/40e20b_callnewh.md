# __callnewh

- ea: `0x40e20b`
- end: `0x40e238`
- name: `__callnewh`
- size: `45`
- prototype: `int __cdecl(size_t Size)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x40b5ee`
- `0x40fda8`
- `0x40ffbd`
- `0x41361d`

## callees

- `0x407eb0`
- `0x40e20b`
- `0x40e238`

## pseudocode

```c
int __cdecl _callnewh(size_t Size)
{
  _PNH new_handler; // eax

  new_handler = _query_new_handler();
  return new_handler && new_handler(Size);
}

```

## disassembly

```asm
0x40e20b  mov     edi, edi
0x40e20d  push    ebp
0x40e20e  mov     ebp, esp
0x40e210  push    esi
0x40e211  call    __query_new_handler
0x40e216  mov     esi, eax
0x40e218  test    esi, esi
0x40e21a  jz      short loc_40E233
0x40e21c  push    [ebp+Size]
0x40e21f  mov     ecx, esi
0x40e221  call    ds:___guard_check_icall_fptr
0x40e227  call    esi
0x40e229  pop     ecx
0x40e22a  test    eax, eax
0x40e22c  jz      short loc_40E233
0x40e22e  xor     eax, eax
0x40e230  inc     eax
0x40e231  jmp     short loc_40E235
0x40e233  xor     eax, eax
0x40e235  pop     esi
0x40e236  pop     ebp
0x40e237  retn
```
