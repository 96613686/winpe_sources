# Windows::Graphics::Capture::Server::_anonymous_namespace_::GetDeviceIdFromDisplayId

- ea: `0x180010f5c`
- end: `0x18001130d`
- name: `Windows::Graphics::Capture::Server::_anonymous_namespace_::GetDeviceIdFromDisplayId`
- size: `945`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180016540`
- `0x1800169d8`

## callees

- `0x180002e60`
- `0x180007630`
- `0x18000907c`
- `0x18000ddc4`
- `0x18000f7b4`
- `0x180010f5c`
- `0x180017da0`
- `0x180017f44`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180010fba`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180010fba`

## string_xrefs

- `0x180010fcd`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x18001100b`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x1800111c0`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180011269`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180011250`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800112b3`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall Windows::Graphics::Capture::Server::_anonymous_namespace_::GetDeviceIdFromDisplayId(
        __int64 a1,
        _QWORD *a2)
{
  int ActivationFactory; // eax
  unsigned int v5; // ebx
  __int64 v6; // rax
  int v7; // eax
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64 **); // rbx
  int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  int i; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, _QWORD); // rbx
  int v17; // eax
  __int64 (__fastcall **v18)(__int64, GUID *, __int64 *); // rax
  int v19; // eax
  __int64 v20; // rdx
  __int64 v22; // [rsp+20h] [rbp-79h] BYREF
  __int64 v23; // [rsp+28h] [rbp-71h] BYREF
  __int64 v24; // [rsp+30h] [rbp-69h] BYREF
  __int64 v25; // [rsp+38h] [rbp-61h]
  unsigned int v26; // [rsp+40h] [rbp-59h]
  __int64 (__fastcall ***v27)(__int64, GUID *, __int64 *); // [rsp+48h] [rbp-51h] BYREF
  __int64 v28; // [rsp+50h] [rbp-49h]
  unsigned int v29; // [rsp+58h] [rbp-41h]
  __int64 *v30; // [rsp+60h] [rbp-39h] BYREF
  __int64 *v31; // [rsp+68h] [rbp-31h] BYREF
  __int64 v32; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v33[8]; // [rsp+78h] [rbp-21h] BYREF
  int v34; // [rsp+80h] [rbp-19h]
  _BYTE v35[8]; // [rsp+88h] [rbp-11h] BYREF
  __int64 v36; // [rsp+90h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-1h] BYREF
  __int64 v38; // [rsp+B0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  *a2 = 0;
  v31 = 0;
  v38 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.UI.WindowManagement.WindowingEnvironment",
    0x31u,
    0x30u);
  ActivationFactory = RoGetActivationFactory(v38, &GUID_874e9fb7_c642_55ab_8aa2_162f734a9a72, &v31);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v22);
LABEL_27:
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v31);
    return v5;
  }
  v22 = 0;
  v6 = *v31;
  v22 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v6 + 48))(v31, &v22);
  v5 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
      (const char *)(unsigned int)v7,
      v22);
LABEL_26:
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v22);
    goto LABEL_27;
  }
  v32 = v22;
  v28 = v22;
  v29 = 0;
  v30 = 0;
  wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_exception_policy>::end(
    &v32,
    v33);
  v8 = v29;
LABEL_6:
  if ( v8 != v34 )
  {
    v9 = v28;
    v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 **))(*(_QWORD *)v28 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    v11 = v10(v9, v29, &v30);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v11,
        v22);
    v23 = 0;
    v12 = *v30;
    v23 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v12 + 64))(v30, &v23);
    v5 = v13;
    if ( v13 >= 0 )
    {
      v36 = v23;
      v25 = v23;
      v26 = 0;
      v27 = 0;
      wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_exception_policy>::end(
        &v36,
        &hstringHeader);
      for ( i = v26; ; i = ++v26 )
      {
        if ( i == *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&hstringHeader.Reserved.Reserved2[16]);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
          wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v23);
          v8 = ++v29;
          goto LABEL_6;
        }
        v15 = v25;
        v16 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v25 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
        v17 = v16(v15, v26, &v27);
        if ( v17 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x1CBE,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
            (const char *)(unsigned int)v17,
            v22);
        v24 = 0;
        v18 = *v27;
        v24 = 0;
        v19 = (*v18)((__int64)v27, &GUID_4d008e5e_e2d5_5e99_bae7_e66d5f3a87c8, &v24);
        v5 = v19;
        if ( v19 < 0 )
        {
          v20 = 32;
          goto LABEL_19;
        }
        v32 = 0;
        v19 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 48LL))(v24, &v32);
        v5 = v19;
        if ( v19 < 0 )
        {
          v20 = 34;
          goto LABEL_19;
        }
        if ( v32 == a1 )
          break;
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v24);
      }
      v19 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *), _QWORD *))(*v27)[6])(v27, a2);
      v5 = v19;
      if ( v19 < 0 )
      {
        v20 = 38;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
          (const char *)(unsigned int)v19,
          v22);
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v24);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&hstringHeader.Reserved.Reserved2[16]);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
        goto LABEL_25;
      }
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v24);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&hstringHeader.Reserved.Reserved2[16]);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v23);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v35);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v22);
      v5 = 0;
      goto LABEL_27;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
      (const char *)(unsigned int)v13,
      v22);
