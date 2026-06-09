# moveToRoot

- ea: `0x1800259b0`
- end: `0x180025cd5`
- name: `moveToRoot`
- size: `805`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `7`
- callee_count: `10`
- tags: ``

## callers

- `0x18001cea8`
- `0x18001ed0c`
- `0x180024eb4`
- `0x18005430c`
- `0x18005fc6c`
- `0x1800601e4`
- `0x180065278`

## callees

- `0x18000aac0`
- `0x1800259b0`
- `0x180025ce0`
- `0x180025d50`
- `0x1800275f0`
- `0x1800277c0`
- `0x180054468`
- `0x180060134`
- `0x180067c8c`
- `0x18009a010`

## pseudocode

```c
__int64 __fastcall moveToRoot(__int64 a1)
{
  char v1; // al
  unsigned int v3; // esi
  __int64 v4; // rax
  __int64 v5; // r8
  __int64 v6; // rcx
  char v7; // al
  __int64 v8; // rdx
  _DWORD *v10; // r14
  unsigned int v11; // esi
  unsigned int inited; // ebp
  __int64 v13; // rcx
  __int64 v14; // r15
  __int64 v15; // rax
  int v16; // r9d
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rcx
  char v20; // al
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rdx
  __int64 v25; // [rsp+70h] [rbp+8h] BYREF

  v1 = *(_BYTE *)(a1 + 84);
  if ( v1 < 0 )
  {
    if ( !*(_DWORD *)(a1 + 80) )
    {
      *(_BYTE *)a1 = 1;
      return 16;
    }
    if ( *(_BYTE *)a1 >= 3u )
    {
      if ( *(_BYTE *)a1 == 4 )
        return *(unsigned int *)(a1 + 4);
      sqlite3_free(*(_QWORD *)(a1 + 24));
      *(_QWORD *)(a1 + 24) = 0;
      *(_BYTE *)a1 = 1;
    }
    v10 = *(_DWORD **)(a1 + 32);
    v11 = *(_DWORD *)(a1 + 80);
    v25 = 0;
    if ( v11 > v10[16] )
    {
      *(_QWORD *)(a1 + 136) = 0;
      inited = sqlite3ReportError(11, 73047, "database corruption");
      if ( inited )
        goto LABEL_23;
    }
    else
    {
      inited = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *, _QWORD))(*(_QWORD *)v10 + 272LL))(
                 *(_QWORD *)v10,
                 v11,
                 &v25,
                 *(unsigned __int8 *)(a1 + 2));
      if ( inited )
      {
LABEL_22:
        *(_QWORD *)(a1 + 136) = 0;
LABEL_23:
        *(_BYTE *)a1 = 1;
        return inited;
      }
      v13 = v25;
      v14 = *(_QWORD *)(v25 + 16);
      if ( !*(_BYTE *)v14 )
      {
        if ( v11 != *(_DWORD *)(v14 + 4) )
        {
          *(_QWORD *)(v14 + 80) = *(_QWORD *)(v25 + 8);
          v20 = 100;
          if ( v11 != 1 )
            v20 = 0;
          *(_QWORD *)(v14 + 112) = v13;
          *(_BYTE *)(v14 + 9) = v20;
          *(_QWORD *)(v14 + 72) = v10;
          *(_DWORD *)(v14 + 4) = v11;
        }
        inited = btreeInitPage(v14);
        if ( inited )
        {
          sqlite3PagerUnrefNotNull(*(_QWORD *)(v14 + 112), v21, v22, v23);
          goto LABEL_22;
        }
      }
      *(_QWORD *)(a1 + 136) = v14;
    }
    v15 = *(_QWORD *)(a1 + 136);
    v3 = 0;
    *(_BYTE *)(a1 + 84) = 0;
    *(_BYTE *)(a1 + 85) = *(_BYTE *)(v15 + 1);
    goto LABEL_18;
  }
  v3 = 0;
  if ( !v1 )
  {
LABEL_18:
    v8 = *(_QWORD *)(a1 + 136);
    if ( !*(_BYTE *)v8 || (*(_QWORD *)(a1 + 128) == 0) != *(_BYTE *)(v8 + 1) )
    {
      v16 = 76221;
LABEL_21:
      sqlite3_log(
        11,
        "%s at line %d of [%.10s]",
        "database corruption",
        v16,
        "2aabe05e2e8cae4847a802ee2daddc1d7413d8fc560254d93ee3e72c14685b6c");
      return 11;
    }
    goto LABEL_7;
  }
  v4 = *(_QWORD *)(a1 + 136);
  v5 = *(_QWORD *)(v4 + 112);
  if ( (*(_BYTE *)(v5 + 52) & 0x20) != 0 )
  {
    v6 = *(_QWORD *)(v5 + 40);
    --*(_DWORD *)(v6 + 152);
    *(_QWORD *)(v5 + 32) = *(_QWORD *)(v6 + 168);
    *(_QWORD *)(v6 + 168) = v5;
    sqlite3OsUnfetch(
      *(_QWORD *)(v6 + 72),
      *(_QWORD *)(v6 + 200) * (unsigned int)(*(_DWORD *)(v5 + 48) - 1),
      *(_QWORD *)(v5 + 8));
  }
  else
  {
    sqlite3PcacheRelease(*(_QWORD *)(v4 + 112));
  }
  v7 = *(_BYTE *)(a1 + 84) - 1;
  for ( *(_BYTE *)(a1 + 84) = v7; v7; *(_BYTE *)(a1 + 84) = v7 )
  {
    v17 = *(_QWORD *)(a1 + 8LL * v7 + 144);
    v18 = *(_QWORD *)(v17 + 112);
    if ( (*(_BYTE *)(v18 + 52) & 0x20) != 0 )
    {
      v19 = *(_QWORD *)(v18 + 40);
      --*(_DWORD *)(v19 + 152);
      *(_QWORD *)(v18 + 32) = *(_QWORD *)(v19 + 168);
      *(_QWORD *)(v19 + 168) = v18;
      sqlite3OsUnfetch(
        *(_QWORD *)(v19 + 72),
        *(_QWORD *)(v19 + 200) * (unsigned int)(*(_DWORD *)(v18 + 48) - 1),
        *(_QWORD *)(v18 + 8));
    }
    else
    {
      sqlite3PcacheRelease(*(_QWORD *)(v17 + 112));
    }
    v7 = *(_BYTE *)(a1 + 84) - 1;
  }
  v8 = *(_QWORD *)(a1 + 144);
  *(_QWORD *)(a1 + 136) = v8;
LABEL_7:
  *(_BYTE *)(a1 + 1) &= 0xF1u;
  *(_WORD *)(a1 + 86) = 0;
  *(_WORD *)(a1 + 70) = 0;
  if ( *(_WORD *)(v8 + 24) )
  {
    *(_BYTE *)a1 = 0;
    return v3;
  }
  if ( *(_BYTE *)(v8 + 8) )
  {
    *(_BYTE *)a1 = 1;
    return 16;
  }
  if ( *(_DWORD *)(v8 + 4) != 1 )
  {
    v16 = 76233;
    goto LABEL_21;
  }
  v24 = _byteswap_ulong(*(_DWORD *)(*(unsigned __int8 *)(v8 + 9) + *(_QWORD *)(v8 + 80) + 8LL));
  *(_BYTE *)a1 = 0;
  return moveToChild(a1, v24);
}

```

