# std::filesystem::path::operator/=(std::filesystem::path const &)

- ea: `0x18001b540`
- end: `0x18001b7fe`
- name: `??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z`
- size: `702`
- prototype: `std::filesystem *__fastcall(std::filesystem *Src, std::filesystem *)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x180016760`
- `0x18001b800`
- `0x18001d320`

## callees

- `0x180010320`
- `0x1800127c0`
- `0x180012900`
- `0x180014440`
- `0x180015250`
- `0x18001b430`
- `0x18001b540`
- `0x18003c020`

## pseudocode

```c
std::filesystem *__fastcall std::filesystem::path::operator/=(std::filesystem *Src, std::filesystem *a2)
{
  std::filesystem *v2; // rdi
  std::filesystem *v4; // rsi
  __int64 v5; // rcx
  const wchar_t *v6; // r8
  __int64 v7; // rdx
  __int16 v8; // ax
  std::filesystem *v9; // r15
  std::filesystem *v10; // r12
  __int64 v11; // rax
  const wchar_t *v12; // r13
  const wchar_t *v13; // r14
  const wchar_t *root_name_end; // rsi
  const wchar_t *v15; // r8
  const wchar_t *v16; // rax
  const wchar_t *v17; // rbp
  unsigned __int64 v18; // r13
  size_t v19; // r8
  unsigned __int64 v20; // rsi
  std::filesystem *v21; // rax
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rdx
  std::filesystem *v24; // rax
  unsigned __int64 v25; // rdx
  __int64 v26; // rcx
  unsigned __int64 v27; // r14
  __int64 v28; // rsi
  std::filesystem *v29; // rdi
  __int16 v30; // ax
  unsigned __int64 v31; // rcx
  unsigned __int64 v32; // rdx
  std::filesystem *v33; // rax
  unsigned __int64 v35; // [rsp+30h] [rbp-48h]
  const wchar_t *v36; // [rsp+38h] [rbp-40h]

  v2 = a2;
  v4 = a2;
  if ( *((_QWORD *)a2 + 3) > 7u )
    v4 = *(std::filesystem **)a2;
  v5 = *((_QWORD *)a2 + 2);
  v6 = (const wchar_t *)(2 * v5);
  v7 = (2 * v5) >> 1;
  if ( v7 < 2 || (*(_DWORD *)v4 & 0xFFFFFFDF) - 3801153 >= 0x1A )
  {
    if ( v4 == (std::filesystem *)std::filesystem::_Find_root_name_end(
                                    v4,
                                    (const wchar_t *const)((char *)v4 + (_QWORD)v6),
                                    v6) )
    {
      v5 = *((_QWORD *)v2 + 2);
      goto LABEL_15;
    }
  }
  else if ( v7 < 3 || (v8 = *((_WORD *)v4 + 2), v8 != 92) && v8 != 47 )
  {
LABEL_15:
    v9 = Src;
    if ( *((_QWORD *)Src + 3) > 7u )
      v9 = *(std::filesystem **)Src;
    v10 = v2;
    v11 = *((_QWORD *)Src + 2);
    v12 = (const wchar_t *)((char *)v9 + 2 * v11);
    v36 = v12;
    if ( *((_QWORD *)v2 + 3) > 7u )
      v10 = *(std::filesystem **)v2;
    v13 = (const wchar_t *)((char *)v10 + 2 * v5);
    root_name_end = std::filesystem::_Find_root_name_end(v9, (const wchar_t *const)v9 + v11, v6);
    v16 = std::filesystem::_Find_root_name_end(v10, v13, v15);
    v17 = v16;
    if ( v10 != (std::filesystem *)v16 )
    {
      v18 = ((char *)v16 - (char *)v10) >> 1;
      v35 = ((char *)root_name_end - (char *)v9) >> 1;
      v19 = v35;
      if ( v18 < v35 )
        v19 = ((char *)v16 - (char *)v10) >> 1;
      if ( wmemcmp((const wchar_t *)v9, (const wchar_t *)v10, v19) || v35 < v18 || v35 > v18 )
      {
        if ( Src == v2 )
          return Src;
        if ( *((_QWORD *)v2 + 3) > 7u )
          v2 = *(std::filesystem **)v2;
        goto LABEL_13;
      }
      v12 = v36;
    }
    if ( v17 != v13 && (*v17 == 92 || *v17 == 47) )
    {
      v20 = ((char *)root_name_end - (char *)v9) >> 1;
      if ( *((_QWORD *)Src + 2) < v20 )
        std::_String_val<std::_Simple_types<char>>::_Xran();
      *((_QWORD *)Src + 2) = v20;
      v21 = Src;
      if ( *((_QWORD *)Src + 3) > 7u )
      {
        _mm_lfence();
        v21 = *(std::filesystem **)Src;
      }
      *((_WORD *)v21 + v20) = 0;
      goto LABEL_45;
    }
    if ( root_name_end == v12 )
    {
      if ( (__int64)(((char *)root_name_end - (char *)v9) & 0xFFFFFFFFFFFFFFFEuLL) < 6 )
        goto LABEL_45;
      _mm_lfence();
      v22 = *((_QWORD *)Src + 2);
      v23 = *((_QWORD *)Src + 3);
      if ( v22 < v23 )
      {
        *((_QWORD *)Src + 2) = v22 + 1;
        v24 = Src;
        if ( v23 > 7 )
        {
          _mm_lfence();
          v24 = *(std::filesystem **)Src;
        }
        *(_DWORD *)((char *)v24 + 2 * v22) = 92;
        goto LABEL_45;
      }
      _mm_lfence();
    }
    else
    {
      v30 = *(v12 - 1);
      if ( v30 == 92 || v30 == 47 )
      {
LABEL_45:
        v25 = *((_QWORD *)Src + 3);
        v26 = *((_QWORD *)Src + 2);
        v27 = v13 - v17;
        _mm_lfence();
        if ( v27 > v25 - v26 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64>(
            Src,
            v27);
        }
        else
        {
          v28 = v26 + v27;
          v29 = Src;
          *((_QWORD *)Src + 2) = v26 + v27;
          if ( v25 > 7 )
            v29 = *(std::filesystem **)Src;
          memmove((char *)v29 + 2 * v26, v17, 2 * v27);
          *((_WORD *)v29 + v28) = 0;
        }
        return Src;
      }
      v31 = *((_QWORD *)Src + 2);
      v32 = *((_QWORD *)Src + 3);
      if ( v31 < v32 )
      {
        *((_QWORD *)Src + 2) = v31 + 1;
        v33 = Src;
        if ( v32 > 7 )
          v33 = *(std::filesystem **)Src;
        *(_DWORD *)((char *)v33 + 2 * v31) = 92;
        goto LABEL_45;
      }
    }
    std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(Src);
    goto LABEL_45;
  }
  if ( Src != v2 )
  {
    if ( *((_QWORD *)v2 + 3) > 7u )
      v2 = *(std::filesystem **)v2;
LABEL_13:
    std::wstring::assign(Src, v2);
  }
  return Src;
}

```

