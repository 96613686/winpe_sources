# Json::valueToQuotedStringN

- ea: `0x18003a174`
- end: `0x18003a4b2`
- name: `Json::valueToQuotedStringN`
- size: `830`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x18003a7e0`

## callees

- `0x1800094a0`
- `0x18000ba50`
- `0x18000c354`
- `0x18000c3d0`
- `0x18000c850`
- `0x18000cb90`
- `0x18000cf90`
- `0x18000d5f0`
- `0x18000fe30`
- `0x1800153b4`
- `0x18001a804`
- `0x180021c8c`
- `0x18003655c`
- `0x1800368e0`
- `0x180039590`
- `0x1800399e4`
- `0x18003a174`

## import_xrefs

- `msvcp_win!?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z` at `0x18003a313`
- `msvcp_win!?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z` at `0x18003a313`
- `msvcp_win!?fill@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x18003a304`
- `msvcp_win!?fill@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x18003a304`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18003a2dc`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18003a2ec`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18003a2dc`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18003a2ec`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x18003a32a`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x18003a32a`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Json::valueToQuotedStringN(__int64 a1, _WORD *a2, int a3)
{
  _WORD *v3; // rdi
  _WORD *v5; // r15
  _WORD *i; // rax
  const wchar_t *j; // rcx
  _WORD *k; // rcx
  int v9; // r8d
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  const wchar_t *v18; // rdx
  __int64 v19; // rax
  _BYTE *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  _BYTE v24[8]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v25[232]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v26[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v27[32]; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v28[4]; // [rsp+160h] [rbp+60h] BYREF

  v3 = a2;
  v28[0] = a1;
  if ( !a2 )
  {
    std::wstring::wstring(a1, (__int64)&qword_180048C70);
    return a1;
  }
  v5 = &a2[a3];
  for ( i = a2; i < v5; ++i )
  {
    for ( j = asc_180069BA0; *j; ++j )
    {
      if ( *j == *i )
        goto LABEL_15;
    }
  }
  for ( k = a2; v5 != k; ++k )
  {
    if ( (unsigned __int16)(*k - 1) <= 0x1Eu || !*k )
    {
LABEL_15:
      std::wstring::wstring((__int64)v26);
      std::wstring::reserve(v26, (unsigned int)(2 * v9 + 3));
      v10 = std::_WChar_traits<unsigned short>::length(L"\"");
      std::wstring::_Append<unsigned short>(v26, L"\"", v10);
      while ( 1 )
      {
        if ( v3 == v5 )
        {
          v19 = std::_WChar_traits<unsigned short>::length(L"\"");
          std::wstring::_Append<unsigned short>(v26, L"\"", v19);
          std::wstring::wstring(a1, v26);
          v20 = v26;
          goto LABEL_39;
        }
        v11 = (unsigned __int16)*v3;
        switch ( *v3 )
        {
          case 8:
            v17 = std::_WChar_traits<unsigned short>::length(L"\\b");
            v18 = L"\\b";
            goto LABEL_34;
          case 9:
            v17 = std::_WChar_traits<unsigned short>::length(L"\\t");
            v18 = L"\\t";
            goto LABEL_34;
          case 0xA:
            v17 = std::_WChar_traits<unsigned short>::length(L"\\n");
            v18 = L"\\n";
            goto LABEL_34;
          case 0xC:
            v17 = std::_WChar_traits<unsigned short>::length(L"\\f");
            v18 = L"\\f";
            goto LABEL_34;
          case 0xD:
            v17 = std::_WChar_traits<unsigned short>::length(L"\\r");
            v18 = L"\\r";
            goto LABEL_34;
        }
        if ( *v3 == 34 )
          break;
        if ( *v3 == 92 )
        {
          v17 = std::_WChar_traits<unsigned short>::length(L"\\\\");
          v18 = L"\\\\";
LABEL_34:
          std::wstring::_Append<unsigned short>(v26, v18, v17);
          goto LABEL_35;
        }
        if ( (unsigned __int16)(v11 - 1) > 0x1Eu && (_WORD)v11 )
        {
          std::wstring::push_back(v26, v11);
        }
        else
        {
          std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v24);
          v12 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v24, L"\\u");
          v13 = std::basic_ostream<unsigned short>::operator<<(v12, std::hex);
          v14 = std::basic_ostream<unsigned short>::operator<<(v13, std::uppercase);
          std::basic_ios<unsigned short>::fill(v14 + *(int *)(*(_QWORD *)v14 + 4LL), 48);
          v15 = std::setw(v28, 4);
          v16 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v14, v15);
          std::basic_ostream<unsigned short>::operator<<(v16, (unsigned __int16)*v3);
          std::basic_stringbuf<unsigned short>::str(v25, v27);
          std::wstring::append(v26, v27);
          std::wstring::_Tidy_deallocate(v27);
          std::basic_ostringstream<unsigned short>::`vbase destructor'(v24);
        }
