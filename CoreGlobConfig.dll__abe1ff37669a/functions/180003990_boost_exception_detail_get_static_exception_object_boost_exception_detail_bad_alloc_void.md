# boost::exception_detail::get_static_exception_object<boost::exception_detail::bad_alloc_>(void)

- ea: `0x180003990`
- end: `0x180003e73`
- name: `??$get_static_exception_object@Ubad_alloc_@exception_detail@boost@@@exception_detail@boost@@YA?AVexception_ptr@1@XZ`
- size: `1251`
- prototype: `volatile signed __int32 *__fastcall(volatile signed __int32 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001ba0`

## callees

- `0x180002730`
- `0x18000288c`
- `0x180002aac`
- `0x180002b14`
- `0x1800031c6`
- `0x1800031d2`
- `0x1800038b0`
- `0x180003990`
- `0x180005b60`
- `0x180025010`

## string_xrefs

- `0x180003b56`: `D:\os\obj\amd64fre\onecoreuap\vcpkg\bond\objfre\amd64\vcpkg_installed\target-windows\include\boost/exception/detail/exception_ptr.hpp`

## pseudocode

```c
volatile signed __int32 *__fastcall boost::exception_detail::get_static_exception_object<boost::exception_detail::bad_alloc_>(
        volatile signed __int32 *a1)
{
  volatile signed __int32 *v2; // rbx
  __int64 v3; // rax
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  volatile signed __int32 *v7; // rcx
  __int64 *v8; // rax
  volatile signed __int32 *v9; // rdi
  volatile signed __int32 *v10; // rbx
  __int64 v11; // [rsp+28h] [rbp-91h] BYREF
  __int64 v12; // [rsp+30h] [rbp-89h]
  void **v13; // [rsp+40h] [rbp-79h]
  volatile signed __int32 *v14; // [rsp+48h] [rbp-71h]
  __int128 v15; // [rsp+50h] [rbp-69h]
  int v16; // [rsp+60h] [rbp-59h]
  int v17; // [rsp+64h] [rbp-55h]
  void **v18; // [rsp+68h] [rbp-51h]
  __int128 v19; // [rsp+70h] [rbp-49h] BYREF
  _QWORD v20[2]; // [rsp+80h] [rbp-39h]
  void **v21; // [rsp+90h] [rbp-29h]
  void **v22; // [rsp+A0h] [rbp-19h]
  __int64 v23; // [rsp+A8h] [rbp-11h]
  __int128 v24; // [rsp+B0h] [rbp-9h]
  int v25; // [rsp+C0h] [rbp+7h]
  int v26; // [rsp+C4h] [rbp+Bh]
  void **v27; // [rsp+C8h] [rbp+Fh]
  _QWORD v28[8]; // [rsp+D0h] [rbp+17h] BYREF
  volatile signed __int32 *v29; // [rsp+120h] [rbp+67h] BYREF
  __int64 v30; // [rsp+128h] [rbp+6Fh] BYREF

  v29 = a1;
  v23 = 0;
  v24 = 0;
  v25 = -1;
  v26 = -1;
  v28[1] = 0;
  v28[0] = "bad allocation";
  v22 = &boost::exception_detail::bad_alloc_::`vftable'{for `boost::exception'};
  v27 = &boost::exception_detail::bad_alloc_::`vftable'{for `std::bad_alloc'};
  v20[0] = boost::exception_detail::clone_impl<boost::exception_detail::bad_alloc_>::`vbtable';
  v21 = &boost::exception_detail::clone_base::`vftable';
  v14 = 0;
  v15 = 0u;
  v16 = -1;
  v17 = -1;
  v19 = 0;
  o___std_exception_copy_0(v28, &v19);
  v13 = &boost::exception_detail::clone_impl<boost::exception_detail::bad_alloc_>::`vftable'{for `boost::exception'};
  v18 = &boost::exception_detail::clone_impl<boost::exception_detail::bad_alloc_>::`vftable'{for `std::bad_alloc'};
  *(_QWORD *)((char *)v20 + *(int *)(v20[0] + 4LL)) = &boost::exception_detail::clone_impl<boost::exception_detail::bad_alloc_>::`vftable';
  *(_DWORD *)((char *)&v19 + *(int *)(v20[0] + 4LL) + 12) = *(_DWORD *)(v20[0] + 4LL) - 16;
  v2 = 0;
  v29 = 0;
  if ( v23 )
  {
    v2 = *(volatile signed __int32 **)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 40LL))(v23, &v30);
    v29 = v2;
    if ( v2 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 24LL))(v2);
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 32LL))(v30);
  }
  v16 = v25;
  v15 = v24;
  v17 = v26;
  if ( v14 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 32LL))(v14);
  v14 = v2;
  if ( v2 )
  {
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 24LL))(v2);
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 32LL))(v2);
  }
  *(_QWORD *)&v15 = "class boost::exception_ptr __cdecl boost::exception_detail::get_static_exception_object<struct boost"
                    "::exception_detail::bad_alloc_>(void)";
  *((_QWORD *)&v15 + 1) = "D:\\os\\obj\\amd64fre\\onecoreuap\\vcpkg\\bond\\objfre\\amd64\\vcpkg_installed\\target-windows"
                          "\\include\\boost/exception/detail/exception_ptr.hpp";
  v16 = 183;
  if ( __TSS0__1____get_static_exception_object_Ubad_alloc__exception_detail_boost___exception_detail_boost__YA_AVexception_ptr_2_XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 8LL) )
  {
    Init_thread_header(&__TSS0__1____get_static_exception_object_Ubad_alloc__exception_detail_boost___exception_detail_boost__YA_AVexception_ptr_2_XZ_4HA);
    if ( __TSS0__1____get_static_exception_object_Ubad_alloc__exception_detail_boost___exception_detail_boost__YA_AVexception_ptr_2_XZ_4HA == -1 )
    {
      v5 = operator new(0x58u);
      v6 = v5;
      v29 = (volatile signed __int32 *)v5;
      if ( v5 )
      {
        v5[8] = boost::exception_detail::clone_impl<boost::exception_detail::bad_alloc_>::`vbtable';
        v5[10] = &boost::exception_detail::clone_base::`vftable';
        *v5 = &boost::exception::`vftable';
        v7 = v14;
        v5[1] = v14;
        if ( v7 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 24LL))(v7);
        *((_OWORD *)v6 + 1) = v15;
        *((_DWORD *)v6 + 8) = v16;
        *((_DWORD *)v6 + 9) = v17;
        v6[5] = &std::exception::`vftable';
        *((_OWORD *)v6 + 3) = 0;
        o___std_exception_copy_0(&v19, v6 + 6);
        *v6 = &boost::exception_detail::clone_impl<boost::exception_detail::bad_alloc_>::`vftable'{for `boost::exception'};
        v6[5] = &boost::exception_detail::clone_impl<boost::exception_detail::bad_alloc_>::`vftable'{for `std::bad_alloc'};
        *(_QWORD *)((char *)v6 + *(int *)(v6[8] + 4LL) + 64) = &boost::exception_detail::clone_impl<boost::exception_detail::bad_alloc_>::`vftable';
        *(_DWORD *)((char *)v6 + *(int *)(v6[8] + 4LL) + 60) = 0;
      }
      else
      {
        v6 = 0;
      }
      if ( v6 )
        v11 = (__int64)v6 + *(int *)(v6[8] + 4LL) + 64;
      else
        v11 = 0;
      v12 = 0;
      v8 = (__int64 *)boost::detail::shared_count::shared_count(&v29, v6);
      v12 = *v8;
      *v8 = 0;
      v9 = v29;
      if ( v29 )
      {
        if ( _InterlockedExchangeAdd(v29 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
          if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
        }
      }
      boost::detail::sp_enable_shared_from_this(&v11, v6, v6);
      `boost::exception_detail::get_static_exception_object<boost::exception_detail::bad_alloc_>'::`2'::ep = v11;
      qword_180032AF0 = v12;
      if ( v12 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
        v10 = (volatile signed __int32 *)v12;
        if ( v12 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v12 + 8), 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
            if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 16LL))(v10);
          }
        }
      }
      atexit(boost::exception_detail::get_static_exception_object_boost::exception_detail::bad_alloc___::_2_::_dynamic_atexit_destructor_for__ep__);
      Init_thread_footer(&__TSS0__1____get_static_exception_object_Ubad_alloc__exception_detail_boost___exception_detail_boost__YA_AVexception_ptr_2_XZ_4HA);
    }
  }
  *(_QWORD *)a1 = `boost::exception_detail::get_static_exception_object<boost::exception_detail::bad_alloc_>'::`2'::ep;
  v3 = qword_180032AF0;
  *((_QWORD *)a1 + 1) = qword_180032AF0;
  if ( v3 )
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 8));
  v13 = &boost::exception_detail::clone_impl<boost::exception_detail::bad_alloc_>::`vftable'{for `boost::exception'};
  v18 = &boost::exception_detail::clone_impl<boost::exception_detail::bad_alloc_>::`vftable'{for `std::bad_alloc'};
  *(_QWORD *)((char *)v20 + *(int *)(v20[0] + 4LL)) = &boost::exception_detail::clone_impl<boost::exception_detail::bad_alloc_>::`vftable';
  *(_DWORD *)((char *)&v19 + *(int *)(v20[0] + 4LL) + 12) = *(_DWORD *)(v20[0] + 4LL) - 16;
  v13 = &boost::exception_detail::bad_alloc_::`vftable'{for `boost::exception'};
  v18 = &std::exception::`vftable';
  o___std_exception_destroy_0(&v19);
  v13 = &boost::exception::`vftable';
  if ( v14 && (*(unsigned __int8 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 32LL))(v14) )
    v14 = 0;
  v21 = &boost::exception_detail::clone_base::`vftable';
  v22 = &boost::exception_detail::bad_alloc_::`vftable'{for `boost::exception'};
  v27 = &std::exception::`vftable';
  o___std_exception_destroy_0(v28);
  v22 = &boost::exception::`vftable';
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 32LL))(v23);
  return a1;
}

