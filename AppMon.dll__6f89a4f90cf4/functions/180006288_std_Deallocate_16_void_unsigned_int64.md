# std::_Deallocate<16>(void *,unsigned __int64)

- ea: `0x180006288`
- end: `0x1800062c0`
- name: `??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z`
- size: `56`
- prototype: ``
- caller_count: `24`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180006408`
- `0x180006468`
- `0x180006bb0`
- `0x180007fb8`
- `0x180008010`
- `0x1800080c0`
- `0x1800086b4`
- `0x180009960`
- `0x18000ab30`
- `0x18000ab5c`
- `0x18000b104`
- `0x18000b128`
- `0x18000b14c`
- `0x18000b1a8`
- `0x18000b204`
- `0x18000b2f4`
- `0x18000b320`
- `0x18000b4f4`
- `0x18000b530`
- `0x18000c0cc`
- `0x18000d5c4`
- `0x18000d628`
- `0x18000e7c4`
- `0x18000e820`

## callees

- `0x1800019f0`
- `0x180006288`
- `0x180007930`

## pseudocode

```c
void __fastcall std::_Deallocate<16>(void *a1, unsigned __int64 a2)
{
  void *v2; // [rsp+30h] [rbp+8h] BYREF
  unsigned __int64 v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = a2;
  v2 = a1;
  if ( a2 >= 0x1000 )
  {
    std::_Adjust_manually_vector_aligned(&v2, &v3);
    a1 = v2;
  }
  operator delete(a1);
}

```

## disassembly

```asm
0x180006288  mov     rax, rsp
0x18000628b  mov     [rax+10h], rdx
0x18000628f  mov     [rax+8], rcx
0x180006293  sub     rsp, 28h
0x180006297  cmp     rdx, 1000h
0x18000629e  jb      short loc_1800062B7
0x1800062a0  lea     rdx, [rax+10h]; unsigned __int64 *
0x1800062a4  lea     rcx, [rax+8]; void **
0x1800062a8  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x1800062ad  mov     rdx, [rsp+28h+arg_8]; unsigned __int64
0x1800062b2  mov     rcx, [rsp+28h+arg_0]; void *
0x1800062b7  add     rsp, 28h
0x1800062bb  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
