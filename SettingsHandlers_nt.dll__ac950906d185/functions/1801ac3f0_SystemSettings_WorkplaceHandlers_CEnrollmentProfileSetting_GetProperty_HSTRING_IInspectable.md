# SystemSettings::WorkplaceHandlers::CEnrollmentProfileSetting::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x1801ac3f0`
- end: `0x1801ac832`
- name: `?GetProperty@CEnrollmentProfileSetting@WorkplaceHandlers@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `1090`
- prototype: `int(SystemSettings::WorkplaceHandlers::CEnrollmentProfileSetting *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180011bb0`
- `0x180019a20`
- `0x180020170`
- `0x1800201c4`
- `0x180021398`
- `0x180032208`
- `0x18004d1ac`
- `0x1801a9710`
- `0x1801aa644`
- `0x1801ac3f0`
- `0x1801b0b90`
- `0x180289010`

## import_xrefs

- `policymanager!PolicyManager_GetPolicyInt` at `0x1801ac6de`
- `policymanager!PolicyManager_GetPolicyInt` at `0x1801ac7c3`
- `policymanager!PolicyManager_GetPolicyInt` at `0x1801ac6de`
- `policymanager!PolicyManager_GetPolicyInt` at `0x1801ac7c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ac489`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ac4ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ac500`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ac568`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ac489`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ac4ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ac500`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ac568`

## string_xrefs

- `0x1801ac707`: `CorpDeviceManagementRemoveNotAllowedText`
- `0x1801ac732`: `CorpDeviceManagementRemoveNotAllowedWorkDeviceWithAAD`
- `0x1801ac4a1`: `SystemSettings_Workplace_CorpDeviceManagement_NoCompanyText`
- `0x1801ac580`: `SystemSettings_Workplace_CorpDeviceManagement_NoCompanyRemoveText`
- `0x1801ac757`: `CorpDeviceManagementRemoveNotAllowedWorkFullWithAAD`
- `0x1801ac777`: `CorpDeviceManagementRemoveText`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall SystemSettings::WorkplaceHandlers::CEnrollmentProfileSetting::GetProperty(
        SystemSettings::WorkplaceHandlers::CEnrollmentProfileSetting *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  const unsigned __int16 *v6; // r8
  const unsigned __int16 *v8; // r8
  int OmadmValue; // ebx
  __int64 v10; // rdx
  HSTRING *v11; // r8
  int ResourceStringById; // eax
  int v13; // esi
  HSTRING v14; // rbx
  __int64 v15; // rdx
  const unsigned __int16 *v16; // r8
  HSTRING *v17; // r8
  const unsigned __int16 *v18; // r8
  const unsigned __int16 *v19; // r8
  int v20; // eax
  __int64 v21; // rdx
  const unsigned __int16 *v22; // r8
  int v23; // eax
  unsigned __int8 v24; // bl
  int v25; // eax
  int v26; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+20h]
  HSTRING string; // [rsp+60h] [rbp+38h] BYREF

  *a3 = 0;
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1803198F0, (const unsigned __int16 *)a3) )
    return SystemSettings::DataModel::PropValueHelper::CreateString(*((const unsigned __int16 **)this + 32), a3);
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031D120, v6) )
  {
    OmadmValue = SystemSettings::WorkplaceHandlers::CEnrollmentHelper::GetOmadmValue(3u);
    if ( OmadmValue < 0 )
    {
      v10 = 1362;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\workplace\\src\\corpdevicemanagement.cpp",
        (const char *)(unsigned int)OmadmValue,
        v26);
      return OmadmValue;
    }
    if ( SystemSettings::WorkplaceHandlers::CEnrollmentHelper::_value )
    {
      OmadmValue = SystemSettings::DataModel::PropValueHelper::CreateString(
                     (const unsigned __int16 *)SystemSettings::WorkplaceHandlers::CEnrollmentHelper::_value,
                     a3);
      if ( OmadmValue < 0 )
      {
        v10 = 1371;
        goto LABEL_6;
      }
      return 0;
    }
    WindowsDeleteString(0);
    string = 0;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                           (SystemSettings::DataModel *)L"SystemSettings_Workplace_CorpDeviceManagement_NoCompanyText",
                           &string,
                           v11);
    v13 = ResourceStringById;
    v14 = string;
    if ( ResourceStringById < 0 )
    {
      v15 = 1366;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\workplace\\src\\corpdevicemanagement.cpp",
        (const char *)(unsigned int)ResourceStringById,
        v26);
      WindowsDeleteString(v14);
      return v13;
    }
    ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
    v13 = ResourceStringById;
    if ( ResourceStringById < 0 )
    {
      v15 = 1367;
      goto LABEL_13;
    }
