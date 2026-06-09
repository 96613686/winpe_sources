# CExec::UpdateEnvironmentMap(std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<void>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14001a640`
- end: `0x14001a8db`
- name: `?UpdateEnvironmentMap@CExec@@YAXAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveLess@Vml@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z`
- size: `667`
- prototype: `void __fastcall(__int64 ***, __int64 ***, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x140016cc0`

## callees

- `0x140002310`
- `0x140006790`
- `0x1400068ac`
- `0x140007a24`
- `0x140008160`
- `0x14000894c`
- `0x140015cdc`
- `0x140015d7c`
- `0x140015e84`
- `0x140015f94`
- `0x14001a640`
- `0x14001abc8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001a69b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001a7e0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001a69b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001a7e0`

## pseudocode

```c
void __fastcall CExec::UpdateEnvironmentMap(__int64 ***a1, __int64 ***a2, _QWORD *a3)
{
  char v5; // bp
  __int64 *v6; // rbx
  __int64 *v7; // rcx
  int v8; // eax
  _QWORD *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 **v12; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 *v15; // rbx
  _QWORD *v16; // rcx
  __int64 **v17; // rcx
  __int64 *k; // rax
  __int64 *m; // rcx
  __int64 v20; // rax
  __int64 v21; // r8
  __int128 Src; // [rsp+20h] [rbp-58h] BYREF
  __int128 v23; // [rsp+30h] [rbp-48h]

  v5 = 0;
  v6 = **a2;
  while ( !*((_BYTE *)v6 + 25) )
  {
    if ( (unsigned __int64)v6[7] <= 7 )
      v7 = v6 + 4;
    else
      v7 = (__int64 *)v6[4];
    v8 = _o__wcsicmp(v7, L"Path");
    if ( v6[10] )
    {
      v9 = v6 + 8;
      if ( v8 )
        goto LABEL_16;
    }
    else
    {
      if ( v8 || !a3[2] )
      {
        std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::erase(
          a1,
          v6 + 4);
        goto LABEL_20;
      }
      v9 = v6 + 8;
    }
    if ( a3[2] )
    {
      v5 = 1;
      std::wstring::wstring(&Src, v9);
      if ( (_QWORD)v23 )
        std::wstring::operator+=(&Src, L";");
      std::wstring::operator+=(&Src);
      v10 = std::map<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>>::operator[](
              a1,
              v6 + 4);
      std::wstring::operator=(v10, &Src);
      std::wstring::~wstring(&Src);
      goto LABEL_20;
    }
LABEL_16:
    v11 = std::map<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>>::operator[](
            a1,
            v6 + 4);
    if ( (_QWORD *)v11 != v9 )
    {
      if ( v9[3] > 7u )
        v9 = (_QWORD *)*v9;
      std::wstring::_Assign<unsigned short>(v11, v9, v6[10]);
    }
LABEL_20:
    v12 = (__int64 **)v6[2];
    if ( *((_BYTE *)v12 + 25) )
    {
      for ( i = (__int64 *)v6[1]; !*((_BYTE *)i + 25) && v6 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v6 = i;
      v6 = i;
    }
    else
    {
      v6 = (__int64 *)v6[2];
      for ( j = *v12; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v6 = j;
    }
  }
  if ( !v5 && a3[2] )
  {
    v15 = **a1;
    while ( !*((_BYTE *)v15 + 25) )
    {
      v16 = v15 + 4;
      if ( (unsigned __int64)v15[7] > 7 )
        v16 = (_QWORD *)*v16;
      if ( !(unsigned int)_o__wcsicmp(v16, L"Path") )
      {
        v5 = 1;
        std::wstring::operator+=(v15 + 8, L";");
        std::wstring::operator+=(v15 + 8);
      }
      v17 = (__int64 **)v15[2];
      if ( *((_BYTE *)v17 + 25) )
      {
        for ( k = (__int64 *)v15[1]; !*((_BYTE *)k + 25) && v15 == (__int64 *)k[2]; k = (__int64 *)k[1] )
          v15 = k;
        v15 = k;
      }
      else
      {
        v15 = (__int64 *)v15[2];
        for ( m = *v17; !*((_BYTE *)m + 25); m = (__int64 *)*m )
          v15 = m;
      }
    }
    if ( !v5 )
    {
      Src = 0;
      v23 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&Src, L"Path", 4);
      v20 = std::map<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>>::operator[](
              a1,
              &Src);
      if ( (_QWORD *)v20 != a3 )
      {
        v21 = a3[2];
        if ( a3[3] > 7u )
          a3 = (_QWORD *)*a3;
        std::wstring::_Assign<unsigned short>(v20, a3, v21);
      }
      std::wstring::~wstring(&Src);
    }
  }
}

```

## disassembly

