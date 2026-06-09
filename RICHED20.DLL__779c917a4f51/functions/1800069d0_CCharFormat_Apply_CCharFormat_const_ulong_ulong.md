# CCharFormat::Apply(CCharFormat const *,ulong,ulong)

- ea: `0x1800069d0`
- end: `0x180006e47`
- name: `?Apply@CCharFormat@@QEAAJPEBV1@KK@Z`
- size: `1143`
- prototype: `__int64 __fastcall(CCharFormat *__hidden this, const struct CCharFormat *, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `11`
- tags: ``

## callers

- `0x180005480`
- `0x18002cc44`
- `0x180030568`
- `0x180031db8`

## callees

- `0x180004fe0`
- `0x1800069d0`
- `0x18001b57c`
- `0x180029d38`
- `0x180031cbc`
- `0x18003dc58`
- `0x18003e168`
- `0x180051168`
- `0x18008dcb0`
- `0x18008ddcc`
- `0x18008de60`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x180006d23`
- `KERNEL32!GetThreadLocale` at `0x180006d23`

## pseudocode

```c
__int64 __fastcall CCharFormat::Apply(CCharFormat *this, const struct CCharFormat *a2, int a3, int a4)
{
  __int16 v5; // bp
  unsigned int v8; // r10d
  char v10; // r14
  int v11; // r9d
  int v12; // r8d
  int v13; // ecx
  __int16 v14; // ax
  int v15; // eax
  unsigned __int8 v16; // dl
  unsigned __int8 v17; // r8
  int v18; // ecx
  const unsigned __int16 *FontName; // rax
  unsigned __int16 ThreadLocale; // ax
  int v21; // r14d
  unsigned __int8 CharSet; // al
  int v23; // edx
  unsigned __int16 v24; // ax
  char v25; // cl
  unsigned __int8 v26; // al
  __int16 v27; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v28; // [rsp+70h] [rbp+18h] BYREF
  unsigned __int8 v29; // [rsp+78h] [rbp+20h] BYREF

  v5 = a4;
  *(_DWORD *)this &= ~(a3 & 0x44037FFF);
  v8 = ~(a4 & 0xBBFC0000) & (*(_DWORD *)this | *(_DWORD *)a2 & a3 & 0x44037FFF);
  *(_DWORD *)this = v8;
  *(_DWORD *)this = v8 | *(_DWORD *)a2 & a4 & 0xBBFC0000;
  if ( (a3 & 1) != 0 )
  {
    v14 = 700;
    if ( (*(_BYTE *)a2 & 1) == 0 )
      v14 = 400;
    *((_WORD *)this + 8) = v14;
  }
  if ( (a3 & 0x40000000) != 0 )
    *((_DWORD *)this + 3) = *((_DWORD *)a2 + 3);
  if ( (a3 & 0xBFFFFFC0) != 0 )
  {
    v10 = 0;
    if ( a3 < 0 )
    {
      v15 = *((__int16 *)a2 + 4);
      if ( (a4 & 0x4000) != 0 )
        LOWORD(v15) = GetUsableFontHeight(*((__int16 *)this + 4), v15);
      *((_WORD *)this + 4) = v15;
    }
    if ( (a3 & 0x10000000) != 0 )
      *((_WORD *)this + 5) = *((_WORD *)a2 + 5);
    if ( (a3 & 0x8000000) == 0 || (int)CW32System::ScriptIndexFromCharSet(*((_BYTE *)a2 + 4)) < 0 )
      goto LABEL_25;
    if ( (v5 & 0x1100) == 0 )
    {
      v12 = *((unsigned __int8 *)this + 4);
      if ( (v5 & 0x2000) != 0 )
      {
        if ( (_BYTE)v11 )
        {
          if ( v12 == 128
            || v12 == 129
            || v12 == 130
            || v12 == 134
            || v12 == 136
            || (_BYTE)v12 == 2
            || (_BYTE)v12 == 0xFF
            || (*(_DWORD *)this & 0x40000) != 0 )
          {
            goto LABEL_25;
          }
        }
        else if ( (unsigned int)(v12 - 177) > 1 )
        {
LABEL_25:
          if ( (v5 & 0x500) == 0x500 )
          {
            v16 = *((_BYTE *)a2 + 4);
            v17 = *((_BYTE *)this + 4);
            if ( v17 != v16 && a3 < 0 )
              *((_WORD *)this + 4) = CW32System::GetPreferredFontHeight(
                                       (v5 & 0x200) != 0,
                                       v16,
                                       v17,
                                       *((_WORD *)this + 4));
          }
          if ( (a3 & 0x20000000) != 0 )
          {
            *((_BYTE *)this + 5) = *((_BYTE *)a2 + 5);
            v18 = *((__int16 *)a2 + 3);
            *((_WORD *)this + 3) = *((_WORD *)a2 + 3);
            FontName = GetFontName(v18);
            if ( FontName )
              LOWORD(FontName) = *FontName;
            if ( v10 || (_WORD)FontName )
            {
              if ( (GetCharFlags((unsigned __int16)FontName, 0) & 0x1E000000) != 0
                && *((unsigned __int8 *)this + 4) != 128
                && *((unsigned __int8 *)this + 4) != 129
                && *((unsigned __int8 *)this + 4) != 130
                && *((unsigned __int8 *)this + 4) != 134
                && *((unsigned __int8 *)this + 4) != 136 )
              {
                v13 = *((__int16 *)this + 3);
                v28 = 0;
                if ( (unsigned int)GetFontSignatureFromFace(v13, &v28) )
                {
                  if ( (v28 & 0x1E0000) != 0 )
                    *((_BYTE *)this + 4) = CW32System::GetFirstAvailCharSet(v28 & 0x1E0000);
                }
              }
            }
            else
            {
              ThreadLocale = GetThreadLocale();
              v21 = CW32System::ConvertLanguageIDtoCodePage(ThreadLocale);
              v27 = 0;
              LOBYTE(v28) = 0;
              v29 = 0;
              if ( CW32System::GetPreferredFontInfo(v21, 0, 0, &v27, (unsigned __int8 *)&v28, &v29) )
              {
                CharSet = CW32System::GetCharSet(v21, 0);
                v23 = (unsigned __int8)v28;
                *((_BYTE *)this + 4) = CharSet;
                *((_WORD *)this + 3) = v27;
                if ( a3 >= 0 || *((__int16 *)this + 4) < 20 * v23 )
                  *((_WORD *)this + 4) = 20 * v23;
                *((_BYTE *)this + 5) = v29;
              }
            }
          }
          if ( (a3 & 0x7FFFFC0) != 0 && (v5 & 0x8000) == 0 )
          {
            if ( (a3 & 0x400001) == 0x400000 )
            {
              v24 = *((_WORD *)a2 + 8);
              *(_DWORD *)this |= 1u;
              *((_WORD *)this + 8) = v24;
              if ( v24 < 0x227u )
                *(_DWORD *)this &= ~1u;
            }
            if ( (a3 & 0x4000000) != 0 )
              *((_DWORD *)this + 5) = *((_DWORD *)a2 + 5);
            if ( (a3 & 0x2000000) != 0 )
              *((_DWORD *)this + 6) = *((_DWORD *)a2 + 6);
            if ( (a3 & 0x200000) != 0 )
              *((_WORD *)this + 9) = *((_WORD *)a2 + 9);
            if ( (a3 & 0x100000) != 0 )
              *((_WORD *)this + 15) = *((_WORD *)a2 + 15);
            if ( (a3 & 0x80000) != 0 )
              *((_WORD *)this + 14) = *((_WORD *)a2 + 14);
            if ( (a3 & 0x800000) != 0 )
            {
              v25 = *((_BYTE *)a2 + 32);
              *((_BYTE *)this + 32) = v25;
              if ( (a3 & 4) == 0 )
              {
                *(_DWORD *)this &= ~4u;
                if ( v25 )
                  *(_DWORD *)this |= 4u;
              }
            }
            if ( (a3 & 0x40000) != 0 )
            {
              v26 = *((_BYTE *)a2 + 33);
              if ( v26 <= 0x12u )
                *((_BYTE *)this + 33) = v26;
            }
            if ( (a3 & 0x8000) != 0 )
              *((_BYTE *)this + 34) = *((_BYTE *)a2 + 34);
          }
          goto LABEL_5;
        }
      }
      else if ( (unsigned int)(v12 - 177) <= 1 != (unsigned int)(v11 - 177) <= 1
             && (_BYTE)v11 != 2
             && (_BYTE)v11 != 0xFF )
      {
        goto LABEL_25;
      }
    }
    v10 = 1;
    *((_BYTE *)this + 4) = v11;
    goto LABEL_25;
  }
LABEL_5:
  if ( (v5 & 0x2000) != 0 )
    *((_WORD *)this + 18) = *((_WORD *)a2 + 18);
  return 0;
}

```

