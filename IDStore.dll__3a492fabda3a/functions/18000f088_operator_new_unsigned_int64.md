# operator new(unsigned __int64)

- ea: `0x18000f088`
- end: `0x18000f0b9`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `13`
- callee_count: `3`
- tags: ``

## callers

- `0x180003a70`
- `0x180004300`
- `0x180005ea0`
- `0x180005fe0`
- `0x180006260`
- `0x180007a10`
- `0x180007b20`
- `0x180008260`
- `0x18000e9fc`
- `0x1800105dc`
- `0x1800106d0`
- `0x180010d24`
- `0x180010e78`

## callees

- `0x18000f088`
- `0x18000f238`
- `0x18000fb46`

## import_xrefs

- `msvcrt!malloc` at `0x18000f0a2`
- `msvcrt!malloc` at `0x18000f0a2`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax

  for ( i = Size; ; Size = i )
  {
    result = malloc(Size);
    if ( result )
      break;
    if ( !callnewh_0(i) )
      std::_Xbad_alloc();
  }
  return result;
}

```

## disassembly

```asm
0x18000f088  push    rbx
0x18000f08a  sub     rsp, 20h
0x18000f08e  mov     rbx, rcx
0x18000f091  jmp     short loc_18000F0A2
0x18000f093  mov     rcx, rbx; Size
0x18000f096  call    _callnewh_0
0x18000f09b  test    eax, eax
0x18000f09d  jz      short loc_18000F0B3
0x18000f09f  mov     rcx, rbx; Size
0x18000f0a2  call    cs:__imp_malloc
0x18000f0a8  test    rax, rax
0x18000f0ab  jz      short loc_18000F093
0x18000f0ad  add     rsp, 20h
0x18000f0b1  pop     rbx
0x18000f0b2  retn
0x18000f0b3  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
