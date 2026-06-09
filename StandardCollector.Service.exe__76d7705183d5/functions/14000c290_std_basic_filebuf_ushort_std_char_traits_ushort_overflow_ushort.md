# std::basic_filebuf<ushort,std::char_traits<ushort>>::overflow(ushort)

- ea: `0x14000c290`
- end: `0x14000c421`
- name: `?overflow@?$basic_filebuf@GU?$char_traits@G@std@@@std@@MEAAGG@Z`
- size: `401`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000c290`
- `0x1400137e0`

## import_xrefs

- `MSVCP140!?out@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBG1AEAPEBGPEAD3AEAPEAD@Z` at `0x14000c3a2`
- `MSVCP140!?out@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBG1AEAPEBGPEAD3AEAPEAD@Z` at `0x14000c3a2`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x14000c3df`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x14000c3df`
- `api-ms-win-crt-stdio-l1-1-0!fputwc` at `0x14000c35f`
- `api-ms-win-crt-stdio-l1-1-0!fputwc` at `0x14000c35f`

## pseudocode

```c
__int64 __fastcall std::basic_filebuf<unsigned short>::overflow(__int64 a1, wchar_t a2)
{
  unsigned __int16 v2; // si
  wchar_t v3; // di
  unsigned __int64 v6; // r8
  int *v7; // rax
  __int64 v8; // r9
  _WORD **v9; // rdx
  wchar_t *v10; // r8
  _QWORD *v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  wchar_t v15; // cx
  int v16; // eax
  int v17; // eax
  __int64 v18; // r14
  _BYTE *v19; // [rsp+40h] [rbp-40h] BYREF
  wchar_t *v20; // [rsp+48h] [rbp-38h] BYREF
  wchar_t v21; // [rsp+50h] [rbp-30h] BYREF
  char v22[6]; // [rsp+52h] [rbp-2Eh] BYREF
  _BYTE Buffer[32]; // [rsp+58h] [rbp-28h] BYREF
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
    v21 = v3;
    v16 = std::codecvt<unsigned short,char,_Mbstatet>::out(v14, a1 + 116, &v21, v22, &v20, Buffer, &v24, &v19);
    if ( v16 && (v17 = v16 - 1) != 0 )
    {
      if ( v17 == 2 )
      {
        v15 = v21;
LABEL_12:
        if ( fputwc(v15, *(FILE **)(a1 + 128)) == 0xFFFF )
          return (wchar_t)-1;
        return v3;
      }
    }
    else if ( v19 == Buffer
           || (_mm_lfence(), v18 = v19 - Buffer, v18 == fwrite(Buffer, 1u, v19 - Buffer, *(FILE **)(a1 + 128))) )
    {
      *(_BYTE *)(a1 + 114) = 1;
      if ( v20 != &v21 )
        return v3;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x14000c290  mov     [rsp-18h+arg_10], rbx
0x14000c295  mov     [rsp-18h+arg_18], rsi
0x14000c29a  push    rbp
0x14000c29b  push    rdi
0x14000c29c  push    r14
0x14000c29e  mov     rbp, rsp
0x14000c2a1  sub     rsp, 80h
0x14000c2a8  mov     rax, cs:__security_cookie
0x14000c2af  xor     rax, rsp
0x14000c2b2  mov     [rbp+var_8], rax
0x14000c2b6  mov     esi, 0FFFFh
0x14000c2bb  xor     r14d, r14d
0x14000c2be  movzx   edi, dx
0x14000c2c1  mov     rbx, rcx
0x14000c2c4  cmp     dx, si
0x14000c2c7  jnz     short loc_14000C2D2
0x14000c2c9  movzx   eax, r14w
0x14000c2cd  jmp     loc_14000C3FD
0x14000c2d2  mov     rax, [rcx+40h]
0x14000c2d6  mov     r8, [rax]
0x14000c2d9  test    r8, r8
0x14000c2dc  jz      short loc_14000C30E
0x14000c2de  mov     rax, [rcx+58h]
0x14000c2e2  movsxd  r9, dword ptr [rax]
0x14000c2e5  lea     rdx, [r8+r9*2]
0x14000c2e9  cmp     r8, rdx
0x14000c2ec  jnb     short loc_14000C30E
0x14000c2ee  lea     ecx, [r9-1]
0x14000c2f2  mov     [rax], ecx
0x14000c2f4  mov     rdx, [rbx+40h]
0x14000c2f8  mov     r8, [rdx]
0x14000c2fb  lea     rcx, [r8+2]
0x14000c2ff  mov     [rdx], rcx
0x14000c302  mov     [r8], di
0x14000c306  movzx   eax, di
0x14000c309  jmp     loc_14000C3FD
0x14000c30e  cmp     [rcx+80h], r14
0x14000c315  jz      loc_14000C3FA
0x14000c31b  mov     r8, [rcx+18h]
0x14000c31f  lea     rax, [rcx+70h]
0x14000c323  cmp     [r8], rax
0x14000c326  jnz     short loc_14000C34C
0x14000c328  mov     rdx, [rcx+90h]
0x14000c32f  mov     rcx, [rcx+88h]
0x14000c336  mov     [r8], rcx
0x14000c339  sub     rdx, rcx
0x14000c33c  mov     rax, [rbx+38h]
0x14000c340  sar     rdx, 1
0x14000c343  mov     [rax], rcx
0x14000c346  mov     rax, [rbx+50h]
0x14000c34a  mov     [rax], edx
0x14000c34c  mov     rcx, [rbx+68h]
0x14000c350  test    rcx, rcx
0x14000c353  jnz     short loc_14000C36E
0x14000c355  movzx   ecx, di; Character
0x14000c358  mov     rdx, [rbx+80h]; Stream
0x14000c35f  call    cs:__imp_fputwc
0x14000c365  cmp     ax, si
0x14000c368  cmovz   di, si
0x14000c36c  jmp     short loc_14000C306
0x14000c36e  lea     rax, [rbp+var_40]
0x14000c372  mov     [rbp+var_30], di
0x14000c376  mov     [rsp+80h+var_48], rax
0x14000c37b  lea     rdx, [rbx+74h]
0x14000c37f  lea     rax, [rbp+var_8]
0x14000c383  mov     [rsp+80h+var_50], rax
0x14000c388  lea     r9, [rbp+var_2E]
0x14000c38c  lea     rax, [rbp+Buffer]
0x14000c390  mov     [rsp+80h+var_58], rax
0x14000c395  lea     r8, [rbp+var_30]
0x14000c399  lea     rax, [rbp+var_38]
0x14000c39d  mov     [rsp+80h+var_60], rax
0x14000c3a2  call    cs:__imp_?out@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBG1AEAPEBGPEAD3AEAPEAD@Z; std::codecvt<ushort,char,_Mbstatet>::out(_Mbstatet &,ushort const *,ushort const *,ushort const * &,char *,char *,char * &)
0x14000c3a8  test    eax, eax
0x14000c3aa  jz      short loc_14000C3BC
0x14000c3ac  sub     eax, 1
0x14000c3af  jz      short loc_14000C3BC
0x14000c3b1  cmp     eax, 2
0x14000c3b4  jnz     short loc_14000C3FA
0x14000c3b6  movzx   ecx, [rbp+var_30]
0x14000c3ba  jmp     short loc_14000C358
0x14000c3bc  mov     r14, [rbp+var_40]
0x14000c3c0  lea     rax, [rbp+Buffer]
0x14000c3c4  sub     r14, rax
0x14000c3c7  jz      short loc_14000C3EA
0x14000c3c9  lfence
0x14000c3cc  mov     r9, [rbx+80h]; Stream
0x14000c3d3  lea     rcx, [rbp+Buffer]; Buffer
0x14000c3d7  mov     r8, r14; ElementCount
0x14000c3da  mov     edx, 1; ElementSize
0x14000c3df  call    cs:__imp_fwrite
0x14000c3e5  cmp     r14, rax
0x14000c3e8  jnz     short loc_14000C3FA
0x14000c3ea  lea     rax, [rbp+var_30]
0x14000c3ee  mov     byte ptr [rbx+72h], 1
0x14000c3f2  cmp     [rbp+var_38], rax
0x14000c3f6  cmovnz  si, di
0x14000c3fa  movzx   eax, si
0x14000c3fd  mov     rcx, [rbp+var_8]
0x14000c401  xor     rcx, rsp; StackCookie
0x14000c404  call    __security_check_cookie
0x14000c409  lea     r11, [rsp+80h+var_s0]
0x14000c411  mov     rbx, [r11+30h]
0x14000c415  mov     rsi, [r11+38h]
0x14000c419  mov     rsp, r11
0x14000c41c  pop     r14
0x14000c41e  pop     rdi
0x14000c41f  pop     rbp
0x14000c420  retn
```
