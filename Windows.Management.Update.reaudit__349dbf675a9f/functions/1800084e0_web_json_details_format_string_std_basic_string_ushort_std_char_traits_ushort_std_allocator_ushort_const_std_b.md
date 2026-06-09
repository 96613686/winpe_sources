# web::json::details::format_string(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x1800084e0`
- end: `0x1800085e4`
- name: `?format_string@details@json@web@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x180004990`

## callees

- `0x180002880`
- `0x180002c74`
- `0x1800040c0`
- `0x180007310`
- `0x1800084e0`
- `0x1800088c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180008588`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180008588`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall web::json::details::format_string(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rbx
  unsigned __int64 v4; // rcx
  unsigned __int64 v5; // rdx
  _QWORD *v6; // rax
  unsigned __int8 *v7; // rax
  _BYTE *v8; // rcx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  __int64 result; // rax
  void *v12; // [rsp+20h] [rbp-38h] BYREF
  unsigned __int64 v13; // [rsp+38h] [rbp-20h]

  v2 = a2;
  v4 = a2[2];
  v5 = a2[3];
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
  v7 = (unsigned __int8 *)utility::conversions::to_utf8string(&v12, a1);
  web::json::details::append_escape_string<char>(v2, v7);
  if ( v13 > 0xF )
  {
    v8 = v12;
    if ( v13 + 1 >= 0x1000 )
    {
      v8 = (_BYTE *)*((_QWORD *)v12 - 1);
      if ( (unsigned __int64)((_BYTE *)v12 - v8 - 8) > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v8, v13 + 40);
        __debugbreak();
      }
    }
    operator delete(v8);
  }
  v9 = v2[2];
  v10 = v2[3];
  if ( v9 >= v10 )
    return ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(v2);
  result = v9 + 1;
  v2[2] = v9 + 1;
  if ( v10 > 0xF )
    v2 = (_QWORD *)*v2;
  *(_WORD *)((char *)v2 + v9) = 34;
  return result;
}

```

## disassembly

```asm
0x1800084e0  mov     [rsp+arg_10], rbx
0x1800084e5  push    rdi
0x1800084e6  sub     rsp, 50h
0x1800084ea  mov     rax, cs:__security_cookie
0x1800084f1  xor     rax, rsp
0x1800084f4  mov     [rsp+58h+var_18], rax
0x1800084f9  mov     rbx, rdx
0x1800084fc  mov     rdi, rcx
0x1800084ff  mov     rcx, [rdx+10h]
0x180008503  mov     rdx, [rdx+18h]
0x180008507  cmp     rcx, rdx
0x18000850a  jnb     short loc_180008528
0x18000850c  lea     rax, [rcx+1]
0x180008510  mov     [rbx+10h], rax
0x180008514  mov     rax, rbx
0x180008517  cmp     rdx, 0Fh
0x18000851b  jbe     short loc_180008520
0x18000851d  mov     rax, [rbx]
0x180008520  mov     word ptr [rax+rcx], 22h ; '"'
0x180008526  jmp     short loc_18000853A
0x180008528  mov     r9b, 22h ; '"'
0x18000852b  xor     r8d, r8d
0x18000852e  lea     edx, [r8+1]
0x180008532  mov     rcx, rbx; Src
0x180008535  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x18000853a  mov     rdx, rdi
0x18000853d  lea     rcx, [rsp+58h+var_38]
0x180008542  call    ?to_utf8string@conversions@utility@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; utility::conversions::to_utf8string(std::wstring const &)
0x180008547  nop
0x180008548  mov     rdx, rax
0x18000854b  mov     rcx, rbx; Src
0x18000854e  call    ??$append_escape_string@D@details@json@web@@YAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV34@@Z; web::json::details::append_escape_string<char>(std::string &,std::string const &)
0x180008553  nop
0x180008554  mov     rdx, [rsp+58h+var_20]
0x180008559  cmp     rdx, 0Fh
0x18000855d  jbe     short loc_180008594
0x18000855f  inc     rdx; unsigned __int64
0x180008562  mov     rcx, [rsp+58h+var_38]; void *
0x180008567  mov     rax, rcx
0x18000856a  cmp     rdx, 1000h
0x180008571  jb      short loc_18000858F
0x180008573  add     rdx, 27h ; '''
0x180008577  mov     rcx, [rcx-8]
0x18000857b  sub     rax, rcx
0x18000857e  add     rax, 0FFFFFFFFFFFFFFF8h
0x180008582  cmp     rax, 1Fh
0x180008586  jbe     short loc_18000858F
0x180008588  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x18000858e  int     3; Trap to Debugger
0x18000858f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008594  mov     rcx, [rbx+10h]
0x180008598  mov     rdx, [rbx+18h]
0x18000859c  cmp     rcx, rdx
0x18000859f  jnb     short loc_1800085BA
0x1800085a1  lea     rax, [rcx+1]
0x1800085a5  mov     [rbx+10h], rax
0x1800085a9  cmp     rdx, 0Fh
0x1800085ad  jbe     short loc_1800085B2
0x1800085af  mov     rbx, [rbx]
0x1800085b2  mov     word ptr [rbx+rcx], 22h ; '"'
0x1800085b8  jmp     short loc_1800085CC
0x1800085ba  mov     r9b, 22h ; '"'
0x1800085bd  xor     r8d, r8d
0x1800085c0  lea     edx, [r8+1]
0x1800085c4  mov     rcx, rbx; Src
0x1800085c7  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x1800085cc  mov     rcx, [rsp+58h+var_18]
0x1800085d1  xor     rcx, rsp; StackCookie
0x1800085d4  call    __security_check_cookie
0x1800085d9  mov     rbx, [rsp+58h+arg_10]
0x1800085de  add     rsp, 50h
0x1800085e2  pop     rdi
0x1800085e3  retn
```
