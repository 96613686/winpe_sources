# DavUrlEncodeNtPath

- ea: `0x180001830`
- end: `0x180001b93`
- name: `DavUrlEncodeNtPath`
- size: `867`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, char *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180001460`

## callees

- `0x180001830`
- `0x1800047b0`
- `0x180005ff0`

## pseudocode

```c
__int64 __fastcall DavUrlEncodeNtPath(unsigned __int16 *a1, __int64 a2, char *a3, _QWORD *a4)
{
  unsigned __int64 v4; // rsi
  unsigned __int16 v5; // r12
  char v6; // bp
  __int64 v7; // r14
  unsigned __int16 *v9; // r11
  unsigned int Utf8EncodedCodeUnitCountForCodePoint; // r10d
  char *v11; // rdi
  __int16 *v12; // r9
  __int16 v13; // dx
  char32_t v14; // ebx
  char v15; // al
  unsigned __int8 v16; // r9
  unsigned __int8 v17; // dl
  unsigned __int64 v18; // rcx
  __int64 result; // rax
  __int16 v20; // dx
  __int64 v21; // rcx
  __int64 v22; // r8
  char v23; // al
  bool v24; // zf
  int v25; // r10d
  unsigned __int16 v26; // dx
  __int64 v27; // r9
  unsigned __int16 v28; // dx
  unsigned __int16 v29; // [rsp+60h] [rbp+8h] BYREF
  char v30; // [rsp+68h] [rbp+10h] BYREF

  v4 = (unsigned __int64)&a1[a2];
  v5 = v29;
  v6 = 0;
  v7 = 0;
  v9 = a1;
  Utf8EncodedCodeUnitCountForCodePoint = 0;
  v11 = &a3[2 * *a4];
LABEL_2:
  v12 = &_ImageBase;
LABEL_3:
  while ( 2 )
  {
    if ( (unsigned __int64)v9 >= v4 )
    {
LABEL_22:
      *a4 = v7;
      result = v6 != 0 ? 0x246 : 0;
      if ( !v6 )
        return Utf8EncodedCodeUnitCountForCodePoint;
      return result;
    }
    if ( a3 >= v11 )
    {
LABEL_27:
      while ( 2 )
      {
        if ( (unsigned __int64)v9 >= v4 )
        {
          Utf8EncodedCodeUnitCountForCodePoint = 122;
          goto LABEL_22;
        }
        v20 = *v9;
        if ( v6 )
        {
          v28 = v20 + 9216;
          if ( v28 > 0x3FFu )
            return 582;
          v6 = 0;
          v21 = v28 + (v5 << 10) + 0x10000;
        }
        else
        {
          if ( (unsigned __int16)(v20 + 10240) < 0x800u )
          {
            if ( (unsigned __int16)(v20 + 10240) > 0x3FFu )
              return 582;
            v6 = 1;
            v5 = v20 + 10240;
            ++v9;
            continue;
          }
          v21 = *v9;
        }
        break;
      }
      v22 = 2;
      if ( (unsigned int)v21 < 0x80 && (*((_BYTE *)v12 + v21 + 29792) & 8) == 0 )
      {
        ++v7;
        goto LABEL_26;
      }
      v23 = 0;
      LOBYTE(v29) = 0;
      while ( 1 )
      {
        if ( v23 )
          goto LABEL_40;
        if ( (unsigned int)v21 < 0x80 )
          goto LABEL_36;
        result = GetUtf8EncodedCodeUnitCountForCodePoint(v21, &v29, v22, v12);
        if ( (_DWORD)result )
        {
          v7 += 3;
          if ( (_DWORD)result != 234 )
            goto LABEL_38;
          v23 = v29;
        }
        else
        {
          v23 = v29;
LABEL_40:
          v24 = v23-- == 1;
          LOBYTE(v29) = v23;
          if ( v24 )
          {
LABEL_36:
            result = 0;
            v7 += 3;
LABEL_38:
            if ( (_DWORD)result )
              return result;
LABEL_26:
            v9 = (unsigned __int16 *)((char *)v9 + v22);
            goto LABEL_27;
          }
          v7 += 3;
        }
      }
    }
    v13 = *v9;
    if ( v6 )
    {
      v26 = v13 + 9216;
      if ( v26 <= 0x3FFu )
      {
        v6 = 0;
        v14 = (v5 << 10) + 0x10000 + v26;
LABEL_8:
        Utf8EncodedCodeUnitCountForCodePoint = 0;
        ++v9;
        if ( v14 == 92 )
        {
          v14 = 47;
        }
        else if ( v14 >= 0x80 )
        {
LABEL_13:
          v15 = 0;
          LOBYTE(v29) = 0;
          while ( 1 )
          {
            if ( (__int64)((v11 - a3) & 0xFFFFFFFFFFFFFFFEuLL) < 6 )
            {
              do
              {
                v30 = 0;
                v7 += 3;
              }
              while ( Utf8Encoder::ProcessCodePoint((Utf8Encoder *)&v29, v14, &v30) == 234 );
              a3 = v11;
              Utf8EncodedCodeUnitCountForCodePoint = 122;
              goto LABEL_2;
            }
            if ( v15 )
              break;
            if ( v14 >= 0x80 )
            {
              Utf8EncodedCodeUnitCountForCodePoint = GetUtf8EncodedCodeUnitCountForCodePoint(v14, &v29, a3, &_ImageBase);
              if ( Utf8EncodedCodeUnitCountForCodePoint )
              {
                v15 = v29;
                v16 = 0;
                goto LABEL_18;
              }
              v15 = v29;
              v25 = *(unsigned __int8 *)(v27 + 2LL * (unsigned __int8)v29 + 30432);
              goto LABEL_43;
            }
            v16 = v14;
            Utf8EncodedCodeUnitCountForCodePoint = 0;
LABEL_18:
            v17 = v16;
            v7 += 3;
            *(_WORD *)a3 = 37;
            v18 = (unsigned __int64)v16 >> 4;
            v12 = &_ImageBase;
            *((_WORD *)a3 + 1) = `HexEncodeNibble'::`2'::hex_chars[v18];
            *((_WORD *)a3 + 2) = `HexEncodeNibble'::`2'::hex_chars[v17 & 0xF];
            a3 += 6;
            if ( Utf8EncodedCodeUnitCountForCodePoint != 234 )
            {
              if ( Utf8EncodedCodeUnitCountForCodePoint && Utf8EncodedCodeUnitCountForCodePoint != 122 )
                return Utf8EncodedCodeUnitCountForCodePoint;
              goto LABEL_3;
            }
          }
          LOBYTE(v25) = 0x80;
LABEL_43:
          LOBYTE(v29) = --v15;
          v16 = v25 | (v14 >> (6 * v15)) & 0x3F;
          Utf8EncodedCodeUnitCountForCodePoint = v15 != 0 ? 0xEA : 0;
          goto LABEL_18;
        }
        if ( (*((_BYTE *)&AsciiUrlCharTraitsTable + v14) & 8) == 0 )
        {
          *(_WORD *)a3 = v14;
          a3 += 2;
          ++v7;
          continue;
        }
        goto LABEL_13;
      }
    }
    else
    {
      if ( (unsigned __int16)(v13 + 10240) >= 0x800u )
      {
        v14 = *v9;
        goto LABEL_8;
      }
      if ( (unsigned __int16)(v13 + 10240) <= 0x3FFu )
      {
        v6 = 1;
        v5 = v13 + 10240;
        Utf8EncodedCodeUnitCountForCodePoint = 997;
        ++v9;
        continue;
      }
    }
    return 582;
  }
}

