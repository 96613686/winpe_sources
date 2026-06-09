# __calloc_base

- ea: `0x413e19`
- end: `0x413e76`
- name: `__calloc_base`
- size: `93`
- prototype: `void *__cdecl(size_t Count, size_t Size)`
- caller_count: `10`
- callee_count: `4`
- tags: ``

## callers

- `0x410bf2`
- `0x410c9a`
- `0x411759`
- `0x413a39`
- `0x413af6`
- `0x413b90`
- `0x4140c0`
- `0x41430a`
- `0x415b10`
- `0x415d2a`

## callees

- `0x410443`
- `0x4115d9`
- `0x413e19`
- `0x4154e4`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x413e5a`
- `KERNEL32!HeapAlloc` at `0x413e5a`

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
      if ( !sub_4115D9() || !_callnewh(v2) )
        goto LABEL_9;
    }
  }
  return result;
}

```

## disassembly

```asm
0x413e19  mov     edi, edi
0x413e1b  push    ebp
0x413e1c  mov     ebp, esp
0x413e1e  push    esi
0x413e1f  mov     esi, [ebp+Count]
0x413e22  test    esi, esi
0x413e24  jz      short loc_413E32
0x413e26  push    0FFFFFFE0h
0x413e28  xor     edx, edx
0x413e2a  pop     eax
0x413e2b  div     esi
0x413e2d  cmp     eax, [ebp+Size]
0x413e30  jb      short loc_413E66
0x413e32  imul    esi, [ebp+Size]
0x413e36  test    esi, esi
0x413e38  jnz     short loc_413E51
0x413e3a  inc     esi
0x413e3b  jmp     short loc_413E51
0x413e3d  call    sub_4115D9
0x413e42  test    eax, eax
0x413e44  jz      short loc_413E66
0x413e46  push    esi; Size
0x413e47  call    __callnewh
0x413e4c  pop     ecx
0x413e4d  test    eax, eax
0x413e4f  jz      short loc_413E66
0x413e51  push    esi; dwBytes
0x413e52  push    8; dwFlags
0x413e54  push    hHeap; hHeap
0x413e5a  call    ds:HeapAlloc
0x413e60  test    eax, eax
0x413e62  jz      short loc_413E3D
0x413e64  jmp     short loc_413E73
0x413e66  call    __errno
0x413e6b  mov     dword ptr [eax], 0Ch
0x413e71  xor     eax, eax
0x413e73  pop     esi
0x413e74  pop     ebp
0x413e75  retn
```
