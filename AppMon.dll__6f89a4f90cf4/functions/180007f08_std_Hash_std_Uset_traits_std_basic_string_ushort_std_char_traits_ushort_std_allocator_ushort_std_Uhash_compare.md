# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Find_last<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64)

- ea: `0x180007f08`
- end: `0x180007f7a`
- name: `??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z`
- size: `114`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007e5c`
- `0x180008428`
- `0x18000a9a8`
- `0x18000ad94`
- `0x18000de70`

## callees

- `0x180007afc`
- `0x180007f08`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // rsi
  _QWORD *v6; // rdx
  _QWORD *v8; // rdi
  _QWORD *v9; // rsi

  v5 = a1[3];
  v6 = (_QWORD *)a1[1];
  v8 = *(_QWORD **)(v5 + 16 * (a4 & a1[6]) + 8);
  if ( v8 == v6 )
  {
    *a2 = v6;
LABEL_3:
    a2[1] = 0;
  }
  else
  {
    v9 = *(_QWORD **)(v5 + 16 * (a4 & a1[6]));
    while ( (unsigned __int8)std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(
                               a1,
                               a3,
                               v8 + 2) )
    {
      if ( v8 == v9 )
      {
        *a2 = v8;
        goto LABEL_3;
      }
      v8 = (_QWORD *)v8[1];
    }
    *a2 = *v8;
    a2[1] = v8;
  }
  return a2;
}

```

## disassembly

```asm
0x180007f08  push    rbx
0x180007f0a  push    rbp
0x180007f0b  push    rsi
0x180007f0c  push    rdi
0x180007f0d  sub     rsp, 28h
0x180007f11  mov     rax, [rcx+30h]
0x180007f15  mov     rbx, rdx
0x180007f18  mov     rsi, [rcx+18h]
0x180007f1c  and     rax, r9
0x180007f1f  mov     rdx, [rcx+8]
0x180007f23  add     rax, rax
0x180007f26  mov     rbp, r8
0x180007f29  mov     rdi, [rsi+rax*8+8]
0x180007f2e  cmp     rdi, rdx
0x180007f31  jnz     short loc_180007F40
0x180007f33  mov     [rbx], rdx
0x180007f36  mov     qword ptr [rbx+8], 0
0x180007f3e  jmp     short loc_180007F6E
0x180007f40  mov     rsi, [rsi+rax*8]
0x180007f44  lea     r8, [rdi+10h]
0x180007f48  mov     rdx, rbp
0x180007f4b  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x180007f50  test    al, al
0x180007f52  jz      short loc_180007F64
0x180007f54  cmp     rdi, rsi
0x180007f57  jz      short loc_180007F5F
0x180007f59  mov     rdi, [rdi+8]
0x180007f5d  jmp     short loc_180007F44
0x180007f5f  mov     [rbx], rdi
0x180007f62  jmp     short loc_180007F36
0x180007f64  mov     rax, [rdi]
0x180007f67  mov     [rbx], rax
0x180007f6a  mov     [rbx+8], rdi
0x180007f6e  mov     rax, rbx
0x180007f71  add     rsp, 28h
0x180007f75  pop     rdi
0x180007f76  pop     rsi
0x180007f77  pop     rbp
0x180007f78  pop     rbx
0x180007f79  retn
```
