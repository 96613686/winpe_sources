# __calloc_base

- ea: `0x40ecf6`
- end: `0x40ed53`
- name: `__calloc_base`
- size: `93`
- prototype: `void *__cdecl(size_t Count, size_t Size)`
- caller_count: `10`
- callee_count: `4`
- tags: ``

## callers

- `0x40b581`
- `0x40b62e`
- `0x40c34f`
- `0x40e819`
- `0x40e8d6`
- `0x40e970`
- `0x40f135`
- `0x40f530`
- `0x4102a9`
- `0x411d90`

## callees

- `0x40bcf9`
- `0x40ece3`
- `0x40ecf6`
- `0x411762`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x40ed37`
- `KERNEL32!HeapAlloc` at `0x40ed37`

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
      if ( !sub_40BCF9() || !_callnewh(v2) )
        goto LABEL_9;
    }
  }
  return result;
}

```

## disassembly

```asm
0x40ecf6  mov     edi, edi
0x40ecf8  push    ebp
0x40ecf9  mov     ebp, esp
0x40ecfb  push    esi
0x40ecfc  mov     esi, [ebp+Count]
0x40ecff  test    esi, esi
0x40ed01  jz      short loc_40ED0F
0x40ed03  push    0FFFFFFE0h
0x40ed05  xor     edx, edx
0x40ed07  pop     eax
0x40ed08  div     esi
0x40ed0a  cmp     eax, [ebp+Size]
0x40ed0d  jb      short loc_40ED43
0x40ed0f  imul    esi, [ebp+Size]
0x40ed13  test    esi, esi
0x40ed15  jnz     short loc_40ED2E
0x40ed17  inc     esi
0x40ed18  jmp     short loc_40ED2E
0x40ed1a  call    sub_40BCF9
0x40ed1f  test    eax, eax
0x40ed21  jz      short loc_40ED43
0x40ed23  push    esi; Size
0x40ed24  call    __callnewh
0x40ed29  pop     ecx
0x40ed2a  test    eax, eax
0x40ed2c  jz      short loc_40ED43
0x40ed2e  push    esi; dwBytes
0x40ed2f  push    8; dwFlags
0x40ed31  push    hHeap; hHeap
0x40ed37  call    ds:HeapAlloc
0x40ed3d  test    eax, eax
0x40ed3f  jz      short loc_40ED1A
0x40ed41  jmp     short loc_40ED50
0x40ed43  call    __errno
0x40ed48  mov     dword ptr [eax], 0Ch
0x40ed4e  xor     eax, eax
0x40ed50  pop     esi
0x40ed51  pop     ebp
0x40ed52  retn
```
