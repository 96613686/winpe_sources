# PCLmWriter::StreamObject::_IsStreamObjectDictionaryKey(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180019fbc`
- end: `0x18001a0e0`
- name: `?_IsStreamObjectDictionaryKey@StreamObject@PCLmWriter@@AEBA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800199e0`

## callees

- `0x18000f16c`
- `0x180010618`
- `0x180019fbc`

## pseudocode

```c
bool __fastcall PCLmWriter::StreamObject::_IsStreamObjectDictionaryKey(__int64 a1, __int64 a2)
{
  const void *v3; // rax
  __int64 v4; // rdx
  const void *v5; // rax
  const void *v6; // rax
  const void *v7; // rax
  const void *v8; // rax
  const void *v9; // rax
  const void *v10; // rax
  bool result; // al

  v3 = (const void *)std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
  result = 1;
  if ( std::_Traits_compare<std::char_traits<char>>(v3, *(_QWORD *)(v4 + 16), "/Length", 7u) )
  {
    v5 = (const void *)std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
    if ( std::_Traits_compare<std::char_traits<char>>(v5, *(_QWORD *)(a2 + 16), "/Filter", 7u) )
    {
      v6 = (const void *)std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
      if ( std::_Traits_compare<std::char_traits<char>>(v6, *(_QWORD *)(a2 + 16), "/DecodeParms", 0xCu) )
      {
        v7 = (const void *)std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
        if ( std::_Traits_compare<std::char_traits<char>>(v7, *(_QWORD *)(a2 + 16), "/F", 2u) )
        {
          v8 = (const void *)std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
          if ( std::_Traits_compare<std::char_traits<char>>(v8, *(_QWORD *)(a2 + 16), "/FFilter", 8u) )
          {
            v9 = (const void *)std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
            if ( std::_Traits_compare<std::char_traits<char>>(v9, *(_QWORD *)(a2 + 16), "/FDecodeParms", 0xDu) )
            {
              v10 = (const void *)std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
              if ( std::_Traits_compare<std::char_traits<char>>(v10, *(_QWORD *)(a2 + 16), "/DL", 3u) )
                return 0;
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180019fbc  push    rbx
0x180019fbe  sub     rsp, 20h
0x180019fc2  mov     rcx, rdx
0x180019fc5  mov     rbx, rdx
0x180019fc8  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180019fcd  mov     rdx, [rdx+10h]
0x180019fd1  lea     r8, aLength; "/Length"
0x180019fd8  mov     rcx, rax
0x180019fdb  mov     r9d, 7
0x180019fe1  call    ??$_Traits_compare@U?$char_traits@D@std@@@std@@YAHQEBD_K01@Z; std::_Traits_compare<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x180019fe6  test    eax, eax
0x180019fe8  jz      loc_18001A0D8
0x180019fee  mov     rcx, rbx
0x180019ff1  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180019ff6  mov     rdx, [rbx+10h]
0x180019ffa  lea     r8, aFilter; "/Filter"
0x18001a001  mov     rcx, rax
0x18001a004  mov     r9d, 7
0x18001a00a  call    ??$_Traits_compare@U?$char_traits@D@std@@@std@@YAHQEBD_K01@Z; std::_Traits_compare<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x18001a00f  test    eax, eax
0x18001a011  jz      loc_18001A0D8
0x18001a017  mov     rcx, rbx
0x18001a01a  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18001a01f  mov     rdx, [rbx+10h]
0x18001a023  lea     r8, aDecodeparms; "/DecodeParms"
0x18001a02a  mov     rcx, rax
0x18001a02d  mov     r9d, 0Ch
0x18001a033  call    ??$_Traits_compare@U?$char_traits@D@std@@@std@@YAHQEBD_K01@Z; std::_Traits_compare<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x18001a038  test    eax, eax
0x18001a03a  jz      loc_18001A0D8
0x18001a040  mov     rcx, rbx
0x18001a043  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18001a048  mov     rdx, [rbx+10h]
0x18001a04c  lea     r8, asc_180025908; "/F"
0x18001a053  mov     rcx, rax
0x18001a056  mov     r9d, 2
0x18001a05c  call    ??$_Traits_compare@U?$char_traits@D@std@@@std@@YAHQEBD_K01@Z; std::_Traits_compare<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x18001a061  test    eax, eax
0x18001a063  jz      short loc_18001A0D8
0x18001a065  mov     rcx, rbx
0x18001a068  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18001a06d  mov     rdx, [rbx+10h]
0x18001a071  lea     r8, aFfilter; "/FFilter"
0x18001a078  mov     rcx, rax
0x18001a07b  mov     r9d, 8
0x18001a081  call    ??$_Traits_compare@U?$char_traits@D@std@@@std@@YAHQEBD_K01@Z; std::_Traits_compare<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x18001a086  test    eax, eax
0x18001a088  jz      short loc_18001A0D8
0x18001a08a  mov     rcx, rbx
0x18001a08d  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18001a092  mov     rdx, [rbx+10h]
0x18001a096  lea     r8, aFdecodeparms; "/FDecodeParms"
0x18001a09d  mov     rcx, rax
0x18001a0a0  mov     r9d, 0Dh
0x18001a0a6  call    ??$_Traits_compare@U?$char_traits@D@std@@@std@@YAHQEBD_K01@Z; std::_Traits_compare<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x18001a0ab  test    eax, eax
0x18001a0ad  jz      short loc_18001A0D8
0x18001a0af  mov     rcx, rbx
0x18001a0b2  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18001a0b7  mov     rdx, [rbx+10h]
0x18001a0bb  lea     r8, aDl; "/DL"
0x18001a0c2  mov     rcx, rax
0x18001a0c5  mov     r9d, 3
0x18001a0cb  call    ??$_Traits_compare@U?$char_traits@D@std@@@std@@YAHQEBD_K01@Z; std::_Traits_compare<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x18001a0d0  test    eax, eax
0x18001a0d2  jz      short loc_18001A0D8
0x18001a0d4  xor     al, al
0x18001a0d6  jmp     short loc_18001A0DA
0x18001a0d8  mov     al, 1
0x18001a0da  add     rsp, 20h
0x18001a0de  pop     rbx
0x18001a0df  retn
```
