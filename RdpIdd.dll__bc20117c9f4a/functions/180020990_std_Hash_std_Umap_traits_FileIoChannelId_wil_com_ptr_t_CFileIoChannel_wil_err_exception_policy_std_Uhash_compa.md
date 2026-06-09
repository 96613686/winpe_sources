# std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x180020990`
- end: `0x180020b43`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@UFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@UFileIoChannelId@@U?$StdHasher@UFileIoChannelId@@@@U?$StdEqual@UFileIoChannelId@@@@@std@@V?$allocator@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@IEAAX_K@Z`
- size: `435`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013520`

## callees

- `0x180007b14`
- `0x1800122b8`
- `0x1800151f0`
- `0x18002040c`
- `0x180020990`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800209d0`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800209d0`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  __int64 v4; // rbp
  unsigned __int64 v5; // rcx
  __int64 *v6; // rsi
  __int64 v7; // rbx
  _QWORD *v8; // rcx
  _QWORD *v9; // rbx
  _QWORD *v10; // rdi
  __int64 v11; // rax
  __int64 v12; // r15
  __int64 v13; // r14
  _QWORD *v14; // rsi
  _QWORD *v15; // r8
  _QWORD *v16; // rdx
  _QWORD *v17; // rax
  _QWORD *v18; // r8
  _QWORD *v19; // r8
  _QWORD *v20; // rdx
  _QWORD *v21; // rax
  _QWORD *v22; // rdx
  _QWORD *v23; // rax
  __int64 v25; // [rsp+78h] [rbp+10h] BYREF

  LODWORD(v25) = 0;
  _BitScanReverse64(&v3, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v3 )
    std::_Xlength_error("invalid hash bucket count");
  v4 = a1[1];
  LODWORD(v25) = 0;
  _BitScanReverse64(&v5, (a2 - 1) | 1);
  v6 = a1 + 3;
  v7 = 1LL << ((unsigned __int8)v5 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>>>>>::_Assign_grow(
    a1 + 3,
    2 * v7,
    v4);
  a1[7] = v7;
  a1[6] = v7 - 1;
  v9 = *(_QWORD **)a1[1];
  v10 = v9;
  while ( v9 != (_QWORD *)v4 )
  {
    v10 = (_QWORD *)*v10;
    v11 = std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>::operator()<FileIoChannelId>(
            v8,
            v9 + 2);
    v12 = *v6;
    v13 = 2 * (a1[6] & v11);
    if ( *(_QWORD *)(*v6 + 16 * (a1[6] & v11)) == v4 )
    {
      *(_QWORD *)(v12 + 16 * (a1[6] & v11)) = v9;
      *(_QWORD *)(v12 + 8 * v13 + 8) = v9;
    }
    else
    {
      v14 = *(_QWORD **)(v12 + 16 * (a1[6] & v11) + 8);
      if ( !memcmp_0(v9 + 2, v14 + 2, 0x28u) )
      {
        v15 = (_QWORD *)*v14;
        if ( (_QWORD *)*v14 != v9 )
        {
          v16 = (_QWORD *)v9[1];
          *v16 = v10;
          v8 = (_QWORD *)v10[1];
          *v8 = v15;
          v17 = (_QWORD *)v15[1];
          *v17 = v9;
          v15[1] = v8;
          v10[1] = v16;
          v9[1] = v17;
        }
        *(_QWORD *)(v12 + 8 * v13 + 8) = v9;
      }
      else
      {
        while ( 1 )
        {
          v18 = v14 + 1;
          if ( *(_QWORD **)(v12 + 8 * v13) == v14 )
            break;
          v14 = (_QWORD *)*v18;
          if ( !memcmp_0(v9 + 2, (const void *)(*v18 + 16LL), 0x28u) )
          {
            v19 = (_QWORD *)*v14;
            v20 = (_QWORD *)v9[1];
            *v20 = v10;
            v8 = (_QWORD *)v10[1];
            *v8 = v19;
            v21 = (_QWORD *)v19[1];
            *v21 = v9;
            v19[1] = v8;
            v10[1] = v20;
            v9[1] = v21;
            goto LABEL_15;
          }
        }
        v22 = (_QWORD *)v9[1];
        *v22 = v10;
        v23 = (_QWORD *)v10[1];
        *v23 = v14;
        v8 = (_QWORD *)*v18;
        *v8 = v9;
        *v18 = v23;
        v10[1] = v22;
        v9[1] = v8;
        *(_QWORD *)(v12 + 8 * v13) = v9;
      }
LABEL_15:
      v6 = a1 + 3;
    }
    v9 = v10;
  }
  v25 = 0;
  return std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::_Clear_guard::~_Clear_guard(&v25);
}

