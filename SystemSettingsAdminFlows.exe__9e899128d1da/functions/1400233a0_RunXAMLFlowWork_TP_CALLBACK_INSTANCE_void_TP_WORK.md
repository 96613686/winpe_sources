# RunXAMLFlowWork(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x1400233a0`
- end: `0x140024fcc`
- name: `?RunXAMLFlowWork@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `7212`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, unsigned int *, struct _TP_WORK *)`
- caller_count: `0`
- callee_count: `88`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x140004e68`
- `0x140005f30`
- `0x140007728`
- `0x1400077e4`
- `0x1400078a0`
- `0x14000794c`
- `0x140007a0c`
- `0x140007ac8`
- `0x140007b74`
- `0x140007c20`
- `0x140007cdc`
- `0x140007d98`
- `0x140007e54`
- `0x140007f10`
- `0x140007fcc`
- `0x140008088`
- `0x140008144`
- `0x1400081f0`
- `0x1400082ac`
- `0x140008368`
- `0x140008414`
- `0x1400084d4`
- `0x140008590`
- `0x14000864c`
- `0x140008708`
- `0x1400087c4`
- `0x140008880`
- `0x140008940`
- `0x1400089fc`
- `0x140008abc`
- `0x140008b68`
- `0x140008c24`
- `0x140008ce0`
- `0x140008d8c`
- `0x140008e48`
- `0x140008f04`
- `0x140008fc4`
- `0x140009080`
- `0x14000913c`
- `0x1400091f8`
- `0x1400092a4`
- `0x140009360`
- `0x14000941c`
- `0x1400094d8`
- `0x140009a68`
- `0x14000a864`
- `0x14000d4b4`
- `0x14000d550`
- `0x14000d808`
- `0x14000d850`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140023411`
- `KERNEL32!GetProcAddress` at `0x140023411`
- `KERNEL32!LocalFree` at `0x1400237ac`
- `KERNEL32!LocalFree` at `0x140023846`
- `KERNEL32!LocalFree` at `0x1400237ac`
- `KERNEL32!LocalFree` at `0x140023846`
- `KERNEL32!LoadLibraryExW` at `0x1400233f8`
- `KERNEL32!LoadLibraryExW` at `0x1400233f8`
- `KERNEL32!GetLastError` at `0x140023851`
- `KERNEL32!GetLastError` at `0x14002493a`
- `KERNEL32!GetLastError` at `0x140023851`
- `KERNEL32!GetLastError` at `0x14002493a`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x140024bee`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x140024bee`
- `SHELL32!ShellExecuteExW` at `0x140024930`
- `SHELL32!ShellExecuteExW` at `0x140024930`
- `SHELL32!CommandLineToArgvW` at `0x14002377f`
- `SHELL32!CommandLineToArgvW` at `0x140023954`
- `SHELL32!CommandLineToArgvW` at `0x14002377f`
- `SHELL32!CommandLineToArgvW` at `0x140023954`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1400233d7`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1400233d7`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140024f74`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140024f74`

## string_xrefs

- `0x1400233f1`: `MsftEdit.dll`
- `0x140023407`: `SetTextServicesDpiCalculationOverride`
- `0x140024fa8`: `pcshell\shell\systemsettings\adminflows\common\main.cpp`
- `0x140024fba`: `pcshell\shell\systemsettings\adminflows\common\main.cpp`
- `0x14002425a`: `Remove`
- `0x1400248fa`: `%systemroot%\system32\PhoneActivate.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall RunXAMLFlowWork(struct _TP_CALLBACK_INSTANCE *a1, unsigned int *a2, struct _TP_WORK *a3)
{
  int v4; // edi
  FARPROC v5; // rsi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FARPROC v8; // rbx
  int MosetWindowHandle; // eax
  __int64 v10; // rdx
  __int64 v11; // r9
  const unsigned __int16 *v12; // rdx
  const struct _GUID *v13; // r8
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  __int64 v19; // rax
  _BYTE *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  struct SystemSettings::XamlHost::IXamlHostHelper **v23; // rcx
  LPWSTR *v24; // rax
  LPWSTR *v25; // rbx
  LPWSTR *v26; // rcx
  signed int v27; // esi
  __int64 v28; // rax
  LPWSTR *v29; // rcx
  signed int LastError; // eax
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  __int64 v34; // rax
  LPWSTR *v35; // rax
  LPWSTR *v36; // r15
  _WORD *v37; // rax
  _WORD *v38; // rdx
  int v39; // ebx
  int v40; // eax
  __int64 v41; // rax
  __int128 *v42; // rcx
  LPWSTR v43; // rax
  __int64 v44; // rcx
  LPWSTR v45; // rdx
  int v46; // ebx
  int v47; // eax
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  int v51; // ecx
  int v52; // ecx
  int v53; // ecx
  int v54; // ecx
  __int64 v55; // r9
  struct IXamlHost *v56; // rsi
  int (__fastcall *v57)(struct IXamlHost *, HWND, _QWORD, _QWORD); // rbx
  bool v58; // al
  __int64 v59; // rax
  int v60; // ecx
  int v61; // ecx
  int v62; // ecx
  __int64 v63; // r9
  __int64 v64; // r9
  __int64 v65; // rdx
  __int64 v66; // rcx
  int v67; // eax
  __int64 v68; // rax
  int v69; // eax
  __int64 v70; // r8
  int v71; // eax
  __int64 v72; // rax
  __int64 v73; // r9
  int v74; // ecx
  int v75; // ecx
  int v76; // ecx
  int v77; // ecx
  __int64 v78; // r9
  __int64 v79; // rax
  __int64 v80; // r9
  __int64 v81; // r9
  int v82; // ecx
  int v83; // ecx
  int v84; // ecx
  __int64 v85; // r9
  __int64 v86; // r9
  __int64 v87; // r9
  signed int v88; // eax
  int v89; // ecx
  int v90; // ecx
  int v91; // ecx
  int v92; // ecx
  int v93; // ecx
  int v94; // ecx
  int v95; // ecx
  int v96; // ecx
  __int64 v97; // rax
  __int64 v98; // r9
  __int64 v99; // r9
  __int64 v100; // r9
  __int64 v101; // r9
  __int64 v102; // r9
  __int64 v103; // rax
  const char *v104; // r9
  __int64 v105; // rbx
  int v106; // eax
  int v107; // [rsp+20h] [rbp-E0h]
  int v108; // [rsp+40h] [rbp-C0h] BYREF
  HWND hWnd; // [rsp+48h] [rbp-B8h] BYREF
  struct IXamlHost *v110; // [rsp+50h] [rbp-B0h] BYREF
  struct SystemSettings::XamlHost::IXamlHostHelper *v111; // [rsp+58h] [rbp-A8h] BYREF
  struct SystemSettings::XamlHost::IXamlHostHelper *v112; // [rsp+60h] [rbp-A0h] BYREF
  int pNumArgs[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v114; // [rsp+70h] [rbp-90h] BYREF
  struct SystemSettings::XamlHost::IXamlHostHelper *v115; // [rsp+80h] [rbp-80h] BYREF
  struct SystemSettings::XamlHost::IXamlHostHelper *v116; // [rsp+88h] [rbp-78h] BYREF
  int v117; // [rsp+90h] [rbp-70h]
  HMODULE v118; // [rsp+98h] [rbp-68h] BYREF
  FARPROC v119; // [rsp+A0h] [rbp-60h]
  __int128 v120; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v121; // [rsp+B8h] [rbp-48h]
  void *v122; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v123[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v124[40]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v125[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v126; // [rsp+128h] [rbp+28h]
  _QWORD v127[2]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v128[56]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v129; // [rsp+178h] [rbp+78h]
  _BYTE v130[16]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v131; // [rsp+190h] [rbp+90h]
  SHELLEXECUTEINFOW pExecInfo; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  v4 = RoInitialize(0, a2);
  v117 = v4;
  v5 = 0;
  v119 = 0;
  Library = LoadLibraryExW(L"MsftEdit.dll", 0, 0);
  v118 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "SetTextServicesDpiCalculationOverride");
    v8 = ProcAddress;
    if ( ProcAddress )
    {
      if ( ((int (__fastcall *)(void (__fastcall *)(void *, int *, int *), _QWORD))ProcAddress)(
             RichEditDPIOverrider::s_InitializeDPI,
             0) >= 0 )
        v5 = v8;
      v119 = v5;
    }
  }
  if ( v4 >= 0 )
  {
    hWnd = 0;
    v110 = 0;
    v112 = 0;
    LOBYTE(v108) = 0;
    MosetWindowHandle = GetMosetWindowHandle(&hWnd);
    if ( MosetWindowHandle >= 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v110);
      MosetWindowHandle = XamlHost_CreateInstance(g_hInst, v12, v13, (void **)&v110);
      if ( MosetWindowHandle >= 0 )
        MosetWindowHandle = Microsoft::WRL::ComPtr<IXamlHost>::As<SystemSettings::XamlHost::IXamlHostHelper>(
                              &v110,
                              &v112);
    }
    v129 = 0;
    if ( MosetWindowHandle < 0 )
      goto LABEL_218;
    v14 = *a2;
    if ( (int)*a2 <= 55 )
    {
      if ( v14 == 55 )
      {
        LOBYTE(v73) = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminFlowRejuv_RemoteDesktop>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AdminFlowRejuv_RemoteDesktop>::GetImpl'::`2'::impl);
        LOBYTE(v108) = v73;
        if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, __int64))(*(_QWORD *)v110 + 48LL))(
               v110,
               hWnd,
               136,
               v73) < 0 )
          goto LABEL_218;
        v111 = 0;
        if ( (*(int (__fastcall **)(struct IXamlHost *, struct SystemSettings::XamlHost::IXamlHostHelper **))(*(_QWORD *)v110 + 96LL))(
               v110,
               &v111) < 0 )
          goto LABEL_218;
        *(_QWORD *)&v114 = hWnd;
        *((_QWORD *)&v114 + 1) = v111;
        v115 = v112;
        Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(&v115);
        std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_db9e91fc3538064f350f01c73ded113d__0_(
          v128,
          &v114);
        goto LABEL_80;
      }
      if ( v14 <= 35 )
      {
        if ( v14 == 35 )
        {
          v114 = *((_OWORD *)a2 + 1);
          if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int128 *))(*(_QWORD *)v110 + 64LL))(v110, hWnd, &v114) < 0 )
            goto LABEL_218;
          v50 = std::wstring::wstring(v124, *((_QWORD *)a2 + 1));
          v120 = *(_OWORD *)v50;
          v121 = *(_OWORD *)(v50 + 16);
          *(_QWORD *)(v50 + 16) = 0;
          *(_QWORD *)(v50 + 24) = 7;
          *(_WORD *)v50 = 0;
          v122 = v112;
          Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(&v122);
          std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_4e90da93e1f659249a9fdc4066ccad9d__0_(
            v128,
            &v120);
          lambda_ef3041f8637048bb84cf09d9e64014cc_::__lambda_ef3041f8637048bb84cf09d9e64014cc_(&v120);
        }
        else
        {
          if ( v14 <= 21 )
          {
            if ( v14 != 21 )
            {
              v15 = v14 - 1;
              if ( v15 )
              {
                v16 = v15 - 16;
                if ( v16 )
                {
                  v17 = v16 - 1;
                  if ( v17 )
                  {
                    v18 = v17 - 1;
                    if ( v18 )
                    {
                      if ( v18 == 1 )
                      {
                        LOBYTE(v108) = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminFlowRejuv_AddDomainUserAndEditUser>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AdminFlowRejuv_AddDomainUserAndEditUser>::GetImpl'::`2'::impl) != 0;
                        if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64))(*(_QWORD *)v110 + 48LL))(
                               v110,
                               hWnd,
                               298) >= 0 )
                        {
                          v19 = std::wstring::wstring(v130, *((_QWORD *)a2 + 1));
                          *(_OWORD *)v124 = *(_OWORD *)v19;
                          *(_OWORD *)&v124[16] = *(_OWORD *)(v19 + 16);
                          *(_QWORD *)(v19 + 16) = 0;
                          *(_QWORD *)(v19 + 24) = 7;
                          *(_WORD *)v19 = 0;
                          *(_QWORD *)&v124[32] = v112;
                          Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(&v124[32]);
                          std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_003402c841f9bc38004ccaf9236a946e__0_(
                            v128,
                            v124);
                          lambda_ef3041f8637048bb84cf09d9e64014cc_::__lambda_ef3041f8637048bb84cf09d9e64014cc_(v124);
LABEL_24:
                          v20 = v130;
LABEL_213:
                          std::wstring::_Tidy_deallocate(v20);
                          goto LABEL_214;
                        }
                      }
                    }
                    else if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, _QWORD))(*(_QWORD *)v110 + 48LL))(
                                v110,
                                hWnd,
                                293,
                                0) >= 0 )
                    {
                      v21 = std::wstring::wstring(v130, *((_QWORD *)a2 + 1));
                      *(_OWORD *)v124 = *(_OWORD *)v21;
                      *(_OWORD *)&v124[16] = *(_OWORD *)(v21 + 16);
                      *(_QWORD *)(v21 + 16) = 0;
                      *(_QWORD *)(v21 + 24) = 7;
                      *(_WORD *)v21 = 0;
                      *(_QWORD *)&v124[32] = v112;
                      Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(&v124[32]);
                      std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_2aabe9215f06c25dd12354f8ee5b7eae__0_(
                        v128,
                        v124);
                      lambda_ef3041f8637048bb84cf09d9e64014cc_::__lambda_ef3041f8637048bb84cf09d9e64014cc_(v124);
                      goto LABEL_24;
                    }
                  }
                  else if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, _QWORD))(*(_QWORD *)v110 + 48LL))(
                              v110,
                              hWnd,
                              253,
                              0) >= 0 )
                  {
                    v22 = std::wstring::wstring(v130, *((_QWORD *)a2 + 1));
                    *(_OWORD *)v124 = *(_OWORD *)v22;
                    *(_OWORD *)&v124[16] = *(_OWORD *)(v22 + 16);
                    *(_QWORD *)(v22 + 16) = 0;
                    *(_QWORD *)(v22 + 24) = 7;
                    *(_WORD *)v22 = 0;
                    *(_QWORD *)&v124[32] = v112;
                    Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(&v124[32]);
                    std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_4a0fc6e81b3f0353b97faa904326748e__0_(
                      v128,
                      v124);
                    lambda_ef3041f8637048bb84cf09d9e64014cc_::__lambda_ef3041f8637048bb84cf09d9e64014cc_(v124);
                    goto LABEL_24;
                  }
