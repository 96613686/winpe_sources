# std::_Hash<std::_Umap_traits<DiagHubCommon::LogLevel,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<DiagHubCommon::LogLevel,std::hash<DiagHubCommon::LogLevel>,std::equal_to<DiagHubCommon::LogLevel>>,std::allocator<std::pair<DiagHubCommon::LogLevel const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Rehash_for_1(void)

- ea: `0x14000dc98`
- end: `0x14000dec8`
- name: `?_Rehash_for_1@?$_Hash@V?$_Umap_traits@W4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@W4LogLevel@DiagHubCommon@@U?$hash@W4LogLevel@DiagHubCommon@@@std@@U?$equal_to@W4LogLevel@DiagHubCommon@@@4@@4@V?$allocator@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@IEAAXXZ`
- size: `560`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000cf14`

## callees

- `0x140004b0c`
- `0x14000dc98`
- `0x14000e060`
- `0x140014c4b`

## import_xrefs

- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000dd62`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000dd62`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Rehash_for_1(
        __int64 a1)
{
  __int64 v1; // rdx
  bool v3; // sf
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rbx
  float v6; // xmm0_4
  float v7; // xmm0_4
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rax
  _QWORD *v13; // rbx
  unsigned __int64 v14; // rcx
  __int64 v15; // rdi
  _QWORD *v16; // rax
  _QWORD *i; // rdx
  __int64 v18; // r11
  unsigned __int64 j; // r8
  __int64 v20; // rcx
  __int64 v21; // rdi
  __int64 v22; // r11
  __int64 *v23; // rcx
  int v24; // r8d
  __int64 v25; // r10
  _QWORD *v26; // r9
  _QWORD *v27; // r8
  _QWORD *v28; // rcx
  _QWORD *v29; // r10
  __int64 **v30; // r9
  _QWORD *v31; // r8
  _QWORD *v33; // r10
  _QWORD *v34; // r9
  _QWORD *v35; // r8
  _QWORD *v36; // rcx
  __int64 v37[3]; // [rsp+20h] [rbp-18h] BYREF

  v1 = *(_QWORD *)(a1 + 16);
  v3 = v1 + 1 < 0;
  v4 = v1 + 1;
  v5 = *(_QWORD *)(a1 + 56);
  if ( v3 )
    v6 = (float)(int)(v4 & 1 | (v4 >> 1)) + (float)(int)(v4 & 1 | (v4 >> 1));
  else
    v6 = (float)(int)v4;
  v7 = ceilf_0(v6 / *(float *)a1);
  v8 = 0;
  if ( v7 >= 9.223372e18 )
  {
    v7 = v7 - 9.223372e18;
    if ( v7 < 9.223372e18 )
      v8 = 0x8000000000000000uLL;
  }
  v9 = v8 + (unsigned int)(int)v7;
  v10 = 8;
  if ( v9 > 8 )
    v10 = v9;
  if ( v5 < v10 )
  {
    if ( v5 >= 0x200 || (v5 *= 8LL, v5 < v10) )
      v5 = v10;
  }
  _BitScanReverse64(&v11, 0xFFFFFFFFFFFFFFFuLL);
  if ( v5 > 1LL << v11 )
    std::_Xlength_error("invalid hash bucket count");
  v12 = v5 - 1;
  v13 = *(_QWORD **)(a1 + 8);
  _BitScanReverse64(&v14, v12 | 1);
  v15 = 1LL << ((unsigned __int8)v14 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::_Assign_grow(
    a1 + 24,
    2 * v15,
    v13);
  *(_QWORD *)(a1 + 56) = v15;
  *(_QWORD *)(a1 + 48) = v15 - 1;
  v16 = **(_QWORD ***)(a1 + 8);
  for ( i = v16; i != v13; v16 = i )
  {
    i = (_QWORD *)*i;
    v18 = 0xCBF29CE484222325uLL;
    for ( j = 0; j < 4; ++j )
    {
      v20 = *((unsigned __int8 *)v16 + j + 16);
      v18 = 0x100000001B3LL * (v20 ^ v18);
    }
    v21 = *(_QWORD *)(a1 + 24);
    v22 = 2 * (*(_QWORD *)(a1 + 48) & v18);
    if ( *(_QWORD **)(v21 + 8 * v22) == v13 )
    {
      *(_QWORD *)(v21 + 8 * v22) = v16;
    }
    else
    {
      v23 = *(__int64 **)(v21 + 8 * v22 + 8);
      v24 = *((_DWORD *)v16 + 4);
      if ( v24 != *((_DWORD *)v23 + 4) )
      {
        do
        {
          if ( *(__int64 **)(v21 + 8 * v22) == v23 )
          {
            v29 = (_QWORD *)v16[1];
            *v29 = i;
            v30 = (__int64 **)i[1];
            *v30 = v23;
            v31 = (_QWORD *)v23[1];
            *v31 = v16;
            v23[1] = (__int64)v30;
            i[1] = v29;
            v16[1] = v31;
            *(_QWORD *)(v21 + 8 * v22) = v16;
            goto LABEL_27;
          }
          v23 = (__int64 *)v23[1];
        }
        while ( v24 != *((_DWORD *)v23 + 4) );
        v33 = (_QWORD *)*v23;
        v34 = (_QWORD *)v16[1];
        *v34 = i;
        v35 = (_QWORD *)i[1];
        *v35 = v33;
        v36 = (_QWORD *)v33[1];
        *v36 = v16;
        v33[1] = v35;
        i[1] = v34;
        v16[1] = v36;
        continue;
      }
      v25 = *v23;
      if ( (_QWORD *)*v23 != v16 )
      {
        v26 = (_QWORD *)v16[1];
        *v26 = i;
        v27 = (_QWORD *)i[1];
        *v27 = v25;
        v28 = *(_QWORD **)(v25 + 8);
        *v28 = v16;
        *(_QWORD *)(v25 + 8) = v27;
        i[1] = v26;
        v16[1] = v28;
      }
    }
    *(_QWORD *)(v21 + 8 * v22 + 8) = v16;
LABEL_27:
    ;
  }
  v37[0] = 0;
  return std::_Hash<std::_Umap_traits<enum DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<enum DiagHubCommon::LogLevel,std::hash<enum DiagHubCommon::LogLevel>,std::equal_to<enum DiagHubCommon::LogLevel>>,std::allocator<std::pair<enum DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Clear_guard::~_Clear_guard(
           v37,
           i);
}

```

