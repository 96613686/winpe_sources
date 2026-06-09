# std::basic_filebuf<char,std::char_traits<char>>::overflow(int)

- ea: `0x180032400`
- end: `0x180032561`
- name: `?overflow@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAAHH@Z`
- size: `353`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800078b0`
- `0x1800307c4`
- `0x180032400`

## import_xrefs

- `msvcp_win!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x1800324e7`
- `msvcp_win!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x1800324e7`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x18003249e`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x18003249e`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x180032521`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x180032521`

## pseudocode

```c
__int64 __fastcall std::filebuf::overflow(__int64 a1, unsigned int a2)
{
  unsigned int v2; // ebx
  __int64 result; // rax
  _QWORD *v6; // rax
  int *v7; // rdx
  _QWORD *v8; // rdx
  _BYTE *v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rcx
  bool v12; // zf
  int v13; // eax
  int v14; // eax
  __int64 v15; // r14
  char v16; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v17[7]; // [rsp+41h] [rbp-3Fh] BYREF
  _BYTE *v18; // [rsp+48h] [rbp-38h] BYREF
  char *v19; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v20[32]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v21; // [rsp+78h] [rbp-8h] BYREF

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
    std::filebuf::_Reset_back(a1);
    v10 = *(_QWORD *)(a1 + 104);
    if ( !v10 )
    {
      v11 = (unsigned int)(char)a2;
LABEL_9:
      v12 = (unsigned int)_o_fputc(v11, *(_QWORD *)(a1 + 128)) == -1;
LABEL_17:
      if ( !v12 )
        return a2;
      return v2;
    }
    v16 = a2;
    v19 = 0;
    v18 = 0;
    v13 = std::codecvt<char,char,_Mbstatet>::out(v10, a1 + 116, &v16, v17, &v19, v20, &v21, &v18);
    if ( !v13 || (v14 = v13 - 1) == 0 )
    {
      if ( v18 != v20 )
      {
        v15 = v18 - v20;
        if ( v15 != _o_fwrite(v20, 1, v18 - v20, *(_QWORD *)(a1 + 128)) )
          return v2;
      }
      *(_BYTE *)(a1 + 113) = 1;
      v12 = v19 == &v16;
      goto LABEL_17;
    }
    if ( v14 == 2 )
    {
      v11 = (unsigned int)v16;
      goto LABEL_9;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180032400  mov     [rsp-18h+arg_10], rbx
0x180032405  mov     [rsp-18h+arg_18], rsi
0x18003240a  push    rbp
0x18003240b  push    rdi
0x18003240c  push    r14
0x18003240e  mov     rbp, rsp
0x180032411  sub     rsp, 80h
0x180032418  mov     rax, cs:__security_cookie
0x18003241f  xor     rax, rsp
0x180032422  mov     [rbp+var_8], rax
0x180032426  or      ebx, 0FFFFFFFFh
0x180032429  mov     esi, edx
0x18003242b  mov     rdi, rcx
0x18003242e  cmp     edx, ebx
0x180032430  jnz     short loc_180032439
0x180032432  xor     eax, eax
0x180032434  jmp     loc_18003253D
0x180032439  mov     rax, [rcx+40h]
0x18003243d  xor     r14d, r14d
0x180032440  cmp     [rax], r14
0x180032443  jz      short loc_180032475
0x180032445  mov     rdx, [rcx+58h]
0x180032449  movsxd  r8, dword ptr [rdx]
0x18003244c  mov     rcx, r8
0x18003244f  add     rcx, [rax]
0x180032452  cmp     [rax], rcx
0x180032455  jnb     short loc_180032475
0x180032457  lea     ecx, [r8-1]
0x18003245b  mov     eax, esi
0x18003245d  mov     [rdx], ecx
0x18003245f  mov     rdx, [rdi+40h]
0x180032463  mov     r8, [rdx]
0x180032466  lea     rcx, [r8+1]
0x18003246a  mov     [rdx], rcx
0x18003246d  mov     [r8], sil
0x180032470  jmp     loc_18003253D
0x180032475  cmp     [rdi+80h], r14
0x18003247c  jz      loc_18003253B
0x180032482  mov     rcx, rdi
0x180032485  call    ?_Reset_back@?$basic_filebuf@DU?$char_traits@D@std@@@std@@AEAAXXZ; std::filebuf::_Reset_back(void)
0x18003248a  mov     rcx, [rdi+68h]
0x18003248e  test    rcx, rcx
0x180032491  jnz     short loc_1800324AB
0x180032493  movsx   ecx, sil
0x180032497  mov     rdx, [rdi+80h]
0x18003249e  call    cs:__imp__o_fputc
0x1800324a4  cmp     eax, ebx
0x1800324a6  jmp     loc_180032538
0x1800324ab  lea     rax, [rbp+var_38]
0x1800324af  mov     [rbp+var_40], sil
0x1800324b3  mov     [rsp+80h+var_48], rax
0x1800324b8  lea     rdx, [rdi+74h]
0x1800324bc  lea     rax, [rbp+var_8]
0x1800324c0  mov     [rbp+var_30], r14
0x1800324c4  mov     [rsp+80h+var_50], rax
0x1800324c9  lea     r9, [rbp+var_3F]
0x1800324cd  lea     rax, [rbp+var_28]
0x1800324d1  mov     [rbp+var_38], r14
0x1800324d5  mov     [rsp+80h+var_58], rax
0x1800324da  lea     r8, [rbp+var_40]
0x1800324de  lea     rax, [rbp+var_30]
0x1800324e2  mov     [rsp+80h+var_60], rax
0x1800324e7  call    cs:__imp_?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::out(_Mbstatet &,char const *,char const *,char const * &,char *,char *,char * &)
0x1800324ed  test    eax, eax
0x1800324ef  jz      short loc_180032501
0x1800324f1  sub     eax, 1
0x1800324f4  jz      short loc_180032501
0x1800324f6  cmp     eax, 2
0x1800324f9  jnz     short loc_18003253B
0x1800324fb  movsx   ecx, [rbp+var_40]
0x1800324ff  jmp     short loc_180032497
0x180032501  mov     r14, [rbp+var_38]
0x180032505  lea     rax, [rbp+var_28]
0x180032509  sub     r14, rax
0x18003250c  jz      short loc_18003252C
0x18003250e  mov     r9, [rdi+80h]
0x180032515  lea     rcx, [rbp+var_28]
0x180032519  mov     r8, r14
0x18003251c  mov     edx, 1
0x180032521  call    cs:__imp__o_fwrite
0x180032527  cmp     r14, rax
0x18003252a  jnz     short loc_18003253B
0x18003252c  lea     rax, [rbp+var_40]
0x180032530  mov     byte ptr [rdi+71h], 1
0x180032534  cmp     [rbp+var_30], rax
0x180032538  cmovnz  ebx, esi
0x18003253b  mov     eax, ebx
0x18003253d  mov     rcx, [rbp+var_8]
0x180032541  xor     rcx, rsp; StackCookie
0x180032544  call    __security_check_cookie
0x180032549  lea     r11, [rsp+80h+var_s0]
0x180032551  mov     rbx, [r11+30h]
0x180032555  mov     rsi, [r11+38h]
0x180032559  mov     rsp, r11
0x18003255c  pop     r14
0x18003255e  pop     rdi
0x18003255f  pop     rbp
0x180032560  retn
```
