# PCLmWriter::PDFDocumentWriter::_IgnoreTrailerEntry(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x18001660c`
- end: `0x1800166fb`
- name: `?_IgnoreTrailerEntry@PDFDocumentWriter@PCLmWriter@@AEAA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016580`

## callees

- `0x18000f16c`
- `0x180010618`
- `0x18001660c`

## pseudocode

```c
bool __fastcall PCLmWriter::PDFDocumentWriter::_IgnoreTrailerEntry(__int64 a1, __int64 a2)
{
  const void *v3; // rax
  __int64 v4; // rdx
  const void *v5; // rax
  size_t v6; // r9
  const char *v7; // r8
  const void *v8; // rax
  __int64 v9; // rdx
  const void *v10; // rax
  const void *v11; // rax

  if ( *(_BYTE *)(a1 + 36) )
  {
    v3 = (const void *)std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
    if ( !std::_Traits_compare<std::char_traits<char>>(v3, *(_QWORD *)(v4 + 16), "/Prev", 5u) )
      return 1;
    v5 = (const void *)std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
    v6 = 5;
    v7 = "/Size";
  }
  else
  {
    v8 = (const void *)std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
    if ( !std::_Traits_compare<std::char_traits<char>>(v8, *(_QWORD *)(v9 + 16), "/Prev", 5u) )
      return 1;
    v10 = (const void *)std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
    if ( !std::_Traits_compare<std::char_traits<char>>(v10, *(_QWORD *)(a2 + 16), "/Size", 5u) )
      return 1;
    v11 = (const void *)std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
    if ( !std::_Traits_compare<std::char_traits<char>>(v11, *(_QWORD *)(a2 + 16), "/Index", 6u) )
      return 1;
    v5 = (const void *)std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
    v6 = 2;
    v7 = "/W";
  }
  return !std::_Traits_compare<std::char_traits<char>>(v5, *(_QWORD *)(a2 + 16), v7, v6);
}

```

## disassembly

```asm
0x18001660c  mov     [rsp+arg_0], rbx
0x180016611  push    rsi
0x180016612  sub     rsp, 20h
0x180016616  cmp     byte ptr [rcx+24h], 0
0x18001661a  mov     rbx, rdx
0x18001661d  mov     rcx, rdx
0x180016620  jz      short loc_18001665E
0x180016622  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180016627  mov     rdx, [rdx+10h]
0x18001662b  lea     r8, aPrev; "/Prev"
0x180016632  mov     esi, 5
0x180016637  mov     rcx, rax
0x18001663a  mov     r9d, esi
0x18001663d  call    ??$_Traits_compare@U?$char_traits@D@std@@@std@@YAHQEBD_K01@Z; std::_Traits_compare<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x180016642  test    eax, eax
0x180016644  jz      loc_1800166EE
0x18001664a  mov     rcx, rbx
0x18001664d  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180016652  mov     r9d, esi
0x180016655  lea     r8, aSize; "/Size"
0x18001665c  jmp     short loc_1800166DA
0x18001665e  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180016663  mov     rdx, [rdx+10h]
0x180016667  lea     r8, aPrev; "/Prev"
0x18001666e  mov     esi, 5
0x180016673  mov     rcx, rax
0x180016676  mov     r9d, esi
0x180016679  call    ??$_Traits_compare@U?$char_traits@D@std@@@std@@YAHQEBD_K01@Z; std::_Traits_compare<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x18001667e  test    eax, eax
0x180016680  jz      short loc_1800166EE
0x180016682  mov     rcx, rbx
0x180016685  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18001668a  mov     rdx, [rbx+10h]
0x18001668e  lea     r8, aSize; "/Size"
0x180016695  mov     rcx, rax
0x180016698  mov     r9d, esi
0x18001669b  call    ??$_Traits_compare@U?$char_traits@D@std@@@std@@YAHQEBD_K01@Z; std::_Traits_compare<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x1800166a0  test    eax, eax
0x1800166a2  jz      short loc_1800166EE
0x1800166a4  mov     rcx, rbx
0x1800166a7  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800166ac  mov     rdx, [rbx+10h]
0x1800166b0  lea     r9d, [rsi+1]
0x1800166b4  mov     rcx, rax
0x1800166b7  lea     r8, aIndex; "/Index"
0x1800166be  call    ??$_Traits_compare@U?$char_traits@D@std@@@std@@YAHQEBD_K01@Z; std::_Traits_compare<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x1800166c3  test    eax, eax
0x1800166c5  jz      short loc_1800166EE
0x1800166c7  mov     rcx, rbx
0x1800166ca  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800166cf  lea     r9d, [rsi-3]
0x1800166d3  lea     r8, aW; "/W"
0x1800166da  mov     rdx, [rbx+10h]
0x1800166de  mov     rcx, rax
0x1800166e1  call    ??$_Traits_compare@U?$char_traits@D@std@@@std@@YAHQEBD_K01@Z; std::_Traits_compare<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x1800166e6  test    eax, eax
0x1800166e8  jz      short loc_1800166EE
0x1800166ea  xor     al, al
0x1800166ec  jmp     short loc_1800166F0
0x1800166ee  mov     al, 1
0x1800166f0  mov     rbx, [rsp+28h+arg_0]
0x1800166f5  add     rsp, 20h
0x1800166f9  pop     rsi
0x1800166fa  retn
```
