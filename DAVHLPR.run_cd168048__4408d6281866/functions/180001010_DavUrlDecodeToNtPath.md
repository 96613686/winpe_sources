# DavUrlDecodeToNtPath

- ea: `0x180001010`
- end: `0x180001455`
- name: `DavUrlDecodeToNtPath`
- size: `1093`
- prototype: `unsigned int __fastcall(unsigned __int16 *, __int64, _WORD *, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180001010`
- `0x180003be0`
- `0x1800040b0`

## pseudocode

```c
unsigned int __fastcall DavUrlDecodeToNtPath(unsigned __int16 *a1, __int64 a2, _WORD *a3, __int64 *a4)
{
  __int64 v4; // rax
  unsigned __int64 v5; // r15
  unsigned int v6; // r13d
  char v7; // r14
  char v8; // r11
  __int64 v9; // rbx
  _WORD *v10; // rdi
  unsigned int result; // eax
  unsigned __int16 *v13; // r10
  int v14; // eax
  unsigned int v15; // ecx
  int v16; // ecx
  unsigned __int16 v17; // ax
  char v18; // dl
  unsigned __int16 v19; // r9
  char v20; // al
  unsigned __int8 v21; // dl
  bool v22; // zf
  unsigned __int64 v23; // rax
  __int64 v24; // r9
  unsigned __int16 v25; // ax
  unsigned __int16 v26; // r9
  char v27; // r13
  unsigned __int16 v28; // ax
  char32_t v29; // r9d
  char32_t v30; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v31; // [rsp+38h] [rbp-10h] BYREF
  unsigned __int8 v32; // [rsp+3Ch] [rbp-Ch]
  char v33; // [rsp+3Dh] [rbp-Bh]
  unsigned __int16 *v34; // [rsp+90h] [rbp+48h] BYREF
  __int16 v35; // [rsp+98h] [rbp+50h] BYREF
  int v36; // [rsp+A0h] [rbp+58h] BYREF
  char v37; // [rsp+A8h] [rbp+60h] BYREF
  unsigned __int16 v38; // [rsp+AAh] [rbp+62h]

  v34 = a1;
  v4 = *a4;
  v5 = (unsigned __int64)&a1[a2];
  v6 = v31;
  v7 = 0;
  v8 = 0;
  v33 = 0;
  v9 = 0;
  v37 = 0;
  v10 = &a3[v4];
  v36 = 2048;
  result = 0;
  v30 = 9216;
  v35 = 0;
  v13 = a1;
  while ( (unsigned __int64)v13 < v5 )
  {
    if ( a3 >= v10 )
    {
      while ( (unsigned __int64)v13 < v5 )
      {
        v30 = 0;
        result = DavpUrlDecodeToNtPathDecodeHelper(
                   (unsigned int)&v34,
                   v5,
                   (unsigned int)&v31,
                   (unsigned int)&v37,
                   (__int64)&v30);
        if ( result != 997 )
        {
          if ( result )
            return result;
          result = Utf16Encoder::ProcessCodePoint((Utf16Encoder *)&v35, v30, (unsigned __int16 *)&v36);
          ++v9;
          if ( result )
          {
            if ( result != 234 )
              return result;
            result = Utf16Encoder::ProcessCodePoint((Utf16Encoder *)&v35, v29, (unsigned __int16 *)&v36);
            if ( result )
              return result;
            ++v9;
          }
        }
        v13 = v34;
      }
      v7 = v33;
      result = 122;
      v8 = v37;
      break;
    }
    v14 = *v13;
    v15 = 0;
    if ( v14 != 37 )
    {
      if ( v7 )
        return 582;
      if ( v8 )
      {
        v28 = v30 + v14;
        v8 = 0;
        v37 = 0;
        if ( v28 <= 0x3FFu )
        {
          v15 = v28 + (v38 << 10) + 0x10000;
          result = 0;
          goto LABEL_9;
        }
      }
      else
      {
        if ( (unsigned __int16)(v14 + 10240) >= (unsigned __int16)v36 )
        {
          v15 = *v13;
          result = 0;
LABEL_9:
          ++v13;
          goto LABEL_10;
        }
        if ( (unsigned __int16)(v14 + 10240) <= 0x3FFu )
        {
          v8 = 1;
          v38 = v14 + 10240;
          v37 = 1;
          result = 997;
          goto LABEL_9;
        }
      }
      result = 582;
      goto LABEL_9;
    }
    if ( v8 || (__int64)((v5 - (_QWORD)v13) & 0xFFFFFFFFFFFFFFFEuLL) < 6 )
      return 582;
    v17 = v13[1];
    v18 = v17 - 48;
    if ( (unsigned __int16)(v17 - 48) >= 0xAu )
    {
      v25 = (v17 | 0x20) - 97;
      if ( v25 >= 6u )
        return 582;
      v18 = v25 + 10;
    }
    v19 = v13[2];
    v20 = v19 - 48;
    if ( (unsigned __int16)(v19 - 48) >= 0xAu )
    {
      v26 = (v19 | 0x20) - 97;
      if ( v26 >= 6u )
        return 582;
      v20 = v26 + 10;
    }
    v21 = v20 | (16 * v18);
    if ( v7 )
    {
      if ( (v21 & 0xC0) == 0x80 )
      {
        v6 = (v6 << 6) | v21 & 0x3F;
        v22 = v7-- == 1;
        v31 = v6;
        v33 = v7;
        if ( !v22 )
        {
          result = 997;
LABEL_33:
          v13 += 3;
          goto LABEL_10;
        }
        if ( v6 >= dword_1800076F0[v32] && (v6 <= 0xD7FF || v6 - 57344 <= 0x101FFF) )
        {
          result = 0;
          v15 = v6;
          goto LABEL_33;
        }
      }
LABEL_37:
      result = 582;
      v13 += 3;
      goto LABEL_10;
    }
    if ( v21 < 0x80u )
    {
      v15 = (char)v21;
      result = 0;
      goto LABEL_33;
    }
    v23 = (unsigned __int64)v21 >> 3;
    v24 = *((unsigned __int8 *)qword_1800074E8 + v23);
    if ( !(_BYTE)v24 )
      goto LABEL_37;
    v7 = v24 - 1;
    v27 = ~byte_1800076E1[2 * v24];
    v32 = *((_BYTE *)qword_1800074E8 + v23);
    v6 = (unsigned __int8)(v21 & v27);
    v33 = v24 - 1;
    v31 = v6;
    v13 += 3;
    result = 997;
LABEL_10:
    v34 = v13;
    if ( !result && v15 == 47 )
      v15 = 92;
    if ( result != 997 )
    {
      if ( result )
        return result;
      if ( v15 <= 0x10FFFF && v15 - 55296 > 0x7FF )
      {
        if ( v15 > 0xFFFF )
        {
          *a3++ = ((v15 - 0x10000) >> 10) | 0xD800;
          if ( a3 < v10 )
          {
            result = 0;
            *a3 = v15 & 0x3FF | 0xDC00;
            v35 = 0;
            ++a3;
          }
          else
          {
            v35 = 0;
            result = 122;
          }
          v9 += 2;
        }
        else
        {
          *a3 = v15;
          result = 0;
          ++a3;
          ++v9;
        }
      }
      else
      {
        result = 582;
        ++a3;
        ++v9;
      }
    }
  }
  if ( v7 )
    v16 = 582;
  else
    v16 = v8 != 0 ? 0x246 : 0;
  *a4 = v9;
  if ( !v16 )
    return result;
  return v16;
}

```

