# CRelation::ProcessTheJunction(void)

- ea: `0x10042b170`
- end: `0x10042b6f1`
- name: `?ProcessTheJunction@CRelation@@UEAAJXZ`
- size: `1409`
- prototype: `__int64 __fastcall(CRelation *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path`

## callees

- `0x10042b170`
- `0x1004453c0`
- `0x100468a30`

## pseudocode

```c
__int64 __fastcall CRelation::ProcessTheJunction(CRelation *this)
{
  char v2; // r15
  char v3; // r14
  char v4; // r12
  char v5; // r13
  int v6; // eax
  int *v7; // rcx
  int v8; // ecx
  int v9; // edx
  int *v10; // rdx
  int *v11; // rcx
  int *v12; // rcx
  int v13; // esi
  int v14; // r11d
  int v15; // r10d
  __int64 v16; // rax
  int v17; // eax
  int v18; // ecx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  unsigned int v22; // r8d
  __int64 *v23; // rdi
  __int64 v24; // r9
  int v25; // edx
  __int64 v26; // rax
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rax
  __int64 v30; // rax
  int v31; // ecx
  __int64 v32; // rax
  int v33; // ecx
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  int v44; // eax
  __int64 v46; // [rsp+20h] [rbp-20h] BYREF
  int v47; // [rsp+28h] [rbp-18h]
  __int64 v48; // [rsp+2Ch] [rbp-14h]
  int v49; // [rsp+34h] [rbp-Ch]

  *((_WORD *)this + 284) = 0;
  *(_QWORD *)((char *)this + 572) = 0;
  *((_QWORD *)this + 75) = 0;
  v2 = 0;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  C2ShapesProcessor::Classify(this);
  v6 = -1;
  v46 = -1;
  v47 = 2;
  if ( *((_BYTE *)this + 568) )
  {
    v7 = (int *)*((_QWORD *)this + 70);
    if ( *v7 < 2 )
      *v7 = 2;
    HIDWORD(v46) = 1;
    v8 = 1;
    v47 = -1;
  }
  else
  {
    if ( *((_BYTE *)this + 552) )
    {
      v6 = 2;
      v47 = -1;
      LODWORD(v46) = 2;
      v2 = 1;
    }
    else
    {
      v4 = 1;
    }
    v8 = -1;
  }
  v9 = *((_DWORD *)this + 143);
  if ( (v9 & 1) != 0 )
  {
    v10 = (int *)*((_QWORD *)this + 70);
    if ( *v10 < 1 )
      *v10 = 1;
    if ( v8 < 0 )
      HIDWORD(v46) = 0;
  }
  else
  {
    if ( !v9 )
      goto LABEL_21;
    v11 = (int *)*((_QWORD *)this + 70);
    if ( *v11 < 1 )
      *v11 = 1;
    if ( v6 < 1 )
      v6 = 1;
    LODWORD(v46) = v6;
  }
  v47 = -1;
LABEL_21:
  if ( *((_DWORD *)this + 90) && !*((_BYTE *)this + 386) )
  {
    v12 = (int *)*((_QWORD *)this + 70);
    if ( *v12 < 0 )
      *v12 = 0;
    v47 = -1;
    if ( v6 < 0 )
      v6 = 0;
    LODWORD(v46) = v6;
  }
  v13 = -1;
  v14 = 2;
  v15 = -1;
  v49 = 2;
  v48 = -1;
  if ( *((_BYTE *)this + 569) )
  {
    v16 = *((_QWORD *)this + 70);
    if ( *(int *)(v16 + 4) < 2 )
      *(_DWORD *)(v16 + 4) = 2;
    v13 = 1;
    HIDWORD(v48) = 1;
    v14 = -1;
    v49 = -1;
    v17 = 1;
  }
  else
  {
    v17 = -1;
    if ( *((_BYTE *)this + 553) )
    {
      v15 = 2;
      LODWORD(v48) = 2;
      v14 = -1;
      v49 = -1;
      v3 = 1;
    }
    else
    {
      v5 = 1;
    }
  }
  v18 = *((_DWORD *)this + 144);
  if ( (v18 & 1) != 0 )
  {
    v19 = *((_QWORD *)this + 70);
    if ( *(int *)(v19 + 4) < 1 )
      *(_DWORD *)(v19 + 4) = 1;
    v14 = -1;
    v49 = -1;
    if ( v17 < 0 )
      v13 = 0;
    HIDWORD(v48) = v13;
  }
  else if ( v18 )
  {
    v20 = *((_QWORD *)this + 70);
    if ( *(int *)(v20 + 4) < 1 )
      *(_DWORD *)(v20 + 4) = 1;
    v14 = -1;
    v49 = -1;
    if ( v15 < 1 )
      v15 = 1;
    LODWORD(v48) = v15;
  }
  if ( *((_DWORD *)this + 91) && !*((_BYTE *)this + 386) )
  {
    v21 = *((_QWORD *)this + 70);
    if ( *(int *)(v21 + 4) < 0 )
      *(_DWORD *)(v21 + 4) = 0;
    v14 = -1;
    v49 = -1;
    if ( v15 < 0 )
      v15 = 0;
    LODWORD(v48) = v15;
  }
  v22 = 0;
  v23 = &v46;
  v24 = 16;
  do
  {
    v25 = *(_DWORD *)v23;
    if ( *(_DWORD *)v23 == 1 && v15 == 1 )
    {
      v26 = *((_QWORD *)this + 70);
      if ( *(int *)(v24 + v26 - 8) < 0 )
      {
        *(_DWORD *)(v24 + v26 - 8) = 0;
        if ( v22 == 2 )
          *(_BYTE *)(v26 + 45) = 0;
        else
          *(_BYTE *)(v26 + 44) = 0;
      }
    }
    else
    {
      v27 = *((_QWORD *)this + 70);
      v28 = v15;
      if ( v25 < v15 )
        v28 = *(_DWORD *)v23;
      if ( v28 > *(_DWORD *)(v24 + v27 - 8) )
      {
        *(_DWORD *)(v24 + v27 - 8) = v28;
        if ( v22 == 2 )
          *(_BYTE *)(v27 + 45) = 0;
        else
          *(_BYTE *)(v27 + 44) = 0;
      }
      if ( v25 != 1 )
        goto LABEL_73;
    }
    if ( v13 == 1 )
    {
      v29 = *((_QWORD *)this + 70);
      if ( *(int *)(v24 + v29 - 4) < 0 )
      {
        *(_DWORD *)(v24 + v29 - 4) = 0;
        if ( v22 == 2 )
          *(_BYTE *)(v29 + 45) = 0;
        else
          *(_BYTE *)(v29 + 44) = 0;
      }
      goto LABEL_79;
    }
LABEL_73:
    v30 = *((_QWORD *)this + 70);
    v31 = v13;
    if ( v25 < v13 )
      v31 = v25;
    if ( v31 > *(_DWORD *)(v24 + v30 - 4) )
    {
      *(_DWORD *)(v24 + v30 - 4) = v31;
      if ( v22 == 2 )
        *(_BYTE *)(v30 + 45) = 0;
      else
        *(_BYTE *)(v30 + 44) = 0;
    }
LABEL_79:
    v32 = *((_QWORD *)this + 70);
    v33 = v14;
    if ( v25 < v14 )
      v33 = v25;
    if ( v33 > *(_DWORD *)(v24 + v32) )
    {
      *(_DWORD *)(v24 + v32) = v33;
      if ( v22 == 2 )
        break;
    }
    ++v22;
    v23 = (__int64 *)((char *)v23 + 4);
    v24 += 12;
  }
  while ( v22 <= 2 );
  if ( v2 )
  {
    if ( v3 )
    {
      v34 = *((_QWORD *)this + 70);
      if ( *(int *)(v34 + 8) < 2 )
      {
        *(_DWORD *)(v34 + 8) = 2;
        *(_BYTE *)(v34 + 44) = 0;
      }
    }
    else if ( v5 )
    {
      v35 = *((_QWORD *)this + 70);
      if ( *(int *)(v35 + 16) < 2 )
        *(_DWORD *)(v35 + 16) = 2;
    }
  }
  else if ( v4 )
  {
    if ( v3 )
    {
      v36 = *((_QWORD *)this + 70);
      if ( *(int *)(v36 + 32) < 2 )
      {
        *(_DWORD *)(v36 + 32) = 2;
        *(_BYTE *)(v36 + 45) = 0;
      }
    }
  }
  if ( *((_BYTE *)this + 600) )
  {
    v37 = *((_QWORD *)this + 70);
    if ( *(int *)(v37 + 8) < 2 )
    {
      *(_DWORD *)(v37 + 8) = 2;
      *(_BYTE *)(v37 + 44) = 0;
      v37 = *((_QWORD *)this + 70);
    }
    if ( *(int *)(v37 + 20) < 1 )
    {
      *(_DWORD *)(v37 + 20) = 1;
      *(_BYTE *)(v37 + 44) = 0;
      v37 = *((_QWORD *)this + 70);
    }
    if ( *(int *)(v37 + 32) < 2 )
    {
      *(_DWORD *)(v37 + 32) = 2;
      *(_BYTE *)(v37 + 45) = 0;
    }
  }
  if ( *((_BYTE *)this + 601) )
  {
    v38 = *((_QWORD *)this + 70);
    if ( *(int *)(v38 + 8) < 2 )
    {
      *(_DWORD *)(v38 + 8) = 2;
      *(_BYTE *)(v38 + 44) = 0;
      v38 = *((_QWORD *)this + 70);
    }
    if ( *(int *)(v38 + 12) < 1 )
    {
      *(_DWORD *)(v38 + 12) = 1;
      *(_BYTE *)(v38 + 44) = 0;
      v38 = *((_QWORD *)this + 70);
    }
    if ( *(int *)(v38 + 16) < 2 )
      *(_DWORD *)(v38 + 16) = 2;
  }
  if ( *((_BYTE *)this + 602) )
  {
    v39 = *((_QWORD *)this + 70);
    if ( *(int *)(v39 + 16) < 2 )
    {
      *(_DWORD *)(v39 + 16) = 2;
      v39 = *((_QWORD *)this + 70);
    }
    if ( *(int *)(v39 + 28) < 1 )
      *(_DWORD *)(v39 + 28) = 1;
  }
  if ( *((_BYTE *)this + 603) )
  {
    v40 = *((_QWORD *)this + 70);
    if ( *(int *)(v40 + 32) < 2 )
    {
      *(_DWORD *)(v40 + 32) = 2;
      *(_BYTE *)(v40 + 45) = 0;
      v40 = *((_QWORD *)this + 70);
    }
    if ( *(int *)(v40 + 36) < 1 )
    {
      *(_DWORD *)(v40 + 36) = 1;
      *(_BYTE *)(v40 + 45) = 0;
    }
  }
  if ( *((_BYTE *)this + 604) || *((_BYTE *)this + 605) )
  {
    v41 = *((_QWORD *)this + 70);
    if ( *(int *)(v41 + 8) < 1 )
    {
      *(_DWORD *)(v41 + 8) = 1;
      *(_BYTE *)(v41 + 44) = 0;
    }
  }
  if ( *((_BYTE *)this + 606) )
  {
    v42 = *((_QWORD *)this + 70);
    if ( *(int *)(v42 + 16) < 1 )
      *(_DWORD *)(v42 + 16) = 1;
  }
  if ( *((_BYTE *)this + 607) )
  {
    v43 = *((_QWORD *)this + 70);
    if ( *(int *)(v43 + 32) < 1 )
    {
      *(_DWORD *)(v43 + 32) = 1;
      *(_BYTE *)(v43 + 45) = 0;
    }
  }
  v44 = *((_DWORD *)this + 152);
  if ( v44 == 2 )
  {
    if ( *(_BYTE *)(*((_QWORD *)this + 70) + 44LL) )
      return 0;
LABEL_134:
    *((_BYTE *)this + 513) = 1;
  }
  else if ( v44 == 3 && !*(_BYTE *)(*((_QWORD *)this + 70) + 45LL) )
  {
    goto LABEL_134;
  }
  return 0;
}

```

