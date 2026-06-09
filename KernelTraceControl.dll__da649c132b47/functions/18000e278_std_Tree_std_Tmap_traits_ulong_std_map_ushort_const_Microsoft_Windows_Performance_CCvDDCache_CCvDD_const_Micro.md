# std::_Tree<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::insert(std::_Tree<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::iterator,std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>> const &)

- ea: `0x18000e278`
- end: `0x18000e4cf`
- name: `?insert@?$_Tree@V?$_Tmap_traits@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AViterator@12@V312@AEBU?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@2@@Z`
- size: `599`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d48c`

## callees

- `0x18000e278`
- `0x18000f0c0`
- `0x180027444`

## pseudocode

```c
__int64 *__fastcall std::_Tree<std::_Tmap_traits<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::insert(
        __int64 a1,
        __int64 *a2,
        __int64 *a3,
        unsigned int *a4)
{
  __int64 *v5; // r14
  __int64 v6; // rbp
  __int64 *v7; // r9
  char v8; // r8
  __int64 **v9; // rsi
  unsigned int v10; // ecx
  __int64 *v11; // r9
  char v12; // r8
  bool v13; // cf
  __int64 *v14; // rax
  __int64 *k; // rax
  __int64 *j; // rdx
  __int64 *v17; // rdi
  __int64 *v18; // rax
  __int64 **v19; // rdi
  __int64 *m; // rax
  __int64 *v21; // rdx
  char v22; // r8
  __int64 *v23; // r9
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 *v26; // rdx
  __int64 v27; // rdx
  __int64 i; // rdx
  uintptr_t Reserved; // [rsp+20h] [rbp-48h]
  char v31; // [rsp+30h] [rbp-38h] BYREF
  char v32; // [rsp+70h] [rbp+8h] BYREF

  v5 = a2;
  v6 = a1;
  if ( !*(_QWORD *)(a1 + 16) )
  {
    Reserved = (uintptr_t)a4;
    v7 = *(__int64 **)(a1 + 8);
LABEL_3:
    v8 = 1;
LABEL_4:
    std::_Tree<std::_Tmap_traits<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Insert(
      a1,
      a2,
      v8,
      v7,
      Reserved);
    return v5;
  }
  v9 = *(__int64 ***)(a1 + 8);
  if ( a3 != *v9 )
  {
    if ( a3 == (__int64 *)v9 )
    {
      v11 = v9[2];
      v10 = *a4;
      if ( *((_DWORD *)v11 + 6) < *a4 )
      {
        v12 = 0;
        goto LABEL_9;
      }
LABEL_48:
      v21 = *(__int64 **)(v6 + 8);
      v22 = 1;
      v23 = v21;
      v24 = v21[1];
      while ( !*(_BYTE *)(v24 + 57) )
      {
        v23 = (__int64 *)v24;
        v22 = v10 < *(_DWORD *)(v24 + 24);
        if ( v10 >= *(_DWORD *)(v24 + 24) )
          v24 = *(_QWORD *)(v24 + 16);
        else
          v24 = *(_QWORD *)v24;
      }
      v25 = (__int64)v23;
      if ( v22 )
      {
        if ( v23 == (__int64 *)*v21 )
        {
          v22 = 1;
          v26 = (__int64 *)&v32;
          goto LABEL_69;
        }
        if ( *((_BYTE *)v23 + 57) )
        {
          v25 = v23[2];
        }
        else
        {
          v27 = *v23;
          if ( *(_BYTE *)(*v23 + 57) )
          {
            for ( i = v23[1]; !*(_BYTE *)(i + 57) && v25 == *(_QWORD *)i; i = *(_QWORD *)(i + 8) )
              v25 = i;
            if ( !*(_BYTE *)(v25 + 57) )
              v25 = i;
          }
          else
          {
            do
            {
              v25 = v27;
              v27 = *(_QWORD *)(v27 + 16);
            }
            while ( !*(_BYTE *)(v27 + 57) );
          }
        }
      }
      if ( *(_DWORD *)(v25 + 24) >= v10 )
      {
LABEL_70:
        *v5 = v25;
        return v5;
      }
      v26 = (__int64 *)&v31;
LABEL_69:
      v25 = *std::_Tree<std::_Tmap_traits<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Insert(
               v6,
               v26,
               v22,
               v23,
               (__int64)a4);
      goto LABEL_70;
    }
    v10 = *a4;
    v13 = *((_DWORD *)a3 + 6) < *a4;
    if ( *((_DWORD *)a3 + 6) > *a4 )
    {
      v14 = a3;
      if ( *((_BYTE *)a3 + 57) )
      {
        v7 = (__int64 *)a3[2];
      }
      else
      {
        v7 = (__int64 *)*a3;
        if ( *(_BYTE *)(*a3 + 57) )
        {
          for ( j = (__int64 *)a3[1]; !*((_BYTE *)j + 57) && v14 == (__int64 *)*j; j = (__int64 *)j[1] )
            v14 = j;
          v7 = v14;
          if ( !*((_BYTE *)v14 + 57) )
            v7 = j;
        }
        else
        {
          for ( k = (__int64 *)v7[2]; !*((_BYTE *)k + 57); k = (__int64 *)k[2] )
            v7 = k;
        }
      }
      if ( *((_DWORD *)v7 + 6) < v10 )
      {
        a2 = v5;
        Reserved = (uintptr_t)a4;
        a1 = v6;
        if ( !*(_BYTE *)(v7[2] + 57) )
        {
          v7 = a3;
          goto LABEL_3;
        }
        goto LABEL_29;
      }
      v13 = *((_DWORD *)a3 + 6) < v10;
    }
    if ( !v13 )
      goto LABEL_48;
    v17 = a3;
    if ( *((_BYTE *)a3 + 57) )
      invalid_parameter(0, 0, 0, 0, 0);
    v18 = (__int64 *)a3[2];
    if ( *((_BYTE *)v18 + 57) )
    {
      for ( m = (__int64 *)a3[1]; !*((_BYTE *)m + 57) && v17 == (__int64 *)m[2]; m = (__int64 *)m[1] )
        v17 = m;
      v19 = (__int64 **)m;
    }
    else
    {
      do
      {
        v19 = (__int64 **)v18;
        v18 = (__int64 *)*v18;
      }
      while ( !*((_BYTE *)v18 + 57) );
    }
    if ( v19 != v9 )
    {
      v10 = *a4;
      if ( *a4 >= *((_DWORD *)v19 + 6) )
        goto LABEL_48;
    }
    a2 = v5;
    Reserved = (uintptr_t)a4;
    a1 = v6;
    if ( !*(_BYTE *)(a3[2] + 57) )
    {
      v7 = (__int64 *)v19;
      goto LABEL_3;
    }
    v7 = a3;
LABEL_29:
    v8 = 0;
    goto LABEL_4;
  }
  v10 = *a4;
  if ( *a4 >= *((_DWORD *)a3 + 6) )
    goto LABEL_48;
  v11 = a3;
  v12 = 1;
LABEL_9:
  std::_Tree<std::_Tmap_traits<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Insert(
    v6,
    a2,
    v12,
    v11,
    (__int64)a4);
  return v5;
}