LABEL_218:
                  std::_Func_class<Microsoft::WRL::ComPtr<IInspectable>,>::_Tidy(v128);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v112);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v110);
                  goto LABEL_219;
                }
                LOBYTE(v108) = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminFlowRejuv_AddDomainUserAndEditUser>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AdminFlowRejuv_AddDomainUserAndEditUser>::GetImpl'::`2'::impl) != 0;
                if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64))(*(_QWORD *)v110 + 48LL))(
                       v110,
                       hWnd,
                       354) < 0 )
                  goto LABEL_218;
                *(_QWORD *)pNumArgs = v112;
                Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(pNumArgs);
                std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_ceb3ceb7ed1466ab6d2e5c4995da4cdc__0_(
                  v128,
                  pNumArgs);
              }
              else
              {
                LOBYTE(v108) = 1;
                LOBYTE(v11) = 1;
                if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, __int64))(*(_QWORD *)v110 + 48LL))(
                       v110,
                       hWnd,
                       308,
                       v11) < 0 )
                  goto LABEL_218;
                *(_QWORD *)pNumArgs = v112;
                Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(pNumArgs);
                std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_bc8e759282621152223107ceb7952b08__0_(
                  v128,
                  pNumArgs);
              }
              goto LABEL_31;
            }
            pNumArgs[0] = 0;
            v24 = CommandLineToArgvW(*((LPCWSTR *)a2 + 1), pNumArgs);
            v25 = v24;
            *(_QWORD *)&v114 = v24;
            if ( v24 )
            {
              if ( pNumArgs[0] != 1 )
              {
                a2[8] = -2147316575;
                v26 = v24;
LABEL_38:
                LocalFree(v26);
                goto LABEL_218;
              }
              v27 = (*(__int64 (__fastcall **)(struct IXamlHost *, HWND, __int64, _QWORD))(*(_QWORD *)v110 + 48LL))(
                      v110,
                      hWnd,
                      249,
                      0);
              if ( v27 >= 0 )
              {
                v28 = std::wstring::wstring(v130, *v25);
                *(_OWORD *)v124 = *(_OWORD *)v28;
                *(_OWORD *)&v124[16] = *(_OWORD *)(v28 + 16);
                *(_QWORD *)(v28 + 16) = 0;
                *(_QWORD *)(v28 + 24) = 7;
                *(_WORD *)v28 = 0;
                v124[32] = 0;
                *(_QWORD *)&v125[0] = v112;
                Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(v125);
                std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_d03e81677f3b08d48ec4ee8801d9d33a__0_(
                  v128,
                  v124);
                lambda_d03e81677f3b08d48ec4ee8801d9d33a_::__lambda_d03e81677f3b08d48ec4ee8801d9d33a_(v124);
                std::wstring::_Tidy_deallocate(v130);
              }
              v29 = v25;
              goto LABEL_42;
            }
            LastError = GetLastError();
            v27 = LastError;
            if ( LastError > 0 )
              v27 = (unsigned __int16)LastError | 0x80070000;
            a2[8] = v27;
