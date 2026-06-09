# CRdpIdAdapter::FindFileIoChannel(FileIoChannelId const &,bool)

- ea: `0x180016834`
- end: `0x180016907`
- name: `?FindFileIoChannel@CRdpIdAdapter@@QEAA?AV?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@AEBUFileIoChannelId@@_N@Z`
- size: `211`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011a60`
- `0x180011c30`
- `0x180017b74`
- `0x1800185bc`

## callees

- `0x18000d6d8`
- `0x18000eb00`
- `0x1800122b8`
- `0x18001303c`
- `0x1800138fc`
- `0x180013b38`
- `0x180016834`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800168ea`
- `msvcp_win!_Mtx_unlock` at `0x1800168ea`

## pseudocode

```c
_QWORD *__fastcall CRdpIdAdapter::FindFileIoChannel(__int64 a1, _QWORD *a2, __int64 a3, char a4)
{
  struct _Mtx_internal_imp_t *v4; // rsi
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rbx
  _BYTE v13[80]; // [rsp+28h] [rbp-50h] BYREF
  __int64 v14; // [rsp+80h] [rbp+8h] BYREF

  v4 = (struct _Mtx_internal_imp_t *)(a1 + 200);
  std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 200));
  v10 = std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>::operator()<FileIoChannelId>(
          v9,
          a3);
  v11 = *(_QWORD *)(std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::_Find_last<FileIoChannelId>(
                      a1 + 280,
                      v13,
                      a3,
                      v10)
                  + 8);
  if ( !v11 )
    v11 = *(_QWORD *)(a1 + 288);
  if ( v11 == *(_QWORD *)(a1 + 288) )
  {
    *a2 = 0;
  }
  else
  {
    wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::com_ptr_t<CIoPacket,wil::err_exception_policy>(
      &v14,
      *(_QWORD *)(v11 + 56));
    if ( a4 )
      std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>>>,0>(
        a1 + 280,
        v13,
        v11);
    *a2 = v14;
    v14 = 0;
    wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::~com_ptr_t<CIoPacket,wil::err_exception_policy>(&v14);
  }
  _Mtx_unlock(v4);
  return a2;
}

```

## disassembly

```asm
0x180016834  push    rbx
0x180016836  push    rbp
0x180016837  push    rsi
0x180016838  push    rdi
0x180016839  push    r14
0x18001683b  push    r15
0x18001683d  sub     rsp, 48h
0x180016841  lea     rsi, [rcx+0C8h]
0x180016848  mov     r14, rcx
0x18001684b  mov     rcx, rsi; this
0x18001684e  mov     r15b, r9b
0x180016851  mov     rbx, r8
0x180016854  mov     rdi, rdx
0x180016857  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001685c  mov     rdx, rbx
0x18001685f  lea     rbp, [r14+118h]
0x180016866  call    ??$?RUFileIoChannelId@@@?$_Uhash_compare@UFileIoChannelId@@U?$StdHasher@UFileIoChannelId@@@@U?$StdEqual@UFileIoChannelId@@@@@std@@QEBA_KAEBUFileIoChannelId@@@Z; std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>::operator()<FileIoChannelId>(FileIoChannelId const &)
0x18001686b  mov     r9, rax
0x18001686e  lea     rdx, [rsp+78h+var_50]
0x180016873  mov     r8, rbx
0x180016876  mov     rcx, rbp
0x180016879  call    ??$_Find_last@UFileIoChannelId@@@?$_Hash@V?$_Umap_traits@UFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@UFileIoChannelId@@U?$StdHasher@UFileIoChannelId@@@@U?$StdEqual@UFileIoChannelId@@@@@std@@V?$allocator@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@1@AEBUFileIoChannelId@@_K@Z; std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::_Find_last<FileIoChannelId>(FileIoChannelId const &,unsigned __int64)
0x18001687e  mov     rbx, [rax+8]
0x180016882  test    rbx, rbx
0x180016885  jnz     short loc_18001688B
0x180016887  mov     rbx, [rbp+8]
0x18001688b  cmp     rbx, [r14+120h]
0x180016892  jnz     short loc_18001689D
0x180016894  mov     qword ptr [rdi], 0
0x18001689b  jmp     short loc_1800168E7
0x18001689d  mov     rdx, [rbx+38h]
0x1800168a1  lea     rcx, [rsp+78h+arg_0]
0x1800168a9  call    ??0?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCIoPacket@@@Z; wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::com_ptr_t<CIoPacket,wil::err_exception_policy>(CIoPacket *)
0x1800168ae  test    r15b, r15b
0x1800168b1  jz      short loc_1800168C3
0x1800168b3  mov     r8, rbx
0x1800168b6  lea     rdx, [rsp+78h+var_50]
0x1800168bb  mov     rcx, rbp
0x1800168be  call    ??$erase@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@std@@$0A@@?$_Hash@V?$_Umap_traits@UFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@UFileIoChannelId@@U?$StdHasher@UFileIoChannelId@@@@U?$StdEqual@UFileIoChannelId@@@@@std@@V?$allocator@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@1@V21@@Z; std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>>>,0>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>>>)
0x1800168c3  mov     rax, [rsp+78h+arg_0]
0x1800168cb  lea     rcx, [rsp+78h+arg_0]
0x1800168d3  mov     [rdi], rax
0x1800168d6  mov     [rsp+78h+arg_0], 0
0x1800168e2  call    ??1?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CIoPacket,wil::err_exception_policy>::~com_ptr_t<CIoPacket,wil::err_exception_policy>(void)
0x1800168e7  mov     rcx, rsi; _Mtx_t
0x1800168ea  call    cs:__imp__Mtx_unlock
0x1800168f1  nop     dword ptr [rax+rax+00h]
0x1800168f6  mov     rax, rdi
0x1800168f9  add     rsp, 48h
0x1800168fd  pop     r15
0x1800168ff  pop     r14
0x180016901  pop     rdi
0x180016902  pop     rsi
0x180016903  pop     rbp
0x180016904  pop     rbx
0x180016905  retn
```
