# BookmarkXmlParser::DoTransition(int,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)

- ea: `0x180018d70`
- end: `0x18001942e`
- name: `?DoTransition@BookmarkXmlParser@@EEAADHV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z`
- size: `1726`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180018348`

## callees

- `0x18000bf84`
- `0x180018d70`
- `0x1800194c8`
- `0x1800195a8`
- `0x180022214`
- `0x180023548`
- `0x180023a28`
- `0x18002dfbc`
- `0x180038fb4`

## pseudocode

```c
char __fastcall BookmarkXmlParser::DoTransition(__int64 a1, __int64 a2, _QWORD *a3)
{
  char v5; // al
  __int64 v6; // rcx
  char v7; // r14
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // r15
  __int64 v13; // rdx
  __int64 v14; // rax
  _QWORD *v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int128 v19; // [rsp+30h] [rbp-40h] BYREF
  __int128 pExceptionObject; // [rsp+40h] [rbp-30h] BYREF
  __int64 v21; // [rsp+50h] [rbp-20h]
  int v22; // [rsp+58h] [rbp-18h]
  int v23; // [rsp+5Ch] [rbp-14h]
  int v24; // [rsp+60h] [rbp-10h]
  __int64 v25; // [rsp+A0h] [rbp+30h] BYREF
  unsigned __int64 v26; // [rsp+A8h] [rbp+38h] BYREF

  v19 = *(_OWORD *)a3;
  v5 = XTransition::DoTransition(a1, a2, &v19);
  v7 = v5;
  if ( v5 == -3 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_d919bee969333976452e2f12f271af1f_Traceguids, 87);
    }
    v21 = 0;
    v22 = 87;
    v23 = -1;
    pExceptionObject = 0;
    v24 = 230;
    throw (EvtException *)&pExceptionObject;
  }
  if ( v5 == 4 )
  {
    *((_QWORD *)&v19 + 1) = 7;
    *(_QWORD *)&v19 = L"forward";
    if ( (unsigned __int8)tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,wchar_t,wchar_t,0>(
                            v6,
                            a3,
                            &v19) )
    {
      *(_DWORD *)(*(_QWORD *)(a1 + 24) + 36LL) = 0;
    }
    else
    {
      *((_QWORD *)&v19 + 1) = 8;
      *(_QWORD *)&v19 = L"backward";
      if ( !(unsigned __int8)tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,wchar_t,wchar_t,0>(
                               v17,
                               a3,
                               &v19) )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_d919bee969333976452e2f12f271af1f_Traceguids, 13);
        }
        v21 = 0;
        v22 = 13;
        v23 = -1;
        pExceptionObject = 0;
        v24 = 150;
        throw (EvtException *)&pExceptionObject;
      }
      *(_DWORD *)(*(_QWORD *)(a1 + 24) + 36LL) = 1;
    }
  }
  else
  {
    if ( v5 != 8 )
    {
      if ( v5 == 13 )
      {
        v15 = (_QWORD *)(*(_QWORD *)(**(_QWORD **)(a1 + 24) + 24LL) - 32LL);
        if ( *v15 != v15[1] )
        {
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_d919bee969333976452e2f12f271af1f_Traceguids, 87);
          }
          v21 = 0;
          v22 = 87;
          v23 = -1;
          pExceptionObject = 0;
          v24 = 182;
          throw (EvtException *)&pExceptionObject;
        }
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                 v15,
                                 *a3,
                                 a3[1]) )
        {
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_d919bee969333976452e2f12f271af1f_Traceguids, 14);
          }
          v21 = 0;
          v22 = 14;
          v23 = -1;
          pExceptionObject = 0;
          v24 = 175;
          throw (EvtException *)&pExceptionObject;
        }
      }
      else
      {
        if ( v5 != 17 )
        {
          if ( v5 == 21 )
          {
            *((_QWORD *)&v19 + 1) = 4;
            *(_QWORD *)&v19 = L"true";
            if ( (unsigned __int8)tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,wchar_t,wchar_t,0>(
                                    v6,
                                    a3,
                                    &v19)
              || (*((_QWORD *)&v19 + 1) = 1,
                  *(_QWORD *)&v19 = L"1",
                  (unsigned __int8)tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,wchar_t,wchar_t,0>(
                                     v8,
                                     a3,
                                     &v19)) )
            {
              v11 = *(_QWORD *)(a1 + 24);
              if ( *(_DWORD *)(v11 + 32) != -1 )
              {
                if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_D(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    17,
                    &WPP_d919bee969333976452e2f12f271af1f_Traceguids,
                    87);
                }
                v21 = 0;
                v22 = 87;
                v23 = -1;
                pExceptionObject = 0;
                v24 = 216;
                throw (EvtException *)&pExceptionObject;
              }
              *(_DWORD *)(v11 + 32) = ((__int64)(*(_QWORD *)(v11 + 16) - *(_QWORD *)(v11 + 8)) >> 3) - 1;
            }
            else
            {
              *((_QWORD *)&v19 + 1) = 5;
              *(_QWORD *)&v19 = L"false";
              if ( !(unsigned __int8)tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,wchar_t,wchar_t,0>(
                                       v9,
                                       a3,
                                       &v19) )
              {
                *((_QWORD *)&v19 + 1) = 1;
                *(_QWORD *)&v19 = L"0";
                if ( !(unsigned __int8)tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,wchar_t,wchar_t,0>(
                                         v10,
                                         a3,
                                         &v19) )
                {
                  if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_D(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      18,
                      &WPP_d919bee969333976452e2f12f271af1f_Traceguids,
                      87);
                  }
                  v21 = 0;
                  v22 = 87;
                  v23 = -1;
                  pExceptionObject = 0;
                  v24 = 222;
                  throw (EvtException *)&pExceptionObject;
                }
              }
            }
          }
          return v7;
        }
        v12 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL);
        if ( *(_QWORD *)(v12 - 8) != -1 )
        {
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_d919bee969333976452e2f12f271af1f_Traceguids, 87);
          }
          v21 = 0;
          v22 = 87;
          v23 = -1;
          pExceptionObject = 0;
          v24 = 202;
          throw (EvtException *)&pExceptionObject;
        }
        v13 = *a3;
        v14 = a3[1];
        v26 = 0;
        LOBYTE(v25) = 0;
        if ( *(_DWORD *)(utl::_FromCharsImpl<utl::from_wchars_result,unsigned __int64,wchar_t>(
                           (unsigned int)&v19,
                           v13,
                           (int)v13 + 2 * (int)v14,
                           (unsigned int)&v26)
                       + 8)
          || v26 > (unsigned __int64)(unsigned __int8)v25 + 0x7FFFFFFFFFFFFFFFLL )
        {
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_d919bee969333976452e2f12f271af1f_Traceguids, 87);
          }
          v21 = 0;
          v22 = 87;
          v23 = -1;
          pExceptionObject = 0;
          v24 = 195;
          throw (EvtException *)&pExceptionObject;
        }
        *(_QWORD *)(v12 - 8) = (unsigned __int8)v25 + (v26 ^ -(__int64)(unsigned __int8)v25);
      }
      ++*(_DWORD *)(a1 + 32);
      return v7;
    }
    if ( *(_DWORD *)(a1 + 32) != 2 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_d919bee969333976452e2f12f271af1f_Traceguids, 87);
      }
      v21 = 0;
      v22 = 87;
      v23 = -1;
      pExceptionObject = 0;
      v24 = 165;
      throw (EvtException *)&pExceptionObject;
    }
    if ( !(unsigned __int8)utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::emplace_back<wchar_t const (&)[1],0>(**(_QWORD **)(a1 + 24) + 16LL)
      || (v16 = *(_QWORD *)(a1 + 24) + 8LL,
          v25 = -1,
          !(unsigned __int8)utl::vector<__int64,utl::allocator<__int64>>::_PushBackOne<__int64>(v16, &v25)) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_d919bee969333976452e2f12f271af1f_Traceguids, 14);
      }
      v21 = 0;
      v22 = 14;
      v23 = -1;
      pExceptionObject = 0;
      v24 = 159;
      throw (EvtException *)&pExceptionObject;
    }
    *(_DWORD *)(a1 + 32) = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180018d70  mov     [rsp-18h+arg_0], rsi
