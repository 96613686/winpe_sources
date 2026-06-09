# operator new(unsigned __int64)

- ea: `0x18002a670`
- end: `0x18002a6a9`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x180013fa0`
- `0x180014f1c`
- `0x18001863c`
- `0x180018f04`
- `0x180019108`
- `0x180025e40`
- `0x1800277ec`
- `0x180028030`
- `0x18002a6bc`
- `0x18002ba80`
- `0x18002c460`

## callees

- `0x18002a670`
- `0x18002b2e6`
- `0x18002b370`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rdi
  void *v2; // rbx

  for ( i = Size; ; Size = i )
  {
    v2 = o_malloc_0(Size);
    if ( v2 || !(unsigned int)o__callnewh_0(i) )
      break;
  }
  return v2;
}

```

## disassembly

```asm
0x18002a670  mov     [rsp+arg_0], rbx
0x18002a675  push    rdi
0x18002a676  sub     rsp, 20h
0x18002a67a  mov     rdi, rcx
0x18002a67d  jmp     short loc_18002A68E
0x18002a67f  mov     rcx, rdi
0x18002a682  call    _o__callnewh_0
0x18002a687  test    eax, eax
0x18002a689  jz      short loc_18002A69B
0x18002a68b  mov     rcx, rdi; Size
0x18002a68e  call    _o_malloc_0
0x18002a693  mov     rbx, rax
0x18002a696  test    rax, rax
0x18002a699  jz      short loc_18002A67F
0x18002a69b  mov     rax, rbx
0x18002a69e  mov     rbx, [rsp+28h+arg_0]
0x18002a6a3  add     rsp, 20h
0x18002a6a7  pop     rdi
0x18002a6a8  retn
```
