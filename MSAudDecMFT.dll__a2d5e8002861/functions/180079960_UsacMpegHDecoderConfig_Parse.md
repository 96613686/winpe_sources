# UsacMpegHDecoderConfig_Parse

- ea: `0x180079960`
- end: `0x180079f4f`
- name: `UsacMpegHDecoderConfig_Parse`
- size: `1519`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18004afa0`

## callees

- `0x1800110c0`
- `0x180012580`
- `0x180013550`
- `0x180079960`
- `0x18007a128`
- `0x18007a198`
- `0x18007a444`
- `0x1800960c0`

## pseudocode

```c
__int64 __fastcall UsacMpegHDecoderConfig_Parse(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  char v6; // bl
  char v7; // r15
  int v8; // eax
  __int64 v9; // r8
  unsigned int v10; // ecx
  unsigned int v11; // r12d
  int v12; // r13d
  int v13; // esi
  int v14; // edx
  int v15; // r9d
  __int64 v16; // rsi
  char v17; // al
  int v18; // edx
  int v19; // edx
  int v20; // edx
  __int64 v21; // rbx
  __int64 result; // rax
  unsigned int v23; // esi
  __int64 v24; // r8
  int v25; // ebx
  __int64 v26; // r8
  __int64 v27; // r8
  unsigned int v28; // eax
  int v29; // r10d
  int v30; // r9d
  __int64 v31; // r8
  int v32; // edx
  __int64 (__fastcall *v33)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, int); // rax
  int v34; // [rsp+20h] [rbp-A8h]
  int v35; // [rsp+28h] [rbp-A0h]
  int v36; // [rsp+30h] [rbp-98h]
  int v37; // [rsp+38h] [rbp-90h]
  unsigned int v38; // [rsp+80h] [rbp-48h]
  unsigned int v39; // [rsp+84h] [rbp-44h]
  int v40; // [rsp+88h] [rbp-40h]
  char v41; // [rsp+D0h] [rbp+8h]
  char v42; // [rsp+E8h] [rbp+20h]

  v6 = 0;
  v42 = 0;
  v7 = 0;
  v41 = 0;
  v8 = escapedValue_0(a2, 4, 8, 16) + 1;
  v40 = v8;
  *(_DWORD *)(a1 + 8) = v8;
  if ( v8 > 10 )
    return 1026;
  *(_BYTE *)(a1 + 3) = 0;
  v10 = *(unsigned __int8 *)(a1 + 1224);
  *(_BYTE *)(a1 + 4) = v10;
  if ( *(_DWORD *)(a1 + 1200) == 42 )
  {
    if ( (char)*((_DWORD *)qword_1800BA980 + v10) > 24 )
      return 1025;
    v6 = BYTE1(*((_DWORD *)qword_1800BA980 + v10));
    v7 = HIBYTE(*((_DWORD *)qword_1800BA980 + v10));
    v41 = BYTE2(*((_DWORD *)qword_1800BA980 + v10));
    v42 = v6;
  }
  v11 = 0;
  v39 = -1;
  v12 = 0;
  v13 = 0;
  while ( 1 )
  {
    v38 = v13;
    if ( v13 >= v8 )
      break;
    v14 = CDKreadBits(a2, 2, v9) | 0x10;
    v16 = 5LL * v13;
    *(_DWORD *)(a1 + 4 * v16 + 12) = v14;
    v9 = *(unsigned int *)(a1 + 1200);
    if ( (_DWORD)v9 == 42 )
    {
      if ( v14 == 16 )
      {
        v17 = v41;
        v42 = --v6;
      }
      else if ( v14 == 17 )
      {
        v17 = --v41;
      }
      else
      {
        v17 = v41;
        if ( v14 == 18 )
          --v7;
      }
      if ( *(_BYTE *)(a1 + 4) && (v17 < 0 || v6 < 0 || v7 < 0) )
        return 1025;
    }
    v18 = v14 - 16;
    if ( !v18 )
    {
      if ( (unsigned int)CDKreadBit((__int64)a2) )
        return 1026;
      *(_BYTE *)(a1 + 4 * v16 + 16) = CDKreadBits(a2, 1, v31);
      if ( *(_BYTE *)(a1 + 2) )
      {
        if ( !a3[10] )
          return 513;
        *(_BYTE *)(a1 + 4 * v16 + 17) = CDKreadBit((__int64)a2);
        *(_BYTE *)(a1 + 4 * v16 + 18) = CDKreadBit((__int64)a2);
        *(_BYTE *)(a1 + 4 * v16 + 19) = CDKreadBit((__int64)a2);
        v37 = v12;
        v36 = 0;
        v35 = *(_DWORD *)(a1 + 1200);
        v34 = *(_DWORD *)(a1 + 1208);
        if ( ((unsigned int (__fastcall *)(_QWORD, _DWORD *, _QWORD, _QWORD))a3[10])(
               a3[11],
               a2,
               *(unsigned int *)(a1 + 1204),
               *(unsigned int *)(a1 + 1220)) )
        {
          return 1025;
        }
      }
      ++*(_BYTE *)(a1 + 3);
      goto LABEL_51;
    }
    v19 = v18 - 1;
    if ( !v19 )
    {
      if ( (unsigned int)CDKreadBit((__int64)a2) )
        return 1026;
      *(_BYTE *)(a1 + 4 * v16 + 16) = CDKreadBits(a2, 1, v24);
      if ( *(_BYTE *)(a1 + 2) )
      {
        if ( !a3[10] )
          return 513;
        *(_BYTE *)(a1 + 4 * v16 + 17) = CDKreadBit((__int64)a2);
        *(_BYTE *)(a1 + 4 * v16 + 18) = CDKreadBit((__int64)a2);
        *(_BYTE *)(a1 + 4 * v16 + 19) = CDKreadBit((__int64)a2);
        v25 = skipSbrHeader(a2, 1);
        *(_BYTE *)(a1 + 4 * v16 + 20) = CDKreadBits(a2, 2, v26);
        CDKpushBack_0(a2, (unsigned int)(v25 + 2));
        v37 = v12;
        v36 = (unsigned __int8)(*(_BYTE *)(a1 + 4 * v16 + 20) - 1) > 1u;
        v35 = *(_DWORD *)(a1 + 1200);
        v34 = *(_DWORD *)(a1 + 1208);
        if ( ((unsigned int (__fastcall *)(_QWORD, _DWORD *, _QWORD, _QWORD))a3[10])(
               a3[11],
               a2,
               *(unsigned int *)(a1 + 1204),
               *(unsigned int *)(a1 + 1220)) )
        {
          return 1025;
        }
        v28 = CDKreadBits(a2, 2, v27);
        v9 = v28;
        *(_BYTE *)(a1 + 4 * v16 + 20) = v28;
        if ( (_BYTE)v28 )
        {
          if ( !a3[8] )
            return 513;
          v29 = 4 * *(_DWORD *)(a1 + 1208);
          if ( *(_BYTE *)(a1 + 2) != 1 )
            v29 = *(_DWORD *)(a1 + 1208);
          if ( *(_BYTE *)(a1 + 2) == 2 )
            v29 = 8 * v29 / 3;
          v30 = 2 * v29;
          if ( *(_BYTE *)(a1 + 2) != 3 )
            v30 = v29;
          v37 = *(unsigned __int8 *)(a1 + 1);
          v36 = (unsigned __int8)v28;
          v35 = 1;
          v34 = v30;
          if ( ((unsigned int (__fastcall *)(_QWORD, _DWORD *, _QWORD, _QWORD))a3[8])(
                 a3[9],
                 a2,
                 *(unsigned int *)(a1 + 1200),
                 *(unsigned int *)(a1 + 1220)) )
          {
            return 1025;
          }
        }
      }
      else
      {
        *(_BYTE *)(a1 + 4 * v16 + 20) = 0;
      }
      *(_BYTE *)(a1 + 3) += 2;
      goto LABEL_51;
    }
    v20 = v19 - 1;
    if ( !v20 )
    {
      *(_BYTE *)(a1 + 4 * v16 + 16) = 0;
      ++*(_BYTE *)(a1 + 3);
      if ( *(_BYTE *)(a1 + 2) )
      {
        if ( !a3[10] )
          return 513;
        *(_WORD *)(a1 + 4 * v16 + 17) = 0;
        *(_BYTE *)(a1 + 4 * v16 + 19) = 0;
        v37 = v12;
        v36 = 3;
        v35 = *(_DWORD *)(a1 + 1200);
        v34 = *(_DWORD *)(a1 + 1208);
        if ( ((unsigned int (__fastcall *)(_QWORD, _DWORD *, _QWORD, _QWORD))a3[10])(
               a3[11],
               a2,
               *(unsigned int *)(a1 + 1204),
               *(unsigned int *)(a1 + 1220)) )
        {
          return 1025;
        }
      }
LABEL_51:
      v23 = v38;
      ++v12;
      goto LABEL_52;
    }
    if ( v20 != 1 )
      return 1025;
    v21 = a1 + 4 * v16;
    result = extElementConfig((int)v21 + 24, (_DWORD)a2, (_DWORD)a3, v15, v34, v35, v36, v37, v9);
    v11 = result;
    v9 = v39;
    v23 = v38;
    if ( *(_DWORD *)(v21 + 24) == 4 )
      v9 = v38;
    v39 = v9;
    if ( (_DWORD)result )
      return result;
LABEL_52:
    v6 = v42;
    v13 = v23 + 1;
    v8 = v40;
  }
  v32 = *(_DWORD *)(a1 + 1200);
  if ( v32 != 42 )
    goto LABEL_57;
  if ( *(_BYTE *)(a1 + 4) )
  {
    if ( !((unsigned __int8)v6 | (unsigned __int8)(v41 | v7)) )
      goto LABEL_57;
    return 1025;
  }
  else
  {
    if ( -v7 - 2 * v41 - v6 < *(unsigned __int8 *)(a1 + 212) )
      return 1025;
LABEL_57:
    if ( v39 != -1 )
      return v11;
    v33 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, int))a3[14];
    if ( !v33 )
      return v11;
    result = v33(a3[15], 0, 0, 0, 0, 0, v32);
    v11 = result;
    if ( !(_DWORD)result )
      return v11;
  }
  return result;
}

