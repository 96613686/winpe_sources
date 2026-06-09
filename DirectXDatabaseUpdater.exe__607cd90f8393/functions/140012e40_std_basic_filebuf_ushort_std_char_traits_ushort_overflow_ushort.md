# std::basic_filebuf<ushort,std::char_traits<ushort>>::overflow(ushort)

- ea: `0x140012e40`
- end: `0x140012fc3`
- name: `?overflow@?$basic_filebuf@GU?$char_traits@G@std@@@std@@MEAAGG@Z`
- size: `387`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140002f40`
- `0x14000e16c`
- `0x14000e298`
- `0x140012c84`
- `0x140012e40`

## import_xrefs

- `msvcp_win!?out@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBG1AEAPEBGPEAD3AEAPEAD@Z` at `0x140012f45`
- `msvcp_win!?out@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBG1AEAPEBGPEAD3AEAPEAD@Z` at `0x140012f45`
- `msvcp_win!?_Pninc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAPEAGXZ` at `0x140012eb6`
- `msvcp_win!?_Pninc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAPEAGXZ` at `0x140012eb6`
- `msvcp_win!?epptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x140012e9c`
- `msvcp_win!?epptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x140012e9c`
- `msvcp_win!?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x140012e8e`
- `msvcp_win!?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x140012ea8`
- `msvcp_win!?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x140012e8e`
- `msvcp_win!?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x140012ea8`
- `api-ms-win-crt-private-l1-1-0!_o_fputwc` at `0x140012ef0`
- `api-ms-win-crt-private-l1-1-0!_o_fputwc` at `0x140012ef0`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x140012f7f`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x140012f7f`

## pseudocode

```c
__int64 __fastcall std::basic_filebuf<unsigned short>::overflow(__int64 a1, __int64 a2)
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
  if ( (unsigned __int8)std::_WChar_traits<unsigned short>::eq_int_type(0xFFFF, a2) )
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
0x140012e40  mov     [rsp-18h+arg_10], rbx
0x140012e45  mov     [rsp-18h+arg_18], rsi
0x140012e4a  push    rbp
0x140012e4b  push    rdi
0x140012e4c  push    r14
0x140012e4e  mov     rbp, rsp
0x140012e51  sub     rsp, 80h
0x140012e58  mov     rax, cs:__security_cookie
0x140012e5f  xor     rax, rsp
0x140012e62  mov     [rbp+var_8], rax
0x140012e66  mov     rsi, rcx
0x140012e69  mov     r14d, 0FFFFh
0x140012e6f  mov     ecx, r14d
0x140012e72  movzx   edi, dx
0x140012e75  call    ?eq_int_type@?$_WChar_traits@G@std@@SA_NGG@Z; std::_WChar_traits<ushort>::eq_int_type(ushort,ushort)
0x140012e7a  test    al, al
0x140012e7c  jz      short loc_140012E8B
0x140012e7e  movzx   ecx, di
0x140012e81  call    ?not_eof@?$_WChar_traits@G@std@@SAGG@Z; std::_WChar_traits<ushort>::not_eof(ushort)
0x140012e86  jmp     loc_140012F9F
0x140012e8b  mov     rcx, rsi
0x140012e8e  call    cs:__imp_?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ; std::basic_streambuf<ushort>::pptr(void)
0x140012e94  test    rax, rax
0x140012e97  jz      short loc_140012EC7
0x140012e99  mov     rcx, rsi
0x140012e9c  call    cs:__imp_?epptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ; std::basic_streambuf<ushort>::epptr(void)
0x140012ea2  mov     rcx, rsi
0x140012ea5  mov     rbx, rax
0x140012ea8  call    cs:__imp_?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ; std::basic_streambuf<ushort>::pptr(void)
0x140012eae  cmp     rax, rbx
0x140012eb1  jnb     short loc_140012EC7
0x140012eb3  mov     rcx, rsi
0x140012eb6  call    cs:__imp_?_Pninc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAPEAGXZ; std::basic_streambuf<ushort>::_Pninc(void)
0x140012ebc  mov     [rax], di
0x140012ebf  movzx   eax, di
0x140012ec2  jmp     loc_140012F9F
0x140012ec7  cmp     qword ptr [rsi+80h], 0
0x140012ecf  jz      loc_140012F9B
0x140012ed5  mov     rcx, rsi
0x140012ed8  call    ?_Reset_back@?$basic_filebuf@GU?$char_traits@G@std@@@std@@AEAAXXZ; std::basic_filebuf<ushort>::_Reset_back(void)
0x140012edd  mov     rcx, [rsi+68h]
0x140012ee1  test    rcx, rcx
0x140012ee4  jnz     short loc_140012F01
0x140012ee6  movzx   ecx, di
0x140012ee9  mov     rdx, [rsi+80h]
0x140012ef0  call    cs:__imp__o_fputwc
0x140012ef6  cmp     ax, r14w
0x140012efa  cmovz   di, r14w
0x140012eff  jmp     short loc_140012EBF
0x140012f01  lea     rax, [rbp+var_38]
0x140012f05  mov     [rbp+var_40], di
0x140012f09  mov     [rsp+80h+var_48], rax
0x140012f0e  lea     rdx, [rsi+74h]
0x140012f12  lea     rax, [rbp+var_8]
0x140012f16  mov     [rbp+var_30], 0
0x140012f1e  mov     [rsp+80h+var_50], rax
0x140012f23  lea     r9, [rbp+var_3E]
0x140012f27  lea     rax, [rbp+var_28]
0x140012f2b  mov     [rbp+var_38], 0
0x140012f33  mov     [rsp+80h+var_58], rax
0x140012f38  lea     r8, [rbp+var_40]
0x140012f3c  lea     rax, [rbp+var_30]
0x140012f40  mov     [rsp+80h+var_60], rax
0x140012f45  call    cs:__imp_?out@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBG1AEAPEBGPEAD3AEAPEAD@Z; std::codecvt<ushort,char,_Mbstatet>::out(_Mbstatet &,ushort const *,ushort const *,ushort const * &,char *,char *,char * &)
0x140012f4b  test    eax, eax
0x140012f4d  jz      short loc_140012F5F
0x140012f4f  sub     eax, 1
0x140012f52  jz      short loc_140012F5F
0x140012f54  cmp     eax, 2
0x140012f57  jnz     short loc_140012F9B
0x140012f59  movzx   ecx, [rbp+var_40]
0x140012f5d  jmp     short loc_140012EE9
0x140012f5f  mov     rbx, [rbp+var_38]
0x140012f63  lea     rax, [rbp+var_28]
0x140012f67  sub     rbx, rax
0x140012f6a  jz      short loc_140012F8A
0x140012f6c  mov     r9, [rsi+80h]
0x140012f73  lea     rcx, [rbp+var_28]
0x140012f77  mov     r8, rbx
0x140012f7a  mov     edx, 1
0x140012f7f  call    cs:__imp__o_fwrite
0x140012f85  cmp     rbx, rax
0x140012f88  jnz     short loc_140012F9B
0x140012f8a  lea     rax, [rbp+var_40]
0x140012f8e  mov     byte ptr [rsi+72h], 1
0x140012f92  cmp     [rbp+var_30], rax
0x140012f96  cmovnz  r14w, di
0x140012f9b  movzx   eax, r14w
0x140012f9f  mov     rcx, [rbp+var_8]
0x140012fa3  xor     rcx, rsp; StackCookie
0x140012fa6  call    __security_check_cookie
0x140012fab  lea     r11, [rsp+80h+var_s0]
0x140012fb3  mov     rbx, [r11+30h]
0x140012fb7  mov     rsi, [r11+38h]
0x140012fbb  mov     rsp, r11
0x140012fbe  pop     r14
0x140012fc0  pop     rdi
0x140012fc1  pop     rbp
0x140012fc2  retn
```
