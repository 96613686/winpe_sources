# std::_Hash<std::_Umap_traits<PayloadType,std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>>,std::_Uhash_compare<PayloadType,std::hash<PayloadType>,std::equal_to<PayloadType>>,std::allocator<std::pair<PayloadType const,std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>>>>,0>>::emplace<std::pair<PayloadType,std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>>>>(std::pair<PayloadType,std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>>> &&)

- ea: `0x18000fd14`
- end: `0x18000ff21`
- name: `??$emplace@U?$pair@W4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@@?$_Hash@V?$_Umap_traits@W4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@V?$_Uhash_compare@W4PayloadType@@U?$hash@W4PayloadType@@@std@@U?$equal_to@W4PayloadType@@@3@@3@V?$allocator@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@1@@Z`
- size: `525`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010094`

## callees

- `0x180003544`
- `0x18000fd14`
- `0x1800211f0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000fdb2`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000fdb2`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<enum PayloadType,std::vector<CbsLanguageFeature>,std::_Uhash_compare<enum PayloadType,std::hash<enum PayloadType>,std::equal_to<enum PayloadType>>,std::allocator<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>,0>>::emplace<std::pair<enum PayloadType,std::vector<CbsLanguageFeature>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rbp
  unsigned __int64 i; // rcx
  __int64 v8; // r8
  __int64 *v9; // rcx
  __int64 **v10; // r12
  __int64 *v11; // rsi
  _DWORD *v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rcx
  float v17; // xmm0_4
  __int64 v18; // rcx
  float v19; // xmm1_4
  __int64 v20; // rax
  __int64 v21; // r8
  __int64 *v22; // rcx
  _QWORD *v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 *v26; // r8

  v6 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 4; ++i )
    v6 = 0x100000001B3LL * (*(unsigned __int8 *)(a3 + i) ^ (unsigned __int64)v6);
  v8 = *(_QWORD *)(a1 + 24);
  v9 = *(__int64 **)(v8 + 16 * (*(_QWORD *)(a1 + 48) & v6) + 8);
  v10 = (__int64 **)(a1 + 8);
  v11 = *(__int64 **)(a1 + 8);
  if ( v9 == v11 )
  {
LABEL_8:
    if ( *(_QWORD *)(a1 + 16) == 0x555555555555555LL )
      std::_Xlength_error("unordered_map/set too long");
    v12 = operator new(0x30u);
    v12[4] = *(_DWORD *)a3;
    v13 = *(_QWORD *)(a3 + 24);
    *(_QWORD *)(a3 + 24) = 0;
    v14 = *(_QWORD *)(a3 + 16);
    *(_QWORD *)(a3 + 16) = 0;
    v15 = *(_QWORD *)(a3 + 8);
    *(_QWORD *)(a3 + 8) = 0;
    *((_QWORD *)v12 + 3) = v15;
    *((_QWORD *)v12 + 4) = v14;
    *((_QWORD *)v12 + 5) = v13;
    v16 = *(_QWORD *)(a1 + 16) + 1LL;
    if ( v16 < 0 )
      v17 = (float)(v16 & 1 | (unsigned int)((unsigned __int64)v16 >> 1))
          + (float)(v16 & 1 | (unsigned int)((unsigned __int64)v16 >> 1));
    else
      v17 = (float)(int)v16;
    v18 = *(_QWORD *)(a1 + 56);
    if ( v18 < 0 )
    {
      v20 = *(_QWORD *)(a1 + 56) & 1LL | ((unsigned __int64)v18 >> 1);
      v19 = (float)(int)v20 + (float)(int)v20;
    }
    else
    {
      v19 = (float)(int)v18;
    }
    if ( (float)(v17 / v19) > *(float *)a1 )
    {
      std::_Hash<std::_Umap_traits<enum PayloadType,std::vector<CbsLanguageFeature>,std::_Uhash_compare<enum PayloadType,std::hash<enum PayloadType>,std::equal_to<enum PayloadType>>,std::allocator<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>,0>>::_Rehash_for_1(a1);
      v21 = *(_QWORD *)(a1 + 24);
      v22 = *(__int64 **)(v21 + 16 * (*(_QWORD *)(a1 + 48) & v6) + 8);
      v11 = *v10;
      if ( v22 != *v10 )
      {
        while ( v12[4] != *((_DWORD *)v22 + 4) )
        {
          if ( v22 == *(__int64 **)(v21 + 16 * (*(_QWORD *)(a1 + 48) & v6)) )
          {
            v11 = v22;
            goto LABEL_23;
          }
          v22 = (__int64 *)v22[1];
        }
        v11 = (__int64 *)*v22;
      }
    }
LABEL_23:
    v23 = (_QWORD *)v11[1];
    ++*(_QWORD *)(a1 + 16);
    *(_QWORD *)v12 = v11;
    *((_QWORD *)v12 + 1) = v23;
    *v23 = v12;
    v11[1] = (__int64)v12;
    v24 = *(_QWORD *)(a1 + 24);
    v25 = 2 * (v6 & *(_QWORD *)(a1 + 48));
    v26 = *(__int64 **)(v24 + 16 * (v6 & *(_QWORD *)(a1 + 48)));
    if ( v26 == *v10 )
    {
      *(_QWORD *)(v24 + 16 * (v6 & *(_QWORD *)(a1 + 48))) = v12;
LABEL_28:
      *(_QWORD *)(v24 + 8 * v25 + 8) = v12;
      goto LABEL_29;
    }
    if ( v26 == v11 )
    {
      *(_QWORD *)(v24 + 16 * (v6 & *(_QWORD *)(a1 + 48))) = v12;
    }
    else if ( *(_QWORD **)(v24 + 16 * (v6 & *(_QWORD *)(a1 + 48)) + 8) == v23 )
    {
      goto LABEL_28;
    }
LABEL_29:
    *(_QWORD *)a2 = v12;
    *(_BYTE *)(a2 + 8) = 1;
    return a2;
  }
  while ( *(_DWORD *)a3 != *((_DWORD *)v9 + 4) )
  {
    if ( v9 == *(__int64 **)(v8 + 16 * (*(_QWORD *)(a1 + 48) & v6)) )
    {
      v11 = v9;
      goto LABEL_8;
    }
    v9 = (__int64 *)v9[1];
  }
  *(_QWORD *)a2 = v9;
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x18000fd14  push    rbx
0x18000fd16  push    rbp
0x18000fd17  push    rsi
0x18000fd18  push    rdi
0x18000fd19  push    r12
0x18000fd1b  push    r14
0x18000fd1d  push    r15
0x18000fd1f  sub     rsp, 30h
0x18000fd23  mov     r15, r8
0x18000fd26  mov     r14, rdx
0x18000fd29  mov     rdi, rcx
0x18000fd2c  mov     rbp, 0CBF29CE484222325h
0x18000fd36  xor     ecx, ecx
0x18000fd38  movzx   eax, byte ptr [r8+rcx]
0x18000fd3d  xor     rbp, rax
0x18000fd40  mov     rdx, 100000001B3h
0x18000fd4a  imul    rbp, rdx
0x18000fd4e  inc     rcx
0x18000fd51  cmp     rcx, 4
0x18000fd55  jb      short loc_18000FD38
0x18000fd57  mov     rdx, rbp
0x18000fd5a  and     rdx, [rdi+30h]
0x18000fd5e  mov     r8, [rdi+18h]
0x18000fd62  mov     rax, rdx
0x18000fd65  add     rax, rax
0x18000fd68  mov     rcx, [r8+rax*8+8]
0x18000fd6d  lea     r12, [rdi+8]
0x18000fd71  mov     rsi, [r12]
0x18000fd75  cmp     rcx, rsi
0x18000fd78  jz      short loc_18000FD9B
0x18000fd7a  add     rdx, rdx
0x18000fd7d  mov     rax, [r8+rdx*8]
0x18000fd81  mov     edx, [r15]
0x18000fd84  cmp     edx, [rcx+10h]
0x18000fd87  jz      loc_18000FF07
0x18000fd8d  cmp     rcx, rax
0x18000fd90  jz      short loc_18000FD98
0x18000fd92  mov     rcx, [rcx+8]
0x18000fd96  jmp     short loc_18000FD84
0x18000fd98  mov     rsi, rcx
0x18000fd9b  mov     rax, 555555555555555h
0x18000fda5  cmp     [rdi+10h], rax
0x18000fda9  jnz     short loc_18000FDB9
0x18000fdab  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18000fdb2  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000fdb9  mov     [rsp+68h+var_48], r12
0x18000fdbe  mov     [rsp+68h+var_40], 0
0x18000fdc7  mov     ecx, 30h ; '0'; Size
0x18000fdcc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fdd1  mov     rbx, rax
0x18000fdd4  mov     [rsp+68h+var_40], rax
0x18000fdd9  mov     eax, [r15]
0x18000fddc  mov     [rbx+10h], eax
0x18000fddf  mov     rdx, [r15+18h]
0x18000fde3  mov     qword ptr [r15+18h], 0
0x18000fdeb  mov     rcx, [r15+10h]
0x18000fdef  mov     qword ptr [r15+10h], 0
0x18000fdf7  mov     rax, [r15+8]
0x18000fdfb  mov     qword ptr [r15+8], 0
0x18000fe03  mov     [rbx+18h], rax
0x18000fe07  mov     [rbx+20h], rcx
0x18000fe0b  mov     [rbx+28h], rdx
0x18000fe0f  mov     rcx, [rdi+10h]
0x18000fe13  add     rcx, 1
0x18000fe17  xorps   xmm0, xmm0
0x18000fe1a  js      short loc_18000FE23
0x18000fe1c  cvtsi2ss xmm0, rcx
0x18000fe21  jmp     short loc_18000FE38
0x18000fe23  mov     rax, rcx
0x18000fe26  shr     rax, 1
0x18000fe29  and     ecx, 1
0x18000fe2c  or      rax, rcx
0x18000fe2f  cvtsi2ss xmm0, rax
0x18000fe34  addss   xmm0, xmm0
0x18000fe38  mov     rcx, [rdi+38h]
0x18000fe3c  xorps   xmm1, xmm1
0x18000fe3f  test    rcx, rcx
0x18000fe42  js      short loc_18000FE4B
0x18000fe44  cvtsi2ss xmm1, rcx
0x18000fe49  jmp     short loc_18000FE60
0x18000fe4b  mov     rax, rcx
0x18000fe4e  shr     rax, 1
0x18000fe51  and     ecx, 1
0x18000fe54  or      rax, rcx
0x18000fe57  cvtsi2ss xmm1, rax
0x18000fe5c  addss   xmm1, xmm1
0x18000fe60  divss   xmm0, xmm1
0x18000fe64  comiss  xmm0, dword ptr [rdi]
0x18000fe67  jbe     short loc_18000FEB2
0x18000fe69  mov     rcx, rdi
0x18000fe6c  call    ?_Rehash_for_1@?$_Hash@V?$_Umap_traits@W4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@V?$_Uhash_compare@W4PayloadType@@U?$hash@W4PayloadType@@@std@@U?$equal_to@W4PayloadType@@@3@@3@V?$allocator@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@@3@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Umap_traits<PayloadType,std::vector<CbsLanguageFeature>,std::_Uhash_compare<PayloadType,std::hash<PayloadType>,std::equal_to<PayloadType>>,std::allocator<std::pair<PayloadType const,std::vector<CbsLanguageFeature>>>,0>>::_Rehash_for_1(void)
0x18000fe71  mov     rdx, rbp
0x18000fe74  and     rdx, [rdi+30h]
0x18000fe78  mov     r8, [rdi+18h]
0x18000fe7c  mov     rax, rdx
0x18000fe7f  add     rax, rax
0x18000fe82  mov     rcx, [r8+rax*8+8]
0x18000fe87  mov     rsi, [r12]
0x18000fe8b  cmp     rcx, rsi
0x18000fe8e  jz      short loc_18000FEB2
0x18000fe90  add     rdx, rdx
0x18000fe93  mov     rax, [r8+rdx*8]
0x18000fe97  mov     edx, [rbx+10h]
0x18000fe9a  cmp     edx, [rcx+10h]
0x18000fe9d  jz      short loc_18000FEAF
0x18000fe9f  cmp     rcx, rax
0x18000fea2  jz      short loc_18000FEAA
0x18000fea4  mov     rcx, [rcx+8]
0x18000fea8  jmp     short loc_18000FE9A
0x18000feaa  mov     rsi, rcx
0x18000fead  jmp     short loc_18000FEB2
0x18000feaf  mov     rsi, [rcx]
0x18000feb2  mov     rdx, [rsi+8]
0x18000feb6  inc     qword ptr [rdi+10h]
0x18000feba  mov     [rbx], rsi
0x18000febd  mov     [rbx+8], rdx
0x18000fec1  mov     [rdx], rbx
0x18000fec4  mov     [rsi+8], rbx
0x18000fec8  mov     rcx, [rdi+18h]
0x18000fecc  mov     rax, [rdi+30h]
0x18000fed0  and     rax, rbp
0x18000fed3  add     rax, rax
0x18000fed6  mov     r8, [rcx+rax*8]
0x18000feda  cmp     r8, [r12]
0x18000fede  jnz     short loc_18000FEE6
0x18000fee0  mov     [rcx+rax*8], rbx
0x18000fee4  jmp     short loc_18000FEF8
0x18000fee6  cmp     r8, rsi
0x18000fee9  jnz     short loc_18000FEF1
0x18000feeb  mov     [rcx+rax*8], rbx
0x18000feef  jmp     short loc_18000FEFD
0x18000fef1  cmp     [rcx+rax*8+8], rdx
0x18000fef6  jnz     short loc_18000FEFD
0x18000fef8  mov     [rcx+rax*8+8], rbx
0x18000fefd  mov     [r14], rbx
0x18000ff00  mov     byte ptr [r14+8], 1
0x18000ff05  jmp     short loc_18000FF0F
0x18000ff07  mov     [r14], rcx
0x18000ff0a  mov     byte ptr [r14+8], 0
0x18000ff0f  mov     rax, r14
0x18000ff12  add     rsp, 30h
0x18000ff16  pop     r15
0x18000ff18  pop     r14
0x18000ff1a  pop     r12
0x18000ff1c  pop     rdi
0x18000ff1d  pop     rsi
0x18000ff1e  pop     rbp
0x18000ff1f  pop     rbx
0x18000ff20  retn
```