LABEL_25:
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v23);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v35);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    goto LABEL_26;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v35);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v22);
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v31);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180010f5c  push    rbp
0x180010f5e  push    rbx
0x180010f5f  push    rsi
0x180010f60  push    rdi
0x180010f61  push    r14
0x180010f63  push    r15
0x180010f65  lea     rbp, [rsp-2Fh]
0x180010f6a  sub     rsp, 0C8h
0x180010f71  mov     rax, cs:__security_cookie
0x180010f78  xor     rax, rsp
0x180010f7b  mov     [rbp+57h+var_38], rax
0x180010f7f  mov     rsi, rdx
0x180010f82  mov     r14, rcx
0x180010f85  xor     r15d, r15d
0x180010f88  mov     [rdx], r15
0x180010f8b  mov     [rbp+57h+var_88], r15
0x180010f8f  mov     [rbp+57h+var_40], r15
0x180010f93  lea     r9d, [r15+30h]; unsigned int
0x180010f97  lea     r8d, [r15+31h]; unsigned int
0x180010f9b  lea     rdx, ?RuntimeClass_Windows_UI_WindowManagement_WindowingEnvironment@@3QBGB; "Windows.UI.WindowManagement.WindowingEn"...
0x180010fa2  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180010fa6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180010fab  lea     r8, [rbp+57h+var_88]
0x180010faf  lea     rdx, _GUID_874e9fb7_c642_55ab_8aa2_162f734a9a72
0x180010fb6  mov     rcx, [rbp+57h+var_40]
0x180010fba  call    cs:__imp_RoGetActivationFactory
0x180010fc0  mov     ebx, eax
0x180010fc2  test    eax, eax
0x180010fc4  jns     short loc_180010FE2
0x180010fc6  mov     rcx, [rbp+5Fh]; this
0x180010fca  mov     r9d, eax; char *
0x180010fcd  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180010fd4  lea     edx, [r15+16h]; void *
0x180010fd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010fdd  jmp     loc_1800112A3
0x180010fe2  mov     [rbp+57h+var_D0], r15
0x180010fe6  mov     rcx, [rbp+57h+var_88]
0x180010fea  mov     rax, [rcx]
0x180010fed  mov     [rbp+57h+var_D0], r15
0x180010ff1  lea     rdx, [rbp+57h+var_D0]
0x180010ff5  mov     rax, [rax+30h]
0x180010ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ffe  mov     ebx, eax
0x180011000  test    eax, eax
0x180011002  jns     short loc_180011021
0x180011004  mov     rcx, [rbp+5Fh]; this
0x180011008  mov     r9d, eax; char *
0x18001100b  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180011012  mov     edx, 18h; void *
0x180011017  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001101c  jmp     loc_180011299
0x180011021  mov     rax, [rbp+57h+var_D0]
0x180011025  mov     [rbp+57h+var_80], rax
0x180011029  mov     [rbp+57h+var_A0], rax
0x18001102d  mov     [rbp+57h+var_98], r15d
0x180011031  mov     [rbp+57h+var_90], r15
0x180011035  lea     rdx, [rbp+57h+var_78]
0x180011039  lea     rcx, [rbp+57h+var_80]
0x18001103d  call    ?end@?$vector_range@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_exception_policy>::end(void)
0x180011042  nop
0x180011043  mov     eax, [rbp+57h+var_98]
0x180011046  cmp     eax, [rbp+57h+var_70]
0x180011049  jz      loc_1800112C5
0x18001104f  mov     rdi, [rbp+57h+var_A0]
0x180011053  mov     rax, [rdi]
0x180011056  mov     rbx, [rax+30h]
0x18001105a  lea     rcx, [rbp+57h+var_90]
0x18001105e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011063  lea     r8, [rbp+57h+var_90]
0x180011067  mov     edx, [rbp+57h+var_98]
0x18001106a  mov     rcx, rdi
0x18001106d  mov     rax, rbx
0x180011070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011075  mov     rcx, [rbp+5Fh]; this
0x180011079  test    eax, eax
0x18001107b  js      loc_1800112B0
0x180011081  mov     [rbp+57h+var_C8], r15
0x180011085  mov     rcx, [rbp+57h+var_90]
0x180011089  mov     rax, [rcx]
0x18001108c  mov     [rbp+57h+var_C8], r15
0x180011090  lea     rdx, [rbp+57h+var_C8]
0x180011094  mov     rax, [rax+40h]
0x180011098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001109d  mov     ebx, eax
0x18001109f  test    eax, eax
0x1800110a1  js      loc_180011262
0x1800110a7  mov     rax, [rbp+57h+var_C8]
0x1800110ab  mov     [rbp+57h+var_60], rax
0x1800110af  mov     [rbp+57h+var_B8], rax
0x1800110b3  mov     [rbp+57h+var_B0], r15d
0x1800110b7  mov     [rbp+57h+var_A8], r15
0x1800110bb  lea     rdx, [rbp+57h+hstringHeader]
0x1800110bf  lea     rcx, [rbp+57h+var_60]
0x1800110c3  call    ?end@?$vector_range@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_exception_policy>::end(void)
0x1800110c8  nop
0x1800110c9  mov     eax, [rbp+57h+var_B0]
0x1800110cc  cmp     eax, dword ptr [rbp+57h+hstringHeader.Reserved+8]
0x1800110cf  jz      loc_180011171
0x1800110d5  mov     rdi, [rbp+57h+var_B8]
0x1800110d9  mov     rax, [rdi]
0x1800110dc  mov     rbx, [rax+30h]
0x1800110e0  lea     rcx, [rbp+57h+var_A8]
0x1800110e4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800110e9  lea     r8, [rbp+57h+var_A8]
0x1800110ed  mov     edx, [rbp+57h+var_B0]
0x1800110f0  mov     rcx, rdi
0x1800110f3  mov     rax, rbx
0x1800110f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110fb  mov     rcx, [rbp+5Fh]; this
0x1800110ff  test    eax, eax
0x180011101  js      loc_18001124D
0x180011107  mov     [rbp+57h+var_C0], r15
0x18001110b  mov     rcx, [rbp+57h+var_A8]
0x18001110f  mov     rax, [rcx]
0x180011112  mov     [rbp+57h+var_C0], r15
0x180011116  lea     r8, [rbp+57h+var_C0]
0x18001111a  lea     rdx, _GUID_4d008e5e_e2d5_5e99_bae7_e66d5f3a87c8
0x180011121  mov     rax, [rax]
0x180011124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011129  mov     ebx, eax
0x18001112b  test    eax, eax
0x18001112d  js      loc_180011243
0x180011133  mov     [rbp+57h+var_80], r15
0x180011137  mov     rcx, [rbp+57h+var_C0]
0x18001113b  mov     rax, [rcx]
0x18001113e  lea     rdx, [rbp+57h+var_80]
0x180011142  mov     rax, [rax+30h]
0x180011146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001114b  mov     ebx, eax
0x18001114d  test    eax, eax
0x18001114f  js      loc_180011239
0x180011155  cmp     [rbp+57h+var_80], r14
0x180011159  jz      short loc_18001119B
0x18001115b  lea     rcx, [rbp+57h+var_C0]
0x18001115f  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180011164  mov     eax, [rbp+57h+var_B0]
0x180011167  inc     eax
0x180011169  mov     [rbp+57h+var_B0], eax
0x18001116c  jmp     loc_1800110CC
0x180011171  lea     rcx, [rbp+57h+hstringHeader.Reserved+10h]
0x180011175  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001117a  nop
0x18001117b  lea     rcx, [rbp+57h+var_A8]
0x18001117f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011184  nop
0x180011185  lea     rcx, [rbp+57h+var_C8]
0x180011189  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001118e  mov     eax, [rbp+57h+var_98]
0x180011191  inc     eax
0x180011193  mov     [rbp+57h+var_98], eax
0x180011196  jmp     loc_180011046
0x18001119b  mov     rcx, [rbp+57h+var_A8]
0x18001119f  mov     rax, [rcx]
0x1800111a2  mov     rdx, rsi
0x1800111a5  mov     rax, [rax+30h]
0x1800111a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111ae  mov     ebx, eax
0x1800111b0  test    eax, eax
0x1800111b2  jns     short loc_1800111EF
0x1800111b4  mov     edx, 26h ; '&'; void *
0x1800111b9  mov     rcx, [rbp+5Fh]; this
0x1800111bd  mov     r9d, eax; char *
0x1800111c0  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x1800111c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800111cc  nop
0x1800111cd  lea     rcx, [rbp+57h+var_C0]
0x1800111d1  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x1800111d6  nop
0x1800111d7  lea     rcx, [rbp+57h+hstringHeader.Reserved+10h]
0x1800111db  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800111e0  nop
0x1800111e1  lea     rcx, [rbp+57h+var_A8]
0x1800111e5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800111ea  jmp     loc_18001127B
0x1800111ef  lea     rcx, [rbp+57h+var_C0]
0x1800111f3  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x1800111f8  nop
0x1800111f9  lea     rcx, [rbp+57h+hstringHeader.Reserved+10h]
0x1800111fd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011202  nop
0x180011203  lea     rcx, [rbp+57h+var_A8]
0x180011207  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001120c  nop
0x18001120d  lea     rcx, [rbp+57h+var_C8]
0x180011211  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180011216  nop
0x180011217  lea     rcx, [rbp+57h+var_68]
0x18001121b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011220  nop
0x180011221  lea     rcx, [rbp+57h+var_90]
0x180011225  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001122a  nop
0x18001122b  lea     rcx, [rbp+57h+var_D0]
0x18001122f  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180011234  mov     ebx, r15d
0x180011237  jmp     short loc_1800112A3
0x180011239  mov     edx, 22h ; '"'
0x18001123e  jmp     loc_1800111B9
0x180011243  mov     edx, 20h ; ' '
0x180011248  jmp     loc_1800111B9
0x18001124d  mov     r9d, eax; char *
0x180011250  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011257  mov     edx, 1CBEh; void *
0x18001125c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180011262  mov     rcx, [rbp+5Fh]; this
0x180011266  mov     r9d, eax; char *
0x180011269  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180011270  mov     edx, 1Ch; void *
0x180011275  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001127a  nop
0x18001127b  lea     rcx, [rbp+57h+var_C8]
0x18001127f  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180011284  nop
0x180011285  lea     rcx, [rbp+57h+var_68]
0x180011289  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001128e  nop
0x18001128f  lea     rcx, [rbp+57h+var_90]
0x180011293  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011298  nop
0x180011299  lea     rcx, [rbp+57h+var_D0]
0x18001129d  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x1800112a2  nop
0x1800112a3  lea     rcx, [rbp+57h+var_88]
0x1800112a7  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x1800112ac  mov     eax, ebx
0x1800112ae  jmp     short loc_1800112F1
0x1800112b0  mov     r9d, eax; char *
0x1800112b3  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800112ba  mov     edx, 1CBEh; void *
0x1800112bf  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800112c5  lea     rcx, [rbp+57h+var_68]
0x1800112c9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800112ce  nop
0x1800112cf  lea     rcx, [rbp+57h+var_90]
0x1800112d3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800112d8  nop
0x1800112d9  lea     rcx, [rbp+57h+var_D0]
0x1800112dd  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x1800112e2  nop
0x1800112e3  lea     rcx, [rbp+57h+var_88]
0x1800112e7  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x1800112ec  mov     eax, 80070057h
0x1800112f1  mov     rcx, [rbp+57h+var_38]
0x1800112f5  xor     rcx, rsp; StackCookie
0x1800112f8  call    __security_check_cookie
0x1800112fd  add     rsp, 0C8h
0x180011304  pop     r15
0x180011306  pop     r14
0x180011308  pop     rdi
0x180011309  pop     rsi
0x18001130a  pop     rbx
0x18001130b  pop     rbp
0x18001130c  retn
```
