# operator new(unsigned __int64)

- ea: `0x140001674`
- end: `0x1400016a5`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `13`
- callee_count: `3`
- tags: ``

## callers

- `0x140002288`
- `0x140002294`
- `0x1400085ec`
- `0x1400086e0`
- `0x140008850`
- `0x1400088f0`
- `0x140008994`
- `0x14000aa3c`
- `0x14000b454`
- `0x14000bca4`
- `0x14000d21c`
- `0x14000e7e3`
- `0x14000e85c`

## callees

- `0x140001674`
- `0x140001ba6`
- `0x140001bb2`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14000169e`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14000169e`

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
      JUMPOUT(0x1400016A4LL);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140001674  push    rbx
0x140001676  sub     rsp, 20h
0x14000167a  mov     rbx, rcx
0x14000167d  jmp     short loc_14000168E
0x14000167f  mov     rcx, rbx; Size
0x140001682  call    _callnewh_0
0x140001687  test    eax, eax
0x140001689  jz      short loc_14000169E
0x14000168b  mov     rcx, rbx; Size
0x14000168e  call    malloc_0
0x140001693  test    rax, rax
0x140001696  jz      short loc_14000167F
0x140001698  add     rsp, 20h
0x14000169c  pop     rbx
0x14000169d  retn
0x14000169e  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
