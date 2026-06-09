# _malloc_base

- ea: `0x140019990`
- end: `0x1400199ee`
- name: `_malloc_base`
- size: `94`
- prototype: `void *__cdecl(size_t Size)`
- caller_count: `10`
- callee_count: `4`
- tags: ``

## callers

- `0x14001001c`
- `0x1400100c4`
- `0x140014d60`
- `0x140016fb0`
- `0x140017498`
- `0x14001c5d0`
- `0x14001d2d4`
- `0x14001dd84`
- `0x140023120`
- `0x14002411c`

## callees

- `0x140016ea0`
- `0x140018a40`
- `0x140018a90`
- `0x140019990`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1400199ce`
- `KERNEL32!HeapAlloc` at `0x1400199ce`

## pseudocode

```c
void *__cdecl malloc_base(size_t Size)
{
  __int64 v1; // rdx
  size_t v2; // rbx
  void *result; // rax

  v2 = Size;
  if ( Size > 0xFFFFFFFFFFFFFFE0uLL )
  {
LABEL_9:
    *(_DWORD *)sub_140016EA0(Size, v1) = 12;
    return 0;
  }
  else
  {
    if ( !Size )
      v2 = 1;
    while ( 1 )
    {
      result = HeapAlloc(hHeap, 0, v2);
      if ( result )
        break;
      if ( !(unsigned int)sub_140018A40() || !(unsigned int)sub_140018A90(v2) )
        goto LABEL_9;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140019990  push    rbx
0x140019992  sub     rsp, 20h
0x140019996  mov     rbx, rcx
0x140019999  cmp     rcx, 0FFFFFFFFFFFFFFE0h
0x14001999d  ja      short loc_1400199DB
0x14001999f  test    rcx, rcx
0x1400199a2  mov     eax, 1
0x1400199a7  cmovz   rbx, rax
0x1400199ab  jmp     short loc_1400199C2
0x1400199ad  call    sub_140018A40
0x1400199b2  test    eax, eax
0x1400199b4  jz      short loc_1400199DB
0x1400199b6  mov     rcx, rbx
0x1400199b9  call    sub_140018A90
0x1400199be  test    eax, eax
0x1400199c0  jz      short loc_1400199DB
0x1400199c2  mov     rcx, cs:hHeap; hHeap
0x1400199c9  mov     r8, rbx; dwBytes
0x1400199cc  xor     edx, edx; dwFlags
0x1400199ce  call    cs:HeapAlloc
0x1400199d4  test    rax, rax
0x1400199d7  jz      short loc_1400199AD
0x1400199d9  jmp     short loc_1400199E8
0x1400199db  call    sub_140016EA0
0x1400199e0  mov     dword ptr [rax], 0Ch
0x1400199e6  xor     eax, eax
0x1400199e8  add     rsp, 20h
0x1400199ec  pop     rbx
0x1400199ed  retn
```
