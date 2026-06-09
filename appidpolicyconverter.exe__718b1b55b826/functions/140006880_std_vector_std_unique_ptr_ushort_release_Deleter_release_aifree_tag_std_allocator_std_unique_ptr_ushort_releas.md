# std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>,std::allocator<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>>::_Destroy(std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> *)

- ea: `0x140006880`
- end: `0x1400068b6`
- name: `?_Destroy@?$vector@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@2@@std@@IEAAXPEAV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@2@0@Z`
- size: `54`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140002894`
- `0x1400037c8`
- `0x140006ac8`

## callees

- `0x140006880`
- `0x140008ef4`

## pseudocode

```c
__int64 __fastcall std::vector<std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>>::_Destroy(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *v4; // rbx
  __int64 result; // rax

  if ( a2 != a3 )
  {
    v4 = a2;
    do
    {
      if ( *v4 )
        result = AiFree(*v4);
      ++v4;
    }
    while ( v4 != a3 );
  }
  return result;
}

```

## disassembly

```asm
0x140006880  cmp     rdx, r8
0x140006883  jz      short locret_1400068B5
0x140006885  mov     [rsp+arg_0], rbx
0x14000688a  push    rdi
0x14000688b  sub     rsp, 20h
0x14000688f  mov     rdi, r8
0x140006892  mov     rbx, rdx
0x140006895  mov     rcx, [rbx]
0x140006898  test    rcx, rcx
0x14000689b  jz      short loc_1400068A2
0x14000689d  call    AiFree
0x1400068a2  add     rbx, 8
0x1400068a6  cmp     rbx, rdi
0x1400068a9  jnz     short loc_140006895
0x1400068ab  mov     rbx, [rsp+28h+arg_0]
0x1400068b0  add     rsp, 20h
0x1400068b4  pop     rdi
0x1400068b5  retn
```
