# operator new(unsigned __int64)

- ea: `0x180002cac`
- end: `0x180002ce8`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `89`
- callee_count: `5`
- tags: ``

## callers

- `0x180002cf0`
- `0x180003970`
- `0x180003d50`
- `0x180003ef0`
- `0x1800040c0`
- `0x180004230`
- `0x1800043e0`
- `0x180004560`
- `0x1800047b0`
- `0x180004ed0`
- `0x180005190`
- `0x180005330`
- `0x180005690`
- `0x180005890`
- `0x180005930`
- `0x180005c10`
- `0x180005e60`
- `0x180005f80`
- `0x180005fd0`
- `0x180006030`
- `0x1800060b0`
- `0x1800061c0`
- `0x180006230`
- `0x180006aa0`
- `0x180006b10`
- `0x180006b80`
- `0x180006bf0`
- `0x180006fb0`
- `0x1800087c0`
- `0x1800088e0`
- `0x180010ff4`
- `0x18001105c`
- `0x1800110c4`
- `0x18001112c`
- `0x180011194`
- `0x1800111fc`
- `0x180011254`
- `0x1800112cc`
- `0x180011334`
- `0x180012ce0`
- `0x180012d80`
- `0x180012e00`
- `0x180013170`
- `0x1800132a0`
- `0x180013310`
- `0x180013390`
- `0x180013490`
- `0x180013530`
- `0x180013640`
- `0x180013750`

## callees

- `0x180002cac`
- `0x180003474`
- `0x18000352e`
- `0x1800035c0`
- `0x18001da08`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax

  for ( i = Size; ; Size = i )
  {
    result = o_malloc_0(Size);
    if ( result )
      break;
    if ( !(unsigned int)o__callnewh_0(i) )
    {
      if ( i != -1 )
        __scrt_throw_std_bad_alloc();
      __scrt_throw_std_bad_array_new_length();
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002cac  push    rbx
0x180002cae  sub     rsp, 20h
0x180002cb2  mov     rbx, rcx
0x180002cb5  jmp     short loc_180002CC6
0x180002cb7  mov     rcx, rbx
0x180002cba  call    _o__callnewh_0
0x180002cbf  test    eax, eax
0x180002cc1  jz      short loc_180002CD6
0x180002cc3  mov     rcx, rbx; Size
0x180002cc6  call    _o_malloc_0
0x180002ccb  test    rax, rax
0x180002cce  jz      short loc_180002CB7
0x180002cd0  add     rsp, 20h
0x180002cd4  pop     rbx
0x180002cd5  retn
0x180002cd6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180002cda  jz      short loc_180002CE2
0x180002cdc  call    ?__scrt_throw_std_bad_alloc@@YAXXZ
0x180002ce2  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ
```
