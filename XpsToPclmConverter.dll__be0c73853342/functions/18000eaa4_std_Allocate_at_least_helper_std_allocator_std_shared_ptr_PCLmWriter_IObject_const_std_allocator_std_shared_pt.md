# std::_Allocate_at_least_helper<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(std::allocator<std::shared_ptr<PCLmWriter::IObject const>> &,unsigned __int64 &)

- ea: `0x18000eaa4`
- end: `0x18000eabc`
- name: `??$_Allocate_at_least_helper@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@std@@@std@@YAPEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@0@AEAV?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@0@AEA_K@Z`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012d34`

## callees

- `0x18000ea34`
- `0x18000f0f8`

## pseudocode

```c
__int64 __fastcall std::_Allocate_at_least_helper<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(
        __int64 a1,
        _QWORD *a2)
{
  __int64 size_of; // rax

  size_of = std::_Get_size_of_n<16>(*a2);
  return std::_Allocate<16,std::_Default_allocate_traits>(size_of);
}

```

## disassembly

```asm
0x18000eaa4  sub     rsp, 28h
0x18000eaa8  mov     rcx, [rdx]
0x18000eaab  call    ??$_Get_size_of_n@$0BA@@std@@YA_K_K@Z; std::_Get_size_of_n<16>(unsigned __int64)
0x18000eab0  mov     rcx, rax
0x18000eab3  add     rsp, 28h
0x18000eab7  jmp     ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
```
