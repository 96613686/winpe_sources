# std::basic_filebuf<char,std::char_traits<char>>::overflow(int)

- ea: `0x18005a250`
- end: `0x18005a3d6`
- name: `?overflow@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAAHH@Z`
- size: `390`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180007660`
- `0x18005a250`

## import_xrefs

- `msvcp_win!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x18005a35c`
- `msvcp_win!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x18005a35c`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x18005a313`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x18005a313`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18005a396`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18005a396`

## pseudocode

```c
__int64 __fastcall std::filebuf::overflow(__int64 a1, unsigned int a2)
{
  unsigned int v2; // edi
  __int64 result; // rax
  _QWORD *v6; // rax
  int *v7; // rdx
  _QWORD *v8; // rdx
  _BYTE *v9; // r8
  _QWORD *v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  bool v15; // zf
  int v16; // eax
  int v17; // eax
  __int64 v18; // r14
  char v19; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v20[7]; // [rsp+41h] [rbp-3Fh] BYREF
  _BYTE *v21; // [rsp+48h] [rbp-38h] BYREF
  char *v22; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v23[32]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v24; // [rsp+78h] [rbp-8h] BYREF

  v2 = -1;
  if ( a2 == -1 )
    return 0;
  v6 = *(_QWORD **)(a1 + 64);
  if ( *v6 )
  {
    v7 = *(int **)(a1 + 88);
    if ( *v6 < (unsigned __int64)(*v6 + *v7) )
    {
      result = a2;
      --*v7;
      v8 = *(_QWORD **)(a1 + 64);
      v9 = (_BYTE *)(*v8)++;
      *v9 = a2;
      return result;
    }
  }
  if ( *(_QWORD *)(a1 + 128) )
  {
    v10 = *(_QWORD **)(a1 + 24);
    if ( *v10 == a1 + 112 )
    {
      v11 = *(_QWORD *)(a1 + 136);
      v12 = *(_QWORD *)(a1 + 144);
      *v10 = v11;
      **(_QWORD **)(a1 + 56) = v11;
      **(_DWORD **)(a1 + 80) = v12 - v11;
    }
    v13 = *(_QWORD *)(a1 + 104);
    if ( !v13 )
    {
      v14 = (unsigned int)(char)a2;
LABEL_11:
      v15 = (unsigned int)_o_fputc(v14, *(_QWORD *)(a1 + 128)) == -1;
LABEL_19:
      if ( !v15 )
        return a2;
      return v2;
    }
    v19 = a2;
    v22 = 0;
    v21 = 0;
    v16 = std::codecvt<char,char,_Mbstatet>::out(v13, a1 + 116, &v19, v20, &v22, v23, &v24, &v21);
    if ( !v16 || (v17 = v16 - 1) == 0 )
    {
      if ( v21 != v23 )
      {
        v18 = v21 - v23;
        if ( v18 != _o_fwrite(v23, 1, v21 - v23, *(_QWORD *)(a1 + 128)) )
          return v2;
      }
      *(_BYTE *)(a1 + 113) = 1;
      v15 = v22 == &v19;
      goto LABEL_19;
    }
    if ( v17 == 2 )
    {
      v14 = (unsigned int)v19;
      goto LABEL_11;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18005a250  mov     [rsp-18h+arg_10], rbx
0x18005a255  mov     [rsp-18h+arg_18], rsi
0x18005a25a  push    rbp
0x18005a25b  push    rdi
0x18005a25c  push    r14
0x18005a25e  mov     rbp, rsp
0x18005a261  sub     rsp, 80h
0x18005a268  mov     rax, cs:__security_cookie
0x18005a26f  xor     rax, rsp
0x18005a272  mov     [rbp+var_8], rax
0x18005a276  or      edi, 0FFFFFFFFh
0x18005a279  mov     esi, edx
0x18005a27b  mov     rbx, rcx
0x18005a27e  cmp     edx, edi
0x18005a280  jnz     short loc_18005A289
0x18005a282  xor     eax, eax
0x18005a284  jmp     loc_18005A3B2
0x18005a289  mov     rax, [rcx+40h]
0x18005a28d  xor     r14d, r14d
0x18005a290  cmp     [rax], r14
0x18005a293  jz      short loc_18005A2C5
0x18005a295  mov     rdx, [rcx+58h]
0x18005a299  movsxd  r8, dword ptr [rdx]
0x18005a29c  mov     rcx, r8
0x18005a29f  add     rcx, [rax]
0x18005a2a2  cmp     [rax], rcx
0x18005a2a5  jnb     short loc_18005A2C5
0x18005a2a7  lea     ecx, [r8-1]
0x18005a2ab  mov     eax, esi
0x18005a2ad  mov     [rdx], ecx
0x18005a2af  mov     rdx, [rbx+40h]
0x18005a2b3  mov     r8, [rdx]
0x18005a2b6  lea     rcx, [r8+1]
0x18005a2ba  mov     [rdx], rcx
0x18005a2bd  mov     [r8], sil
0x18005a2c0  jmp     loc_18005A3B2
0x18005a2c5  cmp     [rbx+80h], r14
0x18005a2cc  jz      loc_18005A3B0
0x18005a2d2  mov     r8, [rbx+18h]
0x18005a2d6  lea     rax, [rbx+70h]
0x18005a2da  cmp     [r8], rax
0x18005a2dd  jnz     short loc_18005A2FF
0x18005a2df  mov     rcx, [rbx+88h]
0x18005a2e6  mov     rdx, [rbx+90h]
0x18005a2ed  mov     [r8], rcx
0x18005a2f0  sub     edx, ecx
0x18005a2f2  mov     rax, [rbx+38h]
0x18005a2f6  mov     [rax], rcx
0x18005a2f9  mov     rax, [rbx+50h]
0x18005a2fd  mov     [rax], edx
0x18005a2ff  mov     rcx, [rbx+68h]
0x18005a303  test    rcx, rcx
0x18005a306  jnz     short loc_18005A320
0x18005a308  movsx   ecx, sil
0x18005a30c  mov     rdx, [rbx+80h]
0x18005a313  call    cs:__imp__o_fputc
0x18005a319  cmp     eax, edi
0x18005a31b  jmp     loc_18005A3AD
0x18005a320  lea     rax, [rbp+var_38]
0x18005a324  mov     [rbp+var_40], sil
0x18005a328  mov     [rsp+80h+var_48], rax
0x18005a32d  lea     rdx, [rbx+74h]
0x18005a331  lea     rax, [rbp+var_8]
0x18005a335  mov     [rbp+var_30], r14
0x18005a339  mov     [rsp+80h+var_50], rax
0x18005a33e  lea     r9, [rbp+var_3F]
0x18005a342  lea     rax, [rbp+var_28]
0x18005a346  mov     [rbp+var_38], r14
0x18005a34a  mov     [rsp+80h+var_58], rax
0x18005a34f  lea     r8, [rbp+var_40]
0x18005a353  lea     rax, [rbp+var_30]
0x18005a357  mov     [rsp+80h+var_60], rax
0x18005a35c  call    cs:__imp_?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::out(_Mbstatet &,char const *,char const *,char const * &,char *,char *,char * &)
0x18005a362  test    eax, eax
0x18005a364  jz      short loc_18005A376
0x18005a366  sub     eax, 1
0x18005a369  jz      short loc_18005A376
0x18005a36b  cmp     eax, 2
0x18005a36e  jnz     short loc_18005A3B0
0x18005a370  movsx   ecx, [rbp+var_40]
0x18005a374  jmp     short loc_18005A30C
0x18005a376  mov     r14, [rbp+var_38]
0x18005a37a  lea     rax, [rbp+var_28]
0x18005a37e  sub     r14, rax
0x18005a381  jz      short loc_18005A3A1
0x18005a383  mov     r9, [rbx+80h]
0x18005a38a  lea     rcx, [rbp+var_28]
0x18005a38e  mov     r8, r14
0x18005a391  mov     edx, 1
0x18005a396  call    cs:__imp__o_fwrite
0x18005a39c  cmp     r14, rax
0x18005a39f  jnz     short loc_18005A3B0
0x18005a3a1  lea     rax, [rbp+var_40]
0x18005a3a5  mov     byte ptr [rbx+71h], 1
0x18005a3a9  cmp     [rbp+var_30], rax
0x18005a3ad  cmovnz  edi, esi
0x18005a3b0  mov     eax, edi
0x18005a3b2  mov     rcx, [rbp+var_8]
0x18005a3b6  xor     rcx, rsp; StackCookie
0x18005a3b9  call    __security_check_cookie
0x18005a3be  lea     r11, [rsp+80h+var_s0]
0x18005a3c6  mov     rbx, [r11+30h]
0x18005a3ca  mov     rsi, [r11+38h]
0x18005a3ce  mov     rsp, r11
0x18005a3d1  pop     r14
0x18005a3d3  pop     rdi
0x18005a3d4  pop     rbp
0x18005a3d5  retn
```
