# StateRepoPackageInformation::LoadStateRepoPackageProperties(void)

- ea: `0x180057e54`
- end: `0x18005861f`
- name: `?LoadStateRepoPackageProperties@StateRepoPackageInformation@@AEAAXXZ`
- size: `1995`
- prototype: `void __fastcall(StateRepoPackageInformation *__hidden this)`
- caller_count: `5`
- callee_count: `26`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180057dd0`
- `0x180090b70`
- `0x180090c90`
- `0x180090ec0`
- `0x180091350`

## callees

- `0x180011328`
- `0x18002a380`
- `0x180031540`
- `0x1800379e0`
- `0x180047048`
- `0x180047068`
- `0x180049dc0`
- `0x18004d8ac`
- `0x18004d9f8`
- `0x18004db7c`
- `0x18004dd9c`
- `0x18004ddf4`
- `0x180054064`
- `0x180054420`
- `0x180055f48`
- `0x180056098`
- `0x180056208`
- `0x180057e54`
- `0x180058a4c`
- `0x18005ae90`
- `0x1800907f0`
- `0x180090908`
- `0x1800913e4`
- `0x180091ef4`
- `0x180091fc0`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058205`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058205`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180058248`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180058248`

## string_xrefs

- `0x18005860d`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180057f4f`: `FileSystemWriteVirtualization`
- `0x180057f91`: `RegistryWriteVirtualization`
- `0x180057f65`: `ExcludedDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
void __fastcall StateRepoPackageInformation::LoadStateRepoPackageProperties(StateRepoPackageInformation *this)
{
  int v2; // r15d
  __int64 v3; // rbx
  __int64 (__fastcall *v4)(__int64, _QWORD, __int64 *); // rdi
  _QWORD *v5; // rax
  __int64 v6; // rax
  int v7; // eax
  unsigned __int8 (__fastcall **v8)(StateRepoPackageInformation *); // rsi
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, _QWORD, __int64 *); // rbx
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  bool v14; // r13
  unsigned __int64 v15; // r12
  int i; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _QWORD, __int64 *); // rbx
  int v19; // eax
  __int64 v20; // rbx
  __int64 *v21; // rdi
  __int64 (__fastcall *v22)(__int64 *, __int64, char *); // rbx
  int v23; // eax
  __int64 *v24; // rdi
  __int64 (__fastcall *v25)(__int64 *, __int64, struct IInspectable **); // rbx
  int v26; // eax
  __int64 v27; // rax
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, HSTRING *); // r15
  HSTRING v30; // rbx
  int v31; // eax
  PCWSTR StringRawBuffer; // rax
  char *v33; // r8
  int v34; // ecx
  int v35; // edx
  int v36; // eax
  __int64 v37; // rax
  int v38; // eax
  int v39; // eax
  __int64 v40; // rax
  int v41; // eax
  char v42; // di
  struct IInspectable **v43; // rbx
  struct IInspectable **v44; // r15
  char v45; // cl
  _QWORD *v46; // rbx
  _QWORD *v47; // rdi
  int v48; // [rsp+20h] [rbp-E0h]
  char v49; // [rsp+30h] [rbp-D0h] BYREF
  char v50; // [rsp+31h] [rbp-CFh] BYREF
  _BYTE v51[2]; // [rsp+32h] [rbp-CEh] BYREF
  int v52; // [rsp+34h] [rbp-CCh]
  struct IInspectable *v53; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v54; // [rsp+40h] [rbp-C0h] BYREF
  int v55; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v57; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v58; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v59; // [rsp+68h] [rbp-98h] BYREF
  __int64 v60; // [rsp+70h] [rbp-90h] BYREF
  __int64 v61; // [rsp+78h] [rbp-88h]
  unsigned int v62; // [rsp+80h] [rbp-80h]
  __int64 v63; // [rsp+88h] [rbp-78h] BYREF
  __int64 v64; // [rsp+90h] [rbp-70h] BYREF
  __int64 v65; // [rsp+98h] [rbp-68h] BYREF
  _QWORD *v66; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v67; // [rsp+A8h] [rbp-58h]
  struct IInspectable **v68; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v69; // [rsp+B8h] [rbp-48h]
  _BYTE v70[8]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v71[8]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v72; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v73[12]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v74[8]; // [rsp+140h] [rbp+40h] BYREF
  int v75; // [rsp+148h] [rbp+48h]
  _BYTE v76[8]; // [rsp+150h] [rbp+50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+158h] [rbp+58h] BYREF
  __int64 v78; // [rsp+170h] [rbp+70h]
  _BYTE v79[24]; // [rsp+178h] [rbp+78h] BYREF
  __int64 v80; // [rsp+190h] [rbp+90h]
  _QWORD v81[42]; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+248h]

  v2 = 0;
  v52 = 0;
  if ( !*((_BYTE *)this + 156) )
  {
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v81);
    v81[0] = &DesktopAppXProvider::LoadStateRepoPackageProperties::`vftable';
    DesktopAppXProvider::LoadStateRepoPackageProperties::StartActivity((DesktopAppXProvider::LoadStateRepoPackageProperties *)v81);
    wil::GetActivationFactory<Windows::Internal::StateRepository::IPackageStatics>(&v65);
    v60 = 0;
    v3 = v65;
    v4 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v65 + 176LL);
    v60 = 0;
    v5 = (_QWORD *)((char *)this + 8);
    if ( *((_QWORD *)this + 4) > 7u )
      v5 = (_QWORD *)*v5;
    v59 = v5;
    v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v79, &v59);
    v7 = v4(v3, *(_QWORD *)(v6 + 24), &v60);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x180,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
        (const char *)(unsigned int)v7,
        v48);
    wil::GetActivationFactory<Windows::Internal::StateRepository::IPackagePropertyStatics>(&v64);
    v73[0] =  StateRepoPackageInformation::`vcall'{56,{flat}};
    v73[1] = (char *)this + 157;
    v73[2] = L"FileSystemWriteVirtualization";
    v73[3] = L"ExcludedDirectories";
    v73[4] = L"ExcludedDirectory";
    v73[5] = StateRepoPackageInformation::ParseAndAddExcludedDirectoryElementContent;
    v73[6] =  Windows::Foundation::IPropertyValueStatics::`vcall'{88,{flat}};
    v73[7] = (char *)this + 158;
    v73[8] = L"RegistryWriteVirtualization";
    v73[9] = L"ExcludedKeys";
    v73[10] = L"ExcludedKey";
    v73[11] = StateRepoPackageInformation::ParseAndAddExcludedKeyElementContent;
    v8 = (unsigned __int8 (__fastcall **)(StateRepoPackageInformation *))v73;
    do
    {
      if ( (*v8)(this) )
      {
        v58 = 0;
        v9 = v64;
        v10 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v64 + 144LL);
        v58 = 0;
        v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v79, v8 + 2);
        v12 = v10(v9, v60, *(_QWORD *)(v11 + 24), &v58);
        if ( v12 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1AA,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
            (const char *)(unsigned int)v12,
            v48);
        v55 = 0;
        v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v58 + 56LL))(v58, &v55);
        if ( v13 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1AD,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
            (const char *)(unsigned int)v13,
            v48);
        if ( v55 )
        {
          v14 = 0;
          v66 = 0;
          v15 = 0;
          v67 = 0;
          v54 = v58;
          v61 = v58;
          v62 = 0;
          v63 = 0;
          wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::PackageProperty *>,wil::err_exception_policy>::end(
            &v54,
            v74);
          for ( i = v62; i != v75; i = ++v62 )
          {
            v17 = v61;
            v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v61 + 48LL);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
            v19 = v18(v17, v62, &v63);
            if ( v19 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1CBE,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
                (const char *)(unsigned int)v19,
                v48);
            v20 = v63;
            v72 = v63;
            if ( v63 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 8LL))(v63);
            ReservedForLocalUse::GetMapFromPackageProperty(&v57, v20);
            v49 = 0;
            v21 = v57;
            v22 = *(__int64 (__fastcall **)(__int64 *, __int64, char *))(*v57 + 64);
            v78 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"#text", 6u, 5u);
            v23 = v22(v21, v78, &v49);
            if ( v23 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1D7,
                (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                (const char *)(unsigned int)v23,
                v48);
            if ( v49 )
            {
              v53 = 0;
              v24 = v57;
              v25 = *(__int64 (__fastcall **)(__int64 *, __int64, struct IInspectable **))(*v57 + 48);
              v53 = 0;
              v78 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"#text", 6u, 5u);
              v26 = v25(v24, v78, &v53);
              if ( v26 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1DC,
                  (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                  (const char *)(unsigned int)v26,
                  v48);
              string = 0;
              v27 = wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<Windows::Foundation::IPropertyValue>(
                      &v53,
                      v71);
              v28 = *(_QWORD *)v27;
              v29 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v27 + 152LL);
              v30 = string;
              if ( string )
              {
                wil::last_error_context::last_error_context((wil::last_error_context *)v70);
                WindowsDeleteString(v30);
                wil::last_error_context::~last_error_context((wil::last_error_context *)v70);
              }
              string = 0;
              v31 = v29(v28, &string);
              if ( v31 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1DF,
                  (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                  (const char *)(unsigned int)v31,
                  v48);
              wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>(v71);
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              v33 = (char *)((char *)L"disabled" - (char *)StringRawBuffer);
              do
              {
                v34 = *(unsigned __int16 *)&v33[(_QWORD)StringRawBuffer];
                v35 = *StringRawBuffer - v34;
                if ( v35 )
                  break;
                ++StringRawBuffer;
              }
              while ( v34 );
              v14 = v35 == 0;
              Windows::Internal::String::~String((Windows::Internal::String *)&string);
              wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>(&v53);
              v2 = v52;
            }
            else
            {
              Microsoft::WRL::Wrappers::HStringReference::HStringReference(v79, v8 + 3);
              v50 = 0;
              v36 = (*(__int64 (__fastcall **)(__int64 *, __int64, char *))(*v57 + 64))(v57, v80, &v50);
              if ( v36 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1EB,
                  (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                  (const char *)(unsigned int)v36,
                  v48);
              if ( v50 )
              {
                v54 = 0;
                v37 = *v57;
                v54 = 0;
                v38 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v37 + 48))(v57, v80, &v54);
                if ( v38 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x1FA,
                    (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                    (const char *)(unsigned int)v38,
                    v48);
                wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>(
                  &v59,
                  v54);
                Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v8 + 4);
                v51[0] = 0;
                v39 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _BYTE *))(*v59 + 64LL))(v59, v78, v51);
                if ( v39 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x205,
                    (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                    (const char *)(unsigned int)v39,
                    v48);
                if ( v51[0] )
                {
                  v53 = 0;
                  v40 = *v59;
                  v53 = 0;
                  v41 = (*(__int64 (__fastcall **)(_QWORD *, __int64, struct IInspectable **))(v40 + 48))(
                          v59,
                          v78,
                          &v53);
                  if ( v41 < 0 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x20B,
                      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
                      (const char *)(unsigned int)v41,
                      v48);
                  ReservedForLocalUse::GetPropertyRepresentingObjectsAsInspectableArray(
                    (ReservedForLocalUse *)&v68,
                    v53);
                  if ( v69 > v15 )
                  {
                    v42 = 1;
                    v43 = v68;
                    v44 = &v68[v69];
                    if ( v68 != v44 )
                    {
                      do
                      {
                        v45 = StateRepoPackageInformation::ShouldIgnoreExclusion(this, *v43) ? v42 : 0;
                        v42 = v45;
                        ++v43;
                      }
                      while ( v43 != v44 );
                      if ( !v45 )
                      {
                        wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::operator=(
                          &v66,
                          &v68);
                        v15 = v67;
                      }
                    }
                    v2 = v52;
                  }
                  wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::reset(&v68);
                  wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>(&v53);
                }
                v2 |= 1u;
                v52 = v2;
                v78 = 0;
                wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>(&v59);
                wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>(&v54);
              }
            }
            wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>(&v57);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v72);
          }
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v76);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
          v46 = v66;
          if ( v66 )
          {
            v47 = &v66[v15];
            while ( v46 != v47 )
              StateRepoPackageInformation::ParseAndAddWriteVirtualizationExcludedItemElement(this, *v46++, v8[5]);
          }
          else if ( v14 )
          {
            *(_BYTE *)v8[1] = 1;
          }
          wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::reset(&v66);
        }
        else
        {
          *(_BYTE *)v8[1] = 1;
        }
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>(&v58);
      }
      v8 += 6;
    }
    while ( v8 != (unsigned __int8 (__fastcall **)(StateRepoPackageInformation *))v74 );
    *((_BYTE *)this + 156) = 1;
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v81);
    wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>(&v64);
    wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>(&v60);
    wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>(&v65);
    DesktopAppXProvider::LoadStateRepoPackageProperties::~LoadStateRepoPackageProperties((DesktopAppXProvider::LoadStateRepoPackageProperties *)v81);
  }
}

