# std::_Tree<std::_Tmap_traits<StringCheckedPtr,uint,StringCheckedPtr::LessThan,std::allocator<std::pair<StringCheckedPtr const,uint>>,0>>::_Emplace<std::pair<StringCheckedPtr,uint>>(std::pair<StringCheckedPtr,uint> &&)

- ea: `0x1800506b0`
- end: `0x18005083b`
- name: `??$_Emplace@U?$pair@VStringCheckedPtr@@I@std@@@?$_Tree@V?$_Tmap_traits@VStringCheckedPtr@@IULessThan@1@V?$allocator@U?$pair@$$CBVStringCheckedPtr@@I@std@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVStringCheckedPtr@@I@std@@PEAX@std@@_N@1@$$QEAU?$pair@VStringCheckedPtr@@I@1@@Z`
- size: `395`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004ffdc`

## callees

- `0x180008a20`
- `0x1800506b0`
- `0x180051860`
- `0x18009df80`
- `0x18009e420`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180050834`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180050834`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005072f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005072f`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<StringCheckedPtr,unsigned int,StringCheckedPtr::LessThan,std::allocator<std::pair<StringCheckedPtr const,unsigned int>>,0>>::_Emplace<std::pair<StringCheckedPtr,unsigned int>>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 *v6; // rdi
  __int64 *v7; // r12
  unsigned int v8; // ebp
  __int64 *i; // rbx
  const WCHAR *lpString2; // rax
  const WCHAR *v11; // r8
  unsigned int cchCount2; // ecx
  unsigned int v13; // r9d
  __int64 *v14; // rbx
  _OWORD *v15; // rax
  __int64 *v17; // [rsp+30h] [rbp-38h] BYREF
  _OWORD *v18; // [rsp+38h] [rbp-30h]

  v6 = (__int64 *)*a1;
  v7 = *(__int64 **)(*a1 + 8);
  v8 = 0;
  for ( i = v7; !*((_BYTE *)i + 25); i = (__int64 *)*i )
  {
    v7 = i;
    lpString2 = *(const WCHAR **)a3;
    v11 = (const WCHAR *)i[4];
    if ( v11 )
    {
      if ( lpString2 )
      {
        cchCount2 = *(_DWORD *)(a3 + 8);
        if ( cchCount2 > 0x7FFFFFFF || (v13 = *((_DWORD *)i + 10), v13 > 0x7FFFFFFF) )
          SafeIntExceptionHandler<Exception>::SafeIntOnOverflow();
        if ( CompareStringW(0x7Fu, 1u, v11, v13, lpString2, cchCount2) - 2 < 0 )
        {
LABEL_9:
          v8 = 0;
          i += 2;
          continue;
        }
      }
    }
    else if ( lpString2 )
    {
      goto LABEL_9;
    }
    v8 = 1;
    v6 = i;
  }
  if ( *((_BYTE *)v6 + 25) || (unsigned __int8)StringCheckedPtr::LessThan::operator()(a1, a3, v6 + 4) )
  {
    if ( a1[1] == 0x492492492492492LL )
      std::_Xlength_error("map/set too long");
    v14 = (__int64 *)*a1;
    v17 = a1;
    v15 = std::_Allocate<16,std::_Default_allocate_traits>(0x38u);
    v18 = v15;
    v15[2] = *(_OWORD *)a3;
    *((_DWORD *)v15 + 12) = *(_DWORD *)(a3 + 16);
    *(_QWORD *)v15 = v14;
    *((_QWORD *)v15 + 1) = v14;
    *((_QWORD *)v15 + 2) = v14;
    *((_WORD *)v15 + 12) = 0;
    v17 = v7;
    v18 = (_OWORD *)v8;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<BasedStringPtr<FontStringsRegion,unsigned int>>>::_Insert_node(
                      a1,
                      &v17,
                      v15);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v6;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x1800506b0  mov     [rsp+arg_8], rbx
0x1800506b5  mov     [rsp+arg_10], rbp
0x1800506ba  push    rsi
0x1800506bb  push    rdi
0x1800506bc  push    r12
0x1800506be  push    r14
0x1800506c0  push    r15
0x1800506c2  sub     rsp, 40h
0x1800506c6  mov     r14, r8
0x1800506c9  mov     rsi, rdx
0x1800506cc  mov     r15, rcx
0x1800506cf  mov     rdi, [rcx]
0x1800506d2  mov     r12, [rdi+8]
0x1800506d6  xor     ebp, ebp
0x1800506d8  xor     eax, eax
0x1800506da  mov     [rsp+68h+arg_0], rax
0x1800506df  mov     rbx, r12
0x1800506e2  cmp     [r12+19h], al
0x1800506e7  jnz     short loc_180050758
0x1800506e9  mov     r12, rbx
0x1800506ec  mov     rax, [r14]
0x1800506ef  mov     r8, [rbx+20h]; lpString1
0x1800506f3  test    r8, r8
0x1800506f6  jz      short loc_180050744
0x1800506f8  test    rax, rax
0x1800506fb  jz      short loc_18005073A
0x1800506fd  mov     ecx, [r14+8]
0x180050701  cmp     ecx, 7FFFFFFFh
0x180050707  ja      loc_18005081E
0x18005070d  mov     r9d, [rbx+28h]; cchCount1
0x180050711  cmp     r9d, 7FFFFFFFh
0x180050718  ja      loc_18005081E
0x18005071e  mov     [rsp+68h+cchCount2], ecx; cchCount2
0x180050722  mov     [rsp+68h+lpString2], rax; lpString2
0x180050727  mov     edx, 1; dwCmpFlags
0x18005072c  lea     ecx, [rdx+7Eh]; Locale
0x18005072f  call    cs:__imp_CompareStringW
0x180050735  add     eax, 0FFFFFFFEh
0x180050738  js      short loc_180050749
0x18005073a  mov     ebp, 1
0x18005073f  mov     rdi, rbx
0x180050742  jmp     short loc_18005074F
0x180050744  test    rax, rax
0x180050747  jz      short loc_18005073A
0x180050749  xor     ebp, ebp
0x18005074b  add     rbx, 10h
0x18005074f  mov     rbx, [rbx]
0x180050752  cmp     byte ptr [rbx+19h], 0
0x180050756  jz      short loc_1800506E9
0x180050758  cmp     byte ptr [rdi+19h], 0
0x18005075c  jnz     short loc_180050772
0x18005075e  lea     r8, [rdi+20h]
0x180050762  mov     rdx, r14
0x180050765  call    ??RLessThan@StringCheckedPtr@@QEBA_NAEBV?$CheckedPtr@$$CB_WV?$FailAsExceptionPolicy@VInvalidCacheDataException@@@@I@@0@Z; StringCheckedPtr::LessThan::operator()(CheckedPtr<wchar_t const,FailAsExceptionPolicy<InvalidCacheDataException>,uint> const &,CheckedPtr<wchar_t const,FailAsExceptionPolicy<InvalidCacheDataException>,uint> const &)
0x18005076a  test    al, al
0x18005076c  jz      loc_180050824
0x180050772  mov     rax, 492492492492492h
0x18005077c  cmp     [r15+8], rax
0x180050780  jz      loc_18005082D
0x180050786  mov     rbx, [r15]
0x180050789  mov     [rsp+68h+var_38], r15
0x18005078e  mov     [rsp+68h+var_30], 0
0x180050797  mov     [rsp+68h+var_30], 0
0x1800507a0  mov     ecx, 38h ; '8'
0x1800507a5  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800507aa  mov     [rsp+68h+var_30], rax
0x1800507af  movups  xmm0, xmmword ptr [r14]
0x1800507b3  movdqu  xmmword ptr [rax+20h], xmm0
0x1800507b8  mov     ecx, [r14+10h]
0x1800507bc  mov     [rax+30h], ecx
0x1800507bf  mov     [rax], rbx
0x1800507c2  mov     [rax+8], rbx
0x1800507c6  mov     [rax+10h], rbx
0x1800507ca  mov     word ptr [rax+18h], 0
0x1800507d0  mov     [rsp+68h+var_30], 0
0x1800507d9  mov     [rsp+68h+var_38], r12
0x1800507de  mov     dword ptr [rsp+68h+var_30], ebp
0x1800507e2  mov     rcx, [rsp+68h+arg_0]
0x1800507e7  mov     dword ptr [rsp+68h+var_30+4], ecx
0x1800507eb  mov     r8, rax
0x1800507ee  lea     rdx, [rsp+68h+var_38]
0x1800507f3  mov     rcx, r15
0x1800507f6  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@V?$BasedStringPtr@VFontStringsRegion@@I@@@std@@@std@@QEAAPEAU?$_Tree_node@V?$BasedStringPtr@VFontStringsRegion@@I@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@V?$BasedStringPtr@VFontStringsRegion@@I@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<BasedStringPtr<FontStringsRegion,uint>>>::_Insert_node(std::_Tree_id<std::_Tree_node<BasedStringPtr<FontStringsRegion,uint>,void *> *>,std::_Tree_node<BasedStringPtr<FontStringsRegion,uint>,void *> * const)
0x1800507fb  mov     [rsi], rax
0x1800507fe  mov     byte ptr [rsi+8], 1
0x180050802  mov     rax, rsi
0x180050805  lea     r11, [rsp+68h+var_28]
0x18005080a  mov     rbx, [r11+38h]
0x18005080e  mov     rbp, [r11+40h]
0x180050812  mov     rsp, r11
0x180050815  pop     r15
0x180050817  pop     r14
0x180050819  pop     r12
0x18005081b  pop     rdi
0x18005081c  pop     rsi
0x18005081d  retn
0x18005081e  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
0x180050824  mov     [rsi], rdi
0x180050827  mov     byte ptr [rsi+8], 0
0x18005082b  jmp     short loc_180050802
0x18005082d  lea     rcx, aMapSetTooLong; "map/set too long"
0x180050834  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