```

## disassembly

```asm
0x180079960  mov     [rsp+arg_8], rbx
0x180079965  push    rbp
0x180079966  push    rsi
0x180079967  push    rdi
0x180079968  push    r12
0x18007996a  push    r13
0x18007996c  push    r14
0x18007996e  push    r15
0x180079970  sub     rsp, 90h
0x180079977  mov     rbp, rdx
0x18007997a  mov     r14, r8
0x18007997d  mov     edx, 4
0x180079982  mov     rdi, rcx
0x180079985  xor     bl, bl
0x180079987  mov     rcx, rbp
0x18007998a  mov     byte ptr [rsp+0C8h+arg_18], bl
0x180079991  xor     r15b, r15b
0x180079994  mov     [rsp+0C8h+arg_0], bl
0x18007999b  lea     r9d, [rdx+0Ch]
0x18007999f  lea     r8d, [rdx+4]
0x1800799a3  call    escapedValue_0
0x1800799a8  inc     eax
0x1800799aa  mov     [rsp+0C8h+var_40], eax
0x1800799b1  mov     [rdi+8], eax
0x1800799b4  cmp     eax, 0Ah
0x1800799b7  jg      loc_180079F2E
0x1800799bd  mov     [rdi+3], bl
0x1800799c0  movzx   ecx, byte ptr [rdi+4C8h]
0x1800799c7  mov     [rdi+4], cl
0x1800799ca  cmp     dword ptr [rdi+4B0h], 2Ah ; '*'
0x1800799d1  jnz     short loc_180079A19
0x1800799d3  mov     eax, ecx
0x1800799d5  lea     rcx, qword_1800BA980
0x1800799dc  mov     eax, [rcx+rax*4]
0x1800799df  mov     [rsp+0C8h+arg_18], eax
0x1800799e6  cmp     al, 18h
0x1800799e8  jg      loc_180079F27
0x1800799ee  mov     al, byte ptr [rsp+0C8h+arg_18+2]
0x1800799f5  mov     bl, byte ptr [rsp+0C8h+arg_18+1]
0x1800799fc  mov     r15b, byte ptr [rsp+0C8h+arg_18+3]
0x180079a04  mov     [rsp+0C8h+arg_0], al
0x180079a0b  mov     eax, [rsp+0C8h+var_40]
0x180079a12  mov     byte ptr [rsp+0C8h+arg_18], bl
0x180079a19  xor     r12d, r12d
0x180079a1c  mov     [rsp+0C8h+var_44], 0FFFFFFFFh
0x180079a27  xor     r13d, r13d
0x180079a2a  xor     esi, esi
0x180079a2c  mov     [rsp+0C8h+var_48], esi
0x180079a33  cmp     esi, eax
0x180079a35  jge     loc_180079EA2
0x180079a3b  mov     edx, 2
0x180079a40  mov     rcx, rbp
0x180079a43  call    CDKreadBits
0x180079a48  movsxd  rcx, esi
0x180079a4b  mov     edx, eax
0x180079a4d  or      edx, 10h
0x180079a50  lea     rsi, [rcx+rcx*4]
0x180079a54  mov     [rdi+rsi*4+0Ch], edx
0x180079a58  mov     r8d, [rdi+4B0h]
0x180079a5f  cmp     r8d, 2Ah ; '*'
0x180079a63  jnz     short loc_180079AC7
0x180079a65  mov     eax, edx
0x180079a67  sub     eax, 10h
0x180079a6a  jz      short loc_180079A94
0x180079a6c  sub     eax, 1
0x180079a6f  jz      short loc_180079A82
0x180079a71  cmp     eax, 1
0x180079a74  mov     al, [rsp+0C8h+arg_0]
0x180079a7b  jnz     short loc_180079AA4
0x180079a7d  dec     r15b
0x180079a80  jmp     short loc_180079AA4
0x180079a82  mov     al, [rsp+0C8h+arg_0]
0x180079a89  dec     al
0x180079a8b  mov     [rsp+0C8h+arg_0], al
0x180079a92  jmp     short loc_180079AA4
0x180079a94  mov     al, [rsp+0C8h+arg_0]
0x180079a9b  dec     bl
0x180079a9d  mov     byte ptr [rsp+0C8h+arg_18], bl
0x180079aa4  cmp     byte ptr [rdi+4], 0
0x180079aa8  jz      short loc_180079AC7
0x180079aaa  test    al, al
0x180079aac  js      loc_180079F27
0x180079ab2  test    bl, bl
0x180079ab4  js      loc_180079F27
0x180079aba  xor     ebx, ebx
0x180079abc  test    r15b, r15b
0x180079abf  js      loc_180079F27
0x180079ac5  jmp     short loc_180079AC9
0x180079ac7  xor     ebx, ebx
0x180079ac9  sub     edx, 10h
0x180079acc  jz      loc_180079DAA
0x180079ad2  sub     edx, 1
0x180079ad5  jz      loc_180079BD0
0x180079adb  sub     edx, 1
0x180079ade  jz      short loc_180079B30
0x180079ae0  cmp     edx, 1
0x180079ae3  jnz     loc_180079F27
0x180079ae9  mov     [rsp+0C8h+var_88], r8d
0x180079aee  lea     rbx, [rdi+rsi*4]
0x180079af2  lea     rcx, [rbx+18h]
0x180079af6  mov     r8, r14
0x180079af9  mov     rdx, rbp
0x180079afc  call    extElementConfig
0x180079b01  cmp     dword ptr [rbx+18h], 4
0x180079b05  mov     r12d, eax
0x180079b08  mov     r8d, [rsp+0C8h+var_44]
0x180079b10  mov     esi, [rsp+0C8h+var_48]
0x180079b17  cmovz   r8d, esi
0x180079b1b  mov     [rsp+0C8h+var_44], r8d
0x180079b23  test    eax, eax
0x180079b25  jnz     loc_180079F33
0x180079b2b  jmp     loc_180079E83
0x180079b30  mov     [rdi+rsi*4+10h], bl
0x180079b34  inc     byte ptr [rdi+3]
0x180079b37  cmp     [rdi+2], bl
0x180079b3a  jbe     loc_180079E79
0x180079b40  cmp     [r14+50h], rbx
0x180079b44  jz      loc_180079E98
0x180079b4a  mov     [rsp+0C8h+var_60], bl
0x180079b4e  lea     rax, [rdi+4D4h]
0x180079b55  mov     word ptr [rdi+rsi*4+11h], 0
0x180079b5c  mov     rdx, rbp
0x180079b5f  mov     [rdi+rsi*4+13h], bl
0x180079b63  mov     cl, [rdi+4D2h]
0x180079b69  mov     r9d, [rdi+4C4h]
0x180079b70  mov     r8d, [rdi+4B4h]
0x180079b77  mov     [rsp+0C8h+var_68], 1
0x180079b7f  mov     [rsp+0C8h+var_70], rax
0x180079b84  mov     rax, [r14+50h]
0x180079b88  mov     byte ptr [rsp+0C8h+var_78], cl
0x180079b8c  mov     cl, [rdi+rsi*4+14h]
0x180079b90  mov     [rsp+0C8h+var_80], cl
0x180079b94  mov     ecx, [rdi+4B0h]
0x180079b9a  mov     byte ptr [rsp+0C8h+var_88], bl
0x180079b9e  mov     [rsp+0C8h+var_90], r13d
0x180079ba3  mov     [rsp+0C8h+var_98], 3
0x180079bab  mov     [rsp+0C8h+var_A0], ecx
0x180079baf  mov     ecx, [rdi+4B8h]
0x180079bb5  mov     [rsp+0C8h+var_A8], ecx
0x180079bb9  mov     rcx, [r14+58h]
0x180079bbd  call    cs:__guard_dispatch_icall_fptr
0x180079bc3  test    eax, eax
0x180079bc5  jnz     loc_180079F27
0x180079bcb  jmp     loc_180079E79
0x180079bd0  mov     rcx, rbp
0x180079bd3  call    CDKreadBit
0x180079bd8  test    eax, eax
0x180079bda  jnz     loc_180079F2E
0x180079be0  lea     edx, [rax+1]
0x180079be3  mov     rcx, rbp
0x180079be6  call    CDKreadBits
0x180079beb  mov     [rdi+rsi*4+10h], al
0x180079bef  cmp     [rdi+2], bl
0x180079bf2  jbe     loc_180079D9D
0x180079bf8  cmp     [r14+50h], rbx
0x180079bfc  jz      loc_180079E98
0x180079c02  mov     rcx, rbp
0x180079c05  call    CDKreadBit
0x180079c0a  mov     rcx, rbp
0x180079c0d  mov     [rdi+rsi*4+11h], al
0x180079c11  call    CDKreadBit
0x180079c16  mov     rcx, rbp
0x180079c19  mov     [rdi+rsi*4+12h], al
0x180079c1d  call    CDKreadBit
0x180079c22  mov     edx, 1
0x180079c27  mov     [rdi+rsi*4+13h], al
0x180079c2b  mov     rcx, rbp
0x180079c2e  call    skipSbrHeader
0x180079c33  mov     edx, 2
0x180079c38  mov     rcx, rbp
0x180079c3b  mov     ebx, eax
0x180079c3d  call    CDKreadBits
0x180079c42  lea     edx, [rbx+2]
0x180079c45  mov     [rdi+rsi*4+14h], al
0x180079c49  mov     rcx, rbp
0x180079c4c  call    CDKpushBack_0
0x180079c51  mov     cl, [rdi+4D2h]
0x180079c57  xor     ebx, ebx
0x180079c59  mov     dl, [rdi+rsi*4+14h]
0x180079c5d  mov     r8d, ebx
0x180079c60  mov     r9d, [rdi+4C4h]
0x180079c67  mov     [rsp+0C8h+var_60], bl
0x180079c6b  mov     [rsp+0C8h+var_68], 1
0x180079c73  lea     eax, [rdx-1]
0x180079c76  cmp     al, 1
0x180079c78  lea     rax, [rdi+4D4h]
0x180079c7f  mov     [rsp+0C8h+var_70], rax
0x180079c84  mov     rax, [r14+50h]
0x180079c88  setnbe  r8b
0x180079c8c  mov     byte ptr [rsp+0C8h+var_78], cl
0x180079c90  mov     cl, [rdi+rsi*4+11h]
0x180079c94  mov     [rsp+0C8h+var_80], dl
0x180079c98  mov     rdx, rbp
0x180079c9b  mov     byte ptr [rsp+0C8h+var_88], cl
0x180079c9f  mov     ecx, [rdi+4B0h]
0x180079ca5  mov     [rsp+0C8h+var_90], r13d
0x180079caa  mov     [rsp+0C8h+var_98], r8d
0x180079caf  mov     r8d, [rdi+4B4h]
0x180079cb6  mov     [rsp+0C8h+var_A0], ecx
0x180079cba  mov     ecx, [rdi+4B8h]
0x180079cc0  mov     [rsp+0C8h+var_A8], ecx
0x180079cc4  mov     rcx, [r14+58h]
0x180079cc8  call    cs:__guard_dispatch_icall_fptr
0x180079cce  test    eax, eax
0x180079cd0  jnz     loc_180079F27
0x180079cd6  lea     edx, [rbx+2]
0x180079cd9  mov     rcx, rbp
0x180079cdc  call    CDKreadBits
0x180079ce1  mov     r8d, eax
0x180079ce4  mov     [rdi+rsi*4+14h], r8b
0x180079ce9  test    al, al
0x180079ceb  jz      loc_180079DA1
0x180079cf1  cmp     [r14+40h], rbx
0x180079cf5  jz      loc_180079E98
0x180079cfb  mov     ecx, [rdi+4B8h]
0x180079d01  cmp     byte ptr [rdi+2], 1
0x180079d05  lea     r10d, ds:0[rcx*4]
0x180079d0d  cmovnz  r10d, ecx
0x180079d11  cmp     byte ptr [rdi+2], 2
0x180079d15  jnz     short loc_180079D30
0x180079d17  lea     ecx, ds:0[r10*8]
0x180079d1f  mov     eax, 55555556h
0x180079d24  imul    ecx
0x180079d26  mov     r10d, edx
0x180079d29  shr     r10d, 1Fh
0x180079d2d  add     r10d, edx
0x180079d30  movzx   edx, byte ptr [rdi+1]
0x180079d34  lea     rcx, [rdi+4D5h]
0x180079d3b  cmp     byte ptr [rdi+2], 3
0x180079d3f  lea     r9d, [r10+r10]
0x180079d43  mov     rax, [r14+40h]
0x180079d47  mov     [rsp+0C8h+var_78], rcx
0x180079d4c  cmovnz  r9d, r10d
0x180079d50  mov     cl, [rdi+4D2h]
0x180079d56  mov     [rsp+0C8h+var_80], cl
0x180079d5a  mov     rcx, [r14+48h]
0x180079d5e  mov     [rsp+0C8h+var_88], ebx
0x180079d62  mov     [rsp+0C8h+var_90], edx
0x180079d66  mov     rdx, rbp
0x180079d69  movzx   r8d, r8b
0x180079d6d  mov     [rsp+0C8h+var_98], r8d
0x180079d72  mov     r8d, [rdi+4B0h]
0x180079d79  mov     [rsp+0C8h+var_A0], 1
0x180079d81  mov     [rsp+0C8h+var_A8], r9d
0x180079d86  mov     r9d, [rdi+4C4h]
0x180079d8d  call    cs:__guard_dispatch_icall_fptr
0x180079d93  test    eax, eax
0x180079d95  jnz     loc_180079F27
0x180079d9b  jmp     short loc_180079DA1
0x180079d9d  mov     [rdi+rsi*4+14h], bl
0x180079da1  add     byte ptr [rdi+3], 2
0x180079da5  jmp     loc_180079E79
0x180079daa  mov     rcx, rbp
0x180079dad  call    CDKreadBit
0x180079db2  test    eax, eax
0x180079db4  jnz     loc_180079F2E
0x180079dba  lea     edx, [rax+1]
0x180079dbd  mov     rcx, rbp
0x180079dc0  call    CDKreadBits
0x180079dc5  mov     [rdi+rsi*4+10h], al
0x180079dc9  cmp     [rdi+2], bl
0x180079dcc  jbe     loc_180079E76
0x180079dd2  cmp     [r14+50h], rbx
0x180079dd6  jz      loc_180079E98
0x180079ddc  mov     rcx, rbp
0x180079ddf  call    CDKreadBit
0x180079de4  mov     rcx, rbp
0x180079de7  mov     [rdi+rsi*4+11h], al
0x180079deb  call    CDKreadBit
0x180079df0  mov     rcx, rbp
0x180079df3  mov     [rdi+rsi*4+12h], al
0x180079df7  call    CDKreadBit
0x180079dfc  mov     cl, [rdi+rsi*4+14h]
0x180079e00  mov     rdx, rbp
0x180079e03  mov     [rdi+rsi*4+13h], al
0x180079e07  lea     rax, [rdi+4D4h]
0x180079e0e  mov     r9d, [rdi+4C4h]
0x180079e15  mov     r8d, [rdi+4B4h]
0x180079e1c  mov     [rsp+0C8h+var_60], bl
0x180079e20  mov     [rsp+0C8h+var_68], 1
0x180079e28  mov     [rsp+0C8h+var_70], rax
0x180079e2d  mov     al, [rdi+4D2h]
0x180079e33  mov     byte ptr [rsp+0C8h+var_78], al
0x180079e37  mov     rax, [r14+50h]
0x180079e3b  mov     [rsp+0C8h+var_80], cl
0x180079e3f  mov     cl, [rdi+rsi*4+11h]
0x180079e43  mov     byte ptr [rsp+0C8h+var_88], cl
0x180079e47  mov     ecx, [rdi+4B0h]
0x180079e4d  mov     [rsp+0C8h+var_90], r13d
0x180079e52  mov     [rsp+0C8h+var_98], ebx
0x180079e56  mov     [rsp+0C8h+var_A0], ecx
0x180079e5a  mov     ecx, [rdi+4B8h]
0x180079e60  mov     [rsp+0C8h+var_A8], ecx
0x180079e64  mov     rcx, [r14+58h]
0x180079e68  call    cs:__guard_dispatch_icall_fptr
0x180079e6e  test    eax, eax
0x180079e70  jnz     loc_180079F27
0x180079e76  inc     byte ptr [rdi+3]
0x180079e79  mov     esi, [rsp+0C8h+var_48]
0x180079e80  inc     r13d
  ... truncated ...
```
