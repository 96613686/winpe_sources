# ViewActivator::ReadProperties(Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer> &,bool *,bool *)

- ea: `0x180020a68`
- end: `0x1800210b5`
- name: `?ReadProperties@ViewActivator@@SAXAEAV?$ComPtr@UIBuffer@Streams@Storage@Windows@@@WRL@Microsoft@@PEA_N1@Z`
- size: `1613`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180020060`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x180020a68`
- `0x180056208`
- `0x18005ae90`
- `0x18005d2ad`
- `0x1800770bc`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020ad8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020c44`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020e6d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020ad8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020c44`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020e6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180020ac2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180020c2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180020e57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180020ac2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180020c2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180020e57`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180020b00`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180020b00`
- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x180020b95`
- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x180020b95`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
void __fastcall ViewActivator::ReadProperties(_QWORD *a1, bool *a2, bool *a3, const char *a4)
{
  HRESULT v7; // eax
  HSTRING v8; // rbx
  int v9; // ebx
  int v10; // eax
  int v11; // eax
  __int64 (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rbx
  HRESULT v13; // eax
  HSTRING v14; // r14
  int v15; // edi
  int v16; // esi
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rsi
  int (__fastcall *v20)(__int64, HSTRING, _QWORD); // rdi
  __int64 (__fastcall ***v21)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v22; // rcx
  int v23; // eax
  __int64 (__fastcall ***v24)(_QWORD, _QWORD, _QWORD); // rcx
  int v25; // eax
  char v26; // al
  HRESULT v27; // eax
  HSTRING v28; // rsi
  int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rdi
  int (__fastcall *v32)(__int64, HSTRING, _QWORD); // rbx
  __int64 (__fastcall ***v33)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v34; // rcx
  int v35; // eax
  __int64 (__fastcall ***v36)(_QWORD, GUID *, _QWORD *); // rcx
  int v37; // eax
  char v38; // al
  __int64 v39; // rcx
  __int64 (__fastcall ***v40)(_QWORD, GUID *, _QWORD *); // rcx
  int v41; // [rsp+20h] [rbp-98h] BYREF
  __int64 (__fastcall ***v42)(_QWORD, GUID *, __int64 *); // [rsp+28h] [rbp-90h] BYREF
  __int64 v43; // [rsp+30h] [rbp-88h] BYREF
  __int64 (__fastcall ***v44)(_QWORD, GUID *, _QWORD *); // [rsp+38h] [rbp-80h] BYREF
  __int64 (__fastcall ***v45)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-78h] BYREF
  __int64 v46; // [rsp+48h] [rbp-70h] BYREF
  __int64 (__fastcall ***v47)(_QWORD, GUID *, _QWORD *); // [rsp+50h] [rbp-68h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-60h] BYREF
  HSTRING string; // [rsp+70h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  try
  {
    *a2 = 0;
    *a3 = 0;
    if ( !*a1 )
      return;
    v45 = 0;
    string = 0;
    v7 = WindowsCreateStringReference(L"Windows.Foundation.Collections.PropertySet", 0x2Au, &hstringHeader, &string);
    if ( v7 < 0 )
      RaiseException(v7, 1u, 0, 0);
    v8 = string;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
    v45 = 0;
    v42 = 0;
    v9 = RoActivateInstance(v8, &v42);
    if ( v9 >= 0 )
    {
      if ( !memcmp_0(&GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
      {
        v45 = v42;
      }
      else
      {
        v9 = (**v42)(v42, &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, (__int64 *)&v45);
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v42)[2])(v42);
      }
    }
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x363,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
        (const char *)(unsigned int)v9,
        v41);
    v46 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
    v10 = RoCreatePropertySetSerializer(&v46);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x366,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
        (const char *)(unsigned int)v10,
        v41);
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v46 + 56LL))(v46, v45, *a1);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x368,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
        (const char *)(unsigned int)v11,
        v41);
    v12 = v45;
    v47 = v45;
    if ( v45 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v45)[1])(v45);
    string = 0;
    v13 = WindowsCreateStringReference(L"IsBackgroundLifecycleApp", 0x18u, &hstringHeader, &string);
    if ( v13 < 0 )
      RaiseException(v13, 1u, 0, 0);
    v14 = string;
    LOBYTE(v41) = 0;
    v42 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
    v43 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
    if ( v12 )
    {
      v17 = (**v12)(v12, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v43);
      v16 = v17;
      if ( v17 >= 0 )
      {
        v44 = 0;
        v19 = v43;
        v20 = *(int (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v43 + 48LL);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
        if ( v20(v19, v14, &v44) >= 0 )
        {
          v23 = (**v44)(v44, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v42);
          if ( v23 >= 0 )
          {
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
            v15 = -2147467261;
            goto LABEL_40;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x25,
            (unsigned int)"onecore\\internal\\shell\\inc\\propertysethelpers.h",
            (const char *)(unsigned int)v23,
            v41);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
        }
        else
        {
          v21 = v44;
          if ( v44 )
          {
            v44 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v21)[2])(v21);
          }
          v22 = v43;
          if ( v43 )
          {
            v43 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          }
        }
        v15 = -2147467261;
LABEL_36:
        v24 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v42;
        if ( v42 )
        {
          v42 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v24)[2])(v24);
        }
        goto LABEL_42;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B,
        (unsigned int)"onecore\\internal\\shell\\inc\\propertysethelpers.h",
        (const char *)(unsigned int)v17,
        v41);
      v15 = -2147467261;
    }
    else
    {
      v15 = -2147467261;
      v16 = -2147467261;
    }
    v18 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    if ( v16 < 0 )
      goto LABEL_36;
LABEL_40:
    v25 =  Windows::Foundation::IPropertyValueStatics::`vcall'{144,{flat}}(v42, &v41);
    if ( v25 >= 0 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
      v26 = v41;
LABEL_44:
      *a2 = v26 != 0;
      string = 0;
      v27 = WindowsCreateStringReference(L"IsRoot", 6u, &hstringHeader, &string);
      if ( v27 < 0 )
        RaiseException(v27, 1u, 0, 0);
      v28 = string;
      LOBYTE(v41) = 0;
      v44 = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
      v43 = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
      if ( v12 )
      {
        v29 = (**v12)(v12, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v43);
        v15 = v29;
        if ( v29 >= 0 )
        {
          v42 = 0;
          v31 = v43;
          v32 = *(int (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v43 + 48LL);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
          if ( v32(v31, v28, &v42) < 0 )
          {
            v33 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v42;
            if ( v42 )
            {
              v42 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v33)[2])(v33);
            }
            v34 = v43;
            if ( v43 )
            {
              v43 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
            }
            goto LABEL_61;
          }
          v35 = (**v42)(v42, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, (__int64 *)&v44);
          if ( v35 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x25,
              (unsigned int)"onecore\\internal\\shell\\inc\\propertysethelpers.h",
              (const char *)(unsigned int)v35,
              v41);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
LABEL_61:
            v36 = v44;
            if ( v44 )
            {
              v44 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v36)[2])(v36);
            }
            goto LABEL_67;
          }
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
LABEL_65:
          v37 =  Windows::Foundation::IPropertyValueStatics::`vcall'{144,{flat}}(v44, &v41);
          if ( v37 >= 0 )
          {
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
            v38 = v41;
            goto LABEL_69;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2F,
            (unsigned int)"onecore\\internal\\shell\\inc\\propertysethelpers.h",
            (const char *)(unsigned int)v37,
            v41);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
LABEL_67:
          v38 = 0;
LABEL_69:
          *a3 = v38 != 0;
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
          v39 = v46;
          if ( v46 )
          {
            v46 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
          }
          v40 = v45;
          if ( v45 )
          {
            v45 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v40)[2])(v40);
          }
          return;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B,
          (unsigned int)"onecore\\internal\\shell\\inc\\propertysethelpers.h",
          (const char *)(unsigned int)v29,
          v41);
      }
      v30 = v43;
      if ( v43 )
      {
        v43 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
      if ( v15 < 0 )
        goto LABEL_61;
      goto LABEL_65;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecore\\internal\\shell\\inc\\propertysethelpers.h",
      (const char *)(unsigned int)v25,
      v41);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
LABEL_42:
    v26 = 0;
    goto LABEL_44;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x375,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
      a4);
  }
}

```

