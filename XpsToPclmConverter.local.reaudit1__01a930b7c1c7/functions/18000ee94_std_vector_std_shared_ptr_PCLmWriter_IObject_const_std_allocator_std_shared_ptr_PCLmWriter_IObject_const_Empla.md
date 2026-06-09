# std::vector<std::shared_ptr<PCLmWriter::IObject const>,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>::_Emplace_reallocate<std::shared_ptr<PCLmWriter::IObject const>>(std::shared_ptr<PCLmWriter::IObject const> * const,std::shared_ptr<PCLmWriter::IObject const> &&)

- ea: `0x18000ee94`
- end: `0x18000efa0`
- name: `??$_Emplace_reallocate@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@QEAV21@$$QEAV21@@Z`
- size: `268`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x180010290`
- `0x180014a14`
- `0x1800152f4`

## callees

- `0x18000ea34`
- `0x18000ee94`
- `0x18000f0f8`
- `0x18000f268`
- `0x18000f898`
- `0x1800100ec`
- `0x180010124`
- `0x180010770`

## pseudocode

```c
unsigned __int64 __fastcall std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Emplace_reallocate<std::shared_ptr<PCLmWriter::IObject const>>(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v3; // rbp
  __int64 v6; // rax
  __int64 v8; // r13
  __int64 v9; // r12
  __int64 size_of; // rax
  __int64 v11; // rdi
  _QWORD *v12; // r8
  _QWORD *v13; // r14
  __int64 v14; // rdx
  __int64 v15; // rcx
  _QWORD *v17; // [rsp+20h] [rbp-78h] BYREF
  __int64 v18; // [rsp+30h] [rbp-68h]
  _QWORD *v19; // [rsp+38h] [rbp-60h]
  _QWORD *v20; // [rsp+40h] [rbp-58h]

  v3 = *a1;
  v6 = (__int64)(a1[1] - *a1) >> 4;
  if ( v6 == 0xFFFFFFFFFFFFFFFLL )
    std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Xlength();
  v8 = v6 + 1;
  v9 = std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Calculate_growth(a1, v6 + 1);
  size_of = std::_Get_size_of_n<16>(v9);
  v17 = a1;
  v11 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v18 = v9;
  v12 = (_QWORD *)v11;
  v13 = (_QWORD *)(v11 + ((a2 - v3) & 0xFFFFFFFFFFFFFFF0uLL));
  v19 = v13;
  *v13 = 0;
  v13[1] = 0;
  *v13 = *a3;
  v13[1] = a3[1];
  *a3 = 0;
  a3[1] = 0;
  v14 = a1[1];
  v15 = *a1;
  v20 = v13 + 2;
  if ( a2 != v14 )
  {
    std::_Uninitialized_move<std::shared_ptr<PCLmWriter::IObject const> *,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(
      v15,
      a2,
      v11);
    v14 = a1[1];
    v12 = v13 + 2;
    v15 = a2;
    v19 = (_QWORD *)v11;
  }
  std::_Uninitialized_move<std::shared_ptr<PCLmWriter::IObject const> *,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(
    v15,
    v14,
    v12);
  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Change_array(a1, v11, v8, v9, v17, 0, v18, v19, v20);
  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Reallocation_guard::~_Reallocation_guard(&v17);
  return v11 + ((a2 - v3) & 0xFFFFFFFFFFFFFFF0uLL);
}

