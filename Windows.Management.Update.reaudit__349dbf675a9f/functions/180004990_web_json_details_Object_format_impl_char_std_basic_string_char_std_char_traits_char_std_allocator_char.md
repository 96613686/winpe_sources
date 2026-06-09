# web::json::details::_Object::format_impl<char>(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x180004990`
- end: `0x180004b67`
- name: `??$format_impl@D@_Object@details@json@web@@AEBAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800067d0`

## callees

- `0x1800040c0`
- `0x180004990`
- `0x1800083d0`
- `0x1800084e0`

## pseudocode

```c
__int64 __fastcall web::json::details::_Object::format_impl<char>(__int64 a1, unsigned __int64 *a2)
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
    ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(v2);
    v7 = v2 + 2;
    v8 = v2 + 3;
  }
  else
  {
    v2[2] = v4 + 1;
    v6 = v2;
    v7 = v2 + 2;
    v8 = v2 + 3;
    if ( v5 > 0xF )
      v6 = (unsigned __int64 *)*v2;
    *(_WORD *)((char *)v6 + v4) = 123;
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
          ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(v2);
        }
        else
        {
          v2[2] = v11 + 1;
          v13 = v2;
          if ( v12 > 0xF )
            v13 = (_QWORD *)*v2;
          *(_WORD *)((char *)v13 + v11) = 58;
        }
        web::json::value::format(v9 + 32, v2);
        v14 = v2[2];
        v15 = v2[3];
        if ( v14 >= v15 )
        {
          ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(v2);
        }
        else
        {
          v2[2] = v14 + 1;
          v16 = v2;
          if ( v15 > 0xF )
            v16 = (_QWORD *)*v2;
          *(_WORD *)((char *)v16 + v14) = 44;
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
      ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(v2);
    }
    else
    {
      *v7 = v17 + 1;
      v19 = v2;
      if ( v18 > 0xF )
        v19 = (_QWORD *)*v2;
      *(_WORD *)((char *)v19 + v17) = 58;
    }
    web::json::value::format(v10 + 32, v2);
  }
  v20 = *v7;
  v21 = *v8;
  if ( *v7 >= *v8 )
    return ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(v2);
  result = v20 + 1;
  *v7 = v20 + 1;
  if ( v21 > 0xF )
    v2 = (unsigned __int64 *)*v2;
  *(_WORD *)((char *)v2 + v20) = 125;
  return result;
}

```

## disassembly