## disassembly

```asm
0x14000dc98  mov     [rsp+arg_8], rbx
0x14000dc9d  mov     [rsp+arg_10], rsi
0x14000dca2  mov     [rsp+arg_18], rdi
0x14000dca7  push    r14
0x14000dca9  sub     rsp, 30h
0x14000dcad  mov     rdx, [rcx+10h]
0x14000dcb1  mov     rsi, rcx
0x14000dcb4  add     rdx, 1
0x14000dcb8  mov     rbx, [rcx+38h]
0x14000dcbc  xorps   xmm0, xmm0
0x14000dcbf  js      short loc_14000DCC8
0x14000dcc1  cvtsi2ss xmm0, rdx
0x14000dcc6  jmp     short loc_14000DCDD
0x14000dcc8  mov     rax, rdx
0x14000dccb  and     edx, 1
0x14000dcce  shr     rax, 1
0x14000dcd1  or      rax, rdx
0x14000dcd4  cvtsi2ss xmm0, rax
0x14000dcd9  addss   xmm0, xmm0
0x14000dcdd  divss   xmm0, dword ptr [rcx]; X
0x14000dce1  call    ceilf_0
0x14000dce6  movss   xmm1, cs:__real@5f000000
0x14000dcee  xor     ecx, ecx
0x14000dcf0  comiss  xmm0, xmm1
0x14000dcf3  jb      short loc_14000DD0B
0x14000dcf5  subss   xmm0, xmm1
0x14000dcf9  comiss  xmm0, xmm1
0x14000dcfc  jnb     short loc_14000DD0B
0x14000dcfe  mov     rax, 8000000000000000h
0x14000dd08  mov     rcx, rax
0x14000dd0b  cvttss2si rax, xmm0
0x14000dd10  add     rax, rcx
0x14000dd13  mov     ecx, 8
0x14000dd18  cmp     rax, rcx
0x14000dd1b  cmova   rcx, rax
0x14000dd1f  cmp     rbx, rcx
0x14000dd22  jnb     short loc_14000DD40
0x14000dd24  cmp     rbx, 200h
0x14000dd2b  jnb     short loc_14000DD3D
0x14000dd2d  lea     rax, ds:0[rbx*8]
0x14000dd35  mov     rbx, rax
0x14000dd38  cmp     rax, rcx
0x14000dd3b  jnb     short loc_14000DD40
0x14000dd3d  mov     rbx, rcx
0x14000dd40  mov     rax, 0FFFFFFFFFFFFFFFh
0x14000dd4a  bsr     rcx, rax
0x14000dd4e  mov     eax, 1
0x14000dd53  shl     rax, cl
0x14000dd56  cmp     rbx, rax
0x14000dd59  jbe     short loc_14000DD69
0x14000dd5b  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x14000dd62  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x14000dd69  lea     rax, [rbx-1]
0x14000dd6d  mov     edi, 1
0x14000dd72  mov     rbx, [rsi+8]
0x14000dd76  or      rax, 1
0x14000dd7a  bsr     rcx, rax
0x14000dd7e  mov     r8, rbx
0x14000dd81  inc     ecx
0x14000dd83  shl     rdi, cl
0x14000dd86  lea     rcx, [rsi+18h]
0x14000dd8a  lea     rdx, [rdi+rdi]
0x14000dd8e  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>)
0x14000dd93  lea     rax, [rdi-1]
0x14000dd97  mov     [rsi+38h], rdi
0x14000dd9b  mov     [rsi+30h], rax
0x14000dd9f  mov     rax, [rsi+8]
0x14000dda3  mov     rax, [rax]
0x14000dda6  mov     rdx, rax
0x14000dda9  cmp     rax, rbx
0x14000ddac  jz      loc_14000DE79
0x14000ddb2  mov     rdx, [rdx]
0x14000ddb5  mov     r11, 0CBF29CE484222325h
0x14000ddbf  xor     r8d, r8d
0x14000ddc2  movzx   ecx, byte ptr [rax+r8+10h]
0x14000ddc8  mov     r9, 100000001B3h
0x14000ddd2  xor     r11, rcx
0x14000ddd5  inc     r8
0x14000ddd8  imul    r11, r9
0x14000dddc  cmp     r8, 4
0x14000dde0  jb      short loc_14000DDC2
0x14000dde2  and     r11, [rsi+30h]
0x14000dde6  mov     rdi, [rsi+18h]
0x14000ddea  add     r11, r11
0x14000dded  cmp     [rdi+r11*8], rbx
0x14000ddf1  jnz     short loc_14000DDFE
0x14000ddf3  mov     [rdi+r11*8], rax
0x14000ddf7  mov     [rdi+r11*8+8], rax
0x14000ddfc  jmp     short loc_14000DE6D
0x14000ddfe  mov     rcx, [rdi+r11*8+8]
0x14000de03  mov     r8d, [rax+10h]
0x14000de07  cmp     r8d, [rcx+10h]
0x14000de0b  jnz     short loc_14000DE42
0x14000de0d  mov     r10, [rcx]
0x14000de10  cmp     r10, rax
0x14000de13  jz      short loc_14000DDF7
0x14000de15  mov     r9, [rax+8]
0x14000de19  mov     [r9], rdx
0x14000de1c  mov     r8, [rdx+8]
0x14000de20  mov     [r8], r10
0x14000de23  mov     rcx, [r10+8]
0x14000de27  mov     [rcx], rax
0x14000de2a  mov     [r10+8], r8
0x14000de2e  mov     [rdx+8], r9
0x14000de32  mov     [rax+8], rcx
0x14000de36  jmp     short loc_14000DDF7
0x14000de38  mov     rcx, [rcx+8]
0x14000de3c  cmp     r8d, [rcx+10h]
0x14000de40  jz      short loc_14000DEA2
0x14000de42  cmp     [rdi+r11*8], rcx
0x14000de46  jnz     short loc_14000DE38
0x14000de48  mov     r10, [rax+8]
0x14000de4c  mov     [r10], rdx
0x14000de4f  mov     r9, [rdx+8]
0x14000de53  mov     [r9], rcx
0x14000de56  mov     r8, [rcx+8]
0x14000de5a  mov     [r8], rax
0x14000de5d  mov     [rcx+8], r9
0x14000de61  mov     [rdx+8], r10
0x14000de65  mov     [rax+8], r8
0x14000de69  mov     [rdi+r11*8], rax
0x14000de6d  mov     rax, rdx
0x14000de70  cmp     rdx, rbx
0x14000de73  jnz     loc_14000DDB2
0x14000de79  lea     rcx, [rsp+38h+var_18]
0x14000de7e  mov     [rsp+38h+var_18], 0
0x14000de87  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@W4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@W4LogLevel@DiagHubCommon@@U?$hash@W4LogLevel@DiagHubCommon@@@std@@U?$equal_to@W4LogLevel@DiagHubCommon@@@4@@4@V?$allocator@U?$pair@$$CBW4LogLevel@DiagHubCommon@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<DiagHubCommon::LogLevel,std::wstring,std::_Uhash_compare<DiagHubCommon::LogLevel,std::hash<DiagHubCommon::LogLevel>,std::equal_to<DiagHubCommon::LogLevel>>,std::allocator<std::pair<DiagHubCommon::LogLevel const,std::wstring>>,0>>::_Clear_guard::~_Clear_guard(void)
0x14000de8c  mov     rbx, [rsp+38h+arg_8]
0x14000de91  mov     rsi, [rsp+38h+arg_10]
0x14000de96  mov     rdi, [rsp+38h+arg_18]
0x14000de9b  add     rsp, 30h
0x14000de9f  pop     r14
0x14000dea1  retn
0x14000dea2  mov     r10, [rcx]
0x14000dea5  mov     r9, [rax+8]
0x14000dea9  mov     [r9], rdx
0x14000deac  mov     r8, [rdx+8]
0x14000deb0  mov     [r8], r10
0x14000deb3  mov     rcx, [r10+8]
0x14000deb7  mov     [rcx], rax
0x14000deba  mov     [r10+8], r8
0x14000debe  mov     [rdx+8], r9
0x14000dec2  mov     [rax+8], rcx
0x14000dec6  jmp     short loc_14000DE6D
```