## disassembly

```asm
0x10042b170  mov     [rsp-28h+arg_8], rbx
0x10042b175  mov     [rsp-28h+arg_10], rsi
0x10042b17a  mov     [rsp-28h+arg_18], rdi
0x10042b17f  push    rbp
0x10042b180  push    r12
0x10042b182  push    r13
0x10042b184  push    r14
0x10042b186  push    r15
0x10042b188  mov     rbp, rsp
0x10042b18b  sub     rsp, 40h
0x10042b18f  mov     rax, cs:__security_cookie
0x10042b196  xor     rax, rsp
0x10042b199  mov     [rbp+var_8], rax
0x10042b19d  xor     edi, edi
0x10042b19f  mov     word ptr [rcx+238h], 0
0x10042b1a8  mov     [rcx+23Ch], rdi
0x10042b1af  mov     rbx, rcx
0x10042b1b2  mov     [rcx+258h], rdi
0x10042b1b9  xor     r15b, r15b
0x10042b1bc  xor     r14b, r14b
0x10042b1bf  xor     r12b, r12b
0x10042b1c2  xor     r13b, r13b
0x10042b1c5  call    ?Classify@C2ShapesProcessor@@IEAAXXZ
0x10042b1ca  lea     eax, [rdi-1]
0x10042b1cd  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFFh
0x10042b1d5  lea     r8d, [rdi+1]
0x10042b1d9  mov     [rbp+var_18], 2
0x10042b1e0  cmp     [rbx+238h], dil
0x10042b1e7  jz      short loc_10042B207
0x10042b1e9  mov     rcx, [rbx+230h]
0x10042b1f0  cmp     dword ptr [rcx], 2
0x10042b1f3  jge     short loc_10042B1FB
0x10042b1f5  mov     dword ptr [rcx], 2
0x10042b1fb  mov     dword ptr [rbp+var_20+4], r8d
0x10042b1ff  mov     ecx, r8d
0x10042b202  mov     [rbp+var_18], eax
0x10042b205  jmp     short loc_10042B22E
0x10042b207  cmp     [rbx+228h], dil
0x10042b20e  jz      short loc_10042B228
0x10042b210  mov     eax, 2
0x10042b215  mov     [rbp+var_18], 0FFFFFFFFh
0x10042b21c  mov     dword ptr [rbp+var_20], eax
0x10042b21f  movzx   r15d, r8b
0x10042b223  lea     ecx, [rax-3]
0x10042b226  jmp     short loc_10042B22E
0x10042b228  movzx   r12d, r8b
0x10042b22c  mov     ecx, eax
0x10042b22e  mov     edx, [rbx+23Ch]
0x10042b234  test    r8b, dl
0x10042b237  jz      short loc_10042B251
0x10042b239  mov     rdx, [rbx+230h]
0x10042b240  cmp     [rdx], r8d
0x10042b243  jge     short loc_10042B248
0x10042b245  mov     [rdx], r8d
0x10042b248  test    ecx, ecx
0x10042b24a  jns     short loc_10042B26E
0x10042b24c  mov     dword ptr [rbp+var_20+4], edi
0x10042b24f  jmp     short loc_10042B26E
0x10042b251  test    edx, edx
0x10042b253  jz      short loc_10042B275
0x10042b255  mov     rcx, [rbx+230h]
0x10042b25c  cmp     [rcx], r8d
0x10042b25f  jge     short loc_10042B264
0x10042b261  mov     [rcx], r8d
0x10042b264  cmp     eax, r8d
0x10042b267  cmovl   eax, r8d
0x10042b26b  mov     dword ptr [rbp+var_20], eax
0x10042b26e  mov     [rbp+var_18], 0FFFFFFFFh
0x10042b275  cmp     [rbx+168h], edi
0x10042b27b  jbe     short loc_10042B2A2
0x10042b27d  cmp     [rbx+182h], dil
0x10042b284  jnz     short loc_10042B2A2
0x10042b286  mov     rcx, [rbx+230h]
0x10042b28d  cmp     [rcx], edi
0x10042b28f  jge     short loc_10042B293
0x10042b291  mov     [rcx], edi
0x10042b293  test    eax, eax
0x10042b295  mov     [rbp+var_18], 0FFFFFFFFh
0x10042b29c  cmovs   eax, edi
0x10042b29f  mov     dword ptr [rbp+var_20], eax
0x10042b2a2  mov     esi, 0FFFFFFFFh
0x10042b2a7  mov     r11d, 2
0x10042b2ad  mov     r10d, esi
0x10042b2b0  mov     [rbp+var_C], r11d
0x10042b2b4  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x10042b2bc  cmp     [rbx+239h], dil
0x10042b2c3  jz      short loc_10042B2E9
0x10042b2c5  mov     rax, [rbx+230h]
0x10042b2cc  cmp     [rax+4], r11d
0x10042b2d0  jge     short loc_10042B2D6
0x10042b2d2  mov     [rax+4], r11d
0x10042b2d6  mov     esi, r8d
0x10042b2d9  mov     dword ptr [rbp+var_14+4], r8d
0x10042b2dd  mov     r11d, r10d
0x10042b2e0  mov     [rbp+var_C], r10d
0x10042b2e4  mov     eax, r8d
0x10042b2e7  jmp     short loc_10042B30B
0x10042b2e9  mov     eax, esi
0x10042b2eb  cmp     [rbx+229h], dil
0x10042b2f2  jz      short loc_10042B307
0x10042b2f4  mov     r10d, r11d
0x10042b2f7  mov     dword ptr [rbp+var_14], r11d
0x10042b2fb  mov     r11d, esi
0x10042b2fe  mov     [rbp+var_C], esi
0x10042b301  movzx   r14d, r8b
0x10042b305  jmp     short loc_10042B30B
0x10042b307  movzx   r13d, r8b
0x10042b30b  mov     ecx, [rbx+240h]
0x10042b311  test    r8b, cl
0x10042b314  jz      short loc_10042B33D
0x10042b316  mov     rcx, [rbx+230h]
0x10042b31d  cmp     [rcx+4], r8d
0x10042b321  jge     short loc_10042B327
0x10042b323  mov     [rcx+4], r8d
0x10042b327  test    eax, eax
0x10042b329  mov     r11d, 0FFFFFFFFh
0x10042b32f  mov     ecx, edi
0x10042b331  mov     [rbp+var_C], r11d
0x10042b335  cmovs   esi, edi
0x10042b338  mov     dword ptr [rbp+var_14+4], esi
0x10042b33b  jmp     short loc_10042B369
0x10042b33d  test    ecx, ecx
0x10042b33f  jz      short loc_10042B367
0x10042b341  mov     rax, [rbx+230h]
0x10042b348  cmp     [rax+4], r8d
0x10042b34c  jge     short loc_10042B352
0x10042b34e  mov     [rax+4], r8d
0x10042b352  cmp     r10d, r8d
0x10042b355  mov     r11d, 0FFFFFFFFh
0x10042b35b  mov     [rbp+var_C], r11d
0x10042b35f  cmovl   r10d, r8d
0x10042b363  mov     dword ptr [rbp+var_14], r10d
0x10042b367  xor     ecx, ecx
0x10042b369  cmp     [rbx+16Ch], edi
0x10042b36f  jbe     short loc_10042B39E
0x10042b371  cmp     [rbx+182h], dil
0x10042b378  jnz     short loc_10042B39E
0x10042b37a  mov     rax, [rbx+230h]
0x10042b381  cmp     [rax+4], edi
0x10042b384  jge     short loc_10042B389
0x10042b386  mov     [rax+4], ecx
0x10042b389  test    r10d, r10d
0x10042b38c  mov     r11d, 0FFFFFFFFh
0x10042b392  mov     [rbp+var_C], r11d
0x10042b396  cmovs   r10d, ecx
0x10042b39a  mov     dword ptr [rbp+var_14], r10d
0x10042b39e  mov     r8d, ecx
0x10042b3a1  lea     rdi, [rbp+var_20]
0x10042b3a5  mov     r9d, 10h
0x10042b3ab  nop     dword ptr [rax+rax+00h]
0x10042b3b0  mov     edx, [rdi]
0x10042b3b2  cmp     edx, 1
0x10042b3b5  jnz     short loc_10042B3E2
0x10042b3b7  cmp     r10d, edx
0x10042b3ba  jnz     short loc_10042B3E2
0x10042b3bc  mov     rax, [rbx+230h]
0x10042b3c3  cmp     dword ptr [r9+rax-8], 0
0x10042b3c9  jge     short loc_10042B415
0x10042b3cb  mov     [r9+rax-8], ecx
0x10042b3d0  cmp     r8d, 2
0x10042b3d4  jz      short loc_10042B3DC
0x10042b3d6  mov     byte ptr [rax+2Ch], 0
0x10042b3da  jmp     short loc_10042B415
0x10042b3dc  mov     byte ptr [rax+2Dh], 0
0x10042b3e0  jmp     short loc_10042B415
0x10042b3e2  mov     rcx, [rbx+230h]
0x10042b3e9  cmp     edx, r10d
0x10042b3ec  mov     eax, r10d
0x10042b3ef  cmovl   eax, edx
0x10042b3f2  cmp     eax, [r9+rcx-8]
0x10042b3f7  jle     short loc_10042B40E
0x10042b3f9  mov     [r9+rcx-8], eax
0x10042b3fe  cmp     r8d, 2
0x10042b402  jz      short loc_10042B40A
0x10042b404  mov     byte ptr [rcx+2Ch], 0
0x10042b408  jmp     short loc_10042B40E
0x10042b40a  mov     byte ptr [rcx+2Dh], 0
0x10042b40e  cmp     edx, 1
0x10042b411  jnz     short loc_10042B440
0x10042b413  xor     ecx, ecx
0x10042b415  cmp     esi, 1
0x10042b418  jnz     short loc_10042B440
0x10042b41a  mov     rax, [rbx+230h]
0x10042b421  cmp     dword ptr [r9+rax-4], 0
0x10042b427  jge     short loc_10042B46F
0x10042b429  mov     [r9+rax-4], ecx
0x10042b42e  cmp     r8d, 2
0x10042b432  jz      short loc_10042B43A
0x10042b434  mov     byte ptr [rax+2Ch], 0
0x10042b438  jmp     short loc_10042B46F
0x10042b43a  mov     byte ptr [rax+2Dh], 0
0x10042b43e  jmp     short loc_10042B46F
0x10042b440  mov     rax, [rbx+230h]
0x10042b447  cmp     edx, esi
0x10042b449  mov     ecx, esi
0x10042b44b  cmovl   ecx, edx
0x10042b44e  cmp     ecx, [r9+rax-4]
0x10042b453  jle     short loc_10042B46A
0x10042b455  mov     [r9+rax-4], ecx
0x10042b45a  cmp     r8d, 2
0x10042b45e  jz      short loc_10042B466
0x10042b460  mov     byte ptr [rax+2Ch], 0
0x10042b464  jmp     short loc_10042B46A
0x10042b466  mov     byte ptr [rax+2Dh], 0
0x10042b46a  cmp     edx, 1
0x10042b46d  jnz     short loc_10042B48A
0x10042b46f  cmp     r11d, 1
0x10042b473  jnz     short loc_10042B48A
0x10042b475  mov     rax, [rbx+230h]
0x10042b47c  xor     ecx, ecx
0x10042b47e  cmp     [r9+rax], ecx
0x10042b482  jge     short loc_10042B4AC
0x10042b484  mov     [r9+rax], ecx
0x10042b488  jmp     short loc_10042B4AC
0x10042b48a  mov     rax, [rbx+230h]
0x10042b491  cmp     edx, r11d
0x10042b494  mov     ecx, r11d
0x10042b497  cmovl   ecx, edx
0x10042b49a  cmp     ecx, [r9+rax]
0x10042b49e  jle     short loc_10042B4AA
0x10042b4a0  mov     [r9+rax], ecx
0x10042b4a4  cmp     r8d, 2
0x10042b4a8  jz      short loc_10042B4C1
0x10042b4aa  xor     ecx, ecx
0x10042b4ac  inc     r8d
0x10042b4af  add     rdi, 4
0x10042b4b3  add     r9, 0Ch
0x10042b4b7  cmp     r8d, 2
0x10042b4bb  jbe     loc_10042B3B0
0x10042b4c1  test    r15b, r15b
0x10042b4c4  jz      short loc_10042B500
0x10042b4c6  test    r14b, r14b
0x10042b4c9  jz      short loc_10042B4E5
0x10042b4cb  mov     rax, [rbx+230h]
0x10042b4d2  cmp     dword ptr [rax+8], 2
0x10042b4d6  jge     short loc_10042B522
0x10042b4d8  mov     dword ptr [rax+8], 2
0x10042b4df  mov     byte ptr [rax+2Ch], 0
0x10042b4e3  jmp     short loc_10042B522
0x10042b4e5  test    r13b, r13b
0x10042b4e8  jz      short loc_10042B522
0x10042b4ea  mov     rax, [rbx+230h]
0x10042b4f1  cmp     dword ptr [rax+10h], 2
0x10042b4f5  jge     short loc_10042B522
0x10042b4f7  mov     dword ptr [rax+10h], 2
0x10042b4fe  jmp     short loc_10042B522
0x10042b500  test    r12b, r12b
0x10042b503  jz      short loc_10042B522
0x10042b505  test    r14b, r14b
0x10042b508  jz      short loc_10042B522
0x10042b50a  mov     rax, [rbx+230h]
0x10042b511  cmp     dword ptr [rax+20h], 2
0x10042b515  jge     short loc_10042B522
0x10042b517  mov     dword ptr [rax+20h], 2
0x10042b51e  mov     byte ptr [rax+2Dh], 0
0x10042b522  cmp     byte ptr [rbx+258h], 0
0x10042b529  jz      short loc_10042B573
0x10042b52b  mov     rax, [rbx+230h]
0x10042b532  cmp     dword ptr [rax+8], 2
0x10042b536  jge     short loc_10042B54A
0x10042b538  mov     dword ptr [rax+8], 2
0x10042b53f  mov     byte ptr [rax+2Ch], 0
0x10042b543  mov     rax, [rbx+230h]
0x10042b54a  cmp     dword ptr [rax+14h], 1
0x10042b54e  jge     short loc_10042B562
0x10042b550  mov     dword ptr [rax+14h], 1
0x10042b557  mov     byte ptr [rax+2Ch], 0
0x10042b55b  mov     rax, [rbx+230h]
0x10042b562  cmp     dword ptr [rax+20h], 2
0x10042b566  jge     short loc_10042B573
0x10042b568  mov     dword ptr [rax+20h], 2
0x10042b56f  mov     byte ptr [rax+2Dh], 0
0x10042b573  cmp     byte ptr [rbx+259h], 0
0x10042b57a  jz      short loc_10042B5C0
0x10042b57c  mov     rax, [rbx+230h]
0x10042b583  cmp     dword ptr [rax+8], 2
0x10042b587  jge     short loc_10042B59B
0x10042b589  mov     dword ptr [rax+8], 2
0x10042b590  mov     byte ptr [rax+2Ch], 0
0x10042b594  mov     rax, [rbx+230h]
0x10042b59b  cmp     dword ptr [rax+0Ch], 1
0x10042b59f  jge     short loc_10042B5B3
0x10042b5a1  mov     dword ptr [rax+0Ch], 1
0x10042b5a8  mov     byte ptr [rax+2Ch], 0
0x10042b5ac  mov     rax, [rbx+230h]
0x10042b5b3  cmp     dword ptr [rax+10h], 2
0x10042b5b7  jge     short loc_10042B5C0
0x10042b5b9  mov     dword ptr [rax+10h], 2
0x10042b5c0  cmp     byte ptr [rbx+25Ah], 0
0x10042b5c7  jz      short loc_10042B5F1
0x10042b5c9  mov     rax, [rbx+230h]
0x10042b5d0  cmp     dword ptr [rax+10h], 2
0x10042b5d4  jge     short loc_10042B5E4
0x10042b5d6  mov     dword ptr [rax+10h], 2
0x10042b5dd  mov     rax, [rbx+230h]
0x10042b5e4  cmp     dword ptr [rax+1Ch], 1
0x10042b5e8  jge     short loc_10042B5F1
0x10042b5ea  mov     dword ptr [rax+1Ch], 1
0x10042b5f1  cmp     byte ptr [rbx+25Bh], 0
0x10042b5f8  jz      short loc_10042B62A
  ... truncated ...
```
