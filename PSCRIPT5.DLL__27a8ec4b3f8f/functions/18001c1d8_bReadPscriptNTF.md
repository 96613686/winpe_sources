# bReadPscriptNTF

- ea: `0x18001c1d8`
- end: `0x18001c625`
- name: `bReadPscriptNTF`
- size: `1101`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18001b8b0`

## callees

- `0x18001bef8`
- `0x18001bf98`
- `0x18001c1d8`
- `0x18001c790`
- `0x18001c88c`
- `0x18001cbec`
- `0x180020074`
- `0x1800203e8`
- `0x18002061c`
- `0x18005e094`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001c5c9`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001c5e5`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001c5c9`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001c5e5`
- `KERNEL32!LocalFree` at `0x18001c283`
- `KERNEL32!LocalFree` at `0x18001c505`
- `KERNEL32!LocalFree` at `0x18001c523`
- `KERNEL32!LocalFree` at `0x18001c537`
- `KERNEL32!LocalFree` at `0x18001c551`
- `KERNEL32!LocalFree` at `0x18001c283`
- `KERNEL32!LocalFree` at `0x18001c505`
- `KERNEL32!LocalFree` at `0x18001c523`
- `KERNEL32!LocalFree` at `0x18001c537`
- `KERNEL32!LocalFree` at `0x18001c551`
- `KERNEL32!LocalAlloc` at `0x18001c243`
- `KERNEL32!LocalAlloc` at `0x18001c266`
- `KERNEL32!LocalAlloc` at `0x18001c243`
- `KERNEL32!LocalAlloc` at `0x18001c266`

## pseudocode

```c
__int64 __fastcall bReadPscriptNTF(__int64 a1)
{
  __int64 v1; // rbx
  int v3; // eax
  HLOCAL v5; // rax
  size_t v6; // rdx
  STRSAFE_LPSTR *v7; // r9
  char *v8; // r12
  void *v9; // rcx
  _QWORD *v10; // r14
  int v11; // r13d
  unsigned int v12; // ecx
  unsigned int *v13; // rdi
  const char *v14; // r8
  _DWORD *v15; // r15
  const char *v16; // rdi
  int v17; // r14d
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // r15d
  __int64 v22; // rdi
  unsigned int *v23; // rax
  __int64 v24; // rax
  _QWORD *v25; // rcx
  void *v26; // rcx
  int v27; // edi
  size_t *v28; // [rsp+20h] [rbp-68h]
  DWORD v29; // [rsp+28h] [rbp-60h]
  unsigned int *v30; // [rsp+30h] [rbp-58h]
  _QWORD *v31; // [rsp+38h] [rbp-50h]
  int v32; // [rsp+90h] [rbp+8h]
  int v33; // [rsp+98h] [rbp+10h]
  int v34; // [rsp+A0h] [rbp+18h]
  __int64 v35; // [rsp+A8h] [rbp+20h] BYREF

  v1 = *(_QWORD *)(a1 + 3656);
  *(_DWORD *)(v1 + 16) = 0;
  *(_QWORD *)(v1 + 32) = 0;
  *(_DWORD *)(v1 + 56) = 0;
  *(_QWORD *)(v1 + 72) = 0;
  v3 = *(_DWORD *)(*(_QWORD *)(a1 + 2144) + 188LL);
  v34 = v3;
  if ( v3 <= 0 )
    return 1;
  v5 = LocalAlloc(0x40u, 48 * v3);
  *(_QWORD *)(v1 + 32) = v5;
  if ( !v5 )
    return 0;
  v8 = (char *)LocalAlloc(0x40u, 0xA0u);
  if ( !v8 )
  {
    v9 = *(void **)(v1 + 32);
    if ( v9 )
      LocalFree(v9);
    *(_QWORD *)(v1 + 32) = 0;
    return 0;
  }
  v10 = (_QWORD *)(a1 + 2128);
  v11 = 0;
  v31 = (_QWORD *)(a1 + 2128);
  v12 = *(_DWORD *)(*(_QWORD *)(a1 + 2144) + 192LL);
  if ( v12 )
  {
    v13 = (unsigned int *)(*v10 + v12);
  }
  else
  {
    v13 = 0;
    v31 = (_QWORD *)(a1 + 2128);
  }
  v30 = v13;
  v33 = 0;
  while ( 1 )
  {
    if ( *v13 )
      v14 = (const char *)(*v10 + *v13);
    else
      v14 = 0;
    StringCchCopyExA(v8, v6, v14, v7, v28, v29);
    if ( v13[2] )
      v15 = (_DWORD *)(*v10 + v13[2]);
    else
      v15 = 0;
    if ( v13[3] )
      v16 = (const char *)(*v10 + v13[3]);
    else
      v16 = 0;
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 2144) + 20LL) >= 0xBC2u && v16 )
    {
      if ( !strcmp_0(v16, "Standard") )
      {
        v17 = 1;
      }
      else if ( !strcmp_0(v16, "Special") )
      {
        v17 = 2;
      }
      else
      {
        v17 = strcmp_0(v16, "ExtendedRoman") == 0 ? 3 : 0;
      }
    }
    else
    {
      v17 = 0;
    }
    v32 = 0;
    if ( !v15 || !v16 )
    {
      while ( 1 )
      {
LABEL_39:
        v18 = *(_QWORD *)(v1 + 40);
        if ( v18 )
        {
          v19 = NTFFindEntry(v18, *(_DWORD *)(v1 + 20), v8, (int *)&v35);
          if ( v19 )
          {
            v20 = NTFGetEntryData(a1, v19, 0);
            if ( !v20 )
              goto LABEL_65;
            if ( v17 )
            {
              if ( *(_DWORD *)(v20 + 64) == v17 )
                goto LABEL_44;
            }
            else if ( *(_DWORD *)(v20 + 64) != 3 )
            {
              goto LABEL_44;
            }
          }
        }
        v21 = *(_DWORD *)(a1 + 3592);
        v22 = 0;
        if ( v21 > 0 )
        {
          while ( 1 )
          {
            v35 = *(_QWORD *)(*(_QWORD *)(a1 + 8 * v22 + 3600) + 16LL);
            v23 = (unsigned int *)NTFFindFontMtxEntry(v35, v8, v17);
            if ( v23 )
              break;
            v22 = (unsigned int)(v22 + 1);
            if ( (int)v22 >= v21 )
              goto LABEL_53;
          }
          if ( !(unsigned int)bStoreEntryData(v35, v23, *(_QWORD *)(v1 + 32), v11, v22) )
          {
            v25 = *(_QWORD **)(v1 + 32);
            if ( v11 )
            {
              vFreePSFontEntry(v25, v11);
            }
            else if ( v25 )
            {
              LocalFree(v25);
            }
            *(_DWORD *)(v1 + 16) = 0;
            *(_QWORD *)(v1 + 32) = 0;
LABEL_65:
            LocalFree(v8);
            return 0;
          }
          ++v11;
        }
LABEL_53:
        if ( (int)v22 >= *(_DWORD *)(a1 + 3592) && v17 == 3 )
        {
          v17 = 1;
        }
        else
        {
          if ( !v32 )
            goto LABEL_44;
          v24 = -1;
          do
            ++v24;
          while ( v8[v24] );
          v8[v24 - 1] = 86;
          v32 = 0;
        }
      }
    }
    if ( *v15 == 1246972754 )
    {
      if ( *(_DWORD *)v16 != 1987064632 )
        goto LABEL_39;
    }
    else if ( *v15 != 1987064632 || *(_DWORD *)v16 != 1651467329 )
    {
      goto LABEL_39;
    }
    if ( !(unsigned int)b90msSupported(a1, v8) )
    {
      v32 = 1;
      goto LABEL_39;
    }
