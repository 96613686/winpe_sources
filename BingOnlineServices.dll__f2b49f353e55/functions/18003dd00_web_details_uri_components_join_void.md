# web::details::uri_components::join(void)

- ea: `0x18003dd00`
- end: `0x18003df97`
- name: `?join@uri_components@details@web@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `663`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18003cc20`
- `0x18003cd00`
- `0x180050b10`
- `0x180050bd0`

## callees

- `0x18000130c`
- `0x18000a228`
- `0x18000e5a8`
- `0x180015914`
- `0x1800167f8`
- `0x1800177f8`
- `0x18001a384`
- `0x18001b200`
- `0x18001e604`
- `0x18003cecc`
- `0x18003dc2c`
- `0x18003dd00`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x18003ded4`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x18003ded4`
- `msvcp_win!?classic@locale@std@@SAAEBV12@XZ` at `0x18003de2b`
- `msvcp_win!?classic@locale@std@@SAAEBV12@XZ` at `0x18003de2b`
- `msvcp_win!?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z` at `0x18003de3c`
- `msvcp_win!?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z` at `0x18003de3c`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x18003dd5f`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x18003ddb0`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x18003dd5f`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x18003ddb0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall web::details::uri_components::join(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  unsigned __int16 *v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // rax
  __int64 v8; // rdx
  unsigned __int16 *v9; // r14
  _WORD *v10; // rsi
  unsigned __int16 *v11; // rbx
  __int64 v12; // r15
  _WORD *v13; // rsi
  __int64 v14; // rcx
  __int64 v15; // r9
  __int64 v16; // rax
  __int64 v17; // r9
  char *v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  _BYTE v26[24]; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v27; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v28[232]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+180h] [rbp+78h] BYREF

  v29 = a2;
  _lambda_579bf79f6e7ba7d94ac2d551d7420f1d_::_lambda_579bf79f6e7ba7d94ac2d551d7420f1d_(&v29, a1);
  v5 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4);
  v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6);
  v9 = (unsigned __int16 *)(v7 + 2LL * *(_QWORD *)(v8 + 16));
  v10 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8);
  while ( v5 != v9 )
    *v10++ = _o_tolower(*v5++);
  _lambda_579bf79f6e7ba7d94ac2d551d7420f1d_::_lambda_579bf79f6e7ba7d94ac2d551d7420f1d_(&v29, a1);
  v11 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 32);
  v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 32) + 2LL * *(_QWORD *)(a1 + 48);
  v13 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 32);
  while ( v11 != (unsigned __int16 *)v12 )
    *v13++ = _o_tolower(*v11++);
  if ( *(_QWORD *)(a1 + 48) )
  {
    v14 = a1 + 96;
    if ( *(_QWORD *)(a1 + 112) )
    {
      if ( *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14) != 47 )
      {
        v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
        std::wstring::insert(v17, &v29, v16);
      }
    }
    else
    {
      std::wstring::assign(v14, L"/");
    }
  }
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(&v27);
  v18 = &v28[*(int *)(v27 + 4) - 8];
  v19 = std::locale::classic();
  std::basic_ios<unsigned short>::imbue(v18, v26, v19);
  std::locale::~locale((std::locale *)v26);
  if ( *(_QWORD *)(a1 + 16) )
  {
    v20 = std::operator<<<unsigned short>(&v27, a1);
    std::basic_ostream<unsigned short>::operator<<(v20, 58);
  }
  if ( *(_QWORD *)(a1 + 48) )
  {
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v27, L"//");
    if ( *(_QWORD *)(a1 + 80) )
    {
      v21 = std::operator<<<unsigned short>(&v27, a1 + 64);
      std::basic_ostream<unsigned short>::operator<<(v21, 64);
    }
    std::operator<<<unsigned short>(&v27, a1 + 32);
    if ( *(int *)(a1 + 192) > 0 )
    {
      v22 = std::basic_ostream<unsigned short>::operator<<(&v27, 58);
      std::basic_ostream<unsigned short>::operator<<(v22, *(unsigned int *)(a1 + 192));
    }
  }
  if ( *(_QWORD *)(a1 + 112) )
  {
    if ( *(_QWORD *)(a1 + 48) && *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 96) != 47 )
      std::basic_ostream<unsigned short>::operator<<(&v27, 47);
    std::operator<<<unsigned short>(&v27, a1 + 96);
  }
  if ( *(_QWORD *)(a1 + 144) )
  {
    v23 = std::basic_ostream<unsigned short>::operator<<(&v27, 63);
    std::operator<<<unsigned short>(v23, a1 + 128);
  }
  if ( *(_QWORD *)(a1 + 176) )
  {
    v24 = std::basic_ostream<unsigned short>::operator<<(&v27, 35);
    std::operator<<<unsigned short>(v24, a1 + 160);
  }
  std::basic_stringbuf<unsigned short>::str(v28, a2);
  std::basic_ostringstream<unsigned short>::`vbase destructor'(&v27);
  return a2;
}