```

## disassembly

```asm
0x18000ee94  push    rbx
0x18000ee96  push    rbp
0x18000ee97  push    rsi
0x18000ee98  push    rdi
0x18000ee99  push    r12
0x18000ee9b  push    r13
0x18000ee9d  push    r14
0x18000ee9f  push    r15
0x18000eea1  sub     rsp, 58h
0x18000eea5  mov     rbp, [rcx]
0x18000eea8  mov     rbx, rcx
0x18000eeab  mov     rax, [rcx+8]
0x18000eeaf  mov     r15, r8
0x18000eeb2  sub     rax, rbp
0x18000eeb5  mov     rcx, 0FFFFFFFFFFFFFFFh
0x18000eebf  sar     rax, 4
0x18000eec3  mov     rsi, rdx
0x18000eec6  cmp     rax, rcx
0x18000eec9  jz      loc_18000EF9A
0x18000eecf  lea     r13, [rax+1]
0x18000eed3  mov     rcx, rbx
0x18000eed6  mov     rdx, r13
0x18000eed9  call    ?_Calculate_growth@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEBA_K_K@Z; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Calculate_growth(unsigned __int64)
0x18000eede  mov     rcx, rax
0x18000eee1  mov     r12, rax
0x18000eee4  call    ??$_Get_size_of_n@$0BA@@std@@YA_K_K@Z; std::_Get_size_of_n<16>(unsigned __int64)
0x18000eee9  mov     rcx, rax
0x18000eeec  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000eef1  xor     ecx, ecx
0x18000eef3  mov     [rsp+98h+var_78], rbx
0x18000eef8  mov     rdi, rax
0x18000eefb  mov     [rsp+98h+var_68], r12
0x18000ef00  mov     r14, rsi
0x18000ef03  mov     r8, rdi
0x18000ef06  sub     r14, rbp
0x18000ef09  and     r14, 0FFFFFFFFFFFFFFF0h
0x18000ef0d  add     r14, rax
0x18000ef10  mov     [rsp+98h+var_60], r14
0x18000ef15  mov     [r14], rcx
0x18000ef18  lea     rbp, [r14+10h]
0x18000ef1c  mov     [r14+8], rcx
0x18000ef20  mov     rax, [r15]
0x18000ef23  mov     [r14], rax
0x18000ef26  mov     rax, [r15+8]
0x18000ef2a  mov     [r14+8], rax
0x18000ef2e  mov     [r15], rcx
0x18000ef31  mov     [r15+8], rcx
0x18000ef35  mov     rdx, [rbx+8]
0x18000ef39  mov     rcx, [rbx]
0x18000ef3c  mov     [rsp+98h+var_58], rbp
0x18000ef41  cmp     rsi, rdx
0x18000ef44  jz      short loc_18000EF5D
0x18000ef46  mov     rdx, rsi
0x18000ef49  call    ??$_Uninitialized_move@PEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@YAPEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@0@@Z; std::_Uninitialized_move<std::shared_ptr<PCLmWriter::IObject const> *,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(std::shared_ptr<PCLmWriter::IObject const> * const,std::shared_ptr<PCLmWriter::IObject const> * const,std::shared_ptr<PCLmWriter::IObject const> *,std::allocator<std::shared_ptr<PCLmWriter::IObject const>> &)
0x18000ef4e  mov     rdx, [rbx+8]
0x18000ef52  mov     r8, rbp
0x18000ef55  mov     rcx, rsi
0x18000ef58  mov     [rsp+98h+var_60], rdi
0x18000ef5d  call    ??$_Uninitialized_move@PEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@YAPEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@0@@Z; std::_Uninitialized_move<std::shared_ptr<PCLmWriter::IObject const> *,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(std::shared_ptr<PCLmWriter::IObject const> * const,std::shared_ptr<PCLmWriter::IObject const> * const,std::shared_ptr<PCLmWriter::IObject const> *,std::allocator<std::shared_ptr<PCLmWriter::IObject const>> &)
0x18000ef62  mov     r9, r12
0x18000ef65  mov     [rsp+98h+var_70], 0
0x18000ef6e  mov     r8, r13
0x18000ef71  mov     rdx, rdi
0x18000ef74  mov     rcx, rbx
0x18000ef77  call    ?_Change_array@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEAAXQEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@_K1@Z; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Change_array(std::shared_ptr<PCLmWriter::IObject const> * const,unsigned __int64,unsigned __int64)
0x18000ef7c  lea     rcx, [rsp+98h+var_78]
0x18000ef81  call    ??1_Reallocation_guard@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18000ef86  mov     rax, r14
0x18000ef89  add     rsp, 58h
0x18000ef8d  pop     r15
0x18000ef8f  pop     r14
0x18000ef91  pop     r13
0x18000ef93  pop     r12
0x18000ef95  pop     rdi
0x18000ef96  pop     rsi
0x18000ef97  pop     rbp
0x18000ef98  pop     rbx
0x18000ef99  retn
0x18000ef9a  call    ?_Xlength@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@CAXXZ; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Xlength(void)
```
