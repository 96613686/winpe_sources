# std::basic_filebuf<ushort,std::char_traits<ushort>>::overflow(ushort)

- ea: `0x14000ff40`
- end: `0x1400100c3`
- name: `?overflow@?$basic_filebuf@GU?$char_traits@G@std@@@std@@MEAAGG@Z`
- size: `387`
- prototype: `__int64 __fastcall(__int64, __int16)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140002210`
- `0x14000793c`
- `0x14000faf4`
- `0x14000ff28`
- `0x14000ff40`

## import_xrefs

- `msvcp_win!?epptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x14000ff9c`
- `msvcp_win!?epptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x14000ff9c`
- `msvcp_win!?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x14000ff8e`
- `msvcp_win!?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x14000ffa8`
- `msvcp_win!?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x14000ff8e`
- `msvcp_win!?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x14000ffa8`
- `msvcp_win!?out@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBG1AEAPEBGPEAD3AEAPEAD@Z` at `0x140010045`
- `msvcp_win!?out@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBG1AEAPEBGPEAD3AEAPEAD@Z` at `0x140010045`
- `msvcp_win!?_Pninc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAPEAGXZ` at `0x14000ffb6`
- `msvcp_win!?_Pninc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAPEAGXZ` at `0x14000ffb6`
- `api-ms-win-crt-private-l1-1-0!_o_fputwc` at `0x14000fff0`
- `api-ms-win-crt-private-l1-1-0!_o_fputwc` at `0x14000fff0`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x14001007f`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x14001007f`

## pseudocode

