# wil::cloud_store::buffer_to_blob(wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy> const &)

- ea: `0x1800167ec`
- end: `0x18001695e`
- name: `?buffer_to_blob@cloud_store@wil@@CA?AVblob@bond@@AEBV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@2@@Z`
- size: `370`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012110`
- `0x180019124`
- `0x18001f4c8`

## callees

- `0x180008ebc`
- `0x18000cf94`
- `0x18000f044`
- `0x18001133c`
- `0x180011f50`
- `0x1800120c8`
- `0x180012904`
- `0x180016584`
- `0x1800167ec`
- `0x180035010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall wil::cloud_store::buffer_to_blob(__int64 a1, _QWORD *a2)
{
  int v4; // eax
  int v5; // eax
  __int64 v6; // rcx
  int v7; // esi
  std::_Ref_count_base *v8; // rbx
  int v10; // [rsp+20h] [rbp-40h]
  __int64 v11; // [rsp+28h] [rbp-38h] BYREF
  std::_Ref_count_base *v12; // [rsp+30h] [rbp-30h]
  __int64 v13; // [rsp+38h] [rbp-28h] BYREF
  _QWORD v14[2]; // [rsp+40h] [rbp-20h] BYREF
  std::_Ref_count_base *v15[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  int v17; // [rsp+88h] [rbp+28h] BYREF
  __int64 *v18; // [rsp+90h] [rbp+30h] BYREF
  __int64 *v19; // [rsp+98h] [rbp+38h] BYREF

  v17 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a2 + 56LL))(*a2, &v17);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6C7,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v4,
      v10);
  v13 = 0;
  wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>::query<Windows::Storage::Streams::IBufferByteAccess>(
    (__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))a2,
    &v19);
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*v19 + 24))(v19, &v13);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6CB,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v5,
      v10);
  v6 = (__int64)v19;
  v18 = v19;
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64 *))(*v19 + 8))(v19);
    v6 = (__int64)v18;
  }
  v14[0] = &v18;
  *(_OWORD *)v15 = 0;
  v18 = 0;
  v11 = v6;
  std::shared_ptr<char const>::_Setpd<char const *,wil::cloud_store::BufferDeleter>(v15, v13, &v11);
  wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>((__int64 *)&v18);
  v7 = v17;
  std::shared_ptr<FocusSingletonConnectorBase>::shared_ptr<FocusSingletonConnectorBase>(&v11, v15);
  v18 = &v11;
  v8 = v15[0];
  *(std::_Ref_count_base **)a1 = v15[0];
  std::shared_ptr<FocusSingletonConnectorBase>::shared_ptr<FocusSingletonConnectorBase>(v14, &v11);
  boost::detail::shared_count::shared_count(a1 + 8, v8, v14);
  boost::detail::sp_deleter_construct<char,char>(a1, v8);
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
  *(_QWORD *)(a1 + 16) = *(_QWORD *)a1;
  *(_DWORD *)(a1 + 24) = v7;
  if ( v15[1] )
    std::_Ref_count_base::_Decref(v15[1]);
  wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>((__int64 *)&v19);
  return a1;
}

