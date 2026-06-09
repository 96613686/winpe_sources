# SystemSettings::PenSettings::GetAppDisplayNameByAumid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180022654`
- end: `0x180022a17`
- name: `?GetAppDisplayNameByAumid@PenSettings@SystemSettings@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@@Z`
- size: `963`
- prototype: ``
- caller_count: `4`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180027350`
- `0x180028910`
- `0x18002ce20`
- `0x18002faf0`

## callees

- `0x1800030e0`
- `0x180008128`
- `0x18000a2bc`
- `0x18000cb8c`
- `0x1800103b4`
- `0x1800115d8`
- `0x1800127cc`
- `0x180019fcc`
- `0x18001a378`
- `0x18001bb98`
- `0x18001bbd4`
- `0x180020638`
- `0x1800206dc`
- `0x180022654`
- `0x180028640`
- `0x180054048`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022682`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180022682`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180022712`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180022712`

## string_xrefs

- `0x1800226b3`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x180022725`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x1800227a4`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x18002280c`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x180022890`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x18002290e`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x180022971`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall SystemSettings::PenSettings::GetAppDisplayNameByAumid(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  void *v5; // r8
  int UserSidString; // eax
  unsigned int v7; // ebx
  __int64 v8; // rbx
  int ActivationFactory; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, _QWORD, __int64 *); // rbx
  __int64 v12; // rax
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64, _QWORD, SystemSettings::PenSettings **); // rbx
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // r9
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // r8
  struct SystemSettings::PenSettings::AppInfo *v26; // r9
  int LaunchableAppInfo; // eax
  int v29; // [rsp+20h] [rbp-E0h]
  __int64 v30; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v31; // [rsp+38h] [rbp-C8h] BYREF
  SystemSettings::PenSettings *v32; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v33; // [rsp+48h] [rbp-B8h] BYREF
  struct Windows::Internal::StateRepository::IApplication *v34; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE CurrentProcess; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-98h] BYREF
  __int64 v38; // [rsp+80h] [rbp-80h]
  _BYTE v39[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v40[33]; // [rsp+B0h] [rbp-50h] BYREF
  int v41; // [rsp+D1h] [rbp-2Fh]
  __int16 v42; // [rsp+D5h] [rbp-2Bh]
  char v43; // [rsp+D7h] [rbp-29h]
  _BYTE v44[32]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+28h]

  CurrentProcess = GetCurrentProcess();
  std::wstring::wstring(v44, v4, CurrentProcess);
  UserSidString = SystemSettings::PenSettings::GetUserSidString(v5, (__int64)v44);
  v7 = UserSidString;
  if ( UserSidString >= 0 )
  {
    v30 = 0;
    v38 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.StateRepository.User",
      0x26u,
      0x25u);
    v8 = v38;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    ActivationFactory = RoGetActivationFactory(v8, &GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720, &v30);
    v7 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v29);
LABEL_5:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
      goto LABEL_24;
    }
    v31 = 0;
    v10 = v30;
    v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v30 + 80LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    v35 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v44);
    v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v35);
    v13 = v11(v10, *(_QWORD *)(v12 + 24), &v31);
    v7 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
        (const char *)(unsigned int)v13,
        v29);
LABEL_8:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
      goto LABEL_5;
    }
    v33 = 0;
    v38 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.StateRepository.Application",
      0x2Du,
      0x2Cu);
    v14 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(
            v38,
            &v33);
    v7 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x86,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
        (const char *)(unsigned int)v14,
        v29);
LABEL_11:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      goto LABEL_8;
    }
    v32 = 0;
    v15 = v33;
    v16 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, SystemSettings::PenSettings **))(*(_QWORD *)v33 + 248LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    v35 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v35);
    v18 = v16(v15, v31, *(_QWORD *)(v17 + 24), &v32);
    v7 = v18;
    if ( v18 >= 0 )
    {
      if ( v32 )
      {
        v34 = 0;
        v38 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Internal.StateRepository.ApplicationResourceResolver",
          0x3Du,
          0x3Cu);
        v21 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationResourceResolverStatics>>(
                v38,
                &v34);
        v7 = v21;
        if ( v21 >= 0 )
        {
          std::wstring::wstring(v39, v22, v23);
          std::wstring::wstring(v40, v24, v25);
          v40[32] = 0;
          v41 = 0;
          v42 = 0;
          v43 = 0;
          LaunchableAppInfo = SystemSettings::PenSettings::GetLaunchableAppInfo(
                                v32,
                                v34,
                                (struct Windows::Internal::StateRepository::IApplicationResourceResolverStatics *)v39,
                                v26);
          v7 = LaunchableAppInfo;
          if ( LaunchableAppInfo >= 0 )
          {
            std::wstring::operator=(a2, v40);
            std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(v39);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
            v7 = 0;
            goto LABEL_24;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x92,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
            (const char *)(unsigned int)LaunchableAppInfo,
            v29);
          std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(v39);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8F,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
            (const char *)(unsigned int)v21,
            v29);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
        goto LABEL_15;
      }
      v7 = -2147009295;
      v19 = 2147958001LL;
      v20 = 137;
    }
    else
    {
      v19 = (unsigned int)v18;
      v20 = 136;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
      (const char *)v19,
      v29);
LABEL_15:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    goto LABEL_11;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x7C,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
    (const char *)(unsigned int)UserSidString,
    v29);
LABEL_24:
  std::wstring::_Tidy_deallocate(v44);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&CurrentProcess);
  return v7;
}

```

