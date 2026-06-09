# web::json::details::_Object::format_impl<char>(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x180004520`
- end: `0x1800046d5`
- name: `??$format_impl@D@_Object@details@json@web@@AEBAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `437`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006360`

## callees

- `0x180003df0`
- `0x180004520`
- `0x180007ea0`
- `0x180007fa0`

## pseudocode

```c
__int64 __fastcall web::json::details::_Object::format_impl<char>(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rsi
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // r8
  _QWORD *v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rbx
  __int64 i; // rdi
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  _QWORD *v12; // rax
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rdx
  _QWORD *v15; // rax
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  _QWORD *v18; // rax
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rdx
  __int64 result; // rax

  v2 = a2;
  v4 = a2[2];
  v5 = v2[3];
  if ( v4 >= v5 )
  {
    ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(v2);
  }
  else
  {
    v2[2] = v4 + 1;
    v6 = v2;
    if ( v5 > 0xF )
      v6 = (_QWORD *)*v2;
    *(_WORD *)((char *)v6 + v4) = 123;
  }
  v7 = *(_QWORD *)(a1 + 16);
  v8 = *(_QWORD *)(a1 + 8);
  if ( v8 != v7 )
  {
    for ( i = v7 - 40; v8 != i; v8 += 40 )
    {
      web::json::details::format_string(v8, v2);
      v10 = v2[2];
      v11 = v2[3];
      if ( v10 >= v11 )
      {
        ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(v2);
      }
      else
      {
        v2[2] = v10 + 1;
        v12 = v2;
        if ( v11 > 0xF )
          v12 = (_QWORD *)*v2;
        *(_WORD *)((char *)v12 + v10) = 58;
      }
      web::json::value::format(v8 + 32, v2);
      v13 = v2[2];
      v14 = v2[3];
      if ( v13 >= v14 )
      {
        ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(v2);
      }
      else
      {
        v2[2] = v13 + 1;
        v15 = v2;
        if ( v14 > 0xF )
          v15 = (_QWORD *)*v2;
        *(_WORD *)((char *)v15 + v13) = 44;
      }
    }
    web::json::details::format_string(i, v2);
    v16 = v2[2];
    v17 = v2[3];
    if ( v16 >= v17 )
    {
      ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(v2);
    }
    else
    {
      v2[2] = v16 + 1;
      v18 = v2;
      if ( v17 > 0xF )
        v18 = (_QWORD *)*v2;
      *(_WORD *)((char *)v18 + v16) = 58;
    }
    web::json::value::format(i + 32, v2);
  }
  v19 = v2[2];
  v20 = v2[3];
  if ( v19 >= v20 )
    return ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(v2);
  result = v19 + 1;
  v2[2] = v19 + 1;
  if ( v20 > 0xF )
    v2 = (_QWORD *)*v2;
  *(_WORD *)((char *)v2 + v19) = 125;
  return result;
}

```

## disassembly

