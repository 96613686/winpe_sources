# __malloc_base

- ea: `0x40fda8`
- end: `0x40fdf6`
- name: `__malloc_base`
- size: `78`
- prototype: `void *__cdecl(size_t Size)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x40e294`
- `0x4108e0`
- `0x410ef3`
- `0x4116ed`
- `0x412c0a`
- `0x41361d`

## callees

- `0x40e20b`
- `0x40eee9`
- `0x40fda8`
- `0x40ffa9`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x40fdda`
- `KERNEL32!HeapAlloc` at `0x40fdda`

## pseudocode

```c
void *__cdecl _malloc_base(size_t Size)
{
  size_t v1; // esi
  void *result; // eax

  v1 = Size;
  if ( Size > 0xFFFFFFE0 )
  {
LABEL_8:
    *_errno() = 12;
    return 0;
  }
  else
  {
    if ( !Size )
      v1 = 1;
    while ( 1 )
    {
      result = HeapAlloc(hHeap, 0, v1);
      if ( result )
        break;
      if ( !sub_40EEE9() || !_callnewh(v1) )
        goto LABEL_8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x40fda8  mov     edi, edi
0x40fdaa  push    ebp
0x40fdab  mov     ebp, esp
0x40fdad  push    esi
0x40fdae  mov     esi, [ebp+dwBytes]
0x40fdb1  cmp     esi, 0FFFFFFE0h
0x40fdb4  ja      short loc_40FDE6
0x40fdb6  test    esi, esi
0x40fdb8  jnz     short loc_40FDD1
0x40fdba  inc     esi
0x40fdbb  jmp     short loc_40FDD1
0x40fdbd  call    sub_40EEE9
0x40fdc2  test    eax, eax
0x40fdc4  jz      short loc_40FDE6
0x40fdc6  push    esi; Size
0x40fdc7  call    __callnewh
0x40fdcc  pop     ecx
0x40fdcd  test    eax, eax
0x40fdcf  jz      short loc_40FDE6
0x40fdd1  push    esi; dwBytes
0x40fdd2  push    0; dwFlags
0x40fdd4  push    hHeap; hHeap
0x40fdda  call    ds:HeapAlloc
0x40fde0  test    eax, eax
0x40fde2  jz      short loc_40FDBD
0x40fde4  jmp     short loc_40FDF3
0x40fde6  call    __errno
0x40fdeb  mov     dword ptr [eax], 0Ch
0x40fdf1  xor     eax, eax
0x40fdf3  pop     esi
0x40fdf4  pop     ebp
0x40fdf5  retn
```
