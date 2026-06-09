# CLongBlock_Read

- ea: `0x18007f350`
- end: `0x18007f6a2`
- name: `CLongBlock_Read`
- size: `850`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18007d4e0`

## callees

- `0x1800363f0`
- `0x180075a20`
- `0x18007edc0`
- `0x18007f350`
- `0x18007f9e0`
- `0x180080100`
- `0x180080800`

## pseudocode

```c
__int64 __fastcall CLongBlock_Read(int *a1, __int64 a2, unsigned __int8 a3)
{
  __int64 v3; // r14
  int *v4; // rbx
  __int64 v5; // rsi
  int v6; // edi
  __int64 v7; // rdx
  unsigned int v8; // r12d
  int v9; // esi
  char v10; // bp
  unsigned int v11; // ecx
  int i; // eax
  int v13; // ecx
  __int64 v14; // rax
  __int64 v15; // r15
  int v16; // r13d
  int v17; // ebp
  unsigned int v18; // edi
  int v19; // ecx
  __int16 v20; // ax
  __int64 result; // rax
  unsigned int v22; // edi
  int v23; // ecx
  __int64 v24; // [rsp+30h] [rbp-48h]
  unsigned __int8 v26; // [rsp+90h] [rbp+18h]
  int v27; // [rsp+98h] [rbp+20h]

  v26 = a3;
  v3 = *(_QWORD *)(a2 + 8);
  v4 = a1;
  LOBYTE(a1) = *(_BYTE *)(a2 + 28);
  v5 = a2;
  v6 = 0;
  v7 = v3;
  v24 = v3;
  v8 = 4;
  if ( (char)a1 <= 0 )
  {
LABEL_16:
    if ( v6 < *(char *)(v5 + 30) )
    {
      do
      {
        v14 = v6++;
        *(_BYTE *)(v14 + v3) = 0;
      }
      while ( v6 < *(char *)(v5 + 30) );
      v7 = *(_QWORD *)(v5 + 8);
      LOBYTE(a1) = *(_BYTE *)(v5 + 28);
      v24 = v7;
    }
    v15 = *(_QWORD *)v5;
    v16 = 0;
    v17 = 0;
    v27 = a3;
    if ( (char)a1 <= 0 )
    {
LABEL_39:
      CPulseData_Read(v4, v5 + 915);
      if ( !*v4 )
        FillBitCache(v4, 1u);
      *(_BYTE *)(v5 + 42) = ((unsigned int)v4[1] >> --*v4) & 1;
      result = CTns_Read(v4, v5);
      if ( !(_DWORD)result )
      {
        if ( !*v4 )
          FillBitCache(v4, 1u);
        if ( (((unsigned int)v4[1] >> --*v4) & 1) == 0 )
          return CLongBlock_ReadSpectralData(v4, (__int64 *)v5);
        result = CGC_Read(v4, v5);
        if ( !(_DWORD)result )
          return CLongBlock_ReadSpectralData(v4, (__int64 *)v5);
      }
      return result;
    }
    while ( *(_BYTE *)(v17 + v7) )
    {
      if ( *(_BYTE *)(v17 + v7) != 13 )
      {
        if ( (unsigned int)(*(char *)(v17 + v7) - 14) < 2 )
        {
          v22 = 0;
          do
          {
            if ( (unsigned int)*v4 < 4 )
              FillBitCache(v4, 4u);
            v23 = *v4 - 4;
            v22 = *((unsigned __int16 *)qword_1800A1E70 + v22 + (((unsigned int)v4[1] >> (*(_BYTE *)v4 - 4)) & 0xF));
            *v4 = v23;
          }
          while ( (v22 & 8) == 0 );
          v5 = a2;
          v7 = v24;
          a3 = v26;
          *v4 = v23 + (v22 & 3);
          v16 += (v22 >> 4) - 60;
          v20 = v16 - 100;
        }
        else
        {
          v18 = 0;
          do
          {
            if ( (unsigned int)*v4 < 4 )
              FillBitCache(v4, 4u);
            v19 = *v4 - 4;
            v18 = *((unsigned __int16 *)qword_1800A1E70 + v18 + (((unsigned int)v4[1] >> (*(_BYTE *)v4 - 4)) & 0xF));
            *v4 = v19;
          }
          while ( (v18 & 8) == 0 );
          v5 = a2;
          a3 = v26;
          *v4 = v19 + (v18 & 3);
          v27 = (v18 >> 4) + v27 - 60;
          v20 = v27 - 100;
          v7 = v24;
        }
        goto LABEL_37;
      }
      CPns_Read(v5, (_DWORD)v4, (unsigned int)&qword_18008B6D0, a3, v17, 0);
      v7 = v24;
      a3 = v26;
LABEL_38:
      if ( ++v17 >= *(char *)(v5 + 28) )
        goto LABEL_39;
    }
    v20 = 0;
LABEL_37:
    *(_WORD *)(v15 + 2LL * v17) = v20;
    goto LABEL_38;
  }
  while ( 1 )
  {
    v9 = 0;
    if ( (unsigned int)*v4 < 4 )
      FillBitCache(v4, 4u);
    *v4 -= 4;
    v10 = ((unsigned int)v4[1] >> *v4) & 0xF;
    if ( (unsigned int)*v4 < 5 )
      FillBitCache(v4, 5u);
    *v4 -= 5;
    v11 = *v4;
    for ( i = ((unsigned int)v4[1] >> *v4) & 0x1F; i == 31; i = ((unsigned int)v4[1] >> *v4) & 0x1F )
    {
      v9 += 31;
      if ( v11 < 5 )
        FillBitCache(v4, 5u);
      *v4 -= 5;
      v11 = *v4;
    }
    v13 = v6 + i + v9;
    if ( v13 > 64 )
      return 3;
    if ( v6 < v13 )
      break;
LABEL_14:
    v5 = a2;
    LODWORD(a1) = *(char *)(a2 + 28);
    if ( v6 >= (int)a1 )
    {
      v7 = *(_QWORD *)(a2 + 8);
      a3 = v26;
      v24 = v7;
      goto LABEL_16;
    }
  }
  while ( 1 )
  {
    *(_BYTE *)(v6 + v3) = v10;
    if ( v10 == 12 )
      return v8;
    if ( ++v6 >= v13 )
      goto LABEL_14;
  }
}

