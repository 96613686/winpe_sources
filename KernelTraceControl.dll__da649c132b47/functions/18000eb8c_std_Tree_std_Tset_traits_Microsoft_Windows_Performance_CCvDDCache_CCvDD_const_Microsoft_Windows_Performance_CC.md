# std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Buynode(std::_Tree_nod<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Node *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const * const &,char)

- ea: `0x18000eb8c`
- end: `0x18000ebf1`
- name: `?_Buynode@?$_Tree@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@2@PEAU342@00AEBQEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@D@Z`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dd64`

## callees

- `0x18000eb8c`
- `0x18002687c`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Buynode(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5)
{
  _QWORD *result; // rax
  _QWORD *v9; // rcx

  result = operator new(0x28u);
  try
  {
    if ( result )
    {
      *result = a2;
      result[1] = a3;
      result[2] = a4;
      v9 = a5;
      result[3] = *a5;
      *((_WORD *)result + 16) = 0;
    }
  }
  catch ( ... )
  {
    std::allocator<unsigned int>::deallocate(v9, result);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18000eb8c  mov     rax, rsp
0x18000eb8f  mov     [rax+8], rcx
0x18000eb93  push    rdi
0x18000eb94  sub     rsp, 30h
0x18000eb98  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x18000eba0  mov     [rax+10h], rbx
0x18000eba4  mov     [rax+18h], rsi
0x18000eba8  mov     rbx, r9
0x18000ebab  mov     rdi, r8
0x18000ebae  mov     rsi, rdx
0x18000ebb1  mov     ecx, 28h ; '('; Size
0x18000ebb6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ebbb  mov     [rsp+38h+arg_0], rax
0x18000ebc0  test    rax, rax
0x18000ebc3  jz      short loc_18000EBE1
0x18000ebc5  mov     [rax], rsi
0x18000ebc8  mov     [rax+8], rdi
0x18000ebcc  mov     [rax+10h], rbx
0x18000ebd0  mov     rcx, [rsp+38h+arg_20]
0x18000ebd5  mov     rdx, [rcx]
0x18000ebd8  mov     [rax+18h], rdx
0x18000ebdc  and     word ptr [rax+20h], 0
0x18000ebe1  mov     rbx, [rsp+38h+arg_8]
0x18000ebe6  mov     rsi, [rsp+38h+arg_10]
0x18000ebeb  add     rsp, 30h
0x18000ebef  pop     rdi
0x18000ebf0  retn
```