LABEL_14:
    WindowsDeleteString(v14);
    return 0;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031D3D8, v8) )
  {
    OmadmValue = SystemSettings::WorkplaceHandlers::CEnrollmentHelper::GetOmadmValue(3u);
    if ( OmadmValue < 0 )
    {
      v10 = 1376;
      goto LABEL_6;
    }
    if ( SystemSettings::WorkplaceHandlers::CEnrollmentHelper::_value )
    {
      OmadmValue = SystemSettings::DataModel::PropValueHelper::CreateString(
                     (const unsigned __int16 *)SystemSettings::WorkplaceHandlers::CEnrollmentHelper::_value,
                     a3);
      if ( OmadmValue < 0 )
      {
        v10 = 1385;
        goto LABEL_6;
      }
      return 0;
    }
    WindowsDeleteString(0);
    string = 0;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                           (SystemSettings::DataModel *)L"SystemSettings_Workplace_CorpDeviceManagement_NoCompanyRemoveText",
                           &string,
                           v17);
    v13 = ResourceStringById;
    v14 = string;
    if ( ResourceStringById < 0 )
    {
      v15 = 1380;
      goto LABEL_13;
    }
    ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
    v13 = ResourceStringById;
    if ( ResourceStringById < 0 )
    {
      v15 = 1381;
      goto LABEL_13;
    }
    goto LABEL_14;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031D108, v16) )
  {
    OmadmValue = SystemSettings::DataModel::PropValueHelper::CreateBoolean(*((_BYTE *)this + 332), a3);
    if ( OmadmValue < 0 )
    {
      v10 = 1390;
      goto LABEL_6;
    }
    return 0;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802EDCB0, v18) )
  {
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
    v20 = SystemSettings::WorkplaceHandlers::CEnrollmentRemoveProfileSetting::CreateInstance(
            *((_QWORD *)this + 38),
            *((unsigned int *)this + 82),
            &string);
    OmadmValue = v20;
    if ( v20 >= 0 )
    {
      v20 = (**(__int64 (__fastcall ***)(HSTRING, GUID *, struct IInspectable **))string)(
              string,
              &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
              a3);
      OmadmValue = v20;
      if ( v20 >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
        return 0;
      }
      v21 = 1397;
    }
    else
    {
      v21 = 1396;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\workplace\\src\\corpdevicemanagement.cpp",
      (const char *)(unsigned int)v20,
      v26);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
    return OmadmValue;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031D490, v19) )
  {
    LODWORD(string) = 0;
    OmadmValue = PolicyManager_GetPolicyInt(L"Experience", L"AllowManualMDMUnenrollment", &string);
    if ( OmadmValue < 0 )
    {
      v10 = 1402;
      goto LABEL_6;
    }
    if ( (_DWORD)string == 1 )
    {
      v23 = *((_DWORD *)this + 82);
      if ( v23 == 6 )
      {
        OmadmValue = SystemSettings::DataModel::PropValueHelper::CreateString(
                       L"CorpDeviceManagementRemoveNotAllowedWorkDeviceWithAAD",
                       a3);
        if ( OmadmValue < 0 )
        {
          v10 = 1409;
          goto LABEL_6;
        }
      }
      else if ( v23 == 13 )
      {
        OmadmValue = SystemSettings::DataModel::PropValueHelper::CreateString(
                       L"CorpDeviceManagementRemoveNotAllowedWorkFullWithAAD",
                       a3);
        if ( OmadmValue < 0 )
        {
          v10 = 1413;
          goto LABEL_6;
        }
      }
      else
      {
        OmadmValue = SystemSettings::DataModel::PropValueHelper::CreateString(L"CorpDeviceManagementRemoveText", a3);
        if ( OmadmValue < 0 )
        {
          v10 = 1417;
          goto LABEL_6;
        }
      }
    }
    else
    {
      OmadmValue = SystemSettings::DataModel::PropValueHelper::CreateString(
                     L"CorpDeviceManagementRemoveNotAllowedText",
                     a3);
      if ( OmadmValue < 0 )
      {
        v10 = 1405;
        goto LABEL_6;
      }
    }
    return 0;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18031DB28, v22) )
  {
    LODWORD(string) = 0;
    OmadmValue = PolicyManager_GetPolicyInt(L"Experience", L"AllowManualMDMUnenrollment", &string);
    if ( OmadmValue < 0 )
    {
      v10 = 1423;
      goto LABEL_6;
    }
    v24 = 1;
    if ( (_DWORD)string != 1
      && (CorpDeviceManagementSettingsTelemetry::UnenrollmentBlocked<unsigned short const (&)[31]>(), (_DWORD)string != 1)
      || (v25 = *((_DWORD *)this + 82), v25 == 6)
      || v25 == 13 )
    {
      v24 = 0;
    }
    OmadmValue = SystemSettings::DataModel::PropValueHelper::CreateBoolean(v24, a3);
    if ( OmadmValue < 0 )
    {
      v10 = 1428;
      goto LABEL_6;
    }
    return 0;
  }
  return -2147024809;
}

