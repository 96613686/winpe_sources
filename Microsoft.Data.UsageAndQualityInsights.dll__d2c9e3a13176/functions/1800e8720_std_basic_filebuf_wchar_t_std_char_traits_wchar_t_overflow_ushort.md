# std::basic_filebuf<wchar_t,std::char_traits<wchar_t>>::overflow(ushort)

- ea: `0x1800e8720`
- end: `0x1800e88b6`
- name: `?overflow@?$basic_filebuf@_WU?$char_traits@_W@std@@@std@@MEAAGG@Z`
- size: `406`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800033d0`
- `0x1800e8720`

## import_xrefs

- `msvcp_win!?out@?$codecvt@_WDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEB_W1AEAPEB_WPEAD3AEAPEAD@Z` at `0x1800e883a`
- `msvcp_win!?out@?$codecvt@_WDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEB_W1AEAPEB_WPEAD3AEAPEAD@Z` at `0x1800e883a`
- `api-ms-win-crt-private-l1-1-0!_o_fputwc` at `0x1800e87ef`
- `api-ms-win-crt-private-l1-1-0!_o_fputwc` at `0x1800e87ef`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800e8874`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800e8874`

## pseudocode

```c
__int64 __fastcall std::wfilebuf::overflow(__int64 a1, unsigned __int16 a2)
{
  unsigned __int16 v2; // si
  unsigned __int16 v3; // di
  unsigned __int64 v6; // r8
  int *v7; // rax
  __int64 v8; // r9
  _WORD **v9; // rdx
  unsigned __int16 *v10; // r8
  _QWORD *v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // eax
  int v17; // eax
  __int64 v18; // r14
  unsigned __int16 v19; // [rsp+40h] [rbp-40h] BYREF
  char v20[6]; // [rsp+42h] [rbp-3Eh] BYREF
  _BYTE *v21; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int16 *v22; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v23[32]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v24; // [rsp+78h] [rbp-8h] BYREF

  v2 = -1;
  v3 = a2;
  if ( a2 == 0xFFFF )
    return 0;
  v6 = **(_QWORD **)(a1 + 64);
  if ( v6 )
  {
    v7 = *(int **)(a1 + 88);
    v8 = *v7;
    if ( v6 < v6 + 2 * v8 )
    {
      *v7 = v8 - 1;
      v9 = *(_WORD ***)(a1 + 64);
      v10 = (*v9)++;
      *v10 = v3;
      return v3;
    }
  }
  if ( *(_QWORD *)(a1 + 128) )
  {
    v11 = *(_QWORD **)(a1 + 24);
    if ( *v11 == a1 + 112 )
    {
      v12 = *(_QWORD *)(a1 + 144);
      v13 = *(_QWORD *)(a1 + 136);
      *v11 = v13;
      **(_QWORD **)(a1 + 56) = v13;
      **(_DWORD **)(a1 + 80) = (v12 - v13) >> 1;
    }
    v14 = *(_QWORD *)(a1 + 104);
    if ( !v14 )
    {
      v15 = v3;
      goto LABEL_12;
    }
    v19 = v3;
    v22 = 0;
    v21 = 0;
    v16 = std::codecvt<wchar_t,char,_Mbstatet>::out(v14, a1 + 116, &v19, v20, &v22, v23, &v24, &v21);
    if ( v16 && (v17 = v16 - 1) != 0 )
    {
      if ( v17 == 2 )
      {
        v15 = v19;
LABEL_12:
        if ( (unsigned __int16)_o_fputwc(v15, *(_QWORD *)(a1 + 128)) == 0xFFFF )
          return (unsigned __int16)-1;
        return v3;
      }
    }
    else if ( v21 == v23 || (v18 = v21 - v23, v18 == _o_fwrite(v23, 1, v21 - v23, *(_QWORD *)(a1 + 128))) )
    {
      *(_BYTE *)(a1 + 114) = 1;
      if ( v22 != &v19 )
        return v3;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800e8720  mov     [rsp-18h+arg_10], rbx
0x1800e8725  mov     [rsp-18h+arg_18], rsi
0x1800e872a  push    rbp
0x1800e872b  push    rdi
0x1800e872c  push    r14
0x1800e872e  mov     rbp, rsp
0x1800e8731  sub     rsp, 80h
0x1800e8738  mov     rax, cs:__security_cookie
0x1800e873f  xor     rax, rsp
0x1800e8742  mov     [rbp+var_8], rax
0x1800e8746  mov     esi, 0FFFFh
0x1800e874b  xor     r14d, r14d
0x1800e874e  movzx   edi, dx
0x1800e8751  mov     rbx, rcx
0x1800e8754  cmp     si, dx
0x1800e8757  jnz     short loc_1800E8762
0x1800e8759  movzx   eax, r14w
0x1800e875d  jmp     loc_1800E8892
0x1800e8762  mov     rax, [rcx+40h]
0x1800e8766  mov     r8, [rax]
0x1800e8769  test    r8, r8
0x1800e876c  jz      short loc_1800E879E
0x1800e876e  mov     rax, [rcx+58h]
0x1800e8772  movsxd  r9, dword ptr [rax]
0x1800e8775  lea     rdx, [r8+r9*2]
0x1800e8779  cmp     r8, rdx
0x1800e877c  jnb     short loc_1800E879E
0x1800e877e  lea     ecx, [r9-1]
0x1800e8782  mov     [rax], ecx
0x1800e8784  mov     rdx, [rbx+40h]
0x1800e8788  mov     r8, [rdx]
0x1800e878b  lea     rcx, [r8+2]
0x1800e878f  mov     [rdx], rcx
0x1800e8792  mov     [r8], di
0x1800e8796  movzx   eax, di
0x1800e8799  jmp     loc_1800E8892
0x1800e879e  cmp     [rcx+80h], r14
0x1800e87a5  jz      loc_1800E888F
0x1800e87ab  mov     r8, [rcx+18h]
0x1800e87af  lea     rax, [rcx+70h]
0x1800e87b3  cmp     [r8], rax
0x1800e87b6  jnz     short loc_1800E87DC
0x1800e87b8  mov     rdx, [rcx+90h]
0x1800e87bf  mov     rcx, [rcx+88h]
0x1800e87c6  mov     [r8], rcx
0x1800e87c9  sub     rdx, rcx
0x1800e87cc  mov     rax, [rbx+38h]
0x1800e87d0  sar     rdx, 1
0x1800e87d3  mov     [rax], rcx
0x1800e87d6  mov     rax, [rbx+50h]
0x1800e87da  mov     [rax], edx
0x1800e87dc  mov     rcx, [rbx+68h]
0x1800e87e0  test    rcx, rcx
0x1800e87e3  jnz     short loc_1800E87FE
0x1800e87e5  movzx   ecx, di
0x1800e87e8  mov     rdx, [rbx+80h]
0x1800e87ef  call    cs:__imp__o_fputwc
0x1800e87f5  cmp     ax, si
0x1800e87f8  cmovz   di, si
0x1800e87fc  jmp     short loc_1800E8796
0x1800e87fe  lea     rax, [rbp+var_38]
0x1800e8802  mov     [rbp+var_40], di
0x1800e8806  mov     [rsp+80h+var_48], rax
0x1800e880b  lea     rdx, [rbx+74h]
0x1800e880f  lea     rax, [rbp+var_8]
0x1800e8813  mov     [rbp+var_30], r14
0x1800e8817  mov     [rsp+80h+var_50], rax
0x1800e881c  lea     r9, [rbp+var_3E]
0x1800e8820  lea     rax, [rbp+var_28]
0x1800e8824  mov     [rbp+var_38], r14
0x1800e8828  mov     [rsp+80h+var_58], rax
0x1800e882d  lea     r8, [rbp+var_40]
0x1800e8831  lea     rax, [rbp+var_30]
0x1800e8835  mov     [rsp+80h+var_60], rax
0x1800e883a  call    cs:__imp_?out@?$codecvt@_WDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEB_W1AEAPEB_WPEAD3AEAPEAD@Z; std::codecvt<wchar_t,char,_Mbstatet>::out(_Mbstatet &,wchar_t const *,wchar_t const *,wchar_t const * &,char *,char *,char * &)
0x1800e8840  test    eax, eax
0x1800e8842  jz      short loc_1800E8854
0x1800e8844  sub     eax, 1
0x1800e8847  jz      short loc_1800E8854
0x1800e8849  cmp     eax, 2
0x1800e884c  jnz     short loc_1800E888F
0x1800e884e  movzx   ecx, [rbp+var_40]
0x1800e8852  jmp     short loc_1800E87E8
0x1800e8854  mov     r14, [rbp+var_38]
0x1800e8858  lea     rax, [rbp+var_28]
0x1800e885c  sub     r14, rax
0x1800e885f  jz      short loc_1800E887F
0x1800e8861  mov     r9, [rbx+80h]
0x1800e8868  lea     rcx, [rbp+var_28]
0x1800e886c  mov     r8, r14
0x1800e886f  mov     edx, 1
0x1800e8874  call    cs:__imp__o_fwrite
0x1800e887a  cmp     r14, rax
0x1800e887d  jnz     short loc_1800E888F
0x1800e887f  lea     rax, [rbp+var_40]
0x1800e8883  mov     byte ptr [rbx+72h], 1
0x1800e8887  cmp     [rbp+var_30], rax
0x1800e888b  cmovnz  si, di
0x1800e888f  movzx   eax, si
0x1800e8892  mov     rcx, [rbp+var_8]
0x1800e8896  xor     rcx, rsp; StackCookie
0x1800e8899  call    __security_check_cookie
0x1800e889e  lea     r11, [rsp+80h+var_s0]
0x1800e88a6  mov     rbx, [r11+30h]
0x1800e88aa  mov     rsi, [r11+38h]
0x1800e88ae  mov     rsp, r11
0x1800e88b1  pop     r14
0x1800e88b3  pop     rdi
0x1800e88b4  pop     rbp
0x1800e88b5  retn
```
