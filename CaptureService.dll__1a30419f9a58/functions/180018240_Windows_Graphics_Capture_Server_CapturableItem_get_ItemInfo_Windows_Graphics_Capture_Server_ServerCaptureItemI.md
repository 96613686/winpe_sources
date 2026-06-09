# Windows::Graphics::Capture::Server::CapturableItem::get_ItemInfo(Windows::Graphics::Capture::Server::ServerCaptureItemInfo *)

- ea: `0x180018240`
- end: `0x180018560`
- name: `?get_ItemInfo@CapturableItem@Server@Capture@Graphics@Windows@@UEAAJPEAUServerCaptureItemInfo@2345@@Z`
- size: `800`
- prototype: `__int64 __fastcall(Windows::Graphics::Capture::Server::CapturableItem *__hidden this, struct Windows::Graphics::Capture::Server::ServerCaptureItemInfo *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005588`
- `0x18000907c`
- `0x18000ddc4`
- `0x180018240`
- `0x18001881c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001825c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001825c`

## string_xrefs

- `0x18001828e`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x18001830e`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x1800183a0`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180018448`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x1800184e5`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::CapturableItem::get_ItemInfo(
        RTL_SRWLOCK *this,
        struct Windows::Graphics::Capture::Server::ServerCaptureItemInfo *a2)
{
  RTL_SRWLOCK *v4; // rbx
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v16; // [rsp+20h] [rbp-50h] BYREF
  __int64 v17; // [rsp+28h] [rbp-48h] BYREF
  __int64 v18; // [rsp+30h] [rbp-40h] BYREF
  __int64 v19; // [rsp+38h] [rbp-38h] BYREF
  __int64 v20; // [rsp+40h] [rbp-30h] BYREF
  __int64 v21; // [rsp+48h] [rbp-28h] BYREF
  RTL_SRWLOCK *v22; // [rsp+50h] [rbp-20h] BYREF
  __int128 v23; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  int v25; // [rsp+90h] [rbp+20h] BYREF
  unsigned int v26; // [rsp+A0h] [rbp+30h] BYREF
  unsigned int v27; // [rsp+A8h] [rbp+38h] BYREF

