# umpToMIDI1Protocol::UMPStreamParse(uint)

- ea: `0x18001098c`
- end: `0x180010e0c`
- name: `?UMPStreamParse@umpToMIDI1Protocol@@QEAAXI@Z`
- size: `1152`
- prototype: `void __fastcall(umpToMIDI1Protocol *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010650`

## callees

- `0x18001098c`

## pseudocode

```c
void __fastcall umpToMIDI1Protocol::UMPStreamParse(umpToMIDI1Protocol *this, unsigned int a2)
{
  int v2; // r10d
  char v4; // r10
  char v5; // bl
  char v6; // di
  char v7; // r10
  int v8; // r11d
  int v9; // eax
  int v10; // ecx
  int v11; // ecx
  int v12; // edi
  int v13; // ebx
  int v14; // ecx
  __int64 v15; // rax
  unsigned __int8 v16; // al
  int v17; // r11d
  int v18; // r10d
  int v19; // ecx
  int v20; // r10d
  int v21; // r9d
  __int64 v22; // rcx
  int v23; // eax
  int v24; // eax
  unsigned int v25; // eax

  v2 = *((unsigned __int8 *)this + 8);
  if ( v2 )
  {
    if ( v2 != 1 )
    {
      if ( v2 != 2 )
      {
        if ( v2 != 3 )
          return;
        goto LABEL_5;
      }
      if ( *(_BYTE *)this == 11 || *(_BYTE *)this == 12 )
      {
        v4 = 0;
        goto LABEL_10;
      }
LABEL_8:
      v4 = v2 + 1;
LABEL_10:
      *((_BYTE *)this + 8) = v4;
      return;
    }
    if ( *(_BYTE *)this == 3 )
    {
      v22 = *((int *)this + 8);
      v23 = *((_DWORD *)this + 1);
      *((_BYTE *)this + 8) = 0;
      *((_DWORD *)this + v22 + 3) = v23;
      ++*((_DWORD *)this + 8);
      ++*((_DWORD *)this + 9);
      v24 = *((_DWORD *)this + 8);
      if ( v24 == 4 )
      {
        *((_DWORD *)this + 8) = 0;
        v24 = 0;
      }
      *((_DWORD *)this + v24 + 3) = a2;
      goto LABEL_66;
    }
    if ( *(_BYTE *)this != 4 )
    {
      if ( *(_BYTE *)this == 8 || (unsigned int)*(unsigned __int8 *)this - 9 < 2 )
      {
LABEL_5:
        *((_BYTE *)this + 8) = 0;
        return;
      }
      goto LABEL_8;
    }
    v5 = *((_BYTE *)this + 5);
    v6 = *((_BYTE *)this + 4);
    v7 = BYTE2(*((_DWORD *)this + 1));
    v8 = HIBYTE(*((_DWORD *)this + 1));
    *((_BYTE *)this + 8) = 0;
    if ( (v7 & 0xF0) == 0x20 )
    {
      v17 = ((v7 & 0xF) << 16) + ((v8 & 0xF) << 24);
      *((_DWORD *)this + (*((_DWORD *)this + 8))++ + 3) = v17 + (v5 & 0x7F) + 548431104;
      ++*((_DWORD *)this + 9);
      v18 = *((_DWORD *)this + 8);
      if ( v18 == 4 )
      {
        *((_DWORD *)this + 8) = 0;
        v18 = 0;
      }
      v19 = (v6 & 0x7F) + 548430848;
    }
    else
    {
      if ( (v7 & 0xF0) != 0x30 )
      {
        switch ( v7 & 0xF0 )
        {
          case 128:
            v9 = ((v8 & 0xF) << 24) + ((v7 & 0xF) << 16) + ((v5 & 0x7F) << 8);
            v10 = (a2 >> 25) + 545259520;
            goto LABEL_26;
          case 144:
            v16 = a2 >> 25;
            if ( !v16 )
              v16 = 1;
            v14 = v16 + 546308096 + ((v8 & 0xF) << 24) + ((v7 & 0xF) << 16) + ((v5 & 0x7F) << 8);
            break;
          case 160:
            v9 = ((v8 & 0xF) << 24) + ((v7 & 0xF) << 16) + ((v5 & 0x7F) << 8);
            v10 = (a2 >> 25) + 547356672;
            goto LABEL_26;
          case 176:
            v9 = ((v8 & 0xF) << 24) + ((v7 & 0xF) << 16) + ((v5 & 0x7F) << 8);
            v10 = (a2 >> 25) + 548405248;
            goto LABEL_26;
          case 192:
            if ( (*((_BYTE *)this + 4) & 1) != 0 )
            {
              v12 = ((v8 & 0xF) << 24) + ((v7 & 0xF) << 16);
              *((_DWORD *)this + (*((_DWORD *)this + 8))++ + 3) = v12 + ((a2 >> 8) & 0x7F) + 548405248;
              ++*((_DWORD *)this + 9);
              v13 = *((_DWORD *)this + 8);
              if ( v13 == 4 )
              {
                *((_DWORD *)this + 8) = 0;
                v13 = 0;
              }
              *((_DWORD *)this + v13 + 3) = v12 + (a2 & 0x7F) + 548413440;
              ++*((_DWORD *)this + 9);
              if ( ++*((_DWORD *)this + 8) == 4 )
                *((_DWORD *)this + 8) = 0;
            }
            v14 = ((v7 & 0xF) << 16) + ((HIBYTE(a2) & 0x7F) << 8) + ((v8 & 0xF) << 24) + 549453824;
            break;
          case 208:
            v11 = (a2 >> 25 << 8) + ((v7 & 0xF) << 16) + ((v8 & 0xF) << 24) + 550502400;
            goto LABEL_27;
          case 224:
            v9 = ((v8 & 0xF) << 24) + ((v7 & 0xF) << 16) + (((a2 >> 18) & 0x7F) << 8);
            v10 = ((unsigned __int16)(a2 >> 18) >> 7) + 551550976;
LABEL_26:
            v11 = v9 + v10;
LABEL_27:
            *((_DWORD *)this + *((int *)this + 8) + 3) = v11;
            goto LABEL_66;
          default:
            return;
        }
        v15 = *((int *)this + 8);
        goto LABEL_36;
      }
      v17 = ((v7 & 0xF) << 16) + ((v8 & 0xF) << 24);
      *((_DWORD *)this + (*((_DWORD *)this + 8))++ + 3) = v17 + (v5 & 0x7F) + 548430592;
      ++*((_DWORD *)this + 9);
      v18 = *((_DWORD *)this + 8);
      if ( v18 == 4 )
      {
        *((_DWORD *)this + 8) = 0;
        v18 = 0;
      }
      v19 = (v6 & 0x7F) + 548430336;
    }
    *((_DWORD *)this + v18 + 3) = v17 + v19;
    ++*((_DWORD *)this + 8);
    ++*((_DWORD *)this + 9);
    v20 = *((_DWORD *)this + 8);
    if ( v20 == 4 )
    {
      *((_DWORD *)this + 8) = 0;
      v20 = 0;
    }
    *((_DWORD *)this + v20 + 3) = v17 + ((unsigned __int16)(a2 >> 18) >> 7) + 548406784;
    ++*((_DWORD *)this + 8);
    ++*((_DWORD *)this + 9);
    v21 = *((_DWORD *)this + 8);
    if ( v21 == 4 )
    {
      *((_DWORD *)this + 8) = 0;
      v21 = 0;
    }
    v14 = ((a2 >> 18) & 0x7F) + v17 + 548414976;
    v15 = v21;
LABEL_36:
    *((_DWORD *)this + v15 + 3) = v14;
    goto LABEL_66;
  }
  v25 = a2 >> 28;
  *(_BYTE *)this = a2 >> 28;
  if ( !(a2 >> 28) )
    return;
  if ( (unsigned __int8)v25 == 1 || (unsigned __int8)v25 == 2 )
  {
    *((_DWORD *)this + *((int *)this + 8) + 3) = a2;
LABEL_66:
    ++*((_DWORD *)this + 9);
    if ( ++*((_DWORD *)this + 8) == 4 )
      *((_DWORD *)this + 8) = 0;
    return;
  }
  if ( (unsigned __int8)v25 == 3 || (unsigned __int8)v25 == 4 )
  {
    *((_DWORD *)this + 1) = a2;
    goto LABEL_8;
  }
  if ( (unsigned int)(unsigned __int8)v25 - 6 >= 2 )
    goto LABEL_8;
}

```

