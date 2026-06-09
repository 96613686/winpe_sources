# std::vector<std::unique_ptr<AdviseInstance,std::default_delete<AdviseInstance>>,std::allocator<std::unique_ptr<AdviseInstance,std::default_delete<AdviseInstance>>>>::_Emplace_reallocate<std::unique_ptr<AdviseInstance,std::default_delete<AdviseInstance>>>(std::unique_ptr<AdviseInstance,std::default_delete<AdviseInstance>> * const,std::unique_ptr<AdviseInstance,std::default_delete<AdviseInstance>> &&)

- ea: `0x18001aa6c`
- end: `0x18001abb0`
- name: `??$_Emplace_reallocate@V?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@std@@@?$vector@V?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@std@@V?$allocator@V?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@1@QEAV21@$$QEAV21@@Z`
- size: `324`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001dac0`

## callees

- `0x180007c1c`
- `0x18000a6a0`
- `0x18000b490`
- `0x180019654`
- `0x180019f9c`
- `0x18001aa6c`
- `0x18001b2b0`
- `0x18001c464`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::unique_ptr<AdviseInstance>>::_Emplace_reallocate<std::unique_ptr<AdviseInstance>>(
        __int64 *a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v3; // rdi
  __int64 v5; // rax
  unsigned __int64 v8; // rbp
  __int64 v9; // r14
  unsigned __int64 v10; // rcx
  __int64 v11; // r14
  unsigned __int64 v12; // rdx
  __int64 size_of; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rsi
  _QWORD *v17; // r8
  _QWORD *v18; // r14
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rcx
  _QWORD v23[3]; // [rsp+20h] [rbp-68h] BYREF
  _QWORD *v24; // [rsp+38h] [rbp-50h]
  _QWORD *v25; // [rsp+40h] [rbp-48h]

  v3 = 0x1FFFFFFFFFFFFFFFLL;
  v5 = (a1[1] - *a1) >> 3;
  if ( v5 == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<Microsoft::WRL::ComPtr<IUIRadioInstance>>::_Xlength();
  v8 = v5 + 1;
  v9 = a2 - *a1;
  v10 = (a1[2] - *a1) >> 3;
  v11 = v9 >> 3;
  v12 = v10 >> 1;
  if ( v10 <= 0x1FFFFFFFFFFFFFFFLL - (v10 >> 1) )
  {
    v3 = v12 + v10;
    if ( v12 + v10 < v8 )
      v3 = v5 + 1;
  }
  size_of = std::_Get_size_of_n<8>(v3);
  v14 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v15 = *a3;
  v16 = v14;
  *a3 = 0;
  v17 = (_QWORD *)v14;
  v23[0] = a1;
  v18 = (_QWORD *)(v14 + 8 * v11);
  v23[2] = v3;
  *v18 = v15;
  v19 = a1[1];
  v20 = *a1;
  v25 = v18 + 1;
  v24 = v18;
  if ( a2 != v19 )
  {
    std::_Uninitialized_move<std::unique_ptr<AdviseInstance> *,std::allocator<std::unique_ptr<AdviseInstance>>>(
      v20,
      a2,
      v14);
    v19 = a1[1];
    v17 = v18 + 1;
    v20 = a2;
    v24 = (_QWORD *)v16;
  }
  std::_Uninitialized_move<std::unique_ptr<AdviseInstance> *,std::allocator<std::unique_ptr<AdviseInstance>>>(
    v20,
    v19,
    v17);
  v21 = *a1;
  v23[1] = 0;
  if ( v21 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<AdviseInstance>>>(v21, a1[1]);
    std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  *a1 = v16;
  a1[1] = v16 + 8 * v8;
  a1[2] = v16 + 8 * v3;
  std::vector<std::unique_ptr<AdviseInstance>>::_Reallocation_guard::~_Reallocation_guard(v23);
  return v18;
}

```

## disassembly