LABEL_175:
            if ( v27 >= 0 )
              goto LABEL_214;
            goto LABEL_218;
          }
          v31 = v14 - 22;
          if ( v31 )
          {
            v32 = v31 - 6;
            if ( v32 )
            {
              v33 = v32 - 1;
              if ( v33 )
              {
                if ( v33 == 5
                  && (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, _QWORD))(*(_QWORD *)v110 + 48LL))(
                       v110,
                       hWnd,
                       188,
                       0) >= 0 )
                {
                  v34 = std::wstring::wstring(v130, *((_QWORD *)a2 + 1));
                  *(_OWORD *)v124 = *(_OWORD *)v34;
                  *(_OWORD *)&v124[16] = *(_OWORD *)(v34 + 16);
                  *(_QWORD *)(v34 + 16) = 0;
                  *(_QWORD *)(v34 + 24) = 7;
                  *(_WORD *)v34 = 0;
                  *(_QWORD *)&v124[32] = v112;
                  Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(&v124[32]);
                  std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_287faa08a55ec09bed06242ab9a76a13__0_(
                    v128,
                    v124);
                  lambda_ef3041f8637048bb84cf09d9e64014cc_::__lambda_ef3041f8637048bb84cf09d9e64014cc_(v124);
                  goto LABEL_24;
                }
                goto LABEL_218;
              }
              LOBYTE(v108) = 1;
              LOBYTE(v11) = 1;
              if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, __int64))(*(_QWORD *)v110 + 48LL))(
                     v110,
                     hWnd,
                     270,
                     v11) < 0 )
                goto LABEL_218;
              pNumArgs[0] = 0;
              v35 = CommandLineToArgvW(*((LPCWSTR *)a2 + 1), pNumArgs);
              v36 = v35;
              *(_QWORD *)&v114 = v35;
              if ( !v35 || pNumArgs[0] < 2 )
              {
                if ( !v35 )
                  goto LABEL_218;
                v26 = v35;
                goto LABEL_38;
              }
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PrinterRename_Fix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PrinterRename_Fix>::GetImpl'::`2'::impl) )
              {
                std::wstring::wstring(v130, *v36);
                v37 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v130);
                v38 = &v37[v131];
                while ( v37 != v38 )
                {
                  if ( *v37 == 44 )
                    *v37 = 32;
                  ++v37;
                }
                v111 = 0;
                v27 = (*(__int64 (__fastcall **)(struct IXamlHost *, struct SystemSettings::XamlHost::IXamlHostHelper **))(*(_QWORD *)v110 + 96LL))(
                        v110,
                        &v111);
                if ( v27 >= 0 )
                {
                  v39 = std::wstring::wstring(v124, v130);
                  v40 = std::wstring::wstring(&v120, v36[1]);
                  v41 = lambda_b4756509c9d8e7e74878bbac1385cf79_::_lambda_b4756509c9d8e7e74878bbac1385cf79_(
                          (unsigned int)&pExecInfo,
                          v39,
                          v40,
                          (unsigned int)&hWnd,
                          (__int64)&v111,
                          (__int64)&v112);
                  std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_b4756509c9d8e7e74878bbac1385cf79__0_(
                    v128,
                    v41);
                  lambda_b4756509c9d8e7e74878bbac1385cf79_::__lambda_b4756509c9d8e7e74878bbac1385cf79_(&pExecInfo);
                  std::wstring::_Tidy_deallocate(&v120);
                  std::wstring::_Tidy_deallocate(v124);
                }
                v42 = (__int128 *)v130;
              }
              else
              {
                v43 = *v36;
                v44 = -1;
                do
                  ++v44;
                while ( v43[v44 + 1] );
                v45 = &v43[2 * v44];
                while ( v43 != v45 )
                {
                  if ( *v43 == 35 )
                    *v43 = 32;
                  ++v43;
                }
                v111 = 0;
                v27 = (*(__int64 (__fastcall **)(struct IXamlHost *, struct SystemSettings::XamlHost::IXamlHostHelper **))(*(_QWORD *)v110 + 96LL))(
                        v110,
                        &v111);
                if ( v27 < 0 )
                  goto LABEL_74;
                v46 = std::wstring::wstring(&v120, *v36);
                v47 = std::wstring::wstring(v124, v36[1]);
                v48 = lambda_b4756509c9d8e7e74878bbac1385cf79_::_lambda_b4756509c9d8e7e74878bbac1385cf79_(
                        (unsigned int)&pExecInfo,
                        v46,
                        v47,
                        (unsigned int)&hWnd,
                        (__int64)&v111,
                        (__int64)&v112);
                std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_62f18b65ea10a1d1058c8ccc6f2f18ef__0_(
                  v128,
                  v48);
                lambda_b4756509c9d8e7e74878bbac1385cf79_::__lambda_b4756509c9d8e7e74878bbac1385cf79_(&pExecInfo);
                std::wstring::_Tidy_deallocate(v124);
                v42 = &v120;
              }
              std::wstring::_Tidy_deallocate(v42);
LABEL_74:
              v29 = v36;
LABEL_42:
              LocalFree(v29);
              goto LABEL_175;
            }
            LOBYTE(v108) = 1;
            LOBYTE(v11) = 1;
            if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, __int64))(*(_QWORD *)v110 + 48LL))(
                   v110,
                   hWnd,
                   270,
                   v11) < 0 )
              goto LABEL_218;
            v111 = 0;
            if ( (*(int (__fastcall **)(struct IXamlHost *, struct SystemSettings::XamlHost::IXamlHostHelper **))(*(_QWORD *)v110 + 96LL))(
                   v110,
                   &v111) < 0 )
              goto LABEL_218;
            *(_QWORD *)&v114 = hWnd;
            *((_QWORD *)&v114 + 1) = v111;
            v115 = v112;
            Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(&v115);
            std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_a825514c5cdf2883ba00a67e433b6c35__0_(
              v128,
              &v114);
LABEL_80:
            v23 = &v115;
            goto LABEL_32;
          }
          if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, _QWORD))(*(_QWORD *)v110 + 48LL))(
                 v110,
                 hWnd,
                 249,
                 0) < 0 )
            goto LABEL_218;
          v49 = std::wstring::wstring(v124, *((_QWORD *)a2 + 1));
          v120 = *(_OWORD *)v49;
          v121 = *(_OWORD *)(v49 + 16);
          *(_QWORD *)(v49 + 16) = 0;
          *(_QWORD *)(v49 + 24) = 7;
          *(_WORD *)v49 = 0;
          v122 = v112;
          Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(&v122);
          std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_ef3041f8637048bb84cf09d9e64014cc__0_(
            v128,
            &v120);
          lambda_ef3041f8637048bb84cf09d9e64014cc_::__lambda_ef3041f8637048bb84cf09d9e64014cc_(&v120);
        }