```asm
0x14001a640  mov     [rsp+arg_8], rbx
0x14001a645  mov     [rsp+arg_18], rbp
0x14001a64a  push    rsi
0x14001a64b  push    rdi
0x14001a64c  push    r12
0x14001a64e  push    r14
0x14001a650  push    r15
0x14001a652  sub     rsp, 50h
0x14001a656  mov     rax, cs:__security_cookie
0x14001a65d  xor     rax, rsp
0x14001a660  mov     [rsp+78h+var_38], rax
0x14001a665  mov     rsi, r8
0x14001a668  mov     r15, rcx
0x14001a66b  xor     r12d, r12d
0x14001a66e  mov     bpl, r12b
0x14001a671  mov     rbx, [rdx]
0x14001a674  mov     rbx, [rbx]
0x14001a677  cmp     [rbx+19h], r12b
0x14001a67b  jnz     loc_14001A7A8
0x14001a681  lea     r14, [rbx+20h]
0x14001a685  cmp     qword ptr [rbx+38h], 7
0x14001a68a  jbe     short loc_14001A691
0x14001a68c  mov     rcx, [r14]
0x14001a68f  jmp     short loc_14001A694
0x14001a691  mov     rcx, r14
0x14001a694  lea     rdx, aPath_0; "Path"
0x14001a69b  call    cs:__imp__o__wcsicmp
0x14001a6a1  cmp     [rbx+50h], r12
0x14001a6a5  jnz     short loc_14001A6C7
0x14001a6a7  test    eax, eax
0x14001a6a9  jnz     short loc_14001A6B7
0x14001a6ab  cmp     [rsi+10h], r12
0x14001a6af  jz      short loc_14001A6B7
0x14001a6b1  lea     rdi, [rbx+40h]
0x14001a6b5  jmp     short loc_14001A6CF
0x14001a6b7  mov     rdx, r14
0x14001a6ba  mov     rcx, r15
0x14001a6bd  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveLess@Vml@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::erase(std::wstring const &)
0x14001a6c2  jmp     loc_14001A759
0x14001a6c7  lea     rdi, [rbx+40h]
0x14001a6cb  test    eax, eax
0x14001a6cd  jnz     short loc_14001A730
0x14001a6cf  cmp     [rsi+10h], r12
0x14001a6d3  jz      short loc_14001A730
0x14001a6d5  mov     bpl, 1
0x14001a6d8  mov     rdx, rdi
0x14001a6db  lea     rcx, [rsp+78h+Src]
0x14001a6e0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14001a6e5  nop
0x14001a6e6  cmp     qword ptr [rsp+78h+var_48], r12
0x14001a6eb  jz      short loc_14001A6FE
0x14001a6ed  lea     rdx, asc_140028B24; ";"
0x14001a6f4  lea     rcx, [rsp+78h+Src]; Src
0x14001a6f9  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x14001a6fe  mov     rdx, rsi
0x14001a701  lea     rcx, [rsp+78h+Src]; Src
0x14001a706  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x14001a70b  mov     rdx, r14
0x14001a70e  mov     rcx, r15
0x14001a711  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveLess@Vml@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::map<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>>::operator[](std::wstring const &)
0x14001a716  mov     rcx, rax
0x14001a719  lea     rdx, [rsp+78h+Src]
0x14001a71e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14001a723  nop
0x14001a724  lea     rcx, [rsp+78h+Src]
0x14001a729  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001a72e  jmp     short loc_14001A759
0x14001a730  mov     rdx, r14
0x14001a733  mov     rcx, r15
0x14001a736  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveLess@Vml@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::map<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>>::operator[](std::wstring const &)
0x14001a73b  cmp     rax, rdi
0x14001a73e  jz      short loc_14001A759
0x14001a740  cmp     qword ptr [rdi+18h], 7
0x14001a745  jbe     short loc_14001A74A
0x14001a747  mov     rdi, [rdi]
0x14001a74a  mov     r8, [rbx+50h]
0x14001a74e  mov     rdx, rdi
0x14001a751  mov     rcx, rax
0x14001a754  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x14001a759  mov     rcx, [rbx+10h]
0x14001a75d  cmp     [rcx+19h], r12b
0x14001a761  jz      short loc_14001A784
0x14001a763  mov     rax, [rbx+8]
0x14001a767  jmp     short loc_14001A776
0x14001a769  cmp     rbx, [rax+10h]
0x14001a76d  jnz     short loc_14001A77C
0x14001a76f  mov     rbx, rax
0x14001a772  mov     rax, [rax+8]
0x14001a776  cmp     [rax+19h], r12b
0x14001a77a  jz      short loc_14001A769
0x14001a77c  mov     rbx, rax
0x14001a77f  jmp     loc_14001A677
0x14001a784  mov     rbx, rcx
0x14001a787  mov     rcx, [rcx]
0x14001a78a  cmp     [rcx+19h], r12b
0x14001a78e  jnz     loc_14001A677
0x14001a794  mov     rbx, rcx
0x14001a797  mov     rax, [rcx]
0x14001a79a  mov     rcx, rax
0x14001a79d  cmp     [rax+19h], r12b
0x14001a7a1  jz      short loc_14001A794
0x14001a7a3  jmp     loc_14001A677
0x14001a7a8  test    bpl, bpl
0x14001a7ab  jnz     loc_14001A8B5
0x14001a7b1  cmp     [rsi+10h], r12
0x14001a7b5  jz      loc_14001A8B5
0x14001a7bb  mov     rbx, [r15]
0x14001a7be  mov     rbx, [rbx]
0x14001a7c1  cmp     [rbx+19h], r12b
0x14001a7c5  jnz     loc_14001A851
0x14001a7cb  lea     rcx, [rbx+20h]
0x14001a7cf  cmp     qword ptr [rbx+38h], 7
0x14001a7d4  jbe     short loc_14001A7D9
0x14001a7d6  mov     rcx, [rcx]
0x14001a7d9  lea     rdx, aPath_0; "Path"
0x14001a7e0  call    cs:__imp__o__wcsicmp
0x14001a7e6  test    eax, eax
0x14001a7e8  jnz     short loc_14001A809
0x14001a7ea  mov     bpl, 1
0x14001a7ed  lea     rdx, asc_140028B24; ";"
0x14001a7f4  lea     rcx, [rbx+40h]; Src
0x14001a7f8  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x14001a7fd  mov     rdx, rsi
0x14001a800  lea     rcx, [rbx+40h]; Src
0x14001a804  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x14001a809  mov     rcx, [rbx+10h]
0x14001a80d  cmp     [rcx+19h], r12b
0x14001a811  jz      short loc_14001A831
0x14001a813  mov     rax, [rbx+8]
0x14001a817  jmp     short loc_14001A826
0x14001a819  cmp     rbx, [rax+10h]
0x14001a81d  jnz     short loc_14001A82C
0x14001a81f  mov     rbx, rax
0x14001a822  mov     rax, [rax+8]
0x14001a826  cmp     [rax+19h], r12b
0x14001a82a  jz      short loc_14001A819
0x14001a82c  mov     rbx, rax
0x14001a82f  jmp     short loc_14001A7C1
0x14001a831  mov     rbx, rcx
0x14001a834  mov     rcx, [rcx]
0x14001a837  cmp     [rcx+19h], r12b
0x14001a83b  jnz     short loc_14001A7C1
0x14001a83d  mov     rbx, rcx
0x14001a840  mov     rax, [rcx]
0x14001a843  mov     rcx, rax
0x14001a846  cmp     [rax+19h], r12b
0x14001a84a  jz      short loc_14001A83D
0x14001a84c  jmp     loc_14001A7C1
0x14001a851  test    bpl, bpl
0x14001a854  jnz     short loc_14001A8B5
0x14001a856  xorps   xmm0, xmm0
0x14001a859  movups  [rsp+78h+Src], xmm0
0x14001a85e  xorps   xmm1, xmm1
0x14001a861  movdqu  [rsp+78h+var_48], xmm1
0x14001a867  mov     r8d, 4
0x14001a86d  lea     rdx, aPath_0; "Path"
0x14001a874  lea     rcx, [rsp+78h+Src]
0x14001a879  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14001a87e  nop
0x14001a87f  lea     rdx, [rsp+78h+Src]
0x14001a884  mov     rcx, r15
0x14001a887  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveLess@Vml@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>>::operator[](std::wstring &&)
0x14001a88c  cmp     rax, rsi
0x14001a88f  jz      short loc_14001A8AB
0x14001a891  mov     r8, [rsi+10h]
0x14001a895  cmp     qword ptr [rsi+18h], 7
0x14001a89a  jbe     short loc_14001A89F
0x14001a89c  mov     rsi, [rsi]
0x14001a89f  mov     rdx, rsi
0x14001a8a2  mov     rcx, rax
0x14001a8a5  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x14001a8aa  nop
0x14001a8ab  lea     rcx, [rsp+78h+Src]
0x14001a8b0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001a8b5  mov     rcx, [rsp+78h+var_38]
0x14001a8ba  xor     rcx, rsp; StackCookie
0x14001a8bd  call    __security_check_cookie
0x14001a8c2  lea     r11, [rsp+78h+var_28]
0x14001a8c7  mov     rbx, [r11+38h]
0x14001a8cb  mov     rbp, [r11+48h]
0x14001a8cf  mov     rsp, r11
0x14001a8d2  pop     r15
0x14001a8d4  pop     r14
0x14001a8d6  pop     r12
0x14001a8d8  pop     rdi
0x14001a8d9  pop     rsi
0x14001a8da  retn
```
