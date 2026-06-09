# std::_Destroy_range<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(std::shared_ptr<PCLmWriter::IObject const> *,std::shared_ptr<PCLmWriter::IObject const> * const,std::allocator<std::shared_ptr<PCLmWriter::IObject const>> &)

- ea: `0x18000ee2c`
- end: `0x18000ee63`
- name: `??$_Destroy_range@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@0@@Z`
- size: `55`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f268`
- `0x18000f898`
- `0x180010124`
- `0x1800106c8`
- `0x180010c08`
- `0x1800146b0`
- `0x180014a14`

## callees

- `0x18000ee2c`
- `0x1800101cc`

## pseudocode

```c
void __fastcall std::_Destroy_range<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  std::_Ref_count_base *v4; // rcx

  if ( a1 != a2 )
  {
    v3 = a1;
    do
    {
      v4 = *(std::_Ref_count_base **)(v3 + 8);
      if ( v4 )
        std::_Ref_count_base::_Decref(v4);
      v3 += 16;
    }
    while ( v3 != a2 );
  }
}

```

## disassembly

```asm
0x18000ee2c  cmp     rcx, rdx
0x18000ee2f  jz      short locret_18000EE62
0x18000ee31  mov     [rsp+arg_0], rbx
0x18000ee36  push    rdi
0x18000ee37  sub     rsp, 20h
0x18000ee3b  mov     rdi, rdx
0x18000ee3e  mov     rbx, rcx
0x18000ee41  mov     rcx, [rbx+8]; this
0x18000ee45  test    rcx, rcx
0x18000ee48  jz      short loc_18000EE4F
0x18000ee4a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000ee4f  add     rbx, 10h
0x18000ee53  cmp     rbx, rdi
0x18000ee56  jnz     short loc_18000EE41
0x18000ee58  mov     rbx, [rsp+28h+arg_0]
0x18000ee5d  add     rsp, 20h
0x18000ee61  pop     rdi
0x18000ee62  retn
```