```

## disassembly

```asm
0x18000e278  mov     [rsp+arg_8], rbx
0x18000e27d  mov     [rsp+arg_10], rbp
0x18000e282  push    rsi
0x18000e283  push    rdi
0x18000e284  push    r12
0x18000e286  push    r14
0x18000e288  push    r15
0x18000e28a  sub     rsp, 40h
0x18000e28e  xor     r12d, r12d
0x18000e291  mov     r15, r9
0x18000e294  mov     rbx, r8
0x18000e297  mov     r14, rdx
0x18000e29a  mov     rbp, rcx
0x18000e29d  cmp     [rcx+10h], r12
0x18000e2a1  jnz     short loc_18000E2B9
0x18000e2a3  mov     [rsp+68h+Reserved], r9
0x18000e2a8  mov     r9, [rcx+8]
0x18000e2ac  mov     r8b, 1
0x18000e2af  call    ?_Insert@?$_Tree@V?$_Tmap_traits@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AViterator@12@_NPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@2@AEBU?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Insert(bool,std::_Tree_nod<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Node *,std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>> const &)
0x18000e2b4  jmp     loc_18000E4B3
0x18000e2b9  mov     rsi, [rcx+8]
0x18000e2bd  cmp     rbx, [rsi]
0x18000e2c0  jnz     short loc_18000E2DF
0x18000e2c2  mov     ecx, [r9]
0x18000e2c5  cmp     ecx, [r8+18h]
0x18000e2c9  jnb     loc_18000E40D
0x18000e2cf  mov     r9, rbx
0x18000e2d2  mov     r8b, 1
0x18000e2d5  mov     [rsp+68h+Reserved], r15
0x18000e2da  mov     rcx, rbp
0x18000e2dd  jmp     short loc_18000E2AF
0x18000e2df  cmp     rbx, rsi
0x18000e2e2  jnz     short loc_18000E2FA
0x18000e2e4  mov     r9, [rsi+10h]
0x18000e2e8  mov     ecx, [r15]
0x18000e2eb  cmp     [r9+18h], ecx
0x18000e2ef  jnb     loc_18000E40D
0x18000e2f5  xor     r8d, r8d
0x18000e2f8  jmp     short loc_18000E2D5
0x18000e2fa  mov     ecx, [r9]
0x18000e2fd  cmp     [r8+18h], ecx
0x18000e301  jbe     short loc_18000E382
0x18000e303  mov     rax, rbx
0x18000e306  cmp     [r8+39h], r12b
0x18000e30a  jz      short loc_18000E312
0x18000e30c  mov     r9, [r8+10h]
0x18000e310  jmp     short loc_18000E353
0x18000e312  mov     r9, [r8]
0x18000e315  cmp     [r9+39h], r12b
0x18000e319  jnz     short loc_18000E330
0x18000e31b  mov     rax, [r9+10h]
0x18000e31f  jmp     short loc_18000E328
0x18000e321  mov     r9, rax
0x18000e324  mov     rax, [rax+10h]
0x18000e328  cmp     [rax+39h], r12b
0x18000e32c  jz      short loc_18000E321
0x18000e32e  jmp     short loc_18000E353
0x18000e330  mov     rdx, [r8+8]
0x18000e334  jmp     short loc_18000E342
0x18000e336  cmp     rax, [rdx]
0x18000e339  jnz     short loc_18000E348
0x18000e33b  mov     rax, rdx
0x18000e33e  mov     rdx, [rdx+8]
0x18000e342  cmp     [rdx+39h], r12b
0x18000e346  jz      short loc_18000E336
0x18000e348  cmp     [rax+39h], r12b
0x18000e34c  mov     r9, rax
0x18000e34f  cmovz   r9, rdx
0x18000e353  cmp     [r9+18h], ecx
0x18000e357  jnb     short loc_18000E37E
0x18000e359  mov     rax, [r9+10h]
0x18000e35d  mov     rdx, r14
0x18000e360  mov     [rsp+68h+Reserved], r15
0x18000e365  mov     rcx, rbp
0x18000e368  cmp     [rax+39h], r12b
0x18000e36c  jz      short loc_18000E376
0x18000e36e  xor     r8d, r8d
0x18000e371  jmp     loc_18000E2AF
0x18000e376  mov     r9, rbx
0x18000e379  jmp     loc_18000E2AC
0x18000e37e  cmp     [r8+18h], ecx
0x18000e382  jnb     loc_18000E40D
0x18000e388  mov     rdi, rbx
0x18000e38b  cmp     [r8+39h], r12b
0x18000e38f  jz      short loc_18000E3A7
0x18000e391  xor     r9d, r9d; LineNo
0x18000e394  mov     [rsp+68h+Reserved], r12; Reserved
0x18000e399  xor     r8d, r8d; FileName
0x18000e39c  xor     edx, edx; FunctionName
0x18000e39e  xor     ecx, ecx; Expression
0x18000e3a0  call    _invalid_parameter
0x18000e3a5  jmp     short loc_18000E3DB
0x18000e3a7  mov     rax, [r8+10h]
0x18000e3ab  cmp     [rax+39h], r12b
0x18000e3af  jnz     short loc_18000E3BF
0x18000e3b1  mov     rdi, rax
0x18000e3b4  mov     rax, [rax]
0x18000e3b7  cmp     [rax+39h], r12b
0x18000e3bb  jz      short loc_18000E3B1
0x18000e3bd  jmp     short loc_18000E3DB
0x18000e3bf  mov     rax, [r8+8]
0x18000e3c3  jmp     short loc_18000E3D2
0x18000e3c5  cmp     rdi, [rax+10h]
0x18000e3c9  jnz     short loc_18000E3D8
0x18000e3cb  mov     rdi, rax
0x18000e3ce  mov     rax, [rax+8]
0x18000e3d2  cmp     [rax+39h], r12b
0x18000e3d6  jz      short loc_18000E3C5
0x18000e3d8  mov     rdi, rax
0x18000e3db  cmp     rdi, rsi
0x18000e3de  jz      short loc_18000E3E8
0x18000e3e0  mov     ecx, [r15]
0x18000e3e3  cmp     ecx, [rdi+18h]
0x18000e3e6  jnb     short loc_18000E40D
0x18000e3e8  mov     rax, [rbx+10h]
0x18000e3ec  mov     rdx, r14
0x18000e3ef  mov     [rsp+68h+Reserved], r15
0x18000e3f4  mov     rcx, rbp
0x18000e3f7  cmp     [rax+39h], r12b
0x18000e3fb  jz      short loc_18000E405
0x18000e3fd  mov     r9, rbx
0x18000e400  jmp     loc_18000E36E
0x18000e405  mov     r9, rdi
0x18000e408  jmp     loc_18000E2AC
0x18000e40d  mov     rdx, [rbp+8]
0x18000e411  mov     r8b, 1
0x18000e414  mov     r9, rdx
0x18000e417  mov     rax, [rdx+8]
0x18000e41b  jmp     short loc_18000E435
0x18000e41d  cmp     ecx, [rax+18h]
0x18000e420  mov     r9, rax
0x18000e423  setb    r8b
0x18000e427  cmp     ecx, [rax+18h]
0x18000e42a  jnb     short loc_18000E431
0x18000e42c  mov     rax, [rax]
0x18000e42f  jmp     short loc_18000E435
0x18000e431  mov     rax, [rax+10h]
0x18000e435  cmp     [rax+39h], r12b
0x18000e439  jz      short loc_18000E41D
0x18000e43b  mov     rax, r9
0x18000e43e  test    r8b, r8b
0x18000e441  jz      short loc_18000E496
0x18000e443  cmp     r9, [rdx]
0x18000e446  jnz     short loc_18000E452
0x18000e448  mov     r8b, 1
0x18000e44b  lea     rdx, [rsp+68h+arg_0]
0x18000e450  jmp     short loc_18000E4A0
0x18000e452  cmp     [r9+39h], r12b
0x18000e456  jz      short loc_18000E45E
0x18000e458  mov     rax, [r9+10h]
0x18000e45c  jmp     short loc_18000E496
0x18000e45e  mov     rdx, [r9]
0x18000e461  cmp     [rdx+39h], r12b
0x18000e465  jnz     short loc_18000E476
0x18000e467  mov     rax, rdx
0x18000e46a  mov     rdx, [rdx+10h]
0x18000e46e  cmp     [rdx+39h], r12b
0x18000e472  jz      short loc_18000E467
0x18000e474  jmp     short loc_18000E496
0x18000e476  mov     rdx, [r9+8]
0x18000e47a  jmp     short loc_18000E488
0x18000e47c  cmp     rax, [rdx]
0x18000e47f  jnz     short loc_18000E48E
0x18000e481  mov     rax, rdx
0x18000e484  mov     rdx, [rdx+8]
0x18000e488  cmp     [rdx+39h], r12b
0x18000e48c  jz      short loc_18000E47C
0x18000e48e  cmp     [rax+39h], r12b
0x18000e492  cmovz   rax, rdx
0x18000e496  cmp     [rax+18h], ecx
0x18000e499  jnb     short loc_18000E4B0
0x18000e49b  lea     rdx, [rsp+68h+var_38]
0x18000e4a0  mov     rcx, rbp
0x18000e4a3  mov     [rsp+68h+Reserved], r15
0x18000e4a8  call    ?_Insert@?$_Tree@V?$_Tmap_traits@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AViterator@12@_NPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@2@AEBU?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Insert(bool,std::_Tree_nod<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Node *,std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>> const &)
0x18000e4ad  mov     rax, [rax]
0x18000e4b0  mov     [r14], rax
0x18000e4b3  lea     r11, [rsp+68h+var_28]
0x18000e4b8  mov     rax, r14
0x18000e4bb  mov     rbx, [r11+38h]
0x18000e4bf  mov     rbp, [r11+40h]
0x18000e4c3  mov     rsp, r11
0x18000e4c6  pop     r15
0x18000e4c8  pop     r14
0x18000e4ca  pop     r12
0x18000e4cc  pop     rdi
0x18000e4cd  pop     rsi
0x18000e4ce  retn
```
