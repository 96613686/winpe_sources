# CFontCache::GetCcs(CCharFormat const * const,long,HDC__ *,int)

- ea: `0x18000b440`
- end: `0x18000b911`
- name: `?GetCcs@CFontCache@@QEAAPEAVCCcs@@QEBVCCharFormat@@JPEAUHDC__@@H@Z`
- size: `1233`
- prototype: `struct CCcs *__usercall@<rax>(CFontCache *__hidden this@<rcx>, const struct CCharFormat *const@<rdx>, int@<r8d>, HDC@<r9>, int)`
- caller_count: `13`
- callee_count: `6`
- tags: ``

## callers

- `0x180009018`
- `0x1800096f8`
- `0x1800098b0`
- `0x18000a0b0`
- `0x18000b0b0`
- `0x18000b3a0`
- `0x18000c070`
- `0x18000d670`
- `0x1800124f0`
- `0x18001afa8`
- `0x180056bf0`
- `0x180059ab0`
- `0x18005ba50`

## callees

- `0x18000b440`
- `0x18001b57c`
- `0x180031ff0`
- `0x1800420a4`
- `0x180047d08`
- `0x18005f6ec`

## pseudocode

```c
struct CCcs *__fastcall CFontCache::GetCcs(CFontCache *this, __m128i *a2, int a3, HDC a4, int a5)
{
  __m128i v6; // xmm2
  __int64 v9; // xmm0_8
  __m128i v11; // xmm6
  char v12; // r15
  __int16 FontNameIndex; // bp
  unsigned __int32 v14; // ebx
  int v15; // edx
  int v16; // r8d
  unsigned int v17; // r12d
  __int64 v18; // r10
  struct CCcs *result; // rax
  __int16 v20; // r11
  int v21; // edx
  CFontCache *v22; // r9
  __int64 v23; // r14
  unsigned int v24; // ecx
  CFontCache *v25; // rax
  CFontCache *v26; // rbx
  __int64 v27; // r14
  __int64 v28; // rcx
  __int64 FontSignatureFromFace; // rax
  __int64 v30; // rcx
  _BYTE *v31; // rax
  __int64 v32; // rbx
  __int8 v33; // eax^2
  __m128i v34; // [rsp+20h] [rbp-68h] BYREF
  __m128i v35; // [rsp+30h] [rbp-58h]
  __int64 v36; // [rsp+40h] [rbp-48h]

  v6 = *a2;
  v9 = a2[2].m128i_i64[0];
  v11 = a2[1];
  v12 = _mm_cvtsi128_si32(_mm_srli_si128(*a2, 4));
  v34 = *a2;
  v35 = v11;
  v36 = v9;
  if ( a5 )
  {
    if ( CW32System::_dwPlatformId != 1 )
    {
      v28 = a2->m128i_i16[3];
      if ( (int)v28 < 0 || (int)v28 > dword_1800A41D4 )
        goto LABEL_54;
      v31 = lpMem;
      v32 = 2 * v28;
      if ( (*((_BYTE *)lpMem + 16 * v28 + 14) & 1) == 0 )
      {
        GetFontSignatureFromFace(v28, 0);
        v31 = lpMem;
      }
      if ( (v31[8 * v32 + 14] & 4) == 0 )
      {
LABEL_54:
        FontNameIndex = v34.m128i_i16[3];
        v14 = v34.m128i_i32[0] | 0x100000;
        v34.m128i_i32[0] |= 0x100000u;
        goto LABEL_4;
      }
      goto LABEL_2;
    }
    if ( CW32System::_ACP == 1258 || CW32System::_ACP == 874 )
    {
      FontSignatureFromFace = GetFontSignatureFromFace(v6.m128i_i16[3], 0);
      if ( v12 == -34 )
      {
        if ( (FontSignatureFromFace & 0x10000) == 0 )
          goto LABEL_67;
      }
      else if ( v12 == -93 && (FontSignatureFromFace & 0x100) == 0 )
      {
        goto LABEL_67;
      }
      if ( (*(_BYTE *)CFontCache::GetInfoFlags(v30, &a5, (unsigned int)a2->m128i_i16[3]) & 4) == 0 )
      {
LABEL_67:
        FontNameIndex = GetFontNameIndex(L"Tahoma");
        v34.m128i_i16[3] = FontNameIndex;
        goto LABEL_3;
      }
    }
  }
LABEL_2:
  FontNameIndex = v34.m128i_i16[3];
LABEL_3:
  v14 = v34.m128i_i32[0];
LABEL_4:
  if ( !a4 )
  {
    a4 = CW32System::_hdcScreen;
    if ( !CW32System::_hdcScreen )
    {
      result = (struct CCcs *)CW32System::CreateIC(L"DISPLAY", 0, 0, 0);
      CW32System::_hdcScreen = (HDC)result;
      a4 = (HDC)result;
      if ( !result )
        return result;
    }
  }
  if ( (v14 & 0x30000) != 0 )
    v15 = 2 * v34.m128i_i16[4] / 3;
  else
    LOWORD(v15) = v34.m128i_i16[4];
  v16 = (a3 * (__int16)v15 + 720) / 1440;
  v34.m128i_i16[4] = v16;
  if ( !(_WORD)v16 )
  {
    LOWORD(v16) = 1;
    v34.m128i_i16[4] = 1;
  }
  v17 = ((v14 & 3) << 14) | FontNameIndex | ((__int16)v16 << 16);
  v18 = v17 % 0x1F;
  if ( v17 == *((_DWORD *)this + 4 * v18 + 770) )
  {
    result = (struct CCcs *)*((_QWORD *)this + 2 * v18 + 386);
    if ( result
      && (*((_BYTE *)result + 123) & 1) != 0
      && *((_WORD *)result + 4) == FontNameIndex
      && *((_WORD *)result + 44) == (_WORD)v16
      && (*((_BYTE *)result + 118) == v12 || *((_BYTE *)result + 119) == v12) )
    {
      v20 = _mm_cvtsi128_si32(v11);
      if ( *((_WORD *)result + 57) == v20
        && (((*((_BYTE *)result + 123) >> 4) ^ (unsigned __int8)(v14 >> 20)) & 1) == 0
        && (((*((_BYTE *)result + 123) >> 2) ^ (unsigned __int8)(v14 >> 1)) & 1) == 0
        && *((HDC *)result + 8) == a4
        && *((_BYTE *)result + 122) == v34.m128i_i8[5]
        && ((v14 & 0x40000) == 0 || *((_BYTE *)result + 121) == 2) )
      {
        goto LABEL_21;
      }
      goto LABEL_29;
    }
  }
  else
  {
    *((_DWORD *)this + 4 * (v17 % 0x1F) + 770) = v17;
  }
  v20 = v35.m128i_i16[0];
LABEL_29:
  v22 = (CFontCache *)((char *)this + 2944);
  for ( result = this; ; result = (struct CCcs *)((char *)result + 128) )
  {
    if ( result > v22 )
    {
      v23 = v18 + 193;
      v24 = -1;
      v25 = 0;
      v26 = this;
      if ( this <= v22 )
      {
        while ( (*((_BYTE *)v26 + 123) & 1) != 0 )
        {
          if ( !*((_WORD *)v26 + 5) && *((_DWORD *)v26 + 1) < v24 )
          {
            v24 = *((_DWORD *)v26 + 1);
            v25 = v26;
          }
          v26 = (CFontCache *)((char *)v26 + 128);
          if ( v26 > v22 )
          {
            if ( !v25 )
              goto LABEL_34;
            v26 = v25;
            break;
          }
        }
        *((_QWORD *)v26 + 8) = a4;
        v27 = 2 * v23;
        if ( (unsigned int)CCcs::Init(v26, (const struct CCharFormat *const)&v34) )
        {
          ++*((_WORD *)v26 + 5);
          *((_QWORD *)this + v27) = v26;
          if ( v26 )
          {
            v33 = v34.m128i_i8[2];
            *((_BYTE *)v26 + 123) &= ~0x10u;
            *(_DWORD *)v26 = v17;
            *((_BYTE *)v26 + 123) |= v33 & 0x10;
          }
          return v26;
        }
      }
      else
      {
LABEL_34:
        v27 = 2 * v23;
      }
      *((_QWORD *)this + v27) = 0;
      return 0;
    }
    if ( *(_DWORD *)result == v17
      && (*((_BYTE *)result + 123) & 1) != 0
      && *((_WORD *)result + 4) == FontNameIndex
      && *((_WORD *)result + 44) == (_WORD)v16
      && (*((_BYTE *)result + 118) == v12 || *((_BYTE *)result + 119) == v12)
      && *((_WORD *)result + 57) == v20
      && (((*((_BYTE *)result + 123) >> 4) ^ (unsigned __int8)(v14 >> 20)) & 1) == 0
      && (((*((_BYTE *)result + 123) >> 2) ^ (unsigned __int8)(v14 >> 1)) & 1) == 0
      && *((HDC *)result + 8) == a4
      && *((_BYTE *)result + 122) == v34.m128i_i8[5]
      && ((v14 & 0x40000) == 0 || *((_BYTE *)result + 121) == 2) )
    {
      break;
    }
  }
  *((_QWORD *)this + 2 * v18 + 386) = result;
LABEL_21:
  v21 = *((_DWORD *)this + 768);
  if ( *((_DWORD *)result + 1) != v21 - 1 )
  {
    *((_DWORD *)this + 768) = v21 + 1;
    *((_DWORD *)result + 1) = v21;
  }
  ++*((_WORD *)result + 5);
  return result;
}

```

