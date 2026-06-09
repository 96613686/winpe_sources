# std::_Hash<std::_Umap_traits<uint,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>,0>>::_Rehash_for_1(void)

- ea: `0x140011634`
- end: `0x140011854`
- name: `?_Rehash_for_1@?$_Hash@V?$_Umap_traits@IUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@5@$0A@@std@@@std@@IEAAXXZ`
- size: `544`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400113e8`

## callees

- `0x140004b0c`
- `0x140011634`
- `0x140014c4b`

## import_xrefs

- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x1400116fe`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x1400116fe`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<unsigned int,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>,0>>::_Rehash_for_1(
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
  _QWORD *result; // rax
  _QWORD *i; // rdx
  __int64 v18; // r8
  unsigned __int64 j; // r9
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
  _QWORD *v32; // r10
  _QWORD *v33; // r9
  _QWORD *v34; // r8
  _QWORD *v35; // rcx

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
  result = **(_QWORD ***)(a1 + 8);
  for ( i = result; i != v13; result = i )
  {
    i = (_QWORD *)*i;
    v18 = 0xCBF29CE484222325uLL;
    for ( j = 0; j < 4; ++j )
    {
      v20 = *((unsigned __int8 *)result + j + 16);
      v18 = 0x100000001B3LL * (v20 ^ v18);
    }
    v21 = *(_QWORD *)(a1 + 24);
    v22 = 2 * (v18 & *(_QWORD *)(a1 + 48));
    if ( *(_QWORD **)(v21 + 16 * (v18 & *(_QWORD *)(a1 + 48))) == v13 )
    {
      *(_QWORD *)(v21 + 16 * (v18 & *(_QWORD *)(a1 + 48))) = result;
    }
    else
    {
      v23 = *(__int64 **)(v21 + 16 * (v18 & *(_QWORD *)(a1 + 48)) + 8);
      v24 = *((_DWORD *)result + 4);
      if ( v24 != *((_DWORD *)v23 + 4) )
      {
        do
        {
          if ( *(__int64 **)(v21 + 8 * v22) == v23 )
          {
            v29 = (_QWORD *)result[1];
            *v29 = i;
            v30 = (__int64 **)i[1];
            *v30 = v23;
            v31 = (_QWORD *)v23[1];
            *v31 = result;
            v23[1] = (__int64)v30;
            i[1] = v29;
            result[1] = v31;
            *(_QWORD *)(v21 + 8 * v22) = result;
            goto LABEL_27;
          }
          v23 = (__int64 *)v23[1];
        }
        while ( v24 != *((_DWORD *)v23 + 4) );
        v32 = (_QWORD *)*v23;
        v33 = (_QWORD *)result[1];
        *v33 = i;
        v34 = (_QWORD *)i[1];
        *v34 = v32;
        v35 = (_QWORD *)v32[1];
        *v35 = result;
        v32[1] = v34;
        i[1] = v33;
        result[1] = v35;
        continue;
      }
      v25 = *v23;
      if ( (_QWORD *)*v23 != result )
      {
        v26 = (_QWORD *)result[1];
        *v26 = i;
        v27 = (_QWORD *)i[1];
        *v27 = v25;
        v28 = *(_QWORD **)(v25 + 8);
        *v28 = result;
        *(_QWORD *)(v25 + 8) = v27;
        i[1] = v26;
        result[1] = v28;
      }
    }
    *(_QWORD *)(v21 + 8 * v22 + 8) = result;
LABEL_27:
    ;
  }
  return result;
}

```

## disassembly

