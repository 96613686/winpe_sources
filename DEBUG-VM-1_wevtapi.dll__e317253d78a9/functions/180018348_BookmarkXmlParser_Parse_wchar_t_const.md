# BookmarkXmlParser::Parse(wchar_t const *)

- ea: `0x180018348`
- end: `0x180018460`
- name: `?Parse@BookmarkXmlParser@@AEAAXPEB_W@Z`
- size: `280`
- prototype: `void __fastcall(BookmarkXmlParser *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800182f0`

## callees

- `0x18000a4b4`
- `0x180018348`
- `0x180018468`
- `0x180018d70`
- `0x1800210b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall BookmarkXmlParser::Parse(BookmarkXmlParser *this, const wchar_t *a2)
{
  __int64 v3; // rax
  unsigned int Token; // ebx
  unsigned __int64 v5; // rdx
  const wchar_t *v6; // r9
  unsigned int i; // ecx
  __int64 v8; // r8
  unsigned __int64 v9; // rax
  const wchar_t *v10; // [rsp+20h] [rbp-29h] BYREF
  unsigned __int64 v11; // [rsp+28h] [rbp-21h]
  _BYTE v12[32]; // [rsp+30h] [rbp-19h] BYREF
  __int64 v13; // [rsp+50h] [rbp+7h]
  unsigned __int64 v14; // [rsp+58h] [rbp+Fh]
  unsigned int v15; // [rsp+68h] [rbp+1Fh]
  unsigned int v16; // [rsp+6Ch] [rbp+23h]

  v3 = -1;
  do
    ++v3;
  while ( a2[v3] );
  v10 = a2;
  v11 = v3;
  WevtXMLParser::WevtXMLParser(v12, &v10);
  do
  {
    while ( 1 )
    {
      Token = WevtXMLParser::NextToken((__int64)v12);
      if ( v15 == -1 )
      {
        v6 = 0;
        v5 = 0;
      }
      else
      {
        if ( v15 > v14 )
          __int2c();
        v5 = v14 - v15;
        v6 = (const wchar_t *)(v13 + 2LL * v15);
        if ( v5 >= v16 )
          v5 = v16;
      }
      if ( (_BYTE)Token != 7 )
        break;
      for ( i = 0; i < v5; ++i )
      {
        if ( v6[i] > 0x20u )
          break;
        v8 = 0x100002600LL;
        if ( !_bittest64(&v8, v6[i]) )
          break;
      }
      if ( i != v5 )
      {
        if ( i > v5 )
          __int2c();
        v9 = v5 - i;
        v5 = -1;
        if ( v9 != -1 )
          v5 = v9;
        v6 += i;
        break;
      }
    }
    v10 = v6;
    v11 = v5;
    BookmarkXmlParser::DoTransition((__int64)this, Token, &v10);
  }
  while ( (_BYTE)Token != 15 );
  utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(v12);
}

```

## disassembly

```asm
0x180018348  push    rbp
0x18001834a  push    rbx
0x18001834b  push    rsi
0x18001834c  push    rdi
0x18001834d  lea     rbp, [rsp-3Fh]
0x180018352  sub     rsp, 88h
0x180018359  mov     rdi, rcx
0x18001835c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018360  xor     esi, esi
0x180018362  inc     rax
0x180018365  cmp     [rdx+rax*2], si
0x180018369  jnz     short loc_180018362
0x18001836b  mov     [rbp+57h+var_80], rdx
0x18001836f  mov     [rbp+57h+var_78], rax
0x180018373  lea     rdx, [rbp+57h+var_80]
0x180018377  lea     rcx, [rbp+57h+var_70]
0x18001837b  call    ??0WevtXMLParser@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; WevtXMLParser::WevtXMLParser(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x180018380  nop
0x180018381  lea     rcx, [rbp+57h+var_70]
0x180018385  call    ?NextToken@WevtXMLParser@@QEAA?AW4XmlTokenType@@XZ; WevtXMLParser::NextToken(void)
0x18001838a  movzx   ebx, al
0x18001838d  cmp     [rbp+57h+var_38], 0FFFFFFFFh
0x180018391  jz      loc_180018449
0x180018397  mov     rdx, [rbp+57h+var_48]
0x18001839b  mov     r8d, [rbp+57h+var_38]
0x18001839f  cmp     r8, rdx
0x1800183a2  ja      loc_180018454
0x1800183a8  sub     rdx, r8
0x1800183ab  mov     ecx, [rbp+57h+var_34]
0x1800183ae  mov     rax, [rbp+57h+var_50]
0x1800183b2  lea     r9, [rax+r8*2]
0x1800183b6  cmp     rdx, rcx
0x1800183b9  cmovnb  rdx, rcx
0x1800183bd  cmp     bl, 7
0x1800183c0  jz      short loc_1800183F2
0x1800183c2  mov     [rbp+57h+var_80], r9
0x1800183c6  mov     [rbp+57h+var_78], rdx
0x1800183ca  mov     edx, ebx
0x1800183cc  lea     r8, [rbp+57h+var_80]
0x1800183d0  mov     rcx, rdi
0x1800183d3  call    ?DoTransition@BookmarkXmlParser@@EEAADHV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; BookmarkXmlParser::DoTransition(int,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x1800183d8  cmp     bl, 0Fh
0x1800183db  jnz     short loc_180018381
0x1800183dd  lea     rcx, [rbp+57h+var_70]
0x1800183e1  call    ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
0x1800183e6  add     rsp, 88h
0x1800183ed  pop     rdi
0x1800183ee  pop     rsi
0x1800183ef  pop     rbx
0x1800183f0  pop     rbp
0x1800183f1  retn
0x1800183f2  mov     ecx, esi
0x1800183f4  test    rdx, rdx
0x1800183f7  jz      short loc_180018421
0x1800183f9  mov     eax, ecx
0x1800183fb  cmp     word ptr [r9+rax*2], 20h ; ' '
0x180018401  ja      short loc_180018421
0x180018403  movzx   eax, word ptr [r9+rax*2]
0x180018408  mov     r8, 100002600h
0x180018412  bt      r8, rax
0x180018416  jnb     short loc_180018421
0x180018418  inc     ecx
0x18001841a  mov     eax, ecx
0x18001841c  cmp     rax, rdx
0x18001841f  jb      short loc_1800183F9
0x180018421  mov     r8d, ecx
0x180018424  cmp     r8, rdx
0x180018427  jz      loc_180018381
0x18001842d  ja      short loc_18001845B
0x18001842f  sub     rdx, r8
0x180018432  mov     rax, rdx
0x180018435  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180018439  cmp     rax, rdx
0x18001843c  cmovb   rdx, rax
0x180018440  lea     r9, [r9+r8*2]
0x180018444  jmp     loc_1800183C2
0x180018449  mov     r9, rsi
0x18001844c  mov     rdx, rsi
0x18001844f  jmp     loc_1800183BD
0x180018454  int     2Ch; Windows NT - assertion failure
0x180018456  jmp     loc_1800183A8
0x18001845b  int     2Ch; Windows NT - assertion failure
0x18001845d  jmp     short loc_18001842F
```