## disassembly

```asm
0x1800069d0  push    rbx
0x1800069d2  push    rsi
0x1800069d3  sub     rsp, 48h
0x1800069d7  mov     rbx, rcx
0x1800069da  mov     [rsp+58h+arg_8], rbp
0x1800069df  mov     r10d, r8d
0x1800069e2  mov     [rsp+58h+var_18], rdi
0x1800069e7  and     r10d, 44037FFFh
0x1800069ee  mov     ebp, r9d
0x1800069f1  mov     eax, r10d
0x1800069f4  mov     edi, r8d
0x1800069f7  not     eax
0x1800069f9  mov     rsi, rdx
0x1800069fc  and     [rcx], eax
0x1800069fe  mov     ecx, r9d
0x180006a01  and     r10d, [rdx]
0x180006a04  and     ecx, 0BBFC0000h
0x180006a0a  or      r10d, [rbx]
0x180006a0d  mov     eax, ecx
0x180006a0f  not     eax
0x180006a11  and     r10d, eax
0x180006a14  mov     [rbx], r10d
0x180006a17  and     ecx, [rdx]
0x180006a19  or      ecx, r10d
0x180006a1c  mov     [rbx], ecx
0x180006a1e  test    r8b, 1
0x180006a22  jnz     loc_180006C30
0x180006a28  bt      edi, 1Eh
0x180006a2c  jnb     short loc_180006A34
0x180006a2e  mov     eax, [rdx+0Ch]
0x180006a31  mov     [rbx+0Ch], eax
0x180006a34  test    edi, 0BFFFFFC0h
0x180006a3a  jnz     short loc_180006A5D
0x180006a3c  mov     rdi, [rsp+58h+var_18]
0x180006a41  bt      ebp, 0Dh
0x180006a45  mov     rbp, [rsp+58h+arg_8]
0x180006a4a  jnb     short loc_180006A54
0x180006a4c  movzx   eax, word ptr [rsi+24h]
0x180006a50  mov     [rbx+24h], ax
0x180006a54  xor     eax, eax
0x180006a56  add     rsp, 48h
0x180006a5a  pop     rsi
0x180006a5b  pop     rbx
0x180006a5c  retn
0x180006a5d  mov     [rsp+58h+var_20], r14
0x180006a62  xor     r14b, r14b
0x180006a65  test    edi, edi
0x180006a67  js      loc_180006C4A
0x180006a6d  bt      edi, 1Ch
0x180006a71  jb      loc_180006C72
0x180006a77  bt      edi, 1Bh
0x180006a7b  jnb     short loc_180006AE9
0x180006a7d  movzx   r9d, byte ptr [rsi+4]
0x180006a82  movzx   ecx, r9b; unsigned __int8
0x180006a86  call    ?ScriptIndexFromCharSet@CW32System@@SAJE@Z; CW32System::ScriptIndexFromCharSet(uchar)
0x180006a8b  test    eax, eax
0x180006a8d  js      short loc_180006AE9
0x180006a8f  test    ebp, 1100h
0x180006a95  jnz     short loc_180006AE2
0x180006a97  movzx   r8d, byte ptr [rbx+4]
0x180006a9c  bt      ebp, 0Dh
0x180006aa0  jnb     loc_180006C7F
0x180006aa6  test    r9b, r9b
0x180006aa9  jz      loc_180006B92
0x180006aaf  mov     ecx, r8d
0x180006ab2  sub     ecx, 80h
0x180006ab8  jz      short loc_180006AE9
0x180006aba  sub     ecx, 1
0x180006abd  jz      short loc_180006AE9
0x180006abf  sub     ecx, 1
0x180006ac2  jz      short loc_180006AE9
0x180006ac4  sub     ecx, 4
0x180006ac7  jz      short loc_180006AE9
0x180006ac9  cmp     ecx, 2
0x180006acc  jz      short loc_180006AE9
0x180006ace  cmp     r8b, 2
0x180006ad2  jz      short loc_180006AE9
0x180006ad4  cmp     r8b, 0FFh
0x180006ad8  jz      short loc_180006AE9
0x180006ada  test    dword ptr [rbx], 40000h
0x180006ae0  jnz     short loc_180006AE9
0x180006ae2  mov     r14b, 1
0x180006ae5  mov     [rbx+4], r9b
0x180006ae9  mov     eax, ebp
0x180006aeb  and     eax, 500h
0x180006af0  cmp     eax, 500h
0x180006af5  jz      loc_180006CBE
0x180006afb  bt      edi, 1Dh
0x180006aff  jb      loc_180006CF3
0x180006b05  mov     r14, [rsp+58h+var_20]
0x180006b0a  test    edi, 7FFFFC0h
0x180006b10  setnz   cl
0x180006b13  bt      ebp, 0Fh
0x180006b17  setnb   al
0x180006b1a  test    al, cl
0x180006b1c  jz      loc_180006A3C
0x180006b22  mov     eax, edi
0x180006b24  and     eax, 400001h
0x180006b29  cmp     eax, 400000h
0x180006b2e  jz      loc_180006DBC
0x180006b34  bt      edi, 1Ah
0x180006b38  jb      loc_180006DDD
0x180006b3e  bt      edi, 19h
0x180006b42  jnb     short loc_180006B4A
0x180006b44  mov     eax, [rsi+18h]
0x180006b47  mov     [rbx+18h], eax
0x180006b4a  bt      edi, 15h
0x180006b4e  jb      loc_180006DE8
0x180006b54  bt      edi, 14h
0x180006b58  jb      loc_180006DF5
0x180006b5e  bt      edi, 13h
0x180006b62  jb      loc_180006E02
0x180006b68  bt      edi, 17h
0x180006b6c  jb      loc_180006E0F
0x180006b72  bt      edi, 12h
0x180006b76  jb      loc_180006E33
0x180006b7c  bt      edi, 0Fh
0x180006b80  jnb     loc_180006A3C
0x180006b86  movzx   eax, byte ptr [rsi+22h]
0x180006b8a  mov     [rbx+22h], al
0x180006b8d  jmp     loc_180006A3C
0x180006b92  lea     eax, [r8-0B1h]
0x180006b99  cmp     eax, 1
0x180006b9c  ja      loc_180006AE9
0x180006ba2  jmp     loc_180006AE2
0x180006ba7  movzx   ecx, byte ptr [rbx+4]
0x180006bab  sub     ecx, 80h
0x180006bb1  jz      loc_180006B05
0x180006bb7  sub     ecx, 1
0x180006bba  jz      loc_180006B05
0x180006bc0  sub     ecx, 1
0x180006bc3  jz      loc_180006B05
0x180006bc9  sub     ecx, 4
0x180006bcc  jz      loc_180006B05
0x180006bd2  cmp     ecx, 2
0x180006bd5  jz      loc_180006B05
0x180006bdb  movsx   ecx, word ptr [rbx+6]; int
0x180006bdf  lea     rdx, [rsp+58h+arg_10]; unsigned int *
0x180006be4  mov     [rsp+58h+arg_10], 0
0x180006bec  call    ?GetFontSignatureFromFace@@YAKHPEAK@Z; GetFontSignatureFromFace(int,ulong *)
0x180006bf1  test    eax, eax
0x180006bf3  jz      loc_180006B05
0x180006bf9  mov     ecx, [rsp+58h+arg_10]
0x180006bfd  and     ecx, 1E0000h; unsigned int
0x180006c03  jz      loc_180006B05
0x180006c09  call    ?GetFirstAvailCharSet@CW32System@@SAEK@Z; CW32System::GetFirstAvailCharSet(ulong)
0x180006c0e  mov     [rbx+4], al
0x180006c11  jmp     loc_180006B05
0x180006c16  movzx   ecx, ax; unsigned int
0x180006c19  xor     edx, edx; unsigned __int8
0x180006c1b  call    ?GetCharFlags@@YAKKE@Z; GetCharFlags(ulong,uchar)
0x180006c20  test    eax, 1E000000h
0x180006c25  jz      loc_180006B05
0x180006c2b  jmp     loc_180006BA7
0x180006c30  test    byte ptr [rdx], 1
0x180006c33  mov     eax, 2BCh
0x180006c38  mov     ecx, 190h
0x180006c3d  cmovz   ax, cx
0x180006c41  mov     [rbx+10h], ax
0x180006c45  jmp     loc_180006A28
0x180006c4a  movsx   eax, word ptr [rdx+8]
0x180006c4e  mov     [rsp+58h+var_28], r15
0x180006c53  bt      ebp, 0Eh
0x180006c57  jnb     short loc_180006C64
0x180006c59  movsx   ecx, word ptr [rbx+8]; int
0x180006c5d  mov     edx, eax; int
0x180006c5f  call    ?GetUsableFontHeight@@YAJJJ@Z; GetUsableFontHeight(long,long)
0x180006c64  mov     r15, [rsp+58h+var_28]
0x180006c69  mov     [rbx+8], ax
0x180006c6d  jmp     loc_180006A6D
0x180006c72  movzx   eax, word ptr [rsi+0Ah]
0x180006c76  mov     [rbx+0Ah], ax
0x180006c7a  jmp     loc_180006A77
0x180006c7f  xor     edx, edx
0x180006c81  lea     eax, [r9-0B1h]
0x180006c88  cmp     eax, 1
0x180006c8b  lea     eax, [r8-0B1h]
0x180006c92  setbe   dl
0x180006c95  xor     ecx, ecx
0x180006c97  cmp     eax, 1
0x180006c9a  setbe   cl
0x180006c9d  cmp     ecx, edx
0x180006c9f  jz      loc_180006AE2
0x180006ca5  cmp     r9b, 2
0x180006ca9  jz      loc_180006AE2
0x180006caf  cmp     r9b, 0FFh
0x180006cb3  jnz     loc_180006AE9
0x180006cb9  jmp     loc_180006AE2
0x180006cbe  movzx   edx, byte ptr [rsi+4]; unsigned __int8
0x180006cc2  movzx   r8d, byte ptr [rbx+4]; unsigned __int8
0x180006cc7  cmp     r8b, dl
0x180006cca  jz      loc_180006AFB
0x180006cd0  test    edi, edi
0x180006cd2  jns     loc_180006AFB
0x180006cd8  movzx   r9d, word ptr [rbx+8]; __int16
0x180006cdd  mov     ecx, ebp
0x180006cdf  shr     ecx, 9
0x180006ce2  and     cl, 1; bool
0x180006ce5  call    ?GetPreferredFontHeight@CW32System@@SAF_NEEF@Z; CW32System::GetPreferredFontHeight(bool,uchar,uchar,short)
0x180006cea  mov     [rbx+8], ax
0x180006cee  jmp     loc_180006AFB
0x180006cf3  movzx   eax, byte ptr [rsi+5]
0x180006cf7  mov     [rbx+5], al
0x180006cfa  movsx   eax, word ptr [rsi+6]
0x180006cfe  mov     ecx, eax; int
0x180006d00  mov     [rbx+6], ax
0x180006d04  call    ?GetFontName@@YAPEBGJ@Z; GetFontName(long)
0x180006d09  test    rax, rax
0x180006d0c  jz      short loc_180006D11
0x180006d0e  movzx   eax, word ptr [rax]
0x180006d11  test    r14b, r14b
0x180006d14  jnz     loc_180006C16
0x180006d1a  test    ax, ax
0x180006d1d  jnz     loc_180006C16
0x180006d23  call    cs:__imp_GetThreadLocale
0x180006d29  mov     ecx, eax; unsigned __int16
0x180006d2b  call    ?ConvertLanguageIDtoCodePage@CW32System@@SAIG@Z; CW32System::ConvertLanguageIDtoCodePage(ushort)
0x180006d30  xor     ecx, ecx
0x180006d32  lea     r9, [rsp+58h+arg_0]; __int16 *
0x180006d37  mov     r14d, eax
0x180006d3a  mov     [rsp+58h+arg_0], cx
0x180006d3f  lea     rax, [rsp+58h+arg_18]
0x180006d44  mov     byte ptr [rsp+58h+arg_10], cl
0x180006d48  mov     [rsp+58h+var_30], rax; unsigned __int8 *
0x180006d4d  xor     r8d, r8d; bool
0x180006d50  lea     rax, [rsp+58h+arg_10]
0x180006d55  mov     [rsp+58h+arg_18], cl
0x180006d59  xor     edx, edx; bool
0x180006d5b  mov     [rsp+58h+var_38], rax; unsigned __int8 *
0x180006d60  mov     ecx, r14d; int
0x180006d63  call    ?GetPreferredFontInfo@CW32System@@SA_NH_N0AEAFAEAE2@Z; CW32System::GetPreferredFontInfo(int,bool,bool,short &,uchar &,uchar &)
0x180006d68  test    al, al
0x180006d6a  jz      loc_180006B05
0x180006d70  xor     edx, edx; int *
0x180006d72  mov     ecx, r14d; int
0x180006d75  call    ?GetCharSet@CW32System@@SAEHPEAH@Z; CW32System::GetCharSet(int,int *)
0x180006d7a  movzx   edx, byte ptr [rsp+58h+arg_10]
0x180006d7f  mov     [rbx+4], al
0x180006d82  movzx   eax, [rsp+58h+arg_0]
0x180006d87  mov     [rbx+6], ax
0x180006d8b  test    edi, edi
0x180006d8d  jns     short loc_180006D9D
0x180006d8f  movsx   eax, word ptr [rbx+8]
0x180006d93  lea     ecx, [rdx+rdx*4]
0x180006d96  shl     ecx, 2
0x180006d99  cmp     eax, ecx
0x180006d9b  jge     short loc_180006DAF
0x180006d9d  movzx   eax, dx
0x180006da0  shl     ax, 2
0x180006da4  lea     ecx, [rax+rdx]
0x180006da7  shl     cx, 2
0x180006dab  mov     [rbx+8], cx
0x180006daf  movzx   eax, [rsp+58h+arg_18]
0x180006db4  mov     [rbx+5], al
0x180006db7  jmp     loc_180006B05
0x180006dbc  movzx   eax, word ptr [rsi+10h]
0x180006dc0  mov     edx, 227h
0x180006dc5  or      dword ptr [rbx], 1
0x180006dc8  mov     [rbx+10h], ax
0x180006dcc  cmp     ax, dx
0x180006dcf  jnb     loc_180006B34
0x180006dd5  and     dword ptr [rbx], 0FFFFFFFEh
0x180006dd8  jmp     loc_180006B34
0x180006ddd  mov     eax, [rsi+14h]
0x180006de0  mov     [rbx+14h], eax
0x180006de3  jmp     loc_180006B3E
0x180006de8  movzx   eax, word ptr [rsi+12h]
0x180006dec  mov     [rbx+12h], ax
0x180006df0  jmp     loc_180006B54
0x180006df5  movzx   eax, word ptr [rsi+1Eh]
0x180006df9  mov     [rbx+1Eh], ax
0x180006dfd  jmp     loc_180006B5E
0x180006e02  movzx   eax, word ptr [rsi+1Ch]
0x180006e06  mov     [rbx+1Ch], ax
0x180006e0a  jmp     loc_180006B68
0x180006e0f  movzx   ecx, byte ptr [rsi+20h]
0x180006e13  mov     [rbx+20h], cl
0x180006e16  test    dil, 4
0x180006e1a  jnz     loc_180006B72
0x180006e20  and     dword ptr [rbx], 0FFFFFFFBh
0x180006e23  test    cl, cl
0x180006e25  jz      loc_180006B72
0x180006e2b  or      dword ptr [rbx], 4
0x180006e2e  jmp     loc_180006B72
0x180006e33  movzx   eax, byte ptr [rsi+21h]
0x180006e37  cmp     al, 12h
0x180006e39  ja      loc_180006B7C
0x180006e3f  mov     [rbx+21h], al
0x180006e42  jmp     loc_180006B7C
```