## disassembly

```asm
0x18000b440  mov     [rsp+arg_10], rbx
0x18000b445  push    rbp
0x18000b446  push    rsi
0x18000b447  push    rdi
0x18000b448  push    r14
0x18000b44a  push    r15
0x18000b44c  sub     rsp, 60h
0x18000b450  cmp     [rsp+88h+arg_20], 0
0x18000b458  mov     rdi, r9
0x18000b45b  movups  xmm2, xmmword ptr [rdx]
0x18000b45e  mov     r14d, r8d
0x18000b461  mov     rbx, rdx
0x18000b464  movsd   xmm0, qword ptr [rdx+20h]
0x18000b469  mov     rsi, rcx
0x18000b46c  movaps  [rsp+88h+var_38], xmm6
0x18000b471  movdqa  xmm1, xmm2
0x18000b475  movups  xmm6, xmmword ptr [rdx+10h]
0x18000b479  psrldq  xmm1, 4
0x18000b47e  movd    r15d, xmm1
0x18000b483  movups  [rsp+88h+var_68], xmm2
0x18000b488  movups  [rsp+88h+var_58], xmm6
0x18000b48d  movsd   [rsp+88h+var_48], xmm0
0x18000b493  jnz     loc_18000B76A
0x18000b499  movzx   ebp, word ptr [rsp+88h+var_68+6]
0x18000b49e  mov     ebx, dword ptr [rsp+88h+var_68]
0x18000b4a2  test    rdi, rdi
0x18000b4a5  jz      loc_18000B633
0x18000b4ab  mov     [rsp+88h+arg_0], r12
0x18000b4b3  test    ebx, 30000h
0x18000b4b9  jnz     loc_18000B862
0x18000b4bf  movzx   edx, word ptr [rsp+88h+var_68+8]
0x18000b4c4  movsx   ecx, dx
0x18000b4c7  mov     eax, 0B60B60B7h
0x18000b4cc  imul    ecx, r14d
0x18000b4d0  add     ecx, 2D0h
0x18000b4d6  imul    ecx
0x18000b4d8  lea     r8d, [rcx+rdx]
0x18000b4dc  sar     r8d, 0Ah
0x18000b4e0  mov     eax, r8d
0x18000b4e3  shr     eax, 1Fh
0x18000b4e6  add     r8d, eax
0x18000b4e9  mov     word ptr [rsp+88h+var_68+8], r8w
0x18000b4ef  test    r8w, r8w
0x18000b4f3  jz      loc_18000B87C
0x18000b4f9  movsx   eax, bp
0x18000b4fc  movsx   r12d, r8w
0x18000b500  shl     r12d, 10h
0x18000b504  or      r12d, eax
0x18000b507  mov     [rsp+88h+arg_8], r13
0x18000b50f  mov     eax, ebx
0x18000b511  and     eax, 3
0x18000b514  shl     eax, 0Eh
0x18000b517  or      r12d, eax
0x18000b51a  mov     eax, 8421085h
0x18000b51f  mul     r12d
0x18000b522  mov     ecx, r12d
0x18000b525  mov     eax, r12d
0x18000b528  sub     eax, edx
0x18000b52a  shr     eax, 1
0x18000b52c  add     eax, edx
0x18000b52e  shr     eax, 4
0x18000b531  imul    eax, 1Fh
0x18000b534  sub     ecx, eax
0x18000b536  movsxd  r10, ecx
0x18000b539  mov     rcx, r10
0x18000b53c  add     rcx, rcx
0x18000b53f  cmp     r12d, [rsi+rcx*8+0C08h]
0x18000b547  jnz     loc_18000B66C
0x18000b54d  lea     rax, [r10+0C1h]
0x18000b554  add     rax, rax
0x18000b557  mov     rax, [rsi+rax*8]
0x18000b55b  test    rax, rax
0x18000b55e  jz      loc_18000B674
0x18000b564  movzx   ecx, byte ptr [rax+7Bh]
0x18000b568  test    cl, 1
0x18000b56b  jz      loc_18000B674
0x18000b571  cmp     [rax+8], bp
0x18000b575  jnz     loc_18000B674
0x18000b57b  cmp     [rax+58h], r8w
0x18000b580  jnz     loc_18000B674
0x18000b586  cmp     [rax+76h], r15b
0x18000b58a  jnz     loc_18000B6D8
0x18000b590  movd    r11d, xmm6
0x18000b595  cmp     [rax+72h], r11w
0x18000b59a  jnz     loc_18000B67A
0x18000b5a0  mov     edx, ebx
0x18000b5a2  mov     r9d, ecx
0x18000b5a5  shr     edx, 14h
0x18000b5a8  shr     ecx, 4
0x18000b5ab  xor     edx, ecx
0x18000b5ad  test    dl, 1
0x18000b5b0  jnz     loc_18000B67A
0x18000b5b6  shr     r9d, 2
0x18000b5ba  mov     ecx, ebx
0x18000b5bc  shr     ecx, 1
0x18000b5be  xor     ecx, r9d
0x18000b5c1  test    cl, 1
0x18000b5c4  jnz     loc_18000B67A
0x18000b5ca  cmp     [rax+40h], rdi
0x18000b5ce  jnz     loc_18000B67A
0x18000b5d4  movzx   ecx, byte ptr [rsp+88h+var_68+5]
0x18000b5d9  cmp     [rax+7Ah], cl
0x18000b5dc  jnz     loc_18000B67A
0x18000b5e2  bt      ebx, 12h
0x18000b5e6  jb      loc_18000B88D
0x18000b5ec  mov     edx, [rsi+0C00h]
0x18000b5f2  lea     ecx, [rdx-1]
0x18000b5f5  cmp     [rax+4], ecx
0x18000b5f8  jz      short loc_18000B606
0x18000b5fa  lea     ecx, [rdx+1]
0x18000b5fd  mov     [rsi+0C00h], ecx
0x18000b603  mov     [rax+4], edx
0x18000b606  inc     word ptr [rax+0Ah]
0x18000b60a  mov     r13, [rsp+88h+arg_8]
0x18000b612  mov     r12, [rsp+88h+arg_0]
0x18000b61a  mov     rbx, [rsp+88h+arg_10]
0x18000b622  movaps  xmm6, [rsp+88h+var_38]
0x18000b627  add     rsp, 60h
0x18000b62b  pop     r15
0x18000b62d  pop     r14
0x18000b62f  pop     rdi
0x18000b630  pop     rsi
0x18000b631  pop     rbp
0x18000b632  retn
0x18000b633  mov     rdi, cs:?_hdcScreen@CW32System@@0PEAUHDC__@@EA; HDC__ * CW32System::_hdcScreen
0x18000b63a  test    rdi, rdi
0x18000b63d  jnz     loc_18000B4AB
0x18000b643  xor     r9d, r9d; struct _devicemodeW *
0x18000b646  lea     rcx, aDisplay; "DISPLAY"
0x18000b64d  xor     r8d, r8d; unsigned __int16 *
0x18000b650  xor     edx, edx; unsigned __int16 *
0x18000b652  call    ?CreateIC@CW32System@@SAPEAUHDC__@@PEBG00PEBU_devicemodeW@@@Z; CW32System::CreateIC(ushort const *,ushort const *,ushort const *,_devicemodeW const *)
0x18000b657  mov     cs:?_hdcScreen@CW32System@@0PEAUHDC__@@EA, rax; HDC__ * CW32System::_hdcScreen
0x18000b65e  mov     rdi, rax
0x18000b661  test    rax, rax
0x18000b664  jnz     loc_18000B4AB
0x18000b66a  jmp     short loc_18000B61A
0x18000b66c  mov     [rsi+rcx*8+0C08h], r12d
0x18000b674  movzx   r11d, word ptr [rsp+88h+var_58]
0x18000b67a  mov     r13d, 0C1h
0x18000b680  lea     r9, [rsi+0B80h]
0x18000b687  mov     rax, rsi
0x18000b68a  cmp     rax, r9
0x18000b68d  ja      short loc_18000B69A
0x18000b68f  cmp     [rax], r12d
0x18000b692  jz      short loc_18000B6E4
0x18000b694  sub     rax, 0FFFFFFFFFFFFFF80h
0x18000b698  jmp     short loc_18000B68A
0x18000b69a  xor     ebp, ebp
0x18000b69c  lea     r14, [r10+r13]
0x18000b6a0  mov     ecx, 0FFFFFFFFh
0x18000b6a5  mov     eax, ebp
0x18000b6a7  mov     rbx, rsi
0x18000b6aa  cmp     rsi, r9
0x18000b6ad  jbe     loc_18000B8AB
0x18000b6b3  add     r14, r14
0x18000b6b6  mov     [rsi+r14*8], rbp
0x18000b6ba  mov     rbx, rbp
0x18000b6bd  jmp     short loc_18000B6D0
0x18000b6bf  inc     word ptr [rbx+0Ah]
0x18000b6c3  mov     [rsi+r14*8], rbx
0x18000b6c7  test    rbx, rbx
0x18000b6ca  jnz     loc_18000B8F9
0x18000b6d0  mov     rax, rbx
0x18000b6d3  jmp     loc_18000B60A
0x18000b6d8  cmp     [rax+77h], r15b
0x18000b6dc  jz      loc_18000B590
0x18000b6e2  jmp     short loc_18000B674
0x18000b6e4  movzx   ecx, byte ptr [rax+7Bh]
0x18000b6e8  test    cl, 1
0x18000b6eb  jz      short loc_18000B694
0x18000b6ed  cmp     [rax+8], bp
0x18000b6f1  jnz     short loc_18000B694
0x18000b6f3  cmp     [rax+58h], r8w
0x18000b6f8  jnz     short loc_18000B694
0x18000b6fa  cmp     [rax+76h], r15b
0x18000b6fe  jnz     loc_18000B796
0x18000b704  cmp     [rax+72h], r11w
0x18000b709  jnz     short loc_18000B694
0x18000b70b  mov     edx, ebx
0x18000b70d  mov     r14d, ecx
0x18000b710  shr     edx, 14h
0x18000b713  shr     ecx, 4
0x18000b716  xor     edx, ecx
0x18000b718  test    dl, 1
0x18000b71b  jnz     loc_18000B694
0x18000b721  shr     r14d, 2
0x18000b725  mov     ecx, ebx
0x18000b727  shr     ecx, 1
0x18000b729  xor     ecx, r14d
0x18000b72c  test    cl, 1
0x18000b72f  jnz     loc_18000B694
0x18000b735  cmp     [rax+40h], rdi
0x18000b739  jnz     loc_18000B694
0x18000b73f  movzx   ecx, byte ptr [rsp+88h+var_68+5]
0x18000b744  cmp     [rax+7Ah], cl
0x18000b747  jnz     loc_18000B694
0x18000b74d  bt      ebx, 12h
0x18000b751  jb      loc_18000B89C
0x18000b757  lea     rcx, [r10+0C1h]
0x18000b75e  add     rcx, rcx
0x18000b761  mov     [rsi+rcx*8], rax
0x18000b765  jmp     loc_18000B5EC
0x18000b76a  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x18000b771  jz      short loc_18000B7B2
0x18000b773  movsx   rcx, word ptr [rdx+6]; int
0x18000b778  test    ecx, ecx
0x18000b77a  jns     loc_18000B82B
0x18000b780  mov     ebx, dword ptr [rsp+88h+var_68]
0x18000b784  movzx   ebp, word ptr [rsp+88h+var_68+6]
0x18000b789  bts     ebx, 14h
0x18000b78d  mov     dword ptr [rsp+88h+var_68], ebx
0x18000b791  jmp     loc_18000B4A2
0x18000b796  cmp     [rax+77h], r15b
0x18000b79a  jz      loc_18000B704
0x18000b7a0  jmp     loc_18000B694
0x18000b7a5  test    byte ptr [rax+rbx*8+0Eh], 4
0x18000b7aa  jnz     loc_18000B499
0x18000b7b0  jmp     short loc_18000B780
0x18000b7b2  mov     eax, cs:?_ACP@CW32System@@0IA; uint CW32System::_ACP
0x18000b7b8  cmp     eax, 4EAh
0x18000b7bd  jz      short loc_18000B7CA
0x18000b7bf  cmp     eax, 36Ah
0x18000b7c4  jnz     loc_18000B499
0x18000b7ca  movq    rax, xmm2
0x18000b7cf  xor     edx, edx; unsigned int *
0x18000b7d1  shr     rax, 30h
0x18000b7d5  movsx   ecx, ax; int
0x18000b7d8  call    ?GetFontSignatureFromFace@@YAKHPEAK@Z; GetFontSignatureFromFace(int,ulong *)
0x18000b7dd  cmp     r15b, 0DEh
0x18000b7e1  jnz     short loc_18000B7EB
0x18000b7e3  bt      eax, 10h
0x18000b7e7  jb      short loc_18000B7F7
0x18000b7e9  jmp     short loc_18000B812
0x18000b7eb  cmp     r15b, 0A3h
0x18000b7ef  jnz     short loc_18000B7F7
0x18000b7f1  bt      eax, 8
0x18000b7f5  jnb     short loc_18000B812
0x18000b7f7  movsx   r8d, word ptr [rbx+6]
0x18000b7fc  lea     rdx, [rsp+88h+arg_20]
0x18000b804  call    ?GetInfoFlags@CFontCache@@QEAA?ATFONTINFO_FLAGS@@H@Z; CFontCache::GetInfoFlags(int)
0x18000b809  test    byte ptr [rax], 4
0x18000b80c  jnz     loc_18000B499
0x18000b812  lea     rcx, Src; "Tahoma"
0x18000b819  call    ?GetFontNameIndex@@YAFPEBG@Z; GetFontNameIndex(ushort const *)
0x18000b81e  movzx   ebp, ax
0x18000b821  mov     word ptr [rsp+88h+var_68+6], ax
0x18000b826  jmp     loc_18000B49E
0x18000b82b  cmp     ecx, cs:dword_1800A41D4
0x18000b831  jg      loc_18000B780
0x18000b837  mov     rax, cs:lpMem
0x18000b83e  mov     rbx, rcx
0x18000b841  add     rbx, rbx
0x18000b844  test    byte ptr [rax+rbx*8+0Eh], 1
0x18000b849  jnz     loc_18000B7A5
0x18000b84f  xor     edx, edx; unsigned int *
0x18000b851  call    ?GetFontSignatureFromFace@@YAKHPEAK@Z; GetFontSignatureFromFace(int,ulong *)
0x18000b856  mov     rax, cs:lpMem
0x18000b85d  jmp     loc_18000B7A5
0x18000b862  movsx   ecx, word ptr [rsp+88h+var_68+8]
0x18000b867  mov     eax, 55555556h
0x18000b86c  add     ecx, ecx
0x18000b86e  imul    ecx
0x18000b870  mov     eax, edx
0x18000b872  shr     eax, 1Fh
0x18000b875  add     edx, eax
0x18000b877  jmp     loc_18000B4C4
0x18000b87c  mov     r8d, 1
0x18000b882  mov     word ptr [rsp+88h+var_68+8], r8w
0x18000b888  jmp     loc_18000B4F9
0x18000b88d  cmp     byte ptr [rax+79h], 2
0x18000b891  jz      loc_18000B5EC
0x18000b897  jmp     loc_18000B67A
0x18000b89c  cmp     byte ptr [rax+79h], 2
0x18000b8a0  jz      loc_18000B757
0x18000b8a6  jmp     loc_18000B694
0x18000b8ab  test    byte ptr [rbx+7Bh], 1
0x18000b8af  jz      short loc_18000B8D8
0x18000b8b1  cmp     [rbx+0Ah], bp
0x18000b8b5  jnz     short loc_18000B8C3
0x18000b8b7  mov     edx, [rbx+4]
0x18000b8ba  cmp     edx, ecx
0x18000b8bc  jnb     short loc_18000B8C3
0x18000b8be  mov     ecx, edx
0x18000b8c0  mov     rax, rbx
0x18000b8c3  sub     rbx, 0FFFFFFFFFFFFFF80h
0x18000b8c7  cmp     rbx, r9
0x18000b8ca  jbe     short loc_18000B8AB
0x18000b8cc  test    rax, rax
0x18000b8cf  jz      loc_18000B6B3
0x18000b8d5  mov     rbx, rax
0x18000b8d8  lea     rdx, [rsp+88h+var_68]; struct CCharFormat *
0x18000b8dd  mov     [rbx+40h], rdi
0x18000b8e1  mov     rcx, rbx; this
0x18000b8e4  call    ?Init@CCcs@@QEAAHQEBVCCharFormat@@@Z; CCcs::Init(CCharFormat const * const)
0x18000b8e9  add     r14, r14
0x18000b8ec  test    eax, eax
0x18000b8ee  jz      loc_18000B6B6
0x18000b8f4  jmp     loc_18000B6BF
0x18000b8f9  mov     eax, dword ptr [rsp+88h+var_68]
  ... truncated ...
```
