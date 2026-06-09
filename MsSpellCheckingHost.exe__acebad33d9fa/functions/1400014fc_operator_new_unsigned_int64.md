# operator new(unsigned __int64)

- ea: `0x1400014fc`
- end: `0x14000152d`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `15`
- callee_count: `3`
- tags: ``

## callers

- `0x1400014f0`
- `0x140006314`
- `0x140009b40`
- `0x14000e94c`
- `0x14000e98c`
- `0x14000e9e0`
- `0x14000ea28`
- `0x14000fe00`
- `0x140010358`
- `0x140010440`
- `0x14001056c`
- `0x1400119d0`
- `0x140011a20`
- `0x1400120e3`
- `0x14001235b`

## callees

- `0x1400014fc`
- `0x140001758`
- `0x1400020a0`

## import_xrefs

- `msvcrt!malloc` at `0x140001516`
- `msvcrt!malloc` at `0x140001516`

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
0x1400014fc  push    rbx
0x1400014fe  sub     rsp, 20h
0x140001502  mov     rbx, rcx
0x140001505  jmp     short loc_140001516
0x140001507  mov     rcx, rbx; Size
0x14000150a  call    _callnewh_0
0x14000150f  test    eax, eax
0x140001511  jz      short loc_140001527
0x140001513  mov     rcx, rbx; Size
0x140001516  call    cs:__imp_malloc
0x14000151c  test    rax, rax
0x14000151f  jz      short loc_140001507
0x140001521  add     rsp, 20h
0x140001525  pop     rbx
0x140001526  retn
0x140001527  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
