# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::emplace<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,XinputHid::XInputHidDevice *>>(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,XinputHid::XInputHidDevice *> &&)

- ea: `0x18000e5a0`
- end: `0x18000e7e9`
- name: `??$emplace@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUXInputHidDevice@XinputHid@@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUXInputHidDevice@XinputHid@@@1@@Z`
- size: `585`
- prototype: `__int64 __fastcall(float *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180010768`

## callees

- `0x1800021fc`
- `0x18000e224`
- `0x18000e5a0`
- `0x18000ed8c`
- `0x180011148`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000e640`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000e640`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::emplace<std::pair<std::wstring,XinputHid::XInputHidDevice *>>(
        float *a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v6; // r8
  _QWORD *v7; // rdx
  unsigned __int64 v8; // rcx
  __int64 v9; // r15
  unsigned __int64 v10; // r8
  _OWORD *v11; // rsi
  __int64 v12; // rbx
  __int64 v13; // rcx
  float v14; // xmm0_4
  __int64 v15; // rcx
  float v16; // xmm1_4
  __int64 v17; // rax
  __int64 v18; // rdx
  _QWORD *v19; // r8
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // r9
  _QWORD *v24; // [rsp+20h] [rbp-20h] BYREF
  _OWORD *v25; // [rsp+28h] [rbp-18h]
  __int128 v26; // [rsp+30h] [rbp-10h] BYREF
  _DWORD *v27; // [rsp+80h] [rbp+40h]

  v6 = a3[2];
  if ( a3[3] <= 7u )
    v7 = a3;
  else
    v7 = (_QWORD *)*a3;
  v8 = 0;
  v9 = 0xCBF29CE484222325uLL;
  v10 = 2 * v6;
  if ( v10 )
  {
    do
      v9 = 0x100000001B3LL * (*((unsigned __int8 *)v7 + v8++) ^ (unsigned __int64)v9);
    while ( v8 < v10 );
  }
  std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::_Find_last<std::wstring>(
    a1,
    &v26,
    (__int64)a3,
    v9);
  if ( !*((_QWORD *)&v26 + 1) )
  {
    if ( *((_QWORD *)a1 + 2) == 0x3FFFFFFFFFFFFFFLL )
      std::_Xlength_error("unordered_map/set too long");
    v24 = a1 + 2;
    v11 = operator new(0x40u);
    v25 = v11;
    v11[1] = 0;
    *((_QWORD *)v11 + 4) = 0;
    *((_QWORD *)v11 + 5) = 0;
    v11[1] = *(_OWORD *)a3;
    v11[2] = *((_OWORD *)a3 + 1);
    a3[2] = 0;
    a3[3] = 7;
    *(_WORD *)a3 = 0;
    v12 = a3[4];
    *((_QWORD *)v11 + 6) = 0;
    *((_QWORD *)v11 + 7) = 0;
    v27 = operator new(0x18u);
    *(_OWORD *)v27 = 0;
    v27[2] = 1;
    v27[3] = 1;
    *(_QWORD *)v27 = &std::_Ref_count<XinputHid::XInputHidDevice>::`vftable';
    *((_QWORD *)v27 + 2) = v12;
    *((_QWORD *)v11 + 6) = v12;
    *((_QWORD *)v11 + 7) = v27;
    v13 = *((_QWORD *)a1 + 2) + 1LL;
    if ( v13 < 0 )
      v14 = (float)(v13 & 1 | (unsigned int)((unsigned __int64)v13 >> 1))
          + (float)(v13 & 1 | (unsigned int)((unsigned __int64)v13 >> 1));
    else
      v14 = (float)(int)v13;
    v15 = *((_QWORD *)a1 + 7);
    if ( v15 < 0 )
    {
      v17 = *((_QWORD *)a1 + 7) & 1LL | ((unsigned __int64)v15 >> 1);
      v16 = (float)(int)v17 + (float)(int)v17;
    }
    else
    {
      v16 = (float)(int)v15;
    }
    if ( (float)(v14 / v16) > *a1 )
    {
      std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::_Rehash_for_1(a1);
      v26 = *(_OWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::_Find_last<std::wstring>(
                         a1,
                         &v26,
                         (__int64)(v11 + 1),
                         v9);
    }
    v25 = 0;
    v18 = v26;
    v19 = *(_QWORD **)(v26 + 8);
    ++*((_QWORD *)a1 + 2);
    *(_QWORD *)v11 = v18;
    *((_QWORD *)v11 + 1) = v19;
    *v19 = v11;
    *(_QWORD *)(v18 + 8) = v11;
    v20 = *((_QWORD *)a1 + 3);
    v21 = 2 * (v9 & *((_QWORD *)a1 + 6));
    v22 = *(_QWORD *)(v20 + 16 * (v9 & *((_QWORD *)a1 + 6)));
    if ( v22 == *((_QWORD *)a1 + 1) )
    {
      *(_QWORD *)(v20 + 16 * (v9 & *((_QWORD *)a1 + 6))) = v11;
LABEL_23:
      *(_QWORD *)(v20 + 8 * v21 + 8) = v11;
      goto LABEL_24;
    }
    if ( v22 == v18 )
    {
      *(_QWORD *)(v20 + 16 * (v9 & *((_QWORD *)a1 + 6))) = v11;
    }
    else if ( *(_QWORD **)(v20 + 16 * (v9 & *((_QWORD *)a1 + 6)) + 8) == v19 )
    {
      goto LABEL_23;
    }
LABEL_24:
    *(_QWORD *)a2 = v11;
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>,void *>>>(&v24);
    return a2;
  }
  *(_QWORD *)a2 = *((_QWORD *)&v26 + 1);
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x18000e5a0  mov     [rsp-38h+arg_8], rbx
0x18000e5a5  push    rbp
0x18000e5a6  push    rsi
0x18000e5a7  push    rdi
0x18000e5a8  push    r12
0x18000e5aa  push    r13
0x18000e5ac  push    r14
0x18000e5ae  push    r15
0x18000e5b0  mov     rbp, rsp
0x18000e5b3  sub     rsp, 40h
0x18000e5b7  mov     rbx, r8
0x18000e5ba  mov     r14, rdx
0x18000e5bd  mov     rdi, rcx
0x18000e5c0  mov     r8, [r8+10h]
0x18000e5c4  cmp     qword ptr [rbx+18h], 7
0x18000e5c9  jbe     short loc_18000E5D0
0x18000e5cb  mov     rdx, [rbx]
0x18000e5ce  jmp     short loc_18000E5D3
0x18000e5d0  mov     rdx, rbx
0x18000e5d3  xor     ecx, ecx
0x18000e5d5  mov     r15, 0CBF29CE484222325h
0x18000e5df  add     r8, r8
0x18000e5e2  jz      short loc_18000E601
0x18000e5e4  movzx   eax, byte ptr [rdx+rcx]
0x18000e5e8  xor     r15, rax
0x18000e5eb  mov     r9, 100000001B3h
0x18000e5f5  imul    r15, r9
0x18000e5f9  inc     rcx
0x18000e5fc  cmp     rcx, r8
0x18000e5ff  jb      short loc_18000E5E4
0x18000e601  mov     r9, r15
0x18000e604  mov     r8, rbx
0x18000e607  lea     rdx, [rbp+var_10]
0x18000e60b  mov     rcx, rdi
0x18000e60e  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18000e613  mov     rax, qword ptr [rbp+var_10+8]
0x18000e617  test    rax, rax
0x18000e61a  jz      short loc_18000E629
0x18000e61c  mov     [r14], rax
0x18000e61f  mov     byte ptr [r14+8], 0
0x18000e624  jmp     loc_18000E7CE
0x18000e629  mov     rax, 3FFFFFFFFFFFFFFh
0x18000e633  cmp     [rdi+10h], rax
0x18000e637  jnz     short loc_18000E647
0x18000e639  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18000e640  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000e647  lea     r12, [rdi+8]
0x18000e64b  mov     [rbp+var_20], r12
0x18000e64f  mov     [rbp+var_18], 0
0x18000e657  mov     ecx, 40h ; '@'; Size
0x18000e65c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e661  mov     rsi, rax
0x18000e664  mov     [rbp+var_18], rax
0x18000e668  lea     r13, [rax+10h]
0x18000e66c  mov     [rbp+arg_0], r13
0x18000e670  xorps   xmm0, xmm0
0x18000e673  movups  xmmword ptr [r13+0], xmm0
0x18000e678  xor     ecx, ecx
0x18000e67a  mov     [r13+10h], rcx
0x18000e67e  mov     [r13+18h], rcx
0x18000e682  movups  xmm0, xmmword ptr [rbx]
0x18000e685  movups  xmmword ptr [r13+0], xmm0
0x18000e68a  movups  xmm1, xmmword ptr [rbx+10h]
0x18000e68e  movups  xmmword ptr [r13+10h], xmm1
0x18000e693  mov     [rbx+10h], rcx
0x18000e697  mov     qword ptr [rbx+18h], 7
0x18000e69f  mov     [rbx], cx
0x18000e6a2  mov     rbx, [rbx+20h]
0x18000e6a6  mov     [r13+20h], rcx
0x18000e6aa  mov     [r13+28h], rcx
0x18000e6ae  mov     [rbp+arg_10], rbx
0x18000e6b2  mov     ecx, 18h; Size
0x18000e6b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e6bc  mov     [rbp+arg_0], rax
0x18000e6c0  xorps   xmm0, xmm0
0x18000e6c3  movups  xmmword ptr [rax], xmm0
0x18000e6c6  mov     dword ptr [rax+8], 1
0x18000e6cd  mov     dword ptr [rax+0Ch], 1
0x18000e6d4  lea     rcx, ??_7?$_Ref_count@UXInputHidDevice@XinputHid@@@std@@6B@; const std::_Ref_count<XinputHid::XInputHidDevice>::`vftable'
0x18000e6db  mov     [rax], rcx
0x18000e6de  mov     [rax+10h], rbx
0x18000e6e2  mov     [r13+20h], rbx
0x18000e6e6  mov     [r13+28h], rax
0x18000e6ea  mov     rcx, [rdi+10h]
0x18000e6ee  add     rcx, 1
0x18000e6f2  xorps   xmm0, xmm0
0x18000e6f5  js      short loc_18000E6FE
0x18000e6f7  cvtsi2ss xmm0, rcx
0x18000e6fc  jmp     short loc_18000E713
0x18000e6fe  mov     rax, rcx
0x18000e701  shr     rax, 1
0x18000e704  and     ecx, 1
0x18000e707  or      rax, rcx
0x18000e70a  cvtsi2ss xmm0, rax
0x18000e70f  addss   xmm0, xmm0
0x18000e713  mov     rcx, [rdi+38h]
0x18000e717  xorps   xmm1, xmm1
0x18000e71a  test    rcx, rcx
0x18000e71d  js      short loc_18000E726
0x18000e71f  cvtsi2ss xmm1, rcx
0x18000e724  jmp     short loc_18000E73B
0x18000e726  mov     rax, rcx
0x18000e729  shr     rax, 1
0x18000e72c  and     ecx, 1
0x18000e72f  or      rax, rcx
0x18000e732  cvtsi2ss xmm1, rax
0x18000e737  addss   xmm1, xmm1
0x18000e73b  divss   xmm0, xmm1
0x18000e73f  comiss  xmm0, dword ptr [rdi]
0x18000e742  jbe     short loc_18000E766
0x18000e744  mov     rcx, rdi
0x18000e747  call    ?_Rehash_for_1@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::_Rehash_for_1(void)
0x18000e74c  mov     r9, r15
0x18000e74f  mov     r8, r13
0x18000e752  lea     rdx, [rbp+var_10]
0x18000e756  mov     rcx, rdi
0x18000e759  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18000e75e  movups  xmm0, xmmword ptr [rax]
0x18000e761  movdqu  [rbp+var_10], xmm0
0x18000e766  mov     [rbp+var_18], 0
0x18000e76e  mov     rdx, qword ptr [rbp+var_10]
0x18000e772  mov     r8, [rdx+8]
0x18000e776  inc     qword ptr [rdi+10h]
0x18000e77a  mov     [rsi], rdx
0x18000e77d  mov     [rsi+8], r8
0x18000e781  mov     [r8], rsi
0x18000e784  mov     [rdx+8], rsi
0x18000e788  mov     rcx, [rdi+18h]
0x18000e78c  mov     rax, [rdi+30h]
0x18000e790  and     rax, r15
0x18000e793  add     rax, rax
0x18000e796  mov     r9, [rcx+rax*8]
0x18000e79a  cmp     r9, [r12]
0x18000e79e  jnz     short loc_18000E7A6
0x18000e7a0  mov     [rcx+rax*8], rsi
0x18000e7a4  jmp     short loc_18000E7B8
0x18000e7a6  cmp     r9, rdx
0x18000e7a9  jnz     short loc_18000E7B1
0x18000e7ab  mov     [rcx+rax*8], rsi
0x18000e7af  jmp     short loc_18000E7BD
0x18000e7b1  cmp     [rcx+rax*8+8], r8
0x18000e7b6  jnz     short loc_18000E7BD
0x18000e7b8  mov     [rcx+rax*8+8], rsi
0x18000e7bd  mov     [r14], rsi
0x18000e7c0  mov     byte ptr [r14+8], 1
0x18000e7c5  lea     rcx, [rbp+var_20]
0x18000e7c9  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>,void *>>>(void)
0x18000e7ce  mov     rax, r14
0x18000e7d1  mov     rbx, [rsp+40h+arg_8]
0x18000e7d9  add     rsp, 40h
0x18000e7dd  pop     r15
0x18000e7df  pop     r14
0x18000e7e1  pop     r13
0x18000e7e3  pop     r12
0x18000e7e5  pop     rdi
0x18000e7e6  pop     rsi
0x18000e7e7  pop     rbp
0x18000e7e8  retn
```
