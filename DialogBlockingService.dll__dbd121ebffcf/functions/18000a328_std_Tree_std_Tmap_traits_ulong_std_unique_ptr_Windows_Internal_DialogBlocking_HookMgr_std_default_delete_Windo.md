# std::_Tree<std::_Tmap_traits<ulong,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr,std::default_delete<Windows::Internal::DialogBlocking::HookMgr>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr,std::default_delete<Windows::Internal::DialogBlocking::HookMgr>>>>,0>>::erase(ulong const &)

- ea: `0x18000a328`
- end: `0x18000a531`
- name: `?erase@?$_Tree@V?$_Tmap_traits@KV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBK@Z`
- size: `521`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000a538`
- `0x18000a65c`

## callees

- `0x180001644`
- `0x18000396c`
- `0x18000899c`
- `0x180009ba8`
- `0x18000a328`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>,0>>::erase(
        _QWORD *a1,
        unsigned int *a2)
{
  _QWORD *v2; // rdi
  _QWORD *v4; // rbx
  _QWORD *v5; // r14
  _QWORD *v6; // r15
  _QWORD *v7; // rax
  char v8; // r8
  unsigned int v9; // ecx
  _QWORD *v10; // rax
  _QWORD *j; // rax
  __int64 v12; // rbp
  __int64 **v13; // rcx
  __int64 i; // rcx
  __int64 *v15; // rdx
  Windows::Internal::DialogBlocking::HookProcess **v16; // rbx
  void *v17; // rsi
  _BYTE *v19; // rcx
  _QWORD *v20; // rdx
  __int64 *v21; // r8
  _QWORD *v22; // rax
  __int64 k; // rcx
  __int64 v24; // r8
  __int64 *v25; // r8
  __int64 *v26; // r8
  _QWORD *v27; // rax
  void *v28; // rsi
  void *v29; // rdi

  v2 = (_QWORD *)*a1;
  v4 = (_QWORD *)*a1;
  v5 = (_QWORD *)*a1;
  v6 = *(_QWORD **)(*a1 + 8LL);
  v7 = v6;
  v8 = *((_BYTE *)v6 + 25);
  if ( !v8 )
  {
    v9 = *a2;
    do
    {
      if ( *((_DWORD *)v7 + 8) >= v9 )
      {
        if ( *((_BYTE *)v5 + 25) && v9 < *((_DWORD *)v7 + 8) )
          v5 = v7;
        v4 = v7;
        v7 = (_QWORD *)*v7;
      }
      else
      {
        v7 = (_QWORD *)v7[2];
      }
    }
    while ( !*((_BYTE *)v7 + 25) );
  }
  v10 = v6;
  if ( !*((_BYTE *)v5 + 25) )
    v10 = (_QWORD *)*v5;
  while ( !*((_BYTE *)v10 + 25) )
  {
    if ( *a2 >= *((_DWORD *)v10 + 8) )
    {
      v10 = (_QWORD *)v10[2];
    }
    else
    {
      v5 = v10;
      v10 = (_QWORD *)*v10;
    }
  }
  j = v4;
  v12 = 0;
  while ( j != v5 )
  {
    v13 = (__int64 **)j[2];
    ++v12;
    if ( *((_BYTE *)v13 + 25) )
    {
      for ( i = j[1]; !*(_BYTE *)(i + 25) && j == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
        j = (_QWORD *)i;
      j = (_QWORD *)i;
    }
    else
    {
      v15 = *v13;
      for ( j = (_QWORD *)j[2]; !*((_BYTE *)v15 + 25); v15 = (__int64 *)*v15 )
        j = v15;
    }
  }
  if ( v4 == (_QWORD *)*v2 && *((_BYTE *)v5 + 25) )
  {
    if ( !v8 )
    {
      do
      {
        std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>,void *>>>(
          (__int64)a1,
          (__int64)a1,
          v6[2]);
        v16 = (Windows::Internal::DialogBlocking::HookProcess **)v6[5];
        v17 = v6;
        v6 = (_QWORD *)*v6;
        if ( v16 )
        {
          Windows::Internal::DialogBlocking::HookMgr::~HookMgr(v16);
          operator delete(v16);
        }
        operator delete(v17);
      }
      while ( !*((_BYTE *)v6 + 25) );
    }
    v2[1] = v2;
    *v2 = v2;
    v2[2] = v2;
    a1[1] = 0;
  }
  else
  {
    while ( v4 != v5 )
    {
      v19 = (_BYTE *)v4[2];
      v20 = v4;
      if ( v19[25] )
      {
        v21 = v4 + 1;
        v22 = v4;
        for ( k = v4[1]; !*(_BYTE *)(k + 25) && v4 == *(_QWORD **)(k + 16); k = *(_QWORD *)(k + 8) )
          v4 = (_QWORD *)k;
        v24 = *v21;
        v4 = (_QWORD *)k;
        while ( !*(_BYTE *)(v24 + 25) && v22 == *(_QWORD **)(v24 + 16) )
        {
          v22 = (_QWORD *)v24;
          v24 = *(_QWORD *)(v24 + 8);
        }
      }
      else
      {
        v25 = *(__int64 **)v19;
        if ( *(_BYTE *)(*(_QWORD *)v19 + 25LL) )
        {
          v4 = (_QWORD *)v4[2];
        }
        else
        {
          do
          {
            v4 = v25;
            v25 = (__int64 *)*v25;
          }
          while ( !*((_BYTE *)v25 + 25) );
        }
        v26 = *(__int64 **)v19;
        if ( !*(_BYTE *)(*(_QWORD *)v19 + 25LL) )
        {
          do
            v26 = (__int64 *)*v26;
          while ( !*((_BYTE *)v26 + 25) );
        }
      }
      v27 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>>::_Extract(
              a1,
              v20);
      v28 = v27;
      v29 = (void *)v27[5];
      if ( v29 )
      {
        Windows::Internal::DialogBlocking::HookMgr::~HookMgr((Windows::Internal::DialogBlocking::HookProcess **)v27[5]);
        operator delete(v29);
      }
      operator delete(v28);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x18000a328  push    rbx
0x18000a32a  push    rbp
0x18000a32b  push    rsi
0x18000a32c  push    rdi
0x18000a32d  push    r12
0x18000a32f  push    r13
0x18000a331  push    r14
0x18000a333  push    r15
0x18000a335  sub     rsp, 28h
0x18000a339  mov     rdi, [rcx]
0x18000a33c  xor     r13d, r13d
0x18000a33f  mov     r12, rcx
0x18000a342  mov     rbx, rdi
0x18000a345  mov     r14, rdi
0x18000a348  mov     r15, [rdi+8]
0x18000a34c  mov     rax, r15
0x18000a34f  mov     r8b, [r15+19h]
0x18000a353  test    r8b, r8b
0x18000a356  jnz     short loc_18000A37E
0x18000a358  mov     ecx, [rdx]
0x18000a35a  cmp     [rax+20h], ecx
0x18000a35d  jnb     short loc_18000A365
0x18000a35f  mov     rax, [rax+10h]
0x18000a363  jmp     short loc_18000A378
0x18000a365  cmp     [r14+19h], r13b
0x18000a369  jz      short loc_18000A372
0x18000a36b  cmp     ecx, [rax+20h]
0x18000a36e  cmovb   r14, rax
0x18000a372  mov     rbx, rax
0x18000a375  mov     rax, [rax]
0x18000a378  cmp     [rax+19h], r13b
0x18000a37c  jz      short loc_18000A35A
0x18000a37e  mov     rax, r15
0x18000a381  cmp     [r14+19h], r13b
0x18000a385  jnz     short loc_18000A38A
0x18000a387  mov     rax, [r14]
0x18000a38a  cmp     [rax+19h], r13b
0x18000a38e  jnz     short loc_18000A3A9
0x18000a390  mov     ecx, [rdx]
0x18000a392  cmp     ecx, [rax+20h]
0x18000a395  jnb     short loc_18000A39F
0x18000a397  mov     r14, rax
0x18000a39a  mov     rax, [rax]
0x18000a39d  jmp     short loc_18000A3A3
0x18000a39f  mov     rax, [rax+10h]
0x18000a3a3  cmp     [rax+19h], r13b
0x18000a3a7  jz      short loc_18000A392
0x18000a3a9  mov     rax, rbx
0x18000a3ac  mov     rbp, r13
0x18000a3af  cmp     rax, r14
0x18000a3b2  jz      short loc_18000A3FC
0x18000a3b4  mov     rcx, [rax+10h]
0x18000a3b8  inc     rbp
0x18000a3bb  cmp     [rcx+19h], r13b
0x18000a3bf  jz      short loc_18000A3DF
0x18000a3c1  mov     rcx, [rax+8]
0x18000a3c5  jmp     short loc_18000A3D4
0x18000a3c7  cmp     rax, [rcx+10h]
0x18000a3cb  jnz     short loc_18000A3DA
0x18000a3cd  mov     rax, rcx
0x18000a3d0  mov     rcx, [rcx+8]
0x18000a3d4  cmp     [rcx+19h], r13b
0x18000a3d8  jz      short loc_18000A3C7
0x18000a3da  mov     rax, rcx
0x18000a3dd  jmp     short loc_18000A3AF
0x18000a3df  mov     rdx, [rcx]
0x18000a3e2  mov     rax, rcx
0x18000a3e5  cmp     [rdx+19h], r13b
0x18000a3e9  jnz     short loc_18000A3AF
0x18000a3eb  mov     rcx, [rdx]
0x18000a3ee  mov     rax, rdx
0x18000a3f1  mov     rdx, rcx
0x18000a3f4  cmp     [rcx+19h], r13b
0x18000a3f8  jz      short loc_18000A3EB
0x18000a3fa  jmp     short loc_18000A3AF
0x18000a3fc  cmp     rbx, [rdi]
0x18000a3ff  jnz     short loc_18000A476
0x18000a401  cmp     [r14+19h], r13b
0x18000a405  jz      short loc_18000A476
0x18000a407  test    r8b, r8b
0x18000a40a  jnz     short loc_18000A452
0x18000a40c  mov     r8, [r15+10h]
0x18000a410  mov     rdx, r12
0x18000a413  mov     rcx, r12
0x18000a416  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>,void *>> &,std::_Tree_node<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>,void *> *)
0x18000a41b  mov     rbx, [r15+28h]
0x18000a41f  mov     rsi, r15
0x18000a422  mov     r15, [r15]
0x18000a425  test    rbx, rbx
0x18000a428  jz      short loc_18000A43F
0x18000a42a  mov     rcx, rbx; this
0x18000a42d  call    ??1HookMgr@DialogBlocking@Internal@Windows@@QEAA@XZ; Windows::Internal::DialogBlocking::HookMgr::~HookMgr(void)
0x18000a432  mov     edx, 28h ; '('; unsigned __int64
0x18000a437  mov     rcx, rbx; void *
0x18000a43a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a43f  mov     edx, 30h ; '0'; unsigned __int64
0x18000a444  mov     rcx, rsi; void *
0x18000a447  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a44c  cmp     [r15+19h], r13b
0x18000a450  jz      short loc_18000A40C
0x18000a452  mov     [rdi+8], rdi
0x18000a456  mov     [rdi], rdi
0x18000a459  mov     [rdi+10h], rdi
0x18000a45d  mov     [r12+8], r13
0x18000a462  mov     rax, rbp
0x18000a465  add     rsp, 28h
0x18000a469  pop     r15
0x18000a46b  pop     r14
0x18000a46d  pop     r13
0x18000a46f  pop     r12
0x18000a471  pop     rdi
0x18000a472  pop     rsi
0x18000a473  pop     rbp
0x18000a474  pop     rbx
0x18000a475  retn
0x18000a476  cmp     rbx, r14
0x18000a479  jz      short loc_18000A462
0x18000a47b  mov     rcx, [rbx+10h]
0x18000a47f  mov     rdx, rbx
0x18000a482  cmp     [rcx+19h], r13b
0x18000a486  jz      short loc_18000A4C4
0x18000a488  lea     r8, [rbx+8]
0x18000a48c  mov     rax, rbx
0x18000a48f  mov     rcx, [r8]
0x18000a492  jmp     short loc_18000A4A1
0x18000a494  cmp     rbx, [rcx+10h]
0x18000a498  jnz     short loc_18000A4A7
0x18000a49a  mov     rbx, rcx
0x18000a49d  mov     rcx, [rcx+8]
0x18000a4a1  cmp     [rcx+19h], r13b
0x18000a4a5  jz      short loc_18000A494
0x18000a4a7  mov     r8, [r8]
0x18000a4aa  mov     rbx, rcx
0x18000a4ad  jmp     short loc_18000A4BC
0x18000a4af  cmp     rax, [r8+10h]
0x18000a4b3  jnz     short loc_18000A4F6
0x18000a4b5  mov     rax, r8
0x18000a4b8  mov     r8, [r8+8]
0x18000a4bc  cmp     [r8+19h], r13b
0x18000a4c0  jz      short loc_18000A4AF
0x18000a4c2  jmp     short loc_18000A4F6
0x18000a4c4  mov     r8, [rcx]
0x18000a4c7  cmp     [r8+19h], r13b
0x18000a4cb  jnz     short loc_18000A4DE
0x18000a4cd  mov     rax, [r8]
0x18000a4d0  mov     rbx, r8
0x18000a4d3  mov     r8, rax
0x18000a4d6  cmp     [rax+19h], r13b
0x18000a4da  jz      short loc_18000A4CD
0x18000a4dc  jmp     short loc_18000A4E1
0x18000a4de  mov     rbx, rcx
0x18000a4e1  mov     r8, [rcx]
0x18000a4e4  cmp     [r8+19h], r13b
0x18000a4e8  jnz     short loc_18000A4F6
0x18000a4ea  mov     rax, [r8]
0x18000a4ed  mov     r8, rax
0x18000a4f0  cmp     [rax+19h], r13b
0x18000a4f4  jz      short loc_18000A4EA
0x18000a4f6  mov     rcx, r12
0x18000a4f9  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>>,std::_Iterator_base0>)
0x18000a4fe  mov     rsi, rax
0x18000a501  mov     rdi, [rax+28h]
0x18000a505  test    rdi, rdi
0x18000a508  jz      short loc_18000A51F
0x18000a50a  mov     rcx, rdi; this
0x18000a50d  call    ??1HookMgr@DialogBlocking@Internal@Windows@@QEAA@XZ; Windows::Internal::DialogBlocking::HookMgr::~HookMgr(void)
0x18000a512  mov     edx, 28h ; '('; unsigned __int64
0x18000a517  mov     rcx, rdi; void *
0x18000a51a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a51f  mov     edx, 30h ; '0'; unsigned __int64
0x18000a524  mov     rcx, rsi; void *
0x18000a527  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a52c  jmp     loc_18000A476
```
