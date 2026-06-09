# SystemSettings::WorkAccess::CApplicationManagedByMDM::SetModernAppName(void)

- ea: `0x180034d08`
- end: `0x180035218`
- name: `?SetModernAppName@CApplicationManagedByMDM@WorkAccess@SystemSettings@@QEAAJXZ`
- size: `1296`
- prototype: `__int64 __fastcall(SystemSettings::WorkAccess::CApplicationManagedByMDM *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180030e8c`

## callees

- `0x180002a60`
- `0x1800076ac`
- `0x1800096ec`
- `0x18000eacc`
- `0x1800208f8`
- `0x180023164`
- `0x180023458`
- `0x180023ae0`
- `0x180027a58`
- `0x1800290b8`
- `0x1800291ec`
- `0x180029234`
- `0x180029e4c`
- `0x180029fb4`
- `0x18002a1c8`
- `0x18002a218`
- `0x18002eccc`
- `0x180034d08`
- `0x180035450`
- `0x1800391a4`
- `0x180039a78`
- `0x18003a944`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180035138`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180035138`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003510d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003510d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180035053`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180035053`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035027`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035089`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800351c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035027`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035089`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800351c6`

## string_xrefs

- `0x180034d94`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`
- `0x180034e01`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall SystemSettings::WorkAccess::CApplicationManagedByMDM::SetModernAppName(
        SystemSettings::WorkAccess::CApplicationManagedByMDM *this)
{
  const unsigned __int16 (*v2)[45]; // rdx
  int v3; // eax
  unsigned int v4; // ebx
  unsigned __int64 v5; // r9
  __int64 v6; // rdx
  __int64 last_of; // rax
  __int64 v8; // rax
  WCHAR *v9; // rax
  __int64 v11; // rdi
  int (__fastcall *v12)(__int64, _QWORD, HSTRING, __int64 *); // rbx
  __int64 v13; // rdi
  void (__fastcall *v14)(__int64, __int64 *); // rbx
  __int64 v15; // rdi
  int (__fastcall *v16)(__int64, __int64 *); // rbx
  unsigned int i; // esi
  __int64 v18; // rdi
  int (__fastcall *v19)(__int64, _QWORD, HANDLE *); // rbx
  HANDLE v20; // rdi
  int (__fastcall *v21)(HANDLE, __int64 *); // rbx
  __int64 v22; // rdi
  int (__fastcall *v23)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  const unsigned __int16 *v25; // rax
  _bstr_t *v26; // rax
  HANDLE Thread; // rax
  unsigned int v28; // r8d
  const char *v29; // r9
  __int64 v30; // rdx
  __int64 v31; // rcx
  DWORD dwCreationFlags; // [rsp+20h] [rbp-E0h]
  char v33[8]; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE v34; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v35; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v37; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v38; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v40; // [rsp+68h] [rbp-98h] BYREF
  __int64 v41; // [rsp+70h] [rbp-90h] BYREF
  __int64 v42; // [rsp+78h] [rbp-88h] BYREF
  __int64 v43; // [rsp+80h] [rbp-80h] BYREF
  __int64 v44; // [rsp+88h] [rbp-78h] BYREF
  HSTRING v45; // [rsp+90h] [rbp-70h] BYREF
  __int64 v46; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v47[32]; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING v48; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v49[32]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  std::wstring::wstring(v47, *((_QWORD *)this + 30));
  v37 = 0;
  Windows::Internal::StringReference::StringReference(&v48, v2);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  v3 = Windows::Foundation::ActivateInstance<Windows::Management::Deployment::IPackageManager>(v48, &v37);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = (unsigned int)v3;
    v6 = 2017;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
      (const char *)v5,
      dwCreationFlags);