LABEL_212:
        v20 = v124;
        goto LABEL_213;
      }
      if ( v14 > 46 )
      {
        v60 = v14 - 48;
        if ( v60 )
        {
          v61 = v60 - 4;
          if ( v61 )
          {
            v62 = v61 - 1;
            if ( v62 )
            {
              if ( v62 != 1 )
                goto LABEL_218;
              LOBYTE(v63) = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminFlowRejuv_RemoteDesktop>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AdminFlowRejuv_RemoteDesktop>::GetImpl'::`2'::impl);
              LOBYTE(v108) = v63;
              if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, __int64))(*(_QWORD *)v110 + 48LL))(
                     v110,
                     hWnd,
                     176,
                     v63) < 0 )
                goto LABEL_218;
              v111 = 0;
              if ( (*(int (__fastcall **)(struct IXamlHost *, struct SystemSettings::XamlHost::IXamlHostHelper **))(*(_QWORD *)v110 + 96LL))(
                     v110,
                     &v111) < 0 )
                goto LABEL_218;
              *(_QWORD *)&v114 = hWnd;
              *((_QWORD *)&v114 + 1) = v111;
              v115 = v112;
              Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(&v115);
              std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_3066bff3c26361ba339976c0146ea6b2__0_(
                v128,
                &v114);
            }
            else
            {
              LOBYTE(v108) = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminFlowRejuv_RemoteDesktop>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AdminFlowRejuv_RemoteDesktop>::GetImpl'::`2'::impl);
              LOBYTE(v64) = v108;
              if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, __int64))(*(_QWORD *)v110 + 48LL))(
                     v110,
                     hWnd,
                     196,
                     v64) < 0 )
                goto LABEL_218;
              v111 = 0;
              if ( (*(int (__fastcall **)(struct IXamlHost *, struct SystemSettings::XamlHost::IXamlHostHelper **))(*(_QWORD *)v110 + 96LL))(
                     v110,
                     &v111) < 0 )
                goto LABEL_218;
              *(_QWORD *)&v114 = hWnd;
              *((_QWORD *)&v114 + 1) = v111;
              v115 = v112;
              Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(&v115);
              std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_6f39a39411269c89502a97227a703a1e__0_(
                v128,
                &v114);
            }
            goto LABEL_80;
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin_SFR>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin_SFR>::GetImpl'::`2'::impl)
            && (unsigned int)LUAIsShadowAdminEnabled(v66, v65) )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs();
          }
          LOBYTE(v108) = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminFlowRejuv_DevModeUnlock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AdminFlowRejuv_DevModeUnlock>::GetImpl'::`2'::impl) != 0;
          if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64))(*(_QWORD *)v110 + 48LL))(v110, hWnd, 250) < 0 )
            goto LABEL_218;
          v111 = 0;
          if ( (*(int (__fastcall **)(struct IXamlHost *, struct SystemSettings::XamlHost::IXamlHostHelper **))(*(_QWORD *)v110 + 96LL))(
                 v110,
                 &v111) < 0 )
            goto LABEL_218;
          v67 = std::wstring::wstring(v124, *((_QWORD *)a2 + 1));
          v68 = lambda_db5534a85f772a90ff651db6586afe13_::_lambda_db5534a85f772a90ff651db6586afe13_(
                  (unsigned int)&v120,
                  v67,
                  (unsigned int)&hWnd,
                  (unsigned int)&v111,
                  (__int64)&v112);
          std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_db5534a85f772a90ff651db6586afe13__0_(
            v128,
            v68);
          lambda_db5534a85f772a90ff651db6586afe13_::__lambda_db5534a85f772a90ff651db6586afe13_(&v120);
        }
        else
        {
          v69 = wcsncmp_0(*((const wchar_t **)a2 + 1), L"Remove", 6u);
          v70 = 224;
          if ( v69 )
            v70 = 269;
          if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, _QWORD))(*(_QWORD *)v110 + 48LL))(
                 v110,
                 hWnd,
                 v70,
                 0) < 0 )
            goto LABEL_218;
          v111 = 0;
          if ( (*(int (__fastcall **)(struct IXamlHost *, struct SystemSettings::XamlHost::IXamlHostHelper **))(*(_QWORD *)v110 + 96LL))(
                 v110,
                 &v111) < 0 )
            goto LABEL_218;
          v71 = std::wstring::wstring(v124, *((_QWORD *)a2 + 1));
          v72 = lambda_db5534a85f772a90ff651db6586afe13_::_lambda_db5534a85f772a90ff651db6586afe13_(
                  (unsigned int)&v120,
                  v71,
                  (unsigned int)&hWnd,
                  (unsigned int)&v111,
                  (__int64)&v112);
          std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_a26ae4d5307d603cde182ef2c8d4d6ef__0_(
            v128,
            v72);
          lambda_db5534a85f772a90ff651db6586afe13_::__lambda_db5534a85f772a90ff651db6586afe13_(&v120);
        }
        goto LABEL_212;
      }
      if ( v14 == 46 )
      {
        if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, _QWORD))(*(_QWORD *)v110 + 48LL))(
               v110,
               hWnd,
               273,
               0) < 0 )
          goto LABEL_218;
        v59 = std::wstring::wstring(v124, *((_QWORD *)a2 + 1));
        v120 = *(_OWORD *)v59;
        v121 = *(_OWORD *)(v59 + 16);
        *(_QWORD *)(v59 + 16) = 0;
        *(_QWORD *)(v59 + 24) = 7;
        *(_WORD *)v59 = 0;
        v122 = hWnd;
        v123[0] = v112;
        Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(v123);
        std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_3a4e723263d527705e89badfc4a22dc0__0_(
          v128,
          &v120);
        lambda_d03e81677f3b08d48ec4ee8801d9d33a_::__lambda_d03e81677f3b08d48ec4ee8801d9d33a_(&v120);
        goto LABEL_212;
      }
      v51 = v14 - 36;
      if ( !v51 )
      {
        if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, _QWORD))(*(_QWORD *)v110 + 48LL))(
               v110,
               hWnd,
               229,
               0) < 0 )
          goto LABEL_218;
        v111 = 0;
        if ( (*(int (__fastcall **)(struct IXamlHost *, struct SystemSettings::XamlHost::IXamlHostHelper **))(*(_QWORD *)v110 + 96LL))(
               v110,
               &v111) < 0 )
          goto LABEL_218;
        *(_QWORD *)&v114 = hWnd;
        *((_QWORD *)&v114 + 1) = v111;
        v115 = v112;
        Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(&v115);
        std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_f9de69aecda4ae4bd001fcb2da50baa4__0_(
          v128,
          &v114);
        goto LABEL_80;
      }
      v52 = v51 - 1;
      if ( !v52 )
      {
        v56 = v110;
        v57 = *(int (__fastcall **)(struct IXamlHost *, HWND, _QWORD, _QWORD))(*(_QWORD *)v110 + 48LL);
        v58 = SHIsCurrentAccountDomainUser();
        if ( v57(v56, hWnd, v58 ? 264 : 204, 0) < 0 )
          goto LABEL_218;
        v111 = 0;
        if ( (*(int (__fastcall **)(struct IXamlHost *, struct SystemSettings::XamlHost::IXamlHostHelper **))(*(_QWORD *)v110 + 96LL))(
               v110,
               &v111) < 0 )
          goto LABEL_218;
        *(_QWORD *)&v114 = hWnd;
        *((_QWORD *)&v114 + 1) = v111;
        v115 = v112;
        Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(&v115);
        std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_c1b063fe06ee3a2883018409ffc5529a__0_(
          v128,
          &v114);
        goto LABEL_80;
      }
      v53 = v52 - 4;
      if ( v53 )
      {
        v54 = v53 - 1;
        if ( v54 )
        {
          if ( v54 != 3 )
            goto LABEL_218;
          LOBYTE(v108) = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminFlowRejuv_RetailDemoConfirmPage>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AdminFlowRejuv_RetailDemoConfirmPage>::GetImpl'::`2'::impl);
          LOBYTE(v55) = v108;
          if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, __int64))(*(_QWORD *)v110 + 48LL))(
                 v110,
                 hWnd,
                 273,
                 v55) < 0 )
            goto LABEL_218;
          v111 = 0;
          if ( (*(int (__fastcall **)(struct IXamlHost *, struct SystemSettings::XamlHost::IXamlHostHelper **))(*(_QWORD *)v110 + 96LL))(
                 v110,
                 &v111) < 0 )
            goto LABEL_218;
          *(_QWORD *)&v114 = hWnd;
          *((_QWORD *)&v114 + 1) = v111;
          v115 = v112;
          Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(&v115);
          std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_0055f12495fe7a7cced1071aef02a264__0_(
            v128,
            &v114);
          goto LABEL_80;
        }
        v114 = *((_OWORD *)a2 + 1);
        if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int128 *, __int64, int, _BYTE))(*(_QWORD *)v110 + 64LL))(
               v110,
               hWnd,
               &v114,
               160,
               270,
               0) < 0 )
          goto LABEL_218;
        *(_QWORD *)pNumArgs = v112;
        Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(pNumArgs);
        std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_2565171d10a3a872a3283350192f2f41__0_(
          v128,
          pNumArgs);
      }
      else
      {
        v114 = *((_OWORD *)a2 + 1);
        if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int128 *, __int64, int, _BYTE))(*(_QWORD *)v110 + 64LL))(
               v110,
               hWnd,
               &v114,
               160,
               270,
               0) < 0 )
          goto LABEL_218;
        *(_QWORD *)pNumArgs = v112;
        Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(pNumArgs);
        std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_1f10a2854750e2d7d1cb57a8c5a26c32__0_(
          v128,
          pNumArgs);
      }
      goto LABEL_31;
    }
    if ( v14 > 145 )
    {
      v89 = v14 - 149;
      if ( !v89 )
      {
        if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, _QWORD))(*(_QWORD *)v110 + 48LL))(
               v110,
               hWnd,
               424,
               0) < 0 )
          goto LABEL_218;
        v103 = std::wstring::wstring(v124, *((_QWORD *)a2 + 1));
        v120 = *(_OWORD *)v103;
        v121 = *(_OWORD *)(v103 + 16);
        *(_QWORD *)(v103 + 16) = 0;
        *(_QWORD *)(v103 + 24) = 7;
        *(_WORD *)v103 = 0;
        v122 = hWnd;
        v123[0] = v112;
        Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(v123);
        std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_7602146b9b7965adb7827db3ee51fc88__0_(
          v128,
          &v120);
        lambda_d03e81677f3b08d48ec4ee8801d9d33a_::__lambda_d03e81677f3b08d48ec4ee8801d9d33a_(&v120);
        goto LABEL_212;
      }
      v90 = v89 - 5;
      if ( !v90 )
      {
        LOBYTE(v108) = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetImpl'::`2'::impl);
        LOBYTE(v102) = v108;
        if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, __int64))(*(_QWORD *)v110 + 48LL))(
               v110,
               hWnd,
               249,
               v102) < 0 )
          goto LABEL_218;
        v111 = 0;
        if ( (*(int (__fastcall **)(struct IXamlHost *, struct SystemSettings::XamlHost::IXamlHostHelper **))(*(_QWORD *)v110 + 96LL))(
               v110,
               &v111) < 0 )
          goto LABEL_218;
        *(_QWORD *)&v114 = hWnd;
        *((_QWORD *)&v114 + 1) = v111;
        v115 = v112;
        Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(&v115);
        std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_83e2e58a5d899ac00bd1ef6ac8aeb245__0_(
          v128,
          &v114);
        goto LABEL_80;
      }
      v91 = v90 - 1;
      if ( !v91 )
      {
        LOBYTE(v108) = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetImpl'::`2'::impl);
        LOBYTE(v101) = v108;
        if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, __int64))(*(_QWORD *)v110 + 48LL))(
               v110,
               hWnd,
               249,
               v101) < 0 )
          goto LABEL_218;
        v111 = 0;
        if ( (*(int (__fastcall **)(struct IXamlHost *, struct SystemSettings::XamlHost::IXamlHostHelper **))(*(_QWORD *)v110 + 96LL))(
               v110,
               &v111) < 0 )
          goto LABEL_218;
        *(_QWORD *)&v114 = hWnd;
        *((_QWORD *)&v114 + 1) = v111;
        v115 = v112;
        Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(&v115);
        std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_3aad2794afd3ea08e6839f3c6fa41bd0__0_(
          v128,
          &v114);
        goto LABEL_80;
      }
      v92 = v91 - 5;
      if ( v92 )
      {
        v93 = v92 - 18;
        if ( v93 )
        {
          v94 = v93 - 2;
          if ( !v94 )
          {
            LOBYTE(v108) = 1;
            LOBYTE(v11) = 1;
            if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, __int64))(*(_QWORD *)v110 + 48LL))(
                   v110,
                   hWnd,
                   270,
                   v11) < 0 )
              goto LABEL_218;
            v111 = 0;
            if ( (*(int (__fastcall **)(struct IXamlHost *, struct SystemSettings::XamlHost::IXamlHostHelper **))(*(_QWORD *)v110 + 96LL))(
                   v110,
                   &v111) < 0 )
              goto LABEL_218;
            *(_QWORD *)&v114 = a2;
            *((_QWORD *)&v114 + 1) = hWnd;
            v115 = v111;
            v116 = v112;
            Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(&v116);
            std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_eb7ec015d81c946806337092ccb086ec__0_(
              v128,
              &v114);
            v23 = &v116;
            goto LABEL_32;
          }
          v95 = v94 - 1;
          if ( !v95 )
          {
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59138840>::__private_IsEnabled(
                                     `wil::Feature<__WilFeatureTraits_Feature_ID59138840>::GetImpl'::`2'::impl,
                                     v10) )
              goto LABEL_214;
            LOBYTE(v108) = 1;
            LOBYTE(v98) = 1;
            if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, __int64))(*(_QWORD *)v110 + 48LL))(
                   v110,
                   hWnd,
                   320,
                   v98) < 0 )
              goto LABEL_218;
            *(_QWORD *)pNumArgs = v112;
            Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(pNumArgs);
            std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_ecb20d5d1e6717d1da525dfee50fbf41__0_(
              v128,
              pNumArgs);
            goto LABEL_31;
          }
          v96 = v95 - 4;
          if ( !v96 )
          {
            LOBYTE(v108) = 1;
            LOBYTE(v11) = 1;
            if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, _QWORD, __int64))(*(_QWORD *)v110 + 48LL))(
                   v110,
                   hWnd,
                   a2[32],
                   v11) < 0 )
              goto LABEL_218;
            *(_QWORD *)v124 = *((_QWORD *)a2 + 7);
            *(_OWORD *)&v124[8] = *((_OWORD *)a2 + 4);
            *(_OWORD *)&v124[24] = *((_OWORD *)a2 + 5);
            v125[0] = *((_OWORD *)a2 + 6);
            v125[1] = *((_OWORD *)a2 + 7);
            v126 = *((_QWORD *)a2 + 16);
            v127[0] = v112;
            Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(v127);
            std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_176bb4239c45d654f395684cabd54648__0_(
              v128,
              v124);
            v23 = (struct SystemSettings::XamlHost::IXamlHostHelper **)v127;
            goto LABEL_32;
          }
          if ( v96 != 1 )
            goto LABEL_218;
          LOBYTE(v108) = 1;
          LOBYTE(v11) = 1;
          if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, __int64))(*(_QWORD *)v110 + 48LL))(
                 v110,
                 hWnd,
                 314,
                 v11) < 0 )
            goto LABEL_218;
          v97 = std::wstring::wstring(v124, *((_QWORD *)a2 + 1));
          v120 = *(_OWORD *)v97;
          v121 = *(_OWORD *)(v97 + 16);
          *(_QWORD *)(v97 + 16) = 0;
          *(_QWORD *)(v97 + 24) = 7;
          *(_WORD *)v97 = 0;
          v122 = v112;
          Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(&v122);
          std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_3f4e49d258e01e26f91dcac337d6ed6f__0_(
            v128,
            &v120);
          lambda_ef3041f8637048bb84cf09d9e64014cc_::__lambda_ef3041f8637048bb84cf09d9e64014cc_(&v120);
          goto LABEL_212;
        }
      }
      else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_46348128>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_46348128>::GetImpl'::`2'::impl) )
      {
        pNumArgs[0] = 0;
        RtlGetDeviceFamilyInfoEnum(0, pNumArgs, 0);
        if ( pNumArgs[0] == 3 )
        {
          LOBYTE(v108) = 1;
          LOBYTE(v99) = 1;
          if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, __int64))(*(_QWORD *)v110 + 48LL))(
                 v110,
                 hWnd,
                 354,
                 v99) < 0 )
            goto LABEL_218;
          v111 = v112;
          Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(&v111);
          std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_1508f6d7f7c4a0bc32e8a6aaa2dfafa0__0_(
            v128,
            &v111);
          v23 = &v111;
          goto LABEL_32;
        }
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SettingsRejuv_TimeServer>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SettingsRejuv_TimeServer>::GetImpl'::`2'::impl) )
        goto LABEL_214;
      LOBYTE(v108) = 1;
      LOBYTE(v100) = 1;
      if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, __int64))(*(_QWORD *)v110 + 48LL))(
             v110,
             hWnd,
             270,
             v100) < 0 )
        goto LABEL_218;
      v111 = 0;
      if ( (*(int (__fastcall **)(struct IXamlHost *, struct SystemSettings::XamlHost::IXamlHostHelper **))(*(_QWORD *)v110 + 96LL))(
             v110,
             &v111) < 0 )
        goto LABEL_218;
      *(_QWORD *)&v114 = hWnd;
      *((_QWORD *)&v114 + 1) = v111;
      v115 = v112;
      Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(&v115);
      std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_868211a2205a1c144b08cb31767e9bd4__0_(
        v128,
        &v114);
      goto LABEL_80;
    }
    if ( v14 == 145 )
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminFlowRejuv_PhoneActivationPage>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AdminFlowRejuv_PhoneActivationPage>::GetImpl'::`2'::impl) )
      {
        memset_0(&pExecInfo, 0, sizeof(pExecInfo));
        pExecInfo.cbSize = 112;
        pExecInfo.lpVerb = L"runas";
        pExecInfo.lpFile = L"%systemroot%\\system32\\PhoneActivate.exe";
        pExecInfo.nShow = 1;
        pExecInfo.fMask = 67109376;
        pExecInfo.lpParameters = L"classic";
        if ( ShellExecuteExW(&pExecInfo) )
        {
          v27 = 0;
        }
        else
        {
          v88 = GetLastError();
          v27 = v88;
          if ( v88 > 0 )
            v27 = (unsigned __int16)v88 | 0x80070000;
        }
        goto LABEL_175;
      }
      LOBYTE(v108) = 1;
      LOBYTE(v87) = 1;
      if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, __int64))(*(_QWORD *)v110 + 48LL))(
             v110,
             hWnd,
             700,
             v87) < 0 )
        goto LABEL_218;
      v111 = 0;
      if ( (*(int (__fastcall **)(struct IXamlHost *, struct SystemSettings::XamlHost::IXamlHostHelper **))(*(_QWORD *)v110 + 96LL))(
             v110,
             &v111) < 0 )
        goto LABEL_218;
      *(_QWORD *)&v114 = hWnd;
      *((_QWORD *)&v114 + 1) = v111;
      v115 = v112;
      Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(&v115);
      std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_cf5bd3c2b99ef0cc05130d83f277991e__0_(
        v128,
        &v114);
      goto LABEL_80;
    }
    if ( v14 > 87 )
    {
      v82 = v14 - 88;
      if ( v82 )
      {
        v83 = v82 - 1;
        if ( !v83 )
        {
          LOBYTE(v85) = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminFlowRejuv_TroubleshootActivation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AdminFlowRejuv_TroubleshootActivation>::GetImpl'::`2'::impl);
          LOBYTE(v108) = v85;
          if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, __int64))(*(_QWORD *)v110 + 48LL))(
                 v110,
                 hWnd,
                 329,
                 v85) < 0 )
            goto LABEL_218;
          v111 = 0;
          if ( (*(int (__fastcall **)(struct IXamlHost *, struct SystemSettings::XamlHost::IXamlHostHelper **))(*(_QWORD *)v110 + 96LL))(
                 v110,
                 &v111) < 0 )
            goto LABEL_218;
          *(_QWORD *)&v114 = hWnd;
          *((_QWORD *)&v114 + 1) = v111;
          v115 = v112;
          Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(&v115);
          std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_f7a34897ad30a5734e3e6160801f900a__0_(
            v128,
            &v114);
          goto LABEL_80;
        }
        v84 = v83 - 24;
        if ( !v84 )
        {
          v27 = SetAutoLogon(hWnd, 1, v112);
          goto LABEL_175;
        }
        if ( v84 != 29 )
          goto LABEL_218;
        LOBYTE(v108) = 1;
        LOBYTE(v11) = 1;
        if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, __int64))(*(_QWORD *)v110 + 48LL))(
               v110,
               hWnd,
               188,
               v11) < 0 )
          goto LABEL_218;
        *(_QWORD *)&v114 = a2;
        *((_QWORD *)&v114 + 1) = v112;
        Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef((char *)&v114 + 8);
        std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_3a2123e6ff170a5a7b4899ef09896aae__0_(
          v128,
          &v114);
      }
      else
      {
        LOBYTE(v86) = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminFlowRejuv_UninstallOS>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AdminFlowRejuv_UninstallOS>::GetImpl'::`2'::impl);
        LOBYTE(v108) = v86;
        if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, __int64))(*(_QWORD *)v110 + 48LL))(
               v110,
               hWnd,
               344,
               v86) < 0 )
          goto LABEL_218;
        *(_QWORD *)&v114 = hWnd;
        *((_QWORD *)&v114 + 1) = v112;
        Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef((char *)&v114 + 8);
        std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_18941ae7933eec05abbbda65ea4777af__0_(
          v128,
          &v114);
      }
    }
    else
    {
      if ( v14 != 87 )
      {
        v74 = v14 - 56;
        if ( !v74 )
        {
          LOBYTE(v108) = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminFlowRejuv_RemoteDesktop>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AdminFlowRejuv_RemoteDesktop>::GetImpl'::`2'::impl);
          LOBYTE(v80) = v108;
          if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, __int64))(*(_QWORD *)v110 + 48LL))(
                 v110,
                 hWnd,
                 196,
                 v80) < 0 )
            goto LABEL_218;
          v111 = 0;
          if ( (*(int (__fastcall **)(struct IXamlHost *, struct SystemSettings::XamlHost::IXamlHostHelper **))(*(_QWORD *)v110 + 96LL))(
                 v110,
                 &v111) < 0 )
            goto LABEL_218;
          *(_QWORD *)&v114 = hWnd;
          *((_QWORD *)&v114 + 1) = v111;
          v115 = v112;
          Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(&v115);
          std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_bf84eceea68181037841ea88398ff7f3__0_(
            v128,
            &v114);
          goto LABEL_80;
        }
        v75 = v74 - 15;
        if ( v75 )
        {
          v76 = v75 - 1;
          if ( v76 )
          {
            v77 = v76 - 1;
            if ( v77 )
            {
              if ( v77 != 13 )
                goto LABEL_218;
              LOBYTE(v78) = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminFlowRejuv_EnterProductKeyPage>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AdminFlowRejuv_EnterProductKeyPage>::GetImpl'::`2'::impl);
              LOBYTE(v108) = v78;
              if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, __int64))(*(_QWORD *)v110 + 48LL))(
                     v110,
                     hWnd,
                     555,
                     v78) < 0 )
                goto LABEL_218;
              v111 = 0;
              if ( (*(int (__fastcall **)(struct IXamlHost *, struct SystemSettings::XamlHost::IXamlHostHelper **))(*(_QWORD *)v110 + 96LL))(
                     v110,
                     &v111) < 0 )
                goto LABEL_218;
              *(_QWORD *)&v114 = hWnd;
              *((_QWORD *)&v114 + 1) = v111;
              v115 = v112;
              Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(&v115);
              std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_94795072181a07a1f3742c479b683c73__0_(
                v128,
                &v114);
              goto LABEL_80;
            }
            if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, _QWORD))(*(_QWORD *)v110 + 48LL))(
                   v110,
                   hWnd,
                   200,
                   0) < 0 )
              goto LABEL_218;
            v79 = std::wstring::wstring(v124, *((_QWORD *)a2 + 1));
            v120 = *(_OWORD *)v79;
            v121 = *(_OWORD *)(v79 + 16);
            *(_QWORD *)(v79 + 16) = 0;
            *(_QWORD *)(v79 + 24) = 7;
            *(_WORD *)v79 = 0;
            v122 = v112;
            Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(&v122);
            std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_dea7fed9a76c98f3a4525bf9a132ad5e__0_(
              v128,
              &v120);
            lambda_ef3041f8637048bb84cf09d9e64014cc_::__lambda_ef3041f8637048bb84cf09d9e64014cc_(&v120);
            goto LABEL_212;
          }
          if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, _QWORD))(*(_QWORD *)v110 + 48LL))(
                 v110,
                 hWnd,
                 200,
                 0) < 0 )
            goto LABEL_218;
          *(_QWORD *)pNumArgs = v112;
          Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(pNumArgs);
          std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_47b19653400993fcf5739a874a22593d__0_(
            v128,
            pNumArgs);
        }
        else
        {
          if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, _QWORD))(*(_QWORD *)v110 + 48LL))(
                 v110,
                 hWnd,
                 200,
                 0) < 0 )
            goto LABEL_218;
          *(_QWORD *)pNumArgs = v112;
          Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(pNumArgs);
          std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_4fc898efe879bfc07177178eb4d2cc89__0_(
            v128,
            pNumArgs);
        }
