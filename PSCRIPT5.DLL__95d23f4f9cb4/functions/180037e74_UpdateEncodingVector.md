# UpdateEncodingVector

- ea: `0x180037e74`
- end: `0x1800380ce`
- name: `UpdateEncodingVector`
- size: `602`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18003cfc0`
- `0x180044be0`

## callees

- `0x180001ee0`
- `0x1800055e0`
- `0x180036ffc`
- `0x180037e74`
- `0x18003858c`
- `0x180038968`

## pseudocode

```c
__int64 __fastcall UpdateEncodingVector(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // r12d
  __int64 v7; // rsi
  unsigned __int16 v8; // ax
  __int64 v9; // r9
  _BYTE *v10; // rdx
  __int16 v11; // ax
  __int64 v12; // r8
  unsigned __int16 v13; // r9
  int v14; // edi
  __int64 v15; // rcx
  unsigned int v16; // ecx
  __int64 v17; // r9
  __int64 v18; // rax
  int v19; // r9d
  __int64 v20; // r9
  __int64 v21; // r8
  __int64 v22; // r8
  __int16 v23; // ax
  __int64 v24; // r8
  unsigned int v25; // r8d
  _BYTE *v27; // [rsp+30h] [rbp-58h] BYREF
  char pszDest[16]; // [rsp+38h] [rbp-50h] BYREF

  v4 = a4;
  if ( (int)a4 <= *(_DWORD *)a2 && (int)a4 > 0 )
  {
    LOBYTE(a4) = 1;
    v7 = *(_QWORD *)(a1[5] + 168LL);
    v8 = StrmPutBytes(v7, "/", 1, a4);
    if ( v8 )
      return v8;
    v10 = (_BYTE *)a1[7];
    v11 = 5;
    if ( v10 )
    {
      if ( !*v10 )
      {
        v13 = 0;
LABEL_10:
        if ( !v13 )
          v13 = StrmPutStringEOL(v7, " findfont /Encoding get");
        v14 = 0;
LABEL_38:
        if ( v13 )
          return v13;
        while ( v14 < v4 )
        {
          if ( *(_BYTE *)a1[5] )
          {
            v15 = *(_QWORD *)(a2 + 16);
            if ( v15 )
            {
              v16 = *(unsigned __int16 *)(v15 + 2LL * v14);
              if ( (*(_BYTE *)(((unsigned __int64)v16 >> 3) + a1[10]) & (unsigned __int8)(1 << (v16 & 7))) != 0 )
                goto LABEL_37;
            }
          }
          v17 = *(_QWORD *)(a2 + 8);
          v27 = 0;
          FindGlyphName((_DWORD)a1, a2, v14, *(unsigned __int16 *)(v17 + 4LL * v14), (__int64)&v27);
          v18 = *(_QWORD *)(a2 + 16);
          if ( v18 )
            v19 = *(unsigned __int16 *)(v18 + 2LL * v14);
          else
            v19 = v14;
          StringCchPrintfA(pszDest, 0x10u, "dup %d /", v19);
          if ( pszDest[0] )
          {
            v21 = -1;
            do
              ++v21;
            while ( pszDest[v21] );
            LOBYTE(v20) = 1;
            v8 = StrmPutBytes(v7, pszDest, v21, v20);
            if ( v8 )
              return v8;
          }
          if ( v27 )
          {
            if ( *v27 )
            {
              v22 = -1;
              do
                ++v22;
              while ( v27[v22] );
              LOBYTE(v20) = 1;
              v23 = StrmPutBytes(v7, v27, v22, v20);
            }
            else
            {
              v23 = 0;
            }
          }
          else
          {
            v23 = 5;
          }
          if ( v23 )
          {
            v13 = v23;
LABEL_37:
            ++v14;
            goto LABEL_38;
          }
          v13 = StrmPutStringEOL(v7, " put");
          if ( v13 )
            goto LABEL_37;
          v24 = *(_QWORD *)(a2 + 16);
          if ( !v24 )
            goto LABEL_37;
          v25 = *(unsigned __int16 *)(v24 + 2LL * v14);
          *(_BYTE *)(((unsigned __int64)v25 >> 3) + a1[10]) |= 1 << (v25 & 7);
          ++v14;
        }
        return (unsigned __int16)StrmPutStringEOL(v7, "pop");
      }
      v12 = -1;
      do
        ++v12;
      while ( v10[v12] );
      LOBYTE(v9) = 1;
      v11 = StrmPutBytes(v7, v10, v12, v9);
    }
    v13 = v11;
    goto LABEL_10;
  }
  return 1;
}

