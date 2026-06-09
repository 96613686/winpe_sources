# std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>> &&)

- ea: `0x180006d28`
- end: `0x180006e62`
- name: `??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180009dfc`

## callees

- `0x18000698c`
- `0x1800069ec`
- `0x180006a58`
- `0x180006d28`
- `0x180006e68`
- `0x180006ed4`
- `0x1800075f4`
- `0x180009ca0`

## pseudocode

```c
_QWORD *__fastcall std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>(
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
  _QWORD *v17; // r8
  _QWORD *v18; // r15
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rcx
  _QWORD v23[3]; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v24; // [rsp+38h] [rbp-60h]
  _QWORD *v25; // [rsp+40h] [rbp-58h]

  v3 = 0x1FFFFFFFFFFFFFFFLL;
  v5 = (a1[1] - *a1) >> 3;
  if ( v5 == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>::_Xlength();
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
  v17 = (_QWORD *)v14;
  v23[2] = v3;
  v18 = (_QWORD *)(v14 + 8 * v11);
  *v18 = v15;
  *a3 = 0;
  v19 = a1[1];
  v20 = *a1;
  v25 = v18 + 1;
  v24 = v18;
  if ( a2 != v19 )
  {
    std::_Uninitialized_move<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>> *,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>>(
      v20,
      a2,
      v14);
    v19 = a1[1];
    v17 = v18 + 1;
    v20 = a2;
    v24 = (_QWORD *)v16;
  }
  std::_Uninitialized_move<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>> *,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>>(
    v20,
    v19,
    v17);
  v21 = *a1;
  v23[1] = 0;
  if ( v21 )
  {
    std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>>(
      v21,
      a1[1]);
    std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  *a1 = v16;
  a1[1] = v16 + 8 * v8;
  a1[2] = v16 + 8 * v3;
  std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>::_Reallocation_guard::~_Reallocation_guard(v23);
  return v18;
}

```

## disassembly

```asm
0x180006d28  push    rbx
0x180006d2a  push    rbp
0x180006d2b  push    rsi
0x180006d2c  push    rdi
0x180006d2d  push    r12
0x180006d2f  push    r13
0x180006d31  push    r14
0x180006d33  push    r15
0x180006d35  sub     rsp, 58h
0x180006d39  mov     rax, [rcx+8]
0x180006d3d  mov     rdi, 1FFFFFFFFFFFFFFFh
0x180006d47  sub     rax, [rcx]
0x180006d4a  mov     r13, r8
0x180006d4d  sar     rax, 3
0x180006d51  mov     rbp, rdx
0x180006d54  mov     rbx, rcx
0x180006d57  cmp     rax, rdi
0x180006d5a  jz      loc_180006E5C
0x180006d60  mov     r15, rdx
0x180006d63  lea     r14, [rax+1]
0x180006d67  sub     r15, [rcx]
0x180006d6a  mov     rax, rdi
0x180006d6d  mov     rcx, [rcx+10h]
0x180006d71  sub     rcx, [rbx]
0x180006d74  sar     rcx, 3
0x180006d78  mov     rdx, rcx
0x180006d7b  sar     r15, 3
0x180006d7f  shr     rdx, 1
0x180006d82  sub     rax, rdx
0x180006d85  cmp     rcx, rax
0x180006d88  ja      short loc_180006D95
0x180006d8a  lea     rdi, [rdx+rcx]
0x180006d8e  cmp     rdi, r14
0x180006d91  cmovb   rdi, r14
0x180006d95  mov     rcx, rdi
0x180006d98  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x180006d9d  mov     rcx, rax
0x180006da0  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180006da5  mov     rcx, [r13+0]
0x180006da9  mov     rsi, rax
0x180006dac  mov     [rsp+98h+var_78], rbx
0x180006db1  mov     r8, rax
0x180006db4  mov     [rsp+98h+var_68], rdi
0x180006db9  lea     r15, [rax+r15*8]
0x180006dbd  mov     [r15], rcx
0x180006dc0  lea     r12, [r15+8]
0x180006dc4  mov     qword ptr [r13+0], 0
0x180006dcc  mov     rdx, [rbx+8]
0x180006dd0  mov     rcx, [rbx]
0x180006dd3  mov     [rsp+98h+var_58], r12
0x180006dd8  mov     [rsp+98h+var_60], r15
0x180006ddd  cmp     rbp, rdx
0x180006de0  jz      short loc_180006DF9
0x180006de2  mov     rdx, rbp
0x180006de5  call    ??$_Uninitialized_move@PEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@0PEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Uninitialized_move<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>> *,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>> *,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>> &)
0x180006dea  mov     rdx, [rbx+8]
0x180006dee  mov     r8, r12
0x180006df1  mov     rcx, rbp
0x180006df4  mov     [rsp+98h+var_60], rsi
0x180006df9  call    ??$_Uninitialized_move@PEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@0PEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Uninitialized_move<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>> *,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>> *,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>> &)
0x180006dfe  mov     rcx, [rbx]
0x180006e01  mov     [rsp+98h+var_70], 0
0x180006e0a  test    rcx, rcx
0x180006e0d  jz      short loc_180006E2B
0x180006e0f  mov     rdx, [rbx+8]
0x180006e13  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>> &)
0x180006e18  mov     rdx, [rbx+10h]
0x180006e1c  sub     rdx, [rbx]
0x180006e1f  mov     rcx, [rbx]
0x180006e22  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180006e26  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180006e2b  mov     [rbx], rsi
0x180006e2e  lea     rcx, [rsi+r14*8]
0x180006e32  mov     [rbx+8], rcx
0x180006e36  lea     rcx, [rsi+rdi*8]
0x180006e3a  mov     [rbx+10h], rcx
0x180006e3e  lea     rcx, [rsp+98h+var_78]
0x180006e43  call    ??1_Reallocation_guard@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>::_Reallocation_guard::~_Reallocation_guard(void)
0x180006e48  mov     rax, r15
0x180006e4b  add     rsp, 58h
0x180006e4f  pop     r15
0x180006e51  pop     r14
0x180006e53  pop     r13
0x180006e55  pop     r12
0x180006e57  pop     rdi
0x180006e58  pop     rsi
0x180006e59  pop     rbp
0x180006e5a  pop     rbx
0x180006e5b  retn
0x180006e5c  call    ?_Xlength@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@CAXXZ; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>>>::_Xlength(void)
```