LABEL_31:
        v23 = (struct SystemSettings::XamlHost::IXamlHostHelper **)pNumArgs;
LABEL_32:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v23);
LABEL_214:
        pNumArgs[0] = *a2;
        v111 = v112;
        Microsoft::WRL::Details::Make<XamlContentProvider,std::function<Microsoft::WRL::ComPtr<IInspectable> (void)>,SystemSettings::XamlHost::IXamlHostHelper *,unsigned int,bool const &>(
          (unsigned int)&v114,
          (unsigned int)v128,
          (unsigned int)&v111,
          (unsigned int)pNumArgs,
          (__int64)&v108);
        v105 = v114;
        if ( !(_QWORD)v114 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0x5EF,
            (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\common\\main.cpp",
            v104);
        v106 = (*(__int64 (__fastcall **)(struct IXamlHost *, _QWORD, _QWORD))(*(_QWORD *)v110 + 72LL))(
                 v110,
                 (v114 + 8) & ((unsigned __int128)-(__int128)(unsigned __int64)v114 >> 64),
                 *a2);
        if ( v106 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x5F0,
            (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\common\\main.cpp",
            (const char *)(unsigned int)v106,
            v107);
        RunMessageLoop(hWnd, v110);
        if ( v105 )
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IPopupXamlContentProvider,Microsoft::WRL::FtmBase>::Release(v105);
        goto LABEL_218;
      }
      LOBYTE(v108) = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminFlowRejuv_FeaturedReset>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AdminFlowRejuv_FeaturedReset>::GetImpl'::`2'::impl);
      LOBYTE(v81) = v108;
      if ( (*(int (__fastcall **)(struct IXamlHost *, HWND, __int64, __int64))(*(_QWORD *)v110 + 48LL))(
             v110,
             hWnd,
             424,
             v81) < 0 )
        goto LABEL_218;
      *(_QWORD *)&v114 = hWnd;
      *((_QWORD *)&v114 + 1) = v112;
      Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef((char *)&v114 + 8);
      std::function_Microsoft::WRL::ComPtr_IInspectable____cdecl_void__::operator___lambda_ee718c81d990b8e434e80cee96c435b6__0_(
        v128,
        &v114);
    }
    v23 = (struct SystemSettings::XamlHost::IXamlHostHelper **)&v114 + 1;
    goto LABEL_32;
  }
