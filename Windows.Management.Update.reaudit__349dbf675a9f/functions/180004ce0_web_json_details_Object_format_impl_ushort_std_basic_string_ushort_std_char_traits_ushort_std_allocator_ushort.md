# web::json::details::_Object::format_impl<ushort>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180004ce0`
- end: `0x180004ec3`
- name: `??$format_impl@G@_Object@details@json@web@@AEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800067e0`

## callees

- `0x180004230`
- `0x180004ce0`
- `0x1800083f0`
- `0x180008410`

## pseudocode

```c
__int64 __fastcall web::json::details::_Object::format_impl<unsigned short>(__int64 a1, unsigned __int64 *a2)
{
  unsigned __int64 *v2; // rsi
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // r8
  unsigned __int64 *v6; // rax
  unsigned __int64 *v7; // r15
  unsigned __int64 *v8; // rbp
  __int64 v9; // rbx
  __int64 v10; // rdi
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  _QWORD *v13; // rax
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  _QWORD *v16; // rax
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rdx
  _QWORD *v19; // rax
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rdx
  __int64 result; // rax

  v2 = a2;
  v4 = a2[2];
  v5 = v2[3];
  if ( v4 >= v5 )
  {
    ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(v2);
    v7 = v2 + 2;
    v8 = v2 + 3;
  }
  else
  {
    v2[2] = v4 + 1;
    v6 = v2;
    v7 = v2 + 2;
    v8 = v2 + 3;
    if ( v5 > 7 )
      v6 = (unsigned __int64 *)*v2;
    *(_DWORD *)((char *)v6 + 2 * v4) = 123;
  }
  v9 = *(_QWORD *)(a1 + 8);
  if ( v9 != *(_QWORD *)(a1 + 16) )
  {
    v10 = *(_QWORD *)(a1 + 16) - 40LL;
    if ( v9 != v10 )
    {
      do
      {
        web::json::details::format_string(v9, v2);
        v11 = v2[2];
        v12 = v2[3];
        if ( v11 >= v12 )
        {
          ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(v2);
        }
        else
        {
          v2[2] = v11 + 1;
          v13 = v2;
          if ( v12 > 7 )
            v13 = (_QWORD *)*v2;
          *(_DWORD *)((char *)v13 + 2 * v11) = 58;
        }
        web::json::value::format(v9 + 32, v2);
        v14 = v2[2];
        v15 = v2[3];
        if ( v14 >= v15 )
        {
          ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(v2);
        }
        else
        {
          v2[2] = v14 + 1;
          v16 = v2;
          if ( v15 > 7 )
            v16 = (_QWORD *)*v2;
          *(_DWORD *)((char *)v16 + 2 * v14) = 44;
        }
        v9 += 40;
      }
      while ( v9 != v10 );
      v7 = v2 + 2;
      v8 = v2 + 3;
    }
    web::json::details::format_string(v10, v2);
    v17 = *v7;
    v18 = *v8;
    if ( *v7 >= *v8 )
    {
      ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(v2);
    }
    else
    {
      *v7 = v17 + 1;
      v19 = v2;
      if ( v18 > 7 )
        v19 = (_QWORD *)*v2;
      *(_DWORD *)((char *)v19 + 2 * v17) = 58;
    }
    web::json::value::format(v10 + 32, v2);
  }
  v20 = *v7;
  v21 = *v8;
  if ( *v7 >= *v8 )
    return ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(v2);
  result = v20 + 1;
  *v7 = v20 + 1;
  if ( v21 > 7 )
    v2 = (unsigned __int64 *)*v2;
  *(_DWORD *)((char *)v2 + 2 * v20) = 125;
  return result;
}

```

## disassembly

