# std::vector<std::shared_ptr<PCLmWriter::IObject const>,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>::_Emplace_reallocate<std::shared_ptr<PCLmWriter::IObject const> const &>(std::shared_ptr<PCLmWriter::IObject const> * const,std::shared_ptr<PCLmWriter::IObject const> const &)

- ea: `0x180013be0`
- end: `0x180013cda`
- name: `??$_Emplace_reallocate@AEBV?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@QEAV21@AEBV21@@Z`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180014a14`

## callees

- `0x18000e7c8`
- `0x18000ea34`
- `0x18000f0f8`
- `0x18000f268`
- `0x18000f898`
- `0x1800100ec`
- `0x180010124`
- `0x180010770`
- `0x180013be0`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Emplace_reallocate<std::shared_ptr<PCLmWriter::IObject const> const &>(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v3; // rbp
  __int64 v6; // rax
  __int64 v8; // r15
  __int64 v9; // r14
  __int64 size_of; // rax
  __int64 v11; // rdi
  _QWORD *v12; // rbp
  __int64 v13; // rdx
  _QWORD *v14; // r8
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
  v18 = v9;
  v11 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v12 = (_QWORD *)(((a2 - v3) & 0xFFFFFFFFFFFFFFF0uLL) + v11);
  v20 = v12 + 2;
  std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(v12, a3);
  v13 = a1[1];
  v14 = (_QWORD *)v11;
  v15 = *a1;
  v19 = v12;
  if ( a2 != v13 )
  {
    std::_Uninitialized_move<std::shared_ptr<PCLmWriter::IObject const> *,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(
      v15,
      a2,
      v11);
    v13 = a1[1];
    v14 = v12 + 2;
    v15 = a2;
    v19 = (_QWORD *)v11;
  }
  std::_Uninitialized_move<std::shared_ptr<PCLmWriter::IObject const> *,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(
    v15,
    v13,
    v14);
  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Change_array(a1, v11, v8, v9, v17, 0, v18, v19, v20);
  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Reallocation_guard::~_Reallocation_guard(&v17);
  return v12;
}

```

## disassembly

```asm
0x180013be0  push    rbx
0x180013be2  push    rbp
0x180013be3  push    rsi
0x180013be4  push    rdi
0x180013be5  push    r12
0x180013be7  push    r13
0x180013be9  push    r14
0x180013beb  push    r15
0x180013bed  sub     rsp, 58h
0x180013bf1  mov     rbp, [rcx]
0x180013bf4  mov     rbx, rcx
0x180013bf7  mov     rax, [rcx+8]
0x180013bfb  mov     r13, r8
0x180013bfe  sub     rax, rbp
0x180013c01  mov     rcx, 0FFFFFFFFFFFFFFFh
0x180013c0b  sar     rax, 4
0x180013c0f  mov     rsi, rdx
0x180013c12  cmp     rax, rcx
0x180013c15  jz      loc_180013CD4
0x180013c1b  lea     r15, [rax+1]
0x180013c1f  mov     rcx, rbx
0x180013c22  mov     rdx, r15
0x180013c25  call    ?_Calculate_growth@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEBA_K_K@Z; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Calculate_growth(unsigned __int64)
0x180013c2a  mov     rcx, rax
0x180013c2d  mov     r14, rax
0x180013c30  call    ??$_Get_size_of_n@$0BA@@std@@YA_K_K@Z; std::_Get_size_of_n<16>(unsigned __int64)
0x180013c35  mov     rcx, rax
0x180013c38  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180013c3d  mov     rcx, rsi
0x180013c40  mov     [rsp+98h+var_78], rbx
0x180013c45  sub     rcx, rbp
0x180013c48  mov     [rsp+98h+var_68], r14
0x180013c4d  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180013c51  mov     rdx, r13
0x180013c54  mov     rdi, rax
0x180013c57  lea     rbp, [rcx+rax]
0x180013c5b  lea     r12, [rbp+10h]
0x180013c5f  mov     rcx, rbp
0x180013c62  mov     [rsp+98h+var_58], r12
0x180013c67  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x180013c6c  mov     rdx, [rbx+8]
0x180013c70  mov     r8, rdi
0x180013c73  mov     rcx, [rbx]
0x180013c76  mov     [rsp+98h+var_60], rbp
0x180013c7b  cmp     rsi, rdx
0x180013c7e  jz      short loc_180013C97
0x180013c80  mov     rdx, rsi
0x180013c83  call    ??$_Uninitialized_move@PEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@YAPEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@0@@Z; std::_Uninitialized_move<std::shared_ptr<PCLmWriter::IObject const> *,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(std::shared_ptr<PCLmWriter::IObject const> * const,std::shared_ptr<PCLmWriter::IObject const> * const,std::shared_ptr<PCLmWriter::IObject const> *,std::allocator<std::shared_ptr<PCLmWriter::IObject const>> &)
0x180013c88  mov     rdx, [rbx+8]
0x180013c8c  mov     r8, r12
0x180013c8f  mov     rcx, rsi
0x180013c92  mov     [rsp+98h+var_60], rdi
0x180013c97  call    ??$_Uninitialized_move@PEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@YAPEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@0@@Z; std::_Uninitialized_move<std::shared_ptr<PCLmWriter::IObject const> *,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(std::shared_ptr<PCLmWriter::IObject const> * const,std::shared_ptr<PCLmWriter::IObject const> * const,std::shared_ptr<PCLmWriter::IObject const> *,std::allocator<std::shared_ptr<PCLmWriter::IObject const>> &)
0x180013c9c  mov     r9, r14
0x180013c9f  mov     [rsp+98h+var_70], 0
0x180013ca8  mov     r8, r15
0x180013cab  mov     rdx, rdi
0x180013cae  mov     rcx, rbx
0x180013cb1  call    ?_Change_array@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEAAXQEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@_K1@Z; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Change_array(std::shared_ptr<PCLmWriter::IObject const> * const,unsigned __int64,unsigned __int64)
0x180013cb6  lea     rcx, [rsp+98h+var_78]
0x180013cbb  call    ??1_Reallocation_guard@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Reallocation_guard::~_Reallocation_guard(void)
0x180013cc0  mov     rax, rbp
0x180013cc3  add     rsp, 58h
0x180013cc7  pop     r15
0x180013cc9  pop     r14
0x180013ccb  pop     r13
0x180013ccd  pop     r12
0x180013ccf  pop     rdi
0x180013cd0  pop     rsi
0x180013cd1  pop     rbp
0x180013cd2  pop     rbx
0x180013cd3  retn
0x180013cd4  call    ?_Xlength@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@CAXXZ; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Xlength(void)
```
