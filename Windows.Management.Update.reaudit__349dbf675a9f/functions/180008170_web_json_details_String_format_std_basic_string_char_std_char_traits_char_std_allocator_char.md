# web::json::details::_String::format(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x180008170`
- end: `0x1800082da`
- name: `?format@_String@details@json@web@@MEBAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `362`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callees

- `0x180002880`
- `0x180002c74`
- `0x1800040c0`
- `0x180007310`
- `0x180008170`
- `0x1800088c0`
- `0x180023c0c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180008223`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18000827e`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180008223`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18000827e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall web::json::details::_String::format(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rbx
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rcx
  _QWORD *v6; // rax
  __int64 v7; // rdx
  unsigned __int8 *v8; // rax
  void *v9; // rcx
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  __int64 result; // rax
  void *v13[3]; // [rsp+20h] [rbp-38h] BYREF
  unsigned __int64 v14; // [rsp+38h] [rbp-20h]

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
    *(_WORD *)((char *)v6 + v4) = 34;
  }
  v7 = a1 + 8;
  if ( *(_BYTE *)(a1 + 40) )
  {
    v8 = (unsigned __int8 *)utility::conversions::to_utf8string(v13, v7);
    web::json::details::append_escape_string<char>(v2, v8);
    if ( v14 <= 0xF )
      goto LABEL_16;
    v9 = v13[0];
    if ( v14 + 1 >= 0x1000 )
    {
      v9 = (void *)*((_QWORD *)v13[0] - 1);
      if ( (unsigned __int64)((char *)v13[0] - (char *)v9 - 8) > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v9, v14 + 40);
        __debugbreak();
      }
    }
  }
  else
  {
    utility::conversions::to_utf8string(v13, v7);
    std::string::append(v2);
    if ( v14 <= 0xF )
      goto LABEL_16;
    v9 = v13[0];
    if ( v14 + 1 >= 0x1000 )
    {
      v9 = (void *)*((_QWORD *)v13[0] - 1);
      if ( (unsigned __int64)((char *)v13[0] - (char *)v9 - 8) > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v9, v14 + 40);
        __debugbreak();
      }
    }
  }
  operator delete(v9);
LABEL_16:
  v10 = v2[2];
  v11 = v2[3];
  if ( v10 >= v11 )
    return ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(v2);
  result = v10 + 1;
  v2[2] = v10 + 1;
  if ( v11 > 0xF )
    v2 = (_QWORD *)*v2;
  *(_WORD *)((char *)v2 + v10) = 34;
  return result;
}

```

## disassembly

