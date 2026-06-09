# std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>>,0>>::emplace<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>>(std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>> &&)

- ea: `0x14000f2d4`
- end: `0x14000f433`
- name: `??$emplace@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@1@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64 *, __int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000fccc`

## callees

- `0x14000892c`
- `0x14000ecf0`
- `0x14000f2d4`
- `0x14000f758`
- `0x140011470`
- `0x14001170c`
- `0x140011d08`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>,0>>::emplace<std::pair<std::wstring,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>(
        __int64 *a1,
        __int64 a2,
        const wchar_t *a3)
{
  _QWORD *v6; // rax
  __int128 v7; // xmm6
  __int64 inserted; // rbx
  const wchar_t *v9; // rdx
  unsigned __int64 v10; // rbp
  unsigned __int64 v11; // rdi
  const wchar_t *v12; // rcx
  size_t v13; // r8
  int v14; // eax
  __int64 v15; // rbx
  _OWORD *v16; // rdi
  __int64 v17; // rax
  char v18; // al
  _OWORD v20[2]; // [rsp+20h] [rbp-68h] BYREF

  v6 = std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>,0>>::_Find_lower_bound<std::wstring>(
         (__int64)a1,
         v20,
         (__int64)a3);
  v7 = *(_OWORD *)v6;
  inserted = v6[2];
  if ( *(_BYTE *)(inserted + 25) )
    goto LABEL_11;
  v9 = (const wchar_t *)(inserted + 32);
  v10 = *(_QWORD *)(inserted + 48);
  if ( *(_QWORD *)(inserted + 56) > 7u )
    v9 = *(const wchar_t **)v9;
  v11 = *((_QWORD *)a3 + 2);
  if ( *((_QWORD *)a3 + 3) <= 7u )
    v12 = a3;
  else
    v12 = *(const wchar_t **)a3;
  v13 = *(_QWORD *)(inserted + 48);
  if ( v10 >= v11 )
    v13 = *((_QWORD *)a3 + 2);
  v14 = wmemcmp(v12, v9, v13);
  if ( v14 )
  {
    if ( v14 < 0 )
      goto LABEL_11;
LABEL_15:
    v18 = 0;
    goto LABEL_13;
  }
  if ( v11 >= v10 )
    goto LABEL_15;
LABEL_11:
  if ( a1[1] == 0x38E38E38E38E38ELL )
    std::_Throw_tree_length_error();
  v15 = *a1;
  v20[0] = (unsigned __int64)a1;
  v16 = operator new(0x48u);
  v16[2] = 0;
  *((_QWORD *)v16 + 6) = 0;
  *((_QWORD *)v16 + 7) = 0;
  v16[2] = *(_OWORD *)a3;
  v16[3] = *((_OWORD *)a3 + 1);
  *((_QWORD *)a3 + 2) = 0;
  *((_QWORD *)a3 + 3) = 7;
  *a3 = 0;
  v17 = *((_QWORD *)a3 + 4);
  *((_QWORD *)a3 + 4) = 0;
  *((_QWORD *)v16 + 8) = v17;
  *(_QWORD *)v16 = v15;
  *((_QWORD *)v16 + 1) = v15;
  *((_QWORD *)v16 + 2) = v15;
  *((_WORD *)v16 + 12) = 0;
  *((_QWORD *)&v20[0] + 1) = 0;
  std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,void *>>>(v20);
  v20[0] = v7;
  inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>>::_Insert_node(
               a1,
               v20,
               v16);
  v18 = 1;
LABEL_13:
  *(_QWORD *)a2 = inserted;
  *(_BYTE *)(a2 + 8) = v18;
  return a2;
}