```asm
0x180004520  mov     [rsp+arg_0], rbx
0x180004525  mov     [rsp+arg_8], rsi
0x18000452a  push    rdi
0x18000452b  sub     rsp, 20h
0x18000452f  mov     rsi, rdx
0x180004532  mov     rbx, rcx
0x180004535  mov     rdx, [rdx+10h]
0x180004539  mov     r8, [rsi+18h]
0x18000453d  cmp     rdx, r8
0x180004540  jnb     short loc_18000455E
0x180004542  lea     rax, [rdx+1]
0x180004546  mov     [rsi+10h], rax
0x18000454a  mov     rax, rsi
0x18000454d  cmp     r8, 0Fh
0x180004551  jbe     short loc_180004556
0x180004553  mov     rax, [rsi]
0x180004556  mov     word ptr [rdx+rax], 7Bh ; '{'
0x18000455c  jmp     short loc_180004571
0x18000455e  mov     r9b, 7Bh ; '{'
0x180004561  xor     r8d, r8d
0x180004564  mov     edx, 1
0x180004569  mov     rcx, rsi; Src
0x18000456c  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180004571  mov     rdi, [rbx+10h]
0x180004575  mov     rbx, [rbx+8]
0x180004579  cmp     rbx, rdi
0x18000457c  jz      loc_18000467F
0x180004582  add     rdi, 0FFFFFFFFFFFFFFD8h
0x180004586  cmp     rbx, rdi
0x180004589  jz      loc_18000462C
0x18000458f  nop
0x180004590  mov     rdx, rsi
0x180004593  mov     rcx, rbx
0x180004596  call    ?format_string@details@json@web@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; web::json::details::format_string(std::wstring const &,std::string &)
0x18000459b  mov     rcx, [rsi+10h]
0x18000459f  mov     rdx, [rsi+18h]
0x1800045a3  cmp     rcx, rdx
0x1800045a6  jnb     short loc_1800045C4
0x1800045a8  lea     rax, [rcx+1]
0x1800045ac  mov     [rsi+10h], rax
0x1800045b0  mov     rax, rsi
0x1800045b3  cmp     rdx, 0Fh
0x1800045b7  jbe     short loc_1800045BC
0x1800045b9  mov     rax, [rsi]
0x1800045bc  mov     word ptr [rcx+rax], 3Ah ; ':'
0x1800045c2  jmp     short loc_1800045D7
0x1800045c4  mov     r9b, 3Ah ; ':'
0x1800045c7  xor     r8d, r8d
0x1800045ca  mov     edx, 1
0x1800045cf  mov     rcx, rsi; Src
0x1800045d2  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x1800045d7  lea     rcx, [rbx+20h]
0x1800045db  mov     rdx, rsi
0x1800045de  call    ?format@value@json@web@@AEBAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::json::value::format(std::string &)
0x1800045e3  mov     rcx, [rsi+10h]
0x1800045e7  mov     rdx, [rsi+18h]
0x1800045eb  cmp     rcx, rdx
0x1800045ee  jnb     short loc_18000460C
0x1800045f0  lea     rax, [rcx+1]
0x1800045f4  mov     [rsi+10h], rax
0x1800045f8  mov     rax, rsi
0x1800045fb  cmp     rdx, 0Fh
0x1800045ff  jbe     short loc_180004604
0x180004601  mov     rax, [rsi]
0x180004604  mov     word ptr [rcx+rax], 2Ch ; ','
0x18000460a  jmp     short loc_18000461F
0x18000460c  mov     r9b, 2Ch ; ','
0x18000460f  xor     r8d, r8d
0x180004612  mov     edx, 1
0x180004617  mov     rcx, rsi; Src
0x18000461a  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x18000461f  add     rbx, 28h ; '('
0x180004623  cmp     rbx, rdi
0x180004626  jnz     loc_180004590
0x18000462c  mov     rdx, rsi
0x18000462f  mov     rcx, rdi
0x180004632  call    ?format_string@details@json@web@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; web::json::details::format_string(std::wstring const &,std::string &)
0x180004637  mov     rcx, [rsi+10h]
0x18000463b  mov     rdx, [rsi+18h]
0x18000463f  cmp     rcx, rdx
0x180004642  jnb     short loc_180004660
0x180004644  lea     rax, [rcx+1]
0x180004648  mov     [rsi+10h], rax
0x18000464c  mov     rax, rsi
0x18000464f  cmp     rdx, 0Fh
0x180004653  jbe     short loc_180004658
0x180004655  mov     rax, [rsi]
0x180004658  mov     word ptr [rcx+rax], 3Ah ; ':'
0x18000465e  jmp     short loc_180004673
0x180004660  mov     r9b, 3Ah ; ':'
0x180004663  xor     r8d, r8d
0x180004666  mov     edx, 1
0x18000466b  mov     rcx, rsi; Src
0x18000466e  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180004673  lea     rcx, [rdi+20h]
0x180004677  mov     rdx, rsi
0x18000467a  call    ?format@value@json@web@@AEBAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::json::value::format(std::string &)
0x18000467f  mov     rcx, [rsi+10h]
0x180004683  mov     rdx, [rsi+18h]
0x180004687  cmp     rcx, rdx
0x18000468a  jnb     short loc_1800046B3
0x18000468c  lea     rax, [rcx+1]
0x180004690  mov     [rsi+10h], rax
0x180004694  cmp     rdx, 0Fh
0x180004698  jbe     short loc_18000469D
0x18000469a  mov     rsi, [rsi]
0x18000469d  mov     word ptr [rcx+rsi], 7Dh ; '}'
0x1800046a3  mov     rbx, [rsp+28h+arg_0]
0x1800046a8  mov     rsi, [rsp+28h+arg_8]
0x1800046ad  add     rsp, 20h
0x1800046b1  pop     rdi
0x1800046b2  retn
0x1800046b3  mov     r9b, 7Dh ; '}'
0x1800046b6  xor     r8d, r8d
0x1800046b9  mov     edx, 1
0x1800046be  mov     rcx, rsi; Src
0x1800046c1  mov     rbx, [rsp+28h+arg_0]
0x1800046c6  mov     rsi, [rsp+28h+arg_8]
0x1800046cb  add     rsp, 20h
0x1800046cf  pop     rdi
0x1800046d0  jmp     ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
```
