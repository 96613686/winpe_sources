# WevtXMLParser::NextToken(void)

- ea: `0x180018468`
- end: `0x180018ab8`
- name: `?NextToken@WevtXMLParser@@QEAA?AW4XmlTokenType@@XZ`
- size: `1616`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180018348`
- `0x18002eb48`

## callees

- `0x180018468`
- `0x180018ac0`
- `0x180019434`
- `0x18001d000`
- `0x180020f3c`
- `0x180023548`
- `0x180023890`
- `0x1800303d0`
- `0x180038fb4`

## pseudocode

```c
unsigned __int8 __fastcall WevtXMLParser::NextToken(__int64 a1)
{
  __int64 v2; // rbx
  unsigned __int8 Token; // al
  unsigned __int8 v4; // si
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rbx
  __int64 v9; // rax
  unsigned __int64 v11; // rbx
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdx
  _WORD *i; // r11
  __int128 v17; // xmm0
  __int64 v18; // r10
  __int128 v19; // [rsp+20h] [rbp-50h] BYREF
  __int128 v20; // [rsp+30h] [rbp-40h] BYREF
  __int128 pExceptionObject; // [rsp+40h] [rbp-30h] BYREF
  __int64 v22; // [rsp+50h] [rbp-20h]
  int v23; // [rsp+58h] [rbp-18h]
  int v24; // [rsp+5Ch] [rbp-14h]
  int v25; // [rsp+60h] [rbp-10h]

  v2 = a1 + 24;
  while ( 1 )
  {
    do
    {
      Token = GenericLexer::NextToken(v2);
      v4 = Token;
    }
    while ( Token == 8 );
    if ( Token <= 8u )
    {
      switch ( Token )
      {
        case 1u:
          v11 = 0;
          if ( *(_DWORD *)(a1 + 68) )
          {
            if ( *(_DWORD *)(a1 + 68) == 2 )
            {
              if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_D(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  10,
                  &WPP_9505920f77393fcf48438baec2ee0d5b_Traceguids,
                  15008);
              }
              v22 = 0;
              v23 = 15008;
              v24 = -1;
              pExceptionObject = 0;
              v25 = 29;
              throw (EvtException *)&pExceptionObject;
            }
          }
          else
          {
            *(_DWORD *)(a1 + 68) = 1;
          }
          ++*(_DWORD *)(a1 + 64);
          if ( *(_DWORD *)(a1 + 56) == -1 )
          {
            v14 = 0;
          }
          else
          {
            v12 = *(_QWORD *)(a1 + 40);
            v13 = *(unsigned int *)(a1 + 56);
            if ( v13 > v12 )
              __int2c();
            v11 = v12 - v13;
            if ( v11 >= *(unsigned int *)(a1 + 60) )
              v11 = *(unsigned int *)(a1 + 60);
            v14 = *(_QWORD *)(a1 + 32) + 2 * v13;
          }
          *(_QWORD *)&v19 = v14;
          *((_QWORD *)&v19 + 1) = v11;
          WevtXMLParser::OpenStartElementTag(a1, &v19);
          return v4;
        case 2u:
          if ( *(_DWORD *)(a1 + 56) == -1 )
          {
            v8 = 0;
            v9 = 0;
          }
          else
          {
            v6 = *(_QWORD *)(a1 + 40);
            v7 = *(unsigned int *)(a1 + 56);
            if ( v7 > v6 )
              __int2c();
            v8 = v6 - v7;
            if ( v8 >= *(unsigned int *)(a1 + 60) )
              v8 = *(unsigned int *)(a1 + 60);
            v9 = *(_QWORD *)(a1 + 32) + 2 * v7;
          }
          *(_QWORD *)&v19 = v9;
          *((_QWORD *)&v19 + 1) = v8;
          WevtXMLParser::EndElementTag((WevtXMLParser *)a1);
          break;
        case 3u:
          return v4;
        case 4u:
          WevtXMLParser::EndCurrentElement((WevtXMLParser *)a1);
          break;
        case 5u:
        case 6u:
          return v4;
        case 7u:
          if ( *(_DWORD *)(a1 + 68) != 1 )
          {
            GenericLexer::GetTokenText(v2, &v19);
            for ( i = (_WORD *)v19; i != (_WORD *)(v19 + 2LL * *((_QWORD *)&v19 + 1)); ++i )
            {
              if ( *i <= 0x20u )
              {
                v15 = 0x100002600LL;
                if ( _bittest64(&v15, (unsigned __int16)*i) )
                  continue;
              }
              if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_D(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  12,
                  &WPP_9505920f77393fcf48438baec2ee0d5b_Traceguids,
                  15008);
              }
              v23 = 15008;
              v24 = -1;
              v22 = 0;
              v25 = 100;
              pExceptionObject = 0;
              throw (EvtException *)&pExceptionObject;
            }
          }
          return v4;
        default:
          goto LABEL_65;
      }
      if ( (*(_DWORD *)(a1 + 64))-- == 1 )
        *(_DWORD *)(a1 + 68) = 2;
      return v4;
    }
    if ( Token == 9 )
      break;
    if ( Token == 11 )
    {
      if ( *(_DWORD *)(a1 + 68) != 1 )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_9505920f77393fcf48438baec2ee0d5b_Traceguids, 15008);
        }
        v23 = 15008;
        v24 = -1;
        v22 = 0;
        v25 = 122;
        pExceptionObject = 0;
        throw (EvtException *)&pExceptionObject;
      }
      GenericLexer::GetTokenText(v2, &v19);
      v17 = v19;
      *(_QWORD *)&v19 = L"gt";
      *((_QWORD *)&v19 + 1) = 2;
      v20 = v17;
      if ( (unsigned __int8)utl::operator!=<wchar_t,utl::char_traits<wchar_t>>(&v20, &v19) )
      {
        *((_QWORD *)&v19 + 1) = 2;
        *(_QWORD *)&v19 = L"lt";
        v20 = v17;
        if ( (unsigned __int8)utl::operator!=<wchar_t,utl::char_traits<wchar_t>>(&v20, &v19) )
        {
          *((_QWORD *)&v19 + 1) = 3;
          *(_QWORD *)&v19 = L"amp";
          v20 = v17;
          if ( (unsigned __int8)utl::operator!=<wchar_t,utl::char_traits<wchar_t>>(&v20, &v19) )
          {
            v20 = v17;
            *(_QWORD *)&v19 = L"apos";
            *((_QWORD *)&v19 + 1) = 4;
            if ( (unsigned __int8)utl::operator!=<wchar_t,utl::char_traits<wchar_t>>(&v20, &v19) )
            {
              *((_QWORD *)&v19 + 1) = v18;
              *(_QWORD *)&v19 = L"quot";
              v20 = v17;
              if ( (unsigned __int8)utl::operator!=<wchar_t,utl::char_traits<wchar_t>>(&v20, &v19) )
              {
                if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_D(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    15,
                    &WPP_9505920f77393fcf48438baec2ee0d5b_Traceguids,
                    15008);
                }
                v22 = 0;
                v23 = 15008;
                v24 = -1;
                pExceptionObject = 0;
                v25 = 133;
                throw (EvtException *)&pExceptionObject;
              }
            }
          }
        }
      }
      return v4;
    }
    if ( Token == 12 )
    {
      if ( *(_DWORD *)(a1 + 68) != 1 )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_9505920f77393fcf48438baec2ee0d5b_Traceguids, 15008);
        }
        v23 = 15008;
        v24 = -1;
        v22 = 0;
        v25 = 113;
        pExceptionObject = 0;
        throw (EvtException *)&pExceptionObject;
      }
      return v4;
    }
    if ( Token != 13 && Token != 14 )
    {
      if ( Token == 15 )
      {
        if ( *(_DWORD *)(a1 + 68) != 2 )
        {
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_9505920f77393fcf48438baec2ee0d5b_Traceguids, 15008);
          }
          v23 = 15008;
          v24 = -1;
          v22 = 0;
          v25 = 141;
          pExceptionObject = 0;
          throw (EvtException *)&pExceptionObject;
        }
        return v4;
      }
