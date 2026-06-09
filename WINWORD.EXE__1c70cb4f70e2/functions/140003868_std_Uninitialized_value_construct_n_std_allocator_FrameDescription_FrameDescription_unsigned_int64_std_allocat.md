# std::_Uninitialized_value_construct_n<std::allocator<FrameDescription>>(FrameDescription *,unsigned __int64,std::allocator<FrameDescription> &)

- ea: `0x140003868`
- end: `0x14000389f`
- name: `??$_Uninitialized_value_construct_n@V?$allocator@UFrameDescription@@@std@@@std@@YAPEAUFrameDescription@@PEAU1@_KAEAV?$allocator@UFrameDescription@@@0@@Z`
- size: `55`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400036f0`
- `0x140003f18`

## callees

- `0x14000274e`
- `0x140003868`

## pseudocode

```c
char *__fastcall std::_Uninitialized_value_construct_n<std::allocator<FrameDescription>>(char *a1, __int64 a2)
{
  __int64 v3; // rbx

  if ( !a2 )
    return a1;
  v3 = 16 * a2;
  memset_0(a1, 0, 16 * a2);
  return &a1[v3];
}

```

## disassembly

```asm
0x140003868  mov     [rsp+arg_0], rbx
0x14000386d  push    rdi
0x14000386e  sub     rsp, 20h
0x140003872  mov     rbx, rdx
0x140003875  mov     rdi, rcx
0x140003878  test    rdx, rdx
0x14000387b  jz      short loc_140003891
0x14000387d  shl     rbx, 4
0x140003881  xor     edx, edx; Val
0x140003883  mov     r8, rbx; Size
0x140003886  call    memset_0
0x14000388b  lea     rax, [rbx+rdi]
0x14000388f  jmp     short loc_140003894
0x140003891  mov     rax, rdi
0x140003894  mov     rbx, [rsp+28h+arg_0]
0x140003899  add     rsp, 20h
0x14000389d  pop     rdi
0x14000389e  retn
```