```

## disassembly

```asm
0x14000f2d4  push    rbx
0x14000f2d6  push    rbp
0x14000f2d7  push    rsi
0x14000f2d8  push    rdi
0x14000f2d9  push    r14
0x14000f2db  push    r15
0x14000f2dd  sub     rsp, 58h
0x14000f2e1  movaps  [rsp+88h+var_48], xmm6
0x14000f2e6  mov     rsi, r8
0x14000f2e9  mov     r14, rdx
0x14000f2ec  mov     r15, rcx
0x14000f2ef  lea     rdx, [rsp+88h+var_68]
0x14000f2f4  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x14000f2f9  movups  xmm6, xmmword ptr [rax]
0x14000f2fc  mov     rbx, [rax+10h]
0x14000f300  cmp     byte ptr [rbx+19h], 0
0x14000f304  jnz     short loc_14000F34B
0x14000f306  lea     rdx, [rbx+20h]
0x14000f30a  mov     rbp, [rdx+10h]
0x14000f30e  cmp     qword ptr [rdx+18h], 7
0x14000f313  jbe     short loc_14000F318
0x14000f315  mov     rdx, [rdx]; S2
0x14000f318  mov     rdi, [rsi+10h]
0x14000f31c  cmp     qword ptr [rsi+18h], 7
0x14000f321  jbe     short loc_14000F328
0x14000f323  mov     rcx, [rsi]
0x14000f326  jmp     short loc_14000F32B
0x14000f328  mov     rcx, rsi; S1
0x14000f32b  mov     r8, rbp
0x14000f32e  cmp     rbp, rdi
0x14000f331  cmovnb  r8, rdi; N
0x14000f335  call    wmemcmp
0x14000f33a  test    eax, eax
0x14000f33c  jnz     loc_14000F423
0x14000f342  cmp     rdi, rbp
0x14000f345  jnb     loc_14000F429
0x14000f34b  mov     rax, 38E38E38E38E38Eh
0x14000f355  cmp     [r15+8], rax
0x14000f359  jz      loc_14000F42D
0x14000f35f  mov     rbx, [r15]
0x14000f362  mov     qword ptr [rsp+88h+var_68], r15
0x14000f367  mov     qword ptr [rsp+88h+var_68+8], 0
0x14000f370  mov     ecx, 48h ; 'H'; Size
0x14000f375  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000f37a  mov     rdi, rax
0x14000f37d  xorps   xmm0, xmm0
0x14000f380  movups  xmmword ptr [rax+20h], xmm0
0x14000f384  mov     qword ptr [rax+30h], 0
0x14000f38c  mov     qword ptr [rax+38h], 0
0x14000f394  movups  xmm0, xmmword ptr [rsi]
0x14000f397  movups  xmmword ptr [rax+20h], xmm0
0x14000f39b  movups  xmm1, xmmword ptr [rsi+10h]
0x14000f39f  movups  xmmword ptr [rax+30h], xmm1
0x14000f3a3  mov     qword ptr [rsi+10h], 0
0x14000f3ab  mov     qword ptr [rsi+18h], 7
0x14000f3b3  xor     eax, eax
0x14000f3b5  mov     [rsi], ax
0x14000f3b8  mov     rax, [rsi+20h]
0x14000f3bc  mov     qword ptr [rsi+20h], 0
0x14000f3c4  mov     [rdi+40h], rax
0x14000f3c8  mov     [rdi], rbx
0x14000f3cb  mov     [rdi+8], rbx
0x14000f3cf  mov     [rdi+10h], rbx
0x14000f3d3  mov     word ptr [rdi+18h], 0
0x14000f3d9  mov     qword ptr [rsp+88h+var_68+8], 0
0x14000f3e2  lea     rcx, [rsp+88h+var_68]
0x14000f3e7  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,void *>>>(void)
0x14000f3ec  movdqu  [rsp+88h+var_68], xmm6
0x14000f3f2  mov     r8, rdi
0x14000f3f5  lea     rdx, [rsp+88h+var_68]
0x14000f3fa  mov     rcx, r15
0x14000f3fd  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,void *> *>,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,void *> * const)
0x14000f402  mov     rbx, rax
0x14000f405  mov     al, 1
0x14000f407  mov     [r14], rbx
0x14000f40a  mov     [r14+8], al
0x14000f40e  mov     rax, r14
0x14000f411  movaps  xmm6, [rsp+88h+var_48]
0x14000f416  add     rsp, 58h
0x14000f41a  pop     r15
0x14000f41c  pop     r14
0x14000f41e  pop     rdi
0x14000f41f  pop     rsi
0x14000f420  pop     rbp
0x14000f421  pop     rbx
0x14000f422  retn
0x14000f423  js      loc_14000F34B
0x14000f429  xor     al, al
0x14000f42b  jmp     short loc_14000F407
0x14000f42d  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
