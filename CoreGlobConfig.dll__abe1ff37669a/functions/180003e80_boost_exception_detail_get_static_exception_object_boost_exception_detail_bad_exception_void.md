# boost::exception_detail::get_static_exception_object<boost::exception_detail::bad_exception_>(void)

- ea: `0x180003e80`
- end: `0x180004363`
- name: `??$get_static_exception_object@Ubad_exception_@exception_detail@boost@@@exception_detail@boost@@YA?AVexception_ptr@1@XZ`
- size: `1251`
- prototype: `volatile signed __int32 *__fastcall(volatile signed __int32 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001bd0`

## callees

- `0x180002730`
- `0x18000288c`
- `0x180002aac`
- `0x180002b14`
- `0x1800031c6`
- `0x1800031d2`
- `0x180003910`
- `0x180003e80`
- `0x180005b60`
- `0x180025010`

## string_xrefs

- `0x180004046`: `D:\os\obj\amd64fre\onecoreuap\vcpkg\bond\objfre\amd64\vcpkg_installed\target-windows\include\boost/exception/detail/exception_ptr.hpp`

## pseudocode

```c
volatile signed __int32 *__fastcall boost::exception_detail::get_static_exception_object<boost::exception_detail::bad_exception_>(
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
  v28[0] = "bad exception";
  v22 = &boost::exception_detail::bad_exception_::`vftable'{for `boost::exception'};
  v27 = &boost::exception_detail::bad_exception_::`vftable'{for `std::bad_exception'};
  v20[0] = &boost::exception_detail::clone_impl<boost::exception_detail::bad_exception_>::`vbtable';
  v21 = &boost::exception_detail::clone_base::`vftable';
  v14 = 0;
  v15 = 0u;
  v16 = -1;
  v17 = -1;
  v19 = 0;
  o___std_exception_copy_0(v28, &v19);
  v13 = &boost::exception_detail::clone_impl<boost::exception_detail::bad_exception_>::`vftable'{for `boost::exception'};
  v18 = &boost::exception_detail::clone_impl<boost::exception_detail::bad_exception_>::`vftable'{for `std::bad_exception'};
  *(_QWORD *)((char *)v20 + *(int *)(v20[0] + 4LL)) = &boost::exception_detail::clone_impl<boost::exception_detail::bad_exception_>::`vftable';
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
                    "::exception_detail::bad_exception_>(void)";
  *((_QWORD *)&v15 + 1) = "D:\\os\\obj\\amd64fre\\onecoreuap\\vcpkg\\bond\\objfre\\amd64\\vcpkg_installed\\target-windows"
                          "\\include\\boost/exception/detail/exception_ptr.hpp";
  v16 = 183;
  if ( __TSS0__1____get_static_exception_object_Ubad_exception__exception_detail_boost___exception_detail_boost__YA_AVexception_ptr_2_XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 8LL) )
  {
    Init_thread_header(&__TSS0__1____get_static_exception_object_Ubad_exception__exception_detail_boost___exception_detail_boost__YA_AVexception_ptr_2_XZ_4HA);
    if ( __TSS0__1____get_static_exception_object_Ubad_exception__exception_detail_boost___exception_detail_boost__YA_AVexception_ptr_2_XZ_4HA == -1 )
    {
      v5 = operator new(0x58u);
      v6 = v5;
      v29 = (volatile signed __int32 *)v5;
      if ( v5 )
      {
        v5[8] = &boost::exception_detail::clone_impl<boost::exception_detail::bad_exception_>::`vbtable';
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
        *v6 = &boost::exception_detail::clone_impl<boost::exception_detail::bad_exception_>::`vftable'{for `boost::exception'};
        v6[5] = &boost::exception_detail::clone_impl<boost::exception_detail::bad_exception_>::`vftable'{for `std::bad_exception'};
        *(_QWORD *)((char *)v6 + *(int *)(v6[8] + 4LL) + 64) = &boost::exception_detail::clone_impl<boost::exception_detail::bad_exception_>::`vftable';
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
      `boost::exception_detail::get_static_exception_object<boost::exception_detail::bad_exception_>'::`2'::ep = v11;
      qword_180032B00 = v12;
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
      atexit(boost::exception_detail::get_static_exception_object_boost::exception_detail::bad_exception___::_2_::_dynamic_atexit_destructor_for__ep__);
      Init_thread_footer(&__TSS0__1____get_static_exception_object_Ubad_exception__exception_detail_boost___exception_detail_boost__YA_AVexception_ptr_2_XZ_4HA);
    }
  }
  *(_QWORD *)a1 = `boost::exception_detail::get_static_exception_object<boost::exception_detail::bad_exception_>'::`2'::ep;
  v3 = qword_180032B00;
  *((_QWORD *)a1 + 1) = qword_180032B00;
  if ( v3 )
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 8));
  v13 = &boost::exception_detail::clone_impl<boost::exception_detail::bad_exception_>::`vftable'{for `boost::exception'};
  v18 = &boost::exception_detail::clone_impl<boost::exception_detail::bad_exception_>::`vftable'{for `std::bad_exception'};
  *(_QWORD *)((char *)v20 + *(int *)(v20[0] + 4LL)) = &boost::exception_detail::clone_impl<boost::exception_detail::bad_exception_>::`vftable';
  *(_DWORD *)((char *)&v19 + *(int *)(v20[0] + 4LL) + 12) = *(_DWORD *)(v20[0] + 4LL) - 16;
  v13 = &boost::exception_detail::bad_exception_::`vftable'{for `boost::exception'};
  v18 = &std::exception::`vftable';
  o___std_exception_destroy_0(&v19);
  v13 = &boost::exception::`vftable';
  if ( v14 && (*(unsigned __int8 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 32LL))(v14) )
    v14 = 0;
  v21 = &boost::exception_detail::clone_base::`vftable';
  v22 = &boost::exception_detail::bad_exception_::`vftable'{for `boost::exception'};
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
0x180003e80  mov     [rsp-8+arg_10], rbx
0x180003e85  mov     [rsp-8+arg_0], rcx
0x180003e8a  push    rbp
0x180003e8b  push    rsi
0x180003e8c  push    rdi
0x180003e8d  push    r12
0x180003e8f  push    r13
0x180003e91  push    r14
0x180003e93  push    r15
0x180003e95  lea     rbp, [rsp-27h]
0x180003e9a  sub     rsp, 0E0h
0x180003ea1  mov     r14, rcx
0x180003ea4  xor     r15d, r15d
0x180003ea7  mov     [rsp+110h+var_F0], r15d
0x180003eac  mov     ecx, r15d
0x180003eaf  mov     [rbp+57h+var_68], rcx
0x180003eb3  xorps   xmm0, xmm0
0x180003eb6  movdqa  [rbp+57h+var_60], xmm0
0x180003ebb  mov     esi, 0FFFFFFFFh
0x180003ec0  mov     edx, esi
0x180003ec2  mov     [rbp+57h+var_50], edx
0x180003ec5  mov     [rbp+57h+var_4C], esi
0x180003ec8  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x180003ecc  lea     rax, aBadException; "bad exception"
0x180003ed3  mov     [rbp+57h+var_40], rax
0x180003ed7  lea     r13, ??_7bad_exception_@exception_detail@boost@@6Bexception@2@@; const boost::exception_detail::bad_exception_::`vftable'{for `boost::exception'}
0x180003ede  mov     [rbp+57h+var_70], r13
0x180003ee2  lea     rax, ??_7bad_exception_@exception_detail@boost@@6Bbad_exception@std@@@; const boost::exception_detail::bad_exception_::`vftable'{for `std::bad_exception'}
0x180003ee9  mov     [rbp+57h+var_48], rax
0x180003eed  lea     rdi, ??_8?$clone_impl@Ubad_exception_@exception_detail@boost@@@exception_detail@boost@@7B@; const boost::exception_detail::clone_impl<boost::exception_detail::bad_exception_>::`vbtable'
0x180003ef4  mov     [rbp+57h+var_90], rdi
0x180003ef8  lea     rax, ??_7clone_base@exception_detail@boost@@6B@; const boost::exception_detail::clone_base::`vftable'
0x180003eff  mov     [rbp+57h+var_80], rax
0x180003f03  mov     [rsp+110h+var_F0], 2
0x180003f0b  lea     r12, ??_7exception@boost@@6B@; const boost::exception::`vftable'
0x180003f12  mov     [rbp+57h+var_D0], r12
0x180003f16  mov     [rbp+57h+var_C8], rcx
0x180003f1a  mov     rax, qword ptr [rbp+57h+var_60]
0x180003f1e  mov     qword ptr [rbp+57h+var_C0], rax
0x180003f22  mov     rax, qword ptr [rbp+57h+var_60+8]
0x180003f26  mov     qword ptr [rbp+57h+var_C0+8], rax
0x180003f2a  mov     [rbp+57h+var_B0], edx
0x180003f2d  mov     [rbp+57h+var_AC], esi
0x180003f30  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180003f37  mov     [rbp+57h+var_A8], rax
0x180003f3b  xorps   xmm0, xmm0
0x180003f3e  movups  [rbp+57h+var_A0], xmm0
0x180003f42  lea     rdx, [rbp+57h+var_A0]
0x180003f46  lea     rcx, [rbp+57h+var_40]
0x180003f4a  call    _o___std_exception_copy_0
0x180003f4f  nop
0x180003f50  lea     rax, ??_7?$clone_impl@Ubad_exception_@exception_detail@boost@@@exception_detail@boost@@6Bexception@2@@; const boost::exception_detail::clone_impl<boost::exception_detail::bad_exception_>::`vftable'{for `boost::exception'}
0x180003f57  mov     [rbp+57h+var_D0], rax
0x180003f5b  lea     rax, ??_7?$clone_impl@Ubad_exception_@exception_detail@boost@@@exception_detail@boost@@6Bbad_exception@std@@@; const boost::exception_detail::clone_impl<boost::exception_detail::bad_exception_>::`vftable'{for `std::bad_exception'}
0x180003f62  mov     [rbp+57h+var_A8], rax
0x180003f66  mov     rax, [rbp+57h+var_90]
0x180003f6a  movsxd  rcx, dword ptr [rax+4]
0x180003f6e  lea     rax, ??_7?$clone_impl@Ubad_exception_@exception_detail@boost@@@exception_detail@boost@@6B@; const boost::exception_detail::clone_impl<boost::exception_detail::bad_exception_>::`vftable'
0x180003f75  mov     [rbp+rcx+57h+var_90], rax
0x180003f7a  mov     rax, [rbp+57h+var_90]
0x180003f7e  movsxd  rcx, dword ptr [rax+4]
0x180003f82  lea     edx, [rcx-10h]
0x180003f85  mov     dword ptr [rbp+rcx+57h+var_A0+0Ch], edx
0x180003f89  mov     ebx, r15d
0x180003f8c  mov     [rbp+57h+arg_0], rbx
0x180003f90  mov     rcx, [rbp+57h+var_68]
0x180003f94  test    rcx, rcx
0x180003f97  jz      short loc_180003FDC
0x180003f99  mov     rax, [rcx]
0x180003f9c  lea     rdx, [rbp+57h+arg_8]
0x180003fa0  mov     rax, [rax+28h]
0x180003fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fa9  nop
0x180003faa  mov     rbx, [rax]
0x180003fad  mov     [rbp+57h+arg_0], rbx
0x180003fb1  test    rbx, rbx
0x180003fb4  jz      short loc_180003FC6
0x180003fb6  mov     rax, [rbx]
0x180003fb9  mov     rcx, rbx
0x180003fbc  mov     rax, [rax+18h]
0x180003fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fc5  nop
0x180003fc6  mov     rcx, [rbp+57h+arg_8]
0x180003fca  test    rcx, rcx
0x180003fcd  jz      short loc_180003FDC
0x180003fcf  mov     rax, [rcx]
0x180003fd2  mov     rax, [rax+20h]
0x180003fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fdb  nop
0x180003fdc  mov     rax, qword ptr [rbp+57h+var_60+8]
0x180003fe0  mov     qword ptr [rbp+57h+var_C0+8], rax
0x180003fe4  mov     eax, [rbp+57h+var_50]
0x180003fe7  mov     [rbp+57h+var_B0], eax
0x180003fea  mov     rax, qword ptr [rbp+57h+var_60]
0x180003fee  mov     qword ptr [rbp+57h+var_C0], rax
0x180003ff2  mov     eax, [rbp+57h+var_4C]
0x180003ff5  mov     [rbp+57h+var_AC], eax
0x180003ff8  mov     rcx, [rbp+57h+var_C8]
0x180003ffc  test    rcx, rcx
0x180003fff  jz      short loc_18000400D
0x180004001  mov     rax, [rcx]
0x180004004  mov     rax, [rax+20h]
0x180004008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000400d  mov     [rbp+57h+var_C8], rbx
0x180004011  test    rbx, rbx
0x180004014  jz      short loc_180004026
0x180004016  mov     rax, [rbx]
0x180004019  mov     rcx, rbx
0x18000401c  mov     rax, [rax+18h]
0x180004020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004025  nop
0x180004026  test    rbx, rbx
0x180004029  jz      short loc_18000403B
0x18000402b  mov     rax, [rbx]
0x18000402e  mov     rcx, rbx
0x180004031  mov     rax, [rax+20h]
0x180004035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000403a  nop
0x18000403b  lea     rax, aClassBoostExce; "class boost::exception_ptr __cdecl boos"...
0x180004042  mov     qword ptr [rbp+57h+var_C0], rax
0x180004046  lea     rax, aDOsObjAmd64fre; "D:\\os\\obj\\amd64fre\\onecoreuap\\vcpk"...
0x18000404d  mov     qword ptr [rbp+57h+var_C0+8], rax
0x180004051  mov     [rbp+57h+var_B0], 0B7h
0x180004058  mov     ecx, cs:_tls_index
0x18000405e  mov     rax, gs:58h
0x180004067  mov     edx, 8
0x18000406c  mov     rax, [rax+rcx*8]
0x180004070  mov     eax, [rdx+rax]
0x180004073  cmp     cs:?$TSS0@?1???$get_static_exception_object@Ubad_exception_@exception_detail@boost@@@exception_detail@boost@@YA?AVexception_ptr@2@XZ@4HA, eax
0x180004079  jg      loc_180004181
0x18000407f  mov     rax, cs:?ep@?1???$get_static_exception_object@Ubad_exception_@exception_detail@boost@@@exception_detail@boost@@YA?AVexception_ptr@2@XZ@4V32@A; boost::exception_ptr `boost::exception_detail::get_static_exception_object<boost::exception_detail::bad_exception_>(void)'::`2'::ep
0x180004086  mov     [r14], rax
0x180004089  mov     rax, cs:qword_180032B00
0x180004090  mov     [r14+8], rax
0x180004094  test    rax, rax
0x180004097  jz      short loc_18000409D
0x180004099  lock inc dword ptr [rax+8]
0x18000409d  lea     rax, ??_7?$clone_impl@Ubad_exception_@exception_detail@boost@@@exception_detail@boost@@6Bexception@2@@; const boost::exception_detail::clone_impl<boost::exception_detail::bad_exception_>::`vftable'{for `boost::exception'}
0x1800040a4  mov     [rbp+57h+var_D0], rax
0x1800040a8  lea     rax, ??_7?$clone_impl@Ubad_exception_@exception_detail@boost@@@exception_detail@boost@@6Bbad_exception@std@@@; const boost::exception_detail::clone_impl<boost::exception_detail::bad_exception_>::`vftable'{for `std::bad_exception'}
0x1800040af  mov     [rbp+57h+var_A8], rax
0x1800040b3  mov     rax, [rbp+57h+var_90]
0x1800040b7  movsxd  rcx, dword ptr [rax+4]
0x1800040bb  lea     rax, ??_7?$clone_impl@Ubad_exception_@exception_detail@boost@@@exception_detail@boost@@6B@; const boost::exception_detail::clone_impl<boost::exception_detail::bad_exception_>::`vftable'
0x1800040c2  mov     [rbp+rcx+57h+var_90], rax
0x1800040c7  mov     rax, [rbp+57h+var_90]
0x1800040cb  movsxd  rcx, dword ptr [rax+4]
0x1800040cf  lea     edx, [rcx-10h]
0x1800040d2  mov     dword ptr [rbp+rcx+57h+var_A0+0Ch], edx
0x1800040d6  mov     [rbp+57h+var_D0], r13
0x1800040da  lea     rbx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800040e1  mov     [rbp+57h+var_A8], rbx
0x1800040e5  lea     rcx, [rbp+57h+var_A0]
0x1800040e9  call    _o___std_exception_destroy_0
0x1800040ee  mov     [rbp+57h+var_D0], r12
0x1800040f2  mov     rcx, [rbp+57h+var_C8]
0x1800040f6  test    rcx, rcx
0x1800040f9  jz      short loc_18000410F
0x1800040fb  mov     rax, [rcx]
0x1800040fe  mov     rax, [rax+20h]
0x180004102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004107  test    al, al
0x180004109  jz      short loc_18000410F
0x18000410b  mov     [rbp+57h+var_C8], r15
0x18000410f  lea     rax, ??_7clone_base@exception_detail@boost@@6B@; const boost::exception_detail::clone_base::`vftable'
0x180004116  mov     [rbp+57h+var_80], rax
0x18000411a  mov     [rbp+57h+var_70], r13
0x18000411e  mov     [rbp+57h+var_48], rbx
0x180004122  lea     rcx, [rbp+57h+var_40]
0x180004126  call    _o___std_exception_destroy_0
0x18000412b  mov     [rbp+57h+var_70], r12
0x18000412f  mov     rcx, [rbp+57h+var_68]
0x180004133  test    rcx, rcx
0x180004136  jz      short loc_180004145
0x180004138  mov     rax, [rcx]
0x18000413b  mov     rax, [rax+20h]
0x18000413f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004144  nop
0x180004145  mov     rax, r14
0x180004148  mov     rbx, [rsp+110h+arg_10]
0x180004150  add     rsp, 0E0h
0x180004157  pop     r15
0x180004159  pop     r14
0x18000415b  pop     r13
0x18000415d  pop     r12
0x18000415f  pop     rdi
0x180004160  pop     rsi
0x180004161  pop     rbp
0x180004162  retn
0x180004163  lea     rcx, _boost__exception_detail__get_static_exception_object_boost__exception_detail__bad_exception______2____dynamic_atexit_destructor_for__ep__; void (__cdecl *)()
0x18000416a  call    atexit
0x18000416f  nop
0x180004170  lea     rcx, ?$TSS0@?1???$get_static_exception_object@Ubad_exception_@exception_detail@boost@@@exception_detail@boost@@YA?AVexception_ptr@2@XZ@4HA
0x180004177  call    _Init_thread_footer
0x18000417c  jmp     loc_18000407F
0x180004181  lea     rcx, ?$TSS0@?1???$get_static_exception_object@Ubad_exception_@exception_detail@boost@@@exception_detail@boost@@YA?AVexception_ptr@2@XZ@4HA
0x180004188  call    _Init_thread_header
0x18000418d  cmp     cs:?$TSS0@?1???$get_static_exception_object@Ubad_exception_@exception_detail@boost@@@exception_detail@boost@@YA?AVexception_ptr@2@XZ@4HA, 0FFFFFFFFh
0x180004194  jnz     loc_18000407F
0x18000419a  mov     ecx, 58h ; 'X'; Size
0x18000419f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800041a4  mov     rbx, rax
0x1800041a7  mov     [rbp+57h+arg_0], rax
0x1800041ab  test    rax, rax
0x1800041ae  jz      loc_180004259
0x1800041b4  mov     [rax+40h], rdi
0x1800041b8  lea     rax, ??_7clone_base@exception_detail@boost@@6B@; const boost::exception_detail::clone_base::`vftable'
0x1800041bf  mov     [rbx+50h], rax
0x1800041c3  mov     [rsp+110h+var_F0], 6
0x1800041cb  mov     [rbx], r12
0x1800041ce  mov     rcx, [rbp+57h+var_C8]
0x1800041d2  mov     [rbx+8], rcx
0x1800041d6  test    rcx, rcx
0x1800041d9  jz      short loc_1800041E7
0x1800041db  mov     rax, [rcx]
0x1800041de  mov     rax, [rax+18h]
0x1800041e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041e7  mov     rax, qword ptr [rbp+57h+var_C0]
0x1800041eb  mov     [rbx+10h], rax
0x1800041ef  mov     rax, qword ptr [rbp+57h+var_C0+8]
0x1800041f3  mov     [rbx+18h], rax
0x1800041f7  mov     eax, [rbp+57h+var_B0]
0x1800041fa  mov     [rbx+20h], eax
0x1800041fd  mov     eax, [rbp+57h+var_AC]
0x180004200  mov     [rbx+24h], eax
0x180004203  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18000420a  mov     [rbx+28h], rax
0x18000420e  lea     rdx, [rbx+30h]
0x180004212  xorps   xmm0, xmm0
0x180004215  movups  xmmword ptr [rdx], xmm0
0x180004218  lea     rcx, [rbp+57h+var_A0]
0x18000421c  call    _o___std_exception_copy_0
0x180004221  lea     rax, ??_7?$clone_impl@Ubad_exception_@exception_detail@boost@@@exception_detail@boost@@6Bexception@2@@; const boost::exception_detail::clone_impl<boost::exception_detail::bad_exception_>::`vftable'{for `boost::exception'}
0x180004228  mov     [rbx], rax
0x18000422b  lea     rax, ??_7?$clone_impl@Ubad_exception_@exception_detail@boost@@@exception_detail@boost@@6Bbad_exception@std@@@; const boost::exception_detail::clone_impl<boost::exception_detail::bad_exception_>::`vftable'{for `std::bad_exception'}
0x180004232  mov     [rbx+28h], rax
0x180004236  mov     rax, [rbx+40h]
0x18000423a  movsxd  rcx, dword ptr [rax+4]
0x18000423e  lea     rax, ??_7?$clone_impl@Ubad_exception_@exception_detail@boost@@@exception_detail@boost@@6B@; const boost::exception_detail::clone_impl<boost::exception_detail::bad_exception_>::`vftable'
0x180004245  mov     [rcx+rbx+40h], rax
0x18000424a  mov     rax, [rbx+40h]
0x18000424e  movsxd  rcx, dword ptr [rax+4]
0x180004252  mov     [rcx+rbx+3Ch], r15d
0x180004257  jmp     short loc_18000425C
0x180004259  mov     rbx, r15
0x18000425c  test    rbx, rbx
0x18000425f  jnz     short loc_180004268
0x180004261  mov     [rsp+110h+var_E8], r15
0x180004266  jmp     short loc_18000427C
0x180004268  mov     rax, [rbx+40h]
0x18000426c  movsxd  rax, dword ptr [rax+4]
0x180004270  add     rax, 40h ; '@'
0x180004274  add     rax, rbx
0x180004277  mov     [rsp+110h+var_E8], rax
0x18000427c  mov     [rsp+110h+var_E0], r15
0x180004281  mov     rdx, rbx
0x180004284  lea     rcx, [rbp+57h+arg_0]
0x180004288  call    ??$?0V?$clone_impl@Ubad_exception_@exception_detail@boost@@@exception_detail@boost@@@shared_count@detail@boost@@QEAA@PEAV?$clone_impl@Ubad_exception_@exception_detail@boost@@@exception_detail@2@@Z; boost::detail::shared_count::shared_count(boost::exception_detail::clone_impl<boost::exception_detail::bad_exception_> *)
0x18000428d  mov     rdx, [rsp+110h+var_E0]
0x180004292  mov     rcx, [rax]
0x180004295  mov     [rsp+110h+var_E0], rcx
0x18000429a  mov     [rax], rdx
0x18000429d  mov     rdi, [rbp+57h+arg_0]
0x1800042a1  test    rdi, rdi
0x1800042a4  jz      short loc_1800042DC
0x1800042a6  mov     eax, esi
0x1800042a8  lock xadd [rdi+8], eax
0x1800042ad  cmp     eax, 1
0x1800042b0  jnz     short loc_1800042DC
0x1800042b2  mov     rax, [rdi]
0x1800042b5  mov     rcx, rdi
0x1800042b8  mov     rax, [rax+8]
0x1800042bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042c1  mov     eax, esi
0x1800042c3  lock xadd [rdi+0Ch], eax
0x1800042c8  cmp     eax, 1
0x1800042cb  jnz     short loc_1800042DC
0x1800042cd  mov     rax, [rdi]
0x1800042d0  mov     rcx, rdi
0x1800042d3  mov     rax, [rax+10h]
0x1800042d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042dc  mov     r8, rbx
0x1800042df  mov     rdx, rbx
0x1800042e2  lea     rcx, [rsp+110h+var_E8]
0x1800042e7  call    ?sp_enable_shared_from_this@detail@boost@@YAXZZ; boost::detail::sp_enable_shared_from_this(...)
0x1800042ec  nop
0x1800042ed  mov     rax, [rsp+110h+var_E8]
0x1800042f2  mov     cs:?ep@?1???$get_static_exception_object@Ubad_exception_@exception_detail@boost@@@exception_detail@boost@@YA?AVexception_ptr@2@XZ@4V32@A, rax; boost::exception_ptr `boost::exception_detail::get_static_exception_object<boost::exception_detail::bad_exception_>(void)'::`2'::ep
0x1800042f9  mov     rbx, [rsp+110h+var_E0]
0x1800042fe  mov     cs:qword_180032B00, rbx
0x180004305  test    rbx, rbx
0x180004308  jz      loc_180004163
0x18000430e  lock inc dword ptr [rbx+8]
0x180004312  mov     rbx, [rsp+110h+var_E0]
0x180004317  test    rbx, rbx
0x18000431a  jz      loc_180004163
0x180004320  mov     eax, esi
0x180004322  lock xadd [rbx+8], eax
0x180004327  cmp     eax, 1
0x18000432a  jnz     loc_180004163
  ... truncated ...
```