LABEL_44:
    v13 = v30 + 6;
    v30 += 6;
    if ( ++v33 >= v34 )
      break;
    v10 = v31;
  }
  LocalFree(v8);
  if ( v11 )
  {
    v27 = 0;
    *(_DWORD *)(v1 + 16) = v11;
    if ( *(int *)(a1 + 3592) > 0 )
    {
      while ( pCreateGlyphSetEntry(
                *(_QWORD *)(*(_QWORD *)(a1 + 8LL * v27 + 3600) + 16LL),
                v27 + 11,
                (int *)(v1 + 56),
                (const void **)(v1 + 72)) )
      {
        if ( ++v27 >= *(_DWORD *)(a1 + 3592) )
          goto LABEL_73;
      }
      vFreePSFontEntry(*(_QWORD **)(v1 + 32), *(_DWORD *)(v1 + 16));
      *(_QWORD *)(v1 + 32) = 0;
      *(_DWORD *)(v1 + 16) = 0;
      return 0;
    }
LABEL_73:
    qsort(*(void **)(v1 + 32), *(int *)(v1 + 16), 0x30u, (_CoreCrtNonSecureSearchSortCompareFunction)compare);
    qsort(*(void **)(v1 + 72), *(int *)(v1 + 56), 0x30u, (_CoreCrtNonSecureSearchSortCompareFunction)compare);
  }
  else
  {
    v26 = *(void **)(v1 + 32);
    if ( v26 )
      LocalFree(v26);
    *(_DWORD *)(v1 + 16) = 0;
    *(_QWORD *)(v1 + 32) = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18001c1d8  push    rbx
0x18001c1da  push    rbp
0x18001c1db  push    rsi
0x18001c1dc  push    rdi
0x18001c1dd  push    r12
0x18001c1df  push    r13
0x18001c1e1  push    r14
0x18001c1e3  push    r15
0x18001c1e5  sub     rsp, 48h
0x18001c1e9  mov     rbx, [rcx+0E48h]
0x18001c1f0  mov     rbp, rcx
0x18001c1f3  mov     dword ptr [rbx+10h], 0
0x18001c1fa  mov     qword ptr [rbx+20h], 0
0x18001c202  mov     dword ptr [rbx+38h], 0
0x18001c209  mov     qword ptr [rbx+48h], 0
0x18001c211  mov     rax, [rcx+860h]
0x18001c218  mov     eax, [rax+0BCh]
0x18001c21e  mov     [rsp+88h+arg_10], eax
0x18001c225  test    eax, eax
0x18001c227  jg      short loc_18001C233
0x18001c229  mov     eax, 1
0x18001c22e  jmp     loc_18001C5F3
0x18001c233  lea     eax, [rax+rax*2]
0x18001c236  mov     edi, 40h ; '@'
0x18001c23b  shl     eax, 4
0x18001c23e  mov     ecx, edi; uFlags
0x18001c240  movsxd  rdx, eax; uBytes
0x18001c243  call    cs:__imp_LocalAlloc
0x18001c24a  nop     dword ptr [rax+rax+00h]
0x18001c24f  mov     [rbx+20h], rax
0x18001c253  test    rax, rax
0x18001c256  jnz     short loc_18001C25F
0x18001c258  xor     eax, eax
0x18001c25a  jmp     loc_18001C5F3
0x18001c25f  mov     edx, 0A0h; uBytes
0x18001c264  mov     ecx, edi; uFlags
0x18001c266  call    cs:__imp_LocalAlloc
0x18001c26d  nop     dword ptr [rax+rax+00h]
0x18001c272  mov     r12, rax
0x18001c275  test    rax, rax
0x18001c278  jnz     short loc_18001C299
0x18001c27a  mov     rcx, [rbx+20h]; hMem
0x18001c27e  test    rcx, rcx
0x18001c281  jz      short loc_18001C28F
0x18001c283  call    cs:__imp_LocalFree
0x18001c28a  nop     dword ptr [rax+rax+00h]
0x18001c28f  mov     qword ptr [rbx+20h], 0
0x18001c297  jmp     short loc_18001C258
0x18001c299  mov     rax, [rbp+860h]
0x18001c2a0  lea     r14, [rbp+850h]
0x18001c2a7  xor     r13d, r13d
0x18001c2aa  mov     [rsp+88h+var_50], r14
0x18001c2af  mov     ecx, [rax+0C0h]
0x18001c2b5  test    ecx, ecx
0x18001c2b7  jz      short loc_18001C2C0
0x18001c2b9  mov     edi, ecx
0x18001c2bb  add     rdi, [r14]
0x18001c2be  jmp     short loc_18001C2C7
0x18001c2c0  xor     edi, edi
0x18001c2c2  mov     [rsp+88h+var_50], r14
0x18001c2c7  xor     eax, eax
0x18001c2c9  mov     [rsp+88h+var_58], rdi
0x18001c2ce  mov     [rsp+88h+arg_8], eax
0x18001c2d5  lea     esi, [rax+1]
0x18001c2d8  cmp     dword ptr [rdi], 0
0x18001c2db  jz      short loc_18001C2E5
0x18001c2dd  mov     r8d, [rdi]
0x18001c2e0  add     r8, [r14]
0x18001c2e3  jmp     short loc_18001C2E8
0x18001c2e5  xor     r8d, r8d; pszSrc
0x18001c2e8  mov     rcx, r12; pszDest
0x18001c2eb  call    StringCchCopyExA
0x18001c2f0  cmp     dword ptr [rdi+8], 0
0x18001c2f4  jz      short loc_18001C2FF
0x18001c2f6  mov     r15d, [rdi+8]
0x18001c2fa  add     r15, [r14]
0x18001c2fd  jmp     short loc_18001C302
0x18001c2ff  xor     r15d, r15d
0x18001c302  cmp     dword ptr [rdi+0Ch], 0
0x18001c306  jz      short loc_18001C310
0x18001c308  mov     edi, [rdi+0Ch]
0x18001c30b  add     rdi, [r14]
0x18001c30e  jmp     short loc_18001C312
0x18001c310  xor     edi, edi
0x18001c312  mov     rax, [rbp+860h]
0x18001c319  cmp     dword ptr [rax+14h], 0BC2h
0x18001c320  jb      short loc_18001C375
0x18001c322  test    rdi, rdi
0x18001c325  jz      short loc_18001C375
0x18001c327  lea     rdx, aStandard; "Standard"
0x18001c32e  mov     rcx, rdi; Str1
0x18001c331  call    strcmp_0
0x18001c336  test    eax, eax
0x18001c338  jnz     short loc_18001C33F
0x18001c33a  mov     r14d, esi
0x18001c33d  jmp     short loc_18001C378
0x18001c33f  lea     rdx, aSpecial; "Special"
0x18001c346  mov     rcx, rdi; Str1
0x18001c349  call    strcmp_0
0x18001c34e  test    eax, eax
0x18001c350  jnz     short loc_18001C358
0x18001c352  lea     r14d, [rax+2]
0x18001c356  jmp     short loc_18001C378
0x18001c358  lea     rdx, aExtendedroman; "ExtendedRoman"
0x18001c35f  mov     rcx, rdi; Str1
0x18001c362  call    strcmp_0
0x18001c367  neg     eax
0x18001c369  sbb     r14d, r14d
0x18001c36c  not     r14d
0x18001c36f  and     r14d, 3
0x18001c373  jmp     short loc_18001C378
0x18001c375  xor     r14d, r14d
0x18001c378  mov     [rsp+88h+arg_0], 0
0x18001c383  test    r15, r15
0x18001c386  jz      short loc_18001C3C7
0x18001c388  test    rdi, rdi
0x18001c38b  jz      short loc_18001C3C7
0x18001c38d  cmp     dword ptr [r15], 4A534B52h
0x18001c394  jnz     short loc_18001C3A0
0x18001c396  cmp     dword ptr [rdi], 76703338h
0x18001c39c  jz      short loc_18001C3B1
0x18001c39e  jmp     short loc_18001C3C7
0x18001c3a0  cmp     dword ptr [r15], 76703338h
0x18001c3a7  jnz     short loc_18001C3C7
0x18001c3a9  cmp     dword ptr [rdi], 626F6441h
0x18001c3af  jnz     short loc_18001C3C7
0x18001c3b1  mov     rdx, r12
0x18001c3b4  mov     rcx, rbp
0x18001c3b7  call    b90msSupported
0x18001c3bc  test    eax, eax
0x18001c3be  jnz     short loc_18001C40A
0x18001c3c0  mov     [rsp+88h+arg_0], esi
0x18001c3c7  mov     rcx, [rbx+28h]
0x18001c3cb  test    rcx, rcx
0x18001c3ce  jz      short loc_18001C445
0x18001c3d0  mov     edx, [rbx+14h]
0x18001c3d3  lea     r9, [rsp+88h+arg_18]
0x18001c3db  mov     r8, r12
0x18001c3de  call    NTFFindEntry
0x18001c3e3  test    rax, rax
0x18001c3e6  jz      short loc_18001C445
0x18001c3e8  xor     r8d, r8d
0x18001c3eb  mov     rdx, rax
0x18001c3ee  mov     rcx, rbp
0x18001c3f1  call    NTFGetEntryData
0x18001c3f6  test    rax, rax
0x18001c3f9  jz      loc_18001C520
0x18001c3ff  test    r14d, r14d
0x18001c402  jz      short loc_18001C43F
0x18001c404  cmp     [rax+40h], r14d
0x18001c408  jnz     short loc_18001C445
0x18001c40a  mov     rdi, [rsp+88h+var_58]
0x18001c40f  mov     eax, [rsp+88h+arg_8]
0x18001c416  add     rdi, 18h
0x18001c41a  add     eax, esi
0x18001c41c  mov     [rsp+88h+var_58], rdi
0x18001c421  mov     [rsp+88h+arg_8], eax
0x18001c428  cmp     eax, [rsp+88h+arg_10]
0x18001c42f  jge     loc_18001C534
0x18001c435  mov     r14, [rsp+88h+var_50]
0x18001c43a  jmp     loc_18001C2D8
0x18001c43f  cmp     dword ptr [rax+40h], 3
0x18001c443  jnz     short loc_18001C40A
0x18001c445  mov     r15d, [rbp+0E08h]
0x18001c44c  xor     edi, edi
0x18001c44e  test    r15d, r15d
0x18001c451  jle     short loc_18001C4A5
0x18001c453  mov     rcx, [rbp+rdi*8+0E10h]
0x18001c45b  mov     r8d, r14d
0x18001c45e  mov     rdx, r12
0x18001c461  mov     rax, [rcx+10h]
0x18001c465  mov     rcx, rax
0x18001c468  mov     [rsp+88h+arg_18], rax
0x18001c470  call    NTFFindFontMtxEntry
0x18001c475  test    rax, rax
0x18001c478  jnz     short loc_18001C483
0x18001c47a  add     edi, esi
0x18001c47c  cmp     edi, r15d
0x18001c47f  jl      short loc_18001C453
0x18001c481  jmp     short loc_18001C4A5
0x18001c483  mov     r8, [rbx+20h]
0x18001c487  mov     r9d, r13d
0x18001c48a  mov     rcx, [rsp+88h+arg_18]
0x18001c492  mov     rdx, rax
0x18001c495  mov     dword ptr [rsp+88h+var_68], edi
0x18001c499  call    bStoreEntryData
0x18001c49e  test    eax, eax
0x18001c4a0  jz      short loc_18001C4ED
0x18001c4a2  add     r13d, esi
0x18001c4a5  cmp     edi, [rbp+0E08h]
0x18001c4ab  jl      short loc_18001C4BB
0x18001c4ad  cmp     r14d, 3
0x18001c4b1  jnz     short loc_18001C4BB
0x18001c4b3  mov     r14d, esi
0x18001c4b6  jmp     loc_18001C3C7
0x18001c4bb  cmp     [rsp+88h+arg_0], 0
0x18001c4c3  jz      loc_18001C40A
0x18001c4c9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c4cd  inc     rax
0x18001c4d0  cmp     byte ptr [r12+rax], 0
0x18001c4d5  jnz     short loc_18001C4CD
0x18001c4d7  mov     byte ptr [rax+r12-1], 56h ; 'V'
0x18001c4dd  mov     [rsp+88h+arg_0], 0
0x18001c4e8  jmp     loc_18001C3C7
0x18001c4ed  mov     rcx, [rbx+20h]; hMem
0x18001c4f1  test    r13d, r13d
0x18001c4f4  jz      short loc_18001C500
0x18001c4f6  mov     edx, r13d
0x18001c4f9  call    vFreePSFontEntry
0x18001c4fe  jmp     short loc_18001C511
0x18001c500  test    rcx, rcx
0x18001c503  jz      short loc_18001C511
0x18001c505  call    cs:__imp_LocalFree
0x18001c50c  nop     dword ptr [rax+rax+00h]
0x18001c511  mov     dword ptr [rbx+10h], 0
0x18001c518  mov     qword ptr [rbx+20h], 0
0x18001c520  mov     rcx, r12; hMem
0x18001c523  call    cs:__imp_LocalFree
0x18001c52a  nop     dword ptr [rax+rax+00h]
0x18001c52f  jmp     loc_18001C258
0x18001c534  mov     rcx, r12; hMem
0x18001c537  call    cs:__imp_LocalFree
0x18001c53e  nop     dword ptr [rax+rax+00h]
0x18001c543  test    r13d, r13d
0x18001c546  jnz     short loc_18001C571
0x18001c548  mov     rcx, [rbx+20h]; hMem
0x18001c54c  test    rcx, rcx
0x18001c54f  jz      short loc_18001C55D
0x18001c551  call    cs:__imp_LocalFree
0x18001c558  nop     dword ptr [rax+rax+00h]
0x18001c55d  mov     dword ptr [rbx+10h], 0
0x18001c564  mov     qword ptr [rbx+20h], 0
0x18001c56c  jmp     loc_18001C5F1
0x18001c571  xor     edi, edi
0x18001c573  mov     [rbx+10h], r13d
0x18001c577  lea     r14, [rbx+38h]
0x18001c57b  lea     r15, [rbx+48h]
0x18001c57f  cmp     [rbp+0E08h], edi
0x18001c585  jle     short loc_18001C5B2
0x18001c587  movsxd  rax, edi
0x18001c58a  lea     edx, [rdi+0Bh]
0x18001c58d  mov     r9, r15
0x18001c590  mov     r8, r14
0x18001c593  mov     rcx, [rbp+rax*8+0E10h]
0x18001c59b  mov     rcx, [rcx+10h]
0x18001c59f  call    pCreateGlyphSetEntry
0x18001c5a4  test    al, al
0x18001c5a6  jz      short loc_18001C605
0x18001c5a8  add     edi, esi
0x18001c5aa  cmp     edi, [rbp+0E08h]
0x18001c5b0  jl      short loc_18001C587
0x18001c5b2  movsxd  rdx, dword ptr [rbx+10h]; NumOfElements
0x18001c5b6  lea     r9, compare; CompareFunction
0x18001c5bd  mov     rcx, [rbx+20h]; Base
0x18001c5c1  mov     edi, 30h ; '0'
0x18001c5c6  mov     r8d, edi; SizeOfElements
0x18001c5c9  call    cs:__imp_qsort
0x18001c5d0  nop     dword ptr [rax+rax+00h]
0x18001c5d5  movsxd  rdx, dword ptr [r14]; NumOfElements
0x18001c5d8  lea     r9, compare; CompareFunction
0x18001c5df  mov     rcx, [r15]; Base
0x18001c5e2  mov     r8d, edi; SizeOfElements
0x18001c5e5  call    cs:__imp_qsort
0x18001c5ec  nop     dword ptr [rax+rax+00h]
0x18001c5f1  mov     eax, esi
0x18001c5f3  add     rsp, 48h
0x18001c5f7  pop     r15
0x18001c5f9  pop     r14
0x18001c5fb  pop     r13
0x18001c5fd  pop     r12
0x18001c5ff  pop     rdi
0x18001c600  pop     rsi
0x18001c601  pop     rbp
0x18001c602  pop     rbx
0x18001c603  retn
0x18001c605  mov     edx, [rbx+10h]
0x18001c608  mov     rcx, [rbx+20h]; hMem
0x18001c60c  call    vFreePSFontEntry
0x18001c611  mov     qword ptr [rbx+20h], 0
0x18001c619  mov     dword ptr [rbx+10h], 0
0x18001c620  jmp     loc_18001C258
```