```

## disassembly

```asm
0x180057e54  push    rbp
0x180057e56  push    rbx
0x180057e57  push    rsi
0x180057e58  push    rdi
0x180057e59  push    r12
0x180057e5b  push    r13
0x180057e5d  push    r14
0x180057e5f  push    r15
0x180057e61  lea     rbp, [rsp-208h]
0x180057e69  sub     rsp, 308h
0x180057e70  mov     rax, cs:__security_cookie
0x180057e77  xor     rax, rsp
0x180057e7a  mov     [rbp+240h+var_50], rax
0x180057e81  mov     r14, rcx
0x180057e84  xor     esi, esi
0x180057e86  mov     r15d, esi
0x180057e89  mov     [rsp+340h+var_30C], esi
0x180057e8d  cmp     [rcx+9Ch], sil
0x180057e94  jnz     loc_180058515
0x180057e9a  lea     rdx, aLoadstaterepop; "LoadStateRepoPackageProperties"
0x180057ea1  lea     rcx, [rbp+240h+var_1A0]; struct wil::details::IFailureCallback *
0x180057ea8  call    ??0?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180057ead  lea     rax, ??_7LoadStateRepoPackageProperties@DesktopAppXProvider@@6B@; const DesktopAppXProvider::LoadStateRepoPackageProperties::`vftable'
0x180057eb4  mov     [rbp+240h+var_1A0], rax
0x180057ebb  lea     rcx, [rbp+240h+var_1A0]; this
0x180057ec2  call    ?StartActivity@LoadStateRepoPackageProperties@DesktopAppXProvider@@QEAAXXZ; DesktopAppXProvider::LoadStateRepoPackageProperties::StartActivity(void)
0x180057ec7  nop
0x180057ec8  lea     rcx, [rbp+240h+var_2A8]
0x180057ecc  call    ??$GetActivationFactory@UIPackageStatics@StateRepository@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIPackageStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::StateRepository::IPackageStatics>(ushort const *)
0x180057ed1  nop
0x180057ed2  mov     [rsp+340h+var_2D0], rsi
0x180057ed7  mov     rbx, [rbp+240h+var_2A8]
0x180057edb  mov     rax, [rbx]
0x180057ede  mov     rdi, [rax+0B0h]
0x180057ee5  mov     [rsp+340h+var_2D0], rsi
0x180057eea  lea     rax, [r14+8]
0x180057eee  cmp     qword ptr [rax+18h], 7
0x180057ef3  jbe     short loc_180057EF8
0x180057ef5  mov     rax, [rax]
0x180057ef8  mov     [rsp+340h+var_2D8], rax
0x180057efd  lea     rdx, [rsp+340h+var_2D8]
0x180057f02  lea     rcx, [rbp+240h+var_1C8]
0x180057f06  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180057f0b  nop
0x180057f0c  lea     r8, [rsp+340h+var_2D0]
0x180057f11  mov     rdx, [rax+18h]
0x180057f15  mov     rcx, rbx
0x180057f18  mov     rax, rdi
0x180057f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057f20  mov     rcx, [rbp+248h]; this
0x180057f27  test    eax, eax
0x180057f29  js      loc_180058562
0x180057f2f  lea     rcx, [rbp+240h+var_2B0]
0x180057f33  call    ??$GetActivationFactory@UIPackagePropertyStatics@StateRepository@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIPackagePropertyStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::StateRepository::IPackagePropertyStatics>(ushort const *)
0x180057f38  nop
0x180057f39  lea     rax, ??_9StateRepoPackageInformation@@$BDI@AA; [thunk]: StateRepoPackageInformation::`vcall'{56,{flat}}
0x180057f40  mov     [rbp+240h+var_260], rax
0x180057f44  lea     rax, [r14+9Dh]
0x180057f4b  mov     [rbp+240h+var_258], rax
0x180057f4f  lea     rax, aFilesystemwrit; "FileSystemWriteVirtualization"
0x180057f56  mov     [rbp+240h+var_250], rax
0x180057f5a  lea     rax, aExcludeddirect_0; "ExcludedDirectories"
0x180057f61  mov     [rbp+240h+var_248], rax
0x180057f65  lea     rax, aExcludeddirect; "ExcludedDirectory"
0x180057f6c  mov     [rbp+240h+var_240], rax
0x180057f70  lea     rax, ?ParseAndAddExcludedDirectoryElementContent@StateRepoPackageInformation@@AEAAXPEBG@Z; StateRepoPackageInformation::ParseAndAddExcludedDirectoryElementContent(ushort const *)
0x180057f77  mov     [rbp+240h+var_238], rax
0x180057f7b  lea     rax, ??_9IPropertyValueStatics@Foundation@Windows@@$BFI@AA; [thunk]: Windows::Foundation::IPropertyValueStatics::`vcall'{88,{flat}}
0x180057f82  mov     [rbp+240h+var_230], rax
0x180057f86  lea     rax, [r14+9Eh]
0x180057f8d  mov     [rbp+240h+var_228], rax
0x180057f91  lea     rax, aRegistrywritev; "RegistryWriteVirtualization"
0x180057f98  mov     [rbp+240h+var_220], rax
0x180057f9c  lea     rax, aExcludedkeys; "ExcludedKeys"
0x180057fa3  mov     [rbp+240h+var_218], rax
0x180057fa7  lea     rax, aExcludedkey; "ExcludedKey"
0x180057fae  mov     [rbp+240h+var_210], rax
0x180057fb2  lea     rax, ?ParseAndAddExcludedKeyElementContent@StateRepoPackageInformation@@AEAAXPEBG@Z; StateRepoPackageInformation::ParseAndAddExcludedKeyElementContent(ushort const *)
0x180057fb9  mov     [rbp+240h+var_208], rax
0x180057fbd  lea     rsi, [rbp+240h+var_260]
0x180057fc1  mov     rcx, r14
0x180057fc4  mov     rax, [rsi]
0x180057fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057fcc  test    al, al
0x180057fce  jz      loc_1800584C4
0x180057fd4  mov     [rsp+340h+var_2E0], 0
0x180057fdd  mov     rdi, [rbp+240h+var_2B0]
0x180057fe1  mov     rax, [rdi]
0x180057fe4  mov     rbx, [rax+90h]
0x180057feb  mov     [rsp+340h+var_2E0], 0
0x180057ff4  lea     rdx, [rsi+10h]
0x180057ff8  lea     rcx, [rbp+240h+var_1C8]
0x180057ffc  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180058001  nop
0x180058002  lea     r9, [rsp+340h+var_2E0]
0x180058007  mov     r8, [rax+18h]
0x18005800b  mov     rdx, [rsp+340h+var_2D0]
0x180058010  mov     rcx, rdi
0x180058013  mov     rax, rbx
0x180058016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005801b  mov     rcx, [rbp+248h]; this
0x180058022  test    eax, eax
0x180058024  js      loc_18005854D
0x18005802a  mov     [rsp+340h+var_2F8], 0
0x180058032  mov     rcx, [rsp+340h+var_2E0]
0x180058037  mov     rax, [rcx]
0x18005803a  lea     rdx, [rsp+340h+var_2F8]
0x18005803f  mov     rax, [rax+38h]
0x180058043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058048  mov     rcx, [rbp+248h]; this
0x18005804f  test    eax, eax
0x180058051  js      loc_180058538
0x180058057  cmp     [rsp+340h+var_2F8], 0
0x18005805c  jnz     short loc_18005806A
0x18005805e  mov     rax, [rsi+8]
0x180058062  mov     byte ptr [rax], 1
0x180058065  jmp     loc_1800584BA
0x18005806a  xor     r13b, r13b
0x18005806d  mov     [rbp+240h+var_2A0], 0
0x180058075  xor     r12d, r12d
0x180058078  mov     [rbp+240h+var_298], r12
0x18005807c  mov     rax, [rsp+340h+var_2E0]
0x180058081  mov     [rsp+340h+var_300], rax
0x180058086  mov     [rsp+340h+var_2C8], rax
0x18005808b  mov     [rbp+240h+var_2C0], r12d
0x18005808f  mov     [rbp+240h+var_2B8], r12
0x180058093  lea     rdx, [rbp+240h+var_200]
0x180058097  lea     rcx, [rsp+340h+var_300]
0x18005809c  call    ?end@?$vector_range@U?$IVectorView@PEAVPackageProperty@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::PackageProperty *>,wil::err_exception_policy>::end(void)
0x1800580a1  nop
0x1800580a2  mov     eax, [rbp+240h+var_2C0]
0x1800580a5  cmp     eax, [rbp+240h+var_1F8]
0x1800580a8  jz      loc_180058468
0x1800580ae  mov     rdi, [rsp+340h+var_2C8]
0x1800580b3  mov     rax, [rdi]
0x1800580b6  mov     rbx, [rax+30h]
0x1800580ba  lea     rcx, [rbp+240h+var_2B8]
0x1800580be  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800580c3  lea     r8, [rbp+240h+var_2B8]
0x1800580c7  mov     edx, [rbp+240h+var_2C0]
0x1800580ca  mov     rcx, rdi
0x1800580cd  mov     rax, rbx
0x1800580d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800580d5  mov     rcx, [rbp+248h]; this
0x1800580dc  test    eax, eax
0x1800580de  js      loc_18005860A
0x1800580e4  mov     rbx, [rbp+240h+var_2B8]
0x1800580e8  mov     [rbp+240h+var_270], rbx
0x1800580ec  test    rbx, rbx
0x1800580ef  jz      short loc_180058101
0x1800580f1  mov     rax, [rbx]
0x1800580f4  mov     rcx, rbx
0x1800580f7  mov     rax, [rax+8]
0x1800580fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058100  nop
0x180058101  mov     rdx, rbx
0x180058104  lea     rcx, [rsp+340h+var_2E8]
0x180058109  call    ?GetMapFromPackageProperty@ReservedForLocalUse@@YA?AV?$com_ptr_t@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@PEAUIPackageProperty@StateRepository@Internal@Windows@@@Z; ReservedForLocalUse::GetMapFromPackageProperty(Windows::Internal::StateRepository::IPackageProperty *)
0x18005810e  nop
0x18005810f  mov     [rsp+340h+var_310], 0
0x180058114  mov     rdi, [rsp+340h+var_2E8]
0x180058119  mov     rax, [rdi]
0x18005811c  mov     rbx, [rax+40h]
0x180058120  mov     [rbp+240h+var_1D0], 0
0x180058128  mov     r9d, 5; unsigned int
0x18005812e  lea     r8d, [r9+1]; unsigned int
0x180058132  lea     rdx, aText; "#text"
0x180058139  lea     rcx, [rbp+240h+hstringHeader]; hstringHeader
0x18005813d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180058142  nop
0x180058143  lea     r8, [rsp+340h+var_310]
0x180058148  mov     rdx, [rbp+240h+var_1D0]
0x18005814c  mov     rcx, rdi
0x18005814f  mov     rax, rbx
0x180058152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058157  mov     rcx, [rbp+248h]; this
0x18005815e  test    eax, eax
0x180058160  js      loc_1800585F5
0x180058166  cmp     [rsp+340h+var_310], 0
0x18005816b  jz      loc_180058291
0x180058171  mov     [rsp+340h+var_308], 0
0x18005817a  mov     rdi, [rsp+340h+var_2E8]
0x18005817f  mov     rax, [rdi]
0x180058182  mov     rbx, [rax+30h]
0x180058186  xor     r13d, r13d
0x180058189  mov     [rsp+340h+var_308], r13
0x18005818e  mov     [rbp+240h+var_1D0], r13
0x180058192  lea     r9d, [r13+5]; unsigned int
0x180058196  lea     r8d, [r13+6]; unsigned int
0x18005819a  lea     rdx, aText; "#text"
0x1800581a1  lea     rcx, [rbp+240h+hstringHeader]; hstringHeader
0x1800581a5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800581aa  nop
0x1800581ab  lea     r8, [rsp+340h+var_308]
0x1800581b0  mov     rdx, [rbp+240h+var_1D0]
0x1800581b4  mov     rcx, rdi
0x1800581b7  mov     rax, rbx
0x1800581ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800581bf  mov     rcx, [rbp+248h]; this
0x1800581c6  test    eax, eax
0x1800581c8  js      loc_18005858C
0x1800581ce  mov     [rsp+340h+string], r13
0x1800581d3  lea     rdx, [rbp+240h+var_278]
0x1800581d7  lea     rcx, [rsp+340h+var_308]
0x1800581dc  call    ??$query@UIPropertyValue@Foundation@Windows@@@?$com_ptr_t@UIInspectable@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIPropertyValue@Foundation@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<Windows::Foundation::IPropertyValue>(void)
0x1800581e1  nop
0x1800581e2  mov     rdi, [rax]
0x1800581e5  mov     rax, [rdi]
0x1800581e8  mov     r15, [rax+98h]
0x1800581ef  mov     rbx, [rsp+340h+string]
0x1800581f4  test    rbx, rbx
0x1800581f7  jz      short loc_180058214
0x1800581f9  lea     rcx, [rbp+240h+var_280]; this
0x1800581fd  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180058202  mov     rcx, rbx; string
0x180058205  call    cs:__imp_WindowsDeleteString
0x18005820b  lea     rcx, [rbp+240h+var_280]; this
0x18005820f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180058214  mov     [rsp+340h+string], r13
0x180058219  lea     rdx, [rsp+340h+string]
0x18005821e  mov     rcx, rdi
0x180058221  mov     rax, r15
0x180058224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058229  mov     rcx, [rbp+248h]; this
0x180058230  test    eax, eax
0x180058232  js      loc_180058577
0x180058238  lea     rcx, [rbp+240h+var_278]
0x18005823c  call    ??1?$com_ptr_t@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>(void)
0x180058241  xor     edx, edx; length
0x180058243  mov     rcx, [rsp+340h+string]; string
0x180058248  call    cs:__imp_WindowsGetStringRawBuffer
0x18005824e  lea     r8, aDisabled; "disabled"
0x180058255  sub     r8, rax
0x180058258  movzx   edx, word ptr [rax]
0x18005825b  movzx   ecx, word ptr [rax+r8]
0x180058260  sub     edx, ecx
0x180058262  jnz     short loc_18005826C
0x180058264  add     rax, 2
0x180058268  test    ecx, ecx
0x18005826a  jnz     short loc_180058258
0x18005826c  test    edx, edx
0x18005826e  setz    r13b
0x180058272  lea     rcx, [rsp+340h+string]; this
0x180058277  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18005827c  nop
0x18005827d  lea     rcx, [rsp+340h+var_308]
0x180058282  call    ??1?$com_ptr_t@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>(void)
0x180058287  mov     r15d, [rsp+340h+var_30C]
0x18005828c  jmp     loc_180058447
0x180058291  lea     rdx, [rsi+18h]
0x180058295  lea     rcx, [rbp+240h+var_1C8]
0x180058299  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18005829e  nop
0x18005829f  mov     [rsp+340h+var_30F], 0
0x1800582a4  mov     rcx, [rsp+340h+var_2E8]
0x1800582a9  mov     rax, [rcx]
0x1800582ac  lea     r8, [rsp+340h+var_30F]
0x1800582b1  mov     rdx, [rbp+240h+var_1B0]
0x1800582b8  mov     rax, [rax+40h]
0x1800582bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800582c1  mov     rcx, [rbp+248h]; this
0x1800582c8  test    eax, eax
0x1800582ca  js      loc_1800585E0
0x1800582d0  cmp     [rsp+340h+var_30F], 0
0x1800582d5  jz      loc_180058447
0x1800582db  mov     [rsp+340h+var_300], 0
0x1800582e4  mov     rcx, [rsp+340h+var_2E8]
0x1800582e9  mov     rax, [rcx]
0x1800582ec  mov     [rsp+340h+var_300], 0
0x1800582f5  lea     r8, [rsp+340h+var_300]
0x1800582fa  mov     rdx, [rbp+240h+var_1B0]
0x180058301  mov     rax, [rax+30h]
0x180058305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005830a  mov     rcx, [rbp+248h]; this
0x180058311  test    eax, eax
0x180058313  js      loc_1800585CB
0x180058319  mov     rdx, [rsp+340h+var_300]
0x18005831e  lea     rcx, [rsp+340h+var_2D8]
0x180058323  call    ??$?0UIInspectable@@@?$com_ptr_t@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIInspectable@@U?$integral_constant@D$0A@@wistd@@@Z; wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,wil::err_exception_policy>(IInspectable *,wistd::integral_constant<char,0>)
0x180058328  nop
0x180058329  lea     rdx, [rsi+20h]
0x18005832d  lea     rcx, [rbp+240h+hstringHeader]
0x180058331  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180058336  nop
0x180058337  mov     [rsp+340h+var_30E], 0
0x18005833c  mov     rcx, [rsp+340h+var_2D8]
0x180058341  mov     rax, [rcx]
0x180058344  lea     r8, [rsp+340h+var_30E]
0x180058349  mov     rdx, [rbp+240h+var_1D0]
0x18005834d  mov     rax, [rax+40h]
0x180058351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058356  mov     rcx, [rbp+248h]; this
0x18005835d  test    eax, eax
0x18005835f  js      loc_1800585B6
0x180058365  cmp     [rsp+340h+var_30E], 0
0x18005836a  jz      loc_180058420
0x180058370  mov     [rsp+340h+var_308], 0
0x180058379  mov     rcx, [rsp+340h+var_2D8]
0x18005837e  mov     rax, [rcx]
0x180058381  mov     [rsp+340h+var_308], 0
  ... truncated ...
```
