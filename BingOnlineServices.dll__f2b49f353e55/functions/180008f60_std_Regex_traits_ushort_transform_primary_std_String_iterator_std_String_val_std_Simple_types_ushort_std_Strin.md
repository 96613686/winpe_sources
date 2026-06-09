# std::_Regex_traits<ushort>::transform_primary<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>)

- ea: `0x180008f60`
- end: `0x1800090b1`
- name: `??$transform_primary@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@?$_Regex_traits@G@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@1@0@Z`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180007a74`

## callees

- `0x180002c2c`
- `0x180004948`
- `0x180004fa0`
- `0x1800063dc`
- `0x180008f60`
- `0x18000e5a8`
- `0x18000f68c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180008fdd`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180008ff1`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180008fdd`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180008ff1`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180008fc9`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180008fc9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Regex_traits<unsigned short>::transform_primary<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // r14
  __int64 v8; // rbp
  unsigned __int64 v9; // rbx
  __int64 v10; // r14
  void *v11; // rax
  unsigned __int64 v12; // rax
  _BYTE v14[16]; // [rsp+40h] [rbp-48h] BYREF
  unsigned __int64 v15; // [rsp+50h] [rbp-38h]

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
0x180008f60  mov     [rsp+arg_10], rbx
0x180008f65  mov     [rsp+arg_18], rbp
0x180008f6a  push    rsi
0x180008f6b  push    rdi
0x180008f6c  push    r14
0x180008f6e  sub     rsp, 70h
0x180008f72  mov     rax, cs:__security_cookie
0x180008f79  xor     rax, rsp
0x180008f7c  mov     [rsp+88h+var_28], rax
0x180008f81  mov     rbx, r9
0x180008f84  mov     rdi, r8
0x180008f87  mov     rsi, rdx
0x180008f8a  mov     [rsp+88h+var_50], rdx
0x180008f8f  mov     [rsp+88h+var_58], 0
0x180008f97  xorps   xmm0, xmm0
0x180008f9a  movups  xmmword ptr [rdx], xmm0
0x180008f9d  mov     qword ptr [rdx+10h], 0
0x180008fa5  mov     qword ptr [rdx+18h], 7
0x180008fad  xor     eax, eax
0x180008faf  mov     [rdx], ax
0x180008fb2  mov     [rsp+88h+var_58], 1
0x180008fba  cmp     r8, r9
0x180008fbd  jz      loc_18000908B
0x180008fc3  mov     r14, [rcx]
0x180008fc6  mov     rcx, r14
0x180008fc9  call    cs:__imp___RTtypeid
0x180008fcf  lea     rbp, [rax+8]
0x180008fd3  lea     rdx, qword_18008E120
0x180008fda  mov     rcx, rbp
0x180008fdd  call    cs:__imp___std_type_info_compare
0x180008fe3  test    eax, eax
0x180008fe5  jz      short loc_180008FFF
0x180008fe7  lea     rdx, qword_18008E0D0
0x180008fee  mov     rcx, rbp
0x180008ff1  call    cs:__imp___std_type_info_compare
0x180008ff7  test    eax, eax
0x180008ff9  jnz     loc_18000908B
0x180008fff  mov     r8, rbx
0x180009002  mov     rdx, rdi
0x180009005  lea     rcx, [rsp+88h+var_48]
0x18000900a  call    ??$?0V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@1@0AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::allocator<ushort> const &)
0x18000900f  nop
0x180009010  lea     rcx, [rsp+88h+var_48]
0x180009015  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000901a  mov     rdi, rax
0x18000901d  mov     rbx, [rsp+88h+var_38]
0x180009022  lea     rbp, [rax+rbx*2]
0x180009026  cmp     [rsi+10h], rbx
0x18000902a  jnb     short loc_180009075
0x18000902c  add     r14, 10h
0x180009030  mov     rdx, rbx
0x180009033  mov     rcx, rsi
0x180009036  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18000903b  mov     rcx, rsi
0x18000903e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180009043  lea     rdx, [rax+rbx*2]
0x180009047  mov     rcx, rsi
0x18000904a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000904f  mov     [rsp+88h+var_68], r14; __int64
0x180009054  mov     r9, rbp
0x180009057  mov     r8, rdi
0x18000905a  mov     rcx, rax; void *
0x18000905d  call    __std_regex_transform_primary_wchar_t
0x180009062  mov     rbx, rax
0x180009065  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009069  jz      short loc_180009073
0x18000906b  cmp     [rsi+10h], rax
0x18000906f  jb      short loc_180009030
0x180009071  jmp     short loc_180009075
0x180009073  xor     ebx, ebx
0x180009075  mov     rdx, rbx
0x180009078  mov     rcx, rsi
0x18000907b  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180009080  nop
0x180009081  lea     rcx, [rsp+88h+var_48]
0x180009086  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000908b  mov     rax, rsi
0x18000908e  mov     rcx, [rsp+88h+var_28]
0x180009093  xor     rcx, rsp; StackCookie
0x180009096  call    __security_check_cookie
0x18000909b  lea     r11, [rsp+88h+var_18]
0x1800090a0  mov     rbx, [r11+30h]
0x1800090a4  mov     rbp, [r11+38h]
0x1800090a8  mov     rsp, r11
0x1800090ab  pop     r14
0x1800090ad  pop     rdi
0x1800090ae  pop     rsi
0x1800090af  retn
```
