# std::vector<std::shared_ptr<PCLmWriter::IObject const>,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)

- ea: `0x180014158`
- end: `0x1800141fc`
- name: `??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180014a14`

## callees

- `0x18000ea34`
- `0x18000f0f8`
- `0x18000f268`
- `0x18000f898`
- `0x1800100ec`
- `0x180010124`
- `0x1800146b0`

## pseudocode

```c
__int64 __fastcall std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Resize_reallocate<std::_Value_init_tag>(
        __int64 *a1)
{
  __int64 v1; // rdi
  __int64 v3; // rsi
  __int64 size_of; // rax
  __int64 v5; // rax
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  _QWORD v11[3]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v12; // [rsp+38h] [rbp-40h]
  __int64 v13; // [rsp+40h] [rbp-38h]

  v1 = (a1[1] - *a1) >> 4;
  v3 = std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Calculate_growth(a1, 4);
  size_of = std::_Get_size_of_n<16>(v3);
  v5 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v11[0] = a1;
  v11[2] = v3;
  v12 = v5 + 16 * v1;
  v6 = v5;
  v7 = std::_Uninitialized_value_construct_n<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(
         v12,
         4 - v1,
         a1);
  v8 = a1[1];
  v9 = *a1;
  v13 = v7;
  std::_Uninitialized_move<std::shared_ptr<PCLmWriter::IObject const> *,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(
    v9,
    v8,
    v6);
  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Change_array(a1, v6, 4, v3, a1, 0, v3, v12, v13);
  return std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Reallocation_guard::~_Reallocation_guard(v11);
}

```

## disassembly

```asm
0x180014158  push    rbx
0x18001415a  push    rbp
0x18001415b  push    rsi
0x18001415c  push    rdi
0x18001415d  push    r14
0x18001415f  sub     rsp, 50h
0x180014163  mov     rdi, [rcx+8]
0x180014167  mov     ebp, 4
0x18001416c  sub     rdi, [rcx]
0x18001416f  mov     edx, ebp
0x180014171  sar     rdi, 4
0x180014175  mov     r14, rcx
0x180014178  call    ?_Calculate_growth@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEBA_K_K@Z; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Calculate_growth(unsigned __int64)
0x18001417d  mov     rcx, rax
0x180014180  mov     rsi, rax
0x180014183  call    ??$_Get_size_of_n@$0BA@@std@@YA_K_K@Z; std::_Get_size_of_n<16>(unsigned __int64)
0x180014188  mov     rcx, rax
0x18001418b  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180014190  mov     rcx, rdi
0x180014193  mov     [rsp+78h+var_58], r14
0x180014198  shl     rcx, 4
0x18001419c  mov     edx, ebp
0x18001419e  add     rcx, rax
0x1800141a1  mov     [rsp+78h+var_48], rsi
0x1800141a6  sub     rdx, rdi
0x1800141a9  mov     [rsp+78h+var_40], rcx
0x1800141ae  mov     r8, r14
0x1800141b1  mov     rbx, rax
0x1800141b4  call    ??$_Uninitialized_value_construct_n@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@std@@@std@@YAPEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@0@PEAV10@_KAEAV?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(std::shared_ptr<PCLmWriter::IObject const> *,unsigned __int64,std::allocator<std::shared_ptr<PCLmWriter::IObject const>> &)
0x1800141b9  mov     rdx, [r14+8]
0x1800141bd  mov     r8, rbx
0x1800141c0  mov     rcx, [r14]
0x1800141c3  mov     [rsp+78h+var_38], rax
0x1800141c8  call    ??$_Uninitialized_move@PEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@YAPEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@0@@Z; std::_Uninitialized_move<std::shared_ptr<PCLmWriter::IObject const> *,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(std::shared_ptr<PCLmWriter::IObject const> * const,std::shared_ptr<PCLmWriter::IObject const> * const,std::shared_ptr<PCLmWriter::IObject const> *,std::allocator<std::shared_ptr<PCLmWriter::IObject const>> &)
0x1800141cd  mov     r9, rsi
0x1800141d0  mov     [rsp+78h+var_50], 0
0x1800141d9  mov     r8d, ebp
0x1800141dc  mov     rdx, rbx
0x1800141df  mov     rcx, r14
0x1800141e2  call    ?_Change_array@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEAAXQEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@_K1@Z; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Change_array(std::shared_ptr<PCLmWriter::IObject const> * const,unsigned __int64,unsigned __int64)
0x1800141e7  lea     rcx, [rsp+78h+var_58]
0x1800141ec  call    ??1_Reallocation_guard@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Reallocation_guard::~_Reallocation_guard(void)
0x1800141f1  add     rsp, 50h
0x1800141f5  pop     r14
0x1800141f7  pop     rdi
0x1800141f8  pop     rsi
0x1800141f9  pop     rbp
0x1800141fa  pop     rbx
0x1800141fb  retn
```