## disassembly

```asm
0x180020a68  mov     r11, rsp
0x180020a6b  push    rbx
0x180020a6c  push    rsi
0x180020a6d  push    rdi
0x180020a6e  push    r12
0x180020a70  push    r13
0x180020a72  push    r14
0x180020a74  push    r15
0x180020a76  sub     rsp, 80h
0x180020a7d  mov     rax, cs:__security_cookie
0x180020a84  xor     rax, rsp
0x180020a87  mov     [rsp+0B8h+var_40], rax
0x180020a8c  mov     r12, r8
0x180020a8f  mov     r15, rdx
0x180020a92  mov     rdi, rcx
0x180020a95  xor     r13d, r13d
0x180020a98  mov     [rdx], r13b
0x180020a9b  mov     [r8], r13b
0x180020a9e  cmp     [rcx], r13
0x180020aa1  jz      loc_180021093
0x180020aa7  mov     [r11-78h], r13
0x180020aab  mov     [r11-48h], r13
0x180020aaf  lea     r9, [r11-48h]; string
0x180020ab3  lea     r8, [r11-60h]; hstringHeader
0x180020ab7  lea     edx, [r13+2Ah]; length
0x180020abb  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_PropertySet@@3QBGB; "Windows.Foundation.Collections.Property"...
0x180020ac2  call    cs:__imp_WindowsCreateStringReference
0x180020ac8  test    eax, eax
0x180020aca  jns     short loc_180020ADF
0x180020acc  xor     r9d, r9d; lpArguments
0x180020acf  xor     r8d, r8d; nNumberOfArguments
0x180020ad2  lea     edx, [r13+1]; dwExceptionFlags
0x180020ad6  mov     ecx, eax; dwExceptionCode
0x180020ad8  call    cs:__imp_RaiseException
0x180020ade  nop
0x180020adf  mov     rbx, [rsp+0B8h+string]
0x180020ae4  lea     rcx, [rsp+0B8h+var_78]
0x180020ae9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180020aee  mov     [rsp+0B8h+var_78], r13
0x180020af3  mov     [rsp+0B8h+var_90], r13
0x180020af8  lea     rdx, [rsp+0B8h+var_90]
0x180020afd  mov     rcx, rbx
0x180020b00  call    cs:__imp_RoActivateInstance
0x180020b06  mov     ebx, eax
0x180020b08  test    eax, eax
0x180020b0a  js      short loc_180020B60
0x180020b0c  mov     r8d, 10h; Size
0x180020b12  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180020b19  lea     rcx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c; Buf1
0x180020b20  call    memcmp_0
0x180020b25  mov     rcx, [rsp+0B8h+var_90]
0x180020b2a  test    eax, eax
0x180020b2c  jnz     short loc_180020B35
0x180020b2e  mov     [rsp+0B8h+var_78], rcx
0x180020b33  jmp     short loc_180020B60
0x180020b35  mov     rax, [rcx]
0x180020b38  lea     r8, [rsp+0B8h+var_78]
0x180020b3d  lea     rdx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c
0x180020b44  mov     rax, [rax]
0x180020b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b4c  mov     ebx, eax
0x180020b4e  mov     rcx, [rsp+0B8h+var_90]
0x180020b53  mov     rax, [rcx]
0x180020b56  mov     rax, [rax+10h]
0x180020b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b5f  nop
0x180020b60  mov     rcx, [rsp+0B8h]; this
0x180020b68  test    ebx, ebx
0x180020b6a  jns     short loc_180020B81
0x180020b6c  mov     r9d, ebx; char *
0x180020b6f  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180020b76  mov     edx, 363h; void *
0x180020b7b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180020b81  mov     [rsp+0B8h+var_70], r13
0x180020b86  lea     rcx, [rsp+0B8h+var_70]
0x180020b8b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180020b90  lea     rcx, [rsp+0B8h+var_70]
0x180020b95  call    cs:__imp_RoCreatePropertySetSerializer
0x180020b9b  mov     rcx, [rsp+0B8h]; this
0x180020ba3  test    eax, eax
0x180020ba5  jns     short loc_180020BBB
0x180020ba7  mov     r9d, eax; char *
0x180020baa  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180020bb1  mov     edx, 366h; void *
0x180020bb6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180020bbb  mov     rcx, [rsp+0B8h+var_70]
0x180020bc0  mov     rax, [rcx]
0x180020bc3  mov     r8, [rdi]
0x180020bc6  mov     rdx, [rsp+0B8h+var_78]
0x180020bcb  mov     rax, [rax+38h]
0x180020bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bd4  mov     rcx, [rsp+0B8h]; this
0x180020bdc  test    eax, eax
0x180020bde  jns     short loc_180020BF4
0x180020be0  mov     r9d, eax; char *
0x180020be3  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180020bea  mov     edx, 368h; void *
0x180020bef  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180020bf4  mov     rbx, [rsp+0B8h+var_78]
0x180020bf9  mov     [rsp+0B8h+var_68], rbx
0x180020bfe  test    rbx, rbx
0x180020c01  jz      short loc_180020C13
0x180020c03  mov     rax, [rbx]
0x180020c06  mov     rcx, rbx
0x180020c09  mov     rax, [rax+8]
0x180020c0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c12  nop
0x180020c13  mov     [rsp+0B8h+string], r13
0x180020c18  lea     r9, [rsp+0B8h+string]; string
0x180020c1d  lea     r8, [rsp+0B8h+hstringHeader]; hstringHeader
0x180020c22  mov     edx, 18h; length
0x180020c27  lea     rcx, aIsbackgroundli; "IsBackgroundLifecycleApp"
0x180020c2e  call    cs:__imp_WindowsCreateStringReference
0x180020c34  test    eax, eax
0x180020c36  jns     short loc_180020C4B
0x180020c38  xor     r9d, r9d; lpArguments
0x180020c3b  xor     r8d, r8d; nNumberOfArguments
0x180020c3e  lea     edx, [r9+1]; dwExceptionFlags
0x180020c42  mov     ecx, eax; dwExceptionCode
0x180020c44  call    cs:__imp_RaiseException
0x180020c4a  nop
0x180020c4b  mov     r14, [rsp+0B8h+string]
0x180020c50  mov     byte ptr [rsp+0B8h+var_98], r13b; int
0x180020c55  mov     [rsp+0B8h+var_90], r13
0x180020c5a  lea     rcx, [rsp+0B8h+var_90]
0x180020c5f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180020c64  mov     [rsp+0B8h+var_88], r13
0x180020c69  lea     rcx, [rsp+0B8h+var_88]
0x180020c6e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180020c73  test    rbx, rbx
0x180020c76  jnz     short loc_180020C81
0x180020c78  mov     edi, 80004003h
0x180020c7d  mov     esi, edi
0x180020c7f  jmp     short loc_180020CC2
0x180020c81  mov     rax, [rbx]
0x180020c84  lea     r8, [rsp+0B8h+var_88]
0x180020c89  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180020c90  mov     rcx, rbx
0x180020c93  mov     rax, [rax]
0x180020c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c9b  mov     esi, eax
0x180020c9d  test    eax, eax
0x180020c9f  jns     short loc_180020CEB
0x180020ca1  mov     rcx, [rsp+0B8h]; this
0x180020ca9  mov     r9d, eax; char *
0x180020cac  lea     r8, aOnecoreInterna_7; "onecore\\internal\\shell\\inc\\property"...
0x180020cb3  mov     edx, 1Bh; void *
0x180020cb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020cbd  mov     edi, 80004003h
0x180020cc2  mov     rcx, [rsp+0B8h+var_88]
0x180020cc7  test    rcx, rcx
0x180020cca  jz      short loc_180020CDE
0x180020ccc  mov     [rsp+0B8h+var_88], r13
0x180020cd1  mov     rax, [rcx]
0x180020cd4  mov     rax, [rax+10h]
0x180020cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cdd  nop
0x180020cde  test    esi, esi
0x180020ce0  jns     loc_180020DE7
0x180020ce6  jmp     loc_180020DAF
0x180020ceb  mov     [rsp+0B8h+var_80], r13
0x180020cf0  mov     rsi, [rsp+0B8h+var_88]
0x180020cf5  mov     rax, [rsi]
0x180020cf8  mov     rdi, [rax+30h]
0x180020cfc  lea     rcx, [rsp+0B8h+var_80]
0x180020d01  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180020d06  lea     r8, [rsp+0B8h+var_80]
0x180020d0b  mov     rdx, r14
0x180020d0e  mov     rcx, rsi
0x180020d11  mov     rax, rdi
0x180020d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d19  test    eax, eax
0x180020d1b  jns     short loc_180020D57
0x180020d1d  mov     rcx, [rsp+0B8h+var_80]
0x180020d22  test    rcx, rcx
0x180020d25  jz      short loc_180020D39
0x180020d27  mov     [rsp+0B8h+var_80], r13
0x180020d2c  mov     rax, [rcx]
0x180020d2f  mov     rax, [rax+10h]
0x180020d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d38  nop
0x180020d39  mov     rcx, [rsp+0B8h+var_88]
0x180020d3e  test    rcx, rcx
0x180020d41  jz      short loc_180020D55
0x180020d43  mov     [rsp+0B8h+var_88], r13
0x180020d48  mov     rax, [rcx]
0x180020d4b  mov     rax, [rax+10h]
0x180020d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d54  nop
0x180020d55  jmp     short loc_180020DAA
0x180020d57  mov     rcx, [rsp+0B8h+var_80]
0x180020d5c  mov     rax, [rcx]
0x180020d5f  lea     r8, [rsp+0B8h+var_90]
0x180020d64  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180020d6b  mov     rax, [rax]
0x180020d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d73  nop
0x180020d74  test    eax, eax
0x180020d76  jns     short loc_180020DCD
0x180020d78  mov     rcx, [rsp+0B8h]; this
0x180020d80  mov     r9d, eax; char *
0x180020d83  lea     r8, aOnecoreInterna_7; "onecore\\internal\\shell\\inc\\property"...
0x180020d8a  mov     edx, 25h ; '%'; void *
0x180020d8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020d94  nop
0x180020d95  lea     rcx, [rsp+0B8h+var_80]
0x180020d9a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180020d9f  nop
0x180020da0  lea     rcx, [rsp+0B8h+var_88]
0x180020da5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180020daa  mov     edi, 80004003h
0x180020daf  mov     rcx, [rsp+0B8h+var_90]
0x180020db4  test    rcx, rcx
0x180020db7  jz      short loc_180020DCB
0x180020db9  mov     [rsp+0B8h+var_90], r13
0x180020dbe  mov     rax, [rcx]
0x180020dc1  mov     rax, [rax+10h]
0x180020dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020dca  nop
0x180020dcb  jmp     short loc_180020E21
0x180020dcd  lea     rcx, [rsp+0B8h+var_80]
0x180020dd2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180020dd7  nop
0x180020dd8  lea     rcx, [rsp+0B8h+var_88]
0x180020ddd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180020de2  mov     edi, 80004003h
0x180020de7  lea     rdx, [rsp+0B8h+var_98]
0x180020dec  mov     rcx, [rsp+0B8h+var_90]
0x180020df1  call    ??_9IPropertyValueStatics@Foundation@Windows@@$BJA@AA; [thunk]: Windows::Foundation::IPropertyValueStatics::`vcall'{144,{flat}}
0x180020df6  test    eax, eax
0x180020df8  jns     short loc_180020E26
0x180020dfa  mov     rcx, [rsp+0B8h]; this
0x180020e02  mov     r9d, eax; char *
0x180020e05  lea     r8, aOnecoreInterna_7; "onecore\\internal\\shell\\inc\\property"...
0x180020e0c  mov     edx, 2Fh ; '/'; void *
0x180020e11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020e16  nop
0x180020e17  lea     rcx, [rsp+0B8h+var_90]
0x180020e1c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180020e21  mov     al, r13b
0x180020e24  jmp     short loc_180020E34
0x180020e26  lea     rcx, [rsp+0B8h+var_90]
0x180020e2b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180020e30  mov     al, byte ptr [rsp+0B8h+var_98]
0x180020e34  test    al, al
0x180020e36  setnz   al
0x180020e39  mov     [r15], al
0x180020e3c  mov     [rsp+0B8h+string], r13
0x180020e41  lea     r9, [rsp+0B8h+string]; string
0x180020e46  lea     r8, [rsp+0B8h+hstringHeader]; hstringHeader
0x180020e4b  mov     edx, 6; length
0x180020e50  lea     rcx, aIsroot; "IsRoot"
0x180020e57  call    cs:__imp_WindowsCreateStringReference
0x180020e5d  test    eax, eax
0x180020e5f  jns     short loc_180020E74
0x180020e61  xor     r9d, r9d; lpArguments
0x180020e64  xor     r8d, r8d; nNumberOfArguments
0x180020e67  lea     edx, [r9+1]; dwExceptionFlags
0x180020e6b  mov     ecx, eax; dwExceptionCode
0x180020e6d  call    cs:__imp_RaiseException
0x180020e73  nop
0x180020e74  mov     rsi, [rsp+0B8h+string]
0x180020e79  mov     byte ptr [rsp+0B8h+var_98], r13b; int
0x180020e7e  mov     [rsp+0B8h+var_80], r13
0x180020e83  lea     rcx, [rsp+0B8h+var_80]
0x180020e88  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180020e8d  mov     [rsp+0B8h+var_88], r13
0x180020e92  lea     rcx, [rsp+0B8h+var_88]
0x180020e97  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180020e9c  test    rbx, rbx
0x180020e9f  jz      short loc_180020EDE
0x180020ea1  mov     rax, [rbx]
0x180020ea4  lea     r8, [rsp+0B8h+var_88]
0x180020ea9  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180020eb0  mov     rcx, rbx
0x180020eb3  mov     rax, [rax]
0x180020eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ebb  mov     edi, eax
0x180020ebd  test    eax, eax
0x180020ebf  jns     short loc_180020F07
0x180020ec1  mov     rcx, [rsp+0B8h]; this
0x180020ec9  mov     r9d, eax; char *
0x180020ecc  lea     r8, aOnecoreInterna_7; "onecore\\internal\\shell\\inc\\property"...
0x180020ed3  mov     edx, 1Bh; void *
0x180020ed8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020edd  nop
0x180020ede  mov     rcx, [rsp+0B8h+var_88]
0x180020ee3  test    rcx, rcx
0x180020ee6  jz      short loc_180020EFA
0x180020ee8  mov     [rsp+0B8h+var_88], r13
0x180020eed  mov     rax, [rcx]
0x180020ef0  mov     rax, [rax+10h]
0x180020ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ef9  nop
0x180020efa  test    edi, edi
0x180020efc  jns     loc_180020FFA
0x180020f02  jmp     loc_180020FC7
0x180020f07  mov     [rsp+0B8h+var_90], r13
0x180020f0c  mov     rdi, [rsp+0B8h+var_88]
0x180020f11  mov     rax, [rdi]
  ... truncated ...
```
