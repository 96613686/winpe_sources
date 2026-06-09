# std::_Tree<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Find_lower_bound<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x18000f030`
- end: `0x18000f0c3`
- name: `??$_Find_lower_bound@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z`
- size: `147`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f1b8`
- `0x180014368`
- `0x180014470`
- `0x180015b6c`
- `0x18001a0e8`

## callees

- `0x18000f030`
- `0x18000f16c`
- `0x180010618`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Find_lower_bound<std::string>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 *v5; // r9
  __int64 *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // r8
  int v9; // eax

  v5 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
  *a2 = v5;
  v6 = v5;
  a2[1] = 0;
  for ( a2[2] = *(_QWORD *)a1; !*((_BYTE *)v6 + 25); v6 = (__int64 *)*v6 )
  {
    *a2 = v6;
    std::_String_val<std::_Simple_types<char>>::_Myptr(a3);
    v7 = std::_String_val<std::_Simple_types<char>>::_Myptr(v6 + 4);
    if ( (int)std::_Traits_compare<std::char_traits<char>>(v7, v6[6], v8, *(_QWORD *)(a3 + 16)) >= 0 )
    {
      a2[2] = v6;
      v9 = 1;
    }
    else
    {
      v6 += 2;
      v9 = 0;
    }
    *((_DWORD *)a2 + 2) = v9;
  }
  return a2;
}

```

## disassembly

```asm
0x18000f030  mov     [rsp+arg_0], rbx
0x18000f035  mov     [rsp+arg_8], rsi
0x18000f03a  push    rdi
0x18000f03b  sub     rsp, 20h
0x18000f03f  mov     rax, [rcx]
0x18000f042  mov     rsi, r8
0x18000f045  mov     rdi, rdx
0x18000f048  mov     r9, [rax+8]
0x18000f04c  mov     [rdx], r9
0x18000f04f  mov     rbx, r9
0x18000f052  mov     qword ptr [rdx+8], 0
0x18000f05a  mov     rax, [rcx]
0x18000f05d  mov     [rdx+10h], rax
0x18000f061  cmp     byte ptr [r9+19h], 0
0x18000f066  jnz     short loc_18000F0B0
0x18000f068  mov     rcx, rsi
0x18000f06b  mov     [rdi], rbx
0x18000f06e  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18000f073  lea     rcx, [rbx+20h]
0x18000f077  mov     r8, rax
0x18000f07a  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18000f07f  mov     r9, [rsi+10h]
0x18000f083  mov     rcx, rax
0x18000f086  mov     rdx, [rbx+30h]
0x18000f08a  call    ??$_Traits_compare@U?$char_traits@D@std@@@std@@YAHQEBD_K01@Z; std::_Traits_compare<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x18000f08f  test    eax, eax
0x18000f091  jns     short loc_18000F09B
0x18000f093  add     rbx, 10h
0x18000f097  xor     eax, eax
0x18000f099  jmp     short loc_18000F0A4
0x18000f09b  mov     [rdi+10h], rbx
0x18000f09f  mov     eax, 1
0x18000f0a4  mov     [rdi+8], eax
0x18000f0a7  mov     rbx, [rbx]
0x18000f0aa  cmp     byte ptr [rbx+19h], 0
0x18000f0ae  jz      short loc_18000F068
0x18000f0b0  mov     rbx, [rsp+28h+arg_0]
0x18000f0b5  mov     rax, rdi
0x18000f0b8  mov     rsi, [rsp+28h+arg_8]
0x18000f0bd  add     rsp, 20h
0x18000f0c1  pop     rdi
0x18000f0c2  retn
```