```asm
0x180004990  mov     [rsp+arg_0], rbx
0x180004995  mov     [rsp+arg_8], rbp
0x18000499a  mov     [rsp+arg_10], rsi
0x18000499f  mov     [rsp+arg_18], rdi
0x1800049a4  push    r12
0x1800049a6  push    r14
0x1800049a8  push    r15
0x1800049aa  sub     rsp, 20h
0x1800049ae  mov     rsi, rdx
0x1800049b1  mov     rdi, rcx
0x1800049b4  mov     rdx, [rdx+10h]
0x1800049b8  mov     r8, [rsi+18h]
0x1800049bc  cmp     rdx, r8
0x1800049bf  jnb     short loc_1800049E5
0x1800049c1  lea     rax, [rdx+1]
0x1800049c5  mov     [rsi+10h], rax
0x1800049c9  mov     rax, rsi
0x1800049cc  lea     r15, [rsi+10h]
0x1800049d0  lea     rbp, [rsi+18h]
0x1800049d4  cmp     r8, 0Fh
0x1800049d8  jbe     short loc_1800049DD
0x1800049da  mov     rax, [rsi]
0x1800049dd  mov     word ptr [rax+rdx], 7Bh ; '{'
0x1800049e3  jmp     short loc_1800049FF
0x1800049e5  xor     r8d, r8d
0x1800049e8  mov     r9b, 7Bh ; '{'
0x1800049eb  mov     rcx, rsi; Src
0x1800049ee  lea     edx, [r8+1]
0x1800049f2  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x1800049f7  lea     r15, [rsi+10h]
0x1800049fb  lea     rbp, [rsi+18h]
0x1800049ff  mov     rbx, [rdi+8]
0x180004a03  cmp     rbx, [rdi+10h]
0x180004a07  jz      loc_180004B12
0x180004a0d  mov     rdi, [rdi+10h]
0x180004a11  sub     rdi, 28h ; '('
0x180004a15  cmp     rbx, rdi
0x180004a18  jz      loc_180004AC2
0x180004a1e  xchg    ax, ax
0x180004a20  mov     rdx, rsi
0x180004a23  mov     rcx, rbx
0x180004a26  call    ?format_string@details@json@web@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; web::json::details::format_string(std::wstring const &,std::string &)
0x180004a2b  mov     rcx, [rsi+10h]
0x180004a2f  mov     rdx, [rsi+18h]
0x180004a33  cmp     rcx, rdx
0x180004a36  jnb     short loc_180004A54
0x180004a38  lea     rax, [rcx+1]
0x180004a3c  mov     [rsi+10h], rax
0x180004a40  mov     rax, rsi
0x180004a43  cmp     rdx, 0Fh
0x180004a47  jbe     short loc_180004A4C
0x180004a49  mov     rax, [rsi]
0x180004a4c  mov     word ptr [rax+rcx], 3Ah ; ':'
0x180004a52  jmp     short loc_180004A66
0x180004a54  xor     r8d, r8d
0x180004a57  mov     r9b, 3Ah ; ':'
0x180004a5a  mov     rcx, rsi; Src
0x180004a5d  lea     edx, [r8+1]
0x180004a61  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180004a66  lea     rcx, [rbx+20h]
0x180004a6a  mov     rdx, rsi
0x180004a6d  call    ?format@value@json@web@@AEBAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::json::value::format(std::string &)
0x180004a72  mov     rcx, [rsi+10h]
0x180004a76  mov     rdx, [rsi+18h]
0x180004a7a  cmp     rcx, rdx
0x180004a7d  jnb     short loc_180004A9B
0x180004a7f  lea     rax, [rcx+1]
0x180004a83  mov     [rsi+10h], rax
0x180004a87  mov     rax, rsi
0x180004a8a  cmp     rdx, 0Fh
0x180004a8e  jbe     short loc_180004A93
0x180004a90  mov     rax, [rsi]
0x180004a93  mov     word ptr [rax+rcx], 2Ch ; ','
0x180004a99  jmp     short loc_180004AAD
0x180004a9b  xor     r8d, r8d
0x180004a9e  mov     r9b, 2Ch ; ','
0x180004aa1  mov     rcx, rsi; Src
0x180004aa4  lea     edx, [r8+1]
0x180004aa8  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180004aad  add     rbx, 28h ; '('
0x180004ab1  cmp     rbx, rdi
0x180004ab4  jnz     loc_180004A20
0x180004aba  lea     r15, [rsi+10h]
0x180004abe  lea     rbp, [rsi+18h]
0x180004ac2  mov     rdx, rsi
0x180004ac5  mov     rcx, rdi
0x180004ac8  call    ?format_string@details@json@web@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; web::json::details::format_string(std::wstring const &,std::string &)
0x180004acd  mov     rcx, [r15]
0x180004ad0  mov     rdx, [rbp+0]
0x180004ad4  cmp     rcx, rdx
0x180004ad7  jnb     short loc_180004AF4
0x180004ad9  lea     rax, [rcx+1]
0x180004add  mov     [r15], rax
0x180004ae0  mov     rax, rsi
0x180004ae3  cmp     rdx, 0Fh
0x180004ae7  jbe     short loc_180004AEC
0x180004ae9  mov     rax, [rsi]
0x180004aec  mov     word ptr [rax+rcx], 3Ah ; ':'
0x180004af2  jmp     short loc_180004B06
0x180004af4  xor     r8d, r8d
0x180004af7  mov     r9b, 3Ah ; ':'
0x180004afa  mov     rcx, rsi; Src
0x180004afd  lea     edx, [r8+1]
0x180004b01  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180004b06  lea     rcx, [rdi+20h]
0x180004b0a  mov     rdx, rsi
0x180004b0d  call    ?format@value@json@web@@AEBAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::json::value::format(std::string &)
0x180004b12  mov     rcx, [r15]
0x180004b15  mov     rdx, [rbp+0]
0x180004b19  cmp     rcx, rdx
0x180004b1c  jnb     short loc_180004B36
0x180004b1e  lea     rax, [rcx+1]
0x180004b22  mov     [r15], rax
0x180004b25  cmp     rdx, 0Fh
0x180004b29  jbe     short loc_180004B2E
0x180004b2b  mov     rsi, [rsi]
0x180004b2e  mov     word ptr [rsi+rcx], 7Dh ; '}'
0x180004b34  jmp     short loc_180004B48
0x180004b36  xor     r8d, r8d
0x180004b39  mov     r9b, 7Dh ; '}'
0x180004b3c  mov     rcx, rsi; Src
0x180004b3f  lea     edx, [r8+1]
0x180004b43  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180004b48  mov     rbx, [rsp+38h+arg_0]
0x180004b4d  mov     rbp, [rsp+38h+arg_8]
0x180004b52  mov     rsi, [rsp+38h+arg_10]
0x180004b57  mov     rdi, [rsp+38h+arg_18]
0x180004b5c  add     rsp, 20h
0x180004b60  pop     r15
0x180004b62  pop     r14
0x180004b64  pop     r12
0x180004b66  retn
```