```

## disassembly

```asm
0x180003990  mov     [rsp-8+arg_10], rbx
0x180003995  mov     [rsp-8+arg_0], rcx
0x18000399a  push    rbp
0x18000399b  push    rsi
0x18000399c  push    rdi
0x18000399d  push    r12
0x18000399f  push    r13
0x1800039a1  push    r14
0x1800039a3  push    r15
0x1800039a5  lea     rbp, [rsp-27h]
0x1800039aa  sub     rsp, 0E0h
0x1800039b1  mov     r14, rcx
0x1800039b4  xor     r15d, r15d
0x1800039b7  mov     [rsp+110h+var_F0], r15d
0x1800039bc  mov     ecx, r15d
0x1800039bf  mov     [rbp+57h+var_68], rcx
0x1800039c3  xorps   xmm0, xmm0
0x1800039c6  movdqa  [rbp+57h+var_60], xmm0
0x1800039cb  mov     esi, 0FFFFFFFFh
0x1800039d0  mov     edx, esi
0x1800039d2  mov     [rbp+57h+var_50], edx
0x1800039d5  mov     [rbp+57h+var_4C], esi
0x1800039d8  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x1800039dc  lea     rax, aBadAllocation; "bad allocation"
0x1800039e3  mov     [rbp+57h+var_40], rax
0x1800039e7  lea     r13, ??_7bad_alloc_@exception_detail@boost@@6Bexception@2@@; const boost::exception_detail::bad_alloc_::`vftable'{for `boost::exception'}
0x1800039ee  mov     [rbp+57h+var_70], r13
0x1800039f2  lea     rax, ??_7bad_alloc_@exception_detail@boost@@6Bbad_alloc@std@@@; const boost::exception_detail::bad_alloc_::`vftable'{for `std::bad_alloc'}
0x1800039f9  mov     [rbp+57h+var_48], rax
0x1800039fd  lea     rdi, ??_8?$clone_impl@Ubad_alloc_@exception_detail@boost@@@exception_detail@boost@@7B@; const boost::exception_detail::clone_impl<boost::exception_detail::bad_alloc_>::`vbtable'
0x180003a04  mov     [rbp+57h+var_90], rdi
0x180003a08  lea     rax, ??_7clone_base@exception_detail@boost@@6B@; const boost::exception_detail::clone_base::`vftable'
0x180003a0f  mov     [rbp+57h+var_80], rax
0x180003a13  mov     [rsp+110h+var_F0], 2
0x180003a1b  lea     r12, ??_7exception@boost@@6B@; const boost::exception::`vftable'
0x180003a22  mov     [rbp+57h+var_D0], r12
0x180003a26  mov     [rbp+57h+var_C8], rcx
0x180003a2a  mov     rax, qword ptr [rbp+57h+var_60]
0x180003a2e  mov     qword ptr [rbp+57h+var_C0], rax
0x180003a32  mov     rax, qword ptr [rbp+57h+var_60+8]
0x180003a36  mov     qword ptr [rbp+57h+var_C0+8], rax
0x180003a3a  mov     [rbp+57h+var_B0], edx
0x180003a3d  mov     [rbp+57h+var_AC], esi
0x180003a40  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180003a47  mov     [rbp+57h+var_A8], rax
0x180003a4b  xorps   xmm0, xmm0
0x180003a4e  movups  [rbp+57h+var_A0], xmm0
0x180003a52  lea     rdx, [rbp+57h+var_A0]
0x180003a56  lea     rcx, [rbp+57h+var_40]
0x180003a5a  call    _o___std_exception_copy_0
0x180003a5f  nop
0x180003a60  lea     rax, ??_7?$clone_impl@Ubad_alloc_@exception_detail@boost@@@exception_detail@boost@@6Bexception@2@@; const boost::exception_detail::clone_impl<boost::exception_detail::bad_alloc_>::`vftable'{for `boost::exception'}
0x180003a67  mov     [rbp+57h+var_D0], rax
0x180003a6b  lea     rax, ??_7?$clone_impl@Ubad_alloc_@exception_detail@boost@@@exception_detail@boost@@6Bbad_alloc@std@@@; const boost::exception_detail::clone_impl<boost::exception_detail::bad_alloc_>::`vftable'{for `std::bad_alloc'}
0x180003a72  mov     [rbp+57h+var_A8], rax
0x180003a76  mov     rax, [rbp+57h+var_90]
0x180003a7a  movsxd  rcx, dword ptr [rax+4]
0x180003a7e  lea     rax, ??_7?$clone_impl@Ubad_alloc_@exception_detail@boost@@@exception_detail@boost@@6B@; const boost::exception_detail::clone_impl<boost::exception_detail::bad_alloc_>::`vftable'
0x180003a85  mov     [rbp+rcx+57h+var_90], rax
0x180003a8a  mov     rax, [rbp+57h+var_90]
0x180003a8e  movsxd  rcx, dword ptr [rax+4]
0x180003a92  lea     edx, [rcx-10h]
0x180003a95  mov     dword ptr [rbp+rcx+57h+var_A0+0Ch], edx
0x180003a99  mov     ebx, r15d
0x180003a9c  mov     [rbp+57h+arg_0], rbx
0x180003aa0  mov     rcx, [rbp+57h+var_68]
0x180003aa4  test    rcx, rcx
0x180003aa7  jz      short loc_180003AEC
0x180003aa9  mov     rax, [rcx]
0x180003aac  lea     rdx, [rbp+57h+arg_8]
0x180003ab0  mov     rax, [rax+28h]
0x180003ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ab9  nop
0x180003aba  mov     rbx, [rax]
0x180003abd  mov     [rbp+57h+arg_0], rbx
0x180003ac1  test    rbx, rbx
0x180003ac4  jz      short loc_180003AD6
0x180003ac6  mov     rax, [rbx]
0x180003ac9  mov     rcx, rbx
0x180003acc  mov     rax, [rax+18h]
0x180003ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ad5  nop
0x180003ad6  mov     rcx, [rbp+57h+arg_8]
0x180003ada  test    rcx, rcx
0x180003add  jz      short loc_180003AEC
0x180003adf  mov     rax, [rcx]
0x180003ae2  mov     rax, [rax+20h]
0x180003ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aeb  nop
0x180003aec  mov     rax, qword ptr [rbp+57h+var_60+8]
0x180003af0  mov     qword ptr [rbp+57h+var_C0+8], rax
0x180003af4  mov     eax, [rbp+57h+var_50]
0x180003af7  mov     [rbp+57h+var_B0], eax
0x180003afa  mov     rax, qword ptr [rbp+57h+var_60]
0x180003afe  mov     qword ptr [rbp+57h+var_C0], rax
0x180003b02  mov     eax, [rbp+57h+var_4C]
0x180003b05  mov     [rbp+57h+var_AC], eax
0x180003b08  mov     rcx, [rbp+57h+var_C8]
0x180003b0c  test    rcx, rcx
0x180003b0f  jz      short loc_180003B1D
0x180003b11  mov     rax, [rcx]
0x180003b14  mov     rax, [rax+20h]
0x180003b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b1d  mov     [rbp+57h+var_C8], rbx
0x180003b21  test    rbx, rbx
0x180003b24  jz      short loc_180003B36
0x180003b26  mov     rax, [rbx]
0x180003b29  mov     rcx, rbx
0x180003b2c  mov     rax, [rax+18h]
0x180003b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b35  nop
0x180003b36  test    rbx, rbx
0x180003b39  jz      short loc_180003B4B
0x180003b3b  mov     rax, [rbx]
0x180003b3e  mov     rcx, rbx
0x180003b41  mov     rax, [rax+20h]
0x180003b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b4a  nop
0x180003b4b  lea     rax, aClassBoostExce_0; "class boost::exception_ptr __cdecl boos"...
0x180003b52  mov     qword ptr [rbp+57h+var_C0], rax
0x180003b56  lea     rax, aDOsObjAmd64fre; "D:\\os\\obj\\amd64fre\\onecoreuap\\vcpk"...
0x180003b5d  mov     qword ptr [rbp+57h+var_C0+8], rax
0x180003b61  mov     [rbp+57h+var_B0], 0B7h
0x180003b68  mov     ecx, cs:_tls_index
0x180003b6e  mov     rax, gs:58h
0x180003b77  mov     edx, 8
0x180003b7c  mov     rax, [rax+rcx*8]
0x180003b80  mov     eax, [rdx+rax]
0x180003b83  cmp     cs:?$TSS0@?1???$get_static_exception_object@Ubad_alloc_@exception_detail@boost@@@exception_detail@boost@@YA?AVexception_ptr@2@XZ@4HA, eax
0x180003b89  jg      loc_180003C91
0x180003b8f  mov     rax, cs:?ep@?1???$get_static_exception_object@Ubad_alloc_@exception_detail@boost@@@exception_detail@boost@@YA?AVexception_ptr@2@XZ@4V32@A; boost::exception_ptr `boost::exception_detail::get_static_exception_object<boost::exception_detail::bad_alloc_>(void)'::`2'::ep
0x180003b96  mov     [r14], rax
0x180003b99  mov     rax, cs:qword_180032AF0
0x180003ba0  mov     [r14+8], rax
0x180003ba4  test    rax, rax
0x180003ba7  jz      short loc_180003BAD
0x180003ba9  lock inc dword ptr [rax+8]
0x180003bad  lea     rax, ??_7?$clone_impl@Ubad_alloc_@exception_detail@boost@@@exception_detail@boost@@6Bexception@2@@; const boost::exception_detail::clone_impl<boost::exception_detail::bad_alloc_>::`vftable'{for `boost::exception'}
0x180003bb4  mov     [rbp+57h+var_D0], rax
0x180003bb8  lea     rax, ??_7?$clone_impl@Ubad_alloc_@exception_detail@boost@@@exception_detail@boost@@6Bbad_alloc@std@@@; const boost::exception_detail::clone_impl<boost::exception_detail::bad_alloc_>::`vftable'{for `std::bad_alloc'}
0x180003bbf  mov     [rbp+57h+var_A8], rax
0x180003bc3  mov     rax, [rbp+57h+var_90]
0x180003bc7  movsxd  rcx, dword ptr [rax+4]
0x180003bcb  lea     rax, ??_7?$clone_impl@Ubad_alloc_@exception_detail@boost@@@exception_detail@boost@@6B@; const boost::exception_detail::clone_impl<boost::exception_detail::bad_alloc_>::`vftable'
0x180003bd2  mov     [rbp+rcx+57h+var_90], rax
0x180003bd7  mov     rax, [rbp+57h+var_90]
0x180003bdb  movsxd  rcx, dword ptr [rax+4]
0x180003bdf  lea     edx, [rcx-10h]
0x180003be2  mov     dword ptr [rbp+rcx+57h+var_A0+0Ch], edx
0x180003be6  mov     [rbp+57h+var_D0], r13
0x180003bea  lea     rbx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180003bf1  mov     [rbp+57h+var_A8], rbx
0x180003bf5  lea     rcx, [rbp+57h+var_A0]
0x180003bf9  call    _o___std_exception_destroy_0
0x180003bfe  mov     [rbp+57h+var_D0], r12
0x180003c02  mov     rcx, [rbp+57h+var_C8]
0x180003c06  test    rcx, rcx
0x180003c09  jz      short loc_180003C1F
0x180003c0b  mov     rax, [rcx]
0x180003c0e  mov     rax, [rax+20h]
0x180003c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c17  test    al, al
0x180003c19  jz      short loc_180003C1F
0x180003c1b  mov     [rbp+57h+var_C8], r15
0x180003c1f  lea     rax, ??_7clone_base@exception_detail@boost@@6B@; const boost::exception_detail::clone_base::`vftable'
0x180003c26  mov     [rbp+57h+var_80], rax
0x180003c2a  mov     [rbp+57h+var_70], r13
0x180003c2e  mov     [rbp+57h+var_48], rbx
0x180003c32  lea     rcx, [rbp+57h+var_40]
0x180003c36  call    _o___std_exception_destroy_0
0x180003c3b  mov     [rbp+57h+var_70], r12
0x180003c3f  mov     rcx, [rbp+57h+var_68]
0x180003c43  test    rcx, rcx
0x180003c46  jz      short loc_180003C55
0x180003c48  mov     rax, [rcx]
0x180003c4b  mov     rax, [rax+20h]
0x180003c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c54  nop
0x180003c55  mov     rax, r14
0x180003c58  mov     rbx, [rsp+110h+arg_10]
0x180003c60  add     rsp, 0E0h
0x180003c67  pop     r15
0x180003c69  pop     r14
0x180003c6b  pop     r13
0x180003c6d  pop     r12
0x180003c6f  pop     rdi
0x180003c70  pop     rsi
0x180003c71  pop     rbp
0x180003c72  retn
0x180003c73  lea     rcx, _boost__exception_detail__get_static_exception_object_boost__exception_detail__bad_alloc______2____dynamic_atexit_destructor_for__ep__; void (__cdecl *)()
0x180003c7a  call    atexit
0x180003c7f  nop
0x180003c80  lea     rcx, ?$TSS0@?1???$get_static_exception_object@Ubad_alloc_@exception_detail@boost@@@exception_detail@boost@@YA?AVexception_ptr@2@XZ@4HA
0x180003c87  call    _Init_thread_footer
0x180003c8c  jmp     loc_180003B8F
0x180003c91  lea     rcx, ?$TSS0@?1???$get_static_exception_object@Ubad_alloc_@exception_detail@boost@@@exception_detail@boost@@YA?AVexception_ptr@2@XZ@4HA
0x180003c98  call    _Init_thread_header
0x180003c9d  cmp     cs:?$TSS0@?1???$get_static_exception_object@Ubad_alloc_@exception_detail@boost@@@exception_detail@boost@@YA?AVexception_ptr@2@XZ@4HA, 0FFFFFFFFh
0x180003ca4  jnz     loc_180003B8F
0x180003caa  mov     ecx, 58h ; 'X'; Size
0x180003caf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003cb4  mov     rbx, rax
0x180003cb7  mov     [rbp+57h+arg_0], rax
0x180003cbb  test    rax, rax
0x180003cbe  jz      loc_180003D69
0x180003cc4  mov     [rax+40h], rdi
0x180003cc8  lea     rax, ??_7clone_base@exception_detail@boost@@6B@; const boost::exception_detail::clone_base::`vftable'
0x180003ccf  mov     [rbx+50h], rax
0x180003cd3  mov     [rsp+110h+var_F0], 6
0x180003cdb  mov     [rbx], r12
0x180003cde  mov     rcx, [rbp+57h+var_C8]
0x180003ce2  mov     [rbx+8], rcx
0x180003ce6  test    rcx, rcx
0x180003ce9  jz      short loc_180003CF7
0x180003ceb  mov     rax, [rcx]
0x180003cee  mov     rax, [rax+18h]
0x180003cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cf7  mov     rax, qword ptr [rbp+57h+var_C0]
0x180003cfb  mov     [rbx+10h], rax
0x180003cff  mov     rax, qword ptr [rbp+57h+var_C0+8]
0x180003d03  mov     [rbx+18h], rax
0x180003d07  mov     eax, [rbp+57h+var_B0]
0x180003d0a  mov     [rbx+20h], eax
0x180003d0d  mov     eax, [rbp+57h+var_AC]
0x180003d10  mov     [rbx+24h], eax
0x180003d13  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180003d1a  mov     [rbx+28h], rax
0x180003d1e  lea     rdx, [rbx+30h]
0x180003d22  xorps   xmm0, xmm0
0x180003d25  movups  xmmword ptr [rdx], xmm0
0x180003d28  lea     rcx, [rbp+57h+var_A0]
0x180003d2c  call    _o___std_exception_copy_0
0x180003d31  lea     rax, ??_7?$clone_impl@Ubad_alloc_@exception_detail@boost@@@exception_detail@boost@@6Bexception@2@@; const boost::exception_detail::clone_impl<boost::exception_detail::bad_alloc_>::`vftable'{for `boost::exception'}
0x180003d38  mov     [rbx], rax
0x180003d3b  lea     rax, ??_7?$clone_impl@Ubad_alloc_@exception_detail@boost@@@exception_detail@boost@@6Bbad_alloc@std@@@; const boost::exception_detail::clone_impl<boost::exception_detail::bad_alloc_>::`vftable'{for `std::bad_alloc'}
0x180003d42  mov     [rbx+28h], rax
0x180003d46  mov     rax, [rbx+40h]
0x180003d4a  movsxd  rcx, dword ptr [rax+4]
0x180003d4e  lea     rax, ??_7?$clone_impl@Ubad_alloc_@exception_detail@boost@@@exception_detail@boost@@6B@; const boost::exception_detail::clone_impl<boost::exception_detail::bad_alloc_>::`vftable'
0x180003d55  mov     [rcx+rbx+40h], rax
0x180003d5a  mov     rax, [rbx+40h]
0x180003d5e  movsxd  rcx, dword ptr [rax+4]
0x180003d62  mov     [rcx+rbx+3Ch], r15d
0x180003d67  jmp     short loc_180003D6C
0x180003d69  mov     rbx, r15
0x180003d6c  test    rbx, rbx
0x180003d6f  jnz     short loc_180003D78
0x180003d71  mov     [rsp+110h+var_E8], r15
0x180003d76  jmp     short loc_180003D8C
0x180003d78  mov     rax, [rbx+40h]
0x180003d7c  movsxd  rax, dword ptr [rax+4]
0x180003d80  add     rax, 40h ; '@'
0x180003d84  add     rax, rbx
0x180003d87  mov     [rsp+110h+var_E8], rax
0x180003d8c  mov     [rsp+110h+var_E0], r15
0x180003d91  mov     rdx, rbx
0x180003d94  lea     rcx, [rbp+57h+arg_0]
0x180003d98  call    ??$?0V?$clone_impl@Ubad_alloc_@exception_detail@boost@@@exception_detail@boost@@@shared_count@detail@boost@@QEAA@PEAV?$clone_impl@Ubad_alloc_@exception_detail@boost@@@exception_detail@2@@Z; boost::detail::shared_count::shared_count(boost::exception_detail::clone_impl<boost::exception_detail::bad_alloc_> *)
0x180003d9d  mov     rdx, [rsp+110h+var_E0]
0x180003da2  mov     rcx, [rax]
0x180003da5  mov     [rsp+110h+var_E0], rcx
0x180003daa  mov     [rax], rdx
0x180003dad  mov     rdi, [rbp+57h+arg_0]
0x180003db1  test    rdi, rdi
0x180003db4  jz      short loc_180003DEC
0x180003db6  mov     eax, esi
0x180003db8  lock xadd [rdi+8], eax
0x180003dbd  cmp     eax, 1
0x180003dc0  jnz     short loc_180003DEC
0x180003dc2  mov     rax, [rdi]
0x180003dc5  mov     rcx, rdi
0x180003dc8  mov     rax, [rax+8]
0x180003dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dd1  mov     eax, esi
0x180003dd3  lock xadd [rdi+0Ch], eax
0x180003dd8  cmp     eax, 1
0x180003ddb  jnz     short loc_180003DEC
0x180003ddd  mov     rax, [rdi]
0x180003de0  mov     rcx, rdi
0x180003de3  mov     rax, [rax+10h]
0x180003de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dec  mov     r8, rbx
0x180003def  mov     rdx, rbx
0x180003df2  lea     rcx, [rsp+110h+var_E8]
0x180003df7  call    ?sp_enable_shared_from_this@detail@boost@@YAXZZ; boost::detail::sp_enable_shared_from_this(...)
0x180003dfc  nop
0x180003dfd  mov     rax, [rsp+110h+var_E8]
0x180003e02  mov     cs:?ep@?1???$get_static_exception_object@Ubad_alloc_@exception_detail@boost@@@exception_detail@boost@@YA?AVexception_ptr@2@XZ@4V32@A, rax; boost::exception_ptr `boost::exception_detail::get_static_exception_object<boost::exception_detail::bad_alloc_>(void)'::`2'::ep
0x180003e09  mov     rbx, [rsp+110h+var_E0]
0x180003e0e  mov     cs:qword_180032AF0, rbx
0x180003e15  test    rbx, rbx
0x180003e18  jz      loc_180003C73
0x180003e1e  lock inc dword ptr [rbx+8]
0x180003e22  mov     rbx, [rsp+110h+var_E0]
0x180003e27  test    rbx, rbx
0x180003e2a  jz      loc_180003C73
0x180003e30  mov     eax, esi
0x180003e32  lock xadd [rbx+8], eax
0x180003e37  cmp     eax, 1
0x180003e3a  jnz     loc_180003C73
  ... truncated ...
```
