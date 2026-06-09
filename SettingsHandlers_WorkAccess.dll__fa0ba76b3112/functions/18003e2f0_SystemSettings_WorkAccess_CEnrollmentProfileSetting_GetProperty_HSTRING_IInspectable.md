# SystemSettings::WorkAccess::CEnrollmentProfileSetting::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x18003e2f0`
- end: `0x18003e76c`
- name: `?GetProperty@CEnrollmentProfileSetting@WorkAccess@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `1148`
- prototype: `int(SystemSettings::WorkAccess::CEnrollmentProfileSetting *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800076ac`
- `0x1800096ec`
- `0x180011898`
- `0x180011a14`
- `0x180015000`
- `0x18001ce98`
- `0x180020584`
- `0x18003bb58`
- `0x18003d944`
- `0x18003e2f0`
- `0x1800476b8`
- `0x18004862c`
- `0x180052010`

## import_xrefs

- `policymanager!PolicyManager_GetPolicyInt` at `0x18003e501`
- `policymanager!PolicyManager_GetPolicyInt` at `0x18003e5a8`
- `policymanager!PolicyManager_GetPolicyInt` at `0x18003e501`
- `policymanager!PolicyManager_GetPolicyInt` at `0x18003e5a8`

## string_xrefs

- `0x18003e375`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003e4a8`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003e518`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003e691`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003e6fe`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003e746`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003e55f`: `SystemSettings_WorkAccess_DisconnectConfirmation`
- `0x18003e53f`: `CorpDeviceManagementRemoveNotAllowedText`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::WorkAccess::CEnrollmentProfileSetting::GetProperty(
        SystemSettings::WorkAccess::CEnrollmentProfileSetting *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  const unsigned __int16 *v6; // r8
  int String; // eax
  int PolicyInt; // edi
  __int64 v9; // rdx
  unsigned __int16 **v10; // rcx
  int v12; // edx
  const unsigned __int16 *v13; // r8
  struct IInspectable **v14; // r9
  int CompanyTextResourceStringInHandler; // ebx
  __int64 v16; // rdx
  int v17; // edx
  const unsigned __int16 *v18; // r8
  struct IInspectable **v19; // r9
  const unsigned __int16 *v20; // r8
  const unsigned __int16 *v21; // r8
  int v22; // eax
  __int64 v23; // rdx
  const unsigned __int16 *v24; // r8
  __int64 v25; // rdx
  const unsigned __int16 *v26; // r8
  unsigned __int8 v27; // r8
  int v28; // eax
  int v29; // eax
  __int64 v30; // rdx
  unsigned __int16 *v31; // [rsp+20h] [rbp-30h] BYREF
  __int64 v32; // [rsp+28h] [rbp-28h]
  __int64 v33; // [rsp+30h] [rbp-20h]
  unsigned __int16 *v34[3]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  __int64 (__fastcall ***v36)(_QWORD, GUID *, struct IInspectable **); // [rsp+80h] [rbp+30h] BYREF

  *a3 = 0;
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005DE50, (const unsigned __int16 *)a3) )
  {
    v31 = 0;
    v32 = 0;
    v33 = 0;
    String = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
               &v31,
               &_ImageBase,
               102);
    PolicyInt = String;
    if ( String < 0 )
    {
      v9 = 381;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
        (const char *)(unsigned int)String,
        (int)v31);
      v10 = &v31;
LABEL_7:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v10);
      return (unsigned int)PolicyInt;
    }
    String = SystemSettings::DataModel::PropValueHelper::CreateString(v31, a3);
    PolicyInt = String;
    if ( String < 0 )
    {
      v9 = 382;
      goto LABEL_6;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v31);
    return 0;
  }
  if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005DEE0, v6) )
  {
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005DED0, v13) )
    {
      CompanyTextResourceStringInHandler = SystemSettings::WorkAccess::GetCompanyTextResourceStringInHandler(
                                             (SystemSettings::WorkAccess *)0x6A,
                                             v17,
                                             (int)a3,
                                             v19);
      if ( CompanyTextResourceStringInHandler < 0 )
      {
        v16 = 397;
        goto LABEL_62;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005D188, v18) )
    {
      CompanyTextResourceStringInHandler = SystemSettings::DataModel::PropValueHelper::CreateBoolean(
                                             *((_BYTE *)this + 332),
                                             a3);
      if ( CompanyTextResourceStringInHandler < 0 )
      {
        v16 = 401;
        goto LABEL_62;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005DF50, v20) )
    {
      v36 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
      v22 = SystemSettings::WorkAccess::CEnrollmentRemoveProfileSetting::CreateInstance(
              *((_QWORD *)this + 38),
              *((_DWORD *)this + 82),
              &v36);
      PolicyInt = v22;
      if ( v22 >= 0 )
      {
        v22 = (**v36)(v36, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, a3);
        PolicyInt = v22;
        if ( v22 >= 0 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
          return 0;
        }
        v23 = 408;
      }
      else
      {
        v23 = 407;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
        (const char *)(unsigned int)v22,
        (int)v31);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
      return (unsigned int)PolicyInt;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005DF00, v21) )
    {
      LODWORD(v36) = 0;
      PolicyInt = PolicyManager_GetPolicyInt(L"Experience", L"AllowManualMDMUnenrollment", &v36);
      if ( PolicyInt >= 0 )
      {
        if ( (_DWORD)v36 == 1 )
        {
          CompanyTextResourceStringInHandler = SystemSettings::DataModel::PropValueHelper::CreateString(
                                                 L"SystemSettings_WorkAccess_DisconnectConfirmation",
                                                 a3);
          if ( CompanyTextResourceStringInHandler < 0 )
          {
            v16 = 420;
            goto LABEL_62;
          }
        }
        else
        {
          CompanyTextResourceStringInHandler = SystemSettings::DataModel::PropValueHelper::CreateString(
                                                 L"CorpDeviceManagementRemoveNotAllowedText",
                                                 a3);
          if ( CompanyTextResourceStringInHandler < 0 )
          {
            v16 = 416;
            goto LABEL_62;
          }
        }
        return 0;
      }
      v25 = 413;
LABEL_30:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
        (const char *)(unsigned int)PolicyInt,
        (int)v31);
      return (unsigned int)PolicyInt;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005E068, v24) )
    {
      LODWORD(v36) = 0;
      PolicyInt = PolicyManager_GetPolicyInt(L"Experience", L"AllowManualMDMUnenrollment", &v36);
      if ( PolicyInt >= 0 )
      {
        v27 = 1;
        if ( (_DWORD)v36 != 1 || ((1LL << *((_DWORD *)this + 82)) & 0x8000001) == 0 )
          v27 = 0;
        CompanyTextResourceStringInHandler = SystemSettings::DataModel::PropValueHelper::CreateBoolean(v27, a3);
        if ( CompanyTextResourceStringInHandler < 0 )
        {
          v16 = 428;
          goto LABEL_62;
        }
        return 0;
      }
      v25 = 426;
      goto LABEL_30;
    }
    if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005E038, v26) )
    {
      CompanyTextResourceStringInHandler = -2147024809;
      v16 = 458;
      goto LABEL_62;
    }
    PolicyInt = SystemSettings::WorkAccess::CEnrollmentHelper::PopulateIDs();
    if ( PolicyInt < 0 )
    {
      v25 = 432;
      goto LABEL_30;
    }
    PolicyInt = SystemSettings::WorkAccess::CEnrollmentHelper::GetOmadmValue(4u);
    if ( PolicyInt < 0 )
    {
      v25 = 433;
      goto LABEL_30;
    }
    memset(v34, 0, sizeof(v34));
    if ( SystemSettings::WorkAccess::CEnrollmentHelper::_value && *SystemSettings::WorkAccess::CEnrollmentHelper::_value )
    {
      v28 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
              v34,
              &_ImageBase,
              106);
      PolicyInt = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1C3,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
          (const char *)(unsigned int)v28,
          (int)v31);
LABEL_60:
        v10 = v34;
        goto LABEL_7;
      }
LABEL_59:
      PolicyInt = SystemSettings::DataModel::PropValueHelper::CreateString(v34[0], a3);
      goto LABEL_60;
    }
    v31 = 0;
    v32 = 0;
    v33 = 0;
    v29 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
            &v31,
            &_ImageBase,
            109);
    PolicyInt = v29;
    if ( v29 >= 0 )
    {
      v29 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
              v34,
              &_ImageBase,
              106);
      PolicyInt = v29;
      if ( v29 >= 0 )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v31);
        goto LABEL_59;
      }
      v30 = 445;
    }
    else
    {
      v30 = 441;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
      (const char *)(unsigned int)v29,
      (int)v31);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v31);
    goto LABEL_60;
  }
  CompanyTextResourceStringInHandler = SystemSettings::WorkAccess::GetCompanyTextResourceStringInHandler(
                                         (SystemSettings::WorkAccess *)0x67,
                                         v12,
                                         (int)a3,
                                         v14);
  if ( CompanyTextResourceStringInHandler >= 0 )
    return 0;
  v16 = 389;
LABEL_62:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
    (const char *)(unsigned int)CompanyTextResourceStringInHandler,
    (int)v31);
  return (unsigned int)CompanyTextResourceStringInHandler;
}

```

## disassembly

```asm
0x18003e2f0  mov     [rsp-18h+arg_0], rbx
0x18003e2f5  mov     [rsp-18h+arg_8], rsi
0x18003e2fa  push    rbp
0x18003e2fb  push    rdi
0x18003e2fc  push    r14
0x18003e2fe  mov     rbp, rsp
0x18003e301  sub     rsp, 50h
0x18003e305  mov     rbx, r8
0x18003e308  mov     rdi, rdx
0x18003e30b  mov     rsi, rcx
0x18003e30e  xor     r14d, r14d
0x18003e311  mov     [r8], r14
0x18003e314  lea     rdx, stru_18005DE50; HSTRING
0x18003e31b  mov     rcx, rdi; this
0x18003e31e  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18003e323  test    al, al
0x18003e325  jz      short loc_18003E3A5
0x18003e327  mov     [rbp+var_30], r14
0x18003e32b  mov     [rbp+var_28], r14
0x18003e32f  mov     [rbp+var_20], r14
0x18003e333  mov     r9, [rsi+100h]
0x18003e33a  lea     r8d, [r14+66h]
0x18003e33e  lea     rdx, __ImageBase
0x18003e345  lea     rcx, [rbp+var_30]
0x18003e349  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x18003e34e  mov     edi, eax
0x18003e350  test    eax, eax
0x18003e352  jns     short loc_18003E35B
0x18003e354  mov     edx, 17Dh
0x18003e359  jmp     short loc_18003E372
0x18003e35b  mov     rdx, rbx; struct IInspectable **
0x18003e35e  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x18003e362  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18003e367  mov     edi, eax
0x18003e369  test    eax, eax
0x18003e36b  jns     short loc_18003E395
0x18003e36d  mov     edx, 17Eh; void *
0x18003e372  mov     r9d, eax; char *
0x18003e375  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003e37c  mov     rcx, [rbp+18h]; this
0x18003e380  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e385  lea     rcx, [rbp+var_30]
0x18003e389  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003e38e  mov     eax, edi
0x18003e390  jmp     loc_18003E758
0x18003e395  lea     rcx, [rbp+var_30]
0x18003e399  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003e39e  xor     eax, eax
0x18003e3a0  jmp     loc_18003E758
0x18003e3a5  lea     rdx, stru_18005DEE0; HSTRING
0x18003e3ac  mov     rcx, rdi; this
0x18003e3af  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18003e3b4  test    al, al
0x18003e3b6  jz      short loc_18003E3D5
0x18003e3b8  mov     r8, rbx; int
0x18003e3bb  mov     ecx, 67h ; 'g'; this
0x18003e3c0  call    ?GetCompanyTextResourceStringInHandler@WorkAccess@SystemSettings@@YAJHHPEAPEAUIInspectable@@@Z; SystemSettings::WorkAccess::GetCompanyTextResourceStringInHandler(int,int,IInspectable * *)
0x18003e3c5  mov     ebx, eax
0x18003e3c7  test    eax, eax
0x18003e3c9  jns     short loc_18003E39E
0x18003e3cb  mov     edx, 185h
0x18003e3d0  jmp     loc_18003E743
0x18003e3d5  lea     rdx, stru_18005DED0; HSTRING
0x18003e3dc  mov     rcx, rdi; this
0x18003e3df  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18003e3e4  test    al, al
0x18003e3e6  jz      short loc_18003E405
0x18003e3e8  mov     r8, rbx; int
0x18003e3eb  mov     ecx, 6Ah ; 'j'; this
0x18003e3f0  call    ?GetCompanyTextResourceStringInHandler@WorkAccess@SystemSettings@@YAJHHPEAPEAUIInspectable@@@Z; SystemSettings::WorkAccess::GetCompanyTextResourceStringInHandler(int,int,IInspectable * *)
0x18003e3f5  mov     ebx, eax
0x18003e3f7  test    eax, eax
0x18003e3f9  jns     short loc_18003E39E
0x18003e3fb  mov     edx, 18Dh
0x18003e400  jmp     loc_18003E743
0x18003e405  lea     rdx, stru_18005D188; HSTRING
0x18003e40c  mov     rcx, rdi; this
0x18003e40f  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18003e414  test    al, al
0x18003e416  jz      short loc_18003E43A
0x18003e418  mov     rdx, rbx; struct IInspectable **
0x18003e41b  mov     cl, [rsi+14Ch]; unsigned __int8
0x18003e421  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x18003e426  mov     ebx, eax
0x18003e428  test    eax, eax
0x18003e42a  jns     loc_18003E39E
0x18003e430  mov     edx, 191h
0x18003e435  jmp     loc_18003E743
0x18003e43a  lea     rdx, stru_18005DF50; HSTRING
0x18003e441  mov     rcx, rdi; this
0x18003e444  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18003e449  test    al, al
0x18003e44b  jz      loc_18003E4D4
0x18003e451  mov     [rbp+arg_10], r14
0x18003e455  lea     rcx, [rbp+arg_10]
0x18003e459  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e45e  lea     r8, [rbp+arg_10]
0x18003e462  mov     edx, [rsi+148h]
0x18003e468  mov     rcx, [rsi+130h]
0x18003e46f  call    ?CreateInstance@CEnrollmentRemoveProfileSetting@WorkAccess@SystemSettings@@SAJPEBGW4EnrollmentEnrollType@@PEAPEAV123@@Z; SystemSettings::WorkAccess::CEnrollmentRemoveProfileSetting::CreateInstance(ushort const *,EnrollmentEnrollType,SystemSettings::WorkAccess::CEnrollmentRemoveProfileSetting * *)
0x18003e474  mov     edi, eax
0x18003e476  test    eax, eax
0x18003e478  jns     short loc_18003E481
0x18003e47a  mov     edx, 197h
0x18003e47f  jmp     short loc_18003E4A5
0x18003e481  mov     rcx, [rbp+arg_10]
0x18003e485  mov     rax, [rcx]
0x18003e488  mov     r8, rbx
0x18003e48b  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18003e492  mov     rax, [rax]
0x18003e495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e49a  mov     edi, eax
0x18003e49c  test    eax, eax
0x18003e49e  jns     short loc_18003E4C6
0x18003e4a0  mov     edx, 198h; void *
0x18003e4a5  mov     r9d, eax; char *
0x18003e4a8  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003e4af  mov     rcx, [rbp+18h]; this
0x18003e4b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e4b8  lea     rcx, [rbp+arg_10]
0x18003e4bc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e4c1  jmp     loc_18003E38E
0x18003e4c6  lea     rcx, [rbp+arg_10]
0x18003e4ca  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e4cf  jmp     loc_18003E39E
0x18003e4d4  lea     rdx, stru_18005DF00; HSTRING
0x18003e4db  mov     rcx, rdi; this
0x18003e4de  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18003e4e3  test    al, al
0x18003e4e5  jz      loc_18003E57F
0x18003e4eb  mov     dword ptr [rbp+arg_10], r14d
0x18003e4ef  lea     r8, [rbp+arg_10]
0x18003e4f3  lea     rdx, aAllowmanualmdm; "AllowManualMDMUnenrollment"
0x18003e4fa  lea     rcx, aExperience; "Experience"
0x18003e501  call    cs:__imp_PolicyManager_GetPolicyInt
0x18003e508  nop     dword ptr [rax+rax+00h]
0x18003e50d  mov     edi, eax
0x18003e50f  test    eax, eax
0x18003e511  jns     short loc_18003E530
0x18003e513  mov     edx, 19Dh; void *
0x18003e518  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003e51f  mov     r9d, edi; char *
0x18003e522  mov     rcx, [rbp+18h]; this
0x18003e526  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e52b  jmp     loc_18003E38E
0x18003e530  mov     r8d, 1
0x18003e536  mov     rdx, rbx; struct IInspectable **
0x18003e539  cmp     dword ptr [rbp+arg_10], r8d
0x18003e53d  jz      short loc_18003E55F
0x18003e53f  lea     rcx, aCorpdevicemana; "CorpDeviceManagementRemoveNotAllowedTex"...
0x18003e546  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18003e54b  mov     ebx, eax
0x18003e54d  test    eax, eax
0x18003e54f  jns     loc_18003E39E
0x18003e555  mov     edx, 1A0h
0x18003e55a  jmp     loc_18003E743
0x18003e55f  lea     rcx, aSystemsettings_7; "SystemSettings_WorkAccess_DisconnectCon"...
0x18003e566  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18003e56b  mov     ebx, eax
0x18003e56d  test    eax, eax
0x18003e56f  jns     loc_18003E39E
0x18003e575  mov     edx, 1A4h
0x18003e57a  jmp     loc_18003E743
0x18003e57f  lea     rdx, stru_18005E068; HSTRING
0x18003e586  mov     rcx, rdi; this
0x18003e589  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18003e58e  test    al, al
0x18003e590  jz      short loc_18003E606
0x18003e592  mov     dword ptr [rbp+arg_10], r14d
0x18003e596  lea     r8, [rbp+arg_10]
0x18003e59a  lea     rdx, aAllowmanualmdm; "AllowManualMDMUnenrollment"
0x18003e5a1  lea     rcx, aExperience; "Experience"
0x18003e5a8  call    cs:__imp_PolicyManager_GetPolicyInt
0x18003e5af  nop     dword ptr [rax+rax+00h]
0x18003e5b4  mov     edi, eax
0x18003e5b6  test    eax, eax
0x18003e5b8  jns     short loc_18003E5C4
0x18003e5ba  mov     edx, 1AAh
0x18003e5bf  jmp     loc_18003E518
0x18003e5c4  mov     r8d, 1
0x18003e5ca  cmp     dword ptr [rbp+arg_10], r8d
0x18003e5ce  jnz     short loc_18003E5E4
0x18003e5d0  mov     ecx, [rsi+148h]
0x18003e5d6  mov     eax, r8d
0x18003e5d9  shl     rax, cl
0x18003e5dc  test    rax, 8000001h
0x18003e5e2  jnz     short loc_18003E5E7
0x18003e5e4  mov     r8b, r14b
0x18003e5e7  mov     rdx, rbx; struct IInspectable **
0x18003e5ea  mov     cl, r8b; unsigned __int8
0x18003e5ed  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x18003e5f2  mov     ebx, eax
0x18003e5f4  test    eax, eax
0x18003e5f6  jns     loc_18003E39E
0x18003e5fc  mov     edx, 1ACh
0x18003e601  jmp     loc_18003E743
0x18003e606  lea     rdx, stru_18005E038; HSTRING
0x18003e60d  mov     rcx, rdi; this
0x18003e610  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18003e615  test    al, al
0x18003e617  jz      loc_18003E739
0x18003e61d  call    ?PopulateIDs@CEnrollmentHelper@WorkAccess@SystemSettings@@SAJXZ; SystemSettings::WorkAccess::CEnrollmentHelper::PopulateIDs(void)
0x18003e622  mov     edi, eax
0x18003e624  test    eax, eax
0x18003e626  jns     short loc_18003E632
0x18003e628  mov     edx, 1B0h
0x18003e62d  jmp     loc_18003E518
0x18003e632  mov     ecx, 4; unsigned int
0x18003e637  call    ?GetOmadmValue@CEnrollmentHelper@WorkAccess@SystemSettings@@SAJK@Z; SystemSettings::WorkAccess::CEnrollmentHelper::GetOmadmValue(ulong)
0x18003e63c  mov     edi, eax
0x18003e63e  test    eax, eax
0x18003e640  jns     short loc_18003E64C
0x18003e642  mov     edx, 1B1h
0x18003e647  jmp     loc_18003E518
0x18003e64c  mov     [rbp+var_18], r14
0x18003e650  mov     [rbp+var_10], r14
0x18003e654  mov     [rbp+var_8], r14
0x18003e658  mov     r9, cs:?_value@CEnrollmentHelper@WorkAccess@SystemSettings@@2PEAGEA; ushort * SystemSettings::WorkAccess::CEnrollmentHelper::_value
0x18003e65f  test    r9, r9
0x18003e662  jz      short loc_18003E6A7
0x18003e664  cmp     r14w, [r9]
0x18003e668  jz      short loc_18003E6A7
0x18003e66a  mov     r8d, 6Ah ; 'j'
0x18003e670  lea     rdx, __ImageBase
0x18003e677  lea     rcx, [rbp+var_18]
0x18003e67b  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x18003e680  mov     edi, eax
0x18003e682  test    eax, eax
0x18003e684  jns     loc_18003E722
0x18003e68a  mov     rcx, [rbp+18h]; this
0x18003e68e  mov     r9d, eax; char *
0x18003e691  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003e698  mov     edx, 1C3h; void *
0x18003e69d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e6a2  jmp     loc_18003E730
0x18003e6a7  mov     [rbp+var_30], r14
0x18003e6ab  mov     [rbp+var_28], r14
0x18003e6af  mov     [rbp+var_20], r14
0x18003e6b3  mov     r8d, 6Dh ; 'm'
0x18003e6b9  lea     rdx, __ImageBase
0x18003e6c0  lea     rcx, [rbp+var_30]
0x18003e6c4  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x18003e6c9  mov     edi, eax
0x18003e6cb  test    eax, eax
0x18003e6cd  jns     short loc_18003E6D6
0x18003e6cf  mov     edx, 1B9h
0x18003e6d4  jmp     short loc_18003E6FB
0x18003e6d6  mov     r9, [rbp+var_30]
0x18003e6da  mov     r8d, 6Ah ; 'j'
0x18003e6e0  lea     rdx, __ImageBase
0x18003e6e7  lea     rcx, [rbp+var_18]
0x18003e6eb  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x18003e6f0  mov     edi, eax
0x18003e6f2  test    eax, eax
0x18003e6f4  jns     short loc_18003E719
0x18003e6f6  mov     edx, 1BDh; void *
0x18003e6fb  mov     r9d, eax; char *
0x18003e6fe  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003e705  mov     rcx, [rbp+18h]; this
0x18003e709  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e70e  lea     rcx, [rbp+var_30]
0x18003e712  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003e717  jmp     short loc_18003E730
0x18003e719  lea     rcx, [rbp+var_30]
0x18003e71d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003e722  mov     rdx, rbx; struct IInspectable **
0x18003e725  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x18003e729  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18003e72e  mov     edi, eax
0x18003e730  lea     rcx, [rbp+var_18]
0x18003e734  jmp     loc_18003E389
0x18003e739  mov     ebx, 80070057h
0x18003e73e  mov     edx, 1CAh; void *
0x18003e743  mov     r9d, ebx; char *
0x18003e746  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003e74d  mov     rcx, [rbp+18h]; this
0x18003e751  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e756  mov     eax, ebx
0x18003e758  mov     rbx, [rsp+50h+arg_0]
0x18003e75d  mov     rsi, [rsp+50h+arg_8]
0x18003e762  add     rsp, 50h
0x18003e766  pop     r14
0x18003e768  pop     rdi
0x18003e769  pop     rbp
0x18003e76a  retn
```