```

## disassembly

```asm
0x18003dd00  mov     rax, rsp
0x18003dd03  mov     [rax+8], rbx
0x18003dd07  mov     [rax+18h], rsi
0x18003dd0b  mov     [rax+10h], rdx
0x18003dd0f  push    rbp
0x18003dd10  push    rdi
0x18003dd11  push    r12
0x18003dd13  push    r14
0x18003dd15  push    r15
0x18003dd17  lea     rbp, [rax-68h]
0x18003dd1b  sub     rsp, 140h
0x18003dd22  mov     r12, rdx
0x18003dd25  mov     rdi, rcx
0x18003dd28  mov     rdx, rcx
0x18003dd2b  lea     rcx, [rbp+60h+arg_8]
0x18003dd2f  call    ??0_lambda_579bf79f6e7ba7d94ac2d551d7420f1d_@@QEAA@PEAU?$_Task_impl@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@details@pplx@@@Z; _lambda_579bf79f6e7ba7d94ac2d551d7420f1d_::_lambda_579bf79f6e7ba7d94ac2d551d7420f1d_(pplx::details::_Task_impl<std::wstring> *)
0x18003dd34  mov     rcx, rdx
0x18003dd37  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003dd3c  mov     rbx, rax
0x18003dd3f  mov     rcx, rdx
0x18003dd42  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003dd47  mov     rcx, [rdx+10h]
0x18003dd4b  lea     r14, [rax+rcx*2]
0x18003dd4f  mov     rcx, rdx
0x18003dd52  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003dd57  mov     rsi, rax
0x18003dd5a  jmp     short loc_18003DD70
0x18003dd5c  movzx   ecx, word ptr [rbx]
0x18003dd5f  call    cs:__imp__o_tolower
0x18003dd65  mov     [rsi], ax
0x18003dd68  lea     rsi, [rsi+2]
0x18003dd6c  add     rbx, 2
0x18003dd70  cmp     rbx, r14
0x18003dd73  jnz     short loc_18003DD5C
0x18003dd75  mov     rdx, rdi
0x18003dd78  lea     rcx, [rbp+60h+arg_8]
0x18003dd7c  call    ??0_lambda_579bf79f6e7ba7d94ac2d551d7420f1d_@@QEAA@PEAU?$_Task_impl@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@details@pplx@@@Z; _lambda_579bf79f6e7ba7d94ac2d551d7420f1d_::_lambda_579bf79f6e7ba7d94ac2d551d7420f1d_(pplx::details::_Task_impl<std::wstring> *)
0x18003dd81  lea     r14, [rdi+20h]
0x18003dd85  mov     rcx, r14
0x18003dd88  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003dd8d  mov     rbx, rax
0x18003dd90  mov     rcx, r14
0x18003dd93  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003dd98  mov     rcx, [r14+10h]
0x18003dd9c  lea     r15, [rax+rcx*2]
0x18003dda0  mov     rcx, r14
0x18003dda3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003dda8  mov     rsi, rax
0x18003ddab  jmp     short loc_18003DDC1
0x18003ddad  movzx   ecx, word ptr [rbx]
0x18003ddb0  call    cs:__imp__o_tolower
0x18003ddb6  mov     [rsi], ax
0x18003ddb9  lea     rsi, [rsi+2]
0x18003ddbd  add     rbx, 2
0x18003ddc1  cmp     rbx, r15
0x18003ddc4  jnz     short loc_18003DDAD
0x18003ddc6  mov     esi, 2Fh ; '/'
0x18003ddcb  cmp     qword ptr [rdi+30h], 0
0x18003ddd0  jz      short loc_18003DE0F
0x18003ddd2  lea     r9, [rdi+60h]
0x18003ddd6  mov     rcx, r9
0x18003ddd9  cmp     qword ptr [r9+10h], 0
0x18003ddde  jnz     short loc_18003DDEE
0x18003dde0  lea     rdx, asc_180068A6C; "/"
0x18003dde7  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18003ddec  jmp     short loc_18003DE0F
0x18003ddee  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003ddf3  cmp     [rax], si
0x18003ddf6  jz      short loc_18003DE0F
0x18003ddf8  mov     rcx, r9
0x18003ddfb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003de00  mov     r8, rax
0x18003de03  lea     rdx, [rbp+60h+arg_8]
0x18003de07  mov     rcx, r9
0x18003de0a  call    ?insert@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@_KG@Z; std::wstring::insert(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,unsigned __int64,ushort)
0x18003de0f  lea     rcx, [rsp+160h+var_110]
0x18003de14  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18003de19  nop
0x18003de1a  mov     rax, [rsp+160h+var_110]
0x18003de1f  movsxd  rcx, dword ptr [rax+4]
0x18003de23  lea     rbx, [rsp+160h+var_110]
0x18003de28  add     rbx, rcx
0x18003de2b  call    cs:__imp_?classic@locale@std@@SAAEBV12@XZ; std::locale::classic(void)
0x18003de31  mov     r8, rax
0x18003de34  lea     rdx, [rsp+160h+var_128]
0x18003de39  mov     rcx, rbx
0x18003de3c  call    cs:__imp_?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z; std::basic_ios<ushort>::imbue(std::locale const &)
0x18003de42  lea     rcx, [rsp+160h+var_128]; this
0x18003de47  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x18003de4c  mov     ebx, 3Ah ; ':'
0x18003de51  cmp     qword ptr [rdi+10h], 0
0x18003de56  jz      short loc_18003DE6F
0x18003de58  mov     rdx, rdi
0x18003de5b  lea     rcx, [rsp+160h+var_110]
0x18003de60  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18003de65  mov     edx, ebx
0x18003de67  mov     rcx, rax
0x18003de6a  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x18003de6f  cmp     qword ptr [rdi+30h], 0
0x18003de74  jz      short loc_18003DEDA
0x18003de76  lea     rdx, asc_180069540; "//"
0x18003de7d  lea     rcx, [rsp+160h+var_110]
0x18003de82  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18003de87  lea     rdx, [rdi+40h]
0x18003de8b  cmp     qword ptr [rdx+10h], 0
0x18003de90  jz      short loc_18003DEA9
0x18003de92  lea     rcx, [rsp+160h+var_110]
0x18003de97  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18003de9c  mov     edx, 40h ; '@'
0x18003dea1  mov     rcx, rax
0x18003dea4  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x18003dea9  mov     rdx, r14
0x18003deac  lea     rcx, [rsp+160h+var_110]
0x18003deb1  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18003deb6  cmp     dword ptr [rdi+0C0h], 0
0x18003debd  jle     short loc_18003DEDA
0x18003debf  mov     edx, ebx
0x18003dec1  lea     rcx, [rsp+160h+var_110]
0x18003dec6  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x18003decb  mov     edx, [rdi+0C0h]
0x18003ded1  mov     rcx, rax
0x18003ded4  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x18003deda  cmp     qword ptr [rdi+70h], 0
0x18003dedf  jz      short loc_18003DF10
0x18003dee1  cmp     qword ptr [rdi+30h], 0
0x18003dee6  jz      short loc_18003DF02
0x18003dee8  lea     rcx, [rdi+60h]
0x18003deec  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003def1  cmp     [rax], si
0x18003def4  jz      short loc_18003DF02
0x18003def6  mov     edx, esi
0x18003def8  lea     rcx, [rsp+160h+var_110]
0x18003defd  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x18003df02  lea     rdx, [rdi+60h]
0x18003df06  lea     rcx, [rsp+160h+var_110]
0x18003df0b  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18003df10  lea     rbx, [rdi+80h]
0x18003df17  cmp     qword ptr [rbx+10h], 0
0x18003df1c  jz      short loc_18003DF38
0x18003df1e  mov     edx, 3Fh ; '?'
0x18003df23  lea     rcx, [rsp+160h+var_110]
0x18003df28  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x18003df2d  mov     rcx, rax
0x18003df30  mov     rdx, rbx
0x18003df33  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18003df38  cmp     qword ptr [rdi+0B0h], 0
0x18003df40  jz      short loc_18003DF60
0x18003df42  mov     edx, 23h ; '#'
0x18003df47  lea     rcx, [rsp+160h+var_110]
0x18003df4c  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x18003df51  mov     rcx, rax
0x18003df54  lea     rdx, [rdi+0A0h]
0x18003df5b  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18003df60  mov     rdx, r12
0x18003df63  lea     rcx, [rsp+160h+var_108]
0x18003df68  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18003df6d  nop
0x18003df6e  lea     rcx, [rsp+160h+var_110]
0x18003df73  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x18003df78  mov     rax, r12
0x18003df7b  lea     r11, [rsp+160h+var_20]
0x18003df83  mov     rbx, [r11+30h]
0x18003df87  mov     rsi, [r11+40h]
0x18003df8b  mov     rsp, r11
0x18003df8e  pop     r15
0x18003df90  pop     r14
0x18003df92  pop     r12
0x18003df94  pop     rdi
0x18003df95  pop     rbp
0x18003df96  retn
```