## disassembly

```asm
0x1800259b0  push    rbx
0x1800259b2  push    rbp
0x1800259b3  push    rsi
0x1800259b4  push    rdi
0x1800259b5  push    r14
0x1800259b7  push    r15
0x1800259b9  sub     rsp, 38h
0x1800259bd  movzx   eax, byte ptr [rcx+54h]
0x1800259c1  mov     rbx, rcx
0x1800259c4  test    al, al
0x1800259c6  js      loc_180025A71
0x1800259cc  xor     edi, edi
0x1800259ce  mov     esi, edi
0x1800259d0  test    al, al
0x1800259d2  jz      loc_180025AF3
0x1800259d8  mov     rax, [rcx+88h]
0x1800259df  mov     r8, [rax+70h]
0x1800259e3  test    byte ptr [r8+34h], 20h
0x1800259e8  jz      short loc_180025A67
0x1800259ea  mov     rcx, [r8+28h]
0x1800259ee  dec     dword ptr [rcx+98h]
0x1800259f4  mov     rax, [rcx+0A8h]
0x1800259fb  mov     [r8+20h], rax
0x1800259ff  mov     [rcx+0A8h], r8
0x180025a06  mov     edx, [r8+30h]
0x180025a0a  mov     r8, [r8+8]
0x180025a0e  dec     edx
0x180025a10  imul    rdx, [rcx+0C8h]
0x180025a18  mov     rcx, [rcx+48h]
0x180025a1c  call    sqlite3OsUnfetch
0x180025a21  movzx   eax, byte ptr [rbx+54h]
0x180025a25  sub     al, 1
0x180025a27  mov     [rbx+54h], al
0x180025a2a  jnz     loc_180025B70
0x180025a30  mov     rdx, [rbx+90h]
0x180025a37  mov     [rbx+88h], rdx
0x180025a3e  and     byte ptr [rbx+1], 0F1h
0x180025a42  mov     [rbx+56h], di
0x180025a46  mov     [rbx+46h], di
0x180025a4a  cmp     word ptr [rdx+18h], 0
0x180025a4f  jbe     loc_180025BCF
0x180025a55  mov     byte ptr [rbx], 0
0x180025a58  mov     eax, esi
0x180025a5a  add     rsp, 38h
0x180025a5e  pop     r15
0x180025a60  pop     r14
0x180025a62  pop     rdi
0x180025a63  pop     rsi
0x180025a64  pop     rbp
0x180025a65  pop     rbx
0x180025a66  retn
0x180025a67  mov     rcx, r8
0x180025a6a  call    sqlite3PcacheRelease
0x180025a6f  jmp     short loc_180025A21
0x180025a71  cmp     dword ptr [rcx+50h], 0
0x180025a75  jz      loc_180025C46
0x180025a7b  movzx   eax, byte ptr [rcx]
0x180025a7e  xor     edi, edi
0x180025a80  cmp     al, 3
0x180025a82  jnb     loc_180025C5B
0x180025a88  mov     r14, [rbx+20h]
0x180025a8c  mov     esi, [rbx+50h]
0x180025a8f  mov     [rsp+68h+arg_0], rdi
0x180025a94  cmp     esi, [r14+40h]
0x180025a98  ja      loc_180025CA9
0x180025a9e  mov     rax, [r14]
0x180025aa1  lea     r8, [rsp+68h+arg_0]
0x180025aa6  movzx   r9d, byte ptr [rbx+2]
0x180025aab  mov     rcx, rax
0x180025aae  mov     edx, esi
0x180025ab0  mov     rax, [rax+110h]
0x180025ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025abc  mov     ebp, eax
0x180025abe  test    eax, eax
0x180025ac0  jnz     loc_180025B4C
0x180025ac6  mov     rcx, [rsp+68h+arg_0]
0x180025acb  mov     r15, [rcx+10h]
0x180025acf  cmp     [r15], dil
0x180025ad2  jz      loc_180025BEC
0x180025ad8  mov     [rbx+88h], r15
0x180025adf  mov     rax, [rbx+88h]
0x180025ae6  mov     esi, edi
0x180025ae8  mov     [rbx+54h], sil
0x180025aec  movzx   ecx, byte ptr [rax+1]
0x180025af0  mov     [rbx+55h], cl
0x180025af3  mov     rdx, [rbx+88h]
0x180025afa  cmp     byte ptr [rdx], 0
0x180025afd  jz      short loc_180025B18
0x180025aff  cmp     qword ptr [rbx+80h], 0
0x180025b07  mov     ecx, edi
0x180025b09  movzx   eax, byte ptr [rdx+1]
0x180025b0d  setz    cl
0x180025b10  cmp     ecx, eax
0x180025b12  jz      loc_180025A3E
0x180025b18  mov     r9d, 129BDh
0x180025b1e  lea     rcx, a20241207203959+14h; "2aabe05e2e8cae4847a802ee2daddc1d7413d8f"...
0x180025b25  mov     [rsp+68h+var_48], rcx
0x180025b2a  lea     r8, aDatabaseCorrup; "database corruption"
0x180025b31  mov     ecx, 0Bh
0x180025b36  lea     rdx, aSAtLineDOf10s; "%s at line %d of [%.10s]"
0x180025b3d  call    sqlite3_log
0x180025b42  mov     eax, 0Bh
0x180025b47  jmp     loc_180025A5A
0x180025b4c  mov     [rbx+88h], rdi
0x180025b53  mov     byte ptr [rbx], 1
0x180025b56  mov     eax, ebp
0x180025b58  add     rsp, 38h
0x180025b5c  pop     r15
0x180025b5e  pop     r14
0x180025b60  pop     rdi
0x180025b61  pop     rsi
0x180025b62  pop     rbp
0x180025b63  pop     rbx
0x180025b64  retn
0x180025b70  movsx   rax, al
0x180025b74  mov     rcx, [rbx+rax*8+90h]
0x180025b7c  mov     r8, [rcx+70h]
0x180025b80  test    byte ptr [r8+34h], 20h
0x180025b85  jz      short loc_180025BE2
0x180025b87  mov     rcx, [r8+28h]
0x180025b8b  dec     dword ptr [rcx+98h]
0x180025b91  mov     rax, [rcx+0A8h]
0x180025b98  mov     [r8+20h], rax
0x180025b9c  mov     [rcx+0A8h], r8
0x180025ba3  mov     edx, [r8+30h]
0x180025ba7  mov     r8, [r8+8]
0x180025bab  dec     edx
0x180025bad  imul    rdx, [rcx+0C8h]
0x180025bb5  mov     rcx, [rcx+48h]
0x180025bb9  call    sqlite3OsUnfetch
0x180025bbe  movzx   eax, byte ptr [rbx+54h]
0x180025bc2  sub     al, 1
0x180025bc4  mov     [rbx+54h], al
0x180025bc7  jz      loc_180025A30
0x180025bcd  jmp     short loc_180025B70
0x180025bcf  cmp     byte ptr [rdx+8], 0
0x180025bd3  jz      short loc_180025C35
0x180025bd5  mov     byte ptr [rbx], 1
0x180025bd8  mov     esi, 10h
0x180025bdd  jmp     loc_180025A58
0x180025be2  mov     rcx, r8
0x180025be5  call    sqlite3PcacheRelease
0x180025bea  jmp     short loc_180025BBE
0x180025bec  cmp     esi, [r15+4]
0x180025bf0  jz      short loc_180025C15
0x180025bf2  mov     rax, [rcx+8]
0x180025bf6  cmp     esi, 1
0x180025bf9  mov     [r15+50h], rax
0x180025bfd  mov     eax, 64h ; 'd'
0x180025c02  cmovnz  eax, edi
0x180025c05  mov     [r15+70h], rcx
0x180025c09  mov     [r15+9], al
0x180025c0d  mov     [r15+48h], r14
0x180025c11  mov     [r15+4], esi
0x180025c15  mov     rcx, r15
0x180025c18  call    btreeInitPage
0x180025c1d  mov     ebp, eax
0x180025c1f  test    eax, eax
0x180025c21  jz      loc_180025AD8
0x180025c27  mov     rcx, [r15+70h]
0x180025c2b  call    sqlite3PagerUnrefNotNull
0x180025c30  jmp     loc_180025B4C
0x180025c35  cmp     dword ptr [rdx+4], 1
0x180025c39  jz      short loc_180025C6F
0x180025c3b  mov     r9d, 129C9h
0x180025c41  jmp     loc_180025B1E
0x180025c46  mov     byte ptr [rcx], 1
0x180025c49  mov     eax, 10h
0x180025c4e  add     rsp, 38h
0x180025c52  pop     r15
0x180025c54  pop     r14
0x180025c56  pop     rdi
0x180025c57  pop     rsi
0x180025c58  pop     rbp
0x180025c59  pop     rbx
0x180025c5a  retn
0x180025c5b  cmp     al, 4
0x180025c5d  jnz     short loc_180025C94
0x180025c5f  mov     eax, [rcx+4]
0x180025c62  add     rsp, 38h
0x180025c66  pop     r15
0x180025c68  pop     r14
0x180025c6a  pop     rdi
0x180025c6b  pop     rsi
0x180025c6c  pop     rbp
0x180025c6d  pop     rbx
0x180025c6e  retn
0x180025c6f  movzx   ecx, byte ptr [rdx+9]
0x180025c73  mov     rax, [rdx+50h]
0x180025c77  mov     edx, [rcx+rax+8]
0x180025c7b  mov     rcx, rbx
0x180025c7e  bswap   edx
0x180025c80  mov     byte ptr [rbx], 0
0x180025c83  add     rsp, 38h
0x180025c87  pop     r15
0x180025c89  pop     r14
0x180025c8b  pop     rdi
0x180025c8c  pop     rsi
0x180025c8d  pop     rbp
0x180025c8e  pop     rbx
0x180025c8f  jmp     moveToChild
0x180025c94  mov     rcx, [rcx+18h]
0x180025c98  call    sqlite3_free
0x180025c9d  mov     [rbx+18h], rdi
0x180025ca1  mov     byte ptr [rbx], 1
0x180025ca4  jmp     loc_180025A88
0x180025ca9  lea     r8, aDatabaseCorrup; "database corruption"
0x180025cb0  mov     [rbx+88h], rdi
0x180025cb7  mov     edx, 11D57h
0x180025cbc  mov     ecx, 0Bh
0x180025cc1  call    sqlite3ReportError
0x180025cc6  mov     ebp, eax
0x180025cc8  test    eax, eax
0x180025cca  jz      loc_180025ADF
0x180025cd0  jmp     loc_180025B53
```
