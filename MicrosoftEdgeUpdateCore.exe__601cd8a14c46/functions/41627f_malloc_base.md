# __malloc_base

- ea: `0x41627f`
- end: `0x4162cd`
- name: `__malloc_base`
- size: `78`
- prototype: `void *__cdecl(size_t Size)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x4116f4`
- `0x411ba6`
- `0x411c23`
- `0x413ccd`
- `0x414700`
- `0x414d77`
- `0x416715`
- `0x4183e0`

## callees

- `0x410443`
- `0x4115d9`
- `0x4154e4`
- `0x41627f`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x4162b1`
- `KERNEL32!HeapAlloc` at `0x4162b1`

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
      if ( !sub_4115D9() || !_callnewh(v1) )
        goto LABEL_8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x41627f  mov     edi, edi
0x416281  push    ebp
0x416282  mov     ebp, esp
0x416284  push    esi
0x416285  mov     esi, [ebp+dwBytes]
0x416288  cmp     esi, 0FFFFFFE0h
0x41628b  ja      short loc_4162BD
0x41628d  test    esi, esi
0x41628f  jnz     short loc_4162A8
0x416291  inc     esi
0x416292  jmp     short loc_4162A8
0x416294  call    sub_4115D9
0x416299  test    eax, eax
0x41629b  jz      short loc_4162BD
0x41629d  push    esi; Size
0x41629e  call    __callnewh
0x4162a3  pop     ecx
0x4162a4  test    eax, eax
0x4162a6  jz      short loc_4162BD
0x4162a8  push    esi; dwBytes
0x4162a9  push    0; dwFlags
0x4162ab  push    hHeap; hHeap
0x4162b1  call    ds:HeapAlloc
0x4162b7  test    eax, eax
0x4162b9  jz      short loc_416294
0x4162bb  jmp     short loc_4162CA
0x4162bd  call    __errno
0x4162c2  mov     dword ptr [eax], 0Ch
0x4162c8  xor     eax, eax
0x4162ca  pop     esi
0x4162cb  pop     ebp
0x4162cc  retn
```