LABEL_35:
        ++v3;
      }
      v17 = std::_WChar_traits<unsigned short>::length(L"\\\"");
      v18 = L"\\\"";
      goto LABEL_34;
    }
  }
  v21 = std::wstring::wstring((__int64)v28, (__int64)L"\"");
  v22 = std::operator+<unsigned short>(v27, v21, v3);
  std::operator+<unsigned short>(a1, v22, L"\"");
  std::wstring::_Tidy_deallocate(v27);
  v20 = v28;
LABEL_39:
  std::wstring::_Tidy_deallocate(v20);
  return a1;
}

```

## disassembly

```asm
0x18003a174  mov     [rsp-8+arg_18], rbx
0x18003a179  push    rbp
0x18003a17a  push    rsi
0x18003a17b  push    rdi
0x18003a17c  push    r12
0x18003a17e  push    r15
0x18003a180  lea     rbp, [rsp-90h]
0x18003a188  sub     rsp, 190h
0x18003a18f  mov     rax, cs:__security_cookie
0x18003a196  xor     rax, rsp
0x18003a199  mov     [rbp+0B0h+var_30], rax
0x18003a1a0  mov     rdi, rdx
0x18003a1a3  mov     rsi, rcx
0x18003a1a6  mov     [rbp+0B0h+var_50], rcx
0x18003a1aa  xor     r12d, r12d
0x18003a1ad  test    rdx, rdx
0x18003a1b0  jnz     short loc_18003A1C3
0x18003a1b2  lea     rdx, qword_180048C70
0x18003a1b9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003a1be  jmp     loc_18003A489
0x18003a1c3  mov     eax, r8d
0x18003a1c6  lea     r15, [rdx+rax*2]
0x18003a1ca  mov     rax, rdi
0x18003a1cd  cmp     rax, r15
0x18003a1d0  jnb     short loc_18003A1F3
0x18003a1d2  movzx   edx, word ptr [rax]
0x18003a1d5  lea     rcx, asc_180069BA0; "\"\\\b"
0x18003a1dc  cmp     [rcx], r12w
0x18003a1e0  jz      short loc_18003A1ED
0x18003a1e2  cmp     [rcx], dx
0x18003a1e5  jz      short loc_18003A217
0x18003a1e7  add     rcx, 2
0x18003a1eb  jmp     short loc_18003A1DC
0x18003a1ed  add     rax, 2
0x18003a1f1  jmp     short loc_18003A1CD
0x18003a1f3  mov     rcx, rdi
0x18003a1f6  cmp     r15, rcx
0x18003a1f9  jz      loc_18003A442
0x18003a1ff  movzx   eax, word ptr [rcx]
0x18003a202  dec     ax
0x18003a205  cmp     ax, 1Eh
0x18003a209  jbe     short loc_18003A217
0x18003a20b  cmp     r12w, [rcx]
0x18003a20f  jz      short loc_18003A217
0x18003a211  add     rcx, 2
0x18003a215  jmp     short loc_18003A1F6
0x18003a217  lea     rcx, [rbp+0B0h+var_90]
0x18003a21b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003a220  nop
0x18003a221  lea     edx, ds:3[r8*2]
0x18003a229  lea     rcx, [rbp+0B0h+var_90]
0x18003a22d  call    ?reserve@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::reserve(unsigned __int64)
0x18003a232  lea     rcx, asc_180069B94; "\""
0x18003a239  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18003a23e  mov     r8, rax
0x18003a241  lea     rdx, asc_180069B94; "\""
0x18003a248  lea     rcx, [rbp+0B0h+var_90]
0x18003a24c  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003a251  jmp     loc_18003A407
0x18003a256  movzx   edx, word ptr [rdi]
0x18003a259  mov     ecx, edx
0x18003a25b  sub     ecx, 8
0x18003a25e  jz      loc_18003A3E4
0x18003a264  sub     ecx, 1
0x18003a267  jz      loc_18003A3CF
0x18003a26d  sub     ecx, 1
0x18003a270  jz      loc_18003A3BA
0x18003a276  sub     ecx, 2
0x18003a279  jz      loc_18003A3A5
0x18003a27f  sub     ecx, 1
0x18003a282  jz      loc_18003A390
0x18003a288  sub     ecx, 15h
0x18003a28b  jz      loc_18003A37B
0x18003a291  cmp     ecx, 3Ah ; ':'
0x18003a294  jz      loc_18003A366
0x18003a29a  lea     eax, [rdx-1]
0x18003a29d  cmp     ax, 1Eh
0x18003a2a1  jbe     short loc_18003A2B6
0x18003a2a3  test    dx, dx
0x18003a2a6  jz      short loc_18003A2B6
0x18003a2a8  lea     rcx, [rbp+0B0h+var_90]
0x18003a2ac  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x18003a2b1  jmp     loc_18003A403
0x18003a2b6  lea     rcx, [rsp+1B0h+var_180]
0x18003a2bb  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18003a2c0  nop
0x18003a2c1  lea     rdx, aU; "\\u"
0x18003a2c8  lea     rcx, [rsp+1B0h+var_180]
0x18003a2cd  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18003a2d2  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18003a2d9  mov     rcx, rax
0x18003a2dc  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x18003a2e2  lea     rdx, ?uppercase@std@@YAAEAVios_base@1@AEAV21@@Z; std::uppercase(std::ios_base &)
0x18003a2e9  mov     rcx, rax
0x18003a2ec  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x18003a2f2  mov     rbx, rax
0x18003a2f5  mov     edx, 30h ; '0'
0x18003a2fa  mov     rcx, [rax]
0x18003a2fd  movsxd  rcx, dword ptr [rcx+4]
0x18003a301  add     rcx, rax
0x18003a304  call    cs:__imp_?fill@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAGG@Z; std::basic_ios<ushort>::fill(ushort)
0x18003a30a  mov     edx, 4
0x18003a30f  lea     rcx, [rbp+0B0h+var_50]
0x18003a313  call    cs:__imp_?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z; std::setw(__int64)
0x18003a319  mov     rdx, rax
0x18003a31c  mov     rcx, rbx
0x18003a31f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBU?$_Smanip@_J@0@@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,std::_Smanip<__int64> const &)
0x18003a324  movzx   edx, word ptr [rdi]
0x18003a327  mov     rcx, rax
0x18003a32a  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x18003a330  lea     rdx, [rbp+0B0h+var_70]
0x18003a334  lea     rcx, [rsp+1B0h+var_178]
0x18003a339  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18003a33e  nop
0x18003a33f  lea     rdx, [rbp+0B0h+var_70]
0x18003a343  lea     rcx, [rbp+0B0h+var_90]
0x18003a347  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18003a34c  nop
0x18003a34d  lea     rcx, [rbp+0B0h+var_70]
0x18003a351  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a356  nop
0x18003a357  lea     rcx, [rsp+1B0h+var_180]
0x18003a35c  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x18003a361  jmp     loc_18003A403
0x18003a366  lea     rcx, asc_180069B84; "\\\\"
0x18003a36d  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18003a372  lea     rdx, asc_180069B84; "\\\\"
0x18003a379  jmp     short loc_18003A3F7
0x18003a37b  lea     rcx, asc_180069B8C; "\\\""
0x18003a382  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18003a387  lea     rdx, asc_180069B8C; "\\\""
0x18003a38e  jmp     short loc_18003A3F7
0x18003a390  lea     rcx, aR; "\\r"
0x18003a397  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18003a39c  lea     rdx, aR; "\\r"
0x18003a3a3  jmp     short loc_18003A3F7
0x18003a3a5  lea     rcx, asc_180069BC0; "\\f"
0x18003a3ac  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18003a3b1  lea     rdx, asc_180069BC0; "\\f"
0x18003a3b8  jmp     short loc_18003A3F7
0x18003a3ba  lea     rcx, aN; "\\n"
0x18003a3c1  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18003a3c6  lea     rdx, aN; "\\n"
0x18003a3cd  jmp     short loc_18003A3F7
0x18003a3cf  lea     rcx, aT; "\\t"
0x18003a3d6  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18003a3db  lea     rdx, aT; "\\t"
0x18003a3e2  jmp     short loc_18003A3F7
0x18003a3e4  lea     rcx, aB; "\\b"
0x18003a3eb  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18003a3f0  lea     rdx, aB; "\\b"
0x18003a3f7  mov     r8, rax
0x18003a3fa  lea     rcx, [rbp+0B0h+var_90]
0x18003a3fe  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003a403  add     rdi, 2
0x18003a407  cmp     rdi, r15
0x18003a40a  jnz     loc_18003A256
0x18003a410  lea     rcx, asc_180069B94; "\""
0x18003a417  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18003a41c  mov     r8, rax
0x18003a41f  lea     rdx, asc_180069B94; "\""
0x18003a426  lea     rcx, [rbp+0B0h+var_90]
0x18003a42a  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003a42f  lea     rdx, [rbp+0B0h+var_90]
0x18003a433  mov     rcx, rsi
0x18003a436  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18003a43b  nop
0x18003a43c  lea     rcx, [rbp+0B0h+var_90]
0x18003a440  jmp     short loc_18003A484
0x18003a442  lea     rdx, asc_180069B94; "\""
0x18003a449  lea     rcx, [rbp+0B0h+var_50]
0x18003a44d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003a452  nop
0x18003a453  mov     r8, rdi
0x18003a456  mov     rdx, rax
0x18003a459  lea     rcx, [rbp+0B0h+var_70]
0x18003a45d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18003a462  nop
0x18003a463  lea     r8, asc_180069B94; "\""
0x18003a46a  mov     rdx, rax
0x18003a46d  mov     rcx, rsi
0x18003a470  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18003a475  nop
0x18003a476  lea     rcx, [rbp+0B0h+var_70]
0x18003a47a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a47f  nop
0x18003a480  lea     rcx, [rbp+0B0h+var_50]
0x18003a484  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a489  mov     rax, rsi
0x18003a48c  mov     rcx, [rbp+0B0h+var_30]
0x18003a493  xor     rcx, rsp; StackCookie
0x18003a496  call    __security_check_cookie
0x18003a49b  mov     rbx, [rsp+1B0h+arg_18]
0x18003a4a3  add     rsp, 190h
0x18003a4aa  pop     r15
0x18003a4ac  pop     r12
0x18003a4ae  pop     rdi
0x18003a4af  pop     rsi
0x18003a4b0  pop     rbp
0x18003a4b1  retn
```