```asm
0x140011634  mov     [rsp+arg_8], rbx
0x140011639  mov     [rsp+arg_10], rsi
0x14001163e  mov     [rsp+arg_18], rdi
0x140011643  push    r14
0x140011645  sub     rsp, 20h
0x140011649  mov     rdx, [rcx+10h]
0x14001164d  mov     rsi, rcx
0x140011650  add     rdx, 1
0x140011654  mov     rbx, [rcx+38h]
0x140011658  xorps   xmm0, xmm0
0x14001165b  js      short loc_140011664
0x14001165d  cvtsi2ss xmm0, rdx
0x140011662  jmp     short loc_140011679
0x140011664  mov     rax, rdx
0x140011667  and     edx, 1
0x14001166a  shr     rax, 1
0x14001166d  or      rax, rdx
0x140011670  cvtsi2ss xmm0, rax
0x140011675  addss   xmm0, xmm0
0x140011679  divss   xmm0, dword ptr [rcx]; X
0x14001167d  call    ceilf_0
0x140011682  movss   xmm1, cs:__real@5f000000
0x14001168a  xor     ecx, ecx
0x14001168c  comiss  xmm0, xmm1
0x14001168f  jb      short loc_1400116A7
0x140011691  subss   xmm0, xmm1
0x140011695  comiss  xmm0, xmm1
0x140011698  jnb     short loc_1400116A7
0x14001169a  mov     rax, 8000000000000000h
0x1400116a4  mov     rcx, rax
0x1400116a7  cvttss2si rax, xmm0
0x1400116ac  add     rax, rcx
0x1400116af  mov     ecx, 8
0x1400116b4  cmp     rax, rcx
0x1400116b7  cmova   rcx, rax
0x1400116bb  cmp     rbx, rcx
0x1400116be  jnb     short loc_1400116DC
0x1400116c0  cmp     rbx, 200h
0x1400116c7  jnb     short loc_1400116D9
0x1400116c9  lea     rax, ds:0[rbx*8]
0x1400116d1  mov     rbx, rax
0x1400116d4  cmp     rax, rcx
0x1400116d7  jnb     short loc_1400116DC
0x1400116d9  mov     rbx, rcx
0x1400116dc  mov     rax, 0FFFFFFFFFFFFFFFh
0x1400116e6  bsr     rcx, rax
0x1400116ea  mov     eax, 1
0x1400116ef  shl     rax, cl
0x1400116f2  cmp     rbx, rax
0x1400116f5  jbe     short loc_140011705
0x1400116f7  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x1400116fe  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x140011705  lea     rax, [rbx-1]
0x140011709  mov     edi, 1
0x14001170e  mov     rbx, [rsi+8]
0x140011712  or      rax, 1
0x140011716  bsr     rcx, rax
0x14001171a  mov     r8, rbx
0x14001171d  inc     ecx
0x14001171f  shl     rdi, cl
0x140011722  lea     rcx, [rsi+18h]
0x140011726  lea     rdx, [rdi+rdi]
0x14001172a  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>)
0x14001172f  lea     rax, [rdi-1]
0x140011733  mov     [rsi+38h], rdi
0x140011737  mov     [rsi+30h], rax
0x14001173b  mov     rax, [rsi+8]
0x14001173f  mov     rax, [rax]
0x140011742  mov     rdx, rax
0x140011745  cmp     rax, rbx
0x140011748  jz      loc_140011818
0x14001174e  mov     rdx, [rdx]
0x140011751  mov     r8, 0CBF29CE484222325h
0x14001175b  xor     r9d, r9d
0x14001175e  movzx   ecx, byte ptr [rax+r9+10h]
0x140011764  mov     r10, 100000001B3h
0x14001176e  xor     r8, rcx
0x140011771  inc     r9
0x140011774  imul    r8, r10
0x140011778  cmp     r9, 4
0x14001177c  jb      short loc_14001175E
0x14001177e  mov     r11, [rsi+30h]
0x140011782  mov     rdi, [rsi+18h]
0x140011786  and     r11, r8
0x140011789  add     r11, r11
0x14001178c  cmp     [rdi+r11*8], rbx
0x140011790  jnz     short loc_14001179D
0x140011792  mov     [rdi+r11*8], rax
0x140011796  mov     [rdi+r11*8+8], rax
0x14001179b  jmp     short loc_14001180C
0x14001179d  mov     rcx, [rdi+r11*8+8]
0x1400117a2  mov     r8d, [rax+10h]
0x1400117a6  cmp     r8d, [rcx+10h]
0x1400117aa  jnz     short loc_1400117E1
0x1400117ac  mov     r10, [rcx]
0x1400117af  cmp     r10, rax
0x1400117b2  jz      short loc_140011796
0x1400117b4  mov     r9, [rax+8]
0x1400117b8  mov     [r9], rdx
0x1400117bb  mov     r8, [rdx+8]
0x1400117bf  mov     [r8], r10
0x1400117c2  mov     rcx, [r10+8]
0x1400117c6  mov     [rcx], rax
0x1400117c9  mov     [r10+8], r8
0x1400117cd  mov     [rdx+8], r9
0x1400117d1  mov     [rax+8], rcx
0x1400117d5  jmp     short loc_140011796
0x1400117d7  mov     rcx, [rcx+8]
0x1400117db  cmp     r8d, [rcx+10h]
0x1400117df  jz      short loc_14001182E
0x1400117e1  cmp     [rdi+r11*8], rcx
0x1400117e5  jnz     short loc_1400117D7
0x1400117e7  mov     r10, [rax+8]
0x1400117eb  mov     [r10], rdx
0x1400117ee  mov     r9, [rdx+8]
0x1400117f2  mov     [r9], rcx
0x1400117f5  mov     r8, [rcx+8]
0x1400117f9  mov     [r8], rax
0x1400117fc  mov     [rcx+8], r9
0x140011800  mov     [rdx+8], r10
0x140011804  mov     [rax+8], r8
0x140011808  mov     [rdi+r11*8], rax
0x14001180c  mov     rax, rdx
0x14001180f  cmp     rdx, rbx
0x140011812  jnz     loc_14001174E
0x140011818  mov     rbx, [rsp+28h+arg_8]
0x14001181d  mov     rsi, [rsp+28h+arg_10]
0x140011822  mov     rdi, [rsp+28h+arg_18]
0x140011827  add     rsp, 20h
0x14001182b  pop     r14
0x14001182d  retn
0x14001182e  mov     r10, [rcx]
0x140011831  mov     r9, [rax+8]
0x140011835  mov     [r9], rdx
0x140011838  mov     r8, [rdx+8]
0x14001183c  mov     [r8], r10
0x14001183f  mov     rcx, [r10+8]
0x140011843  mov     [rcx], rax
0x140011846  mov     [r10+8], r8
0x14001184a  mov     [rdx+8], r9
0x14001184e  mov     [rax+8], rcx
0x140011852  jmp     short loc_14001180C
```