## disassembly

```asm
0x180022654  mov     [rsp-8+arg_10], rbx
0x180022659  mov     [rsp-8+arg_18], rsi
0x18002265e  push    rbp
0x18002265f  push    rdi
0x180022660  push    r14
0x180022662  lea     rbp, [rsp-10h]
0x180022667  sub     rsp, 110h
0x18002266e  mov     rax, cs:__security_cookie
0x180022675  xor     rax, rsp
0x180022678  mov     [rbp+20h+var_20], rax
0x18002267c  mov     rsi, rdx
0x18002267f  mov     r14, rcx
0x180022682  call    cs:__imp_GetCurrentProcess
0x180022688  mov     r8, rax
0x18002268b  mov     [rsp+120h+var_C0], rax
0x180022690  lea     rcx, [rbp+20h+var_40]
0x180022694  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180022699  nop
0x18002269a  lea     rdx, [rbp+20h+var_40]
0x18002269e  mov     rcx, r8
0x1800226a1  call    ?GetUserSidString@PenSettings@SystemSettings@@YAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SystemSettings::PenSettings::GetUserSidString(void *,std::wstring &)
0x1800226a6  mov     ebx, eax
0x1800226a8  test    eax, eax
0x1800226aa  jns     short loc_1800226C9
0x1800226ac  mov     rcx, [rbp+28h]; this
0x1800226b0  mov     r9d, eax; char *
0x1800226b3  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x1800226ba  mov     edx, 7Ch ; '|'; void *
0x1800226bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800226c4  jmp     loc_1800229DD
0x1800226c9  mov     [rsp+120h+var_F0], 0
0x1800226d2  mov     [rbp+20h+var_A0], 0
0x1800226da  mov     r9d, 25h ; '%'; unsigned int
0x1800226e0  lea     r8d, [r9+1]; unsigned int
0x1800226e4  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_User@@3QBGB; "Windows.Internal.StateRepository.User"
0x1800226eb  lea     rcx, [rsp+120h+hstringHeader]; hstringHeader
0x1800226f0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800226f5  mov     rbx, [rbp+20h+var_A0]
0x1800226f9  lea     rcx, [rsp+120h+var_F0]
0x1800226fe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180022703  lea     r8, [rsp+120h+var_F0]
0x180022708  lea     rdx, _GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720
0x18002270f  mov     rcx, rbx
0x180022712  call    cs:__imp_RoGetActivationFactory
0x180022718  mov     ebx, eax
0x18002271a  test    eax, eax
0x18002271c  jns     short loc_180022746
0x18002271e  mov     rcx, [rbp+28h]; this
0x180022722  mov     r9d, eax; char *
0x180022725  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18002272c  mov     edx, 80h; void *
0x180022731  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022736  nop
0x180022737  lea     rcx, [rsp+120h+var_F0]
0x18002273c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180022741  jmp     loc_1800229DD
0x180022746  mov     [rsp+120h+var_E8], 0
0x18002274f  mov     rdi, [rsp+120h+var_F0]
0x180022754  mov     rax, [rdi]
0x180022757  mov     rbx, [rax+50h]
0x18002275b  lea     rcx, [rsp+120h+var_E8]
0x180022760  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180022765  lea     rcx, [rbp+20h+var_40]
0x180022769  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002276e  mov     [rsp+120h+var_C8], rax
0x180022773  lea     rdx, [rsp+120h+var_C8]
0x180022778  lea     rcx, [rsp+120h+hstringHeader]
0x18002277d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180022782  nop
0x180022783  lea     r8, [rsp+120h+var_E8]
0x180022788  mov     rdx, [rax+18h]
0x18002278c  mov     rcx, rdi
0x18002278f  mov     rax, rbx
0x180022792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022797  mov     ebx, eax
0x180022799  test    eax, eax
0x18002279b  jns     short loc_1800227C5
0x18002279d  mov     rcx, [rbp+28h]; this
0x1800227a1  mov     r9d, eax; char *
0x1800227a4  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x1800227ab  mov     edx, 82h; void *
0x1800227b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800227b5  nop
0x1800227b6  lea     rcx, [rsp+120h+var_E8]
0x1800227bb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800227c0  jmp     loc_180022737
0x1800227c5  mov     [rsp+120h+var_D8], 0
0x1800227ce  mov     [rbp+20h+var_A0], 0
0x1800227d6  mov     r9d, 2Ch ; ','; unsigned int
0x1800227dc  lea     r8d, [r9+1]; unsigned int
0x1800227e0  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x1800227e7  lea     rcx, [rsp+120h+hstringHeader]; hstringHeader
0x1800227ec  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800227f1  lea     rdx, [rsp+120h+var_D8]
0x1800227f6  mov     rcx, [rbp+20h+var_A0]
0x1800227fa  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>)
0x1800227ff  mov     ebx, eax
0x180022801  test    eax, eax
0x180022803  jns     short loc_18002282A
0x180022805  mov     rcx, [rbp+28h]; this
0x180022809  mov     r9d, eax; char *
0x18002280c  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x180022813  mov     edx, 86h; void *
0x180022818  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002281d  nop
0x18002281e  lea     rcx, [rsp+120h+var_D8]
0x180022823  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180022828  jmp     short loc_1800227B6
0x18002282a  mov     [rsp+120h+var_E0], 0
0x180022833  mov     rdi, [rsp+120h+var_D8]
0x180022838  mov     rax, [rdi]
0x18002283b  mov     rbx, [rax+0F8h]
0x180022842  lea     rcx, [rsp+120h+var_E0]
0x180022847  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002284c  mov     rcx, r14
0x18002284f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022854  mov     [rsp+120h+var_C8], rax
0x180022859  lea     rdx, [rsp+120h+var_C8]
0x18002285e  lea     rcx, [rsp+120h+hstringHeader]
0x180022863  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180022868  nop
0x180022869  lea     r9, [rsp+120h+var_E0]
0x18002286e  mov     r8, [rax+18h]
0x180022872  mov     rdx, [rsp+120h+var_E8]
0x180022877  mov     rcx, rdi
0x18002287a  mov     rax, rbx
0x18002287d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022882  mov     ebx, eax
0x180022884  test    eax, eax
0x180022886  jns     short loc_1800228B0
0x180022888  mov     r9d, eax; char *
0x18002288b  mov     edx, 88h; void *
0x180022890  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x180022897  mov     rcx, [rbp+28h]; this
0x18002289b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800228a0  nop
0x1800228a1  lea     rcx, [rsp+120h+var_E0]
0x1800228a6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800228ab  jmp     loc_18002281E
0x1800228b0  cmp     [rsp+120h+var_E0], 0
0x1800228b6  jnz     short loc_1800228C7
0x1800228b8  mov     ebx, 80073CF1h
0x1800228bd  mov     r9d, ebx
0x1800228c0  mov     edx, 89h
0x1800228c5  jmp     short loc_180022890
0x1800228c7  mov     [rsp+120h+var_D0], 0
0x1800228d0  mov     [rbp+20h+var_A0], 0
0x1800228d8  mov     r9d, 3Ch ; '<'; unsigned int
0x1800228de  lea     r8d, [r9+1]; unsigned int
0x1800228e2  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationResourceResolver@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x1800228e9  lea     rcx, [rsp+120h+hstringHeader]; hstringHeader
0x1800228ee  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800228f3  lea     rdx, [rsp+120h+var_D0]
0x1800228f8  mov     rcx, [rbp+20h+var_A0]
0x1800228fc  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationResourceResolverStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationResourceResolverStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationResourceResolverStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationResourceResolverStatics>>)
0x180022901  mov     ebx, eax
0x180022903  test    eax, eax
0x180022905  jns     short loc_18002292F
0x180022907  mov     rcx, [rbp+28h]; this
0x18002290b  mov     r9d, eax; char *
0x18002290e  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x180022915  mov     edx, 8Fh; void *
0x18002291a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002291f  nop
0x180022920  lea     rcx, [rsp+120h+var_D0]
0x180022925  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002292a  jmp     loc_1800228A1
0x18002292f  lea     rcx, [rbp+20h+var_90]
0x180022933  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180022938  lea     rcx, [rbp+20h+var_70]
0x18002293c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180022941  mov     [rbp+20h+var_50], 0
0x180022945  xor     eax, eax
0x180022947  mov     [rbp+20h+var_4F], eax
0x18002294a  mov     [rbp+20h+var_4B], ax
0x18002294e  mov     [rbp+20h+var_49], al
0x180022951  lea     r8, [rbp+20h+var_90]; struct Windows::Internal::StateRepository::IApplicationResourceResolverStatics *
0x180022955  mov     rdx, [rsp+120h+var_D0]; struct Windows::Internal::StateRepository::IApplication *
0x18002295a  mov     rcx, [rsp+120h+var_E0]; this
0x18002295f  call    ?GetLaunchableAppInfo@PenSettings@SystemSettings@@YAJPEAUIApplication@StateRepository@Internal@Windows@@PEAUIApplicationResourceResolverStatics@456@PEAUAppInfo@12@@Z; SystemSettings::PenSettings::GetLaunchableAppInfo(Windows::Internal::StateRepository::IApplication *,Windows::Internal::StateRepository::IApplicationResourceResolverStatics *,SystemSettings::PenSettings::AppInfo *)
0x180022964  mov     ebx, eax
0x180022966  test    eax, eax
0x180022968  jns     short loc_18002298E
0x18002296a  mov     rcx, [rbp+28h]; this
0x18002296e  mov     r9d, eax; char *
0x180022971  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x180022978  mov     edx, 92h; void *
0x18002297d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022982  nop
0x180022983  lea     rcx, [rbp+20h+var_90]
0x180022987  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x18002298c  jmp     short loc_180022920
0x18002298e  lea     rdx, [rbp+20h+var_70]
0x180022992  mov     rcx, rsi
0x180022995  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002299a  nop
0x18002299b  lea     rcx, [rbp+20h+var_90]
0x18002299f  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x1800229a4  nop
0x1800229a5  lea     rcx, [rsp+120h+var_D0]
0x1800229aa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800229af  nop
0x1800229b0  lea     rcx, [rsp+120h+var_E0]
0x1800229b5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800229ba  nop
0x1800229bb  lea     rcx, [rsp+120h+var_D8]
0x1800229c0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800229c5  nop
0x1800229c6  lea     rcx, [rsp+120h+var_E8]
0x1800229cb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800229d0  nop
0x1800229d1  lea     rcx, [rsp+120h+var_F0]
0x1800229d6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800229db  xor     ebx, ebx
0x1800229dd  lea     rcx, [rbp+20h+var_40]
0x1800229e1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800229e6  nop
0x1800229e7  lea     rcx, [rsp+120h+var_C0]
0x1800229ec  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800229f1  mov     eax, ebx
0x1800229f3  mov     rcx, [rbp+20h+var_20]
0x1800229f7  xor     rcx, rsp; StackCookie
0x1800229fa  call    __security_check_cookie
0x1800229ff  lea     r11, [rsp+120h+var_10]
0x180022a07  mov     rbx, [r11+30h]
0x180022a0b  mov     rsi, [r11+38h]
0x180022a0f  mov     rsp, r11
0x180022a12  pop     r14
0x180022a14  pop     rdi
0x180022a15  pop     rbp
0x180022a16  retn
```
