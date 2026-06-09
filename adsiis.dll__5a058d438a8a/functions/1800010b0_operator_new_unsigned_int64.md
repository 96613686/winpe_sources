# operator new(unsigned __int64)

- ea: `0x1800010b0`
- end: `0x1800010e9`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `26`
- callee_count: `3`
- tags: ``

## callers

- `0x1800010fc`
- `0x180001ad0`
- `0x180001ed0`
- `0x180002710`
- `0x180002b00`
- `0x180003bb8`
- `0x180004360`
- `0x18000816c`
- `0x1800094f8`
- `0x180009624`
- `0x18000978c`
- `0x18000ce28`
- `0x18000d638`
- `0x18000dc6c`
- `0x18000e2e0`
- `0x18000f7ac`
- `0x180010a74`
- `0x180013378`
- `0x180014d2c`
- `0x1800169d4`
- `0x1800170ac`
- `0x180019504`
- `0x18001a578`
- `0x18001b62c`
- `0x18001b6c4`
- `0x18001c0d4`

## callees

- `0x1800010b0`
- `0x1800017f8`
- `0x180001804`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rdi
  void *v2; // rbx

  for ( i = Size; ; Size = i )
  {
    v2 = malloc_0(Size);
    if ( v2 || !callnewh_0(i) )
      break;
  }
  return v2;
}

```

## disassembly

```asm
0x1800010b0  mov     [rsp+arg_0], rbx
0x1800010b5  push    rdi
0x1800010b6  sub     rsp, 20h
0x1800010ba  mov     rdi, rcx
0x1800010bd  jmp     short loc_1800010CE
0x1800010bf  mov     rcx, rdi; Size
0x1800010c2  call    _callnewh_0
0x1800010c7  test    eax, eax
0x1800010c9  jz      short loc_1800010DB
0x1800010cb  mov     rcx, rdi; Size
0x1800010ce  call    malloc_0
0x1800010d3  mov     rbx, rax
0x1800010d6  test    rax, rax
0x1800010d9  jz      short loc_1800010BF
0x1800010db  mov     rax, rbx
0x1800010de  mov     rbx, [rsp+28h+arg_0]
0x1800010e3  add     rsp, 20h
0x1800010e7  pop     rdi
0x1800010e8  retn
```
