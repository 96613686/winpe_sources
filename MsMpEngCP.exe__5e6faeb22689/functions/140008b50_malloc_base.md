# _malloc_base

- ea: `0x140008b50`
- end: `0x140008bae`
- name: `_malloc_base`
- size: `94`
- prototype: `void *__cdecl(size_t Size)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x140005990`
- `0x1400074c0`
- `0x140007ca4`
- `0x140008e18`
- `0x14000ade8`
- `0x14000b4e0`

## callees

- `0x140005370`
- `0x14000689c`
- `0x140008b50`
- `0x140009b00`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140008b8e`
- `KERNEL32!HeapAlloc` at `0x140008b8e`

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
    *(_DWORD *)sub_14000689C() = 12;
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
      if ( !(unsigned int)sub_140005370() || !(unsigned int)sub_140009B00(v1) )
        goto LABEL_9;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140008b50  push    rbx
0x140008b52  sub     rsp, 20h
0x140008b56  mov     rbx, rcx
0x140008b59  cmp     rcx, 0FFFFFFFFFFFFFFE0h
0x140008b5d  ja      short loc_140008B9B
0x140008b5f  test    rcx, rcx
0x140008b62  mov     eax, 1
0x140008b67  cmovz   rbx, rax
0x140008b6b  jmp     short loc_140008B82
0x140008b6d  call    sub_140005370
0x140008b72  test    eax, eax
0x140008b74  jz      short loc_140008B9B
0x140008b76  mov     rcx, rbx
0x140008b79  call    sub_140009B00
0x140008b7e  test    eax, eax
0x140008b80  jz      short loc_140008B9B
0x140008b82  mov     rcx, cs:hHeap; hHeap
0x140008b89  mov     r8, rbx; dwBytes
0x140008b8c  xor     edx, edx; dwFlags
0x140008b8e  call    cs:HeapAlloc
0x140008b94  test    rax, rax
0x140008b97  jz      short loc_140008B6D
0x140008b99  jmp     short loc_140008BA8
0x140008b9b  call    sub_14000689C
0x140008ba0  mov     dword ptr [rax], 0Ch
0x140008ba6  xor     eax, eax
0x140008ba8  add     rsp, 20h
0x140008bac  pop     rbx
0x140008bad  retn
```
