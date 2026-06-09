# _calloc_base

- ea: `0x1800120b0`
- end: `0x180012125`
- name: `_calloc_base`
- size: `117`
- prototype: `void *__cdecl(size_t Count, size_t Size)`
- caller_count: `13`
- callee_count: `4`
- tags: ``

## callers

- `0x18000dd40`
- `0x18000df94`
- `0x18000e880`
- `0x1800102a4`
- `0x180010378`
- `0x180010420`
- `0x180011ad0`
- `0x180012654`
- `0x180016da8`
- `0x18002218c`
- `0x180023724`
- `0x180023918`
- `0x180023984`

## callees

- `0x18000bfbc`
- `0x18000e744`
- `0x1800120b0`
- `0x1800148a4`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180012105`
- `KERNEL32!HeapAlloc` at `0x180012105`

## pseudocode

```c
void *__cdecl calloc_base(size_t Count, size_t Size)
{
  SIZE_T v2; // rbx
  void *result; // rax

  if ( Count && 0xFFFFFFFFFFFFFFE0uLL / Count < Size )
  {
LABEL_10:
    *errno() = 12;
    return 0;
  }
  else
  {
    v2 = Size * Count;
    if ( !(Size * Count) )
      v2 = 1;
    while ( 1 )
    {
      result = HeapAlloc(_acrt_heap, 8u, v2);
      if ( result )
        break;
      if ( !query_new_mode() || !callnewh(v2) )
        goto LABEL_10;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800120b0  push    rbx
0x1800120b2  sub     rsp, 20h
0x1800120b6  mov     r8, rdx
0x1800120b9  mov     rbx, rcx
0x1800120bc  test    rcx, rcx
0x1800120bf  jz      short loc_1800120CF
0x1800120c1  xor     edx, edx
0x1800120c3  lea     rax, [rdx-20h]
0x1800120c7  div     rbx
0x1800120ca  cmp     rax, r8
0x1800120cd  jb      short loc_180012112
0x1800120cf  imul    rbx, r8
0x1800120d3  mov     eax, 1
0x1800120d8  test    rbx, rbx
0x1800120db  cmovz   rbx, rax
0x1800120df  jmp     short loc_1800120F6
0x1800120e1  call    _query_new_mode
0x1800120e6  test    eax, eax
0x1800120e8  jz      short loc_180012112
0x1800120ea  mov     rcx, rbx; Size
0x1800120ed  call    _callnewh
0x1800120f2  test    eax, eax
0x1800120f4  jz      short loc_180012112
0x1800120f6  mov     rcx, cs:__acrt_heap; hHeap
0x1800120fd  mov     r8, rbx; dwBytes
0x180012100  mov     edx, 8; dwFlags
0x180012105  call    cs:__imp_HeapAlloc
0x18001210b  test    rax, rax
0x18001210e  jz      short loc_1800120E1
0x180012110  jmp     short loc_18001211F
0x180012112  call    _errno
0x180012117  mov     dword ptr [rax], 0Ch
0x18001211d  xor     eax, eax
0x18001211f  add     rsp, 20h
0x180012123  pop     rbx
0x180012124  retn
```