```

## disassembly

```asm
0x1801ac3f0  push    rbp
0x1801ac3f2  push    rbx
0x1801ac3f3  push    rsi
0x1801ac3f4  push    rdi
0x1801ac3f5  mov     rbp, rsp
0x1801ac3f8  sub     rsp, 28h
0x1801ac3fc  mov     rdi, r8
0x1801ac3ff  mov     rbx, rdx
0x1801ac402  mov     rsi, rcx
0x1801ac405  mov     qword ptr [r8], 0
0x1801ac40c  lea     rdx, stru_1803198F0; HSTRING
0x1801ac413  mov     rcx, rbx; this
0x1801ac416  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801ac41b  test    al, al
0x1801ac41d  jz      short loc_1801AC433
0x1801ac41f  mov     rdx, rdi; struct IInspectable **
0x1801ac422  mov     rcx, [rsi+100h]; unsigned __int16 *
0x1801ac429  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1801ac42e  jmp     loc_1801AC828
0x1801ac433  lea     rdx, stru_18031D120; HSTRING
0x1801ac43a  mov     rcx, rbx; this
0x1801ac43d  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801ac442  test    al, al
0x1801ac444  jz      loc_1801AC52B
0x1801ac44a  mov     ecx, 3; unsigned int
0x1801ac44f  call    ?GetOmadmValue@CEnrollmentHelper@WorkplaceHandlers@SystemSettings@@SAJK@Z; SystemSettings::WorkplaceHandlers::CEnrollmentHelper::GetOmadmValue(ulong)
0x1801ac454  mov     ebx, eax
0x1801ac456  test    eax, eax
0x1801ac458  jns     short loc_1801AC479
0x1801ac45a  mov     edx, 552h; void *
0x1801ac45f  lea     r8, aShellSystemset_62; "shell\\systemsettingsthreshold\\handler"...
0x1801ac466  mov     r9d, ebx; char *
0x1801ac469  mov     rcx, [rbp+20h]; this
0x1801ac46d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ac472  mov     eax, ebx
0x1801ac474  jmp     loc_1801AC828
0x1801ac479  mov     rcx, cs:?_value@CEnrollmentHelper@WorkplaceHandlers@SystemSettings@@2PEAGEA; unsigned __int16 *
0x1801ac480  test    rcx, rcx
0x1801ac483  jnz     loc_1801AC513
0x1801ac489  call    cs:__imp_WindowsDeleteString
0x1801ac490  nop     dword ptr [rax+rax+00h]
0x1801ac495  mov     [rbp+string], 0
0x1801ac49d  lea     rdx, [rbp+string]; HSTRING *
0x1801ac4a1  lea     rcx, aSystemsettings_38; "SystemSettings_Workplace_CorpDeviceMana"...
0x1801ac4a8  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x1801ac4ad  mov     esi, eax
0x1801ac4af  mov     rbx, [rbp+string]
0x1801ac4b3  test    eax, eax
0x1801ac4b5  jns     short loc_1801AC4BE
0x1801ac4b7  mov     edx, 556h
0x1801ac4bc  jmp     short loc_1801AC4D4
0x1801ac4be  mov     rdx, rdi; struct IInspectable **
0x1801ac4c1  mov     rcx, rbx; HSTRING
0x1801ac4c4  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x1801ac4c9  mov     esi, eax
0x1801ac4cb  test    eax, eax
0x1801ac4cd  jns     short loc_1801AC4FD
0x1801ac4cf  mov     edx, 557h; void *
0x1801ac4d4  mov     r9d, eax; char *
0x1801ac4d7  lea     r8, aShellSystemset_62; "shell\\systemsettingsthreshold\\handler"...
0x1801ac4de  mov     rcx, [rbp+20h]; this
0x1801ac4e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ac4e7  mov     rcx, rbx; string
0x1801ac4ea  call    cs:__imp_WindowsDeleteString
0x1801ac4f1  nop     dword ptr [rax+rax+00h]
0x1801ac4f6  mov     eax, esi
0x1801ac4f8  jmp     loc_1801AC828
0x1801ac4fd  mov     rcx, rbx; string
0x1801ac500  call    cs:__imp_WindowsDeleteString
0x1801ac507  nop     dword ptr [rax+rax+00h]
0x1801ac50c  xor     eax, eax
0x1801ac50e  jmp     loc_1801AC828
0x1801ac513  mov     rdx, rdi; struct IInspectable **
0x1801ac516  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1801ac51b  mov     ebx, eax
0x1801ac51d  test    eax, eax
0x1801ac51f  jns     short loc_1801AC50C
0x1801ac521  mov     edx, 55Bh
0x1801ac526  jmp     loc_1801AC45F
0x1801ac52b  lea     rdx, stru_18031D3D8; HSTRING
0x1801ac532  mov     rcx, rbx; this
0x1801ac535  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801ac53a  test    al, al
0x1801ac53c  jz      loc_1801AC5DB
0x1801ac542  mov     ecx, 3; unsigned int
0x1801ac547  call    ?GetOmadmValue@CEnrollmentHelper@WorkplaceHandlers@SystemSettings@@SAJK@Z; SystemSettings::WorkplaceHandlers::CEnrollmentHelper::GetOmadmValue(ulong)
0x1801ac54c  mov     ebx, eax
0x1801ac54e  test    eax, eax
0x1801ac550  jns     short loc_1801AC55C
0x1801ac552  mov     edx, 560h
0x1801ac557  jmp     loc_1801AC45F
0x1801ac55c  mov     rcx, cs:?_value@CEnrollmentHelper@WorkplaceHandlers@SystemSettings@@2PEAGEA; unsigned __int16 *
0x1801ac563  test    rcx, rcx
0x1801ac566  jnz     short loc_1801AC5BF
0x1801ac568  call    cs:__imp_WindowsDeleteString
0x1801ac56f  nop     dword ptr [rax+rax+00h]
0x1801ac574  mov     [rbp+string], 0
0x1801ac57c  lea     rdx, [rbp+string]; HSTRING *
0x1801ac580  lea     rcx, aSystemsettings_1057; "SystemSettings_Workplace_CorpDeviceMana"...
0x1801ac587  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x1801ac58c  mov     esi, eax
0x1801ac58e  mov     rbx, [rbp+string]
0x1801ac592  test    eax, eax
0x1801ac594  jns     short loc_1801AC5A0
0x1801ac596  mov     edx, 564h
0x1801ac59b  jmp     loc_1801AC4D4
0x1801ac5a0  mov     rdx, rdi; struct IInspectable **
0x1801ac5a3  mov     rcx, rbx; HSTRING
0x1801ac5a6  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x1801ac5ab  mov     esi, eax
0x1801ac5ad  test    eax, eax
0x1801ac5af  jns     loc_1801AC4FD
0x1801ac5b5  mov     edx, 565h
0x1801ac5ba  jmp     loc_1801AC4D4
0x1801ac5bf  mov     rdx, rdi; struct IInspectable **
0x1801ac5c2  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1801ac5c7  mov     ebx, eax
0x1801ac5c9  test    eax, eax
0x1801ac5cb  jns     loc_1801AC50C
0x1801ac5d1  mov     edx, 569h
0x1801ac5d6  jmp     loc_1801AC45F
0x1801ac5db  lea     rdx, stru_18031D108; HSTRING
0x1801ac5e2  mov     rcx, rbx; this
0x1801ac5e5  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801ac5ea  test    al, al
0x1801ac5ec  jz      short loc_1801AC610
0x1801ac5ee  mov     rdx, rdi; struct IInspectable **
0x1801ac5f1  mov     cl, [rsi+14Ch]; unsigned __int8
0x1801ac5f7  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x1801ac5fc  mov     ebx, eax
0x1801ac5fe  test    eax, eax
0x1801ac600  jns     loc_1801AC50C
0x1801ac606  mov     edx, 56Eh
0x1801ac60b  jmp     loc_1801AC45F
0x1801ac610  lea     rdx, stru_1802EDCB0; HSTRING
0x1801ac617  mov     rcx, rbx; this
0x1801ac61a  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801ac61f  test    al, al
0x1801ac621  jz      loc_1801AC6AE
0x1801ac627  mov     [rbp+string], 0
0x1801ac62f  lea     rcx, [rbp+string]
0x1801ac633  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801ac638  lea     r8, [rbp+string]
0x1801ac63c  mov     edx, [rsi+148h]
0x1801ac642  mov     rcx, [rsi+130h]
0x1801ac649  call    ?CreateInstance@CEnrollmentRemoveProfileSetting@WorkplaceHandlers@SystemSettings@@SAJPEBGW4EnrollmentEnrollType@@PEAPEAV123@@Z; SystemSettings::WorkplaceHandlers::CEnrollmentRemoveProfileSetting::CreateInstance(ushort const *,EnrollmentEnrollType,SystemSettings::WorkplaceHandlers::CEnrollmentRemoveProfileSetting * *)
0x1801ac64e  mov     ebx, eax
0x1801ac650  test    eax, eax
0x1801ac652  jns     short loc_1801AC65B
0x1801ac654  mov     edx, 574h
0x1801ac659  jmp     short loc_1801AC67F
0x1801ac65b  mov     rcx, [rbp+string]
0x1801ac65f  mov     rax, [rcx]
0x1801ac662  mov     r8, rdi
0x1801ac665  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x1801ac66c  mov     rax, [rax]
0x1801ac66f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ac674  mov     ebx, eax
0x1801ac676  test    eax, eax
0x1801ac678  jns     short loc_1801AC6A0
0x1801ac67a  mov     edx, 575h; void *
0x1801ac67f  mov     r9d, eax; char *
0x1801ac682  lea     r8, aShellSystemset_62; "shell\\systemsettingsthreshold\\handler"...
0x1801ac689  mov     rcx, [rbp+20h]; this
0x1801ac68d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ac692  lea     rcx, [rbp+string]
0x1801ac696  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801ac69b  jmp     loc_1801AC472
0x1801ac6a0  lea     rcx, [rbp+string]
0x1801ac6a4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801ac6a9  jmp     loc_1801AC50C
0x1801ac6ae  lea     rdx, stru_18031D490; HSTRING
0x1801ac6b5  mov     rcx, rbx; this
0x1801ac6b8  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801ac6bd  test    al, al
0x1801ac6bf  jz      loc_1801AC797
0x1801ac6c5  mov     dword ptr [rbp+string], 0
0x1801ac6cc  lea     r8, [rbp+string]
0x1801ac6d0  lea     rdx, aAllowmanualmdm; "AllowManualMDMUnenrollment"
0x1801ac6d7  lea     rcx, aExperience; "Experience"
0x1801ac6de  call    cs:__imp_PolicyManager_GetPolicyInt
0x1801ac6e5  nop     dword ptr [rax+rax+00h]
0x1801ac6ea  mov     ebx, eax
0x1801ac6ec  test    eax, eax
0x1801ac6ee  jns     short loc_1801AC6FA
0x1801ac6f0  mov     edx, 57Ah
0x1801ac6f5  jmp     loc_1801AC45F
0x1801ac6fa  mov     ebx, 1
0x1801ac6ff  mov     rdx, rdi; struct IInspectable **
0x1801ac702  cmp     dword ptr [rbp+string], ebx
0x1801ac705  jz      short loc_1801AC727
0x1801ac707  lea     rcx, aCorpdevicemana_10; "CorpDeviceManagementRemoveNotAllowedTex"...
0x1801ac70e  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1801ac713  mov     ebx, eax
0x1801ac715  test    eax, eax
0x1801ac717  jns     loc_1801AC50C
0x1801ac71d  mov     edx, 57Dh
0x1801ac722  jmp     loc_1801AC45F
0x1801ac727  mov     eax, [rsi+148h]
0x1801ac72d  cmp     eax, 6
0x1801ac730  jnz     short loc_1801AC752
0x1801ac732  lea     rcx, aCorpdevicemana_8; "CorpDeviceManagementRemoveNotAllowedWor"...
0x1801ac739  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1801ac73e  mov     ebx, eax
0x1801ac740  test    eax, eax
0x1801ac742  jns     loc_1801AC50C
0x1801ac748  mov     edx, 581h
0x1801ac74d  jmp     loc_1801AC45F
0x1801ac752  cmp     eax, 0Dh
0x1801ac755  jnz     short loc_1801AC777
0x1801ac757  lea     rcx, aCorpdevicemana_5; "CorpDeviceManagementRemoveNotAllowedWor"...
0x1801ac75e  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1801ac763  mov     ebx, eax
0x1801ac765  test    eax, eax
0x1801ac767  jns     loc_1801AC50C
0x1801ac76d  mov     edx, 585h
0x1801ac772  jmp     loc_1801AC45F
0x1801ac777  lea     rcx, aCorpdevicemana_1; "CorpDeviceManagementRemoveText"
0x1801ac77e  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1801ac783  mov     ebx, eax
0x1801ac785  test    eax, eax
0x1801ac787  jns     loc_1801AC50C
0x1801ac78d  mov     edx, 589h
0x1801ac792  jmp     loc_1801AC45F
0x1801ac797  lea     rdx, stru_18031DB28; HSTRING
0x1801ac79e  mov     rcx, rbx; this
0x1801ac7a1  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801ac7a6  test    al, al
0x1801ac7a8  jz      short loc_1801AC823
0x1801ac7aa  mov     dword ptr [rbp+string], 0
0x1801ac7b1  lea     r8, [rbp+string]
0x1801ac7b5  lea     rdx, aAllowmanualmdm; "AllowManualMDMUnenrollment"
0x1801ac7bc  lea     rcx, aExperience; "Experience"
0x1801ac7c3  call    cs:__imp_PolicyManager_GetPolicyInt
0x1801ac7ca  nop     dword ptr [rax+rax+00h]
0x1801ac7cf  mov     ebx, eax
0x1801ac7d1  test    eax, eax
0x1801ac7d3  jns     short loc_1801AC7DF
0x1801ac7d5  mov     edx, 58Fh
0x1801ac7da  jmp     loc_1801AC45F
0x1801ac7df  mov     ebx, 1
0x1801ac7e4  cmp     dword ptr [rbp+string], ebx
0x1801ac7e7  jz      short loc_1801AC7F3
0x1801ac7e9  call    ??$UnenrollmentBlocked@AEAY0BP@$$CBG@CorpDeviceManagementSettingsTelemetry@@SAXAEAY0BP@$$CBG@Z; CorpDeviceManagementSettingsTelemetry::UnenrollmentBlocked<ushort const (&)[31]>(ushort const (&)[31])
0x1801ac7ee  cmp     dword ptr [rbp+string], ebx
0x1801ac7f1  jnz     short loc_1801AC803
0x1801ac7f3  mov     eax, [rsi+148h]
0x1801ac7f9  cmp     eax, 6
0x1801ac7fc  jz      short loc_1801AC803
0x1801ac7fe  cmp     eax, 0Dh
0x1801ac801  jnz     short loc_1801AC805
0x1801ac803  xor     bl, bl
0x1801ac805  mov     rdx, rdi; struct IInspectable **
0x1801ac808  mov     cl, bl; unsigned __int8
0x1801ac80a  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x1801ac80f  mov     ebx, eax
0x1801ac811  test    eax, eax
0x1801ac813  jns     loc_1801AC50C
0x1801ac819  mov     edx, 594h
0x1801ac81e  jmp     loc_1801AC45F
0x1801ac823  mov     eax, 80070057h
0x1801ac828  add     rsp, 28h
0x1801ac82c  pop     rdi
0x1801ac82d  pop     rsi
0x1801ac82e  pop     rbx
0x1801ac82f  pop     rbp
0x1801ac830  retn
```
