# _malloc_base

- ea: `0x18000fe7c`
- end: `0x18000feda`
- name: `_malloc_base`
- size: `94`
- prototype: `void *__cdecl(size_t Size)`
- caller_count: `10`
- callee_count: `4`
- tags: ``

## callers

- `0x18000bc80`
- `0x18000c250`
- `0x18000c2f8`
- `0x180010590`
- `0x180012144`
- `0x1800122bc`
- `0x1800131d8`
- `0x180013954`
- `0x180016c18`
- `0x180017a54`

## callees

- `0x18000bfbc`
- `0x18000e744`
- `0x18000fe7c`
- `0x1800148a4`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000feba`
- `KERNEL32!HeapAlloc` at `0x18000feba`

## pseudocode

```c
void *__cdecl malloc_base(size_t Size)
{
  size_t v1; // rbx
  void *result; // rax

  v1 = Size;
  if ( Size > 0xFFFFFFFFFFFFFFE0uLL )
  {
LABEL_9:
    *errno() = 12;
    return 0;
  }
  else
  {
    if ( !Size )
      v1 = 1;
    while ( 1 )
    {
      result = HeapAlloc(_acrt_heap, 0, v1);
      if ( result )
        break;
      if ( !query_new_mode() || !callnewh(v1) )
        goto LABEL_9;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000fe7c  push    rbx
0x18000fe7e  sub     rsp, 20h
0x18000fe82  mov     rbx, rcx
0x18000fe85  cmp     rcx, 0FFFFFFFFFFFFFFE0h
0x18000fe89  ja      short loc_18000FEC7
0x18000fe8b  test    rcx, rcx
0x18000fe8e  mov     eax, 1
0x18000fe93  cmovz   rbx, rax
0x18000fe97  jmp     short loc_18000FEAE
0x18000fe99  call    _query_new_mode
0x18000fe9e  test    eax, eax
0x18000fea0  jz      short loc_18000FEC7
0x18000fea2  mov     rcx, rbx; Size
0x18000fea5  call    _callnewh
0x18000feaa  test    eax, eax
0x18000feac  jz      short loc_18000FEC7
0x18000feae  mov     rcx, cs:__acrt_heap; hHeap
0x18000feb5  mov     r8, rbx; dwBytes
0x18000feb8  xor     edx, edx; dwFlags
0x18000feba  call    cs:__imp_HeapAlloc
0x18000fec0  test    rax, rax
0x18000fec3  jz      short loc_18000FE99
0x18000fec5  jmp     short loc_18000FED4
0x18000fec7  call    _errno
0x18000fecc  mov     dword ptr [rax], 0Ch
0x18000fed2  xor     eax, eax
0x18000fed4  add     rsp, 20h
0x18000fed8  pop     rbx
0x18000fed9  retn
```
