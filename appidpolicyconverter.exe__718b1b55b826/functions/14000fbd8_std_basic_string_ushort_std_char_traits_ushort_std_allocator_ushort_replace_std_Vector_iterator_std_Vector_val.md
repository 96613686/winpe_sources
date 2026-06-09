# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::replace<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>>(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>)

- ea: `0x14000fbd8`
- end: `0x14000fcb8`
- name: `??$replace@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@std@@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@1@0V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@1@1@Z`
- size: `224`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000ffb8`

## callees

- `0x140008368`
- `0x14000b7a0`
- `0x14000facc`
- `0x14000fbd8`
- `0x140013b10`

## pseudocode

```c
_QWORD *__fastcall std::wstring::replace<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned short>>>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  _QWORD *v8; // rax
  __int64 v9; // rdx
  _WORD v11[8]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v12; // [rsp+40h] [rbp-28h]
  __int64 v13; // [rsp+48h] [rbp-20h]

  v13 = 7;
  v12 = 0;
  v11[0] = 0;
  std::wstring::_Construct<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned short>>>>(v11, a4, a5);
  if ( a3 )
    a3 = (a3 - a2) >> 1;
  if ( a1[3] < 8u )
    v8 = a1;
  else
    v8 = (_QWORD *)*a1;
  if ( a2 )
    a2 = (a2 - (__int64)v8) >> 1;
  std::wstring::replace((_DWORD)a1, a2, a3, (unsigned int)v11, 0, -1);
  LOBYTE(v9) = 1;
  std::wstring::_Tidy(v11, v9, 0);
  return a1;
}

```

## disassembly

```asm
0x14000fbd8  mov     r11, rsp
0x14000fbdb  mov     [r11+10h], rbx
0x14000fbdf  mov     [r11+18h], rsi
0x14000fbe3  push    rdi
0x14000fbe4  sub     rsp, 60h
0x14000fbe8  mov     rax, cs:__security_cookie
0x14000fbef  xor     rax, rsp
0x14000fbf2  mov     [rsp+68h+var_18], rax
0x14000fbf7  mov     rdi, r8
0x14000fbfa  mov     rbx, rdx
0x14000fbfd  mov     rsi, rcx
0x14000fc00  mov     qword ptr [r11-28h], 0
0x14000fc08  mov     qword ptr [r11-20h], 0
0x14000fc10  mov     qword ptr [r11-20h], 7
0x14000fc18  mov     qword ptr [r11-28h], 0
0x14000fc20  xor     eax, eax
0x14000fc22  mov     [rsp+68h+var_38], ax
0x14000fc27  mov     r8, [rsp+68h+arg_20]
0x14000fc2f  mov     rdx, r9
0x14000fc32  lea     rcx, [r11-38h]
0x14000fc36  call    ??$_Construct@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@std@@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@1@0Uforward_iterator_tag@1@@Z; std::wstring::_Construct<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ushort>>>,std::forward_iterator_tag)
0x14000fc3b  nop
0x14000fc3c  test    rdi, rdi
0x14000fc3f  jz      short loc_14000FC47
0x14000fc41  sub     rdi, rbx
0x14000fc44  sar     rdi, 1
0x14000fc47  cmp     qword ptr [rsi+18h], 8
0x14000fc4c  jb      short loc_14000FC53
0x14000fc4e  mov     rax, [rsi]
0x14000fc51  jmp     short loc_14000FC56
0x14000fc53  mov     rax, rsi
0x14000fc56  test    rbx, rbx
0x14000fc59  jz      short loc_14000FC61
0x14000fc5b  sub     rbx, rax
0x14000fc5e  sar     rbx, 1
0x14000fc61  mov     [rsp+68h+var_40], 0FFFFFFFFFFFFFFFFh
0x14000fc6a  mov     [rsp+68h+var_48], 0
0x14000fc73  lea     r9, [rsp+68h+var_38]
0x14000fc78  mov     r8, rdi
0x14000fc7b  mov     rdx, rbx
0x14000fc7e  mov     rcx, rsi
0x14000fc81  call    ?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0AEBV12@00@Z; std::wstring::replace(unsigned __int64,unsigned __int64,std::wstring const &,unsigned __int64,unsigned __int64)
0x14000fc86  nop
0x14000fc87  xor     r8d, r8d
0x14000fc8a  mov     dl, 1
0x14000fc8c  lea     rcx, [rsp+68h+var_38]
0x14000fc91  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000fc96  mov     rax, rsi
0x14000fc99  mov     rcx, [rsp+68h+var_18]
0x14000fc9e  xor     rcx, rsp; StackCookie
0x14000fca1  call    __security_check_cookie
0x14000fca6  lea     r11, [rsp+68h+var_8]
0x14000fcab  mov     rbx, [r11+18h]
0x14000fcaf  mov     rsi, [r11+20h]
0x14000fcb3  mov     rsp, r11
0x14000fcb6  pop     rdi
0x14000fcb7  retn
```
