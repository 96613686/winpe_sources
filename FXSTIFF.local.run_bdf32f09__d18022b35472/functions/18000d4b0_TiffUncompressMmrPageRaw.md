# TiffUncompressMmrPageRaw

- ea: `0x18000d4b0`
- end: `0x18000d8e1`
- name: `TiffUncompressMmrPageRaw`
- size: `1073`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, char *, size_t Size)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000d3d0`

## callees

- `0x180009a7c`
- `0x18000c1a4`
- `0x18000d4b0`
- `0x180017bce`
- `0x180017c00`
- `0x180017c90`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TiffUncompressMmrPageRaw(__int64 a1, unsigned int a2, unsigned int a3, char *a4, size_t Size)
{
  char *v5; // r12
  unsigned __int64 v6; // rbp
  __int64 v8; // rsi
  unsigned __int64 v9; // r15
  __int16 *v10; // r13
  char *v11; // r14
  unsigned __int64 v12; // rdi
  int MrLine; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  unsigned __int16 v17; // r11
  int v18; // ecx
  int v19; // ebx
  char *v20; // rdx
  unsigned __int16 v21; // r9
  unsigned __int8 v22; // cl
  char v23; // r8
  unsigned __int16 v24; // r9
  unsigned __int64 v25; // rcx
  unsigned __int16 v26; // dx
  unsigned __int16 v27; // r9
  unsigned int v28; // eax
  unsigned int v29; // r8d
  unsigned int v30; // eax
  __int16 *v31; // rax
  _QWORD *v33; // rcx
  __int64 v34; // rdx
  char v35; // [rsp+40h] [rbp-1B78h] BYREF
  unsigned __int64 v36; // [rsp+48h] [rbp-1B70h] BYREF
  __int16 v37; // [rsp+50h] [rbp-1B68h] BYREF
  char v38; // [rsp+DE0h] [rbp-DD8h] BYREF

  v5 = a4;
  v6 = a3;
  v8 = a2;
  v9 = (unsigned __int64)&a4[(unsigned int)Size - 1];
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids);
  }
  v10 = &v37;
  v11 = &v38;
  memset_0(v5, 0, (unsigned int)Size);
  v37 = v6;
  v36 = a1 & 0xFFFFFFFFFFFFFFFCuLL;
  v12 = (a1 + v8 - 1) & 0xFFFFFFFFFFFFFFFCuLL;
  v35 = (8 * a1) & 0x18;
  while ( 1 )
  {
    MrLine = ReadMrLine((unsigned int)&v36, (unsigned int)&v35, (_DWORD)v10, (_DWORD)v11, v12, 1, v6);
    if ( !MrLine )
      break;
    v14 = MrLine - 1;
    if ( !v14 )
      return 0;
    v15 = v14 - 1;
    if ( !v15 )
      return 0;
    v16 = v15 - 1;
    if ( !v16 )
      return 0;
    if ( v16 == 1 )
      return 1;
LABEL_37:
    if ( v36 > v12 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids);
      }
      return 0;
    }
  }
  v17 = 0;
  while ( 1 )
  {
    v18 = *(unsigned __int16 *)&v11[2 * v17];
    if ( v18 == (_DWORD)v6 )
    {
LABEL_36:
      v5 += v6 >> 3;
      v31 = v10;
      v10 = (__int16 *)v11;
      v11 = (char *)v31;
      goto LABEL_37;
    }
    if ( (unsigned int)v17 + 1 > 0x6C2 )
    {
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 1;
      }
      v34 = 41;
      goto LABEL_67;
    }
    v19 = *(unsigned __int16 *)&v11[2 * v17 + 2];
    v20 = &v5[(unsigned __int64)*(unsigned __int16 *)&v11[2 * v17] >> 3];
    v21 = v19 - v18;
    if ( (unsigned __int64)v20 > v9 )
    {
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 1;
      }
      v34 = 42;
      goto LABEL_67;
    }
    v22 = v18 & 7;
    v23 = *v20 | (255 >> v22);
    *v20 = v23;
    if ( v22 + (unsigned int)v21 <= 7 )
    {
      *v20 = v23 & *((_BYTE *)qword_1800440A0 + v22 + (unsigned int)v21);
      goto LABEL_34;
    }
    v24 = v22 - 8 + v21;
    v25 = (unsigned __int64)(v20 + 1);
    v26 = v24 >> 3;
    v27 = v24 - 8 * (v24 >> 3);
    v28 = 0;
    if ( v26 >= 7u )
      break;
    if ( v26 )
    {
      while ( v25 <= v9 )
      {
        *(_BYTE *)v25 = -1;
        ++v28;
        ++v25;
        if ( v28 >= v26 )
          goto LABEL_32;
      }
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 1;
      }
      v34 = 45;
LABEL_67:
      WPP_SF_(v33[2], v34, &WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids);
      return 1;
    }
LABEL_32:
    if ( v25 > v9 )
    {
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 1;
      }
      v34 = 46;
      goto LABEL_67;
    }
    *(_BYTE *)v25 = *((_BYTE *)qword_1800440A0 + v27);
LABEL_34:
    if ( v19 != (_DWORD)v6 )
    {
      v17 += 2;
      if ( v17 < 0x6C3u )
        continue;
    }
    goto LABEL_36;
  }
  while ( (v25 & 3) == 0 && !v28 )
  {
    v29 = v26 >> 2;
    v30 = 0;
    if ( v26 >> 2 )
    {
      while ( v25 <= v9 - 3 )
      {
        *(_DWORD *)v25 = -1;
        ++v30;
        v25 += 4LL;
        if ( v30 >= v29 )
          goto LABEL_24;
      }
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v34 = 43;
        goto LABEL_67;
      }
      return 1;
    }
LABEL_24:
    v28 = 1;
    v26 -= 4 * v29;
LABEL_27:
    if ( !v26 )
      goto LABEL_32;
  }
  if ( v25 <= v9 )
  {
    *(_BYTE *)v25++ = -1;
    --v26;
    goto LABEL_27;
  }
  v33 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v34 = 44;
    goto LABEL_67;
  }
  return 1;
}

```

