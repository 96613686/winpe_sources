# std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>>>(std::allocator<std::_Tree_node<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>> &,std::_Tree_node<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *> *)

- ea: `0x180013ce0`
- end: `0x180013d38`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@PEAX@1@@Z`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180013ce0`
- `0x180014868`

## callees

- `0x18000edc0`
- `0x1800101cc`
- `0x180013ce0`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned int const,std::shared_ptr<PCLmWriter::IXrefEntry>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned int const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 *i; // rbx
  std::_Ref_count_base *v6; // rcx
  __int64 *v7; // rdi
  __int64 result; // rax

  for ( i = a3; !*((_BYTE *)i + 25); result = std::_Deallocate<16>(v7, 56) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned int const,std::shared_ptr<PCLmWriter::IXrefEntry>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned int const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>>>(
      a1,
      a2,
      i[2]);
    v6 = (std::_Ref_count_base *)i[6];
    v7 = i;
    i = (__int64 *)*i;
    if ( v6 )
      std::_Ref_count_base::_Decref(v6);
  }
  return result;
}

```

## disassembly

```asm
0x180013ce0  push    rbx
0x180013ce2  push    rbp
0x180013ce3  push    rsi
0x180013ce4  push    rdi
0x180013ce5  sub     rsp, 28h
0x180013ce9  cmp     byte ptr [r8+19h], 0
0x180013cee  mov     rbx, r8
0x180013cf1  mov     rsi, rdx
0x180013cf4  mov     rbp, rcx
0x180013cf7  jnz     short loc_180013D2F
0x180013cf9  mov     r8, [rbx+10h]
0x180013cfd  mov     rdx, rsi
0x180013d00  mov     rcx, rbp
0x180013d03  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>>>(std::allocator<std::_Tree_node<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>> &,std::_Tree_node<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *> *)
0x180013d08  mov     rcx, [rbx+30h]; this
0x180013d0c  mov     rdi, rbx
0x180013d0f  mov     rbx, [rbx]
0x180013d12  test    rcx, rcx
0x180013d15  jz      short loc_180013D1C
0x180013d17  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180013d1c  mov     edx, 38h ; '8'
0x180013d21  mov     rcx, rdi
0x180013d24  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013d29  cmp     byte ptr [rbx+19h], 0
0x180013d2d  jz      short loc_180013CF9
0x180013d2f  add     rsp, 28h
0x180013d33  pop     rdi
0x180013d34  pop     rsi
0x180013d35  pop     rbp
0x180013d36  pop     rbx
0x180013d37  retn
```
