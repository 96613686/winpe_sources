# std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)

- ea: `0x180002880`
- end: `0x1800028ef`
- name: `??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z`
- size: `111`
- prototype: `_QWORD *__fastcall(size_t)`
- caller_count: `32`
- callee_count: `3`
- tags: ``

## callers

- `0x1800029f0`
- `0x180008700`
- `0x18000b2d0`
- `0x18000c6e0`
- `0x18000cca0`
- `0x180010320`
- `0x180012900`
- `0x180012a60`
- `0x180012c50`
- `0x180014440`
- `0x1800146e0`
- `0x1800154d0`
- `0x180019a10`
- `0x18001b200`
- `0x18001b340`
- `0x18001b9a0`
- `0x18001cc10`
- `0x18001d320`
- `0x18001e310`
- `0x180025470`
- `0x180026f60`
- `0x180028550`
- `0x180028730`
- `0x180028d10`
- `0x1800299b0`
- `0x18002a4b0`
- `0x18002a740`
- `0x18002a960`
- `0x18002b2e0`
- `0x18002b3b0`
- `0x18002b6e0`
- `0x18002b870`

## callees

- `0x180002880`
- `0x1800029d0`
- `0x180035060`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800028c2`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800028c2`

## pseudocode

```c
_QWORD *__fastcall std::_Allocate<16,std::_Default_allocate_traits>(size_t a1)
{
  _QWORD *result; // rax
  void *v2; // rax
  void *v3; // rcx

  if ( !a1 )
    return 0;
  if ( a1 < 0x1000 )
  {
    _mm_lfence();
    return operator new(a1);
  }
  else
  {
    if ( a1 + 39 < a1 )
      __scrt_throw_std_bad_array_new_length();
    _mm_lfence();
    v2 = operator new(a1 + 39);
    v3 = v2;
    if ( !v2 )
      _invoke_watson(0, 0, 0, 0, 0);
    _mm_lfence();
    result = (_QWORD *)(((unsigned __int64)v2 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
    *(result - 1) = v3;
  }
  return result;
}

```

## disassembly

```asm
0x180002880  sub     rsp, 38h
0x180002884  test    rcx, rcx
0x180002887  jnz     short loc_180002890
0x180002889  xor     eax, eax
0x18000288b  add     rsp, 38h
0x18000288f  retn
0x180002890  cmp     rcx, 1000h
0x180002897  jb      short loc_1800028DD
0x180002899  lea     rax, [rcx+27h]
0x18000289d  cmp     rax, rcx
0x1800028a0  jbe     short loc_1800028E9
0x1800028a2  lfence
0x1800028a5  mov     rcx, rax; Size
0x1800028a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800028ad  mov     rcx, rax; Expression
0x1800028b0  test    rax, rax
0x1800028b3  jnz     short loc_1800028C9
0x1800028b5  xor     r9d, r9d; LineNo
0x1800028b8  mov     [rsp+38h+Reserved], rax; Reserved
0x1800028bd  xor     r8d, r8d; FileName
0x1800028c0  xor     edx, edx; FunctionName
0x1800028c2  call    cs:__imp__invoke_watson
0x1800028c9  lfence
0x1800028cc  add     rax, 27h ; '''
0x1800028d0  and     rax, 0FFFFFFFFFFFFFFE0h
0x1800028d4  mov     [rax-8], rcx
0x1800028d8  add     rsp, 38h
0x1800028dc  retn
0x1800028dd  lfence
0x1800028e0  add     rsp, 38h
0x1800028e4  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800028e9  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