LABEL_11:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
    std::wstring::_Tidy_deallocate(v47);
    return v4;
  }
  if ( !v37 )
  {
    v4 = -2147024882;
    v6 = 2018;
LABEL_5:
    v5 = v4;
    goto LABEL_6;
  }
  last_of = std::wstring::find_last_of(v47);
  if ( last_of == -1 )
  {
    v4 = -2147023728;
    v6 = 2021;
    goto LABEL_5;
  }
  v39 = 0;
  v8 = std::wstring::substr(v47, v49, last_of + 1);
  v9 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8);
  v4 = UrlUnEscapeWrapper(v9);
  std::wstring::_Tidy_deallocate(v49);
  if ( (v4 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7E7,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
      (const char *)v4,
      dwCreationFlags);
    CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&v39);
    goto LABEL_11;
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
    (char *)this + 216,
    v39,
    -1);
  v45 = 0;
  Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&v45, &v39);
  v44 = 0;
  v11 = v37;
  v12 = *(int (__fastcall **)(__int64, _QWORD, HSTRING, __int64 *))(*(_QWORD *)v37 + 160LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
  if ( v12(v11, 0, v45, &v44) >= 0 )
  {
    v38 = 0;
    v13 = v44;
    v14 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    v14(v13, &v38);
    v33[0] = 0;
    v43 = 0;
    v46 = 0;
    v42 = 0;
    v41 = 0;
    v35 = 0;
    if ( (*(int (__fastcall **)(__int64, char *))(*(_QWORD *)v38 + 56LL))(v38, v33) >= 0
      && v33[0]
      && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 48LL))(v38, &v43) >= 0
      && (int)Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage>::As<Windows::ApplicationModel::IPackage3>(
                &v43,
                &v46) >= 0
      && (v15 = v46,
          v16 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v46 + 64LL),
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42),
          v16(v15, &v42) >= 0)
      && (int)BlockOnCompletionAndGetResults<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *,Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *>>(
                v42,
                &v41) >= 0
      && (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v41 + 56LL))(v41, &v35) >= 0 )
    {
      for ( i = 0; i < v35; ++i )
      {
        v34 = 0;
        v18 = v41;
        v19 = *(int (__fastcall **)(__int64, _QWORD, HANDLE *))(*(_QWORD *)v41 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
        if ( v19(v18, i, &v34) >= 0 )
        {
          v40 = 0;
          v20 = v34;
          v21 = *(int (__fastcall **)(HANDLE, __int64 *))(*(_QWORD *)v34 + 48LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
          if ( v21(v20, &v40) >= 0 )
          {
            string = 0;
            v22 = v40;
            v23 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v40 + 48LL);
            WindowsDeleteString(0);
            string = 0;
            if ( v23(v22, &string) >= 0 )
            {
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                (char *)this + 216,
                StringRawBuffer,
                -1);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                (char *)this + 264,
                L"Succeeded",
                -1);
            }
            WindowsDeleteString(string);
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
      }
    }
    else
    {
      v25 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v47);
      v26 = _bstr_t::_bstr_t((_bstr_t *)&v34, v25);
      _bstr_t::operator=(&SystemSettings::WorkAccess::CEnrollmentHelper::_appStringProperty, v26);
      _bstr_t::_Free((_bstr_t *)&v34);
      LODWORD(string) = 0;
      Thread = CreateThread(
                 0,
                 0,
                 SystemSettings::WorkAccess::CEnrollmentHelper::GetStatusByNodePath,
                 0,
                 0,
                 (LPDWORD)&string);
      v34 = Thread;
      if ( !Thread )
        wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x81C, v28, v29);
      WaitForSingleObject(Thread, 0xFFFFFFFF);
      if ( SystemSettings::WorkAccess::CEnrollmentHelper::_appStatus )
        v30 = *SystemSettings::WorkAccess::CEnrollmentHelper::_appStatus;
      else
        v30 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
        (char *)this + 264,
        v30,
        -1);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v34);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
    v31 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
  WindowsDeleteString(v45);
  v45 = 0;
  CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&v39);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  std::wstring::_Tidy_deallocate(v47);
  return 0;
}

