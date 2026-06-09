# __calloc_base

- ea: `0x40ffbd`
- end: `0x41001a`
- name: `__calloc_base`
- size: `93`
- prototype: `void *__cdecl(size_t Count, size_t Size)`
- caller_count: `10`
- callee_count: `4`
- tags: ``

## callers

- `0x40e76a`
- `0x40e812`
- `0x40f55e`
- `0x40f9a9`
- `0x40fa66`
- `0x40fb00`
- `0x4102a0`
- `0x4104ea`
- `0x410f74`
- `0x412680`

## callees

- `0x40e20b`
- `0x40eee9`
- `0x40ffa9`
- `0x40ffbd`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x40fffe`
- `KERNEL32!HeapAlloc` at `0x40fffe`

## pseudocode

```c
void *__cdecl _calloc_base(size_t Count, size_t Size)
{
  SIZE_T v2; // esi
  void *result; // eax

  if ( Count && 0xFFFFFFE0 / Count < Size )
  {
LABEL_9:
    *_errno() = 12;
    return 0;
  }
  else
  {
    v2 = Size * Count;
    if ( !(Size * Count) )
      v2 = 1;
    while ( 1 )
    {
      result = HeapAlloc(hHeap, 8u, v2);
      if ( result )
        break;
      if ( !sub_40EEE9() || !_callnewh(v2) )
        goto LABEL_9;
    }
  }
  return result;
}

```

## disassembly

```asm
0x40ffbd  mov     edi, edi
0x40ffbf  push    ebp
0x40ffc0  mov     ebp, esp
0x40ffc2  push    esi
0x40ffc3  mov     esi, [ebp+Count]
0x40ffc6  test    esi, esi
0x40ffc8  jz      short loc_40FFD6
0x40ffca  push    0FFFFFFE0h
0x40ffcc  xor     edx, edx
0x40ffce  pop     eax
0x40ffcf  div     esi
0x40ffd1  cmp     eax, [ebp+Size]
0x40ffd4  jb      short loc_41000A
0x40ffd6  imul    esi, [ebp+Size]
0x40ffda  test    esi, esi
0x40ffdc  jnz     short loc_40FFF5
0x40ffde  inc     esi
0x40ffdf  jmp     short loc_40FFF5
0x40ffe1  call    sub_40EEE9
0x40ffe6  test    eax, eax
0x40ffe8  jz      short loc_41000A
0x40ffea  push    esi; Size
0x40ffeb  call    __callnewh
0x40fff0  pop     ecx
0x40fff1  test    eax, eax
0x40fff3  jz      short loc_41000A
0x40fff5  push    esi; dwBytes
0x40fff6  push    8; dwFlags
0x40fff8  push    hHeap; hHeap
0x40fffe  call    ds:HeapAlloc
0x410004  test    eax, eax
0x410006  jz      short loc_40FFE1
0x410008  jmp     short loc_410017
0x41000a  call    __errno
0x41000f  mov     dword ptr [eax], 0Ch
0x410015  xor     eax, eax
0x410017  pop     esi
0x410018  pop     ebp
0x410019  retn
```
