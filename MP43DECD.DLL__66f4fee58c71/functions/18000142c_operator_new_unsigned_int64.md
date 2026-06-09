# operator new(unsigned __int64)

- ea: `0x18000142c`
- end: `0x180001465`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x18000146c`
- `0x180003ac0`
- `0x180003b10`
- `0x180008ef0`
- `0x180009188`
- `0x180009ef4`
- `0x180012d34`
- `0x18001fa30`
- `0x18001fd34`

## callees

- `0x18000142c`
- `0x1800020a6`
- `0x180002120`

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
0x18000142c  mov     [rsp+arg_0], rbx
0x180001431  push    rdi
0x180001432  sub     rsp, 20h
0x180001436  mov     rdi, rcx
0x180001439  jmp     short loc_18000144A
0x18000143b  mov     rcx, rdi
0x18000143e  call    _o__callnewh_0
0x180001443  test    eax, eax
0x180001445  jz      short loc_180001457
0x180001447  mov     rcx, rdi; Size
0x18000144a  call    _o_malloc_0
0x18000144f  mov     rbx, rax
0x180001452  test    rax, rax
0x180001455  jz      short loc_18000143B
0x180001457  mov     rax, rbx
0x18000145a  mov     rbx, [rsp+28h+arg_0]
0x18000145f  add     rsp, 20h
0x180001463  pop     rdi
0x180001464  retn
```