```

## disassembly

```asm
0x180034d08  push    rbp
0x180034d0a  push    rbx
0x180034d0b  push    rsi
0x180034d0c  push    rdi
0x180034d0d  push    r12
0x180034d0f  push    r13
0x180034d11  push    r14
0x180034d13  push    r15
0x180034d15  lea     rbp, [rsp-18h]
0x180034d1a  sub     rsp, 118h
0x180034d21  mov     rax, cs:__security_cookie
0x180034d28  xor     rax, rsp
0x180034d2b  mov     [rbp+50h+var_50], rax
0x180034d2f  mov     r14, rcx
0x180034d32  mov     rdx, [rcx+0F0h]
0x180034d39  lea     rcx, [rbp+50h+var_B0]
0x180034d3d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180034d42  nop
0x180034d43  xor     r12d, r12d
0x180034d46  mov     [rsp+150h+var_100], r12
0x180034d4b  lea     rcx, [rbp+50h+var_90]; string
0x180034d4f  call    ??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[45])
0x180034d54  lea     rcx, [rsp+150h+var_100]
0x180034d59  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034d5e  lea     rdx, [rsp+150h+var_100]
0x180034d63  mov     rcx, [rbp+50h+var_90]
0x180034d67  call    ??$ActivateInstance@UIPackageManager@Deployment@Management@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIPackageManager@Deployment@Management@1@@Z; Windows::Foundation::ActivateInstance<Windows::Management::Deployment::IPackageManager>(HSTRING__ *,Windows::Management::Deployment::IPackageManager * *)
0x180034d6c  mov     ebx, eax
0x180034d6e  test    eax, eax
0x180034d70  jns     short loc_180034D7C
0x180034d72  mov     r9d, eax
0x180034d75  mov     edx, 7E1h
0x180034d7a  jmp     short loc_180034D90
0x180034d7c  cmp     [rsp+150h+var_100], r12
0x180034d81  jnz     short loc_180034DA2
0x180034d83  mov     ebx, 8007000Eh
0x180034d88  mov     edx, 7E2h; void *
0x180034d8d  mov     r9d, ebx; char *
0x180034d90  mov     rcx, [rbp+58h]; this
0x180034d94  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180034d9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034da0  jmp     short loc_180034E1E
0x180034da2  lea     rcx, [rbp+50h+var_B0]
0x180034da6  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find_last_of(ushort,unsigned __int64)
0x180034dab  or      r13, 0FFFFFFFFFFFFFFFFh
0x180034daf  cmp     rax, r13
0x180034db2  jnz     short loc_180034DC0
0x180034db4  mov     ebx, 80070490h
0x180034db9  mov     edx, 7E5h
0x180034dbe  jmp     short loc_180034D8D
0x180034dc0  mov     [rsp+150h+var_F0], r12
0x180034dc5  lea     r8, [rax+1]
0x180034dc9  lea     rdx, [rbp+50h+var_70]
0x180034dcd  lea     rcx, [rbp+50h+var_B0]
0x180034dd1  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180034dd6  mov     rcx, rax
0x180034dd9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180034dde  lea     rdx, [rsp+150h+var_F0]
0x180034de3  mov     rcx, rax; pszUrl
0x180034de6  call    UrlUnEscapeWrapper
0x180034deb  mov     ebx, eax
0x180034ded  lea     rcx, [rbp+50h+var_70]
0x180034df1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034df6  test    ebx, ebx
0x180034df8  jns     short loc_180034E39
0x180034dfa  mov     rcx, [rbp+58h]; this
0x180034dfe  mov     r9d, ebx; char *
0x180034e01  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180034e08  mov     edx, 7E7h; void *
0x180034e0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034e12  nop
0x180034e13  lea     rcx, [rsp+150h+var_F0]
0x180034e18  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x180034e1d  nop
0x180034e1e  lea     rcx, [rsp+150h+var_100]
0x180034e23  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034e28  nop
0x180034e29  lea     rcx, [rbp+50h+var_B0]
0x180034e2d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034e32  mov     eax, ebx
0x180034e34  jmp     loc_1800351F7
0x180034e39  lea     r15, [r14+0D8h]
0x180034e40  mov     r8, r13
0x180034e43  mov     rdx, [rsp+150h+var_F0]
0x180034e48  mov     rcx, r15
0x180034e4b  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180034e50  mov     [rbp+50h+var_C0], r12
0x180034e54  lea     rdx, [rsp+150h+var_F0]
0x180034e59  lea     rcx, [rbp+50h+var_C0]
0x180034e5d  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x180034e62  mov     [rbp+50h+var_C8], r12
0x180034e66  mov     rdi, [rsp+150h+var_100]
0x180034e6b  mov     rax, [rdi]
0x180034e6e  mov     rbx, [rax+0A0h]
0x180034e75  lea     rcx, [rbp+50h+var_C8]
0x180034e79  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034e7e  lea     r9, [rbp+50h+var_C8]
0x180034e82  mov     r8, [rbp+50h+var_C0]
0x180034e86  xor     edx, edx
0x180034e88  mov     rcx, rdi
0x180034e8b  mov     rax, rbx
0x180034e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e93  test    eax, eax
0x180034e95  js      loc_1800351B8
0x180034e9b  mov     [rsp+150h+var_F8], r12
0x180034ea0  mov     rdi, [rbp+50h+var_C8]
0x180034ea4  mov     rax, [rdi]
0x180034ea7  mov     rbx, [rax+30h]
0x180034eab  lea     rcx, [rsp+150h+var_F8]
0x180034eb0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034eb5  lea     rdx, [rsp+150h+var_F8]
0x180034eba  mov     rcx, rdi
0x180034ebd  mov     rax, rbx
0x180034ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034ec5  mov     [rsp+150h+var_120], r12b
0x180034eca  mov     [rbp+50h+var_D0], r12
0x180034ece  mov     [rbp+50h+var_B8], r12
0x180034ed2  mov     [rsp+150h+var_D8], r12
0x180034ed7  mov     [rsp+150h+var_E0], r12
0x180034edc  mov     [rsp+150h+var_110], r12d
0x180034ee1  mov     rcx, [rsp+150h+var_F8]
0x180034ee6  mov     rax, [rcx]
0x180034ee9  lea     rdx, [rsp+150h+var_120]
0x180034eee  mov     rax, [rax+38h]
0x180034ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034ef7  test    eax, eax
0x180034ef9  js      loc_1800350BC
0x180034eff  cmp     [rsp+150h+var_120], r12b
0x180034f04  jz      loc_1800350BC
0x180034f0a  mov     rcx, [rsp+150h+var_F8]
0x180034f0f  mov     rax, [rcx]
0x180034f12  lea     rdx, [rbp+50h+var_D0]
0x180034f16  mov     rax, [rax+30h]
0x180034f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f1f  test    eax, eax
0x180034f21  js      loc_1800350BC
0x180034f27  lea     rdx, [rbp+50h+var_B8]
0x180034f2b  lea     rcx, [rbp+50h+var_D0]
0x180034f2f  call    ??$As@UIPackage3@ApplicationModel@Windows@@@?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPackage3@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage>::As<Windows::ApplicationModel::IPackage3>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage3>>)
0x180034f34  test    eax, eax
0x180034f36  js      loc_1800350BC
0x180034f3c  mov     rdi, [rbp+50h+var_B8]
0x180034f40  mov     rax, [rdi]
0x180034f43  mov     rbx, [rax+40h]
0x180034f47  lea     rcx, [rsp+150h+var_D8]
0x180034f4c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034f51  lea     rdx, [rsp+150h+var_D8]
0x180034f56  mov     rcx, rdi
0x180034f59  mov     rax, rbx
0x180034f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f61  test    eax, eax
0x180034f63  js      loc_1800350BC
0x180034f69  lea     rdx, [rsp+150h+var_E0]
0x180034f6e  mov     rcx, [rsp+150h+var_D8]
0x180034f73  call    ??$BlockOnCompletionAndGetResults@PEAU?$IVectorView@PEAVAppListEntry@Core@ApplicationModel@Windows@@@Collections@Foundation@Windows@@U1234@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppListEntry@Core@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@U?$IVectorView@PEAVAppListEntry@Core@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *,Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *>>>,tagCOWAIT_FLAGS,void *)
0x180034f78  test    eax, eax
0x180034f7a  js      loc_1800350BC
0x180034f80  mov     rcx, [rsp+150h+var_E0]
0x180034f85  mov     rax, [rcx]
0x180034f88  lea     rdx, [rsp+150h+var_110]
0x180034f8d  mov     rax, [rax+38h]
0x180034f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f96  test    eax, eax
0x180034f98  js      loc_1800350BC
0x180034f9e  mov     esi, r12d
0x180034fa1  cmp     [rsp+150h+var_110], r12d
0x180034fa6  jbe     loc_180035173
0x180034fac  mov     [rsp+150h+var_118], r12
0x180034fb1  mov     rdi, [rsp+150h+var_E0]
0x180034fb6  mov     rax, [rdi]
0x180034fb9  mov     rbx, [rax+30h]
0x180034fbd  lea     rcx, [rsp+150h+var_118]
0x180034fc2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034fc7  lea     r8, [rsp+150h+var_118]
0x180034fcc  mov     edx, esi
0x180034fce  mov     rcx, rdi
0x180034fd1  mov     rax, rbx
0x180034fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034fd9  test    eax, eax
0x180034fdb  js      loc_1800350A1
0x180034fe1  mov     [rsp+150h+var_E8], r12
0x180034fe6  mov     rdi, [rsp+150h+var_118]
0x180034feb  mov     rax, [rdi]
0x180034fee  mov     rbx, [rax+30h]
0x180034ff2  lea     rcx, [rsp+150h+var_E8]
0x180034ff7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034ffc  lea     rdx, [rsp+150h+var_E8]
0x180035001  mov     rcx, rdi
0x180035004  mov     rax, rbx
0x180035007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003500c  test    eax, eax
0x18003500e  js      loc_180035096
0x180035014  mov     [rsp+150h+string], r12
0x180035019  mov     rdi, [rsp+150h+var_E8]
0x18003501e  mov     rax, [rdi]
0x180035021  mov     rbx, [rax+30h]
0x180035025  xor     ecx, ecx; string
0x180035027  call    cs:__imp_WindowsDeleteString
0x18003502e  nop     dword ptr [rax+rax+00h]
0x180035033  mov     [rsp+150h+string], r12
0x180035038  lea     rdx, [rsp+150h+string]
0x18003503d  mov     rcx, rdi
0x180035040  mov     rax, rbx
0x180035043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035048  test    eax, eax
0x18003504a  js      short loc_180035084
0x18003504c  xor     edx, edx; length
0x18003504e  mov     rcx, [rsp+150h+string]; string
0x180035053  call    cs:__imp_WindowsGetStringRawBuffer
0x18003505a  nop     dword ptr [rax+rax+00h]
0x18003505f  mov     r8, r13
0x180035062  mov     rdx, rax
0x180035065  mov     rcx, r15
0x180035068  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18003506d  lea     rcx, [r14+108h]
0x180035074  mov     r8, r13
0x180035077  lea     rdx, aSucceeded; "Succeeded"
0x18003507e  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180035083  nop
0x180035084  mov     rcx, [rsp+150h+string]; string
0x180035089  call    cs:__imp_WindowsDeleteString
0x180035090  nop     dword ptr [rax+rax+00h]
0x180035095  nop
0x180035096  lea     rcx, [rsp+150h+var_E8]
0x18003509b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800350a0  nop
0x1800350a1  lea     rcx, [rsp+150h+var_118]
0x1800350a6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800350ab  inc     esi
0x1800350ad  cmp     esi, [rsp+150h+var_110]
0x1800350b1  jb      loc_180034FAC
0x1800350b7  jmp     loc_180035173
0x1800350bc  lea     rcx, [rbp+50h+var_B0]
0x1800350c0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800350c5  mov     rdx, rax; unsigned __int16 *
0x1800350c8  lea     rcx, [rsp+150h+var_118]; this
0x1800350cd  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800350d2  mov     rdx, rax
0x1800350d5  lea     rcx, ?_appStringProperty@CEnrollmentHelper@WorkAccess@SystemSettings@@2V_bstr_t@@A; _bstr_t SystemSettings::WorkAccess::CEnrollmentHelper::_appStringProperty
0x1800350dc  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x1800350e1  lea     rcx, [rsp+150h+var_118]; this
0x1800350e6  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800350eb  mov     dword ptr [rsp+150h+string], r12d
0x1800350f0  lea     rax, [rsp+150h+string]
0x1800350f5  mov     [rsp+150h+lpThreadId], rax; lpThreadId
0x1800350fa  mov     [rsp+150h+dwCreationFlags], r12d; dwCreationFlags
0x1800350ff  xor     r9d, r9d; lpParameter
0x180035102  lea     r8, ?GetStatusByNodePath@CEnrollmentHelper@WorkAccess@SystemSettings@@SAKPEAX@Z; lpStartAddress
0x180035109  xor     edx, edx; dwStackSize
0x18003510b  xor     ecx, ecx; lpThreadAttributes
0x18003510d  call    cs:__imp_CreateThread
0x180035114  nop     dword ptr [rax+rax+00h]
0x180035119  mov     [rsp+150h+var_118], rax
0x18003511e  mov     rcx, [rbp+58h]; this
0x180035122  test    rax, rax
0x180035125  jnz     short loc_180035132
0x180035127  mov     edx, 81Ch; void *
0x18003512c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180035132  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180035135  mov     rcx, rax; hHandle
0x180035138  call    cs:__imp_WaitForSingleObject
0x18003513f  nop     dword ptr [rax+rax+00h]
0x180035144  lea     rcx, [r14+108h]
0x18003514b  mov     rax, cs:?_appStatus@CEnrollmentHelper@WorkAccess@SystemSettings@@2V_bstr_t@@A; _bstr_t SystemSettings::WorkAccess::CEnrollmentHelper::_appStatus
0x180035152  test    rax, rax
0x180035155  jz      short loc_18003515C
0x180035157  mov     rdx, [rax]
0x18003515a  jmp     short loc_18003515F
0x18003515c  mov     rdx, r12
0x18003515f  mov     r8, r13
0x180035162  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180035167  nop
0x180035168  lea     rcx, [rsp+150h+var_118]
0x18003516d  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180035172  nop
0x180035173  lea     rcx, [rsp+150h+var_E0]
0x180035178  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003517d  nop
0x18003517e  lea     rcx, [rsp+150h+var_D8]
0x180035183  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180035188  nop
0x180035189  lea     rcx, [rbp+50h+var_B8]
0x18003518d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180035192  nop
0x180035193  mov     rcx, [rbp+50h+var_D0]
0x180035197  test    rcx, rcx
0x18003519a  jz      short loc_1800351AD
0x18003519c  mov     [rbp+50h+var_D0], r12
0x1800351a0  mov     rax, [rcx]
0x1800351a3  mov     rax, [rax+10h]
0x1800351a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800351ac  nop
0x1800351ad  lea     rcx, [rsp+150h+var_F8]
0x1800351b2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800351b7  nop
0x1800351b8  lea     rcx, [rbp+50h+var_C8]
0x1800351bc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800351c1  nop
0x1800351c2  mov     rcx, [rbp+50h+var_C0]; string
0x1800351c6  call    cs:__imp_WindowsDeleteString
  ... truncated ...
```
