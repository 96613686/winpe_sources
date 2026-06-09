# Huffman::get(CInputBitStream *)

- ea: `0x18000af10`
- end: `0x18000b1b1`
- name: `?get@Huffman@@QEAAJPEAVCInputBitStream@@@Z`
- size: `673`
- prototype: `__int64 __fastcall(Huffman *__hidden this, struct CInputBitStream *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180009780`
- `0x180032950`
- `0x180033324`

## callees

- `0x18000af10`

## pseudocode

```c
__int64 __fastcall Huffman::get(Huffman *this, struct CInputBitStream *a2)
{
  __int64 v2; // rsi
  unsigned int v5; // edx
  int *v6; // r14
  unsigned int v7; // r10d
  __int64 v8; // r11
  unsigned int v9; // ebp
  int v10; // ebx
  _WORD *v11; // r11
  unsigned int v12; // ecx
  unsigned int v13; // r8d
  unsigned int v14; // r10d
  int v16; // ebx
  unsigned int v17; // r8d
  int v18; // ebx
  unsigned __int8 *v19; // rdx
  int v20; // ecx
  int v21; // ebx
  unsigned __int8 *v22; // rdx
  unsigned int v23; // ebp
  int v24; // ecx
  unsigned int v25; // r15d
  unsigned __int8 *v26; // rcx
  int v27; // ebx
  int v28; // edx
  unsigned int v29; // ebp
  int v30; // eax
  int v31; // eax
  unsigned int v32; // eax
  unsigned __int8 *v33; // rdx
  int v34; // ecx
  int v35; // eax

  v2 = *((_QWORD *)this + 5);
  v5 = 0;
  v6 = (int *)((char *)a2 + 8);
  while ( 1 )
  {
    v7 = *((_DWORD *)a2 + 4);
    v8 = *(unsigned int *)(*((_QWORD *)this + 6) + 16LL * v5);
    if ( (unsigned int)v8 > v7 )
    {
      v9 = *((_DWORD *)a2 + 3);
      v16 = v9;
      if ( *v6 < 2 )
      {
        v25 = *((_DWORD *)a2 + 4);
        if ( *v6 )
        {
          v25 = v7 + 8;
          v16 = **(unsigned __int8 **)a2 | (v9 << 8);
        }
        _mm_lfence();
        if ( v25 < (unsigned int)v8 )
          v10 = (*((_DWORD *)&GetMask + v25) & v16) << (v8 - v25);
        else
          v10 = *((_DWORD *)&GetMask + v8) & (v16 >> (v25 - v8));
      }
      else
      {
        v10 = *((_DWORD *)&GetMask + v8)
            & ((int)(*(unsigned __int8 *)(*(_QWORD *)a2 + 1LL) | ((**(unsigned __int8 **)a2 | (v9 << 8)) << 8)) >> (v7 - v8 + 16));
      }
    }
    else
    {
      _mm_lfence();
      v9 = *((_DWORD *)a2 + 3);
      v10 = *((_DWORD *)&GetMask + v8) & (v9 >> (v7 - v8));
    }
    v11 = (_WORD *)(v2 + 2LL * v10);
    v12 = (unsigned __int16)*v11;
    if ( (v12 & 0xF000) != 0 )
    {
      v13 = *((_DWORD *)a2 + 4);
      v14 = v12 >> 12;
      if ( v12 >> 12 > v13 )
      {
        v18 = *v6;
        if ( *v6 >= 2 )
        {
          *((_DWORD *)a2 + 3) <<= 16;
          v19 = *(unsigned __int8 **)a2;
          v20 = *((_DWORD *)a2 + 3) | *(unsigned __int8 *)(*(_QWORD *)a2 + 1LL);
          *((_DWORD *)a2 + 3) = v20;
          *((_DWORD *)a2 + 3) = v20 | (*v19 << 8);
          *((_DWORD *)a2 + 4) = v13 - v14 + 16;
          *(_QWORD *)a2 = v19 + 2;
          *v6 = v18 - 2;
          return *v11 & 0xFFF;
        }
        if ( v18 )
        {
          v33 = *(unsigned __int8 **)a2;
          do
          {
            v13 += 8;
            v34 = *((_DWORD *)a2 + 3) << 8;
            *((_DWORD *)a2 + 3) = v34;
            v35 = *v33++;
            *(_QWORD *)a2 = v33;
            --v18;
            *((_DWORD *)a2 + 3) = v35 | v34;
            *v6 = v18;
            *((_DWORD *)a2 + 4) = v13;
          }
          while ( v18 );
        }
        if ( v13 < v14 )
        {
          *((_DWORD *)a2 + 5) = 1;
          return *v11 & 0xFFF;
        }
      }
      *((_DWORD *)a2 + 4) = v13 - v14;
      return *v11 & 0xFFF;
    }
    if ( (v12 & 0xFFF) == 0xFFF )
      break;
    v17 = *(_DWORD *)(*((_QWORD *)this + 6) + 16LL * v5);
    if ( v17 > v7 )
    {
      v21 = *v6;
      if ( *v6 < 2 )
      {
        if ( v21 )
        {
          v26 = *(unsigned __int8 **)a2;
          v27 = v21 - 1;
          v28 = *((_DWORD *)a2 + 4);
          do
          {
            v29 = v9 << 8;
            v28 += 8;
            *((_DWORD *)a2 + 3) = v29;
            v30 = *v26++;
            v9 = v30 | v29;
            *v6 = v27;
            v31 = v27;
            *(_QWORD *)a2 = v26;
            --v27;
            *((_DWORD *)a2 + 3) = v9;
            *((_DWORD *)a2 + 4) = v28;
          }
          while ( v31 );
        }
        v32 = *((_DWORD *)a2 + 4);
        if ( v32 < v17 )
          *((_DWORD *)a2 + 5) = 1;
        else
          *((_DWORD *)a2 + 4) = v32 - v17;
      }
      else
      {
        v22 = *(unsigned __int8 **)a2;
        v23 = v9 << 16;
        *((_DWORD *)a2 + 3) = v23;
        v24 = v23 | v22[1];
        *((_DWORD *)a2 + 3) = v24;
        *((_DWORD *)a2 + 3) = v24 | (*v22 << 8);
        *((_DWORD *)a2 + 4) = v7 - v17 + 16;
        *(_QWORD *)a2 = v22 + 2;
        *v6 = v21 - 2;
      }
    }
    else
    {
      v6 = (int *)((char *)a2 + 8);
      *((_DWORD *)a2 + 4) = v7 - v17;
    }
    v5 = *v11 & 0xFFF;
    v2 = *(_QWORD *)(*((_QWORD *)this + 6) + 16LL * v5 + 8);
  }
  *((_DWORD *)a2 + 5) = 3;
  return 0;
}

```