0x180018d75  mov     [rsp-18h+arg_8], rdi
0x180018d7a  push    rbp
0x180018d7b  push    r14
0x180018d7d  push    r15
0x180018d7f  mov     rbp, rsp
0x180018d82  sub     rsp, 70h
0x180018d86  movups  xmm0, xmmword ptr [r8]
0x180018d8a  mov     rsi, r8
0x180018d8d  mov     rdi, rcx
0x180018d90  lea     r8, [rbp+var_40]
0x180018d94  movdqu  [rbp+var_40], xmm0
0x180018d99  call    ?DoTransition@XTransition@@MEAADHV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; XTransition::DoTransition(int,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x180018d9e  mov     r14b, al
0x180018da1  cmp     al, 0FDh
0x180018da3  jz      loc_1800193C2
0x180018da9  cmp     al, 4
0x180018dab  jz      loc_1800192DD
0x180018db1  cmp     al, 8
0x180018db3  jz      loc_1800191BC
0x180018db9  cmp     al, 0Dh
0x180018dbb  jz      loc_1800190B2
0x180018dc1  cmp     al, 11h
0x180018dc3  jz      loc_180018F65
0x180018dc9  cmp     al, 15h
0x180018dcb  jnz     loc_18001933B
0x180018dd1  lea     rax, aTrue; "true"
0x180018dd8  mov     qword ptr [rbp+var_40+8], 4
0x180018de0  lea     r8, [rbp+var_40]
0x180018de4  mov     qword ptr [rbp+var_40], rax
0x180018de8  mov     rdx, rsi
0x180018deb  call    ??$?RV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V01@_W_W$0A@@?$string_equal_to_base@Uascii_toupper_transform@tlx@@@tlx@@QEBA_NAEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0@Z; tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,wchar_t,wchar_t,0>(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x180018df0  test    al, al
0x180018df2  jnz     loc_180018ED9
0x180018df8  lea     rax, a1; "1"
0x180018dff  mov     qword ptr [rbp+var_40+8], 1
0x180018e07  lea     r8, [rbp+var_40]
0x180018e0b  mov     qword ptr [rbp+var_40], rax
0x180018e0f  mov     rdx, rsi
0x180018e12  call    ??$?RV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V01@_W_W$0A@@?$string_equal_to_base@Uascii_toupper_transform@tlx@@@tlx@@QEBA_NAEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0@Z; tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,wchar_t,wchar_t,0>(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x180018e17  test    al, al
0x180018e19  jnz     loc_180018ED9
0x180018e1f  lea     rax, aFalse; "false"
0x180018e26  mov     qword ptr [rbp+var_40+8], 5
0x180018e2e  lea     r8, [rbp+var_40]
0x180018e32  mov     qword ptr [rbp+var_40], rax
0x180018e36  mov     rdx, rsi
0x180018e39  call    ??$?RV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V01@_W_W$0A@@?$string_equal_to_base@Uascii_toupper_transform@tlx@@@tlx@@QEBA_NAEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0@Z; tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,wchar_t,wchar_t,0>(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x180018e3e  test    al, al
0x180018e40  jnz     loc_18001933B
0x180018e46  lea     rax, a0; "0"
0x180018e4d  mov     qword ptr [rbp+var_40+8], 1
0x180018e55  lea     r8, [rbp+var_40]
0x180018e59  mov     qword ptr [rbp+var_40], rax
0x180018e5d  mov     rdx, rsi
0x180018e60  call    ??$?RV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V01@_W_W$0A@@?$string_equal_to_base@Uascii_toupper_transform@tlx@@@tlx@@QEBA_NAEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0@Z; tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,wchar_t,wchar_t,0>(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x180018e65  test    al, al
0x180018e67  jnz     loc_18001933B
0x180018e6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180018e74  lea     rax, WPP_GLOBAL_Control
0x180018e7b  mov     edi, 57h ; 'W'
0x180018e80  cmp     rcx, rax
0x180018e83  jz      short loc_180018EA7
0x180018e85  test    byte ptr [rcx+1Ch], 2
0x180018e89  jz      short loc_180018EA7
0x180018e8b  cmp     byte ptr [rcx+19h], 2
0x180018e8f  jb      short loc_180018EA7
0x180018e91  mov     rcx, [rcx+10h]
0x180018e95  lea     edx, [rdi-45h]
0x180018e98  mov     r9d, edi
0x180018e9b  lea     r8, WPP_d919bee969333976452e2f12f271af1f_Traceguids
0x180018ea2  call    WPP_SF_D
0x180018ea7  xorps   xmm0, xmm0
0x180018eaa  mov     [rbp+var_20], 0
0x180018eb2  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180018eb9  mov     [rbp+var_18], edi
0x180018ebc  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180018ec0  mov     [rbp+var_14], 0FFFFFFFFh
0x180018ec7  movdqu  [rbp+pExceptionObject], xmm0
0x180018ecc  mov     [rbp+var_10], 0DEh
0x180018ed3  call    _CxxThrowException_0
0x180018ed9  mov     rcx, [rdi+18h]
0x180018edd  cmp     dword ptr [rcx+20h], 0FFFFFFFFh
0x180018ee1  jnz     short loc_180018EF9
0x180018ee3  mov     rax, [rcx+10h]
0x180018ee7  sub     rax, [rcx+8]
0x180018eeb  sar     rax, 3
0x180018eef  dec     eax
0x180018ef1  mov     [rcx+20h], eax
0x180018ef4  jmp     loc_18001933B
0x180018ef9  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f00  lea     rax, WPP_GLOBAL_Control
0x180018f07  mov     edi, 57h ; 'W'
0x180018f0c  cmp     rcx, rax
0x180018f0f  jz      short loc_180018F33
0x180018f11  test    byte ptr [rcx+1Ch], 2
0x180018f15  jz      short loc_180018F33
0x180018f17  cmp     byte ptr [rcx+19h], 2
0x180018f1b  jb      short loc_180018F33
0x180018f1d  mov     rcx, [rcx+10h]
0x180018f21  lea     edx, [rdi-46h]
0x180018f24  mov     r9d, edi
0x180018f27  lea     r8, WPP_d919bee969333976452e2f12f271af1f_Traceguids
0x180018f2e  call    WPP_SF_D
0x180018f33  xorps   xmm0, xmm0
0x180018f36  mov     [rbp+var_20], 0
0x180018f3e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180018f45  mov     [rbp+var_18], edi
0x180018f48  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180018f4c  mov     [rbp+var_14], 0FFFFFFFFh
0x180018f53  movdqu  [rbp+pExceptionObject], xmm0
0x180018f58  mov     [rbp+var_10], 0D8h
0x180018f5f  call    _CxxThrowException_0
0x180018f65  mov     rax, [rdi+18h]
0x180018f69  mov     r15, [rax+10h]
0x180018f6d  cmp     qword ptr [r15-8], 0FFFFFFFFFFFFFFFFh
0x180018f72  jnz     loc_180019046
0x180018f78  mov     rdx, [rsi]
0x180018f7b  lea     r9, [rbp+arg_18]
0x180018f7f  mov     rax, [rsi+8]
0x180018f83  lea     rcx, [rbp+var_40]
0x180018f87  mov     [rbp+arg_18], 0
0x180018f8f  mov     byte ptr [rbp+arg_10], 0
0x180018f93  lea     r8, [rdx+rax*2]
0x180018f97  lea     rax, [rbp+arg_10]
0x180018f9b  mov     [rsp+70h+var_48], rax
0x180018fa0  call    ??$_FromCharsImpl@Ufrom_wchars_result@utl@@_K_W@utl@@YA?AUfrom_wchars_result@0@PEB_W0AEA_KHPEA_N@Z; utl::_FromCharsImpl<utl::from_wchars_result,unsigned __int64,wchar_t>(wchar_t const *,wchar_t const *,unsigned __int64 &,int,bool *)
0x180018fa5  cmp     dword ptr [rax+8], 0
0x180018fa9  jnz     short loc_180018FDA
0x180018fab  movzx   ecx, byte ptr [rbp+arg_10]
0x180018faf  mov     rax, 7FFFFFFFFFFFFFFFh
0x180018fb9  add     rax, rcx
0x180018fbc  cmp     [rbp+arg_18], rax
0x180018fc0  ja      short loc_180018FDA
0x180018fc2  mov     eax, ecx
0x180018fc4  neg     rax
0x180018fc7  xor     rax, [rbp+arg_18]
0x180018fcb  add     rax, rcx
0x180018fce  mov     [r15-8], rax
0x180018fd2  inc     dword ptr [rdi+20h]
0x180018fd5  jmp     loc_18001933B
0x180018fda  mov     rcx, cs:WPP_GLOBAL_Control
0x180018fe1  lea     rax, WPP_GLOBAL_Control
0x180018fe8  mov     edi, 57h ; 'W'
0x180018fed  cmp     rcx, rax
0x180018ff0  jz      short loc_180019014
0x180018ff2  test    byte ptr [rcx+1Ch], 2
0x180018ff6  jz      short loc_180019014
0x180018ff8  cmp     byte ptr [rcx+19h], 2
0x180018ffc  jb      short loc_180019014
0x180018ffe  mov     rcx, [rcx+10h]
0x180019002  lea     edx, [rdi-48h]
0x180019005  mov     r9d, edi
0x180019008  lea     r8, WPP_d919bee969333976452e2f12f271af1f_Traceguids
0x18001900f  call    WPP_SF_D
0x180019014  xorps   xmm0, xmm0
0x180019017  mov     [rbp+var_20], 0
0x18001901f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180019026  mov     [rbp+var_18], edi
0x180019029  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001902d  mov     [rbp+var_14], 0FFFFFFFFh
0x180019034  movdqu  [rbp+pExceptionObject], xmm0
0x180019039  mov     [rbp+var_10], 0C3h
0x180019040  call    _CxxThrowException_0
0x180019046  mov     rcx, cs:WPP_GLOBAL_Control
0x18001904d  lea     rax, WPP_GLOBAL_Control
0x180019054  mov     edi, 57h ; 'W'
0x180019059  cmp     rcx, rax
0x18001905c  jz      short loc_180019080
0x18001905e  test    byte ptr [rcx+1Ch], 2
0x180019062  jz      short loc_180019080
0x180019064  cmp     byte ptr [rcx+19h], 2
0x180019068  jb      short loc_180019080
0x18001906a  mov     rcx, [rcx+10h]
0x18001906e  lea     edx, [rdi-47h]
0x180019071  mov     r9d, edi
0x180019074  lea     r8, WPP_d919bee969333976452e2f12f271af1f_Traceguids
0x18001907b  call    WPP_SF_D
0x180019080  xorps   xmm0, xmm0
0x180019083  mov     [rbp+var_20], 0
0x18001908b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180019092  mov     [rbp+var_18], edi
0x180019095  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180019099  mov     [rbp+var_14], 0FFFFFFFFh
0x1800190a0  movdqu  [rbp+pExceptionObject], xmm0
0x1800190a5  mov     [rbp+var_10], 0CAh
0x1800190ac  call    _CxxThrowException_0
0x1800190b2  mov     rax, [rdi+18h]
0x1800190b6  mov     rcx, [rax]
0x1800190b9  mov     rcx, [rcx+18h]
0x1800190bd  add     rcx, 0FFFFFFFFFFFFFFE0h
0x1800190c1  mov     rax, [rcx+8]
0x1800190c5  cmp     [rcx], rax
0x1800190c8  jnz     loc_180019150
0x1800190ce  mov     r8, [rsi+8]
0x1800190d2  mov     rdx, [rsi]
0x1800190d5  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800190da  test    al, al
0x1800190dc  jnz     loc_180018FD2
0x1800190e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800190e9  lea     rax, WPP_GLOBAL_Control
0x1800190f0  cmp     rcx, rax
0x1800190f3  jz      short loc_18001911A
0x1800190f5  test    byte ptr [rcx+1Ch], 2
0x1800190f9  jz      short loc_18001911A
0x1800190fb  cmp     byte ptr [rcx+19h], 2
0x1800190ff  jb      short loc_18001911A
0x180019101  mov     rcx, [rcx+10h]
0x180019105  lea     r8, WPP_d919bee969333976452e2f12f271af1f_Traceguids
0x18001910c  mov     edx, 0Dh
0x180019111  lea     r9d, [rdx+1]
0x180019115  call    WPP_SF_D
0x18001911a  xorps   xmm0, xmm0
0x18001911d  mov     [rbp+var_20], 0
0x180019125  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001912c  mov     [rbp+var_18], 0Eh
0x180019133  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180019137  mov     [rbp+var_14], 0FFFFFFFFh
0x18001913e  movdqu  [rbp+pExceptionObject], xmm0
0x180019143  mov     [rbp+var_10], 0AFh
0x18001914a  call    _CxxThrowException_0
0x180019150  mov     rcx, cs:WPP_GLOBAL_Control
0x180019157  lea     rax, WPP_GLOBAL_Control
0x18001915e  mov     edi, 57h ; 'W'
0x180019163  cmp     rcx, rax
0x180019166  jz      short loc_18001918A
0x180019168  test    byte ptr [rcx+1Ch], 2
0x18001916c  jz      short loc_18001918A
0x18001916e  cmp     byte ptr [rcx+19h], 2
0x180019172  jb      short loc_18001918A
0x180019174  mov     rcx, [rcx+10h]
0x180019178  lea     edx, [rdi-49h]
0x18001917b  mov     r9d, edi
0x18001917e  lea     r8, WPP_d919bee969333976452e2f12f271af1f_Traceguids
0x180019185  call    WPP_SF_D
0x18001918a  xorps   xmm0, xmm0
0x18001918d  mov     [rbp+var_20], 0
0x180019195  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001919c  mov     [rbp+var_18], edi
0x18001919f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800191a3  mov     [rbp+var_14], 0FFFFFFFFh
0x1800191aa  movdqu  [rbp+pExceptionObject], xmm0
0x1800191af  mov     [rbp+var_10], 0B6h
0x1800191b6  call    _CxxThrowException_0
0x1800191bc  cmp     dword ptr [rdi+20h], 2
0x1800191c0  jnz     loc_180019271
0x1800191c6  mov     rax, [rdi+18h]
0x1800191ca  mov     rcx, [rax]
0x1800191cd  add     rcx, 10h
0x1800191d1  call    ??$emplace_back@AEAY00$$CB_W$0A@@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA_NAEAY00$$CB_W@Z; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::emplace_back<wchar_t const (&)[1],0>(wchar_t const (&)[1])
0x1800191d6  test    al, al
0x1800191d8  jz      short loc_180019203
0x1800191da  mov     rcx, [rdi+18h]
0x1800191de  lea     rdx, [rbp+arg_10]
0x1800191e2  add     rcx, 8
0x1800191e6  mov     [rbp+arg_10], 0FFFFFFFFFFFFFFFFh
0x1800191ee  call    ??$_PushBackOne@_J@?$vector@_JV?$allocator@_J@utl@@@utl@@AEAA_N$$QEA_J@Z; utl::vector<__int64,utl::allocator<__int64>>::_PushBackOne<__int64>(__int64 &&)
0x1800191f3  test    al, al
0x1800191f5  jz      short loc_180019203
0x1800191f7  mov     dword ptr [rdi+20h], 0
0x1800191fe  jmp     loc_18001933B
0x180019203  mov     rcx, cs:WPP_GLOBAL_Control
0x18001920a  lea     rax, WPP_GLOBAL_Control
0x180019211  cmp     rcx, rax
0x180019214  jz      short loc_18001923B
0x180019216  test    byte ptr [rcx+1Ch], 2
0x18001921a  jz      short loc_18001923B
0x18001921c  cmp     byte ptr [rcx+19h], 2
0x180019220  jb      short loc_18001923B
0x180019222  mov     rcx, [rcx+10h]
0x180019226  lea     r8, WPP_d919bee969333976452e2f12f271af1f_Traceguids
0x18001922d  mov     edx, 0Bh
0x180019232  lea     r9d, [rdx+3]
0x180019236  call    WPP_SF_D
0x18001923b  xorps   xmm0, xmm0
0x18001923e  mov     [rbp+var_20], 0
0x180019246  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001924d  mov     [rbp+var_18], 0Eh
0x180019254  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180019258  mov     [rbp+var_14], 0FFFFFFFFh
0x18001925f  movdqu  [rbp+pExceptionObject], xmm0
0x180019264  mov     [rbp+var_10], 9Fh
0x18001926b  call    _CxxThrowException_0
0x180019271  mov     rcx, cs:WPP_GLOBAL_Control
0x180019278  lea     rax, WPP_GLOBAL_Control
0x18001927f  mov     edi, 57h ; 'W'
0x180019284  cmp     rcx, rax
0x180019287  jz      short loc_1800192AB
0x180019289  test    byte ptr [rcx+1Ch], 2
0x18001928d  jz      short loc_1800192AB
0x18001928f  cmp     byte ptr [rcx+19h], 2
0x180019293  jb      short loc_1800192AB
0x180019295  mov     rcx, [rcx+10h]
0x180019299  lea     edx, [rdi-4Bh]
0x18001929c  mov     r9d, edi
0x18001929f  lea     r8, WPP_d919bee969333976452e2f12f271af1f_Traceguids
0x1800192a6  call    WPP_SF_D
0x1800192ab  xorps   xmm0, xmm0
0x1800192ae  mov     [rbp+var_20], 0
0x1800192b6  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
  ... truncated ...
```