## disassembly

```asm
0x18001098c  push    rbx
0x18001098e  push    rsi
0x18001098f  push    rdi
0x180010990  movzx   r10d, byte ptr [rcx+8]
0x180010995  xor     esi, esi
0x180010997  mov     r8, rcx
0x18001099a  mov     r9d, edx
0x18001099d  mov     ecx, r10d
0x1800109a0  test    r10d, r10d
0x1800109a3  jz      loc_180010DAB
0x1800109a9  sub     ecx, 1
0x1800109ac  jz      short loc_1800109E5
0x1800109ae  sub     ecx, 1
0x1800109b1  jz      short loc_1800109C5
0x1800109b3  cmp     ecx, 1
0x1800109b6  jnz     loc_180010E08
0x1800109bc  mov     [r8+8], sil
0x1800109c0  jmp     loc_180010E08
0x1800109c5  movzx   ecx, byte ptr [r8]
0x1800109c9  sub     ecx, 0Bh
0x1800109cc  jz      short loc_1800109D9
0x1800109ce  cmp     ecx, 1
0x1800109d1  jz      short loc_1800109D9
0x1800109d3  add     r10b, 1
0x1800109d7  jmp     short loc_1800109DC
0x1800109d9  mov     r10b, sil
0x1800109dc  mov     [r8+8], r10b
0x1800109e0  jmp     loc_180010E08
0x1800109e5  movzx   ecx, byte ptr [r8]
0x1800109e9  sub     ecx, 3
0x1800109ec  jz      loc_180010D75
0x1800109f2  sub     ecx, 1
0x1800109f5  jz      short loc_180010A08
0x1800109f7  sub     ecx, 4
0x1800109fa  jz      short loc_1800109BC
0x1800109fc  sub     ecx, 1
0x1800109ff  jz      short loc_1800109BC
0x180010a01  cmp     ecx, 1
0x180010a04  jz      short loc_1800109BC
0x180010a06  jmp     short loc_1800109D3
0x180010a08  mov     eax, [r8+4]
0x180010a0c  mov     r11d, [r8+4]
0x180010a10  movzx   ebx, byte ptr [r8+5]
0x180010a15  movzx   edi, byte ptr [r8+4]
0x180010a1a  shr     eax, 10h
0x180010a1d  movzx   r10d, al
0x180010a21  mov     ecx, r10d
0x180010a24  shr     r11d, 18h
0x180010a28  and     ecx, 0F0h
0x180010a2e  mov     [r8+8], sil
0x180010a32  sub     ecx, 20h ; ' '
0x180010a35  jz      loc_180010D1D
0x180010a3b  mov     eax, 10h
0x180010a40  sub     ecx, eax
0x180010a42  jz      loc_180010C59
0x180010a48  sub     ecx, 50h ; 'P'
0x180010a4b  jz      loc_180010C2B
0x180010a51  sub     ecx, eax
0x180010a53  jz      loc_180010BEB
0x180010a59  sub     ecx, eax
0x180010a5b  jz      loc_180010BBD
0x180010a61  sub     ecx, eax
0x180010a63  jz      loc_180010B8F
0x180010a69  sub     ecx, eax
0x180010a6b  jz      short loc_180010ADF
0x180010a6d  sub     ecx, eax
0x180010a6f  jz      short loc_180010AB8
0x180010a71  cmp     ecx, eax
0x180010a73  jnz     loc_180010E08
0x180010a79  shr     r9d, 12h
0x180010a7d  and     r10d, 0Fh
0x180010a81  movzx   ecx, r9w
0x180010a85  and     r11d, 0Fh
0x180010a89  mov     al, cl
0x180010a8b  shl     r10d, 10h
0x180010a8f  and     eax, 7Fh
0x180010a92  shl     r11d, 18h
0x180010a96  shl     eax, 8
0x180010a99  add     eax, r10d
0x180010a9c  shr     ecx, 7
0x180010a9f  add     eax, r11d
0x180010aa2  add     ecx, 20E00000h
0x180010aa8  add     ecx, eax
0x180010aaa  movsxd  rax, dword ptr [r8+20h]
0x180010aae  mov     [r8+rax*4+0Ch], ecx
0x180010ab3  jmp     loc_180010DF0
0x180010ab8  and     r10d, 0Fh
0x180010abc  shr     r9d, 19h
0x180010ac0  and     r11d, 0Fh
0x180010ac4  shl     r10d, 10h
0x180010ac8  shl     r11d, 18h
0x180010acc  shl     r9d, 8
0x180010ad0  add     r10d, r9d
0x180010ad3  lea     ecx, [r11+20D00000h]
0x180010ada  add     ecx, r10d
0x180010add  jmp     short loc_180010AAA
0x180010adf  mov     edx, 1
0x180010ae4  test    [r8+4], dl
0x180010ae8  jz      short loc_180010B58
0x180010aea  mov     eax, r11d
0x180010aed  mov     edi, r10d
0x180010af0  and     edi, 0Fh
0x180010af3  and     eax, 0Fh
0x180010af6  shl     eax, 18h
0x180010af9  mov     ecx, r9d
0x180010afc  shr     ecx, 8
0x180010aff  and     ecx, 7Fh
0x180010b02  shl     edi, 10h
0x180010b05  add     edi, eax
0x180010b07  add     ecx, 20B00000h
0x180010b0d  movsxd  rax, dword ptr [r8+20h]
0x180010b11  add     ecx, edi
0x180010b13  mov     [r8+rax*4+0Ch], ecx
0x180010b18  add     [r8+20h], edx
0x180010b1c  add     [r8+24h], edx
0x180010b20  mov     ebx, [r8+20h]
0x180010b24  cmp     ebx, 4
0x180010b27  jnz     short loc_180010B2F
0x180010b29  mov     [r8+20h], esi
0x180010b2d  mov     ebx, esi
0x180010b2f  mov     al, r9b
0x180010b32  and     eax, 7Fh
0x180010b35  lea     ecx, [rax+20B02000h]
0x180010b3b  movsxd  rax, ebx
0x180010b3e  add     ecx, edi
0x180010b40  mov     [r8+rax*4+0Ch], ecx
0x180010b45  add     [r8+24h], edx
0x180010b49  add     [r8+20h], edx
0x180010b4d  cmp     dword ptr [r8+20h], 4
0x180010b52  jnz     short loc_180010B58
0x180010b54  mov     [r8+20h], esi
0x180010b58  shr     r9d, 18h
0x180010b5c  and     r11d, 0Fh
0x180010b60  and     r9d, 7Fh
0x180010b64  shl     r11d, 18h
0x180010b68  and     r10d, 0Fh
0x180010b6c  shl     r9d, 8
0x180010b70  shl     r10d, 10h
0x180010b74  add     r9d, r10d
0x180010b77  lea     ecx, [r11+20C00000h]
0x180010b7e  add     ecx, r9d
0x180010b81  movsxd  rax, dword ptr [r8+20h]
0x180010b85  mov     [r8+rax*4+0Ch], ecx
0x180010b8a  jmp     loc_180010DF5
0x180010b8f  and     r10d, 0Fh
0x180010b93  and     r11d, 0Fh
0x180010b97  shl     r10d, 10h
0x180010b9b  mov     eax, ebx
0x180010b9d  and     eax, 7Fh
0x180010ba0  shl     r11d, 18h
0x180010ba4  shl     eax, 8
0x180010ba7  add     eax, r10d
0x180010baa  add     eax, r11d
0x180010bad  shr     r9d, 19h
0x180010bb1  lea     ecx, [r9+20B00000h]
0x180010bb8  jmp     loc_180010AA8
0x180010bbd  and     r10d, 0Fh
0x180010bc1  and     r11d, 0Fh
0x180010bc5  shl     r10d, 10h
0x180010bc9  mov     eax, ebx
0x180010bcb  and     eax, 7Fh
0x180010bce  shl     r11d, 18h
0x180010bd2  shl     eax, 8
0x180010bd5  add     eax, r10d
0x180010bd8  add     eax, r11d
0x180010bdb  shr     r9d, 19h
0x180010bdf  lea     ecx, [r9+20A00000h]
0x180010be6  jmp     loc_180010AA8
0x180010beb  shr     r9d, 19h
0x180010bef  mov     edx, 1
0x180010bf4  test    r9b, r9b
0x180010bf7  movzx   eax, r9b
0x180010bfb  mov     ecx, ebx
0x180010bfd  cmovz   eax, edx
0x180010c00  and     ecx, 7Fh
0x180010c03  shl     ecx, 8
0x180010c06  and     r10d, 0Fh
0x180010c0a  shl     r10d, 10h
0x180010c0e  and     r11d, 0Fh
0x180010c12  add     ecx, r10d
0x180010c15  shl     r11d, 18h
0x180010c19  movzx   eax, al
0x180010c1c  add     ecx, r11d
0x180010c1f  add     eax, 20900000h
0x180010c24  add     ecx, eax
0x180010c26  jmp     loc_180010B81
0x180010c2b  and     r10d, 0Fh
0x180010c2f  and     r11d, 0Fh
0x180010c33  shl     r10d, 10h
0x180010c37  mov     eax, ebx
0x180010c39  and     eax, 7Fh
0x180010c3c  shl     r11d, 18h
0x180010c40  shl     eax, 8
0x180010c43  add     eax, r10d
0x180010c46  add     eax, r11d
0x180010c49  shr     r9d, 19h
0x180010c4d  lea     ecx, [r9+20800000h]
0x180010c54  jmp     loc_180010AA8
0x180010c59  movsxd  rax, dword ptr [r8+20h]
0x180010c5d  and     r10d, 0Fh
0x180010c61  and     r11d, 0Fh
0x180010c65  shl     r10d, 10h
0x180010c69  shl     r11d, 18h
0x180010c6d  mov     edx, 1
0x180010c72  add     r11d, r10d
0x180010c75  mov     ecx, ebx
0x180010c77  and     ecx, 7Fh
0x180010c7a  add     ecx, 20B06300h
0x180010c80  add     ecx, r11d
0x180010c83  mov     [r8+rax*4+0Ch], ecx
0x180010c88  add     [r8+20h], edx
0x180010c8c  add     [r8+24h], edx
0x180010c90  mov     r10d, [r8+20h]
0x180010c94  cmp     r10d, 4
0x180010c98  jnz     short loc_180010CA1
0x180010c9a  mov     [r8+20h], esi
0x180010c9e  mov     r10d, esi
0x180010ca1  mov     ecx, edi
0x180010ca3  and     ecx, 7Fh
0x180010ca6  add     ecx, 20B06200h
0x180010cac  movsxd  rax, r10d
0x180010caf  add     ecx, r11d
0x180010cb2  mov     [r8+rax*4+0Ch], ecx
0x180010cb7  add     [r8+20h], edx
0x180010cbb  add     [r8+24h], edx
0x180010cbf  mov     r10d, [r8+20h]
0x180010cc3  cmp     r10d, 4
0x180010cc7  jnz     short loc_180010CD0
0x180010cc9  mov     [r8+20h], esi
0x180010ccd  mov     r10d, esi
0x180010cd0  shr     r9d, 12h
0x180010cd4  movzx   ebx, r9w
0x180010cd8  mov     ecx, ebx
0x180010cda  movsxd  rax, r10d
0x180010cdd  shr     ecx, 7
0x180010ce0  add     ecx, 20B00600h
0x180010ce6  add     ecx, r11d
0x180010ce9  mov     [r8+rax*4+0Ch], ecx
0x180010cee  add     [r8+20h], edx
0x180010cf2  add     [r8+24h], edx
0x180010cf6  mov     r9d, [r8+20h]
0x180010cfa  cmp     r9d, 4
0x180010cfe  jnz     short loc_180010D07
0x180010d00  mov     [r8+20h], esi
0x180010d04  mov     r9d, esi
0x180010d07  mov     al, bl
0x180010d09  lea     ecx, [r11+20B02600h]
0x180010d10  and     eax, 7Fh
0x180010d13  add     ecx, eax
0x180010d15  movsxd  rax, r9d
0x180010d18  jmp     loc_180010B85
0x180010d1d  movsxd  rax, dword ptr [r8+20h]
0x180010d21  and     r10d, 0Fh
0x180010d25  and     r11d, 0Fh
0x180010d29  shl     r10d, 10h
0x180010d2d  shl     r11d, 18h
0x180010d31  mov     edx, 1
0x180010d36  add     r11d, r10d
0x180010d39  mov     ecx, ebx
0x180010d3b  and     ecx, 7Fh
0x180010d3e  add     ecx, 20B06500h
0x180010d44  add     ecx, r11d
0x180010d47  mov     [r8+rax*4+0Ch], ecx
0x180010d4c  add     [r8+20h], edx
0x180010d50  add     [r8+24h], edx
0x180010d54  mov     r10d, [r8+20h]
0x180010d58  cmp     r10d, 4
0x180010d5c  jnz     short loc_180010D65
0x180010d5e  mov     [r8+20h], esi
0x180010d62  mov     r10d, esi
0x180010d65  mov     ecx, edi
0x180010d67  and     ecx, 7Fh
0x180010d6a  add     ecx, 20B06400h
0x180010d70  jmp     loc_180010CAC
0x180010d75  movsxd  rcx, dword ptr [r8+20h]
0x180010d79  mov     edx, 1
0x180010d7e  mov     eax, [r8+4]
0x180010d82  mov     [r8+8], sil
0x180010d86  mov     [r8+rcx*4+0Ch], eax
0x180010d8b  add     [r8+20h], edx
0x180010d8f  add     [r8+24h], edx
0x180010d93  mov     eax, [r8+20h]
0x180010d97  cmp     eax, 4
0x180010d9a  jnz     short loc_180010DA2
0x180010d9c  mov     [r8+20h], esi
0x180010da0  mov     eax, esi
0x180010da2  cdqe
0x180010da4  mov     [r8+rax*4+0Ch], r9d
0x180010da9  jmp     short loc_180010DF5
0x180010dab  mov     eax, r9d
0x180010dae  shr     eax, 1Ch
0x180010db1  movzx   ecx, al
0x180010db4  mov     [r8], cl
0x180010db7  test    al, al
0x180010db9  jz      short loc_180010E08
0x180010dbb  sub     ecx, 1
0x180010dbe  jz      short loc_180010DE7
0x180010dc0  sub     ecx, 1
0x180010dc3  jz      short loc_180010DE7
0x180010dc5  sub     ecx, 1
  ... truncated ...
```
