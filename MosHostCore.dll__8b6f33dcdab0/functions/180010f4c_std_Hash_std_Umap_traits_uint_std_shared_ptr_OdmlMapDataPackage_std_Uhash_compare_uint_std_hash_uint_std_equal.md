# std::_Hash<std::_Umap_traits<uint,std::shared_ptr<OdmlMapDataPackage>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::shared_ptr<OdmlMapDataPackage>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x180010f4c`
- end: `0x1800110cf`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@IV?$shared_ptr@VOdmlMapDataPackage@@@std@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VOdmlMapDataPackage@@@std@@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `387`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000e2b0`

## callees

- `0x18000a90c`
- `0x18000e92c`
- `0x18000ea1c`
- `0x180010f4c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180010f8d`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180010f8d`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<OdmlMapDataPackage>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<OdmlMapDataPackage>>>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  __int64 v4; // rdi
  unsigned __int64 v5; // rcx
  __int64 v6; // rbx
  _QWORD *v7; // r11
  _QWORD *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // r11
  __int64 v11; // r9
  __int64 v12; // r8
  __int64 *v13; // rax
  int v14; // ecx
  __int64 v15; // r10
  _QWORD *v16; // rdx
  _QWORD *v17; // rcx
  _QWORD *v18; // rax
  __int64 **v19; // r10
  __int64 v20; // r8
  _QWORD *v21; // rdx
  _QWORD *v22; // rcx
  _QWORD *v23; // rax
  _QWORD *v24; // rdx
  __int64 **v25; // rcx
  __int64 *v26; // rax
  __int64 v28; // [rsp+48h] [rbp+10h] BYREF

  LODWORD(v28) = 0;
  _BitScanReverse64(&v3, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v3 )
    std::_Xlength_error("invalid hash bucket count");
  v4 = a1[1];
  LODWORD(v28) = 0;
  _BitScanReverse64(&v5, (a2 - 1) | 1);
  v6 = 1LL << ((unsigned __int8)v5 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>>>>>::_Assign_grow(
    a1 + 3,
    2 * v6,
    v4);
  a1[7] = v6;
  a1[6] = v6 - 1;
  v7 = *(_QWORD **)a1[1];
  v8 = v7;
  while ( v7 != (_QWORD *)v4 )
  {
    v8 = (_QWORD *)*v8;
    v9 = std::_Conditionally_enabled_hash<unsigned int,1>::operator()((unsigned __int8 *)v7 + 16);
    v11 = a1[3];
    v12 = 2 * (a1[6] & v9);
    if ( *(_QWORD *)(v11 + 16 * (a1[6] & v9)) == v4 )
    {
      *(_QWORD *)(v11 + 16 * (a1[6] & v9)) = v10;
LABEL_7:
      *(_QWORD *)(v11 + 8 * v12 + 8) = v10;
      goto LABEL_15;
    }
    v13 = *(__int64 **)(v11 + 16 * (a1[6] & v9) + 8);
    v14 = *(_DWORD *)(v10 + 16);
    if ( v14 == *((_DWORD *)v13 + 4) )
    {
      v15 = *v13;
      if ( *v13 != v10 )
      {
        v16 = *(_QWORD **)(v10 + 8);
        *v16 = v8;
        v17 = (_QWORD *)v8[1];
        *v17 = v15;
        v18 = *(_QWORD **)(v15 + 8);
        *v18 = v10;
        *(_QWORD *)(v15 + 8) = v17;
        v8[1] = v16;
        *(_QWORD *)(v10 + 8) = v18;
      }
      goto LABEL_7;
    }
    while ( 1 )
    {
      v19 = (__int64 **)(v13 + 1);
      if ( *(__int64 **)(v11 + 8 * v12) == v13 )
        break;
      v13 = *v19;
      if ( v14 == *((_DWORD *)*v19 + 4) )
      {
        v20 = *v13;
        v21 = *(_QWORD **)(v10 + 8);
        *v21 = v8;
        v22 = (_QWORD *)v8[1];
        *v22 = v20;
        v23 = *(_QWORD **)(v20 + 8);
        *v23 = v10;
        *(_QWORD *)(v20 + 8) = v22;
        v8[1] = v21;
        *(_QWORD *)(v10 + 8) = v23;
        goto LABEL_15;
      }
    }
    v24 = *(_QWORD **)(v10 + 8);
    *v24 = v8;
    v25 = (__int64 **)v8[1];
    *v25 = v13;
    v26 = *v19;
    *v26 = v10;
    *v19 = (__int64 *)v25;
    v8[1] = v24;
    *(_QWORD *)(v10 + 8) = v26;
    *(_QWORD *)(v11 + 8 * v12) = v10;
LABEL_15:
    v7 = v8;
  }
  v28 = 0;
  return std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<OdmlMapDataPackage>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<OdmlMapDataPackage>>>,0>>::_Clear_guard::~_Clear_guard(&v28);
}