```asm
0x18001aa6c  mov     [rsp+arg_18], rbx
0x18001aa71  push    rbp
0x18001aa72  push    rsi
0x18001aa73  push    rdi
0x18001aa74  push    r12
0x18001aa76  push    r13
0x18001aa78  push    r14
0x18001aa7a  push    r15
0x18001aa7c  sub     rsp, 50h
0x18001aa80  mov     rax, [rcx+8]
0x18001aa84  mov     rdi, 1FFFFFFFFFFFFFFFh
0x18001aa8e  sub     rax, [rcx]
0x18001aa91  mov     r13, r8
0x18001aa94  sar     rax, 3
0x18001aa98  mov     r15, rdx
0x18001aa9b  mov     rbx, rcx
0x18001aa9e  cmp     rax, rdi
0x18001aaa1  jz      loc_18001ABAA
0x18001aaa7  mov     r14, rdx
0x18001aaaa  lea     rbp, [rax+1]
0x18001aaae  sub     r14, [rcx]
0x18001aab1  mov     rax, rdi
0x18001aab4  mov     rcx, [rcx+10h]
0x18001aab8  sub     rcx, [rbx]
0x18001aabb  sar     rcx, 3
0x18001aabf  mov     rdx, rcx
0x18001aac2  sar     r14, 3
0x18001aac6  shr     rdx, 1
0x18001aac9  sub     rax, rdx
0x18001aacc  cmp     rcx, rax
0x18001aacf  ja      short loc_18001AADC
0x18001aad1  lea     rdi, [rdx+rcx]
0x18001aad5  cmp     rdi, rbp
0x18001aad8  cmovb   rdi, rbp
0x18001aadc  mov     rcx, rdi
0x18001aadf  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18001aae4  mov     rcx, rax
0x18001aae7  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001aaec  mov     rcx, [r13+0]
0x18001aaf0  mov     rsi, rax
0x18001aaf3  mov     qword ptr [r13+0], 0
0x18001aafb  mov     r8, rax
0x18001aafe  mov     [rsp+88h+var_68], rbx
0x18001ab03  lea     r14, [rax+r14*8]
0x18001ab07  mov     [rsp+88h+var_58], rdi
0x18001ab0c  mov     [r14], rcx
0x18001ab0f  lea     r12, [r14+8]
0x18001ab13  mov     rdx, [rbx+8]
0x18001ab17  mov     rcx, [rbx]
0x18001ab1a  mov     [rsp+88h+var_48], r12
0x18001ab1f  mov     [rsp+88h+var_50], r14
0x18001ab24  cmp     r15, rdx
0x18001ab27  jz      short loc_18001AB40
0x18001ab29  mov     rdx, r15
0x18001ab2c  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@std@@V?$allocator@V?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<AdviseInstance> *,std::allocator<std::unique_ptr<AdviseInstance>>>(std::unique_ptr<AdviseInstance> * const,std::unique_ptr<AdviseInstance> * const,std::unique_ptr<AdviseInstance> *,std::allocator<std::unique_ptr<AdviseInstance>> &)
0x18001ab31  mov     rdx, [rbx+8]
0x18001ab35  mov     r8, r12
0x18001ab38  mov     rcx, r15
0x18001ab3b  mov     [rsp+88h+var_50], rsi
0x18001ab40  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@std@@V?$allocator@V?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<AdviseInstance> *,std::allocator<std::unique_ptr<AdviseInstance>>>(std::unique_ptr<AdviseInstance> * const,std::unique_ptr<AdviseInstance> * const,std::unique_ptr<AdviseInstance> *,std::allocator<std::unique_ptr<AdviseInstance>> &)
0x18001ab45  mov     rcx, [rbx]
0x18001ab48  mov     [rsp+88h+var_60], 0
0x18001ab51  test    rcx, rcx
0x18001ab54  jz      short loc_18001AB72
0x18001ab56  mov     rdx, [rbx+8]
0x18001ab5a  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<AdviseInstance>>>(std::unique_ptr<AdviseInstance> *,std::unique_ptr<AdviseInstance> * const,std::allocator<std::unique_ptr<AdviseInstance>> &)
0x18001ab5f  mov     rdx, [rbx+10h]
0x18001ab63  sub     rdx, [rbx]
0x18001ab66  mov     rcx, [rbx]
0x18001ab69  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001ab6d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001ab72  mov     [rbx], rsi
0x18001ab75  lea     rcx, [rsi+rbp*8]
0x18001ab79  mov     [rbx+8], rcx
0x18001ab7d  lea     rcx, [rsi+rdi*8]
0x18001ab81  mov     [rbx+10h], rcx
0x18001ab85  lea     rcx, [rsp+88h+var_68]
0x18001ab8a  call    ??1_Reallocation_guard@?$vector@V?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@std@@V?$allocator@V?$unique_ptr@VAdviseInstance@@U?$default_delete@VAdviseInstance@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<AdviseInstance>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18001ab8f  mov     rbx, [rsp+88h+arg_18]
0x18001ab97  mov     rax, r14
0x18001ab9a  add     rsp, 50h
0x18001ab9e  pop     r15
0x18001aba0  pop     r14
0x18001aba2  pop     r13
0x18001aba4  pop     r12
0x18001aba6  pop     rdi
0x18001aba7  pop     rsi
0x18001aba8  pop     rbp
0x18001aba9  retn
0x18001abaa  call    ?_Xlength@?$vector@V?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@@std@@@std@@CAXXZ; std::vector<Microsoft::WRL::ComPtr<IUIRadioInstance>>::_Xlength(void)
```