```asm
0x180008170  mov     [rsp+arg_10], rbx
0x180008175  push    rdi
0x180008176  sub     rsp, 50h
0x18000817a  mov     rax, cs:__security_cookie
0x180008181  xor     rax, rsp
0x180008184  mov     [rsp+58h+var_18], rax
0x180008189  mov     rbx, rdx
0x18000818c  mov     rdi, rcx
0x18000818f  mov     rdx, [rdx+10h]
0x180008193  mov     rcx, [rbx+18h]
0x180008197  cmp     rdx, rcx
0x18000819a  jnb     short loc_1800081B8
0x18000819c  lea     rax, [rdx+1]
0x1800081a0  mov     [rbx+10h], rax
0x1800081a4  mov     rax, rbx
0x1800081a7  cmp     rcx, 0Fh
0x1800081ab  jbe     short loc_1800081B0
0x1800081ad  mov     rax, [rbx]
0x1800081b0  mov     word ptr [rax+rdx], 22h ; '"'
0x1800081b6  jmp     short loc_1800081CA
0x1800081b8  mov     r9b, 22h ; '"'
0x1800081bb  xor     r8d, r8d
0x1800081be  lea     edx, [r8+1]
0x1800081c2  mov     rcx, rbx; Src
0x1800081c5  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x1800081ca  lea     rdx, [rdi+8]
0x1800081ce  lea     rcx, [rsp+58h+var_38]
0x1800081d3  cmp     byte ptr [rdi+28h], 0
0x1800081d7  jz      short loc_18000822A
0x1800081d9  call    ?to_utf8string@conversions@utility@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; utility::conversions::to_utf8string(std::wstring const &)
0x1800081de  nop
0x1800081df  mov     rdx, rax
0x1800081e2  mov     rcx, rbx; Src
0x1800081e5  call    ??$append_escape_string@D@details@json@web@@YAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV34@@Z; web::json::details::append_escape_string<char>(std::string &,std::string const &)
0x1800081ea  nop
0x1800081eb  mov     rdx, [rsp+58h+var_20]
0x1800081f0  cmp     rdx, 0Fh
0x1800081f4  jbe     loc_18000828A
0x1800081fa  inc     rdx; unsigned __int64
0x1800081fd  mov     rcx, [rsp+58h+var_38]; void *
0x180008202  mov     rax, rcx
0x180008205  cmp     rdx, 1000h
0x18000820c  jb      short loc_180008285
0x18000820e  add     rdx, 27h ; '''
0x180008212  mov     rcx, [rcx-8]
0x180008216  sub     rax, rcx
0x180008219  add     rax, 0FFFFFFFFFFFFFFF8h
0x18000821d  cmp     rax, 1Fh
0x180008221  jbe     short loc_180008285
0x180008223  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x180008229  int     3; Trap to Debugger
0x18000822a  call    ?to_utf8string@conversions@utility@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; utility::conversions::to_utf8string(std::wstring const &)
0x18000822f  nop
0x180008230  mov     rdx, rax
0x180008233  cmp     qword ptr [rax+18h], 0Fh
0x180008238  jbe     short loc_18000823D
0x18000823a  mov     rdx, [rax]
0x18000823d  mov     r8, [rax+10h]
0x180008241  mov     rcx, rbx; Src
0x180008244  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x180008249  nop
0x18000824a  mov     rdx, [rsp+58h+var_20]
0x18000824f  cmp     rdx, 0Fh
0x180008253  jbe     short loc_18000828A
0x180008255  inc     rdx
0x180008258  mov     rcx, [rsp+58h+var_38]
0x18000825d  mov     rax, rcx
0x180008260  cmp     rdx, 1000h
0x180008267  jb      short loc_180008285
0x180008269  add     rdx, 27h ; '''
0x18000826d  mov     rcx, [rcx-8]
0x180008271  sub     rax, rcx
0x180008274  add     rax, 0FFFFFFFFFFFFFFF8h
0x180008278  cmp     rax, 1Fh
0x18000827c  jbe     short loc_180008285
0x18000827e  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x180008284  int     3; Trap to Debugger
0x180008285  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000828a  mov     rcx, [rbx+10h]
0x18000828e  mov     rdx, [rbx+18h]
0x180008292  cmp     rcx, rdx
0x180008295  jnb     short loc_1800082B0
0x180008297  lea     rax, [rcx+1]
0x18000829b  mov     [rbx+10h], rax
0x18000829f  cmp     rdx, 0Fh
0x1800082a3  jbe     short loc_1800082A8
0x1800082a5  mov     rbx, [rbx]
0x1800082a8  mov     word ptr [rbx+rcx], 22h ; '"'
0x1800082ae  jmp     short loc_1800082C2
0x1800082b0  mov     r9b, 22h ; '"'
0x1800082b3  xor     r8d, r8d
0x1800082b6  lea     edx, [r8+1]
0x1800082ba  mov     rcx, rbx; Src
0x1800082bd  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x1800082c2  mov     rcx, [rsp+58h+var_18]
0x1800082c7  xor     rcx, rsp; StackCookie
0x1800082ca  call    __security_check_cookie
0x1800082cf  mov     rbx, [rsp+58h+arg_10]
0x1800082d4  add     rsp, 50h
0x1800082d8  pop     rdi
0x1800082d9  retn
```