## disassembly

```asm
0x18001b540  push    rbx
0x18001b542  push    rsi
0x18001b543  push    rdi
0x18001b544  sub     rsp, 60h
0x18001b548  cmp     qword ptr [rdx+18h], 7
0x18001b54d  mov     rdi, rdx
0x18001b550  mov     rbx, rcx
0x18001b553  mov     rsi, rdx
0x18001b556  jbe     short loc_18001B55B
0x18001b558  mov     rsi, [rdx]
0x18001b55b  mov     rcx, [rdx+10h]
0x18001b55f  mov     [rsp+78h+arg_10], rbp
0x18001b567  mov     [rsp+78h+var_20], r12
0x18001b56c  mov     [rsp+78h+var_28], r13
0x18001b571  lea     r8, [rcx+rcx]; wchar_t *
0x18001b575  mov     [rsp+78h+var_30], r14
0x18001b57a  mov     rdx, r8
0x18001b57d  mov     [rsp+78h+var_38], r15
0x18001b582  sar     rdx, 1
0x18001b585  cmp     rdx, 2
0x18001b589  jl      short loc_18001B5B2
0x18001b58b  mov     eax, [rsi]
0x18001b58d  and     eax, 0FFFFFFDFh
0x18001b590  sub     eax, 3A0041h
0x18001b595  cmp     eax, 1Ah
0x18001b598  jnb     short loc_18001B5B2
0x18001b59a  cmp     rdx, 3
0x18001b59e  jl      short loc_18001B5EE
0x18001b5a0  movzx   eax, word ptr [rsi+4]
0x18001b5a4  cmp     ax, 5Ch ; '\'
0x18001b5a8  jz      short loc_18001B5C3
0x18001b5aa  cmp     ax, 2Fh ; '/'
0x18001b5ae  jz      short loc_18001B5C3
0x18001b5b0  jmp     short loc_18001B5EE
0x18001b5b2  lea     rdx, [r8+rsi]; wchar_t *
0x18001b5b6  mov     rcx, rsi; this
0x18001b5b9  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x18001b5be  cmp     rsi, rax
0x18001b5c1  jz      short loc_18001B5EA
0x18001b5c3  cmp     rbx, rdi
0x18001b5c6  jz      loc_18001B7D1
0x18001b5cc  cmp     qword ptr [rdi+18h], 7
0x18001b5d1  mov     r8, [rdi+10h]
0x18001b5d5  jbe     short loc_18001B5DA
0x18001b5d7  mov     rdi, [rdi]
0x18001b5da  mov     rdx, rdi; Src
0x18001b5dd  mov     rcx, rbx; void *
0x18001b5e0  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x18001b5e5  jmp     loc_18001B7D1
0x18001b5ea  mov     rcx, [rdi+10h]
0x18001b5ee  cmp     qword ptr [rbx+18h], 7
0x18001b5f3  mov     r15, rbx
0x18001b5f6  jbe     short loc_18001B5FB
0x18001b5f8  mov     r15, [rbx]
0x18001b5fb  cmp     qword ptr [rdi+18h], 7
0x18001b600  mov     r12, rdi
0x18001b603  mov     rax, [rbx+10h]
0x18001b607  lea     r13, [r15+rax*2]
0x18001b60b  mov     [rsp+78h+var_40], r13
0x18001b610  jbe     short loc_18001B615
0x18001b612  mov     r12, [rdi]
0x18001b615  lea     r14, [r12+rcx*2]
0x18001b619  mov     rdx, r13; wchar_t *
0x18001b61c  mov     rcx, r15; this
0x18001b61f  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x18001b624  mov     rdx, r14; wchar_t *
0x18001b627  mov     rcx, r12; this
0x18001b62a  mov     rsi, rax
0x18001b62d  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x18001b632  mov     rbp, rax
0x18001b635  cmp     r12, rax
0x18001b638  jz      short loc_18001B69F
0x18001b63a  mov     r13, rax
0x18001b63d  mov     rdx, r12; S2
0x18001b640  sub     r13, r12
0x18001b643  mov     rax, rsi
0x18001b646  sub     rax, r15
0x18001b649  sar     r13, 1
0x18001b64c  sar     rax, 1
0x18001b64f  mov     rcx, r15; S1
0x18001b652  cmp     r13, rax
0x18001b655  mov     [rsp+78h+var_48], rax
0x18001b65a  mov     r8, rax
0x18001b65d  cmovb   r8, r13; N
0x18001b661  call    wmemcmp
0x18001b666  test    eax, eax
0x18001b668  jnz     short loc_18001B673
0x18001b66a  cmp     [rsp+78h+var_48], r13
0x18001b66f  jb      short loc_18001B673
0x18001b671  jbe     short loc_18001B69A
0x18001b673  cmp     rbx, rdi
0x18001b676  jz      loc_18001B7D1
0x18001b67c  cmp     qword ptr [rdi+18h], 7
0x18001b681  mov     r8, [rdi+10h]
0x18001b685  jbe     short loc_18001B68A
0x18001b687  mov     rdi, [rdi]
0x18001b68a  mov     rdx, rdi; Src
0x18001b68d  mov     rcx, rbx; void *
0x18001b690  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x18001b695  jmp     loc_18001B7D1
0x18001b69a  mov     r13, [rsp+78h+var_40]
0x18001b69f  xor     r12d, r12d
0x18001b6a2  cmp     rbp, r14
0x18001b6a5  jz      short loc_18001B6E2
0x18001b6a7  movzx   eax, word ptr [rbp+0]
0x18001b6ab  cmp     ax, 5Ch ; '\'
0x18001b6af  jz      short loc_18001B6B7
0x18001b6b1  cmp     ax, 2Fh ; '/'
0x18001b6b5  jnz     short loc_18001B6E2
0x18001b6b7  sub     rsi, r15
0x18001b6ba  sar     rsi, 1
0x18001b6bd  cmp     [rbx+10h], rsi
0x18001b6c1  jb      loc_18001B7F8
0x18001b6c7  mov     [rbx+10h], rsi
0x18001b6cb  mov     rax, rbx
0x18001b6ce  cmp     qword ptr [rbx+18h], 7
0x18001b6d3  jbe     short loc_18001B6DB
0x18001b6d5  lfence
0x18001b6d8  mov     rax, [rbx]
0x18001b6db  mov     [rax+rsi*2], r12w
0x18001b6e0  jmp     short loc_18001B739
0x18001b6e2  cmp     rsi, r13
0x18001b6e5  jnz     loc_18001B780
0x18001b6eb  sub     rsi, r15
0x18001b6ee  and     rsi, 0FFFFFFFFFFFFFFFEh
0x18001b6f2  cmp     rsi, 6
0x18001b6f6  jl      short loc_18001B739
0x18001b6f8  lfence
0x18001b6fb  mov     rcx, [rbx+10h]
0x18001b6ff  mov     rdx, [rbx+18h]
0x18001b703  cmp     rcx, rdx
0x18001b706  jnb     short loc_18001B728
0x18001b708  lea     rax, [rcx+1]
0x18001b70c  mov     [rbx+10h], rax
0x18001b710  mov     rax, rbx
0x18001b713  cmp     rdx, 7
0x18001b717  jbe     short loc_18001B71F
0x18001b719  lfence
0x18001b71c  mov     rax, [rbx]
0x18001b71f  mov     dword ptr [rax+rcx*2], 5Ch ; '\'
0x18001b726  jmp     short loc_18001B739
0x18001b728  lfence
0x18001b72b  mov     r9d, 5Ch ; '\'
0x18001b731  mov     rcx, rbx; Src
0x18001b734  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x18001b739  mov     rdx, [rbx+18h]
0x18001b73d  sub     r14, rbp
0x18001b740  mov     rcx, [rbx+10h]
0x18001b744  mov     rax, rdx
0x18001b747  sar     r14, 1
0x18001b74a  sub     rax, rcx
0x18001b74d  lfence
0x18001b750  cmp     r14, rax
0x18001b753  ja      short loc_18001B7BE
0x18001b755  lea     rsi, [rcx+r14]
0x18001b759  mov     rdi, rbx
0x18001b75c  mov     [rbx+10h], rsi
0x18001b760  cmp     rdx, 7
0x18001b764  jbe     short loc_18001B769
0x18001b766  mov     rdi, [rbx]
0x18001b769  lea     r8, [r14+r14]; Size
0x18001b76d  mov     rdx, rbp; Src
0x18001b770  lea     rcx, [rdi+rcx*2]; void *
0x18001b774  call    memmove
0x18001b779  mov     [rdi+rsi*2], r12w
0x18001b77e  jmp     short loc_18001B7D1
0x18001b780  movzx   eax, word ptr [r13-2]
0x18001b785  cmp     ax, 5Ch ; '\'
0x18001b789  jz      short loc_18001B739
0x18001b78b  cmp     ax, 2Fh ; '/'
0x18001b78f  jz      short loc_18001B739
0x18001b791  mov     rcx, [rbx+10h]
0x18001b795  mov     rdx, [rbx+18h]
0x18001b799  cmp     rcx, rdx
0x18001b79c  jnb     short loc_18001B72B
0x18001b79e  lea     rax, [rcx+1]
0x18001b7a2  mov     [rbx+10h], rax
0x18001b7a6  mov     rax, rbx
0x18001b7a9  cmp     rdx, 7
0x18001b7ad  jbe     short loc_18001B7B2
0x18001b7af  mov     rax, [rbx]
0x18001b7b2  mov     dword ptr [rax+rcx*2], 5Ch ; '\'
0x18001b7b9  jmp     loc_18001B739
0x18001b7be  mov     r9, rbp
0x18001b7c1  mov     [rsp+78h+var_58], r14; __int64
0x18001b7c6  mov     rdx, r14
0x18001b7c9  mov     rcx, rbx; Src
0x18001b7cc  call    ??$_Reallocate_grow_by@V_lambda_1dfe18491bcca09701d8ccb01d0b0af4_@@PEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1dfe18491bcca09701d8ccb01d0b0af4_@@PEB_W_K@Z; std::wstring::_Reallocate_grow_by<_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64>(unsigned __int64,_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64)
0x18001b7d1  mov     r15, [rsp+78h+var_38]
0x18001b7d6  mov     rax, rbx
0x18001b7d9  mov     r14, [rsp+78h+var_30]
0x18001b7de  mov     r13, [rsp+78h+var_28]
0x18001b7e3  mov     r12, [rsp+78h+var_20]
0x18001b7e8  mov     rbp, [rsp+78h+arg_10]
0x18001b7f0  add     rsp, 60h
0x18001b7f4  pop     rdi
0x18001b7f5  pop     rsi
0x18001b7f6  pop     rbx
0x18001b7f7  retn
0x18001b7f8  call    ?_Xran@?$_String_val@U?$_Simple_types@D@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<char>>::_Xran(void)
```