```

## disassembly

```asm
0x180001830  mov     [rsp+arg_10], rbx
0x180001835  push    rbp
0x180001836  push    rsi
0x180001837  push    rdi
0x180001838  push    r12
0x18000183a  push    r13
0x18000183c  push    r14
0x18000183e  push    r15
0x180001840  sub     rsp, 20h
0x180001844  mov     rax, [r9]
0x180001847  lea     rsi, [rcx+rdx*2]
0x18000184b  movzx   r12d, [rsp+58h+arg_0]
0x180001851  xor     bpl, bpl
0x180001854  xor     r14d, r14d
0x180001857  mov     r15, r9
0x18000185a  mov     r11, rcx
0x18000185d  xor     r10d, r10d
0x180001860  lea     rdi, [r8+rax*2]
0x180001864  mov     r13d, 2800h
0x18000186a  lea     r9, __ImageBase
0x180001871  mov     ecx, 800h
0x180001876  mov     ebx, 3FFh
0x18000187b  mov     eax, 2400h
0x180001880  cmp     r11, rsi
0x180001883  jnb     loc_180001984
0x180001889  cmp     r8, rdi
0x18000188c  jnb     loc_1800019C2
0x180001892  movzx   edx, word ptr [r11]
0x180001896  test    bpl, bpl
0x180001899  jnz     loc_180001AB3
0x18000189f  lea     eax, [rdx+r13]
0x1800018a3  cmp     ax, cx
0x1800018a6  jb      loc_180001A77
0x1800018ac  mov     ebx, edx
0x1800018ae  xor     r10d, r10d
0x1800018b1  add     r11, 2
0x1800018b5  cmp     ebx, 5Ch ; '\'
0x1800018b8  jnz     short loc_1800018D9
0x1800018ba  mov     ebx, 2Fh ; '/'
0x1800018bf  mov     eax, ebx
0x1800018c1  test    byte ptr [rax+r9+7460h], 8
0x1800018ca  jnz     short loc_1800018E1
0x1800018cc  mov     [r8], bx
0x1800018d0  add     r8, 2
0x1800018d4  inc     r14
0x1800018d7  jmp     short loc_180001876
0x1800018d9  cmp     ebx, 80h
0x1800018df  jb      short loc_1800018BF
0x1800018e1  xor     al, al
0x1800018e3  mov     byte ptr [rsp+58h+arg_0], al
0x1800018e7  mov     rcx, rdi
0x1800018ea  sub     rcx, r8
0x1800018ed  and     rcx, 0FFFFFFFFFFFFFFFEh
0x1800018f1  cmp     rcx, 6
0x1800018f5  jl      loc_180001B0D
0x1800018fb  test    al, al
0x1800018fd  jnz     loc_180001A48
0x180001903  cmp     ebx, 80h
0x180001909  jnb     loc_180001ADA
0x18000190f  movzx   r9d, bl
0x180001913  xor     r10d, r10d
0x180001916  movzx   edx, r9b
0x18000191a  add     r14, 3
0x18000191e  mov     ecx, edx
0x180001920  mov     word ptr [r8], 25h ; '%'
0x180001926  shr     rcx, 4
0x18000192a  lea     r9, __ImageBase
0x180001931  and     edx, 0Fh
0x180001934  movsx   ecx, byte ptr [rcx+r9+7508h]
0x18000193d  mov     [r8+2], cx
0x180001942  movsx   ecx, byte ptr [rdx+r9+7508h]
0x18000194b  mov     [r8+4], cx
0x180001950  add     r8, 6
0x180001954  cmp     r10d, 0EAh
0x18000195b  jz      short loc_1800018E7
0x18000195d  mov     ecx, 800h
0x180001962  mov     ebx, 3FFh
0x180001967  mov     eax, 2400h
0x18000196c  test    r10d, r10d
0x18000196f  jz      loc_180001880
0x180001975  cmp     r10d, 7Ah ; 'z'
0x180001979  jz      loc_180001880
0x18000197f  mov     eax, r10d
0x180001982  jmp     short loc_18000199D
0x180001984  movzx   eax, bpl
0x180001988  mov     [r15], r14
0x18000198b  neg     al
0x18000198d  mov     ecx, 246h
0x180001992  sbb     eax, eax
0x180001994  and     eax, ecx
0x180001996  test    bpl, bpl
0x180001999  cmovz   eax, r10d
0x18000199d  mov     rbx, [rsp+58h+arg_10]
0x1800019a2  add     rsp, 20h
0x1800019a6  pop     r15
0x1800019a8  pop     r14
0x1800019aa  pop     r13
0x1800019ac  pop     r12
0x1800019ae  pop     rdi
0x1800019af  pop     rsi
0x1800019b0  pop     rbp
0x1800019b1  retn
0x1800019b2  inc     r14
0x1800019b5  add     r11, r8
0x1800019b8  mov     ecx, 800h
0x1800019bd  mov     eax, 2400h
0x1800019c2  cmp     r11, rsi
0x1800019c5  jnb     loc_180001B88
0x1800019cb  movzx   edx, word ptr [r11]
0x1800019cf  test    bpl, bpl
0x1800019d2  jnz     loc_180001B3C
0x1800019d8  lea     eax, [rdx+r13]
0x1800019dc  cmp     ax, cx
0x1800019df  jb      loc_180001A88
0x1800019e5  mov     ecx, edx
0x1800019e7  mov     r8d, 2
0x1800019ed  cmp     ecx, 80h
0x1800019f3  jnb     short loc_180001A00
0x1800019f5  test    byte ptr [rcx+r9+7460h], 8
0x1800019fe  jz      short loc_1800019B2
0x180001a00  xor     al, al
0x180001a02  mov     byte ptr [rsp+58h+arg_0], al
0x180001a06  test    al, al
0x180001a08  jnz     short loc_180001A3A
0x180001a0a  cmp     ecx, 80h
0x180001a10  jnb     loc_180001B62
0x180001a16  xor     eax, eax
0x180001a18  add     r14, 3
0x180001a1c  jmp     short loc_180001A2D
0x180001a1e  add     r14, 3
0x180001a22  cmp     eax, 0EAh
0x180001a27  jz      loc_180001B7E
0x180001a2d  test    eax, eax
0x180001a2f  jnz     loc_18000199D
0x180001a35  jmp     loc_1800019B5
0x180001a3a  add     al, 0FFh
0x180001a3c  mov     byte ptr [rsp+58h+arg_0], al
0x180001a40  jz      short loc_180001A16
0x180001a42  add     r14, 3
0x180001a46  jmp     short loc_180001A06
0x180001a48  mov     r10b, 80h
0x180001a4b  add     al, 0FFh
0x180001a4d  mov     r9d, ebx
0x180001a50  movzx   edx, al
0x180001a53  mov     byte ptr [rsp+58h+arg_0], al
0x180001a57  lea     ecx, [rdx+rdx*2]
0x180001a5a  add     ecx, ecx
0x180001a5c  shr     r9d, cl
0x180001a5f  and     r9b, 3Fh
0x180001a63  or      r9b, r10b
0x180001a66  neg     dl
0x180001a68  sbb     r10d, r10d
0x180001a6b  and     r10d, 0EAh
0x180001a72  jmp     loc_180001916
0x180001a77  cmp     ax, bx
0x180001a7a  jbe     short loc_180001A9D
0x180001a7c  mov     ecx, 246h
0x180001a81  mov     eax, ecx
0x180001a83  jmp     loc_18000199D
0x180001a88  cmp     ax, bx
0x180001a8b  ja      short loc_180001A7C
0x180001a8d  mov     bpl, 1
0x180001a90  movzx   r12d, ax
0x180001a94  add     r11, 2
0x180001a98  jmp     loc_1800019BD
0x180001a9d  mov     bpl, 1
0x180001aa0  movzx   r12d, ax
0x180001aa4  mov     r10d, 3E5h
0x180001aaa  add     r11, 2
0x180001aae  jmp     loc_18000187B
0x180001ab3  add     dx, ax
0x180001ab6  cmp     dx, bx
0x180001ab9  ja      short loc_180001A7C
0x180001abb  movzx   ecx, r12w
0x180001abf  xor     bpl, bpl
0x180001ac2  shl     ecx, 0Ah
0x180001ac5  add     ecx, 10000h
0x180001acb  movzx   ebx, dx
0x180001ace  add     ebx, ecx
0x180001ad0  mov     ecx, 800h
0x180001ad5  jmp     loc_1800018AE
0x180001ada  lea     rdx, [rsp+58h+arg_0]
0x180001adf  mov     ecx, ebx
0x180001ae1  call    GetUtf8EncodedCodeUnitCountForCodePoint
0x180001ae6  mov     r10d, eax
0x180001ae9  test    eax, eax
0x180001aeb  jz      short loc_180001AFA
0x180001aed  movzx   eax, byte ptr [rsp+58h+arg_0]
0x180001af2  xor     r9b, r9b
0x180001af5  jmp     loc_180001916
0x180001afa  movzx   eax, byte ptr [rsp+58h+arg_0]
0x180001aff  movzx   r10d, byte ptr [r9+rax*2+76E0h]
0x180001b08  jmp     loc_180001A4B
0x180001b0d  lea     r8, [rsp+58h+arg_8]; char *
0x180001b12  mov     [rsp+58h+arg_8], 0
0x180001b17  mov     edx, ebx; char32_t
0x180001b19  lea     rcx, [rsp+58h+arg_0]; this
0x180001b1e  add     r14, 3
0x180001b22  call    ?ProcessCodePoint@Utf8Encoder@@QEAAK_UAEAD@Z; Utf8Encoder::ProcessCodePoint(char32_t,char &)
0x180001b27  cmp     eax, 0EAh
0x180001b2c  jz      short loc_180001B0D
0x180001b2e  mov     r8, rdi
0x180001b31  mov     r10d, 7Ah ; 'z'
0x180001b37  jmp     loc_18000186A
0x180001b3c  add     dx, ax
0x180001b3f  cmp     dx, bx
0x180001b42  ja      loc_180001A7C
0x180001b48  movzx   ecx, r12w
0x180001b4c  xor     bpl, bpl
0x180001b4f  shl     ecx, 0Ah
0x180001b52  add     ecx, 10000h
0x180001b58  movzx   eax, dx
0x180001b5b  add     ecx, eax
0x180001b5d  jmp     loc_1800019E7
0x180001b62  lea     rdx, [rsp+58h+arg_0]
0x180001b67  call    GetUtf8EncodedCodeUnitCountForCodePoint
0x180001b6c  test    eax, eax
0x180001b6e  jnz     loc_180001A1E
0x180001b74  movzx   eax, byte ptr [rsp+58h+arg_0]
0x180001b79  jmp     loc_180001A3A
0x180001b7e  movzx   eax, byte ptr [rsp+58h+arg_0]
0x180001b83  jmp     loc_180001A06
0x180001b88  mov     r10d, 7Ah ; 'z'
0x180001b8e  jmp     loc_180001984
```