  v4 = this + 8;
  AcquireSRWLockShared(this + 8);
  v22 = v4;
  v25 = 0;
  v5 = (*(__int64 (__fastcall **)(PVOID, int *))(*(_QWORD *)this[3].Ptr + 56LL))(this[3].Ptr, &v25);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v23 = 0;
    switch ( v25 )
    {
      case 1:
        v16 = 0;
        wil::com_ptr_t<IDCompositionCaptureRenderTargetInternal,wil::err_returncode_policy>::reset(&v16);
        v13 = (**(__int64 (__fastcall ***)(PVOID, GUID *, __int64 *))this[3].Ptr)(
                this[3].Ptr,
                &GUID_5ed78b65_017c_4cb7_a935_7521855ecc71,
                &v16);
        v6 = v13;
        if ( v13 >= 0 )
        {
          v27 = 0;
          v13 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v16 + 48LL))(v16, &v27);
          v6 = v13;
          if ( v13 >= 0 )
          {
            *((_QWORD *)&v23 + 1) = v27;
            wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v16);
            goto LABEL_34;
          }
          v14 = 432;
        }
        else
        {
          v14 = 430;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
          (const char *)(unsigned int)v13,
          v16);
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v16);
        goto LABEL_35;
      case 2:
        v19 = 0;
        v11 = (**(__int64 (__fastcall ***)(PVOID, GUID *, __int64 *))this[3].Ptr)(
                this[3].Ptr,
                &GUID_2f5f1c42_2dea_4fa2_a9e1_b744015aaa42,
                &v19);
        v6 = v11;
        if ( v11 >= 0 )
        {
          v21 = 0;
          v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 48LL))(v19, &v21);
          v6 = v11;
          if ( v11 >= 0 )
          {
            LODWORD(v23) = 1;
            *((_QWORD *)&v23 + 1) = v21;
            wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v19);
            goto LABEL_34;
          }
          v12 = 442;
        }
        else
        {
          v12 = 440;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
          (const char *)(unsigned int)v11,
          v16);
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v19);
        goto LABEL_35;
      case 4:
        LODWORD(v23) = 2;
        *((_QWORD *)&v23 + 1) = 0;
        goto LABEL_34;
    }
    if ( v25 != 5 )
    {
      if ( v25 != 6 )
      {
        v6 = -2147418113;
        goto LABEL_35;
      }
      v17 = 0;
      v7 = (**(__int64 (__fastcall ***)(PVOID, GUID *, __int64 *))this[3].Ptr)(
             this[3].Ptr,
             &GUID_1b9befd5_cada_463e_8233_56806ba2bfe7,
             &v17);
      v6 = v7;
      if ( v7 < 0 )
      {
        v8 = 466;
LABEL_11:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v8,
          (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
          (const char *)(unsigned int)v7,
          v16);
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v17);
        goto LABEL_35;
      }
      v26 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v17 + 48LL))(v17, &v26);
      v6 = v7;
      if ( v7 < 0 )
      {
        v8 = 468;
        goto LABEL_11;
      }
      LODWORD(v23) = 4;
      *((_QWORD *)&v23 + 1) = v26;
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v17);
LABEL_34:
      *(_OWORD *)a2 = v23;
      v6 = 0;
      goto LABEL_35;
    }
    v18 = 0;
    v9 = (**(__int64 (__fastcall ***)(PVOID, GUID *, __int64 *))this[3].Ptr)(
           this[3].Ptr,
           &GUID_f8ac82ef_90cb_41d2_bc28_8b23c9b47995,
           &v18);
    v6 = v9;
    if ( v9 >= 0 )
    {
      v20 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 48LL))(v18, &v20);
      v6 = v9;
      if ( v9 >= 0 )
      {
        LODWORD(v23) = 3;
        *((_QWORD *)&v23 + 1) = v20;
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v18);
        goto LABEL_34;
      }
      v10 = 458;
    }
    else
    {
      v10 = 456;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
      (const char *)(unsigned int)v9,
      v16);
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v18);
    goto LABEL_35;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1A5,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
    (const char *)(unsigned int)v5,
    v16);
LABEL_35:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v22);
  return v6;
}

