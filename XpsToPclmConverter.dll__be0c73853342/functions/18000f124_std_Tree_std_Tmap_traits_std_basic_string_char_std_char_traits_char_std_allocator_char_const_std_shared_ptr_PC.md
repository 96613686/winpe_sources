# std::_Tree<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Lower_bound_duplicate<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>(std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * const,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x18000f124`
- end: `0x18000f164`
- name: `??$_Lower_bound_duplicate@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z`
- size: `64`
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

- `0x18000f124`
- `0x18000f16c`
- `0x180010618`

## pseudocode

```c
bool __fastcall std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Lower_bound_duplicate<std::string>(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // r10
  __int64 v3; // rax
  __int64 v4; // rdx
  __int64 v5; // r10
  __int64 v6; // r8
  bool result; // al

  result = 0;
  if ( !*(_BYTE *)(a2 + 25) )
  {
    std::_String_val<std::_Simple_types<char>>::_Myptr(a2 + 32);
    v3 = std::_String_val<std::_Simple_types<char>>::_Myptr(v2);
    if ( (int)std::_Traits_compare<std::char_traits<char>>(v3, *(_QWORD *)(v5 + 16), v6, *(_QWORD *)(v4 + 48)) >= 0 )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000f124  sub     rsp, 28h
0x18000f128  cmp     byte ptr [rdx+19h], 0
0x18000f12c  mov     r10, r8
0x18000f12f  jnz     short loc_18000F15D
0x18000f131  lea     rcx, [rdx+20h]
0x18000f135  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18000f13a  mov     rcx, r10
0x18000f13d  mov     r8, rax
0x18000f140  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18000f145  mov     r9, [rdx+30h]
0x18000f149  mov     rcx, rax
0x18000f14c  mov     rdx, [r10+10h]
0x18000f150  call    ??$_Traits_compare@U?$char_traits@D@std@@@std@@YAHQEBD_K01@Z; std::_Traits_compare<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x18000f155  test    eax, eax
0x18000f157  js      short loc_18000F15D
0x18000f159  mov     al, 1
0x18000f15b  jmp     short loc_18000F15F
0x18000f15d  xor     al, al
0x18000f15f  add     rsp, 28h
0x18000f163  retn
```
