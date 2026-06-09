# I_FreeReaderStates

- ea: `0x1800140d0`
- end: `0x18001412f`
- name: `I_FreeReaderStates`
- size: `95`
- prototype: `BOOL __fastcall(_QWORD *lpMem, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ba4c`
- `0x18001c158`

## callees

- `0x1800140d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014106`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001411e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014106`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001411e`

## pseudocode

```c
BOOL __fastcall I_FreeReaderStates(_QWORD *lpMem, int a2)
{
  int v2; // ebx
  void *v4; // r8
  BOOL result; // eax

  if ( lpMem )
  {
    v2 = a2;
    while ( v2 )
    {
      while ( 1 )
      {
        v4 = (void *)lpMem[8 * (unsigned __int64)(unsigned int)--v2];
        if ( !v4 )
          break;
        if ( !v2 )
          return HeapFree(hHeap, 0, lpMem);
        HeapFree(hHeap, 0, v4);
      }
    }
    return HeapFree(hHeap, 0, lpMem);
  }
  return result;
}

```

## disassembly

```asm
0x1800140d0  test    rcx, rcx
0x1800140d3  jz      short locret_18001412E
0x1800140d5  mov     [rsp+arg_0], rbx
0x1800140da  push    rdi
0x1800140db  sub     rsp, 20h
0x1800140df  mov     ebx, edx
0x1800140e1  mov     rdi, rcx
0x1800140e4  test    edx, edx
0x1800140e6  jz      short loc_180014112
0x1800140e8  dec     ebx
0x1800140ea  mov     eax, ebx
0x1800140ec  shl     rax, 6
0x1800140f0  mov     r8, [rax+rdi]; lpMem
0x1800140f4  test    r8, r8
0x1800140f7  jz      short loc_18001410E
0x1800140f9  test    ebx, ebx
0x1800140fb  jz      short loc_180014112
0x1800140fd  mov     rcx, cs:hHeap; hHeap
0x180014104  xor     edx, edx; dwFlags
0x180014106  call    cs:__imp_HeapFree
0x18001410c  jmp     short loc_1800140E8
0x18001410e  test    ebx, ebx
0x180014110  jnz     short loc_1800140E8
0x180014112  mov     rcx, cs:hHeap; hHeap
0x180014119  mov     r8, rdi; lpMem
0x18001411c  xor     edx, edx; dwFlags
0x18001411e  call    cs:__imp_HeapFree
0x180014124  mov     rbx, [rsp+28h+arg_0]
0x180014129  add     rsp, 20h
0x18001412d  pop     rdi
0x18001412e  retn
```