LABEL_219:
  RichEditDPIOverrider::~RichEditDPIOverrider((RichEditDPIOverrider *)&v118);
  if ( v4 >= 0 )
    RoUninitialize();
}

```

## disassembly

```asm
0x1400233a0  mov     [rsp-8+arg_0], rbx
0x1400233a5  mov     [rsp-8+arg_10], rsi
0x1400233aa  push    rbp
0x1400233ab  push    rdi
0x1400233ac  push    r12
0x1400233ae  push    r14
0x1400233b0  push    r15
0x1400233b2  lea     rbp, [rsp-120h]
0x1400233ba  sub     rsp, 220h
0x1400233c1  mov     rax, cs:__security_cookie
0x1400233c8  xor     rax, rsp
0x1400233cb  mov     [rbp+140h+var_30], rax
0x1400233d2  mov     r14, rdx
0x1400233d5  xor     ecx, ecx
0x1400233d7  call    cs:__imp_RoInitialize
0x1400233dd  mov     edi, eax
0x1400233df  mov     [rbp+140h+var_1B0], eax
0x1400233e2  xor     r12d, r12d
0x1400233e5  mov     esi, r12d
0x1400233e8  mov     [rbp+140h+var_1A0], r12
0x1400233ec  xor     r8d, r8d; dwFlags
0x1400233ef  xor     edx, edx; hFile
0x1400233f1  lea     rcx, aMsfteditDll; "MsftEdit.dll"
0x1400233f8  call    cs:__imp_LoadLibraryExW
0x1400233fe  mov     [rbp+140h+var_1A8], rax
0x140023402  test    rax, rax
0x140023405  jz      short loc_140023437
0x140023407  lea     rdx, aSettextservice; "SetTextServicesDpiCalculationOverride"
0x14002340e  mov     rcx, rax; hModule
0x140023411  call    cs:__imp_GetProcAddress
0x140023417  mov     rbx, rax
0x14002341a  test    rax, rax
0x14002341d  jz      short loc_140023437
0x14002341f  xor     edx, edx
0x140023421  lea     rcx, ?s_InitializeDPI@RichEditDPIOverrider@@KAXPEAXPEAJ1@Z; RichEditDPIOverrider::s_InitializeDPI(void *,long *,long *)
0x140023428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002342d  test    eax, eax
0x14002342f  cmovns  rsi, rbx
0x140023433  mov     [rbp+140h+var_1A0], rsi
0x140023437  test    edi, edi
0x140023439  js      loc_140024F66
0x14002343f  mov     [rsp+240h+hWnd], r12
0x140023444  mov     [rsp+240h+var_1F0], r12
0x140023449  mov     [rsp+240h+var_1E0], r12
0x14002344e  movzx   ebx, r12b
0x140023452  mov     byte ptr [rsp+240h+var_200], bl
0x140023456  lea     rcx, [rsp+240h+hWnd]; HWND *
0x14002345b  call    ?GetMosetWindowHandle@@YAJPEAPEAUHWND__@@@Z; GetMosetWindowHandle(HWND__ * *)
0x140023460  test    eax, eax
0x140023462  js      short loc_140023492
0x140023464  lea     rcx, [rsp+240h+var_1F0]
0x140023469  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14002346e  lea     r9, [rsp+240h+var_1F0]; void **
0x140023473  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x14002347a  call    ?XamlHost_CreateInstance@@YAJPEAUHINSTANCE__@@PEBGAEBU_GUID@@PEAPEAX@Z; XamlHost_CreateInstance(HINSTANCE__ *,ushort const *,_GUID const &,void * *)
0x14002347f  test    eax, eax
0x140023481  js      short loc_140023492
0x140023483  lea     rdx, [rsp+240h+var_1E0]
0x140023488  lea     rcx, [rsp+240h+var_1F0]
0x14002348d  call    ??$As@UIXamlHostHelper@XamlHost@SystemSettings@@@?$ComPtr@UIXamlHost@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIXamlHostHelper@XamlHost@SystemSettings@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IXamlHost>::As<SystemSettings::XamlHost::IXamlHostHelper>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SystemSettings::XamlHost::IXamlHostHelper>>)
0x140023492  mov     [rbp+140h+var_C8], r12
0x140023496  test    eax, eax
0x140023498  js      loc_140024F46
0x14002349e  mov     ecx, [r14]
0x1400234a1  cmp     ecx, 37h ; '7'
0x1400234a4  jg      loc_14002439C
0x1400234aa  jz      loc_140024309
0x1400234b0  mov     esi, 23h ; '#'
0x1400234b5  cmp     ecx, esi
0x1400234b7  jg      loc_140023CF2
0x1400234bd  jz      loc_140023C5B
0x1400234c3  cmp     ecx, 15h
0x1400234c6  jg      loc_14002386F
0x1400234cc  jz      loc_140023771
0x1400234d2  sub     ecx, 1
0x1400234d5  jz      loc_14002371D
0x1400234db  sub     ecx, 10h
0x1400234de  jz      loc_1400236A9
0x1400234e4  sub     ecx, 1
0x1400234e7  jz      loc_140023626
0x1400234ed  sub     ecx, 1
0x1400234f0  jz      loc_1400235A3
0x1400234f6  cmp     ecx, 1
0x1400234f9  jnz     loc_140024F46
0x1400234ff  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AdminFlowRejuv_AddDomainUserAndEditUser@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AdminFlowRejuv_AddDomainUserAndEditUser@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminFlowRejuv_AddDomainUserAndEditUser> `wil::Feature<__WilFeatureTraits_Feature_AdminFlowRejuv_AddDomainUserAndEditUser>::GetImpl(void)'::`2'::impl
0x140023506  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AdminFlowRejuv_AddDomainUserAndEditUser@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminFlowRejuv_AddDomainUserAndEditUser>::__private_IsEnabled(void)
0x14002350b  mov     r9d, ebx
0x14002350e  lea     edx, [rsi-22h]
0x140023511  test    al, al
0x140023513  cmovnz  r9d, edx
0x140023517  mov     byte ptr [rsp+240h+var_200], r9b
0x14002351c  mov     rcx, [rsp+240h+var_1F0]
0x140023521  mov     rax, [rcx]
0x140023524  mov     r8d, 12Ah
0x14002352a  mov     rdx, [rsp+240h+hWnd]
0x14002352f  mov     rax, [rax+30h]
0x140023533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023538  test    eax, eax
0x14002353a  js      loc_140024F46
0x140023540  mov     rdx, [r14+8]
0x140023544  lea     rcx, [rbp+140h+var_C0]
0x14002354b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140023550  movups  xmm1, xmmword ptr [rax]
0x140023553  movups  [rbp+140h+var_160], xmm1
0x140023557  movups  xmm0, xmmword ptr [rax+10h]
0x14002355b  movups  [rbp+140h+var_150], xmm0
0x14002355f  mov     [rax+10h], r12
0x140023563  mov     qword ptr [rax+18h], 7
0x14002356b  mov     [rax], r12w
0x14002356f  mov     rax, [rsp+240h+var_1E0]
0x140023574  mov     [rbp+140h+var_140], rax
0x140023578  lea     rcx, [rbp+140h+var_140]
0x14002357c  call    ?InternalAddRef@?$ComPtr@VCLanguageManagerSingleton@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(void)
0x140023581  lea     rdx, [rbp+140h+var_160]
0x140023585  lea     rcx, [rbp+140h+var_100]
0x140023589  call    std__function_Microsoft__WRL__ComPtr_IInspectable____cdecl_void____operator___lambda_003402c841f9bc38004ccaf9236a946e__0_
0x14002358e  lea     rcx, [rbp+140h+var_160]
0x140023592  call    _lambda_ef3041f8637048bb84cf09d9e64014cc_____lambda_ef3041f8637048bb84cf09d9e64014cc_
0x140023597  lea     rcx, [rbp+140h+var_C0]
0x14002359e  jmp     loc_140024EAB
0x1400235a3  mov     rcx, [rsp+240h+var_1F0]
0x1400235a8  mov     rax, [rcx]
0x1400235ab  xor     r9d, r9d
0x1400235ae  mov     r8d, 125h
0x1400235b4  mov     rdx, [rsp+240h+hWnd]
0x1400235b9  mov     rax, [rax+30h]
0x1400235bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400235c2  test    eax, eax
0x1400235c4  js      loc_140024F46
0x1400235ca  mov     rdx, [r14+8]
0x1400235ce  lea     rcx, [rbp+140h+var_C0]
0x1400235d5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400235da  movups  xmm1, xmmword ptr [rax]
0x1400235dd  movups  [rbp+140h+var_160], xmm1
0x1400235e1  movups  xmm0, xmmword ptr [rax+10h]
0x1400235e5  movups  [rbp+140h+var_150], xmm0
0x1400235e9  mov     [rax+10h], r12
0x1400235ed  mov     qword ptr [rax+18h], 7
0x1400235f5  mov     [rax], r12w
0x1400235f9  mov     rax, [rsp+240h+var_1E0]
0x1400235fe  mov     [rbp+140h+var_140], rax
0x140023602  lea     rcx, [rbp+140h+var_140]
0x140023606  call    ?InternalAddRef@?$ComPtr@VCLanguageManagerSingleton@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(void)
0x14002360b  lea     rdx, [rbp+140h+var_160]
0x14002360f  lea     rcx, [rbp+140h+var_100]
0x140023613  call    std__function_Microsoft__WRL__ComPtr_IInspectable____cdecl_void____operator___lambda_2aabe9215f06c25dd12354f8ee5b7eae__0_
0x140023618  lea     rcx, [rbp+140h+var_160]
0x14002361c  call    _lambda_ef3041f8637048bb84cf09d9e64014cc_____lambda_ef3041f8637048bb84cf09d9e64014cc_
0x140023621  jmp     loc_140023597
0x140023626  mov     rcx, [rsp+240h+var_1F0]
0x14002362b  mov     rax, [rcx]
0x14002362e  xor     r9d, r9d
0x140023631  mov     r8d, 0FDh
0x140023637  mov     rdx, [rsp+240h+hWnd]
0x14002363c  mov     rax, [rax+30h]
0x140023640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023645  test    eax, eax
0x140023647  js      loc_140024F46
0x14002364d  mov     rdx, [r14+8]
0x140023651  lea     rcx, [rbp+140h+var_C0]
0x140023658  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14002365d  movups  xmm1, xmmword ptr [rax]
0x140023660  movups  [rbp+140h+var_160], xmm1
0x140023664  movups  xmm0, xmmword ptr [rax+10h]
0x140023668  movups  [rbp+140h+var_150], xmm0
0x14002366c  mov     [rax+10h], r12
0x140023670  mov     qword ptr [rax+18h], 7
0x140023678  mov     [rax], r12w
0x14002367c  mov     rax, [rsp+240h+var_1E0]
0x140023681  mov     [rbp+140h+var_140], rax
0x140023685  lea     rcx, [rbp+140h+var_140]
0x140023689  call    ?InternalAddRef@?$ComPtr@VCLanguageManagerSingleton@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(void)
0x14002368e  lea     rdx, [rbp+140h+var_160]
0x140023692  lea     rcx, [rbp+140h+var_100]
0x140023696  call    std__function_Microsoft__WRL__ComPtr_IInspectable____cdecl_void____operator___lambda_4a0fc6e81b3f0353b97faa904326748e__0_
0x14002369b  lea     rcx, [rbp+140h+var_160]
0x14002369f  call    _lambda_ef3041f8637048bb84cf09d9e64014cc_____lambda_ef3041f8637048bb84cf09d9e64014cc_
0x1400236a4  jmp     loc_140023597
0x1400236a9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AdminFlowRejuv_AddDomainUserAndEditUser@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AdminFlowRejuv_AddDomainUserAndEditUser@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminFlowRejuv_AddDomainUserAndEditUser> `wil::Feature<__WilFeatureTraits_Feature_AdminFlowRejuv_AddDomainUserAndEditUser>::GetImpl(void)'::`2'::impl
0x1400236b0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AdminFlowRejuv_AddDomainUserAndEditUser@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminFlowRejuv_AddDomainUserAndEditUser>::__private_IsEnabled(void)
0x1400236b5  mov     r9d, ebx
0x1400236b8  mov     edx, 1
0x1400236bd  test    al, al
0x1400236bf  cmovnz  r9d, edx
0x1400236c3  mov     byte ptr [rsp+240h+var_200], r9b
0x1400236c8  mov     rcx, [rsp+240h+var_1F0]
0x1400236cd  mov     rax, [rcx]
0x1400236d0  mov     r8d, 162h
0x1400236d6  mov     rdx, [rsp+240h+hWnd]
0x1400236db  mov     rax, [rax+30h]
0x1400236df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400236e4  test    eax, eax
0x1400236e6  js      loc_140024F46
0x1400236ec  mov     rax, [rsp+240h+var_1E0]
0x1400236f1  mov     qword ptr [rsp+240h+pNumArgs], rax
0x1400236f6  lea     rcx, [rsp+240h+pNumArgs]
0x1400236fb  call    ?InternalAddRef@?$ComPtr@VCLanguageManagerSingleton@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(void)
0x140023700  lea     rdx, [rsp+240h+pNumArgs]
0x140023705  lea     rcx, [rbp+140h+var_100]
0x140023709  call    std__function_Microsoft__WRL__ComPtr_IInspectable____cdecl_void____operator___lambda_ceb3ceb7ed1466ab6d2e5c4995da4cdc__0_
0x14002370e  lea     rcx, [rsp+240h+pNumArgs]
0x140023713  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140023718  jmp     loc_140024EB0
0x14002371d  mov     edx, 1
0x140023722  mov     byte ptr [rsp+240h+var_200], dl
0x140023726  mov     rcx, [rsp+240h+var_1F0]
0x14002372b  mov     rax, [rcx]
0x14002372e  mov     r9b, dl
0x140023731  mov     r8d, 134h
0x140023737  mov     rdx, [rsp+240h+hWnd]
0x14002373c  mov     rax, [rax+30h]
0x140023740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023745  test    eax, eax
0x140023747  js      loc_140024F46
0x14002374d  mov     rax, [rsp+240h+var_1E0]
0x140023752  mov     qword ptr [rsp+240h+pNumArgs], rax
0x140023757  lea     rcx, [rsp+240h+pNumArgs]
0x14002375c  call    ?InternalAddRef@?$ComPtr@VCLanguageManagerSingleton@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(void)
0x140023761  lea     rdx, [rsp+240h+pNumArgs]
0x140023766  lea     rcx, [rbp+140h+var_100]
0x14002376a  call    std__function_Microsoft__WRL__ComPtr_IInspectable____cdecl_void____operator___lambda_bc8e759282621152223107ceb7952b08__0_
0x14002376f  jmp     short loc_14002370E
0x140023771  mov     [rsp+240h+pNumArgs], r12d
0x140023776  lea     rdx, [rsp+240h+pNumArgs]; pNumArgs
0x14002377b  mov     rcx, [r14+8]; lpCmdLine
0x14002377f  call    cs:__imp_CommandLineToArgvW
0x140023785  mov     rbx, rax
0x140023788  mov     qword ptr [rsp+240h+var_1D0], rax
0x14002378d  test    rax, rax
0x140023790  jz      loc_140023851
0x140023796  mov     edx, 1
0x14002379b  cmp     [rsp+240h+pNumArgs], edx
0x14002379f  jz      short loc_1400237B7
0x1400237a1  mov     dword ptr [r14+20h], 80028CA1h
0x1400237a9  mov     rcx, rax; hMem
0x1400237ac  call    cs:__imp_LocalFree
0x1400237b2  jmp     loc_140024F46
0x1400237b7  mov     rcx, [rsp+240h+var_1F0]
0x1400237bc  mov     rax, [rcx]
0x1400237bf  xor     r9d, r9d
0x1400237c2  mov     r8d, 0F9h
0x1400237c8  mov     rdx, [rsp+240h+hWnd]
0x1400237cd  mov     rax, [rax+30h]
0x1400237d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400237d6  mov     esi, eax
0x1400237d8  test    eax, eax
0x1400237da  js      short loc_140023843
0x1400237dc  mov     rdx, [rbx]
0x1400237df  lea     rcx, [rbp+140h+var_C0]
0x1400237e6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400237eb  movups  xmm1, xmmword ptr [rax]
0x1400237ee  movups  [rbp+140h+var_160], xmm1
0x1400237f2  movups  xmm0, xmmword ptr [rax+10h]
0x1400237f6  movups  [rbp+140h+var_150], xmm0
0x1400237fa  mov     [rax+10h], r12
0x1400237fe  mov     qword ptr [rax+18h], 7
0x140023806  mov     [rax], r12w
0x14002380a  mov     byte ptr [rbp+140h+var_140], r12b
0x14002380e  mov     rax, [rsp+240h+var_1E0]
0x140023813  mov     qword ptr [rbp+140h+var_138], rax
0x140023817  lea     rcx, [rbp+140h+var_138]
0x14002381b  call    ?InternalAddRef@?$ComPtr@VCLanguageManagerSingleton@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CLanguageManagerSingleton>::InternalAddRef(void)
0x140023820  lea     rdx, [rbp+140h+var_160]
0x140023824  lea     rcx, [rbp+140h+var_100]
0x140023828  call    std__function_Microsoft__WRL__ComPtr_IInspectable____cdecl_void____operator___lambda_d03e81677f3b08d48ec4ee8801d9d33a__0_
0x14002382d  lea     rcx, [rbp+140h+var_160]
0x140023831  call    _lambda_d03e81677f3b08d48ec4ee8801d9d33a_____lambda_d03e81677f3b08d48ec4ee8801d9d33a_
0x140023836  lea     rcx, [rbp+140h+var_C0]
0x14002383d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140023842  nop
0x140023843  mov     rcx, rbx; hMem
0x140023846  call    cs:__imp_LocalFree
0x14002384c  jmp     loc_140024954
0x140023851  call    cs:__imp_GetLastError
0x140023857  mov     esi, eax
0x140023859  test    eax, eax
0x14002385b  jle     short loc_140023866
0x14002385d  movzx   esi, ax
0x140023860  or      esi, 80070000h
0x140023866  mov     [r14+20h], esi
0x14002386a  jmp     loc_140024954
0x14002386f  sub     ecx, 16h
0x140023872  jz      loc_140023BDB
0x140023878  sub     ecx, 6
0x14002387b  jz      loc_140023B4B
0x140023881  sub     ecx, 1
0x140023884  jz      loc_140023916
0x14002388a  cmp     ecx, 5
0x14002388d  jnz     loc_140024F46
0x140023893  mov     rcx, [rsp+240h+var_1F0]
0x140023898  mov     rax, [rcx]
0x14002389b  xor     r9d, r9d
0x14002389e  mov     r8d, 0BCh
0x1400238a4  mov     rdx, [rsp+240h+hWnd]
0x1400238a9  mov     rax, [rax+30h]
0x1400238ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400238b2  test    eax, eax
0x1400238b4  js      loc_140024F46
0x1400238ba  mov     rdx, [r14+8]
0x1400238be  lea     rcx, [rbp+140h+var_C0]
  ... truncated ...
```
