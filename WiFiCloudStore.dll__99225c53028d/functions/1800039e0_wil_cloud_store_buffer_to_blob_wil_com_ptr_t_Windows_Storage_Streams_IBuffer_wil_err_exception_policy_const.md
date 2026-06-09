# wil::cloud_store::buffer_to_blob(wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy> const &)

- ea: `0x1800039e0`
- end: `0x180003c3a`
- name: `?buffer_to_blob@cloud_store@wil@@CA?AVblob@bond@@AEBV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@2@@Z`
- size: `602`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003350`
- `0x180004050`
- `0x180008354`

## callees

- `0x180002de0`
- `0x1800039e0`
- `0x180003c40`
- `0x180003ca0`
- `0x18002a8dc`
- `0x18002e2d0`
- `0x180041010`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall wil::cloud_store::buffer_to_blob(__int64 a1, _QWORD *a2)
{
  int v4; // eax
  int v5; // eax
  __int128 *v6; // rcx
  __int64 v7; // rdi
  void *v8; // rbx
  __int128 *v9; // rax
  int v10; // r15d
  volatile signed __int32 *v11; // rdi
  int v13; // [rsp+20h] [rbp-60h]
  __int128 *v14; // [rsp+28h] [rbp-58h] BYREF
  __int64 v15; // [rsp+30h] [rbp-50h] BYREF
  __int128 v16; // [rsp+40h] [rbp-40h] BYREF
  __int128 v17; // [rsp+50h] [rbp-30h] BYREF
  __int64 v18; // [rsp+60h] [rbp-20h]
  __int128 **v19; // [rsp+68h] [rbp-18h]
  char v20; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  int v22; // [rsp+B8h] [rbp+38h] BYREF
  __int128 *v23; // [rsp+C0h] [rbp+40h] BYREF
  __int128 *v24; // [rsp+C8h] [rbp+48h] BYREF

  v22 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a2 + 56LL))(*a2, &v22);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6C7,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v4,
      v13);
  v15 = 0;
  wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>::query<Windows::Storage::Streams::IBufferByteAccess>(
    (__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))a2,
    &v14);
  v5 = (*(__int64 (__fastcall **)(__int128 *, __int64 *))(*(_QWORD *)v14 + 24LL))(v14, &v15);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6CB,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v5,
      v13);
  v6 = v14;
  v24 = v14;
  if ( v14 )
  {
    (*(void (__fastcall **)(__int128 *))(*(_QWORD *)v14 + 8LL))(v14);
    v6 = v24;
  }
  *(_QWORD *)&v16 = &v24;
  v7 = v15;
  v24 = 0;
  v23 = v6;
  *(_QWORD *)&v17 = &v23;
  v18 = v15;
  v19 = &v23;
  v20 = 1;
  v8 = operator new(0x20u);
  *(_QWORD *)&v17 = v8;
  v9 = v23;
  v23 = 0;
  *(_OWORD *)v8 = 0;
  *((_DWORD *)v8 + 2) = 1;
  *((_DWORD *)v8 + 3) = 1;
  *(_QWORD *)v8 = &std::_Ref_count_resource<char const *,wil::cloud_store::BufferDeleter>::`vftable';
  *((_QWORD *)v8 + 2) = v9;
  *((_QWORD *)v8 + 3) = v7;
  v18 = v7;
  v19 = (__int128 **)v8;
  if ( v23 )
    (*(void (__fastcall **)(__int128 *))(*(_QWORD *)v23 + 16LL))(v23);
  if ( v24 )
    (*(void (__fastcall **)(__int128 *))(*(_QWORD *)v24 + 16LL))(v24);
  v10 = v22;
  v17 = 0;
  _InterlockedIncrement((volatile signed __int32 *)v8 + 2);
  *(_QWORD *)&v17 = v7;
  *((_QWORD *)&v17 + 1) = v8;
  v23 = &v17;
  *(_QWORD *)a1 = v7;
  v16 = 0;
  _InterlockedIncrement((volatile signed __int32 *)v8 + 2);
  v16 = v17;
  boost::detail::shared_count::shared_count((_QWORD *)(a1 + 8), v7, &v16);
  boost::detail::sp_deleter_construct<char,char>(a1, v7);
  v11 = (volatile signed __int32 *)*((_QWORD *)&v17 + 1);
  if ( *((_QWORD *)&v17 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v17 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  *(_QWORD *)(a1 + 16) = *(_QWORD *)a1;
  *(_DWORD *)(a1 + 24) = v10;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(void *))v8)(v8);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 8LL))(v8);
  }
  if ( v14 )
    (*(void (__fastcall **)(__int128 *))(*(_QWORD *)v14 + 16LL))(v14);
  return a1;
}