```

## disassembly

```asm
0x180020990  push    rbx
0x180020992  push    rbp
0x180020993  push    rsi
0x180020994  push    rdi
0x180020995  push    r12
0x180020997  push    r13
0x180020999  push    r14
0x18002099b  push    r15
0x18002099d  sub     rsp, 28h
0x1800209a1  mov     rax, 0FFFFFFFFFFFFFFFh
0x1800209ab  mov     dword ptr [rsp+68h+arg_8], 0
0x1800209b3  mov     r13, rcx
0x1800209b6  mov     ebx, 1
0x1800209bb  bsr     rcx, rax
0x1800209bf  mov     eax, ebx
0x1800209c1  shl     rax, cl
0x1800209c4  cmp     rdx, rax
0x1800209c7  jbe     short loc_1800209DD
0x1800209c9  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x1800209d0  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800209dd  mov     rbp, [r13+8]
0x1800209e1  lea     rax, [rdx-1]
0x1800209e5  or      rax, rbx
0x1800209e8  mov     dword ptr [rsp+68h+arg_8], 0
0x1800209f0  bsr     rcx, rax
0x1800209f4  lea     rsi, [r13+18h]
0x1800209f8  mov     r8, rbp
0x1800209fb  inc     ecx
0x1800209fd  shl     rbx, cl
0x180020a00  mov     rcx, rsi
0x180020a03  lea     rdx, [rbx+rbx]
0x180020a07  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>>>)
0x180020a0c  lea     rax, [rbx-1]
0x180020a10  mov     [r13+38h], rbx
0x180020a14  mov     [r13+30h], rax
0x180020a18  mov     rbx, [r13+8]
0x180020a1c  mov     rbx, [rbx]
0x180020a1f  mov     rdi, rbx
0x180020a22  cmp     rbx, rbp
0x180020a25  jz      loc_180020B1E
0x180020a2b  mov     rdi, [rdi]
0x180020a2e  lea     r12, [rbx+10h]
0x180020a32  mov     rdx, r12
0x180020a35  call    ??$?RUFileIoChannelId@@@?$_Uhash_compare@UFileIoChannelId@@U?$StdHasher@UFileIoChannelId@@@@U?$StdEqual@UFileIoChannelId@@@@@std@@QEBA_KAEBUFileIoChannelId@@@Z; std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>::operator()<FileIoChannelId>(FileIoChannelId const &)
0x180020a3a  mov     r15, [rsi]
0x180020a3d  mov     r14, rax
0x180020a40  and     r14, [r13+30h]
0x180020a44  add     r14, r14
0x180020a47  cmp     [r15+r14*8], rbp
0x180020a4b  jnz     short loc_180020A5B
0x180020a4d  mov     [r15+r14*8], rbx
0x180020a51  mov     [r15+r14*8+8], rbx
0x180020a56  jmp     loc_180020B16
0x180020a5b  mov     rsi, [r15+r14*8+8]
0x180020a60  mov     r8d, 28h ; '('; Size
0x180020a66  mov     rcx, r12; Buf1
0x180020a69  lea     rdx, [rsi+10h]; Buf2
0x180020a6d  call    memcmp_0
0x180020a72  test    eax, eax
0x180020a74  jnz     short loc_180020AA6
0x180020a76  mov     r8, [rsi]
0x180020a79  cmp     r8, rbx
0x180020a7c  jz      short loc_180020A9F
0x180020a7e  mov     rdx, [rbx+8]
0x180020a82  mov     [rdx], rdi
0x180020a85  mov     rcx, [rdi+8]
0x180020a89  mov     [rcx], r8
0x180020a8c  mov     rax, [r8+8]
0x180020a90  mov     [rax], rbx
0x180020a93  mov     [r8+8], rcx
0x180020a97  mov     [rdi+8], rdx
0x180020a9b  mov     [rbx+8], rax
0x180020a9f  mov     [r15+r14*8+8], rbx
0x180020aa4  jmp     short loc_180020B12
0x180020aa6  lea     r8, [rsi+8]
0x180020aaa  cmp     [r15+r14*8], rsi
0x180020aae  jz      short loc_180020AEF
0x180020ab0  mov     rsi, [r8]
0x180020ab3  mov     rcx, r12; Buf1
0x180020ab6  mov     r8d, 28h ; '('; Size
0x180020abc  lea     rdx, [rsi+10h]; Buf2
0x180020ac0  call    memcmp_0
0x180020ac5  test    eax, eax
0x180020ac7  jnz     short loc_180020AA6
0x180020ac9  mov     r8, [rsi]
0x180020acc  mov     rdx, [rbx+8]
0x180020ad0  mov     [rdx], rdi
0x180020ad3  mov     rcx, [rdi+8]
0x180020ad7  mov     [rcx], r8
0x180020ada  mov     rax, [r8+8]
0x180020ade  mov     [rax], rbx
0x180020ae1  mov     [r8+8], rcx
0x180020ae5  mov     [rdi+8], rdx
0x180020ae9  mov     [rbx+8], rax
0x180020aed  jmp     short loc_180020B12
0x180020aef  mov     rdx, [rbx+8]
0x180020af3  mov     [rdx], rdi
0x180020af6  mov     rax, [rdi+8]
0x180020afa  mov     [rax], rsi
0x180020afd  mov     rcx, [r8]
0x180020b00  mov     [rcx], rbx
0x180020b03  mov     [r8], rax
0x180020b06  mov     [rdi+8], rdx
0x180020b0a  mov     [rbx+8], rcx
0x180020b0e  mov     [r15+r14*8], rbx
0x180020b12  lea     rsi, [r13+18h]
0x180020b16  mov     rbx, rdi
0x180020b19  jmp     loc_180020A22
0x180020b1e  lea     rcx, [rsp+68h+arg_8]
0x180020b23  mov     [rsp+68h+arg_8], 0
0x180020b2c  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@UFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@UFileIoChannelId@@U?$StdHasher@UFileIoChannelId@@@@U?$StdEqual@UFileIoChannelId@@@@@std@@V?$allocator@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::_Clear_guard::~_Clear_guard(void)
0x180020b31  add     rsp, 28h
0x180020b35  pop     r15
0x180020b37  pop     r14
0x180020b39  pop     r13
0x180020b3b  pop     r12
0x180020b3d  pop     rdi
0x180020b3e  pop     rsi
0x180020b3f  pop     rbp
0x180020b40  pop     rbx
0x180020b41  retn
```
