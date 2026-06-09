# wil::cloud_store::buffer_to_blob(wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy> const &)

- ea: `0x180022e18`
- end: `0x180022f8a`
- name: `?buffer_to_blob@cloud_store@wil@@CA?AVblob@bond@@AEBV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@2@@Z`
- size: `370`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800181fc`
- `0x1800184c0`
- `0x180018778`
- `0x180018a50`
- `0x180018d24`
- `0x180018f98`
- `0x180019250`

## callees

- `0x180009304`
- `0x1800127ac`
- `0x180016db0`
- `0x1800181ec`
- `0x180019f54`
- `0x18001b128`
- `0x1800229f0`
- `0x180022b80`
- `0x180022e18`
- `0x180031010`

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
  std::shared_ptr<char const>::shared_ptr<char const>(&v11, v15);
  v18 = &v11;
  v8 = v15[0];
  *(std::_Ref_count_base **)a1 = v15[0];
  std::shared_ptr<char const>::shared_ptr<char const>(v14, &v11);
  boost::detail::shared_count::shared_count((_QWORD *)(a1 + 8), (__int64)v8, v14);
  boost::detail::sp_deleter_construct<char,char>(a1, (__int64)v8);
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
0x180022e18  mov     [rsp-18h+arg_0], rbx
0x180022e1d  push    rbp
0x180022e1e  push    rsi
0x180022e1f  push    rdi
0x180022e20  mov     rbp, rsp
0x180022e23  sub     rsp, 60h
0x180022e27  mov     rbx, rdx
0x180022e2a  mov     rdi, rcx
0x180022e2d  mov     [rbp+arg_8], 0
0x180022e34  mov     rcx, [rdx]
0x180022e37  mov     rax, [rcx]
0x180022e3a  lea     rdx, [rbp+arg_8]
0x180022e3e  mov     rax, [rax+38h]
0x180022e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e47  mov     rcx, [rbp+18h]; this
0x180022e4b  test    eax, eax
0x180022e4d  jns     short loc_180022E64
0x180022e4f  mov     r9d, eax; char *
0x180022e52  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180022e59  mov     edx, 6C7h; void *
0x180022e5e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180022e64  mov     [rbp+var_28], 0
0x180022e6c  lea     rdx, [rbp+arg_18]
0x180022e70  mov     rcx, rbx
0x180022e73  call    ??$query@UIBufferByteAccess@Streams@Storage@Windows@@@?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIBufferByteAccess@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>::query<Windows::Storage::Streams::IBufferByteAccess>(void)
0x180022e78  nop
0x180022e79  mov     rcx, [rbp+arg_18]
0x180022e7d  mov     rax, [rcx]
0x180022e80  lea     rdx, [rbp+var_28]
0x180022e84  mov     rax, [rax+18h]
0x180022e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e8d  mov     rcx, [rbp+18h]; this
0x180022e91  test    eax, eax
0x180022e93  jns     short loc_180022EAA
0x180022e95  mov     r9d, eax; char *
0x180022e98  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180022e9f  mov     edx, 6CBh; void *
0x180022ea4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180022eaa  mov     rcx, [rbp+arg_18]
0x180022eae  mov     [rbp+arg_10], rcx
0x180022eb2  test    rcx, rcx
0x180022eb5  jz      short loc_180022EC7
0x180022eb7  mov     rax, [rcx]
0x180022eba  mov     rax, [rax+8]
0x180022ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ec3  mov     rcx, [rbp+arg_10]
0x180022ec7  lea     rax, [rbp+arg_10]
0x180022ecb  mov     [rbp+var_20], rax
0x180022ecf  xorps   xmm0, xmm0
0x180022ed2  movdqu  xmmword ptr [rbp+var_10], xmm0
0x180022ed7  mov     [rbp+arg_10], 0
0x180022edf  mov     [rbp+var_38], rcx
0x180022ee3  lea     r8, [rbp+var_38]
0x180022ee7  mov     rdx, [rbp+var_28]
0x180022eeb  lea     rcx, [rbp+var_10]
0x180022eef  call    ??$_Setpd@PEBDVBufferDeleter@cloud_store@wil@@@?$shared_ptr@$$CBD@std@@AEAAXQEBDVBufferDeleter@cloud_store@wil@@@Z; std::shared_ptr<char const>::_Setpd<char const *,wil::cloud_store::BufferDeleter>(char const * const,wil::cloud_store::BufferDeleter)
0x180022ef4  nop
0x180022ef5  lea     rcx, [rbp+arg_10]
0x180022ef9  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x180022efe  nop
0x180022eff  mov     esi, [rbp+arg_8]
0x180022f02  lea     rdx, [rbp+var_10]
0x180022f06  lea     rcx, [rbp+var_38]
0x180022f0a  call    ??0?$shared_ptr@$$CBD@std@@QEAA@AEBV01@@Z; std::shared_ptr<char const>::shared_ptr<char const>(std::shared_ptr<char const> const &)
0x180022f0f  lea     rcx, [rbp+var_38]
0x180022f13  mov     [rbp+arg_10], rcx
0x180022f17  mov     rbx, [rbp+var_10]
0x180022f1b  mov     [rdi], rbx
0x180022f1e  lea     rdx, [rbp+var_38]
0x180022f22  lea     rcx, [rbp+var_20]
0x180022f26  call    ??0?$shared_ptr@$$CBD@std@@QEAA@AEBV01@@Z; std::shared_ptr<char const>::shared_ptr<char const>(std::shared_ptr<char const> const &)
0x180022f2b  lea     rcx, [rdi+8]
0x180022f2f  lea     r8, [rbp+var_20]
0x180022f33  mov     rdx, rbx
0x180022f36  call    ??$?0PEBDU?$deleter@V?$shared_ptr@$$CBD@std@@@blob@bond@@@shared_count@detail@boost@@QEAA@PEBDU?$deleter@V?$shared_ptr@$$CBD@std@@@blob@bond@@@Z; boost::detail::shared_count::shared_count(char const *,bond::blob::deleter<std::shared_ptr<char const>>)
0x180022f3b  mov     rdx, rbx
0x180022f3e  mov     rcx, rdi
0x180022f41  call    ??$sp_deleter_construct@DD@detail@boost@@YAXPEAV?$shared_ptr@D@1@PEAD@Z; boost::detail::sp_deleter_construct<char,char>(boost::shared_ptr<char> *,char *)
0x180022f46  nop
0x180022f47  mov     rcx, [rbp+var_30]; this
0x180022f4b  test    rcx, rcx
0x180022f4e  jz      short loc_180022F55
0x180022f50  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022f55  mov     rax, [rdi]
0x180022f58  mov     [rdi+10h], rax
0x180022f5c  mov     [rdi+18h], esi
0x180022f5f  mov     rcx, [rbp+var_10+8]; this
0x180022f63  test    rcx, rcx
0x180022f66  jz      short loc_180022F6E
0x180022f68  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022f6d  nop
0x180022f6e  lea     rcx, [rbp+arg_18]
0x180022f72  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x180022f77  mov     rax, rdi
0x180022f7a  mov     rbx, [rsp+60h+arg_0]
0x180022f82  add     rsp, 60h
0x180022f86  pop     rdi
0x180022f87  pop     rsi
0x180022f88  pop     rbp
0x180022f89  retn
```
