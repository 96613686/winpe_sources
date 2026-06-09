# TiffUncompressMmrPageRaw

- ea: `0x18000da70`
- end: `0x18000dea2`
- name: `TiffUncompressMmrPageRaw`
- size: `1074`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, char *, size_t Size)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000d990`

## callees

- `0x180009f04`
- `0x18000c750`
- `0x18000da70`
- `0x18001899e`
- `0x1800189d0`
- `0x180018a60`

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
      *v20 = v23 & *((_BYTE *)qword_1800440D0 + v22 + (unsigned int)v21);
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
    *(_BYTE *)v25 = *((_BYTE *)qword_1800440D0 + v27);
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
0x18000da70  mov     [rsp+arg_8], rbx
0x18000da75  push    rbp
0x18000da76  push    rsi
0x18000da77  push    rdi
0x18000da78  push    r12
0x18000da7a  push    r13
0x18000da7c  push    r14
0x18000da7e  push    r15
0x18000da80  mov     eax, 1B80h
0x18000da85  call    _alloca_probe
0x18000da8a  sub     rsp, rax
0x18000da8d  mov     rax, cs:__security_cookie
0x18000da94  xor     rax, rsp
0x18000da97  mov     [rsp+1BB8h+var_48], rax
0x18000da9f  mov     eax, dword ptr [rsp+1BB8h+Size]
0x18000daa6  mov     r12, r9
0x18000daa9  mov     ebp, r8d
0x18000daac  mov     rbx, rcx
0x18000daaf  mov     esi, edx
0x18000dab1  mov     edi, eax
0x18000dab3  lea     r15, [rax-1]
0x18000dab7  add     r15, r9
0x18000daba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dac1  lea     rax, WPP_GLOBAL_Control
0x18000dac8  cmp     rcx, rax
0x18000dacb  jz      short loc_18000DAEE
0x18000dacd  test    byte ptr [rcx+1Ch], 2
0x18000dad1  jz      short loc_18000DAEE
0x18000dad3  cmp     byte ptr [rcx+19h], 5
0x18000dad7  jb      short loc_18000DAEE
0x18000dad9  mov     rcx, [rcx+10h]
0x18000dadd  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000dae4  mov     edx, 28h ; '('
0x18000dae9  call    WPP_SF_
0x18000daee  mov     r8, rdi; Size
0x18000daf1  lea     r13, [rsp+1BB8h+var_1B68]
0x18000daf6  xor     edx, edx; Val
0x18000daf8  lea     r14, [rsp+1BB8h+var_DD8]
0x18000db00  mov     rcx, r12; void *
0x18000db03  call    memset_0
0x18000db08  mov     rax, rbx
0x18000db0b  mov     [rsp+1BB8h+var_1B68], bp
0x18000db10  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000db14  lea     rdi, [rsi-1]
0x18000db18  add     rdi, rbx
0x18000db1b  mov     [rsp+1BB8h+var_1B70], rax
0x18000db20  and     rdi, 0FFFFFFFFFFFFFFFCh
0x18000db24  shl     bl, 3
0x18000db27  and     bl, 18h
0x18000db2a  mov     [rsp+1BB8h+var_1B78], bl
0x18000db2e  mov     [rsp+1BB8h+var_1B88], ebp
0x18000db32  lea     rdx, [rsp+1BB8h+var_1B78]
0x18000db37  mov     [rsp+1BB8h+var_1B90], 1
0x18000db3f  lea     rcx, [rsp+1BB8h+var_1B70]
0x18000db44  mov     r9, r14
0x18000db47  mov     [rsp+1BB8h+var_1B98], rdi
0x18000db4c  mov     r8, r13
0x18000db4f  call    ReadMrLine
0x18000db54  xor     r10d, r10d
0x18000db57  mov     ecx, eax
0x18000db59  test    eax, eax
0x18000db5b  jz      short loc_18000DB86
0x18000db5d  sub     ecx, 1
0x18000db60  jz      loc_18000DD4E
0x18000db66  sub     ecx, 1
0x18000db69  jz      loc_18000DD4E
0x18000db6f  sub     ecx, 1
0x18000db72  jz      loc_18000DD4E
0x18000db78  cmp     ecx, 1
0x18000db7b  jz      loc_18000DE98
0x18000db81  jmp     loc_18000DD0F
0x18000db86  mov     r11d, r10d
0x18000db89  mov     si, 2
0x18000db8d  movzx   edx, r11w
0x18000db91  movzx   ecx, word ptr [r14+rdx*2]
0x18000db96  cmp     ecx, ebp
0x18000db98  jz      loc_18000DCFC
0x18000db9e  movzx   eax, r11w
0x18000dba2  inc     eax
0x18000dba4  cmp     eax, 6C2h
0x18000dba9  ja      loc_18000DE64
0x18000dbaf  movzx   ebx, word ptr [r14+rdx*2+2]
0x18000dbb5  mov     edx, ecx
0x18000dbb7  shr     rdx, 3
0x18000dbbb  movzx   r9d, bx
0x18000dbbf  add     rdx, r12
0x18000dbc2  sub     r9w, cx
0x18000dbc6  cmp     rdx, r15
0x18000dbc9  ja      loc_18000DE3E
0x18000dbcf  and     ecx, 80000007h
0x18000dbd5  jge     short loc_18000DBDE
0x18000dbd7  dec     ecx
0x18000dbd9  or      ecx, 0FFFFFFF8h
0x18000dbdc  inc     ecx
0x18000dbde  movzx   ecx, cl
0x18000dbe1  mov     r8d, 0FFh
0x18000dbe7  sar     r8d, cl
0x18000dbea  or      r8b, [rdx]
0x18000dbed  movzx   eax, r9w
0x18000dbf1  add     eax, ecx
0x18000dbf3  mov     [rdx], r8b
0x18000dbf6  cmp     eax, 7
0x18000dbf9  ja      short loc_18000DC15
0x18000dbfb  movzx   eax, r9w
0x18000dbff  add     eax, ecx
0x18000dc01  lea     rcx, qword_1800440D0
0x18000dc08  mov     cl, [rax+rcx]
0x18000dc0b  and     cl, r8b
0x18000dc0e  mov     [rdx], cl
0x18000dc10  jmp     loc_18000DCE5
0x18000dc15  lea     eax, [rcx-8]
0x18000dc18  add     r9w, ax
0x18000dc1c  lea     rcx, [rdx+1]
0x18000dc20  movzx   edx, r9w
0x18000dc24  shr     dx, 3
0x18000dc28  movzx   eax, dx
0x18000dc2b  shl     ax, 3
0x18000dc2f  sub     r9w, ax
0x18000dc33  mov     eax, 7
0x18000dc38  cmp     dx, ax
0x18000dc3b  mov     eax, r10d
0x18000dc3e  jb      short loc_18000DCAD
0x18000dc40  test    cl, 3
0x18000dc43  jnz     short loc_18000DC8D
0x18000dc45  test    eax, eax
0x18000dc47  jnz     short loc_18000DC8D
0x18000dc49  movzx   eax, dx
0x18000dc4c  shr     ax, 2
0x18000dc50  movzx   r8d, ax
0x18000dc54  mov     eax, r10d
0x18000dc57  test    r8d, r8d
0x18000dc5a  jz      short loc_18000DC7D
0x18000dc5c  lea     r10, [r15-3]
0x18000dc60  cmp     rcx, r10
0x18000dc63  ja      loc_18000DD7C
0x18000dc69  mov     dword ptr [rcx], 0FFFFFFFFh
0x18000dc6f  inc     eax
0x18000dc71  add     rcx, 4
0x18000dc75  cmp     eax, r8d
0x18000dc78  jb      short loc_18000DC60
0x18000dc7a  xor     r10d, r10d
0x18000dc7d  shl     r8w, 2
0x18000dc82  mov     eax, 1
0x18000dc87  sub     dx, r8w
0x18000dc8b  jmp     short loc_18000DCA6
0x18000dc8d  cmp     rcx, r15
0x18000dc90  ja      loc_18000DDB1
0x18000dc96  mov     byte ptr [rcx], 0FFh
0x18000dc99  mov     r8d, 0FFFFh
0x18000dc9f  inc     rcx
0x18000dca2  add     dx, r8w
0x18000dca6  test    dx, dx
0x18000dca9  jnz     short loc_18000DC40
0x18000dcab  jmp     short loc_18000DCCC
0x18000dcad  movzx   r8d, dx
0x18000dcb1  test    r8d, r8d
0x18000dcb4  jz      short loc_18000DCCC
0x18000dcb6  cmp     rcx, r15
0x18000dcb9  ja      loc_18000DDE6
0x18000dcbf  mov     byte ptr [rcx], 0FFh
0x18000dcc2  inc     eax
0x18000dcc4  inc     rcx
0x18000dcc7  cmp     eax, r8d
0x18000dcca  jb      short loc_18000DCB6
0x18000dccc  cmp     rcx, r15
0x18000dccf  ja      loc_18000DE18
0x18000dcd5  movzx   eax, r9w
0x18000dcd9  lea     rdx, qword_1800440D0
0x18000dce0  mov     al, [rax+rdx]
0x18000dce3  mov     [rcx], al
0x18000dce5  cmp     ebx, ebp
0x18000dce7  jz      short loc_18000DCFC
0x18000dce9  add     r11w, si
0x18000dced  mov     eax, 6C3h
0x18000dcf2  cmp     r11w, ax
0x18000dcf6  jb      loc_18000DB8D
0x18000dcfc  mov     rax, rbp
0x18000dcff  shr     rax, 3
0x18000dd03  add     r12, rax
0x18000dd06  mov     rax, r13
0x18000dd09  mov     r13, r14
0x18000dd0c  mov     r14, rax
0x18000dd0f  cmp     [rsp+1BB8h+var_1B70], rdi
0x18000dd14  jbe     loc_18000DB2E
0x18000dd1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd21  lea     rax, WPP_GLOBAL_Control
0x18000dd28  cmp     rcx, rax
0x18000dd2b  jz      short loc_18000DD4E
0x18000dd2d  test    byte ptr [rcx+1Ch], 2
0x18000dd31  jz      short loc_18000DD4E
0x18000dd33  cmp     byte ptr [rcx+19h], 2
0x18000dd37  jb      short loc_18000DD4E
0x18000dd39  mov     rcx, [rcx+10h]
0x18000dd3d  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000dd44  mov     edx, 2Fh ; '/'
0x18000dd49  call    WPP_SF_
0x18000dd4e  xor     eax, eax
0x18000dd50  mov     rcx, [rsp+1BB8h+var_48]
0x18000dd58  xor     rcx, rsp; StackCookie
0x18000dd5b  call    __security_check_cookie
0x18000dd60  mov     rbx, [rsp+1BB8h+arg_8]
0x18000dd68  add     rsp, 1B80h
0x18000dd6f  pop     r15
0x18000dd71  pop     r14
0x18000dd73  pop     r13
0x18000dd75  pop     r12
0x18000dd77  pop     rdi
0x18000dd78  pop     rsi
0x18000dd79  pop     rbp
0x18000dd7a  retn
0x18000dd7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd83  lea     rax, WPP_GLOBAL_Control
0x18000dd8a  cmp     rcx, rax
0x18000dd8d  jz      loc_18000DE98
0x18000dd93  test    [rcx+1Ch], sil
0x18000dd97  jz      loc_18000DE98
0x18000dd9d  cmp     [rcx+19h], sil
0x18000dda1  jb      loc_18000DE98
0x18000dda7  mov     edx, 2Bh ; '+'
0x18000ddac  jmp     loc_18000DE88
0x18000ddb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ddb8  lea     rax, WPP_GLOBAL_Control
0x18000ddbf  cmp     rcx, rax
0x18000ddc2  jz      loc_18000DE98
0x18000ddc8  test    [rcx+1Ch], sil
0x18000ddcc  jz      loc_18000DE98
0x18000ddd2  cmp     [rcx+19h], sil
0x18000ddd6  jb      loc_18000DE98
0x18000dddc  mov     edx, 2Ch ; ','
0x18000dde1  jmp     loc_18000DE88
0x18000dde6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dded  lea     rax, WPP_GLOBAL_Control
0x18000ddf4  cmp     rcx, rax
0x18000ddf7  jz      loc_18000DE98
0x18000ddfd  test    [rcx+1Ch], sil
0x18000de01  jz      loc_18000DE98
0x18000de07  cmp     [rcx+19h], sil
0x18000de0b  jb      loc_18000DE98
0x18000de11  mov     edx, 2Dh ; '-'
0x18000de16  jmp     short loc_18000DE88
0x18000de18  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de1f  lea     rax, WPP_GLOBAL_Control
0x18000de26  cmp     rcx, rax
0x18000de29  jz      short loc_18000DE98
0x18000de2b  test    [rcx+1Ch], sil
0x18000de2f  jz      short loc_18000DE98
0x18000de31  cmp     [rcx+19h], sil
0x18000de35  jb      short loc_18000DE98
0x18000de37  mov     edx, 2Eh ; '.'
0x18000de3c  jmp     short loc_18000DE88
0x18000de3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de45  lea     rax, WPP_GLOBAL_Control
0x18000de4c  cmp     rcx, rax
0x18000de4f  jz      short loc_18000DE98
0x18000de51  test    [rcx+1Ch], sil
0x18000de55  jz      short loc_18000DE98
0x18000de57  cmp     [rcx+19h], sil
0x18000de5b  jb      short loc_18000DE98
0x18000de5d  mov     edx, 2Ah ; '*'
0x18000de62  jmp     short loc_18000DE88
0x18000de64  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de6b  lea     rax, WPP_GLOBAL_Control
0x18000de72  cmp     rcx, rax
0x18000de75  jz      short loc_18000DE98
0x18000de77  test    [rcx+1Ch], sil
0x18000de7b  jz      short loc_18000DE98
0x18000de7d  cmp     [rcx+19h], sil
0x18000de81  jb      short loc_18000DE98
0x18000de83  mov     edx, 29h ; ')'
0x18000de88  mov     rcx, [rcx+10h]
0x18000de8c  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000de93  call    WPP_SF_
0x18000de98  mov     eax, 1
0x18000de9d  jmp     loc_18000DD50
```
