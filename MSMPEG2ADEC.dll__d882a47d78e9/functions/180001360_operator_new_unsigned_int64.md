# operator new(unsigned __int64)

- ea: `0x180001360`
- end: `0x180001399`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `27`
- callee_count: `3`
- tags: ``

## callers

- `0x1800013ac`
- `0x18000b690`
- `0x18000b900`
- `0x18000d2f0`
- `0x18000f9f0`
- `0x1800108f0`
- `0x18001b610`
- `0x18001bb60`
- `0x18001e6e0`
- `0x180025500`
- `0x180026900`
- `0x1800269a0`
- `0x180026f20`
- `0x180026f90`
- `0x180029520`
- `0x18002b608`
- `0x18002b6d0`
- `0x180033080`
- `0x18004f4c0`
- `0x18004fbb0`
- `0x180059f00`
- `0x18005a380`
- `0x18005a530`
- `0x18005c430`
- `0x18005eaa0`
- `0x180060ca0`
- `0x180064740`

## callees

- `0x180001360`
- `0x1800020ce`
- `0x180002178`

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
0x180001360  mov     [rsp+arg_0], rbx
0x180001365  push    rdi
0x180001366  sub     rsp, 20h
0x18000136a  mov     rdi, rcx
0x18000136d  jmp     short loc_18000137E
0x18000136f  mov     rcx, rdi
0x180001372  call    _o__callnewh_0
0x180001377  test    eax, eax
0x180001379  jz      short loc_18000138B
0x18000137b  mov     rcx, rdi; Size
0x18000137e  call    _o_malloc_0
0x180001383  mov     rbx, rax
0x180001386  test    rax, rax
0x180001389  jz      short loc_18000136F
0x18000138b  mov     rax, rbx
0x18000138e  mov     rbx, [rsp+28h+arg_0]
0x180001393  add     rsp, 20h
0x180001397  pop     rdi
0x180001398  retn
```