```asm
0x180004ce0  mov     [rsp+arg_0], rbx
0x180004ce5  mov     [rsp+arg_8], rbp
0x180004cea  mov     [rsp+arg_10], rsi
0x180004cef  push    rdi
0x180004cf0  push    r12
0x180004cf2  push    r13
0x180004cf4  push    r14
0x180004cf6  push    r15
0x180004cf8  sub     rsp, 20h
0x180004cfc  mov     rsi, rdx
0x180004cff  mov     rdi, rcx
0x180004d02  mov     rdx, [rdx+10h]
0x180004d06  mov     r8, [rsi+18h]
0x180004d0a  cmp     rdx, r8
0x180004d0d  jnb     short loc_180004D34
0x180004d0f  lea     rax, [rdx+1]
0x180004d13  mov     [rsi+10h], rax
0x180004d17  mov     rax, rsi
0x180004d1a  lea     r15, [rsi+10h]
0x180004d1e  lea     rbp, [rsi+18h]
0x180004d22  cmp     r8, 7
0x180004d26  jbe     short loc_180004D2B
0x180004d28  mov     rax, [rsi]
0x180004d2b  mov     dword ptr [rax+rdx*2], 7Bh ; '{'
0x180004d32  jmp     short loc_180004D51
0x180004d34  mov     r9d, 7Bh ; '{'
0x180004d3a  xor     r8d, r8d
0x180004d3d  mov     rcx, rsi; Src
0x180004d40  lea     edx, [r9-7Ah]
0x180004d44  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x180004d49  lea     r15, [rsi+10h]
0x180004d4d  lea     rbp, [rsi+18h]
0x180004d51  mov     rbx, [rdi+8]
0x180004d55  cmp     rbx, [rdi+10h]
0x180004d59  jz      loc_180004E6C
0x180004d5f  mov     rdi, [rdi+10h]
0x180004d63  mov     r13d, 3Ah ; ':'
0x180004d69  sub     rdi, 28h ; '('
0x180004d6d  cmp     rbx, rdi
0x180004d70  jz      loc_180004E1E
0x180004d76  lea     r15d, [r13-0Eh]
0x180004d7a  nop     word ptr [rax+rax+00h]
0x180004d80  mov     rdx, rsi
0x180004d83  mov     rcx, rbx
0x180004d86  call    ?format_string@details@json@web@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV45@@Z; web::json::details::format_string(std::wstring const &,std::wstring &)
0x180004d8b  mov     rcx, [rsi+10h]
0x180004d8f  mov     rdx, [rsi+18h]
0x180004d93  cmp     rcx, rdx
0x180004d96  jnb     short loc_180004DB2
0x180004d98  lea     rax, [rcx+1]
0x180004d9c  mov     [rsi+10h], rax
0x180004da0  mov     rax, rsi
0x180004da3  cmp     rdx, 7
0x180004da7  jbe     short loc_180004DAC
0x180004da9  mov     rax, [rsi]
0x180004dac  mov     [rax+rcx*2], r13d
0x180004db0  jmp     short loc_180004DC4
0x180004db2  xor     r8d, r8d
0x180004db5  mov     r9d, r13d
0x180004db8  mov     rcx, rsi; Src
0x180004dbb  lea     edx, [r8+1]
0x180004dbf  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x180004dc4  lea     rcx, [rbx+20h]
0x180004dc8  mov     rdx, rsi
0x180004dcb  call    ?format@value@json@web@@AEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::format(std::wstring &)
0x180004dd0  mov     rcx, [rsi+10h]
0x180004dd4  mov     rdx, [rsi+18h]
0x180004dd8  cmp     rcx, rdx
0x180004ddb  jnb     short loc_180004DF7
0x180004ddd  lea     rax, [rcx+1]
0x180004de1  mov     [rsi+10h], rax
0x180004de5  mov     rax, rsi
0x180004de8  cmp     rdx, 7
0x180004dec  jbe     short loc_180004DF1
0x180004dee  mov     rax, [rsi]
0x180004df1  mov     [rax+rcx*2], r15d
0x180004df5  jmp     short loc_180004E09
0x180004df7  xor     r8d, r8d
0x180004dfa  mov     r9d, r15d
0x180004dfd  mov     rcx, rsi; Src
0x180004e00  lea     edx, [r8+1]
0x180004e04  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x180004e09  add     rbx, 28h ; '('
0x180004e0d  cmp     rbx, rdi
0x180004e10  jnz     loc_180004D80
0x180004e16  lea     r15, [rsi+10h]
0x180004e1a  lea     rbp, [rsi+18h]
0x180004e1e  mov     rdx, rsi
0x180004e21  mov     rcx, rdi
0x180004e24  call    ?format_string@details@json@web@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV45@@Z; web::json::details::format_string(std::wstring const &,std::wstring &)
0x180004e29  mov     rcx, [r15]
0x180004e2c  mov     rdx, [rbp+0]
0x180004e30  cmp     rcx, rdx
0x180004e33  jnb     short loc_180004E4E
0x180004e35  lea     rax, [rcx+1]
0x180004e39  mov     [r15], rax
0x180004e3c  mov     rax, rsi
0x180004e3f  cmp     rdx, 7
0x180004e43  jbe     short loc_180004E48
0x180004e45  mov     rax, [rsi]
0x180004e48  mov     [rax+rcx*2], r13d
0x180004e4c  jmp     short loc_180004E60
0x180004e4e  xor     r8d, r8d
0x180004e51  mov     r9d, r13d
0x180004e54  mov     rcx, rsi; Src
0x180004e57  lea     edx, [r8+1]
0x180004e5b  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x180004e60  lea     rcx, [rdi+20h]
0x180004e64  mov     rdx, rsi
0x180004e67  call    ?format@value@json@web@@AEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::format(std::wstring &)
0x180004e6c  mov     rcx, [r15]
0x180004e6f  mov     rdx, [rbp+0]
0x180004e73  cmp     rcx, rdx
0x180004e76  jnb     short loc_180004E91
0x180004e78  lea     rax, [rcx+1]
0x180004e7c  mov     [r15], rax
0x180004e7f  cmp     rdx, 7
0x180004e83  jbe     short loc_180004E88
0x180004e85  mov     rsi, [rsi]
0x180004e88  mov     dword ptr [rsi+rcx*2], 7Dh ; '}'
0x180004e8f  jmp     short loc_180004EA6
0x180004e91  mov     r9d, 7Dh ; '}'
0x180004e97  xor     r8d, r8d
0x180004e9a  mov     rcx, rsi; Src
0x180004e9d  lea     edx, [r9-7Ch]
0x180004ea1  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x180004ea6  mov     rbx, [rsp+48h+arg_0]
0x180004eab  mov     rbp, [rsp+48h+arg_8]
0x180004eb0  mov     rsi, [rsp+48h+arg_10]
0x180004eb5  add     rsp, 20h
0x180004eb9  pop     r15
0x180004ebb  pop     r14
0x180004ebd  pop     r13
0x180004ebf  pop     r12
0x180004ec1  pop     rdi
0x180004ec2  retn
```
