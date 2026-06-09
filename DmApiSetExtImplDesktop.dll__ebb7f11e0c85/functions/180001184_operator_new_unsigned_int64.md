# operator new(unsigned __int64)

- ea: `0x180001184`
- end: `0x1800011b5`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180001c00`
- `0x180002dd8`
- `0x1800058ac`
- `0x1800059a4`
- `0x18000a62d`
- `0x18000a6ac`

## callees

- `0x180001184`
- `0x1800019c3`
- `0x1800019cf`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1800011ae`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1800011ae`

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
      JUMPOUT(0x1800011B4LL);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180001184  push    rbx
0x180001186  sub     rsp, 20h
0x18000118a  mov     rbx, rcx
0x18000118d  jmp     short loc_18000119E
0x18000118f  mov     rcx, rbx; Size
0x180001192  call    _callnewh_0
0x180001197  test    eax, eax
0x180001199  jz      short loc_1800011AE
0x18000119b  mov     rcx, rbx; Size
0x18000119e  call    malloc_0
0x1800011a3  test    rax, rax
0x1800011a6  jz      short loc_18000118F
0x1800011a8  add     rsp, 20h
0x1800011ac  pop     rbx
0x1800011ad  retn
0x1800011ae  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