## disassembly

```asm
0x180001010  mov     [rsp-40h+arg_0], rcx
0x180001015  push    rbp
0x180001016  push    rbx
0x180001017  push    rsi
0x180001018  push    rdi
0x180001019  push    r12
0x18000101b  push    r13
0x18000101d  push    r14
0x18000101f  push    r15
0x180001021  mov     rbp, rsp
0x180001024  sub     rsp, 48h
0x180001028  mov     rax, [r9]
0x18000102b  lea     r15, [rcx+rdx*2]
0x18000102f  mov     r13d, [rbp+var_10]
0x180001033  xor     r14b, r14b
0x180001036  xor     r11b, r11b
0x180001039  mov     [rbp+var_B], r14b
0x18000103d  xor     ebx, ebx
0x18000103f  mov     [rbp+arg_18], r11b
0x180001043  lea     rdi, [r8+rax*2]
0x180001047  mov     [rbp+arg_10], 800h
0x18000104e  xor     eax, eax
0x180001050  mov     [rbp+var_18], 2400h
0x180001057  xor     esi, esi
0x180001059  mov     r12, r9
0x18000105c  mov     [rbp+arg_8], si
0x180001060  mov     r10, rcx
0x180001063  mov     r9d, 2800h
0x180001069  nop     dword ptr [rax+00000000h]
0x180001070  mov     edx, 3FFh
0x180001075  cmp     r10, r15
0x180001078  jnb     loc_180001121
0x18000107e  cmp     r8, rdi
0x180001081  jnb     loc_1800013C9
0x180001087  movzx   eax, word ptr [r10]
0x18000108b  xor     ecx, ecx
0x18000108d  cmp     eax, 25h ; '%'
0x180001090  jz      short loc_180001106
0x180001092  test    r14b, r14b
0x180001095  jnz     short loc_18000110B
0x180001097  test    r11b, r11b
0x18000109a  jnz     loc_180001395
0x1800010a0  lea     edx, [r9+rax]
0x1800010a4  cmp     dx, word ptr [rbp+arg_10]
0x1800010a8  jb      loc_1800012C7
0x1800010ae  mov     ecx, eax
0x1800010b0  xor     eax, eax
0x1800010b2  add     r10, 2
0x1800010b6  mov     [rbp+arg_0], r10
0x1800010ba  test    eax, eax
0x1800010bc  jnz     short loc_1800010C8
0x1800010be  cmp     ecx, 2Fh ; '/'
0x1800010c1  jnz     short loc_1800010C8
0x1800010c3  mov     ecx, 5Ch ; '\'
0x1800010c8  cmp     eax, 3E5h
0x1800010cd  jz      short loc_180001070
0x1800010cf  test    eax, eax
0x1800010d1  jnz     short loc_180001110
0x1800010d3  test    si, si
0x1800010d6  jnz     loc_180001202
0x1800010dc  cmp     ecx, 10FFFFh
0x1800010e2  ja      short loc_1800010F5
0x1800010e4  lea     eax, [rcx-0D800h]
0x1800010ea  cmp     eax, 7FFh
0x1800010ef  ja      loc_1800012DF
0x1800010f5  mov     eax, 246h
0x1800010fa  add     r8, 2
0x1800010fe  inc     rbx
0x180001101  jmp     loc_180001070
0x180001106  test    r11b, r11b
0x180001109  jz      short loc_180001142
0x18000110b  mov     eax, 246h
0x180001110  add     rsp, 48h
0x180001114  pop     r15
0x180001116  pop     r14
0x180001118  pop     r13
0x18000111a  pop     r12
0x18000111c  pop     rdi
0x18000111d  pop     rsi
0x18000111e  pop     rbx
0x18000111f  pop     rbp
0x180001120  retn
0x180001121  test    r14b, r14b
0x180001124  jnz     loc_1800011BF
0x18000112a  neg     r11b
0x18000112d  sbb     ecx, ecx
0x18000112f  and     ecx, 246h
0x180001135  test    ecx, ecx
0x180001137  mov     [r12], rbx
0x18000113b  cmovz   ecx, eax
0x18000113e  mov     eax, ecx
0x180001140  jmp     short loc_180001110
0x180001142  mov     rax, r15
0x180001145  sub     rax, r10
0x180001148  and     rax, 0FFFFFFFFFFFFFFFEh
0x18000114c  cmp     rax, 6
0x180001150  jl      short loc_18000110B
0x180001152  movzx   eax, word ptr [r10+2]
0x180001157  lea     edx, [rax-30h]
0x18000115a  cmp     dx, 0Ah
0x18000115e  jnb     loc_180001214
0x180001164  movzx   r9d, word ptr [r10+4]
0x180001169  lea     eax, [r9-30h]
0x18000116d  cmp     ax, 0Ah
0x180001171  jnb     loc_18000122E
0x180001177  shl     dl, 4
0x18000117a  or      dl, al
0x18000117c  test    r14b, r14b
0x18000117f  jz      short loc_1800011C9
0x180001181  movzx   eax, dl
0x180001184  and     al, 0C0h
0x180001186  cmp     al, 80h
0x180001188  jnz     short loc_1800011EE
0x18000118a  mov     eax, r13d
0x18000118d  and     edx, 3Fh
0x180001190  shl     eax, 6
0x180001193  mov     r13d, edx
0x180001196  or      r13d, eax
0x180001199  add     r14b, 0FFh
0x18000119d  mov     [rbp+var_10], r13d
0x1800011a1  mov     [rbp+var_B], r14b
0x1800011a5  jz      loc_180001289
0x1800011ab  mov     eax, 3E5h
0x1800011b0  add     r10, 6
0x1800011b4  mov     r9d, 2800h
0x1800011ba  jmp     loc_1800010B6
0x1800011bf  mov     ecx, 246h
0x1800011c4  jmp     loc_180001135
0x1800011c9  cmp     dl, 80h
0x1800011cc  jb      loc_180001376
0x1800011d2  movzx   eax, dl
0x1800011d5  lea     r9, __ImageBase
0x1800011dc  shr     rax, 3
0x1800011e0  movzx   r9d, byte ptr [rax+r9+74E8h]
0x1800011e9  test    r9b, r9b
0x1800011ec  jnz     short loc_18000124C
0x1800011ee  mov     eax, 246h
0x1800011f3  add     r10, 6
0x1800011f7  mov     r9d, 2800h
0x1800011fd  jmp     loc_1800010B6
0x180001202  xor     eax, eax
0x180001204  mov     [r8], si
0x180001208  movzx   esi, ax
0x18000120b  mov     [rbp+arg_8], ax
0x18000120f  jmp     loc_1800010FA
0x180001214  or      ax, 20h
0x180001218  sub     ax, 61h ; 'a'
0x18000121c  cmp     ax, 6
0x180001220  jnb     loc_18000110B
0x180001226  lea     edx, [rax+0Ah]
0x180001229  jmp     loc_180001164
0x18000122e  or      r9w, 20h
0x180001233  sub     r9w, 61h ; 'a'
0x180001238  cmp     r9w, 6
0x18000123d  jnb     loc_18000110B
0x180001243  lea     eax, [r9+0Ah]
0x180001247  jmp     loc_180001177
0x18000124c  lea     r14, __ImageBase
0x180001253  movzx   eax, dl
0x180001256  movzx   r13d, ds:rva byte_1800076E1[r14+r9*2]
0x18000125f  lea     r14d, [r9-1]
0x180001263  not     r13d
0x180001266  mov     [rbp+var_C], r9b
0x18000126a  and     r13d, eax
0x18000126d  mov     [rbp+var_B], r14b
0x180001271  mov     [rbp+var_10], r13d
0x180001275  add     r10, 6
0x180001279  mov     eax, 3E5h
0x18000127e  mov     r9d, 2800h
0x180001284  jmp     loc_1800010B6
0x180001289  movzx   eax, [rbp+var_C]
0x18000128d  lea     rdx, __ImageBase
0x180001294  cmp     r13d, ds:rva dword_1800076F0[rdx+rax*4]
0x18000129c  jb      loc_1800011EE
0x1800012a2  cmp     r13d, 0D7FFh
0x1800012a9  jbe     short loc_1800012BD
0x1800012ab  lea     eax, [r13-0E000h]
0x1800012b2  cmp     eax, 101FFFh
0x1800012b7  ja      loc_1800011EE
0x1800012bd  xor     eax, eax
0x1800012bf  mov     ecx, r13d
0x1800012c2  jmp     loc_1800011B0
0x1800012c7  mov     eax, 3FFh
0x1800012cc  cmp     dx, ax
0x1800012cf  jbe     loc_180001380
0x1800012d5  mov     eax, 246h
0x1800012da  jmp     loc_1800010B2
0x1800012df  cmp     ecx, 0FFFFh
0x1800012e5  ja      short loc_1800012F9
0x1800012e7  mov     [r8], cx
0x1800012eb  xor     eax, eax
0x1800012ed  add     r8, 2
0x1800012f1  inc     rbx
0x1800012f4  jmp     loc_180001070
0x1800012f9  lea     edx, [rcx-10000h]
0x1800012ff  mov     esi, 0D800h
0x180001304  mov     eax, edx
0x180001306  shr     eax, 0Ah
0x180001309  or      ax, si
0x18000130c  mov     [r8], ax
0x180001310  mov     eax, 3FFh
0x180001315  and     dx, ax
0x180001318  add     r8, 2
0x18000131c  or      dx, 0DC00h
0x180001321  cmp     r8, rdi
0x180001324  jb      short loc_180001335
0x180001326  test    dx, dx
0x180001329  jnz     short loc_180001366
0x18000132b  mov     eax, 0EAh
0x180001330  jmp     loc_180001110
0x180001335  test    dx, dx
0x180001338  jnz     short loc_18000134C
0x18000133a  lea     eax, [rcx-10000h]
0x180001340  shr     eax, 0Ah
0x180001343  or      ax, si
0x180001346  mov     [r8], ax
0x18000134a  jmp     short loc_18000132B
0x18000134c  xor     eax, eax
0x18000134e  mov     [r8], dx
0x180001352  movzx   esi, ax
0x180001355  mov     [rbp+arg_8], ax
0x180001359  add     r8, 2
0x18000135d  add     rbx, 2
0x180001361  jmp     loc_180001070
0x180001366  xor     eax, eax
0x180001368  movzx   esi, ax
0x18000136b  mov     [rbp+arg_8], ax
0x18000136f  mov     eax, 7Ah ; 'z'
0x180001374  jmp     short loc_18000135D
0x180001376  movsx   ecx, dl
0x180001379  xor     eax, eax
0x18000137b  jmp     loc_1800011B0
0x180001380  mov     r11b, 1
0x180001383  mov     [rbp+arg_1A], dx
0x180001387  mov     [rbp+arg_18], r11b
0x18000138b  mov     eax, 3E5h
0x180001390  jmp     loc_1800010B2
0x180001395  add     ax, word ptr [rbp+var_18]
0x180001399  xor     r11b, r11b
0x18000139c  mov     [rbp+arg_18], r11b
0x1800013a0  cmp     ax, dx
0x1800013a3  ja      loc_1800012D5
0x1800013a9  movzx   ecx, [rbp+arg_1A]
0x1800013ad  shl     ecx, 0Ah
0x1800013b0  add     ecx, 10000h
0x1800013b6  movzx   eax, ax
0x1800013b9  add     ecx, eax
0x1800013bb  xor     eax, eax
0x1800013bd  jmp     loc_1800010B2
0x1800013c2  inc     rbx
0x1800013c5  mov     r10, [rbp+arg_0]
0x1800013c9  cmp     r10, r15
0x1800013cc  jnb     short loc_180001441
0x1800013ce  lea     rax, [rbp+var_18]
0x1800013d2  mov     [rbp+var_18], 0
0x1800013d9  lea     r9, [rbp+arg_18]
0x1800013dd  mov     [rsp+48h+var_28], rax
0x1800013e2  lea     r8, [rbp+var_10]
0x1800013e6  mov     rdx, r15
0x1800013e9  lea     rcx, [rbp+arg_0]
0x1800013ed  call    DavpUrlDecodeToNtPathDecodeHelper
0x1800013f2  cmp     eax, 3E5h
0x1800013f7  jz      short loc_1800013C5
0x1800013f9  test    eax, eax
0x1800013fb  jnz     loc_180001110
0x180001401  mov     r9d, [rbp+var_18]
0x180001405  lea     r8, [rbp+arg_10]; unsigned __int16 *
0x180001409  mov     edx, r9d; char32_t
0x18000140c  lea     rcx, [rbp+arg_8]; this
0x180001410  call    ?ProcessCodePoint@Utf16Encoder@@QEAAK_UAEAG@Z; Utf16Encoder::ProcessCodePoint(char32_t,ushort &)
0x180001415  inc     rbx
0x180001418  test    eax, eax
0x18000141a  jz      short loc_1800013C5
0x18000141c  cmp     eax, 0EAh
0x180001421  jnz     loc_180001110
0x180001427  lea     r8, [rbp+arg_10]; unsigned __int16 *
0x18000142b  mov     edx, r9d; char32_t
0x18000142e  lea     rcx, [rbp+arg_8]; this
0x180001432  call    ?ProcessCodePoint@Utf16Encoder@@QEAAK_UAEAG@Z; Utf16Encoder::ProcessCodePoint(char32_t,ushort &)
0x180001437  test    eax, eax
0x180001439  jnz     loc_180001110
0x18000143f  jmp     short loc_1800013C2
0x180001441  movzx   r14d, [rbp+var_B]
0x180001446  mov     eax, 7Ah ; 'z'
0x18000144b  movzx   r11d, [rbp+arg_18]
0x180001450  jmp     loc_180001121
```
