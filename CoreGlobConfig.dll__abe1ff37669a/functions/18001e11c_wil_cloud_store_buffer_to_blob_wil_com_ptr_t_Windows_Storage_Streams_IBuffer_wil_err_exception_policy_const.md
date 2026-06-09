# wil::cloud_store::buffer_to_blob(wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy> const &)

- ea: `0x18001e11c`
- end: `0x18001e233`
- name: `?buffer_to_blob@cloud_store@wil@@CA?AVblob@bond@@AEBV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@2@@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ef9c`

## callees

- `0x18000950c`
- `0x18000d9e8`
- `0x18000ecf0`
- `0x18001106c`
- `0x18001b4e4`
- `0x18001cc40`
- `0x18001e11c`
- `0x180025010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall wil::cloud_store::buffer_to_blob(__int64 a1, _QWORD *a2)
{
  int v4; // eax
  int v5; // eax
  __int64 v6; // rcx
  int v8; // [rsp+20h] [rbp-30h]
  __int64 v9; // [rsp+28h] [rbp-28h] BYREF
  __int64 v10[2]; // [rsp+30h] [rbp-20h] BYREF
  std::_Ref_count_base *v11[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  unsigned int v13; // [rsp+78h] [rbp+28h] BYREF
  __int64 v14; // [rsp+80h] [rbp+30h] BYREF
  __int64 v15; // [rsp+88h] [rbp+38h] BYREF

  v13 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)*a2 + 56LL))(*a2, &v13);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6C7,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v4,
      v8);
  v10[0] = 0;
  wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>::query<Windows::Storage::Streams::IBufferByteAccess>(
    (__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))a2,
    &v15);
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 24LL))(v15, v10);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6CB,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v5,
      v8);
  v6 = v15;
  v14 = v15;
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
    v6 = v14;
  }
  v10[1] = (__int64)&v14;
  *(_OWORD *)v11 = 0;
  v14 = 0;
  v9 = v6;
  std::shared_ptr<char const>::_Setpd<char const *,wil::cloud_store::BufferDeleter>(v11, v10[0], &v9);
  wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v14);
  bond::blob::blob(a1, v11, v13);
  if ( v11[1] )
    std::_Ref_count_base::_Decref(v11[1]);
  wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v15);
  return a1;
}

```

## disassembly

```asm
0x18001e11c  push    rbp
0x18001e11e  push    rbx
0x18001e11f  push    rdi
0x18001e120  mov     rbp, rsp
0x18001e123  sub     rsp, 50h
0x18001e127  mov     rdi, rdx
0x18001e12a  mov     rbx, rcx
0x18001e12d  mov     [rbp+arg_8], 0
0x18001e134  mov     rcx, [rdx]
0x18001e137  mov     rax, [rcx]
0x18001e13a  lea     rdx, [rbp+arg_8]
0x18001e13e  mov     rax, [rax+38h]
0x18001e142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e147  mov     rcx, [rbp+18h]; this
0x18001e14b  test    eax, eax
0x18001e14d  jns     short loc_18001E164
0x18001e14f  mov     r9d, eax; char *
0x18001e152  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18001e159  mov     edx, 6C7h; void *
0x18001e15e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e164  mov     [rbp+var_20], 0
0x18001e16c  lea     rdx, [rbp+arg_18]
0x18001e170  mov     rcx, rdi
0x18001e173  call    ??$query@UIBufferByteAccess@Streams@Storage@Windows@@@?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIBufferByteAccess@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>::query<Windows::Storage::Streams::IBufferByteAccess>(void)
0x18001e178  nop
0x18001e179  mov     rcx, [rbp+arg_18]
0x18001e17d  mov     rax, [rcx]
0x18001e180  lea     rdx, [rbp+var_20]
0x18001e184  mov     rax, [rax+18h]
0x18001e188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e18d  mov     rcx, [rbp+18h]; this
0x18001e191  test    eax, eax
0x18001e193  jns     short loc_18001E1AA
0x18001e195  mov     r9d, eax; char *
0x18001e198  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x18001e19f  mov     edx, 6CBh; void *
0x18001e1a4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e1aa  mov     rcx, [rbp+arg_18]
0x18001e1ae  mov     [rbp+arg_10], rcx
0x18001e1b2  test    rcx, rcx
0x18001e1b5  jz      short loc_18001E1C7
0x18001e1b7  mov     rax, [rcx]
0x18001e1ba  mov     rax, [rax+8]
0x18001e1be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1c3  mov     rcx, [rbp+arg_10]
0x18001e1c7  lea     rax, [rbp+arg_10]
0x18001e1cb  mov     [rbp+var_18], rax
0x18001e1cf  xorps   xmm0, xmm0
0x18001e1d2  movdqu  xmmword ptr [rbp+var_10], xmm0
0x18001e1d7  mov     [rbp+arg_10], 0
0x18001e1df  mov     [rbp+var_28], rcx
0x18001e1e3  lea     r8, [rbp+var_28]
0x18001e1e7  mov     rdx, [rbp+var_20]
0x18001e1eb  lea     rcx, [rbp+var_10]
0x18001e1ef  call    ??$_Setpd@PEBDVBufferDeleter@cloud_store@wil@@@?$shared_ptr@$$CBD@std@@AEAAXQEBDVBufferDeleter@cloud_store@wil@@@Z; std::shared_ptr<char const>::_Setpd<char const *,wil::cloud_store::BufferDeleter>(char const * const,wil::cloud_store::BufferDeleter)
0x18001e1f4  nop
0x18001e1f5  lea     rcx, [rbp+arg_10]
0x18001e1f9  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x18001e1fe  nop
0x18001e1ff  mov     r8d, [rbp+arg_8]
0x18001e203  lea     rdx, [rbp+var_10]
0x18001e207  mov     rcx, rbx
0x18001e20a  call    ??$?0$$CBDVshared_ptr@std@@@blob@bond@@QEAA@AEBV?$shared_ptr@$$CBD@std@@I@Z; bond::blob::blob(std::shared_ptr<char const> const &,uint)
0x18001e20f  nop
0x18001e210  mov     rcx, [rbp+var_10+8]; this
0x18001e214  test    rcx, rcx
0x18001e217  jz      short loc_18001E21F
0x18001e219  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001e21e  nop
0x18001e21f  lea     rcx, [rbp+arg_18]
0x18001e223  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x18001e228  mov     rax, rbx
0x18001e22b  add     rsp, 50h
0x18001e22f  pop     rdi
0x18001e230  pop     rbx
0x18001e231  pop     rbp
0x18001e232  retn
```
