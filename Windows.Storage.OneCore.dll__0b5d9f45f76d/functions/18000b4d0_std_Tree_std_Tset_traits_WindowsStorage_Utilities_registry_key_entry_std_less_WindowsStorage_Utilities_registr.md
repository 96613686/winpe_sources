# std::_Tree<std::_Tset_traits<WindowsStorage::Utilities::registry_key_entry,std::less<WindowsStorage::Utilities::registry_key_entry>,std::allocator<WindowsStorage::Utilities::registry_key_entry>,0>>::_Find_hint<WindowsStorage::Utilities::registry_key_entry>(std::_Tree_node<WindowsStorage::Utilities::registry_key_entry,void *> * const,WindowsStorage::Utilities::registry_key_entry const &)

- ea: `0x18000b4d0`
- end: `0x18000b7eb`
- name: `??$_Find_hint@Vregistry_key_entry@Utilities@WindowsStorage@@@?$_Tree@V?$_Tset_traits@Vregistry_key_entry@Utilities@WindowsStorage@@U?$less@Vregistry_key_entry@Utilities@WindowsStorage@@@std@@V?$allocator@Vregistry_key_entry@Utilities@WindowsStorage@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_hint_result@PEAU?$_Tree_node@Vregistry_key_entry@Utilities@WindowsStorage@@PEAX@std@@@1@QEAU?$_Tree_node@Vregistry_key_entry@Utilities@WindowsStorage@@PEAX@1@AEBVregistry_key_entry@Utilities@WindowsStorage@@@Z`
- size: `795`
- prototype: `__int64 __fastcall(_QWORD **, __int64, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ae6c`

## callees

