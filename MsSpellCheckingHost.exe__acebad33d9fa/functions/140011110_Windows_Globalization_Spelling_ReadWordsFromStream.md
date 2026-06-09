# Windows::Globalization::Spelling::ReadWordsFromStream

- ea: `0x140011110`
- end: `0x140011767`
- name: `Windows::Globalization::Spelling::ReadWordsFromStream`
- size: `1623`
- prototype: `_QWORD *__fastcall(_QWORD *, _WORD *i, __int64, char)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x140010d08`

## callees

- `0x140008040`
- `0x14000e94c`
- `0x14000f060`
- `0x14000f530`
- `0x14001093c`
- `0x1400109c4`
- `0x140010a1c`
- `0x140011110`
- `0x140011770`
- `0x140011894`
- `0x140011ab0`
- `0x140011e10`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400112b6`
- `msvcrt!??3@YAXPEAX@Z` at `0x14001131e`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400113b9`
- `msvcrt!??3@YAXPEAX@Z` at `0x14001145d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400114a0`
- `msvcrt!??3@YAXPEAX@Z` at `0x140011532`
- `msvcrt!??3@YAXPEAX@Z` at `0x140011543`
- `msvcrt!??3@YAXPEAX@Z` at `0x140011555`
- `msvcrt!??3@YAXPEAX@Z` at `0x140011583`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400115a1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400115c5`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400115db`
- `msvcrt!??3@YAXPEAX@Z` at `0x14001166b`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400116eb`
- `msvcrt!??3@YAXPEAX@Z` at `0x140011701`
- `msvcrt!??3@YAXPEAX@Z` at `0x14001172d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400112b6`
- `msvcrt!??3@YAXPEAX@Z` at `0x14001131e`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400113b9`
- `msvcrt!??3@YAXPEAX@Z` at `0x14001145d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400114a0`
- `msvcrt!??3@YAXPEAX@Z` at `0x140011532`
- `msvcrt!??3@YAXPEAX@Z` at `0x140011543`
- `msvcrt!??3@YAXPEAX@Z` at `0x140011555`
- `msvcrt!??3@YAXPEAX@Z` at `0x140011583`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400115a1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400115c5`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400115db`
- `msvcrt!??3@YAXPEAX@Z` at `0x14001166b`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400116eb`
- `msvcrt!??3@YAXPEAX@Z` at `0x140011701`
- `msvcrt!??3@YAXPEAX@Z` at `0x14001172d`

## pseudocode

```c
_QWORD *__fastcall Windows::Globalization::Spelling::ReadWordsFromStream(_QWORD *a1, _WORD *i, __int64 a3, char a4)
{
  int v8; // r15d
  _WORD *v9; // r14
  _QWORD *v10; // rcx
  void *v11; // r10
  unsigned __int64 v12; // r9
  _QWORD *v13; // rdx
  _QWORD *v14; // rcx
  _WORD *v15; // rbx
  _WORD *v16; // rax
  unsigned __int64 v17; // rcx
  __int64 v18; // r8
  void **v19; // rax
  void **v20; // rax
  void **v21; // rbx
  void **v22; // rax
  void *v23; // rcx
  void **v24; // rdx
  char *v25; // rdx
  void **v26; // rcx
  char *v27; // r9
  char *v28; // r8
  __int64 v29; // rax
  int v30; // r8d
  void *v31; // rcx
  void **v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rax
  int v35; // r8d
  char v37; // [rsp+40h] [rbp-C0h] BYREF
  char v38; // [rsp+50h] [rbp-B0h] BYREF
  void *v39[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v40; // [rsp+70h] [rbp-90h]
  unsigned __int64 v41; // [rsp+78h] [rbp-88h]
  void *v42[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v43; // [rsp+90h] [rbp-70h]
  unsigned __int64 v44; // [rsp+98h] [rbp-68h]
  void *v45[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v46; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v47; // [rsp+B8h] [rbp-48h]
  void *v48[3]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v49; // [rsp+D8h] [rbp-28h]
  _QWORD v50[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v51; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v52; // [rsp+F8h] [rbp-8h]
  void *v53[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v54; // [rsp+110h] [rbp+10h]
  unsigned __int64 v55; // [rsp+118h] [rbp+18h]

  *a1 = 0;
  a1[1] = 0;
  *a1 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,std::wstring>>>::_Buyheadnode();
  v8 = 1;
  v9 = &i[a3];
  while ( i != v9 )
  {
    v52 = 7;
    v51 = 0;
    LOWORD(v50[0]) = 0;
    std::wstring::assign(v50, L"\r\n");
    v10 = v50;
    v11 = (void *)v50[0];
    v12 = v52;
    if ( v52 >= 8 )
      v10 = (_QWORD *)v50[0];
    v13 = (_QWORD *)((char *)v10 + 2 * v51);
    v14 = v50;
    if ( v52 >= 8 )
      v14 = (_QWORD *)v50[0];
    v15 = i;
    if ( i != v9 )
    {
      while ( v14 == v13 )
      {
LABEL_11:
        if ( ++v15 == v9 )
          goto LABEL_12;
      }
      v16 = v14;
      while ( *v15 != *v16 )
      {
        if ( ++v16 == (_WORD *)v13 )
          goto LABEL_11;
      }
    }
LABEL_12:
    v17 = 7;
    v41 = 7;
    v18 = 0;
    v40 = 0;
    LOWORD(v39[0]) = 0;
    if ( i != v15 )
    {
      std::wstring::assign(v39, i);
      v12 = v52;
      v11 = (void *)v50[0];
      v17 = v41;
      v18 = v40;
    }
    for ( i = v15; i != v9; ++i )
    {
      if ( *i != 13 && *i != 10 )
        break;
    }
    if ( !v18 )
      goto LABEL_84;
    v19 = v39;
    if ( v17 >= 8 )
      v19 = (void **)v39[0];
    if ( *(_WORD *)v19 == 35 )
    {
LABEL_84:
      if ( v17 >= 8 )
      {
        operator delete(v39[0]);
        v12 = v52;
        v11 = (void *)v50[0];
      }
      v41 = 7;
      v40 = 0;
      LOWORD(v39[0]) = 0;
      if ( v12 < 8 )
        continue;
      v23 = v11;
      goto LABEL_88;
    }
    v44 = 7;
    v43 = 0;
    LOWORD(v42[0]) = 0;
    std::wstring::assign(v42, L" \t");
    Windows::Globalization::Spelling::TrimLeadingSpaces(v39);
    if ( v44 >= 8 )
      operator delete(v42[0]);
    v20 = v39;
    if ( v41 >= 8 )
      v20 = (void **)v39[0];
    v21 = v39;
    if ( v41 >= 8 )
      v21 = (void **)v39[0];
    while ( v21 != (void **)((char *)v20 + 2 * v40) && *(_WORD *)v21 != 124 )
      v21 = (void **)((char *)v21 + 2);
    v22 = v39;
    if ( a4 )
    {
      if ( v41 >= 8 )
        v22 = (void **)v39[0];
      if ( v21 == (void **)((char *)v22 + 2 * v40) )
      {
        if ( v41 < 8 )
          goto LABEL_38;
LABEL_37:
        operator delete(v39[0]);
        goto LABEL_38;
      }
      v24 = v39;
      if ( v41 >= 8 )
        v24 = (void **)v39[0];
      v55 = 7;
      v54 = 0;
      LOWORD(v53[0]) = 0;
      std::wstring::_Construct<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
        v53,
        v24,
        v21);
      v47 = 7;
      v46 = 0;
      LOWORD(v45[0]) = 0;
      std::wstring::assign(v45, L" \t");
      Windows::Globalization::Spelling::TrimTrailingSpaces(v53);
      if ( v47 >= 8 )
        operator delete(v45[0]);
      if ( (unsigned __int64)(v54 - 1) > 0x7F )
      {
        if ( v55 >= 8 )
          operator delete(v53[0]);
        goto LABEL_67;
      }
      v25 = (char *)v21 + 2;
      v26 = v39;
      if ( v41 >= 8 )
        v26 = (void **)v39[0];
      v27 = (char *)v26 + 2 * v40;
      v28 = (char *)v21 + 2;
      if ( v25 != v27 )
      {
        do
        {
          if ( *(_WORD *)v28 == 124 )
            break;
          v28 += 2;
        }
        while ( v28 != v27 );
      }
      v44 = 7;
      v43 = 0;
      LOWORD(v42[0]) = 0;
      std::wstring::_Construct<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
        v42,
        v25,
        v28);
      v47 = 7;
      v46 = 0;
      LOWORD(v45[0]) = 0;
      std::wstring::assign(v45, L" \t");
      Windows::Globalization::Spelling::TrimLeadingSpaces(v42);
      if ( v47 >= 8 )
        operator delete(v45[0]);
      v47 = 7;
      v46 = 0;
      LOWORD(v45[0]) = 0;
      std::wstring::assign(v45, L" \t");
      Windows::Globalization::Spelling::TrimTrailingSpaces(v42);
      if ( v47 >= 8 )
        operator delete(v45[0]);
      if ( (unsigned __int64)(v43 - 1) > 0x7F )
      {
        if ( v44 >= 8 )
          operator delete(v42[0]);
        v44 = 7;
        v43 = 0;
        LOWORD(v42[0]) = 0;
        if ( v55 >= 8 )
          operator delete(v53[0]);
LABEL_67:
        v55 = 7;
        v54 = 0;
        LOWORD(v53[0]) = 0;
        goto LABEL_68;
      }
      v47 = 7;
      v46 = 0;
      LOWORD(v45[0]) = 0;
      std::wstring::assign(v45, v53, 0, 0xFFFFFFFFFFFFFFFFuLL);
      v49 = 7;
      v48[2] = 0;
      LOWORD(v48[0]) = 0;
      std::wstring::assign(v48, v42, 0, 0xFFFFFFFFFFFFFFFFuLL);
      v8 |= 2u;
      v29 = std::_Tree_buy<std::pair<std::wstring const,std::wstring>>::_Buynode<std::pair<std::wstring,std::wstring>>(
              a1,
              v45);
      std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Insert_nohint<std::pair<std::wstring const,std::wstring> &,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *>(
        (_DWORD)a1,
        (unsigned int)&v37,
        v30,
        v29 + 32,
        v29);
      if ( v49 >= 8 )
        operator delete(v48[0]);
      if ( v47 >= 8 )
        operator delete(v45[0]);
      if ( v44 >= 8 )
        operator delete(v42[0]);
      v44 = 7;
      v43 = 0;
      LOWORD(v42[0]) = 0;
      if ( v55 >= 8 )
      {
        v31 = v53[0];
LABEL_83:
        operator delete(v31);
      }
    }
    else
    {
      v32 = v39;
      if ( v41 >= 8 )
        v32 = (void **)v39[0];
      if ( v21 )
        v33 = ((char *)v21 - (char *)v32) >> 1;
      else
        v33 = 0;
      std::wstring::erase(v39, v33);
      v47 = 7;
      v46 = 0;
      LOWORD(v45[0]) = 0;
      std::wstring::assign(v45, L" \t");
      Windows::Globalization::Spelling::TrimTrailingSpaces(v39);
      if ( v47 >= 8 )
        operator delete(v45[0]);
      if ( (unsigned __int64)(v40 - 1) <= 0x7F )
      {
        v47 = 7;
        v46 = 0;
        LOWORD(v45[0]) = 0;
        std::wstring::assign(v45, v39, 0, 0xFFFFFFFFFFFFFFFFuLL);
        v48[0] = byte_1400171A8;
        v8 |= 4u;
        v34 = std::_Tree_buy<std::pair<std::wstring const,std::wstring>>::_Buynode<std::pair<std::wstring,unsigned short const *>>(
                a1,
                v45);
        std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Insert_nohint<std::pair<std::wstring const,std::wstring> &,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *>(
          (_DWORD)a1,
          (unsigned int)&v38,
          v35,
          v34 + 32,
          v34);
        if ( v47 >= 8 )
        {
          v31 = v45[0];
          goto LABEL_83;
        }
      }
    }
LABEL_68:
    if ( v41 >= 8 )
      goto LABEL_37;
LABEL_38:
    v41 = 7;
    v40 = 0;
    LOWORD(v39[0]) = 0;
    if ( v52 >= 8 )
    {
      v23 = (void *)v50[0];
LABEL_88:
      operator delete(v23);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x140011110  mov     [rsp-8+arg_10], rbx
0x140011115  push    rbp
0x140011116  push    rsi
0x140011117  push    rdi
0x140011118  push    r12
0x14001111a  push    r13
0x14001111c  push    r14
0x14001111e  push    r15
0x140011120  lea     rbp, [rsp-30h]
0x140011125  sub     rsp, 130h
0x14001112c  mov     rax, cs:__security_cookie
0x140011133  xor     rax, rsp
0x140011136  mov     [rbp+60h+var_40], rax
0x14001113a  mov     r12b, r9b
0x14001113d  mov     rbx, r8
0x140011140  mov     rdi, rdx
0x140011143  mov     rsi, rcx
0x140011146  mov     [rsp+160h+var_128], rcx
0x14001114b  xor     r13d, r13d
0x14001114e  mov     [rsp+160h+var_130], r13d
0x140011153  mov     [rcx], r13
0x140011156  mov     [rcx+8], r13
0x14001115a  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,std::wstring>>>::_Buyheadnode(void)
0x14001115f  mov     [rsi], rax
0x140011162  lea     r15d, [r13+1]
0x140011166  mov     [rsp+160h+var_130], r15d
0x14001116b  lea     r14, [rdi+rbx*2]
0x14001116f  cmp     rdi, r14
0x140011172  jz      loc_14001173C
0x140011178  lea     ebx, [r13+7]
0x14001117c  mov     [rbp+60h+var_68], rbx
0x140011180  mov     [rbp+60h+var_70], r13
0x140011184  mov     word ptr [rbp+60h+var_80], r13w
0x140011189  mov     r8d, 2
0x14001118f  lea     rdx, asc_1400171AC; "\r\n"
0x140011196  lea     rcx, [rbp+60h+var_80]; void *
0x14001119a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x14001119f  nop
0x1400111a0  lea     rcx, [rbp+60h+var_80]
0x1400111a4  mov     r10, [rbp+60h+var_80]
0x1400111a8  mov     r9, [rbp+60h+var_68]
0x1400111ac  cmp     r9, 8
0x1400111b0  cmovnb  rcx, r10
0x1400111b4  mov     rax, [rbp+60h+var_70]
0x1400111b8  lea     rdx, [rcx+rax*2]
0x1400111bc  lea     rcx, [rbp+60h+var_80]
0x1400111c0  cmovnb  rcx, r10
0x1400111c4  mov     rbx, rdi
0x1400111c7  cmp     rdi, r14
0x1400111ca  jz      short loc_1400111F0
0x1400111cc  cmp     rcx, rdx
0x1400111cf  jz      short loc_1400111E7
0x1400111d1  mov     rax, rcx
0x1400111d4  movzx   r8d, word ptr [rbx]
0x1400111d8  cmp     r8w, [rax]
0x1400111dc  jz      short loc_1400111F0
0x1400111de  add     rax, 2
0x1400111e2  cmp     rax, rdx
0x1400111e5  jnz     short loc_1400111D8
0x1400111e7  add     rbx, 2
0x1400111eb  cmp     rbx, r14
0x1400111ee  jnz     short loc_1400111CC
0x1400111f0  mov     ecx, 7
0x1400111f5  mov     [rsp+160h+var_E8], rcx
0x1400111fa  mov     r8, r13
0x1400111fd  mov     [rsp+160h+var_F0], r13
0x140011202  mov     word ptr [rsp+160h+var_100], r13w
0x140011208  cmp     rdi, rbx
0x14001120b  jz      short loc_140011235
0x14001120d  mov     r8, rbx
0x140011210  sub     r8, rdi
0x140011213  sar     r8, 1
0x140011216  mov     rdx, rdi; Src
0x140011219  lea     rcx, [rsp+160h+var_100]; void *
0x14001121e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x140011223  mov     r9, [rbp+60h+var_68]
0x140011227  mov     r10, [rbp+60h+var_80]
0x14001122b  mov     rcx, [rsp+160h+var_E8]
0x140011230  mov     r8, [rsp+160h+var_F0]
0x140011235  mov     rdi, rbx
0x140011238  cmp     rbx, r14
0x14001123b  jz      short loc_140011252
0x14001123d  cmp     word ptr [rdi], 0Dh
0x140011241  jz      short loc_140011249
0x140011243  cmp     word ptr [rdi], 0Ah
0x140011247  jnz     short loc_140011252
0x140011249  add     rdi, 2
0x14001124d  cmp     rdi, r14
0x140011250  jnz     short loc_14001123D
0x140011252  test    r8, r8
0x140011255  jz      loc_1400116F6
0x14001125b  lea     rax, [rsp+160h+var_100]
0x140011260  cmp     rcx, 8
0x140011264  cmovnb  rax, [rsp+160h+var_100]
0x14001126a  cmp     word ptr [rax], 23h ; '#'
0x14001126e  jz      loc_1400116F6
0x140011274  mov     [rbp+60h+var_C8], 7
0x14001127c  mov     [rbp+60h+var_D0], r13
0x140011280  mov     word ptr [rbp+60h+var_E0], r13w
0x140011285  mov     r8d, 2
0x14001128b  lea     rdx, asc_1400171A0; " \t"
0x140011292  lea     rcx, [rbp+60h+var_E0]; void *
0x140011296  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x14001129b  nop
0x14001129c  lea     rdx, [rbp+60h+var_E0]
0x1400112a0  lea     rcx, [rsp+160h+var_100]; void *
0x1400112a5  call    ?TrimLeadingSpaces@Spelling@Globalization@Windows@@YAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV45@AEBV45@@Z; Windows::Globalization::Spelling::TrimLeadingSpaces(std::wstring &,std::wstring const &)
0x1400112aa  nop
0x1400112ab  cmp     [rbp+60h+var_C8], 8
0x1400112b0  jb      short loc_1400112BC
0x1400112b2  mov     rcx, [rbp+60h+var_E0]
0x1400112b6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400112bc  lea     rax, [rsp+160h+var_100]
0x1400112c1  mov     r9, [rsp+160h+var_100]
0x1400112c6  mov     rcx, [rsp+160h+var_E8]
0x1400112cb  cmp     rcx, 8
0x1400112cf  cmovnb  rax, r9
0x1400112d3  mov     rdx, [rsp+160h+var_F0]
0x1400112d8  lea     rbx, [rsp+160h+var_100]
0x1400112dd  cmovnb  rbx, r9
0x1400112e1  lea     r8, [rax+rdx*2]
0x1400112e5  jmp     short loc_1400112F1
0x1400112e7  cmp     word ptr [rbx], 7Ch ; '|'
0x1400112eb  jz      short loc_1400112F6
0x1400112ed  add     rbx, 2
0x1400112f1  cmp     rbx, r8
0x1400112f4  jnz     short loc_1400112E7
0x1400112f6  lea     rax, [rsp+160h+var_100]
0x1400112fb  test    r12b, r12b
0x1400112fe  jz      loc_1400115E8
0x140011304  cmp     rcx, 8
0x140011308  cmovnb  rax, r9
0x14001130c  lea     rax, [rax+rdx*2]
0x140011310  cmp     rbx, rax
0x140011313  jnz     short loc_14001134D
0x140011315  cmp     rcx, 8
0x140011319  jb      short loc_140011324
0x14001131b  mov     rcx, r9
0x14001131e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140011324  mov     ebx, 7
0x140011329  mov     [rsp+160h+var_E8], rbx
0x14001132e  mov     [rsp+160h+var_F0], r13
0x140011333  mov     word ptr [rsp+160h+var_100], r13w
0x140011339  cmp     [rbp+60h+var_68], 8
0x14001133e  jb      loc_140011733
0x140011344  mov     rcx, [rbp+60h+var_80]
0x140011348  jmp     loc_14001172D
0x14001134d  lea     rdx, [rsp+160h+var_100]
0x140011352  cmp     rcx, 8
0x140011356  cmovnb  rdx, r9
0x14001135a  mov     [rbp+60h+var_48], 7
0x140011362  mov     [rbp+60h+var_50], r13
0x140011366  mov     word ptr [rbp+60h+var_60], r13w
0x14001136b  mov     r8, rbx
0x14001136e  lea     rcx, [rbp+60h+var_60]
0x140011372  call    ??$_Construct@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@1@0Uforward_iterator_tag@1@@Z; std::wstring::_Construct<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::forward_iterator_tag)
0x140011377  nop
0x140011378  mov     [rbp+60h+var_A8], 7
0x140011380  mov     [rbp+60h+var_B0], r13
0x140011384  mov     word ptr [rbp+60h+var_C0], r13w
0x140011389  mov     r8d, 2
0x14001138f  lea     rdx, asc_1400171A0; " \t"
0x140011396  lea     rcx, [rbp+60h+var_C0]; void *
0x14001139a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x14001139f  nop
0x1400113a0  lea     rdx, [rbp+60h+var_C0]
0x1400113a4  lea     rcx, [rbp+60h+var_60]; void *
0x1400113a8  call    ?TrimTrailingSpaces@Spelling@Globalization@Windows@@YAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV45@AEBV45@@Z; Windows::Globalization::Spelling::TrimTrailingSpaces(std::wstring &,std::wstring const &)
0x1400113ad  nop
0x1400113ae  cmp     [rbp+60h+var_A8], 8
0x1400113b3  jb      short loc_1400113BF
0x1400113b5  mov     rcx, [rbp+60h+var_C0]
0x1400113b9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400113bf  mov     rax, [rbp+60h+var_50]
0x1400113c3  dec     rax
0x1400113c6  cmp     rax, 7Fh
0x1400113ca  ja      loc_1400115D0
0x1400113d0  lea     rdx, [rbx+2]
0x1400113d4  lea     rcx, [rsp+160h+var_100]
0x1400113d9  cmp     [rsp+160h+var_E8], 8
0x1400113df  cmovnb  rcx, [rsp+160h+var_100]
0x1400113e5  mov     rax, [rsp+160h+var_F0]
0x1400113ea  lea     r9, [rcx+rax*2]
0x1400113ee  mov     r8, rdx
0x1400113f1  cmp     rdx, r9
0x1400113f4  jz      short loc_140011406
0x1400113f6  cmp     word ptr [r8], 7Ch ; '|'
0x1400113fb  jz      short loc_140011406
0x1400113fd  add     r8, 2
0x140011401  cmp     r8, r9
0x140011404  jnz     short loc_1400113F6
0x140011406  mov     ebx, 7
0x14001140b  mov     [rbp+60h+var_C8], rbx
0x14001140f  mov     [rbp+60h+var_D0], r13
0x140011413  mov     word ptr [rbp+60h+var_E0], r13w
0x140011418  lea     rcx, [rbp+60h+var_E0]
0x14001141c  call    ??$_Construct@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@1@0Uforward_iterator_tag@1@@Z; std::wstring::_Construct<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::forward_iterator_tag)
0x140011421  nop
0x140011422  mov     [rbp+60h+var_A8], rbx
0x140011426  mov     [rbp+60h+var_B0], r13
0x14001142a  mov     word ptr [rbp+60h+var_C0], r13w
0x14001142f  lea     r8d, [rbx-5]
0x140011433  lea     rdx, asc_1400171A0; " \t"
0x14001143a  lea     rcx, [rbp+60h+var_C0]; void *
0x14001143e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x140011443  nop
0x140011444  lea     rdx, [rbp+60h+var_C0]
0x140011448  lea     rcx, [rbp+60h+var_E0]; void *
0x14001144c  call    ?TrimLeadingSpaces@Spelling@Globalization@Windows@@YAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV45@AEBV45@@Z; Windows::Globalization::Spelling::TrimLeadingSpaces(std::wstring &,std::wstring const &)
0x140011451  nop
0x140011452  cmp     [rbp+60h+var_A8], 8
0x140011457  jb      short loc_140011463
0x140011459  mov     rcx, [rbp+60h+var_C0]
0x14001145d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140011463  mov     [rbp+60h+var_A8], rbx
0x140011467  mov     [rbp+60h+var_B0], r13
0x14001146b  mov     word ptr [rbp+60h+var_C0], r13w
0x140011470  mov     r8d, 2
0x140011476  lea     rdx, asc_1400171A0; " \t"
0x14001147d  lea     rcx, [rbp+60h+var_C0]; void *
0x140011481  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x140011486  nop
0x140011487  lea     rdx, [rbp+60h+var_C0]
0x14001148b  lea     rcx, [rbp+60h+var_E0]; void *
0x14001148f  call    ?TrimTrailingSpaces@Spelling@Globalization@Windows@@YAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV45@AEBV45@@Z; Windows::Globalization::Spelling::TrimTrailingSpaces(std::wstring &,std::wstring const &)
0x140011494  nop
0x140011495  cmp     [rbp+60h+var_A8], 8
0x14001149a  jb      short loc_1400114A6
0x14001149c  mov     rcx, [rbp+60h+var_C0]
0x1400114a0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400114a6  mov     rax, [rbp+60h+var_D0]
0x1400114aa  dec     rax
0x1400114ad  cmp     rax, 7Fh
0x1400114b1  ja      loc_140011578
0x1400114b7  mov     [rbp+60h+var_A8], rbx
0x1400114bb  mov     [rbp+60h+var_B0], r13
0x1400114bf  mov     word ptr [rbp+60h+var_C0], r13w
0x1400114c4  or      r9, 0FFFFFFFFFFFFFFFFh
0x1400114c8  xor     r8d, r8d
0x1400114cb  lea     rdx, [rbp+60h+var_60]
0x1400114cf  lea     rcx, [rbp+60h+var_C0]; void *
0x1400114d3  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1400114d8  nop
0x1400114d9  mov     [rbp+60h+var_88], rbx
0x1400114dd  mov     [rbp+60h+var_90], r13
0x1400114e1  mov     word ptr [rbp+60h+var_A0], r13w
0x1400114e6  or      r9, 0FFFFFFFFFFFFFFFFh
0x1400114ea  xor     r8d, r8d
0x1400114ed  lea     rdx, [rbp+60h+var_E0]
0x1400114f1  lea     rcx, [rbp+60h+var_A0]; void *
0x1400114f5  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1400114fa  nop
0x1400114fb  or      r15d, 2
0x1400114ff  mov     [rsp+160h+var_130], r15d
0x140011504  lea     rdx, [rbp+60h+var_C0]
0x140011508  mov     rcx, rsi
0x14001150b  call    ??$_Buynode@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@?$_Tree_buy@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@@Z; std::_Tree_buy<std::pair<std::wstring const,std::wstring>>::_Buynode<std::pair<std::wstring,std::wstring>>(std::pair<std::wstring,std::wstring> &&)
0x140011510  lea     r9, [rax+20h]
0x140011514  mov     [rsp+160h+var_140], rax
0x140011519  lea     rdx, [rsp+160h+var_120]
0x14001151e  mov     rcx, rsi
0x140011521  call    ??$_Insert_nohint@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Insert_nohint<std::pair<std::wstring const,std::wstring> &,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *>(bool,std::pair<std::wstring const,std::wstring> &,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x140011526  nop
0x140011527  cmp     [rbp+60h+var_88], 8
0x14001152c  jb      short loc_140011538
0x14001152e  mov     rcx, [rbp+60h+var_A0]
0x140011532  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140011538  cmp     [rbp+60h+var_A8], 8
0x14001153d  jb      short loc_14001154A
0x14001153f  mov     rcx, [rbp+60h+var_C0]
0x140011543  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140011549  nop
0x14001154a  cmp     [rbp+60h+var_C8], 8
0x14001154f  jb      short loc_14001155B
0x140011551  mov     rcx, [rbp+60h+var_E0]
0x140011555  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14001155b  mov     [rbp+60h+var_C8], rbx
0x14001155f  mov     [rbp+60h+var_D0], r13
0x140011563  mov     word ptr [rbp+60h+var_E0], r13w
0x140011568  cmp     [rbp+60h+var_48], 8
0x14001156d  jb      short loc_1400115B4
0x14001156f  mov     rcx, [rbp+60h+var_60]
0x140011573  jmp     loc_1400116EB
0x140011578  cmp     [rbp+60h+var_C8], 8
0x14001157d  jb      short loc_140011589
0x14001157f  mov     rcx, [rbp+60h+var_E0]
0x140011583  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140011589  mov     [rbp+60h+var_C8], rbx
0x14001158d  mov     [rbp+60h+var_D0], r13
0x140011591  mov     word ptr [rbp+60h+var_E0], r13w
0x140011596  cmp     [rbp+60h+var_48], 8
0x14001159b  jb      short loc_1400115A7
0x14001159d  mov     rcx, [rbp+60h+var_60]
0x1400115a1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400115a7  mov     [rbp+60h+var_48], rbx
0x1400115ab  mov     [rbp+60h+var_50], r13
0x1400115af  mov     word ptr [rbp+60h+var_60], r13w
0x1400115b4  cmp     [rsp+160h+var_E8], 8
0x1400115ba  jb      loc_140011329
0x1400115c0  mov     rcx, [rsp+160h+var_100]
  ... truncated ...
```
