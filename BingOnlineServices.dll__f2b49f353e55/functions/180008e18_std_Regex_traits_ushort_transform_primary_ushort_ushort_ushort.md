# std::_Regex_traits<ushort>::transform_primary<ushort *>(ushort *,ushort *)

- ea: `0x180008e18`
- end: `0x180008f58`
- name: `??$transform_primary@PEAG@?$_Regex_traits@G@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEAG0@Z`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000b034`

## callees

- `0x180002c2c`
- `0x180004948`
- `0x180004fa0`
- `0x1800063dc`
- `0x180008e18`
- `0x18000e5a8`
- `0x18000f68c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180008e8e`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180008ea2`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180008e8e`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180008ea2`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180008e7a`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180008e7a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Regex_traits<unsigned short>::transform_primary<unsigned short *>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // rsi
  __int64 v8; // rdi
  unsigned __int64 v9; // rdi
  __int64 v10; // rsi
  void *v11; // rax
  unsigned __int64 v12; // rax
  _BYTE v14[16]; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int64 v15; // [rsp+50h] [rbp-48h]

  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 7;
  *(_WORD *)a2 = 0;
  if ( a3 != a4 )
  {
    v7 = *a1;
    v8 = __RTtypeid(*a1) + 8;
    if ( !(unsigned int)__std_type_info_compare(v8, &qword_18008E120)
      || !(unsigned int)__std_type_info_compare(v8, &qword_18008E0D0) )
    {
      std::wstring::wstring(v14, a3, a4);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
      v9 = v15;
      if ( *(_QWORD *)(a2 + 16) < v15 )
      {
        v10 = v7 + 16;
        while ( 1 )
        {
          std::wstring::resize(a2, v9);
          std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
          v11 = (void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
          v12 = _std_regex_transform_primary_wchar_t(v11, v10);
          v9 = v12;
          if ( v12 == -1 )
            break;
          if ( *(_QWORD *)(a2 + 16) >= v12 )
            goto LABEL_10;
        }
        v9 = 0;
      }
LABEL_10:
      std::wstring::resize(a2, v9);
      std::wstring::_Tidy_deallocate(v14);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180008e18  push    rbx
0x180008e1a  push    rbp
0x180008e1b  push    rsi
0x180008e1c  push    rdi
0x180008e1d  push    r14
0x180008e1f  sub     rsp, 70h
0x180008e23  mov     rax, cs:__security_cookie
0x180008e2a  xor     rax, rsp
0x180008e2d  mov     [rsp+98h+var_38], rax
0x180008e32  mov     r14, r9
0x180008e35  mov     rbp, r8
0x180008e38  mov     rbx, rdx
0x180008e3b  mov     [rsp+98h+var_60], rdx
0x180008e40  mov     [rsp+98h+var_68], 0
0x180008e48  xorps   xmm0, xmm0
0x180008e4b  movups  xmmword ptr [rdx], xmm0
0x180008e4e  mov     qword ptr [rdx+10h], 0
0x180008e56  mov     qword ptr [rdx+18h], 7
0x180008e5e  xor     eax, eax
0x180008e60  mov     [rdx], ax
0x180008e63  mov     [rsp+98h+var_68], 1
0x180008e6b  cmp     r8, r9
0x180008e6e  jz      loc_180008F3C
0x180008e74  mov     rsi, [rcx]
0x180008e77  mov     rcx, rsi
0x180008e7a  call    cs:__imp___RTtypeid
0x180008e80  lea     rdi, [rax+8]
0x180008e84  lea     rdx, qword_18008E120
0x180008e8b  mov     rcx, rdi
0x180008e8e  call    cs:__imp___std_type_info_compare
0x180008e94  test    eax, eax
0x180008e96  jz      short loc_180008EB0
0x180008e98  lea     rdx, qword_18008E0D0
0x180008e9f  mov     rcx, rdi
0x180008ea2  call    cs:__imp___std_type_info_compare
0x180008ea8  test    eax, eax
0x180008eaa  jnz     loc_180008F3C
0x180008eb0  mov     r8, r14
0x180008eb3  mov     rdx, rbp
0x180008eb6  lea     rcx, [rsp+98h+var_58]
0x180008ebb  call    ??$?0V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@1@0AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::allocator<ushort> const &)
0x180008ec0  nop
0x180008ec1  lea     rcx, [rsp+98h+var_58]
0x180008ec6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180008ecb  mov     r14, rax
0x180008ece  mov     rdi, [rsp+98h+var_48]
0x180008ed3  lea     rbp, [rax+rdi*2]
0x180008ed7  cmp     [rbx+10h], rdi
0x180008edb  jnb     short loc_180008F26
0x180008edd  add     rsi, 10h
0x180008ee1  mov     rdx, rdi
0x180008ee4  mov     rcx, rbx
0x180008ee7  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180008eec  mov     rcx, rbx
0x180008eef  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180008ef4  lea     rdx, [rax+rdi*2]
0x180008ef8  mov     rcx, rbx
0x180008efb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180008f00  mov     [rsp+98h+var_78], rsi; __int64
0x180008f05  mov     r9, rbp
0x180008f08  mov     r8, r14
0x180008f0b  mov     rcx, rax; void *
0x180008f0e  call    __std_regex_transform_primary_wchar_t
0x180008f13  mov     rdi, rax
0x180008f16  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008f1a  jz      short loc_180008F24
0x180008f1c  cmp     [rbx+10h], rax
0x180008f20  jb      short loc_180008EE1
0x180008f22  jmp     short loc_180008F26
0x180008f24  xor     edi, edi
0x180008f26  mov     rdx, rdi
0x180008f29  mov     rcx, rbx
0x180008f2c  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180008f31  nop
0x180008f32  lea     rcx, [rsp+98h+var_58]
0x180008f37  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180008f3c  mov     rax, rbx
0x180008f3f  mov     rcx, [rsp+98h+var_38]
0x180008f44  xor     rcx, rsp; StackCookie
0x180008f47  call    __security_check_cookie
0x180008f4c  add     rsp, 70h
0x180008f50  pop     r14
0x180008f52  pop     rdi
0x180008f53  pop     rsi
0x180008f54  pop     rbp
0x180008f55  pop     rbx
0x180008f56  retn
```