```

## disassembly

```asm
0x1800039e0  mov     [rsp-28h+arg_0], rbx
0x1800039e5  push    rbp
0x1800039e6  push    rsi
0x1800039e7  push    rdi
0x1800039e8  push    r14
0x1800039ea  push    r15
0x1800039ec  mov     rbp, rsp
0x1800039ef  sub     rsp, 80h
0x1800039f6  mov     rbx, rdx
0x1800039f9  mov     r14, rcx
0x1800039fc  xor     esi, esi
0x1800039fe  mov     [rbp+arg_8], esi
0x180003a01  mov     rcx, [rdx]
0x180003a04  mov     rax, [rcx]
0x180003a07  lea     rdx, [rbp+arg_8]
0x180003a0b  mov     rax, [rax+38h]
0x180003a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a14  mov     rcx, [rbp+28h]; this
0x180003a18  test    eax, eax
0x180003a1a  js      loc_180003C10
0x180003a20  mov     [rbp+var_50], rsi
0x180003a24  lea     rdx, [rbp+var_58]
0x180003a28  mov     rcx, rbx
0x180003a2b  call    ??$query@UIBufferByteAccess@Streams@Storage@Windows@@@?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIBufferByteAccess@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>::query<Windows::Storage::Streams::IBufferByteAccess>(void)
0x180003a30  nop
0x180003a31  mov     rcx, [rbp+var_58]
0x180003a35  mov     rax, [rcx]
0x180003a38  lea     rdx, [rbp+var_50]
0x180003a3c  mov     rax, [rax+18h]
0x180003a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a45  mov     rcx, [rbp+28h]; this
0x180003a49  test    eax, eax
0x180003a4b  js      loc_180003C25
0x180003a51  mov     rcx, [rbp+var_58]
0x180003a55  mov     [rbp+arg_18], rcx
0x180003a59  test    rcx, rcx
0x180003a5c  jz      short loc_180003A6E
0x180003a5e  mov     rax, [rcx]
0x180003a61  mov     rax, [rax+8]
0x180003a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a6a  mov     rcx, [rbp+arg_18]
0x180003a6e  lea     rax, [rbp+arg_18]
0x180003a72  mov     qword ptr [rbp+var_40], rax
0x180003a76  mov     rdi, [rbp+var_50]
0x180003a7a  mov     [rbp+arg_18], rsi
0x180003a7e  mov     [rbp+arg_10], rcx
0x180003a82  lea     rax, [rbp+arg_10]
0x180003a86  mov     qword ptr [rbp+var_30], rax
0x180003a8a  mov     [rbp+var_20], rdi
0x180003a8e  lea     rax, [rbp+arg_10]
0x180003a92  mov     [rbp+var_18], rax
0x180003a96  mov     [rbp+var_10], 1
0x180003a9a  mov     ecx, 20h ; ' '; Size
0x180003a9f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003aa4  mov     rbx, rax
0x180003aa7  mov     qword ptr [rbp+var_30], rax
0x180003aab  mov     rax, [rbp+arg_10]
0x180003aaf  mov     [rbp+arg_10], rsi
0x180003ab3  xorps   xmm0, xmm0
0x180003ab6  movups  xmmword ptr [rbx], xmm0
0x180003ab9  mov     dword ptr [rbx+8], 1
0x180003ac0  mov     dword ptr [rbx+0Ch], 1
0x180003ac7  lea     rcx, ??_7?$_Ref_count_resource@PEBDVBufferDeleter@cloud_store@wil@@@std@@6B@; const std::_Ref_count_resource<char const *,wil::cloud_store::BufferDeleter>::`vftable'
0x180003ace  mov     [rbx], rcx
0x180003ad1  mov     [rbx+10h], rax
0x180003ad5  mov     [rbx+18h], rdi
0x180003ad9  mov     [rbp+var_20], rdi
0x180003add  mov     [rbp+var_18], rbx
0x180003ae1  mov     rcx, [rbp+arg_10]
0x180003ae5  test    rcx, rcx
0x180003ae8  jz      short loc_180003AF7
0x180003aea  mov     rax, [rcx]
0x180003aed  mov     rax, [rax+10h]
0x180003af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003af6  nop
0x180003af7  mov     rcx, [rbp+arg_18]
0x180003afb  test    rcx, rcx
0x180003afe  jz      short loc_180003B0D
0x180003b00  mov     rax, [rcx]
0x180003b03  mov     rax, [rax+10h]
0x180003b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b0c  nop
0x180003b0d  mov     r15d, [rbp+arg_8]
0x180003b11  xorps   xmm0, xmm0
0x180003b14  movdqa  [rbp+var_30], xmm0
0x180003b19  lock inc dword ptr [rbx+8]
0x180003b1d  mov     qword ptr [rbp+var_30], rdi
0x180003b21  mov     qword ptr [rbp+var_30+8], rbx
0x180003b25  lea     rax, [rbp+var_30]
0x180003b29  mov     [rbp+arg_10], rax
0x180003b2d  mov     [r14], rdi
0x180003b30  lea     rcx, [r14+8]
0x180003b34  movdqa  [rbp+var_40], xmm0
0x180003b39  lock inc dword ptr [rbx+8]
0x180003b3d  movaps  xmm0, [rbp+var_30]
0x180003b41  movdqa  [rbp+var_40], xmm0
0x180003b46  lea     r8, [rbp+var_40]
0x180003b4a  mov     rdx, rdi
0x180003b4d  call    ??$?0PEBDU?$deleter@V?$shared_ptr@$$CBD@std@@@blob@bond@@@shared_count@detail@boost@@QEAA@PEBDU?$deleter@V?$shared_ptr@$$CBD@std@@@blob@bond@@@Z; boost::detail::shared_count::shared_count(char const *,bond::blob::deleter<std::shared_ptr<char const>>)
0x180003b52  mov     rdx, rdi
0x180003b55  mov     rcx, r14
0x180003b58  call    ??$sp_deleter_construct@DD@detail@boost@@YAXPEAV?$shared_ptr@D@1@PEAD@Z; boost::detail::sp_deleter_construct<char,char>(boost::shared_ptr<char> *,char *)
0x180003b5d  nop
0x180003b5e  mov     rdi, qword ptr [rbp+var_30+8]
0x180003b62  mov     esi, 0FFFFFFFFh
0x180003b67  test    rdi, rdi
0x180003b6a  jz      short loc_180003BA1
0x180003b6c  mov     eax, esi
0x180003b6e  lock xadd [rdi+8], eax
0x180003b73  cmp     eax, 1
0x180003b76  jnz     short loc_180003BA1
0x180003b78  mov     rax, [rdi]
0x180003b7b  mov     rcx, rdi
0x180003b7e  mov     rax, [rax]
0x180003b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b86  mov     eax, esi
0x180003b88  lock xadd [rdi+0Ch], eax
0x180003b8d  cmp     eax, 1
0x180003b90  jnz     short loc_180003BA1
0x180003b92  mov     rax, [rdi]
0x180003b95  mov     rcx, rdi
0x180003b98  mov     rax, [rax+8]
0x180003b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ba1  mov     rax, [r14]
0x180003ba4  mov     [r14+10h], rax
0x180003ba8  mov     [r14+18h], r15d
0x180003bac  mov     eax, esi
0x180003bae  lock xadd [rbx+8], eax
0x180003bb3  cmp     eax, 1
0x180003bb6  jnz     short loc_180003BE0
0x180003bb8  mov     rax, [rbx]
0x180003bbb  mov     rcx, rbx
0x180003bbe  mov     rax, [rax]
0x180003bc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bc6  lock xadd [rbx+0Ch], esi
0x180003bcb  cmp     esi, 1
0x180003bce  jnz     short loc_180003BE0
0x180003bd0  mov     rax, [rbx]
0x180003bd3  mov     rcx, rbx
0x180003bd6  mov     rax, [rax+8]
0x180003bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bdf  nop
0x180003be0  mov     rcx, [rbp+var_58]
0x180003be4  test    rcx, rcx
0x180003be7  jz      short loc_180003BF6
0x180003be9  mov     rax, [rcx]
0x180003bec  mov     rax, [rax+10h]
0x180003bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bf5  nop
0x180003bf6  mov     rax, r14
0x180003bf9  mov     rbx, [rsp+80h+arg_0]
0x180003c01  add     rsp, 80h
0x180003c08  pop     r15
0x180003c0a  pop     r14
0x180003c0c  pop     rdi
0x180003c0d  pop     rsi
0x180003c0e  pop     rbp
0x180003c0f  retn
0x180003c10  mov     r9d, eax; char *
0x180003c13  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180003c1a  mov     edx, 6C7h; void *
0x180003c1f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180003c25  mov     r9d, eax; char *
0x180003c28  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180003c2f  mov     edx, 6CBh; void *
0x180003c34  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