```

## disassembly

```asm
0x180010f4c  mov     [rsp+arg_0], rbx
0x180010f51  mov     [rsp+arg_10], rbp
0x180010f56  push    rsi
0x180010f57  push    rdi
0x180010f58  push    r14
0x180010f5a  sub     rsp, 20h
0x180010f5e  mov     rax, 0FFFFFFFFFFFFFFFh
0x180010f68  mov     dword ptr [rsp+38h+arg_8], 0
0x180010f70  mov     rbp, rcx
0x180010f73  mov     ebx, 1
0x180010f78  bsr     rcx, rax
0x180010f7c  mov     eax, ebx
0x180010f7e  shl     rax, cl
0x180010f81  cmp     rdx, rax
0x180010f84  jbe     short loc_180010F94
0x180010f86  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x180010f8d  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180010f94  mov     rdi, [rbp+8]
0x180010f98  lea     rax, [rdx-1]
0x180010f9c  or      rax, rbx
0x180010f9f  mov     dword ptr [rsp+38h+arg_8], 0
0x180010fa7  bsr     rcx, rax
0x180010fab  mov     r8, rdi
0x180010fae  inc     ecx
0x180010fb0  shl     rbx, cl
0x180010fb3  lea     rcx, [rbp+18h]
0x180010fb7  lea     rdx, [rbx+rbx]
0x180010fbb  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>>>)
0x180010fc0  mov     [rbp+38h], rbx
0x180010fc4  lea     rax, [rbx-1]
0x180010fc8  mov     [rbp+30h], rax
0x180010fcc  mov     r11, [rbp+8]
0x180010fd0  mov     r11, [r11]
0x180010fd3  mov     rbx, r11
0x180010fd6  cmp     r11, rdi
0x180010fd9  jz      loc_1800110A9
0x180010fdf  mov     rbx, [rbx]
0x180010fe2  lea     rcx, [r11+10h]; unsigned __int8 *
0x180010fe6  call    ??R?$_Conditionally_enabled_hash@I$00@std@@SA_KAEBI@Z; std::_Conditionally_enabled_hash<uint,1>::operator()(uint const &)
0x180010feb  mov     r9, [rbp+18h]
0x180010fef  mov     r8, rax
0x180010ff2  and     r8, [rbp+30h]
0x180010ff6  add     r8, r8
0x180010ff9  cmp     [r9+r8*8], rdi
0x180010ffd  jnz     short loc_18001100D
0x180010fff  mov     [r9+r8*8], r11
0x180011003  mov     [r9+r8*8+8], r11
0x180011008  jmp     loc_1800110A1
0x18001100d  mov     rax, [r9+r8*8+8]
0x180011012  mov     ecx, [r11+10h]
0x180011016  cmp     ecx, [rax+10h]
0x180011019  jnz     short loc_180011046
0x18001101b  mov     r10, [rax]
0x18001101e  cmp     r10, r11
0x180011021  jz      short loc_180011003
0x180011023  mov     rdx, [r11+8]
0x180011027  mov     [rdx], rbx
0x18001102a  mov     rcx, [rbx+8]
0x18001102e  mov     [rcx], r10
0x180011031  mov     rax, [r10+8]
0x180011035  mov     [rax], r11
0x180011038  mov     [r10+8], rcx
0x18001103c  mov     [rbx+8], rdx
0x180011040  mov     [r11+8], rax
0x180011044  jmp     short loc_180011003
0x180011046  lea     r10, [rax+8]
0x18001104a  cmp     [r9+r8*8], rax
0x18001104e  jz      short loc_18001107E
0x180011050  mov     rax, [r10]
0x180011053  cmp     ecx, [rax+10h]
0x180011056  jnz     short loc_180011046
0x180011058  mov     r8, [rax]
0x18001105b  mov     rdx, [r11+8]
0x18001105f  mov     [rdx], rbx
0x180011062  mov     rcx, [rbx+8]
0x180011066  mov     [rcx], r8
0x180011069  mov     rax, [r8+8]
0x18001106d  mov     [rax], r11
0x180011070  mov     [r8+8], rcx
0x180011074  mov     [rbx+8], rdx
0x180011078  mov     [r11+8], rax
0x18001107c  jmp     short loc_1800110A1
0x18001107e  mov     rdx, [r11+8]
0x180011082  mov     [rdx], rbx
0x180011085  mov     rcx, [rbx+8]
0x180011089  mov     [rcx], rax
0x18001108c  mov     rax, [r10]
0x18001108f  mov     [rax], r11
0x180011092  mov     [r10], rcx
0x180011095  mov     [rbx+8], rdx
0x180011099  mov     [r11+8], rax
0x18001109d  mov     [r9+r8*8], r11
0x1800110a1  mov     r11, rbx
0x1800110a4  jmp     loc_180010FD6
0x1800110a9  lea     rcx, [rsp+38h+arg_8]
0x1800110ae  mov     [rsp+38h+arg_8], 0
0x1800110b7  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@IV?$shared_ptr@VOdmlMapDataPackage@@@std@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VOdmlMapDataPackage@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<uint,std::shared_ptr<OdmlMapDataPackage>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::shared_ptr<OdmlMapDataPackage>>>,0>>::_Clear_guard::~_Clear_guard(void)
0x1800110bc  mov     rbx, [rsp+38h+arg_0]
0x1800110c1  mov     rbp, [rsp+38h+arg_10]
0x1800110c6  add     rsp, 20h
0x1800110ca  pop     r14
0x1800110cc  pop     rdi
0x1800110cd  pop     rsi
0x1800110ce  retn
```