## disassembly

```asm
0x18000d4b0  mov     [rsp+arg_8], rbx
0x18000d4b5  push    rbp
0x18000d4b6  push    rsi
0x18000d4b7  push    rdi
0x18000d4b8  push    r12
0x18000d4ba  push    r13
0x18000d4bc  push    r14
0x18000d4be  push    r15
0x18000d4c0  mov     eax, 1B80h
0x18000d4c5  call    _alloca_probe
0x18000d4ca  sub     rsp, rax
0x18000d4cd  mov     rax, cs:__security_cookie
0x18000d4d4  xor     rax, rsp
0x18000d4d7  mov     [rsp+1BB8h+var_48], rax
0x18000d4df  mov     eax, dword ptr [rsp+1BB8h+Size]
0x18000d4e6  mov     r12, r9
0x18000d4e9  mov     ebp, r8d
0x18000d4ec  mov     rbx, rcx
0x18000d4ef  mov     esi, edx
0x18000d4f1  mov     edi, eax
0x18000d4f3  lea     r15, [rax-1]
0x18000d4f7  add     r15, r9
0x18000d4fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d501  lea     rax, WPP_GLOBAL_Control
0x18000d508  cmp     rcx, rax
0x18000d50b  jz      short loc_18000D52E
0x18000d50d  test    byte ptr [rcx+1Ch], 2
0x18000d511  jz      short loc_18000D52E
0x18000d513  cmp     byte ptr [rcx+19h], 5
0x18000d517  jb      short loc_18000D52E
0x18000d519  mov     rcx, [rcx+10h]
0x18000d51d  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000d524  mov     edx, 28h ; '('
0x18000d529  call    WPP_SF_
0x18000d52e  mov     r8, rdi; Size
0x18000d531  lea     r13, [rsp+1BB8h+var_1B68]
0x18000d536  xor     edx, edx; Val
0x18000d538  lea     r14, [rsp+1BB8h+var_DD8]
0x18000d540  mov     rcx, r12; void *
0x18000d543  call    memset_0
0x18000d548  mov     rax, rbx
0x18000d54b  mov     [rsp+1BB8h+var_1B68], bp
0x18000d550  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000d554  lea     rdi, [rsi-1]
0x18000d558  add     rdi, rbx
0x18000d55b  mov     [rsp+1BB8h+var_1B70], rax
0x18000d560  and     rdi, 0FFFFFFFFFFFFFFFCh
0x18000d564  shl     bl, 3
0x18000d567  and     bl, 18h
0x18000d56a  mov     [rsp+1BB8h+var_1B78], bl
0x18000d56e  mov     [rsp+1BB8h+var_1B88], ebp
0x18000d572  lea     rdx, [rsp+1BB8h+var_1B78]
0x18000d577  mov     [rsp+1BB8h+var_1B90], 1
0x18000d57f  lea     rcx, [rsp+1BB8h+var_1B70]
0x18000d584  mov     r9, r14
0x18000d587  mov     [rsp+1BB8h+var_1B98], rdi
0x18000d58c  mov     r8, r13
0x18000d58f  call    ReadMrLine
0x18000d594  xor     r10d, r10d
0x18000d597  mov     ecx, eax
0x18000d599  test    eax, eax
0x18000d59b  jz      short loc_18000D5C6
0x18000d59d  sub     ecx, 1
0x18000d5a0  jz      loc_18000D78E
0x18000d5a6  sub     ecx, 1
0x18000d5a9  jz      loc_18000D78E
0x18000d5af  sub     ecx, 1
0x18000d5b2  jz      loc_18000D78E
0x18000d5b8  cmp     ecx, 1
0x18000d5bb  jz      loc_18000D8D7
0x18000d5c1  jmp     loc_18000D74F
0x18000d5c6  mov     r11d, r10d
0x18000d5c9  mov     si, 2
0x18000d5cd  movzx   edx, r11w
0x18000d5d1  movzx   ecx, word ptr [r14+rdx*2]
0x18000d5d6  cmp     ecx, ebp
0x18000d5d8  jz      loc_18000D73C
0x18000d5de  movzx   eax, r11w
0x18000d5e2  inc     eax
0x18000d5e4  cmp     eax, 6C2h
0x18000d5e9  ja      loc_18000D8A3
0x18000d5ef  movzx   ebx, word ptr [r14+rdx*2+2]
0x18000d5f5  mov     edx, ecx
0x18000d5f7  shr     rdx, 3
0x18000d5fb  movzx   r9d, bx
0x18000d5ff  add     rdx, r12
0x18000d602  sub     r9w, cx
0x18000d606  cmp     rdx, r15
0x18000d609  ja      loc_18000D87D
0x18000d60f  and     ecx, 80000007h
0x18000d615  jge     short loc_18000D61E
0x18000d617  dec     ecx
0x18000d619  or      ecx, 0FFFFFFF8h
0x18000d61c  inc     ecx
0x18000d61e  movzx   ecx, cl
0x18000d621  mov     r8d, 0FFh
0x18000d627  sar     r8d, cl
0x18000d62a  or      r8b, [rdx]
0x18000d62d  movzx   eax, r9w
0x18000d631  add     eax, ecx
0x18000d633  mov     [rdx], r8b
0x18000d636  cmp     eax, 7
0x18000d639  ja      short loc_18000D655
0x18000d63b  movzx   eax, r9w
0x18000d63f  add     eax, ecx
0x18000d641  lea     rcx, qword_1800440A0
0x18000d648  mov     cl, [rax+rcx]
0x18000d64b  and     cl, r8b
0x18000d64e  mov     [rdx], cl
0x18000d650  jmp     loc_18000D725
0x18000d655  lea     eax, [rcx-8]
0x18000d658  add     r9w, ax
0x18000d65c  lea     rcx, [rdx+1]
0x18000d660  movzx   edx, r9w
0x18000d664  shr     dx, 3
0x18000d668  movzx   eax, dx
0x18000d66b  shl     ax, 3
0x18000d66f  sub     r9w, ax
0x18000d673  mov     eax, 7
0x18000d678  cmp     dx, ax
0x18000d67b  mov     eax, r10d
0x18000d67e  jb      short loc_18000D6ED
0x18000d680  test    cl, 3
0x18000d683  jnz     short loc_18000D6CD
0x18000d685  test    eax, eax
0x18000d687  jnz     short loc_18000D6CD
0x18000d689  movzx   eax, dx
0x18000d68c  shr     ax, 2
0x18000d690  movzx   r8d, ax
0x18000d694  mov     eax, r10d
0x18000d697  test    r8d, r8d
0x18000d69a  jz      short loc_18000D6BD
0x18000d69c  lea     r10, [r15-3]
0x18000d6a0  cmp     rcx, r10
0x18000d6a3  ja      loc_18000D7BB
0x18000d6a9  mov     dword ptr [rcx], 0FFFFFFFFh
0x18000d6af  inc     eax
0x18000d6b1  add     rcx, 4
0x18000d6b5  cmp     eax, r8d
0x18000d6b8  jb      short loc_18000D6A0
0x18000d6ba  xor     r10d, r10d
0x18000d6bd  shl     r8w, 2
0x18000d6c2  mov     eax, 1
0x18000d6c7  sub     dx, r8w
0x18000d6cb  jmp     short loc_18000D6E6
0x18000d6cd  cmp     rcx, r15
0x18000d6d0  ja      loc_18000D7F0
0x18000d6d6  mov     byte ptr [rcx], 0FFh
0x18000d6d9  mov     r8d, 0FFFFh
0x18000d6df  inc     rcx
0x18000d6e2  add     dx, r8w
0x18000d6e6  test    dx, dx
0x18000d6e9  jnz     short loc_18000D680
0x18000d6eb  jmp     short loc_18000D70C
0x18000d6ed  movzx   r8d, dx
0x18000d6f1  test    r8d, r8d
0x18000d6f4  jz      short loc_18000D70C
0x18000d6f6  cmp     rcx, r15
0x18000d6f9  ja      loc_18000D825
0x18000d6ff  mov     byte ptr [rcx], 0FFh
0x18000d702  inc     eax
0x18000d704  inc     rcx
0x18000d707  cmp     eax, r8d
0x18000d70a  jb      short loc_18000D6F6
0x18000d70c  cmp     rcx, r15
0x18000d70f  ja      loc_18000D857
0x18000d715  movzx   eax, r9w
0x18000d719  lea     rdx, qword_1800440A0
0x18000d720  mov     al, [rax+rdx]
0x18000d723  mov     [rcx], al
0x18000d725  cmp     ebx, ebp
0x18000d727  jz      short loc_18000D73C
0x18000d729  add     r11w, si
0x18000d72d  mov     eax, 6C3h
0x18000d732  cmp     r11w, ax
0x18000d736  jb      loc_18000D5CD
0x18000d73c  mov     rax, rbp
0x18000d73f  shr     rax, 3
0x18000d743  add     r12, rax
0x18000d746  mov     rax, r13
0x18000d749  mov     r13, r14
0x18000d74c  mov     r14, rax
0x18000d74f  cmp     [rsp+1BB8h+var_1B70], rdi
0x18000d754  jbe     loc_18000D56E
0x18000d75a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d761  lea     rax, WPP_GLOBAL_Control
0x18000d768  cmp     rcx, rax
0x18000d76b  jz      short loc_18000D78E
0x18000d76d  test    byte ptr [rcx+1Ch], 2
0x18000d771  jz      short loc_18000D78E
0x18000d773  cmp     byte ptr [rcx+19h], 2
0x18000d777  jb      short loc_18000D78E
0x18000d779  mov     rcx, [rcx+10h]
0x18000d77d  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000d784  mov     edx, 2Fh ; '/'
0x18000d789  call    WPP_SF_
0x18000d78e  xor     eax, eax
0x18000d790  mov     rcx, [rsp+1BB8h+var_48]
0x18000d798  xor     rcx, rsp; StackCookie
0x18000d79b  call    __security_check_cookie
0x18000d7a0  mov     rbx, [rsp+1BB8h+arg_8]
0x18000d7a8  add     rsp, 1B80h
0x18000d7af  pop     r15
0x18000d7b1  pop     r14
0x18000d7b3  pop     r13
0x18000d7b5  pop     r12
0x18000d7b7  pop     rdi
0x18000d7b8  pop     rsi
0x18000d7b9  pop     rbp
0x18000d7ba  retn
0x18000d7bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7c2  lea     rax, WPP_GLOBAL_Control
0x18000d7c9  cmp     rcx, rax
0x18000d7cc  jz      loc_18000D8D7
0x18000d7d2  test    [rcx+1Ch], sil
0x18000d7d6  jz      loc_18000D8D7
0x18000d7dc  cmp     [rcx+19h], sil
0x18000d7e0  jb      loc_18000D8D7
0x18000d7e6  mov     edx, 2Bh ; '+'
0x18000d7eb  jmp     loc_18000D8C7
0x18000d7f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7f7  lea     rax, WPP_GLOBAL_Control
0x18000d7fe  cmp     rcx, rax
0x18000d801  jz      loc_18000D8D7
0x18000d807  test    [rcx+1Ch], sil
0x18000d80b  jz      loc_18000D8D7
0x18000d811  cmp     [rcx+19h], sil
0x18000d815  jb      loc_18000D8D7
0x18000d81b  mov     edx, 2Ch ; ','
0x18000d820  jmp     loc_18000D8C7
0x18000d825  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d82c  lea     rax, WPP_GLOBAL_Control
0x18000d833  cmp     rcx, rax
0x18000d836  jz      loc_18000D8D7
0x18000d83c  test    [rcx+1Ch], sil
0x18000d840  jz      loc_18000D8D7
0x18000d846  cmp     [rcx+19h], sil
0x18000d84a  jb      loc_18000D8D7
0x18000d850  mov     edx, 2Dh ; '-'
0x18000d855  jmp     short loc_18000D8C7
0x18000d857  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d85e  lea     rax, WPP_GLOBAL_Control
0x18000d865  cmp     rcx, rax
0x18000d868  jz      short loc_18000D8D7
0x18000d86a  test    [rcx+1Ch], sil
0x18000d86e  jz      short loc_18000D8D7
0x18000d870  cmp     [rcx+19h], sil
0x18000d874  jb      short loc_18000D8D7
0x18000d876  mov     edx, 2Eh ; '.'
0x18000d87b  jmp     short loc_18000D8C7
0x18000d87d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d884  lea     rax, WPP_GLOBAL_Control
0x18000d88b  cmp     rcx, rax
0x18000d88e  jz      short loc_18000D8D7
0x18000d890  test    [rcx+1Ch], sil
0x18000d894  jz      short loc_18000D8D7
0x18000d896  cmp     [rcx+19h], sil
0x18000d89a  jb      short loc_18000D8D7
0x18000d89c  mov     edx, 2Ah ; '*'
0x18000d8a1  jmp     short loc_18000D8C7
0x18000d8a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8aa  lea     rax, WPP_GLOBAL_Control
0x18000d8b1  cmp     rcx, rax
0x18000d8b4  jz      short loc_18000D8D7
0x18000d8b6  test    [rcx+1Ch], sil
0x18000d8ba  jz      short loc_18000D8D7
0x18000d8bc  cmp     [rcx+19h], sil
0x18000d8c0  jb      short loc_18000D8D7
0x18000d8c2  mov     edx, 29h ; ')'
0x18000d8c7  mov     rcx, [rcx+10h]
0x18000d8cb  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000d8d2  call    WPP_SF_
0x18000d8d7  mov     eax, 1
0x18000d8dc  jmp     loc_18000D790
```
