# CRdpIdAdapter::StopEncodingProcessor(void)

- ea: `0x18001d938`
- end: `0x18001db60`
- name: `?StopEncodingProcessor@CRdpIdAdapter@@AEAAXXZ`
- size: `552`
- prototype: `void __fastcall(CRdpIdAdapter *__hidden this)`
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b530`
- `0x18001b644`
- `0x18001d810`

## callees

- `0x18000d6d8`
- `0x18000e9f8`
- `0x18000ead8`
- `0x180013854`
- `0x180013ad0`
- `0x180013be8`
- `0x1800152a8`
- `0x180015850`
- `0x180017ac8`
- `0x18001d938`
- `0x180020fd8`
- `0x180021750`
- `0x18003f010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18001d9dd`
- `msvcp_win!_Mtx_unlock` at `0x18001d9dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CRdpIdAdapter::StopEncodingProcessor(CRdpIdAdapter *this)
{
  __int64 v2; // rcx
  _QWORD *v3; // rdi
  _QWORD *i; // rbx
  __int64 v5; // rsi
  __int64 v6; // rcx
  __int64 (__fastcall *v7)(__int64, __int64, __int64, _QWORD); // r12
  unsigned int v8; // r15d
  __int64 v9; // r14
  __int64 v10; // rax
  unsigned int v11; // eax
  __int64 v12; // r14
  __int64 (__fastcall *v13)(__int64, __int64); // rsi
  __int64 v14; // rax
  __int64 v15; // rcx
  unsigned int v16; // eax
  __int64 v17; // rcx
  const char *v18; // [rsp+28h] [rbp-48h]
  _BYTE v19[8]; // [rsp+30h] [rbp-40h] BYREF
  _QWORD *v20; // [rsp+38h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  __int64 v22; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v23; // [rsp+B8h] [rbp+48h] BYREF

  if ( *((_QWORD *)this + 21) )
    CRdpIdAdapter::DeleteAllMonitors(this);
  v23 = 0;
  v22 = 0;
  if ( *((_QWORD *)this + 70) )
  {
    v23 = 0;
    if ( !(unsigned __int8)wil::com_ptr_t<Rdp::Avenc::IEncodingProcessor,wil::err_exception_policy>::try_query_to<Rdp::Avenc::IFileIoControlEvents1>(
                             (char *)this + 560,
                             &v23) )
    {
      v2 = v22;
      v22 = 0;
      if ( v2 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
      wil::com_ptr_t<Rdp::Avenc::IEncodingProcessor,wil::err_exception_policy>::copy_to<Rdp::Avenc::IFileIoControlEvents>(
        (__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))this + 70,
        &v22);
    }
  }
  std::unordered_map<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>>::unordered_map<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>>(v19);
  std::_Mutex_base::lock((CRdpIdAdapter *)((char *)this + 200));
  std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::operator=(
    v19,
    (char *)this + 280);
  _Mtx_unlock((CRdpIdAdapter *)((char *)this + 200));
  v3 = v20;
  for ( i = (_QWORD *)*v20; i != v3; i = (_QWORD *)*i )
  {
    v5 = v23;
    v6 = i[7];
    if ( v23 )
    {
      v7 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v23 + 32LL);
      v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 96LL))(v6);
      v9 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)i[7] + 88LL))(i[7]);
      v10 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)i[7] + 48LL))(i[7]);
      v11 = v7(v5, v10, v9, v8);
    }
    else
    {
      v12 = v22;
      v13 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 32LL);
      v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 48LL))(v6);
      v11 = v13(v12, v14);
    }
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0xCF9,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
      (const char *)v11,
      (int)"Failed to close channel",
      v18);
  }
  std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::clear(v19);
  v15 = *((_QWORD *)this + 70);
  if ( v15 )
  {
    v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 40LL))(v15);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0xD03,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
      (const char *)v16,
      (int)"Failed to stop encoding processor",
      v18);
  }
  v17 = *((_QWORD *)this + 53);
  *((_QWORD *)this + 53) = 0;
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  wil::com_ptr_t<Rdp::Avenc::IFileIoChannelEvents,wil::err_exception_policy>::reset((char *)this + 560);
  *((_OWORD *)this + 34) = xmmword_180046C80;
  std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>(v19);
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v22);
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v23);
}