- `0x18000b4d0`
- `0x18000b974`
- `0x18000d9c0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b540`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b5a2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b5f0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b669`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b6c5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b71c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b76b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b540`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b5a2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b5f0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b669`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b6c5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b71c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b76b`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<WindowsStorage::Utilities::registry_key_entry,std::less<WindowsStorage::Utilities::registry_key_entry>,std::allocator<WindowsStorage::Utilities::registry_key_entry>,0>>::_Find_hint<WindowsStorage::Utilities::registry_key_entry>(
        _QWORD **a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4)
{
  _QWORD *v6; // rdx
  _QWORD *v9; // rbx
  const WCHAR ***v10; // r14
  _QWORD *v11; // rax
  const WCHAR *v12; // r8
  _QWORD *v13; // rax
  const WCHAR *v14; // rcx
  const WCHAR **v15; // rax
  const WCHAR *v16; // r8
  const WCHAR **v17; // rax
  const WCHAR *v18; // rcx
  const WCHAR *v19; // r8
  const WCHAR **v20; // rax
  const WCHAR *v21; // rcx
  const WCHAR *v22; // rcx
  __int64 *v23; // rbx
  __int64 *v24; // rax
  const WCHAR *v25; // r8
  const WCHAR **v26; // rax
  bool v27; // zf
  const WCHAR *v28; // r8
  const WCHAR **v29; // rax
  const WCHAR *v30; // rcx
  __int64 v31; // rax
  const WCHAR *v32; // rcx
  __int64 v33; // rbx
  const WCHAR **v34; // rax
  const WCHAR *v35; // r8
  __int64 v36; // rbx
  _QWORD *v37; // rax
  const WCHAR *v38; // r8
  const WCHAR *v39; // rcx
  __int128 v42; // [rsp+30h] [rbp-68h] BYREF
  __int64 v43; // [rsp+40h] [rbp-58h]
  __int64 *v44; // [rsp+A0h] [rbp+8h] BYREF

  v6 = *a1;
  if ( !*((_BYTE *)a3 + 25) )
  {
    v15 = (const WCHAR **)a3[5];
    if ( a3 == (__int64 *)*v6 )
    {
      if ( v15 )
        v16 = *v15;
      else
        v16 = 0;
      v10 = (const WCHAR ***)(a4 + 8);
      v17 = *(const WCHAR ***)(a4 + 8);
      if ( v17 )
        v18 = *v17;
      else
        v18 = 0;
      if ( CompareStringOrdinal(v18, -1, v16, -1, 1) != 1 )
        goto LABEL_63;
      *(_QWORD *)(a2 + 8) = 1;
      *(_BYTE *)(a2 + 16) = 0;
    }
    else
    {
      if ( v15 )
        v19 = *v15;
      else
        v19 = 0;
      v10 = (const WCHAR ***)(a4 + 8);
      v20 = *(const WCHAR ***)(a4 + 8);
      if ( v20 )
        v21 = *v20;
      else
        v21 = 0;
      if ( CompareStringOrdinal(v21, -1, v19, -1, 1) == 1 )
      {
        v22 = 0;
        if ( *((_BYTE *)a3 + 25) )
        {
          v23 = (__int64 *)a3[2];
        }
        else
        {
          v23 = (__int64 *)*a3;
          if ( *(_BYTE *)(*a3 + 25) )
          {
            v23 = (__int64 *)a3[1];
            v24 = a3;
            while ( !*((_BYTE *)v23 + 25) && v24 == (__int64 *)*v23 )
            {
              v24 = v23;
              v23 = (__int64 *)v23[1];
            }
            if ( *((_BYTE *)v24 + 25) )
              v23 = v24;
          }
          else
          {
            while ( !*(_BYTE *)(v23[2] + 25) )
              v23 = (__int64 *)v23[2];
          }
        }
        if ( *v10 )
          v25 = **v10;
        else
          v25 = 0;
        v26 = (const WCHAR **)v23[5];
        if ( v26 )
          v22 = *v26;
        if ( CompareStringOrdinal(v22, -1, v25, -1, 1) != 1 )
          goto LABEL_63;
        v27 = *(_BYTE *)(v23[2] + 25) == 0;
        *(_BYTE *)(a2 + 16) = 0;
        if ( !v27 )
        {
          *(_QWORD *)a2 = v23;
          *(_QWORD *)(a2 + 8) = 0;
          goto LABEL_81;
        }
        *(_QWORD *)(a2 + 8) = 1;
      }
      else
      {
        if ( *v10 )
          v28 = **v10;
        else
          v28 = 0;
        v29 = (const WCHAR **)a3[5];
        if ( v29 )
          v30 = *v29;
        else
          v30 = 0;
        if ( CompareStringOrdinal(v30, -1, v28, -1, 1) == 1 )
        {
          v44 = a3;
          v31 = std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsStorage::Utilities::registry_key_entry>>,std::_Iterator_base0>::operator++(&v44);
          v32 = 0;
          v33 = *(_QWORD *)v31;
          if ( !*(_BYTE *)(*(_QWORD *)v31 + 25LL) )
          {
            v34 = *(const WCHAR ***)(v33 + 40);
            if ( v34 )
              v35 = *v34;
            else
              v35 = 0;
            if ( *v10 )
              v32 = **v10;
            if ( CompareStringOrdinal(v32, -1, v35, -1, 1) != 1 )
              goto LABEL_63;
          }
          v27 = *(_BYTE *)(a3[2] + 25) == 0;
          *(_BYTE *)(a2 + 16) = 0;
          if ( v27 )
          {
            *(_QWORD *)a2 = v33;
            *(_QWORD *)(a2 + 8) = 1;
            goto LABEL_81;
          }
          *(_QWORD *)(a2 + 8) = 0;
        }
        else
        {
          *(_QWORD *)(a2 + 8) = 0;
          *(_BYTE *)(a2 + 16) = 1;
        }
      }
    }
    *(_QWORD *)a2 = a3;
    goto LABEL_81;
  }
  v9 = v6 + 2;
  if ( !*(_BYTE *)(v6[1] + 25LL) )
  {
    v10 = (const WCHAR ***)(a4 + 8);
    v11 = *(_QWORD **)(a4 + 8);
    v12 = v11 ? (const WCHAR *)*v11 : 0LL;
    v13 = *(_QWORD **)(*v9 + 40LL);
    v14 = v13 ? (const WCHAR *)*v13 : 0LL;
    if ( CompareStringOrdinal(v14, -1, v12, -1, 1) != 1 )
    {
LABEL_63:
      std::_Tree<std::_Tset_traits<WindowsStorage::Utilities::registry_key_entry,std::less<WindowsStorage::Utilities::registry_key_entry>,std::allocator<WindowsStorage::Utilities::registry_key_entry>,0>>::_Find_lower_bound<WindowsStorage::Utilities::registry_key_entry>(
        a1,
        &v42,
        a4);
      v36 = v43;
      if ( !*(_BYTE *)(v43 + 25) )
      {
        v37 = *(_QWORD **)(v43 + 40);
        v38 = v37 ? (const WCHAR *)*v37 : 0LL;
        v39 = *v10 ? **v10 : 0LL;
        if ( CompareStringOrdinal(v39, -1, v38, -1, 1) != 1 )
        {
          *(_QWORD *)a2 = v36;
          *(_QWORD *)(a2 + 8) = 2;
          *(_BYTE *)(a2 + 16) = 1;
          goto LABEL_81;
        }
      }
      *(_OWORD *)a2 = v42;
      goto LABEL_11;
    }
  }
  *(_QWORD *)a2 = *v9;
  *(_QWORD *)(a2 + 8) = 0;
LABEL_11:
  *(_BYTE *)(a2 + 16) = 0;
LABEL_81:
  *(_DWORD *)(a2 + 17) = 0;
  *(_WORD *)(a2 + 21) = 0;
  *(_BYTE *)(a2 + 23) = 0;
  return a2;
}