```c
__int64 __fastcall std::basic_filebuf<unsigned short>::overflow(__int64 a1, __int16 a2)
{
  unsigned __int16 v3; // r14
  unsigned __int16 v4; // di
  unsigned __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rcx
  int v9; // eax
  int v10; // eax
  __int64 v11; // rbx
  unsigned __int16 v12; // [rsp+40h] [rbp-40h] BYREF
  char v13[6]; // [rsp+42h] [rbp-3Eh] BYREF
  _BYTE *v14; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int16 *v15; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v16[32]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v17; // [rsp+78h] [rbp-8h] BYREF

  v3 = -1;
  v4 = a2;
  if ( std::_WChar_traits<unsigned short>::eq_int_type(0xFFFF, a2) )
    return std::_WChar_traits<unsigned short>::not_eof(v4);
  if ( std::basic_streambuf<unsigned short>::pptr(a1) )
  {
    v6 = std::basic_streambuf<unsigned short>::epptr(a1);
    if ( std::basic_streambuf<unsigned short>::pptr(a1) < v6 )
    {
      *(_WORD *)std::basic_streambuf<unsigned short>::_Pninc(a1) = v4;
      return v4;
    }
  }
  if ( *(_QWORD *)(a1 + 128) )
  {
    std::basic_filebuf<unsigned short>::_Reset_back(a1);
    v7 = *(_QWORD *)(a1 + 104);
    if ( !v7 )
    {
      v8 = v4;
      goto LABEL_10;
    }
    v12 = v4;
    v15 = 0;
    v14 = 0;
    v9 = std::codecvt<unsigned short,char,_Mbstatet>::out(v7, a1 + 116, &v12, v13, &v15, v16, &v17, &v14);
    if ( v9 && (v10 = v9 - 1) != 0 )
    {
      if ( v10 == 2 )
      {
        v8 = v12;
LABEL_10:
        if ( (unsigned __int16)_o_fputwc(v8, *(_QWORD *)(a1 + 128)) == 0xFFFF )
          return (unsigned __int16)-1;
        return v4;
      }
    }
    else if ( v14 == v16 || (v11 = v14 - v16, v11 == _o_fwrite(v16, 1, v14 - v16, *(_QWORD *)(a1 + 128))) )
    {
      *(_BYTE *)(a1 + 114) = 1;
      if ( v15 != &v12 )
        return v4;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x14000ff40  mov     [rsp-18h+arg_10], rbx
0x14000ff45  mov     [rsp-18h+arg_18], rsi
0x14000ff4a  push    rbp
0x14000ff4b  push    rdi
0x14000ff4c  push    r14
0x14000ff4e  mov     rbp, rsp
0x14000ff51  sub     rsp, 80h
0x14000ff58  mov     rax, cs:__security_cookie
0x14000ff5f  xor     rax, rsp
0x14000ff62  mov     [rbp+var_8], rax
0x14000ff66  mov     rsi, rcx
0x14000ff69  mov     r14d, 0FFFFh
0x14000ff6f  mov     ecx, r14d
0x14000ff72  movzx   edi, dx
0x14000ff75  call    ?eq_int_type@?$_WChar_traits@G@std@@SA_NGG@Z; std::_WChar_traits<ushort>::eq_int_type(ushort,ushort)
0x14000ff7a  test    al, al
0x14000ff7c  jz      short loc_14000FF8B
0x14000ff7e  movzx   ecx, di
0x14000ff81  call    ?not_eof@?$_WChar_traits@G@std@@SAGG@Z; std::_WChar_traits<ushort>::not_eof(ushort)
0x14000ff86  jmp     loc_14001009F
0x14000ff8b  mov     rcx, rsi
0x14000ff8e  call    cs:__imp_?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ; std::basic_streambuf<ushort>::pptr(void)
0x14000ff94  test    rax, rax
0x14000ff97  jz      short loc_14000FFC7
0x14000ff99  mov     rcx, rsi
0x14000ff9c  call    cs:__imp_?epptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ; std::basic_streambuf<ushort>::epptr(void)
0x14000ffa2  mov     rcx, rsi
0x14000ffa5  mov     rbx, rax
0x14000ffa8  call    cs:__imp_?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ; std::basic_streambuf<ushort>::pptr(void)
0x14000ffae  cmp     rax, rbx
0x14000ffb1  jnb     short loc_14000FFC7
0x14000ffb3  mov     rcx, rsi
0x14000ffb6  call    cs:__imp_?_Pninc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAPEAGXZ; std::basic_streambuf<ushort>::_Pninc(void)
0x14000ffbc  mov     [rax], di
0x14000ffbf  movzx   eax, di
0x14000ffc2  jmp     loc_14001009F
0x14000ffc7  cmp     qword ptr [rsi+80h], 0
0x14000ffcf  jz      loc_14001009B
0x14000ffd5  mov     rcx, rsi
0x14000ffd8  call    ?_Reset_back@?$basic_filebuf@GU?$char_traits@G@std@@@std@@AEAAXXZ; std::basic_filebuf<ushort>::_Reset_back(void)
0x14000ffdd  mov     rcx, [rsi+68h]
0x14000ffe1  test    rcx, rcx
0x14000ffe4  jnz     short loc_140010001
0x14000ffe6  movzx   ecx, di
0x14000ffe9  mov     rdx, [rsi+80h]
0x14000fff0  call    cs:__imp__o_fputwc
0x14000fff6  cmp     ax, r14w
0x14000fffa  cmovz   di, r14w
0x14000ffff  jmp     short loc_14000FFBF
0x140010001  lea     rax, [rbp+var_38]
0x140010005  mov     [rbp+var_40], di
0x140010009  mov     [rsp+80h+var_48], rax
0x14001000e  lea     rdx, [rsi+74h]
0x140010012  lea     rax, [rbp+var_8]
0x140010016  mov     [rbp+var_30], 0
0x14001001e  mov     [rsp+80h+var_50], rax
0x140010023  lea     r9, [rbp+var_3E]
0x140010027  lea     rax, [rbp+var_28]
0x14001002b  mov     [rbp+var_38], 0
0x140010033  mov     [rsp+80h+var_58], rax
0x140010038  lea     r8, [rbp+var_40]
0x14001003c  lea     rax, [rbp+var_30]
0x140010040  mov     [rsp+80h+var_60], rax
0x140010045  call    cs:__imp_?out@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBG1AEAPEBGPEAD3AEAPEAD@Z; std::codecvt<ushort,char,_Mbstatet>::out(_Mbstatet &,ushort const *,ushort const *,ushort const * &,char *,char *,char * &)
0x14001004b  test    eax, eax
0x14001004d  jz      short loc_14001005F
0x14001004f  sub     eax, 1
0x140010052  jz      short loc_14001005F
0x140010054  cmp     eax, 2
0x140010057  jnz     short loc_14001009B
0x140010059  movzx   ecx, [rbp+var_40]
0x14001005d  jmp     short loc_14000FFE9
0x14001005f  mov     rbx, [rbp+var_38]
0x140010063  lea     rax, [rbp+var_28]
0x140010067  sub     rbx, rax
0x14001006a  jz      short loc_14001008A
0x14001006c  mov     r9, [rsi+80h]
0x140010073  lea     rcx, [rbp+var_28]
0x140010077  mov     r8, rbx
0x14001007a  mov     edx, 1
0x14001007f  call    cs:__imp__o_fwrite
0x140010085  cmp     rbx, rax
0x140010088  jnz     short loc_14001009B
0x14001008a  lea     rax, [rbp+var_40]
0x14001008e  mov     byte ptr [rsi+72h], 1
0x140010092  cmp     [rbp+var_30], rax
0x140010096  cmovnz  r14w, di
0x14001009b  movzx   eax, r14w
0x14001009f  mov     rcx, [rbp+var_8]
0x1400100a3  xor     rcx, rsp; StackCookie
0x1400100a6  call    __security_check_cookie
0x1400100ab  lea     r11, [rsp+80h+var_s0]
0x1400100b3  mov     rbx, [r11+30h]
0x1400100b7  mov     rsi, [r11+38h]
0x1400100bb  mov     rsp, r11
0x1400100be  pop     r14
0x1400100c0  pop     rdi
0x1400100c1  pop     rbp
0x1400100c2  retn
```