```

## disassembly

```asm
0x18001d938  mov     [rsp-38h+arg_10], rbx
0x18001d93d  push    rbp
0x18001d93e  push    rsi
0x18001d93f  push    rdi
0x18001d940  push    r12
0x18001d942  push    r13
0x18001d944  push    r14
0x18001d946  push    r15
0x18001d948  mov     rbp, rsp
0x18001d94b  sub     rsp, 70h
0x18001d94f  mov     r13, rcx
0x18001d952  xor     r14d, r14d
0x18001d955  cmp     [rcx+0A8h], r14
0x18001d95c  jbe     short loc_18001D963
0x18001d95e  call    ?DeleteAllMonitors@CRdpIdAdapter@@AEAAXXZ; CRdpIdAdapter::DeleteAllMonitors(void)
0x18001d963  mov     [rbp+arg_8], r14
0x18001d967  mov     [rbp+arg_0], r14
0x18001d96b  lea     rsi, [r13+230h]
0x18001d972  cmp     [rsi], r14
0x18001d975  jz      short loc_18001D9B1
0x18001d977  mov     [rbp+arg_8], r14
0x18001d97b  lea     rdx, [rbp+arg_8]
0x18001d97f  mov     rcx, rsi
0x18001d982  call    ??$try_query_to@UIFileIoControlEvents1@Avenc@Rdp@@@?$com_ptr_t@UIEncodingProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEBA_NPEAPEAUIFileIoControlEvents1@Avenc@Rdp@@@Z; wil::com_ptr_t<Rdp::Avenc::IEncodingProcessor,wil::err_exception_policy>::try_query_to<Rdp::Avenc::IFileIoControlEvents1>(Rdp::Avenc::IFileIoControlEvents1 * *)
0x18001d987  test    al, al
0x18001d989  jnz     short loc_18001D9B1
0x18001d98b  mov     rcx, [rbp+arg_0]
0x18001d98f  mov     [rbp+arg_0], r14
0x18001d993  test    rcx, rcx
0x18001d996  jz      short loc_18001D9A5
0x18001d998  mov     rax, [rcx]
0x18001d99b  mov     rax, [rax+10h]
0x18001d99f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9a4  nop
0x18001d9a5  lea     rdx, [rbp+arg_0]
0x18001d9a9  mov     rcx, rsi
0x18001d9ac  call    ??$copy_to@UIFileIoControlEvents@Avenc@Rdp@@@?$com_ptr_t@UIEncodingProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEBAXPEAPEAUIFileIoControlEvents@Avenc@Rdp@@@Z; wil::com_ptr_t<Rdp::Avenc::IEncodingProcessor,wil::err_exception_policy>::copy_to<Rdp::Avenc::IFileIoControlEvents>(Rdp::Avenc::IFileIoControlEvents * *)
0x18001d9b1  lea     rcx, [rbp+var_40]
0x18001d9b5  call    ??0?$unordered_map@UFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@U?$StdHasher@UFileIoChannelId@@@@U?$StdEqual@UFileIoChannelId@@@@V?$allocator@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@QEAA@XZ; std::unordered_map<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>>::unordered_map<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>>(void)
0x18001d9ba  nop
0x18001d9bb  lea     rbx, [r13+0C8h]
0x18001d9c2  mov     rcx, rbx; this
0x18001d9c5  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001d9ca  lea     rdx, [r13+118h]
0x18001d9d1  lea     rcx, [rbp+var_40]
0x18001d9d5  call    ??4?$_Hash@V?$_Umap_traits@UFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@UFileIoChannelId@@U?$StdHasher@UFileIoChannelId@@@@U?$StdEqual@UFileIoChannelId@@@@@std@@V?$allocator@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::operator=(std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>> &&)
0x18001d9da  mov     rcx, rbx; _Mtx_t
0x18001d9dd  call    cs:__imp__Mtx_unlock
0x18001d9e4  nop     dword ptr [rax+rax+00h]
0x18001d9e9  mov     rdi, [rbp+var_38]
0x18001d9ed  mov     rbx, [rdi]
0x18001d9f0  cmp     rbx, rdi
0x18001d9f3  jz      loc_18001DAA9
0x18001d9f9  mov     rsi, [rbp+arg_8]
0x18001d9fd  mov     rcx, [rbx+38h]
0x18001da01  test    rsi, rsi
0x18001da04  jz      short loc_18001DA55
0x18001da06  mov     rax, [rsi]
0x18001da09  mov     r12, [rax+20h]
0x18001da0d  mov     rax, [rcx]
0x18001da10  mov     rax, [rax+60h]
0x18001da14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da19  mov     r15d, eax
0x18001da1c  mov     rcx, [rbx+38h]
0x18001da20  mov     rdx, [rcx]
0x18001da23  mov     rax, [rdx+58h]
0x18001da27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da2c  mov     r14, rax
0x18001da2f  mov     rcx, [rbx+38h]
0x18001da33  mov     rdx, [rcx]
0x18001da36  mov     rax, [rdx+30h]
0x18001da3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da3f  mov     r9d, r15d
0x18001da42  mov     r8, r14
0x18001da45  mov     rdx, rax
0x18001da48  mov     rcx, rsi
0x18001da4b  mov     rax, r12
0x18001da4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da53  jmp     short loc_18001DA7A
0x18001da55  mov     r14, [rbp+arg_0]
0x18001da59  mov     rax, [r14]
0x18001da5c  mov     rsi, [rax+20h]
0x18001da60  mov     rdx, [rcx]
0x18001da63  mov     rax, [rdx+30h]
0x18001da67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da6c  mov     rdx, rax
0x18001da6f  mov     rcx, r14
0x18001da72  mov     rax, rsi
0x18001da75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da7a  mov     rcx, [rbp+38h]; this
0x18001da7e  lea     rdx, aFailedToCloseC; "Failed to close channel"
0x18001da85  mov     qword ptr [rsp+70h+var_50], rdx; int
0x18001da8a  mov     r9d, eax; char *
0x18001da8d  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001da94  mov     edx, 0CF9h; void *
0x18001da99  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001da9e  mov     rbx, [rbx]
0x18001daa1  xor     r14d, r14d
0x18001daa4  jmp     loc_18001D9F0
0x18001daa9  lea     rcx, [rbp+var_40]
0x18001daad  call    ?clear@?$_Hash@V?$_Umap_traits@UFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@UFileIoChannelId@@U?$StdHasher@UFileIoChannelId@@@@U?$StdEqual@UFileIoChannelId@@@@@std@@V?$allocator@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::clear(void)
0x18001dab2  lea     rsi, [r13+230h]
0x18001dab9  mov     rcx, [rsi]
0x18001dabc  test    rcx, rcx
0x18001dabf  jz      short loc_18001DAF2
0x18001dac1  mov     rax, [rcx]
0x18001dac4  mov     rax, [rax+28h]
0x18001dac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dacd  mov     rcx, [rbp+38h]; this
0x18001dad1  lea     rdx, aFailedToStopEn; "Failed to stop encoding processor"
0x18001dad8  mov     qword ptr [rsp+70h+var_50], rdx; int
0x18001dadd  mov     r9d, eax; char *
0x18001dae0  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001dae7  mov     edx, 0D03h; void *
0x18001daec  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001daf1  nop
0x18001daf2  mov     rcx, [r13+1A8h]
0x18001daf9  mov     [r13+1A8h], r14
0x18001db00  test    rcx, rcx
0x18001db03  jz      short loc_18001DB12
0x18001db05  mov     rax, [rcx]
0x18001db08  mov     rax, [rax+10h]
0x18001db0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db11  nop
0x18001db12  mov     rcx, rsi
0x18001db15  call    ?reset@?$com_ptr_t@UIFileIoChannelEvents@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Rdp::Avenc::IFileIoChannelEvents,wil::err_exception_policy>::reset(void)
0x18001db1a  movups  xmm0, cs:xmmword_180046C80
0x18001db21  movdqu  xmmword ptr [r13+220h], xmm0
0x18001db2a  lea     rcx, [rbp+var_40]
0x18001db2e  call    ??1?$_Hash@V?$_Umap_traits@UFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@UFileIoChannelId@@U?$StdHasher@UFileIoChannelId@@@@U?$StdEqual@UFileIoChannelId@@@@@std@@V?$allocator@U?$pair@$$CBUFileIoChannelId@@V?$com_ptr_t@VCFileIoChannel@@Uerr_exception_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<FileIoChannelId,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>,std::_Uhash_compare<FileIoChannelId,StdHasher<FileIoChannelId>,StdEqual<FileIoChannelId>>,std::allocator<std::pair<FileIoChannelId const,wil::com_ptr_t<CFileIoChannel,wil::err_exception_policy>>>,0>>(void)
0x18001db33  nop
0x18001db34  lea     rcx, [rbp+arg_0]
0x18001db38  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18001db3d  nop
0x18001db3e  lea     rcx, [rbp+arg_8]
0x18001db42  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18001db47  mov     rbx, [rsp+70h+arg_10]
0x18001db4f  add     rsp, 70h
0x18001db53  pop     r15
0x18001db55  pop     r14
0x18001db57  pop     r13
0x18001db59  pop     r12
0x18001db5b  pop     rdi
0x18001db5c  pop     rsi
0x18001db5d  pop     rbp
0x18001db5e  retn
```
