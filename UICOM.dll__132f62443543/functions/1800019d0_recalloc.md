# _recalloc

- ea: `0x1800019d0`
- end: `0x180001a24`
- name: `_recalloc`
- size: `84`
- prototype: `void *__cdecl(void *Block, size_t Count, size_t Size)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180002448`

## callees

- `0x1800019d0`
- `0x180001cf3`
- `0x180001d00`
- `0x180001df7`

## pseudocode

```c
void *__cdecl recalloc(void *Block, size_t Count, size_t Size)
{
  if ( Count && 0xFFFFFFFFFFFFFFE0uLL / Count < Size )
  {
    *errno_0() = 12;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  return realloc_0(Block, Size * Count);
}

```

## disassembly

```asm
0x1800019d0  sub     rsp, 38h
0x1800019d4  mov     r9, rdx
0x1800019d7  test    rdx, rdx
0x1800019da  jz      short loc_180001A14
0x1800019dc  xor     edx, edx
0x1800019de  lea     rax, [rdx-20h]
0x1800019e2  div     r9
0x1800019e5  cmp     rax, r8
0x1800019e8  jnb     short loc_180001A14
0x1800019ea  call    _errno_0
0x1800019ef  xor     r9d, r9d; LineNo
0x1800019f2  mov     [rsp+38h+Reserved], 0; Reserved
0x1800019fb  xor     r8d, r8d; FileName
0x1800019fe  xor     edx, edx; FunctionName
0x180001a00  xor     ecx, ecx; Expression
0x180001a02  mov     dword ptr [rax], 0Ch
0x180001a08  call    _invalid_parameter
0x180001a0d  xor     eax, eax
0x180001a0f  add     rsp, 38h
0x180001a13  retn
0x180001a14  imul    r9, r8
0x180001a18  mov     rdx, r9; Size
0x180001a1b  add     rsp, 38h
0x180001a1f  jmp     realloc_0
```
