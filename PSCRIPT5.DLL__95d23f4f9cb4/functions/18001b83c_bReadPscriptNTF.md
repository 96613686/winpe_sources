# bReadPscriptNTF

- ea: `0x18001b83c`
- end: `0x18001bc4f`
- name: `bReadPscriptNTF`
- size: `1043`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18001af6c`

## callees

- `0x18001b574`
- `0x18001b610`
- `0x18001b83c`
- `0x18001bda0`
- `0x18001be9c`
- `0x18001c1e0`
- `0x18001f4c8`
- `0x18001f838`
- `0x18001fa6c`
- `0x18005c404`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001bc00`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001bc16`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001bc00`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18001bc16`
- `KERNEL32!LocalFree` at `0x18001b8db`
- `KERNEL32!LocalFree` at `0x18001bb57`
- `KERNEL32!LocalFree` at `0x18001bb6f`
- `KERNEL32!LocalFree` at `0x18001bb7d`
- `KERNEL32!LocalFree` at `0x18001bb91`
- `KERNEL32!LocalFree` at `0x18001b8db`
- `KERNEL32!LocalFree` at `0x18001bb57`
- `KERNEL32!LocalFree` at `0x18001bb6f`
- `KERNEL32!LocalFree` at `0x18001bb7d`
- `KERNEL32!LocalFree` at `0x18001bb91`
- `KERNEL32!LocalAlloc` at `0x18001b8a7`
- `KERNEL32!LocalAlloc` at `0x18001b8c4`
- `KERNEL32!LocalAlloc` at `0x18001b8a7`
- `KERNEL32!LocalAlloc` at `0x18001b8c4`

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
  unsigned int v17; // r14d
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // r15d
  __int64 v22; // rdi
  __int64 v23; // rax
  __int64 v24; // rax
  void *v25; // rcx
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
          v19 = NTFFindEntry(v18, *(unsigned int *)(v1 + 20), v8, &v35);
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
            v23 = NTFFindFontMtxEntry(v35, v8, v17);
            if ( v23 )
              break;
            v22 = (unsigned int)(v22 + 1);
            if ( (int)v22 >= v21 )
              goto LABEL_53;
          }
          if ( !(unsigned int)bStoreEntryData(v35, v23, *(_QWORD *)(v1 + 32), v11, v22) )
          {
            v25 = *(void **)(v1 + 32);
            if ( v11 )
            {
              vFreePSFontEntry(v25);
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
      while ( (unsigned __int8)pCreateGlyphSetEntry(
                                 *(_QWORD *)(*(_QWORD *)(a1 + 8LL * v27 + 3600) + 16LL),
                                 (unsigned int)(v27 + 11),
                                 v1 + 56,
                                 v1 + 72) )
      {
        if ( ++v27 >= *(_DWORD *)(a1 + 3592) )
          goto LABEL_73;
      }
      vFreePSFontEntry(*(HLOCAL *)(v1 + 32));
      *(_QWORD *)(v1 + 32) = 0;
      *(_DWORD *)(v1 + 16) = 0;
      return 0;
    }
LABEL_73:
    qsort(*(void **)(v1 + 32), *(int *)(v1 + 16), 0x30u, compare);
    qsort(*(void **)(v1 + 72), *(int *)(v1 + 56), 0x30u, compare);
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
0x18001b83c  push    rbx
0x18001b83e  push    rbp
0x18001b83f  push    rsi
0x18001b840  push    rdi
0x18001b841  push    r12
0x18001b843  push    r13
0x18001b845  push    r14
0x18001b847  push    r15
0x18001b849  sub     rsp, 48h
0x18001b84d  mov     rbx, [rcx+0E48h]
0x18001b854  mov     rbp, rcx
0x18001b857  mov     dword ptr [rbx+10h], 0
0x18001b85e  mov     qword ptr [rbx+20h], 0
0x18001b866  mov     dword ptr [rbx+38h], 0
0x18001b86d  mov     qword ptr [rbx+48h], 0
0x18001b875  mov     rax, [rcx+860h]
0x18001b87c  mov     eax, [rax+0BCh]
0x18001b882  mov     [rsp+88h+arg_10], eax
0x18001b889  test    eax, eax
0x18001b88b  jg      short loc_18001B897
0x18001b88d  mov     eax, 1
0x18001b892  jmp     loc_18001BC1E
0x18001b897  lea     eax, [rax+rax*2]
0x18001b89a  mov     edi, 40h ; '@'
0x18001b89f  shl     eax, 4
0x18001b8a2  mov     ecx, edi; uFlags
0x18001b8a4  movsxd  rdx, eax; uBytes
0x18001b8a7  call    cs:__imp_LocalAlloc
0x18001b8ad  mov     [rbx+20h], rax
0x18001b8b1  test    rax, rax
0x18001b8b4  jnz     short loc_18001B8BD
0x18001b8b6  xor     eax, eax
0x18001b8b8  jmp     loc_18001BC1E
0x18001b8bd  mov     edx, 0A0h; uBytes
0x18001b8c2  mov     ecx, edi; uFlags
0x18001b8c4  call    cs:__imp_LocalAlloc
0x18001b8ca  mov     r12, rax
0x18001b8cd  test    rax, rax
0x18001b8d0  jnz     short loc_18001B8EB
0x18001b8d2  mov     rcx, [rbx+20h]; hMem
0x18001b8d6  test    rcx, rcx
0x18001b8d9  jz      short loc_18001B8E1
0x18001b8db  call    cs:__imp_LocalFree
0x18001b8e1  mov     qword ptr [rbx+20h], 0
0x18001b8e9  jmp     short loc_18001B8B6
0x18001b8eb  mov     rax, [rbp+860h]
0x18001b8f2  lea     r14, [rbp+850h]
0x18001b8f9  xor     r13d, r13d
0x18001b8fc  mov     [rsp+88h+var_50], r14
0x18001b901  mov     ecx, [rax+0C0h]
0x18001b907  test    ecx, ecx
0x18001b909  jz      short loc_18001B912
0x18001b90b  mov     edi, ecx
0x18001b90d  add     rdi, [r14]
0x18001b910  jmp     short loc_18001B919
0x18001b912  xor     edi, edi
0x18001b914  mov     [rsp+88h+var_50], r14
0x18001b919  xor     eax, eax
0x18001b91b  mov     [rsp+88h+var_58], rdi
0x18001b920  mov     [rsp+88h+arg_8], eax
0x18001b927  lea     esi, [rax+1]
0x18001b92a  cmp     dword ptr [rdi], 0
0x18001b92d  jz      short loc_18001B937
0x18001b92f  mov     r8d, [rdi]
0x18001b932  add     r8, [r14]
0x18001b935  jmp     short loc_18001B93A
0x18001b937  xor     r8d, r8d; pszSrc
0x18001b93a  mov     rcx, r12; pszDest
0x18001b93d  call    StringCchCopyExA
0x18001b942  cmp     dword ptr [rdi+8], 0
0x18001b946  jz      short loc_18001B951
0x18001b948  mov     r15d, [rdi+8]
0x18001b94c  add     r15, [r14]
0x18001b94f  jmp     short loc_18001B954
0x18001b951  xor     r15d, r15d
0x18001b954  cmp     dword ptr [rdi+0Ch], 0
0x18001b958  jz      short loc_18001B962
0x18001b95a  mov     edi, [rdi+0Ch]
0x18001b95d  add     rdi, [r14]
0x18001b960  jmp     short loc_18001B964
0x18001b962  xor     edi, edi
0x18001b964  mov     rax, [rbp+860h]
0x18001b96b  cmp     dword ptr [rax+14h], 0BC2h
0x18001b972  jb      short loc_18001B9C7
0x18001b974  test    rdi, rdi
0x18001b977  jz      short loc_18001B9C7
0x18001b979  lea     rdx, aStandard; "Standard"
0x18001b980  mov     rcx, rdi; Str1
0x18001b983  call    strcmp_0
0x18001b988  test    eax, eax
0x18001b98a  jnz     short loc_18001B991
0x18001b98c  mov     r14d, esi
0x18001b98f  jmp     short loc_18001B9CA
0x18001b991  lea     rdx, aSpecial; "Special"
0x18001b998  mov     rcx, rdi; Str1
0x18001b99b  call    strcmp_0
0x18001b9a0  test    eax, eax
0x18001b9a2  jnz     short loc_18001B9AA
0x18001b9a4  lea     r14d, [rax+2]
0x18001b9a8  jmp     short loc_18001B9CA
0x18001b9aa  lea     rdx, aExtendedroman; "ExtendedRoman"
0x18001b9b1  mov     rcx, rdi; Str1
0x18001b9b4  call    strcmp_0
0x18001b9b9  neg     eax
0x18001b9bb  sbb     r14d, r14d
0x18001b9be  not     r14d
0x18001b9c1  and     r14d, 3
0x18001b9c5  jmp     short loc_18001B9CA
0x18001b9c7  xor     r14d, r14d
0x18001b9ca  mov     [rsp+88h+arg_0], 0
0x18001b9d5  test    r15, r15
0x18001b9d8  jz      short loc_18001BA19
0x18001b9da  test    rdi, rdi
0x18001b9dd  jz      short loc_18001BA19
0x18001b9df  cmp     dword ptr [r15], 4A534B52h
0x18001b9e6  jnz     short loc_18001B9F2
0x18001b9e8  cmp     dword ptr [rdi], 76703338h
0x18001b9ee  jz      short loc_18001BA03
0x18001b9f0  jmp     short loc_18001BA19
0x18001b9f2  cmp     dword ptr [r15], 76703338h
0x18001b9f9  jnz     short loc_18001BA19
0x18001b9fb  cmp     dword ptr [rdi], 626F6441h
0x18001ba01  jnz     short loc_18001BA19
0x18001ba03  mov     rdx, r12
0x18001ba06  mov     rcx, rbp
0x18001ba09  call    b90msSupported
0x18001ba0e  test    eax, eax
0x18001ba10  jnz     short loc_18001BA5C
0x18001ba12  mov     [rsp+88h+arg_0], esi
0x18001ba19  mov     rcx, [rbx+28h]
0x18001ba1d  test    rcx, rcx
0x18001ba20  jz      short loc_18001BA97
0x18001ba22  mov     edx, [rbx+14h]
0x18001ba25  lea     r9, [rsp+88h+arg_18]
0x18001ba2d  mov     r8, r12
0x18001ba30  call    NTFFindEntry
0x18001ba35  test    rax, rax
0x18001ba38  jz      short loc_18001BA97
0x18001ba3a  xor     r8d, r8d
0x18001ba3d  mov     rdx, rax
0x18001ba40  mov     rcx, rbp
0x18001ba43  call    NTFGetEntryData
0x18001ba48  test    rax, rax
0x18001ba4b  jz      loc_18001BB6C
0x18001ba51  test    r14d, r14d
0x18001ba54  jz      short loc_18001BA91
0x18001ba56  cmp     [rax+40h], r14d
0x18001ba5a  jnz     short loc_18001BA97
0x18001ba5c  mov     rdi, [rsp+88h+var_58]
0x18001ba61  mov     eax, [rsp+88h+arg_8]
0x18001ba68  add     rdi, 18h
0x18001ba6c  add     eax, esi
0x18001ba6e  mov     [rsp+88h+var_58], rdi
0x18001ba73  mov     [rsp+88h+arg_8], eax
0x18001ba7a  cmp     eax, [rsp+88h+arg_10]
0x18001ba81  jge     loc_18001BB7A
0x18001ba87  mov     r14, [rsp+88h+var_50]
0x18001ba8c  jmp     loc_18001B92A
0x18001ba91  cmp     dword ptr [rax+40h], 3
0x18001ba95  jnz     short loc_18001BA5C
0x18001ba97  mov     r15d, [rbp+0E08h]
0x18001ba9e  xor     edi, edi
0x18001baa0  test    r15d, r15d
0x18001baa3  jle     short loc_18001BAF7
0x18001baa5  mov     rcx, [rbp+rdi*8+0E10h]
0x18001baad  mov     r8d, r14d
0x18001bab0  mov     rdx, r12
0x18001bab3  mov     rax, [rcx+10h]
0x18001bab7  mov     rcx, rax
0x18001baba  mov     [rsp+88h+arg_18], rax
0x18001bac2  call    NTFFindFontMtxEntry
0x18001bac7  test    rax, rax
0x18001baca  jnz     short loc_18001BAD5
0x18001bacc  add     edi, esi
0x18001bace  cmp     edi, r15d
0x18001bad1  jl      short loc_18001BAA5
0x18001bad3  jmp     short loc_18001BAF7
0x18001bad5  mov     r8, [rbx+20h]
0x18001bad9  mov     r9d, r13d
0x18001badc  mov     rcx, [rsp+88h+arg_18]
0x18001bae4  mov     rdx, rax
0x18001bae7  mov     dword ptr [rsp+88h+var_68], edi
0x18001baeb  call    bStoreEntryData
0x18001baf0  test    eax, eax
0x18001baf2  jz      short loc_18001BB3F
0x18001baf4  add     r13d, esi
0x18001baf7  cmp     edi, [rbp+0E08h]
0x18001bafd  jl      short loc_18001BB0D
0x18001baff  cmp     r14d, 3
0x18001bb03  jnz     short loc_18001BB0D
0x18001bb05  mov     r14d, esi
0x18001bb08  jmp     loc_18001BA19
0x18001bb0d  cmp     [rsp+88h+arg_0], 0
0x18001bb15  jz      loc_18001BA5C
0x18001bb1b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001bb1f  inc     rax
0x18001bb22  cmp     byte ptr [r12+rax], 0
0x18001bb27  jnz     short loc_18001BB1F
0x18001bb29  mov     byte ptr [rax+r12-1], 56h ; 'V'
0x18001bb2f  mov     [rsp+88h+arg_0], 0
0x18001bb3a  jmp     loc_18001BA19
0x18001bb3f  mov     rcx, [rbx+20h]; hMem
0x18001bb43  test    r13d, r13d
0x18001bb46  jz      short loc_18001BB52
0x18001bb48  mov     edx, r13d
0x18001bb4b  call    vFreePSFontEntry
0x18001bb50  jmp     short loc_18001BB5D
0x18001bb52  test    rcx, rcx
0x18001bb55  jz      short loc_18001BB5D
0x18001bb57  call    cs:__imp_LocalFree
0x18001bb5d  mov     dword ptr [rbx+10h], 0
0x18001bb64  mov     qword ptr [rbx+20h], 0
0x18001bb6c  mov     rcx, r12; hMem
0x18001bb6f  call    cs:__imp_LocalFree
0x18001bb75  jmp     loc_18001B8B6
0x18001bb7a  mov     rcx, r12; hMem
0x18001bb7d  call    cs:__imp_LocalFree
0x18001bb83  test    r13d, r13d
0x18001bb86  jnz     short loc_18001BBA8
0x18001bb88  mov     rcx, [rbx+20h]; hMem
0x18001bb8c  test    rcx, rcx
0x18001bb8f  jz      short loc_18001BB97
0x18001bb91  call    cs:__imp_LocalFree
0x18001bb97  mov     dword ptr [rbx+10h], 0
0x18001bb9e  mov     qword ptr [rbx+20h], 0
0x18001bba6  jmp     short loc_18001BC1C
0x18001bba8  xor     edi, edi
0x18001bbaa  mov     [rbx+10h], r13d
0x18001bbae  lea     r14, [rbx+38h]
0x18001bbb2  lea     r15, [rbx+48h]
0x18001bbb6  cmp     [rbp+0E08h], edi
0x18001bbbc  jle     short loc_18001BBE9
0x18001bbbe  movsxd  rax, edi
0x18001bbc1  lea     edx, [rdi+0Bh]
0x18001bbc4  mov     r9, r15
0x18001bbc7  mov     r8, r14
0x18001bbca  mov     rcx, [rbp+rax*8+0E10h]
0x18001bbd2  mov     rcx, [rcx+10h]
0x18001bbd6  call    pCreateGlyphSetEntry
0x18001bbdb  test    al, al
0x18001bbdd  jz      short loc_18001BC2F
0x18001bbdf  add     edi, esi
0x18001bbe1  cmp     edi, [rbp+0E08h]
0x18001bbe7  jl      short loc_18001BBBE
0x18001bbe9  movsxd  rdx, dword ptr [rbx+10h]; NumOfElements
0x18001bbed  lea     r9, compare; CompareFunction
0x18001bbf4  mov     rcx, [rbx+20h]; Base
0x18001bbf8  mov     edi, 30h ; '0'
0x18001bbfd  mov     r8d, edi; SizeOfElements
0x18001bc00  call    cs:__imp_qsort
0x18001bc06  movsxd  rdx, dword ptr [r14]; NumOfElements
0x18001bc09  lea     r9, compare; CompareFunction
0x18001bc10  mov     rcx, [r15]; Base
0x18001bc13  mov     r8d, edi; SizeOfElements
0x18001bc16  call    cs:__imp_qsort
0x18001bc1c  mov     eax, esi
0x18001bc1e  add     rsp, 48h
0x18001bc22  pop     r15
0x18001bc24  pop     r14
0x18001bc26  pop     r13
0x18001bc28  pop     r12
0x18001bc2a  pop     rdi
0x18001bc2b  pop     rsi
0x18001bc2c  pop     rbp
0x18001bc2d  pop     rbx
0x18001bc2e  retn
0x18001bc2f  mov     edx, [rbx+10h]
0x18001bc32  mov     rcx, [rbx+20h]; hMem
0x18001bc36  call    vFreePSFontEntry
0x18001bc3b  mov     qword ptr [rbx+20h], 0
0x18001bc43  mov     dword ptr [rbx+10h], 0
0x18001bc4a  jmp     loc_18001B8B6
```
