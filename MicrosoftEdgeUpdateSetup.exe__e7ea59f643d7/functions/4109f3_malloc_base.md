# __malloc_base

- ea: `0x4109f3`
- end: `0x410a41`
- name: `__malloc_base`
- size: `78`
- prototype: `void *__cdecl(size_t Size)`
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x40c2a6`
- `0x40c713`
- `0x40c790`
- `0x40f511`
- `0x40fac9`
- `0x410143`
- `0x410d19`
- `0x413934`
- `0x413c7d`

## callees

- `0x40bcf9`
- `0x40ece3`
- `0x4109f3`
- `0x411762`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x410a25`
- `KERNEL32!HeapAlloc` at `0x410a25`

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
      if ( !sub_40BCF9() || !_callnewh(v1) )
        goto LABEL_8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x4109f3  mov     edi, edi
0x4109f5  push    ebp
0x4109f6  mov     ebp, esp
0x4109f8  push    esi
0x4109f9  mov     esi, [ebp+dwBytes]
0x4109fc  cmp     esi, 0FFFFFFE0h
0x4109ff  ja      short loc_410A31
0x410a01  test    esi, esi
0x410a03  jnz     short loc_410A1C
0x410a05  inc     esi
0x410a06  jmp     short loc_410A1C
0x410a08  call    sub_40BCF9
0x410a0d  test    eax, eax
0x410a0f  jz      short loc_410A31
0x410a11  push    esi; Size
0x410a12  call    __callnewh
0x410a17  pop     ecx
0x410a18  test    eax, eax
0x410a1a  jz      short loc_410A31
0x410a1c  push    esi; dwBytes
0x410a1d  push    0; dwFlags
0x410a1f  push    hHeap; hHeap
0x410a25  call    ds:HeapAlloc
0x410a2b  test    eax, eax
0x410a2d  jz      short loc_410A08
0x410a2f  jmp     short loc_410A3E
0x410a31  call    __errno
0x410a36  mov     dword ptr [eax], 0Ch
0x410a3c  xor     eax, eax
0x410a3e  pop     esi
0x410a3f  pop     ebp
0x410a40  retn
```
