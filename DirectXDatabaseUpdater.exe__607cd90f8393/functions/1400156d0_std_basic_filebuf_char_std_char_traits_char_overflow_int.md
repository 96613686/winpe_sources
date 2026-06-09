# std::basic_filebuf<char,std::char_traits<char>>::overflow(int)

- ea: `0x1400156d0`
- end: `0x14001585b`
- name: `?overflow@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAAHH@Z`
- size: `395`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140002f40`
- `0x140015490`
- `0x1400155a4`
- `0x140015630`
- `0x1400156d0`
- `0x140015b58`

## import_xrefs

- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x14001571a`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x140015734`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x14001571a`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x140015734`
- `msvcp_win!?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x140015728`
- `msvcp_win!?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x140015728`
- `msvcp_win!?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ` at `0x140015742`
- `msvcp_win!?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ` at `0x140015742`
- `msvcp_win!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x1400157df`
- `msvcp_win!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x1400157df`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x140015789`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x140015789`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x140015819`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x140015819`

## pseudocode

```c
__int64 __fastcall std::filebuf::overflow(__int64 a1, __int64 a2)
{
  unsigned int v3; // r14d
  unsigned int v4; // edi
  unsigned __int64 v6; // rbx
  _BYTE *v7; // rbx
  char v8; // al
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rbx
  char v14; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v15[7]; // [rsp+41h] [rbp-3Fh] BYREF
  _BYTE *v16; // [rsp+48h] [rbp-38h] BYREF
  char *v17; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v18[32]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v19; // [rsp+78h] [rbp-8h] BYREF

  v3 = -1;
  v4 = a2;
  if ( (unsigned __int8)std::_Narrow_char_traits<char,int>::eq_int_type(0xFFFFFFFFLL, a2) )
    return std::_Narrow_char_traits<char,int>::not_eof(v4);
  if ( std::streambuf::pptr(a1) )
  {
    v6 = std::streambuf::epptr(a1);
    if ( std::streambuf::pptr(a1) < v6 )
    {
      v7 = (_BYTE *)std::streambuf::_Pninc(a1);
      *v7 = std::_Narrow_char_traits<char,int>::to_char_type(v4);
      return v4;
    }
  }
  if ( *(_QWORD *)(a1 + 128) )
  {
    std::filebuf::_Reset_back(a1);
    v8 = std::_Narrow_char_traits<char,int>::to_char_type(v4);
    if ( !*(_QWORD *)(a1 + 104) )
    {
      v9 = (unsigned int)v8;
      goto LABEL_10;
    }
    v10 = *(_QWORD *)(a1 + 104);
    v14 = v8;
    v17 = 0;
    v16 = 0;
    v11 = std::codecvt<char,char,_Mbstatet>::out(v10, a1 + 116, &v14, v15, &v17, v18, &v19, &v16);
    if ( v11 && (v12 = v11 - 1) != 0 )
    {
      if ( v12 == 2 )
      {
        v9 = (unsigned int)v14;
LABEL_10:
        if ( (unsigned int)_o_fputc(v9, *(_QWORD *)(a1 + 128)) == -1 )
          return (unsigned int)-1;
        return v4;
      }
    }
    else if ( v16 == v18 || (v13 = v16 - v18, v13 == _o_fwrite(v18, 1, v16 - v18, *(_QWORD *)(a1 + 128))) )
    {
      *(_BYTE *)(a1 + 113) = 1;
      if ( v17 != &v14 )
        return v4;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1400156d0  mov     [rsp-18h+arg_10], rbx
0x1400156d5  mov     [rsp-18h+arg_18], rsi
0x1400156da  push    rbp
0x1400156db  push    rdi
0x1400156dc  push    r14
0x1400156de  mov     rbp, rsp
0x1400156e1  sub     rsp, 80h
0x1400156e8  mov     rax, cs:__security_cookie
0x1400156ef  xor     rax, rsp
0x1400156f2  mov     [rbp+var_8], rax
0x1400156f6  mov     rsi, rcx
0x1400156f9  or      r14d, 0FFFFFFFFh
0x1400156fd  mov     ecx, r14d
0x140015700  mov     edi, edx
0x140015702  call    ?eq_int_type@?$_Narrow_char_traits@DH@std@@SA_NHH@Z; std::_Narrow_char_traits<char,int>::eq_int_type(int,int)
0x140015707  test    al, al
0x140015709  jz      short loc_140015717
0x14001570b  mov     ecx, edi
0x14001570d  call    ?not_eof@?$_Narrow_char_traits@DH@std@@SAHH@Z; std::_Narrow_char_traits<char,int>::not_eof(int)
0x140015712  jmp     loc_140015837
0x140015717  mov     rcx, rsi
0x14001571a  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x140015720  test    rax, rax
0x140015723  jz      short loc_14001575B
0x140015725  mov     rcx, rsi
0x140015728  call    cs:__imp_?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::epptr(void)
0x14001572e  mov     rcx, rsi
0x140015731  mov     rbx, rax
0x140015734  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x14001573a  cmp     rax, rbx
0x14001573d  jnb     short loc_14001575B
0x14001573f  mov     rcx, rsi
0x140015742  call    cs:__imp_?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ; std::streambuf::_Pninc(void)
0x140015748  mov     ecx, edi
0x14001574a  mov     rbx, rax
0x14001574d  call    ?to_char_type@?$_Narrow_char_traits@DH@std@@SADH@Z; std::_Narrow_char_traits<char,int>::to_char_type(int)
0x140015752  mov     [rbx], al
0x140015754  mov     eax, edi
0x140015756  jmp     loc_140015837
0x14001575b  cmp     qword ptr [rsi+80h], 0
0x140015763  jz      loc_140015834
0x140015769  mov     rcx, rsi
0x14001576c  call    ?_Reset_back@?$basic_filebuf@DU?$char_traits@D@std@@@std@@AEAAXXZ; std::filebuf::_Reset_back(void)
0x140015771  mov     ecx, edi
0x140015773  call    ?to_char_type@?$_Narrow_char_traits@DH@std@@SADH@Z; std::_Narrow_char_traits<char,int>::to_char_type(int)
0x140015778  cmp     qword ptr [rsi+68h], 0
0x14001577d  jnz     short loc_140015798
0x14001577f  movsx   ecx, al
0x140015782  mov     rdx, [rsi+80h]
0x140015789  call    cs:__imp__o_fputc
0x14001578f  cmp     eax, r14d
0x140015792  cmovz   edi, r14d
0x140015796  jmp     short loc_140015754
0x140015798  mov     rcx, [rsi+68h]
0x14001579c  lea     rdx, [rsi+74h]
0x1400157a0  mov     [rbp+var_40], al
0x1400157a3  lea     r9, [rbp+var_3F]
0x1400157a7  lea     rax, [rbp+var_38]
0x1400157ab  mov     [rbp+var_30], 0
0x1400157b3  mov     [rsp+80h+var_48], rax
0x1400157b8  lea     r8, [rbp+var_40]
0x1400157bc  lea     rax, [rbp+var_8]
0x1400157c0  mov     [rbp+var_38], 0
0x1400157c8  mov     [rsp+80h+var_50], rax
0x1400157cd  lea     rax, [rbp+var_28]
0x1400157d1  mov     [rsp+80h+var_58], rax
0x1400157d6  lea     rax, [rbp+var_30]
0x1400157da  mov     [rsp+80h+var_60], rax
0x1400157df  call    cs:__imp_?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::out(_Mbstatet &,char const *,char const *,char const * &,char *,char *,char * &)
0x1400157e5  test    eax, eax
0x1400157e7  jz      short loc_1400157F9
0x1400157e9  sub     eax, 1
0x1400157ec  jz      short loc_1400157F9
0x1400157ee  cmp     eax, 2
0x1400157f1  jnz     short loc_140015834
0x1400157f3  movsx   ecx, [rbp+var_40]
0x1400157f7  jmp     short loc_140015782
0x1400157f9  mov     rbx, [rbp+var_38]
0x1400157fd  lea     rax, [rbp+var_28]
0x140015801  sub     rbx, rax
0x140015804  jz      short loc_140015824
0x140015806  mov     r9, [rsi+80h]
0x14001580d  lea     rcx, [rbp+var_28]
0x140015811  mov     r8, rbx
0x140015814  mov     edx, 1
0x140015819  call    cs:__imp__o_fwrite
0x14001581f  cmp     rbx, rax
0x140015822  jnz     short loc_140015834
0x140015824  lea     rax, [rbp+var_40]
0x140015828  mov     byte ptr [rsi+71h], 1
0x14001582c  cmp     [rbp+var_30], rax
0x140015830  cmovnz  r14d, edi
0x140015834  mov     eax, r14d
0x140015837  mov     rcx, [rbp+var_8]
0x14001583b  xor     rcx, rsp; StackCookie
0x14001583e  call    __security_check_cookie
0x140015843  lea     r11, [rsp+80h+var_s0]
0x14001584b  mov     rbx, [r11+30h]
0x14001584f  mov     rsi, [r11+38h]
0x140015853  mov     rsp, r11
0x140015856  pop     r14
0x140015858  pop     rdi
0x140015859  pop     rbp
0x14001585a  retn
```
