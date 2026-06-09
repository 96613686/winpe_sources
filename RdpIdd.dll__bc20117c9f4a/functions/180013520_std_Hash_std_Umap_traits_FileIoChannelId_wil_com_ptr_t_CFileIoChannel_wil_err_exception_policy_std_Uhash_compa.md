# std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::_Try_emplace<FileIoChannelId const &,>(FileIoChannelId const &)

- ea: `0x180013520`
- end: `0x1800136b2`
- name: `??$_Try_emplace@AEBUFileIoChannelId@@$$V@?$_Hash@V?$_Umap_traits@UFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@UFileIoChannelId@@U?$StdHasher@UFileIoChannelId@@@@U?$StdEqual@UFileIoChannelId@@@@@std@@V?$allocator@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@_N@1@AEBUFileIoChannelId@@@Z`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001818c`

## callees

- `0x180012190`
- `0x1800122b8`
- `0x18001303c`
- `0x180013520`
- `0x180014a48`
- `0x180020610`
- `0x180020990`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180013582`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180013582`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::_Try_emplace<FileIoChannelId const &,>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // r15
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  float v10; // xmm0_4
  __int64 v11; // rcx
  float v12; // xmm1_4
  __int64 v13; // rax
  __int64 v14; // rax
  _QWORD *v15; // rbx
  __int64 v16; // rdx
  _QWORD *v17; // r8
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // r9
  _BYTE v22[8]; // [rsp+30h] [rbp-28h] BYREF
  _QWORD *v23; // [rsp+38h] [rbp-20h]
  __int128 v24; // [rsp+40h] [rbp-18h] BYREF
  __int64 v25; // [rsp+90h] [rbp+38h] BYREF

  v6 = std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>::operator()<FileIoChannelId>(
         a1,
         a3);
  std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::_Find_last<FileIoChannelId>(
    a1,
    &v24,
    v7,
    v6);
  if ( !*((_QWORD *)&v24 + 1) )
  {
    if ( *(_QWORD *)(a1 + 16) == 0x3FFFFFFFFFFFFFFLL )
      std::_Xlength_error("unordered_map/set too long");
    v25 = a3;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>,void *>>>(
      v22,
      a1 + 8,
      v8,
      &v25);
    v9 = *(_QWORD *)(a1 + 16) + 1LL;
    if ( v9 < 0 )
      v10 = (float)(v9 & 1 | (unsigned int)((unsigned __int64)v9 >> 1))
          + (float)(v9 & 1 | (unsigned int)((unsigned __int64)v9 >> 1));
    else
      v10 = (float)(int)v9;
    v11 = *(_QWORD *)(a1 + 56);
    if ( v11 < 0 )
    {
      v13 = *(_QWORD *)(a1 + 56) & 1LL | ((unsigned __int64)v11 >> 1);
      v12 = (float)(int)v13 + (float)(int)v13;
    }
    else
    {
      v12 = (float)(int)v11;
    }
    if ( (float)(v10 / v12) <= *(float *)a1 )
    {
      v15 = v23;
    }
    else
    {
      v14 = std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::_Desired_grow_bucket_count(a1);
      std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::_Forced_rehash(
        a1,
        v14);
      v15 = v23;
      v24 = *(_OWORD *)std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::_Find_last<FileIoChannelId>(
                         a1,
                         &v24,
                         v23 + 2,
                         v6);
    }
    v23 = 0;
    v16 = v24;
    v17 = *(_QWORD **)(v24 + 8);
    ++*(_QWORD *)(a1 + 16);
    *v15 = v16;
    v15[1] = v17;
    *v17 = v15;
    *(_QWORD *)(v16 + 8) = v15;
    v18 = 2 * (v6 & *(_QWORD *)(a1 + 48));
    v19 = *(_QWORD *)(a1 + 24);
    v20 = *(_QWORD *)(v19 + 16 * (v6 & *(_QWORD *)(a1 + 48)));
    if ( v20 == *(_QWORD *)(a1 + 8) )
    {
      *(_QWORD *)(v19 + 16 * (v6 & *(_QWORD *)(a1 + 48))) = v15;
LABEL_19:
      *(_QWORD *)(v19 + 8 * v18 + 8) = v15;
      goto LABEL_20;
    }
    if ( v20 == v16 )
    {
      *(_QWORD *)(v19 + 16 * (v6 & *(_QWORD *)(a1 + 48))) = v15;
    }
    else if ( *(_QWORD **)(v19 + 16 * (v6 & *(_QWORD *)(a1 + 48)) + 8) == v17 )
    {
      goto LABEL_19;
    }
LABEL_20:
    *(_QWORD *)a2 = v15;
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>,void *>>>(v22);
    return a2;
  }
  *(_QWORD *)a2 = *((_QWORD *)&v24 + 1);
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x180013520  push    rbp
0x180013522  push    rbx
0x180013523  push    rsi
0x180013524  push    rdi
0x180013525  push    r14
0x180013527  push    r15
0x180013529  mov     rbp, rsp
0x18001352c  sub     rsp, 58h
0x180013530  mov     rbx, r8
0x180013533  mov     rdi, rdx
0x180013536  mov     rsi, rcx
0x180013539  mov     rdx, r8
0x18001353c  call    ??$?RUFileIoChannelId@@@?$_Uhash_compare@UFileIoChannelId@@U?$StdHasher@UFileIoChannelId@@@@U?$StdEqual@UFileIoChannelId@@@@@std@@QEBA_KAEBUFileIoChannelId@@@Z; std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>::operator()<FileIoChannelId>(FileIoChannelId const &)
0x180013541  mov     r15, rax
0x180013544  mov     r9, rax
0x180013547  mov     r8, rdx
0x18001354a  lea     rdx, [rbp+var_18]
0x18001354e  mov     rcx, rsi
0x180013551  call    ??$_Find_last@UFileIoChannelId@@@?$_Hash@V?$_Umap_traits@UFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@UFileIoChannelId@@U?$StdHasher@UFileIoChannelId@@@@U?$StdEqual@UFileIoChannelId@@@@@std@@V?$allocator@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@1@AEBUFileIoChannelId@@_K@Z; std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::_Find_last<FileIoChannelId>(FileIoChannelId const &,unsigned __int64)
0x180013556  mov     rcx, qword ptr [rbp+var_18+8]
0x18001355a  test    rcx, rcx
0x18001355d  jz      short loc_18001356B
0x18001355f  mov     [rdi], rcx
0x180013562  mov     byte ptr [rdi+8], 0
0x180013566  jmp     loc_1800136A1
0x18001356b  mov     rax, 3FFFFFFFFFFFFFFh
0x180013575  cmp     [rsi+10h], rax
0x180013579  jnz     short loc_18001358F
0x18001357b  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180013582  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001358f  mov     [rbp+arg_0], rbx
0x180013593  lea     r9, [rbp+arg_0]
0x180013597  lea     rdx, [rsi+8]
0x18001359b  lea     rcx, [rbp+var_28]
0x18001359f  call    ??$?0AEBUpiecewise_construct_t@std@@V?$tuple@AEBUFileIoChannelId@@@1@V?$tuple@$$V@1@@?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_List_node@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBUFileIoChannelId@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>,void *>>>(std::allocator<std::_List_node<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>,void *>> &,std::piecewise_construct_t const &,std::tuple<FileIoChannelId const &> &&,std::tuple<> &&)
0x1800135a4  nop
0x1800135a5  mov     rdx, [rsi+10h]
0x1800135a9  add     rdx, 1
0x1800135ad  xorps   xmm0, xmm0
0x1800135b0  js      short loc_1800135B9
0x1800135b2  cvtsi2ss xmm0, rdx
0x1800135b7  jmp     short loc_1800135D1
0x1800135b9  mov     rcx, rdx
0x1800135bc  shr     rcx, 1
0x1800135bf  mov     rax, rdx
0x1800135c2  and     eax, 1
0x1800135c5  or      rcx, rax
0x1800135c8  cvtsi2ss xmm0, rcx
0x1800135cd  addss   xmm0, xmm0
0x1800135d1  mov     rcx, [rsi+38h]
0x1800135d5  xorps   xmm1, xmm1
0x1800135d8  test    rcx, rcx
0x1800135db  js      short loc_1800135E4
0x1800135dd  cvtsi2ss xmm1, rcx
0x1800135e2  jmp     short loc_1800135F9
0x1800135e4  mov     rax, rcx
0x1800135e7  shr     rax, 1
0x1800135ea  and     ecx, 1
0x1800135ed  or      rax, rcx
0x1800135f0  cvtsi2ss xmm1, rax
0x1800135f5  addss   xmm1, xmm1
0x1800135f9  divss   xmm0, xmm1
0x1800135fd  comiss  xmm0, dword ptr [rsi]
0x180013600  jbe     short loc_180013636
0x180013602  mov     rcx, rsi
0x180013605  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@UFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@UFileIoChannelId@@U?$StdHasher@UFileIoChannelId@@@@U?$StdEqual@UFileIoChannelId@@@@@std@@V?$allocator@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x18001360a  mov     rdx, rax
0x18001360d  mov     rcx, rsi
0x180013610  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@UFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@UFileIoChannelId@@U?$StdHasher@UFileIoChannelId@@@@U?$StdEqual@UFileIoChannelId@@@@@std@@V?$allocator@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::_Forced_rehash(unsigned __int64)
0x180013615  mov     rbx, [rbp+var_20]
0x180013619  lea     r8, [rbx+10h]
0x18001361d  mov     r9, r15
0x180013620  lea     rdx, [rbp+var_18]
0x180013624  mov     rcx, rsi
0x180013627  call    ??$_Find_last@UFileIoChannelId@@@?$_Hash@V?$_Umap_traits@UFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@UFileIoChannelId@@U?$StdHasher@UFileIoChannelId@@@@U?$StdEqual@UFileIoChannelId@@@@@std@@V?$allocator@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@1@AEBUFileIoChannelId@@_K@Z; std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::_Find_last<FileIoChannelId>(FileIoChannelId const &,unsigned __int64)
0x18001362c  movups  xmm0, xmmword ptr [rax]
0x18001362f  movdqu  [rbp+var_18], xmm0
0x180013634  jmp     short loc_18001363A
0x180013636  mov     rbx, [rbp+var_20]
0x18001363a  mov     [rbp+var_20], 0
0x180013642  mov     rdx, qword ptr [rbp+var_18]
0x180013646  mov     r8, [rdx+8]
0x18001364a  inc     qword ptr [rsi+10h]
0x18001364e  mov     [rbx], rdx
0x180013651  mov     [rbx+8], r8
0x180013655  mov     [r8], rbx
0x180013658  mov     [rdx+8], rbx
0x18001365c  mov     rax, [rsi+30h]
0x180013660  and     rax, r15
0x180013663  add     rax, rax
0x180013666  mov     rcx, [rsi+18h]
0x18001366a  mov     r9, [rcx+rax*8]
0x18001366e  cmp     r9, [rsi+8]
0x180013672  jnz     short loc_18001367A
0x180013674  mov     [rcx+rax*8], rbx
0x180013678  jmp     short loc_18001368C
0x18001367a  cmp     r9, rdx
0x18001367d  jnz     short loc_180013685
0x18001367f  mov     [rcx+rax*8], rbx
0x180013683  jmp     short loc_180013691
0x180013685  cmp     [rcx+rax*8+8], r8
0x18001368a  jnz     short loc_180013691
0x18001368c  mov     [rcx+rax*8+8], rbx
0x180013691  mov     [rdi], rbx
0x180013694  mov     byte ptr [rdi+8], 1
0x180013698  lea     rcx, [rbp+var_28]
0x18001369c  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>,void *>>>(void)
0x1800136a1  mov     rax, rdi
0x1800136a4  add     rsp, 58h
0x1800136a8  pop     r15
0x1800136aa  pop     r14
0x1800136ac  pop     rdi
0x1800136ad  pop     rsi
0x1800136ae  pop     rbx
0x1800136af  pop     rbp
0x1800136b0  retn
```
