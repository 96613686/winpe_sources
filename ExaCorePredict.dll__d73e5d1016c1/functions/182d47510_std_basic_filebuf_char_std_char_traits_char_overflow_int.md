# std::basic_filebuf<char,std::char_traits<char>>::overflow(int)

- ea: `0x182d47510`
- end: `0x182d477bc`
- name: `?overflow@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAAHH@Z`
- size: `684`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x182d46c40`
- `0x182d46d50`
- `0x182d47510`
- `0x1832c3a30`
- `0x1832ce3b0`

## import_xrefs

- `MSVCP140!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x182d47556`
- `MSVCP140!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x182d47572`
- `MSVCP140!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x182d47556`
- `MSVCP140!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x182d47572`
- `MSVCP140!?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ` at `0x182d47580`
- `MSVCP140!?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ` at `0x182d47580`
- `MSVCP140!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x182d47674`
- `MSVCP140!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x182d47674`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182d47757`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182d47767`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182d47777`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182d47784`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182d47757`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182d47767`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182d47777`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182d47784`
- `api-ms-win-crt-stdio-l1-1-0!fputc` at `0x182d475e1`
- `api-ms-win-crt-stdio-l1-1-0!fputc` at `0x182d4771c`
- `api-ms-win-crt-stdio-l1-1-0!fputc` at `0x182d475e1`
- `api-ms-win-crt-stdio-l1-1-0!fputc` at `0x182d4771c`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x182d476c3`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x182d476c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::filebuf::overflow(__int64 a1, unsigned int a2)
{
  unsigned __int64 v5; // rbx
  _QWORD *v6; // r8
  __int64 v7; // rdx
  __int64 v8; // rcx
  unsigned int v9; // ebx
  void **v10; // r8
  unsigned __int64 v11; // r9
  void **v12; // rcx
  void **v13; // rdx
  int v14; // eax
  void **v15; // rax
  signed __int64 v16; // rbx
  void **v17; // rcx
  size_t v18; // rax
  void **v19; // rax
  unsigned __int64 v20; // r8
  __int64 v21; // [rsp+48h] [rbp-9h]
  void **v22; // [rsp+50h] [rbp-1h] BYREF
  char *v23; // [rsp+58h] [rbp+7h] BYREF
  char v24; // [rsp+60h] [rbp+Fh] BYREF
  char v25[7]; // [rsp+61h] [rbp+10h] BYREF
  void *Buffer[2]; // [rsp+68h] [rbp+17h] BYREF
  unsigned __int64 v27; // [rsp+78h] [rbp+27h]
  unsigned __int64 v28; // [rsp+80h] [rbp+2Fh]

  v21 = -2;
  if ( a2 == -1 )
    return 0;
  if ( ((__int64 (*)(void))std::streambuf::pptr)()
    && (v5 = **(_QWORD **)(a1 + 64) + **(int **)(a1 + 88), std::streambuf::pptr(a1) < v5) )
  {
    *(_BYTE *)std::streambuf::_Pninc(a1) = a2;
    return a2;
  }
  else if ( *(_QWORD *)(a1 + 128) )
  {
    v6 = *(_QWORD **)(a1 + 24);
    if ( *v6 == a1 + 112 )
    {
      v7 = *(_QWORD *)(a1 + 144);
      v8 = *(_QWORD *)(a1 + 136);
      *v6 = v8;
      **(_QWORD **)(a1 + 56) = v8;
      **(_DWORD **)(a1 + 80) = v7 - v8;
    }
    if ( *(_QWORD *)(a1 + 104) )
    {
      v24 = a2;
      v28 = 15;
      v27 = 0;
      LOBYTE(Buffer[0]) = 0;
      std::string::assign(Buffer, 8u);
LABEL_15:
      v10 = (void **)Buffer[0];
      v11 = v28;
      while ( 1 )
      {
        v12 = Buffer;
        if ( v11 >= 0x10 )
          v12 = v10;
        v13 = Buffer;
        if ( v11 >= 0x10 )
          v13 = v10;
        v14 = std::codecvt<char,char,_Mbstatet>::out(
                *(_QWORD *)(a1 + 104),
                a1 + 116,
                &v24,
                v25,
                &v23,
                v13,
                (char *)v12 + v27,
                &v22,
                v21);
        if ( v14 < 0 )
          goto LABEL_37;
        if ( v14 > 1 )
          break;
        v15 = Buffer;
        v10 = (void **)Buffer[0];
        v11 = v28;
        if ( v28 >= 0x10 )
          v15 = (void **)Buffer[0];
        v16 = (char *)v22 - (char *)v15;
        if ( v22 != v15 )
        {
          v17 = Buffer;
          if ( v28 >= 0x10 )
            v17 = (void **)Buffer[0];
          v18 = fwrite(v17, 1u, (char *)v22 - (char *)v15, *(FILE **)(a1 + 128));
          v11 = v28;
          v10 = (void **)Buffer[0];
          if ( v16 != v18 )
            goto LABEL_38;
        }
        *(_BYTE *)(a1 + 113) = 1;
        if ( v23 != &v24 )
        {
          v9 = a2;
          goto LABEL_39;
        }
        if ( !v16 )
        {
          if ( v27 < 0x20 )
          {
            std::string::append(Buffer, 8, 0);
            goto LABEL_15;
          }
          goto LABEL_38;
        }
      }
      if ( v14 != 3 )
      {
LABEL_37:
        v11 = v28;
        v10 = (void **)Buffer[0];
LABEL_38:
        v9 = -1;
        goto LABEL_39;
      }
      v9 = -1;
      if ( fputc(v24, *(FILE **)(a1 + 128)) != -1 )
        v9 = a2;
      v11 = v28;
      v10 = (void **)Buffer[0];
LABEL_39:
      if ( v11 >= 0x10 )
      {
        if ( v11 + 1 >= 0x1000 )
        {
          if ( ((__int64)Buffer[0] & 0x1F) != 0 )
            _invalid_parameter_noinfo_noreturn();
          v19 = (void **)*(v10 - 1);
          if ( v19 >= v10 )
            _invalid_parameter_noinfo_noreturn();
          v20 = (char *)v10 - (char *)v19;
          if ( v20 < 8 )
            _invalid_parameter_noinfo_noreturn();
          if ( v20 > 0x27 )
            _invalid_parameter_noinfo_noreturn();
          v10 = v19;
        }
        operator delete(v10);
      }
    }
    else
    {
      v9 = -1;
      if ( fputc((char)a2, *(FILE **)(a1 + 128)) != -1 )
        return a2;
    }
    return v9;
  }
  else
  {
    return 0xFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x182d47510  mov     rax, rsp
0x182d47513  push    rbp
0x182d47514  push    rdi
0x182d47515  push    r14
0x182d47517  lea     rbp, [rax-5Fh]
0x182d4751b  sub     rsp, 90h
0x182d47522  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFEh
0x182d4752a  mov     [rax+18h], rbx
0x182d4752e  mov     [rax+20h], rsi
0x182d47532  mov     rax, cs:__security_cookie
0x182d47539  xor     rax, rsp
0x182d4753c  mov     [rbp+57h+var_20], rax
0x182d47540  mov     esi, edx
0x182d47542  mov     rdi, rcx
0x182d47545  cmp     edx, 0FFFFFFFFh
0x182d47548  jnz     short loc_182D47556
0x182d4754a  xor     eax, eax
0x182d4754c  cmp     edx, edx
0x182d4754e  cmovnz  eax, edx
0x182d47551  jmp     loc_182D47798
0x182d47556  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x182d4755c  test    rax, rax
0x182d4755f  jz      short loc_182D47590
0x182d47561  mov     rdx, [rdi+58h]
0x182d47565  movsxd  rbx, dword ptr [rdx]
0x182d47568  mov     rdx, [rdi+40h]
0x182d4756c  add     rbx, [rdx]
0x182d4756f  mov     rcx, rdi
0x182d47572  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x182d47578  cmp     rax, rbx
0x182d4757b  jnb     short loc_182D47590
0x182d4757d  mov     rcx, rdi
0x182d47580  call    cs:__imp_?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ; std::streambuf::_Pninc(void)
0x182d47586  mov     [rax], sil
0x182d47589  mov     eax, esi
0x182d4758b  jmp     loc_182D47798
0x182d47590  cmp     qword ptr [rdi+80h], 0
0x182d47598  jnz     short loc_182D475A2
0x182d4759a  or      eax, 0FFFFFFFFh
0x182d4759d  jmp     loc_182D47798
0x182d475a2  mov     r8, [rdi+18h]
0x182d475a6  lea     rax, [rdi+70h]
0x182d475aa  cmp     [r8], rax
0x182d475ad  jnz     short loc_182D475CF
0x182d475af  mov     rdx, [rdi+90h]
0x182d475b6  mov     rcx, [rdi+88h]
0x182d475bd  mov     [r8], rcx
0x182d475c0  mov     rax, [rdi+38h]
0x182d475c4  mov     [rax], rcx
0x182d475c7  sub     edx, ecx
0x182d475c9  mov     rax, [rdi+50h]
0x182d475cd  mov     [rax], edx
0x182d475cf  cmp     qword ptr [rdi+68h], 0
0x182d475d4  jnz     short loc_182D475F4
0x182d475d6  movsx   ecx, sil; Character
0x182d475da  mov     rdx, [rdi+80h]; Stream
0x182d475e1  call    cs:__imp_fputc
0x182d475e7  or      ebx, 0FFFFFFFFh
0x182d475ea  cmp     eax, ebx
0x182d475ec  cmovnz  ebx, esi
0x182d475ef  jmp     loc_182D47796
0x182d475f4  mov     [rbp+57h+var_48], sil
0x182d475f8  mov     [rbp+57h+var_28], 0Fh
0x182d47600  xor     eax, eax
0x182d47602  mov     [rbp+57h+var_30], rax
0x182d47606  mov     byte ptr [rbp+57h+Buffer], al
0x182d47609  xor     r8d, r8d
0x182d4760c  lea     edx, [rax+8]; Size
0x182d4760f  lea     rcx, [rbp+57h+Buffer]; void *
0x182d47613  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KD@Z; std::string::assign(unsigned __int64,char)
0x182d47618  nop
0x182d47619  mov     r8, [rbp+57h+Buffer]
0x182d4761d  mov     r9, [rbp+57h+var_28]
0x182d47621  nop     dword ptr [rax+00h]
0x182d47625  nop     word ptr [rax+rax+00000000h]
0x182d47630  lea     rcx, [rbp+57h+Buffer]
0x182d47634  cmp     r9, 10h
0x182d47638  cmovnb  rcx, r8
0x182d4763c  lea     rdx, [rbp+57h+Buffer]
0x182d47640  cmovnb  rdx, r8
0x182d47644  add     rcx, [rbp+57h+var_30]
0x182d47648  lea     rax, [rbp+57h+var_58]
0x182d4764c  mov     [rsp+0A0h+var_68], rax
0x182d47651  mov     [rsp+0A0h+var_70], rcx
0x182d47656  mov     [rsp+0A0h+var_78], rdx
0x182d4765b  lea     rax, [rbp+57h+var_50]
0x182d4765f  mov     [rsp+0A0h+var_80], rax
0x182d47664  lea     r9, [rbp+57h+var_47]
0x182d47668  lea     r8, [rbp+57h+var_48]
0x182d4766c  lea     rdx, [rdi+74h]
0x182d47670  mov     rcx, [rdi+68h]
0x182d47674  call    cs:__imp_?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::out(_Mbstatet &,char const *,char const *,char const * &,char *,char *,char * &)
0x182d4767a  test    eax, eax
0x182d4767c  js      loc_182D47734
0x182d47682  cmp     eax, 1
0x182d47685  jg      loc_182D4770C
0x182d4768b  lea     rax, [rbp+57h+Buffer]
0x182d4768f  mov     r8, [rbp+57h+Buffer]
0x182d47693  mov     r9, [rbp+57h+var_28]
0x182d47697  cmp     r9, 10h
0x182d4769b  cmovnb  rax, r8
0x182d4769f  mov     rbx, [rbp+57h+var_58]
0x182d476a3  sub     rbx, rax
0x182d476a6  jz      short loc_182D476D6
0x182d476a8  lea     rcx, [rbp+57h+Buffer]
0x182d476ac  cmp     r9, 10h
0x182d476b0  cmovnb  rcx, r8; Buffer
0x182d476b4  mov     r9, [rdi+80h]; Stream
0x182d476bb  mov     r8, rbx; ElementCount
0x182d476be  mov     edx, 1; ElementSize
0x182d476c3  call    cs:__imp_fwrite
0x182d476c9  mov     r9, [rbp+57h+var_28]
0x182d476cd  mov     r8, [rbp+57h+Buffer]
0x182d476d1  cmp     rbx, rax
0x182d476d4  jnz     short loc_182D4773C
0x182d476d6  mov     byte ptr [rdi+71h], 1
0x182d476da  lea     rax, [rbp+57h+var_48]
0x182d476de  cmp     [rbp+57h+var_50], rax
0x182d476e2  jnz     short loc_182D47708
0x182d476e4  test    rbx, rbx
0x182d476e7  jnz     loc_182D47630
0x182d476ed  cmp     [rbp+57h+var_30], 20h ; ' '
0x182d476f2  jnb     short loc_182D4773C
0x182d476f4  xor     r8d, r8d
0x182d476f7  lea     edx, [rbx+8]
0x182d476fa  lea     rcx, [rbp+57h+Buffer]
0x182d476fe  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KD@Z; std::string::append(unsigned __int64,char)
0x182d47703  jmp     loc_182D47619
0x182d47708  mov     ebx, esi
0x182d4770a  jmp     short loc_182D4773F
0x182d4770c  cmp     eax, 3
0x182d4770f  jnz     short loc_182D47734
0x182d47711  movsx   ecx, [rbp+57h+var_48]; Character
0x182d47715  mov     rdx, [rdi+80h]; Stream
0x182d4771c  call    cs:__imp_fputc
0x182d47722  or      ebx, 0FFFFFFFFh
0x182d47725  cmp     eax, ebx
0x182d47727  cmovnz  ebx, esi
0x182d4772a  mov     r9, [rbp+57h+var_28]
0x182d4772e  mov     r8, [rbp+57h+Buffer]
0x182d47732  jmp     short loc_182D4773F
0x182d47734  mov     r9, [rbp+57h+var_28]
0x182d47738  mov     r8, [rbp+57h+Buffer]
0x182d4773c  or      ebx, 0FFFFFFFFh
0x182d4773f  cmp     r9, 10h
0x182d47743  jb      short loc_182D47796
0x182d47745  lea     rax, [r9+1]
0x182d47749  cmp     rax, 1000h
0x182d4774f  jb      short loc_182D4778E
0x182d47751  test    byte ptr [rbp+57h+Buffer], 1Fh
0x182d47755  jz      short loc_182D4775E
0x182d47757  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x182d4775e  mov     rax, [r8-8]
0x182d47762  cmp     rax, r8
0x182d47765  jb      short loc_182D4776E
0x182d47767  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x182d4776e  sub     r8, rax
0x182d47771  cmp     r8, 8
0x182d47775  jnb     short loc_182D4777E
0x182d47777  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x182d4777e  cmp     r8, 27h ; '''
0x182d47782  jbe     short loc_182D4778B
0x182d47784  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x182d4778b  mov     r8, rax
0x182d4778e  mov     rcx, r8; void *
0x182d47791  call    ??3@YAXPEAX@Z; operator delete(void *)
0x182d47796  mov     eax, ebx
0x182d47798  mov     rcx, [rbp+57h+var_20]
0x182d4779c  xor     rcx, rsp; StackCookie
0x182d4779f  call    __security_check_cookie
0x182d477a4  lea     r11, [rsp+0A0h+var_10]
0x182d477ac  mov     rbx, [r11+30h]
0x182d477b0  mov     rsi, [r11+38h]
0x182d477b4  mov     rsp, r11
0x182d477b7  pop     r14
0x182d477b9  pop     rdi
0x182d477ba  pop     rbp
0x182d477bb  retn
```