```

## disassembly

```asm
0x180037e74  mov     [rsp+arg_10], rbx
0x180037e79  push    rbp
0x180037e7a  push    rsi
0x180037e7b  push    rdi
0x180037e7c  push    r12
0x180037e7e  push    r13
0x180037e80  push    r14
0x180037e82  push    r15
0x180037e84  sub     rsp, 50h
0x180037e88  mov     rax, cs:__security_cookie
0x180037e8f  xor     rax, rsp
0x180037e92  mov     [rsp+88h+var_40], rax
0x180037e97  mov     r12d, r9d
0x180037e9a  mov     r14, rdx
0x180037e9d  mov     rbp, rcx
0x180037ea0  cmp     r9d, [rdx]
0x180037ea3  jg      loc_1800380A4
0x180037ea9  xor     r13d, r13d
0x180037eac  test    r9d, r9d
0x180037eaf  jle     loc_1800380A4
0x180037eb5  mov     rax, [rcx+28h]
0x180037eb9  lea     ebx, [r13+1]
0x180037ebd  mov     r9b, bl
0x180037ec0  lea     rdx, asc_1800647FC; "/"
0x180037ec7  mov     r8d, ebx
0x180037eca  mov     rsi, [rax+0A8h]
0x180037ed1  mov     rcx, rsi
0x180037ed4  call    StrmPutBytes
0x180037ed9  cmp     r13w, ax
0x180037edd  jnz     loc_18003809A
0x180037ee3  mov     rdx, [rbp+38h]
0x180037ee7  lea     eax, [rbx+4]
0x180037eea  test    rdx, rdx
0x180037eed  jz      short loc_180037F0C
0x180037eef  cmp     [rdx], r13b
0x180037ef2  jz      short loc_180037F31
0x180037ef4  or      r8, 0FFFFFFFFFFFFFFFFh
0x180037ef8  inc     r8
0x180037efb  cmp     [rdx+r8], r13b
0x180037eff  jnz     short loc_180037EF8
0x180037f01  mov     r9b, bl
0x180037f04  mov     rcx, rsi
0x180037f07  call    StrmPutBytes
0x180037f0c  movzx   r9d, ax
0x180037f10  cmp     r13w, r9w
0x180037f14  jnz     short loc_180037F29
0x180037f16  lea     rdx, aFindfontEncodi; " findfont /Encoding get"
0x180037f1d  mov     rcx, rsi
0x180037f20  call    StrmPutStringEOL
0x180037f25  movzx   r9d, ax
0x180037f29  mov     edi, r13d
0x180037f2c  jmp     loc_18003807F
0x180037f31  mov     r9d, r13d
0x180037f34  jmp     short loc_180037F10
0x180037f36  cmp     edi, r12d
0x180037f39  jge     loc_18003808B
0x180037f3f  mov     rax, [rbp+28h]
0x180037f43  cmp     [rax], r13b
0x180037f46  jz      short loc_180037F76
0x180037f48  mov     rcx, [r14+10h]
0x180037f4c  test    rcx, rcx
0x180037f4f  jz      short loc_180037F76
0x180037f51  movsxd  rax, edi
0x180037f54  movzx   ecx, word ptr [rcx+rax*2]
0x180037f58  mov     rax, [rbp+50h]
0x180037f5c  mov     edx, ecx
0x180037f5e  shr     rdx, 3
0x180037f62  and     ecx, 7
0x180037f65  mov     r8b, [rdx+rax]
0x180037f69  mov     eax, ebx
0x180037f6b  shl     eax, cl
0x180037f6d  test    al, r8b
0x180037f70  jnz     loc_18003807D
0x180037f76  mov     r9, [r14+8]
0x180037f7a  lea     rax, [rsp+88h+var_58]
0x180037f7f  movsxd  r15, edi
0x180037f82  mov     r8d, edi
0x180037f85  mov     rdx, r14
0x180037f88  mov     [rsp+88h+var_58], r13
0x180037f8d  mov     rcx, rbp
0x180037f90  mov     [rsp+88h+var_68], rax
0x180037f95  movzx   r9d, word ptr [r9+r15*4]
0x180037f9a  call    FindGlyphName
0x180037f9f  mov     rax, [r14+10h]
0x180037fa3  test    rax, rax
0x180037fa6  jz      short loc_180037FAF
0x180037fa8  movzx   r9d, word ptr [rax+r15*2]
0x180037fad  jmp     short loc_180037FB2
0x180037faf  mov     r9d, edi
0x180037fb2  lea     r8, aDupD; "dup %d /"
0x180037fb9  mov     edx, 10h; cchDest
0x180037fbe  lea     rcx, [rsp+88h+pszDest]; pszDest
0x180037fc3  call    StringCchPrintfA
0x180037fc8  cmp     [rsp+88h+pszDest], r13b
0x180037fcd  jz      short loc_180037FFA
0x180037fcf  lea     rax, [rsp+88h+pszDest]
0x180037fd4  or      r8, 0FFFFFFFFFFFFFFFFh
0x180037fd8  inc     r8
0x180037fdb  cmp     [rax+r8], r13b
0x180037fdf  jnz     short loc_180037FD8
0x180037fe1  mov     r9b, bl
0x180037fe4  lea     rdx, [rsp+88h+pszDest]
0x180037fe9  mov     rcx, rsi
0x180037fec  call    StrmPutBytes
0x180037ff1  test    ax, ax
0x180037ff4  jnz     loc_18003809A
0x180037ffa  mov     rdx, [rsp+88h+var_58]
0x180037fff  test    rdx, rdx
0x180038002  jz      short loc_180038028
0x180038004  cmp     [rdx], r13b
0x180038007  jz      short loc_180038023
0x180038009  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003800d  inc     r8
0x180038010  cmp     [rdx+r8], r13b
0x180038014  jnz     short loc_18003800D
0x180038016  mov     r9b, bl
0x180038019  mov     rcx, rsi
0x18003801c  call    StrmPutBytes
0x180038021  jmp     short loc_18003802D
0x180038023  mov     eax, r13d
0x180038026  jmp     short loc_18003802D
0x180038028  mov     eax, 5
0x18003802d  test    ax, ax
0x180038030  jnz     short loc_180038079
0x180038032  lea     rdx, aPut_1; " put"
0x180038039  mov     rcx, rsi
0x18003803c  call    StrmPutStringEOL
0x180038041  movzx   r9d, ax
0x180038045  test    ax, ax
0x180038048  jnz     short loc_18003807D
0x18003804a  mov     r8, [r14+10h]
0x18003804e  test    r8, r8
0x180038051  jz      short loc_18003807D
0x180038053  movzx   r8d, word ptr [r8+r15*2]
0x180038058  mov     rcx, [rbp+50h]
0x18003805c  mov     edx, r8d
0x18003805f  shr     rdx, 3
0x180038063  and     r8d, 7
0x180038067  movzx   eax, byte ptr [rdx+rcx]
0x18003806b  bts     eax, r8d
0x18003806f  mov     [rdx+rcx], al
0x180038072  add     edi, ebx
0x180038074  jmp     loc_180037F36
0x180038079  movzx   r9d, ax
0x18003807d  add     edi, ebx
0x18003807f  test    r9w, r9w
0x180038083  jz      loc_180037F36
0x180038089  jmp     short loc_18003809E
0x18003808b  lea     rdx, aPop_0; "pop"
0x180038092  mov     rcx, rsi
0x180038095  call    StrmPutStringEOL
0x18003809a  movzx   r9d, ax
0x18003809e  movzx   eax, r9w
0x1800380a2  jmp     short loc_1800380A9
0x1800380a4  mov     eax, 1
0x1800380a9  mov     rcx, [rsp+88h+var_40]
0x1800380ae  xor     rcx, rsp; StackCookie
0x1800380b1  call    __security_check_cookie
0x1800380b6  mov     rbx, [rsp+88h+arg_10]
0x1800380be  add     rsp, 50h
0x1800380c2  pop     r15
0x1800380c4  pop     r14
0x1800380c6  pop     r13
0x1800380c8  pop     r12
0x1800380ca  pop     rdi
0x1800380cb  pop     rsi
0x1800380cc  pop     rbp
0x1800380cd  retn
```
