# std::basic_filebuf<ushort,std::char_traits<ushort>>::overflow(ushort)

- ea: `0x1800e0070`
- end: `0x1800e01e0`
- name: `?overflow@?$basic_filebuf@GU?$char_traits@G@std@@@std@@MEAAGG@Z`
- size: `368`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005890`
- `0x1800dff54`
- `0x1800e0070`

## import_xrefs

- `msvcp_win!?out@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBG1AEAPEBGPEAD3AEAPEAD@Z` at `0x1800e0163`
- `msvcp_win!?out@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBG1AEAPEBGPEAD3AEAPEAD@Z` at `0x1800e0163`
- `msvcp_win!?epptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x1800e00c3`
- `msvcp_win!?epptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x1800e00c3`
- `msvcp_win!?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x1800e00b2`
- `msvcp_win!?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x1800e00cf`
- `msvcp_win!?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x1800e00b2`
- `msvcp_win!?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x1800e00cf`
- `msvcp_win!?_Pninc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAPEAGXZ` at `0x1800e00dd`
- `msvcp_win!?_Pninc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAPEAGXZ` at `0x1800e00dd`
- `api-ms-win-crt-private-l1-1-0!_o_fputwc` at `0x1800e0116`
- `api-ms-win-crt-private-l1-1-0!_o_fputwc` at `0x1800e0116`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800e019d`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800e019d`

## pseudocode

```c
__int64 __fastcall std::basic_filebuf<unsigned short>::overflow(__int64 a1, unsigned __int16 a2)
{
  unsigned __int16 v2; // r14
  unsigned __int16 v3; // si
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

  v2 = -1;
  v3 = a2;
  if ( a2 == 0xFFFF )
    return 0;
  if ( ((__int64 (*)(void))std::basic_streambuf<unsigned short>::pptr)() )
  {
    v6 = std::basic_streambuf<unsigned short>::epptr(a1);
    if ( std::basic_streambuf<unsigned short>::pptr(a1) < v6 )
    {
      *(_WORD *)std::basic_streambuf<unsigned short>::_Pninc(a1) = v3;
      return v3;
    }
  }
  if ( *(_QWORD *)(a1 + 128) )
  {
    std::basic_filebuf<unsigned short>::_Reset_back(a1);
    v7 = *(_QWORD *)(a1 + 104);
    if ( !v7 )
    {
      v8 = v3;
      goto LABEL_10;
    }
    v12 = v3;
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
        return v3;
      }
    }
    else if ( v14 == v16 || (v11 = v14 - v16, v11 == _o_fwrite(v16, 1, v14 - v16, *(_QWORD *)(a1 + 128))) )
    {
      *(_BYTE *)(a1 + 114) = 1;
      if ( v15 != &v12 )
        return v3;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800e0070  mov     [rsp-28h+arg_10], rbx
0x1800e0075  push    rbp
0x1800e0076  push    rsi
0x1800e0077  push    rdi
0x1800e0078  push    r14
0x1800e007a  push    r15
0x1800e007c  mov     rbp, rsp
0x1800e007f  sub     rsp, 80h
0x1800e0086  mov     rax, cs:__security_cookie
0x1800e008d  xor     rax, rsp
0x1800e0090  mov     [rbp+var_8], rax
0x1800e0094  mov     r14d, 0FFFFh
0x1800e009a  movzx   esi, dx
0x1800e009d  mov     rdi, rcx
0x1800e00a0  cmp     r14w, dx
0x1800e00a4  jnz     short loc_1800E00B2
0x1800e00a6  xor     r15d, r15d
0x1800e00a9  movzx   eax, r15w
0x1800e00ad  jmp     loc_1800E01BD
0x1800e00b2  call    cs:__imp_?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ; std::basic_streambuf<ushort>::pptr(void)
0x1800e00b8  xor     r15d, r15d
0x1800e00bb  test    rax, rax
0x1800e00be  jz      short loc_1800E00EE
0x1800e00c0  mov     rcx, rdi
0x1800e00c3  call    cs:__imp_?epptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ; std::basic_streambuf<ushort>::epptr(void)
0x1800e00c9  mov     rcx, rdi
0x1800e00cc  mov     rbx, rax
0x1800e00cf  call    cs:__imp_?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ; std::basic_streambuf<ushort>::pptr(void)
0x1800e00d5  cmp     rax, rbx
0x1800e00d8  jnb     short loc_1800E00EE
0x1800e00da  mov     rcx, rdi
0x1800e00dd  call    cs:__imp_?_Pninc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAPEAGXZ; std::basic_streambuf<ushort>::_Pninc(void)
0x1800e00e3  mov     [rax], si
0x1800e00e6  movzx   eax, si
0x1800e00e9  jmp     loc_1800E01BD
0x1800e00ee  cmp     [rdi+80h], r15
0x1800e00f5  jz      loc_1800E01B9
0x1800e00fb  mov     rcx, rdi
0x1800e00fe  call    ?_Reset_back@?$basic_filebuf@GU?$char_traits@G@std@@@std@@AEAAXXZ; std::basic_filebuf<ushort>::_Reset_back(void)
0x1800e0103  mov     rcx, [rdi+68h]
0x1800e0107  test    rcx, rcx
0x1800e010a  jnz     short loc_1800E0127
0x1800e010c  movzx   ecx, si
0x1800e010f  mov     rdx, [rdi+80h]
0x1800e0116  call    cs:__imp__o_fputwc
0x1800e011c  cmp     ax, r14w
0x1800e0120  cmovz   si, r14w
0x1800e0125  jmp     short loc_1800E00E6
0x1800e0127  lea     rax, [rbp+var_38]
0x1800e012b  mov     [rbp+var_40], si
0x1800e012f  mov     [rsp+80h+var_48], rax
0x1800e0134  lea     rdx, [rdi+74h]
0x1800e0138  lea     rax, [rbp+var_8]
0x1800e013c  mov     [rbp+var_30], r15
0x1800e0140  mov     [rsp+80h+var_50], rax
0x1800e0145  lea     r9, [rbp+var_3E]
0x1800e0149  lea     rax, [rbp+var_28]
0x1800e014d  mov     [rbp+var_38], r15
0x1800e0151  mov     [rsp+80h+var_58], rax
0x1800e0156  lea     r8, [rbp+var_40]
0x1800e015a  lea     rax, [rbp+var_30]
0x1800e015e  mov     [rsp+80h+var_60], rax
0x1800e0163  call    cs:__imp_?out@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBG1AEAPEBGPEAD3AEAPEAD@Z; std::codecvt<ushort,char,_Mbstatet>::out(_Mbstatet &,ushort const *,ushort const *,ushort const * &,char *,char *,char * &)
0x1800e0169  test    eax, eax
0x1800e016b  jz      short loc_1800E017D
0x1800e016d  sub     eax, 1
0x1800e0170  jz      short loc_1800E017D
0x1800e0172  cmp     eax, 2
0x1800e0175  jnz     short loc_1800E01B9
0x1800e0177  movzx   ecx, [rbp+var_40]
0x1800e017b  jmp     short loc_1800E010F
0x1800e017d  mov     rbx, [rbp+var_38]
0x1800e0181  lea     rax, [rbp+var_28]
0x1800e0185  sub     rbx, rax
0x1800e0188  jz      short loc_1800E01A8
0x1800e018a  mov     r9, [rdi+80h]
0x1800e0191  lea     rcx, [rbp+var_28]
0x1800e0195  mov     r8, rbx
0x1800e0198  mov     edx, 1
0x1800e019d  call    cs:__imp__o_fwrite
0x1800e01a3  cmp     rbx, rax
0x1800e01a6  jnz     short loc_1800E01B9
0x1800e01a8  lea     rax, [rbp+var_40]
0x1800e01ac  mov     byte ptr [rdi+72h], 1
0x1800e01b0  cmp     [rbp+var_30], rax
0x1800e01b4  cmovnz  r14w, si
0x1800e01b9  movzx   eax, r14w
0x1800e01bd  mov     rcx, [rbp+var_8]
0x1800e01c1  xor     rcx, rsp; StackCookie
0x1800e01c4  call    __security_check_cookie
0x1800e01c9  mov     rbx, [rsp+80h+arg_10]
0x1800e01d1  add     rsp, 80h
0x1800e01d8  pop     r15
0x1800e01da  pop     r14
0x1800e01dc  pop     rdi
0x1800e01dd  pop     rsi
0x1800e01de  pop     rbp
0x1800e01df  retn
```