```

## disassembly

```asm
0x1800167ec  mov     [rsp-18h+arg_0], rbx
0x1800167f1  push    rbp
0x1800167f2  push    rsi
0x1800167f3  push    rdi
0x1800167f4  mov     rbp, rsp
0x1800167f7  sub     rsp, 60h
0x1800167fb  mov     rbx, rdx
0x1800167fe  mov     rdi, rcx
0x180016801  mov     [rbp+arg_8], 0
0x180016808  mov     rcx, [rdx]
0x18001680b  mov     rax, [rcx]
0x18001680e  lea     rdx, [rbp+arg_8]
0x180016812  mov     rax, [rax+38h]
0x180016816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001681b  mov     rcx, [rbp+18h]; this
0x18001681f  test    eax, eax
0x180016821  jns     short loc_180016838
0x180016823  mov     r9d, eax; char *
0x180016826  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18001682d  mov     edx, 6C7h; void *
0x180016832  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180016838  mov     [rbp+var_28], 0
0x180016840  lea     rdx, [rbp+arg_18]
0x180016844  mov     rcx, rbx
0x180016847  call    ??$query@UIBufferByteAccess@Streams@Storage@Windows@@@?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIBufferByteAccess@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>::query<Windows::Storage::Streams::IBufferByteAccess>(void)
0x18001684c  nop
0x18001684d  mov     rcx, [rbp+arg_18]
0x180016851  mov     rax, [rcx]
0x180016854  lea     rdx, [rbp+var_28]
0x180016858  mov     rax, [rax+18h]
0x18001685c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016861  mov     rcx, [rbp+18h]; this
0x180016865  test    eax, eax
0x180016867  jns     short loc_18001687E
0x180016869  mov     r9d, eax; char *
0x18001686c  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180016873  mov     edx, 6CBh; void *
0x180016878  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001687e  mov     rcx, [rbp+arg_18]
0x180016882  mov     [rbp+arg_10], rcx
0x180016886  test    rcx, rcx
0x180016889  jz      short loc_18001689B
0x18001688b  mov     rax, [rcx]
0x18001688e  mov     rax, [rax+8]
0x180016892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016897  mov     rcx, [rbp+arg_10]
0x18001689b  lea     rax, [rbp+arg_10]
0x18001689f  mov     [rbp+var_20], rax
0x1800168a3  xorps   xmm0, xmm0
0x1800168a6  movdqu  xmmword ptr [rbp+var_10], xmm0
0x1800168ab  mov     [rbp+arg_10], 0
0x1800168b3  mov     [rbp+var_38], rcx
0x1800168b7  lea     r8, [rbp+var_38]
0x1800168bb  mov     rdx, [rbp+var_28]
0x1800168bf  lea     rcx, [rbp+var_10]
0x1800168c3  call    ??$_Setpd@PEBDVBufferDeleter@cloud_store@wil@@@?$shared_ptr@$$CBD@std@@AEAAXQEBDVBufferDeleter@cloud_store@wil@@@Z; std::shared_ptr<char const>::_Setpd<char const *,wil::cloud_store::BufferDeleter>(char const * const,wil::cloud_store::BufferDeleter)
0x1800168c8  nop
0x1800168c9  lea     rcx, [rbp+arg_10]
0x1800168cd  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x1800168d2  nop
0x1800168d3  mov     esi, [rbp+arg_8]
0x1800168d6  lea     rdx, [rbp+var_10]
0x1800168da  lea     rcx, [rbp+var_38]
0x1800168de  call    ??0?$shared_ptr@VFocusSingletonConnectorBase@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<FocusSingletonConnectorBase>::shared_ptr<FocusSingletonConnectorBase>(std::shared_ptr<FocusSingletonConnectorBase> const &)
0x1800168e3  lea     rcx, [rbp+var_38]
0x1800168e7  mov     [rbp+arg_10], rcx
0x1800168eb  mov     rbx, [rbp+var_10]
0x1800168ef  mov     [rdi], rbx
0x1800168f2  lea     rdx, [rbp+var_38]
0x1800168f6  lea     rcx, [rbp+var_20]
0x1800168fa  call    ??0?$shared_ptr@VFocusSingletonConnectorBase@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<FocusSingletonConnectorBase>::shared_ptr<FocusSingletonConnectorBase>(std::shared_ptr<FocusSingletonConnectorBase> const &)
0x1800168ff  lea     rcx, [rdi+8]
0x180016903  lea     r8, [rbp+var_20]
0x180016907  mov     rdx, rbx
0x18001690a  call    ??$?0PEBDU?$deleter@V?$shared_ptr@$$CBD@std@@@blob@bond@@@shared_count@detail@boost@@QEAA@PEBDU?$deleter@V?$shared_ptr@$$CBD@std@@@blob@bond@@@Z; boost::detail::shared_count::shared_count(char const *,bond::blob::deleter<std::shared_ptr<char const>>)
0x18001690f  mov     rdx, rbx
0x180016912  mov     rcx, rdi
0x180016915  call    ??$sp_deleter_construct@DD@detail@boost@@YAXPEAV?$shared_ptr@D@1@PEAD@Z; boost::detail::sp_deleter_construct<char,char>(boost::shared_ptr<char> *,char *)
0x18001691a  nop
0x18001691b  mov     rcx, [rbp+var_30]; this
0x18001691f  test    rcx, rcx
0x180016922  jz      short loc_180016929
0x180016924  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016929  mov     rax, [rdi]
0x18001692c  mov     [rdi+10h], rax
0x180016930  mov     [rdi+18h], esi
0x180016933  mov     rcx, [rbp+var_10+8]; this
0x180016937  test    rcx, rcx
0x18001693a  jz      short loc_180016942
0x18001693c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016941  nop
0x180016942  lea     rcx, [rbp+arg_18]
0x180016946  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x18001694b  mov     rax, rdi
0x18001694e  mov     rbx, [rsp+60h+arg_0]
0x180016956  add     rsp, 60h
0x18001695a  pop     rdi
0x18001695b  pop     rsi
0x18001695c  pop     rbp
0x18001695d  retn
```
