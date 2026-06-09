# std::vector<Microsoft::WRL::ComPtr<IUIRadioInstance>,std::allocator<Microsoft::WRL::ComPtr<IUIRadioInstance>>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IUIRadioInstance> const &>(Microsoft::WRL::ComPtr<IUIRadioInstance> * const,Microsoft::WRL::ComPtr<IUIRadioInstance> const &)

- ea: `0x18001a500`
- end: `0x18001a644`
- name: `??$_Emplace_reallocate@AEBV?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@@?$vector@V?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@QEAV234@AEBV234@@Z`
- size: `324`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001ecb0`

## callees

- `0x180006b98`
- `0x180007c1c`
- `0x18000a6a0`
- `0x18000b490`
- `0x180017774`
- `0x180019654`
- `0x18001a500`
- `0x18001b154`
- `0x18001c374`

## pseudocode

```c
__int64 *__fastcall std::vector<Microsoft::WRL::ComPtr<IUIRadioInstance>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IUIRadioInstance> const &>(
        __int64 *a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v3; // rdi
  __int64 v5; // rax
  unsigned __int64 v8; // r14
  __int64 v9; // r15
  unsigned __int64 v10; // rcx
  __int64 v11; // r15
  unsigned __int64 v12; // rdx
  __int64 size_of; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rsi
  __int64 *v17; // r15
  __int64 v18; // rdx
  __int64 *v19; // r8
  __int64 v20; // rcx
  __int64 v21; // rcx
  _QWORD v23[3]; // [rsp+20h] [rbp-68h] BYREF
  __int64 *v24; // [rsp+38h] [rbp-50h]
  __int64 *v25; // [rsp+40h] [rbp-48h]

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
  v23[0] = a1;
  v23[2] = v3;
  v17 = (__int64 *)(v14 + 8 * v11);
  *v17 = v15;
  v25 = v17 + 1;
  Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(v17);
  v18 = a1[1];
  v19 = (__int64 *)v16;
  v20 = *a1;
  v24 = v17;
  if ( a2 != v18 )
  {
    std::_Uninitialized_move<Microsoft::WRL::ComPtr<IUIRadioInstance> *,std::allocator<Microsoft::WRL::ComPtr<IUIRadioInstance>>>(
      v20,
      a2,
      v16);
    v18 = a1[1];
    v19 = v17 + 1;
    v20 = a2;
    v24 = (__int64 *)v16;
  }
  std::_Uninitialized_move<Microsoft::WRL::ComPtr<IUIRadioInstance> *,std::allocator<Microsoft::WRL::ComPtr<IUIRadioInstance>>>(
    v20,
    v18,
    v19);
  v21 = *a1;
  v23[1] = 0;
  if ( v21 )
  {
    std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<IUIRadioInstance>>>(v21, a1[1]);
    std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  *a1 = v16;
  a1[1] = v16 + 8 * v8;
  a1[2] = v16 + 8 * v3;
  std::vector<Microsoft::WRL::ComPtr<IUIRadioInstance>>::_Reallocation_guard::~_Reallocation_guard(v23);
  return v17;
}

```

## disassembly

```asm
0x18001a500  mov     [rsp+arg_10], rbx
0x18001a505  push    rbp
0x18001a506  push    rsi
0x18001a507  push    rdi
0x18001a508  push    r12
0x18001a50a  push    r13
0x18001a50c  push    r14
0x18001a50e  push    r15
0x18001a510  sub     rsp, 50h
0x18001a514  mov     rax, [rcx+8]
0x18001a518  mov     rdi, 1FFFFFFFFFFFFFFFh
0x18001a522  sub     rax, [rcx]
0x18001a525  mov     r13, r8
0x18001a528  sar     rax, 3
0x18001a52c  mov     rbp, rdx
0x18001a52f  mov     rbx, rcx
0x18001a532  cmp     rax, rdi
0x18001a535  jz      loc_18001A63E
0x18001a53b  mov     r15, rdx
0x18001a53e  lea     r14, [rax+1]
0x18001a542  sub     r15, [rcx]
0x18001a545  mov     rax, rdi
0x18001a548  mov     rcx, [rcx+10h]
0x18001a54c  sub     rcx, [rbx]
0x18001a54f  sar     rcx, 3
0x18001a553  mov     rdx, rcx
0x18001a556  sar     r15, 3
0x18001a55a  shr     rdx, 1
0x18001a55d  sub     rax, rdx
0x18001a560  cmp     rcx, rax
0x18001a563  ja      short loc_18001A570
0x18001a565  lea     rdi, [rdx+rcx]
0x18001a569  cmp     rdi, r14
0x18001a56c  cmovb   rdi, r14
0x18001a570  mov     rcx, rdi
0x18001a573  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18001a578  mov     rcx, rax
0x18001a57b  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001a580  mov     rcx, [r13+0]
0x18001a584  mov     rsi, rax
0x18001a587  mov     [rsp+88h+var_68], rbx
0x18001a58c  mov     [rsp+88h+var_58], rdi
0x18001a591  lea     r15, [rax+r15*8]
0x18001a595  mov     [r15], rcx
0x18001a598  lea     r12, [r15+8]
0x18001a59c  mov     rcx, r15
0x18001a59f  mov     [rsp+88h+var_48], r12
0x18001a5a4  call    ?InternalAddRef@?$ComPtr@UIUIRadioInstanceInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(void)
0x18001a5a9  mov     rdx, [rbx+8]
0x18001a5ad  mov     r8, rsi
0x18001a5b0  mov     rcx, [rbx]
0x18001a5b3  mov     [rsp+88h+var_50], r15
0x18001a5b8  cmp     rbp, rdx
0x18001a5bb  jz      short loc_18001A5D4
0x18001a5bd  mov     rdx, rbp
0x18001a5c0  call    ??$_Uninitialized_move@PEAV?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@@std@@@std@@YAPEAV?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@QEAV123@0PEAV123@AEAV?$allocator@V?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@@0@@Z; std::_Uninitialized_move<Microsoft::WRL::ComPtr<IUIRadioInstance> *,std::allocator<Microsoft::WRL::ComPtr<IUIRadioInstance>>>(Microsoft::WRL::ComPtr<IUIRadioInstance> * const,Microsoft::WRL::ComPtr<IUIRadioInstance> * const,Microsoft::WRL::ComPtr<IUIRadioInstance> *,std::allocator<Microsoft::WRL::ComPtr<IUIRadioInstance>> &)
0x18001a5c5  mov     rdx, [rbx+8]
0x18001a5c9  mov     r8, r12
0x18001a5cc  mov     rcx, rbp
0x18001a5cf  mov     [rsp+88h+var_50], rsi
0x18001a5d4  call    ??$_Uninitialized_move@PEAV?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@@std@@@std@@YAPEAV?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@QEAV123@0PEAV123@AEAV?$allocator@V?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@@0@@Z; std::_Uninitialized_move<Microsoft::WRL::ComPtr<IUIRadioInstance> *,std::allocator<Microsoft::WRL::ComPtr<IUIRadioInstance>>>(Microsoft::WRL::ComPtr<IUIRadioInstance> * const,Microsoft::WRL::ComPtr<IUIRadioInstance> * const,Microsoft::WRL::ComPtr<IUIRadioInstance> *,std::allocator<Microsoft::WRL::ComPtr<IUIRadioInstance>> &)
0x18001a5d9  mov     rcx, [rbx]
0x18001a5dc  mov     [rsp+88h+var_60], 0
0x18001a5e5  test    rcx, rcx
0x18001a5e8  jz      short loc_18001A606
0x18001a5ea  mov     rdx, [rbx+8]
0x18001a5ee  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<IUIRadioInstance>>>(Microsoft::WRL::ComPtr<IUIRadioInstance> *,Microsoft::WRL::ComPtr<IUIRadioInstance> * const,std::allocator<Microsoft::WRL::ComPtr<IUIRadioInstance>> &)
0x18001a5f3  mov     rdx, [rbx+10h]
0x18001a5f7  sub     rdx, [rbx]
0x18001a5fa  mov     rcx, [rbx]
0x18001a5fd  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001a601  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001a606  mov     [rbx], rsi
0x18001a609  lea     rcx, [rsi+r14*8]
0x18001a60d  mov     [rbx+8], rcx
0x18001a611  lea     rcx, [rsi+rdi*8]
0x18001a615  mov     [rbx+10h], rcx
0x18001a619  lea     rcx, [rsp+88h+var_68]
0x18001a61e  call    ??1_Reallocation_guard@?$vector@V?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<IUIRadioInstance>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18001a623  mov     rbx, [rsp+88h+arg_10]
0x18001a62b  mov     rax, r15
0x18001a62e  add     rsp, 50h
0x18001a632  pop     r15
0x18001a634  pop     r14
0x18001a636  pop     r13
0x18001a638  pop     r12
0x18001a63a  pop     rdi
0x18001a63b  pop     rsi
0x18001a63c  pop     rbp
0x18001a63d  retn
0x18001a63e  call    ?_Xlength@?$vector@V?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@@std@@@std@@CAXXZ; std::vector<Microsoft::WRL::ComPtr<IUIRadioInstance>>::_Xlength(void)
```