```

## disassembly

```asm
0x18007f350  mov     [rsp+arg_10], r8b
0x18007f355  mov     [rsp+arg_8], rdx
0x18007f35a  push    rbx
0x18007f35b  push    rbp
0x18007f35c  push    rsi
0x18007f35d  push    rdi
0x18007f35e  push    r12
0x18007f360  push    r14
0x18007f362  sub     rsp, 48h
0x18007f366  mov     r14, [rdx+8]
0x18007f36a  mov     rbx, rcx
0x18007f36d  movzx   ecx, byte ptr [rdx+1Ch]
0x18007f371  mov     rsi, rdx
0x18007f374  xor     edi, edi
0x18007f376  mov     rdx, r14
0x18007f379  mov     [rsp+78h+var_48], rdx
0x18007f37e  mov     r12d, 4
0x18007f384  test    cl, cl
0x18007f386  jle     loc_18007F44D
0x18007f38c  nop     dword ptr [rax+00h]
0x18007f390  xor     esi, esi
0x18007f392  cmp     [rbx], r12d
0x18007f395  jnb     short loc_18007F3A2
0x18007f397  mov     edx, r12d
0x18007f39a  mov     rcx, rbx
0x18007f39d  call    FillBitCache
0x18007f3a2  add     dword ptr [rbx], 0FFFFFFFCh
0x18007f3a5  mov     ecx, [rbx]
0x18007f3a7  mov     ebp, [rbx+4]
0x18007f3aa  shr     ebp, cl
0x18007f3ac  and     bpl, 0Fh
0x18007f3b0  cmp     ecx, 5
0x18007f3b3  jnb     short loc_18007F3C2
0x18007f3b5  mov     edx, 5
0x18007f3ba  mov     rcx, rbx
0x18007f3bd  call    FillBitCache
0x18007f3c2  add     dword ptr [rbx], 0FFFFFFFBh
0x18007f3c5  mov     eax, [rbx+4]
0x18007f3c8  mov     ecx, [rbx]
0x18007f3ca  shr     eax, cl
0x18007f3cc  and     eax, 1Fh
0x18007f3cf  cmp     eax, 1Fh
0x18007f3d2  jnz     short loc_18007F3FB
0x18007f3d4  add     esi, 1Fh
0x18007f3d7  cmp     ecx, 5
0x18007f3da  jnb     short loc_18007F3E9
0x18007f3dc  mov     edx, 5
0x18007f3e1  mov     rcx, rbx
0x18007f3e4  call    FillBitCache
0x18007f3e9  add     dword ptr [rbx], 0FFFFFFFBh
0x18007f3ec  mov     eax, [rbx+4]
0x18007f3ef  mov     ecx, [rbx]
0x18007f3f1  shr     eax, cl
0x18007f3f3  and     eax, 1Fh
0x18007f3f6  cmp     eax, 1Fh
0x18007f3f9  jz      short loc_18007F3D4
0x18007f3fb  lea     ecx, [rax+rsi]
0x18007f3fe  add     ecx, edi
0x18007f400  cmp     ecx, 40h ; '@'
0x18007f403  jg      loc_18007F54C
0x18007f409  cmp     edi, ecx
0x18007f40b  jge     short loc_18007F427
0x18007f40d  nop     dword ptr [rax]
0x18007f410  movsxd  rax, edi
0x18007f413  mov     [rax+r14], bpl
0x18007f417  cmp     bpl, 0Ch
0x18007f41b  jz      loc_18007F552
0x18007f421  inc     edi
0x18007f423  cmp     edi, ecx
0x18007f425  jl      short loc_18007F410
0x18007f427  mov     rsi, [rsp+78h+arg_8]
0x18007f42f  movsx   ecx, byte ptr [rsi+1Ch]
0x18007f433  cmp     edi, ecx
0x18007f435  jl      loc_18007F390
0x18007f43b  mov     rdx, [rsi+8]
0x18007f43f  movzx   r8d, [rsp+78h+arg_10]
0x18007f448  mov     [rsp+78h+var_48], rdx
0x18007f44d  movsx   eax, byte ptr [rsi+1Eh]
0x18007f451  mov     [rsp+78h+arg_0], r13
0x18007f459  mov     [rsp+78h+var_38], r15
0x18007f45e  cmp     edi, eax
0x18007f460  jge     short loc_18007F48F
0x18007f462  nop     dword ptr [rax+00h]
0x18007f466  nop     word ptr [rax+rax+00000000h]
0x18007f470  movsxd  rax, edi
0x18007f473  inc     edi
0x18007f475  mov     byte ptr [rax+r14], 0
0x18007f47a  movsx   eax, byte ptr [rsi+1Eh]
0x18007f47e  cmp     edi, eax
0x18007f480  jl      short loc_18007F470
0x18007f482  mov     rdx, [rsi+8]
0x18007f486  movzx   ecx, byte ptr [rsi+1Ch]
0x18007f48a  mov     [rsp+78h+var_48], rdx
0x18007f48f  mov     r15, [rsi]
0x18007f492  xor     r13d, r13d
0x18007f495  xor     ebp, ebp
0x18007f497  movzx   eax, r8b
0x18007f49b  mov     [rsp+78h+arg_18], eax
0x18007f4a2  test    cl, cl
0x18007f4a4  jle     loc_18007F610
0x18007f4aa  nop     word ptr [rax+rax+00h]
0x18007f4b0  movsxd  r14, ebp
0x18007f4b3  movsx   ecx, byte ptr [r14+rdx]
0x18007f4b8  test    ecx, ecx
0x18007f4ba  jz      loc_18007F5FB
0x18007f4c0  sub     ecx, 0Dh
0x18007f4c3  jz      loc_18007F5C9
0x18007f4c9  sub     ecx, 1
0x18007f4cc  jz      loc_18007F563
0x18007f4d2  cmp     ecx, 1
0x18007f4d5  jz      loc_18007F563
0x18007f4db  mov     rsi, cs:off_18008B6D8
0x18007f4e2  xor     edi, edi
0x18007f4e4  cmp     [rbx], r12d
0x18007f4e7  jnb     short loc_18007F4F4
0x18007f4e9  mov     edx, r12d
0x18007f4ec  mov     rcx, rbx
0x18007f4ef  call    FillBitCache
0x18007f4f4  mov     ecx, [rbx]
0x18007f4f6  mov     eax, [rbx+4]
0x18007f4f9  add     ecx, 0FFFFFFFCh
0x18007f4fc  shr     eax, cl
0x18007f4fe  and     eax, 0Fh
0x18007f501  add     eax, edi
0x18007f503  movzx   edi, word ptr [rsi+rax*2]
0x18007f507  mov     [rbx], ecx
0x18007f509  test    dil, 8
0x18007f50d  jz      short loc_18007F4E4
0x18007f50f  mov     edx, [rsp+78h+arg_18]
0x18007f516  mov     eax, edi
0x18007f518  mov     rsi, [rsp+78h+arg_8]
0x18007f520  and     eax, 3
0x18007f523  movzx   r8d, [rsp+78h+arg_10]
0x18007f52c  add     eax, ecx
0x18007f52e  add     edx, 0FFFFFFC4h
0x18007f531  shr     edi, 4
0x18007f534  add     edx, edi
0x18007f536  mov     [rbx], eax
0x18007f538  mov     [rsp+78h+arg_18], edx
0x18007f53f  lea     eax, [rdx-64h]
0x18007f542  mov     rdx, [rsp+78h+var_48]
0x18007f547  jmp     loc_18007F5FD
0x18007f54c  mov     r12d, 3
0x18007f552  mov     eax, r12d
0x18007f555  add     rsp, 48h
0x18007f559  pop     r14
0x18007f55b  pop     r12
0x18007f55d  pop     rdi
0x18007f55e  pop     rsi
0x18007f55f  pop     rbp
0x18007f560  pop     rbx
0x18007f561  retn
0x18007f563  mov     rsi, cs:off_18008B6D8
0x18007f56a  xor     edi, edi
0x18007f56c  nop     dword ptr [rax+00h]
0x18007f570  cmp     [rbx], r12d
0x18007f573  jnb     short loc_18007F580
0x18007f575  mov     edx, r12d
0x18007f578  mov     rcx, rbx
0x18007f57b  call    FillBitCache
0x18007f580  mov     ecx, [rbx]
0x18007f582  mov     eax, [rbx+4]
0x18007f585  add     ecx, 0FFFFFFFCh
0x18007f588  shr     eax, cl
0x18007f58a  and     eax, 0Fh
0x18007f58d  add     eax, edi
0x18007f58f  movzx   edi, word ptr [rsi+rax*2]
0x18007f593  mov     [rbx], ecx
0x18007f595  test    dil, 8
0x18007f599  jz      short loc_18007F570
0x18007f59b  mov     rsi, [rsp+78h+arg_8]
0x18007f5a3  mov     eax, edi
0x18007f5a5  mov     rdx, [rsp+78h+var_48]
0x18007f5aa  and     eax, 3
0x18007f5ad  movzx   r8d, [rsp+78h+arg_10]
0x18007f5b6  add     eax, ecx
0x18007f5b8  shr     edi, 4
0x18007f5bb  add     edi, 0FFFFFFC4h
0x18007f5be  mov     [rbx], eax
0x18007f5c0  add     r13d, edi
0x18007f5c3  lea     eax, [r13-64h]
0x18007f5c7  jmp     short loc_18007F5FD
0x18007f5c9  movzx   r9d, r8b
0x18007f5cd  mov     [rsp+78h+var_50], 0
0x18007f5d5  lea     r8, qword_18008B6D0
0x18007f5dc  mov     [rsp+78h+var_58], ebp
0x18007f5e0  mov     rdx, rbx
0x18007f5e3  mov     rcx, rsi
0x18007f5e6  call    CPns_Read
0x18007f5eb  mov     rdx, [rsp+78h+var_48]
0x18007f5f0  movzx   r8d, [rsp+78h+arg_10]
0x18007f5f9  jmp     short loc_18007F602
0x18007f5fb  xor     eax, eax
0x18007f5fd  mov     [r15+r14*2], ax
0x18007f602  movsx   eax, byte ptr [rsi+1Ch]
0x18007f606  inc     ebp
0x18007f608  cmp     ebp, eax
0x18007f60a  jl      loc_18007F4B0
0x18007f610  lea     rdx, [rsi+393h]
0x18007f617  mov     rcx, rbx
0x18007f61a  call    CPulseData_Read
0x18007f61f  cmp     dword ptr [rbx], 1
0x18007f622  mov     r15, [rsp+78h+var_38]
0x18007f627  mov     r13, [rsp+78h+arg_0]
0x18007f62f  jnb     short loc_18007F63E
0x18007f631  mov     edx, 1
0x18007f636  mov     rcx, rbx
0x18007f639  call    FillBitCache
0x18007f63e  dec     dword ptr [rbx]
0x18007f640  mov     rdx, rsi
0x18007f643  mov     ecx, [rbx]
0x18007f645  mov     eax, [rbx+4]
0x18007f648  shr     eax, cl
0x18007f64a  mov     rcx, rbx
0x18007f64d  and     al, 1
0x18007f64f  mov     [rsi+2Ah], al
0x18007f652  call    CTns_Read
0x18007f657  test    eax, eax
0x18007f659  jnz     short loc_18007F694
0x18007f65b  cmp     dword ptr [rbx], 1
0x18007f65e  jnb     short loc_18007F66D
0x18007f660  mov     edx, 1
0x18007f665  mov     rcx, rbx
0x18007f668  call    FillBitCache
0x18007f66d  dec     dword ptr [rbx]
0x18007f66f  mov     eax, [rbx+4]
0x18007f672  mov     ecx, [rbx]
0x18007f674  shr     eax, cl
0x18007f676  test    al, 1
0x18007f678  jz      short loc_18007F689
0x18007f67a  mov     rdx, rsi
0x18007f67d  mov     rcx, rbx
0x18007f680  call    CGC_Read
0x18007f685  test    eax, eax
0x18007f687  jnz     short loc_18007F694
0x18007f689  mov     rdx, rsi
0x18007f68c  mov     rcx, rbx
0x18007f68f  call    CLongBlock_ReadSpectralData
0x18007f694  add     rsp, 48h
0x18007f698  pop     r14
0x18007f69a  pop     r12
0x18007f69c  pop     rdi
0x18007f69d  pop     rsi
0x18007f69e  pop     rbp
0x18007f69f  pop     rbx
0x18007f6a0  retn
```
