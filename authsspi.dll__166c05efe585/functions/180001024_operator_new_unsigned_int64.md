# operator new(unsigned __int64)

- ea: `0x180001024`
- end: `0x18000105d`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1800021f0`
- `0x180003ed4`
- `0x180005be0`
- `0x180005eac`
- `0x180005ff0`
- `0x180007d34`
- `0x18000839c`

## callees

- `0x180001024`
- `0x180001542`
- `0x18000154e`

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
0x180001024  mov     [rsp+arg_0], rbx
0x180001029  push    rdi
0x18000102a  sub     rsp, 20h
0x18000102e  mov     rdi, rcx
0x180001031  jmp     short loc_180001042
0x180001033  mov     rcx, rdi; Size
0x180001036  call    _callnewh_0
0x18000103b  test    eax, eax
0x18000103d  jz      short loc_18000104F
0x18000103f  mov     rcx, rdi; Size
0x180001042  call    malloc_0
0x180001047  mov     rbx, rax
0x18000104a  test    rax, rax
0x18000104d  jz      short loc_180001033
0x18000104f  mov     rax, rbx
0x180001052  mov     rbx, [rsp+28h+arg_0]
0x180001057  add     rsp, 20h
0x18000105b  pop     rdi
0x18000105c  retn
```
