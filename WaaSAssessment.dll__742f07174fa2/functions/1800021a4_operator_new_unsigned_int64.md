# operator new(unsigned __int64)

- ea: `0x1800021a4`
- end: `0x1800021d5`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x1800021dc`
- `0x180002f58`
- `0x180004898`
- `0x180004a50`
- `0x18000b400`
- `0x180019ccc`

## callees

- `0x1800021a4`
- `0x180002b86`
- `0x180002b92`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1800021ce`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1800021ce`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax

  for ( i = Size; ; Size = i )
  {
    result = malloc_0(Size);
    if ( result )
      break;
    if ( !callnewh_0(i) )
    {
      std::_Xbad_alloc();
      JUMPOUT(0x1800021D4LL);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800021a4  push    rbx
0x1800021a6  sub     rsp, 20h
0x1800021aa  mov     rbx, rcx
0x1800021ad  jmp     short loc_1800021BE
0x1800021af  mov     rcx, rbx; Size
0x1800021b2  call    _callnewh_0
0x1800021b7  test    eax, eax
0x1800021b9  jz      short loc_1800021CE
0x1800021bb  mov     rcx, rbx; Size
0x1800021be  call    malloc_0
0x1800021c3  test    rax, rax
0x1800021c6  jz      short loc_1800021AF
0x1800021c8  add     rsp, 20h
0x1800021cc  pop     rbx
0x1800021cd  retn
0x1800021ce  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
