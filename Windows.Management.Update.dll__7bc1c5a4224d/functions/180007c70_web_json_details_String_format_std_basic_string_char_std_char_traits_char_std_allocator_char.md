# web::json::details::_String::format(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x180007c70`
- end: `0x180007da3`
- name: `?format@_String@details@json@web@@MEBAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `307`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callees

- `0x1800028f0`
- `0x180002cc0`
- `0x180003df0`
- `0x180006cb0`
- `0x180007c70`
- `0x180008330`
- `0x1800203bc`

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
  _QWORD *v8; // rax
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
    v8 = (_QWORD *)utility::conversions::to_utf8string(v13, v7);
    web::json::details::append_escape_string<char>((char *)v2, v8);
  }
  else
  {
    utility::conversions::to_utf8string(v13, v7);
    std::string::_Append<char>(v2);
  }
  if ( v14 > 0xF )
  {
    if ( v14 + 1 < 0x1000 )
    {
      v9 = v13[0];
    }
    else
    {
      v9 = (void *)*((_QWORD *)v13[0] - 1);
      if ( (unsigned __int64)((char *)v13[0] - (char *)v9 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v9);
  }
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
0x180007c70  mov     [rsp+arg_10], rbx
0x180007c75  push    rdi
0x180007c76  sub     rsp, 50h
0x180007c7a  mov     rax, cs:__security_cookie
0x180007c81  xor     rax, rsp
0x180007c84  mov     [rsp+58h+var_18], rax
0x180007c89  mov     rbx, rdx
0x180007c8c  mov     rdi, rcx
0x180007c8f  mov     rdx, [rdx+10h]
0x180007c93  mov     rcx, [rbx+18h]
0x180007c97  cmp     rdx, rcx
0x180007c9a  jnb     short loc_180007CB8
0x180007c9c  lea     rax, [rdx+1]
0x180007ca0  mov     [rbx+10h], rax
0x180007ca4  mov     rax, rbx
0x180007ca7  cmp     rcx, 0Fh
0x180007cab  jbe     short loc_180007CB0
0x180007cad  mov     rax, [rbx]
0x180007cb0  mov     word ptr [rdx+rax], 22h ; '"'
0x180007cb6  jmp     short loc_180007CCB
0x180007cb8  mov     r9b, 22h ; '"'
0x180007cbb  xor     r8d, r8d
0x180007cbe  mov     edx, 1
0x180007cc3  mov     rcx, rbx; Src
0x180007cc6  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180007ccb  lea     rdx, [rdi+8]
0x180007ccf  lea     rcx, [rsp+58h+var_38]
0x180007cd4  cmp     byte ptr [rdi+28h], 0
0x180007cd8  jz      short loc_180007CEE
0x180007cda  call    ?to_utf8string@conversions@utility@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; utility::conversions::to_utf8string(std::wstring const &)
0x180007cdf  nop
0x180007ce0  mov     rdx, rax
0x180007ce3  mov     rcx, rbx; Src
0x180007ce6  call    ??$append_escape_string@D@details@json@web@@YAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV34@@Z; web::json::details::append_escape_string<char>(std::string &,std::string const &)
0x180007ceb  nop
0x180007cec  jmp     short loc_180007D10
0x180007cee  call    ?to_utf8string@conversions@utility@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; utility::conversions::to_utf8string(std::wstring const &)
0x180007cf3  nop
0x180007cf4  cmp     qword ptr [rax+18h], 0Fh
0x180007cf9  jbe     short loc_180007D00
0x180007cfb  mov     rdx, [rax]
0x180007cfe  jmp     short loc_180007D03
0x180007d00  mov     rdx, rax
0x180007d03  mov     r8, [rax+10h]
0x180007d07  mov     rcx, rbx; Src
0x180007d0a  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x180007d0f  nop
0x180007d10  mov     rdx, [rsp+58h+var_20]
0x180007d15  cmp     rdx, 0Fh
0x180007d19  jbe     short loc_180007D52
0x180007d1b  mov     rax, [rsp+58h+var_38]
0x180007d20  inc     rdx; unsigned __int64
0x180007d23  cmp     rdx, 1000h
0x180007d2a  jb      short loc_180007D4A
0x180007d2c  mov     rcx, [rax-8]
0x180007d30  sub     rax, rcx
0x180007d33  sub     rax, 8
0x180007d37  cmp     rax, 1Fh
0x180007d3b  ja      short loc_180007D43
0x180007d3d  add     rdx, 27h ; '''
0x180007d41  jmp     short loc_180007D4D
0x180007d43  mov     ecx, 5
0x180007d48  int     29h; Win8: RtlFailFast(ecx)
0x180007d4a  mov     rcx, rax; void *
0x180007d4d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007d52  mov     rcx, [rbx+10h]
0x180007d56  mov     rdx, [rbx+18h]
0x180007d5a  cmp     rcx, rdx
0x180007d5d  jnb     short loc_180007D78
0x180007d5f  lea     rax, [rcx+1]
0x180007d63  mov     [rbx+10h], rax
0x180007d67  cmp     rdx, 0Fh
0x180007d6b  jbe     short loc_180007D70
0x180007d6d  mov     rbx, [rbx]
0x180007d70  mov     word ptr [rcx+rbx], 22h ; '"'
0x180007d76  jmp     short loc_180007D8B
0x180007d78  mov     r9b, 22h ; '"'
0x180007d7b  xor     r8d, r8d
0x180007d7e  mov     edx, 1
0x180007d83  mov     rcx, rbx; Src
0x180007d86  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180007d8b  mov     rcx, [rsp+58h+var_18]
0x180007d90  xor     rcx, rsp; StackCookie
0x180007d93  call    __security_check_cookie
0x180007d98  mov     rbx, [rsp+58h+arg_10]
0x180007d9d  add     rsp, 50h
0x180007da1  pop     rdi
0x180007da2  retn
```