## disassembly

```asm
0x18000af10  push    rbx
0x18000af12  push    rbp
0x18000af13  push    rsi
0x18000af14  push    rdi
0x18000af15  push    r12
0x18000af17  push    r13
0x18000af19  push    r14
0x18000af1b  mov     rsi, [rcx+28h]
0x18000af1f  mov     r9, rdx
0x18000af22  mov     rdi, rcx
0x18000af25  mov     [rsp+38h+arg_0], r15
0x18000af2a  xor     edx, edx
0x18000af2c  mov     r13d, 0F000h
0x18000af32  mov     r12d, 0FFFh
0x18000af38  lea     r14, [r9+8]
0x18000af3c  mov     rcx, [rdi+30h]
0x18000af40  lea     r8, ?GetMask@@3QBKB; ulong const near * const GetMask
0x18000af47  mov     r10d, [r9+10h]
0x18000af4b  mov     eax, edx
0x18000af4d  add     rax, rax
0x18000af50  mov     r11d, [rcx+rax*8]
0x18000af54  cmp     r11d, r10d
0x18000af57  ja      short loc_18000AFB1
0x18000af59  lfence
0x18000af5c  mov     ebp, [r9+0Ch]
0x18000af60  mov     ecx, r10d
0x18000af63  sub     ecx, r11d
0x18000af66  mov     ebx, ebp
0x18000af68  shr     ebx, cl
0x18000af6a  and     ebx, [r8+r11*4]
0x18000af6e  movsxd  rcx, ebx
0x18000af71  lea     r11, [rsi+rcx*2]
0x18000af75  movzx   ecx, word ptr [rsi+rcx*2]
0x18000af79  test    r13w, cx
0x18000af7d  jbe     short loc_18000AFE8
0x18000af7f  mov     r8d, [r9+10h]
0x18000af83  mov     r10d, ecx
0x18000af86  shr     r10d, 0Ch
0x18000af8a  cmp     r10d, r8d
0x18000af8d  ja      loc_18000B02A
0x18000af93  sub     r8d, r10d
0x18000af96  mov     [r9+10h], r8d
0x18000af9a  movzx   eax, word ptr [r11]
0x18000af9e  and     eax, r12d
0x18000afa1  mov     r15, [rsp+38h+arg_0]
0x18000afa6  pop     r14
0x18000afa8  pop     r13
0x18000afaa  pop     r12
0x18000afac  pop     rdi
0x18000afad  pop     rsi
0x18000afae  pop     rbp
0x18000afaf  pop     rbx
0x18000afb0  retn
0x18000afb1  mov     ecx, [r14]
0x18000afb4  mov     ebp, [r9+0Ch]
0x18000afb8  mov     ebx, ebp
0x18000afba  cmp     ecx, 2
0x18000afbd  jl      loc_18000B0BC
0x18000afc3  mov     rdx, [r9]
0x18000afc6  shl     ebx, 8
0x18000afc9  movzx   ecx, byte ptr [rdx]
0x18000afcc  or      ebx, ecx
0x18000afce  movzx   ecx, byte ptr [rdx+1]
0x18000afd2  shl     ebx, 8
0x18000afd5  or      ebx, ecx
0x18000afd7  mov     ecx, r10d
0x18000afda  sub     ecx, r11d
0x18000afdd  add     ecx, 10h
0x18000afe0  sar     ebx, cl
0x18000afe2  and     ebx, [r8+r11*4]
0x18000afe6  jmp     short loc_18000AF6E
0x18000afe8  and     cx, r12w
0x18000afec  cmp     cx, r12w
0x18000aff0  jz      loc_18000B15A
0x18000aff6  mov     rcx, [rdi+30h]
0x18000affa  mov     r8d, [rcx+rax*8]
0x18000affe  cmp     r8d, r10d
0x18000b001  ja      short loc_18000B073
0x18000b003  sub     r10d, r8d
0x18000b006  lea     r14, [r9+8]
0x18000b00a  mov     [r9+10h], r10d
0x18000b00e  movzx   eax, word ptr [r11]
0x18000b012  and     eax, r12d
0x18000b015  mov     ecx, eax
0x18000b017  mov     edx, eax
0x18000b019  add     rcx, rcx
0x18000b01c  mov     rax, [rdi+30h]
0x18000b020  mov     rsi, [rax+rcx*8+8]
0x18000b025  jmp     loc_18000AF3C
0x18000b02a  mov     ebx, [r14]
0x18000b02d  cmp     ebx, 2
0x18000b030  jl      loc_18000B169
0x18000b036  shl     dword ptr [r9+0Ch], 10h
0x18000b03b  sub     r8d, r10d
0x18000b03e  mov     rdx, [r9]
0x18000b041  movzx   ecx, byte ptr [rdx+1]
0x18000b045  or      ecx, [r9+0Ch]
0x18000b049  mov     [r9+0Ch], ecx
0x18000b04d  movzx   eax, byte ptr [rdx]
0x18000b050  shl     eax, 8
0x18000b053  or      eax, ecx
0x18000b055  mov     [r9+0Ch], eax
0x18000b059  add     r8d, 10h
0x18000b05d  lea     rax, [rdx+2]
0x18000b061  mov     [r9+10h], r8d
0x18000b065  mov     [r9], rax
0x18000b068  lea     eax, [rbx-2]
0x18000b06b  mov     [r14], eax
0x18000b06e  jmp     loc_18000AF9A
0x18000b073  mov     ebx, [r14]
0x18000b076  cmp     ebx, 2
0x18000b079  jl      loc_18000B103
0x18000b07f  mov     rdx, [r9]
0x18000b082  sub     r10d, r8d
0x18000b085  shl     ebp, 10h
0x18000b088  mov     [r9+0Ch], ebp
0x18000b08c  movzx   ecx, byte ptr [rdx+1]
0x18000b090  or      ecx, ebp
0x18000b092  mov     [r9+0Ch], ecx
0x18000b096  movzx   eax, byte ptr [rdx]
0x18000b099  shl     eax, 8
0x18000b09c  or      eax, ecx
0x18000b09e  mov     [r9+0Ch], eax
0x18000b0a2  add     r10d, 10h
0x18000b0a6  lea     rax, [rdx+2]
0x18000b0aa  mov     [r9+10h], r10d
0x18000b0ae  mov     [r9], rax
0x18000b0b1  lea     eax, [rbx-2]
0x18000b0b4  mov     [r14], eax
0x18000b0b7  jmp     loc_18000B00E
0x18000b0bc  mov     r15d, r10d
0x18000b0bf  test    ecx, ecx
0x18000b0c1  jnz     short loc_18000B0F2
0x18000b0c3  lfence
0x18000b0c6  cmp     r15d, r11d
0x18000b0c9  jb      short loc_18000B0DD
0x18000b0cb  sub     r15d, r11d
0x18000b0ce  movzx   ecx, r15b
0x18000b0d2  sar     ebx, cl
0x18000b0d4  and     ebx, [r8+r11*4]
0x18000b0d8  jmp     loc_18000AF6E
0x18000b0dd  sub     r11d, r15d
0x18000b0e0  mov     edx, r15d
0x18000b0e3  movzx   ecx, r11b
0x18000b0e7  and     ebx, [r8+rdx*4]
0x18000b0eb  shl     ebx, cl
0x18000b0ed  jmp     loc_18000AF6E
0x18000b0f2  mov     rcx, [r9]
0x18000b0f5  lea     r15d, [r10+8]
0x18000b0f9  shl     ebx, 8
0x18000b0fc  movzx   edx, byte ptr [rcx]
0x18000b0ff  or      ebx, edx
0x18000b101  jmp     short loc_18000B0C3
0x18000b103  test    ebx, ebx
0x18000b105  jz      short loc_18000B138
0x18000b107  mov     rcx, [r9]
0x18000b10a  dec     ebx
0x18000b10c  mov     edx, [r9+10h]
0x18000b110  shl     ebp, 8
0x18000b113  add     edx, 8
0x18000b116  mov     [r9+0Ch], ebp
0x18000b11a  movzx   eax, byte ptr [rcx]
0x18000b11d  inc     rcx
0x18000b120  or      ebp, eax
0x18000b122  mov     [r14], ebx
0x18000b125  mov     eax, ebx
0x18000b127  mov     [r9], rcx
0x18000b12a  dec     ebx
0x18000b12c  mov     [r9+0Ch], ebp
0x18000b130  mov     [r9+10h], edx
0x18000b134  test    eax, eax
0x18000b136  jnz     short loc_18000B110
0x18000b138  mov     eax, [r9+10h]
0x18000b13c  cmp     eax, r8d
0x18000b13f  jb      short loc_18000B14D
0x18000b141  sub     eax, r8d
0x18000b144  mov     [r9+10h], eax
0x18000b148  jmp     loc_18000B00E
0x18000b14d  mov     dword ptr [r9+14h], 1
0x18000b155  jmp     loc_18000B00E
0x18000b15a  mov     dword ptr [r9+14h], 3
0x18000b162  xor     eax, eax
0x18000b164  jmp     loc_18000AFA1
0x18000b169  test    ebx, ebx
0x18000b16b  jz      short loc_18000B19B
0x18000b16d  mov     rdx, [r9]
0x18000b170  mov     ecx, [r9+0Ch]
0x18000b174  add     r8d, 8
0x18000b178  shl     ecx, 8
0x18000b17b  mov     [r9+0Ch], ecx
0x18000b17f  movzx   eax, byte ptr [rdx]
0x18000b182  inc     rdx
0x18000b185  or      ecx, eax
0x18000b187  mov     [r9], rdx
0x18000b18a  dec     ebx
0x18000b18c  mov     [r9+0Ch], ecx
0x18000b190  mov     [r14], ebx
0x18000b193  mov     [r9+10h], r8d
0x18000b197  test    ebx, ebx
0x18000b199  jnz     short loc_18000B170
0x18000b19b  cmp     r8d, r10d
0x18000b19e  jnb     loc_18000AF93
0x18000b1a4  mov     dword ptr [r9+14h], 1
0x18000b1ac  jmp     loc_18000AF9A
```
