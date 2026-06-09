# operator new(unsigned __int64)

- ea: `0x180035060`
- end: `0x18003509c`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `55`
- callee_count: `5`
- tags: ``

## callers

- `0x180001d80`
- `0x180001dc0`
- `0x180002880`
- `0x180004e40`
- `0x1800057f0`
- `0x180007820`
- `0x180008c60`
- `0x18000bc40`
- `0x18000bf60`
- `0x18000c970`
- `0x18000cb20`
- `0x18000d1f0`
- `0x18000d4e0`
- `0x18000d7a0`
- `0x18000e040`
- `0x180010240`
- `0x180011190`
- `0x180012250`
- `0x180018db0`
- `0x180019270`
- `0x180019700`
- `0x1800198b0`
- `0x18001a290`
- `0x18001a610`
- `0x18001c9d0`
- `0x18001cc10`
- `0x18001d320`
- `0x18001eb00`
- `0x1800216e0`
- `0x180021960`
- `0x1800229c0`
- `0x180022dd0`
- `0x180023260`
- `0x180023860`
- `0x180023c50`
- `0x180024120`
- `0x180024840`
- `0x180025430`
- `0x180025800`
- `0x180025a10`
- `0x180026450`
- `0x180026c50`
- `0x180026dc0`
- `0x180026f60`
- `0x1800271c0`
- `0x1800273b0`
- `0x1800276e0`
- `0x180028a70`
- `0x18002c290`
- `0x18002c9c0`

## callees

- `0x1800029d0`
- `0x180032340`
- `0x180035060`
- `0x180039715`
- `0x180039757`

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
      if ( i != -1 )
        std::_Xbad_alloc();
      __scrt_throw_std_bad_array_new_length();
    }
  }
  return result;
}

```

## disassembly

```asm
0x180035060  push    rbx
0x180035062  sub     rsp, 20h
0x180035066  mov     rbx, rcx
0x180035069  jmp     short loc_18003507A
0x18003506b  mov     rcx, rbx; Size
0x18003506e  call    _callnewh_0
0x180035073  test    eax, eax
0x180035075  jz      short loc_18003508A
0x180035077  mov     rcx, rbx; Size
0x18003507a  call    malloc_0
0x18003507f  test    rax, rax
0x180035082  jz      short loc_18003506B
0x180035084  add     rsp, 20h
0x180035088  pop     rbx
0x180035089  retn
0x18003508a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18003508e  jz      short loc_180035096
0x180035090  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180035096  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
