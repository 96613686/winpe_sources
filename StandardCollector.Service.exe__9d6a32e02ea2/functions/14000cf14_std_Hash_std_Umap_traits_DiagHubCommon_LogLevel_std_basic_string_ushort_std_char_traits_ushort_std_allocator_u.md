# std::_Hash<std::_Umap_traits<DiagHubCommon::LogLevel,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<DiagHubCommon::LogLevel,std::hash<DiagHubCommon::LogLevel>,std::equal_to<DiagHubCommon::LogLevel>>,std::allocator<std::pair<DiagHubCommon::LogLevel const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Try_emplace<DiagHubCommon::LogLevel,>(DiagHubCommon::LogLevel &&)

- ea: `0x14000cf14`
- end: `0x14000d102`
- name: `??$_Try_emplace@W4LogLevel@DiagHubCommon@@$$V@?$_Hash@V?$_Umap_traits@W4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@W4LogLevel@DiagHubCommon@@U?$hash@W4LogLevel@DiagHubCommon@@@std@@U?$equal_to@W4LogLevel@DiagHubCommon@@@4@@4@V?$allocator@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@$$QEAW4LogLevel@DiagHubCommon@@@Z`
- size: `494`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000a42c`
- `0x14000b2cc`

## callees

- `0x14000cf14`
- `0x14000dc98`
- `0x140013834`

## import_xrefs

- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000cfbf`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000cfbf`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Try_emplace<enum DiagHubCommon::LogLevel,>(
        __int64 a1,
        __int64 a2,
        _DWORD *a3)
{
  __int64 v6; // rbp
  unsigned __int64 i; // rcx
  __int64 v8; // rdx
  __int64 *v9; // rax
  __int64 *v10; // rsi
  char *v11; // rbx
  __int64 v12; // rcx
  float v13; // xmm0_4
  __int64 v14; // rcx
  float v15; // xmm1_4
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 *v18; // rax
  _QWORD *v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 *v22; // r8

  v6 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 4; ++i )
    v6 = 0x100000001B3LL * (*((unsigned __int8 *)a3 + i) ^ (unsigned __int64)v6);
  v8 = *(_QWORD *)(a1 + 24);
  v9 = *(__int64 **)(v8 + 16 * (v6 & *(_QWORD *)(a1 + 48)) + 8);
  v10 = *(__int64 **)(a1 + 8);
  if ( v9 == v10 )
  {
LABEL_11:
    if ( *(_QWORD *)(a1 + 16) == 0x492492492492492LL )
      std::_Xlength_error("unordered_map/set too long");
    v11 = (char *)operator new(0x38u);
    *((_DWORD *)v11 + 4) = *a3;
    *(_OWORD *)(v11 + 24) = 0;
    *((_QWORD *)v11 + 5) = 0;
    *((_QWORD *)v11 + 6) = 7;
    *((_WORD *)v11 + 12) = 0;
    v12 = *(_QWORD *)(a1 + 16) + 1LL;
    if ( v12 < 0 )
      v13 = (float)(v12 & 1 | (unsigned int)((unsigned __int64)v12 >> 1))
          + (float)(v12 & 1 | (unsigned int)((unsigned __int64)v12 >> 1));
    else
      v13 = (float)(int)v12;
    v14 = *(_QWORD *)(a1 + 56);
    if ( v14 < 0 )
    {
      v16 = *(_QWORD *)(a1 + 56) & 1LL | ((unsigned __int64)v14 >> 1);
      v15 = (float)(int)v16 + (float)(int)v16;
    }
    else
    {
      v15 = (float)(int)v14;
    }
    if ( (float)(v13 / v15) > *(float *)a1 )
    {
      std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Rehash_for_1(a1);
      v17 = *(_QWORD *)(a1 + 24);
      v18 = *(__int64 **)(v17 + 16 * (v6 & *(_QWORD *)(a1 + 48)) + 8);
      v10 = *(__int64 **)(a1 + 8);
      if ( v18 != v10 )
      {
        while ( 1 )
        {
          if ( *((_DWORD *)v11 + 4) == *((_DWORD *)v18 + 4) )
          {
            v10 = (__int64 *)*v18;
            goto LABEL_26;
          }
          if ( v18 == *(__int64 **)(v17 + 16 * (v6 & *(_QWORD *)(a1 + 48))) )
            break;
          v18 = (__int64 *)v18[1];
        }
        v10 = v18;
      }
    }
LABEL_26:
    v19 = (_QWORD *)v10[1];
    ++*(_QWORD *)(a1 + 16);
    *(_QWORD *)v11 = v10;
    *((_QWORD *)v11 + 1) = v19;
    *v19 = v11;
    v10[1] = (__int64)v11;
    v20 = 2 * (v6 & *(_QWORD *)(a1 + 48));
    v21 = *(_QWORD *)(a1 + 24);
    v22 = *(__int64 **)(v21 + 16 * (v6 & *(_QWORD *)(a1 + 48)));
    if ( v22 == *(__int64 **)(a1 + 8) )
    {
      *(_QWORD *)(v21 + 16 * (v6 & *(_QWORD *)(a1 + 48))) = v11;
LABEL_32:
      *(_QWORD *)(v21 + 8 * v20 + 8) = v11;
      goto LABEL_33;
    }
    if ( v22 == v10 )
    {
      *(_QWORD *)(v21 + 16 * (v6 & *(_QWORD *)(a1 + 48))) = v11;
    }
    else if ( *(_QWORD **)(v21 + 16 * (v6 & *(_QWORD *)(a1 + 48)) + 8) == v19 )
    {
      goto LABEL_32;
    }
LABEL_33:
    *(_QWORD *)a2 = v11;
    *(_BYTE *)(a2 + 8) = 1;
    return a2;
  }
  while ( *a3 != *((_DWORD *)v9 + 4) )
  {
    if ( v9 == *(__int64 **)(v8 + 16 * (v6 & *(_QWORD *)(a1 + 48))) )
    {
      v10 = v9;
      goto LABEL_11;
    }
    v9 = (__int64 *)v9[1];
  }
  v10 = (__int64 *)*v9;
  if ( !v9 )
    goto LABEL_11;
  *(_QWORD *)a2 = v9;
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x14000cf14  push    rbx
0x14000cf16  push    rbp
0x14000cf17  push    rsi
0x14000cf18  push    rdi
0x14000cf19  push    r12
0x14000cf1b  push    r14
0x14000cf1d  push    r15
0x14000cf1f  sub     rsp, 30h
0x14000cf23  mov     r15, r8
0x14000cf26  mov     r14, rdx
0x14000cf29  mov     rdi, rcx
0x14000cf2c  mov     rbp, 0CBF29CE484222325h
0x14000cf36  xor     r12d, r12d
0x14000cf39  mov     ecx, r12d
0x14000cf3c  movzx   eax, byte ptr [r8+rcx]
0x14000cf41  xor     rbp, rax
0x14000cf44  mov     rdx, 100000001B3h
0x14000cf4e  imul    rbp, rdx
0x14000cf52  inc     rcx
0x14000cf55  cmp     rcx, 4
0x14000cf59  jb      short loc_14000CF3C
0x14000cf5b  mov     rcx, [rdi+30h]
0x14000cf5f  and     rcx, rbp
0x14000cf62  add     rcx, rcx
0x14000cf65  mov     rdx, [rdi+18h]
0x14000cf69  mov     rax, [rdx+rcx*8+8]
0x14000cf6e  lea     r9, [rdi+8]
0x14000cf72  mov     rsi, [r9]
0x14000cf75  cmp     rax, rsi
0x14000cf78  jz      short loc_14000CFA8
0x14000cf7a  mov     r8, [rdx+rcx*8]
0x14000cf7e  mov     ecx, [r15]
0x14000cf81  jmp     short loc_14000CF8C
0x14000cf83  cmp     rax, r8
0x14000cf86  jz      short loc_14000CFA5
0x14000cf88  mov     rax, [rax+8]
0x14000cf8c  cmp     ecx, [rax+10h]
0x14000cf8f  jnz     short loc_14000CF83
0x14000cf91  mov     rsi, [rax]
0x14000cf94  test    rax, rax
0x14000cf97  jz      short loc_14000CFA8
0x14000cf99  mov     [r14], rax
0x14000cf9c  mov     [r14+8], r12b
0x14000cfa0  jmp     loc_14000D0F0
0x14000cfa5  mov     rsi, rax
0x14000cfa8  mov     rax, 492492492492492h
0x14000cfb2  cmp     [rdi+10h], rax
0x14000cfb6  jnz     short loc_14000CFC6
0x14000cfb8  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x14000cfbf  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x14000cfc6  mov     [rsp+68h+var_48], r9
0x14000cfcb  mov     [rsp+68h+var_40], r12
0x14000cfd0  mov     ecx, 38h ; '8'; Size
0x14000cfd5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000cfda  mov     rbx, rax
0x14000cfdd  mov     [rsp+68h+var_40], rax
0x14000cfe2  mov     ecx, [r15]
0x14000cfe5  mov     [rax+10h], ecx
0x14000cfe8  xorps   xmm0, xmm0
0x14000cfeb  movups  xmmword ptr [rax+18h], xmm0
0x14000cfef  mov     [rax+28h], r12
0x14000cff3  mov     qword ptr [rax+30h], 7
0x14000cffb  mov     [rax+18h], r12w
0x14000d000  mov     rcx, [rdi+10h]
0x14000d004  add     rcx, 1
0x14000d008  xorps   xmm0, xmm0
0x14000d00b  js      short loc_14000D014
0x14000d00d  cvtsi2ss xmm0, rcx
0x14000d012  jmp     short loc_14000D029
0x14000d014  mov     rax, rcx
0x14000d017  shr     rax, 1
0x14000d01a  and     ecx, 1
0x14000d01d  or      rax, rcx
0x14000d020  cvtsi2ss xmm0, rax
0x14000d025  addss   xmm0, xmm0
0x14000d029  mov     rcx, [rdi+38h]
0x14000d02d  xorps   xmm1, xmm1
0x14000d030  test    rcx, rcx
0x14000d033  js      short loc_14000D03C
0x14000d035  cvtsi2ss xmm1, rcx
0x14000d03a  jmp     short loc_14000D051
0x14000d03c  mov     rax, rcx
0x14000d03f  shr     rax, 1
0x14000d042  and     ecx, 1
0x14000d045  or      rax, rcx
0x14000d048  cvtsi2ss xmm1, rax
0x14000d04d  addss   xmm1, xmm1
0x14000d051  divss   xmm0, xmm1
0x14000d055  comiss  xmm0, dword ptr [rdi]
0x14000d058  jbe     short loc_14000D098
0x14000d05a  mov     rcx, rdi
0x14000d05d  call    ?_Rehash_for_1@?$_Hash@V?$_Umap_traits@W4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@W4LogLevel@DiagHubCommon@@U?$hash@W4LogLevel@DiagHubCommon@@@std@@U?$equal_to@W4LogLevel@DiagHubCommon@@@4@@4@V?$allocator@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Umap_traits<DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<DiagHubCommon::LogLevel,std::hash<DiagHubCommon::LogLevel>,std::equal_to<DiagHubCommon::LogLevel>>,std::allocator<std::pair<DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Rehash_for_1(void)
0x14000d062  mov     rcx, [rdi+30h]
0x14000d066  and     rcx, rbp
0x14000d069  add     rcx, rcx
0x14000d06c  mov     rdx, [rdi+18h]
0x14000d070  mov     rax, [rdx+rcx*8+8]
0x14000d075  mov     rsi, [rdi+8]
0x14000d079  cmp     rax, rsi
0x14000d07c  jz      short loc_14000D098
0x14000d07e  mov     r8, [rdx+rcx*8]
0x14000d082  mov     ecx, [rbx+10h]
0x14000d085  jmp     short loc_14000D090
0x14000d087  cmp     rax, r8
0x14000d08a  jz      short loc_14000D0CC
0x14000d08c  mov     rax, [rax+8]
0x14000d090  cmp     ecx, [rax+10h]
0x14000d093  jnz     short loc_14000D087
0x14000d095  mov     rsi, [rax]
0x14000d098  mov     rdx, [rsi+8]
0x14000d09c  inc     qword ptr [rdi+10h]
0x14000d0a0  mov     [rbx], rsi
0x14000d0a3  mov     [rbx+8], rdx
0x14000d0a7  mov     [rdx], rbx
0x14000d0aa  mov     [rsi+8], rbx
0x14000d0ae  mov     rax, [rdi+30h]
0x14000d0b2  and     rax, rbp
0x14000d0b5  add     rax, rax
0x14000d0b8  mov     rcx, [rdi+18h]
0x14000d0bc  mov     r8, [rcx+rax*8]
0x14000d0c0  cmp     r8, [rdi+8]
0x14000d0c4  jnz     short loc_14000D0D1
0x14000d0c6  mov     [rcx+rax*8], rbx
0x14000d0ca  jmp     short loc_14000D0E3
0x14000d0cc  mov     rsi, rax
0x14000d0cf  jmp     short loc_14000D098
0x14000d0d1  cmp     r8, rsi
0x14000d0d4  jnz     short loc_14000D0DC
0x14000d0d6  mov     [rcx+rax*8], rbx
0x14000d0da  jmp     short loc_14000D0E8
0x14000d0dc  cmp     [rcx+rax*8+8], rdx
0x14000d0e1  jnz     short loc_14000D0E8
0x14000d0e3  mov     [rcx+rax*8+8], rbx
0x14000d0e8  mov     [r14], rbx
0x14000d0eb  mov     byte ptr [r14+8], 1
0x14000d0f0  mov     rax, r14
0x14000d0f3  add     rsp, 30h
0x14000d0f7  pop     r15
0x14000d0f9  pop     r14
0x14000d0fb  pop     r12
0x14000d0fd  pop     rdi
0x14000d0fe  pop     rsi
0x14000d0ff  pop     rbp
0x14000d100  pop     rbx
0x14000d101  retn
```