```

## disassembly

```asm
0x18000b4d0  push    rbx
0x18000b4d2  push    rbp
0x18000b4d3  push    rsi
0x18000b4d4  push    rdi
0x18000b4d5  push    r12
0x18000b4d7  push    r13
0x18000b4d9  push    r14
0x18000b4db  push    r15
0x18000b4dd  sub     rsp, 58h
0x18000b4e1  xor     ebx, ebx
0x18000b4e3  mov     rdi, rdx
0x18000b4e6  mov     r13, r9
0x18000b4e9  mov     rdx, [rcx]
0x18000b4ec  mov     rsi, r8
0x18000b4ef  mov     r12, rcx
0x18000b4f2  cmp     [r8+19h], bl
0x18000b4f6  jz      short loc_18000B565
0x18000b4f8  mov     rax, [rdx+8]
0x18000b4fc  lea     rbx, [rdx+10h]
0x18000b500  cmp     byte ptr [rax+19h], 0
0x18000b504  jnz     short loc_18000B54E
0x18000b506  mov     rcx, [rbx]
0x18000b509  lea     r14, [r9+8]
0x18000b50d  mov     rax, [r14]
0x18000b510  test    rax, rax
0x18000b513  jz      short loc_18000B51A
0x18000b515  mov     r8, [rax]
0x18000b518  jmp     short loc_18000B51D
0x18000b51a  xor     r8d, r8d; lpString2
0x18000b51d  mov     rax, [rcx+28h]
0x18000b521  test    rax, rax
0x18000b524  jz      short loc_18000B52B
0x18000b526  mov     rcx, [rax]
0x18000b529  jmp     short loc_18000B52D
0x18000b52b  xor     ecx, ecx; lpString1
0x18000b52d  or      r15d, 0FFFFFFFFh
0x18000b531  mov     ebp, 1
0x18000b536  mov     r9d, r15d; cchCount2
0x18000b539  mov     [rsp+98h+bIgnoreCase], ebp; bIgnoreCase
0x18000b53d  mov     edx, r15d; cchCount1
0x18000b540  call    cs:__imp_CompareStringOrdinal
0x18000b546  cmp     eax, ebp
0x18000b548  jnz     loc_18000B726
0x18000b54e  mov     rax, [rbx]
0x18000b551  mov     [rdi], rax
0x18000b554  mov     qword ptr [rdi+8], 0
0x18000b55c  mov     byte ptr [rdi+10h], 0
0x18000b560  jmp     loc_18000B7CB
0x18000b565  mov     rax, [r8+28h]
0x18000b569  cmp     rsi, [rdx]
0x18000b56c  jnz     short loc_18000B5BC
0x18000b56e  test    rax, rax
0x18000b571  jz      short loc_18000B578
0x18000b573  mov     r8, [rax]
0x18000b576  jmp     short loc_18000B57B
0x18000b578  mov     r8, rbx; lpString2
0x18000b57b  lea     r14, [r9+8]
0x18000b57f  mov     rax, [r14]
0x18000b582  test    rax, rax
0x18000b585  jz      short loc_18000B58C
0x18000b587  mov     rcx, [rax]
0x18000b58a  jmp     short loc_18000B58F
0x18000b58c  mov     rcx, rbx; lpString1
0x18000b58f  or      r15d, 0FFFFFFFFh
0x18000b593  mov     ebp, 1
0x18000b598  mov     r9d, r15d; cchCount2
0x18000b59b  mov     [rsp+98h+bIgnoreCase], ebp; bIgnoreCase
0x18000b59f  mov     edx, r15d; cchCount1
0x18000b5a2  call    cs:__imp_CompareStringOrdinal
0x18000b5a8  cmp     eax, ebp
0x18000b5aa  jnz     loc_18000B726
0x18000b5b0  mov     [rdi+8], rbp
0x18000b5b4  mov     [rdi+10h], bl
0x18000b5b7  jmp     loc_18000B7C8
0x18000b5bc  test    rax, rax
0x18000b5bf  jz      short loc_18000B5C6
0x18000b5c1  mov     r8, [rax]
0x18000b5c4  jmp     short loc_18000B5C9
0x18000b5c6  mov     r8, rbx; lpString2
0x18000b5c9  lea     r14, [r9+8]
0x18000b5cd  mov     rax, [r14]
0x18000b5d0  test    rax, rax
0x18000b5d3  jz      short loc_18000B5DA
0x18000b5d5  mov     rcx, [rax]
0x18000b5d8  jmp     short loc_18000B5DD
0x18000b5da  mov     rcx, rbx; lpString1
0x18000b5dd  or      r15d, 0FFFFFFFFh
0x18000b5e1  mov     ebp, 1
0x18000b5e6  mov     r9d, r15d; cchCount2
0x18000b5e9  mov     [rsp+98h+bIgnoreCase], ebp; bIgnoreCase
0x18000b5ed  mov     edx, r15d; cchCount1
0x18000b5f0  call    cs:__imp_CompareStringOrdinal
0x18000b5f6  cmp     eax, ebp
0x18000b5f8  jnz     loc_18000B69A
0x18000b5fe  xor     ecx, ecx
0x18000b600  cmp     [rsi+19h], bl
0x18000b603  jz      short loc_18000B60B
0x18000b605  mov     rbx, [rsi+10h]
0x18000b609  jmp     short loc_18000B643
0x18000b60b  mov     rbx, [rsi]
0x18000b60e  cmp     [rbx+19h], cl
0x18000b611  jz      short loc_18000B63A
0x18000b613  mov     rbx, [rsi+8]
0x18000b617  mov     rax, rsi
0x18000b61a  jmp     short loc_18000B628
0x18000b61c  cmp     rax, [rbx]
0x18000b61f  jnz     short loc_18000B62D
0x18000b621  mov     rax, rbx
0x18000b624  mov     rbx, [rbx+8]
0x18000b628  cmp     [rbx+19h], cl
0x18000b62b  jz      short loc_18000B61C
0x18000b62d  cmp     [rax+19h], cl
0x18000b630  cmovnz  rbx, rax
0x18000b634  jmp     short loc_18000B643
0x18000b636  mov     rbx, [rbx+10h]
0x18000b63a  mov     rax, [rbx+10h]
0x18000b63e  cmp     [rax+19h], cl
0x18000b641  jz      short loc_18000B636
0x18000b643  mov     rax, [r14]
0x18000b646  test    rax, rax
0x18000b649  jz      short loc_18000B650
0x18000b64b  mov     r8, [rax]
0x18000b64e  jmp     short loc_18000B653
0x18000b650  mov     r8, rcx; lpString2
0x18000b653  mov     rax, [rbx+28h]
0x18000b657  test    rax, rax
0x18000b65a  jz      short loc_18000B65F
0x18000b65c  mov     rcx, [rax]; lpString1
0x18000b65f  mov     r9d, r15d; cchCount2
0x18000b662  mov     [rsp+98h+bIgnoreCase], ebp; bIgnoreCase
0x18000b666  mov     edx, r15d; cchCount1
0x18000b669  call    cs:__imp_CompareStringOrdinal
0x18000b66f  cmp     eax, ebp
0x18000b671  jnz     loc_18000B726
0x18000b677  mov     rax, [rbx+10h]
0x18000b67b  xor     ecx, ecx
0x18000b67d  cmp     [rax+19h], cl
0x18000b680  mov     [rdi+10h], cl
0x18000b683  jz      short loc_18000B691
0x18000b685  mov     [rdi], rbx
0x18000b688  mov     [rdi+8], rcx
0x18000b68c  jmp     loc_18000B7CB
0x18000b691  mov     [rdi+8], rbp
0x18000b695  jmp     loc_18000B7C8
0x18000b69a  mov     rax, [r14]
0x18000b69d  test    rax, rax
0x18000b6a0  jz      short loc_18000B6A7
0x18000b6a2  mov     r8, [rax]
0x18000b6a5  jmp     short loc_18000B6AA
0x18000b6a7  mov     r8, rbx; lpString2
0x18000b6aa  mov     rax, [rsi+28h]
0x18000b6ae  test    rax, rax
0x18000b6b1  jz      short loc_18000B6B8
0x18000b6b3  mov     rcx, [rax]
0x18000b6b6  jmp     short loc_18000B6BB
0x18000b6b8  mov     rcx, rbx; lpString1
0x18000b6bb  mov     r9d, r15d; cchCount2
0x18000b6be  mov     [rsp+98h+bIgnoreCase], ebp; bIgnoreCase
0x18000b6c2  mov     edx, r15d; cchCount1
0x18000b6c5  call    cs:__imp_CompareStringOrdinal
0x18000b6cb  cmp     eax, ebp
0x18000b6cd  jnz     loc_18000B7C0
0x18000b6d3  lea     rcx, [rsp+98h+arg_0]
0x18000b6db  mov     [rsp+98h+arg_0], rsi
0x18000b6e3  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@Vregistry_key_entry@Utilities@WindowsStorage@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsStorage::Utilities::registry_key_entry>>,std::_Iterator_base0>::operator++(void)
0x18000b6e8  xor     ecx, ecx
0x18000b6ea  mov     rbx, [rax]
0x18000b6ed  cmp     [rbx+19h], cl
0x18000b6f0  jnz     loc_18000B7A1
0x18000b6f6  mov     rax, [rbx+28h]
0x18000b6fa  test    rax, rax
0x18000b6fd  jz      short loc_18000B704
0x18000b6ff  mov     r8, [rax]
0x18000b702  jmp     short loc_18000B707
0x18000b704  mov     r8, rcx; lpString2
0x18000b707  mov     rax, [r14]
0x18000b70a  test    rax, rax
0x18000b70d  jz      short loc_18000B712
0x18000b70f  mov     rcx, [rax]; lpString1
0x18000b712  mov     r9d, r15d; cchCount2
0x18000b715  mov     [rsp+98h+bIgnoreCase], ebp; bIgnoreCase
0x18000b719  mov     edx, r15d; cchCount1
0x18000b71c  call    cs:__imp_CompareStringOrdinal
0x18000b722  cmp     eax, ebp
0x18000b724  jz      short loc_18000B79F
0x18000b726  mov     r8, r13
0x18000b729  lea     rdx, [rsp+98h+var_68]
0x18000b72e  mov     rcx, r12
0x18000b731  call    ??$_Find_lower_bound@Vregistry_key_entry@Utilities@WindowsStorage@@@?$_Tree@V?$_Tset_traits@Vregistry_key_entry@Utilities@WindowsStorage@@U?$less@Vregistry_key_entry@Utilities@WindowsStorage@@@std@@V?$allocator@Vregistry_key_entry@Utilities@WindowsStorage@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@Vregistry_key_entry@Utilities@WindowsStorage@@PEAX@std@@@1@AEBVregistry_key_entry@Utilities@WindowsStorage@@@Z; std::_Tree<std::_Tset_traits<WindowsStorage::Utilities::registry_key_entry,std::less<WindowsStorage::Utilities::registry_key_entry>,std::allocator<WindowsStorage::Utilities::registry_key_entry>,0>>::_Find_lower_bound<WindowsStorage::Utilities::registry_key_entry>(WindowsStorage::Utilities::registry_key_entry const &)
0x18000b736  mov     rbx, [rsp+98h+var_58]
0x18000b73b  cmp     byte ptr [rbx+19h], 0
0x18000b73f  jnz     short loc_18000B77A
0x18000b741  mov     rax, [rbx+28h]
0x18000b745  test    rax, rax
0x18000b748  jz      short loc_18000B74F
0x18000b74a  mov     r8, [rax]
0x18000b74d  jmp     short loc_18000B752
0x18000b74f  xor     r8d, r8d; lpString2
0x18000b752  mov     rax, [r14]
0x18000b755  test    rax, rax
0x18000b758  jz      short loc_18000B75F
0x18000b75a  mov     rcx, [rax]
0x18000b75d  jmp     short loc_18000B761
0x18000b75f  xor     ecx, ecx; lpString1
0x18000b761  mov     r9d, r15d; cchCount2
0x18000b764  mov     [rsp+98h+bIgnoreCase], ebp; bIgnoreCase
0x18000b768  mov     edx, r15d; cchCount1
0x18000b76b  call    cs:__imp_CompareStringOrdinal
0x18000b771  cmp     eax, ebp
0x18000b773  jz      short loc_18000B77A
0x18000b775  mov     al, bpl
0x18000b778  jmp     short loc_18000B77C
0x18000b77a  xor     al, al
0x18000b77c  test    al, al
0x18000b77e  jz      short loc_18000B791
0x18000b780  mov     [rdi], rbx
0x18000b783  mov     qword ptr [rdi+8], 2
0x18000b78b  mov     [rdi+10h], bpl
0x18000b78f  jmp     short loc_18000B7CB
0x18000b791  movups  xmm0, [rsp+98h+var_68]
0x18000b796  movdqu  xmmword ptr [rdi], xmm0
0x18000b79a  jmp     loc_18000B55C
0x18000b79f  xor     ecx, ecx
0x18000b7a1  mov     rax, [rsi+10h]
0x18000b7a5  cmp     [rax+19h], cl
0x18000b7a8  mov     [rdi+10h], cl
0x18000b7ab  jz      short loc_18000B7B7
0x18000b7ad  mov     qword ptr [rdi+8], 0
0x18000b7b5  jmp     short loc_18000B7C8
0x18000b7b7  mov     [rdi], rbx
0x18000b7ba  mov     [rdi+8], rbp
0x18000b7be  jmp     short loc_18000B7CB
0x18000b7c0  mov     [rdi+8], rbx
0x18000b7c4  mov     [rdi+10h], bpl
0x18000b7c8  mov     [rdi], rsi
0x18000b7cb  xor     eax, eax
0x18000b7cd  mov     [rdi+11h], eax
0x18000b7d0  mov     [rdi+15h], ax
0x18000b7d4  mov     [rdi+17h], al
0x18000b7d7  mov     rax, rdi
0x18000b7da  add     rsp, 58h
0x18000b7de  pop     r15
0x18000b7e0  pop     r14
0x18000b7e2  pop     r13
0x18000b7e4  pop     r12
0x18000b7e6  pop     rdi
0x18000b7e7  pop     rsi
0x18000b7e8  pop     rbp
0x18000b7e9  pop     rbx
0x18000b7ea  retn
```
