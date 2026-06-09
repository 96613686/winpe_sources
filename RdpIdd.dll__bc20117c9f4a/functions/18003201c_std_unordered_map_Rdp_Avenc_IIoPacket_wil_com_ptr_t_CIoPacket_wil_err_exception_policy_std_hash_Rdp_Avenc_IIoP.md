# std::unordered_map<Rdp::Avenc::IIoPacket *,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>,std::hash<Rdp::Avenc::IIoPacket *>,std::equal_to<Rdp::Avenc::IIoPacket *>,std::allocator<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>>::_Insert_or_assign<Rdp::Avenc::IIoPacket *,wil::com_ptr_t<CIoPacket,wil::err_exception_policy> &>(Rdp::Avenc::IIoPacket * &&,wil::com_ptr_t<CIoPacket,wil::err_exception_policy> &)

- ea: `0x18003201c`
- end: `0x1800321e1`
- name: `??$_Insert_or_assign@PEAUIIoPacket@Avenc@Rdp@@AEAV?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@?$unordered_map@PEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@U?$hash@PEAUIIoPacket@Avenc@Rdp@@@std@@U?$equal_to@PEAUIIoPacket@Avenc@Rdp@@@7@V?$allocator@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@@7@@std@@AEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@std@@_N@1@$$QEAPEAUIIoPacket@Avenc@Rdp@@AEAV?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@Z`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032c90`

## callees

- `0x1800086fc`
- `0x180013b38`
- `0x180020610`
- `0x180031a20`
- `0x180031fc0`
- `0x18003201c`
- `0x1800329e0`
- `0x180032be4`
- `0x1800359b8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180032094`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180032094`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::unordered_map<Rdp::Avenc::IIoPacket *,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>::_Insert_or_assign<Rdp::Avenc::IIoPacket *,wil::com_ptr_t<CIoPacket,wil::err_exception_policy> &>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4)
{
  __int64 v8; // r12
  __int64 v9; // rdx
  __int64 v10; // rbx
  _QWORD *v11; // rbx
  __int64 v12; // rdx
  float v13; // xmm0_4
  __int64 v14; // rcx
  float v15; // xmm1_4
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rdx
  _QWORD *v19; // r8
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // r9
  __int64 v24; // [rsp+20h] [rbp-68h] BYREF
  _QWORD *v25; // [rsp+28h] [rbp-60h]
  _OWORD v26[5]; // [rsp+30h] [rbp-58h] BYREF

  v8 = std::_Uhash_compare<Rdp::Avenc::IIoPacket *,std::hash<Rdp::Avenc::IIoPacket *>,std::equal_to<Rdp::Avenc::IIoPacket *>>::operator()<Rdp::Avenc::IIoPacket *>(
         a1,
         a3);
  std::_Hash<std::_Umap_traits<Rdp::Avenc::IIoPacket *,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>,std::_Uhash_compare<Rdp::Avenc::IIoPacket *,std::hash<Rdp::Avenc::IIoPacket *>,std::equal_to<Rdp::Avenc::IIoPacket *>>,std::allocator<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>,0>>::_Find_last<Rdp::Avenc::IIoPacket *>(
    a1,
    v26,
    v9,
    v8);
  v10 = *((_QWORD *)&v26[0] + 1);
  if ( !*((_QWORD *)&v26[0] + 1) )
  {
    if ( *(_QWORD *)(a1 + 16) == 0x7FFFFFFFFFFFFFFLL )
      std::_Xlength_error("unordered_map/set too long");
    v24 = a1 + 8;
    v11 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(32);
    v25 = v11;
    v11[2] = *a3;
    wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::com_ptr_t<CIoPacket,wil::err_exception_policy>(v11 + 3, *a4);
    v12 = *(_QWORD *)(a1 + 16) + 1LL;
    if ( v12 < 0 )
      v13 = (float)(v12 & 1 | (unsigned int)((unsigned __int64)v12 >> 1))
          + (float)(v12 & 1 | (unsigned int)((unsigned __int64)v12 >> 1));
    else
      v13 = (float)(int)v12;
    v14 = *(_QWORD *)(a1 + 56);
    if ( v14 < 0 )
    {
      v16 = *(_QWORD *)(a1 + 56) & 1LL | ((unsigned __int64)v14 >> 1);
      v15 = (float)(int)v16 + (float)(int)v16;
    }
    else
    {
      v15 = (float)(int)v14;
    }
    if ( (float)(v13 / v15) > *(float *)a1 )
    {
      v17 = std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::_Desired_grow_bucket_count(a1);
      std::_Hash<std::_Umap_traits<Rdp::Avenc::IIoPacket *,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>,std::_Uhash_compare<Rdp::Avenc::IIoPacket *,std::hash<Rdp::Avenc::IIoPacket *>,std::equal_to<Rdp::Avenc::IIoPacket *>>,std::allocator<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>,0>>::_Forced_rehash(
        a1,
        v17);
      v26[0] = *(_OWORD *)std::_Hash<std::_Umap_traits<Rdp::Avenc::IIoPacket *,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>,std::_Uhash_compare<Rdp::Avenc::IIoPacket *,std::hash<Rdp::Avenc::IIoPacket *>,std::equal_to<Rdp::Avenc::IIoPacket *>>,std::allocator<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>,0>>::_Find_last<Rdp::Avenc::IIoPacket *>(
                            a1,
                            v26,
                            v11 + 2,
                            v8);
    }
    v25 = 0;
    v18 = *(_QWORD *)&v26[0];
    v19 = *(_QWORD **)(*(_QWORD *)&v26[0] + 8LL);
    ++*(_QWORD *)(a1 + 16);
    *v11 = v18;
    v11[1] = v19;
    *v19 = v11;
    *(_QWORD *)(v18 + 8) = v11;
    v20 = 2 * (v8 & *(_QWORD *)(a1 + 48));
    v21 = *(_QWORD *)(a1 + 24);
    v22 = *(_QWORD *)(v21 + 16 * (v8 & *(_QWORD *)(a1 + 48)));
    if ( v22 == *(_QWORD *)(a1 + 8) )
    {
      *(_QWORD *)(v21 + 16 * (v8 & *(_QWORD *)(a1 + 48))) = v11;
LABEL_18:
      *(_QWORD *)(v21 + 8 * v20 + 8) = v11;
      goto LABEL_19;
    }
    if ( v22 == v18 )
    {
      *(_QWORD *)(v21 + 16 * (v8 & *(_QWORD *)(a1 + 48))) = v11;
    }
    else if ( *(_QWORD **)(v21 + 16 * (v8 & *(_QWORD *)(a1 + 48)) + 8) == v19 )
    {
      goto LABEL_18;
    }
LABEL_19:
    *(_QWORD *)a2 = v11;
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>,void *>>>(&v24);
    return a2;
  }
  wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::operator=(*((_QWORD *)&v26[0] + 1) + 24LL, a4);
  *(_QWORD *)a2 = v10;
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x18003201c  push    rbx
0x18003201e  push    rbp
0x18003201f  push    rsi
0x180032020  push    rdi
0x180032021  push    r12
0x180032023  push    r13
0x180032025  push    r14
0x180032027  push    r15
0x180032029  sub     rsp, 48h
0x18003202d  mov     r14, r9
0x180032030  mov     r15, r8
0x180032033  mov     rdi, rdx
0x180032036  mov     rsi, rcx
0x180032039  mov     rdx, r8
0x18003203c  call    ??$?RPEAUIIoPacket@Avenc@Rdp@@@?$_Uhash_compare@PEAUIIoPacket@Avenc@Rdp@@U?$hash@PEAUIIoPacket@Avenc@Rdp@@@std@@U?$equal_to@PEAUIIoPacket@Avenc@Rdp@@@5@@std@@QEBA_KAEBQEAUIIoPacket@Avenc@Rdp@@@Z; std::_Uhash_compare<Rdp::Avenc::IIoPacket *,std::hash<Rdp::Avenc::IIoPacket *>,std::equal_to<Rdp::Avenc::IIoPacket *>>::operator()<Rdp::Avenc::IIoPacket *>(Rdp::Avenc::IIoPacket * const &)
0x180032041  mov     r12, rax
0x180032044  mov     r9, rax
0x180032047  mov     r8, rdx
0x18003204a  lea     rdx, [rsp+88h+var_58]
0x18003204f  mov     rcx, rsi
0x180032052  call    ??$_Find_last@PEAUIIoPacket@Avenc@Rdp@@@?$_Hash@V?$_Umap_traits@PEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@PEAUIIoPacket@Avenc@Rdp@@U?$hash@PEAUIIoPacket@Avenc@Rdp@@@std@@U?$equal_to@PEAUIIoPacket@Avenc@Rdp@@@5@@std@@V?$allocator@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@@7@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@1@AEBQEAUIIoPacket@Avenc@Rdp@@_K@Z; std::_Hash<std::_Umap_traits<Rdp::Avenc::IIoPacket *,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>,std::_Uhash_compare<Rdp::Avenc::IIoPacket *,std::hash<Rdp::Avenc::IIoPacket *>,std::equal_to<Rdp::Avenc::IIoPacket *>>,std::allocator<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>,0>>::_Find_last<Rdp::Avenc::IIoPacket *>(Rdp::Avenc::IIoPacket * const &,unsigned __int64)
0x180032057  mov     rbx, qword ptr [rsp+88h+var_58+8]
0x18003205c  test    rbx, rbx
0x18003205f  jz      short loc_180032079
0x180032061  lea     rcx, [rbx+18h]
0x180032065  mov     rdx, r14
0x180032068  call    ??4?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::operator=(wil::com_ptr_t<CIoPacket,wil::err_exception_policy> const &)
0x18003206d  mov     [rdi], rbx
0x180032070  mov     byte ptr [rdi+8], 0
0x180032074  jmp     loc_1800321CC
0x180032079  lea     rbp, [rsi+8]
0x18003207d  mov     rax, 7FFFFFFFFFFFFFFh
0x180032087  cmp     [rbp+8], rax
0x18003208b  jnz     short loc_1800320A1
0x18003208d  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180032094  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800320a1  mov     [rsp+88h+var_68], rbp
0x1800320a6  mov     [rsp+88h+var_60], 0
0x1800320af  mov     ecx, 20h ; ' '
0x1800320b4  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800320b9  mov     rbx, rax
0x1800320bc  mov     [rsp+88h+var_60], rax
0x1800320c1  mov     rcx, [r15]
0x1800320c4  mov     [rax+10h], rcx
0x1800320c8  lea     rcx, [rax+18h]
0x1800320cc  mov     rdx, [r14]
0x1800320cf  call    ??0?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCIoPacket@@@Z; wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::com_ptr_t<CIoPacket,wil::err_exception_policy>(CIoPacket *)
0x1800320d4  nop
0x1800320d5  mov     rdx, [rsi+10h]
0x1800320d9  add     rdx, 1
0x1800320dd  xorps   xmm0, xmm0
0x1800320e0  js      short loc_1800320E9
0x1800320e2  cvtsi2ss xmm0, rdx
0x1800320e7  jmp     short loc_180032101
0x1800320e9  mov     rcx, rdx
0x1800320ec  shr     rcx, 1
0x1800320ef  mov     rax, rdx
0x1800320f2  and     eax, 1
0x1800320f5  or      rcx, rax
0x1800320f8  cvtsi2ss xmm0, rcx
0x1800320fd  addss   xmm0, xmm0
0x180032101  mov     rcx, [rsi+38h]
0x180032105  xorps   xmm1, xmm1
0x180032108  test    rcx, rcx
0x18003210b  js      short loc_180032114
0x18003210d  cvtsi2ss xmm1, rcx
0x180032112  jmp     short loc_180032129
0x180032114  mov     rax, rcx
0x180032117  shr     rax, 1
0x18003211a  and     ecx, 1
0x18003211d  or      rax, rcx
0x180032120  cvtsi2ss xmm1, rax
0x180032125  addss   xmm1, xmm1
0x180032129  divss   xmm0, xmm1
0x18003212d  comiss  xmm0, dword ptr [rsi]
0x180032130  jbe     short loc_180032162
0x180032132  mov     rcx, rsi
0x180032135  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@UFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@UFileIoChannelId@@U?$StdHasher@UFileIoChannelId@@@@U?$StdEqual@UFileIoChannelId@@@@@std@@V?$allocator@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x18003213a  mov     rdx, rax
0x18003213d  mov     rcx, rsi
0x180032140  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@PEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@PEAUIIoPacket@Avenc@Rdp@@U?$hash@PEAUIIoPacket@Avenc@Rdp@@@std@@U?$equal_to@PEAUIIoPacket@Avenc@Rdp@@@5@@std@@V?$allocator@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@@7@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<Rdp::Avenc::IIoPacket *,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>,std::_Uhash_compare<Rdp::Avenc::IIoPacket *,std::hash<Rdp::Avenc::IIoPacket *>,std::equal_to<Rdp::Avenc::IIoPacket *>>,std::allocator<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>,0>>::_Forced_rehash(unsigned __int64)
0x180032145  mov     r9, r12
0x180032148  lea     r8, [rbx+10h]
0x18003214c  lea     rdx, [rsp+88h+var_58]
0x180032151  mov     rcx, rsi
0x180032154  call    ??$_Find_last@PEAUIIoPacket@Avenc@Rdp@@@?$_Hash@V?$_Umap_traits@PEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@PEAUIIoPacket@Avenc@Rdp@@U?$hash@PEAUIIoPacket@Avenc@Rdp@@@std@@U?$equal_to@PEAUIIoPacket@Avenc@Rdp@@@5@@std@@V?$allocator@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@@7@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@1@AEBQEAUIIoPacket@Avenc@Rdp@@_K@Z; std::_Hash<std::_Umap_traits<Rdp::Avenc::IIoPacket *,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>,std::_Uhash_compare<Rdp::Avenc::IIoPacket *,std::hash<Rdp::Avenc::IIoPacket *>,std::equal_to<Rdp::Avenc::IIoPacket *>>,std::allocator<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>,0>>::_Find_last<Rdp::Avenc::IIoPacket *>(Rdp::Avenc::IIoPacket * const &,unsigned __int64)
0x180032159  movups  xmm0, xmmword ptr [rax]
0x18003215c  movdqu  [rsp+88h+var_58], xmm0
0x180032162  mov     [rsp+88h+var_60], 0
0x18003216b  mov     rdx, qword ptr [rsp+88h+var_58]
0x180032170  mov     r8, [rdx+8]
0x180032174  inc     qword ptr [rsi+10h]
0x180032178  mov     [rbx], rdx
0x18003217b  mov     [rbx+8], r8
0x18003217f  mov     [r8], rbx
0x180032182  mov     [rdx+8], rbx
0x180032186  mov     rax, [rsi+30h]
0x18003218a  and     rax, r12
0x18003218d  add     rax, rax
0x180032190  mov     rcx, [rsi+18h]
0x180032194  mov     r9, [rcx+rax*8]
0x180032198  cmp     r9, [rbp+0]
0x18003219c  jnz     short loc_1800321A4
0x18003219e  mov     [rcx+rax*8], rbx
0x1800321a2  jmp     short loc_1800321B6
0x1800321a4  cmp     r9, rdx
0x1800321a7  jnz     short loc_1800321AF
0x1800321a9  mov     [rcx+rax*8], rbx
0x1800321ad  jmp     short loc_1800321BB
0x1800321af  cmp     [rcx+rax*8+8], r8
0x1800321b4  jnz     short loc_1800321BB
0x1800321b6  mov     [rcx+rax*8+8], rbx
0x1800321bb  mov     [rdi], rbx
0x1800321be  mov     byte ptr [rdi+8], 1
0x1800321c2  lea     rcx, [rsp+88h+var_68]
0x1800321c7  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>,void *>>>(void)
0x1800321cc  mov     rax, rdi
0x1800321cf  add     rsp, 48h
0x1800321d3  pop     r15
0x1800321d5  pop     r14
0x1800321d7  pop     r13
0x1800321d9  pop     r12
0x1800321db  pop     rdi
0x1800321dc  pop     rsi
0x1800321dd  pop     rbp
0x1800321de  pop     rbx
0x1800321df  retn
```
