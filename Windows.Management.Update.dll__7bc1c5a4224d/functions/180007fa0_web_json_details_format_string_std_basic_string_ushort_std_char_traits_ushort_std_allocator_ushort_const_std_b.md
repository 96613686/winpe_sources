# web::json::details::format_string(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x180007fa0`
- end: `0x1800080a8`
- name: `?format_string@details@json@web@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z`
- size: `264`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x180004520`

## callees

- `0x1800028f0`
- `0x180002cc0`
- `0x180003df0`
- `0x180006cb0`
- `0x180007fa0`
- `0x180008330`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall web::json::details::format_string(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rbx
  unsigned __int64 v4; // rcx
  unsigned __int64 v5; // rdx
  _QWORD *v6; // rax
  _QWORD *v7; // rax
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
  v7 = (_QWORD *)utility::conversions::to_utf8string(&v12, a1);
  web::json::details::append_escape_string<char>((char *)v2, v7);
  if ( v13 > 0xF )
  {
    if ( v13 + 1 < 0x1000 )
    {
      v8 = v12;
    }
    else
    {
      v8 = (_BYTE *)*((_QWORD *)v12 - 1);
      if ( (unsigned __int64)((_BYTE *)v12 - v8 - 8) > 0x1F )
        __fastfail(5u);
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
0x180007fa0  mov     [rsp+arg_10], rbx
0x180007fa5  push    rdi
0x180007fa6  sub     rsp, 50h
0x180007faa  mov     rax, cs:__security_cookie
0x180007fb1  xor     rax, rsp
0x180007fb4  mov     [rsp+58h+var_18], rax
0x180007fb9  mov     rbx, rdx
0x180007fbc  mov     rdi, rcx
0x180007fbf  mov     rcx, [rdx+10h]
0x180007fc3  mov     rdx, [rdx+18h]
0x180007fc7  cmp     rcx, rdx
0x180007fca  jnb     short loc_180007FE8
0x180007fcc  lea     rax, [rcx+1]
0x180007fd0  mov     [rbx+10h], rax
0x180007fd4  mov     rax, rbx
0x180007fd7  cmp     rdx, 0Fh
0x180007fdb  jbe     short loc_180007FE0
0x180007fdd  mov     rax, [rbx]
0x180007fe0  mov     word ptr [rcx+rax], 22h ; '"'
0x180007fe6  jmp     short loc_180007FFB
0x180007fe8  mov     r9b, 22h ; '"'
0x180007feb  xor     r8d, r8d
0x180007fee  mov     edx, 1
0x180007ff3  mov     rcx, rbx; Src
0x180007ff6  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180007ffb  mov     rdx, rdi
0x180007ffe  lea     rcx, [rsp+58h+var_38]
0x180008003  call    ?to_utf8string@conversions@utility@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; utility::conversions::to_utf8string(std::wstring const &)
0x180008008  nop
0x180008009  mov     rdx, rax
0x18000800c  mov     rcx, rbx; Src
0x18000800f  call    ??$append_escape_string@D@details@json@web@@YAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV34@@Z; web::json::details::append_escape_string<char>(std::string &,std::string const &)
0x180008014  nop
0x180008015  mov     rdx, [rsp+58h+var_20]
0x18000801a  cmp     rdx, 0Fh
0x18000801e  jbe     short loc_180008057
0x180008020  mov     rax, [rsp+58h+var_38]
0x180008025  inc     rdx; unsigned __int64
0x180008028  cmp     rdx, 1000h
0x18000802f  jb      short loc_18000804F
0x180008031  mov     rcx, [rax-8]
0x180008035  sub     rax, rcx
0x180008038  sub     rax, 8
0x18000803c  cmp     rax, 1Fh
0x180008040  ja      short loc_180008048
0x180008042  add     rdx, 27h ; '''
0x180008046  jmp     short loc_180008052
0x180008048  mov     ecx, 5
0x18000804d  int     29h; Win8: RtlFailFast(ecx)
0x18000804f  mov     rcx, rax; void *
0x180008052  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008057  mov     rcx, [rbx+10h]
0x18000805b  mov     rdx, [rbx+18h]
0x18000805f  cmp     rcx, rdx
0x180008062  jnb     short loc_18000807D
0x180008064  lea     rax, [rcx+1]
0x180008068  mov     [rbx+10h], rax
0x18000806c  cmp     rdx, 0Fh
0x180008070  jbe     short loc_180008075
0x180008072  mov     rbx, [rbx]
0x180008075  mov     word ptr [rcx+rbx], 22h ; '"'
0x18000807b  jmp     short loc_180008090
0x18000807d  mov     r9b, 22h ; '"'
0x180008080  xor     r8d, r8d
0x180008083  mov     edx, 1
0x180008088  mov     rcx, rbx; Src
0x18000808b  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180008090  mov     rcx, [rsp+58h+var_18]
0x180008095  xor     rcx, rsp; StackCookie
0x180008098  call    __security_check_cookie
0x18000809d  mov     rbx, [rsp+58h+arg_10]
0x1800080a2  add     rsp, 50h
0x1800080a6  pop     rdi
0x1800080a7  retn
```