LABEL_65:
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_9505920f77393fcf48438baec2ee0d5b_Traceguids, 15008);
      }
      v23 = 15008;
      v24 = -1;
      v22 = 0;
      v25 = 147;
      pExceptionObject = 0;
      throw (EvtException *)&pExceptionObject;
    }
    if ( *(_DWORD *)(a1 + 68) == 1 )
      return v4;
  }
  if ( *(_DWORD *)(a1 + 68) != 1 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_9505920f77393fcf48438baec2ee0d5b_Traceguids, 15008);
    }
    v23 = 15008;
    v24 = -1;
    v22 = 0;
    v25 = 63;
    pExceptionObject = 0;
    throw (EvtException *)&pExceptionObject;
  }
  return v4;
}

```

## disassembly

```asm
0x180018468  mov     [rsp-18h+arg_8], rbx
0x18001846d  mov     [rsp-18h+arg_10], rsi
0x180018472  push    rbp
0x180018473  push    rdi
0x180018474  push    r14
0x180018476  mov     rbp, rsp
0x180018479  sub     rsp, 70h
0x18001847d  mov     rdi, rcx
0x180018480  lea     rbx, [rcx+18h]
0x180018484  mov     r14d, 2
0x18001848a  mov     rcx, rbx
0x18001848d  call    ?NextToken@GenericLexer@@QEAA?AW4XmlTokenType@@XZ; GenericLexer::NextToken(void)
0x180018492  movzx   esi, al
0x180018495  mov     ecx, esi
0x180018497  cmp     sil, 8
0x18001849b  jz      short loc_18001848A
0x18001849d  ja      loc_180018542
0x1800184a3  sub     ecx, 1
0x1800184a6  jz      loc_1800185EE
0x1800184ac  sub     ecx, 1
0x1800184af  jz      short loc_1800184F3
0x1800184b1  sub     ecx, 1
0x1800184b4  jz      short loc_1800184DB
0x1800184b6  sub     ecx, 1
0x1800184b9  jz      loc_180018643
0x1800184bf  sub     ecx, 1
0x1800184c2  jz      short loc_1800184DB
0x1800184c4  sub     ecx, 1
0x1800184c7  jz      short loc_1800184DB
0x1800184c9  cmp     ecx, 1
0x1800184cc  jnz     loc_18001879B
0x1800184d2  cmp     [rdi+44h], ecx
0x1800184d5  jnz     loc_180018698
0x1800184db  lea     r11, [rsp+70h+var_s0]
0x1800184e0  mov     al, sil
0x1800184e3  mov     rbx, [r11+28h]
0x1800184e7  mov     rsi, [r11+30h]
0x1800184eb  mov     rsp, r11
0x1800184ee  pop     r14
0x1800184f0  pop     rdi
0x1800184f1  pop     rbp
0x1800184f2  retn
0x1800184f3  cmp     dword ptr [rdi+38h], 0FFFFFFFFh
0x1800184f7  jz      loc_180018650
0x1800184fd  mov     rbx, [rdi+28h]
0x180018501  mov     ecx, [rdi+38h]
0x180018504  mov     eax, [rdi+3Ch]
0x180018507  cmp     rcx, rbx
0x18001850a  ja      loc_18001865E
0x180018510  sub     rbx, rcx
0x180018513  cmp     rbx, rax
0x180018516  cmovnb  rbx, rax
0x18001851a  mov     rax, [rdi+20h]
0x18001851e  lea     rax, [rax+rcx*2]
0x180018522  lea     rdx, [rbp+var_50]
0x180018526  mov     qword ptr [rbp+var_50], rax
0x18001852a  mov     rcx, rdi; this
0x18001852d  mov     qword ptr [rbp+var_50+8], rbx
0x180018531  call    ?EndElementTag@WevtXMLParser@@AEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; WevtXMLParser::EndElementTag(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x180018536  add     dword ptr [rdi+40h], 0FFFFFFFFh
0x18001853a  jnz     short loc_1800184DB
0x18001853c  mov     [rdi+44h], r14d
0x180018540  jmp     short loc_1800184DB
0x180018542  sub     ecx, 9
0x180018545  jz      loc_180018A42
0x18001854b  sub     ecx, r14d
0x18001854e  jz      loc_18001887D
0x180018554  sub     ecx, 1
0x180018557  jz      loc_180018807
0x18001855d  sub     ecx, 1
0x180018560  jz      loc_180018689
0x180018566  sub     ecx, 1
0x180018569  jz      loc_180018689
0x18001856f  cmp     ecx, 1
0x180018572  jnz     loc_18001879B
0x180018578  cmp     [rdi+44h], r14d
0x18001857c  jz      loc_1800184DB
0x180018582  mov     rcx, cs:WPP_GLOBAL_Control
0x180018589  lea     rax, WPP_GLOBAL_Control
0x180018590  mov     edi, 3AA0h
0x180018595  cmp     rcx, rax
0x180018598  jz      short loc_1800185BE
0x18001859a  test    [rcx+1Ch], r14b
0x18001859e  jz      short loc_1800185BE
0x1800185a0  cmp     [rcx+19h], r14b
0x1800185a4  jb      short loc_1800185BE
0x1800185a6  mov     rcx, [rcx+10h]
0x1800185aa  lea     r8, WPP_9505920f77393fcf48438baec2ee0d5b_Traceguids
0x1800185b1  mov     edx, 10h
0x1800185b6  mov     r9d, edi
0x1800185b9  call    WPP_SF_D
0x1800185be  xorps   xmm0, xmm0
0x1800185c1  mov     [rbp+var_18], edi
0x1800185c4  xor     ebx, ebx
0x1800185c6  mov     [rbp+var_14], 0FFFFFFFFh
0x1800185cd  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800185d4  mov     [rbp+var_20], rbx
0x1800185d8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800185dc  mov     [rbp+var_10], 8Dh
0x1800185e3  movdqu  [rbp+pExceptionObject], xmm0
0x1800185e8  call    _CxxThrowException_0
0x1800185ee  xor     ebx, ebx
0x1800185f0  cmp     [rdi+44h], ebx
0x1800185f3  jnz     loc_180018727
0x1800185f9  mov     dword ptr [rdi+44h], 1
0x180018600  inc     dword ptr [rdi+40h]
0x180018603  cmp     dword ptr [rdi+38h], 0FFFFFFFFh
0x180018607  jz      short loc_180018659
0x180018609  mov     rbx, [rdi+28h]
0x18001860d  mov     ecx, [rdi+38h]
0x180018610  mov     eax, [rdi+3Ch]
0x180018613  cmp     rcx, rbx
0x180018616  ja      short loc_180018665
0x180018618  sub     rbx, rcx
0x18001861b  cmp     rbx, rax
0x18001861e  cmovnb  rbx, rax
0x180018622  mov     rax, [rdi+20h]
0x180018626  lea     rax, [rax+rcx*2]
0x18001862a  lea     rdx, [rbp+var_50]
0x18001862e  mov     qword ptr [rbp+var_50], rax
0x180018632  mov     rcx, rdi
0x180018635  mov     qword ptr [rbp+var_50+8], rbx
0x180018639  call    ?OpenStartElementTag@WevtXMLParser@@AEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; WevtXMLParser::OpenStartElementTag(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18001863e  jmp     loc_1800184DB
0x180018643  mov     rcx, rdi; this
0x180018646  call    ?EndCurrentElement@WevtXMLParser@@AEAAXXZ; WevtXMLParser::EndCurrentElement(void)
0x18001864b  jmp     loc_180018536
0x180018650  xor     ebx, ebx
0x180018652  mov     eax, ebx
0x180018654  jmp     loc_180018522
0x180018659  mov     rax, rbx
0x18001865c  jmp     short loc_18001862A
0x18001865e  int     2Ch; Windows NT - assertion failure
0x180018660  jmp     loc_180018510
0x180018665  int     2Ch; Windows NT - assertion failure
0x180018667  jmp     short loc_180018618
0x180018669  cmp     word ptr [r11], 20h ; ' '
0x18001866e  ja      short loc_1800186BB
0x180018670  movzx   ecx, word ptr [r11]
0x180018674  mov     rdx, 100002600h
0x18001867e  bt      rdx, rcx
0x180018682  jnb     short loc_1800186BB
0x180018684  add     r11, r14
0x180018687  jmp     short loc_1800186B0
0x180018689  cmp     dword ptr [rdi+44h], 1
0x18001868d  jnz     loc_18001848A
0x180018693  jmp     loc_1800184DB
0x180018698  lea     rdx, [rbp+var_50]
0x18001869c  mov     rcx, rbx
0x18001869f  call    ?GetTokenText@GenericLexer@@QEAA?AV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@XZ; GenericLexer::GetTokenText(void)
0x1800186a4  mov     rax, qword ptr [rbp+var_50+8]
0x1800186a8  mov     r11, qword ptr [rbp+var_50]
0x1800186ac  lea     rax, [r11+rax*2]
0x1800186b0  cmp     r11, rax
0x1800186b3  jz      loc_1800184DB
0x1800186b9  jmp     short loc_180018669
0x1800186bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800186c2  lea     rax, WPP_GLOBAL_Control
0x1800186c9  mov     edi, 3AA0h
0x1800186ce  cmp     rcx, rax
0x1800186d1  jz      short loc_1800186F7
0x1800186d3  test    [rcx+1Ch], r14b
0x1800186d7  jz      short loc_1800186F7
0x1800186d9  cmp     [rcx+19h], r14b
0x1800186dd  jb      short loc_1800186F7
0x1800186df  mov     rcx, [rcx+10h]
0x1800186e3  lea     r8, WPP_9505920f77393fcf48438baec2ee0d5b_Traceguids
0x1800186ea  mov     edx, 0Ch
0x1800186ef  mov     r9d, edi
0x1800186f2  call    WPP_SF_D
0x1800186f7  xorps   xmm0, xmm0
0x1800186fa  mov     [rbp+var_18], edi
0x1800186fd  xor     ebx, ebx
0x1800186ff  mov     [rbp+var_14], 0FFFFFFFFh
0x180018706  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001870d  mov     [rbp+var_20], rbx
0x180018711  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180018715  mov     [rbp+var_10], 64h ; 'd'
0x18001871c  movdqu  [rbp+pExceptionObject], xmm0
0x180018721  call    _CxxThrowException_0
0x180018727  cmp     [rdi+44h], r14d
0x18001872b  jnz     loc_180018600
0x180018731  mov     rcx, cs:WPP_GLOBAL_Control
0x180018738  lea     rax, WPP_GLOBAL_Control
0x18001873f  mov     edi, 3AA0h
0x180018744  cmp     rcx, rax
0x180018747  jz      short loc_18001876D
0x180018749  test    [rcx+1Ch], r14b
0x18001874d  jz      short loc_18001876D
0x18001874f  cmp     [rcx+19h], r14b
0x180018753  jb      short loc_18001876D
0x180018755  mov     rcx, [rcx+10h]
0x180018759  lea     r8, WPP_9505920f77393fcf48438baec2ee0d5b_Traceguids
0x180018760  mov     edx, 0Ah
0x180018765  mov     r9d, edi
0x180018768  call    WPP_SF_D
0x18001876d  xorps   xmm0, xmm0
0x180018770  mov     [rbp+var_20], rbx
0x180018774  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001877b  mov     [rbp+var_18], edi
0x18001877e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180018782  mov     [rbp+var_14], 0FFFFFFFFh
0x180018789  movdqu  [rbp+pExceptionObject], xmm0
0x18001878e  mov     [rbp+var_10], 1Dh
0x180018795  call    _CxxThrowException_0
0x18001879b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800187a2  lea     rax, WPP_GLOBAL_Control
0x1800187a9  mov     edi, 3AA0h
0x1800187ae  cmp     rcx, rax
0x1800187b1  jz      short loc_1800187D7
0x1800187b3  test    [rcx+1Ch], r14b
0x1800187b7  jz      short loc_1800187D7
0x1800187b9  cmp     [rcx+19h], r14b
0x1800187bd  jb      short loc_1800187D7
0x1800187bf  mov     rcx, [rcx+10h]
0x1800187c3  lea     r8, WPP_9505920f77393fcf48438baec2ee0d5b_Traceguids
0x1800187ca  mov     edx, 11h
0x1800187cf  mov     r9d, edi
0x1800187d2  call    WPP_SF_D
0x1800187d7  xorps   xmm0, xmm0
0x1800187da  mov     [rbp+var_18], edi
0x1800187dd  xor     ebx, ebx
0x1800187df  mov     [rbp+var_14], 0FFFFFFFFh
0x1800187e6  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800187ed  mov     [rbp+var_20], rbx
0x1800187f1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800187f5  mov     [rbp+var_10], 93h
0x1800187fc  movdqu  [rbp+pExceptionObject], xmm0
0x180018801  call    _CxxThrowException_0
0x180018807  cmp     dword ptr [rdi+44h], 1
0x18001880b  jz      loc_1800184DB
0x180018811  mov     rcx, cs:WPP_GLOBAL_Control
0x180018818  lea     rax, WPP_GLOBAL_Control
0x18001881f  mov     edi, 3AA0h
0x180018824  cmp     rcx, rax
0x180018827  jz      short loc_18001884D
0x180018829  test    [rcx+1Ch], r14b
0x18001882d  jz      short loc_18001884D
0x18001882f  cmp     [rcx+19h], r14b
0x180018833  jb      short loc_18001884D
0x180018835  mov     rcx, [rcx+10h]
0x180018839  lea     r8, WPP_9505920f77393fcf48438baec2ee0d5b_Traceguids
0x180018840  mov     edx, 0Dh
0x180018845  mov     r9d, edi
0x180018848  call    WPP_SF_D
0x18001884d  xorps   xmm0, xmm0
0x180018850  mov     [rbp+var_18], edi
0x180018853  xor     ebx, ebx
0x180018855  mov     [rbp+var_14], 0FFFFFFFFh
0x18001885c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180018863  mov     [rbp+var_20], rbx
0x180018867  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001886b  mov     [rbp+var_10], 71h ; 'q'
0x180018872  movdqu  [rbp+pExceptionObject], xmm0
0x180018877  call    _CxxThrowException_0
0x18001887d  cmp     dword ptr [rdi+44h], 1
0x180018881  jnz     loc_1800189D6
0x180018887  lea     rdx, [rbp+var_50]
0x18001888b  mov     rcx, rbx
0x18001888e  call    ?GetTokenText@GenericLexer@@QEAA?AV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@XZ; GenericLexer::GetTokenText(void)
0x180018893  movaps  xmm0, [rbp+var_50]
0x180018897  lea     rax, aGt_0; "gt"
0x18001889e  lea     rdx, [rbp+var_50]
0x1800188a2  mov     qword ptr [rbp+var_50], rax
0x1800188a6  lea     rcx, [rbp+var_40]
0x1800188aa  mov     qword ptr [rbp+var_50+8], r14
0x1800188ae  movdqa  [rbp+var_40], xmm0
0x1800188b3  call    ??$?9_WU?$char_traits@_W@utl@@@utl@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@0@0@Z; utl::operator!=<wchar_t,utl::char_traits<wchar_t>>(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x1800188b8  xor     ebx, ebx
0x1800188ba  test    al, al
0x1800188bc  jz      loc_1800184DB
0x1800188c2  lea     rax, aLt_0; "lt"
0x1800188c9  mov     qword ptr [rbp+var_50+8], r14
0x1800188cd  lea     rdx, [rbp+var_50]
0x1800188d1  mov     qword ptr [rbp+var_50], rax
0x1800188d5  lea     rcx, [rbp+var_40]
0x1800188d9  movdqa  [rbp+var_40], xmm0
0x1800188de  call    ??$?9_WU?$char_traits@_W@utl@@@utl@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@0@0@Z; utl::operator!=<wchar_t,utl::char_traits<wchar_t>>(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x1800188e3  test    al, al
0x1800188e5  jz      loc_1800184DB
0x1800188eb  lea     rax, aAmp_0; "amp"
0x1800188f2  mov     qword ptr [rbp+var_50+8], 3
0x1800188fa  lea     rdx, [rbp+var_50]
0x1800188fe  mov     qword ptr [rbp+var_50], rax
0x180018902  lea     rcx, [rbp+var_40]
0x180018906  movdqa  [rbp+var_40], xmm0
0x18001890b  call    ??$?9_WU?$char_traits@_W@utl@@@utl@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@0@0@Z; utl::operator!=<wchar_t,utl::char_traits<wchar_t>>(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x180018910  test    al, al
0x180018912  jz      loc_1800184DB
0x180018918  lea     rax, aApos_0; "apos"
0x18001891f  movdqa  [rbp+var_40], xmm0
0x180018924  lea     r10d, [rbx+4]
0x180018928  mov     qword ptr [rbp+var_50], rax
0x18001892c  lea     rdx, [rbp+var_50]
0x180018930  mov     qword ptr [rbp+var_50+8], r10
0x180018934  lea     rcx, [rbp+var_40]
0x180018938  call    ??$?9_WU?$char_traits@_W@utl@@@utl@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@0@0@Z; utl::operator!=<wchar_t,utl::char_traits<wchar_t>>(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18001893d  test    al, al
0x18001893f  jz      loc_1800184DB
0x180018945  lea     rax, aQuot; "quot"
  ... truncated ...
```