```

## disassembly

```asm
0x180018240  mov     [rsp-18h+arg_8], rbx
0x180018245  push    rbp
0x180018246  push    rsi
0x180018247  push    rdi
0x180018248  mov     rbp, rsp
0x18001824b  sub     rsp, 70h
0x18001824f  mov     rsi, rdx
0x180018252  mov     rdi, rcx
0x180018255  lea     rbx, [rcx+40h]
0x180018259  mov     rcx, rbx; SRWLock
0x18001825c  call    cs:__imp_AcquireSRWLockShared
0x180018262  mov     [rbp+var_20], rbx
0x180018266  mov     [rbp+arg_0], 0
0x18001826d  mov     rcx, [rdi+18h]
0x180018271  mov     rax, [rcx]
0x180018274  lea     rdx, [rbp+arg_0]
0x180018278  mov     rax, [rax+38h]
0x18001827c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018281  mov     ebx, eax
0x180018283  test    eax, eax
0x180018285  jns     short loc_1800182A4
0x180018287  mov     rcx, [rbp+18h]; this
0x18001828b  mov     r9d, eax; char *
0x18001828e  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180018295  mov     edx, 1A5h; void *
0x18001829a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001829f  jmp     loc_180018545
0x1800182a4  xorps   xmm0, xmm0
0x1800182a7  movups  [rbp+var_18], xmm0
0x1800182ab  mov     eax, [rbp+arg_0]
0x1800182ae  sub     eax, 1
0x1800182b1  jz      loc_1800184AF
0x1800182b7  sub     eax, 1
0x1800182ba  jz      loc_18001841B
0x1800182c0  sub     eax, 2
0x1800182c3  jz      loc_180018407
0x1800182c9  sub     eax, 1
0x1800182cc  jz      loc_180018373
0x1800182d2  cmp     eax, 1
0x1800182d5  jz      short loc_1800182E1
0x1800182d7  mov     ebx, 8000FFFFh
0x1800182dc  jmp     loc_180018545
0x1800182e1  mov     [rbp+var_48], 0
0x1800182e9  mov     rcx, [rdi+18h]
0x1800182ed  mov     rax, [rcx]
0x1800182f0  lea     r8, [rbp+var_48]
0x1800182f4  lea     rdx, _GUID_1b9befd5_cada_463e_8233_56806ba2bfe7
0x1800182fb  mov     rax, [rax]
0x1800182fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018303  mov     ebx, eax
0x180018305  test    eax, eax
0x180018307  jns     short loc_18001832F
0x180018309  mov     edx, 1D2h; void *
0x18001830e  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180018315  mov     r9d, eax; char *
0x180018318  mov     rcx, [rbp+18h]; this
0x18001831c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018321  lea     rcx, [rbp+var_48]
0x180018325  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001832a  jmp     loc_180018545
0x18001832f  mov     [rbp+arg_10], 0
0x180018336  mov     rcx, [rbp+var_48]
0x18001833a  mov     rax, [rcx]
0x18001833d  lea     rdx, [rbp+arg_10]
0x180018341  mov     rax, [rax+30h]
0x180018345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001834a  mov     ebx, eax
0x18001834c  test    eax, eax
0x18001834e  jns     short loc_180018357
0x180018350  mov     edx, 1D4h
0x180018355  jmp     short loc_18001830E
0x180018357  mov     dword ptr [rbp+var_18], 4
0x18001835e  mov     eax, [rbp+arg_10]
0x180018361  mov     qword ptr [rbp+var_18+8], rax
0x180018365  lea     rcx, [rbp+var_48]
0x180018369  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001836e  jmp     loc_18001853B
0x180018373  mov     [rbp+var_40], 0
0x18001837b  mov     rcx, [rdi+18h]
0x18001837f  mov     rax, [rcx]
0x180018382  lea     r8, [rbp+var_40]
0x180018386  lea     rdx, _GUID_f8ac82ef_90cb_41d2_bc28_8b23c9b47995
0x18001838d  mov     rax, [rax]
0x180018390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018395  mov     ebx, eax
0x180018397  test    eax, eax
0x180018399  jns     short loc_1800183C1
0x18001839b  mov     edx, 1C8h; void *
0x1800183a0  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x1800183a7  mov     r9d, eax; char *
0x1800183aa  mov     rcx, [rbp+18h]; this
0x1800183ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800183b3  lea     rcx, [rbp+var_40]
0x1800183b7  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x1800183bc  jmp     loc_180018545
0x1800183c1  mov     [rbp+var_30], 0
0x1800183c9  mov     rcx, [rbp+var_40]
0x1800183cd  mov     rax, [rcx]
0x1800183d0  lea     rdx, [rbp+var_30]
0x1800183d4  mov     rax, [rax+30h]
0x1800183d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183dd  mov     ebx, eax
0x1800183df  test    eax, eax
0x1800183e1  jns     short loc_1800183EA
0x1800183e3  mov     edx, 1CAh
0x1800183e8  jmp     short loc_1800183A0
0x1800183ea  mov     dword ptr [rbp+var_18], 3
0x1800183f1  mov     rax, [rbp+var_30]
0x1800183f5  mov     qword ptr [rbp+var_18+8], rax
0x1800183f9  lea     rcx, [rbp+var_40]
0x1800183fd  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180018402  jmp     loc_18001853B
0x180018407  mov     dword ptr [rbp+var_18], 2
0x18001840e  mov     qword ptr [rbp+var_18+8], 0
0x180018416  jmp     loc_18001853B
0x18001841b  mov     [rbp+var_38], 0
0x180018423  mov     rcx, [rdi+18h]
0x180018427  mov     rax, [rcx]
0x18001842a  lea     r8, [rbp+var_38]
0x18001842e  lea     rdx, _GUID_2f5f1c42_2dea_4fa2_a9e1_b744015aaa42
0x180018435  mov     rax, [rax]
0x180018438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001843d  mov     ebx, eax
0x18001843f  test    eax, eax
0x180018441  jns     short loc_180018469
0x180018443  mov     edx, 1B8h; void *
0x180018448  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001844f  mov     r9d, eax; char *
0x180018452  mov     rcx, [rbp+18h]; this
0x180018456  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001845b  lea     rcx, [rbp+var_38]
0x18001845f  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180018464  jmp     loc_180018545
0x180018469  mov     [rbp+var_28], 0
0x180018471  mov     rcx, [rbp+var_38]
0x180018475  mov     rax, [rcx]
0x180018478  lea     rdx, [rbp+var_28]
0x18001847c  mov     rax, [rax+30h]
0x180018480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018485  mov     ebx, eax
0x180018487  test    eax, eax
0x180018489  jns     short loc_180018492
0x18001848b  mov     edx, 1BAh
0x180018490  jmp     short loc_180018448
0x180018492  mov     dword ptr [rbp+var_18], 1
0x180018499  mov     rax, [rbp+var_28]
0x18001849d  mov     qword ptr [rbp+var_18+8], rax
0x1800184a1  lea     rcx, [rbp+var_38]
0x1800184a5  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x1800184aa  jmp     loc_18001853B
0x1800184af  mov     [rbp+var_50], 0
0x1800184b7  lea     rcx, [rbp+var_50]
0x1800184bb  call    ?reset@?$com_ptr_t@UIDCompositionCaptureRenderTargetInternal@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IDCompositionCaptureRenderTargetInternal,wil::err_returncode_policy>::reset(void)
0x1800184c0  mov     rcx, [rdi+18h]
0x1800184c4  mov     rax, [rcx]
0x1800184c7  lea     r8, [rbp+var_50]
0x1800184cb  lea     rdx, _GUID_5ed78b65_017c_4cb7_a935_7521855ecc71
0x1800184d2  mov     rax, [rax]
0x1800184d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184da  mov     ebx, eax
0x1800184dc  test    eax, eax
0x1800184de  jns     short loc_180018503
0x1800184e0  mov     edx, 1AEh; void *
0x1800184e5  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x1800184ec  mov     r9d, eax; char *
0x1800184ef  mov     rcx, [rbp+18h]; this
0x1800184f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800184f8  lea     rcx, [rbp+var_50]
0x1800184fc  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180018501  jmp     short loc_180018545
0x180018503  mov     [rbp+arg_18], 0
0x18001850a  mov     rcx, [rbp+var_50]
0x18001850e  mov     rax, [rcx]
0x180018511  lea     rdx, [rbp+arg_18]
0x180018515  mov     rax, [rax+30h]
0x180018519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001851e  mov     ebx, eax
0x180018520  test    eax, eax
0x180018522  jns     short loc_18001852B
0x180018524  mov     edx, 1B0h
0x180018529  jmp     short loc_1800184E5
0x18001852b  mov     eax, [rbp+arg_18]
0x18001852e  mov     qword ptr [rbp+var_18+8], rax
0x180018532  lea     rcx, [rbp+var_50]
0x180018536  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001853b  movups  xmm0, [rbp+var_18]
0x18001853f  movdqu  xmmword ptr [rsi], xmm0
0x180018543  xor     ebx, ebx
0x180018545  lea     rcx, [rbp+var_20]
0x180018549  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001854e  mov     eax, ebx
0x180018550  mov     rbx, [rsp+70h+arg_8]
0x180018558  add     rsp, 70h
0x18001855c  pop     rdi
0x18001855d  pop     rsi
0x18001855e  pop     rbp
0x18001855f  retn
```
